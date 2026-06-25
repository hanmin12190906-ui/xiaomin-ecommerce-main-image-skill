# 电商主图类型

Use this file when selecting a main image direction.

## 1. 白底搜索主图

Use for platform search listings, SKU shelves, and catalog clarity.

- Product occupies 70-88% of the frame.
- Background is pure white or very light gray.
- Shadow is soft and realistic.
- Text is none or minimal.
- Best for standardized products, multi-SKU stores, JD/Amazon-like listings.

Prompt focus: product cutout, clean edges, faithful packaging, clear variant/spec.

## 2. 场景点击主图

Use when the product benefits from usage context.

- Product remains the biggest readable subject.
- Scene explains use case in one glance.
- Background should be shallow-depth and not busy.
- Human/pet/lifestyle element supports the product, never replaces it.

Prompt focus: real usage scene, product in foreground, warm but clean commercial photography.

## 3. 卖点主图

Use when the product has 1-3 strong provided selling points.

- Use one headline and up to three badges.
- Icons should be simple and familiar.
- Text must be large enough for thumbnail viewing.
- Avoid unsupported, absolute, or regulated claims.

Prompt focus: product hero + clear benefit badges + brand-consistent palette.

## 4. 质地主图

Use for food, beauty, fabric, home goods, pet food, materials, and sensory products.

- Use macro texture as secondary hero.
- Show product package plus texture/use result.
- Texture must look appetizing/realistic, not synthetic.
- Food texture should be photographed or rendered as realistic product-adjacent material, with coherent shadows and lighting.
- Do not use flat clip-art food pieces, sticker-like flying props, or fake crumbs as the main sensory cue.

Prompt focus: micro texture, glossy/moist/soft/crisp/material details, studio light.

## 5. 对比主图

Use only when the comparison is supported by user-provided facts.

- Compare old/new, before/after, product vs ordinary item, or size scale.
- Do not fabricate competitor claims.
- Keep layout simple: two columns or split field.

Prompt focus: clean visual contrast, truthful labels, no fake competitor logos.

## 6. 组合 / SKU 主图

Use for bundles, multipacks, color/flavor variants, gift boxes, or set products.

- Show all included items clearly.
- Use labels only for provided variants/specs.
- Avoid hiding smaller items behind the hero product.
- Arrange items with intentional depth and hierarchy: one hero SKU can lead, but every included SKU must still be legible.
- Avoid simply pasting an existing lineup screenshot into a new frame. Rebuild the layout as a clean product arrangement with unified lighting and shadows.
- For multi-flavor food packs, make variety feel abundant without making the image crowded or low-end.

Prompt focus: ordered product arrangement, exact quantities, SKU clarity.

## 7. 活动 / 价格券主图

Use for shopping festivals, price-led clicks, coupon conversion, membership gifts, threshold discounts, and short campaign windows. Read `promo-layouts.md` before using this type.

- Stronger color contrast, event strips, price zones, coupon blocks, gift modules, and countdown/date text are acceptable.
- Product must remain recognizable, but price/coupon may be the biggest element when conversion is the primary goal.
- Price, coupon, date, membership mechanic, gift, and threshold discount must be user-provided.
- Use a clear three-zone hierarchy: event/campaign zone, hero product/benefit zone, conversion offer zone.

Prompt focus: promotional hierarchy, product hero, concise activity copy.

## 8. 赠品 / 会员机制主图

Use when the click driver is a gift, membership package, buy-X-get-Y, or add-on item.

- Hero product and gift module must be visually separated.
- Gift must not look like the main product unless it is the main offer.
- Use plus signs, cards, or small inset packs to show relationship.
- Do not invent gifts or member benefits.

Prompt focus: product hero + secondary gift card + clean membership/coupon mechanics.

## 9. 质感大特写 + 小包装主图

Use when the product's internal texture is the strongest click reason: bread filling, snack crispness, beverage liquid, lipstick texture, oral-care freshness, pet food mousse.

- Macro/use texture can dominate the upper or middle zone.
- Product packshot confirms SKU and brand.
- Bottom bar can carry offer if supplied.
- This type works well for food examples where bite/pull-apart/filling is more clickable than packaging alone.

Prompt focus: appetizing close-up, clean product confirmation, restrained offer module.

## Default Selection

If the user provides only a product image and says “做主图”:

1. Create a clean search main image.
2. Create a scene click-through main image.
3. Create a selling-point or texture main image depending on category.

For food, pet food, beauty, and beverage products, prefer `质地主图` as one of the options.

If the user provides campaign examples, price/coupon/gift information, or asks for “活动主图”:

1. Choose an activity/price-coupon archetype from `promo-layouts.md`.
2. Preserve exact supplied offer copy.
3. Use bottom or side conversion modules instead of scattering offer text across the whole canvas.
