# TTL UART to RS232 Converter — Verified Reference

| Field | Value |
|---|---|
| Product code | URS232A [PP] |
| Family | USB and serial converters |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | Cytron product page "TTL UART to RS232 Converter" (https://my.cytron.io/p-ttl-uart-to-rs232-converter), read by the coordinator 2026-10-19 [PP]. No Cytron datasheet or user manual was found. The linked "URS232A Schematic.pdf" (Drive, 1 Feb 2016) exists, but only its title block could be extracted as text and the PDF could not be downloaded to view, so it is **not** used as [DS-schematic]. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: untagged facts are from the product page as read by the coordinator on 2026-10-19 [PP]. [VEN] = Texas Instruments MAX232 datasheet SLLS047N (Feb 2024), used for chip-level context only — Cytron does not state which maker's MAX232 is fitted.  = cross-reference to the UC00A / UC00C KB files.

## What it is
A level-shifter board that sits between a microcontroller's TTL UART and an RS232 (DB9) device such as a GSM modem or RFID reader [PP]. It uses the MAX232 and comes pre-soldered with a male DB9 connector, the MAX232 and its capacitors [PP]. Cytron states it can be used with UC00A or UC00C to make a USB-to-RS232 converter [PP].

## Specifications
The product page has no numeric specification table; its Features list is reproduced in full.

| Item | Value | Src |
|---|---|---|
| Function | Level shifter between microcontroller TTL UART and RS232 (DB9) devices | [PP] |
| Level-shifter IC | MAX232 | [PP] |
| RS232 connector | DB9-Male (PC side) | [PP] |
| Signals supported | Tx, Rx, CTS and RTS | [PP] |
| Works with | UC00A or UC00C (to make a USB-to-RS232 converter) | [PP] |
| Assembly | Pre-soldered: male DB9 connector, MAX232 and capacitors | [PP] |
| Warranty | 12 months | [PP] |
| Supply voltage, supply current | Not stated | [PP] |
| TTL-side logic level (3.3 V / 5 V) | Not stated | [PP] |
| Baud rate range | Not stated | [PP] |
| TTL-side connector type and pin order | Not stated | [PP] |
| Dimensions, weight | Not stated | [PP] |

Chip-level context only (not a URS232A spec) [VEN]: TI MAX232 "Operates from a single 5V power supply with 1µF charge-pump capacitors", "Operates up to 120kbit/s", "Two drivers and two receivers", "±30V Input levels", "Low supply current: 8mA typical"; recommended VCC 4.5 V min, 5 V nom, 5.5 V max.

## Interfaces, terminals and pin mapping
- **RS232 side:** DB9 male connector, described as "PC side" [PP]. DB9 pin assignment is not given in text.
- **TTL (microcontroller) side:** supports Tx, Rx, CTS and RTS [PP]. Connector type, pin labels and order, and power pins are not stated in text. Do not draw a header pinout as Cytron fact.
- **Schematic:** "URS232A Schematic.pdf" (title block: URS232A.sch, Sheet 1/1, dated 1/2/2016) is linked from the product page [PP]; its drawing could not be read here (see Needs verification).
- Two driver + two receiver channels in the MAX232 [VEN] match the four signals Cytron lists (Tx, Rx, CTS, RTS) — consistent, but Cytron's own channel mapping is in the unread schematic.

## Rules and gotchas (for code, wiring and tutorials)
- **TTL to RS232 crossover:** name signals from the point of view stated on the board silkscreen; the product page does not say whether the TTL-side "Tx" is an input from the MCU's TX or an output to the MCU's RX. Show wiring by label from a photo of the actual board, or flag it as unverified.
- **Do not claim 3.3 V MCU compatibility.** Cytron does not state the supply or logic level. The MAX232 is a 5 V part [VEN]; whether the board's receiver outputs are safe for a 3.3 V UART is not stated.
- **USB-to-RS232 with UC00A / UC00C** is a Cytron-stated use [PP]. Cross-reference :
  - UC00A Rev3.0 6-way socket has DTR, TX, RX, GND, CTS, VCC; RTS is only on its extra pads JP4/JP6 [KB uc00a.md].
  - UC00C's 6-way socket has DTR, RX, TX, VCC, CTS, GND and **no RTS** pin [KB uc00c.md] — RTS hardware handshake to URS232A is not available from UC00C as documented.
  - Set the UC00A/UC00C Vsel to 5V if the URS232A needs 5 V (its supply is not stated; the MAX232 itself is 5 V [VEN]) — flag as unverified in tutorials.
- **DB9 "Male (PC side)"**: the board presents the same gender as a PC serial port [PP]. Whether a straight-through or null-modem cable is needed depends on the far device; Cytron gives no cable guidance.
- Flow control: CTS/RTS are supported [PP]; for devices that do not use them, set flow control to none in terminal software (general practice; Cytron gives no setting).
- The Cytron "Serial Loopback Test" tutorial linked from the product page now returns 404 — do not link it.

## Power and electrical limits
- Supply voltage, current draw and logic level: not stated [PP].
- MAX232 chip: recommended VCC 4.5–5.5 V, 8 mA typical supply current [VEN] — chip context only.
- No reverse-polarity or ESD rating for the board is stated [PP].

## Software support
- None needed on the board; it is a transparent level shifter [PP]. Use any serial terminal or UART library on the host at the far device's baud rate.
- Product page links a Fritzing part [PP] (not opened).

## Compatibility and accessories
- Example RS232 devices named by Cytron: GSM modem, RFID reader [PP].
- Pairs with Cytron UC00A or UC00C for USB-to-RS232 [PP]; see  notes above on RTS availability.
- Package: board with pre-soldered male DB9 connector, MAX232 and capacitors [PP]. Cables, headers or jumper wires are not stated as included.

## Common mistakes / troubleshooting
- No data at all → TTL Tx/Rx swapped; or baud rate/format mismatch with the RS232 device (general practice — no Cytron troubleshooting text exists).
- Works with UC00A but hardware handshake fails with UC00C → UC00C has no RTS pin on its socket [KB uc00c.md].
- Cannot mate with a PC's serial port directly → both are male DB9 ("PC side") [PP]; a female-female (null-modem or gender-changer) cable is needed — general practice, not Cytron-stated.
- Garbage characters at correct baud → check that the far device is truly RS232-level, not TTL (a TTL device needs no MAX232) [PP description implies RS232 devices only].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Features | [PP] MAX232; DB9-Male (PC side); works with UC00A/UC00C; Tx, Rx, CTS, RTS | [3P] RobotShop (Manufacturer # URS232A): same list | No conflict |
| Operating voltage | [PP] not stated | A Korean manual for "ET-URS232" (LK Embedded, V03 2013) says DC 3.3–5V | Different product from a different maker — not used for URS232A |

## Needs verification
- Supply voltage and current; whether 3.3 V logic hosts are supported — read the schematic or ask Cytron [DT].
- TTL-side connector type, pin labels and order (including VCC/GND), and Tx/Rx direction naming.
- DB9 pin assignment and which DB9 pins carry RTS/CTS.
- Whether the fitted chip is MAX232 or MAX232A/MAX202 equivalent (affects capacitor values and max baud) — product page only says MAX232.
- Board dimensions and mounting holes.
- Readable copy of "URS232A Schematic.pdf" (Drive 0BzFWfMiqqjyqMFMzdTVJN0pmM0U): the Drive text tool returns only the title block; direct download is blocked here.

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM22.05, availability 158, warranty 12 months, description and Features list) — https://my.cytron.io/p-ttl-uart-to-rs232-converter
- [PP] "URS232A Schematic.pdf" (title block "URS232A.sch (Sheet: 1/1)", 1/2/2016; drawing not readable here) — https://drive.google.com/file/d/0BzFWfMiqqjyqMFMzdTVJN0pmM0U/view
- [VEN] Texas Instruments MAX232 datasheet, SLLS047N, revised February 2024 (chip context only) — https://www.ti.com/lit/ds/symlink/max232.pdf
- [3P] (cross-check only) RobotShop, Manufacturer # URS232A, SKU RB-Cyt-190 — https://www.robotshop.com/products/cytron-rs232to-uart-converter
- Not used (different product): LK Embedded "UART TO RS232 통신모듈 매뉴얼" ET-URS232 V03 — https://www.icbanq.com/icdownload/V2_DATA/ICBShop/Board/매뉴얼_UARTtoRS232통신모듈_(URS232)_13_0708.pdf
- Product-page tutorial "Serial Loopback Test" — returns 404 on my.cytron.io (2026-10-19); not read.
