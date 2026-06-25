# xiaomin-ecommerce-main-image-skill

小敏电商主图设计 Skill，用于从产品图或产品 brief 出发，先整理并确认产品、价格、机制、利益点等主图关键信息，再生成或规划适合电商平台的高点击主图。

## 核心能力

- 主图需求信息确认：产品名称、价格、优惠机制、利益点、禁用信息等
- 主图类型判断：白底、场景、卖点、质地、SKU 组合、活动价格、会员赠品等
- 平台风格适配：天猫、京东、淘宝、抖音、拼多多、小红书、Amazon 等
- 生图提示词组织：适配 `gpt-image-2` 的产品编辑/生成提示词
- 质量与合规检查：避免编造价格、券、赠品、认证、活动时间和敏感功效

## 文件结构

```text
xiaomin-ecommerce-main-image-skill/
  SKILL.md
  agents/openai.yaml
  references/
    intake-confirmation.md
    main-image-types.md
    platform-style.md
    promo-layouts.md
    prompt-template.md
    compliance-check.md
    example-analysis.md
```

## 使用手册

详见 [使用手册.md](./使用手册.md)。

## 安装

将 `xiaomin-ecommerce-main-image-skill/` 文件夹复制到你的 skills 目录，例如：

```bash
cp -R xiaomin-ecommerce-main-image-skill ~/.agents/skills/
```

然后在对话中使用：

```text
$xiaomin-ecommerce-main-image-skill 做一张某产品的电商主图
```

## 重要原则

这个 skill 默认不会一上来直接做图。它会先整理确认信息，尤其是价格、活动机制、赠品、会员权益和核心利益点。确认后才进入主图规划或生图流程。
