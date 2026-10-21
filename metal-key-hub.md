# Metal Key Hub (6 mm / 8 mm / 10 mm) — Verified Reference

| | |
|---|---|
| Product code | `CO-SPG` (6 mm), `CO-MTL-08` (8 mm), `CO-MTL-10` (10 mm) — three listings [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: all three product pages read in full in the browser; Cytron drawings read: "CO-SPG" (rev 1.0, 21-Dec-20, scale 2:1) via the Drive connector, "Bush - Steel - 8mm" (rev 1.0, 24/2/2015) and the 10 mm drawing ("Metal Key Hub 10mm.PDF") in the browser PDF viewer |
| Primary source | No datasheet. Primary sources = the **Cytron drawings** — CO-SPG (Cytron document — link not public) "Metal Key Hub - 8mm.pdf" and "Metal Key Hub - 10mm.pdf" on static.cytron.io/download [PP: drawing] — and the **three Cytron product pages** (https://my.cytron.io/cytron-oem/p-metal-key-hub-6mm, …-8mm, …-10mm), read 2026-10-21 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP: drawing] = the three Cytron drawings above (mm). The 10 mm drawing's title block was outside the visible area; its views match the 8 mm drawing except the Ø10 bore. The 6 mm hub is a different design (aluminium, M3) from the 8/10 mm hubs (steel, M5). The 6 mm mecanum hub is a separate product (`mecanum-key-hub-6mm.md`). The 8 mm and 10 mm hubs are also sold in wheel combos (`robot-wheel-5in.md`).

## What it is
- A shaft hub that "convert[s] the round output shaft of a DC motor to a flat surface" so you can attach a pulley, wheel, sprocket or mechanism [PP].
- Three listings [PP]:

| Listing | Code | Bore | Material | Size (page) | Mounting threads | Stated fit | Price | Stock |
|---|---|---|---|---|---|---|---|---|
| Metal Key Hub - 6mm | CO-SPG | 6 mm | Aluminium | 15 × 26 mm | 4 × M3 | SPG30 / SPG50 / IG32 (6 mm shaft) | RM10.50 (was RM21.00) | 87 |
| Metal Key Hub - 8mm | CO-MTL-08 | 8 mm | Zinc-plated steel | 26 × 40 mm | 3 × M5 | IG42 (8 mm shaft) | RM35.00 | 19 |
| Metal Key Hub - 10mm | CO-MTL-10 | 10 mm | Zinc-plated steel | 26 × 40 mm | 3 × M5 | IG45 / 40W DC brush motor / 30W Vexta brushless (10 mm shaft) | RM35.00 | 10 |

## Specifications
| Item | 6 mm (CO-SPG) | 8 mm (CO-MTL-08) | 10 mm (CO-MTL-10) | Src |
|---|---|---|---|---|
| Bore | Ø6 mm, round | Ø8 mm | Ø10 mm | [PP: drawing] |
| Flange | Ø25 mm × 6 mm | Ø40 mm × 12 mm | Ø40 mm × 12 mm | [PP: drawing] |
| Boss | Ø15 mm × 9 mm | Ø24 mm × 14 mm | Ø24 mm × 14 mm | [PP: drawing] |
| Overall length | 15 mm | 26 mm | 26 mm | [PP: drawing] |
| Mounting holes (flange face) | **4 × M3 threaded**, 90° apart, opposite holes 20 mm apart (Ø20 mm circle) | **3 × tapped M5** at 120° on R15.50 mm (**Ø31 mm** circle) | same as 8 mm | [PP: drawing] |
| Set-screw holes (boss) | **2 × M3 threaded**, radial, 90° apart, 4.5 mm from the flange | **Tapped M4** radial, 7 mm from the boss end (two M4 screws supplied) | same as 8 mm | [PP: drawing][PP] |
| Chamfers | C0.5 | — | — | [PP: drawing] |
| Material | Aluminium | Zinc-plated steel | Zinc-plated steel | [PP] |
| Weight | Not stated | Not stated | Not stated | — |
| Warranty | 12 months | 12 months | 12 months | [PP] |

### Packing list [PP]
| Listing | Contents |
|---|---|
| CO-SPG | 1 × 6mm Metal Key Hub; 6 × M3 screws |
| CO-MTL-08 | 1 × 8mm Metal Key Hub; 2 × M4 screw; 3 × M5 screw |
| CO-MTL-10 | "1 x 8mm Metal Key Hub" (as printed — see *Conflicts*); 2 × M4 screw; 3 × M5 screw |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- 6 mm page: "comes with 4 threaded mounting holes (M3 size)"; resources "Dimension/Drawing in PDF format"; page also embeds `CO-SPG Drawing.jpg` [PP].
- 8 mm and 10 mm pages: "comes with 3 threaded mounting holes (M5 size)"; resource "Technical Drawing" (static.cytron.io PDF) [PP].
- The 6 mm hub is offered as an accessory on the SPG30 and SPG30HP motor pages [PP of those pages].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface.
- **Hub → shaft:** set screws through the boss (6 mm: 2 × M3; 8/10 mm: M4) bear on the shaft [PP: drawing][PP]. On a **D-shaft** (SPG30 / SPG30HP) put a set screw on the flat (general practice, inferred).
- **Part → hub:** 6 mm hub — 4 × M3 into the flange (Ø20 mm circle); 8/10 mm hubs — 3 × M5 into the flange (Ø31 mm circle) [PP: drawing].
- The 8/10 mm hub's **3 × M5 on Ø31 mm** matches the 5-inch robot wheel's 3 × Ø5 holes on Ø31 mm (`robot-wheel-5in.md`) and the power-window coupling's pattern (`power-window-motor.md`) — inferred from the drawings.

## Rules and gotchas (for code, wiring and tutorials)
- The 6 mm hub (M3, Ø20 circle) and the 8/10 mm hubs (M5, Ø31 circle) are **not interchangeable** at the flange [PP: drawing].
- The 6 mm hub is aluminium — don't over-tighten the M3 set screws (inferred).
- Bores are plain round; there is no keyway despite the name "key hub" [PP: drawing].
- Of the 6 × M3 screws with the 6 mm hub, 2 are presumably the set screws and 4 the flange screws (inferred from the hole count).

## Power and electrical limits
- None (mechanical part).

## Software support
- None.

## Compatibility and accessories
- 6 mm: SPG30 / SPG30E (`dc-geared-motor-37mm-12v.md`), SPG30HP (`high-power-dc-geared-motor-12v.md`), SPG50, IG32 [PP].
- 8 mm: IG42 [PP]; with `robot-wheel-5in.md` as WL-RBT-508.
- 10 mm: IG45, 40W DC brush motor, 30W Vexta brushless [PP]; with `robot-wheel-5in.md` as WL-RBT-510.
- Brackets for these motors: `motor-bracket-spg30-spg50.md`, `motor-bracket-ig32e.md`, `motor-bracket-ig42e-ig45.md`.

## Common mistakes / troubleshooting
- **Hub slips on the shaft** → tighten the set screws; on a D-shaft, onto the flat (inferred).
- **5-inch wheel won't bolt to the 6 mm hub** → hole patterns differ; use an 8/10/15 mm hub (inferred from drawings, [PP] wheel fit list).
- **10 mm packing list says "8mm"** → listing typo; the drawing and title are 10 mm (see *Conflicts*).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 6 mm hub size | [PP: drawing] flange Ø25 mm, 15 mm long | [PP] "15mm x 26mm" | Drawing wins (Ø25 mm) |
| 10 mm packing list | [PP: drawing] / page title: 10 mm hub | [PP] packing list "1 x 8mm Metal Key Hub" | Copy error on the page; the listing ships the 10 mm hub (inferred) — report to the product team |

## Needs verification
- Number of M4 set-screw holes on the 8/10 mm hubs (the drawing labels "Tapped M4 Thread" in two views; 2 screws are supplied).
- Screw lengths supplied (not stated).
- Weights.
- The 10 mm drawing's title block, date and revision (not visible in the viewer).

## Sources
- [PP: drawing] "CO-SPG Drawing.PDF" (rev 1.0, 21-Dec-20) (Cytron document — link not public) — read 2026-10-21
- [PP: drawing] https://static.cytron.io/download/Metal%20Key%20Hub%20-%208mm.pdf ("Bush - Steel - 8mm", rev 1.0, 24/2/2015) — read 2026-10-21
- [PP: drawing] https://static.cytron.io/download/Metal%20Key%20Hub%20-%2010mm.pdf — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-metal-key-hub-6mm ; https://my.cytron.io/cytron-oem/p-metal-key-hub-8mm ; https://my.cytron.io/cytron-oem/p-metal-key-hub-10mm — read 2026-10-21
- KB cross-references: `robot-wheel-5in.md`, `power-window-motor.md`, `dc-geared-motor-37mm-12v.md`, `high-power-dc-geared-motor-12v.md`, `mecanum-key-hub-6mm.md`, `motor-bracket-spg30-spg50.md`, `motor-bracket-ig32e.md`, `motor-bracket-ig42e-ig45.md`
