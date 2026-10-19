# Robo Base Mini — Verified Reference

| | |
|---|---|
| Product code | `Robo Base Mini (series page code V-ROBO-BASE-MINI)` [PP] — Robo Base Mini and Robo Base are sold as two "series" choices on one product page; no separate Cytron SKU for Robo Base Mini is shown in text |
| Family | Robot platforms and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: all 16 parts of the "Getting Started with Robo Base Mini" tutorial series read (Hao Zhen Goh, 26 Feb – 5 Mar 2025): assembly order, standoff use, Maker Line on 10 mm standoffs, servo fixing without dedicated holes, battery positions, per-board mounting (M3 vs M2.5 for Pi/Jetson). Hardware part — guide tutorial is the main source (KB rule 7); no datasheet required |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
- The smaller plate of Cytron's Robo Base series: a PCB chassis for small mobile robot cars, or an adapter plate to mount a Cytron controller board on another chassis [PP].
- Made of "durable PCB material" — "cost-friendly alternative to metal chassis and tougher than fragile acrylic plates" [PP]. Cytron's STRIKER:BIT page calls its Robobase Mini chassis "non-copper PCB" [PP: STRIKER:BIT page, see `strikerbit.md`].
- Pre-made mounting holes for Cytron controller boards; sensors, ball castors, DC motors or servo motors attach with standard screws, nuts and standoffs [PP].
- Sold as Single Base Only or in "Double Base" kits (two plates on standoffs) with 2WD, 4WD (mecanum) or accessories-only contents [PP].
- Warranty 12 months [PP].

## Specifications
No datasheet spec table exists. Facts stated in text:

| Item | Value | Src |
|---|---|---|
| Material | PCB ("durable PCB material"); "non-copper PCB" on the STRIKER:BIT page | [PP] |
| Thickness | 1.6 mm (Cytron Robo Base Series comparison image) | [PP: img] |
| Dimensions | 109 × 88 × 1.6 mm (comparison image) | [PP: img] |
| Use / labels / servo holes | "Robot Base, Adapter Board"; "No Label"; no servo mounting holes (comparison image) | [PP: img] |
| Weight | Not stated | — |
| Fixings used | Standard screws, nuts and standoffs; kit hardware is M3 | [PP] |
| Kit options | Double Base 4WD (Mecanum Wheels) / Double Base 2WD (Rubber Wheels) / Double Base with Accessories / Single Base Only | [PP] |
| Standoffs in Double Base kits | 4x M3 PCB stand (screw+nut) **25 mm** + 4x M3 PCB stand 10 mm (Robo Base uses 30 mm) | [PP] |
| Warranty | 12 months | [PP] |
| Price (series page) | RM9.00–RM112.00 across both Robo Base and Robo Base Mini options; per-option prices not stated | [PP] |
| Tutorial product card | "Robo Base Mini Basic Bundle" RM19.80 (contents not stated) | [PP: tutorial GS-RBM] |

### Packing lists [PP]
| Option | Contents |
|---|---|
| Double Base 4WD (Mecanum Wheels) | 2x Robo Base Mini, 4x M3 PCB stand (screw+nut) 25mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 4x TT motor 15cm wire, 2x 48mm Mecanum left and right wheel set, 2x TT DC gear motor bracket |
| Double Base 2WD (Rubber Wheels) | 2x Robo Base Mini, 4x M3 PCB stand 25mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 2x TT motor 15cm wire, 2x plastic wheels, 2x TT motor bracket, 1x W420 ball castor |
| Double Base with Accessories | 2x Robo Base Mini, 4x M3 PCB stand 25mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench |
| Single Base Only | 1x Robo Base Mini |

## Interfaces, terminals and pin mapping
- Mechanical part only; no electrical connections [PP].
- Positions covered by the Getting Started tutorial [PP: tutorial GS-RBM]: Double Base 2WD and 4WD assembly; DC Motor & Castors; Maker Line; Ultrasonic; Micro Servo; **Battery**; Mounting main controller boards & sample codes.
- **Recommended assembly order:** Motor > Castor > Sensor > Servo > Battery > Boards [PP: tutorial GS-RBM].
- **Double layer:** the two plates are joined with the 25 mm M3 standoffs [PP: tutorial GS-RBM].
- **Maker Line:** mounted under the plate on 2 × 10 mm standoffs [PP: tutorial GS-RBM].
- **Micro servo:** the Mini has no dedicated servo holes; the servo is fixed with an M2 screw from the servo's own accessory pack (or use the Robo Bracket for Micro Servo) [PP: tutorial GS-RBM][PP: img].
- **Battery:** either between the two plates, or a 4 × AA holder underneath when the TT motors are mounted on top [PP: tutorial GS-RBM]. No battery or holder is supplied [PP].
- **Controller boards:** REKA:BIT, MOTION:BIT and Robo Pico on M3 10 mm standoffs; Raspberry Pi and Jetson use **M2.5** fixings; on Jetson one standoff is fitted from the nut side and tightened with 3 nuts; Maker UNO is bolted flat, with a shield on top or Maker Drive beside it on standoffs [PP: tutorial GS-RBM].
- Hole sizes, pitch and slot positions are not stated in text (images only) [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **Standoffs are 25 mm (+10 mm)** — not the 30 mm used by Robo Base [PP].
- **No controller, battery, sensors or servo in any kit** [PP packing lists]. The tutorial's Battery section shows positions only; no battery is supplied.
- **Follow the build order** Motor > Castor > Sensor > Servo > Battery > Boards — boards last, or the lower fixings become unreachable [PP: tutorial GS-RBM].
- **Pi and Jetson need M2.5 standoffs/screws, not the kit's M3** [PP: tutorial GS-RBM]; M2.5 hardware is not in any Mini kit [PP].
- **No servo holes on the Mini** — use the servo's own M2 screw, or the Robo Bracket for Micro Servo [PP: tutorial GS-RBM].
- **⌀37mm 12V DC motor** is a Robo Base tutorial section, not a Robo Base Mini one — don't claim it for the Mini.
- **4WD = 4 TT motors + mecanum wheels; 2WD = 2 TT motors + 2 wheels + W420 castor** [PP].
- **"Rubber Wheels" vs "plastic wheels":** option name vs packing list on the same page [PP] — quote the packing list.
- Single Base Only = plate only, no hardware [PP].
- Size 109 × 88 × 1.6 mm [PP: img] (Robo Base is 154 × 124 × 2 mm). Do not say "half the size of Robo Base".

## Power and electrical limits
- None (mechanical part). Motor, servo and battery limits belong to the controller board's KB file (e.g. `motion-bit.md`, `reka-bit.md`, `maker-drive.md`, `robo-pico.md`).

## Software support
- None needed for the chassis. The tutorial's board-mounting part links sample codes for the mounted boards [PP: tutorial GS-RBM]; code belongs to each board's KB file.
- Cytron projects on Robo Base Mini : "Robo Base Mini Line Following Robot with Maker UNO and Maker Drive" (Khye Yen Ang, 19 Sep 2025); "Robo Base Mini Obstacle Avoidance Robot with Maker UNO and Maker Drive" (12 Sep 2025); "Line Following Robo Base Mini" (ESP32 + Cytron motor driver + Maker Line, Azfar Rosdi, 11 Jul 2025) [PP]. Bodies not read.

## Compatibility and accessories
- **Controller boards with matching mounting holes** (series page list, which the Mini tutorial repeats) [PP][PP: tutorial GS-RBM]: REKA:BIT, MOTION:BIT, MOTION:BIT Pro, MOTION 2350 Pro, Robo Pico, Maker Pi RP2040, Maker UNO or Arduino UNO form factor, Maker UNO + Maker Drive, Raspberry Pi 4 or 5, Jetson series; the tutorial also names "Robo series".
- **Attachments** [PP][PP: tutorial GS-RBM]: TT DC gear motors (TT motor bracket), ball castor (W420 in 2WD kit), Maker Line (`maker-line.md`), ultrasonic sensor, micro servo, battery.
- **Servo bracket:** Robo Bracket for Micro Servo Motor (`ROBO-BK-SG90`, `robo-bracket-micro-servo.md`) — "Designed to fit Robo Base and Robo Base Mini" [PP].
- **Gripper:** Robo Grip Mini (`robo-grip-mini.md`) — mounting holes "compatible with the Robo Base Series" [PP].
- **Kits that use it:** STRIKER:BIT ships "Robobase Mini kit for 2WD Robot" per robot [PP: STRIKER:BIT page, `strikerbit.md`].

## Common mistakes / troubleshooting
- **Robot won't move** → no controller, motor driver or battery is included; add a supported board and power source [PP].
- **Standoffs don't match a Robo Base build** → Mini kits use 25 mm stands; Robo Base kits 30 mm [PP].
- **Board holes don't line up** → only the listed boards are stated to fit [PP]; Pi/Jetson need M2.5 fixings, others M3 10 mm standoffs [PP: tutorial GS-RBM].
- **Battery won't fit between plates with TT motors on top** → use a 4 × AA holder underneath instead [PP: tutorial GS-RBM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 2WD wheel type | [PP] option name "Double Base 2WD (Rubber Wheels)" | [PP] packing list "2x plastic wheels"; [3P] Switch Science 10530 also "plastic wheel" | Use the packing-list wording; tyre material in Needs verification |
| TT motor brackets in 4WD kit | [PP] 2x TT DC gear motor bracket | [3P] Switch Science 10531 (4WD Mini) lists 4x TT DC gear motor bracket | [PP] wins (2x); count goes to Needs verification |
| Plate thickness | [PP: img] 1.6 mm | [3P] The Pi Hut: "1.6 mm non-copper PCB" | Consistent; Cytron image confirms 1.6 mm |

## Needs verification
- **Weight** — not stated.
- **TT motor bracket count in the 4WD kit** (2 per Cytron page vs 4 per Switch Science) — see Conflicts.
- **"2x 48mm Mecanum left and right wheel set"** — whether this means 4 wheels in total.
- **Wheel/tyre material** for 2WD (rubber vs plastic).
- **What "Robo Base Mini Basic Bundle" (RM19.80) contains**; per-option prices.
- Hole diameters and pitch (drawings only, no dimensioned hole map).
- Reseller codes `CYTRON-CK-ROBO-BASE-MINI-2WD` / `-4WD` [3P Switch Science].

## Sources
- [PP] https://my.cytron.io/p-robo-base-mini-and-kits — Robo Base Series page, read by the coordinator 2026-10-19 (options, Mini packing lists with 25 mm stands, compatible boards, RM9.00–RM112.00, availability 333, warranty 12 months)
- [PP: tutorial GS-RBM] https://my.cytron.io/tutorial/getting-started-with-robo-base-mini — "Getting Started with Robo Base Mini", Hao Zhen Goh, 05 Mar 2025, and its 16 linked parts (26 Feb – 3 Mar 2025), all read 2026-10-19
- [PP] https://my.cytron.io/p-robo-bracket-for-microservo-motor and https://my.cytron.io/p-robo-grip-mini-kits (fit statements)
- [3P] https://www.switch-science.com/products/10530 (Mini 2WD), https://www.switch-science.com/products/10531 (Mini 4WD), https://thepihut.com/products/robo-base-mini
- Drive (marketing only, no specs): "Website Banner Robo Base Mini .png" (Cytron document — link not public) ; "IV ROBO BASE MINI LATEST VERSION.mp4" (Cytron document — link not public)
- KB cross-references: `robo-base.md`, `robo-grip-mini.md`, `robo-bracket-micro-servo.md`, `strikerbit.md`, `maker-line.md`
