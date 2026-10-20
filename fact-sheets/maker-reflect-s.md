# Product fact sheets

## Product name
Maker Reflect S (MAKER-REFLECT-S)

## Aliases
MAKER-REFLECT-S, Maker Reflect S, Cytron Maker Reflect S, Maker Reflect-S, MakerReflectS

## What it is
The newer "S" variant of the Maker Reflect infrared reflectance sensor (line detector) with the same 3-pin VCC/GND/OUT connector; its output is higher on darker surfaces and its datasheet lists it as digital-IO compatible with no ADC required. It is a 5 VDC sensor with an optimal sensing distance of 3 mm.

## Specs and functions
- Sensor type: IR Reflectance Sensor — infrared sensors for line detection (datasheet)
- Operating voltage: 5VDC (datasheet)
- Supply current: 25mA (datasheet)
- Digital IO Compatible (datasheet)
- No ADC required (datasheet)
- Optimal sensing distance: 3mm (0.125") (datasheet)
- Output: "OUT : Analog output. Higher voltage = darker surface." (datasheet connector table)
- Threshold: "The new Maker Reflect S comes with a smaller threshold sensing for more stable output" (product page); no numeric threshold stated
- Reverse polarity protection: none — "Reversed Polarity will damage the sensor" (datasheet)
- On-board adjustment, trimmer or switch: none listed (datasheet)
- Indicator LED: none listed (datasheet)
- Supply voltage min/max: [NOT STATED]
- Sensing distance min/max: [NOT STATED]
- Output voltage levels: [NOT STATED]
- Sensor IC / IR part number: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Operating temperature: [NOT STATED]
- Datasheet: MAKER-REFLECT-S Datasheet, "Analog Reflectance Sensor (Line Detector)", Rev 1.0, February 2026
- Warranty: 12 months (product page)
- Supply: 5.0 V only; supply current 25 mA (product page comparison table)
- Output: analog, 0–VCC, higher on darker surfaces; optimal distance 3 mm (product page)
- Ikedo Mini Sumo Robot V2 uses it as the edge sensor from March 2026 (product page)

## Interfaces and compatibility
- Connector: 3 pins — VCC (power input), GND (ground), OUT (output)
- Readable on a digital input pin (datasheet: "Digital IO Compatible", "No ADC required") or an analog input (datasheet: "Analog output")
- Compatible boards named in the datasheet: [NOT STATED]
- Sold as the option "Maker Reflect S" on the Maker Reflect product page (code MAKER-REFLECT-S)
- The Ikedo Mini Sumo Robot V2 ships with 2 x Maker Reflect S edge sensors from March 2026 (Ikedo V2 product page); its older Getting Started guide links the Maker Reflect page
- Documents linked from the product page: datasheet only

## Use cases
- Line detection (datasheet: "Infrared sensors for line detection")
- Edge sensor on sumo robots (Ikedo Mini Sumo Robot V2 product page)

## Known limitations
- Only 5VDC is stated as the operating voltage; 3.3 V operation is not stated
- Reversed polarity will damage the sensor (no reverse polarity protection)
- Only the 3 mm optimal sensing distance is stated; no minimum/maximum range
- The datasheet calls OUT an analog output and also says "Digital IO Compatible / No ADC required"; output voltage levels are not stated
- Dimensions and sensor part number are not stated in the datasheet
- No Cytron library or code example

## Positioning (kept apart from specs)
- "The new Maker Reflect S comes with a smaller threshold sensing for more stable output" (product page)
- Sold under "Maker Reflect: Simplifying IR Reflectance Sensor for Beginner" as the newer option

## Price band
RM8.00–RM9.00 across Maker Reflect / Maker Reflect S (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-reflect-ir-reflectance-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit
