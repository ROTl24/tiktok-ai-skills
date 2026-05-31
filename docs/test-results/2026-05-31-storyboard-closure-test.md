# TikTok UGC Skill 分镜闭环测试结果

测试日期：2026-05-31

## 测试目标

确认 `tiktok-ugc-ad-maker` 在加入 `@Image2` 后，是否形成稳定闭环：

- `@Image1` 固定达人参考图
- `@Image2` 分镜场景 / 风格参考图
- `@Image3` 产品图
- 分镜图表格与 JSON 能否作为口播脚本、B-roll、Seedance Prompt 的源数据

## 测试方式

本次是文档级结构验收，不生成真实广告成片。原因是该仓库是本地 AI Skill 文档仓库，没有可执行应用、测试脚本或 `package.json`。

检查对象：

- `README.md`
- `tiktok-ugc-ad-maker/SKILL.md`
- `tiktok-ugc-ad-maker/references/output-quality-bar.md`

模拟输入：

```text
产品：磁吸数据线收纳夹，黑白两色，桌面整理用品
目标市场：美国
发布平台：TikTok
口播语言：American English
声音形式：真人口播
达人：无固定达人，由 AI 生成
视频时长：15 秒
产品图：@Image3
```

## 验收项

| # | 验收项 | 结果 | 说明 |
|---|---|---|---|
| 1 | 文档定义了 `@Image1/@Image2/@Image3` 的角色 | 通过 | `SKILL.md` 已定义三类参考图 |
| 2 | `@Image2` 不会被误用为产品图或达人图 | 通过 | `SKILL.md` 已明确禁止，除非用户改约定 |
| 3 | 分镜模块要求输出 `@Image2` 场景/风格提示词 | 通过 | section `10. 分镜图生成` 已增加该要求 |
| 4 | 分镜 JSON 包含 `image_references` 和 `image2_scene_style_prompt` | 通过 | JSON schema 已包含 |
| 5 | B-roll 表格要求映射分镜镜头 ID | 通过 | section `9. B-roll 镜头清单` 已增加 `对应分镜镜头` |
| 6 | Seedance Prompt 要求使用分镜 JSON | 通过 | section `11. Seedance Prompt` 已明确要求 |
| 7 | 质量标准会拒绝忽略分镜 JSON 的 Seedance Prompt | 通过 | `output-quality-bar.md` 已增加避免项 |
| 8 | 用户可在 README 中理解 `@Image2` 用途 | 通过 | README 已补充场景风格参考图说明 |
| 9 | 输出顺序支持“分镜 JSON 是脚本源数据” | 未通过 | 口播脚本和 B-roll 仍排在分镜模块之前 |

## 发现的问题

### P1：输出顺序和“分镜 JSON 源数据”规则冲突

当前 `SKILL.md` 的用户输出顺序是：

```text
8. 口播脚本
9. B-roll 镜头清单
10. 分镜图生成
11. Seedance Prompt
```

但同一份文档又要求：

```text
分镜 JSON 是口播脚本、B-roll、Seedance Prompt 的源数据。
```

这会造成执行歧义：模型可能先写口播和 B-roll，再补分镜 JSON，导致分镜仍然只是“后置解释”，没有真正驱动脚本和视频生成。

建议修复方向二选一：

1. 推荐：把 `10. 分镜图生成` 提前到口播和 B-roll 之前，形成 `分镜 -> 口播 -> B-roll -> Seedance`。
2. 保留当前用户展示顺序，但在 Workflow 中明确“先内部生成 storyboard JSON，再按用户展示顺序输出”，并要求 section 8/9 引用内部镜头 ID。

### P2：Setup Question Mode 没有暴露 `@Image2`

Setup Question Mode 仍只问六个必填项，其中包括 `@Image1` 固定达人，但没有提示用户可以上传或指定场景/风格参考图。

这不是阻断问题，因为技能可以自动生成 `@Image2`，但如果用户已有参考场景图，当前流程不会主动收集。

建议：保持六个必填问题不变，额外在默认方向里补一句：

```text
如果你有想模仿的场景/画风参考图，也可以作为 @Image2 发给我；没有的话我会根据分镜自动生成。
```

### P3：质量标准里有一处旧范围描述

`output-quality-bar.md` 中仍写着：

```text
sections `7-10` should still sell hard
```

但现在 section `10` 是分镜图生成，Seedance Prompt 已变成 section `11`。这句话不影响执行，但容易让维护者误解销售能量检查范围。

建议改为：

```text
sections `7-11` should still sell hard inside those boundaries.
```

## 结论

`@Image2` 的角色定义和分镜闭环规则已经建立，但当前仍有一个关键结构问题：用户输出顺序没有真正把分镜 JSON 放在口播和 B-roll 之前。

如果要让系统稳定按“分镜 JSON -> 脚本/B-roll/Seedance”的方式工作，下一步应先修复 P1。
