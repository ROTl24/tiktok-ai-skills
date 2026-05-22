---
name: tiktok-ugc-ad-maker
description: Create Chinese-facing TikTok/short-video UGC ad production plans from product images or product notes across ecommerce product categories. Use when the user asks for /skill, 真人感UGC广告, TikTok/Reels/Shorts scripts, hooks, B-roll shot lists, virtual creator setup, Seedance/Midjourney/video-generation prompts, product-category compliance checks, or a reusable workflow that turns an AI-user dialogue into an ad-making skill.
---

# TikTok UGC Ad Maker

## Workflow

Produce a complete, practical UGC ad package in Chinese for any product category that can be responsibly promoted. Keep the output specific to the uploaded product and requested market; do not add unrelated future features.

1. Inspect the product image or product notes first.
2. Classify the product category and risk level before writing hooks or claims. Read `references/general-tiktok-product-compliance.md` for category routing, restricted/prohibited categories, disclosure rules, AIGC notes, and landing-page consistency.
3. If the product appears prohibited, illegal, counterfeit, unsafe, or too regulated to assess from the available information, do not write a promotional ad. Explain the blocker and ask for proof, category clarification, or a safer non-promotional alternative.
4. If the product is restricted, sensitive, newly regulated, or not clearly covered by bundled references, verify current official TikTok and market-specific policy sources before producing direct-response ad copy. Ask for required market, age-gating, business verification, substantiation, and legal/approval details.
5. If any of these six items are missing, use Setup Question Mode before writing the full plan unless the user explicitly asks you to decide by default:
   - target country or region
   - publishing platform
   - spoken language
   - voice format: on-camera dialogue or voiceover
   - fixed creator reference: uploaded creator image or AI-designed virtual creator
   - duration
6. If the user asks you to decide, state the default assumptions briefly and continue.
7. For U.S. TikTok beauty, skincare, lip care, health-adjacent, influencer, or AI-generated creator content, also read `references/us-tiktok-beauty-compliance.md` before drafting claims, comparisons, disclosures, or AIGC notes.
8. Read `references/output-quality-bar.md` when producing a full ad package or testing whether output matches the source dialogue's quality level.
9. Generate the ad package with the fixed section order below.
10. End with an execution checklist the user can follow immediately.

## Quality Gate

Before finalizing a full ad package, verify it would pass these checks:

- It starts from the actual product image details, not a generic ecommerce template.
- It either asks the six setup questions first or states explicit defaults when the user authorized default decisions.
- Every section includes product-specific details, not placeholders such as "show product", "highlight benefits", or "add CTA".
- The output feels like a strong TikTok seeding script, not a cautious compliance memo: hooks, product understanding, script, B-roll, and CTA should push the strongest credible reason to buy.
- For ordinary products with visible demo potential, use a contrast/result/demo angle by default: before vs after, indoor vs outdoor, problem vs quick fix, old routine vs new routine, or first impression vs reaction.
- Product selling points should be densely packed but still grounded: include visible packaging, physical design, texture/material, scent/color/finish, usage scene, routine fit, and the strongest provided label claims when they are available.
- Spoken lines should sound platform-native: use casual U.S. TikTok phrasing such as "wait okay", "hear me out", "I need to show you", "look at this", "POV", "I'm keeping this in my bag", and natural direct CTAs when appropriate.
- The creator profile, scene, wardrobe, tone, hooks, script, B-roll, and AI video prompt match the product category and target buyer.
- The AI video prompt uses consistent reference placeholders: `@Image1` for the fixed creator and `@Image3` for the product image, unless the user supplies a different convention.
- The Seedance/video prompt is directly copyable and includes timestamped action blocks, audio, spoken lines, and fallback sub-segments.
- The final checklist includes product-identity, first-2-second hook, creator consistency, key physical selling point, before/after or demo honesty, platform-native voice, CTA clarity, disclosure, and AIGC label checks.

## Sales Energy Rules

The source dialogue's effect is strong because it sounds like a creator trying to sell a product she is excited about. Preserve that energy while staying within claim limits.

- Default to "strong seeding" language for ordinary ecommerce products: excited first-person experience, visible demo, reason-to-believe stack, and a clear purchase action.
- Do not make the main script over-cautious. Put proof caveats in section `5. 信息缺失/合规话术`; keep the spoken script punchy and creator-like.
- When a claim needs proof, use a claim ladder instead of flattening the ad:
  - If the product image, label, landing page, or user notes support it, the script may say the claim directly in natural language.
  - If only the demo can show it, phrase it as what the viewer can observe: "look how...", "you can see...", "it goes from... to...".
  - If only the creator can personally feel it, phrase it as personal experience: "for me", "it feels", "I like using it when...".
  - If the claim is unverified safety, medical, guaranteed result, certification, or quantified performance, move it to the compliance section and write a safer punchy alternative for the script.
- For before/after or effect-led products, include the strongest credible transformation in the hook, script, B-roll, and Seedance prompt. Examples of transformation formats: dry to glossy, clear to tinted, messy to organized, dull to shiny, bulky to compact, slow to easy, ordinary to premium.
- Prefer direct-response CTA when the platform and market fit it: "linked in my bio", "shop it now", "check the comments", "go look at the details", or the user's requested CTA.

## Setup Question Mode

When the user uploads a product image and says `/skill` or asks for a plan but has not provided the six required setup items:

Use the same user-facing rhythm as the source dialogue. This mode is not a place to expose the agent's work plan.

Required setup-question format:

1. Start with the title `中文真人感UGC广告制作方案`.
2. Open with a first-person product-image read: `我先看了你上传的产品图...`. In 2-4 concrete sentences, name the product/category, visible packaging or physical design, label text or scene cues, and likely market/style positioning. Translate visible features into sales intuition, not only neutral facts.
3. Add this transition sentence, adapted only if the input was product notes instead of an image: `在我开始帮你做完整方案之前，需要先确认6个关键信息，避免做出错语言、错平台的视频。你回答完我马上出完整方案：`
4. Add the heading `二、制作前必须确认的6件事`.
5. Ask the six questions in this exact order:
   - 投放国家/地区? Include product-specific clues only when visible, then ask whether the user wants U.S., China, Southeast Asia, Europe, Latin America, or another market.
   - 发布平台? Include region examples when useful, such as U.S./Europe > TikTok, Instagram Reels, YouTube Shorts, Amazon; China > Douyin, Xiaohongshu, Taobao; Southeast Asia > TikTok, Shopee.
   - 成片口播用什么语言? Give realistic options based on the likely market.
   - 想要哪种声音形式? Contrast on-camera creator dialogue with voiceover over product/hand/detail shots.
   - 是否已经有固定达人? If yes, ask for the creator reference as `@Image1`; if no, say you will design one virtual creator.
   - 视频时长想要多少? Offer 15s, 30s, and 45s with brief use cases.
6. Add the heading `我建议的默认方向（仅供参考）` and give a compact product-specific recommendation covering platform, style, creator, and key B-roll. Make it feel like a useful creative recommendation, not a compliance memo.
7. End with: `请告诉我上面6个问题的答案，或者直接回复“你帮我默认决定，先给我一版美国TikTok英文真人口播15秒版本”，我就立刻按默认假设出完整方案。`

Do not include sections titled `参数确认模式`, `简要计划`, `图片识别`, `合规初判`, or `验证点` in Setup Question Mode. If the product is ordinary ecommerce, keep compliance notes out of this setup response except for one short embedded caution when a visible claim clearly needs proof. Save the full compliance discussion for section `5. 信息缺失/合规话术` in the complete package. If the product is restricted, prohibited, unsafe, or unclear, follow the workflow blocker rules instead of using this normal setup-question format.

## Output Structure

Use this order unless the user asks for another format:

Full package mode is a user-facing production document. Do not expose internal planning or engineering workflow. Do not add opening sections such as `执行假设`, `权衡`, `简要计划`, or final notes such as `验证说明`, lint, test, or code-change status. Start at the title, then section `0`.

Title
   First line exactly `中文真人感UGC广告制作方案`. Second line should be a compact source-style subtitle such as `产品名·美国TikTok15秒真人口播` or `产品名·美国TikTok15秒旁白种草`. Avoid colon-heavy report titles such as `中文真人感 UGC 广告制作方案：...`. Ensure the duration in the title matches the user's request.

0. 小白解释（先把术语讲清楚）
   Explain only the terms needed for this task, such as UGC, Hook, B-roll, CTA, 真人口播, and Segment. For each term, add why it matters for TikTok conversion or video generation, not just a dictionary definition.

1. 制作参数确认
   Confirm the user's choices in a two-column table-like block with `项目` and `确认结果`. Include at least 投放国家, 发布平台, 成片口播语言, 声音形式, 视频时长/Segment count, 画面比例, 达人, 产品图.

2. 我替你做的默认假设
   List defaults you chose because the user did not specify them. Focus on 达人, 场景, 风格, CTA, 核心情绪, and why those defaults fit the product. Keep this honest and editable, and end with a short sentence like `如果不喜欢以上任何一项，告诉我我改。` Do not put proof gaps, UV/certification caveats, or other compliance-heavy material here unless one short caution is necessary; save that for section `5`.

3. 产品理解（翻译成人话）
   Translate product features into user-facing benefits and pain points. Separate:
   - 产品是什么
   - 用户为什么需要它
   - 用户现在的痛点
   - 这条广告要让用户相信什么
   - 最后要用户做什么

   Write this section with sales density. Do not stop at safe factual description. Convert each visible or provided product feature into a buyer-facing reason to care, including:
   - physical hook: shape, applicator, lens, texture, color, packaging, size, material, or visual mechanism
   - emotional hook: why the user would feel smart, upgraded, relieved, prettier, more prepared, cleaner, faster, or more put-together
   - routine hook: where it lives, when it is used, what old habit it replaces, and why it is convenient
   - proof hook: what the viewer can actually see in the demo or what the label/user-provided notes support

4. 广告结构
   Start with `选用: ...` and `为什么选这个: ...`. Prefer hook-body-close, before/after, problem/product/result, or contrast-led TikTok structures over neutral explainers. Then provide a table-like timeline with columns `时间`, `内容`, and `目的`. For 15-second product ads, a common structure is:
   - 0:00-0:02 hook with product, use case, problem, result, or surprising line
   - 0:02-0:05 product reveal and context
   - 0:05-0:10 use/demo/proof shot
   - 0:10-0:13 result, reaction, or strongest reason to care
   - 0:13-0:15 CTA

   For ordinary products with a visible result or use demonstration, prefer a strong TikTok sales structure over a neutral explainer:
   - before/after contrast
   - problem/product/result
   - "I did not expect this" reveal
   - routine upgrade
   - side-by-side comparison with the old habit

5. 信息缺失与合规话术
   Include this before creator/reference setup so the later script does not inherit risky claims. If key evidence, landing-page details, pricing, specs, or claim proof is missing, use the source-style heading `5. 信息缺失，这个需要补充` and list exactly what the user should verify. If nothing material is missing, use `5. 合规话术与发布前检查`.

   Include:
   - 品类判断: ordinary, restricted/sensitive, prohibited/high-risk, or unclear. State the product category in plain Chinese without creating a one-off rule for the current product.
   - 可说: observable product facts, use cases, sensory experience, convenience, design, material, routine fit, and personal experience that the creator could honestly support.
   - 慎说: before/after, competitor comparisons, superlatives, price/value claims, safety claims, health/body/financial results, time-limited offers, and any claim requiring proof.
   - 不说: guaranteed outcomes, miracle results, deceptive urgency, unsupported certifications, counterfeit/brand-authenticity claims, medical cures, financial gains, unsafe use, illegal use, or anything inconsistent with the landing page.
   - 披露: if paid, gifted, affiliate-linked, commissioned, or brand-created, add clear in-video disclosure in the same language as the endorsement and use platform disclosure tools where required.
   - AIGC 标注: if the creator, voice, product demo, or footage is significantly AI-generated or altered, add TikTok's AIGC label or a clear disclaimer/caption/watermark.
   - 落地页一致: product name, specs, price, discount, availability, proof, CTA, and restrictions must match the destination page.

   Add a short rewrite table when useful:
   - 风险话术
   - 风险原因
   - 安全改写

6. 固定虚拟达人+参考图
   If there is no fixed creator image, design one creator only. Split into `固定虚拟达人设定` and `参考图准备`. Keep age, look, wardrobe, setting, speaking style, and why it fits the product. Provide an image-generation prompt for `@Image1`. For `@Image3`, say to use the uploaded product image directly; optionally provide a cleaner product-photo prompt only if it helps.

7. Hook备选（10条美式英文）
   Provide 8-10 hooks in the spoken language requested by the user. If the requested language is American English, use this heading. Group them by testing angle: testing, contrast, pain point, real experience, curiosity, or social proof. Number hooks clearly and recommend 1-2 hook numbers with a brief reason.
   Hooks should sound native to the platform and a little salesy, not corporate. Include punchy creator formats such as "Wait okay...", "I need to show you...", "POV...", "Tell me why...", "I did not expect...", "This is the reason...", and "If you [pain point], watch this." Do not make all hooks cautious or informational.

8. 口播脚本
   Provide `15秒短版（推荐使用）` with timestamps. For TikTok English UGC, make it natural, spoken, and short enough for the duration. Avoid over-polished ad copy.
   The primary script should be the strongest credible selling version, not the safest possible wording. It should:
   - open with a creator-style hook in the first 2 seconds
   - name the product or product type quickly
   - stack 2-4 concrete product selling points in spoken language
   - include a visible demo/result/reaction moment
   - end with a clear CTA
   - reserve long disclaimers for section `5`, not the spoken script

   When useful, include:
   - `30秒完整版（备用）`
   - `更素人口语版（更松弛）`

9. B-roll 镜头清单
   Include a table-like list with columns `#`, `画面内容`, `时长`, `是否要口播`, and `剪辑位置`.
   B-roll should prove the sales claim visually. Include close-ups of the key physical hook, a before/after or contrast shot when possible, creator reaction, packaging/label detail, and a final product beauty shot that makes the item easy to recognize.

10. Seedance Prompt（可复制）
   Use this heading when the user did not request another video model. Start with a compact line such as `Segment1|产品名 前后对比UGC|0:00-0:15`, then `用途说明:`. Write a copyable prompt for Seedance or the requested video model. Include:
   - aspect ratio and duration
   - handheld phone-video style
   - fixed creator reference and product reference placeholders
   - timestamped actions
   - audio/voice/lip-sync requirements
   - spoken lines
   - fallback sub-segments if single-shot generation is unstable
   The prompt should carry the same sales energy as the script: demo the transformation clearly, keep the creator excited and casual, show the strongest product details, and avoid turning the scene into a neutral product explainer.

11. 素材表
   Split into `素材剪辑顺序`, `字幕`, `音效`, and `成片自检清单`. Provide edit order, caption placement, caption style, light sound effects, music decision, and a final QC checklist. The self-check should be concrete enough for a CapCut/TikTok draft review.

12. 下一步操作（你现在该做什么）
   Give direct operational steps as `Step1`, `Step2`, `Step3`, etc., such as generating `@Image1`, using the product image as `@Image3`, testing the first segment, editing in CapCut, previewing in TikTok drafts, and A/B testing hooks.

## Style Rules

- Write the final ad plan in Chinese unless the user requests another output language.
- Keep spoken scripts in the requested spoken language.
- Use concrete details from the product image; do not invent ingredients, price, certifications, tests, or awards.
- Prefer "真人随手分享" over polished brand-film language.
- Prefer strong creator seeding over cautious consultant language for ordinary products. The output should feel like it can be handed to a creator or video model and immediately sell the item.
- Keep one creator consistent across all image/video prompts.
- Use natural, platform-native CTA wording: "link in bio", "check the comments", "shop now", or the user's requested CTA.
- When claims are uncertain, say what evidence is needed instead of guessing.

## Useful Defaults

Use these defaults only when the user authorizes you to decide:

- Ordinary ecommerce product: 9:16, 15 seconds, platform-native creator dialogue, handheld phone-video style, clear product demo, one CTA.
- U.S. TikTok default: American English, on-camera creator dialogue, natural indoor or real-use setting, no polished brand-film language.
- Creator: match the product's likely buyer and setting; do not default every product to a beauty creator.
- Structure: problem/use case, product reveal, demo/proof, reaction/result, CTA.
- Sound: creator voice first; use subtle product-relevant sound effects only if they do not make the video feel fake.
