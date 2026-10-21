# 12V High Power Brushed DC Geared Motors (SPG30HP-30K / SPG30HP-10K) — Verified Reference

| | |
|---|---|
| Product code | `SPG30HP-30K` (12V 380RPM 1.4kgfcm) and `SPG30HP-10K` (12V 1100RPM 0.5kgfcm) — two separate listings [PP] |
| Family | Motors (Cytron OEM) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: both product pages read in full in the browser; both linked "Motor Dimension and Spec" outline drawings (SPG30HP-30K.pdf, SPG30HP-10K.pdf, each a 1-page "DC Geared Motor Outline Drawing" with a specification block) read in the Drive viewer at full resolution; linked and related tutorials read for relevant facts |
| Primary source | **Outline drawings with specification** "SPG30HP-30K" (Production No. CCN5-227-1603212) and "SPG30HP-10K" (Production No. CCN5-227-1603211), linked as "Motor Dimension and Spec" [DS], and the **Cytron product pages** https://my.cytron.io/cytron-oem/p-12v-380rpm-1.4kgfcm-high-power-brushed-dc-geared-motor and https://my.cytron.io/cytron-oem/p-12v-1100rpm-0.5kgfcm-high-power-brushed-dc-geared-motor, read 2026-10-21 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [DS] = the two outline drawings (supplier-style drawing with "SPECIFICATIONS — For reference only" block; "The final specifications depend on the test result of samples"); no manufacturer name is printed on them. [PP] = the two product pages. [PP: tutorial] = Cytron tutorials linked or shown as related on the pages. Both listings share one file because they are the same SPG30HP motor with a 30:1 or 10:1 gearhead. Not the same product as the standard SPG30 (`dc-geared-motor-37mm-12v.md`).

## What it is
- A "high power range of SPG30 gear motor": 12 V brushed DC motor with a Ø37 mm spur gearbox and 6 mm D-shaft, giving "higher speed and higher torque compared to its SPG30 sibling" but drawing more current [PP].
- Two listings [PP]:

| Listing | Code | Gear ratio | No-load speed | Rated torque | Price | Stock (21 Oct 2026) |
|---|---|---|---|---|---|---|
| 12V 380RPM 1.4kgfcm High Power Brushed DC Geared Motor | SPG30HP-30K | 30:1 | 380 RPM | 1.4 kgf·cm (137 mN·m) | RM55.00 | 27 |
| 12V 1100RPM 0.5kgfcm High Power Brushed DC Geared Motor | SPG30HP-10K | 10:1 | 1100 RPM | 0.5 kgf·cm (49 mN·m) | RM55.00 | 81 |

- "The maximum current of this motor may exceed 5 Amp, so please make sure you drive it with a DC motor driver that can withstand at least 5 Amp current." [PP]
- No encoder version is offered [PP].

## Specifications
| Item | SPG30HP-30K | SPG30HP-10K | Src |
|---|---|---|---|
| Rated voltage | 12 V | 12 V | [DS][PP] |
| No-load speed | 380 RPM ±10% | 1100 RPM ±10% | [DS][PP] |
| No-load current | ≤ 0.3 A | ≤ 0.3 A | [DS][PP "< 0.3A"] |
| Rated-load speed | 300 RPM ±10% | 865 RPM ±10% | [DS][PP] |
| Rated-load current | ≤ 1 A | ≤ 1 A | [DS][PP "< 1A"] |
| Rated-load torque | 1.4 kg·cm (137 mN·m) | 0.5 kg·cm (49 mN·m) | [DS][PP] |
| Permitted max torque | 6.5 kg·cm | 2.0 kg·cm | [DS] |
| Permitted max current | ≤ 3.7 A | ≤ 3.7 A | [DS] |
| Max current (page note) | "may exceed 5 Amp" | "may exceed 5 Amp" | [PP] |
| Total gear ratio | 1:30 | 1:10 | [DS][PP] |
| Weight | 160 g | 160 g | [PP] |
| Gearbox | Ø37 ± 0.2 mm × **21.5 ± 0.2 mm** long | Ø37 ± 0.2 mm × **19 ± 0.2 mm** long | [DS] |
| Motor can | Ø32.8 ± 0.3 mm × 22.7 ± 0.3 mm | same | [DS] |
| Shaft boss | Ø12 ± 0.1 mm × 6 ± 0.2 mm | same | [DS] |
| Output shaft | Ø6 mm (−0.002/−0.030), D-flat 5.4 mm, D-flat length 12 ± 0.2 mm, 21 ± 0.5 mm from boss face | same | [DS] |
| Shaft (page) | "D-shaped with 6mm diameter, 15.5mm in length" | same | [PP] |
| Shaft offset | 7 ± 0.15 mm from gearbox centre | same | [DS] |
| Gearbox mounting holes | **6 × M3, depth ≤ 3.5 mm**, on Ø31 mm circle ("3-120°" groups) | same | [DS] |
| Encoder | None | None | [PP] |
| Warranty | 3 months from purchase | 3 months | [PP] |

### Packing list [PP]
| Listing | Contents |
|---|---|
| SPG30HP-30K | 1 × 12V 380RPM 1.4kgfcm High Power Brushed DC Geared Motor |
| SPG30HP-10K | 1 × 12V 1100RPM 0.5kgfcm High Power Brushed DC Geared Motor |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Both pages: "Note: Motor's warranty period is 3 months from the purchase date"; accessories offered: DC Geared Motor Bracket (SPG30/SPG50) RM14.00 and Metal Key Hub – 6mm RM10.50; description images show the SPG bracket, a plastic wheel for SPG30/SPG50 and the 6 mm metal key hub [PP].
- Resources: "Motor Dimension and Spec" (Drive PDF); tutorials "How to choose a DC motor", "5 Easiest Ways to Control A DC Motor", "Control a DC Motor Using Arduino" [PP].
- "You May Also Need" includes the 12V 37MM DC Geared Motor, 10Amp 5V-30V DC Motor Driver (2 Channels), 13Amp 6V-30V DC Motor Driver (MD10C), 60Amp SmartDrive (2 channels) and the Motor Mount & 5 Inches Wheel Bundle (30K page) [PP].

## Interfaces, terminals and pin mapping
- Two solder tabs on the motor rear cap; no leads are supplied (packing list is the motor only) [DS][PP]. Polarity marking on the tabs is not legible in the drawing (one tab appears marked — not confirmed).
- Reverse the two motor wires to reverse direction [PP: tutorial "Choosing a DC Motor"].

## Rules and gotchas (for code, wiring and tutorials)
- **Driver rating:** the page asks for a driver that withstands at least 5 A [PP]; the drawing's permitted maximum is ≤ 3.7 A [DS]. Use a 10 A-class driver for headroom (inferred).
- **Mounting screws must be short:** the gearbox M3 holes are only ≤ 3.5 mm deep [DS]; with a 1.5 mm bracket, an M3 × 4 mm screw (as supplied with `HD-BK-SPG`) leaves ~2.5 mm engagement (arithmetic). Longer screws can bottom out on the gears (inferred).
- Gearbox length differs between the two ratios (21.5 mm vs 19 mm) [DS] — shaft position along a chassis changes if you swap ratios.
- Don't call these "SPG30" in tutorials without "HP": the standard SPG30 has a different motor (Ø34.5 mm can) and different currents (`dc-geared-motor-37mm-12v.md`).
- Warranty is only 3 months [PP].

## Power and electrical limits
- 12 V rated; no-load ≤ 0.3 A, rated ≤ 1 A, permitted max ≤ 3.7 A [DS]; page: may exceed 5 A [PP].
- **Driver choice:**
  - **MDD10A** (`mdd10a.md`), **MD10C** (`md10c.md`), **MD10-POT** (`md10-pot.md`): 10–13 A continuous — comfortably above both limits (inferred). The 10K turntable tutorial uses **MD10-POT** with a 7.4 V LiPo [PP: tutorial].
  - **MDD3A** (`mdd3a.md`, 3 A continuous / 5 A peak, 4–16 V): used by Cytron's tutorials with **two SPG30HP-30K on an 11.1 V LiPo** (MDD3A getting-started; Raspberry Pi + Maker pHAT + Maker Line robot) [PP: tutorial]; matches the page's "at least 5 A" only at peak — fine for light robots, marginal for stalls (inferred).
  - Not suitable: **Maker Drive** (`maker-drive.md`, 1 A, max 9.5 V) and the **3A Motor Driver Shield** (`shield-3amotor.md`, 1.2 A continuous) for loaded use (inferred from ratings).

## Software support
- No motor-specific library. Cytron tutorials: "Getting Started With MDD3A/MAKER DRIVE Using Arduino" (Maker UNO, MDD3A PWM_PWM mode, 2 × SPG30HP-30K, 11.1 V 2200 mAh LiPo, SPG30/SPG50 brackets) [PP: tutorial]; "Raspberry Pi Line Following Robot with Maker Line" (Raspberry Pi Zero WH, Maker pHAT, Maker Line, Robo Base kit, SPG30HP-30K, MDD3A) [PP: tutorial]; "Make Turntable using MD10-POT Motor Driver" (SPG30HP-10K, no programming) [PP: tutorial].

## Compatibility and accessories
- Bracket: `HD-BK-SPG` (`motor-bracket-spg30-spg50.md`) — offered on both pages [PP]; the bracket face has 2 × Ø3.3 holes 31 mm apart that match the gearbox's Ø31 mm hole circle (inferred from both drawings).
- Shaft hub: Metal Key Hub – 6mm `CO-SPG` (`metal-key-hub.md`) [PP]; 60 mm mecanum hub `CO-MEC-06` (`mecanum-key-hub-6mm.md`) fits 6 mm shafts.
- Boards used in Cytron tutorials: Maker UNO (`maker-uno.md`), Maker pHAT (`maker-phat.md`), Maker Line (`maker-line.md`), Robo Base (`robo-base.md`) [PP: tutorial].

## Common mistakes / troubleshooting
- **Driver shuts down or burns** → stall current can exceed 5 A [PP]; use a 10 A-class driver.
- **Screws jam the gearbox** → M3 holes are ≤ 3.5 mm deep [DS]; use M3 × 4 mm through a 1.5 mm bracket.
- **Motor too fast for a robot** → the 10K (1100 RPM) is a speed motor; robots in Cytron tutorials use the 30K (380 RPM) [PP: tutorial].
- **Early failure** → a reviewer reports one of two motors burnt after 3 weeks [PP review — anecdotal, not a spec]; keep within ≤ 1 A rated load.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Maximum current | [DS] permitted max ≤ 3.7 A | [PP] "may exceed 5 Amp" | Different quantities (permitted operating max vs real stall); size the driver for ≥ 5 A as the page says |
| Shaft length | [DS] 21 ± 0.5 mm from the boss face | [PP] 15.5 mm | Unresolved; 15.5 mm may be the usable length beyond the boss (inferred) — measure a sample |
| Weight | — | [PP] 160 g for both ratios | Not on the drawing; page value used |

## Needs verification
- Real stall current and stall torque (only "permit max" and "may exceed 5 A" are given).
- Which motor tab is "+" and the rotation direction for positive voltage (the drawing has a direction arrow but the text is not legible).
- Shaft length definition (15.5 vs 21 mm).
- Original motor manufacturer (not named).
- The page video ("Play") was not readable.

## Sources
- [DS] "Motor Dimension and Spec" SPG30HP-30K.pdf (Cytron document — link not public) (Production No. CCN5-227-1603212) — read in the Drive viewer 2026-10-21
- [DS] "Motor Dimension and Spec" SPG30HP-10K.pdf (Cytron document — link not public) (Production No. CCN5-227-1603211) — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-12v-380rpm-1.4kgfcm-high-power-brushed-dc-geared-motor — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-12v-1100rpm-0.5kgfcm-high-power-brushed-dc-geared-motor — read 2026-10-21
- [PP: tutorial] https://my.cytron.io/tutorial/getting-started-mdd3a-makerdrive-motor-driver-using-arduino ; https://my.cytron.io/tutorial/raspberry-pi-line-following-robot-with-maker-line ; https://my.cytron.io/tutorial/turntable-md10pot ; https://my.cytron.io/tutorial/choosing-dc-motor ; https://my.cytron.io/tutorial/5-easiest-ways-control-dc-motor ; https://my.cytron.io/tutorial/getting-started-3a-motor-driver-shield/ — read 2026-10-21 for relevant facts
- KB cross-references: `dc-geared-motor-37mm-12v.md`, `motor-bracket-spg30-spg50.md`, `metal-key-hub.md`, `mecanum-key-hub-6mm.md`, `mdd10a.md`, `md10c.md`, `md10-pot.md`, `mdd3a.md`, `maker-drive.md`, `shield-3amotor.md`, `maker-uno.md`, `maker-phat.md`, `maker-line.md`, `robo-base.md`
