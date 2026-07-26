# TikTok AI Skills

这是一个面向 TikTok / Reels / Shorts 短视频广告制作的 AI 技能仓库，当前包含 `tiktok-ugc-ad-maker` 技能。

## 项目用途

`tiktok-ugc-ad-maker` 用于把产品图片或产品说明转成中文可执行的 UGC 广告制作方案，包括：

- 产品理解与卖点转译
- 投放参数确认（含投放方式与 TikTok Shop 挂车）
- TikTok 风格 Hook 和口播脚本（支持 Hook A/B 变体批量生成）
- B-roll 镜头清单
- 分镜图生成表格与 JSON（作为口播/B-roll/视频提示词的源数据，并输出分镜一致性核对表）
- Seedance / 视频生成提示词
- 发布前合规检查清单（含披露、AIGC 标注、音乐版权）
- 发布后数据复盘与迭代建议

## 目录结构

```text
tiktok-ai-skills/
├── docs/
│   └── test-results/
└── tiktok-ugc-ad-maker/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── general-tiktok-product-compliance.md
        ├── us-tiktok-beauty-compliance.md
        ├── cn-douyin-compliance.md
        ├── output-quality-bar.md
        ├── example-output.md
        └── iteration-playbook.md
```

## 使用方式

在支持本地技能的 Codex / Claude Code / AI Agent 环境中加载本仓库后，可以通过 `tiktok-ugc-ad-maker` 技能生成 TikTok UGC 广告方案。

技能开始前会确认 6 个关键参数：

- 投放国家 / 地区
- 发布平台（含自然种草还是付费投放、是否挂 TikTok Shop 商品卡）
- 口播语言
- 声音形式：真人口播或旁白
- 是否已有固定达人参考图（`@Image1`）；没有则设计虚拟达人
- 视频时长（15s / 30s / 45s）

可选补充：分镜 / 场景风格参考图（`@Image2`，没有则由分镜自动生成）、落地页链接、合作关系（受赠 / 佣金）。

如果关键信息不完整，技能会先询问必要参数，再继续生成完整方案。也支持：

- 分段交付：先出分镜确认，再出口播 / B-roll / 视频提示词
- 增量更新：改某个镜头或 hook 时联动更新受影响的下游模块并重出核对表
- Hook 变体：只换开头做 A/B 测试，其余复用

## 合规说明

本技能会根据产品品类做基础风险判断，并参考仓库内的合规文档处理普通商品、受限品类、披露与 AIGC 标注、音乐版权等问题。合规覆盖深度目前不对称：

- 美国 TikTok：覆盖最深（含美妆专项、FTC 披露、FDA 化妆品宣称边界）
- 中国抖音：提供基础参考（广告法绝对化用语、品类规则、价格促销、AIGC 标识）
- 其他市场：按通用规则处理，并提示核对当地平台政策

当达人为 AI 生成的虚拟达人时，技能会应用"虚拟达人证言规则"：不编造使用史类第一人称证言，改用可观察演示与镜头内即时反应，并要求开启 AIGC 标注。

实际投放前仍需核对目标市场、平台政策、落地页信息和广告主资质，避免使用未经证明的功效、安全、认证、价格或对比声明。合规文档头部标注了最后核对日期，间隔较久或涉及受限品类、AIGC 标注、TikTok Shop 时请先核对官方最新政策。

## 维护原则

- 保持输出面向真实投放和创意执行
- 优先使用具体产品信息，不写通用模板
- 不虚构产品成分、认证、测试结果或价格
- 合规提醒服务于广告可执行性，而不是替代正式法律审查
- 章节编号与输出结构只在 `SKILL.md` 定义一次，其他文档按名称引用，避免同步漂移
- `references/example-output.md` 是输出质量基准（金标准样例）；修改 `SKILL.md` 结构后需同步更新样例，并在 `docs/test-results/` 留验收记录
