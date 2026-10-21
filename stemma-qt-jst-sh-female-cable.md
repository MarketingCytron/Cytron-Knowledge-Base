# STEMMA QT / Qwiic JST SH 4-pin Cable with Premium Female Sockets - 150mm — Verified Reference

| Field | Value |
|---|---|
| Product code | `WR-SQ-150F` [PP] |
| Family | Cables and small accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (Description, Packing List) and its description photo (JST-SH plug to four black female Dupont sockets) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-stemmaqt-qwiic-jst-sh-4-pin-cable-with-premium-female-sockets-150mm (read 2026-10-21) [PP]. No datasheet; the page links JST's SH series web page and SparkFun's Qwiic page (not read) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = the description photo. The description text says "premium Dupont male headers", while the title, packing list and photo show **female sockets** — see *Conflicts*. JST-SH electrical ratings are in `grove-to-jst-sh-cable.md` (JST datasheet).

## What it is
- A ~150 mm (a little over 6") 4-wire cable with a **JST-SH 4-pin, 1 mm pitch (STEMMA QT / Qwiic)** plug on one end and **four separate 0.1" (2.54 mm) Dupont female sockets** on the other [PP][PP: img].
- Connects a Qwiic / STEMMA QT module or a Cytron **Maker Port** to 0.1" male header pins (e.g. a Raspberry Pi GPIO header or a board's pin header) [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Length | ~150 mm ("a little over 150mm / 6" long") | [PP] |
| End A | JST-SH 4-pin, 1 mm pitch ("1mm pitch instead of 2mm" vs JST-PH; latching) | [PP] |
| End B | 4 × individual Dupont female sockets (black housings) | [PP: title, packing list][PP: img] |
| Wire colours (Qwiic use) | Red = 3.3 VDC power; Black = Ground; Blue = I2C SDA; Yellow = I2C SCL | [PP] |
| Current / voltage rating | Not stated on this page (JST-SH series: 1.0 A at AWG #28, 50 V — `grove-to-jst-sh-cable.md`) | — |
| Price | RM5.00; 10 or more RM4.50 | [PP] |
| Warranty | 12 months | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `WR-SQ-150F`; "Backorder Only", 327 units estimated on 30 Oct 2026; 15 ratings [PP].
- Packing list: 1 × Female STEMMA QT / Qwiic JST SH 4-pin Cable with Premium Sockets - 150mm [PP].
- Links: SparkFun Qwiic page; JST SH series page; an Adafruit STEMMA QT video (not watched) [PP].
- Related tutorials: "ESP32 Water Tank Monitoring with Web Dashboard" and "ESP32 Digital Clock" (Sep 2026) [PP].

## Interfaces, terminals and pin mapping
| Wire colour | Signal (Qwiic) | Src |
|---|---|---|
| Red | 3.3 VDC | [PP] |
| Black | GND | [PP] |
| Blue | SDA | [PP] |
| Yellow | SCL | [PP] |
- Each colour ends in its own female socket, so the four can go to any header pins [PP: img].

## Rules and gotchas (for code, wiring and tutorials)
- **Female sockets fit male header pins** (Raspberry Pi GPIO, Arduino-style male pins, breadboard via male jumpers) — not straight into a breadboard (inferred from the female ends).
- **Wire by colour:** red → 3.3 V, black → GND, blue → SDA, yellow → SCL [PP]. On a Raspberry Pi that is physical pins 1 (3V3), 6 (GND), 3 (SDA), 5 (SCL) — Raspberry Pi header convention, not stated by Cytron.
- **Qwiic power is 3.3 V** [PP] — do not feed 5 V to a Qwiic-only module.
- Stock is backorder at the time of reading [PP].

## Power and electrical limits
- Not stated on this page; see the JST-SH ratings in `grove-to-jst-sh-cable.md`.

## Software support
- None.

## Compatibility and accessories
- Cytron Maker Ports (JST-SH 4-way): MOTION 2350 Pro ships 1 × "STEMMA QT / Qwiic JST-SH 4-pin cable with female sockets (150 mm)" (`motion-2350-pro.md`); also usable with `maker-nano-rp2040.md`, `maker-pi-pico-mini.md`, `maker-feather-aiot-s3.md`, `maker-uno-rp2040.md`, `robo-pico.md`, `cm4-maker-board.md` Maker Ports (inferred from the shared JST-SH 4-way connector).
- Grove-plug version: `grove-to-jst-sh-cable.md`.

## Common mistakes / troubleshooting
- **Sensor not detected:** SDA and SCL swapped — blue is SDA, yellow is SCL [PP].
- **Ordering expecting male pins:** the description mentions male headers, but this listing is the female-socket version [PP] (see *Conflicts*).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Header-end gender | Description: "premium Dupont male headers on the other" [PP] | Title "with Premium Female Sockets", packing list "Female …", photo shows female sockets [PP][PP: img] | Female wins (title, packing list and photo agree); the description sentence is from a male-pin variant |
| JST-end wording | Description: "JST-SH female 4-pin connectors" [PP] | Photo: a JST-SH cable plug (crimp housing) [PP: img] | Same thing — the cable-side JST-SH housing mates with the board's header |

## Needs verification
- Wire gauge and current rating for this cable.
- Whether a male-pin version (`V-WR-SQ-150` image folder suggests a parent listing) is sold separately.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-stemmaqt-qwiic-jst-sh-4-pin-cable-with-premium-female-sockets-150mm — read 2026-10-21
- [PP: img] `WR-SQ-150F/untitled-design-35.png`
- [VEN] (linked, not read) https://www.sparkfun.com/qwiic ; http://www.jst-mfg.com/product/detail_e.php?series=231
- KB cross-references: `grove-to-jst-sh-cable.md`, `motion-2350-pro.md`, `maker-nano-rp2040.md`, `maker-pi-pico-mini.md`, `maker-feather-aiot-s3.md`, `maker-uno-rp2040.md`, `robo-pico.md`, `cm4-maker-board.md`
