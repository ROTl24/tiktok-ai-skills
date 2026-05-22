# Output Quality Bar

Use this reference when producing a full ad package or testing whether the skill matches the source dialogue's quality level.

## Source Dialogue Success Pattern

The source dialogue is strong because it does all of the following:

1. Reads the product image first and names concrete visual/label details.
2. Asks six setup questions before the full plan when key parameters are missing.
3. If parameters are missing, asks the six setup questions after first explaining what is visible in the product image and recommending a default direction.
4. If the user supplies parameters, produces a complete Chinese-facing production plan with a title plus 13 numbered parts: 0 小白解释, 1 制作参数确认, 2 默认假设, 3 产品理解, 4 广告结构, 5 合规话术, 6 固定虚拟达人+参考图, 7 Hook 备选, 8 口播脚本, 9 B-roll, 10 Seedance Prompt, 11 素材表/字幕/音效/自检, 12 下一步操作.
5. Converts product features into user pain points and believable TikTok language.
6. Sounds like a strong creator seeding script, not a cautious compliance memo: the hooks, script, and CTA should feel like they are trying to sell.
7. Uses effect-led or contrast-led framing when the product supports it, such as before/after, old routine/new routine, clear/tinted, dry/glossy, dull/shiny, bulky/compact, or problem/result.
8. Uses U.S. TikTok-native spoken phrasing when American English is requested: casual first-person reactions, "wait okay", "hear me out", "I need to show you", "look at this", "POV", and direct CTA language.
9. Packs product-specific selling points tightly: visible packaging, physical design, applicator/lens/material/texture, use scene, sensory detail, label claims, and why the buyer should care.
10. Gives copyable prompts, not vague advice.
11. Maintains one fixed creator and one product reference throughout generation.
12. Gives fallback segment generation instructions if a 15-second single shot is unstable.

## Setup Question Mode Acceptance Bar

When required setup parameters are missing, the response should resemble the source dialogue's setup screen, not an internal planning note.

It must include:

- title `中文真人感UGC广告制作方案`
- first-person product read beginning like `我先看了你上传的产品图...`
- a clear reason for asking setup questions: avoiding wrong language, wrong platform, or wrong market assumptions
- heading `二、制作前必须确认的6件事`
- the six questions in order: market, platform, spoken language, voice form, fixed creator, duration
- platform examples by region when helpful
- heading `我建议的默认方向（仅供参考）`
- product-specific default recommendation with platform, style, creator, and key B-roll
- final shortcut sentence inviting the user to approve the default 15-second U.S. TikTok English on-camera version

It should not include:

- `参数确认模式`
- `简要计划`
- `验证点`
- standalone `图片识别`
- standalone `合规初判` for ordinary ecommerce products
- long proof or policy discussion before the user answers the six setup questions

For ordinary products with visible technical or protection claims, mention evidence needs only as a short embedded caution. Keep the response sales-oriented and product-specific; reserve the full compliance rewrite for section `5. 合规话术与发布前检查` in the complete package.

## Sales Energy Requirements

A full package should not become weaker just because it includes compliance. Section `5. 合规话术与发布前检查` should set boundaries; sections `7-10` should still sell hard inside those boundaries.

For ordinary ecommerce products:

- The recommended hook should lead with the strongest visible product moment or pain point.
- The main script should be the strongest credible version, not the most cautious version.
- The script should include a creator reaction line such as "look at this", "I did not expect this", "I get it now", "this is staying in my bag", or a category-appropriate equivalent.
- The B-roll should include the product's key proof shot, not only generic product beauty shots.
- The CTA should be clear and direct unless the user requests a softer brand-awareness video.

For claims that require substantiation, keep the selling effect by using a claim ladder:

1. Supported by image, label, landing page, or user notes: use the claim naturally.
2. Supported only by the generated/demo visual: phrase it as visible observation.
3. Supported only as personal creator experience: phrase it as "for me", "it feels", or "I like using it when...".
4. Unsupported safety, medical, guaranteed, certified, or quantified claim: keep it out of the main script and provide a punchy safe replacement.

## Minimum Full-Package Requirements

A full package is not acceptable if it lacks any of these:

- concrete product identification from the image
- target market, platform, spoken language, voice form, duration, ratio, creator, product image reference
- product-specific default assumptions
- product-specific pain points and reasons to believe
- compliance/claim rewrite section before script generation
- fixed creator reference prompt
- 8-10 native hooks in the spoken language, including strong creator-style and pain/contrast hooks
- timestamped 15-second script plus at least one backup version, with strong seeding energy and a clear CTA
- B-roll list with edit timing, including the key proof/demo shot and any credible contrast or result shot
- copyable AI video prompt with `@Image1` and `@Image3`
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
- keeps the same 0-12 full-package structure from the source dialogue
- gives a copyable prompt that could be adapted to another product of a different category

When a test product contains a technical, safety, protection, performance, medical, financial, or certification claim, the expected behavior is:

- describe only what is visible or provided by the user
- ask for proof before repeating exact certification or quantified protection claims
- rewrite risky wording into observable, experience-based wording that still sounds like a creator selling the product
- include the risk in the section `5. 合规话术与发布前检查`
