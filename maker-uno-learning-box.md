# Maker UNO Learning Box — Verified Reference

| | |
|---|---|
| Product code | `KIT-MAKER-UNO-START` (my.cytron.io product page [PP]; Opencircuit "model" agrees [3P]) |
| Family | Arduino kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — the kit's guide book "Arduino Learning Guide for Beginner Using Maker UNO" (Ver 1.3, Dec 2018, 90 pages) read in full from the copy in the team folder: text layer plus the wiring figures for Projects 5, 6, 12, 14 and 16 viewed as images. Project wiring is now Cytron-stated for this kit [UM] and matches the Maker UNO X edition. Raised Medium → Medium-high; still open: whether a printed guide ships and which project uses the 1 kΩ resistors. Earlier: 2026-10-19 master-table review of the live product page |
| Primary source | No datasheet exists (KB rule 7: the guide book is the main source). Guide book: **"Arduino Learning Guide For Beginner Using Maker UNO"**, Cytron, **Ver 1.3, Dec 2018**, 90 pages, file `Arduino_Learning_Guide_for_Beginner_Using_Maker_UNO.pdf` (the PDF linked from the product page), read in full 2026-10-21 [UM]. Also the Cytron product page "Maker UNO Learning Box - Everything You Need to Start Making" [PP]. The board in the kit is documented in `maker-uno.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the Maker UNO edition of the guide above (read 2026-10-21). [PP] = my.cytron.io product page facts (coordinator capture). [UM-X] = the sibling guide "Arduino Learning Guide for Beginners Using Maker UNO X", v1.5 Feb 2023 (Drive PDF, read as text up to Lesson 6) — it is written for the **Maker UNO X** board; its project wiring matches this kit's guide. [3P] = Opencircuit listing (cross-check). Board facts: **see maker-uno.md**.

## What it is
- A starter kit: a **Maker UNO** board (see `maker-uno.md`) packed with the electronic parts needed for the 17 projects of Cytron's beginner learning guide [PP]. Product title: "Maker UNO Learning Box - Everything You Need to Start Making" [PP].
- Cytron's framing (reseller copy of the page): a beginner Arduino learning set written by a non-technical author, for students and teachers with no electronics or coding experience; each lesson shows a visible result early, then explains how it works [3P, quoting Cytron copy].
- The guide is "Arduino Learning Guide For Beginner Using Maker UNO", Ver 1.3, Dec 2018: Lesson 0 (setting up hardware and software) plus Lessons 1–7 with 17 projects, each with "How it works", "Good To Know", a challenge and demo-video links [UM]. Whether a printed copy is in the box is not stated (the packing list does not list a book) [PP].

## Specifications
No spec table exists. Kit-level facts:

| Item | Value | Src |
|---|---|---|
| Controller board | 1× Maker UNO — board specs in `maker-uno.md` | [PP] |
| Lessons / projects | Lesson 0 setup + 7 lessons, 17 projects (list below) | [UM][PP] |
| Packing list | 1× Maker UNO; 1× 3V miniature brush motor; 1× DIY 4-blade propeller (blue); 1× SR04 ultrasonic sensor; 1× IR line sensor; 3× LED 5 mm red; 3× LED 5 mm yellow; 3× LED 5 mm green; 3× pushbutton switch; 10× 220 Ω; 10× 1 kΩ; 10× 10 kΩ; 1× 1N4007 diode; 2× 2N2222 transistor; 1× finger preset 10K; 1× 40-way M-M jumper; 1× 40-way M-F jumper; 1× Micro B USB cable; 1× breadboard 8.5 cm × 5.5 cm | [PP] |
| Software | Arduino IDE; CH341 (CH34x) USB driver; Maker UNO default sketch on GitHub | [PP] |
| Warranty | 12 months | [PP] |
| Price | RM62.90 | [PP] |
| Dimensions / weight | Not stated | — |

### Lesson and project list [UM][PP]
| Lesson | Projects |
|---|---|
| 1 Digital Output | P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence |
| 2 Digital Input | P4 On-board Pushbutton Switch; P5 External Pushbutton Switch |
| 3 Analog Output | P6 Construct An LED Circuit; P7 Fade An LED |
| 4 Melody Tone | P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code |
| 5 Analog Input | P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line |
| 6 DC Motor | P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton |
| 7 Ultrasonic Sensor | P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Page re-read:** 17 projects covering 7 lessons (digital output, digital input, analog output, melody tone, analog input, DC motor, ultrasonic sensor); packing list unchanged; prices subject to SST from April 2026 [PP].
- **Parts linked from the packing list:** 3 V miniature brush motor (MO-130SA-2270), 4-blade propeller (HD-PROP-4B), SR04 ultrasonic (SN-HC-SR04), IR line sensor (SN-IRLINE-MOD), 5 mm LEDs (DS-LED-5NR/5NY/5NG), push button (SW-PBM-2N-060601), resistors (RS-025W-220R/1K/10K), 1N4007, 2N2222, finger preset 10K (RS-MP3386-10K), jumper wires (WR-JW-40MM, WR-JW-40MF), USB Micro-B cable (WR-USB-UB), breadboard (BD-BB-0508) [PP: packing-list links].
- **Resources:** Beginner Guide PDF (cdn.cytron.io), CH34X drivers, Maker UNO default program (GitHub), Arduino IDE [PP].

## Interfaces, terminals and pin mapping
Project wiring as printed in the guide (text and Fritzing figures) [UM]:

| Project | Wiring / pins | Src |
|---|---|---|
| Lesson 0 | stick the pin-label stickers on the Maker UNO pin headers; connect with the micro USB cable | [UM] |
| P1–P3 LEDs | on-board LEDs: P1/P2 pin 7; P3 pins 2–7 in sequence (challenge: LEDs 2–13) | [UM] |
| P4 on-board button | pin 2 `INPUT_PULLUP` (pressed = LOW) → LED pin 4; the on-board switch occupies pin 2, so nothing else can use it | [UM] |
| P5 external button | push button on the breadboard with a **10 kΩ pull-up**, read on **pin 3** (`INPUT`) → LED pin 4 | [UM] |
| P6–P7 external LED | LED + **220 Ω** on **pin 5** (PWM); long leg = +, short leg (flat edge) = − ; P6 waits for the on-board button (pin 2) then blinks forever until reset | [UM] |
| P8–P10 tones | on-board piezo buzzer on **pin 8** — slide its switch to the speaker sign to use it, to the mute sign when pin 8 drives other I/O | [UM] |
| P11 potentiometer | wiper on **A0**, Serial Monitor | [UM] |
| P12–P13 IR sensor | IR module (VCC, GND, D0, A0 pins) powered from 5V/GND, analog output → **A0**; P13 LED on pin 3 lights over the black line; threshold "IRvalue > 500 for my case" — measure your own white and black readings | [UM] |
| P14–P15 DC motor | motor driven from **pin 5** (PWM) through a **2N2222** transistor with a **220 Ω** base resistor and a **diode** across the motor; the diode's white stripe goes to the motor's positive (red) wire; P14 runs 255 for 3 s then 80 for 3 s after the on-board button is pressed | [UM] |
| P16–P17 ultrasonic | HC-SR04: **GND → GND, Echo → pin 12, Trig → pin 11, VCC → 5V**; mount it at the breadboard edge so jumpers do not block it; P17 beeps the buzzer (pin 8, note F4) faster as the object gets closer (beep interval = distance × 10 ms; continuous under 2 cm) | [UM] |

Board-level facts: see `maker-uno.md` (PWM on ~3, ~5, ~6, ~9, ~10, ~11; analog inputs A0–A5).

## Rules and gotchas (for code, wiring and tutorials)
- **Board:** Maker UNO — USB power only, no DC jack, no Vin; CH340 driver; select "Arduino Uno" (Cytron: "Arduino/Genuino Uno") — see `maker-uno.md`.
- **Driver install:** the product page says to plug the Maker UNO into a USB port during CH34X driver installation [3P quoting the page]; Linux normally already has the driver [PP].
- **IR line sensor in the kit is analog-read in the lessons** (A0) [UM] — write the threshold from the user's own readings, not a fixed number; P13 uses a 2 cm black line on white card about 2 cm from the sensor [UM].
- **Motor projects use a 2N2222 transistor and the 1N4007 diode** (pin 5 PWM, 220 Ω base resistor) [UM][PP]; the 3 V brush motor must not be driven straight from an I/O pin (20 mA per pin, `maker-uno.md`). Hold the motor while testing — it may lack the torque to spin if the propeller rests on the table [UM]. The guide notes the motor is a 3 V toy motor and that running a motor above its rated voltage for long shortens its life; this circuit cannot reverse the motor — use a motor driver for that [UM].
- **Tone timing:** 1 beat (quarter note) = 250 ms; add a delay about 30 % longer than the tone (e.g. 325 ms) so the note completes [UM].
- **Driver links printed in the guide:** cdn.cytron.io/makeruno/CH341SER.EXE (Windows) and CH341SER_MAC.ZIP (macOS); on macOS the port shows as /dev/cu.wchusbserial1410 [UM]. Screenshots show Arduino IDE 1.8.5 [UM]; use the current IDE.
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
- Beginner Guide PDF: Ver 1.3, Dec 2018 — see *Sources*.

## Compatibility and accessories
- Controller: Maker UNO (`maker-uno.md`).
- Related products: Maker UNO Edu Kit (`maker-uno-edu-kit.md`, a different parts list with LDR and no sensors), PikaBot (`pikabot.md`), the Maker UNO X edition of this guide sold as a book (`maker-uno-x-learning-guide.md`, for the Maker UNO X Learning Box — a different kit).

## Common mistakes / troubleshooting
- No COM port → CH34X driver; plug the board in during install [PP/3P].
- Confusing this kit with the **Maker UNO X Learning Box**: same 17-project structure, different board (Maker UNO X) and guide edition [PP][UM-X].
- Motor won't spin on a surface → hold the motor; it may lack torque if the blades rest on the table; check the LED on pin 5 lights full then dim [UM].
- No sound from the buzzer → its slide switch is on the mute side [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Guide in the box | [PP] packing list has no book; page links a PDF | [3P] Opencircuit: "Beginner Guide (PDF)" only | Treat the guide as a PDF download; printed copy not stated |
| Resistor quantities | [PP] 10× 220 Ω, 10× 1 kΩ, 10× 10 kΩ | [3P] Opencircuit same | No conflict (Edu Kit resellers list 5× 1k/10k — different kit) |

## Needs verification
- Whether a printed guide book ships in the box (the packing list does not list one).
- What the 1 kΩ resistors and the second 2N2222 are for — the guide's 17 projects use only 220 Ω and 10 kΩ resistors and one transistor.
- Breadboard type (8.5 cm × 5.5 cm stated; tie-point count not stated).
- Box dimensions and weight.
- Age range / syllabus tags (none on the page capture).

## Sources
- [PP] https://my.cytron.io/p-maker-uno-learning-box-everything-you-need-to-start-making (coordinator capture, 2026-10-19)
- [UM] Arduino Learning Guide For Beginner Using Maker UNO, Ver 1.3, Dec 2018, 90 pages: http://s3-ap-southeast-1.amazonaws.com/cdn.cytron.io/makeruno/Arduino_Learning_Guide_for_Beginner_Using_Maker_UNO.pdf (read in full 2026-10-21 from the copy in the team folder)
- [UM-X, cross-reference] Arduino Learning Guide for Beginners Using Maker UNO X, v1.5 Feb 2023: (Cytron document — link not public)
- [UM, board] MAKER-UNO User's Manual Rev 1.0, Dec 2017 — see `maker-uno.md`
- [GH] https://github.com/CytronTechnologies/MakerUno_Examples/tree/master/MakerUno_DefaultSketch
- [PP] CH34X driver links on the page: https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view (Windows) · https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view (macOS) · https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view (Linux)
- [3P] https://opencircuit.shop/product/Maker-UNO-Learning-Box-Everything-You-Need-To (copy of the Cytron page text; read 2026-10-19)
