# 500g Sumo Robot Map — Verified Reference

| | |
|---|---|
| Product code | `PM-MAP-SUMO` [PP] |
| Family | Sumo robot kits and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-22 |
| Primary source | No datasheet, drawing or guide exists. Primary source = the **Cytron product page** https://my.cytron.io/cytron-oem/p-map-for-sumo-robot (read 2026-10-21) [PP] and its two images [PP: img]; Cytron team confirmation 2026-10-22  |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text, read in the browser 2026-10-21. [PP: img] = the page's images `pm-map-sumo-b.jpg` (photo: the map flat on a tiled floor with two mini sumo robots) and `pm-map-sumo-a2.jpg` (artwork: black disc with a thin white outer ring), viewed 2026-10-21. The page calls the product a "Map", "Sumo Robot Training Arena" and (packing list) "Map for Sumo Robot"; in sumo terms it is a printed practice dohyo (ring).  = Cytron team answer to the KB, 2026-10-22.

## What it is
- A flexible, printed **practice ring for 500 g (mini) sumo robots**: a black circle with a white border, printed on UV vinyl [PP].
- "Note: This map serves as a Practice Map and not for competition purposes." [PP]
- "Made from durable UV Vinyl, this arena is built to handle the fighting between Mini Sumo Robot battles"; "Its flexible design makes it easy to set up in any space" [PP].
- "Note: Please purchase this product separately, if you plan to purchase other items as well to ensure proper packaging." [PP]
- Warranty 12 months [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | UV Vinyl | [PP] |
| Outer diameter (white) | 77 cm | [PP] |
| Inner diameter (black) | 72 cm | [PP] |
| White border width | 2.5 cm — inferred from (77 − 72) / 2 | inferred |
| Start (shikiri) lines | None visible in the artwork or the photo | [PP: img] |
| Form | Flat flexible sheet laid on the floor; no raised platform | [PP][PP: img] |
| Thickness | Not stated | — |
| Weight | Not stated | — |
| Use | "Suitable for Sumo Robot training" | [PP] |
| Competition rules followed | None named; "not for competition purposes" | [PP] |
| Price | RM45.00 | [PP] |
| Stock (2026-10-21) | 29 | [PP] |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | Map for Sumo Robot |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "500g Sumo Robot Map"; Brand Cytron OEM; code PM-MAP-SUMO; 23 ratings; RM45.00; cashback RM1.35; availability 29 [PP].
- Features: suitable for sumo robot training; material UV Vinyl; diameter 77 cm (outer, white) and 72 cm (inner, black) [PP].
- "You May Also Need": Ikedo Mini Sumo Robot Pro Bundle, IR Sumo Start Module, Robot Battle (500g) - SUMO:BIT, Ikedo Mini Sumo Robot V2, SUMO:BIT Robot Kits, 1KG Sumo Robot Bundles RC, SOCCER:BIT, Maker Mini Sumo Controller, Sumo Robot 1KG Auto Kits, silicon wheels [PP].

## Interfaces, terminals and pin mapping
- None: passive printed mat [PP].
- **Edge detection:** robots find the ring edge by the black-to-white change on the border (general sumo practice; Cytron edge sensors such as Maker Reflect S are in `maker-reflect-s.md`, used by `ikedo-mini-sumo-pro.md` / `ikedo-mini-sumo-v2.md`).

## Rules and gotchas (for code, wiring and tutorials)
- **Practice only:** Cytron states it is not for competition [PP]. For an event, use the organiser's official ring.
- **Size is for the 500 g class:** 77 cm outer [PP]. The SUMO:BIT 1 kg guide uses a 1 m dohyo (`sumobit-robot-kit.md`); do not present this map as a 1 kg ring.
- **No start lines** are printed [PP: img]; mark start positions yourself if the code needs them (e.g. a 5 s countdown start).
- **Flat vinyl on the floor:** no raised edge, so a robot pushed out lands on the floor beside the mat; the floor colour around the mat affects any sensor that looks past the edge (inferred).
- **Calibrate edge sensors on the mat itself:** a printed vinyl surface reflects differently from a painted wooden dohyo (general practice, not stated by Cytron).

## Power and electrical limits
- None (passive mat) [PP].

## Software support
- None. No tutorial is linked from the page. Robot code for the 500 g class: `maker-mini-sumo.md`, `ikedo-mini-sumo-pro.md`, `ikedo-mini-sumo-v2.md`, `robot-battle-500g-sumobit.md`; start module `ir-sumo-start.md`.

## Compatibility and accessories
- 500 g / mini sumo robots: Ikedo Mini Sumo Robot V2 and Pro (`ikedo-mini-sumo-v2.md`, `ikedo-mini-sumo-pro.md`), Robot Battle (500g) - SUMO:BIT (`robot-battle-500g-sumobit.md`), robots on Maker Mini Sumo (`maker-mini-sumo.md`) [PP You May Also Need].
- IR Sumo Start Module (`ir-sumo-start.md`) for remote start [PP You May Also Need].
- 32 × 22 mm silicone wheels for 500 g robots (`sumo-silicone-wheels.md`).

## Common mistakes / troubleshooting
- **Robot drives off the edge** → re-tune edge-sensor thresholds on this mat; check the sensors see the 2.5 cm white border before the robot leaves the black area (general practice).
- **Map arrived damaged with other items** → Cytron asks buyers to order it separately for proper packaging [PP].
- **Using it to qualify a robot for an event** → it is a practice map, not a competition ring [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Robot class | [PP] title "500g Sumo Robot Map"; description "Mini Sumo Robot battles" | [PP] "You May Also Need" also lists 1 kg kits (SUMO:BIT, 1KG RC, 1KG Auto) | No spec conflict; the map is sized and titled for 500 g; the 1 kg kits are cross-sell only |

## Needs verification
- **Vinyl thickness, weight, surface finish (matt/gloss)** — not stated.
- Whether the black area has start lines in any version — none visible in the images read.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-map-for-sumo-robot — read 2026-10-21 (PM-MAP-SUMO; RM45.00; availability 29; warranty 12 months; notes; UV vinyl; 77 cm / 72 cm; packing list)
- [PP: img] https://static.cytron.io/image/catalog/products/PM-MAP-SUMO/pm-map-sumo-b.jpg and https://static.cytron.io/image/catalog/products/PM-MAP-SUMO/pm-map-sumo-a2.jpg — viewed 2026-10-21
- KB cross-references: `sumobit-robot-kit.md`, `ikedo-mini-sumo-v2.md`, `ikedo-mini-sumo-pro.md`, `robot-battle-500g-sumobit.md`, `maker-mini-sumo.md`, `maker-reflect-s.md`, `ir-sumo-start.md`, `sumo-silicone-wheels.md`
