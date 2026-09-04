# Phase 0 · Intake from source

Goal: an established brand arrives as a URL, PDF, screenshots, CSS or a logo, and the user types nothing. You read the brand, fill the inputs, propose guardrails, and ask two questions at most.

## 1. Read, by source type

**Website URL** — fetch the homepage plus 2–3 key pages (product/shop, about, one content page).
- Palette: CSS custom properties first; then page background, headline color, primary button bg/fg, link color, one secondary surface. Keep the 4–6 that recur. Name by role: bg · ink · accent · secondary · line.
- Type: `font-family` stacks, Google/Adobe Fonts links, self-hosted `@font-face` names. Note weight and case for display vs body; whether a mono appears for figures.
- Radius: primary button, card, input.
- Wordmark: find the logo asset (SVG > PNG). Describe: face or custom, weight, case, color, any mark.
- Voice, verbatim: hero line, 3 CTA labels, 3 product sentences, any tagline. These seed SAY and the As-is board.
- Proof: what they use to be believed (tests, certifications, numbers, reviews, guarantees).
- Commercial: category, product form, price tier, channel, market (from currency, spelling, shipping).
- Photography: lighting, crop, subject, grading, in one line each. Note if there is none.

**Brand-guide PDF** — read it fully. Palette, type, logo clearspace/min size/misuse, tone words, do/don't lists, all verbatim. Highest authority; where it conflicts with the live site, record both and follow the guide, flagging the drift as an audit finding for Phase A.

**Screenshots / DevTools captures** — sample the largest fields and the primary button; name the closest Google Fonts face by eye and mark it "approx"; copy visible headline and button text.

**CSS / tokens / Figma export** — map variables straight into palette, type, radius, spacing.

**Logo only** — describe the mark; infer the rest from CATEGORY and mark every inferred line as such.

Use *brand-system-extractor* when available for a full token dump; its output slots straight into the As-is board.

## 2. Derive draft guardrails

Don't ask what's locked; propose it.
- **Locked** — anything consistent across every source: the wordmark, a color that appears on every surface, the body face, a tone the guide names.
- **Open** — anything that already varies between the brand's own surfaces (accent shifts between site and pack, mixed radii, inconsistent photography), and anything the guide is silent on.
- **Stretch** — one locked item whose age or inconsistency suggests the client might move it; propose at most one.

## 3. Write intake/<brand>.md

Use `intake-template.md`. Sections: Sources · Read (sourced) · Inferred (flagged) · Draft guardrails · Gaps · Filled inputs (the SKILL.md YAML, complete).

## 4. Ask, then stop

In chat, short: the Read list as 6–8 bullets, the draft guardrails, the gaps. Then only:
1. Guardrails right? Move anything between locked / open / stretch.
2. Directions count; deck, canvas, or both.
Ask AUDIENCE only if no source answered it.

## Rules
- Quote copy verbatim. Never paraphrase the brand's own lines.
- Hex from source beats hex by eye; label eyeballed values "approx".
- The As-is board uses sourced values only. Inferred values go to new directions.
- Never present a competitor's or template's values as the brand's.
- Record drift between guide and live site; it is Phase A audit material, not something to silently resolve.
