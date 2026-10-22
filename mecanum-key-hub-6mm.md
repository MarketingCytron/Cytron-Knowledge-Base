# 6mm Key Hub for 60mm Mecanum Wheel — Verified Reference

| | |
|---|---|
| Product code | `CO-MEC-06` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: product page read in full in the browser; Cytron SolidWorks drawing "CO-MEC-06" (rev 1.0, 6/8/2023, scale 2:1) read via the Drive connector |
| Primary source | No datasheet. Primary sources = the **Cytron drawing "CO-MEC-06"** ((Cytron document — link not public) linked as "Dimension") [PP: drawing] and the **Cytron product page** https://my.cytron.io/cytron-oem/p-6mm-key-hub-for-60mm-mecanum-wheel, read 2026-10-21 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP: drawing] = Cytron drawing CO-MEC-06 (front view, section A-A, side view, iso). The 60 mm Mecanum Wheel itself is a separate listing with no KB file. Not the same part as the general 6 mm Metal Key Hub `CO-SPG` (`metal-key-hub.md`), and not related to the 48 mm mecanum wheels of the Robo Base kit (`robo-base.md`, TT motors).

## What it is
- An aluminium shaft hub that mounts to Cytron's **60mm Mecanum Wheel** so a small omnidirectional robot can be built on **SPG30 / SPG50 / IG32** DC geared motors (6 mm shafts) [PP].
- "You can mount it directly to the 60mm Mecanum Wheel before you connect to the motor" [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | Aluminium | [PP] |
| Outside diameter | 28 mm (drawing Ø28.00 ± 0.05 mm flange) | [PP][PP: drawing] |
| Bore | 6 mm (drawing Ø6.00 +0.02/0 mm) — "fit with most of the 6mm shaft DC Geared Motors" | [PP][PP: drawing] |
| Flange thickness | 4 mm | [PP: drawing] |
| Boss | Ø15 mm | [PP: drawing] |
| Overall height | 12 mm | [PP: drawing] |
| Wheel mounting holes | **3 × Ø3.20 mm** through holes on a **Ø23 mm** circle (evenly spaced as drawn — 120° inferred) | [PP: drawing] |
| Set-screw hole | **1 × M4 thread**, radial, centre 8 mm from the boss end | [PP: drawing] |
| Net weight | 12 g | [PP] |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | 6mm Key Hub for 60mm Mecanum Wheel |
| 1 | M3 screw |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Description image: "60mm Mecanum Wheel with 6mm Key Hub" (photo, not read for dimensions) [PP].
- Resources: Dimension (Drive PDF) [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface.
- **Hub → wheel:** 3 × Ø3.2 mm clearance holes on Ø23 mm, i.e. M3 screws through the flange into the wheel (inferred from hole size; screws for this are not listed in the packing list).
- **Hub → shaft:** one radial **M4** threaded hole for a set screw [PP: drawing]; on a D-shaft (SPG30 / SPG30HP) tighten it onto the flat (inferred).

## Rules and gotchas (for code, wiring and tutorials)
- Order one hub per wheel; a 4-wheel mecanum robot needs four hubs and four 60 mm mecanum wheels (inferred).
- The hub's set-screw thread is **M4** but the page supplies **one M3 screw** — check before assembly (see *Conflicts*).
- The 3 × Ø3.2 flange holes are clearance holes (not threaded) [PP: drawing].
- Mecanum wheel orientation (left/right roller direction) must alternate — see the Robo Base mecanum notes in `robo-base.md` for the general rule (that kit uses different 48 mm wheels).

## Power and electrical limits
- None (mechanical part).

## Software support
- None.

## Compatibility and accessories
- Wheel: 60mm Mecanum Wheel (separate listing; no KB file) [PP].
- Motors: SPG30 / SPG30E (`dc-geared-motor-37mm-12v.md`), SPG30HP (`high-power-dc-geared-motor-12v.md`, 6 mm D-shaft), SPG50, IG32 [PP].
- Brackets: `motor-bracket-spg30-spg50.md` (HD-BK-IG3X (IG32E bracket, being discontinued — not in the KB)).

## Common mistakes / troubleshooting
- **Supplied screw doesn't fit the side hole** → the drawing shows an M4 thread; use an M4 set screw (see *Conflicts*).
- **Wheel wobbles** → tighten all three flange screws evenly (inferred).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Set-screw size | [PP: drawing] radial "M4 Thread" | [PP] packing list "1 x M3 screw" | Unresolved — the M3 screw may be meant for something else; confirm with the product team before quoting |

## Needs verification
- Which screw the single M3 screw is for, and whether wheel-mounting screws come with the wheel.
- Set-screw size (M3 vs M4).
- Exact angular spacing of the three flange holes (drawn evenly, angle not dimensioned).

## Sources
- [PP: drawing] "CO-MEC-06.pdf" (rev 1.0, 6/8/2023) (Cytron document — link not public) — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-6mm-key-hub-for-60mm-mecanum-wheel — read 2026-10-21
- KB cross-references: `metal-key-hub.md`, `dc-geared-motor-37mm-12v.md`, `high-power-dc-geared-motor-12v.md`, `motor-bracket-spg30-spg50.md`, `robo-base.md`
