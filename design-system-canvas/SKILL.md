---
name: design-system-canvas
description: Turn an existing brand source (live website URL, style guide PDF, screenshots, CSS or tokens file) into a pan-and-zoom canvas of complete design-system boards — one board per direction, each with wordmark, palette + contrast ratios, type scale, voice Say/Never, CTA matrix, components, color rules, type and color in use, and applications. Use when someone uploads a style guide or pastes a site and asks for "the canvas", "boards", "3 looks inside our brand", "extend our system", or "what could this look like if we moved X". Established brands only (something is locked); for a blank-slate brand use brand-exploration-kit Phase A first.
---

# Design-system canvas (from an existing brand)

Input: a brand that already exists somewhere. Output: one `.dc.html` canvas, N boards side by side, every board 1180px wide, all styles inline.

## 1 · Extract before you draw

Read whatever arrived and write `tokens.json` first. Nothing goes on a board that isn't in the token file or explicitly marked invented.

| Source | How to read it | What you get |
|---|---|---|
| Live URL | fetch HTML + linked CSS; if client-rendered, ask for 2× screenshots and a DevTools capture of `:root` / computed styles | exact hex, families, sizes, radii |
| Style guide PDF | read_pdf; sample swatches; copy type specs verbatim | palette, type, rules, voice |
| Screenshots | pixel-sample at 2×; note ±2/channel drift | approximate palette, layout, radius |
| CSS / tokens file | parse custom properties and Tailwind config | everything, exact |

Every token carries `provenance: measured | inferred | invented`. Ramps, hover/pressed/disabled and focus rings are almost always invented; say so.

Minimum token set: field color, ink color, 1 accent, panel/surface color, border color, display family, body family, mono family, display size, body size, label size + tracking, card radius, button radius, shadow (usually none), max-width.

## 2 · Decide what's locked

```yaml
MODE: established
LOCKED:   [wordmark, primary field, primary ink, voice grammar]   # default; confirm with the user
OPEN:     [accent, display face, mono face, radius, layout code, photography, register]
STRETCH:  [one locked item the client might move, e.g. invert the field]
```

Ask one round if unclear: what's locked, how many boards (default 3), core (9 sections) or full (13), market spelling.

## 3 · Spec each direction before HTML

One paragraph per board, on named axes. Boards must share every locked token and differ on ≥2 open axes. Name each for a borrowed printed code (monograph, menu board, safety card, spec sheet, form), never a pun. Draw 2–3 choices at random from short lists (accents, faces, radii, register) so the set doesn't collapse into one look.

Rules: max two faces + one mono per board, all on Google Fonts; never Inter, Roboto, Arial or Fraunces as lead. No category-default color leads. No emoji, no gradients, no SVG illustration; striped drop zones for photography. Every board carries the same proof point (dose, count, price) in its own idiom.

## 4 · Build the canvas

Shell:
- `<meta name="design_doc_mode" content="canvas">` in helmet
- one `<section>` per turn, newest on top; boards in a flex row, 48px gap, `flex-wrap:wrap`
- id badge `{turn}{letter}` on each board as `<a href="#2a">2a</a>`
- header bar: badge + `{BRAND} DESIGN SYSTEM · NO. 0N` left, `0N {NAME} · {CODE}` right, mono 13px
- guardrail strip under the header: LOCKED chips in the brand's existing accent, OPEN chips outlined in the board's accent, STRETCH dashed

Sections, same order and numbering on every board, separated by 1px hairlines in the board's border color, 36px padding (44px on the wordmark row):

1. **Wordmark + 01 Palette** — wordmark at 120px in the locked face, one caption line on treatment; four 88px swatches with NAME + #HEX; a 2–3 sentence rule for what the palette does and refuses
2. **02 Type scale + 03 Voice** — Display 72 / Section 40 / Statement 22 / Body 16 / Data 13 mono, each in real copy, spec at right; lead line in quotes, register paragraph, SAY ×3, NEVER ×3 struck through
3. **04 CTA system** — Primary / Secondary / Tertiary × Default / Hover / Pressed / Disabled with real copy (verb + object, no exclamation); SIZES 56/44/32; 4 bold-lead COPY RULES; ✕ DON'T with 2–3 wrong buttons and a one-line reason
4. **05 Components + 06 Color rules** — 2×2 of the four components this direction most needs; proportion bar summing to 100; 4 Aa tiles with FG / BG · ratio · verdict; 3 bold-lead color rules
5. **07 Typography in use** — three 3:4 tiles: pack front, long copy, data
6. **08 Color in use** — four 1:1 tiles, one per palette color as a field, caption `A · NAME · where used`
7. **09 Applications** — grid 1fr 1fr 2fr: social 1:1, label/sticker 1:1, web header + hero 2:1
8. Footer bar: `NO. 0N · {BRAND} · {NAME}` left; "Answers to: … Risk: …" right

Full depth (add to the winner only): 10 Wordmark rules · 11 Iconography & motion · 12 Grid & spacing + form states · 13 Imagery.

Contrast: compute WCAG ratios for every FG/BG pairing shown; write the number and AA/AAA verdict on the tile. If a pairing fails for body text, keep it and label it "≥18px only" rather than silently fixing.

## 5 · Checklist

- [ ] tokens.json with provenance on every value; measured count stated
- [ ] locked / open / stretch list confirmed and shown on every board
- [ ] each board a different borrowed code, ≥2 open axes apart
- [ ] same nine sections, same order, same numbering
- [ ] hex on every swatch; ratio + verdict on every pairing
- [ ] SAY ×3 / NEVER ×3; CTA matrix complete; no exclamation marks
- [ ] one risk line per board in the footer
- [ ] ids visible and linkable; nothing on-board below 8px

## 6 · Export

Winner → `EXPORT.md` pattern: single-file HTML (super_inline), `tokens.json` + `tokens.css` + `tailwind.theme.js`, and an application SKILL.md whose rules are the winner's sections 01–13 rewritten as instructions.
