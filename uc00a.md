# UC00A (FTDI) USB to UART Converter — Verified Reference

| Field | Value |
|---|---|
| Product code | UC00A [PP][UM]; current hardware revision Rev3.0 [UM] |
| Family | USB and serial converters |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "UC00A Rev3.0 Cytron USB to UART Converter User's Manual", V1.1, December 2018 (Cytron Technologies Sdn Bhd) — no separate Cytron datasheet exists; the user manual is the top Cytron source and is tagged [UM]. Older manuals: Rev2.0 UM V1.0 July 2012; Rev1.0 UM V1.0 Oct 2008 (tagged [UM-R2] / [UM-R1], lower precedence for the current product) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A USB-powered USB-to-UART converter built on an FTDI chip that gives a computer a virtual COM port and connects it directly to a 3.3 V or 5 V TTL UART device [UM]. Rev3.0 has a USB Micro-B socket, a 3.3V/5V slide switch (Vsel), a standard 6-way header socket (DTR, TX, RX, GND, CTS, VCC) for Arduino-style bootloader headers, and extra solder pads (JP4/JP6) that break out the full FTDI modem-control set [UM]. The manual calls it "low cost, easy to use", "USB plug and play, direct interface with microcontroller and it provides 5V power supply from USB port" [UM].

The FTDI chip is named only as "FTDI chip" in the manual [UM]; the Rev3.0 schematic linked from the product page shows an FT232RL [PP, schematic], and the product page links the FT232RL vendor datasheet [PP][VEN].

## Specifications
The user manual has no numeric spec table; the rows below collect every stated feature and figure for Rev3.0 [UM] unless marked.

| Item | Value | Src |
|---|---|---|
| USB-to-UART chip | "FTDI chip" (FTDI's TX/RX indicator LEDs) | [UM] |
| USB-to-UART chip | FT232RL (Rev3.0 schematic, "UC00A R3.sch", 3/14/2016) | [PP] schematic |
| USB connector | USB Micro-B socket ("New! Utilize USB Micro-B socket") | [UM] |
| Power source | USB powered, "no external source is required to use this converter" | [UM] |
| UART logic level | 3.3 V or 5 V TTL, set by Vsel slide switch at "G" ("New! Selectable Switch 5V and 3.3V") | [UM] |
| Default Vsel | 5V ("Default Vsel is 5V") | [UM] |
| Standard interface | "Standard 6 pin interface: DTR, TX, RX, GND, CTS and VCC" | [UM] |
| VCC pin output | 3.3 V or 5 V, follows Vsel | [UM] |
| 5V pin (JP4/JP6) | Constant 5 V from USB, not affected by Vsel; "maximum current is limited from USB port, normally is 900mA" | [UM] |
| 5V pin max current (older revisions) | 250 mA (Rev2.0); 200 mA (Rev1.0) | [UM-R2][UM-R1] |
| Vsel output current (Rev2.0 only) | 5V: up to 250 mA; 3.3V: only 50 mA | [UM-R2] |
| Extra pins (JP4/JP6) | 5V, GND, CTS, DCD, DSR, RI, RX, RTS, DTR, TX | [UM] |
| LEDs | Power LED (green); FTDI TX indicator LED; FTDI RX indicator LED | [UM] |
| Bootloader compatibility | "Compatible with Bootloader for Arduino board such as BBFuino, Boarduino, Arduino Mini Pro, etc." | [UM] |
| Driver | "Plug and Play, driver is needed for 1st time user only"; FTDI driver | [UM] |
| Operating systems | "compatible for Window XP, Vista, Win 7, 8 and 10. It appears as Virtual COM port" | [UM] |
| Dimension (Rev3.0) | 4.4 cm x 2 cm | [UM] |
| Dimension (Rev2.0) | 3.9 cm x 2 cm | [UM-R2] |
| Packing list (Rev3.0) | 1 x UC00A Rev3.0; optional: USB Micro B cable | [UM] |
| Warranty | 6 months | [UM] |
| Warranty | 12 months | [PP] |
| Price | RM43.05 | [PP] |
| Baud rate range, supply current, operating temperature, VCC output current (Rev3.0), header pitch, weight | Not stated | [UM] |

Chip-vendor reference (context only, not a UC00A spec): FT232R datasheet v2.11 states 300 baud to 3 Mbaud at TTL level, USB 2.0 full speed, VCCIO 1.8–5.25 V, 3V3OUT up to 50 mA, royalty-free VCP and D2XX drivers for Windows/Mac/Linux, -40 to 85 °C, SSOP-28 [VEN]. The Rev3.0 schematic feeds the UART side from the Vsel switch output (+5V or +3V3 into VCCIO) [PP, schematic].

## Interfaces, terminals and pin mapping
### Board layout (Rev3.0, manual section 4.0) [UM]
| Label | Function | Src |
|---|---|---|
| A | MicroB USB socket — USB connection to PC | [UM] |
| B | Power LED (green) — lit once USB connection is ready | [UM] |
| C | Extra UART pins (JP4 and JP6); logic level follows Vsel; "5V" is always 5 V from USB | [UM] |
| D | FTDI's TX indicator LED — transmit activity from the FTDI chip / computer virtual COM port | [UM] |
| E | Standard 6-way header socket — "breakout of pins which are commonly used for loading program to Arduino PROMini, BBFuino, Fio and others" | [UM] |
| F | FTDI's RX indicator LED — receive activity | [UM] |
| G | Vsel: VCC and UART pin logic level (3.3 V or 5 V) selectable slide switch | [UM] |

### Standard 6-way header socket (manual section 5.1, table order) [UM]
| Label | Definition | Function | Src |
|---|---|---|---|
| DTR | Data Terminal Ready | "In Arduino compatible board, this pin is use for auto-reset." Marked Green on UC00A | [UM] |
| RXI | UART Receive pin | UC00A receiver; connect to the device's transmitter pin | [UM] |
| TXO | UART Transmit pin | UC00A transmitter; connect to the device's receiver pin | [UM] |
| VCC | 3.3 V or 5 V power output | Follows Vsel: 5V selected → 5 V, "and vice versa for 3.3V" | [UM] |
| CTS | Clear To Send | "Hardware Hand-shaking pin." | [UM] |
| GND | Ground | Ground of power and signal. Marked Black on UC00A | [UM] |

The Arduino Pro Mini wiring table in the manual lists the same six pins in the order DTR (Green), RX, TX, Vsel, CTS, GND (Black) — this matches the standard FTDI-cable/Pro Mini bootloader header order (GRN at one end, BLK at the other) [UM]. Pro Mini connection [UM]: DTR→RESET, RX→TXD, TX→RXD, Vsel/VCC→5V (or 3.3 V), CTS→GND, GND→GND.

### Extra UART pins JP4/JP6 (manual section 5.2) [UM]
| Label | Function | Src |
|---|---|---|
| 5V | Constant 5 V from USB; "optional for user to power external device"; not affected by Vsel; max current "limited from USB port, normally is 900mA" | [UM] |
| GND | Common ground | [UM] |
| CTS, DCD, DSR, RI, RTS, DTR | "unused under normal UART operation"; TTL level follows Vsel | [UM] |
| RX, TX | Second breakout of the UART receive/transmit pins; TTL level follows Vsel | [UM] |

### Voltage selection [UM]
- Vsel at "G" sets the TTL level of all interface pins (TX, RX, DTR, CTS, RTS, DSR) and the VCC pin voltage at "E": 5V → 5 V TTL and VCC = 5 V; 3V3 → 3.3 V TTL and VCC = 3.3 V [UM].
- "Default Vsel is 5V" [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Cross the data lines.** RXI ↔ target TX, TXO ↔ target RX, common GND; "No extra component is necessary" [UM].
- **Check Vsel before plugging into a 3.3 V board.** Default is 5V; UC00A Rev3.0 supports both 5 V and 3.3 V Pro Mini variants "but user must select the voltage from Vsel slide switch" [UM].
- **Match the GRN/BLK marks.** Green (DTR) on UC00A goes to the Pro Mini "GRN" (reset) pad; Black (GND) to "BLK" [UM]. Reversing the 6-way plug swaps DTR and GND.
- **Do not power application circuits from Vsel/VCC or 5V.** Caution: "'Vsel' and '5V' on UC00A is supply directly from USB of computer; it is advised not to use this power source to power application circuit or device. Wrong connection such as wrong polarity, wrong voltage, shorted might permanently damage computer." [UM] The "normally is 900mA" figure is the USB port's limit, not a UC00A rating [UM].
- **Flow control = none** in terminal software for ordinary UART devices [UM]. CTS/RTS/DSR/DCD/RI are "unused under normal UART operation" [UM].
- **Driver once.** Install the FTDI driver (Win/Mac/Linux links in the manual) before the COM port appears [UM]. OS list stated: Windows XP, Vista, 7, 8, 10 [UM].
- **TX/RX LEDs reflect the FTDI chip / virtual COM activity** and work only when connected to a PC [UM].
- **Name the revision.** Rev1.0 (2008) and Rev2.0 (2012) have different connectors, voltage options and current limits — see Revision differences. Document Rev3.0 as the current product [UM].

### Revision differences [UM][UM-R2][UM-R1]
| Item | Rev1.0 (UM V1.0, Oct 2008) | Rev2.0 (UM V1.0, July 2012) | Rev3.0 (UM V1.1, Dec 2018, current) |
|---|---|---|---|
| USB connector | USB A type male plug on the board | Mini USB socket | Micro-B socket |
| Logic / power levels | 5 V only | 3.3 V or 5 V via "Vsel" solder pad/jumper (label H) | 3.3 V or 5 V via Vsel slide switch (label G) |
| Microcontroller interface | 4-way 2510 header pin: +, -, TX, RX | 4-way 2510 connector (Vsel, GND, TX, RX) + 6-way header socket + extra RS232 pin pads (JP4/JP6) | 6-way header socket (DTR, RXI, TXO, VCC, CTS, GND) + extra UART pins JP4/JP6; no 4-way 2510 |
| Extra modem pins | CTS, RTS, DTR, DSR on a 2x5 solderable pad | 5V, GND, CTS, DCD, DSR, RI, RX, RTS, DTR, TX pads | same set as Rev2.0 |
| 5V output max | 200 mA | 250 mA (Vsel at 3.3V: only 50 mA) | "limited from USB port, normally is 900mA" |
| Absolute max TX/RX | 0–5.5 V (Rev1.0 table) | not stated | not stated |
| LEDs | red (USB TX) and yellow (USB RX) | Power (green), TX, RX | Power (green), FTDI TX, FTDI RX |
| OS stated | Windows XP, Vista | Windows XP, Vista, 7 | Windows XP, Vista, 7, 8, 10 |
| Packing | board + 2510 4-way connector + 4 iron pins | board + 2510 4-way connector + 4 terminal pins | board only (Micro-B cable optional) |
| Dimension | not stated | 3.9 cm x 2 cm | 4.4 cm x 2 cm |

## Power and electrical limits
- Supply: USB bus power only; no external supply input [UM].
- VCC pin: 3.3 V or 5 V, follows Vsel [UM]. Current limit for Rev3.0: not stated [UM] (Rev2.0 stated 250 mA at 5V / 50 mA at 3.3V [UM-R2] — do not apply to Rev3.0 without confirmation).
- 5V pin: constant 5 V from USB; limit is the USB port's, "normally is 900mA" [UM].
- Absolute maximum ratings for Rev3.0: not stated [UM]. (Rev1.0 only: TX/RX 0–5.5 V max [UM-R1].)
- Caution on damage to the host computer from wrong polarity, wrong voltage or shorts on Vsel/5V [UM].

## Software support
- Appears as a Virtual COM port; works with HyperTerminal-style terminals and the Arduino IDE for bootloader uploads [UM].
- FTDI drivers: manual links "Driver Installation Guide" and "Driver Installation Guide for Win 7" (https://drive.google.com/file/d/12HDo0o2ygGj9s0I90drnNp0FnFZG2jAx/view), FTDI install guides http://www.ftdichip.com/Support/Documents/InstallGuides.htm and drivers http://www.ftdichip.com/FTDrivers.htm for Win/Mac/Linux [UM]. (Record only; not downloaded.)
- Vendor: FT232R has royalty-free VCP and D2XX drivers [VEN] — context only.
- No Cytron library or GitHub repository stated [UM].

## Compatibility and accessories
- Targets stated: "any device which offer 3.3V/5V UART interface, this includes microcontroller, RFID reader, XBee, Bluetooth, WiFi, wireless module and more" [UM].
- Program loading stated for: Arduino Pro Mini, Arduino FIO, ArduPilot, Rainbow LED Ring V3, BBFuino; bootloader-compatible with BBFuino, Boarduino, Arduino Mini Pro [UM]. Cytron boards named: BBFuino (and SKPS as a UART device example) [UM]. No current Cytron board (Maker UNO, Maker Nano, etc.) is named — do not claim them without a source.
- PC-to-PC link: two UC00A boards cross-wired RXI↔TXO, TXO↔RXI, GND↔GND with male-to-male jumper wires, same baud on both PCs [UM].
- Cable: USB Micro-B cable, optional, not included [UM].
- Not supported / not stated: RS232 levels (TTL only; the manual's introduction explains the DB9/RS232 case needs a level shifter) [UM]; external power input (none) [UM]; 4-way 2510 cable of Rev1.0/2.0 (no 2510 connector on Rev3.0) [UM].

## Common mistakes / troubleshooting
- No COM port → FTDI driver not installed; install once, re-plug; find the port under Device Manager → Ports (COM & LPT) → "USB Serial Port" [UM].
- Garbage or nothing in terminal → baud mismatch; "Bits per second must be same with [device] Baud Rate and Flow control must be set to none" [UM].
- Pro Mini upload fails → plug reversed (GRN/BLK), or wrong Vsel for a 3.3 V Pro Mini [UM].
- 3.3 V device damaged → Vsel left at the 5V default [UM].
- Computer USB port shuts down or board resets → load on VCC/5V too high or shorted; USB-port limited, manual advises against powering circuits from it [UM].
- Using a Rev2.0 tutorial on a Rev3.0 board → Rev2.0 has a Vsel solder jumper and a 4-way 2510 connector; Rev3.0 has a slide switch and no 2510 connector [UM][UM-R2].
- Typing is not echoed locally → enable "Echo typed characters locally" in the terminal's ASCII setup [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Warranty | [UM] Rev3.0 manual (Dec 2018): "valid for 6 months" | [PP] product page (2026-10-16): 12 months | [UM] outranks [PP] in the text, but the product page is newer and is the sale term shown to buyers; state both and confirm with Cytron |
| 5V pin maximum current | [UM] Rev3.0: "limited from USB port, normally is 900mA" | [UM-R2] 250 mA; [UM-R1] 200 mA | Rev3.0 manual wins for the current board; the older figures apply to their revisions. 900 mA is a USB-port figure, not a board rating |
| Pin labels on the 6-way socket | [UM] section 5.1: RXI / TXO | [UM] section 7.3 wiring table: RX / TX | Same pins; RXI/TXO are the silkscreen-style labels in the spec table |
| USB chip identity | [UM] "FTDI chip" | [PP] schematic: FT232RL; [PP] links FT232RL datasheet | No conflict; FT232RL is the specific part shown |
| Extra-pin naming | [UM] Rev3.0: "Extra UART pin" | [UM-R2] "Extra RS232 pin" | Same pads; they are TTL-level modem-control lines, not RS232 levels |

## Needs verification
- Baud rate range supported on UC00A Rev3.0 — not stated [UM]; FT232R vendor figure 300 baud–3 Mbaud [VEN] not confirmed by Cytron.
- VCC pin output current at 5 V and at 3.3 V on Rev3.0 — not stated [UM]; Rev2.0's 250 mA / 50 mA may or may not carry over (the 3.3 V rail source on Rev3.0 is the FT232RL 3V3OUT per the schematic, which the vendor rates at 50 mA [VEN] — confirm with design team [DT]).
- Whether the Rev3.0 warranty is 6 months or 12 months — [UM] vs [PP] conflict.
- Physical left-to-right order and keying of the 6-way socket — figures did not extract; the table order and GRN/BLK marks are stated [UM].
- Windows 11 / current macOS / Linux support — manual lists XP to Windows 10 only [UM].
- Supply current, operating temperature, absolute maximum ratings for Rev3.0 — not stated [UM].
- Which current Cytron boards it programs — only BBFuino named [UM]; confirm with design team before naming others.
- Date the Rev3.0 hardware was released — schematic dated 3/14/2016, manual V1.1 December 2018; no release date stated.
- Product page body text was not read by this agent (page read by the coordinator) [PP].

## Sources
- [UM] UC00A Rev3.0 Cytron USB to UART Converter User's Manual, V1.1, December 2018 — https://docs.google.com/document/d/1pFK7DSRuZB7SeP3aCmjYzWB0i7aT-C_W_D-x25WLops/view (Google Doc; figures did not extract)
- [UM-R2] UC00A Rev2.0 Cytron USB to UART Converter User's Manual, V1.0, July 2012 — https://docs.google.com/document/d/1NzYIGVAZ6Ag8efs4lL3g3SEAHSsp9qsj3M6aJMoFAIk/view
- [UM-R1] UC00A User's Manual (Rev1), V1.0, Oct 2008 (PDF "UC00A User's Manual (Rev1).pdf") — https://drive.google.com/file/d/0BxAdRu9AxxJuRHhIckVlak1NNUk/view
- [PP] schematic "UC00A R3 Schematic.pdf" (UC00A R3.sch, 3/14/2016; shows FT232RL, Vsel switch S1 selecting +5V/+3V3) — https://drive.google.com/file/d/15aQuzmaxM7FiHtMJkuptoebEAMuz-Wip/view
- [PP] Product page https://my.cytron.io/p-uc00a-ftdi-usb-to-uart-converter (read by coordinator 2026-10-16: RM43.05, in stock 274, warranty 12 months)
- [UM] Driver Installation Guide for Win 7 (linked from manual; not opened) — https://drive.google.com/file/d/12HDo0o2ygGj9s0I90drnNp0FnFZG2jAx/view
- [VEN] FTDI FT232R USB UART IC Datasheet, Document No. FT_000053, Version 2.11 — https://www.ftdichip.com/Support/Documents/DataSheets/ICs/DS_FT232R.pdf (product page link; fetch failed here, read via mirror https://www.digikey.ca/en/resources/datasheets/ftdi/ft232r)
