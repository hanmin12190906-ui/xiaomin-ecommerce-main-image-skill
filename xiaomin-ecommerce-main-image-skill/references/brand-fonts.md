# 品牌字体规则

Use this file when the product is a Mars / Mars Petcare brand, when the user provides a brand font library, or when optimizing typography on a generated ecommerce main image.

## Mars Brand Font Library

The skill package includes a reference image:

```text
assets/mars-brand-font-library.jpg
```

It records Mars-purchased permanent font libraries:

- 汉仪字库 87 款
- 方正字库 61 款

Treat this as a brand-approved font source list, not as actual installable font files.

## Typography Rules

- Do not use random AI-generated decorative Chinese glyphs for key commercial copy.
- Do not use overly calligraphic, warped, playful, or malformed text for Mars-owned brand ecommerce main images unless the brand reference explicitly uses that style.
- Prefer approved 汉仪 or 方正 fonts when installed locally.
- If the exact 汉仪/方正 font file is unavailable, use a clean fallback and mark the output as a direction draft:
  - `Source Han Sans / 思源黑体` for bold ecommerce headlines.
  - `PingFang SC` or `Hiragino Sans GB` for neutral UI/spec labels.
  - `Source Han Serif / 思源宋体` or a similar serif only when a refined gift/luxury tone is needed and the font is installed.
- For final production, replace fallback fonts with approved Mars font files before delivery.

## Recommended Main Image Font Choices

For brand-clean ecommerce headlines:

- 方正兰亭黑 / 方正兰亭粗黑
- 方正正黑 / 方正大黑
- 汉仪粗黑 / 汉仪大黑 / 汉仪中黑

For elegant gift-box or premium chocolate copy:

- 汉仪中宋 / 汉仪书宋
- 方正兰亭黑 with lighter tracking and gold/cream coloring
- A clean approved sans-serif in medium or bold weight if legibility at thumbnail size matters more than elegance

For small mechanism/spec badges:

- 方正兰亭黑 / 方正正黑
- 汉仪中黑 / 汉仪细黑
- Use high contrast and avoid thin strokes below thumbnail size.

## Production Workflow

1. During prompt writing, specify the intended approved font style, for example:
   `Use approved Mars brand Chinese typography, preferably Founder Lantinghei/FZLanTingHei or Hanyi Zhonghei style; no random decorative AI glyphs.`
2. After image generation, inspect all text.
3. If the headline looks AI-made, malformed, or off-brand, replace it locally with approved installed fonts instead of regenerating the whole image.
4. If approved 汉仪/方正 files are not installed, use the closest fallback and state that final production should swap in the official font.

## Quality Gate

Reject or revise typography when:

- Chinese characters are malformed or have random decorative strokes.
- The headline font feels inconsistent with the product category or brand.
- The font is too thin or ornate for marketplace thumbnail reading.
- The output invents a logo-like wordmark that is not part of the package.
