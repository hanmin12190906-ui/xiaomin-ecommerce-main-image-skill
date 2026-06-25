# 主图生图提示词模板

Use this file when preparing prompts for image generation or image editing.

## Generation Strategy

Before writing a production prompt for a new request, the commercial brief must be confirmed according to `intake-confirmation.md`, unless the user explicitly skipped confirmation. Use only confirmed price, mechanism, gift, event time, and benefit copy.

If a product image is supplied:
- Prefer image edit/composition with the product image as reference.
- Preserve recognizable packaging, logo feel, colorway, shape, variant, flavor, and visible specs.
- Ask the model to polish, relight, and integrate the product rather than redesigning it from scratch.
- If the supplied image is a screenshot, collage, or low-resolution marketplace preview, use it only as packaging/SKU reference. Ask for a clean commercial reconstruction, not a pasted screenshot.
- Final output must remove visible source-image background blocks, web-page artifacts, screenshot borders, and inconsistent lighting.

If no product image is supplied:
- Generate a concept only.
- Mark that packaging and exact product appearance are not guaranteed.

For `gpt-image-2`:
- Use high quality for final main images.
- Use `1024x1024` for square drafts.
- Use `1024x1536` or `1536x2048` for vertical first images.
- Do not request transparent background with `gpt-image-2`.

## Prompt Skeleton

```text
Use the input image as product reference. Create a premium Chinese ecommerce main image for [brand/product/category].

Main image type:
[white-background / scene / selling-point / texture / comparison / bundle / campaign]

Platform and ratio:
[platform], [1:1 / 3:4 / 4:5 / 2:3]

Visual goal:
Make shoppers instantly understand the product and want to click. Product must be dominant and recognizable.

Product preservation:
Preserve the product packaging shape, brand mark, color system, variant, visible spec, and key label areas from the input image. Improve lighting, cleanliness, edge quality, and commercial polish without changing SKU facts.

Composition:
[Describe product scale, placement, background, props, scene, texture, and depth.]

Source handling:
If the input is a screenshot or existing marketplace image, do not paste it into the new canvas. Recreate a clean product-led commercial composition using the input only as visual reference. Remove the original background rectangle, screenshot artifacts, and mismatched edges.

Required readable text:
- "[exact headline]"
- "[exact badge 1]"
- "[exact badge 2]"
- "[exact badge 3]"

Copy layout:
Use one clear headline and up to three badges. Keep text large, readable, correctly spelled, and not cropped.

Style:
[platform-appropriate style], commercial product photography, clean hierarchy, no cheap template feeling.

Constraints:
Do not invent ingredients, medical effects, certifications, prices, promotions, dates, awards, or platform badges. No watermark, QR code, random logos, unrelated products, messy collage, screenshot paste, internal review copy, or process labels such as "主图优化", "设计稿", "方案", "视觉优化".
```

## Promotional Main Image Skeleton

Use this skeleton when the user supplies campaign, coupon, gift, price, threshold, membership, or event-time information.

```text
Use the input image as product reference. Create a Chinese ecommerce activity main image for [brand/product/category].

Layout archetype:
[top event + hero + bottom price bar / texture hero + promotion footer / brand campaign + offer module / benefit headline + product scene + gift card / multi-SKU bundle + offer bar]

Platform and ratio:
[Tmall/Taobao/JD/Douyin/etc.], square 1:1 unless specified.

Commercial goal:
Make shoppers understand the product and the current offer in one second. The image must have a clear three-zone hierarchy: event/campaign zone, hero product/benefit zone, conversion offer zone.

Event/campaign zone:
Use only supplied text:
- Event name: "[provided or leave blank]"
- Activity time: "[provided or leave blank]"

Hero zone:
Product must remain recognizable. Use [product photo / texture close-up / usage scene / SKU lineup] as the main visual. Keep product lighting coherent and avoid pasted screenshot artifacts.

Conversion offer zone:
Use only supplied text:
- Price: "[provided or leave blank]"
- Coupon: "[provided or leave blank]"
- Gift: "[provided or leave blank]"
- Threshold discount: "[provided or leave blank]"
- Membership mechanic: "[provided or leave blank]"

Typography:
Use large bold Chinese for the main claim, oversized numerals only for real supplied price/discount, and clear separated modules. Do not create more than four major text groups.

Constraints:
Do not invent prices, gifts, dates, coupons, discount percentages, official event labels, certification marks, or membership benefits. No watermark, QR code, process words, fake platform icons, or competitor brands.
```

## Copy Compression Patterns

Use short phrases:

- Event: `天猫双11`, `618`, `520礼遇季`, `超划算节`
- Offer: `满300减30`, `第2件半价`, `买2得8`, `0元入会领券`
- Gift: `买2赠`, `加赠`, `会员礼`
- Time: `活动时间：9/19 20:00-9/25 23:59`
- Product stage: `幼犬 1-2 月龄`
- Texture: `超柔慕斯`
- Spec: `88g`
- Category: `湿粮罐头`
- Benefit without overclaim: `柔软好入口`, `细腻质地`, `开罐即食`

Avoid:

- `第一`, `最强`, `100%`, `根治`, `治疗`, `官方认证` unless supplied and legally safe.
- Long paragraphs.
- More than three badges.
- Internal/process-facing text such as `主图优化`, `设计稿`, `方案`, `视觉优化`, `示意`.

For campaign images, short offer text is allowed to be larger and denser than normal main images, but every number must come from the user.

## Prompt Output Format

When not directly generating, output:

1. Confirmation card
2. Product facts
3. Main image direction
4. Copy text
5. Layout
6. Final prompt
7. Negative prompt / constraints
8. Compliance notes

When directly generating or compositing, inspect the result before delivery and include:

1. Output status: `可作为方向稿`, `接近正式稿`, or `不合格需重做`
2. The 3 most important quality notes
3. Whether the image has any visible screenshot/collage artifacts
