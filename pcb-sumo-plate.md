# PCB Plate for Sumo Robot — Verified Reference

| | |
|---|---|
| Product code | `V-PCB-SUMO-PLATE` [PP] (options 15cm / 10cm; per-option codes not stated) |
| Family | Sumo robot kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Page matches the KB (training use only; 15 cm for 1 kg robots, 10 cm for 500 g; sizes and weights) |
| Primary source | **Cytron product page** (read by the coordinator 2026-10-19) [PP] — https://my.cytron.io/p-v-pcb-sumo-plate. The page lists no documents; no datasheet exists. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] only. The SUMO:BIT Robot Kit page lists "1x PCB Plate for Blade (training)" in its Complete packing list [PP: SUMO:BIT kit page] — the same plate type, used as a cross-reference only.

## What it is
A flat PCB-material plate that stands in for a steel blade on a sumo robot during training and education; "not intended for official competitions" [PP]. Two sizes: the 15 cm plate is recommended for 1 kg sumo robots and the 10 cm plate for 500 g robots [PP]. Lightweight PCB material [PP].
Positioning (marketing, not spec): training/educational blade substitute [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Options | 15cm / 10cm | [PP] |
| 15CM — dimensions | 15 cm × 2.3 cm × 0.2 cm | [PP] |
| 15CM — weight | 10.6 g | [PP] |
| 15CM — recommended for | 1 kg sumo robots | [PP] |
| 10CM — dimensions | 10 cm × 1.8 cm × 0.1 cm | [PP] |
| 10CM — weight | 3.5 g | [PP] |
| 10CM — recommended for | 500 g sumo robots | [PP] |
| Material | PCB material, lightweight | [PP] |
| Intended use | Training/educational blade substitute; "not intended for official competitions" | [PP] |
| Packing list | 1 × plate | [PP] |
| Warranty | 12 months | [PP] |
| Price | RM5.00–RM8.00 across the two sizes (Cytron product page, read 2026-10-19) | [PP] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- Page re-read: training and education blade substitute, "not intended for official competitions"; 15 cm plate for 1 kg robots (15 × 2.3 × 0.2 cm, 10.6 g); 10 cm plate for 500 g robots (10 × 1.8 × 0.1 cm, 3.5 g); lightweight PCB material; packing 1 plate of the chosen size [PP]. Matches the KB.

## Interfaces, terminals and pin mapping
- Mechanical part only — no electrical interface [PP].
- Mounting holes, hole spacing and fixing hardware: **not stated** on the page [PP].

## Rules and gotchas (for code, wiring and tutorials)
- Never present it as a competition blade: the page says "not intended for official competitions" [PP].
- Match the size to the class: 15 cm ↔ 1 kg robots, 10 cm ↔ 500 g robots [PP].
- The two sizes differ in thickness (0.2 cm vs 0.1 cm) and weight (10.6 g vs 3.5 g) — quote per option [PP].
- Which price belongs to which size is inferred from the range order; the extract only gives "RM5.00–RM8.00; options 15cm / 10cm" — state the range unless the page is re-read.

## Power and electrical limits
- Not applicable (passive mechanical part) [PP].

## Software support
- Not applicable [PP].

## Compatibility and accessories
- 1 kg robots: 1KG Sumo Robot Bundles - RC (`sumo-1kg-rc-bundle.md`, which ships a 6" stainless steel blade) and SUMO:BIT Robot Kit (its Complete packing list includes a "PCB Plate for Blade (training)") [PP].
- 500 g robots: Ikedo Mini Sumo Robot V2 (`ikedo-mini-sumo-v2.md`) and Pro Bundle (`ikedo-mini-sumo-pro.md`, which ships a 4" stainless steel razor blade) [PP]. No source states the plate's mounting matches the Ikedo chassis — see Needs verification.

## Common mistakes / troubleshooting
- Ordering the 10 cm plate for a 1 kg robot (or vice versa) [PP].
- Using it in an official match — training only [PP].
- Expecting screws or a bracket — packing list is the plate alone [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | No second source exists | — | None |

## Needs verification
- Mounting hole pattern, hole diameter and compatible robot chassis (Ikedo, SUMO:BIT body, RC 1KG body).
- Which price is the 10 cm and which the 15 cm option (range RM5.00–RM8.00 only).
- PCB material grade (e.g. FR-4) and whether the plate has a copper layer (the SUMO:BIT kit's "copper base" is a different part).
- Edge finish / sharpness (not a blade — assumed blunt; not stated).

## Sources
- [PP] Product page (read by coordinator 2026-10-19) — https://my.cytron.io/p-v-pcb-sumo-plate
- [PP: SUMO:BIT kit page] packing-list cross-reference — https://my.cytron.io/p-sumobit-robot-kits-1kg-sumo-robot-for-microbit
- KB cross-references: /home/claude/kb/sumo-1kg-rc-bundle.md · /home/claude/kb/ikedo-mini-sumo-v2.md · /home/claude/kb/ikedo-mini-sumo-pro.md
