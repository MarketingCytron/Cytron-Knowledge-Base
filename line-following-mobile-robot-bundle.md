# Line Following Mobile Robot Bundle — Verified Reference

| | |
|---|---|
| Product code | `KIT-RBT-LF` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron OEM product page read in full (notes, description, features, specifications, packing list, resources), its wiring diagram `Kit-RBT-LF Schematic.jpg` and packing photo viewed, and the linked Cytron tutorial "Robo Base Mini Line Following Robot with Maker UNO and Maker Drive" (Khye Yen Ang, 19 Sep 2025) read in full including its sample sketch |
| Primary source | No datasheet or manual exists for the kit. Primary sources = the Cytron tutorial **"Robo Base Mini Line Following Robot with Maker UNO and Maker Drive"** (Khye Yen Ang, 19 Sep 2025, Tutorial, Beginner) https://my.cytron.io/tutorial/robo-base-mini-line-following-robot-with-maker-uno-and-maker-drive — read in full 2026-10-21 [PP: tutorial] — and the **Cytron product page** https://my.cytron.io/cytron-oem/p-line-following-mobile-robot-kit, read 2026-10-21 [PP]. The boards follow their own KB files (`maker-uno.md`, `maker-drive.md`) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text, read in the browser 2026-10-21. [PP: img] = the page's wiring diagram (`Kit-RBT-LF Schematic.jpg`, 2048 × 926 Fritzing picture) and packing photo (`kit-rbt-lf-pack.png`). [PP: tutorial] = the assembly tutorial above (text, wiring tables and the embedded sketch; gist `interns24-bit/0a760fdb7abdf7446c47fd476057a20b`, file `Robo_Base_Mini_Line_Following_Robot.ino`). KIT RULE: Maker UNO, Maker Drive and Robo Base Mini have their own KB files and are cross-linked, not re-documented. The IR Line Tracking Module, TT motors, TT motor brackets, castor and breadboard have no KB file. The page video (YouTube `X6qFEwy2X2w`, the same video as the obstacle-avoidance bundle) was not watched.

## What it is
- A no-solder **Arduino line-following robot kit** on a two-layer **Robo Base Mini** PCB chassis, controlled by **Maker UNO** with a **Maker Drive** motor driver, two **IR Line Tracking Modules**, two TT motors with wheels, and a 4 × AA battery pack that powers both the controller and the motors [PP].
- "The kit comes in loose parts, so you will need to assemble it, but there is no soldering needed" [PP]; Cytron provides assembly steps and a sample Arduino sketch [PP][PP: tutorial].
- Page notes: SST applies from April 2026; "Check out the Pikabot that uses Maker UNO and comes with similar functions as this mobile robot kit" (`pikabot.md`) [PP].
- Warranty 12 months [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Controller | Maker UNO (Arduino UNO compatible) | [PP] |
| Motor driver | Maker Drive dual-channel DC brush motor driver | [PP] |
| Chassis | Robo Base Mini (2 plates, "custom designed PCB base") | [PP] |
| Chassis size | 109 mm × 88 mm | [PP] |
| Line sensors | 2 × IR Line Tracking Module | [PP] |
| Drive | 2 × "TT" motor with wheel, differential drive; 1 × steel ball castor | [PP] |
| Wheel diameter | 67 mm | [PP] |
| Castor height | 34 mm | [PP] |
| TT motor gear ratio | 48:1 | [PP] |
| TT motor speed | 0.65 m/s with 66 mm wheel at 7.2 VDC | [PP] |
| TT motor recommended voltage | 5–10 VDC | [PP] |
| TT motor noise | < 65 dB | [PP] |
| TT motor current | 120 mA each motor (running at 6 V) | [PP] |
| Power | 4 × AA battery (included) in a 4 × AA holder; powers controller and motors | [PP] |
| Weight | Not stated | — |
| Price | RM120.75 special offer (RM141.75, −15%) | [PP] |
| Stock (2026-10-21) | 43 | [PP] |
| Warranty | 12 months | [PP] |

### Packing list (product page, as stated) [PP]
| Qty | Item |
|---|---|
| 2 | Robo Base Mini |
| 1 | Maker UNO (Simplifying Arduino for Education) |
| 1 | Maker Drive: Dual H-Bridge Motor Driver for Beginner |
| 2 | IR Line Tracking Module |
| 2 | TT Motor with 15cm Wires and Wheel Set |
| 2 | TT Motor Bracket |
| 1 | N20 Steel Ball Universal Wheel (Castor) |
| 1 | 40 ways Male to Female Jumper Wire |
| 1 | 40-Way Male to Male Jumper Wire |
| 4 | 10mm PCB stand |
| 6 | 20mm PCB stand |
| 26 | M3x6mm bolt |
| 6 | M3 Nut |
| 1 | PKCELL Heavy Duty AA Battery (4pcs) |
| 1 | 4xAA battery holder |
| 1 | USB Micro B cable |
| 1 | 85mmx3mm Tiny Phillips Screwdriver - Transparent |
| 1 | Mini Cross Sleeve Cross Wrench Socket |

The tutorial's "What is Included in the Kit?" list differs: **4 × M3 15mm PCB stand** (not 10 mm) and an extra **1 × Breadboard Mini - 170 holes (35mm x 47mm)**; the packing photo also shows a mini breadboard [PP: tutorial][PP: img]. See *Conflicts*.

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Line Following Mobile Robot Bundle"; Brand Cytron OEM; code KIT-RBT-LF; 41 ratings; special offer RM120.75 (RM141.75, −15%); cashback RM3.45; availability 43 [PP].
- Resources: "Tutorial guide to building this mobile robot" (the 2025 tutorial), "Arduino IDE Download", "Maker UNO product page" [PP].
- Related tutorial: "Robo Base Mini Line Following Robot with Maker UNO and Ma…" (Khye Yen Ang, 19 Sep 2025) [PP].
- "You May Also Need" includes the Cytron Reconfigurable Line Following Track, the Obstacle Avoidance Mobile Robot Bundle and Maker Line [PP].

## Interfaces, terminals and pin mapping
Wiring as stated in the tutorial [PP: tutorial]:

| Maker Drive | Maker UNO |
|---|---|
| M1A | Pin 11 |
| M1B | Pin 10 |
| 5V | 5V |
| GND | GND |
| M2A | Pin 6 |
| M2B | Pin 5 |

| IR Line Tracking Module | Maker UNO |
|---|---|
| Left: Digital Output (DO) | Pin A1 |
| Right: Digital Output (DO) | Pin A2 |
| VCC | 3.3V |
| GND | GND |

| TT motors / battery holder | Maker Drive |
|---|---|
| Left TT motor: black | M1A |
| Left TT motor: red | M1B |
| Right TT motor: red | M2A |
| Right TT motor: black | M2B |
| Battery holder + (red) | VB+ |
| Battery holder − (black) | VB− |

- The jumper wires go to the IR modules' VCC, GND and DO pins "through the holes on the Robo Base Mini" [PP: tutorial].
- The Maker UNO is powered from the Maker Drive's 5 V output (Maker Drive 5V → Maker UNO 5V) [PP: tutorial]; Maker Drive 5 V output is 200 mA max (`maker-drive.md` [DS]).
- On-board Maker UNO parts used by the sketch: button on pin 2 (start), piezo on pin 8 (melody) [PP: tutorial]; see `maker-uno.md`.
- The page's wiring diagram is a Fritzing picture with a mini breadboard and a battery holder labelled "AAA Battery"; pin numbers are not legible at the size read [PP: img].

## Rules and gotchas (for code, wiring and tutorials)
- **Assembly order (tutorial)** [PP: tutorial]: (1) unpack; (2) TT brackets on the motors — screw heads facing away from the motor wires, the two brackets mounted in opposite directions; (3) lower base: motors with brackets, **wires facing inward**; (4) battery holder with M3 bolts and nuts; (5) 2 × M3 20 mm standoffs, ball castor on them; (6) 2 × M3 15 mm standoffs, IR modules on them; (7) wheels onto the motors; (8) jumper wires on the IR modules' VCC/GND/DO through the base holes; (9) 4 × M3 20 mm standoffs for the upper base; (10) upper base: Maker UNO with M3 bolts and nuts; (11) 2 × M3 15 mm standoffs, Maker Drive on them; (12) peel and stick the breadboard; (13) join the bases with 4 M3 bolts; (14) wire per the tables.
- **Motor direction test before coding** [PP: tutorial]: insert the 4 AA batteries (Maker Drive PWR LED on), then press the Maker Drive test buttons — M1A left wheel forward, M1B left backward, M2A right forward, M2B right backward; swap that motor's wires if wrong.
- **Software setup** [PP: tutorial]: Arduino IDE, board "Arduino Uno", install the **Cytron Motor Drivers Library** (`CytronMotorDriver.h`); the sketch drives Maker Drive in PWM_PWM mode — motor 1 on pins 11/10, motor 2 on pins 6/5, speed 150 — and starts when the Maker UNO button is pressed.
- **Sample sketch reads a third sensor the kit does not have:** it defines `IR_CENTRE` on **A3** and uses a 3-bit left/centre/right state; "forward" needs the centre sensor alone to be active. The kit has only two sensors (A1, A2), so A3 is unconnected and floating (inferred from the code). The code comments also say "wall" (copied from a maze sketch). Expect to edit the logic for two sensors.
- **Text vs code:** the tutorial says "If both sensors detect black, it will stop", but the sketch turns left in the left+right and all-sensors states; only the default case stops [PP: tutorial]. Describe what the code does, not the sentence.
- **IR module power:** the tutorial powers the IR modules from **3.3 V** [PP: tutorial]; the module's own voltage range and output polarity (high or low on black) are not stated.
- **Line rule:** the robot follows a black line on a white surface [PP: tutorial].
- **Breadboard and standoffs:** follow the tutorial's parts (15 mm standoffs, mini breadboard) — see *Conflicts*.

## Power and electrical limits
- 4 × AA batteries power both the motors (Maker Drive VB+/VB−) and the Maker UNO (via the Maker Drive 5 V output) [PP][PP: tutorial]. Maker Drive accepts 2.5–9.5 V, 1.0 A continuous per channel, 5 V out 200 mA (`maker-drive.md` [DS]).
- TT motors: recommended 5–10 VDC; 120 mA each at 6 V [PP].
- Maker UNO has no DC jack or Vin pin (`maker-uno.md`); it runs from USB when programming. Whether USB and the battery may be connected at the same time is not stated.

## Software support
- Arduino IDE; Cytron Motor Drivers Library; sample sketch `Robo_Base_Mini_Line_Following_Robot.ino` (GitHub gist by interns24-bit, embedded in the tutorial) [PP: tutorial]. Tutorial code is not copied here.
- The tutorial references two older Cytron tutorials, "Line Following Robot Using Arduino and Maker Drive" and "DC Motor & Castors" (not read).

## Compatibility and accessories
- Components with KB files (not re-documented): **Maker UNO** → `maker-uno.md`; **Maker Drive** → `maker-drive.md`; **Robo Base Mini** (2 plates, 109 × 88 mm) → `robo-base-mini.md`.
- Similar kit: **PikaBot** (Maker UNO smart car) → `pikabot.md` [PP note].
- Sister kit: **Obstacle Avoidance Mobile Robot Bundle** → `obstacle-avoidance-mobile-robot-bundle.md` (same chassis, controller, driver and motors; ultrasonic sensor instead of IR modules).
- Cross-sell on the page: Cytron Reconfigurable Line Following Track → `line-following-track.md`; Maker Line → `maker-line.md` (not included; a different line sensor) [PP].
- No KB file: IR Line Tracking Module, TT motor and wheel set, TT motor bracket, N20 steel ball castor, mini breadboard.

## Common mistakes / troubleshooting
- **A wheel turns the wrong way** → swap that motor's two wires on the Maker Drive; check with the test buttons [PP: tutorial].
- **Robot never drives straight forward with the sample sketch** → the sketch expects a centre sensor on A3, which the kit lacks; rewrite the forward condition for two sensors (inferred from the code).
- **Short standoffs too short / breadboard missing from the list** → the tutorial uses 15 mm standoffs and a mini breadboard; check the bag against the tutorial list [PP: tutorial].
- **Maker UNO resets when motors start** → AA voltage sags under load and the board runs from the Maker Drive 5 V (200 mA max) output; use fresh batteries (inferred; not stated by Cytron).
- **Sensors don't react** → they are wired to A1/A2 and powered from 3.3 V in the tutorial; check each module's DO, VCC, GND [PP: tutorial].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Short standoffs | [PP] packing list "4 x 10mm PCB stand" | [PP: tutorial] kit list and steps "4 x M3 15mm PCB stand" | Unresolved; the tutorial (newer, step-by-step) uses 15 mm for the IR modules and Maker Drive |
| Breadboard | [PP] packing list: none | [PP: tutorial] "1 x Breadboard Mini - 170 holes (35mmx47mm)"; [PP: img] packing photo and wiring diagram show a mini breadboard | Breadboard appears to be included; page packing list omits it |
| Battery size | [PP] packing list "PKCELL Heavy Duty AA Battery (4pcs)", "4xAA battery holder" | [PP: img] wiring diagram labels the holder "AAA Battery" | AA (packing list and photo); the diagram label is a drawing error |
| Wheel diameter | [PP] "Wheel Diameter: 67mm" | [PP] "Speed with 66mm diameter wheel" | Page-internal; 67 mm is the wheel spec, 66 mm is the motor-speed test condition |
| Stop condition | [PP: tutorial] text: stops when both sensors see black | [PP: tutorial] sketch: turns left in those states | Follow the code; flag in tutorials |

## Needs verification
- **IR Line Tracking Module** part number, voltage range and output polarity.
- **TT motor** stall current and wheel width.
- Whether 10 mm or 15 mm standoffs ship today; whether the breadboard ships today.
- Whether USB and battery power may be connected at once.
- Kit weight.
- Contents of the page video (YouTube `X6qFEwy2X2w`).

## Cytron tutorials
Add-on: Cytron tutorials that use this product. They never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Robo Base Mini Line Following Robot with Maker UNO and Maker Drive](https://my.cytron.io/tutorial/robo-base-mini-line-following-robot-with-maker-uno-and-maker-drive) — Tutorial, Beginner, 2025

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-line-following-mobile-robot-kit — read 2026-10-21 (KIT-RBT-LF; RM120.75 offer, RM141.75 normal; availability 43; warranty 12 months; description; features; specifications; packing list; resources; related tutorial)
- [PP: img] https://www.cytron.io/image/catalog/products/KIT-RBT-LF/Kit-RBT-LF%20Schematic.jpg (wiring diagram) and https://static.cytron.io/image/catalog/products/KIT-RBT-LF/kit-rbt-lf-pack.png (packing photo) — viewed 2026-10-21
- [PP: tutorial] "Robo Base Mini Line Following Robot with Maker UNO and Maker Drive", Khye Yen Ang, 19 Sep 2025 — https://my.cytron.io/tutorial/robo-base-mini-line-following-robot-with-maker-uno-and-maker-drive — read in full 2026-10-21; sketch https://gist.github.com/interns24-bit/0a760fdb7abdf7446c47fd476057a20b
- KB cross-references: `maker-uno.md`, `maker-drive.md`, `robo-base-mini.md`, `pikabot.md`, `obstacle-avoidance-mobile-robot-bundle.md`, `line-following-track.md`, `maker-line.md`
