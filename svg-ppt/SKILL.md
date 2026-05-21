---
name: svg-ppt
description: Convert complete written content into a premium single-slide SVG presentation page. Use when Codex needs to generate an SVG-based PPT-style slide, transform outlines or prose into a 1280x720 visual page, apply a content-driven Bento Grid layout, or deliver presentation visuals as editable SVG markup.
---

# SVG PPT

Turn source text into one complete SVG slide, not a fragment. By default, deliver it as a rendered SVG image in chat, not as raw SVG code.

## Workflow

1. Parse the input into presentation units.
   Extract the page title, optional subtitle, and the core content blocks.
   Group related points together instead of mapping each paragraph to a separate card.

2. Choose the layout from content importance.
   Use a Bento Grid, but do not force a rigid template.
   Let the number, weight, and shape of cards follow the material.
   Put the most important message in the largest card.

3. Write the visual hierarchy before coding.
   Decide:
   - which card is primary
   - which cards are supporting
   - whether the slide needs comparison, process, summary, or hero treatment
   - whether content should be shown as short paragraphs, metrics, bullets, or labels

4. Produce a complete SVG on `viewBox="0 0 1280 720"`.
   Keep the output self-contained.
   Save it as a local `.svg` file first.
   Then present that file as an image in chat with Markdown using its absolute path.

5. Start from the standard output scaffold.
   Read [`references/output-template.md`](./references/output-template.md).
   Reuse its structure, sizing rhythm, and text conventions unless the content clearly needs a different composition.

## Hard Requirements

- Use `viewBox="0 0 1280 720"`.
- Build a single-slide composition sized for presentation use.
- Keep at least `20px` gap between all cards.
- Use Bento Grid composition with card sizes driven by content.
- Preserve clear hierarchy, high legibility, and strong whitespace.
- Keep the page premium, minimal, and professional rather than decorative.
- Default to image delivery, not code delivery.

## Layout Rules

Read [`references/layout-spec.md`](./references/layout-spec.md) before composing the slide.
Read [`references/output-template.md`](./references/output-template.md) before writing the final SVG.

Apply these defaults unless the content clearly needs another choice:
- Outer page margin: `40px`.
- Card corner radius: `24-32px`.
- Card padding: `24-32px`.
- Title block usually sits above the grid, unless a hero card can absorb it cleanly.
- Prefer 2-5 cards. Use 1 card for a strong single-message slide. Exceed 5 only when the content genuinely benefits.

## Visual Style

- Use a restrained palette: one background, one dominant foreground, one accent color, and one muted support color.
- Prefer soft neutral backgrounds, deep text color, and limited accent use.
- Use subtle shadows, strokes, or translucent fills only when they improve separation.
- Avoid noisy gradients, excessive iconography, or dashboard clutter.
- Favor large headings, short supporting text, and generous line spacing.
- Use system-safe font stacks in SVG, for example:
  `font-family="Inter, Segoe UI, PingFang SC, Microsoft YaHei, Helvetica, Arial, sans-serif"`

## Content Compression Rules

- Rewrite long prose into presentation language.
- Keep each card focused on one idea.
- Replace repetition with sharper summaries.
- Convert dense narrative into one of:
  - concise bullets
  - key-value facts
  - numbered steps
  - highlighted quote or takeaway
- If the source is too long for one slide, preserve only the highest-value information and make the hierarchy obvious.

## SVG Authoring Rules

- Start with a full background rect covering `1280x720`.
- Use groups (`<g>`) for major regions such as header and cards.
- Give every card a visible container shape, usually `<rect>`.
- Prefer explicit `x`, `y`, `width`, `height` values over transforms when possible.
- Keep text lines short enough to avoid edge collisions.
- When the slide contains bullets, draw them with simple circles or use separate text rows with hanging indent.
- Do not depend on external CSS, JS, web fonts, or images unless the user explicitly requests them.
- Prefer the standard section order:
  - background
  - header
  - grid shell
  - primary card
  - supporting cards
  - fine-detail labels or footer

## Delivery Rules

- Default behavior in Codex desktop:
  - write the finished SVG to a local file in the current workspace
  - use a clear filename such as `slide.svg`, `svg-ppt-slide.svg`, or another task-specific name
  - return the result as a rendered Markdown image using the absolute file path, for example:
    `![svg slide](/absolute/path/to/slide.svg)`
- Do not paste the full SVG markup into chat unless the user explicitly asks for:
  - source code
  - SVG markup
  - inline SVG
  - code block output
- If useful, include one short sentence before or after the image, but keep the visual asset as the primary output.
- When both preview and source are requested, show the image first and provide the file path or code second.

## Decision Heuristics

- Use a single large hero card when the input has one dominant thesis or one dense diagram-like explanation.
- Use asymmetrical two-column layout when one block is primary and the other is supporting.
- Use three equal columns for clean comparison.
- Use a top hero plus lower mini-cards when there is one headline idea followed by several supporting facts.
- Use mixed card sizes when the content has uneven importance or mixed content types.

## Output Standard

The final result should feel like a slide a designer would actually present:
- immediately scannable
- visually balanced
- information-dense without feeling crowded
- polished enough to drop into a deck unchanged

Unless the user asks for a radically different visual language, bias toward the standard template's composition and token choices so outputs stay consistent across slides.
