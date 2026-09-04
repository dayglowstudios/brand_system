---
name: brand-exploration-kit
description: Run a complete brand exploration for a new or repositioned brand and produce two linked artifacts — (1) a 1920×1080 exploration deck that moves from category landscape and archetypes through a positioning map and white space to N named design directions with a side-by-side and next steps, and (2) a pan-and-zoom canvas of full design-system boards (wordmark, palette with contrast ratios, type scale, voice Say/Never, CTA states, components, color rules, type and color in use, applications) for the directions worth developing. Use whenever someone asks to explore brand directions, run a brand sprint, map a category, find the white space, propose identity options, "3 looks for brand X", rebrand, build a brand book or design-system canvas, or add a direction to an existing exploration. Works for any category; the reference set is the Meridian supplement brand.
---

# Brand exploration kit

Two phases, two artifacts, one brand.

**Phase A · Exploration deck** — research the category, name the archetypes, find the white space, state the position, propose N directions as one-slide sketches. Output: a deck to present and decide with.

**Phase B · Design-system canvas** — for the 2–4 directions that survive, build a complete board each, side by side, so the decision can be made by looking. Output: a canvas, later exported as a hosted page and a tokens/skill package for the winner.

**Phase C · Voice tests** (optional) — sticker-sheet prompts per direction for an image model, to see the voice at volume before committing.

**Phase D · Export** — hosted single-file HTML and an application skill with tokens for the winner.

## Folder structure (one folder per phase)

```
SKILL.md                         process, rules, checklists (this file)
CHANGES.md                       what changed after the first run
01-research-deck/                Phase A
  DECK_SPEC.md                   slide-by-slide anatomy
  Brand Research Framework.md    six-stage research method
  reference/          (add a finished deck here when one is cleared for sharing)
02-design-system-canvas/         Phase B
  BOARD_SPEC.md                  section-by-section board anatomy
  templates/board-template.html  tokenized board ({{BRAND}}, {{BG}}, {{ACCENT}} …)
  templates/canvas-shell.html    side-by-side wrapper with turn/letter ids
  reference/design-system-canvas.html
  reference/example-board.html
03-voice-tests/                  Phase C (optional)
  sticker-pack-prompts.md        image-model prompts to stress-test a direction's voice
04-export/                       Phase D
  EXPORT.md                      hosted page + application skill + tokens
  tokens-example/                the Meridian tokens as the pattern
```

## Skills to invoke (when running in Claude Design)

Pull these in alongside this kit; each phase leans on one or two.

- **Phase A** — *Web research* for the competitor audit (facts dated, hooks quoted from live copy) · *Make a deck* for the 1920×1080 build and speaker notes · *Maps & geography* only if distribution or origin matters
- **Phase B** — *Hi-fi design* for the canvas and board build · *Frontend design* when choosing each direction's aesthetic · *Options* for the turn/letter side-by-side layout · *Make tweakable* if the client wants to flip accents or radii live
- **Phase C** — none; the prompts go to an image model
- **Phase D** — *Save as standalone HTML* for the hosted page · *Export as PPTX (editable)* if the deck needs to leave as a file · *Create design system* when writing the winner up as a full system · *versioned-deliverables* to keep a changelog across rounds

Outside Claude Design, skip this list; SKILL.md and the phase specs carry the method on their own.

## Inputs

Collect or infer, restate before building:

```yaml
BRAND:            # fixed; never propose alternatives
CATEGORY:
PRODUCT_FORM:     # what the customer physically receives
AUDIENCE:         # the person, and what they won't do
MARKET:           # governs spelling and idiom (US → American spelling)
COMPETITORS:      # 10–15 brands if known; otherwise research them
CONSTRAINTS:      # locked wordmark, palette, regulatory limits
DIRECTIONS:       # Phase A count (default 6); Phase B count (default 3)
DEPTH:            # Phase B: "core" (9 sections) or "full" (13)
```

If vague, one round of questions: category, audience, what's fixed, how many directions, what the directions should push on (tone, era, medium, price tier), whether they want the deck, the canvas, or both.

## Phase A · Exploration deck

Follow `01-research-deck/DECK_SPEC.md`. Method from `01-research-deck/Brand Research Framework.md` stages 1–4.

1. **Landscape.** 10–15 competitors. Group by the story they tell, not price or formula. Five archetypes is typical; four to six is fine. Each archetype gets a slide: thesis, 3 dated facts, 4 hooks quoted from their copy, angle/offer/tone, design language (4 sampled swatches, Type · Surface · Tell), and one honest "reads as".
2. **What they share.** The 3 assumptions every archetype makes. This is where the white space hides.
3. **Positioning map.** Two axes, recalibrated until incumbents cluster and a quadrant is empty. Ring the gap.
4. **Design direction.** The 3–5 shifts the research supports (material, format, type, color, voice), each tied to a finding.
5. **The opportunity.** One sentence, on the signal-colored slide.
6. **Directions.** N one-slide sketches, each in its own palette and type. Spread across borrowed codes so there is room to play. Same name and product on all; only the system changes.
7. **Side by side + next steps.** A table and four asks.

## Phase B · Design-system canvas

Follow `02-design-system-canvas/BOARD_SPEC.md`. Use `02-design-system-canvas/templates/`.

1. Pick the directions to develop (the deck's side-by-side names the safest and the most distinctive; take one of each plus a wildcard).
2. Write each direction's spec paragraph before any HTML. Directions must differ on ≥3 named axes: borrowed code, palette temperature, type genre, radius language, register, surface.
3. Build one `.dc.html` canvas: `<meta name="design_doc_mode" content="canvas">`, one `<section>` per turn (newest on top), boards 1180px wide in a flex row with 48px gap, id badge `{turn}{letter}` on each board. All styles inline.
4. Populate honestly: real copy in the direction's voice, hex on every swatch, measured contrast ratio and verdict on every pairing, primary/secondary/tertiary CTA × default/hover/pressed/disabled, at least three application surfaces.
5. When a direction wins, extend it to DEPTH full (sections 10–13), then run `04-export/EXPORT.md`.

## Phase C · Voice tests (optional)

One prompt per direction from `03-voice-tests/sticker-pack-prompts.md`: shared preamble + a concept block filled entirely from that direction's spec (field color, four swatches, two faces, radius language, seven Say lines, a Never line as the warning sticker). Nothing is invented at this stage. Sixteen to twenty-two stickers force the voice to hold up across seals, warnings, bumper strips and lot codes. Run after Phase A, before committing Phase B effort.

## Phase D · Export

See `04-export/EXPORT.md`.

## Rules that hold in both phases

- Max two typefaces per direction plus one mono, all on Google Fonts. Never Inter, Roboto, Arial, or Fraunces as the lead face.
- No category-default color leads a direction (if the category is green, nobody leads with green).
- Name directions for their borrowed code ("The Honest Label", "The Signal"), never a brand-name pun.
- Every direction carries the brand's proof point (dose, spec, lot, price) in its own idiom.
- Hooks and Say lines are usable copy, verbatim, idiomatic for MARKET.
- No emoji, no gradients, no leaves or category clichés, no SVG-drawn illustration; use image drop zones for photography.
- One honest risk line per direction wherever directions are summarized.
- Draw 2–3 spec choices at random from short lists (a script or dice) so the set doesn't collapse into the same three looks every time.

## Checklists

**Deck**
- [ ] Archetypes grouped by story; each has thesis, 3 facts, 4 hooks, angle/offer/tone, sampled swatches, "reads as"
- [ ] Facts dated and sourced in speaker notes
- [ ] Positioning axes leave a visibly empty quadrant
- [ ] One-sentence opportunity slide
- [ ] N direction slides in their own systems; same brand name on all
- [ ] Side-by-side table includes risk; next steps ≤ 4 asks
- [ ] Nothing below 24px; speaker notes on every slide

**Canvas**
- [ ] Each board a different borrowed code, ≥3 axes apart from every other
- [ ] Same nine sections, same order, same numbering on every board
- [ ] Hex on every swatch; contrast ratio + verdict on every pairing
- [ ] Say ×3 / Never ×3 per voice
- [ ] CTA matrix complete; copy is verb + object, no exclamation
- [ ] Turn/letter ids visible and linkable
- [ ] Wordmark treatment stated in one caption line
