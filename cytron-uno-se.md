# Cytron UNO Special Edition - Arduino Compatible — Verified Reference

| | |
|---|---|
| Product code | `CT-UNO-SE` (my.cytron.io product-page image paths use CT-UNO-SE [PP]) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: full product page read; it states the SE is "exactly the same as CT-UNO, with the special side connectors", so the CT-UNO manual applies. Dimension drawing added |
| Primary source | **Product page description** (read in full 2026-10-19): "CT-UNO-SE is exactly the same as CT-UNO, with the special side connectors" [PP] — so the **CT-UNO User's Manual** applies:  "CT UNO (Arduino Uno Compatible)", V1.0, Nov 2014** (Cytron Technologies Sdn Bhd) — the only document the Special Edition product page links (with the CT-UNO Schematic). The manual itself never mentions a Special Edition; no SE datasheet, SE manual or newer revision was found on Drive or the web |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = my.cytron.io product page — name, price, stock, warranty and links read 2026-10-16; the full description, feature list, resources and the "CT-UNO-SE Dimensions" drawing read 2026-10-19. [PP: photo] = product photo CT-UNO-SE_b (what the picture shows, not a written spec). [UM] = the CT-UNO User's Manual linked from this product page (read in full from Google Drive 2026-10-16). The CT-UNO Schematic PDF returned no text and could not be downloaded here. No [DS], [DT], [GH] or [3P] source names the Special Edition — web searches for "Cytron UNO Special Edition" and "CT-UNO-SE" found only CT-UNO and Maker UNO pages.

**Read this first — what is confirmed for the Special Edition (2026-10-19):**
- The product page answers the main question: "CT-UNO-SE comes with special side connectors to enable it to be stacked on TOP or at the Bottom of a shield. Basically CT-UNO-SE is Arduino UNO R3 with special side connectors. CT-UNO-SE is exactly the same as CT-UNO, with the special side connectors." [PP]
- So the CT-UNO User's Manual specs below apply to CT-UNO-SE, and the companion file `cytron-uno.md` covers the board itself. Only the side connectors are SE-specific.
- The product page feature list repeats the CT-UNO manual figures and adds "Special version of side connector (CT-UNO-SE only)" [PP].

## What it is
An Arduino UNO R3-compatible board sold by Cytron as "Cytron UNO Special Edition - Arduino® Compatible" (code CT-UNO-SE) [PP]. It is the Cytron UNO (CT-UNO) with "special side connectors" that let it be stacked on top of, or at the bottom of, a shield [PP]. Cytron documents it with the CT-UNO User's Manual and schematic [PP]. The product page points beginners and students to Maker UNO instead [PP].

## Specifications
SE-specific facts [PP]:

| Item | Value | Src |
|---|---|---|
| Product name | Cytron UNO Special Edition - Arduino Compatible | [PP] |
| Product code | CT-UNO-SE | [PP] |
| Price | RM63.00 (Cytron product page, read 2026-10-16) | [PP] |
| Stock | In stock (76), 2026-10-16 | [PP] |
| Warranty | 12 months | [PP] |
| Linked documents | CT-UNO User's Manual; FTDI Drivers Download; CT-UNO Schematic; CT-UNO Fritzing File; Arduino IDE Download; tutorials incl. "Introducing CT-UNO", "Using ISP to Burn Bootloader into Arduino", "Micro-B Peeled off?" | [PP] |
| What is "special" | Special side connectors to stack the board on top of or at the bottom of a shield; "Special version of side connector (CT-UNO-SE only)" | [PP] |
| Relation to CT-UNO | "exactly the same as CT-UNO, with the special side connectors" | [PP] |
| Side connectors (photo) | Product photo shows the board with four separate long-leg stacking headers (pin counts look like 6, 8, 8 and 10 — matching the UNO R3 header set) | [PP: photo] |
| Dimensions | 68.58 mm × 55.88 mm board outline; 4 × Ø3 mm mounting holes (CT-UNO-SE Dimensions drawing) | [PP] |
| Memory (feature list) | 32KByte Flash, SRAM 2KByte, EEPROM 1KByte, 16MHz | [PP] |
| Suggested accessories | USB Micro B Cable; Adapter 12V 1A (UK Plug) | [PP] |

Specifications in the linked CT-UNO User's Manual V1.0 — they apply to CT-UNO-SE because the product page says it is "exactly the same as CT-UNO" apart from the side connectors [PP]:

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
The linked CT-UNO manual's board layout (A Reset Button, B Micro USB B connector, C RX LED, D TX LED, E Programmable LED on pin 13, F Power LED, G 2.1 mm Adapter Socket, H Extra Pads, I Arduino R3 Standard Header, J ISP Header Pin) is the layout Cytron publishes for this product [UM][PP]; the SE is the same board with side connectors [PP]. The CT-UNO-SE Dimensions drawing shows the R3 header labels (GND, 13–8, 7–0 with TX/RX; IOREF, RESET, 3V3, 5V, GND, GND, Vin; A0–A5), "Cytron UNO SE" silkscreen, a 68.58 × 55.88 mm outline and 4 × Ø3 mm holes [PP]. See /home/claude/kb/cytron-uno.md for the full layout.

## Rules and gotchas (for code, wiring and tutorials)
- **The only difference from CT-UNO is the side connectors** (stack on top of or below a shield) [PP]. Do not invent other differences (USB chip, regulator, PCB colour are the same as CT-UNO).
- Do not describe the side-connector type, pin length or whether they come soldered — the page states none of it; the photo suggests loose stacking headers (see Needs verification).
- Setup steps (CT-UNO manual, valid for SE): board "Arduino Uno" in Tools > Board, FTDI VCP driver for the FT231X, select the COM port, upload Blink [UM].
- Do not use Maker UNO (CH340, no DC jack, pin LEDs, buzzer, button) facts for this board.
- Price differs from Cytron UNO: RM63.00 (SE) vs RM61.74 (CT-UNO), both [PP] 2026-10-16.
- For beginners or students, Cytron's own page points to Maker UNO [PP].

## Power and electrical limits
CT-UNO manual figures, valid for SE [UM][PP]: DC jack 7–15 V recommended, 6–20 V limits; USB power; adapter is chosen automatically when both are connected; 5V regulator 1 A max at Vin 12 V; 3.3V regulator 500 mA max; per-pin current — refer to the ATmega328P specification [UM]. The product page feature list gives the same "Input voltage: DC7-15V", 1A 5V regulator and 500mA 3.3V regulator [PP].

## Software support
- Linked CT-UNO manual: Arduino IDE, board "Arduino Uno", FTDI VCP driver from http://www.ftdichip.com/Drivers/VCP.htm, Optiboot bootloader re-flashable via ISP with an AVR programmer [UM].
- No SE-specific software, board package, MicroPython or CircuitPython support is stated.

## Compatibility and accessories
- Arduino UNO R3 shield compatible [UM][PP]; the side connectors let it sit on top of or under a shield [PP]. The manual suggests a 12V 2A adapter [UM]; the SE page suggests "Adapter 12V 1A (UK Plug)" and a USB Micro B cable [PP].
- Packing list for the SE: not stated in text; the product photo shows the board plus four separate stacking headers [PP: photo]; a customer review says it "Include side connector" (review, not a spec).
- Differences from a genuine Arduino UNO: as in the CT-UNO manual and the SE feature list — FT231X USB-serial, Micro-B, SMD MCU, 7–15 V input, LEDs moved to the edge, extra pads, white PCB [UM][PP] — plus the SE side connectors [PP].

## Common mistakes / troubleshooting
- Thinking the SE has different electronics — it is CT-UNO with side connectors [PP].
- Micro-B socket peeled off: Cytron's tutorial "Micro-B Peeled off?" shows how to load a program without the USB (linked from the product page) [PP].
- Confusing CT-UNO-SE with Maker UNO / Maker UNO Plus — different products.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Document coverage | [PP] SE product page links the CT-UNO User's Manual and says the SE is "exactly the same as CT-UNO, with the special side connectors" | [UM] manual covers "CT-UNO" only | **Resolved** — manual applies to SE |
| Suggested adapter | [UM] optional 12V 2A adapter | [PP] SE page suggests Adapter 12V 1A (UK Plug) | Both within 7–15 V; either works for the board alone |
| Price vs standard CT-UNO | [PP] CT-UNO-SE RM63.00 | [PP] CT-UNO RM61.74 | Both true; different products |

## Needs verification
- Side connectors: exact type (long-leg stackable female headers?), whether they ship loose or soldered, and the pin counts — only the product photo shows them.
- SE packing list in text (board + 4 stacking headers per the photo).
- CT-UNO Schematic contents (not readable here).

## Sources
- [PP] https://my.cytron.io/p-cytron-uno-special-arduino-compatible (price/stock 2026-10-16; full description, features, resources 2026-10-19)
- [PP] CT-UNO-SE Dimensions drawing — https://static.cytron.io/image/catalog/products/CT-UNO-SE/CT-UNO-SE%20Dimensions.png
- [PP: photo] CT-UNO-SE_b product photo (board + stacking headers)
- CT-UNO Fritzing File (folder, linked from the page) — (Cytron document — link not public)
- [UM] CT-UNO User's Manual (CT UNO (Arduino Uno Compatible), V1.0, Nov 2014) — https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view (public; read 2026-10-16)
- CT-UNO Schematic (not readable here) — https://drive.google.com/file/d/0BzFWfMiqqjyqTHlXdTlxaDU4bWM/view
- Companion KB file: /home/claude/kb/cytron-uno.md
