# Obstacle Avoidance Mobile Robot Bundle — Verified Reference

| | |
|---|---|
| Product code | `KIT-RBT-OA` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron OEM product page read in full (notes, description, features, specifications, packing list, resources), its wiring diagram and packing photo viewed, both linked Cytron tutorials read ("Robo Base Mini Obstacle Avoidance Robot with Maker UNO and Maker Drive", Khye Yen Ang, 12 Sep 2025, incl. its sketch; "Obstacle Avoiding Robot", suadanwar, 24 Jan 2019), and the page's "Sample code" gist read |
| Primary source | No datasheet or manual exists for the kit. Primary sources = the Cytron tutorial **"Robo Base Mini Obstacle Avoidance Robot with Maker UNO and Maker Drive"** (Khye Yen Ang, 12 Sep 2025, Tutorial, Beginner) https://my.cytron.io/tutorial/robo-base-mini-obstacle-avoidance-robot-with-maker-uno-and-maker-drive — read in full 2026-10-21 [PP: tutorial] — and the **Cytron product page** https://my.cytron.io/cytron-oem/p-obstacle-avoidance-mobile-robot-kit, read 2026-10-21 [PP]. The boards follow their own KB files (`maker-uno.md`, `maker-drive.md`) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text, read in the browser 2026-10-21. [PP: img] = the page's wiring diagram (`Kit-RBT-OA Sch.jpg`, 666 × 350 Fritzing picture) and packing photo (`kit-rbt-oa-pack.png`). [PP: tutorial] = the 2025 assembly tutorial above (sketch in gist `interns24-bit/a5906d33b629c7a83ccbe2b7de7daaa0`). [PP: tutorial 2019] = "Obstacle Avoiding Robot" (suadanwar, 24 Jan 2019, Intermediate) — an older build of this kit using an **L298ND** driver, kept only as history. [PP: sample code] = the page's "Sample code" link, gist `suadanwar/de0a5c33ec351e02e0c5b389b5bfafd1` (`ObstaclesAvoidingRobot_MakerDrive.ino`, 20 Mar 2019). KIT RULE: Maker UNO, Maker Drive and Robo Base Mini have their own KB files and are cross-linked, not re-documented. The SR04P ultrasonic module, TT motors, brackets and castor have no KB file. The CH34X driver files on Google Drive were not opened (installers). The page video (YouTube `X6qFEwy2X2w`) was not watched.

## What it is
- A no-solder **Arduino obstacle-avoiding robot kit** on a two-layer **Robo Base Mini** PCB chassis, controlled by **Maker UNO** with a **Maker Drive** motor driver, one **ultrasonic sensor** on a bracket, two TT motors with wheels, a castor, and a 4 × AA battery pack that powers both the controller and the motors [PP].
- "The kit comes in loose parts, so you will need to assemble it, but no soldering is needed"; Cytron provides a "Full Tutorial Guide" and "Sample code for obstacle avoidance using Ultrasonic Sensor" [PP].
- Page notes: SST applies from April 2026; "Check out the Pikabot that uses Maker UNO and comes with similar functions as this mobile robot kit" (`pikabot.md`) [PP].
- Warranty 12 months [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Controller | Maker UNO (Arduino UNO compatible) | [PP] |
| Motor driver | Maker Drive dual-channel DC brush motor driver | [PP] |
| Chassis | Robo Base Mini (2 plates, "custom-designed PCB base") | [PP] |
| Chassis size | 109 mm × 88 mm | [PP] |
| Obstacle sensor | 1 × SR04P Ultrasonic Ranging Module (product link "3V-5.5V ultrasonic ranging module") on a Bracket for Ultrasonic HC-SR04 | [PP] |
| Drive | 2 × "TT" motor with wheel, differential drive; 1 × W420 steel ball castor | [PP] |
| Wheel diameter | 67 mm | [PP] |
| Castor height | 34 mm | [PP] |
| TT motor gear ratio | 48:1 | [PP] |
| TT motor speed | 0.65 m/s with 66 mm wheel at 7.2 VDC | [PP] |
| TT motor recommended voltage | 5–10 VDC | [PP] |
| TT motor noise | < 65 dB | [PP] |
| TT motor current | 120 mA for each motor (running at 6 V) | [PP] |
| Power | 4 × AA battery (included) in a 4 × AA holder; powers controller and motors | [PP] |
| Weight | Not stated | — |
| Price | RM114.45 special offer (RM131.25, −13%); 30 or more RM105.00 | [PP] |
| Stock (2026-10-21) | 35 | [PP] |
| Warranty | 12 months | [PP] |

### Packing list (product page, as stated) [PP]
| Qty | Item |
|---|---|
| 2 | Robo Base Mini |
| 1 | Maker UNO (Simplifying Arduino for Education) |
| 1 | Maker Drive: Dual H-Bridge Motor Driver for Beginner |
| 1 | SR04P Ultrasonic Ranging Module |
| 1 | Bracket for Ultrasonic HC-SR04 |
| 2 | TT Motor with 15cm Wires and Wheel Set |
| 2 | TT Motor Bracket |
| 1 | W420 Steel Ball Universal Wheel (Castor) |
| 1 | 40 ways Male to Female Jumper Wire |
| 4 | 10mm PCB stand |
| 2 | 30mm PCB stand |
| 22 | M3x6mm bolt |
| 10 | M3 Nut |
| 1 | PKCELL Heavy Duty AA Battery (4pcs) |
| 1 | 4xAA battery holder |
| 1 | USB Micro B cable |
| 1 | 85mmx3mm Tiny Phillips Screwdriver - Transparent |
| 1 | Mini Cross Sleeve Cross Wrench Socket |

The 2025 tutorial's kit list repeats this list but also shows "2 x Ultrasonic Sensor" and a second "1 x 4xAA battery holder" (apparent copy errors), and its steps use **4 × M3 30 mm** and **2 × M3 15 mm** standoffs [PP: tutorial]. See *Conflicts*.

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Obstacle Avoidance Mobile Robot Bundle"; Brand Cytron OEM; code KIT-RBT-OA; 21 ratings; special offer RM114.45 (RM131.25, −13%); cashback RM3.27; 30 or more RM105.00; availability 35 [PP].
- Features list includes "Acrylic mobile robot base with much more space for prototyping" (see *Conflicts*) [PP].
- Resources: Tutorial Guide (2025 tutorial); "Sample code - Arduino" (2019 gist); CH34X driver for Windows (V3.5 Mar2019), Mac OS (V1.5 Mar2019), Linux (V1.5 Mar2019, "Normally is readily installed") on Google Drive, plus "Get the latest driver from the factory" (wch.cn) — "Please ensure the Maker UNO is plugged into the computer USB port during driver installation"; Arduino IDE download; Maker UNO product page [PP].
- Related tutorials: "Robo Base Mini Obstacle Avoidance Robot with Maker UNO an…" (Khye Yen Ang, 12 Sep 2025) and "Obstacle Avoiding Robot" (suadanwar, 24 Jan 2019) [PP].

## Interfaces, terminals and pin mapping
Wiring as stated in the 2025 tutorial [PP: tutorial]:

| Maker Drive | Maker UNO |
|---|---|
| M1A | Pin 11 |
| M1B | Pin 10 |
| 5V | 5V |
| GND | GND |
| M2A | Pin 6 |
| M2B | Pin 5 |

| Ultrasonic sensor | Maker UNO |
|---|---|
| TRIG | Pin 3 |
| ECHO | Pin 4 |
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

- The Maker UNO is powered from the Maker Drive 5 V output [PP: tutorial]; that output is 200 mA max (`maker-drive.md` [DS]).
- On-board Maker UNO parts used by the sketch: button on pin 2 (start/stop), piezo on pin 8 [PP: tutorial]; see `maker-uno.md`.
- **The page's "Sample code" uses different pins** — Maker Drive on pins 3/9 and 10/11, TRIG on pin 5, ECHO on pin 4 [PP: sample code] — so it does not match the 2025 wiring above. See *Rules and gotchas*.
- The page's wiring diagram is a small Fritzing picture showing an HC-SR04 on a mini breadboard and an AA holder; pin numbers are not legible [PP: img].

## Rules and gotchas (for code, wiring and tutorials)
- **Match code to wiring:** use the 2025 tutorial's wiring **and** its sketch together (Maker Drive 11/10 and 6/5, TRIG 3, ECHO 4). The page's 2019 "Sample code" expects Maker Drive on 3/9 and 10/11 and TRIG on 5; mixing them makes the motors and sensor misbehave [PP: tutorial][PP: sample code].
- **Ignore the 2019 L298ND pin table** for this kit: the 2019 tutorial wires an L298ND driver (ENA 5, ENB 6, IN1 7, IN2 9, IN3 10, IN4 11; Trig 3, Echo 4) — not the Maker Drive that ships now [PP: tutorial 2019].
- **Assembly order (2025 tutorial)** [PP: tutorial]: (1) unpack; (2) TT brackets on the motors — screw heads facing away from the motor wires, brackets in opposite directions; (3) lower base: motors, **wires facing inward**; (4) ball castor with M3 bolts and nuts; (5) battery holder with M3 bolts and nuts; (6) wheels on; (7) 4 × M3 30 mm standoffs for the upper base; (8) upper base: Maker UNO with M3 bolts and nuts; (9) 2 × M3 15 mm standoffs, Maker Drive on them; (10) ultrasonic bracket with M3 bolts and nuts; (11) sensor into the bracket, **pins facing upwards**; (12) join the bases with 4 M3 bolts; (13) wire per the tables.
- **Motor direction test before coding** [PP: tutorial]: batteries in (Maker Drive PWR LED on), press the test buttons — M1A left wheel forward, M1B left backward, M2A right forward, M2B right backward; swap that motor's wires if wrong.
- **Software setup** [PP: tutorial]: Arduino IDE, board "Arduino Uno", Cytron Motor Drivers Library (`CytronMotorDriver.h`), PWM_PWM mode. Behaviour of the 2025 sketch: press the button to start (press again to stop); reads distance every 100 ms; if an obstacle is under **10 cm** it stops, reverses for 300 ms, turns right for 500 ms, then continues; speed 200; no echo within 20 ms counts as "no obstacle" [PP: tutorial].
- **Sensor supply:** the tutorial powers the sensor from **3.3 V** [PP: tutorial]; the supplied SR04P is listed as a 3 V–5.5 V module [PP]. A classic 5 V-only HC-SR04 substitute would need 5 V (general practice; inferred).
- **CH34X USB driver:** install it with the Maker UNO plugged in [PP]; see `maker-uno.md` for the USB chip.

## Power and electrical limits
- 4 × AA batteries power both the motors (Maker Drive VB+/VB−) and the Maker UNO (via the Maker Drive 5 V output) [PP][PP: tutorial]. Maker Drive accepts 2.5–9.5 V, 1.0 A continuous per channel, 5 V out 200 mA (`maker-drive.md` [DS]).
- TT motors: recommended 5–10 VDC; 120 mA each at 6 V [PP].
- Maker UNO has no DC jack or Vin pin (`maker-uno.md`). Whether USB and the battery may be connected at the same time is not stated.

## Software support
- 2025 sketch (matches the current wiring): gist `interns24-bit/a5906d33b629c7a83ccbe2b7de7daaa0`, embedded in the 2025 tutorial [PP: tutorial].
- Page "Sample code - Arduino": gist `suadanwar/de0a5c33ec351e02e0c5b389b5bfafd1`, `ObstaclesAvoidingRobot_MakerDrive.ino` (2019; turns right while an obstacle is under 10 cm; different pins) [PP: sample code].
- Arduino IDE; Cytron Motor Drivers Library; CH34X driver [PP]. Tutorial code is not copied here.
- The 2025 tutorial references "Obstacles Avoiding Robot Using Arduino and Maker Drive" and "DC Motor & Castors" (not read).

## Compatibility and accessories
- Components with KB files (not re-documented): **Maker UNO** → `maker-uno.md`; **Maker Drive** → `maker-drive.md`; **Robo Base Mini** (2 plates, 109 × 88 mm) → `robo-base-mini.md`.
- Similar kit: **PikaBot** → `pikabot.md` [PP note].
- Sister kit: **Line Following Mobile Robot Bundle** → `line-following-mobile-robot-bundle.md` (same chassis, boards and motors; IR line modules instead of the ultrasonic sensor). The 2025 tutorial suggests adding IR sensors for line following [PP: tutorial].
- No KB file: SR04P ultrasonic module, HC-SR04 bracket, TT motor and wheel set, TT motor bracket, W420 castor.

## Common mistakes / troubleshooting
- **Motors twitch or one side doesn't run with the page's sample code** → the 2019 sample uses pins 3/9 and 10/11; either rewire or use the 2025 sketch that matches pins 11/10 and 6/5 [PP: sample code][PP: tutorial].
- **Distance always huge or zero** → check TRIG on pin 3 and ECHO on pin 4 (2025) and sensor VCC/GND; the 2025 sketch reports 999 when no echo returns [PP: tutorial].
- **A wheel turns the wrong way** → swap that motor's wires; check with the Maker Drive test buttons [PP: tutorial].
- **Standoffs don't match the steps** → the steps use 4 × 30 mm and 2 × 15 mm; the page list says 4 × 10 mm and 2 × 30 mm — check the bag [PP][PP: tutorial].
- **Maker UNO not seen by the PC** → install the CH34X driver with the board plugged in [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Standoffs | [PP] packing list "4 x 10mm PCB stand", "2 x 30mm PCB stand" | [PP: tutorial] steps use 4 × M3 30 mm (join the bases) and 2 × M3 15 mm (Maker Drive); [PP: img] packing photo appears to show 4 tall and 2 short standoffs | Unresolved; the tutorial steps and photo suggest 4 long + 2 short |
| Base material | [PP] feature "Acrylic mobile robot base" | [PP] packing list and description: Robo Base Mini, "custom-designed PCB base"; [PP: img] yellow PCB plates | PCB (Robo Base Mini); the "acrylic" line is left over from an older kit version |
| Sample code pins | [PP: sample code] motors 3/9 and 10/11, TRIG 5, ECHO 4 | [PP: tutorial] motors 11/10 and 6/5, TRIG 3, ECHO 4 | Use the 2025 tutorial wiring with the 2025 sketch |
| Motor driver | [PP: tutorial 2019] L298ND driver | [PP] Maker Drive | Current kit uses Maker Drive; the 2019 tutorial is a legacy version |
| Sensor name | [PP] packing list "SR04P Ultrasonic Ranging Module"; feature link "Ultrasonic Sensor" → HC-SR04 page | [PP: tutorial] wiring table titled "HC-SR04 Ultrasonic Sensor" | SR04P ships (packing list); the tutorial uses the generic name |
| Kit list extras | [PP] 1 ultrasonic sensor, 1 battery holder | [PP: tutorial] kit list also shows "2 x Ultrasonic Sensor" and a second battery holder | Packing list wins; tutorial list has copy errors |
| Wheel diameter | [PP] "Wheel Diameter: 67mm" | [PP] "Speed with 66mm diameter wheel" | Page-internal; 67 mm is the wheel spec |

## Needs verification
- Which standoff lengths ship today (10/30 mm or 15/30 mm).
- Whether two TT motor brackets are packed (the packing photo appears to show one).
- SR04P detailed specs (range, current) — product page not read.
- Whether USB and battery power may be connected at once.
- Kit weight.
- Contents of the page video (YouTube `X6qFEwy2X2w`) and the CH34X driver files.

## Cytron tutorials
Add-on: Cytron tutorials that use this product. They never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Robo Base Mini Obstacle Avoidance Robot with Maker UNO and Maker Drive](https://my.cytron.io/tutorial/robo-base-mini-obstacle-avoidance-robot-with-maker-uno-and-maker-drive) — Tutorial, Beginner, 2025 (current build)
- [Obstacle Avoiding Robot](https://my.cytron.io/tutorial/obstacle-avoiding-robot) — Tutorial, Intermediate, 2019 (legacy L298ND build; pins do not apply)

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-obstacle-avoidance-mobile-robot-kit — read 2026-10-21 (KIT-RBT-OA; RM114.45 offer, RM131.25 normal, 30+ RM105.00; availability 35; warranty 12 months; description; features; specifications; packing list; resources; related tutorials)
- [PP: img] https://www.cytron.io/image/catalog/products/KIT-RBT-OA/Kit-RBT-OA%20Sch.jpg (wiring diagram) and https://static.cytron.io/image/catalog/products/KIT-RBT-OA/kit-rbt-oa-pack.png (packing photo) — viewed 2026-10-21
- [PP: tutorial] "Robo Base Mini Obstacle Avoidance Robot with Maker UNO and Maker Drive", Khye Yen Ang, 12 Sep 2025 — read in full 2026-10-21; sketch https://gist.github.com/interns24-bit/a5906d33b629c7a83ccbe2b7de7daaa0
- [PP: tutorial 2019] "Obstacle Avoiding Robot", suadanwar, 24 Jan 2019 — https://my.cytron.io/tutorial/obstacle-avoiding-robot — read 2026-10-21
- [PP: sample code] https://gist.github.com/suadanwar/de0a5c33ec351e02e0c5b389b5bfafd1 (`ObstaclesAvoidingRobot_MakerDrive.ino`, 20 Mar 2019) — read 2026-10-21
- KB cross-references: `maker-uno.md`, `maker-drive.md`, `robo-base-mini.md`, `pikabot.md`, `line-following-mobile-robot-bundle.md`
