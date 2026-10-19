# Robo Base — Verified Reference

| | |
|---|---|
| Product code | `Robo Base (series page code V-ROBO-BASE-MINI)` [PP] — Robo Base and Robo Base Mini are sold as two "series" choices on one product page; no separate Cytron SKU for Robo Base is shown in text |
| Family | Robot platforms and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: all 16 parts of the "Getting Started with Robo Base" tutorial series read in full, plus the product page's Dimension, Material & Thickness and Comparison images. Hardware part — guide tutorial is the main source (KB rule 7); no datasheet required |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
- A PCB chassis plate for building small mobile robot cars, or for use as an adapter plate to mount a Cytron controller board on another chassis [PP].
- Made of "durable PCB material" — described as a "cost-friendly alternative to metal chassis and tougher than fragile acrylic plates" [PP]. Cytron's BEETLE:BIT page, which ships 2x Robo Base plates, calls the chassis "non-copper PCB" [PP: BEETLE:BIT page, see `beetlebit.md`].
- Pre-made mounting holes for Cytron controller boards; sensors, ball castors, DC motors or servo motors attach to it with standard screws, nuts and standoffs [PP].
- Sold as Single Base Only or in "Double Base" kits (two plates stacked on standoffs) with 2WD, 4WD (mecanum) or accessories-only contents [PP].
- Warranty 12 months [PP].

## Specifications
No datasheet spec table exists. Facts stated in text:

| Item | Value | Src |
|---|---|---|
| Material | PCB ("durable PCB material"); "non-copper PCB" on the BEETLE:BIT page | [PP] |
| Thickness | 2.0 mm | [PP: img] |
| Dimensions | 154 × 124 × 2 mm; mounting holes Ø3 mm | [PP: img] |
| Material | Non-copper PCB (Printed Circuit Board), yellow, with printed position labels | [PP: img] |
| Labels | "With Label" — the plate is silkscreened with mounting positions: REKA:BIT, MOTION Series, Arduino UNO, ROBO Series / Maker Pi RP2040, Raspberry Pi 4/5, Jetson Series, Maker Drive, Micro Servo Motor, Ultrasonic Sensor | [PP: img] |
| Servo mounting holes | 3 | [PP: img] |
| Use | Robot base | [PP: img] |
| Weight | Not stated | — |
| Fixings used | Standard screws, nuts and standoffs; kit hardware is M3 | [PP] |
| Kit options | Double Base 4WD (Mecanum Wheels) / Double Base 2WD (Rubber Wheels) / Double Base with Accessories / Single Base Only | [PP] |
| Standoffs in Double Base kits | 4x M3 PCB stand (screw+nut) **30 mm** + 4x M3 PCB stand 10 mm (Robo Base Mini uses 25 mm instead of 30 mm) | [PP] |
| Warranty | 12 months | [PP] |
| Price (series page) | RM9.00–RM112.00 across both Robo Base and Robo Base Mini options; per-option prices not stated in text | [PP] |
| Tutorial product card | "Robo Base Basic Bundle" RM41.80 (contents not stated) | [PP: tutorial GS-RB] |

### Packing lists [PP]
| Option | Contents |
|---|---|
| Double Base 4WD (Mecanum Wheels) | 2x Robo Base, 4x M3 PCB stand (screw+nut) 30mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 4x TT motor 15cm wire, 2x 48mm Mecanum left and right wheel set, 2x TT DC gear motor bracket |
| Double Base 2WD (Rubber Wheels) | 2x Robo Base, 4x M3 PCB stand 30mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 2x TT motor 15cm wire, 2x plastic wheels, 2x TT motor bracket, 1x W420 ball castor |
| Double Base with Accessories | 2x Robo Base, 4x M3 PCB stand 30mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench (no motors, wheels or castor) |
| Single Base Only | 1x Robo Base |

## Interfaces, terminals and pin mapping
- Mechanical part only; no electrical connections, pins or terminals [PP].
- Mounting holes are Ø3 mm [PP: img]; positions for each board and accessory are printed on the plate and shown in the tutorial figures [PP: img][PP: tutorial GS-RB].
- **Assembly order (tutorial):** DC Motor > Castor > Sensor > Servo > Boards [PP: tutorial GS-RB].
- **TT motors:** fit the TT motor bracket so the screw heads face away from the motor wires, and mount the two metal brackets in opposite directions; wires face inward. 2WD: motors on top of the plate (lower layer of a double-layer car) or under it (then the castor needs extra PCB standoffs: two M3×6 mm bolts, M3 nuts and 30 mm standoffs). Positions are marked for both **N20 and W420 ball castors** [PP: tutorial GS-RB].
- **4WD mecanum:** four TT motors with metal brackets; each mecanum wheel's orientation is opposite to (not parallel with) the adjacent wheels [PP: tutorial GS-RB].
- **Ultrasonic sensor:** bracket fixed with 2 M3 bolts and nuts; same position on single- or double-layer builds [PP: tutorial GS-RB].
- **Maker Line:** centred on the plate with 2 M3 bolts and nuts; route wires through the plate's holes/slots [PP: tutorial GS-RB].
- **Micro servo:** fixed with **M2** bolts and nuts [PP: tutorial GS-RB].
- **⌀37 mm 12V DC motor:** bracket fixed with 4 M3 bolts and nuts, motor to bracket with 2 M3 bolts and nuts (6 sets in total); the two brackets face opposite directions. Cytron warns the wires sit close together — use heat-shrink tubing to prevent short circuits [PP: tutorial GS-RB].
- **Controller boards** (all on 10 mm standoffs, wires connected first): REKA:BIT, MOTION:BIT / MOTION:BIT Pro / MOTION 2350 Pro, Robo Pico / Robo ESP32 and Maker Pi RP2040 use **M3** standoffs; Raspberry Pi 4/5 and Jetson boards use **M2.5** standoffs, bolts and nuts; Maker UNO mounts flat with 4 M3 bolts and nuts (no standoffs), with Maker Drive on 10 mm M3 standoffs beside it [PP: tutorial GS-RB].
- **Double-layer car:** 4 × 30 mm standoffs on the lower plate, the controller on 10 mm standoffs on the upper plate, then the two plates joined with 4 M3 bolts; a Mini Cross Sleeve (the kit's mini cross wrench) tightens the nuts [PP: tutorial GS-RB].

## Rules and gotchas (for code, wiring and tutorials)
- **No controller, battery, sensors or servo in any kit** — none appear in the packing lists [PP]. Tutorials must list a controller board, power source and sensors separately.
- **Standoffs are 30 mm (+10 mm)** for Robo Base; 25 mm (+10 mm) for Robo Base Mini [PP]. Don't copy Mini hardware into Robo Base text.
- **4WD kit = mecanum wheels and 4 TT motors**; 2WD kit = 2 TT motors, 2 wheels and a W420 ball castor [PP].
- **⌀37mm 12V DC motor mounting is a Robo Base tutorial section** [PP: tutorial GS-RB]; it is not listed for Robo Base Mini. The 37 mm motor itself is not in any kit [PP].
- **Battery mounting** is not covered in any part of the Robo Base tutorial series (it is in the Robo Base Mini tutorial) — don't claim a battery position for Robo Base.
- **Raspberry Pi and Jetson need M2.5 hardware**, which is not in any Robo Base kit (kits contain M3 only) [PP][PP: tutorial GS-RB].
- **Micro servo uses M2 bolts**, also not in the kits [PP: tutorial GS-RB].
- If a board won't fit because a motor or sensor is in the way, Cytron's advice is to move the other component, not the board [PP: tutorial GS-RB].
- **"Rubber Wheels" vs "plastic wheels":** the 2WD option name says rubber, its packing list says "2x plastic wheels" [PP]. Write "wheels" or quote the packing list.
- Size: 154 × 124 × 2 mm [PP: img] — do not give Robo Base Mini's 109 × 88 × 1.6 mm.
- Single Base Only is just the plate — no screws or standoffs [PP].

## Power and electrical limits
- None (mechanical part). Motor and servo limits belong to the controller board's KB file (e.g. `reka-bit.md`, `motion-bit.md`, `motion-2350-pro.md`, `robo-pico.md`, `maker-drive.md`).

## Software support
- None needed for the chassis. Cytron example projects using Robo Base [PP]: "Getting Started with Robo Base" (16 Jun 2025, 17-part series); "Fire Fighting Robot using MOTION 2350 Pro" (24 Feb 2026; tags Robo Base, Maker Drive, Servo Motor); "Line Following with Robo Base using URC10" (30 Jul 2025). The series page also links "Robot with ESP32 and FreeRTOS" and a Raspberry Pi line-following robot with Maker Line, without saying which base they use [PP]. Tutorial bodies were not read.

## Compatibility and accessories
- **Controller boards with matching mounting holes** [PP]: REKA:BIT, MOTION:BIT, MOTION:BIT Pro, MOTION 2350 Pro, Robo Pico, Maker Pi RP2040, Maker UNO or Arduino UNO form factor, Maker UNO + Maker Drive, Raspberry Pi 4 or 5, Jetson series. The tutorial's mounting section also names "Robo series" [PP: tutorial GS-RB].
- **Attachments** [PP][PP: tutorial GS-RB]: TT DC gear motors (with TT motor bracket), ⌀37mm 12V DC motor, ball castor (W420 in the 2WD kit), ultrasonic sensor, Maker Line (`maker-line.md`), micro servo.
- **Servo bracket:** Robo Bracket for Micro Servo Motor (`ROBO-BK-SG90`, `robo-bracket-micro-servo.md`) — "Designed to fit Robo Base and Robo Base Mini" [PP: Robo Bracket page].
- **Gripper:** Robo Grip Mini (`robo-grip-mini.md`) — "mounting holes compatible with the Robo Base Series" [PP: Robo Grip Mini page].
- **Kits that use it:** BEETLE:BIT ships "2x Robo Base (PCB only)" in its accessories kit [PP: BEETLE:BIT page, `beetlebit.md`].

## Common mistakes / troubleshooting
- **Robot won't move** → the kit has no controller, motor driver or battery; add a supported board (e.g. MOTION 2350 Pro, REKA:BIT, Maker UNO + Maker Drive) and a power source [PP].
- **Standoffs too short/long** → Robo Base kits use 30 mm stands; 25 mm stands belong to Robo Base Mini [PP].
- **Mecanum robot drifts or won't strafe** → a wheel is on the wrong side; adjacent mecanum wheels must have opposite roller orientation [PP: tutorial GS-RB].
- **Short circuit on the 12V motor wires** → fit heat-shrink tubing, as the tutorial warns [PP: tutorial GS-RB].
- **Board holes don't line up** → only the listed boards are stated to have compatible holes [PP]; check the tutorial's mounting-position section.
- **Single Base Only arrived without screws** → that option is 1x plate only [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 2WD wheel type | [PP] option name "Double Base 2WD (Rubber Wheels)" | [PP] packing list "2x plastic wheels"; [3P] Switch Science 10708 also lists plastic wheels | Use the packing list wording; tyre material in Needs verification |
| Material named on reseller pages | [PP] "durable PCB material" | [3P] Switch Science 10708/10709 do not name the material | [PP] stands |

## Needs verification
- Weight of the plate.
- **Wheel/tyre material** for the 2WD kit (rubber vs plastic) — see Conflicts.
- **"2x 48mm Mecanum left and right wheel set"** — whether this is 4 wheels in total (4 motors are supplied) is not stated.
- **What "Robo Base Basic Bundle" (RM41.80; RM38.00 on the tutorial card) contains** — the tutorial sub-pages also link "Robo Base Bundle for 2WD Robot" RM62.80 and "Robo Base Bundle for 4WD Robot" RM115.80 [PP: tutorial GS-RB]; match them to the page options.
- **Per-option prices** — only the series range is in text.
- Robo Uno Shield fit — the tutorial names Robo Pico and Robo ESP32 only.
- Reseller codes `CYTRON-CK-ROBO-BASE-2WD` / `CYTRON-CK-ROBO-BASE-4WD` [3P Switch Science] — not Cytron SKUs shown on the product page.

## Sources
- [PP] https://my.cytron.io/p-robo-base-mini-and-kits — Robo Base Series page, read by the coordinator 2026-10-19 (options, packing lists, compatible boards, material text, RM9.00–RM112.00, availability 333, warranty 12 months)
- [PP: tutorial GS-RB] https://my.cytron.io/tutorial/getting-started-with-robo-base — "Getting Started with Robo Base", Sim Jia Hong, 16–19 Jun 2025; sub-pages https://my.cytron.io/tutorial/getting-started-with-rb-<part> for assembly-guide, double-base-2wd-full-assembly, double-base-4wd-full-assembly, dc-motor-and-castors, ultrasonic-sensor, maker-line, micro-servo-motor, 12v-dc-motor, mounting-main-controller-boards, reka-bit, motion-series, uno, robo-series, maker-pi-rp2040, raspberry-pi, jetson-series (all read 2026-10-19)
- [PP: img] https://static.cytron.io/image/catalog/products/PCB-ROBO-BASE/robo-base-dimension.png · robo-base-material.png · robo-base-series-compare.png
- [PP] https://my.cytron.io/p-robo-bracket-for-microservo-motor and https://my.cytron.io/p-robo-grip-mini-kits (fit statements; via `robo-bracket-micro-servo.md`, m-pp.md)
- [3P] https://www.switch-science.com/products/10708 (Robo Base Kit 2WD) and https://www.switch-science.com/products/10709 (Robo Base Kit 4WD) — packing lists match [PP]; dimensions images only
- KB cross-references: `robo-base-mini.md`, `robo-grip-mini.md`, `robo-bracket-micro-servo.md`, `beetlebit.md`, `maker-line.md`
