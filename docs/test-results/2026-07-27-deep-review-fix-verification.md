# 深度审查修复验证结果

测试日期：2026-07-27

## 修复范围

本次修复覆盖 2026-07-27 深度审查发现的五层问题。SKILL.md frontmatter 自本次起加入 `version` 字段（1.1.0；此前未标注版本的状态视为 1.0.0）。

### 第一层：规范 bug

| 问题 | 修复结果 |
|---|---|
| SKILL.md section 11 写 "storyboard shot IDs from section `10`"（P1 重排残留，应为 section 8） | 已改为 `from section 8` |
| Section 7 标题"10条" vs 正文 "8-10 hooks" 矛盾 | 统一为 exactly 10 hooks（SKILL.md 与 quality bar 同步） |
| 15 秒硬编码 vs 30/45 秒选项无结构适配 | 口播脚本改为按请求时长命名主版本；section 4 增加 30/45 秒扩展规则；Seedance 增加分段长度建议（每段 5-10 秒）；quality bar 改为 requested duration |
| JSON schema 示例 `参考图` 全选三张 | 示例改为子集，并新增"按镜头实际需要选参考图"指令 |

### 第二层：虚拟达人 × 个人体验话术矛盾

- SKILL.md Sales Energy Rules 新增 AI virtual creator testimony rule：AI 虚拟达人不得编造使用史类证言，改用可观察演示、镜头内即时反应或产品事实；镜头内当场测试可以，编造历史不行。
- 规则联动到：Quality Gate、section 5（AIGC 标注）、section 6（达人设定）、section 9（口播）、quality bar、`us-tiktok-beauty-compliance.md`（FTC 段）、`general-tiktok-product-compliance.md`（AIGC 段）、`cn-douyin-compliance.md`（AIGC 段）。

### 第三层：维护脆弱性

- 章节编号与结构改为只在 SKILL.md `Output Structure` 定义一次；`output-quality-bar.md` 全部按章节名称引用，删除了三处完整的 0-13 编号复述，并声明冲突时以 SKILL.md 为准。
- Claim ladder 只保留 SKILL.md 一份权威版本，quality bar 改为引用。
- "source dialogue" 幽灵引用清除：新增金标准样例 `references/example-output.md`（Setup Question 示例 + 完整 14 节示例，产品沿用此前测试输入"磁吸理线夹"），SKILL.md 和 quality bar 全部改为引用金标准样例。

### 第四层：工作流

- 新增 Staged delivery（Workflow step 10）：用户要求先确认分镜时，先出 Title-第8节，确认后再出 9-13。
- 新增 Incremental Update Mode：分镜级修改先改 JSON 再联动重出下游模块；下游修改只改对应模块并确认镜头 ID 对齐。
- 新增 Hook Variant Mode：只换镜头1和开头口播，产出 V1/V2/V3 变体，其余复用。
- 新增闭环自检输出：section 12 开头强制输出 `分镜一致性核对表`（镜头×口播/B-roll/Seedance），Workflow step 11 要求交付前核对。
- 删除分镜-执行对齐表：镜头信息从写三遍降为两遍（分镜表 + JSON），JSON 字段在 9/10/11 节渲染；分镜表增加 `时间` 列。
- 运镜词表扩展为 推/拉/摇/移/跟/手持晃动/静；景别增加 近景。

### 第五层：领域覆盖

- 新增 `references/cn-douyin-compliance.md`：广告法绝对化用语、品类规则、价格促销、广告标识、中国 AIGC 标识（含 2025-09-01 施行的标识办法）、安全改写示例。
- Workflow step 7 增加中国市场路由，并如实声明覆盖深度不对称（美国最深、中国基础、其他市场通用规则+现场核对）。
- TikTok Shop / 付费 vs 自然流量：进入第 2 问（发布平台）子问项、section 1 参数表、CTA 机制匹配规则、Useful Defaults、`general-tiktok-product-compliance.md` 新增 "Paid Ads, Organic Seeding, and TikTok Shop" 一节。
- 音乐版权：`general-tiktok-product-compliance.md` 新增 "Music and Audio Rights"（Commercial Music Library 规则）；SKILL.md section 5 新增音乐版权项、section 12 音乐决策必须注明可商用来源。
- 合规文档时效：三份合规文档头部加 `Last reviewed: 2026-07` 与重新核对指令。
- Seedance 适配：新增"@ImageN 是引用约定而非各工具通用语法，需按目标模型实际机制适配并核对段长/多参考图/口播能力"的说明。

### 小项

- Frontmatter description 重写：删除 "/skill" 泛触发词与 "turns an AI-user dialogue into an ad-making skill" 历史遗留，补充中文触发词（带货/种草视频、口播稿、分镜、hook 变体等）。
- Section 0 增加"熟悉术语可跳过"提示。
- 新增 `references/iteration-playbook.md`（指标解读、决策树、测试节奏、如何向技能提需求），section 13 增加发布后复盘步骤。
- 新增 `.gitattributes`（文本文件统一 LF，防中文乱码/换行漂移）。
- README 全面同步（目录树、六问、三种交互模式、合规深度声明、维护原则新增"编号单点定义"与"金标准样例同步"两条）。

## 验证方式

文本级结构验收（本仓库无可执行应用与 lint/test）。检查命令基于 ripgrep 内容搜索。

| # | 检查项 | 结果 |
|---|---|---|
| 1 | `from section \`10\`` 不再出现于 SKILL.md | 通过（0 处） |
| 2 | `8-10 hooks` / `sections \`7-10\`` 不再出现 | 通过（0 处） |
| 3 | "source dialogue" 仅剩 example-output.md 中一处历史说明 | 通过 |
| 4 | "alignment table" 仅出现在两条禁止性规则中（SKILL.md、quality bar） | 通过 |
| 5 | quality bar 不再硬编码 "15-second script" | 通过（0 处） |
| 6 | `分镜一致性核对表` / testimony rule / Commercial Music Library / cn-douyin 路由在各文件到位 | 通过（6 文件 28 处） |
| 7 | `exactly 10 hooks`、`version: 1.1.0`、参考图子集指令、Staged delivery、两个新 Mode、`Last reviewed: 2026-07` 到位 | 通过（6 文件 16 处） |
| 8 | 金标准样例遵守全部新规则（时间列分镜表、无对齐表、参考图子集、核对表、AI 达人无使用史证言、CML 音乐、信息缺失标题变体） | 通过（人工核对） |

## 遗留说明

- 金标准样例成为新的回归基准：后续修改 SKILL.md 结构时，需用同一测试输入重新生成并与样例对比结构。
- `cn-douyin-compliance.md` 仅覆盖长期稳定红线，平台细则以抖音规则中心为准。
- 两份存量合规文档当前为 CRLF，`.gitattributes` 生效后 git 下次触碰时将自动归一为 LF（git status 的警告即此含义，属预期行为）。
