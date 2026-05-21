# SVG PPT Standard Output Template

Use this as the default output scaffold. Do not copy it blindly when the content clearly needs another layout, but start here first.

## Intent

Produce a complete single-page SVG with:
- quiet premium background
- strong title row
- one primary card
- two to four supporting cards
- balanced whitespace

This template is the default for most business, strategy, product, research, and summary slides.

## Default Structure

1. Canvas background
2. Top header with title and optional subtitle
3. Bento grid card area
4. One dominant card for the main idea
5. Supporting cards for evidence, comparison, steps, or metrics

## Default Geometry

- `viewBox="0 0 1280 720"`
- outer margin: `40`
- header area height: about `110-130`
- grid top start: around `y=140`
- grid height: about `540`
- inter-card gap: `24`

Recommended default layout:
- primary hero card on the left: `x=40 y=140 w=712 h=540`
- top-right support card: `x=776 y=140 w=464 h=168`
- mid-right support card: `x=776 y=332 w=464 h=168`
- bottom-right support card: `x=776 y=524 w=464 h=156`

Adjust dimensions when:
- the content is mostly comparative
- the right column needs only two cards
- the hero card should become full-width
- the slide needs three equal columns instead

## Default Visual Tokens

- background: light neutral, such as `#F5F7FB`
- primary text: deep gray, such as `#111827`
- muted text: medium gray, such as `#6B7280`
- primary card fill: near-white, such as `#FCFCFD`
- accent: one restrained cool or warm color, such as `#2563EB` or `#0F766E`
- card stroke: subtle neutral, such as `#E5E7EB`
- shadow: very soft, low blur, low opacity

## Typography Tokens

- title: `font-size="36"` `font-weight="700"`
- subtitle: `font-size="17"` `font-weight="400"`
- card title: `font-size="22"` `font-weight="700"`
- large metric or takeaway: `font-size="42"` `font-weight="700"`
- body: `font-size="16"` `font-weight="400"`
- label: `font-size="13"` `font-weight="600"` with increased letter spacing if useful

Font stack:
- `Inter, Segoe UI, PingFang SC, Microsoft YaHei, Helvetica, Arial, sans-serif`

## Default Content Mapping

- Page title:
  one short headline
- Subtitle:
  one sentence of framing, source, or context
- Primary card:
  the thesis, central model, core narrative, or most important summary
- Supporting card A:
  evidence, metrics, or key signals
- Supporting card B:
  process, steps, or grouped bullets
- Supporting card C:
  implications, risks, recommendations, or quote

## Standard SVG Skeleton

Use this as the baseline shape and replace the text and colors as needed.

```xml
<svg width="1280" height="720" viewBox="0 0 1280 720" fill="none" xmlns="http://www.w3.org/2000/svg">
  <rect width="1280" height="720" fill="#F5F7FB"/>

  <g id="header">
    <text x="40" y="72"
      font-family="Inter, Segoe UI, PingFang SC, Microsoft YaHei, Helvetica, Arial, sans-serif"
      font-size="36" font-weight="700" fill="#111827">Slide Title</text>
    <text x="40" y="104"
      font-family="Inter, Segoe UI, PingFang SC, Microsoft YaHei, Helvetica, Arial, sans-serif"
      font-size="17" font-weight="400" fill="#6B7280">Optional subtitle or framing sentence</text>
  </g>

  <g id="card-primary">
    <rect x="40" y="140" width="712" height="540" rx="28" fill="#FCFCFD" stroke="#E5E7EB"/>
    <text x="72" y="188"
      font-family="Inter, Segoe UI, PingFang SC, Microsoft YaHei, Helvetica, Arial, sans-serif"
      font-size="22" font-weight="700" fill="#111827">Primary Card</text>
  </g>

  <g id="card-support-a">
    <rect x="776" y="140" width="464" height="168" rx="28" fill="#FCFCFD" stroke="#E5E7EB"/>
  </g>

  <g id="card-support-b">
    <rect x="776" y="332" width="464" height="168" rx="28" fill="#FCFCFD" stroke="#E5E7EB"/>
  </g>

  <g id="card-support-c">
    <rect x="776" y="524" width="464" height="156" rx="28" fill="#FCFCFD" stroke="#E5E7EB"/>
  </g>
</svg>
```

## Adaptation Rules

- If the slide has only one message, expand the primary card and reduce or remove support cards.
- If the slide is a three-way comparison, abandon the default split and use three equal columns.
- If the content is metric-heavy, let one support card become a high-contrast metric card.
- If the content is process-heavy, turn one card into a vertical numbered list.
- If text becomes cramped, shorten the copy before shrinking typography.

## Output Discipline

- Default final asset flow:
  - generate valid SVG
  - save it to a local `.svg` file
  - render it back to the user as a Markdown image using the absolute file path
- Return raw SVG code only when the user explicitly asks for code or markup.
- Keep IDs readable when you use them.
- Avoid unnecessary filters and path complexity.
- Prefer a small set of repeatable visual decisions over novelty for novelty's sake.
