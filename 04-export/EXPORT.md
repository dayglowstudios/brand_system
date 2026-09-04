# Phase D · Export

Run when a direction wins.

## 1. Hosted page
Bundle the canvas (and the deck, if wanted) into a single self-contained HTML with fonts still loading from Google Fonts. Drop at the subdomain root as `index.html`. No other files needed.

## 2. Application skill
Write a companion skill named `<brand>-design-system` so agents can build *in* the system:
- `SKILL.md` — one section per direction: palette with roles, type, voice with Say/Never, CTA states, components; shared rules; checklist
- `tokens/<direction>.json` — colors, roles (background/ink/accent/muted/border/surface), fonts + Google Fonts URL, radii
- `tokens/<direction>.css` — the same as `:root` custom properties, prefixed `--m-`
- `tokens/all.json` — every direction in one file
- `reference/index.html` — the hosted canvas

`tokens-example/` holds the Meridian set as the pattern to copy.

## 3. Full depth
Before export, extend the winning board to sections 10–13 (wordmark rules, iconography & motion, grid & spacing & form states, imagery). See `../02-design-system-canvas/BOARD_SPEC.md`.
