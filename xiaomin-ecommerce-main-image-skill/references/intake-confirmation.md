# 主图需求信息确认

Use this file at the beginning of every new ecommerce main image request before generating or composing an image.

## Purpose

Main image layout depends on commercial information. Price, coupons, gifts, membership, event timing, and benefit claims decide whether the image should be a clean shelf image, benefit image, or activity conversion image. Do not guess these fields.

## Confirmation Card

Before production, output a concise confirmation card in Chinese:

```text
我先整理一下主图信息，请你确认：

- 产品名称：
- 品牌：
- 类目：
- 规格/SKU：
- 目标平台/场景：
- 主图类型判断：
- 价格信息：
- 活动/优惠机制：
- 赠品/会员机制：
- 活动时间：
- 核心利益点：
- 必须展示文案：
- 不展示/禁用信息：
- 素材质量判断：
- 缺失信息：

请确认以上信息；确认后我再做图。
```

Use `用户未提供` for absent fields and `未识别` for fields that might exist in the image but cannot be read safely.

## Field Rules

- Product name: infer from visible packaging only when readable; otherwise mark `未识别`.
- Brand: infer from clear logo/label only when readable.
- Category: can be inferred conservatively from product appearance, such as `罐装薯片`, `宠物湿粮`, `漱口水`.
- Specification/SKU: include count, weight, flavor, stage, pack count, or model only when visible or supplied.
- Target platform/scene: if absent, use `未提供，默认天猫/JD平衡风格`.
- Main image type: choose from clean shelf, scene click-through, selling-point, texture, bundle/SKU, activity/promotion, price/coupon, gift/member.
- Price information: use exact user-provided price only. Never infer from market knowledge or example images.
- Activity/offer mechanism: include only supplied coupon, threshold discount, buy-X-get-Y, second-item discount, member coupon, deposit/final-payment, or limited-time mechanics.
- Gift/member mechanism: include only supplied gifts and membership rules.
- Event time: include exact supplied date/time only.
- Benefits: separate factual visual benefits from unsupported claims. Mark uncertain claims as `待确认`.
- Required copy: include only copy that can safely appear in the image.
- Forbidden information: list any claims, prices, gifts, or platform badges that should not be invented.
- Material quality: classify as `可直接精修`, `仅适合方向参考`, or `需要补高清图`.
- Missing information: explicitly list the fields that affect whether price/promo modules should appear.

## When Confirmation Can Be Skipped

Skip the confirmation wait only if one of these is true:

- The user explicitly says `不用确认`, `直接生成`, `按你整理的直接做`, or equivalent.
- The user is continuing from an immediately preceding confirmed brief and asks for a small revision.
- The task is critique-only and no image generation/composition will be performed.

Even when skipping the wait, still include the extracted commercial facts in the prompt or work notes and do not invent missing data.

## Decision Rules After Confirmation

- If price/coupon/gift/activity information is confirmed: use `promo-layouts.md` and design an activity benefit main image.
- If no price or mechanism is confirmed: do not show price bars, coupons, countdowns, gifts, or membership modules.
- If benefits are confirmed but no price exists: use a selling-point, texture, scene, or SKU bundle main image.
- If the user provides only a product image: default to a clean product/SKU or texture main image with minimal copy.
- If required information remains missing and would materially affect the design, ask one concise follow-up before production.
