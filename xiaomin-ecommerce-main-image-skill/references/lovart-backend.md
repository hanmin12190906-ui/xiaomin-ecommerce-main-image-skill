# Lovart / OpenClaw 主图生成后端

Use this file only when the user asks for Lovart/OpenClaw or when a main image needs stronger commercial art direction than a direct `gpt-image-2` edit.

## When To Choose Lovart

Prefer Lovart when:

- The goal is a polished commercial scene, campaign-style art direction, or premium product photography.
- The source product image is only a rough reference and the user accepts a direction-grade generation.
- The user explicitly says `Lovart`, `OpenClaw`, `本地模型`, or `调用 Lovart AI`.

Prefer `gpt-image-2` when:

- Exact SKU, packaging text, logo shape, or product cutout fidelity is more important than atmosphere.
- The output must preserve an existing product reference very tightly.
- The image has only 1-3 required text groups and must avoid hallucinated copy.

Recommended workflow for difficult ecommerce main images:

1. Use Lovart to create one high-level commercial composition draft.
2. Use the skill's compliance check to reject wrong SKU/copy.
3. If Lovart has the right mood but weaker product fidelity, use `gpt-image-2` for a tighter product-preserving refinement.

## Security Rules

- Never write Lovart Access Key or Secret Key into `SKILL.md`, references, scripts, README files, prompts, screenshots, generated images, Git commits, or terminal output.
- Use environment variables or local Keychain/runtime injection only:
  - `LOVART_ACCESS_KEY`
  - `LOVART_SECRET_KEY`
- If the local network has certificate interception and Lovart fails with certificate verification, the existing Lovart skill supports:
  - `LOVART_INSECURE_SSL=1`
  Use it only for the Lovart command process, not globally.

## Local Lovart Skill

Use the installed Lovart skill commands. Do not build raw API calls or guess endpoints.

Base path:

```bash
LOVART_SKILL="/Users/hanmin/.openclaw/workspace/skills/lovart-skill/agent_skill.py"
```

Mandatory first-use checks in a conversation:

```bash
python3 "$LOVART_SKILL" config --json
python3 "$LOVART_SKILL" threads --json
```

If `config --json` has `active_project`, reuse it. Do not create a project unless the user asks.

If there is a recent related ecommerce-main-image thread, reuse it with `--thread-id`. If not, omit `--thread-id` and let Lovart create a new thread.

## Reference Image Upload

For product-reference generation, upload each local image before chat:

```bash
python3 "$LOVART_SKILL" upload --file /absolute/path/to/product.png
```

Use the returned URL in the Lovart prompt as an attachment or reference. Describe each image role:

- product/SKU reference
- negative reference
- style/example reference
- texture reference

## Chat Command

Use `chat`, wait for completion, and download results:

```bash
python3 "$LOVART_SKILL" chat \
  --prompt "$PROMPT" \
  --json \
  --download \
  --output-dir /absolute/output/dir
```

For image edits with uploaded attachments:

```bash
python3 "$LOVART_SKILL" chat \
  --prompt "$PROMPT" \
  --attachments "$IMAGE_URL" \
  --json \
  --download \
  --output-dir /absolute/output/dir
```

If the command returns `final_status: "pending_confirmation"`, ask the user before running `confirm`.

If it returns `generation_succeeded: false`, do not present the result as an image. Surface the warning and retry with a simpler prompt or use `gpt-image-2`.

## Ecommerce Prompt Requirements

A Lovart main-image prompt must include:

- Confirmed product name, brand, category, SKU/package form.
- Main image type and platform ratio.
- Product reference image role.
- Required copy, verbatim.
- Forbidden copy, price, mechanism, gift, and platform claims.
- Layout hierarchy: product -> headline -> badge/offer.
- SKU failure rule: if package form changes, output is invalid.
- Text failure rule: if unapproved text appears, output is invalid.

Keep Lovart prompts shorter and more art-directed than `gpt-image-2` prompts. Lovart usually responds better to clear visual direction plus hard SKU/copy constraints than to long negative lists.

## Quality Gate

After download, inspect every output against `compliance-check.md`.

Reject Lovart outputs when:

- SKU/package form changes.
- Required text is missing, garbled, or extra unapproved text appears.
- The product is too small for marketplace thumbnail reading.
- It looks like a generic poster, mood board, or decorative scene rather than a sellable ecommerce main image.
- It adds fake price, coupon, membership, gift, activity time, platform badge, certification, or brand endorsement.

When Lovart output is visually strong but commercially inaccurate, report it as `方向稿` and either:

- regenerate with tighter prompt constraints, or
- use it as a style/composition reference for a `gpt-image-2` product-preserving edit.
