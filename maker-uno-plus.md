# Maker UNO Plus for Education (Arduino Compatible) — Verified Reference

| | |
|---|---|
| Product code | `MAKER-UNO-PLUS` (user manual cover "MAKER-UNO-PLUS"; packing list "Maker Uno Plus (Code: MAKER-UNO-PLUS)" [UM]; product-page image paths [PP]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 3): live my.cytron.io product page read (description, features, packing list, resources). Product page confirms FT231X, 12 LEDs (pins 2–13), 3.3 V at 500 mA, packing list with USB cable and pin sticker, and 12-month warranty |
| Primary source | **Maker Uno Plus (MAKER-UNO-PLUS) User's Manual, Rev 1.0, Oct 2018** (Cytron Technologies Sdn Bhd), public Google Doc linked from the product page (file last modified 2018-11-02) [UM]. No separate datasheet exists in any source found |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the linked public User's Manual above, read as text through Google Drive; the dimension drawing, board-layout picture, schematic and gallery are images and were not readable. The same text is mirrored on RobotShop's CDN.  = a second Drive copy of the same User's Manual (also labelled Rev 1.0 Oct 2018, last modified 2022-10-13, not linked from the product page — internal). [PP: LG] in this file = Cytron "Arduino Learning Guide for Beginners" (Maker UNO+), v1.3, Dec 2018, linked from the product page — a learning guide, used for cross-check only, never as the spec source. [PP] = my.cytron.io product page as read by the coordinator on 2026-10-16 (price, stock, warranty). [VEN] = Arduino facts.

## What it is
An Arduino UNO R3-compatible board for students, built on the SMD ATmega328P with the Optiboot (UNO) bootloader, powered and programmed through a USB Micro-B socket via an FT231X (FTDI) USB-to-serial chip [UM]. It adds programmable LEDs on the digital pins, a piezo buzzer on pin 8 with a slide switch and a programmable push button on pin 2 [UM]. It has no DC jack, no 5V linear regulator and no Vin pin [UM]. Purple PCB [UM]. Cytron says the board lets students "learn digital input, output, PWM (piezo buzzer and LED brightness) with just the Maker-UNO board" [UM].
Positioning (marketing, not spec): product page name "Maker UNO Plus: Simplifying Arduino for Education" [PP]; "designed and developed specially for students to learn coding and microcontroller"; named Maker UNO Plus "to encourage everyone to be a maker"; a redesign of CT-UNO made with the ARUS and rero teams, "more affordable, and more beginner friendly" [UM].

## Specifications
User's Manual section 3 "Absolute Maximum Rating of Maker Uno Plus" — every row:

| Item | Value | Src |
|---|---|---|
| Input Voltage via USB connector | Min 4.8 V, Max 5.2 V | [UM] |
| DC Current for 3.3V Pin (Max Continuous) | Max 500 mA | [UM] |
| DC Current per I/O Pin (Max) | Max 20 mA | [UM] |
| Dimension | Drawing only; no values in the text | [UM] |

User's Manual section 1 feature list and "Maker Uno Plus Comparison Table" (Maker UNO Plus column):

| Item | Value | Src |
|---|---|---|
| Microcontroller | SMD ATmega328P ("the same microcontroller on Arduino UNO") with Optiboot (UNO) bootloader | [UM] |
| USB programming | "USB Programming facilitated by the FT231X"; comparison table "USB to Serial Chip: FT231X"; board layout F "USB-SERIAL IC CONVERTER (FT231X)" | [UM] |
| Operating voltage | 5V | [UM] |
| Input voltage | "USB 5V, from computer, power bank or standard USB adapter"; table: recommended and limit "5V (USB only)" | [UM] |
| DC current for 5V | "USB source" | [UM] |
| 3.3V regulator | 500mA (maximum); regulates 5V USB to 3.3V, connected to the 3.3V pin | [UM] |
| I/O levels | "0-5V outputs with 3.3V compatible inputs" | [UM] |
| Digital I/O | Features: 14 Digital I/O Pins (6 PWM outputs). Comparison table: "Digital IO Pins (PWM) 20 (6)" (same figure given for Arduino Uno) | [UM] |
| Analog inputs | 6 | [UM] |
| Analog, UART, SPI, I2C | 6, 1, 1, 1 | [UM] |
| External interrupts | 2 | [UM] |
| Flash, SRAM, EEPROM | 32KB, 2KB, 1KB | [UM] |
| Clock | 16MHz | [UM] |
| ISP | ISP 6-pin header (2x3) | [UM] |
| Shield compatibility | "R3 Shield Compatible" (except shields that need Vin) | [UM] |
| LEDs | "LED array for 5V, 3.3V, TX, RX and all digital pins"; programmable indicator LED at pins 2–13 (see Conflicts) | [UM] |
| Push button | Programmable push button on pin 2, configure as INPUT_PULLUP | [UM] |
| Buzzer | Piezo buzzer on pin 8 with selector (slide) switch | [UM] |
| USB connector | USB Micro-B socket | [UM] |
| FCC, CE, RoHS | Yes | [UM] |
| PCB colour | Purple | [UM] |
| Programming IDE | Arduino IDE | [UM] |
| Packing list | 1 × Maker Uno Plus (Code: MAKER-UNO-PLUS), 1 × Micro USB cable, 1 × Pin Header Sticker | [UM] |
| Warranty | UM: 6 months, manufacturing defects only; misuse and two-way freight not covered. PP: 12 months (see Conflicts) | [UM][PP] |
| Price | RM75.60 (Cytron product page, read 2026-10-16); UM Oct 2018 table: RM60 (~USD15) | [PP][UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **USB-serial:** "The USB to serial converter used at Maker UNO Plus is upgraded to FT231X from CH340 at Maker UNO"; resources link the FTDI driver (Windows, macOS, Linux) [PP].
- **Versus Arduino Uno:** adds 12x LED, 1x piezo buzzer, 1x programmable push button; 3.3 V current boosted to 500 mA (from 150 mA); no DC jack; USB Micro-B instead of USB-B [PP].
- **Extras:** pin-header label stickers (user sticks them on); area on the back to write a name; CE, FCC and RoHS compliant [PP].
- **Packing list:** 1x Maker UNO Plus, 1x Micro USB cable, 1x pin header sticker [PP].
- **Resources:** User's Manual (Google Doc), Beginner's Guide (PDF, cdn.cytron.io), schematic, Fritzing file, FTDI driver, Maker UNO projects [PP].

## Interfaces, terminals and pin mapping
Board layout (User's Manual section 4) [UM]:

| Label | Part | Function |
|---|---|---|
| A | On-board piezo buzzer | Connected to pin 8 through slide switch B |
| B | Piezo buzzer slide switch | "To use piezo buzzer, slide the switch on and program the buzzer. To use pin 8 for other purpose, slide the switch off." |
| C | 3.3V voltage regulator | 5V USB to 3.3V, to the 3.3V pin |
| D | USB-serial LED | Shows upload / Serial Monitor data |
| E | USB Micro B connector | Main supply; program and debug (Serial Monitor) |
| F | USB-serial IC converter | **FT231X** |
| G | Reset button | Restarts the program |
| H | Programmable button | "connected to pin 2 and GND"; configure as `INPUT_PULLUP` |
| I | Arduino UNO R3 standard female header | "The only difference is, Maker UNO does not have Vin." SDA, SCL and IOREF broken out as on UNO R3 |
| J | Main microcontroller | ATmega328P, same as Arduino Uno R3 |
| K | Series of MOSFET | Lets each LED be controlled or act as an input indicator, "even for pull-up input" |
| L | Series of LED for digital I/O | "Every digital IO is equipped with LED" |
| M | ISP header | 2x3, for AVR programmer; "Some uses it for SPI communication too" |

Pin summary for tutorials:

| Function | Pin | Src |
|---|---|---|
| Standard LED | Pin 13 | [UM] |
| Programmable indicator LEDs | Pins 2–13 (comparison table, section 7.1); intro says D0–D13 (see Conflicts) | [UM] |
| Push button | Pin 2 to GND; `pinMode(2, INPUT_PULLUP);` | [UM] |
| Piezo buzzer | Pin 8, switch on | [UM] |
| Serial (USB) | via FT231X; TX/RX LEDs | [UM] |
| PWM | 6 outputs. [PP: LG] lists pins 3, 5, 6, 9, 10, 11 | [UM][PP: LG] |
| Analog | 6 inputs ([PP: LG]: A0–A5) | [UM][PP: LG] |
| I2C | SDA, SCL header pins as on UNO R3 | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **USB power only (4.8–5.2 V).** Cytron removed the DC jack (12V adapter input) and the 5V linear regulator [UM]. There is no Vin pin [UM]. Never tell readers to plug a 9 V/12 V adapter into this board.
- **Shields that need Vin are not compatible**, unless the shield can select an external power source instead of Vin (UM examples that work that way: Cytron 3A Motor Driver Shield, G15 Shield, 10A Motor Driver Shield; example that does not: GPRS Shield V3.0). Check the shield schematic for a Vin connection [UM].
- **5V current = whatever the USB source gives** ("USB source") — no 5V figure is stated [UM]. 3.3V pin: 500 mA max; each I/O pin 20 mA max [UM].
- **Button on pin 2 needs `pinMode(2, INPUT_PULLUP);`**; it connects pin 2 to GND, so pressed = LOW [UM]. [PP: LG]: the on-board switch occupies pin 2, so do not use pin 2 for external parts at the same time.
- **Buzzer shares pin 8.** Slide the switch on to hear `tone(8, …)` (UM suggests the toneMelody example, File > Examples > 01.Digital); slide it off ("mute") to use pin 8 for something else [UM].
- **Pin LEDs (2–13) work for outputs and as input indicators**, including input pull-up [UM]. [PP: LG]: `digitalWrite(pin, HIGH)` turns an LED on; the pin 2 LED goes off when the on-board button is pressed.
- **Board selection: "Arduino/Genuino UNO"** and the correct COM port [UM][PP: LG]. In current Arduino IDEs this board is named "Arduino Uno" [VEN].
- **USB-serial chip is FT231X (FTDI), not CH340** — do not reuse Maker UNO's CH340 driver steps [UM].
- **Use one power source at a time** — "It is advisable to have 1 power source only at 1 time" [UM].
- Inputs are 3.3V-compatible, outputs are 0–5 V [UM].

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Main power | USB Micro-B, 5V (computer, power bank or standard USB adapter) | [UM] |
| USB input range | 4.8 – 5.2 V | [UM] |
| Portable power | Power bank or Cytron LiPo Power Shield | [UM] |
| Power sources at once | "advisable to have 1 power source only at 1 time" | [UM] |
| DC jack / 5V linear regulator | Removed | [UM] |
| Vin pin | None | [UM] |
| 3.3V output | 500 mA max continuous | [UM] |
| 5V output | "USB source" (no figure) | [UM] |
| I/O pin current | 20 mA max per pin | [UM] |
| Reverse-polarity / over-current protection | Not stated | — |

## Software support
- **Arduino IDE**; select "Arduino/Genuino UNO" and the correct COM port [UM]. Compatible with the example code and libraries for Arduino UNO [UM].
- **Driver:** the UM does not describe driver installation. [PP: LG] (cross-check): Windows installs the driver automatically when the board is plugged in; macOS 10.11 and later does not need the FTDI driver; older macOS needs the FTDI driver; example Mac port `/dev/cu.usbserial-…`.
- A Cytron board package for Maker UNO Plus: not stated (the Maker UNO package is for Maker UNO).
- MicroPython / CircuitPython / block coding: not stated.

## Compatibility and accessories
- Arduino UNO R3 shields: compatible except those needing Vin with no power-source option [UM]. Fully compatible examples given: LCD Keypad Shield, Cytron XBee Shield, Cytron SKM53 GPS Shield [UM].
- Cytron LiPo Power Shield for portable power [UM].
- **Differences from the genuine Arduino Uno** (UM comparison table) [UM]: input 5V USB only (Uno: 7–12V recommended, 6–20V limit via adapter); 5V current "USB source" (Uno: 1A); 3.3V current 500mA (Uno: 50mA); USB-serial FT231X (Uno: ATmega16U2); SMD ATmega328P; USB Micro-B; no DC jack, no Vin; extra LEDs on pins 2–13, button on pin 2, buzzer on pin 8 with switch. Same: 5V operating voltage, 6 analog, 1 UART/SPI/I2C, 2 interrupts, 32KB/2KB/1KB, 16MHz, FCC/CE/RoHS Yes.
- **Differences from Maker UNO** stated by the UM comparison table [UM]: USB-serial FT231X (Maker UNO: CH340G); FCC, CE, RoHS Yes (Maker UNO: No); price RM60 vs RM29 (2018). Packing list adds a Micro USB cable and pin header sticker [UM]. All other listed rows are the same. Do not copy any other Maker UNO detail across without a source.

## Common mistakes / troubleshooting
- Buzzer silent → slide switch is off [UM].
- Device on pin 8 misbehaves → buzzer switch is on [UM].
- Button reads random/always HIGH → missing `INPUT_PULLUP` on pin 2 [UM].
- Shield not powered → it needs Vin, which the board lacks [UM].
- Wrong driver installed → this board uses FT231X (FTDI), not CH340 [UM].
- Do not describe the board as having a DC jack, Vin pin or 7–12 V input [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Programmable LED range | [UM] intro: "a programmable LED on every digital pin, from pin D0 to D13" | [UM] comparison table and 7.1: "pin 2 - 13"; [PP] "added with 12x LED" | Pins 2–13 (12 LEDs) [PP][UM]; D0/D1 have the TX/RX LEDs |
| USB-serial chip | [UM] linked public copy: FT231X (features, table, layout); [PP] (read 2026-10-19): "upgraded to FT231X from CH340 at Maker UNO", FTDI driver linked |  internal Drive copy (2022 edit): features line "facilitated by the CH340" | **FT231X** — the CH340 line is a copy-paste from the Maker UNO manual |
| Warranty | [UM] Rev 1.0 (Oct 2018): 6 months | [PP] (read 2026-10-19): 12 months | Use the product page (current sales term): 12 months |
| Price | [UM] (Oct 2018): RM60 (~USD15) | [PP] (2026-10-16): RM75.60 | Use the product page for price (2026) |
| USB cable | [UM] packing list: 1 × Micro USB cable; [PP] packing list (read 2026-10-19): Micro USB cable included | [UM] intro: "…sold separately";  copy's packing list: board only | Included [PP][UM] |
| Digital I/O count | [UM] features: 14 (6 PWM) | [UM] table: 20 (6) | Not a true conflict: 20 counts A0–A5 as digital (same as Arduino Uno row). Use "14 digital I/O (6 PWM) + 6 analog" |

## Needs verification
- Board dimensions, mounting holes (drawing not readable); schematic details (PDF has no text layer).
- 5V pin current limit (only "USB source"); any USB fuse or protection.
- Physical differences from Maker UNO beyond the UM table (e.g. layout, label areas) — [3P] The Pi Hut mentions a space on the back to write a name.

## Sources
- [UM] Maker Uno Plus User's Manual (MAKER-UNO-PLUS), Rev 1.0, Oct 2018: https://docs.google.com/document/d/1M2sYWbmmt-Auyq963b5VpsdONsfrjwCBTLAf0VuP6zk/edit (public; read as text 2026-10-16). Mirror: https://cdn.robotshop.com/media/c/cyt/rb-cyt-253/pdf/cytron-maker-uno-plus-microcontroller-datasheet.pdf
- Schematic (linked from product page; no text layer): https://drive.google.com/file/d/1vyIWxDlVMzHl-M1A7_JfoeQfRj2kpdf5/view
- [PP: LG] Arduino Learning Guide for Beginners (Maker UNO+), v1.3, Dec 2018 (cross-check only): https://s3-ap-southeast-1.amazonaws.com/cdn.cytron.io/makeruno/Maker+UNO+Plus-+Beginner+Learning+Guide.pdf
- [PP] https://my.cytron.io/p-maker-uno-plus-simplifying-arduino-for-education (read by coordinator 2026-10-16: price, stock, warranty)
- [3P] (cross-check only): https://thepihut.com/products/maker-uno-plus
