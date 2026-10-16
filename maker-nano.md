# Maker Nano for Projects (Arduino Compatible) — Verified Reference

| | |
|---|---|
| Product code | `MAKER-NANO` (datasheet cover "MAKER-NANO" [DS]; product-page image paths [PP]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **MAKER-NANO "Simplifying Arduino for Projects" Datasheet, Rev 1.0, June 2020** (Cytron Technologies Sdn Bhd), public Google Doc linked from the product page (file last modified 2022-10-20; revision label still Rev 1.0) [DS] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = the datasheet above, read as text through Google Drive. **Section 1 "ARDUINO NANO 3.X vs MAKER NANO" (the comparison table), Figure 3 (pinout diagram) and Figure 4 (dimension drawing) are images and could not be read.** So the MCU, USB-serial chip, dimensions and the Nano comparison are NOT confirmed by any Cytron source read here — see *Needs verification*. [PP] = my.cytron.io product page as read by the coordinator on 2026-10-16 (price, stock, warranty only). No user manual, [DT] or [GH] source was found. The schematic (Drive "Maker Nano Schematic v1.0.0.pdf") exists but returned no text (image-only).

## What it is
An Arduino Nano-form-factor board ("Simplifying Arduino for Projects") whose pin header is "Compatible with original Arduino Nano" [DS]. It adds digital IO LEDs on D2–D13, a programmable piezo buzzer with a mute switch (shares D8), a user programmable button on D2, power LEDs for 3V3 and 5V, and TX/RX serial LEDs, and accepts a 7.0–30.0 VDC Vin input [DS]. Programs are uploaded from a PC through the Micro USB port [DS].

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
| Microcontroller | **Not readable in the datasheet text** (comparison table is an image). [3P] say ATmega328P — see Needs verification | — |
| USB-serial chip / driver | **Not readable in the datasheet text.** [3P] say CH340C — see Needs verification | — |
| Dimensions | Figure 4 drawing only; no values in the text | [DS] |
| Price | RM37.38 | [PP] |
| Stock | 292 (2026-10-16) | [PP] |
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
| Full pinout | Figure 3 is an image — not readable; header is "Compatible with original Arduino Nano" | [DS] |

## Rules and gotchas (for code, wiring and tutorials)
- **5V rail is only 100 mA max and 3V3 only 50 mA max, *including onboard usage*** [DS]. Do not power servos, motors, LED strips or other high-current loads from the 5V/3V3 pins. Do not quote higher figures from the genuine Arduino Nano or from Maker UNO / Maker UNO Plus (500 mA 3.3V) — those are different boards.
- **Vin accepts 7.0–30.0 VDC** [DS]. Do not tell readers to feed 5 V into Vin (below the 7.0 V minimum).
- **D8 is shared with the buzzer.** Slide the mute switch to mute the buzzer when D8 drives something else [DS]. Switch positions/markings are not described in text.
- **D2 is the user button.** The datasheet says only that the button is "connected to pin D2 internally" — it does not say whether it pulls D2 to GND or needs `INPUT_PULLUP`. Do not state the wiring or the pressed logic level until verified (see Needs verification).
- **Digital IO LEDs (D2–D13) light when the IO state is high** [DS] — so an LED can glow on a pin used as an input. To stop this permanently, cut the "Digital IO LEDs Enable Jumper" trace on the bottom [DS]; the datasheet does not describe how to re-enable.
- **Input thresholds:** digital LOW 0–0.5 V, HIGH 1.7–5.0 V; analog input 0–5.0 V [DS]. Never exceed 5.0 V on an input.
- The datasheet does not name the Arduino IDE board to select, the MCU, or the USB driver in readable text — do not invent them in tutorials; use the Needs verification items only after confirmation.

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Vin input | 7.0 – 30.0 VDC | [DS] |
| USB as power source | Not stated in the datasheet text (Micro USB is described for upload and Serial Monitor; Power LEDs turn on "when powered up") | [DS] |
| DC +5V max current | 100 mA, including onboard usage | [DS] |
| DC +3V3 max current | 50 mA, including onboard usage | [DS] |
| Digital input | Low 0–0.5 V; High 1.7–5.0 V | [DS] |
| Analog input | 0 – 5.0 V | [DS] |
| Regulator type, reverse-polarity / over-current protection | Not stated | — |
| Per-I/O-pin current | Not stated | — |

## Software support
- Arduino: the Micro USB port is "Used to upload Arduino program from PC" and supports Serial Monitor debugging [DS].
- Board to select in Arduino IDE: **not stated** in any Cytron source read.
- USB driver: **not stated** in any Cytron source read.
- MicroPython / CircuitPython / block coding: not stated.

## Compatibility and accessories
- Pin header "Compatible with original Arduino Nano" [DS].
- Differences from the genuine Arduino Nano: the datasheet's comparison table (section 1) is an image and could not be read. Stated in text: onboard D2–D13 IO LEDs, buzzer with mute switch on D8, user button on D2, power LEDs, IO-LED enable jumper, Vin 7.0–30.0 VDC [DS].
- Maker Nano RP2040, Maker UNO and Maker UNO Plus are **separate products**; do not copy their specs (RP2040 pins, 500 mA 3.3V, RGB LEDs, Maker Ports) into Maker Nano content.
- Accessories in the box: not stated.

## Common mistakes / troubleshooting
- Buzzer silent → mute switch is set to mute [DS].
- Device on D8 clicks or behaves oddly → buzzer not muted [DS].
- LEDs lighting on input pins → normal: D2–D13 LEDs show a HIGH state [DS]; cut the enable jumper if unwanted [DS].
- Board resets or browns out when a sensor/servo is added on 5V → load exceeds the 100 mA (5V) or 50 mA (3V3) limit, which includes onboard usage [DS].
- Do not describe Maker Nano with Maker UNO-style figures (500 mA 3.3V, USB-only power) — it has a Vin input and much lower rail limits [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | No conflict found between Cytron sources read. [3P] retailer specs could not be compared against the datasheet's comparison table (image) | — | See Needs verification |

## Needs verification
- **Microcontroller:** [3P] (Core Electronics, The Pi Hut, RobotShop) say ATmega328P, 16 MHz, 32 KB flash / 2 KB SRAM / 1 KB EEPROM. Not in readable Cytron text.
- **USB-serial chip and driver:** [3P] (Core Electronics, The Pi Hut) say CH340C, CH34x driver needed on some systems. Not in readable Cytron text.
- **Arduino IDE board selection** (e.g. "Arduino Nano" and which processor/bootloader option) — no source read states it.
- **Datasheet section 1 "Arduino Nano 3.x vs Maker Nano"** comparison table and Figure 3 pinout — images; need a person to read them.
- **Dimensions:** [3P] Core Electronics 45.8 × 21.1 mm; The Pi Hut 21 × 46 mm; [3P] "about 1 mm longer and 3 mm wider than the original Arduino Nano". Datasheet Figure 4 not readable.
- [3P] say 20 digital I/O (6 PWM), 8 analog inputs (10-bit), 1 UART/SPI/I2C, 2 external interrupts, 5V regulator, "works with most Arduino Nano shields", breadboard friendly.
- Whether USB powers the board (almost certain, but not stated in readable text) and what happens with USB and Vin connected together.
- User button wiring (to GND? needs `INPUT_PULLUP`?) and pressed logic level.
- Whether the 100 mA / 50 mA limits differ between USB and Vin power (the Maker Nano RP2040 datasheet splits them; this one does not).
- How to re-enable IO LEDs after cutting the jumper; mute switch position markings.
- Packing list (USB cable included or not), certifications.

## Sources
- [DS] Maker Nano Datasheet ("MAKER-NANO Simplifying Arduino for Projects", Rev 1.0, June 2020): https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view (public; read as text 2026-10-16)
- [PP] https://my.cytron.io/p-maker-nano-simplifying-arduino-for-projects (read by coordinator 2026-10-16: price, stock, warranty)
- Schematic (image only, no text extracted): "Maker Nano Schematic v1.0.0.pdf" https://drive.google.com/file/d/1xRj-DJnCv_tZUSp1jUOuZCaw-S2rgI9P/view (link found on a reseller page)
- [3P] (cross-check only): https://core-electronics.com.au/cytron-maker-nano.html · https://thepihut.com/collections/arduino-store/products/maker-nano · https://www.robotshop.com/products/maker-nano-arduino-based-microcontroller · https://www.slideshare.net/slideshow/maker-nano-datasheetdocx/259830635 (copy of the datasheet, same text gaps)
