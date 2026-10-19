# Maker UNO Edu Kit (Arduino Compatible) — Verified Reference

| | |
|---|---|
| Product code | `V-KIT-MUNO-EDU` (my.cytron.io product page [PP]; RobotShop "Manufacturer #" agrees [3P]). Cytron's older www.cytron.com.my page shows `KIT-MAKER-UNO-EDU` [PP: cytron.com.my] — see *Conflicts* |
| Family | Arduino kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | No datasheet exists for the kit. **Getting Started doc: "Maker UNO Edu Kit Getting Started Module" (PDF, `Maker_Uno_Edu_Kit_Module.pdf`, Cytron Technologies Sdn Bhd; sections Introduction / Lessons / Projects; editors Atifah Suad Anwar and Idris Zainal Abidin; no version or date printed)** [UM]. Second [UM]: "Teacher Guidebook, Maker-UNO / Arduino" (`MakerUNO_Teacher_Guide.pdf`, no version or date printed). The board in the kit is documented in `maker-uno.md` (MAKER-UNO User's Manual Rev 1.0, Dec 2017) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the Getting Started Module and the Teacher Guidebook above, both read through a summarising fetch of the PDF (not raw text; quotes limited, schematic labels partly garbled). [PP] = my.cytron.io product page facts captured by the coordinator on 2026-10-19, plus the cytron.com.my copy of the page. [3P] = The Pi Hut, Kubii, RobotShop, PiShop listings (cross-check only). Board facts: **see maker-uno.md** — this file does not re-document the Maker UNO.

## What it is
- A classroom kit built around the **Maker UNO** board (see `maker-uno.md`), sold as "Maker UNO Edu Kit (Arduino Compatible)" [PP]. Cytron's framing: students often lack basic electronics knowledge and spend most of a lesson wiring and troubleshooting, and teachers spend time sorting parts; the Maker UNO's on-board LEDs, buzzer and button let students "skip building basic circuits at first and start coding quickly" [PP].
- The module describes the Maker UNO as "designed and developed specially for students to learn coding and microcontroller" and as an Arduino UNO-compatible board [UM].
- Two purchase options [PP]: **Maker UNO Edu Kit** (single set) and **School Package 10+1** ("10 sets + 1 free set (Get 11 sets for the price of 10)").
- Teaching material: the Getting Started Module (10 lessons + 2 projects) [UM], a Teacher Guidebook written for the Malaysian **Form Two (Tingkatan 2) DSKP KSSM RBT** (Reka Bentuk dan Teknologi) syllabus [UM], a Student's Class Module and Answer Scheme in English and Bahasa Malaysia [PP: links], and the DSKP KSSM RBT Tingkatan 2 PDF [PP].
- The box has an opening for the USB cable so the board can be stored and used inside the box; students can write their name on the board; pin-label stickers are included but the user must peel and apply them [PP].

## Specifications
No kit-level spec table exists in any source. Kit-level items from the sources read:

| Item | Value | Src |
|---|---|---|
| Controller board | Maker UNO (ATmega328P, CH340 USB-serial, Micro USB, no DC jack) — details in `maker-uno.md` | [PP][UM] |
| On-board I/O used by the lessons | "12x LEDs, 1x piezo buzzer and 1x programmable button" | [PP] |
| Kit packing list | **Not stated in any Cytron text read.** The product page's "Each set comes with" list is an image that did not extract; the module and the Teacher Guidebook contain no packing list. Reseller lists exist — see *Needs verification* | — |
| Lessons in the Getting Started Module | 10 lessons + 2 projects (table below) | [UM] |
| Teacher Guidebook | 4 units, 10 hours total (2 + 3 + 2 + 3 h), learning standards 2.4.1–2.4.8, assessment Tier 1–6 | [UM] |
| Software | Arduino IDE 1.8.x (module screenshots); CH340 driver from the product page Attachment tab | [UM] |
| Pin-label stickers | Included; user applies them | [PP] |
| Warranty | Blank on the my.cytron.io page [PP]. (Maker UNO User's Manual: 6 months — see `maker-uno.md`) | [PP] |
| Price | RM60.00 (single kit) to RM689.92 (School Package 10+1) | [PP] |

### Getting Started Module — lesson list [UM]
| # | Title | Teaches | Wiring stated in the module |
|---|---|---|---|
| Intro | Introduction to Components (Maker UNO, Maker UNO Board); Setting Up (Download Arduino IDE; Install Maker UNO Drivers) | IDE install, driver, board/port selection | — |
| 1 | The LED (Digital Output) | `pinMode()`, `digitalWrite()`, `setup()`/`loop()` | LED on **pin 7** |
| 2 | LED Blinking | `delay()` | LED on pin 7 |
| 3 | LED Output (PWM) | `analogWrite()`; PWM pins marked "~" (~3, ~5, ~6, ~9, ~10, ~11) | LED on **pin 3** |
| 4 | Push Button as Digital Input | `digitalRead()`, `if`/`else if`, `INPUT_PULLUP` | LED on pin 4; on-board button on **pin 2** as `INPUT_PULLUP` |
| 5 | Serial Write | `Serial.begin(9600)`, `Serial.print()`, `Serial.println()` | USB only |
| 6 | Serial Read | `Serial.available()`, `Serial.read()` | LED on pin 7; "1" = on, "0" = off |
| 7 | Tone Melody | File > Examples > 02.Digital > toneMelody, `pitches.h` | Buzzer pin not named in the lesson text (on-board buzzer is pin 8 per the Components section) |
| 8 | Potentiometer as Analog Input | `analogRead()` | 10 kΩ potentiometer on **A0**; LED on pin 13 blinks at a rate set by the pot |
| 9 | LDR as Analog Input | `analogRead()`, `if`/`else` | LDR with 10 kΩ resistor on A0; LED on pin 13 turns on when the reading exceeds 600 |
| 10 | Controlling Motor | `analogWrite()` speed steps 255, 123, 50, 0 (1 s each) | Drive signal on **pin 6** through a 220 Ω resistor to a transistor (schematic labels e/b/c; transistor part number not named in the extracted text); no diode mentioned |
| P1 | Interactive Traffic Light | Combined outputs + button | Vehicle: green pin 5, yellow pin 6, red pin 7; pedestrian: green pin 3, red pin 4; button pin 2 (`INPUT_PULLUP`); 5 × 220 Ω. Sequence: yellow 2 s, red, pedestrian green 5 s, vehicle green again. Ingredients: Maker UNO ×1, breadboard ×1, red LED ×2, green LED ×2, yellow LED ×1, 220 Ω ×5, jumper wires |
| P2 | Light Theremin | Analog input to `tone()` | LDR + 10 kΩ on A0; piezo buzzer pin 8 via `tone()`; LED 13 shows calibration; calibration runs for the first 5 s after power-up. Ingredients: Maker UNO ×1, breadboard ×1, 10 kΩ ×1, LDR ×1, jumper wires |

### Teacher Guidebook — unit list [UM]
| Unit | Title | Time | Sub-units |
|---|---|---|---|
| 1 | Microcontroller Theory | 2 h | 1.1 microcontroller vs microprocessor; 1.2 parts of a microcontroller; 1.3 block diagrams; 1.4 schematic diagrams (60 min) |
| 2 | Output | 3 h | 2.1 output circuit programming (sample code toggles pins 8 and 9 with 1 s delays); 2.2 output device types; 2.3 connecting output circuits; 2.4 output circuit simulation |
| 3 | Input | 2 h | 3.1 input circuit programming; 3.2 input device types; 3.3 input circuit connection; 3.4 input circuit simulation |
| 4 | Combination of Input and Output | 3 h | 4.1 conditional structure (LED on pin 13 when a pushbutton reads 1); 4.2 combine circuits; 4.3 simulation; 4.4 project creation (90 min) |

Appendix 1 of the Teacher Guidebook: programming the board from an Android phone with "USB OTG Checker" and "ArduinoDroid" apps [UM]. Units 2.4, 3.4 and 4.3 need internet access; each student needs a Maker UNO [UM].

## Interfaces, terminals and pin mapping
Pins the Edu Kit lessons occupy on the Maker UNO (board pinout in `maker-uno.md`):

| Function | Pin | Src |
|---|---|---|
| On-board programmable button | D2, `INPUT_PULLUP` (pressed = LOW) | [UM] |
| On-board piezo buzzer | D8 (through the slide switch) | [UM] |
| Lesson LEDs (on-board or external) | D3 (PWM), D4, D5, D6 (PWM), D7, D13 | [UM] |
| Motor drive (Lesson 10) | D6 PWM → 220 Ω → transistor base | [UM] |
| Analog sensors (pot, LDR) | A0 | [UM] |
| Serial Monitor | USB (CH340), 9600 baud | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **Board selection:** the module's screenshots show "Select Board" and "Select Serial Port" but give no written board name [UM]. Use the Maker UNO rule in `maker-uno.md` (Cytron's advice: "Arduino/Genuino Uno", listed as "Arduino Uno" in current IDEs).
- **Driver:** "download the Maker UNO driver from the product page's Attachment tab, pick the version for your OS"; after install the port shows under Ports (COM & LPT), e.g. "USB-SERIAL CH340 (COM3)" [UM]. The module says CH340, the product page links "CH341" driver files (`CH341SER.EXE`, `CH341SER_MAC.ZIP`) — same WCH driver family [PP].
- **Button needs `INPUT_PULLUP`** on D2 and reads LOW when pressed [UM].
- **Buzzer shares D8** with the slide switch: slide on to use the buzzer, off to use pin 8 for something else [UM].
- **PWM only on ~3, ~5, ~6, ~9, ~10, ~11** [UM] — Lesson 3 uses pin 3 and Lesson 10 pin 6 for that reason.
- **Lesson 9 threshold 600 and Lesson 10 speed steps 255/123/50/0** are the module's values; tutorials that change them should say so [UM].
- **Light Theremin calibrates for 5 s after power-up** (LED 13 lit) — wave a hand over the LDR during that time [UM].
- The module was written for **Arduino IDE 1.8.x** (download page screenshots) [UM]; "a newer version is referenced, but no version is specified".
- Power is USB only (Maker UNO has no DC jack and no Vin) — never tell students to add a 9 V adapter (see `maker-uno.md`).

## Power and electrical limits
- Powered from the Micro USB cable (computer) — the kit adds no battery or adapter [PP][UM]. Board limits (USB 4.8–5.2 V, 3.3 V pin 500 mA, 20 mA per I/O pin) are in `maker-uno.md`.
- Lesson 10 drives the 3 V motor through a transistor from pin 6, not directly from the pin [UM]. The motor's own voltage/current rating is not stated in the module.

## Software support
- Arduino IDE (arduino.cc download; Windows installer recommended) [UM].
- CH340/CH341 USB driver for Windows and macOS; Linux normally needs none [PP][UM].
- Default sketch on GitHub: `MakerUno_Examples/MakerUno_DefaultSketch` [PP]. The optional "Maker Uno" Boards Manager package is described in `maker-uno.md` (not mentioned in the module [UM]).
- Teacher Guidebook Appendix 1: Android programming via USB OTG + ArduinoDroid [UM].
- Module: Lessons 5–6 use the Serial Monitor at 9600 baud; Lesson 7 uses the IDE's built-in toneMelody example [UM].

## Compatibility and accessories
- Controller: Maker UNO — `maker-uno.md` (Arduino UNO R3 shield-compatible except shields needing Vin).
- Documents linked from the product page [PP]: Maker UNO User's Manual (Google Doc), Getting Started Module PDF, MAKER-UNO schematic PDF, Fritzing part, CH341 drivers, DSKP KSSM RBT Tingkatan 2 PDF, Teacher's Guide, Student's Class Module, Answer Scheme, and Bahasa Malaysia versions (Modul Arduino, Panduan Guru, Modul Murid, Skema Jawapan).
- Syllabus: Malaysian KSSM RBT Form 2 (Teacher Guidebook) [UM][PP].
- Related products (separate KB files, not aliases): Maker UNO Learning Box (`maker-uno-learning-box.md`), PikaBot (`pikabot.md`), Maker UNO X Learning Guide book (`maker-uno-x-learning-guide.md`).

## Common mistakes / troubleshooting
- No COM port → install the CH340/CH341 driver; check Device Manager > Ports (COM & LPT) [UM].
- Button always reads HIGH → missing `INPUT_PULLUP` [UM].
- Buzzer silent → buzzer slide switch off; D8 device misbehaves → switch on [UM] (details in `maker-uno.md`).
- LED on a non-"~" pin won't fade → `analogWrite()` only works on PWM pins [UM].
- Random LEDs glowing after upload → floating inputs, normal (see `maker-uno.md`).
- Describing the kit's parts: do not quote a packing list as Cytron fact until the product-page image list is confirmed (see *Needs verification*).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Product code | [PP] my.cytron.io (2026-10-19): `V-KIT-MUNO-EDU`; RobotShop agrees [3P] | [PP] www.cytron.com.my page: `KIT-MAKER-UNO-EDU` | Use `V-KIT-MUNO-EDU` (current store). `KIT-MAKER-UNO-EDU` is the older code; keep as alias |
| Driver name | [UM] module: "CH340 driver" | [PP] links: "CH341" driver files | Same WCH CH34x driver family; say "CH340/CH341 (CH34x) driver" |
| Warranty | [PP] blank on the product page | Maker UNO User's Manual: 6 months (board) | Not stated for the kit — do not quote a kit warranty |
| Kit packing list | [PP] image only, not extracted; [UM] none | [3P] The Pi Hut and Kubii lists (below) | No Cytron text — list goes to *Needs verification* |

## Needs verification
- **Packing list.** Two resellers [3P] give the same list: 1× Maker UNO, 1× Micro USB cable, 3× red / 3× yellow / 3× green 5 mm LEDs, 1× breadboard, 40× male-to-male jumper wires, 10× 220 Ω, 5× 1 kΩ, 5× 10 kΩ resistors, 1× LDR, 1× 2N2222 transistor, 1× 10 kΩ preset potentiometer, 1× 3 V miniature brush motor, 1× 4-blade propeller, plastic box (The Pi Hut adds "pin-label stickers"; Kubii lists resistors as 0.25 W 5%). It matches the module's lessons (LDR, pot, motor, transistor) but no Cytron text states it. Confirm against the product-page image or packing SOP before quoting.
- Transistor part number and whether a flyback diode is used in Lesson 10 (module schematic labels garbled in extraction).
- Version, revision date and page count of the Getting Started Module (page numbers run to 55) and of the Teacher Guidebook.
- Whether the School Package 10+1 ships 11 identical single-kit boxes.
- Kit warranty term (page blank).
- Box dimensions and weight — not stated anywhere read.
- Whether the Getting Started Module tells readers which board name to select (only screenshots).
- The Student's Class Module and Answer Scheme PDFs were not read.

## Sources
- [UM] Maker UNO Edu Kit Getting Started Module (PDF, Cytron): https://cdn.cytron.io/makeruno/Maker_Uno_Edu_Kit_Module.pdf (read 2026-10-19 via summarising fetch)
- [UM] Teacher Guidebook, Maker-UNO / Arduino (PDF, Cytron): https://cdn.cytron.io/makeruno/MakerUNO_Teacher_Guide.pdf (read 2026-10-19 via summarising fetch)
- [UM, board] MAKER-UNO User's Manual Rev 1.0, Dec 2017: https://docs.google.com/document/d/1gJIF-tssdoxk8qAq2aHBmPwVHulFL_lSElOhA17Du64/edit (see `maker-uno.md`)
- [PP] https://my.cytron.io/p-maker-uno-edu-kits-arduino-compatible (coordinator capture, 2026-10-19) · https://www.cytron.com.my/p-kit-maker-uno-edu (read 2026-10-19)
- [PP] Linked documents: https://cdn.cytron.io/makeruno/MAKER-UNO.pdf (schematic) · https://cdn.cytron.io/makeruno/CH341SER.EXE · https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP · https://cdn.cytron.io/makeruno/MakerUNO_Student_Module.pdf · https://cdn.cytron.io/makeruno/MakerUNO_Answer_Scheme.pdf · http://cdn.cytron.io/makeruno/DSKP_KSSM_RBT_%20TINGKATAN2.pdf · http://cdn.cytron.io/makeruno/MakerUNO_Panduan_Guru.pdf · http://cdn.cytron.io/makeruno/MakerUNO_Modul_Murid.pdf
- [GH] https://github.com/CytronTechnologies/MakerUno_Examples/tree/master/MakerUno_DefaultSketch
- [3P] https://thepihut.com/products/maker-uno-edukit · https://www.kubii.com/en/micro-controllers/3483-makeruno-microcontroller-education-kit-for-arduino-3272496308343.html · https://www.robotshop.com/products/cytron-maker-uno-edu-kit-arduino-compatible · https://www.pishop.us/product/maker-uno-edu-kit-arduino-compatible/
