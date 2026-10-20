# Cytron UNO - Arduino UNO Compatible — Verified Reference

| | |
|---|---|
| Product code | `CT-UNO` (user manual cover "CT-UNO"; my.cytron.io product-page image paths use CT-UNO [PP]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. The product page states "SMD ATmega328P", FT231X, 7–15 V, 5 V 1 A and 3.3 V 500 mA, and links the schematic |
| Primary source | **CT-UNO "CT UNO (Arduino Uno Compatible)" User's Manual, V1.0, Nov 2014** (Cytron Technologies Sdn Bhd), Google Doc linked from the product page; Drive metadata: created 2014-10-31, last modified 2025-09-16, cover still reads V1.0 Nov 2014 [UM]. No separate datasheet exists in any source found — the user manual is the top source |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the User's Manual above, read in full as text from Google Drive on 2026-10-16 (the Dimension drawing, board-layout picture and power-supply photos are images and did not come through). [PP] = (a) the my.cytron.io product page facts read by the coordinator on 2026-10-16 (price, stock, warranty, linked documents, product code in image paths) and (b) Cytron's own www.cytron.com.my/p-CT-UNO page, read 2026-10-16 through a summarising fetch (not verbatim). [VEN] = Arduino / Microchip general facts. The CT-UNO Schematic PDF (linked) returned no text from Drive and could not be downloaded here, so nothing below is taken from the schematic. No [DS], [DT] or [GH] source exists.

## What it is
CT-UNO is "a Cytron version of Arduino Uno": an SMD ATmega328 board with the Optiboot (UNO) bootloader, USB programming through an FTDI FT231X USB-serial chip on a USB Micro-B socket, and Arduino UNO R3 shield compatibility [UM]. It can be powered from a 2.1 mm DC adapter socket (7–15 V) or from USB, has a 1 A 5 V regulator and a 500 mA 3.3 V regulator, and moves the TX, RX, power and pin 13 LEDs to the board edge [UM]. Cytron's cytron.com.my page recommends Maker UNO instead for beginners and students [PP].

## Specifications
User's Manual section 3 "Product Specification" — Absolute Maximum Rating table, every row [UM]:

| Item | Value | Src |
|---|---|---|
| Input Voltage via Adapter (Recommended) | Min 7 V, Max 15 V | [UM] |
| Input Voltage via Adapter (Limits) | Min 6 V, Max 20 V | [UM] |
| IMAX (5V) (from on-board 5V Voltage regulator) | Max 1 A — footnote "\* With Vin at 12V" | [UM] |
| IMAX (3.3V) (from on-board 3.3V Voltage regulator) | Max 500 mA | [UM] |
| Other electrical limits | "The specification of ATmega328p used should be referred" | [UM] |

User's Manual section 1 feature list — every item:

| Item | Value | Src |
|---|---|---|
| Microcontroller | "SMD ATmega328 microcontroller with Optiboot (UNO) Bootloader" (sections 3 and 6.2 name it ATmega328p) | [UM] |
| USB programming | "Facilitated by the Ubiquitous FTDI FT231X (more stable)" | [UM] |
| Input voltage | DC7-15V | [UM] |
| 5V regulator | On board 1A (maximum) 5V voltage regulator | [UM] |
| 3.3V regulator | On board 500mA (maximum) 3.3V voltage regulator | [UM] |
| I/O levels | 0-5V digital outputs with 3.3V compatible inputs | [UM] |
| Digital I/O | 14 Digital I/O Pins (6 PWM outputs) | [UM] |
| Analog inputs | 6 Analog Inputs (can be digital I/O too) | [UM] |
| Peripherals | UART, SPI, external interrupts, I2C | [UM] |
| ISP | ISP 6-pin Header (populated; "SPI and power") | [UM] |
| Flash | 32k Flash Memory | [UM] |
| Clock | 16MHz Clock Speed | [UM] |
| Shield compatibility | R3 Shield Compatible; SDA, SCL and IOREF broken out as on UNO R3 | [UM] |
| LEDs | TX, RX, Power, pin 13 LEDs are moved to edge (near the USB socket for easier viewing with a shield on [PP]) | [UM][PP] |
| USB connector | USB Micro-B socket | [UM] |
| PCB colour | White PCB | [UM] |
| Packing list | 1 x CT-UNO board; optional add-ons: 12V 2A AC to DC Adapter, USB Micro B cable | [UM] |
| USB cable | Micro-B cable sold separately | [PP] |
| Warranty | 12 months; manufacturing defects only; misuse not covered; freight both ways not covered | [UM][PP] |
| Price | RM61.74 (Cytron product page, read 2026-10-16) | [PP] |
| Dimensions | Drawing only (section 4); no values in the text | [UM] |
| SRAM / EEPROM | Not stated by Cytron. ATmega328P: 2 KB SRAM, 1 KB EEPROM | [VEN] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Features list:** **SMD ATmega328P** with Optiboot (UNO R3) bootloader; FTDI FT231X USB; input 7–15 V DC; 5 V regulator 1 A max; 3.3 V regulator 500 mA max; 0–5 V outputs, 3.3 V-compatible inputs; 14 digital I/O (6 PWM); 6 analog inputs; ISP header; 32 KB flash, 2 KB SRAM, 1 KB EEPROM; 16 MHz; R3 shield compatible; TX, RX, power and pin-13 LEDs at the board edge; USB micro-B; white PCB [PP].
- **Description:** select "Arduino UNO" in the IDE; USB micro-B cable sold separately [PP].
- **Packing list:** 1x CT-UNO [PP]. **Resources:** user's manual, 3D CAD, FTDI drivers, **schematic (Google Drive)**, Fritzing, Arduino IDE [PP].

## Interfaces, terminals and pin mapping
Board layout (User's Manual section 5) [UM]:

| Label | Part | Function (manual wording) |
|---|---|---|
| A | Reset Button | Resets/restarts the CT-UNO program |
| B | Micro USB B Type Connector (Female) | Upload program or power via USB; needs a USB micro-B cable |
| C | RX LED Indicator (Serial) | Lights when data transfers from USB to ATmega328 |
| D | TX LED Indicator (Serial) | Lights when data transfers from ATmega328 to USB |
| E | Programmable LED | **Active HIGH, connected to pin 13**; blinks orange with Blink |
| F | Power LED Indicator | Lights once the board is powered; green ("PWR LED (green)") |
| G | Adapter Socket (2.1mm) | DC adapter input, 7 to 15 V |
| H | Extra Pads | Let CT-UNO be stacked on strip/donut board (0.1" pitch); solder header pins at the outer (left and right) side |
| I | Arduino R3 Standard Header | Stack Arduino shields |
| J | ISP Header Pin | Upload Arduino Uno bootloader with an AVR programmer (e.g. AVR USBasp) |

Pin summary for tutorials:

| Function | Pin | Src |
|---|---|---|
| Programmable LED (`LED_BUILTIN`) | D13, active HIGH | [UM] |
| Serial (USB) | D0 RX / D1 TX via FT231X (standard UNO mapping) | [UM][VEN] |
| PWM | 6 pins (UM does not list them; UNO mapping D3, D5, D6, D9, D10, D11) | [UM][VEN] |
| I2C | SDA/SCL header pins as on UNO R3 (A4/A5 on the UNO mapping) | [UM][VEN] |
| Analog | 6 inputs, also usable as digital I/O | [UM] |
| SPI | Available; also on the 6-pin ISP header | [UM] |

There are no onboard buttons other than Reset, and no buzzer — the only user-controllable indicator is the pin 13 LED [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **USB-serial chip is FTDI FT231X, not CH340.** Readers need the FTDI VCP driver, not the CH340 driver [UM]. Do not copy Maker UNO's CH340 instructions.
- **Board to select: Tools > Board > "Arduino Uno"** [UM]. The manual says "Tools > Serial Port"; current Arduino IDEs call this "Tools > Port" [VEN].
- **DC jack input: 7–15 V recommended, 6–20 V absolute limits** [UM]. The 1 A 5 V rating is given "With Vin at 12V" — do not quote 1 A at other input voltages [UM].
- **Both supplies connected → adapter wins.** "If CT-UNO is powered using both supply (12V adapter and USB cable) it will automatically choose power from adapter" [UM].
- **I/O level:** outputs are 0–5 V; inputs are 3.3 V compatible [UM]. A 5 V HIGH reaches any module wired to an output — check a 3.3 V-only module's input tolerance (general practice, not a Cytron statement).
- **Pin 13 LED is active HIGH** — `digitalWrite(13, HIGH)` turns it on [UM].
- **Per-pin current limits are not given by Cytron**; the manual says refer to the ATmega328P specification [UM].
- **The USB cable is not in the box** — only the board is included [UM][PP].
- The extra pads need header pins soldered at the outer side before stacking on strip/donut board [UM].
- CT-UNO is a different product from Maker UNO, Maker UNO Plus and Cytron UNO Special Edition; do not mix their features (CH340, no DC jack, pin LEDs, buzzer, button belong to Maker UNO, not CT-UNO).

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Power sources | 12V power adapter via DC jack, or USB cable | [UM] |
| DC jack | 2.1 mm adapter socket | [UM] |
| Adapter input, recommended | 7–15 V | [UM] |
| Adapter input, limits | 6–20 V | [UM] |
| Both connected | Board automatically uses the adapter | [UM] |
| 5V regulator output | 1 A max, with Vin at 12 V | [UM] |
| 3.3V regulator output | 500 mA max | [UM] |
| Regulator note | "upgraded the on board voltage regulator" to supply higher current | [PP] |
| Suggested adapter | 12V 2A AC to DC Adapter (optional add-on) | [UM] |
| I/O pin current | Not stated — refer to ATmega328P specification | [UM] |
| Reverse-polarity / over-current protection | Not stated | — |

## Software support
- **Arduino IDE**: Blink example (File > Examples > 01.Basics > Blink), board "Arduino Uno", then select the CT-UNO serial port and Upload; RX/TX LEDs flash during upload, "Done uploading." appears, and the pin 13 (L) LED blinks orange [UM].
- **Driver**: on Windows the automatic install may fail unless an FTDI device was used before; download the latest FTDI VCP driver from http://www.ftdichip.com/Drivers/VCP.htm for your OS, then the board gets a COM port [UM].
- **Bootloader**: Optiboot (UNO); can be re-flashed through the ISP header with an AVR programmer such as AVR USBasp [UM].
- No Cytron board package, MicroPython, CircuitPython or block-coding support is stated.

## Compatibility and accessories
- Arduino UNO shields: "compatible with all Arduino UNO's shield"; R3 shield compatible [UM]. Manual examples: LCD Keypad shield (SHIELD-LCD); a wireless remote omni robot using CT-UNO with SHIELD-XBEE and FD04A-R2 [UM].
- Strip/donut board (0.1" pitch) via the extra pads [UM]; cytron.com.my page: extra 2.54 mm pads "for building your own shield" [PP].
- Optional add-ons: 12V 2A AC to DC Adapter, USB Micro B cable [UM].
- AVR USBasp programmer for the ISP header [UM].
- **Differences from a genuine Arduino UNO R3** (as Cytron states) [UM][PP]: FTDI FT231X USB-serial (cytron.com.my: FTDI approach of the Duemilanove) instead of the UNO R3's ATmega16U2 [VEN]; USB Micro-B socket instead of USB-B [VEN]; SMD ATmega328; DC input stated as 7–15 V recommended (Arduino states 7–12 V for UNO R3 [VEN]); upgraded regulator (5V 1A); TX/RX/power/pin 13 LEDs moved to the edge; extra pads for strip/donut board; white PCB.

## Common mistakes / troubleshooting
- No COM port / driver install fails on Windows → install the FTDI VCP driver from ftdichip.com [UM].
- Wrong board selected → choose "Arduino Uno" [UM].
- Power LED (green) off → board not powered; check USB cable or adapter [UM].
- Quoting "1 A from the 5 V pin" without the condition → the manual rates 1 A only with Vin at 12 V; no figure is given for other input voltages or for USB power [UM].
- Using a CH340 driver or Maker UNO board package for CT-UNO → wrong; CT-UNO uses FTDI and the standard "Arduino Uno" board [UM].
- Do not describe CT-UNO as having pin LEDs on every digital pin, a buzzer or a user button.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| MCU name | [UM] feature list: "SMD ATmega328" | [UM] sections 3 and 6.2 and [PP] features (read 2026-10-20): "ATmega328P" | **ATmega328P** [PP][UM] |
| Product name | [PP] my.cytron.io: "Cytron UNO - Arduino UNO Compatible" | [UM]: "CT-UNO", "CT UNO (Arduino Uno Compatible)" | Same product (code CT-UNO); use either |
| Manual date vs Drive edit | [UM] cover: V1.0, Nov 2014 | Drive metadata: last modified 2025-09-16 | Content still V1.0; links inside point to old cytron.com.my URLs |
| Warranty | [UM] 12 months | [PP] 12 months | Agree |

## Needs verification
- Schematic contents (CT-UNO Schematic.pdf, Dec 2014) — could not be read here; confirm the exact MCU part (ATmega328P vs ATmega328), regulator parts and auto power-selection circuit.
- Board dimensions, weight and mounting holes (drawing only in the manual). The CT-UNO-SE product page (SE = "exactly the same as CT-UNO, with the special side connectors") has a dimension drawing: 68.58 × 55.88 mm, 4 × Ø3 mm holes — likely the same for CT-UNO; confirm before quoting for CT-UNO.
- Whether any current CT-UNO production revision has changed the USB-serial chip (manual is V1.0, 2014; no newer revision found).
- 5V output current at Vin other than 12 V, and from USB power.
- Per-pin LED colours other than PWR (green) and pin 13 (orange) — TX/RX LED colours not stated.
- 3D CAD folder (linked) was not listed by the Drive tool; contents not checked.

## Sources
- [UM] CT-UNO User's Manual (CT UNO (Arduino Uno Compatible), V1.0, Nov 2014) — https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view (public; read 2026-10-16)
- CT-UNO Schematic (not readable here) — https://drive.google.com/file/d/0BzFWfMiqqjyqTHlXdTlxaDU4bWM/view
- 3D CAD folder (not read) — https://drive.google.com/drive/folders/1T0tSZfnqNUEP873tR0BSAQXPIU9SnEkR
- [PP] https://my.cytron.io/p-cytron-uno-arduino-uno-compatible (facts read by coordinator 2026-10-16)
- [PP] https://www.cytron.com.my/p-CT-UNO (read 2026-10-16, summarised fetch)
- [UM] driver link given in the manual: http://www.ftdichip.com/Drivers/VCP.htm
- [3P] (cross-check only; agrees with UM) https://tindie.com/products/cytron/ct-uno
