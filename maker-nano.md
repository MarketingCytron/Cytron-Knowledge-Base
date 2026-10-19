# Maker Nano for Projects (Arduino Compatible) — Verified Reference

| | |
|---|---|
| Product code | `MAKER-NANO` (datasheet cover "MAKER-NANO" [DS]; product-page image paths [PP]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: product-page images read ("Arduino Nano 3.x vs Maker Nano" comparison table, pinout, layout, dimension drawing) — MCU, USB chip, dimensions and pin functions now confirmed by Cytron; CH34X driver links and packing list added |
| Primary source | **MAKER-NANO "Simplifying Arduino for Projects" Datasheet, Rev 1.0, June 2020** (Cytron Technologies Sdn Bhd), public Google Doc linked from the product page (file last modified 2022-10-20; revision label still Rev 1.0) [DS] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = the datasheet above, read as text through Google Drive (its section 1 comparison table, Figure 3 pinout and Figure 4 dimension drawing are images). [PP] = my.cytron.io product page, read in full 2026-10-19 (description, packing list, resources, CH34X driver links). [PP: img] = Cytron's own product-page images, read visually 2026-10-19: "Arduino Nano 3.X vs Maker Nano" comparison table (arduino-nano-vs-maker-nano.png — the same title as datasheet section 1), pinout (maker-nano-pinout.png, also published as the "Maker Nano Pinout Diagram"), board layout (maker-nano-layout.png) and dimension drawing (maker-nano-dimension.png). [PP: tutorial] = Cytron tutorial "Social Distance Alert Wristband Using Arduino (Maker Nano)" (17 Jun 2020). No user manual, [DT] or [GH] source was found. The schematic (Drive "Maker Nano Schematic v1.0.0.pdf") exists but returned no text (image-only).

## What it is
An Arduino Nano-form-factor board ("Simplifying Arduino for Projects") whose pin header is "Compatible with original Arduino Nano" [DS]. Built around the ATmega328P with a CH340C USB-serial chip [PP: img]. It adds digital IO LEDs on D2–D13, a programmable piezo buzzer with a mute switch (shares D8), a user programmable button on D2, power LEDs for 3V3 and 5V, and TX/RX serial LEDs, and accepts a 7.0–30.0 VDC Vin input [DS]. Programs are uploaded from a PC through the Micro USB port [DS].

## Specifications
Datasheet section 4 "Specifications" — Table 3 "MAKER-NANO Absolute Maximum Ratings", every row:

| Item | Value | Src |
|---|---|---|
| Power Input Voltage (Vin) | Min 7.0, Max 30.0 VDC | [DS] |
| Digital Input Voltage — Low Level | Min 0, Max 0.5 V | [DS] |
| Digital Input Voltage — High Level | Min 1.7, Max 5.0 V | [DS] |
| Analog Input Voltage | Min 0, Max 5.0 V | [DS] |
| DC +5V Maximum Current (Including Onboard Usage) | Max 100 mA | [DS] |
| DC +3V3 Maximum Current (Including Onboard Usage) | Max 50 mA | [DS] |

Other product facts:

| Item | Value | Src |
|---|---|---|
| USB connector | Micro USB Port — "Used to upload Arduino program from PC. Can be used for debugging purpose too (Serial Monitor)." | [DS] |
| Microcontroller | ATmega328P, 16MHz; 32KB flash, 2KB SRAM, 1KB EEPROM/Data Flash | [PP: img] |
| Operating voltage | 5V | [PP: img] |
| I/O | 20 digital I/O, 6 PWM, 8 analog inputs (10-bit), 1 UART, 1 SPI, 1 I2C, 2 external interrupts | [PP: img] |
| Power supply | Vin or USB; Vin 7–30V; onboard 5V regulator, so it runs from a battery or DC adapter as well as USB | [PP: img][PP] |
| USB-serial chip / driver | CH340C [PP: img]; Cytron links CH34X drivers (Windows 10 note, Windows V3.5 Mar2019, Mac OS V1.5 Mar2019, Linux V1.5 — "normally is readily installed") and the WCH download page; "ensure that Maker Nano is connected to the computer's USB port during driver installation" | [PP] |
| Programming IDE | Arduino IDE | [PP: img] |
| Dimensions | 45.80 mm × 21.09 mm board; header rows 15.24 mm apart, 2.54 mm pitch [PP: img]. Comparison table rounds to 21 × 46 mm; "1mm longer and 3mm wider" than the original Arduino Nano | [PP: img][PP] |
| Packing list | 1 x Maker Nano (USB Micro B cable is a suggested accessory, not included) | [PP] |
| Price | RM37.38 | [PP] |
| Stock | 292 (2026-10-19) | [PP] |
| Warranty | 12 months | [PP] |

## Interfaces, terminals and pin mapping
Datasheet Table 1 "Board Functions (Top)" [DS]:

| Function | Description |
|---|---|
| Power LEDs | LED indicator for 3V3 and 5V. Turn on when powered up. |
| Digital IO LEDs (D2–D13) | LED indicator for digital IO D2–D13. **Turn on when the IO state is high.** |
| Serial Port LEDs | USB serial port activity. TX: on when data is transmitted from Maker Nano. RX: on when data is received by Maker Nano. |
| Micro USB Port | Upload Arduino program from PC; debugging (Serial Monitor). |
| Mute Switch | Mutes the piezo buzzer if pin **D8** is used for other purposes. |
| Reset Button | Press to reset the Maker Nano. |
| User Programmable Button | Connected to pin **D2** internally. Accessible from the user program. |

Datasheet Table 2 "Board Functions (Bottom)" [DS]:

| Function | Description |
|---|---|
| Pin Header | Used for external connection. "Compatible with original Arduino Nano." |
| Piezo Buzzer | Programmable piezo buzzer. Can be used to play tone or melody. |
| Digital IO LEDs Enable Jumper | "Cut the trace to disable the digital IO LEDs." Done to save power or reduce distraction from the digital IO LEDs. |

Pin summary for tutorials:

| Function | Pin | Src |
|---|---|---|
| Programmable button | D2 (internal connection) | [DS] |
| Piezo buzzer | D8 (implied by the mute switch description: mute "if pin D8 is used for other purposes") | [DS] |
| Digital IO LEDs | D2–D13, lit when the pin is HIGH | [DS] |
| D0 / D1 | No IO LED listed (the LED range is D2–D13); TX/RX LEDs show USB serial activity | [DS] |
| Full pinout (Cytron pinout image) | Left header: D13 (SCK, LED), 3V3 (power LED), REF (analog reference), A0–A3 (analog in / digital IO), A4 (SDA), A5 (SCL), A6 and A7 (**analog in only**), 5V (power LED), RST, GND, VIN. Right header: D12 (MISO), D11 (PWM, MOSI), D10 (PWM, SS), D9 (PWM), D8 (piezo buzzer), D7, D6 (PWM), D5 (PWM), D4, D3 (PWM, INT1), D2 (INT0, user button), GND, RST (reset button), D0 (Rx ← USB COM Tx), D1 (Tx → USB COM Rx). D2–D13 each have an IO LED | [PP: img] |
| Header order (layout image) | Top row: TX1, RX0, RST, GND, D2–D12. Bottom row: VIN, GND, RST, 5V, A7–A0, REF, 3V3, D13 | [PP: img] |

## Rules and gotchas (for code, wiring and tutorials)
- **5V rail is only 100 mA max and 3V3 only 50 mA max, *including onboard usage*** [DS]. Do not power servos, motors, LED strips or other high-current loads from the 5V/3V3 pins. Do not quote higher figures from the genuine Arduino Nano or from Maker UNO / Maker UNO Plus (500 mA 3.3V) — those are different boards.
- **Vin accepts 7.0–30.0 VDC** [DS]. Do not tell readers to feed 5 V into Vin (below the 7.0 V minimum).
- **D8 is shared with the buzzer.** Slide the mute switch to mute the buzzer when D8 drives something else [DS]. Switch positions/markings are not described in text.
- **D2 is the user button.** The datasheet says only that the button is "connected to pin D2 internally" — it does not say whether it pulls D2 to GND or needs `INPUT_PULLUP`. Do not state the wiring or the pressed logic level until verified (see Needs verification).
- **Digital IO LEDs (D2–D13) light when the IO state is high** [DS] — so an LED can glow on a pin used as an input. To stop this permanently, cut the "Digital IO LEDs Enable Jumper" trace on the bottom [DS]; the datasheet does not describe how to re-enable.
- **Input thresholds:** digital LOW 0–0.5 V, HIGH 1.7–5.0 V; analog input 0–5.0 V [DS]. Never exceed 5.0 V on an input.
- **Board in Arduino IDE: "Arduino Nano"** — Cytron's own tutorial sketch header says "Board: Arduino Nano (Maker Nano)" [PP: tutorial]. Which Processor option ("ATmega328P" or "ATmega328P (Old Bootloader)") is **not stated** — if upload fails with one, try the other (general Arduino Nano practice, not a Cytron statement).
- **Install the CH34X driver** (CH340C chip) before first upload [PP][PP: img].
- **A6 and A7 are analog inputs only** — no digital IO [PP: img].
- Powering from a battery: Cytron's wristband tutorial feeds a 7.4V 2S LiPo into VIN [PP: tutorial] — within the 7.0–30.0 V Vin range [DS].

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Vin input | 7.0 – 30.0 VDC | [DS] |
| USB as power source | Yes — "Vin or USB" [PP: img]; "you can power up your circuit from battery or DC adapter, besides the USB port" [PP] | [PP: img][PP] |
| DC +5V max current | 100 mA, including onboard usage | [DS] |
| DC +3V3 max current | 50 mA, including onboard usage | [DS] |
| Digital input | Low 0–0.5 V; High 1.7–5.0 V | [DS] |
| Analog input | 0 – 5.0 V | [DS] |
| Regulator type, reverse-polarity / over-current protection | Not stated | — |
| Per-I/O-pin current | Not stated | — |

## Software support
- Arduino: the Micro USB port is "Used to upload Arduino program from PC" and supports Serial Monitor debugging [DS].
- Board to select in Arduino IDE: "Arduino Nano" [PP: tutorial]; Processor option not stated.
- USB driver: CH34X (CH340C chip) — Cytron links Windows, Mac OS and Linux driver files and the WCH download page [PP].
- MicroPython / CircuitPython / block coding: not stated.

## Compatibility and accessories
- Pin header "Compatible with original Arduino Nano" [DS].
- Differences from Arduino Nano 3.x (Cytron comparison table): same ATmega328P, memory, I/O, 5V operation; Maker Nano has Vin 7–30V (Nano 7–12V), CH340C (Nano: FTDI FT232RL), 12 programmable LEDs on D2–D13 (Nano: 1 on D13), a programmable push button on D2, a piezo buzzer on D8, and is 21 × 46 mm (Nano 18 × 45 mm) [PP: img]. Same pin arrangement; "compatible with most, if not all, of the daughter boards for Arduino Nano"; breadboard friendly [PP].
- Maker Nano RP2040, Maker UNO and Maker UNO Plus are **separate products**; do not copy their specs (RP2040 pins, 500 mA 3.3V, RGB LEDs, Maker Ports) into Maker Nano content.
- In the box: 1 x Maker Nano [PP]. USB Micro B cable sold separately (suggested accessory) [PP].

## Common mistakes / troubleshooting
- Buzzer silent → mute switch is set to mute [DS].
- Device on D8 clicks or behaves oddly → buzzer not muted [DS].
- LEDs lighting on input pins → normal: D2–D13 LEDs show a HIGH state [DS]; cut the enable jumper if unwanted [DS].
- Board resets or browns out when a sensor/servo is added on 5V → load exceeds the 100 mA (5V) or 50 mA (3V3) limit, which includes onboard usage [DS].
- Do not describe Maker Nano with Maker UNO-style figures (500 mA 3.3V, USB-only power) — it has a Vin input and much lower rail limits [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Dimensions | [PP: img] drawing: 45.80 × 21.09 mm | [PP: img] comparison table: 21 × 46 mm; [3P] Core Electronics 45.8 × 21.1 mm | Same size, rounded; quote 45.80 × 21.09 mm |
| USB chip | [PP: img] CH340C | [3P] CH340C | Consistent; now Cytron-confirmed |

## Needs verification
- **Arduino IDE Processor option** — "ATmega328P" or "ATmega328P (Old Bootloader)"; Cytron states only the board "Arduino Nano" [PP: tutorial]. Ask [DT] which bootloader ships.
- Whether the product-page comparison image is identical to datasheet section 1 (same title; the datasheet copy is an image and was not compared pixel by pixel).
- What happens with USB and Vin connected together (which source wins).
- User button wiring (to GND? needs `INPUT_PULLUP`?) and pressed logic level.
- Whether the 100 mA / 50 mA limits differ between USB and Vin power (the Maker Nano RP2040 datasheet splits them; this one does not).
- How to re-enable IO LEDs after cutting the jumper; mute switch position markings.
- Certifications.

## Sources
- [DS] Maker Nano Datasheet ("MAKER-NANO Simplifying Arduino for Projects", Rev 1.0, June 2020): https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view (public; read as text 2026-10-16)
- [PP] https://my.cytron.io/p-maker-nano-simplifying-arduino-for-projects (price/stock 2026-10-16; full description, packing list, resources 2026-10-19)
- [PP: img] https://static.cytron.io/image/catalog/products/maker-nano/arduino-nano-vs-maker-nano.png · https://static.cytron.io/image/catalog/products/maker-nano/maker-nano-pinout.png · https://static.cytron.io/image/catalog/products/maker-nano/maker-nano-layout.png · https://static.cytron.io/image/catalog/products/maker-nano/maker-nano-dimension.png
- [PP] Maker Nano Pinout Diagram (published drawing) — https://docs.google.com/drawings/d/e/2PACX-1vTKaRKXaAJUKBge3Wpr_IIrPP4mBkCpcovmvXzoGLalp1upD5NcrzEnB-GQo3_tZbJ-YOaU6EM9zr3e/pub?w=2755&h=1816
- [PP: tutorial] Social Distance Alert Wristband Using Arduino (Maker Nano) — https://my.cytron.io/tutorial/social-distance-alert-wristband-using-arduino-maker-nano
- Schematic (image only, no text extracted): "Maker Nano Schematic v1.0.0.pdf" https://drive.google.com/file/d/1xRj-DJnCv_tZUSp1jUOuZCaw-S2rgI9P/view (link found on a reseller page)
- [3P] (cross-check only): https://core-electronics.com.au/cytron-maker-nano.html · https://thepihut.com/collections/arduino-store/products/maker-nano · https://www.robotshop.com/products/maker-nano-arduino-based-microcontroller · https://www.slideshare.net/slideshow/maker-nano-datasheetdocx/259830635 (copy of the datasheet, same text gaps)
