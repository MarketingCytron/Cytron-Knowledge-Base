# Dual Output Cable - USB A to 2.1mm DC Barrel & Micro USB — Verified Reference

| Field | Value |
|---|---|
| Product code | `WR-USB-UB-DC` [PP] |
| Family | Cables and small accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (Description, Features, Packing List) and its two images (the cable; EDU:BIT with both plugs connected) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-dual-output-cable-usb-a-to-2p1-mm-dc-barrel-and-micro-usb (read 2026-10-21) [PP]. No datasheet or drawing |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = the two page images. It is the "USB power and data cable" in the EDU:BIT kit (inferred from `edu-bit.md`, which describes the kit cable as a micro USB + barrel Y-cable; the EDU:BIT page packing list does not give this code).

## What it is
- A black Y-cable from one **USB 2.0 Type-A plug** to two outputs: a **micro USB (USB micro-B)** plug carrying **data and power**, and a **2.1 mm DC barrel plug** carrying **power only** [PP].
- "Designed specifically for EDU:BIT to reduce the number of wires or cables needed": one computer USB port both programs the micro:bit (micro-B) and powers the EDU:BIT board (barrel) [PP][PP: img].

## Specifications
| Item | Value | Src |
|---|---|---|
| End A | USB 2.0 Type-A plug | [PP] |
| End B1 | USB micro-B plug — data and power | [PP] |
| End B2 | 2.1 mm DC barrel plug — power only | [PP] |
| Length | ~1 metre | [PP] |
| Colour | Black | [PP] |
| Barrel outer diameter, polarity, wire gauge, current rating | Not stated (polarity of USB 5 V on the barrel not stated; a customer measured 5 V on the barrel [3P]) | — |
| Price | RM10.00; 10 or more RM9.00 | [PP] |
| Warranty | 12 months | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `WR-USB-UB-DC`, availability 593, 19 ratings [PP].
- Packing list: 1 × USB A to 2.1mm DC Barrel & Micro USB [PP].
- Image: EDU:BIT with the barrel plug in its power jack and the micro USB in the micro:bit [PP: img].

## Interfaces, terminals and pin mapping
| End | Connector | Carries | Src |
|---|---|---|---|
| Host | USB-A plug | USB 5 V, GND, D+/D− | [PP] |
| Branch 1 | micro USB (micro-B) plug | Data and power | [PP] |
| Branch 2 | 2.1 mm DC barrel plug | Power only (from USB 5 V) | [PP]; voltage 5 V measured by a customer [3P] |
Wire colours and barrel centre polarity are not given [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **The barrel branch has no data** — programming goes through the micro-B branch [PP].
- **5 V from USB only:** it powers boards whose barrel input accepts 5 V (EDU:BIT is the stated target) [PP]. Do not use it for 12 V barrel inputs or motor drivers needing more current than a USB port supplies (inferred).
- **Check the board's barrel size and polarity** before using it on boards other than EDU:BIT — the page states only "2.1mm" [PP].
- Switch EDU:BIT's power switch ON after plugging in (`edu-bit.md`).

## Power and electrical limits
- Limited by the USB host port (typically 500 mA for USB 2.0 — general knowledge, not stated). No current rating is given [PP].

## Software support
- None.

## Compatibility and accessories
- EDU:BIT (`edu-bit.md`) with a BBC micro:bit [PP].
- Other Cytron micro:bit boards with a DC jack (e.g. REKA:BIT's DC jack is 3.6–6 VDC, `reka-bit.md`) — fit not stated by Cytron; check jack size before claiming it.

## Common mistakes / troubleshooting
- **micro:bit programs but EDU:BIT modules dead:** the barrel plug is not seated or EDU:BIT's power switch is OFF (`edu-bit.md`).
- **Computer does not see the micro:bit:** the data path is only on the micro-B branch [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | [PP] text | [PP: img] | No conflict found |

## Needs verification
- Barrel plug outer diameter (5.5 mm?), centre-positive polarity, wire gauge and current rating.
- Whether this exact code ships in the EDU:BIT kit (inferred).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-dual-output-cable-usb-a-to-2p1-mm-dc-barrel-and-micro-usb — read 2026-10-21
- [PP: img] `WR-USB-UB-DC-a.jpg` (cable), `EDUBIT-top-800x800-lq.png` (in use)
- [3P] Customer review (31 Oct 2020) measuring 5 V on the barrel
- KB cross-references: `edu-bit.md`, `reka-bit.md`
