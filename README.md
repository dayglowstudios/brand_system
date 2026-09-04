# Brand exploration kit (v2.4)

Four phases, one folder each: `01-research-deck` → `02-design-system-canvas` → `03-voice-tests` → `04-export`. Each holds its spec, templates and, where cleared, a finished reference (the Meridian canvas in 02).

## Get it

**Download** — [brand_system-main.zip](https://github.com/dayglowstudios/brand_system/archive/refs/heads/main.zip) (one click, ~1.4 MB).

**Terminal** — installs it as a Claude Code skill in one line:

```bash
git clone https://github.com/dayglowstudios/brand_system.git ~/.claude/skills/brand-exploration-kit
```

Update later with `git -C ~/.claude/skills/brand-exploration-kit pull`.

## Install
**Claude Code** — the terminal line above, or clone anywhere and copy into `<repo>/.claude/skills/brand-exploration-kit`.
**Claude.ai / Desktop** — download the zip above and upload it under Settings → Capabilities → Skills.
**Elsewhere** — paste SKILL.md plus the phase spec you need (01/DECK_SPEC.md, 02/BOARD_SPEC.md) into the system prompt.

## Use
Two starting points.

**New brand** — "Run a brand exploration for <brand>, a <category> for <audience>, US market, six directions." Full research, wide-open directions.

**Established brand** — "Explore three directions for <brand>. Locked: wordmark, primary green, body typeface. Open: accent, display type, radius, photography. Here's the current style guide and six references." Audit of the current system, then directions that move only the open axes.

Then: "Build boards for directions 1, 3 and 6."

## What to give it

As much or as little as you have. Nothing below is required: the kit researches competitors, derives a position, and draws directions on its own. Anything you do supply narrows the search and replaces a guess. Drop files in an `inputs/` folder and name them in the prompt.

**Brand**
- Name (fixed), category, product form, audience, market/spelling
- New brand or established? If established: what's locked, what's open, anything you'd consider moving; plus the current style guide, tokens or live site
- Anything locked: wordmark file, existing palette, legal or regulatory limits
- Positioning or a one-line brief if you have one

**Color**
- Colors you want in play, as hex, and why (heritage, packaging constraint, category signal)
- Colors that are off the table (a competitor owns it, category cliché)
- Temperature preference: warm paper, cold screen, saturated field, dark

**Style**
- 3–5 adjectives for the register you want and 3–5 you don't ("deadpan, exact, warm" / "wellness, aspirational, glossy")
- Era or code you want the directions to borrow from, or to push toward (2026 trends, editorial, clinical, retro-utility)
- Radius language if you have a view: sharp, 6px, pill

**Visual references** (the most useful input you can give)
- Screenshots or links to 3–8 brands, sites, packs or posters you like, one line each on what specifically works (a type pairing, a color pair, a layout move, a tone)
- 2–3 you dislike, same treatment
- They go on a References slide as pull/push, and each direction names which one it answers to
- Any mood board, Pinterest/Are.na board, or Figma file
- Photography direction if imagery matters: lighting, crop, what is never shown

**Brand references**
- Competitors, 10–15 if known, or say "research them"
- Brands outside the category whose voice or system you admire
- Your own past work: previous decks, style guides, old packaging

**Output preferences**
- Deck only, canvas only, or both
- Number of directions per phase (default 6 → 3)
- Depth for winning direction: core (9 sections) or full (13)
- Hosting target and whether you want the tokens/skill export

The Meridian run in `02-design-system-canvas/reference/` started from: name, category, US market, a black wordmark PNG, "push 2026 trends", and five studied competitor decks.

See CHANGES.md for what we learned building Meridian and changed in this version.
