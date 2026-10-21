# 5 Inches Robot Wheel (without hub / with 8 mm / with 10 mm key hub) — Verified Reference

| | |
|---|---|
| Product code | `WL-RBT-5` (without key hub), `WL-RBT-508` (with 8 mm key hub), `WL-RBT-510` (with 10 mm key hub) — three listings [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: all three product pages read in full in the browser; Cytron drawing "5 Inch Wheel" (rev 1.0, 3/3/2015, A4 1:2, mm) read in the Drive viewer; the 8 mm and 10 mm key-hub drawings are documented in `metal-key-hub.md` |
| Primary source | No datasheet. Primary sources = the **Cytron drawing "5 Inch Wheel"** ((Cytron document — link not public) linked as "5 inches wheel Dimension" / "Dimension") [PP: drawing] and the **three Cytron product pages** (https://my.cytron.io/cytron-oem/p-5-inches-robot-wheel-without-key-hub, …-with-8mm-key-hub, …-with-10mm-key-hub), read 2026-10-21 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = the three product pages. [PP: drawing] = Cytron "5 Inch Wheel" drawing (front, side, section A-A, iso views). The key hubs in the combo listings are the same parts as `metal-key-hub.md` (CO-MTL-08 / CO-MTL-10) — documented there, not here. The 15 mm key hub and "5 inches Robot wheel with 15mm key hub" are mentioned on the page but are not in this batch.

## What it is
- A **5-inch (127 mm) robot wheel**, "Cytron's custom design": ABS rim with a TPE outer tyre that "provides perfect size and good friction force on most of the surface" [PP].
- Three listings [PP]:

| Listing | Code | Contents | Stated fit | Price | Stock |
|---|---|---|---|---|---|
| 5 Inches Robot Wheel Without Key Hub | WL-RBT-5 | wheel only | Cytron 8 mm, 10 mm and 15 mm metal key hubs | RM50.00 | 94 |
| 5 Inches Robot Wheel With 8mm Key Hub | WL-RBT-508 | 5-inch rubber wheel + 8 mm metal key hub | IG42 DC geared motor or any motor with 8 mm round shaft | RM80.00 | 1 |
| 5 Inches Robot Wheel With 10mm Key Hub | WL-RBT-510 | 5-inch rubber wheel + 10 mm metal key hub | IG45 DC geared motor, 30W Vexta brushless motor, 40W DC brush motor, any motor with 10 mm round shaft | RM80.00 | 15 |

- Combo listings: "The metal key coupling/hub is made of steel with zinc plated and comes with the necessary bolts for mounting" [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Outer diameter | 5 inches; drawing R63.50 mm = **Ø127 mm** | [PP][PP: drawing] |
| Width | **25.40 mm** | [PP: drawing] |
| Rim material | ABS | [PP] |
| Tyre material | TPE (combo pages: "rubber"; bundle page: "thermoplastic rubber") | [PP] |
| Centre bore | **Ø10.40 mm** | [PP: drawing] |
| Hub mounting holes | **3 × Ø5 mm** at 120° on a **Ø31 mm** circle (R15.50) | [PP: drawing] |
| Hub seat | Ø40.30 mm recess/boss around the centre (the leader's target is not fully clear — inferred hub seat) | [PP: drawing] |
| Other drawing dims | Ø104 mm (rim/tyre interface), Ø96 mm (inner rim), section 17.19 / 18.93 / 2 / 2.47 / 2.50 mm; tyre embossed "www.cytron.com.my" | [PP: drawing] |
| Weight | Not stated | — |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Listing | Contents |
|---|---|
| WL-RBT-5 | 5 Inches Robot Wheel (no packing list section; hub not included) |
| WL-RBT-508 | 5 Inches Rubber Wheel; Metal Key Hub 8mm (with mounting bolts) |
| WL-RBT-510 | 5 Inches Rubber Wheel; Metal Key Hub 10mm (with mounting bolts) |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Resources: WL-RBT-5 — "Dimension"; WL-RBT-508 — "8mm metal Key hub dimension", "5 inches wheel Dimension"; WL-RBT-510 — "10mm Metal Key Hub Dimension", "5 inches wheel Dimension" (also under Attachments) [PP].
- The 8 mm combo had only 1 unit in stock on 2026-10-21 (still sellable) [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface.
- **Wheel → hub:** the wheel's 3 × Ø5 mm holes on Ø31 mm match the **3 × tapped M5 on Ø31 mm (R15.5)** of the Cytron 8 mm / 10 mm metal key hubs (`metal-key-hub.md`) and the power-window coupling (`power-window-motor.md`) — M5 screws pass through the wheel into the hub (inferred from the drawings).
- **Hub → shaft:** M4 set screws in the key hub (see `metal-key-hub.md`).
- The **6 mm** metal key hub (CO-SPG, Ø25 flange, 4 × M3 on Ø20) is **not** listed as a fit and its hole pattern differs (inferred from the drawings).

## Rules and gotchas (for code, wiring and tutorials)
- The wheel alone has **no shaft fitting** — buy a combo or a separate 8/10/15 mm key hub [PP].
- The hubs are for **round** shafts (8 mm IG42, 10 mm IG45 etc.) [PP]; they are not for 6 mm D-shaft SPG motors.
- Wheel diameter for speed calculations: 127 mm (circumference ≈ 399 mm — arithmetic).

## Power and electrical limits
- None (mechanical part).

## Software support
- None.

## Compatibility and accessories
- Hubs: `metal-key-hub.md` (8 mm and 10 mm; 15 mm not in KB) [PP].
- Motors named: IG42 (8 mm), IG45 / 30W Vexta brushless / 40W DC brush (10 mm) — no KB files; power-window motor via its coupling (`power-window-motor.md`), as in `motor-mount-5in-wheel-bundle.md` [PP].
- Brackets for the named motors: `motor-bracket-ig42e-ig45.md` [PP].

## Common mistakes / troubleshooting
- **Wheel wobbles** → tighten all three M5 screws evenly and the hub's set screws on the shaft (inferred).
- **Hub doesn't match the holes** → only the Ø40-flange hubs (8/10/15 mm) match; the 6 mm hub does not (inferred).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Tyre material | [PP WL-RBT-5] tyre TPE, rim ABS | [PP combos] "outer ring is made of rubber" | Same part; TPE is a rubber-like thermoplastic — use "TPE (rubber-like)" |

## Needs verification
- Meaning of the Ø40.30 mm dimension (hub seat vs recess).
- Weight and load rating.
- Tyre colour options (bundle photo shows blue — not stated).

## Sources
- [PP: drawing] "5 Inch Wheel.PDF" (rev 1.0, 3/3/2015) (Cytron document — link not public) — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-5-inches-robot-wheel-without-key-hub — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-5-inches-robot-wheel-with-8mm-key-hub — read 2026-10-21 (linked hub drawing (Cytron document — link not public) not opened separately; the 8 mm hub drawing was read from the hub's own page, see `metal-key-hub.md`)
- [PP] https://my.cytron.io/cytron-oem/p-5-inches-robot-wheel-with-10mm-key-hub — read 2026-10-21 (linked hub drawing (Cytron document — link not public) not opened separately)
- KB cross-references: `metal-key-hub.md`, `power-window-motor.md`, `motor-mount-5in-wheel-bundle.md`, `motor-bracket-ig42e-ig45.md`
