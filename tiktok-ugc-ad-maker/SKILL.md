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
5. If any of these six items are missing, ask for them before writing the full plan unless the user explicitly asks you to decide by default:
   - target country or region
   - publishing platform
   - spoken language
   - voice format: on-camera dialogue or voiceover
   - fixed creator reference: uploaded creator image or AI-designed virtual creator
   - duration
6. If the user asks you to decide, state the default assumptions briefly and continue.
7. For U.S. TikTok beauty, skincare, lip care, health-adjacent, influencer, or AI-generated creator content, also read `references/us-tiktok-beauty-compliance.md` before drafting claims, comparisons, disclosures, or AIGC notes.
8. Generate the ad package with the fixed section order below.
9. End with an execution checklist the user can follow immediately.

## Output Structure

Use this order unless the user asks for another format:

0. 小白解释
   Explain only the terms needed for this task, such as UGC, Hook, B-roll, CTA, 真人口播, and Segment.

1. 制作参数确认
   Confirm the user's choices in a compact table-like list.

2. 默认假设
   List defaults you chose because the user did not specify them. Keep this honest and editable.

3. 产品理解
   Translate product features into user-facing benefits and pain points. Separate:
   - 产品是什么
   - 用户为什么需要它
   - 用户现在的痛点
   - 这条广告要让用户相信什么
   - 最后要用户做什么

4. 广告结构
   Choose one structure and explain why. Prefer hook-body-close for TikTok. For 15-second product ads, a common structure is:
   - 0:00-0:02 hook with product, use case, problem, result, or surprising line
   - 0:02-0:05 product reveal and context
   - 0:05-0:10 use/demo/proof shot
   - 0:10-0:13 result, reaction, or strongest reason to care
   - 0:13-0:15 CTA

5. 合规话术与发布前检查
   Treat this as the missing section from the source dialogue. Include it before creator/reference setup so the later script does not inherit risky claims.

   Include:
   - 品类判断: ordinary, restricted/sensitive, prohibited/high-risk, or unclear.
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

6. 固定虚拟达人与参考图
   If there is no fixed creator image, design one creator only. Keep age, look, wardrobe, setting, speaking style, and why it fits the product. Provide an image-generation prompt for `@Image1`.

7. Hook 备选
   Provide 8-10 hooks in the spoken language requested by the user. Group them by testing angle: curiosity, contrast, pain point, real experience, or social proof. Recommend 1-2 hooks and explain the reason briefly.

8. 口播脚本
   Provide the primary script with timestamps. For TikTok English UGC, make it natural, spoken, and short enough for the duration. Avoid over-polished ad copy.

   When useful, include:
   - recommended short version
   - backup longer version
   - more casual creator-style version

9. B-roll 镜头清单
   Include shot number, visual content, approximate duration, whether speech continues on/off camera, and edit position.

10. AI 视频生成 Prompt
   Write a copyable prompt for Seedance or the requested video model. Include:
   - aspect ratio and duration
   - handheld phone-video style
   - fixed creator reference and product reference placeholders
   - timestamped actions
   - audio/voice/lip-sync requirements
   - spoken lines
   - fallback sub-segments if single-shot generation is unstable

11. 素材表、字幕、音效、自检
   Provide edit order, caption placement, caption style, light sound effects, music decision, and a final QC checklist.

12. 下一步操作
   Give direct operational steps, such as generating `@Image1`, using the product image as `@Image3`, testing the first segment, editing in CapCut, previewing in TikTok drafts, and A/B testing hooks.

## Style Rules

- Write the final ad plan in Chinese unless the user requests another output language.
- Keep spoken scripts in the requested spoken language.
- Use concrete details from the product image; do not invent ingredients, price, certifications, tests, or awards.
- Prefer "真人随手分享" over polished brand-film language.
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
