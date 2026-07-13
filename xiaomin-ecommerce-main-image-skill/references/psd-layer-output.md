# 主图 PSD 分层输出流程

Use this file when the user asks for PSD, 分层文件, 可编辑源文件, Photoshop source, source file handoff, layer split, or PSD-ready ecommerce main image output.

## Output Principle

PSD output is a handoff format, not a different design direction. First finish the normal main-image workflow:

1. Confirm commercial information.
2. Choose main image type and platform style.
3. Compress copy and lock allowed text.
4. Generate or compose the main image.
5. Pass the quality/compliance check.
6. Then prepare the layered handoff.

Do not output a PSD-ready file from an unapproved or low-quality main image.

## Deliverable Modes

Prefer the strongest mode the current environment supports:

1. **True PSD**: a `.psd` file with layer groups and editable text layers, when a PSD-capable local tool/library/app is available.
2. **PSD-ready package**: a folder containing transparent PNG layer assets, flattened preview, and a layer manifest. Use this when true PSD writing is unavailable.
3. **Layer spec only**: a Markdown/JSON layer plan, when the user is still planning or no source image exists.

If true PSD cannot be written, say that clearly and deliver the PSD-ready package instead.

## Standard Folder Structure

```text
<project-name>/
├── preview/
│   ├── main-image-preview.png
│   └── main-image-preview.jpg
├── layers/
│   ├── 00_canvas-background.png
│   ├── 10_product-hero.png
│   ├── 20_texture-or-props.png
│   ├── 30_shadow-contact.png
│   ├── 40_highlights.png
│   ├── 50_headline-text.png
│   ├── 51_subtitle-text.png
│   ├── 60_badge-service.png
│   ├── 70_offer-module.png
│   └── 90_overlay-guides.png
├── manifest/
│   ├── layer-manifest.json
│   └── layer-notes.md
└── source/
    └── original-reference.*
```

Only include layers that exist in the design. Do not create fake offer or badge layers when no offer/badge was confirmed.

## Layer Group Rules

Use this group order from bottom to top:

1. `00_Background`
2. `10_Product`
3. `20_Texture_Props`
4. `30_Shadows`
5. `40_Light_Effects`
6. `50_Text`
7. `60_Badges`
8. `70_Offer_Modules`
9. `80_Platform_Safe_Area`
10. `90_Notes_Guides`

Layer naming format:

```text
<group-number>_<role>__<short-description>
```

Examples:

```text
10_Product__hero-packshot
50_Text__headline-浪漫心语知你心意
60_Badges__ice-delivery
70_Offer_Modules__coupon-5yuan
```

## Text Layer Requirements

For every text group, record:

- Exact text.
- Whether it is editable text or rasterized.
- Font family and fallback.
- Font size.
- Weight.
- Fill color.
- Stroke/shadow effects.
- Alignment.
- Position and bounding box.
- Safe-area notes.

Never let editable text differ from the confirmed copy. Do not include process text such as `主图优化`, `方案`, or `设计稿`.

## Manifest JSON Schema

Use this structure for `layer-manifest.json`:

```json
{
  "canvas": {
    "width": 1024,
    "height": 1024,
    "ratio": "1:1",
    "platform": "Tmall/JD"
  },
  "product": {
    "brand": "",
    "name": "",
    "sku": "",
    "source_images": []
  },
  "confirmed_copy": [],
  "forbidden_copy": [],
  "layers": [
    {
      "name": "10_Product__hero-packshot",
      "group": "10_Product",
      "type": "image",
      "file": "layers/10_product-hero.png",
      "editable": false,
      "x": 0,
      "y": 0,
      "width": 1024,
      "height": 1024,
      "opacity": 1,
      "blend_mode": "normal",
      "notes": ""
    }
  ],
  "fonts": [
    {
      "text": "",
      "font_family": "",
      "fallback": "",
      "license_note": ""
    }
  ],
  "quality_check": {
    "sku_consistent": true,
    "copy_checked": true,
    "no_unconfirmed_offer": true,
    "thumbnail_readable": true
  }
}
```

## PSD-Ready Package Checklist

Before final delivery, verify:

- Flattened preview matches the approved main image.
- Transparent PNG layers have clean edges.
- Product layer does not contain background remnants.
- Text layers or text PNGs use confirmed copy only.
- Offer/price/coupon layers exist only if confirmed.
- Shadows and highlights are separate from product when possible.
- The manifest can reconstruct the design order.
- The package does not include irrelevant screenshots, prompt drafts, or rejected variants.

## When Editing An Existing Generated Image

If the final image was generated as one flattened bitmap and cannot be cleanly separated:

1. Do not pretend it is a true editable PSD.
2. Create a practical PSD-ready handoff:
   - flattened approved preview
   - original reference
   - locally recreated editable text layers when possible
   - separate badge/offer/text overlays
   - notes explaining which visual parts remain flattened
3. Recommend a true redesign/composition pass if the user needs fully editable product, prop, and background layers.

## Final Response Format

When delivering PSD/layer output, include:

```text
输出状态：PSD-ready 分层包 / true PSD / layer spec only
预览图：
源文件/分层包路径：
包含内容：
不可编辑限制：
下一步建议：
```
