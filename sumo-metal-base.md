# Metal Base for Sumo Robot — Verified Reference

| | |
|---|---|
| Product code | `HD-BSC-MSUMO-MB` [PP] |
| Family | Sumo robot kits and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron OEM product page read in full (description, features, packing list) and its product photo viewed. No drawing, datasheet or tutorial is linked |
| Primary source | No datasheet or drawing exists. Primary source = the **Cytron product page** https://my.cytron.io/cytron-oem/p-metal-base-for-sumo-robot (read 2026-10-21) [PP] and its photo `hd-bsc-msumo-mb-a.png` [PP: img] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text, read in the browser 2026-10-21. [PP: img] = the single product photo (black rectangular plate, two holes), viewed 2026-10-21. The packing list calls it "Metal Plate for Sumo Robot"; the 1 kg RC bundle's packing list calls the same part "metal base for mini sumo robot" (`sumo-1kg-rc-bundle.md`). The code's "MSUMO" matches Cytron's mini-sumo parts naming (e.g. Copper Base for Mini Sumo Robot, `HD-BSC-MSUMO-CB`) — inferred. The **Copper Base for Mini Sumo Robot** is a different product, not an alias.

## What it is
- A flat metal plate used as **ballast** in sumo and soccer robots: "This metal plate is commonly used in Sumo Robots and Soccer Robots to add weight. It comes with mounting holes for direct attachment to body parts using screws. It's available as a replacement part or as an upgrade for your own Sumo Robot!" [PP]
- Warranty 12 months [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | "Metal" (alloy not stated) | [PP] |
| Dimensions | 8.3 cm × 5 cm × 0.3 cm | [PP] |
| Weight | 96 g | [PP] |
| Mounting holes | M3 | [PP] |
| Number of holes | 2, near opposite corners (diagonal); they appear countersunk | [PP: img] |
| Hole positions | Not dimensioned | — |
| Finish / colour | Black | [PP: img] |
| Density check | 8.3 × 5 × 0.3 cm = 12.45 cm³; 96 g → about 7.7 g/cm³, consistent with steel (inferred, not stated) | inferred |
| Price | RM29.00; 5 or more RM27.55 | [PP] |
| Stock (2026-10-21) | 139 | [PP] |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | Metal Plate for Sumo Robot |

No screws or nuts are listed [PP].

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Metal Base for Sumo Robot"; Brand Cytron OEM; code HD-BSC-MSUMO-MB; 7 ratings; RM29.00; cashback 3%; 5 or more RM27.55; availability 139 [PP].
- Features: suitable for sumo robot to add weight; material metal; mounting holes M3; weight 96 g; dimension 8.3 cm × 5 cm × 0.3 cm [PP].
- "You May Also Need": IR Sumo Start Module, Ikedo Mini Sumo Robot Pro Bundle, Copper Base for Mini Sumo Robot, both silicon wheel sizes, 6V 800RPM micro metal gearmotor, MDDRC10, Maker Mini Sumo Controller, MDDRC5, Sumo Robot Controller R1.1 (URC10), Ikedo Mini Sumo Robot V2 [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface [PP].
- Fixes to the robot body with **M3 screws** through its mounting holes [PP]; screws are not included [PP packing list].

## Rules and gotchas (for code, wiring and tutorials)
- **Purpose is weight:** 96 g per plate [PP]. Two plates (as in `sumo-1kg-rc-bundle.md`) add 192 g (inferred arithmetic). Always weigh the finished robot against the class limit (500 g or 1 kg).
- **Size check for mini sumo:** 8.3 × 5 cm fits inside a 10 × 10 cm mini-sumo footprint, but placement depends on the body design (inferred).
- **Bring your own M3 screws** — none supplied [PP].
- **Metal plate near electronics:** keep it from shorting exposed pads, motor terminals or battery leads (general practice).
- **Low mounting helps:** fitting ballast low and near the drive wheels is general sumo practice for traction; Cytron does not state a position.

## Power and electrical limits
- None (mechanical part) [PP].

## Software support
- None. No tutorial is linked from the page. The 1 kg RC bundle tutorial lists a "Metal base" in its hardware list ("1KG RC Sumo Robot Using MDDRC10", see `sumo-1kg-rc-bundle.md`).

## Compatibility and accessories
- Used as "2x metal base for mini sumo robot" in the **1KG Sumo Robot Bundles - Radio Controlled (RC)** (`sumo-1kg-rc-bundle.md`).
- Sumo and soccer robots generally [PP]: e.g. `soccerbit-robot-kit.md`, `robot-battle-500g-sumobit.md`, `ikedo-mini-sumo-v2.md`, `ikedo-mini-sumo-pro.md` (whether those kits use this plate is not stated; the Ikedo Pro uses a copper weight base).
- Related but different: Copper Base for Mini Sumo Robot (`HD-BSC-MSUMO-CB`, RM29.00 on the wheel pages) [PP].
- Wheels: `sumo-silicone-wheels.md`; start module: `ir-sumo-start.md`.

## Common mistakes / troubleshooting
- **Robot over the weight limit after adding plates** → each plate is 96 g [PP]; remove one or use a lighter ballast.
- **Screw holes don't line up with a custom body** → only two M3 holes, positions not published; measure the plate before designing the body.
- **No screws in the bag** → buy M3 screws separately [PP packing list].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Name | [PP] title "Metal Base for Sumo Robot"; packing "Metal Plate for Sumo Robot" | [PP] 1KG RC bundle packing list "metal base for mini sumo robot" (`sumo-1kg-rc-bundle.md`) | Naming only; same part assumed (inferred from the name and the MSUMO code) |

## Needs verification
- **Metal type** (steel inferred from the weight) and finish (black coating type).
- **Hole positions and countersink** — not dimensioned; the photo shows 2 holes that appear countersunk.
- Whether the plate in the 1KG RC bundle is exactly this part (same code) — not stated.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-metal-base-for-sumo-robot — read 2026-10-21 (HD-BSC-MSUMO-MB; RM29.00, 5+ RM27.55; availability 139; warranty 12 months; description; features; packing list)
- [PP: img] https://static.cytron.io/image/catalog/products/HD-BSC-MSUMO-MB/hd-bsc-msumo-mb-a.png — viewed 2026-10-21
- KB cross-references: `sumo-1kg-rc-bundle.md`, `soccerbit-robot-kit.md`, `robot-battle-500g-sumobit.md`, `ikedo-mini-sumo-v2.md`, `ikedo-mini-sumo-pro.md`, `sumo-silicone-wheels.md`, `ir-sumo-start.md`, `pcb-sumo-plate.md`
