# Brand Research & Direction Framework

A runnable framework for taking a brand from zero to a brand book. Paste this whole file into an agent with web search and an image model, fill in the **Inputs** block, and run the stages in order.

Category-agnostic. Nothing below assumes a product type until you fill in the inputs.

**Finished product:** a brand book containing the competitive landscape, the positioning case, six recommended brand directions, and rendered pack or asset examples for each.

---

## 1. Inputs

Fill these in. Everything downstream reads from here.

```yaml
BRAND:          # the brand name — fixed. Never generate alternatives.
WEBSITE:        # brand site or landing page, if one exists
CATEGORY:       # e.g. "single-origin coffee", "period care", "B2B payroll software"
PRODUCT_FORM:   # what the customer physically or literally receives
POSITION:       # one line on what the brand is for. Leave blank to derive it.
COMPETITORS:    # 2–3 to kick off research; the agent expands to 12–15
  -
  -
  -
MARKET:         # e.g. US. Governs spelling, idiom, retail channels, offer conventions
AUDIENCE:       # who this is for, one line
PRICE_TIER:     # value / mid / premium / luxury, or leave blank to derive
CHANNEL:        # DTC, retail, wholesale, app store, enterprise sales
CONSTRAINTS:    # anything fixed: existing logo, locked palette, regulatory limits
```

**Rule:** `BRAND` is the name. Every direction sets that same name differently. Do not propose alternative brand names unless explicitly asked.

---

## 2. Stages

Run in order. Stop after each and show the output before continuing.

| # | Stage | Produces |
|---|---|---|
| 1 | Category research | 12–15 competitors, audited |
| 2 | Archetypes | 4–6 families with their design languages |
| 3 | Synthesis | Shared premise, positioning map, the gap |
| 4 | Directions | Six brand directions, fully specified |
| 5 | Renders | Pack or asset renders per direction |
| 6 | Brand book | Assembled document |

---

## 3. Stage 1 — Category research

```
Research the {{CATEGORY}} category in {{MARKET}}. Start from {{COMPETITORS}}
and {{WEBSITE}}, then expand to 12–15 players a customer would realistically
compare. Include the category leader, the value challenger, the newest
entrant, and at least one adjacent-category brand encroaching on it.

Audit each one. Capture only what you can source:

  COMMERCIAL
  - price and price architecture; subscription vs one-off; bundle logic
  - where it sells and who owns the shelf or the feed
  - any funding, acquisition or revenue signal, dated

  MESSAGE
  - the exact claims on the front of pack or above the fold, quoted
  - the hooks and angles their marketing leans on, quoted
  - offer structure: discounts, trials, autoship, referral, guarantees
  - proof they offer: certifications, testing, clinical claims, reviews
  - tone of voice in one line

  DESIGN
  - palette as hex values
  - typeface class for display and text, named if identifiable
  - substrate, print method, finish, structure
  - photography style, or none
  - the one giveaway detail that identifies the brand at a glance

Constraints:
- Cite every number. If you cannot source it, leave it out.
- Label anything sourced outside {{MARKET}} as a leading indicator, not a local fact.
- Hooks and offers are OBSERVED from public marketing. Never present them as
  measured performance data. State this explicitly wherever they appear.
- No invented metrics. No CTRs, ROAS, conversion rates or market shares unless
  supplied in the inputs or sourced and cited.
```

---

## 4. Stage 2 — Archetypes

```
Group the audited brands into 4–6 archetypes by THE STORY THEY TELL, not by
price or product spec. Two or three words per archetype name.

For each archetype:
- which brands belong to it, listed
- the claim it makes, in one sentence
- the hooks it leans on, quoted
- its angle: the persuasion strategy in one sentence
- its offer pattern
- its tone in one line
- its design language: 4 hex swatches, type, surface, and the giveaway detail
- a "reads as" line: the honest read of how it lands on a customer

Then answer: which archetype is most crowded, which is thinning out, and which
one is being quietly abandoned. Say why, with evidence.
```

---

## 5. Stage 3 — Synthesis

```
Three questions.

1. SHARED PREMISE. What do all of them assume? Three assumptions the whole
   category makes, including the uncomfortable one. End with a single line that
   names what nobody is saying.

2. POSITIONING MAP. Draw a 2×2. Choose the two axes that actually discriminate.
   Do not default to price and quality.

   Test each candidate axis pair before you commit:
   - Does it separate the leader from the challenger?
   - Does it separate the newest entrant from the incumbents?
   - If the category's biggest recent success lands in the quadrant you want to
     call empty, THE AXES ARE WRONG. Redraw them.

   Then plot all 12–15 brands with coordinates, name the empty quadrant, and
   state which brand sits closest to it and how far away.

3. COUNTER-POSITION. Two columns, four matched points each: what the category
   says, and what {{BRAND}} says instead. Lead with the substantive difference,
   not the tonal one — tone is the easiest thing for an incumbent to copy.

Then the opportunity in one sentence: what {{BRAND}} is, who it is for, what it
is against, and what proves it.

Self-check before showing this:
- Is the empty quadrant genuinely empty?
- Would each competitor's own team agree with where you plotted them?
- Does the axis legend read in the same direction as the plotted data?
- Is the counter-position defensible for more than six months?
```

---

## 6. Stage 4 — Six brand directions

Six, not three. The point is range.

```
Produce six brand directions for {{BRAND}}. Same name, same product, same
position in all six. Only the design system changes.

Spread them across genuinely different codes. Derive the six from the category,
but each one must borrow its visual authority from a DIFFERENT world. Useful
sources to draw from — pick six that fit {{CATEGORY}}:

  clinical / pharmaceutical      utility / industrial / issued
  grocery / pantry / domestic    institutional / bureaucratic
  editorial / newsstand          luxury / fashion / gallery
  technical / instrumentation    heritage / archival
  confectionery / toy            software / systems

For each direction:
- a descriptive name — the code it borrows from, not a brand name
- the idea in one sentence: why this world lends credibility here
- palette: 4 hex values, plus what the palette is doing
- type: display face + text face, both real and freely licensable, plus one
  line on how they behave together
- material and finish: substrate, print or build method, structure
- hook: the line that leads, in quotes
- angle: the persuasion strategy
- offer: priced and channelled for {{MARKET}} and {{CHANNEL}}
- value proposition: one sentence
- tone: three adjectives and a register
- risk: the honest weakness of this direction

Then a comparison table: all six against code, hook, angle, offer, closest
rival, strongest at, weakest at.

Constraints:
- Maximum two typefaces per direction.
- No category-default color leads any direction. If everyone is green, none of
  the six leads with green.
- Every direction must be able to carry the proof identified in Stage 3. If one
  cannot, say so in its risk line.
- Respect {{CONSTRAINTS}}.
```

---

## 7. Stage 5 — Renders

Three modes. Run **A** and **C** for every direction; add **B** for the two or three you want to present hardest.

Modes A and B are cutouts on transparent backgrounds. Mode C is the exception — it is a filled 16:9 frame built to drop straight into a slide.

### Shared preamble — prepend to every prompt

```
TRANSPARENT BACKGROUND — alpha channel, no backdrop, no surface, no gradient
sweep, no contact shadow, no reflection, no props, no hands, no lifestyle
context. Output PNG with alpha, 2048px on the long edge.
Brand name reads exactly: {{BRAND}}
All copy correctly spelled and legible at 25% zoom.
Typography and material do the work. No illustration, no mascot, no botanical
drawing, no icon set, no stock imagery, no AI-gradient blur.
```

### Mode A — flat artwork

For dielines, shelf comps, and anything that has to be edited later.

```
{{SHARED PREAMBLE}}
Flat front-facing artwork, dieline-trimmed, straight-on orthographic view, no
perspective, no mockup.
Print-accurate flat vector look: crisp edges, true flat color, no bevel, no
emboss, no photographic grain.
Format: {{PRODUCT_FORM}} primary face at its real aspect ratio.
Then apply the direction spec below.
```

### Mode B — dimensional pack shot

For the brand book cover and the recommendation slides.

```
{{SHARED PREAMBLE}}
Photographic product render of {{PRODUCT_FORM}}, single unit, three-quarter
front view, centered, full object in frame with even margins.
Studio lighting: one large soft key from upper left, gentle fill, subtle
specular roll-off on the edge. Physically accurate material — the substrate and
finish must be readable as a real surface.
Shallow depth of field is NOT used; the whole object is sharp.
Cut out cleanly at the silhouette. No cast shadow, no ground plane, no plinth.
Then apply the direction spec below.
```

### Mode C — sticker sheet, 16:9

One per direction. This is where a direction proves it has a *language* and not
just a logo: the voice, the marks, the secondary type, the badges, the warning
labels, the throwaway jokes. If a direction can't fill a sticker sheet, it isn't
a system yet — say so in its risk line.

Native 16:9 so it lands in a deck without cropping.

```
Sticker sheet exploration for {{BRAND}}, native 16:9 landscape, 1920×1080
composition, filled frame edge to edge — this mode does NOT use a transparent
background.

Field: a single flat {{field hex}} backdrop, no texture, no gradient, no vignette.
Lay out 16–22 die-cut stickers in a loose editorial grid: varied shapes
(rectangles, rounded rectangles, circles, ovals, banners, shields, triangles,
hexagons, long horizontal bumper strips), varied sizes, tightly packed with
even negative space, a few rotated no more than 3 degrees. Nothing overlaps and
nothing is cropped by the frame edge.
Each sticker sits on its own solid or outlined shape with a visible die-cut
border, as if peeled from one printed sheet.

Content mix, all set in the direction's own type and palette:
- 1 hero sticker: the {{BRAND}} wordmark, largest element
- 2–3 taglines or hooks drawn from this direction's voice
- 1 spec or proof sticker rendered as a small table or data block
- 1 barcode or lot-code sticker
- 1 warning or notice sticker in the direction's register
- 2–3 short slogans, 2–5 words each
- 2–3 pure-mark stickers: monogram, symbol, or numeral only
- 1 long horizontal bumper strip
- 1–2 seals or roundels with text set around the curve

Typography and flat shape only. No mascot, no illustration, no photography, no
3D, no glossy plastic simulation, no drop shadow, no bevel, no AI gradient blur.
Maximum two typefaces plus the palette from the direction spec.
All copy correctly spelled, in {{MARKET}} idiom, legible at 25% zoom.
Then apply the direction spec below.
```

**Transparent variant.** For stickers that need to be reused individually,
re-run with: `TRANSPARENT BACKGROUND — alpha channel, no field color, stickers
floating on alpha with clean die-cut silhouettes, no contact shadow.`

### Per-direction spec block

Write one of these for each of the six directions, filled from Stage 4.

```
DIRECTION: {{name}}
Substrate and finish: {{material, print method, finish}}
Structure: {{closure, proportion, any structural detail}}
Field color: {{primary hex}}
Brand name: set in {{display face}}, {{case}}, {{tracking}}, {{arrangement}},
  in {{hex}}, positioned {{placement}}
Secondary copy: {{what it says}}, set in {{text face}}, {{size relationship}}
Proof element: {{the dose table / batch code / spec list / certification —
  whatever Stage 3 identified as the proof, and how it is rendered}}
Accent: {{accent hex}}, used exactly once, on {{element}}
Explicitly absent: {{the category tropes this direction refuses}}
Sticker voice: {{5–8 short lines this direction would actually say, verbatim}}
Sticker marks: {{the monogram, symbol or numeral this direction owns}}
```

### Render checklist

- [ ] Modes A and B carry the transparent-background clause; Mode C is a filled 16:9 frame
- [ ] Brand name identical and correctly spelled across every render
- [ ] One pack render and one sticker sheet per direction
- [ ] Renders of the same mode share angle, scale and lighting so they compare fairly
- [ ] Every sticker sheet is native 16:9 with nothing cropped at the edge
- [ ] Each sticker sheet uses only its direction's two typefaces and palette
- [ ] No render includes a competitor's trade dress

---

## 8. Stage 6 — Brand book

Assemble everything into one document. Structure:

```
01  Cover                  brand name, category, date
02  The brief              what we are making and who for, one spread
03  Method                 what was researched and how, briefly
04  The category           12–15 brands audited, table form
05  Archetypes             one spread each: brands, claim, hooks, angle,
                           offer, tone, design language, reads-as
06  Shared premise         what everyone assumes
07  Positioning map        the 2×2, all brands plotted, the gap named
08  Counter-position       category says / we say
09  Where design is going  4–6 shifts, each sourced and dated
10  The opportunity        one sentence, plus for / against / proof
11  Directions             two spreads per direction: (a) pack render, palette,
                           type, material, hook, angle, offer, value prop, risk
                           (b) full-bleed 16:9 sticker sheet
12  Comparison             all six against one set of criteria
13  Recommendation         two directions, why, and what would change your mind
14  Next steps             owners and dates
15  Sources                every citation, dated
```

Rules for the book:
- Nothing below 24px on screen, 10pt in print.
- One idea per spread.
- Every number carries its source.
- Hooks are labelled as observed, not measured.
- Renders sit at identical scale and lighting so directions compare fairly.
- Sticker sheets run full-bleed, one per spread, at native 16:9.
- The recommendation names what would change your mind. A recommendation
  without a falsifier is a preference.

---

## 9. Guardrails

- **The name is fixed.** Never generate alternative brand names.
- **Cite or cut.** Unsourced figures get deleted, not softened.
- **Hooks are observed, not measured.** Say so wherever they appear.
- **Foreign data gets flagged** as a leading indicator, not a local fact.
- **Spelling and idiom follow `{{MARKET}}`.** Check hooks specifically — idiom hides there.
- **Channels and offers follow `{{MARKET}}` and `{{CHANNEL}}`.** Name real ones.
- **Renders are transparent.** Every image prompt keeps the alpha clause.
- **No invented performance data.** Ever.
- **No competitor trade dress** in any render or direction.

---

## 10. Final self-check

- [ ] Does the empty quadrant survive scrutiny — is the category's biggest recent success outside it?
- [ ] Does the axis legend read in the same direction as the plotted data?
- [ ] Do the cover, the directions section, and the comparison agree on how many directions there are?
- [ ] Is every hook idiomatic for `{{MARKET}}`?
- [ ] Six directions, six different borrowed codes, maximum two typefaces each?
- [ ] Do Modes A and B specify transparent backgrounds, and Mode C a filled 16:9 frame?
- [ ] Does every direction have a sticker sheet, and does each one fill it without padding?
- [ ] Is the brand name identical across every render?
- [ ] Does the recommendation state what would change your mind?
