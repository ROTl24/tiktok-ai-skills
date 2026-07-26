---
name: tiktok-ugc-ad-maker
version: 1.1.0
description: Create Chinese-facing TikTok/short-video UGC ad production plans from product images or product notes across ecommerce product categories. Use when the user uploads a product image or product notes and wants an ad plan — 真人感UGC广告、带货/种草视频方案、口播稿、分镜图生成（storyboard tables/JSON）、TikTok/Reels/Shorts scripts, hooks, B-roll shot lists, virtual creator setup, Seedance/Midjourney/video-generation prompts, hook A/B variants, or product-category compliance checks for U.S. TikTok or China Douyin.
---

# TikTok UGC Ad Maker

## Workflow

Produce a complete, practical UGC ad package in Chinese for any product category that can be responsibly promoted. Keep the output specific to the uploaded product and requested market; do not add unrelated future features.

1. Inspect the product image or product notes first.
2. Classify the product category and risk level before writing hooks or claims. Read `references/general-tiktok-product-compliance.md` for category routing, restricted/prohibited categories, disclosure rules, AIGC notes, music rights, paid-vs-organic differences, TikTok Shop notes, and landing-page consistency.
3. If the product appears prohibited, illegal, counterfeit, unsafe, or too regulated to assess from the available information, do not write a promotional ad. Explain the blocker and ask for proof, category clarification, or a safer non-promotional alternative.
4. If the product is restricted, sensitive, newly regulated, or not clearly covered by bundled references, verify current official TikTok and market-specific policy sources before producing direct-response ad copy. Ask for required market, age-gating, business verification, substantiation, and legal/approval details.
5. If any of these six items are missing, use Setup Question Mode before writing the full plan unless the user explicitly asks you to decide by default:
   - target country or region
   - publishing platform, including 投放方式 (organic seeding or paid ads) and whether the video will carry a TikTok Shop product card / 挂车
   - spoken language
   - voice format: on-camera dialogue or voiceover
   - fixed creator reference: uploaded creator image or AI-designed virtual creator
   - duration
6. If the user asks you to decide, state the default assumptions briefly and continue.
7. Route market-specific compliance before drafting claims:
   - U.S. TikTok beauty, skincare, lip care, health-adjacent, influencer, or AI-generated creator content: read `references/us-tiktok-beauty-compliance.md` before drafting claims, comparisons, disclosures, or AIGC notes.
   - China market content (Douyin, Xiaohongshu, Taobao content commerce): read `references/cn-douyin-compliance.md` before drafting superlatives, effect claims, before/after comparisons, price claims, or AIGC notes.
   - Coverage depth is not symmetric: U.S. TikTok has the deepest bundled coverage, China Douyin has a basic reference, and other markets fall back to the general reference plus live verification of local policy. For non-U.S.-English output, use phrasing native to that market's platform and language instead of the American English phrase bank.
8. Read `references/output-quality-bar.md` and skim `references/example-output.md` (the golden example) when producing a full ad package or testing output quality. Treat the golden example as the benchmark for density, energy, and structure — never copy its product details, hooks, or claims onto another product.
9. Generate the ad package with the fixed section order below. Before drafting the user-facing script, B-roll, and Seedance prompt, establish the storyboard shot logic as the working source of truth. The final sections must share the same shot IDs, timeline, visual references, and spoken lines instead of inventing separate structures.
10. Staged delivery option: if the user asks to confirm the storyboard first (for example 先出分镜, 分段交付, or 先确认再继续), output the Title through section `8. 分镜图生成`, ask for confirmation, and produce sections `9`-`13` after approval. Otherwise deliver the full package in one response.
11. Before finalizing, run the storyboard closure check: every storyboard shot ID must appear in the spoken-script timeline, the B-roll mapping, and the Seedance timestamped blocks. Render the result as the `分镜一致性核对表` at the start of section `12. 素材表` and fix any mismatch before delivering.
12. End with an execution checklist the user can follow immediately.

## Quality Gate

Before finalizing a full ad package, verify it would pass these checks:

- It starts from the actual product image details, not a generic ecommerce template.
- It either asks the six setup questions first or states explicit defaults when the user authorized default decisions.
- Every section includes product-specific details, not placeholders such as "show product", "highlight benefits", or "add CTA".
- The output feels like a strong TikTok seeding script, not a cautious compliance memo: hooks, product understanding, script, B-roll, and CTA should push the strongest credible reason to buy.
- For ordinary products with visible demo potential, use a contrast/result/demo angle by default: before vs after, indoor vs outdoor, problem vs quick fix, old routine vs new routine, or first impression vs reaction.
- Product selling points should be densely packed but still grounded: include visible packaging, physical design, texture/material, scent/color/finish, usage scene, routine fit, and the strongest provided label claims when they are available.
- Spoken lines should sound platform-native. For American English requests, use casual U.S. TikTok phrasing such as "wait okay", "hear me out", "I need to show you", "look at this", "POV", "I'm keeping this in my bag", and natural direct CTAs when appropriate. For other languages and markets, use phrasing native to that platform and language; do not translate these examples literally.
- The creator profile, scene, wardrobe, tone, hooks, script, B-roll, and AI video prompt match the product category and target buyer.
- The AI video prompt uses consistent reference placeholders: `@Image1` for the fixed creator, `@Image2` for the storyboard scene/style reference, and `@Image3` for the product image, unless the user supplies a different convention.
- The storyboard image-generation section keeps a closed logic chain from product breakdown to pain-point prompt conversion to shot storyboard, and outputs both a table and a JSON version.
- The storyboard JSON is consumed by the spoken script, B-roll list, and Seedance/video prompt. Each later timeline block should map back to a storyboard shot ID instead of becoming a separate script.
- Each storyboard JSON shot lists only the reference images that shot actually needs; shots do not default to all three references.
- Section `7` contains exactly 10 hooks, and the primary spoken script matches the requested duration.
- When the creator is an AI-designed virtual creator, the script contains no fabricated usage-history testimony: it follows the AI virtual creator testimony rule in Sales Energy Rules, and section `5` carries the AIGC label note.
- The Seedance/video prompt is directly copyable and includes timestamped action blocks, audio, spoken lines, storyboard shot IDs, reference placeholders, and fallback sub-segments.
- Section `12` opens with a passing `分镜一致性核对表` covering every storyboard shot ID.
- The final checklist includes product-identity, first-2-second hook, creator consistency, key physical selling point, before/after or demo honesty, platform-native voice, CTA clarity, disclosure, music rights, and AIGC label checks.

## Sales Energy Rules

The golden example's effect is strong because it sounds like a creator trying to sell a product she is excited about. Preserve that energy while staying within claim limits.

- Default to "strong seeding" language for ordinary ecommerce products: excited first-person experience, visible demo, reason-to-believe stack, and a clear purchase action.
- Do not make the main script over-cautious. Put proof caveats in section `5. 信息缺失/合规话术`; keep the spoken script punchy and creator-like.
- When a claim needs proof, use a claim ladder instead of flattening the ad. The ladder is defined once here; other documents reference it instead of restating it:
  - If the product image, label, landing page, or user notes support it, the script may say the claim directly in natural language.
  - If only the demo can show it, phrase it as what the viewer can observe: "look how...", "you can see...", "it goes from... to...".
  - If only the creator can personally feel it, phrase it as personal experience: "for me", "it feels", "I like using it when...".
  - If the claim is unverified safety, medical, guaranteed result, certification, or quantified performance, move it to the compliance section and write a safer punchy alternative for the script.
- AI virtual creator testimony rule: when the creator is AI-designed (a generated `@Image1`, not a real person), do not script durable personal-usage testimony such as "I've been using this for two weeks", "this fixed my skin", or implied purchase history. Convert those lines into what the viewer can see in the demo ("look how...", "you can see..."), in-the-moment on-camera reactions ("okay, that snap is so satisfying"), or supported product facts. On-camera testing shown inside the video itself is fine; invented history is not. Keep the excitement through demos and reactions, note the AIGC label in section `5`, and keep sections `9` and `11` consistent with this rule.
- For before/after or effect-led products, include the strongest credible transformation in the hook, script, B-roll, and Seedance prompt. Examples of transformation formats: dry to glossy, clear to tinted, messy to organized, dull to shiny, bulky to compact, slow to easy, ordinary to premium.
- Prefer direct-response CTA when the platform and market fit it, and match the CTA to the purchase mechanism: TikTok Shop product card > "tap the orange cart" / "it's on the shop tab"; bio link > "linked in my bio"; comments > "check the comments"; or the user's requested CTA.

## Setup Question Mode

When the user uploads a product image and says `/skill` or asks for a plan but has not provided the six required setup items:

Use the same user-facing rhythm as the golden example in `references/example-output.md`. This mode is not a place to expose the agent's work plan.

Required setup-question format:

1. Start with the title `中文真人感UGC广告制作方案`.
2. Open with a first-person product-image read: `我先看了你上传的产品图...`. In 2-4 concrete sentences, name the product/category, visible packaging or physical design, label text or scene cues, and likely market/style positioning. Translate visible features into sales intuition, not only neutral facts.
3. Add this transition sentence, adapted only if the input was product notes instead of an image: `在我开始帮你做完整方案之前，需要先确认6个关键信息，避免做出错语言、错平台的视频。你回答完我马上出完整方案：`
4. Add the heading `二、制作前必须确认的6件事`.
5. Ask the six questions in this exact order:
   - 投放国家/地区? Include product-specific clues only when visible, then ask whether the user wants U.S., China, Southeast Asia, Europe, Latin America, or another market.
   - 发布平台? Include region examples when useful, such as U.S./Europe > TikTok, Instagram Reels, YouTube Shorts, Amazon; China > Douyin, Xiaohongshu, Taobao; Southeast Asia > TikTok, Shopee. In the same question, ask whether the video is organic seeding or paid ads (such as Spark Ads), and whether it will carry a TikTok Shop product card / 挂车 — these change the CTA and review strictness.
   - 成片口播用什么语言? Give realistic options based on the likely market.
   - 想要哪种声音形式? Contrast on-camera creator dialogue with voiceover over product/hand/detail shots.
   - 是否已经有固定达人? If yes, ask for the creator reference as `@Image1`; if no, say you will design one virtual creator.
   - 视频时长想要多少? Offer 15s, 30s, and 45s with brief use cases.
6. Add the heading `我建议的默认方向（仅供参考）` and give a compact product-specific recommendation covering platform, style, creator, key B-roll, and the likely `@Image2` scene/style direction. Make it feel like a useful creative recommendation, not a compliance memo. If the user already has a scene, mood, room, set, or visual-style reference, invite them to provide it as `@Image2`; otherwise say you will generate `@Image2` from the storyboard.
7. End with: `请告诉我上面6个问题的答案，或者直接回复“你帮我默认决定，先给我一版美国TikTok英文真人口播15秒版本”，我就立刻按默认假设出完整方案。`

Do not include sections titled `参数确认模式`, `简要计划`, `图片识别`, `合规初判`, or `验证点` in Setup Question Mode. If the product is ordinary ecommerce, keep compliance notes out of this setup response except for one short embedded caution when a visible claim clearly needs proof. Save the full compliance discussion for section `5. 信息缺失/合规话术` in the complete package. If the product is restricted, prohibited, unsafe, or unclear, follow the workflow blocker rules instead of using this normal setup-question format.

## Incremental Update Mode

Use when the user asks to change part of an already-delivered package instead of starting a new product plan.

- Storyboard-level change (shot content, shot order, structure, creator, scene, chosen hook, spoken angle, or duration): update the storyboard JSON first, then regenerate every downstream section that consumes the changed shots — `9. 口播脚本`, `10. B-roll 镜头清单`, `11. Seedance Prompt`, and the affected parts of `12. 素材表` — and re-output the `分镜一致性核对表`. Never patch a downstream section while leaving the JSON stale.
- Downstream-only change (caption style, sound effects, CTA wording that keeps the same shot, swapping a `fallback insert`): update that section only, then confirm the shot IDs still match the JSON and say so.
- A hook swap that changes shot 1's `画面内容` or `口播/旁白` is a storyboard-level change.
- Output only the updated sections plus the refreshed `分镜一致性核对表`; do not re-print unchanged sections unless the user asks for the full document again.

## Hook Variant Mode

Use when the user asks for multiple hook versions for A/B testing, such as `给我3条hook变体` or "make hook variants".

- Keep the storyboard body (shot 2 onward) unchanged; vary only shot 1 and the opening spoken line.
- Default to 3 variants from different angles (for example pain point, contrast, curiosity) unless the user specifies a count or angles.
- For each variant output: the hook line, a revised shot-1 row (`主体动态` and `画面内容`), the revised opening timestamp block of the spoken script, and a replacement opening block for the Seedance prompt.
- Label variants `V1`, `V2`, `V3`..., keep the same `@Image1/@Image2/@Image3` contract, and state that everything after the hook reuses the base package unchanged.

## Output Structure

Use this order unless the user asks for another format:

Full package mode is a user-facing production document. Do not expose internal planning or engineering workflow. Do not add opening sections such as `执行假设`, `权衡`, `简要计划`, or final notes such as `验证说明`, lint, test, or code-change status. Start at the title, then section `0`. If the user chose staged delivery, stop after section `8`, ask for storyboard confirmation, and continue with sections `9`-`13` after approval.

Title
   First line exactly `中文真人感UGC广告制作方案`. Second line should be a compact source-style subtitle such as `产品名·美国TikTok15秒真人口播` or `产品名·美国TikTok15秒旁白种草`. Avoid colon-heavy report titles such as `中文真人感 UGC 广告制作方案：...`. Ensure the duration in the title matches the user's request.

0. 小白解释（先把术语讲清楚）
   Open with one short line telling experienced users they can skip to section `1`. Explain only the terms needed for this task, such as UGC, Hook, B-roll, CTA, 真人口播, and Segment. For each term, add why it matters for TikTok conversion or video generation, not just a dictionary definition.

1. 制作参数确认
   Confirm the user's choices in a two-column table-like block with `项目` and `确认结果`. Include at least 投放国家, 发布平台, 投放方式（自然种草/付费投放）, TikTok Shop挂车（是/否）, 成片口播语言, 声音形式, 视频时长/Segment count, 画面比例, 达人, 分镜/场景风格参考, 产品图.

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

   For 30-second and 45-second requests, keep the hook inside the first 2 seconds and the CTA in the final 2-3 seconds; extend the middle with a second selling point, objection handling, or a longer demo/comparison instead of slowing down the opening.

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
   - AIGC 标注: if the creator, voice, product demo, or footage is significantly AI-generated or altered, add TikTok's AIGC label or a clear disclaimer/caption/watermark. If the creator is an AI-designed virtual creator, restate the AI virtual creator testimony rule here: the script must not contain fabricated usage-history testimony.
   - 音乐版权: commercial or branded videos must use TikTok's Commercial Music Library, properly licensed audio, or original audio; do not assume trending sounds are cleared for ads.
   - 落地页一致: product name, specs, price, discount, availability, proof, CTA, and restrictions must match the destination page (and the TikTok Shop listing when the video carries a product card).

   Add a short rewrite table when useful:
   - 风险话术
   - 风险原因
   - 安全改写

6. 固定虚拟达人+参考图
   If there is no fixed creator image, design one creator only. Split into `固定虚拟达人设定` and `参考图准备`. Keep age, look, wardrobe, setting, speaking style, and why it fits the product. Provide an image-generation prompt for `@Image1`. If the creator is AI-designed, say so explicitly here so the AIGC label in section `5` and the testimony rule in the script stay consistent.

   In `参考图准备`, define the full reference contract:
   - `@Image1`: fixed creator reference.
   - `@Image2`: storyboard scene/style reference generated from section `8. 分镜图生成`; it should lock the core environment, lighting, phone-shot texture, props, and visual mood used by the storyboard.
   - `@Image3`: product image; use the uploaded product image directly, and optionally provide a cleaner product-photo prompt only if it helps.

   Do not use `@Image2` as another product image or another creator image unless the user explicitly changes the convention.

7. Hook备选（10条美式英文）
   Use this heading when the requested spoken language is American English; otherwise name it `7. Hook备选（10条{语言}）`. Provide exactly 10 hooks in the spoken language requested by the user. Group them by testing angle: testing, contrast, pain point, real experience, curiosity, or social proof. Number hooks clearly and recommend 1-2 hook numbers with a brief reason.
   Hooks should sound native to the platform and a little salesy, not corporate. For American English, include punchy creator formats such as "Wait okay...", "I need to show you...", "POV...", "Tell me why...", "I did not expect...", "This is the reason...", and "If you [pain point], watch this." For other languages, write hooks native to that language and platform culture; do not translate the English formats literally. Do not make all hooks cautious or informational.

8. 分镜图生成
   This section is mandatory in full package mode. It must keep the full logic closed loop: `产品拆解 -> 痛点转提示词 -> 分镜脚本 -> 口播/B-roll/Seedance对齐`. Do not skip any step, and do not output vague placeholders. This section defines the visual source of truth for sections `9`, `10`, and `11`.

   First output a compact product-to-prompt table with columns `产品元素`, `对应痛点`, `核心卖点`, `使用场景`, and `画面提示词方向`. Each row should turn a real product detail, pain point, selling point, or use scene into a visual prompt direction for the storyboard.

   Then output the storyboard table exactly with these columns:

   | 镜头 | 时间 | 阶段 | 景别 | 运镜 | 主体动态 | 画面内容 |

   Requirements:
   - Shot times must be contiguous, cover the full requested duration, and match the section `4` timeline.
   - Each shot must label one stage from `Hook`, `Problem`, `Solution`, `Benefit`, and `CTA`.
   - Each shot must use one clear shot size: `全景`, `中景`, `近景`, or `特写`.
   - Each shot must use one camera movement: `推`, `拉`, `摇`, `移`, `跟`, `手持晃动`, or `静`.
   - `主体动态` must describe the creator's or product's action, expression, or interaction.
   - `画面内容` must describe the environment, props, people, and mood clearly enough for direct creative execution or AI image generation.
   - Shots must progress logically: Hook grabs attention, Problem makes the pain point visible, Solution shows product advantage, Benefit shows the credible result or emotional payoff, and CTA guides purchase.
   - Every shot must stay tied to the product's pain point, selling point, and use scenario. Do not add unrelated lifestyle filler.
   - The shot IDs and timeline must be reused by the spoken script, B-roll list, and Seedance prompt.

   Then output an `@Image2` scene/style reference prompt. It should summarize the shared environment, lighting, phone-camera texture, props, color mood, and composition rules from the storyboard. This prompt should not replace `@Image1` or `@Image3`; it only locks the visual world that the storyboard happens inside.

   Do not output a separate storyboard-to-execution alignment table. The JSON below already carries `口播/旁白`, `对应B-roll`, and `Seedance动作` per shot, and sections `9`, `10`, and `11` are its rendered views. Fill those JSON fields here — before writing the later sections — so the JSON is complete when the script is drafted.

   After the tables, output a JSON version in a fenced `json` block. Use this schema and fill every field:

   ```json
   {
     "storyboard_image_generation": {
       "product_breakdown": [
         {
           "产品元素": "",
           "对应痛点": "",
           "核心卖点": "",
           "使用场景": "",
           "画面提示词方向": ""
         }
       ],
       "image_references": {
         "@Image1": "固定达人参考图",
         "@Image2": "分镜场景/风格参考图",
         "@Image3": "产品图"
       },
       "image2_scene_style_prompt": "",
       "shots": [
         {
           "镜头": 1,
           "时间": "0:00-0:02",
           "阶段": "Hook",
           "景别": "特写",
           "运镜": "推",
           "主体动态": "",
           "画面内容": "",
           "口播/旁白": "",
           "对应B-roll": "",
           "Seedance动作": "",
           "参考图": ["@Image2", "@Image3"]
         }
       ]
     }
   }
   ```

   In each shot's `参考图`, list only the references that shot actually needs: creator-on-camera shots need `@Image1`; pure product or environment close-ups usually need only `@Image2` and/or `@Image3`. Do not default every shot to all three references.

9. 口播脚本
   Provide the primary script at the requested duration with timestamps, labeled in source style: `15秒短版（推荐使用）` for 15 seconds, or `30秒版（推荐使用）` / `45秒版（推荐使用）` for longer requests. For TikTok English UGC, make it natural, spoken, and short enough for the duration. Avoid over-polished ad copy.
   The script timeline must be generated from the storyboard shot IDs in section `8. 分镜图生成`. Each timestamp block must map to one shot stage such as Hook, Problem, Solution, Benefit, or CTA.
   The primary script should be the strongest credible selling version, not the safest possible wording. It should:
   - open with a creator-style hook in the first 2 seconds
   - name the product or product type quickly
   - stack 2-4 concrete product selling points in spoken language
   - include a visible demo/result/reaction moment
   - end with a clear CTA
   - reserve long disclaimers for section `5`, not the spoken script
   - follow the AI virtual creator testimony rule when the creator is AI-designed

   When useful, include:
   - a backup length: `30秒完整版（备用）` for a 15-second request, or a `15秒剪短版（备用）` cutdown for a 30/45-second request
   - `更素人口语版（更松弛）`

10. B-roll 镜头清单
   Include a table-like list with columns `#`, `对应分镜镜头`, `画面内容`, `时长`, `是否要口播`, and `剪辑位置`.
   B-roll should prove the sales claim visually. Include close-ups of the key physical hook, a before/after or contrast shot when possible, creator reaction, packaging/label detail, and a final product beauty shot that makes the item easy to recognize. Every B-roll row must map to a storyboard shot ID from section `8`; if an extra insert shot is needed, mark it as `fallback insert` and explain why it does not break the main storyboard.

11. Seedance Prompt（可复制）
   Use this heading when the user did not request another video model. Start with a compact line such as `Segment1|产品名 前后对比UGC|0:00-0:15`, then `用途说明:`. Write a copyable prompt for Seedance or the requested video model. Include:
   - aspect ratio and duration
   - handheld phone-video style
   - fixed creator, scene/style, and product reference placeholders: `@Image1`, `@Image2`, and `@Image3`
   - timestamped actions
   - storyboard shot IDs from section `8`
   - audio/voice/lip-sync requirements
   - spoken lines
   - fallback sub-segments if single-shot generation is unstable
   Default fallback sub-segments to 5-10 seconds each: a 15-second video is one full segment plus a two-part fallback split (for example `0:00-0:08` and `0:08-0:15`), a 30-second video about 3 sub-segments, and a 45-second video 4-5 sub-segments.
   `@Image1/@Image2/@Image3` are a reference convention, not literal syntax for every tool: adapt them to the target model's actual reference-image mechanism, and check the current model's segment-length, multi-reference, and lip-sync limits instead of promising a single unstable long take. If the user names a different video model, follow that model's constraints and rename the section accordingly.
   The prompt must be generated from the storyboard JSON in section `8`. Each timestamped action block must map to one storyboard shot ID and reuse that shot's `画面内容`, `主体动态`, `口播/旁白`, and `Seedance动作`. Do not add a new core shot that is absent from the storyboard JSON unless it is marked as a fallback sub-segment. The prompt should carry the same sales energy as the script: demo the transformation clearly, keep the creator excited and casual, show the strongest product details, and avoid turning the scene into a neutral product explainer.

12. 素材表
   Start with `分镜一致性核对表`: a table with columns `镜头`, `口播`, `B-roll`, `Seedance`, and `状态`, covering every storyboard shot ID and verifying that each appears in the script timeline, the B-roll mapping, and the Seedance timestamped blocks. Fix any mismatch before delivering; every row must pass.
   Then split into `素材剪辑顺序`, `字幕`, `音效`, and `成片自检清单`. Provide edit order, caption placement, caption style, light sound effects, music decision, and a final QC checklist. The music decision must name a commercially cleared source (TikTok Commercial Music Library, licensed, or original audio). The self-check should be concrete enough for a CapCut/TikTok draft review.
   In `成片自检清单`, include a storyboard consistency check: each final clip should match a storyboard shot ID, use the same `@Image1/@Image2/@Image3` reference contract, and keep spoken lines aligned with the JSON. Also include disclosure, AIGC label, and music-rights checks.

13. 下一步操作（你现在该做什么）
   Give direct operational steps as `Step1`, `Step2`, `Step3`, etc., such as generating `@Image1`, generating `@Image2` from the storyboard scene/style prompt in section `8`, using the product image as `@Image3`, checking that the Seedance prompt follows the storyboard JSON, testing the first segment, editing in CapCut, previewing in TikTok drafts, publishing, then generating 2-3 hook variants with Hook Variant Mode for A/B testing and reviewing performance with `references/iteration-playbook.md` after 48-72 hours.

## Style Rules

- Write the final ad plan in Chinese unless the user requests another output language.
- Keep spoken scripts in the requested spoken language.
- Use concrete details from the product image; do not invent ingredients, price, certifications, tests, or awards.
- Prefer "真人随手分享" over polished brand-film language.
- Prefer strong creator seeding over cautious consultant language for ordinary products. The output should feel like it can be handed to a creator or video model and immediately sell the item.
- Keep one creator consistent across all image/video prompts.
- Use natural, platform-native CTA wording: "link in bio", "check the comments", "shop now", "tap the orange cart" for TikTok Shop, or the user's requested CTA.
- For non-U.S. markets and non-English scripts, platform-native means native to that market's platform and language; do not reuse the American English phrase bank literally.
- When claims are uncertain, say what evidence is needed instead of guessing.

## Useful Defaults

Use these defaults only when the user authorizes you to decide:

- Ordinary ecommerce product: 9:16, 15 seconds, platform-native creator dialogue, handheld phone-video style, clear product demo, one CTA.
- U.S. TikTok default: American English, on-camera creator dialogue, natural indoor or real-use setting, no polished brand-film language.
- 投放方式 default: organic seeding content with no TikTok Shop product card and a "link in bio" CTA; state this assumption explicitly when the user lets you decide.
- Creator: match the product's likely buyer and setting; do not default every product to a beauty creator.
- Structure: problem/use case, product reveal, demo/proof, reaction/result, CTA.
- Sound: creator voice first; use subtle product-relevant sound effects only if they do not make the video feel fake.
