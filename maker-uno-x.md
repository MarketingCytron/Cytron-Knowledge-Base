# Maker UNO X for Classrooms (Arduino Compatible) — Verified Reference

| | |
|---|---|
| Product code | `MAKER-UNO-X` [PP] |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). D0/D1 LEDs and the packing list are confirmed; the chip name (CH9340 vs CH340) and dimensions (image only) stay open, so it stays Medium |
| Primary source | No Cytron datasheet exists for this board (none found on Drive or GitHub). Main source: Cytron guide book **"Arduino Learning Guide For Beginners — MAKER UNO X", v1.5, February 2023**, published by Cytron Technologies (Drive PDF `Arduino Learning Guide for Beginners Using Maker UNO X R15 Feb23.pdf`) [UM], plus the my.cytron.io product page [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the v1.5 guide (text extraction; read from the cover to Lesson 6 Project 14, p. ~80; Projects 15–17 were cut off by the reader; drawings are images and were not readable). [UM-v1.4] = the v1.4 edition (February 2020), read to the same point, used only for differences. [PP] = my.cytron.io page "Maker UNO X for Classrooms (Arduino Compatible)", captured by the coordinator in a browser on 2026-10-19. [GH] = github.com/CytronTechnologies/MAKER-UNO-X: the repo shows only two folders, `Fritzing/` and `Schematic and PCB/`, and no README; the schematic folder could not be listed or downloaded here, so [GH] facts come only from the Fritzing part `Fritzing/MakerUnoX.fzpz` (part title "Maker UNO X", author SC Lim, dated Fri Jan 17 2020, family "Maker UNO"). The guide book itself is a separate KB product (`maker-uno-x-learning-guide.md`, BOK-MUNOX); the older board is `maker-uno.md`.

## What it is
- An Arduino UNO-compatible board built on the ATmega328P, aimed at educators and classrooms: "code right away", the board lights up and plays a melody with a button press, no soldering [PP].
- Built in: an LED on every digital pin (12x LEDs D2–D13 plus TX/RX LEDs on D0/D1), a piezo buzzer on D8, a programmable push button on D2, and an onboard perfboard prototyping area plus a breadboard [PP]. A "Debug" mode slide switch enables the built-in LEDs and the buzzer [UM].
- Powered, programmed and connected over USB Micro-B; "Powerbank-friendly" [PP].
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
| USB to UART chip | "CH9340" as written on the page (see Conflicts; the guide's driver is CH341SER and the port shows as CH340) | [PP] |
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
| Dimensions, weight | Not stated | — |

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
| TX/RX LEDs | D0 & D1 UART activity | [PP] |
| PWM | D3, D5, D6, D9, D10, D11 | [UM] |
| Analog in | A0–A5 | [UM] |
| Power pins used in the guide | 3.3V and 5V pins (DC motor demo), GND | [UM] |
| USB | Micro-B | [PP][UM] |

Header connectors defined in Cytron's Fritzing part (36 connectors) [GH]: D0/RX, D1/TX, D2, D3 PWM, D4, D5 PWM, D6 PWM, D7, D8, D9 PWM, D10 PWM/SS, D11 PWM/MOSI, D12/MISO, D13/SCK, A0–A3, A4/SDA, A5/SCL (A4/SDA and A5/SCL appear twice — a separate SDA/SCL pair), AREF, IOREF, RESET, 3V3, 5V, GND, and ICSP MISO / SCK / MOSI. **No Vin connector** is defined. Silkscreen text in the Fritzing breadboard art includes "DEBUG", "PIEZO", "ON OFF", "BUTTON", "PWRBANK", "USB5V", "USB-UART", "CH340C", "3.3VREG", "16MHz", "ATMEGA 328P", "RX0", "TX0" [GH].

## Rules and gotchas (for code, wiring and tutorials)
- **Turn on Debug mode.** "Remember to turn on the 'Debug' mode to enable the built-in LEDs on Maker UNO X"; "Slide the switch on the board to turn on the 'Debug' mode" [UM]. With Debug off, tell readers the built-in LEDs and buzzer will not work.
- **Buzzer shares D8.** "You need to switch on the DEBUG mode to activate the piezo buzzer"; "If you want to connect Pin 8 to another I/O device, remember to switch off the DEBUG mode to deactivate the piezo buzzer" [UM]. The guide describes one Debug switch; it does not describe a separate mute switch.
- **Button on D2 needs `INPUT_PULLUP`**; pressed = LOW. The switch is "occupied and cannot be connected to any other external components when it is in use" [UM].
- **LED 2 as input indicator:** with Debug on, "LED 2 will be turned off whenever the on-board switch is pressed" [UM].
- **PWM only on 3, 5, 6, 9, 10, 11; analog input only on A0–A5** [UM].
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
| Operating voltage | 5V | [PP] |
| Powerbank | "Powerbank-friendly"; "*Enable continuous supply from most powerbanks"; "to enable the portability of the projects" | [PP] |
| Other power inputs | None named by any source; the Fritzing part has no Vin connector | [PP][GH] |
| 5V pin output current | Not stated | — |
| 3.3V pin output current | Not stated | — |
| Per-I/O-pin current | Not stated | — |
| USB input voltage range | Not stated | — |
| Protection (fuse, polarity) | Not stated | — |

- "Powerbank-friendly" means, in Cytron's words, continuous supply from most powerbanks; the page does not say how it is achieved (see Needs verification).
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
- Shield compatibility (UNO R3 shields) is not stated for Maker UNO X.
- **Differences vs Maker UNO** (as sources state them): Maker UNO X adds the onboard perfboard and breadboard area [PP]; its built-in LEDs **and** buzzer are enabled by one Debug switch [UM], while the Maker UNO manual describes a buzzer-only slide switch (`maker-uno.md`); Maker UNO X lists 12 I/O LEDs D2–D13 plus TX/RX LEDs on D0/D1 [PP]. Maker UNO is described as the predecessor [PP].
- **Differences vs genuine Arduino UNO R3:** no source read lists them for Maker UNO X. What the sources do state: USB Micro B instead of the UNO's USB connector [PP]; a CH340-family USB-serial chip [UM][GH]; no Vin connector in the Fritzing part [GH]; LEDs, buzzer, button and prototyping area onboard [PP].

## Common mistakes / troubleshooting
- Built-in LEDs or buzzer do nothing → Debug switch is off [UM].
- External device on D8 misbehaves → Debug is on, so the buzzer is still connected; switch Debug off [UM].
- Upload error → board not connected or wrong port (Tools > Port > COM_) [UM].
- No COM port → install the CH34X/CH341 driver; check Device Manager > Ports (COM & LPT) [UM][PP].
- Windows 7 PC → driver not compatible; use a newer Windows [PP].
- Button always reads HIGH → missing `INPUT_PULLUP` on D2 [UM].
- `analogWrite` has no fade on a pin → pin is not one of 3, 5, 6, 9, 10, 11 [UM].
- Motor doesn't spin but LED 5 pulses (Debug on) → check the motor circuit [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| USB-serial chip name | [PP] spec list: "USB to UART chip: CH9340" | [PP] driver links "CH34X"; [UM] driver CH341SER and port "CH340"; [GH] Fritzing silkscreen "CH340C"; [3P] The Pi Hut "CH340" | [UM] wins: say "CH340-family USB-serial chip (CH34X/CH341 driver)". "CH9340" is unconfirmed — do not quote it |
| Breadboard size | [PP] features: "a half-size breadboard" | [PP] packing list: "1x mini breadboard" | Same source contradicts itself; say "breadboard (included)" until confirmed |
| Arduino IDE Windows recommendation | [UM] v1.5 (Feb 2023, newer): "Windows 10 and newer, 64 bits" | [UM-v1.4] (Feb 2020): "Windows XP and up" | v1.5 is newer and matches [PP] Windows 7 driver notice; use v1.5 |
| Mac port name | [UM] v1.5: `/dev/cu.usbserial-220` | [UM-v1.4]: `/dev/cu.wchusbserial1410` | Both are the author's examples; port names vary by Mac and driver |
| Guide IDE version | [PP] v1.5 "updated to Arduino IDE 2.X" | [PP] v1.4 "based on Arduino IDE 1.8.X" | Use v1.5 |

## Needs verification
- Real USB-serial part number: "CH9340" [PP] vs "CH340C" (Fritzing art) — no schematic read.
- Whether there is any switch besides Debug (e.g. a separate mute switch); what the "PWRBANK" silkscreen label in the Fritzing art marks (switch, jumper or circuit) and how powerbank-friendliness works.
- 5V and 3.3V pin current limits, per-pin current, USB input range, protection.
- What the "20 digital I/O pins" count includes (not explained by the page).
- Breadboard size (half-size vs mini) and whether the perfboard is a soldering area on the PCB.
- UNO R3 shield compatibility; presence of a DC jack (none mentioned; Fritzing part has no Vin).
- Dimensions, weight, PCB colour, mounting holes.
- Guide Projects 15–17 (pins and parts) — not read.
- Schematic files in the GitHub `Schematic and PCB/` folder — not listed or read.
- [3P] The Pi Hut marks the product "Discontinued" on its own store; Cytron's page shows it in stock — no effect on Cytron status.
- Read the product page images `maker-uno-x-specs.png` and `maker-uno-x-whats-included.jpeg` (dimensions, breadboard size) when the browser can render images.

## Sources
- [UM] Arduino Learning Guide For Beginners — MAKER UNO X, v1.5, Feb 2023 (PDF, Drive): (Cytron document — link not public) (read 2026-10-19 as text, cover to p. ~80)
- [UM-v1.4] same title, v1.4, Feb 2020 (Drive): (Cytron document — link not public) (read to p. ~80); public copy https://static.cytron.io/download/MAKER-UNO-X/Arduino-Learning-Guide-for-Beginners-Using-Maker-UNO-X-EN-v1.4.pdf (not reachable from here)
- [PP] https://my.cytron.io/p-maker-uno-x-simplifying-arduino-for-classrooms (coordinator browser capture 2026-10-19, local file `unox-pp.md`)
- [PP] CH34X drivers: Windows V3.5 https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view · Mac V1.5 https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view · Linux V1.5 https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view (not opened)
- [UM] Guide driver links: https://cdn.cytron.io/makeruno/CH341SER.EXE · https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP · https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf
- [GH] https://github.com/CytronTechnologies/MAKER-UNO-X (folder list only) · Fritzing part https://raw.githubusercontent.com/CytronTechnologies/MAKER-UNO-X/master/Fritzing/MakerUnoX.fzpz (downloaded and read 2026-10-19)
- [3P] (cross-check only) https://thepihut.com/products/maker-uno-x
