# SVG PPT Layout Spec

Use this file as the concrete layout guardrail for slide generation.

## Fixed Canvas

- SVG `viewBox` must be `0 0 1280 720`.
- Treat the usable area as a 40px outer margin unless the content strongly benefits from a tighter crop.
- Keep all important content inside the safe area.

## Bento Grid Principle

The grid is content-driven, not template-driven.

Rules:
- card count is flexible
- card sizes establish hierarchy
- the most important content gets the largest card
- every card gap must be at least `20px`
- whitespace is part of the design, not leftover space

## Recommended Layout Families

### Single Focus

- One large card covering most of the content area
- Typical size: around `w=1200`, `h=580`
- Use for one big idea, one framework, or one chart-like explanation

### Two Columns

- `50/50`: two equal cards for balanced comparison
- `2/3 + 1/3`: wide primary card plus narrow support card
- Use when one side carries the main narrative and the other adds proof, metrics, or notes

### Three Columns

- Three equal-width cards
- Use for comparison among three options, stages, or themes

### Primary With Side Supports

- One large center card
- One narrow vertical card on each side
- Use when there is one main message plus two supporting dimensions

### Top Hero With Bottom Grid

- One wide hero card on top
- Two to four smaller cards below
- Use when one main takeaway should lead and details should follow

### Mixed Grid

- Freely combine medium, horizontal, vertical, and square cards
- Use when content importance is uneven

## Suggested Spacing Defaults

- outer margin: `40px`
- inter-card gap: `20-28px`
- card padding: `24-32px`
- small text block gap: `10-14px`
- section gap inside card: `16-24px`

## Typography Defaults

- page title: `32-40px`, weight `700`
- subtitle or deck context: `16-20px`, weight `400-500`
- card title: `20-28px`, weight `600-700`
- key metric: `36-52px`, weight `700`
- body text: `14-18px`, weight `400-500`
- line height: about `1.4-1.6`

Reduce font size only after trying to simplify content.

## Density Rules

- Prefer fewer, stronger cards over many small weak cards.
- Avoid placing more than 6-8 short bullet rows in one card.
- Avoid paragraphs longer than 3 compact lines inside a card.
- If the content overflows, summarize harder instead of shrinking everything.

## Visual Tone

- premium
- clean
- modern
- restrained
- presentation-first

Avoid:
- default template look
- gratuitous gradients
- thin low-contrast text
- overly rounded toy-like cards
- excessive decoration that competes with the message
