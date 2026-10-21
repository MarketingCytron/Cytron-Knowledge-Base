# Maker UNO X for Classrooms (Arduino Compatible) — Verified Reference

| | |
|---|---|
| Product code | `MAKER-UNO-X` [PP] |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron design files from the GitHub repo `CytronTechnologies/MAKER-UNO-X` ("Schematic & PCB Layout") read in full: the one-sheet schematic PDF (MAKER UNO X, REV 1.0.0, dated "11/1/2019") viewed as zoomed images, both assembly diagrams (Value / Name), and the Eagle .sch/.brd checked for part values, nets, header positions and the board outline. Settled: USB-serial chip printed CH340C (library MPN "CH9340C"), RT9013-33GB 3.3 V regulator ("3.3V 500mA"), USB 5 V wired straight to the 5 V rail with no fuse or diode, VIN header pin fed *from* 5 V through a Schottky diode (output, not an input), no DC jack, a 555 "power bank keep-alive load" with PWRBANK LED, the Debug switch powering the LED/buzzer rail from 3.3 V with each LED and the buzzer driven by a BSS138 MOSFET, button D2 to GND via 1 kΩ, UNO R3-style header pinout, board outline 127.0 × 88.9 mm. Raised Medium → Medium-high; still open: chip marking on real boards, UNO R3 shield physical fit, 5 V / 3.3 V pin current limits. Earlier: 2026-10-19 master-table review of the live product page (D0/D1 LEDs and packing list confirmed; CH9340 vs CH340 and dimensions were left open) |
| Primary source | No Cytron datasheet exists for this board (none found on Drive or GitHub). Main source: Cytron guide book **"Arduino Learning Guide For Beginners — MAKER UNO X", v1.5, February 2023**, published by Cytron Technologies (Drive PDF `Arduino Learning Guide for Beginners Using Maker UNO X R15 Feb23.pdf`) [UM], plus the Cytron design files — schematic **"MAKER UNO X", product code MAKER-UNO-X, REV 1.0.0, dated "11/1/2019"**, assembly diagrams and Eagle board file from https://github.com/CytronTechnologies/MAKER-UNO-X [DT] — and the my.cytron.io product page [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the v1.5 guide (text extraction; read in full on 2026-10-21, 104 pages; drawings are images). [UM-v1.4] = the v1.4 edition (February 2020), read to the same point, used only for differences. [PP] = my.cytron.io page "Maker UNO X for Classrooms (Arduino Compatible)", captured by the coordinator in a browser on 2026-10-19. [DT] = Cytron design files in https://github.com/CytronTechnologies/MAKER-UNO-X folder `Schematic and PCB/` (supplied by the Cytron marketing team; repo last commit 29 Jul 2021): `Schematic - PDF/MAKER-UNO-X.pdf` (1 sheet, title block "Name: MAKER UNO X · Product Code: MAKER-UNO-X · REV: 1.0.0 · Date: 11/1/2019 11:51 AM · Sheet 1/1", PDF printed 14 Nov 2019; no text layer, read as 400 dpi images), `Assembly Diagrams/Value - MAKER-UNO-X.pdf` and `Name - MAKER-UNO-X.pdf`, and the Eagle 7.7 `Project/MAKER-UNO-X.sch` / `.brd` (parsed for part values, nets, header pad positions, holes and board outline), all read 2026-10-21. Measurements and current/timing figures marked *calculated* or *inferred* are worked out from these files, not printed in them. [GH] = the Fritzing part `Fritzing/MakerUnoX.fzpz` in the same repo (part title "Maker UNO X", author SC Lim, dated Fri Jan 17 2020, family "Maker UNO"); the repo has no README. The guide book itself is a separate KB product (`maker-uno-x-learning-guide.md`, BOK-MUNOX); the older board is `maker-uno.md`.

## What it is
- An Arduino UNO-compatible board built on the ATmega328P, aimed at educators and classrooms: "code right away", the board lights up and plays a melody with a button press, no soldering [PP].
- Built in: an LED on every digital pin (12x LEDs D2–D13 plus TX/RX LEDs on D0/D1), a piezo buzzer on D8, a programmable push button on D2, and an onboard perfboard prototyping area plus a breadboard [PP]. A "Debug" mode slide switch enables the built-in LEDs and the buzzer [UM].
- Powered, programmed and connected over USB Micro-B; "Powerbank-friendly" [PP] — done by an onboard 555-timer "power bank keep-alive load" that pulses a small load so power banks do not switch off [DT].
- Schematic blocks (REV 1.0.0): USB to UART converter (CH340C), 3.3V voltage regulator (RT9013-33GB), power bank keep-alive load (NE555), ATmega328P-AU with 16 MHz crystal, female headers in the UNO R3 pinout plus a 2×3 ICSP header, push buttons (RESET, BUTTON), and "Debug IO LEDs & piezo buzzer" [DT].
- Cytron calls it "the culmination of years of teaching Arduino & STEM by our education partners - Chumbaka, ARUS, and rero EDUteam"; its predecessor Maker UNO was 1825% funded on Kickstarter (17 Apr 2018) [PP] — positioning, not spec.

## Specifications
No datasheet spec table exists. The product page feature/spec list, every row [PP]:

| Item | Value | Src |
|---|---|---|
| Compatibility | Arduino UNO compatible; "fully compatible with Arduino UNO R3 sample code and libraries" | [PP] |
| Microcontroller | ATmega328P | [PP] |
| Operating voltage | 5V | [PP] |
| USB connector | USB Micro B — "for power, program loading and USB communication" | [PP] |
| Powerbank | "Powerbank-friendly" ("*Enable continuous supply from most powerbanks") | [PP] |
| Digital I/O pins | 20 | [PP] |
| PWM pins | 6 | [PP] |
| Analog input pins | 6 (10-bit) | [PP] |
| UART / SPI / I2C | 1 / 1 / 1 | [PP] |
| Flash memory | 32KB | [PP] |
| SRAM | 2KB | [PP] |
| EEPROM | 1KB | [PP] |
| Clock speed | 16MHz | [PP] |
| USB to UART chip | "CH9340" as written on the page; the schematic, silkscreen and assembly diagram print **CH340C** (U2, SOIC-16) — see Conflicts | [PP][DT] |
| Push button | 1x programmable push button (Pin D2) | [PP] |
| Buzzer | 1x piezo buzzer (Pin D8) | [PP] |
| I/O indicator LEDs | 12x LED as I/O indicators (Pin D2 to D13) | [PP] |
| UART activity LEDs | 2x LED as UART TX/RX activity indicators (Pin D0 & D1) | [PP] |
| Prototyping | Onboard perfboard prototyping area and a half-size breadboard; "Breadboard and donut board (perfboard) are included onboard" | [PP] |
| Programming | Arduino IDE, choosing "Arduino UNO" | [PP] |
| Packing list | 1x Maker UNO X board, 1x mini breadboard, 1x Maker UNO pin sticker | [PP] |
| Optional accessory | USB Micro B cable (offered on the page, not in the packing list) | [PP] |
| Warranty | 12 months | [PP] |
| Price | RM50.40 | [PP] |
| Dimensions | Board outline in the PCB file: **127.0 × 88.9 mm** overall (UNO-shaped controller section plus a perfboard section and a logo strip); weight not stated | [DT] |

Facts from the guide about the board [UM]:

| Item | Value | Src |
|---|---|---|
| PWM ("analog output") pins | "Only pins 3, 5, 6, 9, 10 and 11 (indicated with the ~ sign)" | [UM] |
| analogWrite range | 0 to 255 | [UM] |
| Analog input pins | "Only pins A0, A1, A2, A3, A4 and A5"; values 0 to 1023 | [UM] |
| Debug mode | Slide switch; on = built-in LEDs and piezo buzzer enabled | [UM] |
| USB cable | "Connect Maker UNO X to your PC with a micro USB cable" | [UM] |
| Breadboard | Supplied separately; "remove the adhesive backing and then attach it to the Maker UNO X board" | [UM] |
| Pin labels | Labelling stickers are peeled off and attached to the pin headers | [UM] |
| Reset button | Present (pressing it restarts the sketch) | [UM] |

### Design-file facts (schematic REV 1.0.0 and Eagle board) [DT]
| Item | Value | Src |
|---|---|---|
| Revision | REV 1.0.0, date "11/1/2019", sheet 1/1 | [DT] |
| Microcontroller | ATMEGA328P-AU (U1, TQFP-32); ADC6/ADC7 pins not connected; AREF has a 0.1 µF capacitor to GND | [DT] |
| Clock | Y1 16 MHz crystal (HC49 SMD) with 2 × 30 pF | [DT] |
| USB-serial | U2 CH340C (library MPN field "CH9340C"); runs from 5 V (V3 pin decoupled with 0.1 µF); DTR → 0.1 µF (C13) → RESET for auto-reset; 1 kΩ (R6, R7) between the chip and D0/D1 | [DT] |
| USB connector | CN1 micro-B, right-angle; ID pin unused | [DT] |
| 3.3 V regulator | U4 **RT9013-33GB** (SOT-23-5), part value "3.3V 500mA", fed from 5 V; 10 µF output capacitor | [DT] |
| 5 V bulk capacitor | C10 220 µF 16 V electrolytic | [DT] |
| VIN pin | Fed from +5V through D1 **15MQ040N** Schottky (40 V 3 A), anode on 5 V, cathode on VIN | [DT] |
| Power bank keep-alive | U3 NE555DT astable (R4 100 kΩ, R5 10 kΩ, C9 10 µF) switching Q1 MMBT2907A PNP into R11 5.1 Ω + R12 10 Ω to GND; PWRBANK LED DS5 (red) on the same switched node; no switch or jumper to disable it | [DT] |
| Debug switch | S3 SPDT slide switch "DEBUG" (silkscreen ON / OFF): common → DEBUG rail; one side +3V3, other side GND | [DT] |
| I/O LEDs | L2–L13 (DS6–DS17, blue): DEBUG rail → LED → 10 kΩ → BSS138 N-MOSFET to GND; gate on D2–D13 with a 3.3 MΩ pull-down | [DT] |
| Buzzer | LS1 (8530 package; silkscreen "PIEZO"): DEBUG rail → buzzer → BSS138 Q11 to GND; gate on D8 with 3.3 MΩ pull-down; 0.1 µF on the DEBUG rail | [DT] |
| TX / RX LEDs | TX (DS3, red): 5 V → 1 kΩ → LED → D1/TXD; RX (DS4, yellow): 5 V → 1 kΩ → LED → CH340C TXD (the line into D0). Not switched by Debug | [DT] |
| Power LEDs | L3V (DS1, green) on 3.3 V and L5V (DS2, green) on 5 V, 1 kΩ each | [DT] |
| RESET button | S1 to GND; RESET has a 10 kΩ pull-up to 5 V | [DT] |
| User button | S2 "BUTTON": D2 → 1 kΩ (R10) → button → GND; no pull-up on the board | [DT] |
| Headers | SMD female headers JP1 (8-way power), JP2 (6-way analog), JP3 (10-way), JP4 (8-way); JP5 2×3 male ICSP | [DT] |
| Perfboard | Right-hand section: 400 plated 1.0 mm holes (1.905 mm pads, 2.54 mm pitch) linked like a breadboard — 30 rows × two groups of 5 (a–e, f–j) and four 25-hole +/− rails; silkscreen numbers 1–30, letters a–j | [DT] |
| Outline and holes | Overall 127.0 × 88.9 mm; the UNO-shaped controller section spans about 62 × 69 mm (*measured from the outline*); four 3.0 mm holes in the controller section and two unplated M3 holes in the perfboard section; routed slots with rows of 0.8 mm holes separate the sections (whether they are meant to be snapped apart is not stated) | [DT] |
| Silkscreen | "MAKER UNO X", "Simplifying Digital Making", "www.cytron.io", "Cytron in collaboration with" chumbaka / ARUS / rero logos; labels USB5V, 3.3VREG, USB-UART CH340C, ATMEGA 328P, 16MHZ, PWRBANK, PIEZO, DEBUG, BUTTON, RESET, POWER, ANALOG IN, DIGITAL (PWM~) | [DT] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Packing list:** 1x Maker UNO X board, 1x mini breadboard, 1x Maker UNO pin sticker [PP].
- **LEDs:** 12x I/O indicator LEDs on D2–D13; the 2 LEDs on D0 and D1 are the UART TX/RX activity indicators [PP].
- **Spec list (unchanged from earlier read):** ATmega328P, 5 V, 20 digital I/O, 6 PWM, 6 analog inputs (10-bit), 1 UART / 1 SPI / 1 I2C, 32 KB flash, 2 KB SRAM, 1 KB EEPROM, 16 MHz, USB to UART chip "CH9340", button D2, piezo D8, powerbank-friendly, micro-USB [PP].
- **Driver notice:** the USB-serial driver does not support Windows 7 [PP].
- **Resources:** Arduino Learning Guide Rev 1.5 (IDE 2.x, Google Drive) and Rev 1.4 (IDE 1.8.x, static.cytron.io); CH34X drivers (Windows V3.5, Mac V1.5, Linux V1.5, Mar 2019) and the WCH factory link; Fritzing file (GitHub); Maker UNO projects [PP].
- Page images include a specifications image (`maker-uno-x-specs.png`) and a "what's included" photo — not read here (image only).

## Interfaces, terminals and pin mapping
| Function | Pin / part | Src |
|---|---|---|
| Programmable push button | D2, "internally connected to Pin 2"; use `pinMode(2, INPUT_PULLUP)`; reads LOW when pressed | [UM][PP] |
| Piezo buzzer | D8; active only with Debug mode on | [UM][PP] |
| I/O indicator LEDs | D2–D13 (12 LEDs); enabled by Debug mode | [PP][UM] |
| TX/RX LEDs | D0 & D1 UART activity; wired to the serial lines directly, not through Debug | [PP][DT] |
| PWM | D3, D5, D6, D9, D10, D11 | [UM] |
| Analog in | A0–A5 | [UM] |
| Power pins used in the guide | 3.3V and 5V pins (DC motor demo), GND | [UM] |
| ICSP (JP5, 2×3) | 1 MISO (D12), 2 5V, 3 SCK (D13), 4 MOSI (D11), 5 RST, 6 GND | [DT] |
| USB | Micro-B | [PP][UM] |

Header pinout from the schematic [DT] (UNO R3 naming):

| Header | Pins in order |
|---|---|
| JP1 power (8) | 1 not connected · 2 IOREF (tied to 5 V) · 3 RESET · 4 3.3V · 5 5V · 6 GND · 7 GND · 8 VIN (5 V through Schottky D1) |
| JP2 analog (6) | A0 · A1 · A2 · A3 · A4 · A5 |
| JP3 (10) | 1 SCL (A5) · 2 SDA (A4) · 3 AREF · 4 GND · 5 D13 · 6 D12 · 7 D11 · 8 D10 · 9 D9 · 10 D8 |
| JP4 (8) | D7 · D6 · D5 · D4 · D3 · D2 · D1(TX) · D0(RX) |

Header geometry in the board file [DT] (*measured*): the power/analog row and the digital row are 48.26 mm (1.9 in) apart; the gap between VIN and A0 is 5.08 mm (0.2 in); the gap between D7 and D8 is 3.81 mm (0.15 in); D0 and A5 sit at the same position along the board. Not checked against an Arduino UNO R3 reference drawing — see Needs verification.

Fritzing part note: header connectors defined in Cytron's Fritzing part (36 connectors) [GH]: D0/RX, D1/TX, D2, D3 PWM, D4, D5 PWM, D6 PWM, D7, D8, D9 PWM, D10 PWM/SS, D11 PWM/MOSI, D12/MISO, D13/SCK, A0–A3, A4/SDA, A5/SCL (A4/SDA and A5/SCL appear twice — a separate SDA/SCL pair), AREF, IOREF, RESET, 3V3, 5V, GND, and ICSP MISO / SCK / MOSI. **No Vin connector** is defined (the schematic does have VIN on JP1 pin 8 — see Conflicts). Silkscreen text in the Fritzing breadboard art includes "DEBUG", "PIEZO", "ON OFF", "BUTTON", "PWRBANK", "USB5V", "USB-UART", "CH340C", "3.3VREG", "16MHz", "ATMEGA 328P", "RX0", "TX0" [GH].

## Rules and gotchas (for code, wiring and tutorials)
- **Turn on Debug mode.** "Remember to turn on the 'Debug' mode to enable the built-in LEDs on Maker UNO X"; "Slide the switch on the board to turn on the 'Debug' mode" [UM]. With Debug off, tell readers the built-in LEDs and buzzer will not work.
- **Buzzer shares D8.** "You need to switch on the DEBUG mode to activate the piezo buzzer"; "If you want to connect Pin 8 to another I/O device, remember to switch off the DEBUG mode to deactivate the piezo buzzer" [UM]. The guide describes one Debug switch; the schematic confirms there is no separate mute switch — the only switches are DEBUG (S3), RESET (S1) and BUTTON (S2) [DT].
- **Button on D2 needs `INPUT_PULLUP`**; pressed = LOW. The schematic confirms why: D2 goes through 1 kΩ and the button to GND, with no pull-up resistor on the board [DT]. The switch is "occupied and cannot be connected to any other external components when it is in use" [UM].
- **LED 2 as input indicator:** with Debug on, "LED 2 will be turned off whenever the on-board switch is pressed" [UM].
- **How Debug works (schematic):** the Debug switch connects the LED/buzzer supply rail to 3.3 V (on) or GND (off). Each I/O pin only drives the gate of a BSS138 MOSFET that switches its LED (and, on D8, the buzzer as well) [DT]. So the LEDs never load the pins; with Debug off the LEDs and buzzer simply have no supply. *Inferred:* each of D2–D13 still sees a MOSFET gate and a 3.3 MΩ pull-down to GND with Debug off — negligible for normal digital use but it pulls a floating input LOW.
- **D8 drives both LED 8 and the buzzer** (two MOSFETs on the same pin) [DT]; with Debug on, any signal on D8 also sounds the buzzer — hence the guide's advice to switch Debug off when D8 is used for another device [UM].
- **TX/RX LEDs are always active** (wired to the serial lines, not to the Debug rail) [DT].
- **VIN is not a power input.** VIN (JP1 pin 8) is fed *from* the 5 V rail through a Schottky diode, so it gives out about 5 V minus the diode drop; a supply connected to VIN is blocked by the diode and will not power the board (*inferred from the schematic*). There is no DC jack and no on-board 5 V regulator [DT]. Do not tell readers to power Maker UNO X from VIN or a barrel jack.
- **The 5 V header pin is the USB 5 V rail** — CN1 VCC goes straight to +5V with no fuse, polarity diode or switch [DT].
- **Power bank keep-alive is always running.** The 555 load circuit has no enable switch; the red PWRBANK LED blinking is normal (*inferred* from the circuit: it lights during each load pulse) [DT].
- **PWM only on 3, 5, 6, 9, 10, 11; analog input only on A0–A5** [UM]. The ATmega328P's ADC6/ADC7 are not connected [DT].
- **Board to select:** "Arduino UNO" in Arduino IDE [PP]. The guide pages read do not name a board.
- **Windows 7 not supported:** "the USB to Serial driver for this product is not compatible with Windows 7. We recommend using a more recent version of Windows" [PP].
- Code in `setup()` runs once (e.g. a melody plays once until reset); `while(1)` never exits without the reset button [UM].
- Tone timing: delay 30 % longer than the note (250 ms note → 325 ms delay) [UM].
- The breadboard comes loose with adhesive backing; it is stuck on by the user [UM].
- Do not copy Maker UNO (`maker-uno.md`) buzzer-switch wording or its Maker Uno board-package advice into Maker UNO X content; the sources for Maker UNO X do not mention that board package.

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Power input | USB Micro B ("for power, program loading and USB communication") | [PP] |
| 5 V rail | USB VBUS connected directly to +5V (C4/C5 0.1 µF, C10 220 µF bulk); no fuse, polyfuse, polarity diode or ESD part on the schematic | [DT] |
| Operating voltage | 5V | [PP] |
| 3.3 V rail | RT9013-33GB LDO from 5 V, part value "3.3V 500mA"; feeds the 3.3V header pin, the L3V LED and the Debug rail | [DT] |
| Powerbank | "Powerbank-friendly"; "*Enable continuous supply from most powerbanks"; "to enable the portability of the projects" | [PP] |
| Power bank keep-alive load | NE555 astable switching an MMBT2907A PNP into 15.1 Ω (5.1 Ω + 10 Ω) with the PWRBANK LED; always on | [DT] |
| Keep-alive pulse (*calculated*) | Standard 555 timing with R4 100 kΩ, R5 10 kΩ, C9 10 µF: load on about 0.07 s every about 0.83 s; roughly 0.3 A while on (5 V ÷ 15.1 Ω, ignoring transistor drop), about 25–30 mA average — worked out here, not printed by Cytron | [DT] |
| VIN pin | Output only: +5V → 15MQ040N Schottky → VIN | [DT] |
| DC jack / external regulator | None | [DT] |
| 5V pin output current | Not stated (limited by the USB source; no fuse on the board) | [DT] |
| 3.3V pin output current | Not stated; regulator part value "3.3V 500mA" is shared with the Debug LEDs/buzzer and L3V LED | [DT] |
| Per-I/O-pin current | Not stated | — |
| USB input voltage range | Not stated | — |

- "Powerbank-friendly" is achieved by the keep-alive load circuit (schematic block "POWER BANK KEEP-ALIVE LOAD") [DT]; Cytron does not state its current or timing — the figures above are calculated.
- The guide drives the kit DC motor (recommended 3–6 V) briefly from the 3.3V and 5V pins to show speed vs voltage, and through a 2N2222 transistor from D5 in Project 14 [UM]. No current rating is given for those pins.

## Software support
- **Arduino IDE.** v1.5 guide is "updated to Arduino IDE 2.X"; v1.4 is "based on Arduino IDE 1.8.X" [PP]. Download from https://www.arduino.cc/en/main/software; v1.5 recommends "Windows 10 and newer, 64 bits" [UM]; v1.4 said "Windows Installer, for Windows XP and up" [UM-v1.4].
- **Board:** "Arduino UNO" [PP].
- **Driver (CH34X / CH341):** Product page links "CH34X drivers": Windows V3.5 Mar2019, Mac V1.5, Linux V1.5 (Drive links in Sources) [PP]. Guide links https://cdn.cytron.io/makeruno/CH341SER.EXE (Windows, then check Device Manager > Ports (COM & LPT) for the CH340 COM port) and https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP (Mac, then restart) [UM]. Mac troubleshooting PDF: https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf [UM].
- Mac port example: `/dev/cu.usbserial-220` (v1.5) [UM]; `/dev/cu.wchusbserial1410` (v1.4) [UM-v1.4].
- Code and libraries: "fully compatible with Arduino UNO R3 sample code and libraries" [PP]; the guide uses the built-in toneMelody example with `pitches.h` [UM].
- Fritzing part: https://github.com/CytronTechnologies/MAKER-UNO-X/raw/master/Fritzing/MakerUnoX.fzpz [PP][GH].
- MicroPython / CircuitPython / block coding: not stated.

## Compatibility and accessories
- Learning material: "Arduino Learning Guide for Beginners with Maker UNO X" (printed book is product BOK-MUNOX, `maker-uno-x-learning-guide.md`) [PP]. "Note: This book is written by Cytron Technologies and is not an official publication from Arduino" [PP].
- Maker UNO X Learning Box kit page is linked in the guide (not read) [UM].
- USB Micro B cable is sold separately as an accessory [PP].
- Shield compatibility (UNO R3 shields) is not stated by Cytron. The schematic uses the UNO R3 header set and pin order (IOREF, SDA/SCL beside AREF, ICSP 2×3) [DT], but physical fit has not been checked (header geometry under Interfaces); VIN does not accept power, so shields that feed the board through VIN will not power it (*inferred*).
- **Differences vs Maker UNO** (as sources state them): Maker UNO X adds the onboard perfboard and breadboard area [PP]; its built-in LEDs **and** buzzer are enabled by one Debug switch [UM], while the Maker UNO manual describes a buzzer-only slide switch (`maker-uno.md`); Maker UNO X lists 12 I/O LEDs D2–D13 plus TX/RX LEDs on D0/D1 [PP]. Maker UNO is described as the predecessor [PP].
- **Differences vs genuine Arduino UNO R3:** no source read lists them for Maker UNO X. What the sources do state: USB Micro B instead of the UNO's USB connector [PP]; a CH340-family USB-serial chip [UM][GH]; VIN pin present but fed from 5 V through a diode (output only) and no DC jack [DT]; IOREF tied to 5 V [DT]; MOSFET-buffered I/O LEDs and buzzer, power bank keep-alive load, button and prototyping area onboard [PP][DT].

## Common mistakes / troubleshooting
- Built-in LEDs or buzzer do nothing → Debug switch is off [UM].
- External device on D8 misbehaves → Debug is on, so the buzzer is still connected; switch Debug off [UM].
- Upload error → board not connected or wrong port (Tools > Port > COM_) [UM].
- No COM port → install the CH34X/CH341 driver; check Device Manager > Ports (COM & LPT) [UM][PP].
- Windows 7 PC → driver not compatible; use a newer Windows [PP].
- Button always reads HIGH → missing `INPUT_PULLUP` on D2 [UM].
- `analogWrite` has no fade on a pin → pin is not one of 3, 5, 6, 9, 10, 11 [UM].
- Motor doesn't spin but LED 5 pulses (Debug on) → check the motor circuit [UM].
- Red PWRBANK LED keeps blinking → normal; it is the power bank keep-alive load [DT].
- Board does not power up from VIN or an external supply on VIN → VIN is an output only; power through USB [DT].
- An input on D2–D13 reads LOW when nothing is connected → expected; each pin has a 3.3 MΩ pull-down via the Debug LED driver (*inferred*) [DT].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| USB-serial chip name | [PP] spec list: "USB to UART chip: CH9340" | [DT] schematic PDF, silkscreen and assembly diagram: "CH340C" (the Eagle library entry for U2 is named "CH9340C" with MPN "CH9340C", likely where the page's name comes from — *inferred*); [UM] driver CH341SER and port "CH340"; [PP] driver links "CH34X"; [GH] Fritzing "CH340C"; [3P] The Pi Hut "CH340" | [UM] and [DT] win: say "CH340C USB-serial chip (CH34X/CH341 driver)". Do not quote "CH9340" until a real board's chip marking is checked |
| VIN pin | [GH] Fritzing part: no Vin connector | [DT] schematic: VIN on JP1 pin 8, fed from 5 V through Schottky D1 | [DT] wins: a VIN pin exists, but it is an output only |
| Prototyping area | [PP]: "onboard perfboard prototyping area"; "donut board (perfboard) included onboard" | [DT]: the perfboard section is plated holes linked in a breadboard pattern (strips of 5 and +/− rails), not a plain donut grid | No contradiction in substance; describe it as "breadboard-pattern perfboard" |
| Breadboard size | [PP] features: "a half-size breadboard" | [PP] packing list: "1x mini breadboard" | Same source contradicts itself; the [DT] perfboard silkscreen is a 30-row layout but does not size the loose breadboard. Say "breadboard (included)" until confirmed |
| Arduino IDE Windows recommendation | [UM] v1.5 (Feb 2023, newer): "Windows 10 and newer, 64 bits" | [UM-v1.4] (Feb 2020): "Windows XP and up" | v1.5 is newer and matches [PP] Windows 7 driver notice; use v1.5 |
| Mac port name | [UM] v1.5: `/dev/cu.usbserial-220` | [UM-v1.4]: `/dev/cu.wchusbserial1410` | Both are the author's examples; port names vary by Mac and driver |
| Guide IDE version | [PP] v1.5 "updated to Arduino IDE 2.X" | [PP] v1.4 "based on Arduino IDE 1.8.X" | Use v1.5 |

## Needs verification
- Chip marking on a production board (CH340C per the schematic/silkscreen vs "CH9340" on the page and in the Eagle library MPN).
- UNO R3 shield physical fit: compare the measured header geometry (rows 48.26 mm apart, D7–D8 gap 3.81 mm, D0 level with A5) and the 3.0 mm hole positions with an official Arduino UNO R3 drawing (not read here); Cytron does not claim shield compatibility.
- Current limits Cytron would quote for the 5V and 3.3V pins (no fuse; regulator part value "3.3V 500mA"), per-pin current, USB input range.
- Keep-alive load: Cytron's own current/timing figures (only calculated here) and whether it works with every power bank ("most powerbanks" [PP]).
- What the "20 digital I/O pins" count includes (*likely* D0–D13 plus A0–A5 — inferred; the page does not explain).
- Breadboard size (half-size vs mini) and where the loose breadboard is meant to be stuck (the perfboard section already carries a breadboard-pattern hole grid).
- Whether the perfboard section and the logo strip are meant to be snapped off (slots and 0.8 mm hole rows in the board file; no source says).
- Weight, PCB colour; the production revision (schematic REV 1.0.0, "11/1/2019") vs boards sold today.
- [3P] The Pi Hut marks the product "Discontinued" on its own store; Cytron's page shows it in stock — no effect on Cytron status.
- Read the product page images `maker-uno-x-specs.png` and `maker-uno-x-whats-included.jpeg` (dimensions, breadboard size) when the browser can render images.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [K-Type Thermocouple With Maker UnoX And Blynk](https://my.cytron.io/tutorial/k-type-thermocouple-with-maker-uno-x-and-blynk) — Tutorial, Intermediate, 2021 [PP: tutorial]

## Sources
- [UM] Arduino Learning Guide For Beginners — MAKER UNO X, v1.5, Feb 2023 (PDF, Drive): (Cytron document — link not public) (read 2026-10-19 as text, cover to p. ~80)
- [UM-v1.4] same title, v1.4, Feb 2020 (Drive): (Cytron document — link not public) (read to p. ~80); public copy https://static.cytron.io/download/MAKER-UNO-X/Arduino-Learning-Guide-for-Beginners-Using-Maker-UNO-X-EN-v1.4.pdf (not reachable from here)
- [PP] https://my.cytron.io/p-maker-uno-x-simplifying-arduino-for-classrooms (coordinator browser capture 2026-10-19, local file `unox-pp.md`)
- [PP] CH34X drivers: Windows V3.5 https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view · Mac V1.5 https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view · Linux V1.5 https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view (not opened)
- [UM] Guide driver links: https://cdn.cytron.io/makeruno/CH341SER.EXE · https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP · https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf
- [DT] Cytron design files, https://github.com/CytronTechnologies/MAKER-UNO-X → `Schematic and PCB/`: `Schematic - PDF/MAKER-UNO-X.pdf` ("MAKER UNO X", product code MAKER-UNO-X, REV 1.0.0, dated "11/1/2019", 1 sheet), `Assembly Diagrams/Value - MAKER-UNO-X.pdf`, `Assembly Diagrams/Name - MAKER-UNO-X.pdf`, `Project/MAKER-UNO-X.sch` and `.brd` (Eagle 7.7), Gerber/drill files — read in full 2026-10-21 (supplied by the Cytron marketing team)
- [GH] https://github.com/CytronTechnologies/MAKER-UNO-X (no README) · Fritzing part https://raw.githubusercontent.com/CytronTechnologies/MAKER-UNO-X/master/Fritzing/MakerUnoX.fzpz (downloaded and read 2026-10-19)
- [3P] (cross-check only) https://thepihut.com/products/maker-uno-x
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
