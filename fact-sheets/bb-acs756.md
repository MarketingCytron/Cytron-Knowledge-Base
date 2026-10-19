# Product fact sheets

## Product name
50A Current Sensor — BB-ACS756

## Aliases
BB-ACS756, 50A Current Sensor, Cytron 50A Current Sensor, Cytron BB-ACS756, ACS756 50A Current Sensor Breakout, 50A Current Sensor Breakout

## What it is
A breakout board for the Allegro ACS756 Hall-effect linear current sensor (50 A version) that measures AC or DC current and gives an analog output voltage. It is supplied with a Dean-T connector set and a 3-way right-angle pin header that are not soldered.

## Specs and functions
- Sensor IC: Allegro ACS756, X050 (50 Amp) version, model ACS756KCA-050B-PFF-T (product page)
- Current type: AC or DC; output voltage proportional to AC or DC current (product page)
- Primary sampled current: −50 A to +50 A (Allegro ACS756 chip datasheet, chip-level)
- Supply: 5.0 V single supply (product page); the chip itself is specified 3 V min, 5.0 V typ, 5.5 V max and factory-trimmed at 5 V (Allegro chip datasheet)
- Sensitivity: 40 mV/A (product page; Allegro typical at 25 °C); 37.2–42.8 mV/A over −40 °C to 125 °C (Allegro chip datasheet)
- Output at 0 A: VCC/2, i.e. 2.5 V at VCC = 5 V (Allegro chip datasheet)
- Total output error: 0.8% at TA = 25 °C (product page)
- Internal conductor resistance: 130 µΩ (product page)
- Isolation: 3 kV RMS minimum from pins 1-3 to 4-5 (product page)
- Output rise time: 3 µs (product page)
- Factory-trimmed; stable offset; nearly zero magnetic hysteresis (product page)
- On-board capacitors: 0.1 µF on VIOUT–GND and 0.1 µF on VCC–GND (Cytron schematic)
- Dimension: 1.43 x 1.435 inch (product page)
- Included: one set of Dean-T connector and a 3-way right-angle pin header, not soldered (product page)
- Weight: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Current path: 2-pin IN (+/−) and 2-pin OUT (+/−); the + line runs IN+ → ACS756 IP+ → IP− → OUT+, the − line passes straight through from IN to OUT (Cytron schematic)
- Signal header, 3 pins: 1 VCC, 2 GND, 3 VIOUT (analog output) (Cytron schematic)
- Output: single analog voltage; read with any ADC-capable pin
- Output is ratiometric: the 0 A level and sensitivity scale with VCC (Allegro chip datasheet)
- Fritzing part linked from the product page (product page)
- Library / sample code: [NOT STATED]

## Use cases
- Motor control (product page)
- Load detection (product page)
- Power supplies (product page)
- Over-current fault protection (product page)

## Known limitations
- The Dean-T connector and 3-way header are not soldered when purchased (product page)
- Output sits at VCC/2 at 0 A and is ratiometric to the supply, so supply variation changes offset and sensitivity (Allegro chip datasheet)
- Specified for a 5.0 V supply (product page); Allegro says 3.3 V operation needs confirmation of accuracy from Allegro (Allegro chip datasheet)
- Chip output drive: 3 mA source, 1 mA sink max; minimum load 4.7 kΩ (Allegro chip datasheet)
- No Cytron datasheet, user manual or sample code exists; board-level maximum continuous current is [NOT STATED]

## Positioning (kept apart from specs)
- [NOT STATED]

## Price band
RM52.50 (10+ RM47.25, 30+ RM42.00) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-50a-current-sensor

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-50a-current-sensor
