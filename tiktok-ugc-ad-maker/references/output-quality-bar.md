# Output Quality Bar

Use this reference when producing a full ad package or testing whether the output matches the golden example's quality level. The golden example lives in `references/example-output.md`; treat it as the benchmark for tone, density, and structure — never copy its product details, hooks, or claims onto another product.

Section order, heading names, and per-section required elements are defined once in `SKILL.md` `Output Structure`. This file does not restate or renumber them; if this file and `SKILL.md` ever disagree, `SKILL.md` wins.

## Target Output Pattern

A strong output does all of the following (see the golden example for how this reads in practice):

1. Reads the product image first and names concrete visual/label details.
2. When key parameters are missing, asks the six setup questions after first explaining what is visible in the product image and recommending a default direction.
3. When the user supplies parameters or approves defaults, produces a complete Chinese-facing production plan following the Title + sections `0`-`13` order defined in `SKILL.md` `Output Structure`.
4. Converts product features into user pain points and believable platform-native language.
5. Sounds like a strong creator seeding script, not a cautious compliance memo: the hooks, script, and CTA should feel like they are trying to sell.
6. Uses effect-led or contrast-led framing when the product supports it, such as before/after, old routine/new routine, clear/tinted, dry/glossy, dull/shiny, bulky/compact, or problem/result.
7. Uses spoken phrasing native to the requested platform and language, per the phrase guidance in `SKILL.md` `Quality Gate`.
8. Packs product-specific selling points tightly: visible packaging, physical design, applicator/lens/material/texture, use scene, sensory detail, label claims, and why the buyer should care.
9. Gives copyable prompts, not vague advice.
10. Maintains one fixed creator (`@Image1`), one storyboard scene/style reference (`@Image2`), and one product reference (`@Image3`) throughout generation.
11. Uses the storyboard JSON as the source of truth for the spoken script, B-roll, and video prompt, and proves it with a passing `分镜一致性核对表`.
12. Gives fallback sub-segment instructions when single-take generation is unstable.

## Setup Question Mode Acceptance Bar

When required setup parameters are missing, the response should resemble the golden example's setup screen, not an internal planning note.

It must include:

- title `中文真人感UGC广告制作方案`
- first-person product read beginning like `我先看了你上传的产品图...`
- a clear reason for asking setup questions: avoiding wrong language, wrong platform, or wrong market assumptions
- heading `二、制作前必须确认的6件事`
- the six questions in order: market, platform, spoken language, voice form, fixed creator, duration
- the platform question may fold in 投放方式 (organic vs paid) and TikTok Shop 挂车 sub-asks without changing the six-question count
- platform examples by region when helpful
- heading `我建议的默认方向（仅供参考）`
- product-specific default recommendation with platform, style, creator, key B-roll, and optional `@Image2` scene/style reference guidance
- final shortcut sentence inviting the user to approve the default 15-second U.S. TikTok English on-camera version

It should not include:

- `参数确认模式`
- `简要计划`
- `验证点`
- standalone `图片识别`
- standalone `合规初判` for ordinary ecommerce products
- long proof or policy discussion before the user answers the six setup questions

For ordinary products with visible technical or protection claims, mention evidence needs only as a short embedded caution. Keep the response sales-oriented and product-specific; reserve the full compliance rewrite for section `5. 信息缺失/合规话术` in the complete package.

## Full Package Acceptance Bar

The package must follow `SKILL.md` `Output Structure` exactly. On top of that, verify these cross-cutting checks:

- first line exactly `中文真人感UGC广告制作方案`, followed by a compact source-style subtitle, with the duration in the subtitle matching the user's request
- no preface before section `0`; no `执行假设`, `权衡`, `简要计划`, or code-task `验证说明`
- the section-`5` heading switches correctly between `信息缺失，这个需要补充` and `合规话术与发布前检查`
- exactly 10 hooks, grouped by testing angle, with 1-2 recommended
- the storyboard table includes the `时间` column and uses only the allowed 景别/运镜 vocabulary from `SKILL.md`
- no separate storyboard-to-execution alignment table: per-shot 口播/B-roll/Seedance data lives in the storyboard JSON
- every storyboard JSON shot lists only the reference images it needs, not all three by default
- the primary script matches the requested duration, and every timestamp block maps to a storyboard shot ID
- every B-roll row maps to a storyboard shot ID; extra inserts are marked `fallback insert` with a reason
- the video prompt reuses storyboard shots instead of inventing new core shots; additions are marked as fallback sub-segments
- section `12` opens with a `分镜一致性核对表` and every shot passes
- when the creator is AI-designed: the AIGC label note is present and the script contains no fabricated usage-history testimony
- the music decision names a commercially cleared source

It should avoid:

- bolding every section heading as if it were a report
- colon-heavy title format such as `中文真人感 UGC 广告制作方案：...`
- moving compliance caveats into the opening assumptions
- generic B-roll bullets without duration, speech state, and edit position
- video prompts that ignore the storyboard JSON, change the shot order, or introduce new core shots without marking them as fallback
- naming the prompt section `AI 视频生成 Prompt` when the requested/default model is Seedance
- ending with development-process notes such as lint/test status

## Sales Energy Requirements

A full package should not become weaker just because it includes compliance. Section `5. 信息缺失/合规话术` should set boundaries; the hook, script, B-roll, and video-prompt sections should still sell hard inside those boundaries.

For ordinary ecommerce products:

- The recommended hook should lead with the strongest visible product moment or pain point.
- The main script should be the strongest credible version, not the most cautious version.
- The script should include a creator reaction line such as "look at this", "I did not expect this", "I get it now", "this is staying in my bag", or a category-appropriate equivalent.
- The B-roll should include the product's key proof shot, not only generic product beauty shots.
- The CTA should be clear, direct, and matched to the purchase mechanism (product card, bio link, or comments) unless the user requests a softer brand-awareness video.

For claims that require substantiation, apply the claim ladder defined once in `SKILL.md` `Sales Energy Rules`, including its AI virtual creator testimony rule. Do not restate the ladder here.

## Minimum Full-Package Requirements

A full package is not acceptable if it lacks any of these:

- concrete product identification from the image
- target market, platform, 投放方式/挂车, spoken language, voice form, duration, ratio, creator, product image reference
- product-specific default assumptions
- product-specific pain points and reasons to believe
- missing-info/compliance/claim rewrite content before script generation, including disclosure, AIGC, and music-rights notes when relevant
- fixed creator reference prompt
- 10 native hooks in the spoken language, including strong creator-style and pain/contrast hooks
- a timestamped primary script at the requested duration plus at least one backup version, with strong seeding energy and a clear CTA
- B-roll list with edit timing, including the key proof/demo shot and any credible contrast or result shot
- storyboard table and JSON that include `@Image2` as the scene/style reference and per-shot reference subsets
- copyable AI video prompt with `@Image1`, `@Image2`, and `@Image3` adapted to the target model
- a passing `分镜一致性核对表` linking storyboard shot IDs, spoken lines, B-roll rows, and video-prompt blocks
- subtitles, sound effects, QC checklist, and next steps

## General Product Test Protocol

Use real product images as tests, but do not write product-specific rules into the skill unless the pattern applies broadly across categories.

For each test image, verify that the output:

- names visible product details instead of guessing hidden specs
- chooses a creator archetype that matches the likely buyer and scene
- turns visible features into believable UGC hooks, pain points, B-roll, and video prompts
- preserves strong sales energy instead of defaulting to bland safety language
- packs product-specific selling points into the hook, product understanding, script, B-roll, and prompt
- separates ordinary observable claims from claims needing evidence
- avoids making a category-specific branch for a single uploaded product
- keeps the full-package structure defined in `SKILL.md` `Output Structure`
- reads close to the golden example's density and energy without copying its product details
- gives a copyable prompt that could be adapted to another product of a different category
- reuses the storyboard JSON in B-roll, script, and video prompt instead of treating it as a standalone table

When a test product contains a technical, safety, protection, performance, medical, financial, or certification claim, the expected behavior is:

- describe only what is visible or provided by the user
- ask for proof before repeating exact certification or quantified protection claims
- rewrite risky wording into observable, experience-based wording that still sounds like a creator selling the product
- include the risk in section `5. 信息缺失/合规话术`
