# Robo Base — Verified Reference

| | |
|---|---|
| Product code | `Robo Base (series page code V-ROBO-BASE-MINI)` [PP] — Robo Base and Robo Base Mini are sold as two "series" choices on one product page; no separate Cytron SKU for Robo Base is shown in text |
| Family | Robot platforms and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |

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
| Thickness | **Not stated in text** (Features table "Material & Thickness" is an image) | [PP] |
| Dimensions | **Not stated in text** (Features table "Dimension" is an image) | [PP] |
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
- Mounting positions covered by the Getting Started tutorial sections [PP: tutorial GS-RB]: TT Motor & Castors; Ultrasonic Sensor; Maker Line; Micro Servo Motor; **⌀37mm 12V DC Motor**; Mounting main controller boards.
- Hole sizes, hole pitch and slot positions are not stated in text (images only) [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **No controller, battery, sensors or servo in any kit** — none appear in the packing lists [PP]. Tutorials must list a controller board, power source and sensors separately.
- **Standoffs are 30 mm (+10 mm)** for Robo Base; 25 mm (+10 mm) for Robo Base Mini [PP]. Don't copy Mini hardware into Robo Base text.
- **4WD kit = mecanum wheels and 4 TT motors**; 2WD kit = 2 TT motors, 2 wheels and a W420 ball castor [PP].
- **⌀37mm 12V DC motor mounting is a Robo Base tutorial section** [PP: tutorial GS-RB]; it is not listed for Robo Base Mini. The 37 mm motor itself is not in any kit [PP].
- **Battery mounting** is a section in the Robo Base Mini tutorial but not in the Robo Base tutorial's section list — don't claim a battery position for Robo Base without checking the tutorial body.
- **"Rubber Wheels" vs "plastic wheels":** the 2WD option name says rubber, its packing list says "2x plastic wheels" [PP]. Write "wheels" or quote the packing list.
- No dimensions in text — do not state a size.
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
- **Board holes don't line up** → only the listed boards are stated to have compatible holes [PP]; check the tutorial's mounting-position section.
- **Single Base Only arrived without screws** → that option is 1x plate only [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 2WD wheel type | [PP] option name "Double Base 2WD (Rubber Wheels)" | [PP] packing list "2x plastic wheels"; [3P] Switch Science 10708 also lists plastic wheels | Use the packing list wording; tyre material in Needs verification |
| Material named on reseller pages | [PP] "durable PCB material" | [3P] Switch Science 10708/10709 do not name the material | [PP] stands |

## Needs verification
- **Dimensions, plate thickness and weight** — images only on the product page; Switch Science also gives drawings only [3P].
- **Hole pattern / slot positions** for each controller board, motor and sensor — tutorial tab content did not render.
- **Wheel/tyre material** for the 2WD kit (rubber vs plastic) — see Conflicts.
- **"2x 48mm Mecanum left and right wheel set"** — whether this is 4 wheels in total (4 motors are supplied) is not stated.
- **What "Robo Base Basic Bundle" (RM41.80) contains** and which page option it matches.
- **Per-option prices** — only the series range is in text.
- **Which "Robo series" boards** fit (Robo Pico is listed; Robo ESP32 / Robo Uno Shield not stated).
- Reseller codes `CYTRON-CK-ROBO-BASE-2WD` / `CYTRON-CK-ROBO-BASE-4WD` [3P Switch Science] — not Cytron SKUs shown on the product page.
- Plate thickness "1.6 mm non-copper PCB" appears only on The Pi Hut's Robo Base **Mini** page [3P]; not confirmed for Robo Base.

## Sources
- [PP] https://my.cytron.io/p-robo-base-mini-and-kits — Robo Base Series page, read by the coordinator 2026-10-19 (options, packing lists, compatible boards, material text, RM9.00–RM112.00, availability 333, warranty 12 months)
- [PP: tutorial GS-RB] https://my.cytron.io/tutorial/getting-started-with-robo-base — "Getting Started with Robo Base", Sim Jia Hong, 16 Jun 2025 (section list only)
- [PP] https://my.cytron.io/p-robo-bracket-for-microservo-motor and https://my.cytron.io/p-robo-grip-mini-kits (fit statements; via `robo-bracket-micro-servo.md`, m-pp.md)
- [3P] https://www.switch-science.com/products/10708 (Robo Base Kit 2WD) and https://www.switch-science.com/products/10709 (Robo Base Kit 4WD) — packing lists match [PP]; dimensions images only
- KB cross-references: `robo-base-mini.md`, `robo-grip-mini.md`, `robo-bracket-micro-servo.md`, `beetlebit.md`, `maker-line.md`
