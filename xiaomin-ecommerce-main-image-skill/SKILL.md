---
name: xiaomin-ecommerce-main-image-skill
description: Use when designing, planning, generating, or critiquing Chinese ecommerce main images, product first images, search listing images, white-background product images, scene main images, SKU hero images, click-through product creatives, marketplace thumbnails, or platform-specific main images for Taobao, Tmall, JD, Douyin, Pinduoduo, Xiaohongshu, Amazon, Shopee, Lazada, and similar stores. Handles product-image analysis, main-image type selection, copy compression, layout rules, gpt-image-2/image generation prompts, Lovart/OpenClaw generation, Cowart annotation iteration, and ecommerce compliance checks.
---

# 小敏电商主图设计 Skill

Use this skill to turn a product image or product brief into high-click ecommerce main image concepts, prompts, and image-generation workflows.

Core principle: a main image is not a detail page. Optimize for instant recognition, product dominance, click-through appeal, platform fit, and truthful claims.

Commercial bar: a delivered main image must look like a marketplace-ready product creative, not a pasted screenshot, mood board, internal review poster, or rough composition draft. If the available source image is too low quality for a marketplace-ready result, say so before generation and produce a direction/prompt instead of pretending it is final.

Important distinction: a quiet search main image and a shopping-festival conversion main image are different products. Do not over-clean a campaign main image when the user's goal is price/coupon/gift conversion.

Confirmation rule: before generating, editing, or composing a main image from a new user request, first organize the available commercial information into a confirmation card and wait for the user's confirmation, unless the user has already supplied a complete confirmed brief or explicitly says to skip confirmation / directly generate. This is mandatory because price, promotion mechanics, benefits, and claims change the visual structure.

## Workflow

1. **Extract and confirm commercial facts**
   - Read `references/intake-confirmation.md`.
   - Identify brand, product name, category, package form, SKU/variant, visible specs, visible texture/material, and supplied selling points.
   - Also identify product price, coupon/discount, activity mechanism, gift/member mechanism, event time, target platform, main benefit points, required display copy, and forbidden/unsupported claims.
   - Mark missing or unclear information as `未识别` / `用户未提供`.
   - Do not invent ingredients, medical claims, official certifications, prices, dosage, or platform badges.
   - Classify input image quality: `可直接精修`, `仅适合方向参考`, or `需要用户补高清图`.
   - If the source is a screenshot, web preview, low-resolution collage, or contains background blocks that cannot be cleanly separated, do not call it a final main image without warning.
   - If the user supplies example main images, read `references/example-analysis.md` and analyze them as design references: layout archetype, hierarchy, price/coupon mechanics, product scale, typography, color bands, and offer modules.
   - Output a concise confirmation card before production. Ask the user to confirm, correct, or add missing price/mechanism/benefit information.
   - Do not proceed to image generation if the main image would display price, coupon, discount, gift, membership, activity time, or strong benefit claims that have not been confirmed.

2. **Choose main image type**
   - Read `references/main-image-types.md`.
   - Select one or more: white-background main image, scene main image, selling-point main image, texture main image, comparison main image, bundle/SKU main image, campaign/promotion main image, price/coupon main image, gift/member main image.
   - If the user says only “做主图”, default to 3 options: clean search main image, scene click-through main image, selling-point main image.
   - If the user provides price, coupon, discount, event time, gift, membership, or shopping-festival context, read `references/promo-layouts.md` and choose an activity benefit archetype.

3. **Adapt to platform**
   - Read `references/platform-style.md` when the user names a platform or channel.
   - If no platform is named, use a balanced Tmall/JD-style brand ecommerce look: clean, product-dominant, moderate copy, no loud low-end promotion.

4. **Compress copy**
   - Main image copy must be short and legible.
   - Prefer 1 main headline + 1 subtitle + 1-3 badges.
   - Keep exact user-provided brand/product/spec text unchanged.
   - Avoid unsupported absolute claims and sensitive claims.
   - Do not place internal labels such as `主图优化`, `设计稿`, `视觉优化`, `方案`, `示意`, or tool/process descriptions inside the image.
   - For activity benefit main images, separate copy into zones: event/campaign, hero claim, offer/price/gift. Do not blend all information into one dense middle area.

5. **Plan production composition**
   - Decide whether the output is `正式主图`, `方向稿`, or `生图提示词`.
   - For a formal main image, require product cutout/compositing quality, coherent lighting, no visible screenshot rectangle, no mismatched pasted elements, and no low-fidelity decorative props.
   - For food and snacks, use realistic appetizing texture as a supporting element; do not use flat clip-art chips, fake crumbs, or decorative stickers as the main appetite cue.
   - Product should normally occupy 70-88% of a square search main image unless platform rules or SKU quantity require otherwise.
   - In activity benefit main images, product/use texture may occupy 35-60% while price/coupon/gift modules occupy 20-35%; this is acceptable when conversion is the goal and the product remains recognizable.

6. **Generate prompt**
   - Read `references/prompt-template.md`.
   - For AI image generation, produce a production prompt with:
     - input image roles
     - target platform and ratio
     - product preservation constraints
     - composition
     - copy text
     - negative constraints
   - Choose a generation backend:
     - Use `gpt-image-2` when SKU/package fidelity, exact product preservation, or text control is the highest priority.
     - Use Lovart/OpenClaw when the user asks for Lovart, when a stronger commercial-photography scene is needed, or when the output needs art-direction polish beyond direct product editing.
     - For Lovart/OpenClaw generation, read `references/lovart-backend.md` and follow its local-state, upload, chat, download, and quality-gate workflow.
   - For `gpt-image-2`, prefer product-image edit/composition when a reference product image is supplied. Use generation only when no product image exists.
   - For Lovart, upload reference images first, state their roles in the prompt, and require the same confirmation/compliance constraints used for `gpt-image-2`.

7. **Quality and compliance check**
   - Read `references/compliance-check.md`.
   - Check subject size, product recognizability, text readability, platform risk, visual clutter, claim truthfulness, and packaging consistency.
   - Before delivering any generated or composited image, explicitly reject it if it looks like a poster, screenshot collage, low-end template, or internal concept board.
   - If the image fails the check, critique it first and either regenerate or provide a better prompt. Do not present a failed image as acceptable.

8. **Cowart iteration**
   - When Cowart is available, insert generated main images onto the canvas for review.
   - Treat Cowart annotations as edit briefs. Keep originals unless the user explicitly asks to replace them.

## Defaults

- Ratio: `1:1` for marketplace/search main image; `3:4` or `4:5` when the user wants a vertical first image; `16:9` only for banner-like placements.
- Style: clean premium commercial photography unless the user asks for low-price promotion or platform-native liveliness.
- Output count: if unspecified, provide 3 directions before final generation.
- Text language: Chinese by default, with short English support lines only when useful.
- If the user supplies example images, first summarize the extracted design principles and then update or apply the prompt strategy.

## Output Modes

- If the user asks to **design / plan**: first output the confirmation card, then after confirmation output product facts, chosen type, copy, layout, and final prompt.
- If the user asks to **直接生成 / 继续生成**: for a new unconfirmed brief, first output the confirmation card instead of generating. After confirmation, generate or edit the image when a generation tool/API is available, inspect it against the quality gate, and place it in Cowart if relevant. If it fails, do not frame it as final; explain the failure and improve it.
- If the user asks to **复盘 / 为什么丑 / 改主图**: critique against `references/compliance-check.md`, then propose specific fixes.

## Do Not

- Do not make a detail page, long poster, or multi-screen layout unless asked.
- Do not fill the main image with dense text.
- Do not use decorative scenes that reduce product recognition.
- Do not alter packaging, flavor, count, variant, or brand marks unless the user asks for concept exploration.
- Do not claim effects not visible in the image or supplied by the user.
- Do not paste a screenshot or product preview into a new frame and call it optimized.
- Do not use obvious AI/vector filler props when realistic product texture is required.
- Do not include process-facing words in the image, such as `主图优化`, `方案`, `设计稿`, or `视觉优化`.
