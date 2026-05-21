# svg-ppt

`svg-ppt` is a Codex skill for turning complete written content into a premium single-slide SVG presentation page.

It is designed for:
- SVG-based PPT-style slides
- 1280x720 presentation visuals
- content-driven Bento Grid layouts
- direct visual delivery as rendered SVG images in Codex desktop

## Files

- `SKILL.md`: main skill instructions
- `agents/openai.yaml`: UI metadata for the skill
- `references/layout-spec.md`: layout families and spacing rules
- `references/output-template.md`: standard output scaffold and delivery rules

## Behavior

The skill:
- parses the source text into presentation units
- chooses a Bento Grid layout based on content importance
- compresses long prose into presentation-friendly blocks
- generates a complete SVG slide on `viewBox="0 0 1280 720"`
- writes the SVG to a local file and returns it as a rendered image by default

## Install

Copy this repository into your Codex skills directory as `svg-ppt`:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills/svg-ppt"
cp -R . "${CODEX_HOME:-$HOME/.codex}/skills/svg-ppt"
```

## Use

Example prompt:

```text
Use $svg-ppt to turn my text into a premium 1280x720 SVG presentation slide.
```

If you want source code instead of the rendered image, explicitly ask for SVG markup or raw SVG code.
