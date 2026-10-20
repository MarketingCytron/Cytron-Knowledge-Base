# Learning Guide for Beginners with Maker Uno X (book) — Verified Reference

| | |
|---|---|
| Product code | `BOK-MUNOX` (my.cytron.io product page [PP]) |
| Family | Arduino kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 4): live my.cytron.io product page read (description, features, packing list, resources). Page lists all 17 project titles and the packing list; Projects 15–17 content is still unread, so it stays Medium |
| Primary source | The product IS the document. **Guide book: "Arduino Learning Guide for Beginners Using Maker UNO X", v1.5, February 2023, published by Cytron Technologies** (Drive PDF `Arduino Learning Guide for Beginners Using Maker UNO X R15 Feb23.pdf`) [UM]. Read as extracted text from the cover to Lesson 6 Project 14 (p. ~80); Projects 15–17 were cut off by the reader. An older edition v1.4 (February 2020) also exists on Drive [UM-v1.4, cover only] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the v1.5 guide above (text extraction; circuit drawings are images and were not readable; "ti" ligature drops appear in places). [PP] = my.cytron.io page "Learning Guide for Beginners with Maker Uno X compatible with Arduino" (coordinator capture 2026-10-19). This file documents the **book** only. The Maker UNO X board has its own KB file (`maker-uno-x.md`) — statements about the board below are what the guide says.

## What it is
- A printed beginner's guidebook for learning Arduino on the **Maker UNO X** board, sold on its own as "Learning Guide for Beginners with Maker Uno X compatible with Arduino"; "designed for the Maker Uno X Learning Box"; packing: 1× book [PP].
- Cover/inside title: "Arduino Learning Guide For Beginners — MAKER UNO X", "Explore STEM and Coding with Maker UNO Xperiment Kit"; written by ET Tan (Tan Eng Tong, Co-founder and CEO, Cytron Technologies), edited by Cheryl Ng, illustrated by Suhana Azmi (OCR: "Suhana Oazmi"), revised by Hairil and 'Awatif (v1.5); "v1.5 February 2023"; "Published by Cytron Technologies" [UM].
- Opens with a letter from Eng Tong: written "with you in mind - a student (or teacher), learning Arduino for the first time"; explains the "how it works" that other guides skip, for readers without a C background [UM].
- Structure: Lesson 0 (Setting Up) + 7 lessons / 17 projects; every project ends with "Click here or scan QR code to watch the demo video" (YouTube), and each lesson ends with a Task and a "CONGRATULATIONS! You have completed Lesson N and learnt the following" summary [UM].

## Specifications
| Item | Value | Src |
|---|---|---|
| Format | Printed book ("Packing: 1x book") | [PP] |
| Edition | v1.5, February 2023 (page footer "Simplifying Digital Making") | [UM] |
| Earlier edition | v1.4, February 2020 (same title, same lesson list) | [UM-v1.4] |
| Target board | Maker UNO X (with the Maker UNO X Learning Box) | [PP][UM] |
| Lessons / projects | 7 lessons, 17 projects (+ Lesson 0 Setting Up) | [PP][UM] |
| Page numbers (v1.5 contents) | L0 p.6–7; P1 p.14; P4 p.27; P6 p.36; P8 p.47; P11 p.61; P14 p.76; P16 p.89; P17 p.97 | [UM] |
| Software covered | Arduino IDE (arduino.cc download; Windows 10+ 64-bit recommended); CH340/CH341 driver for Windows and Mac | [UM] |
| Price | RM39.00 (5+ RM37.10, 10+ RM35.10) | [PP] |
| Warranty | 12 months | [PP] |
| Size / page count / ISBN | Not stated | — |

### Lesson and project list [UM]
| Lesson | Projects | Learnt (lesson summary) |
|---|---|---|
| 0 Setting Up | Hardware (stickers, breadboard, USB); Software — Arduino IDE and driver | — |
| 1 Digital Output | P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence | set a pin as digital output; HIGH/LOW; `delay()` |
| 2 Digital Input | P4 On-board Pushbutton Switch; P5 External Pushbutton Switch | read digital input; control an LED with a switch; pull-up / pull-down circuit; `if-else` |
| 3 Analog Output | P6 Construct An LED Circuit; P7 Fade An LED | LED circuit; `while` loop; digital vs analog output; shorter code |
| 4 Melody Tone | P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code | `tone()`; compose a melody; load an IDE example (toneMelody); `for` loop and arrays |
| 5 Analog Input | P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line | `analogRead()` 0–1023; Serial Monitor; how an IR sensor works; variables |
| 6 DC Motor | P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton | transistor-driven motor; PWM speed (P15 not read) |
| 7 Ultrasonic Sensor | P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor | (not read) |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** guidebook designed for the Maker Uno X Learning Box, also usable as a general Arduino beginner reference; written by a non-technical person; "copy, upload, see the result, then learn" approach [PP].
- **Project list (page):** Lessons 1–7 with Projects 1–17, ending with Project 15 "Controlling A Motor Speed Using A Pushbutton", Project 16 "Setting Up Ultrasonic Sensor", Project 17 "Build A Car's Rear Bumper Sensor" [PP].
- **Packing list:** 1x Arduino Learning Guide for Beginners with Maker Uno X [PP]. No PDF link on this page (the Maker UNO X board page links the Rev1.5 and Rev1.4 PDFs) [PP].

## Interfaces, terminals and pin mapping
Pins and parts each project uses, as the guide states them [UM]:

| Project | Components | Wiring / pins |
|---|---|---|
| P1–P2 | on-board LED | `pinMode(7, OUTPUT)`; `digitalWrite(7, HIGH)`; blink with `delay(100)` then `delay(1000)` |
| P3 | on-board LEDs 2–7 | pins 2–7 OUTPUT, lit in sequence with 1000 ms delays; Task: LEDs 2–13 pattern |
| P4 | on-board switch, LED 4 | `pinMode(2, INPUT_PULLUP)`; `digitalRead(2) == LOW` → `digitalWrite(4, HIGH)` |
| P5 | pushbutton switch, jumper wires, 10 kΩ resistor | external switch on **pin 3** (`pinMode(3, INPUT)`, pull-up circuit; LOW when pressed) → LED 4 |
| P6 | LED, 220 Ω resistor, jumper wires | external LED on **pin 5**; on-board switch (pin 2) starts an endless `while(1)` blink at 200 ms; stops only on reset |
| P7 | same circuit as P6 | `analogWrite(5, 60…0)` fading in steps of 10 every 200 ms; then a `brightness` variable version |
| P8 | on-board piezo buzzer | `tone(8, f, 250)` + `delay(325)`: Do 262, Re 294, Mi 330, Fa 349, So 392, La 440, Ti 494, high Do 523 Hz |
| P9 | buzzer | first line of "Happy Birthday": G4 392 ×2 (125 ms), A4 440, G4 392, C5 523 (250 ms), B4 494 (500 ms), in `setup()` so it plays once |
| P10 | buzzer | File > Examples > 02.Digital > toneMelody with `pitches.h`; melody `{G4, G4, A4, G4, C5, B4}`, durations `{8, 8, 4, 4, 4, 2}`, 6 notes |
| P11 | potentiometer, jumper wires | pot on **A0**; `Serial.begin(9600)`; `Serial.println(analogRead(A0))` every 1000 ms |
| P12 | IR sensor, jumper wires | IR sensor VCC → 5V, GND → GND, A0 → A0 (D0 not connected); same sketch as P11 |
| P13 | IR sensor, white card with a 2 cm black line, ~2 cm from the sensor | `irValue > 500` (author's threshold; reader sets midpoint of white/black readings) → LED 3 on |
| P14 | DC motor with blade, diode ("white stripe … to the positive wire (red)"), 220 Ω resistor, 2N2222 transistor, jumper wires | motor driven from **pin 5** (PWM) via the transistor; on-board switch (pin 2) starts `analogWrite(5, 255)` 3 s / `analogWrite(5, 80)` 3 s forever |

Board behaviour the guide relies on [UM]: on-board LEDs on pins 2–13, piezo buzzer on pin 8, on-board switch on pin 2 (internally connected; cannot be used for other components while in use), a **"Debug" mode slide switch** that enables the built-in LEDs and the buzzer, PWM only on pins 3, 5, 6, 9, 10, 11 ("~"), analog input only on A0–A5, 3.3V and 5V pins used to demonstrate motor speed vs voltage.

## Rules and gotchas (for code, wiring and tutorials)
- **Debug mode:** "Remember to turn on the 'Debug' mode to enable the built-in LEDs on Maker UNO X"; "The on-board piezo buzzer is connected to Pin 8. You need to switch on the DEBUG mode to activate the piezo buzzer"; switch it off "if you want to connect Pin 8 to another I/O device" [UM]. This is a Maker UNO X feature — the plain Maker UNO has separate buzzer-switch behaviour (`maker-uno.md`).
- **On-board switch = pin 2 with `INPUT_PULLUP`**; LED 2 goes off when the switch is pressed (input indicator) [UM].
- **Tone timing rule:** add a delay 30 % longer than the note duration (250 ms note → 325 ms delay); quarter note = 250 ms assuming a 1 s whole note [UM].
- **Threshold rule for the IR sensor:** Threshold = (reading on white + reading on black) / 2; the author's 500 is an example ("You may need to change the threshold value according to your readings") [UM]. Near object = low reading, far = high; black = high, white = low [UM].
- **Motor circuit:** diode stripe to the red (positive) wire; motor may lack torque "if the blades are resting on a surface"; "WARNING! Applying high voltage to a motor (beyond the recommended voltage) will shorten a motor's life cycle"; the kit motor's recommended voltage is 3–6 V [UM].
- **Code hygiene taught:** Arduino is case sensitive (`OUTPUT`, `pinMode`, `digitalWrite`); check `;`, `( )`, `{ }`; code in `setup()` runs once, in `loop()` forever; `while(1)` never exits without reset [UM].
- **Driver:** Windows `CH341SER.EXE`; Mac `CH341SER_MAC.ZIP` then restart; Mac port appears as `/dev/cu.usbserial-220` (author's example); Mac troubleshooting PDF `Troubleshooting_CH431_Driver_For_Mac.pdf` on cdn.cytron.io [UM].
- **Board selection is not stated in the text read** — do not quote one from this book.

## Power and electrical limits
- Not a powered product. Projects run from the Maker UNO X over a micro USB cable [UM]. Motor voltage demonstration uses the board's 3.3V and 5V pins; the kit motor is "3-6V" [UM].

## Software support
- Arduino IDE from https://www.arduino.cc/en/main/software ("JUST DOWNLOAD"); Windows installer "Windows Win 10 and newer, 64 bits" recommended; Mac package [UM].
- Drivers: https://cdn.cytron.io/makeruno/CH341SER.EXE and https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP [UM].
- Demo videos: YouTube links per project (m.youtube.com, listed in the PDF) [UM].
- Reference: Arduino ToneMelody tutorial for note frequencies [UM].

## Compatibility and accessories
- For the **Maker UNO X** board and the **Maker UNO X Learning Box** [PP][UM]; the Maker UNO X Learning Box product is not documented in this KB.
- Not for the Maker UNO Learning Box (`maker-uno-learning-box.md`), which uses the Maker UNO edition of the same guide ("Arduino Learning Guide for Beginner Using Maker UNO") and a board without a Debug switch.
- Related: Maker UNO Edu Kit (`maker-uno-edu-kit.md`), PikaBot (`pikabot.md`).

## Common mistakes / troubleshooting
- LEDs/buzzer dead → Debug mode switch off [UM].
- Upload error → board not connected or wrong port (Tools > Port > COM_) [UM].
- "Done Compiling" fails → case, missing `;`/brackets, `( )` vs `{ }` [UM].
- P3 LEDs all light at once → no `delay()` between writes [UM].
- P6 LED keeps blinking → by design (`while(1)`); press reset [UM].
- P9 plays once → by design (code in `setup()`) [UM].
- Motor doesn't spin but LED 5 pulses → circuit fault; check diode polarity and transistor wiring [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Title | [PP] "Learning Guide for Beginners with Maker Uno X compatible with Arduino" | [UM] "Arduino Learning Guide For Beginners — MAKER UNO X" | Product title vs book title; use the product title for the store, the book title for citations |
| Illustrator name | [UM] OCR "Suhana Oazmi" | Cytron staff listing "Suhana Azmi" (Drive) | OCR error; "Suhana Azmi" |

## Needs verification
- Projects 15, 16 and 17 (pins, components, code) — not read (reader truncation).
- Total page count, physical size, binding, ISBN.
- Whether the printed book sold as BOK-MUNOX is v1.5 (the page does not state the edition; "an earlier KB note says v1.5").
- Which Arduino board name the guide tells readers to select.
- Breadboard supplied with the Learning Box (the guide says to peel and stick it onto the Maker UNO X board) — kit fact, not book fact.

## Sources
- [UM] Arduino Learning Guide for Beginners Using Maker UNO X, v1.5 Feb 2023 (PDF): (Cytron document — link not public) (read 2026-10-19 as text, cover to p. ~80)
- [UM-v1.4] Arduino-Learning-Guide-for-Beginners-Using-Maker-UNO-X.pdf, v1.4 Feb 2020: (Cytron document — link not public) (cover and contents only)
- [PP] https://my.cytron.io/p-arduino-learning-guide-for-beginners-with-maker-uno-x (coordinator capture, 2026-10-19)
- [UM] Driver links in the guide: https://cdn.cytron.io/makeruno/CH341SER.EXE · https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP · https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf
- [UM] Kit page linked in the guide: https://my.cytron.io/p-maker-uno-x-learning-box-everything-you-need-to-start-making (not read)
