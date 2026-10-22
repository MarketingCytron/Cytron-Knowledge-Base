# Metal Base for Sumo Robot — Verified Reference

| | |
|---|---|
| Product code | `HD-BSC-MSUMO-MB` [PP] |
| Family | Sumo robot kits and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-22 |
| Primary source | No datasheet or drawing exists. Primary sources = the **Cytron product page** https://my.cytron.io/cytron-oem/p-metal-base-for-sumo-robot (read 2026-10-21) [PP] and its photo [PP: img]; **Cytron team confirmation** 2026-10-22 ; geometry from the sister part's CAD, **CopperBase.stl** (linked on the Copper Base page) [PP: STL] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text, read in the browser 2026-10-21. [PP: img] = the single product photo (black rectangular plate, two holes), viewed 2026-10-21. The packing list calls it "Metal Plate for Sumo Robot"; the 1 kg RC bundle's packing list calls the same part "metal base for mini sumo robot" (`sumo-1kg-rc-bundle.md`). The code's "MSUMO" matches Cytron's mini-sumo parts naming (e.g. Copper Base for Mini Sumo Robot, `HD-BSC-MSUMO-CB`) — inferred. The **Copper Base for Mini Sumo Robot** is a different product (copper, 110 g), not an alias — but the team says the two plates are the **same size** .  = team answer to the KB, 2026-10-22. [PP: STL] = `CopperBase.stl` (Google Drive, Cytron, Feb 2025) linked under the Copper Base page's Resources; measured in the cloud workspace 2026-10-22. The Metal Base page links no STL; the team has one (not yet received).

## What it is
- A flat metal plate used as **ballast** in sumo and soccer robots: "This metal plate is commonly used in Sumo Robots and Soccer Robots to add weight. It comes with mounting holes for direct attachment to body parts using screws. It's available as a replacement part or as an upgrade for your own Sumo Robot!" [PP]
- Warranty 12 months [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Dimensions | 8.5 cm × 5 cm × 0.3 cm (team; same as Copper Base) ; page says 8.3 cm × 5 cm × 0.3 cm [PP]; Copper Base CAD measures **83.6 × 50.1 × 3.0 mm** [PP: STL] — see *Conflicts* | [PP][PP: STL] |
| Weight | 96 g | [PP] |
| Mounting holes | M3 | [PP] |
| Number of holes | 2, both counterbored from one face | [PP: img][PP: STL] |
| Hole positions (from the Copper Base CAD, same-size part) | Both on the long centre line (≈25 mm from each long edge), **49.0 mm apart**; centres 19.8 mm from one short end and 14.8 mm from the other (not symmetrical) | [PP: STL] |
| Hole profile (Copper Base CAD) | Ø3.2 mm through-hole (M3 clearance) for the last 1.0 mm; Ø6.0 mm counterbore about 2 mm deep with a rounded floor from the other face — an M3 socket-head screw sits below the surface (inferred from the 6.0 mm bore) | [PP: STL] |
| Finish / colour | Black | [PP: img] |
| Weight check | Copper Base CAD volume ≈ 12.4 cm³ after holes; × steel 7.85 g/cm³ ≈ 97 g (page 96 g) and × copper 8.96 g/cm³ ≈ 111 g (Copper Base page 110 g) — consistent with the same outline and holes in steel | inferred |
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
- Fixes to the robot body with **M3 screws** through its two counterbored holes [PP][PP: STL]; screws are not included [PP packing list]. Put the screw head on the counterbored face.

## Rules and gotchas (for code, wiring and tutorials)
- **Purpose is weight:** 96 g per plate [PP]. Two plates (as in `sumo-1kg-rc-bundle.md`) add 192 g (inferred arithmetic). Always weigh the finished robot against the class limit (500 g or 1 kg).
- **Size check for mini sumo:** about 8.4 × 5 cm fits inside a 10 × 10 cm mini-sumo footprint, but placement depends on the body design (inferred).
- **Interchangeable with the Copper Base** (same size ): the copper plate is heavier (110 g vs 96 g) for the same footprint [PP]. A body designed around `CopperBase.stl` takes either plate (inferred from the team answer; confirm the steel plate's holes against its own STL).
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
- **Screw holes don't line up with a custom body** → use the Copper Base STL positions (holes 49 mm apart on the centre line, not centred end-to-end) and orient the plate the right way round [PP: STL].
- **No screws in the bag** → buy M3 screws separately [PP packing list].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Length | Team: 8.5 cm (same as Copper Base) ; Copper Base page also says 8.5 cm [PP] | Metal Base page: 8.3 cm [PP]; Copper Base CAD: 83.6 mm [PP: STL] | Quote "about 8.4 × 5 × 0.3 cm" and give the CAD figure (83.6 × 50.1 × 3.0 mm) for body design; ask the web team to align both pages |
| Hole layout | Earlier KB reading of the photo: holes "near opposite corners (diagonal)" | Copper Base CAD: both holes on the long centre line; the photo re-checked 2026-10-22 is consistent with this (perspective view) | Use the CAD layout; confirm with the steel plate's STL |
| Name | [PP] title "Metal Base for Sumo Robot"; packing "Metal Plate for Sumo Robot" | [PP] 1KG RC bundle packing list "metal base for mini sumo robot" (`sumo-1kg-rc-bundle.md`) | Naming only; same part assumed (inferred from the name and the MSUMO code) |

## Needs verification
- Hole positions **measured on the steel plate's own STL** (the team has it; the figures here come from the Copper Base CAD, which the team says is the same size).
- Black finish type (paint, powder coat or oxide).
- Whether the plate in the 1KG RC bundle is exactly this part (same code) — not stated.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-metal-base-for-sumo-robot — read 2026-10-21 (HD-BSC-MSUMO-MB; RM29.00, 5+ RM27.55; availability 139; warranty 12 months; description; features; packing list)
- [PP: img] https://static.cytron.io/image/catalog/products/HD-BSC-MSUMO-MB/hd-bsc-msumo-mb-a.png — viewed 2026-10-21
- [PP] Copper Base for Mini Sumo Robot https://my.cytron.io/p-copper-base-for-mini-sumo-robot (HD-BSC-MSUMO-CB, copper, 110 g, 8.5 × 5 × 0.3 cm) — read 2026-10-22
- [PP: STL] CopperBase.stl (Cytron document — link not public) (Feb 2025) — measured 2026-10-22
- KB cross-references: `sumo-1kg-rc-bundle.md`, `soccerbit-robot-kit.md`, `robot-battle-500g-sumobit.md`, `ikedo-mini-sumo-v2.md`, `ikedo-mini-sumo-pro.md`, `sumo-silicone-wheels.md`, `ir-sumo-start.md`, `pcb-sumo-plate.md`
