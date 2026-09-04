# Board anatomy

Every board is 1180px wide, its own background/ink/type, one continuous column of sections separated by 1px hairlines in the board's border color. Section labels are 13–14px mono, uppercase, +.04em, in the board's muted color, numbered `01 · PALETTE` etc.

## Header bar
Left: id badge (`<a href="#2a">2a</a>`, board's accent or ink on contrast) + `{{BRAND}} DESIGN SYSTEM · NO. 0N`. Right: `0N {{DIRECTION NAME}} · {{BORROWED CODE}}`. Mono 13–14px.

## Wordmark + 01 Palette (two columns)
Left: wordmark at 120–136px in the direction's display face, with a caption line describing the treatment (face, weight, case, tracking, the one distinguishing move).
Right: four swatches 88px tall with NAME + #HEX in mono, and a 2–3 sentence rule for what the palette does and what it refuses.

## 02 Type scale + 03 Voice (two columns)
Left, five rows with spec on the right: Display (72), Section head (40), Statement (22), Body (15–16), Data (12–13 mono). Each row uses real copy from the direction.
Right: the lead line in quotes (22px), a 2-sentence description of the register, then SAY (3 lines) and NEVER (3 lines, struck through).

## 04 CTA system
Grid: rows Primary / Secondary / Tertiary × columns Default / Hover / Pressed / Disabled, each a real button with real copy. Below: three columns — SIZES (Large 56 / Medium 44 / Small 32 with a rule), COPY RULES (4 bold-lead rules), ✕ DON'T (3 wrong buttons + one-line reason).

## 05 Components + 06 Color rules (two columns)
Left, 2×2: the four components this direction most needs (e.g. chips, field, proof card, seal & mark), each labeled.
Right: proportion bar (flex segments summing to 100 with % labels), then a 4-up of Aa tiles with FG / BG · ratio · verdict, then 3 bold-lead color rules.

## 07 Typography in use
Three 3:4 tiles: pack front, long copy, data. Caption under each in mono.

## 08 Color in use
Four 1:1 tiles, one per palette color as a field, with a mono caption naming the color and where it is used (A · BONE · WEB, EMAIL …).

## 09 Applications
Grid 1fr 1fr 2fr: two square tiles (social post, label/scoop/tag) and one wide tile (web header + hero, or app screen). Caption under each.

## Footer bar
Two mono lines: `NO. 0N · {{BRAND}} · {{THEME}}` left, a direction tagline right.

## Full depth (sections 10–13, add when a direction wins)
10 Wordmark rules — clearspace, min size, on-color variants, misuse
11 Iconography & motion — stroke, grid, corner; easing, duration, what never animates
12 Grid & spacing — base unit, container widths, breakpoints, form states (error/success/helper)
13 Imagery — lighting, crop, grading, what is never shown; drop zones for real photography

## Measurements
Board 1180 wide · section padding 36px (44px on wordmark row) · gap 18–22px · tile radius = the direction's card radius · nothing on-board below 8px type (captions inside mock tiles may go to 8–10px because they are mockups, not UI).
