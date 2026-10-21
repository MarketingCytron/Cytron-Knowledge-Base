# TTL UART to RS232 Converter — Verified Reference

| Field | Value |
|---|---|
| Product code | URS232A [PP] |
| Family | USB and serial converters |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron schematic "URS232A Schematic.pdf" (URS232A.sch, Sheet 1/1, dated 1/2/2016; project folder "URS232A (UART to RS232 Converter)") downloaded through the Google Drive connector and rendered at 500 dpi, so every pin line could be followed. Settled: JP1 pin order (1 RX_TTL, 2 TX_TTL, 3 GND, 4 +5V), JP2 pin order (1 GND, 2 CTS_TTL, 3 +5V, 4 RX_TTL, 5 TX_TTL, 6 RTS_TTL), DB9 pins (2 RX, 3 TX, 7 RTS, 8 CTS, 5 GND, 4–6 tied, 1 and 9 not connected). The document confirms a TTL UART-to-RS232 board, not a USB converter (see *Conflicts*). Schematic re-tagged [DT] (Cytron design file). Raised Medium → Medium-high; still open: supply current, baud limit, board dimensions, fitted chip maker. Earlier: 2026-10-19 master-table review — same schematic read visually through the Drive viewer plus the product photo (5 V-only supply, MAX232 with five 1 µF capacitors, signal directions, DB9 pin 5 = GND) |
| Primary source | Cytron product page "TTL UART to RS232 Converter" (https://my.cytron.io/p-ttl-uart-to-rs232-converter), read by the coordinator 2026-10-19 [PP]. No Cytron datasheet or user manual was found. Wiring and pin facts come from the Cytron schematic "URS232A Schematic.pdf" (URS232A.sch, Sheet 1/1, 1/2/2016), read in full at high resolution on 2026-10-21 [DT] — https://drive.google.com/file/d/0BzFWfMiqqjyqMFMzdTVJN0pmM0U/view?resourcekey=0-brRs0cMxhpw77OpeXPLsJw |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: untagged facts are from the product page as read by the coordinator on 2026-10-19 [PP]. [DT] = Cytron schematic "URS232A Schematic.pdf" (title block: Product Code URS232A, Date 1/2/2016 3:06 PM, Sheet 1/1, REV field blank; footer path "Cytron SVN\URS232A (UART to RS232 Converter)\PCB and Schematic\Project\URS232A.sch"), one page — a Cytron design file, so tagged [DT] (it was tagged [DS-schematic] on 2026-10-19). [VEN] = Texas Instruments MAX232 datasheet SLLS047N (Feb 2024), used for chip-level context only — Cytron does not state which maker's MAX232 is fitted.  = cross-reference to the UC00A / UC00C KB files.

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
| Supply voltage | **+5 V only** — MAX232 VCC on the +5V net; no regulator on the board | [DT] |
| Supply current | Not stated | [PP] |
| Charge-pump / decoupling capacitors | 5 × 1 µF (C1–C5) | [DT] |
| TTL-side logic level (3.3 V / 5 V) | Not stated | [PP] |
| Baud rate range | Not stated | [PP] |
| TTL-side headers | JP1 4-way: 1 RX_TTL, 2 TX_TTL, 3 GND, 4 +5V; JP2 6-way: 1 GND, 2 CTS_TTL, 3 +5V, 4 RX_TTL, 5 TX_TTL, 6 RTS_TTL (schematic pin numbers; check the board silkscreen for which end is pin 1) | [DT] |
| RS232-side pins used | DB9 (JP3) 2 RX, 3 TX, 5 GND, 7 RTS, 8 CTS; 4 and 6 tied together; 1 and 9 not connected | [DT] |
| Bill of materials (schematic) | U3 MAX232 (symbol MAX232PTH), C1–C5 1 µF, JP1, JP2, JP3 (DB9) — no USB chip, no regulator, no LED | [DT] |
| On-board connector photo | White 4-way polarised connector + 6-way header row (JP2), male DB9 | [PP: photo] |
| Dimensions, weight | Not stated | [PP] |

Chip-level context only (not a URS232A spec) [VEN]: TI MAX232 "Operates from a single 5V power supply with 1µF charge-pump capacitors", "Operates up to 120kbit/s", "Two drivers and two receivers", "±30V Input levels", "Low supply current: 8mA typical"; recommended VCC 4.5 V min, 5 V nom, 5.5 V max.

## Interfaces, terminals and pin mapping
- **RS232 side:** DB9 male connector (JP3), described as "PC side" [PP]. DB9 pins from the schematic [DT]:

| DB9 pin | Net | MAX232 pin | Direction (board view) |
|---|---|---|---|
| 2 | RX | R1IN (13) | Input from the far device |
| 3 | TX | T1OUT (14) | Output to the far device |
| 5 | GND | GND (15) | Ground |
| 7 | RTS | T2OUT (7) | Output to the far device |
| 8 | CTS | R2IN (8) | Input from the far device |
| 4 and 6 | tied to each other (DTR–DSR loop-back) | — | — |
| 1, 9 | not connected | — | — |

  This is the standard PC (DTE) pin-out, which matches Cytron's "PC side" wording. The DB9 shell lugs (G1, G2) have no wire drawn to GND in the schematic [DT].
- **TTL (microcontroller) side** [DT]:

| Net | Direction (board view) | MAX232 pin | Connect to MCU |
|---|---|---|---|
| RX_TTL | **Input** to the board | T1IN (11) → T1OUT (14) → DB9 | MCU **TX** |
| TX_TTL | **Output** from the board | R1OUT (12) ← R1IN (13) ← DB9 | MCU **RX** |
| RTS_TTL | Input to the board | T2IN (10) → T2OUT (7) → DB9 RTS | MCU RTS output |
| CTS_TTL | Output from the board | R2OUT (9) ← R2IN (8) ← DB9 | MCU CTS input |
| +5V / GND | Supply | VCC (16) / GND (15) | 5 V supply and ground |

| Header | Pin 1 | Pin 2 | Pin 3 | Pin 4 | Pin 5 | Pin 6 |
|---|---|---|---|---|---|---|
| JP1 (4-way) | RX_TTL | TX_TTL | GND | +5V | — | — |
| JP2 (6-way) | GND | CTS_TTL | +5V | RX_TTL | TX_TTL | RTS_TTL |

- JP1 (4-way) carries RX_TTL, TX_TTL, GND, +5V; JP2 (6-way) adds CTS_TTL and RTS_TTL. The two headers are wired in parallel for RX_TTL, TX_TTL, +5V and GND [DT].
- JP2 order (GND, CTS, +5V, RX, TX, RTS) does not match the UC00A (DTR, TX, RX, GND, CTS, VCC) or UC00C (DTR, RX, TX, VCC, CTS, GND) socket orders recorded in the KB — a straight 6-way cable does **not** line up; wire each signal by name [DT] (inference from the two pin lists).
- **Schematic:** "URS232A Schematic.pdf" (URS232A.sch, Sheet 1/1, 1/2/2016), read visually 2026-10-19 and in full at high resolution 2026-10-21 [DT]. The chip symbol is "MAX232PTH" (through-hole MAX232).

## Rules and gotchas (for code, wiring and tutorials)
- **Wire crossed: MCU TX → board RX_TTL, MCU RX ← board TX_TTL** [DT]. The board's RX_TTL feeds the MAX232 driver input (T1IN) and TX_TTL comes from the receiver output (R1OUT). Same for flow control: MCU RTS → RTS_TTL, MCU CTS ← CTS_TTL.
- **5 V board.** The supply is +5 V only, straight to the MAX232 [DT]; TX_TTL/CTS_TTL outputs swing to about 5 V [VEN]. Do not connect them directly to a 3.3 V-only UART input without a level shifter or divider — Cytron states no 3.3 V support.
- **This is not a USB device.** The schematic has no USB connector or USB chip [DT]; USB-to-RS232 needs a separate USB-UART board such as UC00A or UC00C.
- **USB-to-RS232 with UC00A / UC00C** is a Cytron-stated use [PP]. Cross-reference :
  - UC00A Rev3.0 6-way socket has DTR, TX, RX, GND, CTS, VCC; RTS is only on its extra pads JP4/JP6 [KB uc00a.md].
  - UC00C's 6-way socket has DTR, RX, TX, VCC, CTS, GND and **no RTS** pin [KB uc00c.md] — RTS hardware handshake to URS232A is not available from UC00C as documented.
  - Set the UC00A/UC00C Vsel to **5V** — the URS232A is a 5 V board [DT].
- **DB9 "Male (PC side)"**: the board presents the same gender and the same DTE pin-out as a PC serial port (TX on pin 3, RX on pin 2) [PP][DT]. So, by general RS232 practice (not Cytron-stated): a device that is itself DTE (a PC port, another URS232A) needs a null-modem cable; a DCE device such as a modem uses a straight-through cable. Cytron gives no cable guidance.
- **DTR/DSR, DCD, RI are not supported:** DB9 pins 4 and 6 are only looped to each other and pins 1 and 9 are open [DT].
- Flow control: CTS/RTS are supported [PP]; for devices that do not use them, set flow control to none in terminal software (general practice; Cytron gives no setting).
- The Cytron "Serial Loopback Test" tutorial linked from the product page now returns 404 — do not link it.

## Power and electrical limits
- Supply: +5 V only, no on-board regulator [DT]; current draw not stated [PP]. TTL logic level: 5 V (MAX232 outputs) [DT][VEN].
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
- No data at all → MCU TX must go to the board's **RX_TTL** (JP1 pin 1 / JP2 pin 4) and MCU RX to **TX_TTL** (JP1 pin 2 / JP2 pin 5) [DT]; then check baud rate/format.
- Works on the bench, not with a PC or another DTE device → both ends drive TX on pin 3; use a null-modem cable (general practice; pin-out from [DT]).
- Works with UC00A but hardware handshake fails with UC00C → UC00C has no RTS pin on its socket [KB uc00c.md].
- Cannot mate with a PC's serial port directly → both are male DB9 ("PC side") [PP]; a female-female (null-modem or gender-changer) cable is needed — general practice, not Cytron-stated.
- Garbage characters at correct baud → check that the far device is truly RS232-level, not TTL (a TTL device needs no MAX232) [PP description implies RS232 devices only].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Features | [PP] MAX232; DB9-Male (PC side); works with UC00A/UC00C; Tx, Rx, CTS, RTS | [3P] RobotShop (Manufacturer # URS232A): same list | No conflict |
| Schematic tag | 2026-10-19 file: [DS-schematic] | Brief tag rules: Cytron schematic = [DT] | Re-tagged [DT]; no fact changed |
| Operating voltage | [PP] not stated | A Korean manual for "ET-URS232" (LK Embedded, V03 2013) says DC 3.3–5V | Different product from a different maker — not used for URS232A |

## Needs verification
- Which physical end of JP1/JP2 is pin 1 on the board silkscreen (schematic pin numbers are known; no PCB layout was read).
- Whether the DB9 shell is grounded on the PCB (no wire in the schematic).
- Maximum baud rate for the board (chip context only: MAX232 up to 120 kbit/s [VEN]).
- Supply current.
- Whether the fitted chip is MAX232 or an equivalent (schematic symbol MAX232PTH; 1 µF caps match MAX232 [VEN]).
- Board dimensions and mounting holes.

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM22.05, availability 158, warranty 12 months, description and Features list) — https://my.cytron.io/p-ttl-uart-to-rs232-converter
- [DT] "URS232A Schematic.pdf" (URS232A.sch, Sheet 1/1, 1/2/2016; one page; Cytron SVN project "URS232A (UART to RS232 Converter)"). Read through the Drive viewer 2026-10-19; downloaded via the Google Drive connector and read in full at 500 dpi 2026-10-21 — https://drive.google.com/file/d/0BzFWfMiqqjyqMFMzdTVJN0pmM0U/view?resourcekey=0-brRs0cMxhpw77OpeXPLsJw
- [VEN] Texas Instruments MAX232 datasheet, SLLS047N, revised February 2024 (chip context only) — https://www.ti.com/lit/ds/symlink/max232.pdf
- [3P] (cross-check only) RobotShop, Manufacturer # URS232A, SKU RB-Cyt-190 — https://www.robotshop.com/products/cytron-rs232to-uart-converter
- Not used (different product): LK Embedded "UART TO RS232 통신모듈 매뉴얼" ET-URS232 V03 — https://www.icbanq.com/icdownload/V2_DATA/ICBShop/Board/매뉴얼_UARTtoRS232통신모듈_(URS232)_13_0708.pdf
- Product-page tutorial "Serial Loopback Test" — returns 404 on my.cytron.io (2026-10-19); not read.
