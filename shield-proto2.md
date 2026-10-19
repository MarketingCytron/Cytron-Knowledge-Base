# Cytron Prototyping Shield — Verified Reference

| Field | Value |
|---|---|
| Product code | SHIELD-PROTO2 [PP] |
| Family | Arduino shields (non-motor) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: untagged facts are from the product page as read by the coordinator on 2026-10-19 [PP]. The schematic/PCB prints and Fritzing files were not opened.

## What it is
An Arduino prototyping shield, "revised to be UNO R3 and Leonardo compatible", with "the pads for ISP" prepared [PP]. It solves the 0.1-inch offset between the Arduino header and a standard protoboard by giving a standard 0.1" x 0.1" prototyping area within the Arduino dimensions, with stackable headers, a reset button, one LED, GND and +5V rails, and every pin extended out to two sides of the headers [PP]. It is delivered assembled [PP].

## Specifications
Every row of the product page Features list, plus the description facts.

| Item | Value | Src |
|---|---|---|
| Compatibility | "revised to be UNO R3 and Leonardo compatible" | [PP] |
| Prototyping area | Standard 0.1" x 0.1" prototyping area | [PP] |
| Headers | Stackable headers; "4 rows of stackable header" | [PP] |
| Reset button | Yes | [PP] |
| LED | One LED "for power or output indicator" | [PP] |
| Pin extension | Every pin extended out to two sides of the headers | [PP] |
| Power rails | GND and +5V rails | [PP] |
| Mounting | 4 screw holes | [PP] |
| ISP | "We have also prepared the pads for ISP." | [PP] |
| SMD parts fitted | "4 SMD components — LED, push-button and resistor — soldered on the labelled PCB" | [PP] |
| PCB | Labelled PCB | [PP] |
| Delivery | Delivered assembled | [PP] |
| Dimension | 68.58mm x 58.42mm | [PP] |
| Packing list | 1x shield | [PP] |
| Warranty | 12 months | [PP] |
| Hole count, rail layout, weight, header type for ISP | Not stated | [PP] |

## Interfaces, terminals and pin mapping
- **Arduino headers:** stackable, 4 rows [PP]; layout matches UNO R3 and Leonardo [PP]. Each Arduino pin is "extended out to two sides of the headers", i.e. extra 0.1" holes beside the header for soldering wires [PP].
- **ISP:** the page says pads for ISP are prepared [PP]. It does not say a 2x3 ICSP header is fitted, nor whether the pads pass the Arduino ICSP signals through. Write "ISP pads (header not stated as fitted)", never "ICSP header included".
- **Reset button:** on the shield [PP]; presumably wired to the Arduino RESET line (implied by name, not stated).
- **LED:** one LED, usable as a power or output indicator [PP]. How it is connected (fixed to +5V, or a free LED with resistor for the user to wire to a pin) is not stated — see Needs verification.
- **Rails:** GND and +5V rails [PP]. A 3.3V rail is not mentioned — do not claim one.
- **Prototyping area:** standard 0.1" x 0.1" grid [PP]; whether holes are isolated or strip-connected is not stated.

## Rules and gotchas (for code, wiring and tutorials)
- No code is needed for the shield itself; it only extends the Arduino pins [PP], so pin numbers in a sketch are the Arduino's own.
- Compatibility claimed by Cytron is **UNO R3 and Leonardo** [PP]. Do not list Mega, Due or other boards as Cytron-stated.
- The headline benefit is fixing the Arduino's 0.1-inch header offset so standard 0.1" parts and headers fit the grid [PP].
- "4 SMD components" are named as "LED, push-button and resistor" (three part types for four parts) [PP]; do not invent which component is doubled.
- The +5V rail is the Arduino's 5V via the headers; the shield has no regulator stated [PP] — do not claim one.
- The page's resources include a "Getting Started with Fritzing" tutorial dated 2013 — it is about drawing circuits in Fritzing, not a shield manual; the Fritzing part may show an older board revision.
- Schematic and PCB prints are offered "given as is" [PP].

## Power and electrical limits
- Power comes from the host Arduino through the headers to the GND and +5V rails [PP].
- No current rating for the rails, no fuse and no protection are stated [PP].

## Software support
- None required. Fritzing files are provided for drawing circuits [PP].

## Compatibility and accessories
- UNO R3 and Leonardo [PP].
- Package: 1x shield, delivered assembled [PP].
- Related Cytron product (different board, do not merge facts): SHIELD-SCREW2 Cytron Screw Terminal Shield — 3.5 mm screw terminals plus a prototyping area, 74.93 mm x 81.28 mm, Getting Started Guide V1.0 JAN 2015; its guide does not mention ISP pads [KB shield-screw2.md]. The Proto Shield is the smaller (68.58mm x 58.42mm) solder-only option and is the one with ISP pads [PP].

## Common mistakes / troubleshooting
- "Where is the ICSP header?" → only pads for ISP are mentioned [PP]; fit a header yourself if the pads accept one (not stated).
- LED does not light → its wiring is not documented; check the PCB labels / schematic before assuming it is a power LED.
- Arduino cannot be reset with the shield stacked → use the shield's reset button [PP].
- Parts do not line up with the Arduino header → the shield's prototyping area is on the standard 0.1" grid; the Arduino header offset is handled on the shield [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| ISP pads | [PP] "We have also prepared the pads for ISP." | [3P] RobotShop (Manufacturer # SHIELD-PROTO2) Features list does not mention ISP | No contradiction; [PP] wins |
| Dimension / Features | [PP] 68.58mm x 58.42mm; 0.1" grid, stackable headers, reset, one LED, GND and +5V rails | [3P] RobotShop: same values | No conflict |

## Needs verification
- LED circuit (always-on power LED vs user LED) and which pads it connects to.
- Whether ISP pads accept a 2x3 header and connect to the Arduino ICSP pins.
- Prototyping-area hole count and whether any holes are strip-connected.
- Which component is counted twice in "4 SMD components — LED, push-button and resistor".
- Weight and PCB revision marking.
- Whether the schematic/PCB prints folder matches the current revision (page says "given as is").

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM14.70, availability 273, warranty 12 months, description, Features list, packing list) — https://my.cytron.io/p-cytron-prototyping-shield
- [PP resource] "Getting Started with Fritzing" (Cytron tutorial, 2013) — linked from the product page; not read
- [3P] (cross-check only) RobotShop "Cytron Arduino Proto Shield", Manufacturer # SHIELD-PROTO2, SKU RB-Cyt-100 — https://www.robotshop.com/products/cytron-arduino-proto-shield
