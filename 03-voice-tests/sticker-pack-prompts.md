# Sticker pack prompts

One prompt per direction. Paste into an image model. Each produces a native 16:9 sticker-sheet slide in that direction's own design system, so the voice can be judged at volume before Phase B effort is spent.

Fill the concept block from the direction's spec (Phase A direction slide or Phase B board). Every field maps to something already decided; nothing new is invented here.

---

## Shared preamble

Prepend to every prompt. Replace `{{BRAND}}` only.

```
Sticker sheet exploration for the brand "{{BRAND}}". Native 16:9 landscape,
1920×1080 composition, frame filled edge to edge with a single flat field color.
No texture, gradient, vignette, or photograph on the field.

Lay out 16–22 die-cut stickers in a loose editorial grid: mixed shapes
(rectangles, rounded rectangles, circles, ovals, banners, shields, hexagons,
one long horizontal bumper strip), mixed sizes, tightly packed with even
negative space. A few rotated no more than 3 degrees. Nothing overlaps, nothing
is cropped by the frame edge. Each sticker sits on its own solid or outlined
shape with a visible die-cut border, as if peeled from one printed sheet.

Content mix, all set in the concept's own typefaces and palette:
- 1 hero sticker: the "{{BRAND}}" wordmark, largest element
- 2–3 taglines from the voice list below, verbatim
- 1 proof sticker rendered as a small table or data block
- 1 barcode or lot-code sticker
- 1 warning or notice sticker in the concept's register
- 2–3 short slogans, 2–5 words each
- 2–3 pure-mark stickers: monogram, symbol, or numeral only
- 1 long horizontal bumper strip
- 1–2 seals or roundels with text set around the curve

Typography and flat color only. No illustration, no mascot, no category
clichés, no icon set, no stock imagery, no AI-gradient blur, no drop
shadows unless the concept spec calls for a hard offset shadow.
All copy correctly spelled and legible at 25% zoom. Brand name reads exactly
"{{BRAND}}" on every sticker that carries it.
```

---

## Concept block template

One per direction. Copy, fill, append to the preamble.

```
{{SHARED PREAMBLE}}

CONCEPT: {{DIRECTION NAME}}
Field color: {{FIELD HEX}} ({{field color name}})
Palette: {{color 1 name + hex}}, {{color 2}}, {{color 3}}, {{accent name + hex}}
used on exactly {{N}} sticker(s)
Typefaces: {{display face, weight, case, tracking}} for the wordmark and
slogans. {{secondary/mono face}} for every number, label, and table.
Sticker treatment: {{fills: flat / two-color / reversed}}. {{rules: hairline /
3–4px keyline / double rule}}. {{corners: none / ≤4px / 12–20px / pill}}.
{{one sentence on what it must NOT look like}}.

Voice list, set verbatim:
"{{hook line}}"
"{{proof line with exact figures}}"
"{{instruction line}}"
"{{refusal line — what the brand won't claim}}"
"{{price or value line}}"
"{{short slogan}}"
"{{short slogan}}"

Marks: a monogram "{{INITIALS}}" set in {{display face}} inside a {{shape}};
a numeral "{{N}}" alone; a bumper strip reading "{{PHRASE}} — {{BRAND}} —
{{PHRASE}}" in {{mono face}}.
Warning sticker: "{{NOTICE IN THE DIRECTION'S REGISTER}}"
Reads as: {{three adjectives}}. {{one-line simile}}.
```

### Field guide

- **Field color** — the direction's background color from its palette. Dark directions use the dark.
- **Palette** — the board's four swatches, verbatim hex. State how many stickers may carry the accent; one is the usual answer.
- **Typefaces** — the two faces from the direction spec, with the weight and case the board uses for its wordmark and labels. Never add a third.
- **Sticker treatment** — translate the direction's radius language and border style. Pill CTAs → pill stickers; 3px keylines → 3–4px keylines; 6px radii → ≤6px corners.
- **Voice list** — pull from the board's Say list, the direction slide's hook, and the CTA copy. Seven lines: hook, proof, instruction, refusal, value, two slogans. Verbatim; never paraphrase.
- **Marks** — monogram from the brand initials; a numeral that means something (ingredient count, unit count, issue number); the bumper strip repeats the direction's borrowed-code phrase.
- **Warning sticker** — the Never list inverted: a notice that refuses a category promise, in the direction's register.
- **Reads as** — copy the direction's "reads as" line from the deck.

---

## Worked example

Filled from a light, pharmacy-shelf direction (Honest Label pattern). Shows the density expected; every value came from that direction's board.

```
{{SHARED PREAMBLE}}

CONCEPT: The Honest Label
Field color: #F4F2EC (bone)
Palette: ink #17170F, bone #F4F2EC, dose grey #9C9A90, signal red #E0451F
used on exactly one sticker
Typefaces: Instrument Sans, weight 600, sentence case, tight negative tracking,
for the wordmark and slogans. Geist Mono for every number, label, and table.
Sticker treatment: flat ink on bone or bone on ink. Hairline rules. Pill and
20px-radius shapes only. No fill colors other than ink, bone, grey, and the
single red. Must not look like a supplement badge cluster.

Voice list, set verbatim:
"Four things. All of them measured."
"Spirulina, 2,000 mg. That's the first thing."
"Put it in water."
"No proprietary blend."
"A third of the price. Same four things."
"That is the list."
"COA on request. Actually on request."

Marks: a monogram "M." set in Instrument Sans 600 inside a hairline pill; a
numeral "4" alone; a bumper strip reading "DISCLOSED DOSES — MERIDIAN —
DISCLOSED DOSES" in Geist Mono.
Warning sticker: "CONTAINS: EXACTLY WHAT IT SAYS."
Reads as: austere, exact, quietly confident. A spec sheet that learned to be brief.
```

---

## Transparent variant

To lift individual stickers into other layouts, re-run with this line replacing the field-color instruction:

```
TRANSPARENT BACKGROUND — alpha channel, no field color. Stickers float on
alpha with clean die-cut silhouettes, no contact shadow. Output PNG with alpha.
```

## Checklist

- [ ] One sheet per direction, all native 16:9, nothing cropped at the frame edge
- [ ] Brand name identical on every sheet
- [ ] Each sheet uses only its direction's two typefaces and four colors
- [ ] Every value in the concept block traces to the direction's board or slide
- [ ] Voice lines set verbatim, not paraphrased
- [ ] Sheets comparable side by side at the same scale
