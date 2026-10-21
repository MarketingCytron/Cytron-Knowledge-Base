# Grove to JST-SH (Qwiic) Cable - 20cm — Verified Reference

| Field | Value |
|---|---|
| Product code | `WR-GRV-JST-SH` [PP] |
| Family | Cables and small accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (Description, Features/Specifications, Packing List, Resources), its two photos (the cable; Maker Nano RP2040 to a Grove DHT20), and the linked JST "SH Connector" datasheet (3 pages, Google Drive) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-grove-to-jst-sh-qwiic-cable-20cm (read 2026-10-21) [PP]; JST "SH CONNECTOR — 1.0 mm pitch/Disconnectable Crimp style connectors" datasheet linked as "JST-SH Connector Datasheet" [VEN: JST] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = page photos; [VEN: JST] = the connector maker's (J.S.T. Mfg.) SH series datasheet linked from the page — it describes the JST-SH connector family, not this cable assembly. The Grove connector pitch is not stated on the page (Grove is a 2.0 mm 4-pin system — general knowledge).

## What it is
- A 20 cm, 4-wire "chimera" cable: **STEMMA QT / SparkFun Qwiic JST-SH 4-pin (1 mm pitch)** plug on one end and a **Grove 4-pin** plug on the other [PP].
- Used to connect Grove I2C modules to boards with Cytron **Maker Ports** (JST-SH) — e.g. Maker Nano RP2040 — or STEMMA QT / Qwiic modules to Grove hosts [PP].
- **I2C only:** "The Grove system has a variety of different signal systems that use the same connector. This cable only works with the I2C variety" [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Length | 20 cm | [PP] |
| End A | JST-SH 4-pin, 1 mm pitch (STEMMA QT / Qwiic) | [PP][VEN: JST] |
| End B | Grove 4-pin connector (white housing in photo) | [PP][PP: img] |
| Wire colours | Black = GND; Red = V+ (3.3 V for Qwiic boards, 3–5 V for STEMMA QT); Blue = SDA; Yellow = SCL | [PP] |
| Current rating | 1.0 A (AWG #28) | [PP][VEN: JST] |
| Voltage rating | 50 V | [PP]; 50 V AC/DC [VEN: JST] |
| JST-SH temperature range | −25 °C to +85 °C (incl. temperature rise) | [VEN: JST] |
| JST-SH contact resistance | 20 mΩ max initial, 40 mΩ after environmental tests | [VEN: JST] |
| JST-SH applicable wire | AWG #32 to #28, insulation OD 0.4–0.8 mm; contact SSH-003T-P0.2-H; 4-pin housing SHR-04V-S(-B) | [VEN: JST] |
| Price | RM4.00; 5 or more RM3.60 | [PP] |
| Warranty | 12 months | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `WR-GRV-JST-SH`, availability 11401, 15 ratings [PP].
- Packing list: 1 × Grove to JST-SH (Qwiic) Cable [PP]. "The Maker Nano RP2040 and DHT20 sensor are NOT INCLUDED" [PP].
- Resources: JST-SH Connector Datasheet (PDF) [PP]. Related tutorial: "Environment Data Monitoring With Maker Feather AIOT S3 and …" (24 Mar 2023) [PP].
- Photo: Maker Nano RP2040 Maker Port → this cable → Grove DHT20 temperature/humidity sensor [PP: img].

## Interfaces, terminals and pin mapping
| Wire colour | Signal | Src |
|---|---|---|
| Black | GND | [PP] |
| Red | V+ (3.3 V on Qwiic; 3–5 V on STEMMA QT) | [PP] |
| Blue | SDA | [PP] |
| Yellow | SCL | [PP] |
- Both ends carry the same four signals (straight-through, inferred from the colour list). Physical pin order inside each housing is not drawn on the page.
- On Cytron boards the Maker Port pins are board-specific (e.g. Maker Nano RP2040 Port 0 = GP0/GP1, Port 1 = GP26/GP27 — `maker-nano-rp2040.md`).

## Rules and gotchas (for code, wiring and tutorials)
- **Only Grove I2C modules work** through it [PP]. Grove analog/digital/UART modules on a Maker Port need the board's I2C/GPIO mapping and are not promised by this page.
- **Voltage:** Qwiic is 3.3 V only. "If you want to connect a Qwiic board (3V power only!) to a Grove or STEMMA host, make sure the power switch is set to 3V" [PP]. Grove I2C sensors (3–5 V) are fine on a 3.3 V Maker Port host [PP].
- **SDA is blue**, not the white wire of standard Grove cables [PP]; tutorials should use the colours above.
- Polarised connectors — cannot be plugged in reversed [PP].

## Power and electrical limits
- Cable/connector rating 1.0 A, 50 V [PP][VEN: JST]. Real limit is the host's 3.3 V rail (e.g. MOTION 2350 Pro 200 mA total on +3V3 — `motion-2350-pro.md`).

## Software support
- None.

## Compatibility and accessories
- Cytron boards with JST-SH Maker Ports that ship this cable: Maker Nano RP2040 (2 per box, `maker-nano-rp2040.md`), Maker Pi Pico Mini (3 per box, `maker-pi-pico-mini.md`), Maker Feather AIOT S3 (3 per box, `maker-feather-aiot-s3.md`), MOTION 2350 Pro (2 × "Grove to JST-SH cable (200 mm)", `motion-2350-pro.md`) [PP of those products, per their KB files].
- Other Cytron boards with a Maker Port: Maker UNO RP2040 (`maker-uno-rp2040.md`), Robo Pico (`robo-pico.md`), CM4 Maker Board (`cm4-maker-board.md`) — Grove via conversion cable per their datasheets.
- Female-socket alternative for breadboards/headers: `stemma-qt-jst-sh-female-cable.md`.

## Common mistakes / troubleshooting
- **Grove sensor not found on I2C scan:** confirm it is a Grove **I2C** module [PP] and that the code uses the I2C bus wired to that Maker Port (board KB file).
- **Qwiic board damaged on a 5 V Grove host:** set the host to 3 V first [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Current / voltage rating | Page: 1.0 A (AWG#28), 50 V [PP] | JST SH datasheet: 1.0 A AC/DC (AWG #28), 50 V AC/DC [VEN: JST] | Agree |

## Needs verification
- Actual wire gauge used in the cable (the 1.0 A figure is the JST rating at AWG #28).
- Grove-end housing part and pitch (2.0 mm by Grove convention, not stated).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-grove-to-jst-sh-qwiic-cable-20cm — read 2026-10-21
- [PP: img] `WR-GRV-JST-SH (a).jpg` (cable), `WR-GRV-JST-SH (d).jpg` (Maker Nano RP2040 + DHT20)
- [VEN: JST] "JST-SH Datasheet.pdf" — (Cytron document — link not public) (downloaded, text extracted 2026-10-21)
- KB cross-references: `maker-nano-rp2040.md`, `maker-pi-pico-mini.md`, `maker-feather-aiot-s3.md`, `motion-2350-pro.md`, `maker-uno-rp2040.md`, `robo-pico.md`, `cm4-maker-board.md`, `stemma-qt-jst-sh-female-cable.md`
