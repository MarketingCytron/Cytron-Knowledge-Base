# Cytron Reconfigurable Line Following Track — Verified Reference

| | |
|---|---|
| Product code | `V-RE-TRACKS` [PP] |
| Family | Robot parts and project bundles |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Page matches the KB (EVA foam, 315 × 315 × 10 mm tiles, 18 mm line, 8 options); no new facts |
| Primary source | No datasheet, user manual or guide exists ("No documents" on the page). Primary source = **Cytron product page "Cytron Reconfigurable Line Following Track"** (https://my.cytron.io/p-cytron-reconfigurable-line-following-track), read by the coordinator on 2026-10-19 [PP]. The Cytron tutorial "Learn Robotics with Bocobot Car Kit and Robo Pico" (Abdul Salam A Haris, 27 Jun 2023, 6-part series) mentions the track but could not be fetched here |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page facts saved by the coordinator (jkl-pp.md, 2026-10-19).  = Cytron Marketing tutorial index (metadata only). A single Cytron source exists, so no conflicts can be checked. Not a board: no KB file is referenced by the kit rule, but the track is used with line sensors such as Maker Line (`maker-line.md`) and LSA08 (`lsa08.md`).

## What it is
- A set of square EVA-foam floor tiles printed with black line patterns on a white, non-reflective surface, which can be laid in different arrangements to build a line-following course [PP].
- Six tile types: Cross, Curve, Station, Straight, Blank, T-Junction [PP].
- Sold as **Combo Tiles** (starter sets of 8 or 16 tiles) or **Add On Tiles** (packs of 4 tiles of one type) [PP].
- "Each set includes an info sheet of track designs" [PP].
- Price RM44.00–RM176.00 across the options (Cytron product page, read 2026-10-19) [PP]. Warranty 12 months [PP]. Stock 947 on 2026-10-19 [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | EVA foam, "no lamination layer" | [PP] |
| Surface | White, non-reflective, with black line patterns | [PP] |
| Hardness | 40 degree (±5) (scale not stated) | [PP] |
| Tile size | 315 mm x 315 mm | [PP] |
| Thickness | 10 mm | [PP] |
| Black line width | 18 mm | [PP] |
| Tile types | 6: Cross, Curve, Station, Straight, Blank, T-Junction | [PP] |
| Included paper | Info sheet of track designs (every set) | [PP] |
| Warranty | 12 months | [PP] |
| Price (all options) | RM44.00–RM176.00 | [PP] |
| Weight | Not stated | — |

### Options and contents [PP]
| Option | Tiles | Contents |
|---|---|---|
| Combo 8 | 8 | 1 Cross, 4 Curve, 3 Straight |
| Combo 16 | 16 | 2 Cross, 8 Curve, 6 Straight |
| Add On 1 — 4 Cross | 4 | 4 Cross |
| Add On 2 — 4 Curve | 4 | 4 Curve |
| Add On 3 — 4 Station | 4 | 4 Station |
| Add On 4 — 4 Straight | 4 | 4 Straight |
| Add On 5 — 4 Blank | 4 | 4 Blank |
| Add On 6 — 4 T-Junction | 4 | 4 T-Junction |

The page's pattern list names the options as "16 Combo, 8 Combo, 4 Cross, 4 Curve, 4 Station, 4 Straight, 4 Blank, 4 T-Junction" [PP]. The price of each individual option is not stated in the saved page text (range only).
### Product page facts (my.cytron.io, read 20 Oct 2026)
- Page re-read: 6 tile types on white non-reflective EVA foam (no lamination); hardness "40 degree (+/- 5)"; 315 × 315 mm, 10 mm thick; black line 18 mm; options Combo 8 (1 cross, 4 curve, 3 straight), Combo 16 (2, 8, 6), Add On 1–6 (4 tiles each of cross, curve, T-junction, straight, blank, station); info sheet with track designs in each set [PP]. Matches the KB.

## Interfaces, terminals and pin mapping
- Not applicable — a passive floor track with no electronics [PP].
- Tile-to-tile joining method (interlocking edges, tape, loose placement) is **not stated** [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **Line width is 18 mm** [PP]: when writing sensor code or choosing a sensor, quote this value — a 5-sensor bar such as Maker Line (`maker-line.md`) reads a single 18 mm line; check the sensor's own pitch/height rules before claiming it "fits".
- **Black line on white, non-reflective EVA** [PP]: set line sensors to "dark line" mode (e.g. Maker Line's line-colour switch) and calibrate on the actual tile, since EVA foam reflectance differs from paper or laminated tracks.
- **No lamination layer** [PP]: the surface is matte; do not describe it as glossy or laminated.
- **Combo sets contain no Station, Blank or T-Junction tiles** [PP] — a tutorial that needs a T-junction or a stop "station" must specify the matching Add On pack.
- **Course geometry must close:** Combo 8 (1 cross, 4 curve, 3 straight) and Combo 16 (2 cross, 8 curve, 6 straight) are the only Cytron-stated layouts; the "info sheet of track designs" in each set shows the intended arrangements [PP]. The sheet was not read — do not invent layouts.
- Tile size 315 mm × 315 mm, 10 mm thick [PP]: a 16-tile 4 × 4 layout is 1.26 m × 1.26 m (arithmetic from [PP]; not a stated spec).

## Power and electrical limits
- None (no electronics) [PP].

## Software support

## Compatibility and accessories
- Intended for line-following robots using IR line sensors; Cytron sensors with KB files: Maker Line (`maker-line.md`), LSA08 (`lsa08.md`), Maker Reflect (`maker-reflect.md`). The product page does not name a specific sensor [PP].
- Related Cytron kits that ship their own tracks (separate products, not this one): ZOOM:BIT (printed track in the box, `zoom-bit.md`) and BEETLE:BIT (track PDF). This EVA tile set is sold separately [PP].
- Add On packs extend a Combo set with the three tile types the combos lack (Station, Blank, T-Junction) or more of the basic three [PP].

## Common mistakes / troubleshooting
- **Sensor calibrated on paper misreads on the tiles** → recalibrate on the EVA surface; it is non-reflective, unlike laminated tracks [PP].
- **Robot loses the line at a Station or T-Junction** → those tiles are only in Add On packs [PP]; code must handle them explicitly.
- **Bought "4 Blank" expecting a line** → Blank tiles carry no line pattern (name only; the page gives no further description) [PP].
- **Mixing tile sets** → all tiles are 315 mm × 315 mm × 10 mm with an 18 mm line [PP], so sets mix freely.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | Only one Cytron source (product page) states facts | — | No conflict found |

## Needs verification
- **Hardness scale** — "40 degree (±5)" with no scale named (likely Shore A for EVA foam, but not stated).
- **Price per option** (which option is RM44.00 and which is RM176.00) — range only in the saved text.
- **Tile joining** — whether edges interlock (puzzle-mat style) or tiles lie loose.
- **Station tile pattern** — what the "Station" line pattern looks like (not described in text).
- **Curve geometry** (radius, quarter-circle or not) and whether Cross/T-Junction lines run to tile edges at centre — not stated.
- **Weight per tile / per set** — not stated.
- **Info sheet contents** (the stated track designs) — not read.
- **Colour / reflectance figures** of the white surface and black line — not stated.
- Use in the Bocobot tutorial (which part, which sensor, calibration advice) — tutorial not read.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [4.Line Following](https://my.cytron.io/tutorial/line-following) — Tutorial, Beginner, 2023 (part of "Learn Robotics with Bocobot Car Kit and Robo Pico") [PP: tutorial]

## Sources
- [PP] https://my.cytron.io/p-cytron-reconfigurable-line-following-track — read by the coordinator 2026-10-19 (RM44.00–RM176.00; variants and set contents; stock 947; warranty 12 months; material, hardness, size, thickness, line width; info sheet)
- [PP: tutorial] https://my.cytron.io/tutorial/build-bocobot-car-with-robo-pico — not readable here (blocked); metadata from  index https://raw.githubusercontent.com/MarketingCytron/Restructure-Cytron-Tutorial-Page/main/data/tutorials.json (id 453)
- KB cross-references: `maker-line.md`, `lsa08.md`, `maker-reflect.md`, `robo-pico.md`, `zoom-bit.md`
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
