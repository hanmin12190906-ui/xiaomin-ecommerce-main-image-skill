# 活动利益型主图设计

Use this file when the user provides promotional main image examples, asks for Tmall/Taobao/JD/Douyin campaign creatives, or supplies price/coupon/gift/activity information.

## What These Examples Teach

Many high-performing Chinese ecommerce main images are not clean product-only thumbnails. They are conversion surfaces with three jobs:

1. **Stop the scroll** with a big promise, sensory visual, or price anchor.
2. **Prove the product** with recognizable pack/product/use texture.
3. **Convert now** with coupon, gift, membership, countdown, or event mechanic.

Do not force every main image into a quiet premium style. Choose the commercial mode that matches platform, category, and campaign.

## Core Layout Archetypes

### 1. Top Event + Hero + Bottom Price Bar

Use for shopping festivals and aggressive conversion.

- Top strip: event logo/name, date, membership cue.
- Middle hero: product plus key selling point.
- Bottom strip: price, coupon, discount, gift, CTA.
- Product is still recognizable but may share attention with price.

Good for: FMCG, food, pet supplies, oral care, health products, drink multipacks.

### 2. Product/Texture Hero + Promotion Footer

Use when texture or use result creates desire.

- Upper/middle: large food texture, product use scene, or product close-up.
- Small packshot confirms SKU.
- Bottom footer carries offer.

Good for: snacks, bakery, beverages, beauty texture, supplements.

### 3. Brand Campaign Poster + Offer Module

Use for premium brands and new product launches.

- Brand and campaign identity are visible.
- Product is photographed beautifully.
- Offer module is separated as a clean card or lower band.
- More whitespace and mood are acceptable.

Good for: beauty, lifestyle, premium drinks, branded collaborations.

### 4. Benefit Headline + Product Scene + Gift Card

Use when the click reason is benefit plus gift/coupon.

- Large benefit headline at upper left.
- Product scene at center/right.
- Gift or membership card as a secondary module.
- Bottom bar for final offer.

Good for: oral care, health drinks, home goods, pet nutrition.

### 5. Multi-SKU Bundle + Offer Bar

Use when selling a set, multi-flavor pack, or multi-box bundle.

- Hero SKU leads; other SKUs fan behind or sit in a clean row.
- Add only real included variants.
- Bottom bar can carry bundle price, buy-X-get-Y, or coupon.

Good for: snacks, drinks, capsules, multipacks, gift boxes.

## Hierarchy Ratios

For quiet search main images:
- Product: 70-88%
- Text/offers: 0-20%
- Background/props: support only

For activity benefit main images:
- Product/use texture: 35-60%
- Main headline: 15-25%
- Price/coupon/offer bar: 20-35%
- Gift/member/event modules: 10-20%

For premium brand campaign images:
- Product: 35-55%
- Atmosphere/brand field: 20-40%
- Offer module: 15-25%

## Typography Rules

- Use one dominant message. Make it unmistakable.
- Price numerals must be the largest element only when price is the campaign driver.
- Use black or brand-color bold Chinese for the main claim.
- Use white-on-color strips for event and coupon messages.
- Keep legal/small-print tiny but present only if user supplies it.
- Avoid more than 3 major text groups in the middle hero zone.

## Offer Copy Rules

Only use user-provided offer data:

- price
- discount
- coupon amount
- date/time
- gift
- membership mechanism
- buy-X-get-Y mechanic
- threshold discount

If not provided, use placeholders in the prompt rather than inventing:

- `活动价：[用户未提供]`
- `优惠机制：[用户未提供]`
- `赠品：[用户未提供]`

## Category-Specific Cues

Food/snacks:
- Use bite, pull-apart, filling, crisp texture, steam, sauce, or real product pieces.
- Avoid fake clip-art food fragments.

Beverages:
- Use bottle clarity, liquid color, condensation, fruit/ingredient cue only if supplied.

Beauty:
- Use texture smear, applicator, product shadow, premium gradient, gift module.

Pet/health:
- Use trust badges only if supplied.
- Avoid medical claims unless supplied and legally safe.

Electronics/home:
- Use product angle, feature callouts, clean spec cards, gift module.

## Prompt Add-On

When generating a promotional main image, include:

```text
Layout archetype: [top event + hero + bottom price bar / texture hero + promotion footer / brand campaign + offer module / benefit headline + product scene + gift card / multi-SKU bundle + offer bar].
Keep a clear three-zone hierarchy: event/campaign zone, hero product/benefit zone, conversion offer zone.
Use the supplied offer text only. If offer text is missing, leave that module blank or use neutral non-price copy.
```

## Failure Modes

Reject or regenerate if:

- It looks like a generic poster without a clear purchase mechanic.
- The product is too small for thumbnail recognition.
- The price/coupon dominates but the product is unclear.
- Gift module looks like an unrelated ad.
- The image invents discounts or dates.
- Text groups collide or exceed four major zones.
