# Cytron Prototyping Shield — Verified Reference

| Field | Value |
|---|---|
| Product code | SHIELD-PROTO2 [PP] |
| Family | Arduino shields (non-motor) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Primary source | No datasheet or user manual exists. Design files: **Schematic Prints Rev 1.0.1** ("ARDUINO PROTO SHIELD", Revision 1.0.1, dated 01-Nov-11, Altium file "Arduino Proto Shield.SchDoc") and **Final Artwork Prints Rev 1.0.1** (12 pages: copper, silkscreen, solder mask, drill and outline; bottom copper text "Nov11 Rev1.0.1") — both from the "Schematic and PCB Prints" folder linked on the product page [DT]. Plus the Cytron product page https://my.cytron.io/p-cytron-prototyping-shield [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DT] = the Cytron schematic and artwork prints Rev 1.0.1 (read 2026-10-20). Untagged facts are from the product page as read by the coordinator on 2026-10-19 [PP]. [PP: photo] = the product photo. The two prints sit in the "Arduino-Proto2" Drive folder linked from the product page; the folder opens publicly but the files ask for a Google sign-in, so customers cannot open them from the page (reported 2026-10-20).

## What it is
An Arduino prototyping shield, "revised to be UNO R3 and Leonardo compatible", with "the pads for ISP" prepared [PP]. It solves the 0.1-inch offset between the Arduino header and a standard protoboard by giving a standard 0.1" x 0.1" prototyping area within the Arduino dimensions, with stackable headers, a reset button, one LED, GND and +5V rails, and every pin extended out to two sides of the headers [PP]. It is delivered assembled [PP].

## Specifications
Every row of the product page Features list, plus the description facts.

| Item | Value | Src |
|---|---|---|
| Compatibility | "revised to be UNO R3 and Leonardo compatible" | [PP] |
| Prototyping area | Standard 0.1" x 0.1" prototyping area | [PP] |
| Headers | Stackable headers; "4 rows of stackable header" | [PP] |
| Reset button | SMD push-button S1 labelled RESET, between the Arduino RST pin and GND, with a 0.1 µF capacitor (C1) across it | [DT] |
| LED | One SMD LED (DS1) with a 1 kΩ resistor (R1) to GND, fed from a 2-pin jumper JP1 labelled **5V** and **LED**: link the two pins for a power LED, or wire the LED pin to an Arduino I/O to use it as an output indicator | [DT] |
| Pin extension | Every Arduino header pin (POWER: RST, 3V3, 5V, GND, GND, VIN; ANALOG IN: A0–A5; DIGITAL: AREF, GND, D13–D0) is joined to **two extra holes** beside its header (JP2–JP15 groups of three) | [DT] |
| Power rails | **GND rail of 16 holes** (JP12) along the digital-header side and **5V rail of 12 holes** (JP11) along the power/analog side | [DT] |
| Mounting | 4 screw holes | [PP] |
| ISP | "We have also prepared the pads for ISP." | [PP] |
| SMD parts fitted | Four: LED DS1, push-button S1, 1 kΩ resistor R1 and 0.1 µF capacitor C1 (the page lists only "LED, push-button and resistor") | [DT][PP] |
| PCB | Labelled PCB | [PP] |
| Delivery | Delivered assembled | [PP] |
| Dimension | 68.58mm x 58.42mm | [PP] |
| Packing list | 1x shield | [PP] |
| Warranty | 12 months | [PP] |
| Board revision | Rev 1.0.1, schematic dated 01-Nov-11; bottom copper marked "Nov11 Rev1.0.1" | [DT] |
| Silkscreen | Artwork: Cytron logo, "Arduino Proto Shield", www.cytron.com.my; header labels; RESET at S1; JP1 labelled 5V / LED; open-source-hardware logo on the bottom side. Product photo: "Cytron Technologies — Proto Shield — Cytron.com.my" | [DT][PP: photo] |
| Plated holes | 489 plated through-holes in total, counted from the Rev 1.0.1 artwork (prototyping grid plus header, breakout, rail and JP1 holes); the prototyping holes are isolated (no strips) | [DT] |
| Weight, rail current rating | Not stated | [PP] |

## Interfaces, terminals and pin mapping
- **Arduino headers:** stackable, 4 rows [PP]; layout matches UNO R3 and Leonardo [PP]. Schematic groups: POWER (RST, 3V3, 5V, GND, GND, VIN), ANALOG IN (A0–A5), DIGITAL 2 (AREF, GND, D13–D8), DIGITAL 1 (D7–D0) [DT].
- **Breakout holes:** each header pin is wired to two extra holes beside it (three holes per signal) [DT].
- **Rails:** GND rail 16 holes, 5V rail 12 holes [DT]. There is no 3.3 V rail; 3V3 is only available at its header pin and its two breakout holes [DT].
- **Reset:** S1 connects RST to GND; C1 0.1 µF across the button [DT].
- **LED:** JP1 pin "5V" → link → pin "LED" → R1 1 kΩ → DS1 → GND [DT]. The packing list has no jumper; whether JP1 is bridged at the factory is not stated (see *Needs verification*).
- **ISP:** the Rev 1.0.1 schematic has **no ISP/ICSP connector or net** [DT]. See *Conflicts*.
- **Prototyping area:** standard 0.1" grid of isolated plated holes [DT][PP].

## Rules and gotchas (for code, wiring and tutorials)
- No code is needed for the shield itself; it only extends the Arduino pins [PP], so pin numbers in a sketch are the Arduino's own.
- Compatibility claimed by Cytron is **UNO R3 and Leonardo** [PP]. Do not list Mega, Due or other boards as Cytron-stated.
- **No ICSP pass-through:** the schematic has no ISP/ICSP connection [DT]. Do not tell readers they can program through the shield's ISP pads.
- The +5V rail is the Arduino's 5V via the headers; the shield has no regulator, fuse or protection [DT].
- The prototyping holes are isolated — join them with solder bridges or wire, not as strips [DT].
- The headline benefit is fixing the Arduino's 0.1-inch header offset so standard 0.1" parts and headers fit the grid [PP].
- The page's resources include a "Getting Started with Fritzing" tutorial dated 2013 — it is about drawing circuits in Fritzing, not a shield manual.

## Power and electrical limits
- Power comes from the host Arduino through the headers to the GND and 5V rails [DT][PP].
- No regulator, fuse or protection on the board [DT]; no current rating for the rails is stated [PP].
- LED branch: 5V through 1 kΩ and the LED (only when JP1 is linked or the LED pin is driven) [DT].

## Software support
- None required. Fritzing files are provided for drawing circuits [PP].

## Compatibility and accessories
- UNO R3 and Leonardo [PP].
- Package: 1x shield, delivered assembled [PP].
- Related Cytron product (different board, do not merge facts): SHIELD-SCREW2 Cytron Screw Terminal Shield — 3.5 mm screw terminals plus a prototyping area, 74.93 mm x 81.28 mm, Getting Started Guide V1.0 JAN 2015; its guide does not mention ISP pads [KB shield-screw2.md]. The Proto Shield is the smaller (68.58mm x 58.42mm) solder-only option and is the one with ISP pads [PP].

## Common mistakes / troubleshooting
- **LED never lights** → JP1 may not be linked: bridge 5V to LED for a power LED, or wire the LED pin to an I/O pin [DT].
- **"Where is the ICSP header?"** → there is none, and the schematic has no ICSP net [DT]; program the Arduino over USB as usual.
- **Arduino cannot be reset with the shield stacked** → use the shield's RESET button (wired to RST) [DT].
- **Parts not connected** → the prototyping holes are isolated; add solder bridges or wire [DT].
- **Parts do not line up with the Arduino header** → the shield's prototyping area is on the standard 0.1" grid; the Arduino header offset is handled on the shield [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| ISP pads | [PP] "We have also prepared the pads for ISP." | [DT] schematic Rev 1.0.1: no ISP/ICSP connector or net | [DT] outranks [PP]: say the shield has **no ICSP connection**. Ask the product team whether "pads for ISP" refers to a later revision; otherwise the page sentence should be removed |
| SMD component list | [PP] "4 SMD components — LED, push-button and resistor" | [DT] LED, push-button, resistor **and 0.1 µF capacitor** | Same four parts; the page omits the capacitor |
| LED function | [PP] "LED for power or output indicator" | [DT] LED fed through jumper JP1 (5V / LED) | No conflict: JP1 chooses power-LED use; wiring the LED pin gives indicator use |
| Dimension / Features | [PP] 68.58mm x 58.42mm; 0.1" grid, stackable headers, reset, one LED, GND and +5V rails | [3P] RobotShop: same values | No conflict |

## Needs verification
- Whether JP1 ships bridged (LED always on) or open — check a unit.
- Whether any newer board revision than Rev 1.0.1 (Nov 2011) is being shipped, and whether it adds ISP pads.
- Header type for the ISP claim (moot unless a newer revision has ISP pads).
- Weight; rail current rating.

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM14.70, availability 273, warranty 12 months, description, Features list, packing list) — https://my.cytron.io/p-cytron-prototyping-shield
- [PP resource] "Getting Started with Fritzing" (Cytron tutorial, 2013) — linked from the product page; not read
- [3P] (cross-check only) RobotShop "Cytron Arduino Proto Shield", Manufacturer # SHIELD-PROTO2, SKU RB-Cyt-100 — https://www.robotshop.com/products/cytron-arduino-proto-shield
