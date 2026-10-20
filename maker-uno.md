# Maker UNO — Verified Reference

| | |
|---|---|
| Product code | `MAKER-UNO` (user manual cover "MAKER-UNO"; packing list "Maker Uno (Code: MAKER-UNO)" [UM]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (description, packing list, resources and attachments). Status, current warranty, price, package and the original User's Manual link are now Cytron-stated |
| Primary source | MAKER-UNO **User's Manual, Rev 1.0, Dec 2017** (Cytron Technologies Sdn Bhd), section 6.5 "Board Package Updated 21 March 2018" [UM]. No separate datasheet exists in any source found; the public mirror is filed as "datasheet" on RobotShop's CDN but its title page is the User's Manual |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the User's Manual above, read from the public RobotShop CDN mirror (PDF text; the dimension drawing and board-layout picture are images and were not readable). Text extraction drops "ti" ligatures ("Opboot" = Optiboot, "buon" = button, "compable" = compatible). [PP] = Cytron product page at www.cytron.com.my (Cytron's own site). [GH] = CytronTechnologies/MakerUno repo (`boards.txt`) and the board-package index `package_cytron_makeruno_index.json`. [VEN] = Microchip ATmega328P / Arduino facts. No [DS] or [DT] source exists for this product.

## What it is
An Arduino UNO-compatible board built on the SMD ATmega328P (the same microcontroller as the Arduino UNO) with the Optiboot (UNO) bootloader [UM]. It is powered and programmed only through a USB Micro-B socket via a CH340 USB-to-serial chip, and adds an LED on the digital pins, a piezo buzzer on pin 8 and a programmable push button on pin 2 [UM]. It has no DC jack and no Vin pin [PP][UM]. Cytron positions it for classroom use [PP].

## Specifications
User's Manual section 3 "Product Specifications" (absolute maximum ratings) — every row:

| Item | Value | Src |
|---|---|---|
| Input Voltage via USB connector | Min 4.8 V, Max 5.2 V | [UM] |
| DC Current for 3.3V Pin (Max Continuous) | 500 mA max | [UM] |
| DC Current per I/O Pin (Max) | 20 mA max | [UM] |
| Dimension | Drawing only; no values in the text | [UM] |

User's Manual section 1 feature list — every item:

| Item | Value | Src |
|---|---|---|
| Microcontroller | SMD ATmega328P ("the same microcontroller on Arduino UNO") with Optiboot (UNO) bootloader | [UM] |
| USB programming | "facilitated by the CH340"; board layout names the USB-serial converter **CH340G** | [UM] |
| Input voltage | USB 5V, from computer, power bank or standard USB adapter | [UM] |
| 3.3V regulator | 500mA (maximum) 3.3V voltage regulator; regulates 5V USB to 3.3V, connected to the 3.3V pin | [UM] |
| I/O levels | "0-5V outputs with 3.3V compatible inputs" | [UM] |
| Digital I/O | 14 Digital I/O Pins (6 PWM outputs) | [UM] |
| Analog inputs | 6 | [UM] |
| ISP | ISP 6-pin header (2x3) | [UM] |
| Flash | 32k Flash Memory | [UM] |
| Clock | 16MHz | [UM] |
| Shield compatibility | "R3 Shield Compatible" (except shields that need Vin — see Rules) | [UM] |
| LEDs | "LED array for 5V, 3.3V, TX, RX and all digital pins" | [UM] |
| Push button | On-board programmable push button (pin 2, need to configure as INPUT_PULLUP) | [UM] |
| Buzzer | On-board piezo buzzer (pin 8) | [UM] |
| USB connector | USB Micro-B socket | [UM] |
| PCB colour | Purple | [UM] |
| Packing list | 1 × Maker Uno (Code: MAKER-UNO) | [UM] |
| Pin label stickers | "we include a set of these label stickers for pin headers in each of the Maker UNO" | [PP] |
| Warranty | 6 months, manufacturing defects only; misuse and two-way freight not covered (product page says 12 months — see Conflicts) | [UM] |
| SRAM / EEPROM | Not stated by Cytron. ATmega328P: 2 KB SRAM, 1 KB EEPROM | [VEN] |
| Upload limits (board package) | `maximum_size=32256` bytes, `maximum_data_size=2048` bytes, `upload.speed=115200`, bootloader `optiboot_atmega328.hex`, `f_cpu=16000000L` | [GH] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Description: Kickstarter-funded 1825% (17 Apr 2018); built-in 12 LEDs, 1 buzzer, 1 button [PP].
- **Packing:** 1x Maker UNO, 1x GPIO labeling sticker [PP].
- **Warranty:** 12 months on the current product page [PP] (manual Rev 1.0 says 6 months — see *Conflicts*).
- **Resources / attachments:** default program (GitHub MakerUno_DefaultSketch); Arduino IDE; Atmel Studio and Chromebook tutorials; **Maker UNO User's Manual (original Cytron Google Doc `1gJIF-tssdoxk8qAq2aHBmPwVHulFL_lSElOhA17Du64`)**; Edu Kit Getting Started Module; schematic (cdn.cytron.io/makeruno/MAKER-UNO.pdf); Fritzing; 3D IGS/STEP; PCB Eagle file; CH341 drivers for Windows 10 and macOS; teacher and student modules (EN/BM) [PP].

## Interfaces, terminals and pin mapping
Board layout items (User's Manual section 4) [UM]:

| Label | Part | Function |
|---|---|---|
| A / B | Piezo buzzer + slide switch | Buzzer on **pin 8** through the slide switch. "To use piezo buzzer, slide the switch on and program the buzzer. To use pin 8 for other purpose, slide the switch off." |
| C | 3.3V regulator | 5V USB to 3.3V, 500 mA max, to the 3.3V pin |
| D | USB-serial LED | Shows upload / Serial Monitor activity |
| E | USB Micro-B connector | Main power, program upload, debugging |
| F | USB-serial converter | CH340G |
| G | Reset button | — |
| H | Programmable button | "connected to pin 2 and GND"; configure as `INPUT_PULLUP` |
| I | Arduino UNO R3-standard female headers | **No Vin pin.** "The SDA, SCL and IOREF pins which being broken out on UNO R3 are on MAKER-UNO too." |
| J | Main microcontroller | ATmega328P |
| K | MOSFET series | "These series of MOSFET is a 'secret' why you can control LED or make it as indicator for input, even for pull-up input." |
| L | LEDs | "Every digital IO is equipped with LED, where you can control it or make it as indicator for input." |
| M | ISP header | 2x3, "standard for loading program via AVR programmer. Some uses it for SPI communication too." |

Pin summary for tutorials:

| Function | Pin | Src |
|---|---|---|
| Standard LED (`LED_BUILTIN`) | D13 ("the standard LED on pin 13") | [UM] |
| Programmable LEDs | UM: "a programmable LED on every digital pin, from pin D0 to D13"; product page: "12x LEDs" (see Conflicts) | [UM][PP] |
| Push button | D2 to GND, `INPUT_PULLUP` → reads LOW when pressed | [UM] |
| Piezo buzzer | D8, only when the slide switch is on | [UM] |
| Serial (USB) | D0 RX / D1 TX via CH340G (standard UNO mapping) | [UM][VEN] |
| PWM | 6 pins (UM does not list them; on ATmega328P UNO mapping: D3, D5, D6, D9, D10, D11) | [UM][VEN] |
| I2C | SDA, SCL header pins as on UNO R3 (A4/A5 on the ATmega328P UNO mapping) | [UM][VEN] |
| Analog | 6 inputs (A0–A5) | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **Power only from USB (4.8–5.2 V).** There is no DC jack [PP] and no Vin pin [UM]. Do not tell readers to plug a 9 V/12 V adapter into the board.
- **Shields that need Vin are not compatible** — "Since Maker-UNO doesn't have Vin, any Arduino shield that require Vin is not compatible"; check the shield schematic for a Vin connection [UM].
- **Buzzer shares D8.** Slide the buzzer switch off to use D8 for something else; slide it on to hear `tone(8, …)` [UM].
- **Button on D2 needs `pinMode(2, INPUT_PULLUP)`**; it connects D2 to GND, so pressed = LOW [UM]. Do not wire another device to D2 while the button is used.
- **Floating-input LED glow.** With board "Arduino/Genuino Uno", all I/O pins default to INPUT; a Blink upload makes LED 13 blink and "other LEDs light up randomly" because floating inputs (0–5 V) can light the pin LEDs. This is normal, not a fault [UM].
- **Board selection — Cytron's advice is "Arduino/Genuino Uno"** "for safety purpose" [UM]. The optional Cytron "Maker Uno" board package sets all digital pins to OUTPUT by default so only pin 13 blinks [UM]; it was made to avoid the confusion above. Cytron does not give the safety reason in writing — do not invent one.
- In current Arduino IDEs the board formerly called "Arduino/Genuino Uno" is listed as **"Arduino Uno"** [VEN]. The Maker UNO board package uses the same upload settings as UNO (Optiboot, 115200 baud) [GH].
- **3.3V pin limit is 500 mA**; each I/O pin 20 mA max [UM]. No 5V-pin current limit is stated — do not quote one.
- Inputs accept 3.3V logic ("3.3V compatible inputs"); outputs are 0–5 V [UM]. So a 5 V HIGH reaches any module wired to an output; check a 3.3V-only module's input tolerance first (general practice, not a Cytron statement).
- **Use one power source at a time** — "It is advisable to have 1 power source only at 1 time" (USB, power bank or Cytron LiPo Power Shield) [UM].
- Pin LEDs are driven through MOSFETs, and show input state "even for pull-up input" [UM]. How a given state appears (lit = HIGH) is not stated for Maker UNO — see Needs verification.

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Main power | USB Micro-B, 5 V ("USB 5V, from computer, power bank or standard USB adapter") | [UM] |
| USB input range | 4.8 – 5.2 V | [UM] |
| Portable power | "power bank or Cytron LiPo Power Shield" | [UM] |
| Power sources at once | "advisable to have 1 power source only at 1 time" | [UM] |
| DC jack | Removed ("most of the boards used in classes are powered using USB") | [PP] |
| Vin pin | None | [UM] |
| 3.3V output | 500 mA max continuous (on-board 3.3V regulator) | [UM] |
| 5V output | **Not stated** | — |
| I/O pin current | 20 mA max per pin | [UM] |
| Reverse-polarity / over-current protection | Not stated | — |

## Software support
- **Arduino IDE.** Cytron's first example: Blink with board "Arduino/Genuino Uno" and the right COM port [UM].
- **CH340 driver** required on Windows/macOS: the UM says download it from the Maker UNO product page Attachment tab; after install the port shows under "Ports (COM & LPT)" as e.g. "USB-SERIAL CH340 (COM3)" [UM]. Cytron's CDN driver files (linked in Cytron's Maker UNO X learning guide, same CH340 family): `https://cdn.cytron.io/makeruno/CH341SER.EXE` (Windows), `https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP` (macOS).
- **Optional Cytron board package "Maker Uno":** File > Preferences > Additional Boards Manager URLs → `https://cytrontechnologies.github.io/package_cytron_makeruno_index.json`, then Boards Manager > "Maker Uno" by Cytron Technologies (internet needed) [UM]. Latest version in the index: **1.1.0-rc2**; architecture avr; board name "Maker UNO" in `boards.txt` [GH].
- MicroPython / CircuitPython / block coding: not stated for Maker UNO.

## Compatibility and accessories
- Arduino UNO R3 shields: compatible ("R3 Shield Compatible") **except** shields needing Vin [UM].
- SDA, SCL and IOREF are broken out as on UNO R3 [UM] — I2C LCD and MPU6050 tutorials can use the SDA/SCL header pins.
- Cytron LiPo Power Shield: named by Cytron for portable power [UM].
- Differences from a genuine Arduino UNO R3 [UM][PP]: CH340 USB-serial instead of ATmega16U2 ("to bring down the cost"); USB Micro-B instead of USB-B; no DC jack; no Vin pin; SMD ATmega328P; LEDs on the digital pins; buzzer on D8 with switch; button on D2; purple PCB.
- Maker UNO X and Maker UNO Plus are **separate products** with their own documents; do not copy their features (e.g. breadboard, prototyping area, LED/buzzer switch behaviour) into Maker UNO content.

## Common mistakes / troubleshooting
- Random LEDs glowing after uploading Blink → floating inputs; normal [UM]. Cytron's fix is the Maker Uno board package (all digital pins OUTPUT by default) [UM]; setting unused pins to OUTPUT in the sketch has the same effect (general Arduino practice, not stated by Cytron).
- No COM port → install the CH340 driver; check Device Manager > Ports (COM & LPT) for "USB-SERIAL CH340" [UM].
- Buzzer silent → buzzer slide switch is off [UM].
- External device on D8 behaves oddly / clicks → buzzer switch is on [UM].
- Button reads always HIGH/random → missing `INPUT_PULLUP` on D2 [UM].
- Shield not powered → it needs Vin, which Maker UNO lacks [UM].
- Do not describe the board as having a DC jack, 7–12 V input or a Vin pin.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Number of programmable LEDs | [UM] "a programmable LED on every digital pin, from pin D0 to D13"; "LED array for 5V, 3.3V, TX, RX and all digital pins" | [PP] "We put in 12x LEDs" | [UM] wins in text ("an LED on every digital pin"). 12 likely = D2–D13 with D0/D1 covered by TX/RX LEDs, but no source says so — see Needs verification |
| Warranty | [UM] Rev 1.0 (Dec 2017): "valid for 6 months" | [PP] (live 2026-10-16): "Warranty Period: 12 months" | [UM] wins under the rule; the product page is newer and is Cytron's current sales term — confirm with Cytron before quoting |
| USB-serial chip name | [UM] board layout: "CH340G" | [UM] features and [PP]: "CH340" | Same family; say "CH340G (CH340 driver)" |

## Needs verification
- Whether D0 and D1 have their own programmable LEDs or only the TX/RX LEDs (12 vs 14 LEDs — see Conflicts).
- LED polarity for inputs: is a pin LED lit when the input is HIGH (so the D2 button LED goes off when pressed)? Not stated for Maker UNO.
- 5V pin maximum output current; whether USB input has a fuse or polarity/over-current protection.
- Board dimensions, weight and mounting holes (UM drawing not readable as text).
- Whether the power header has 5V, 3.3V, GND, RESET in the standard UNO order (implied by "Arduino UNO R3-standard female headers", not listed).
- Price history: only the current RM37.80 is Cytron-stated.

## Sources
- [UM] MAKER-UNO User's Manual, Rev 1.0, Dec 2017, Cytron Technologies Sdn Bhd — public mirror: https://cdn.robotshop.com/media/c/cyt/rb-cyt-250/pdf/cytron-maker-uno-microcontroller-datasheet1.pdf (public; read 2026-10-16 as text)
- [PP] https://www.cytron.com.my/p-maker-uno-simplifying-arduino-for-education (read 2026-10-16)
- [GH] https://raw.githubusercontent.com/CytronTechnologies/MakerUno/master/boards.txt · https://raw.githubusercontent.com/CytronTechnologies/cytrontechnologies.github.io/master/package_cytron_makeruno_index.json · https://github.com/CytronTechnologies/MakerUno
- [3P] (cross-check only) https://www.notebookcheck.com/Maker-Uno-Einplatinenrechner-mit-erleichterter-Fehlersuche.293572.0.html · https://www.manualslib.com/manual/2040269/Cytron-Technologies-Maker-Uno.html (copy of the UM, not opened)
