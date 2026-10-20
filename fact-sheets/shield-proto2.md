# Product fact sheets

## Product name
Cytron Prototyping Shield (SHIELD-PROTO2)

## Aliases
SHIELD-PROTO2, Shield-Proto2, Cytron Prototyping Shield, Prototyping Shield for Arduino, Cytron Proto Shield, Cytron Arduino Proto Shield

## What it is
An Arduino prototyping shield with a standard 0.1" x 0.1" prototyping area, stackable headers, a reset button, one LED and GND and +5V rails, revised to be UNO R3 and Leonardo compatible. It is delivered assembled.

## Specs and functions
- Prototyping area: standard 0.1" x 0.1" (product page)
- Headers: stackable, 4 rows of stackable header (product page)
- Reset button: SMD push-button S1 between RST and GND, with 0.1 µF capacitor C1 across it (schematic Rev 1.0.1)
- LED: SMD LED DS1 with 1 kΩ resistor to GND, fed from 2-pin jumper JP1 (5V / LED): link JP1 for a power LED, or wire the LED pin to an I/O pin for an output indicator (schematic)
- Every Arduino header pin joined to two extra breakout holes (schematic)
- Rails: GND rail 16 holes, 5V rail 12 holes; no 3.3 V rail (schematic)
- Mounting: 4 screw holes (product page)
- ISP: product page says "pads for ISP", but the Rev 1.0.1 schematic has no ISP/ICSP connection
- SMD components: 4 — LED, push-button, 1 kΩ resistor and 0.1 µF capacitor (schematic)
- Dimension: 68.58mm x 58.42mm (product page)
- Delivered assembled (product page)
- Packing list: 1x shield (product page)
- Warranty: 12 months (product page)
- Board revision: Rev 1.0.1, dated 01-Nov-2011 (schematic)
- Plated holes: 489 in total (artwork count); prototyping holes are isolated (no strips)
- Rail current rating: [NOT STATED]

## Interfaces and compatibility
- Compatible with Arduino UNO R3 and Leonardo (product page)
- Mounts on the Arduino with stackable headers (product page)
- No ICSP pass-through (schematic shows no ISP connection)
- Software: none required; Fritzing files provided (product page)

## Use cases
- Building circuits on a standard 0.1" protoboard grid on top of an Arduino, without the Arduino's 0.1-inch header offset
- Low-cost prototyping with maximum prototyping area within the Arduino dimensions

## Known limitations
- No Cytron datasheet or user manual; facts come from the schematic and artwork Rev 1.0.1 and the product page
- The LED works only when JP1 is linked (power LED) or its pin is wired to an I/O; whether JP1 ships bridged is not stated
- No ICSP connection, although the product page mentions "pads for ISP"
- Prototyping holes are isolated; connections need solder bridges or wire
- No regulator, fuse or protection; the 5V rail comes from the Arduino
- Only UNO R3 and Leonardo compatibility is stated
- Schematic and PCB prints are provided "given as is"

## Positioning (kept apart from specs)
- Product page: low cost, maximum prototyping area within Arduino dimensions
- Product page: solves the 0.1-inch offset of the Arduino header versus standard protoboard

## Price band
RM14.70 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-cytron-prototyping-shield

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-cytron-prototyping-shield
