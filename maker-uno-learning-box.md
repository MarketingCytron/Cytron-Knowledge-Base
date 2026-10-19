# Maker UNO Learning Box — Verified Reference

| | |
|---|---|
| Product code | `KIT-MAKER-UNO-START` (my.cytron.io product page [PP]; Opencircuit "model" agrees [3P]) |
| Family | Arduino kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | No datasheet exists. The kit's guide book is **"Arduino Learning Guide for Beginner Using Maker UNO"** (PDF, `Arduino_Learning_Guide_for_Beginner_Using_Maker_UNO.pdf`, Cytron) — **its host (s3-ap-southeast-1.amazonaws.com / cdn.cytron.io) was blocked from this environment, so the guide was NOT read**. Main source used: **Cytron product page "Maker UNO Learning Box - Everything You Need to Start Making"** (my.cytron.io, read by the coordinator 2026-10-19) [PP]. The board in the kit is documented in `maker-uno.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = my.cytron.io product page facts (coordinator capture). [UM-X] = the sibling guide "Arduino Learning Guide for Beginners Using Maker UNO X", v1.5 Feb 2023 (Drive PDF, read as text up to Lesson 6) — it is written for the **Maker UNO X** board and the Maker UNO X Learning Box, so its wiring is cited only as a cross-reference, never as this kit's spec. [3P] = Opencircuit listing (cross-check). Board facts: **see maker-uno.md**.

## What it is
- A starter kit: a **Maker UNO** board (see `maker-uno.md`) packed with the electronic parts needed for the 17 projects of Cytron's beginner learning guide [PP]. Product title: "Maker UNO Learning Box - Everything You Need to Start Making" [PP].
- Cytron's framing (reseller copy of the page): a beginner Arduino learning set written by a non-technical author, for students and teachers with no electronics or coding experience; each lesson shows a visible result early, then explains how it works [3P, quoting Cytron copy].
- The guide is "Arduino Learning Guide for Beginner Using Maker UNO" (PDF link on the page) [PP]. Whether a printed copy is in the box is not stated in the page text (the packing list does not list a book) [PP].

## Specifications
No spec table exists. Kit-level facts:

| Item | Value | Src |
|---|---|---|
| Controller board | 1× Maker UNO — board specs in `maker-uno.md` | [PP] |
| Lessons / projects | 7 lessons, 17 projects (list below) | [PP] |
| Packing list | 1× Maker UNO; 1× 3V miniature brush motor; 1× DIY 4-blade propeller (blue); 1× SR04 ultrasonic sensor; 1× IR line sensor; 3× LED 5 mm red; 3× LED 5 mm yellow; 3× LED 5 mm green; 3× pushbutton switch; 10× 220 Ω; 10× 1 kΩ; 10× 10 kΩ; 1× 1N4007 diode; 2× 2N2222 transistor; 1× finger preset 10K; 1× 40-way M-M jumper; 1× 40-way M-F jumper; 1× Micro B USB cable; 1× breadboard 8.5 cm × 5.5 cm | [PP] |
| Software | Arduino IDE; CH341 (CH34x) USB driver; Maker UNO default sketch on GitHub | [PP] |
| Warranty | 12 months | [PP] |
| Price | RM62.90 | [PP] |
| Dimensions / weight | Not stated | — |

### Lesson and project list [PP] (project titles [3P], matching the Maker UNO X edition of the guide [UM-X])
| Lesson | Projects |
|---|---|
| 1 Digital Output | P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence |
| 2 Digital Input | P4 On-board Pushbutton Switch; P5 External Pushbutton Switch |
| 3 Analog Output | P6 Construct An LED Circuit; P7 Fade An LED |
| 4 Melody Tone | P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code |
| 5 Analog Input | P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line |
| 6 DC Motor | P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton |
| 7 Ultrasonic Sensor | P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor |

## Interfaces, terminals and pin mapping
The Maker UNO edition of the guide was not read, so **no project wiring is confirmed for this kit**. Board-level pins that the lesson titles rely on (from `maker-uno.md`): on-board button D2 (`INPUT_PULLUP`), on-board piezo buzzer D8 (slide switch), programmable LEDs on the digital pins, analog inputs A0–A5, PWM on ~3, ~5, ~6, ~9, ~10, ~11.

Cross-reference only — the **Maker UNO X edition** (v1.5) wires its projects as follows [UM-X]; confirm against the Maker UNO edition before using in content: P1–P3 LED pins 7 and 2–7; P4 button D2 `INPUT_PULLUP` → LED 4; P5 external pushbutton on D3 with a 10 kΩ pull-up → LED 4; P6–P7 external LED + 220 Ω on D5 (PWM); P8–P10 buzzer `tone(8, …)`; P11 potentiometer on A0; P12–P13 IR sensor VCC→5V, GND→GND, A0→A0 (D0 unused), threshold ≈ 500 (user-measured); P14 motor on D5 PWM through a 2N2222 transistor, 220 Ω base resistor and a diode (white stripe to the red/positive wire).

## Rules and gotchas (for code, wiring and tutorials)
- **Board:** Maker UNO — USB power only, no DC jack, no Vin; CH340 driver; select "Arduino Uno" (Cytron: "Arduino/Genuino Uno") — see `maker-uno.md`.
- **Driver install:** the product page says to plug the Maker UNO into a USB port during CH34X driver installation [3P quoting the page]; Linux normally already has the driver [PP].
- **IR line sensor in the kit is analog-read in the lessons** ("Read Analog IR Sensor", "IR Sensor To Detect Black Line") [PP] — write the threshold from the user's own readings, not a fixed number.
- **Motor projects use the 2N2222 transistors and the 1N4007 diode in the packing list** [PP]; the 3 V brush motor must not be driven straight from an I/O pin (20 mA per pin, `maker-uno.md`).
- **Ultrasonic sensor is an SR04** (HC-SR04 class, 5 V) [PP]; it is used in Lesson 7 only.
- The 10 kΩ "finger preset" is the potentiometer for Lesson 5 [PP].
- Do not copy Maker UNO X-only behaviour (DEBUG switch, built-in breadboard) into Maker UNO Learning Box content — the X guide is for a different board.

## Power and electrical limits
- Power from the Micro USB cable only; no battery pack or adapter in the kit [PP]. Board limits in `maker-uno.md` (USB 4.8–5.2 V; 3.3 V pin 500 mA; 20 mA per I/O pin).
- Motor: "3V miniature brush motor" [PP]; its current draw is not stated by Cytron.

## Software support
- Arduino IDE (arduino.cc) [PP].
- CH34X driver downloads linked from the page: Windows (V3.5, Mar 2019), macOS (V1.5, Mar 2019), Linux (V1.5, Mar 2019, usually not needed), plus the WCH manufacturer page [PP].
- Maker UNO default program: https://github.com/CytronTechnologies/MakerUno_Examples/tree/master/MakerUno_DefaultSketch [PP].
- Beginner Guide PDF: see *Sources* (not read).

## Compatibility and accessories
- Controller: Maker UNO (`maker-uno.md`).
- Related products: Maker UNO Edu Kit (`maker-uno-edu-kit.md`, a different parts list with LDR and no sensors), PikaBot (`pikabot.md`), the Maker UNO X edition of this guide sold as a book (`maker-uno-x-learning-guide.md`, for the Maker UNO X Learning Box — a different kit).

## Common mistakes / troubleshooting
- No COM port → CH34X driver; plug the board in during install [PP/3P].
- Confusing this kit with the **Maker UNO X Learning Box**: same 17-project structure, different board (Maker UNO X) and guide edition [PP][UM-X].
- Quoting project wiring from the X guide as if it were this kit's — not confirmed (see *Needs verification*).
- Motor won't spin on a surface → the X edition notes the motor may lack torque if the blades rest on a surface [UM-X]; applies to the same 3 V motor/propeller but is not confirmed in this kit's guide.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Guide in the box | [PP] packing list has no book; page links a PDF | [3P] Opencircuit: "Beginner Guide (PDF)" only | Treat the guide as a PDF download; printed copy not stated |
| Resistor quantities | [PP] 10× 220 Ω, 10× 1 kΩ, 10× 10 kΩ | [3P] Opencircuit same | No conflict (Edu Kit resellers list 5× 1k/10k — different kit) |

## Needs verification
- **The Beginner Guide itself** (title, version, date, page count, every project's wiring and code) — PDF host blocked here. Read it before writing any Learning Box tutorial wiring.
- Whether a printed guide book ships in the box.
- Project pin assignments for the Maker UNO edition (X edition pins listed above as cross-reference).
- Which projects use the 1 kΩ resistors and the second 2N2222 (not stated on the page).
- Breadboard type (8.5 cm × 5.5 cm stated; tie-point count not stated).
- Box dimensions and weight.
- Age range / syllabus tags (none on the page capture).

## Sources
- [PP] https://my.cytron.io/p-maker-uno-learning-box-everything-you-need-to-start-making (coordinator capture, 2026-10-19)
- [UM, not read] Arduino Learning Guide for Beginner Using Maker UNO: http://s3-ap-southeast-1.amazonaws.com/cdn.cytron.io/makeruno/Arduino_Learning_Guide_for_Beginner_Using_Maker_UNO.pdf (blocked: s3-ap-southeast-1.amazonaws.com and cdn.cytron.io CONNECT 403 / WebFetch provenance refusal)
- [UM-X, cross-reference] Arduino Learning Guide for Beginners Using Maker UNO X, v1.5 Feb 2023: (Cytron document — link not public)
- [UM, board] MAKER-UNO User's Manual Rev 1.0, Dec 2017 — see `maker-uno.md`
- [GH] https://github.com/CytronTechnologies/MakerUno_Examples/tree/master/MakerUno_DefaultSketch
- [PP] CH34X driver links on the page: https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view (Windows) · https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view (macOS) · https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view (Linux)
- [3P] https://opencircuit.shop/product/Maker-UNO-Learning-Box-Everything-You-Need-To (copy of the Cytron page text; read 2026-10-19)
