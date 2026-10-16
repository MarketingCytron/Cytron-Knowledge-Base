# Cytron UNO Special Edition - Arduino Compatible — Verified Reference

| | |
|---|---|
| Product code | `CT-UNO-SE` (my.cytron.io product-page image paths use CT-UNO-SE [PP]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **CT-UNO User's Manual, "CT UNO (Arduino Uno Compatible)", V1.0, Nov 2014** (Cytron Technologies Sdn Bhd) — the only document the Special Edition product page links (with the CT-UNO Schematic). **The manual never mentions a Special Edition or CT-UNO-SE.** No SE datasheet, SE manual or newer revision was found on Drive or the web |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = my.cytron.io product page facts read by the coordinator on 2026-10-16 (name, price, stock, warranty, linked documents, product code in image paths). [UM] = the CT-UNO User's Manual linked from this product page (read in full from Google Drive 2026-10-16). The CT-UNO Schematic PDF returned no text and could not be downloaded here. No [DS], [DT], [GH] or [3P] source names the Special Edition — web searches for "Cytron UNO Special Edition" and "CT-UNO-SE" found only CT-UNO and Maker UNO pages.

**Read this first — what is confirmed for the Special Edition:**
- Confirmed for CT-UNO-SE itself [PP]: product name "Cytron UNO Special Edition - Arduino Compatible"; product code CT-UNO-SE; price RM63.00; in stock (76) on 2026-10-16; warranty 12 months; its product page links the CT-UNO User's Manual and CT-UNO Schematic.
- Everything technical below comes from the CT-UNO manual that Cytron links for this product. It is Cytron's only published documentation for the SE, but the manual is written for CT-UNO and **does not say the SE is identical**. Any feature that makes it "Special" is **not stated in any source read**.

## What it is
An Arduino-compatible board sold by Cytron as "Cytron UNO Special Edition - Arduino Compatible" (code CT-UNO-SE) [PP]. Its product page documents it with the CT-UNO (Cytron UNO) User's Manual and schematic [PP]; how the Special Edition differs from the standard Cytron UNO (CT-UNO) is not stated in any source read.

## Specifications
SE-specific facts [PP]:

| Item | Value | Src |
|---|---|---|
| Product name | Cytron UNO Special Edition - Arduino Compatible | [PP] |
| Product code | CT-UNO-SE | [PP] |
| Price | RM63.00 (Cytron product page, read 2026-10-16) | [PP] |
| Stock | In stock (76), 2026-10-16 | [PP] |
| Warranty | 12 months | [PP] |
| Linked documents | CT-UNO User's Manual; CT-UNO Schematic | [PP] |

Specifications in the linked CT-UNO User's Manual V1.0 (written for CT-UNO; **not confirmed to apply unchanged to CT-UNO-SE**):

| Item | Value (CT-UNO manual) | Src |
|---|---|---|
| Input Voltage via Adapter (Recommended) | 7–15 V | [UM] |
| Input Voltage via Adapter (Limits) | 6–20 V | [UM] |
| IMAX (5V), on-board 5V regulator | 1 A max, "With Vin at 12V" | [UM] |
| IMAX (3.3V), on-board 3.3V regulator | 500 mA max | [UM] |
| Microcontroller | SMD ATmega328 (ATmega328p in spec section) with Optiboot (UNO) bootloader | [UM] |
| USB-serial | FTDI FT231X | [UM] |
| USB connector | USB Micro-B socket | [UM] |
| DC jack | Adapter Socket (2.1mm) | [UM] |
| I/O levels | 0-5V digital outputs with 3.3V compatible inputs | [UM] |
| I/O | 14 digital I/O (6 PWM), 6 analog inputs; UART, SPI, external interrupts, I2C | [UM] |
| Flash / clock | 32k Flash, 16MHz | [UM] |
| LEDs | RX, TX, Power (green), programmable LED on pin 13 (active HIGH) | [UM] |
| Buttons | Reset button | [UM] |
| Other | ISP 6-pin header; extra pads for strip/donut board; R3 standard headers; white PCB | [UM] |

## Interfaces, terminals and pin mapping
The linked CT-UNO manual's board layout (A Reset Button, B Micro USB B connector, C RX LED, D TX LED, E Programmable LED on pin 13, F Power LED, G 2.1 mm Adapter Socket, H Extra Pads, I Arduino R3 Standard Header, J ISP Header Pin) is the only layout Cytron publishes for this product [UM][PP]. Whether the SE board follows it exactly is not stated. See /home/claude/kb/cytron-uno.md for the full layout.

## Rules and gotchas (for code, wiring and tutorials)
- **Do not invent the "Special" features.** No source read says what is special — not the PCB colour, USB chip, connector, regulator or headers.
- **Do not state that CT-UNO-SE is identical to CT-UNO**; say "Cytron documents it with the CT-UNO User's Manual".
- When writing setup steps, the linked manual's procedure is: board "Arduino Uno" in Tools > Board, FTDI VCP driver for the FT231X, select the COM port, upload Blink [UM]. Flag in content that this comes from the CT-UNO manual.
- Do not use Maker UNO (CH340, no DC jack, pin LEDs, buzzer, button) facts for this board.
- Price differs from Cytron UNO: RM63.00 (SE) vs RM61.74 (CT-UNO), both [PP] 2026-10-16.

## Power and electrical limits
Only the CT-UNO manual gives figures (not confirmed for SE): DC jack 7–15 V recommended, 6–20 V limits; USB power; adapter is chosen automatically when both are connected; 5V regulator 1 A max at Vin 12 V; 3.3V regulator 500 mA max; per-pin current — refer to the ATmega328P specification [UM]. No SE-specific power figure is stated.

## Software support
- Linked CT-UNO manual: Arduino IDE, board "Arduino Uno", FTDI VCP driver from http://www.ftdichip.com/Drivers/VCP.htm, Optiboot bootloader re-flashable via ISP with an AVR programmer [UM].
- No SE-specific software, board package, MicroPython or CircuitPython support is stated.

## Compatibility and accessories
- Linked CT-UNO manual: Arduino UNO R3 shield compatible; optional 12V 2A AC to DC Adapter and USB Micro B cable [UM]. Not confirmed separately for SE.
- Packing list for the SE: [NOT STATED] (the CT-UNO manual lists "1 x CT-UNO board").
- Differences from a genuine Arduino UNO: only as in the CT-UNO manual (FT231X USB-serial, Micro-B, SMD MCU, 7–15 V input, LEDs at edge, extra pads, white PCB) — not confirmed for SE.

## Common mistakes / troubleshooting
- Treating "Special Edition" as a known spec difference — no source states one.
- Quoting the CT-UNO packing list, PCB colour or dimensions as SE facts without the CT-UNO-manual caveat.
- Confusing CT-UNO-SE with Maker UNO / Maker UNO Plus — different products.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Document coverage | [PP] SE product page links the CT-UNO User's Manual as its document | [UM] manual covers "CT-UNO" only; no Special Edition mention | Manual specs reported with a caveat; SE-specific differences listed as not stated |
| Price vs standard CT-UNO | [PP] CT-UNO-SE RM63.00 | [PP] CT-UNO RM61.74 | Both true; different products |

## Needs verification
- What makes the Special Edition "special" — hardware, PCB colour, bundled items or anything else (ask Cytron product team [DT]).
- Whether all CT-UNO manual specs (FT231X, 7–15 V DC jack, 1 A 5V regulator, white PCB, LED positions) apply to CT-UNO-SE.
- SE packing list, dimensions and photos-based features (product page description beyond price/stock/warranty was not available to this agent).
- CT-UNO Schematic contents (not readable here).

## Sources
- [PP] https://my.cytron.io/p-cytron-uno-special-arduino-compatible (facts read by coordinator 2026-10-16)
- [UM] CT-UNO User's Manual (CT UNO (Arduino Uno Compatible), V1.0, Nov 2014) — https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view (public; read 2026-10-16)
- CT-UNO Schematic (not readable here) — https://drive.google.com/file/d/0BzFWfMiqqjyqTHlXdTlxaDU4bWM/view
- Companion KB file: /home/claude/kb/cytron-uno.md
