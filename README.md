# TikTok AI Skills

这是一个面向 TikTok / Reels / Shorts 短视频广告制作的 AI 技能仓库，当前包含 `tiktok-ugc-ad-maker` 技能。

## 项目用途

`tiktok-ugc-ad-maker` 用于把产品图片或产品说明转成中文可执行的 UGC 广告制作方案，包括：

- 产品理解与卖点转译
- 投放参数确认
- TikTok 风格 Hook 和口播脚本
- B-roll 镜头清单
- 分镜图生成表格与 JSON
- Seedance / 视频生成提示词
- 发布前合规检查清单

## 目录结构

```text
tiktok-ai-skills/
└── tiktok-ugc-ad-maker/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── general-tiktok-product-compliance.md
        ├── output-quality-bar.md
        └── us-tiktok-beauty-compliance.md
```

## 使用方式

在支持本地技能的 Codex / AI Agent 环境中加载本仓库后，可以通过 `tiktok-ugc-ad-maker` 技能生成 TikTok UGC 广告方案。

推荐输入信息：

- 产品图片或产品说明
- 目标国家 / 地区
- 发布平台
- 口播语言
- 声音形式：真人口播或旁白
- 是否已有固定达人参考图
- 是否已有分镜 / 场景风格参考图；如果没有，技能会生成 `@Image2`
- 视频时长

如果关键信息不完整，技能会先询问必要参数，再继续生成完整方案。

## 合规说明

本技能会根据产品品类做基础风险判断，并参考仓库内的合规文档处理普通商品、受限品类、美国 TikTok 美妆相关内容和 AIGC 标注要求。

实际投放前仍需核对目标市场、平台政策、落地页信息和广告主资质，避免使用未经证明的功效、安全、认证、价格或对比声明。

## 维护原则

- 保持输出面向真实投放和创意执行
- 优先使用具体产品信息，不写通用模板
- 不虚构产品成分、认证、测试结果或价格
- 合规提醒服务于广告可执行性，而不是替代正式法律审查
