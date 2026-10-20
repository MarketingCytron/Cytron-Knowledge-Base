# Product fact sheets

## Product name
Maker Reflect: Simplifying IR Reflectance Sensor for Beginner (MAKER-REFLECT)

## Aliases
MAKER-REFLECT, V-MAKER-REFLECT, Maker Reflect, Cytron Maker Reflect, Maker Reflect: Simplifying IR Reflectance Sensor for Beginner, Maker Reflect IR Reflectance Sensor, Maker Reflectance Sensor, Analog Reflectance Sensor (Line Detector)

## What it is
A tiny analog infrared reflectance sensor (line detector) with a 3-pin VCC/GND/OUT connector; its analog output voltage rises on darker surfaces. It runs from 3.0 V to 5.5 V and senses 1 mm to 40 mm at VCC = 5 V with a black line on a white surface.

## Specs and functions
- Sensor type: IR Reflectance Sensor — infrared sensors for line detection (datasheet)
- VCC voltage: 3.0 V min, 5.5 V max (datasheet absolute maximum ratings)
- Analog output voltage: 0 V min, VCC max (datasheet)
- Output rule: higher voltage = darker surface (datasheet)
- Sensing distance: 1 mm min, 40 mm max, at VCC = 5 V with a black line on white surface (datasheet)
- Sensing distance may reduce if VCC is less than 5 V or the line-background contrast is low (datasheet)
- Reverse polarity protection: none — "Reversed Polarity will damage the sensor" (datasheet)
- On-board threshold, trimmer, calibration or switch: none listed (datasheet)
- Indicator LED: none listed (datasheet)
- Supply current: [NOT STATED]
- Sensor IC / IR part number: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Operating temperature: [NOT STATED]
- Datasheet: MAKER-REFLECT Datasheet, "Analog Reflectance Sensor (Line Detector)", Rev 1.0, November 2019
- Warranty: 12 months (product page)
- Size 18.1 × 8.4 × 4.2 mm excluding header pin; mounting hole at the centre (product page)
- Optimal distance 1–40 mm (product page comparison table)

## Interfaces and compatibility
- Connector: 3 pins — VCC (power input), GND (ground), OUT (analog output)
- Read with any analog input (ADC) pin; no library needed
- Compatible boards named in the datasheet: [NOT STATED]
- SUMO:BIT edge-sensor ports accept "Maker Reflect or any other analog sensors" (SUMO:BIT datasheet)
- Maker Mini Sumo Controller edge ports (A0/A1, analog) are read with the Cytron Maker Sumo Library (Maker Mini Sumo datasheet and library)
- Sold on the same product page as the newer Maker Reflect S (option "Maker Reflect S", code MAKER-REFLECT-S); the product page says "The new Maker Reflect S comes with a smaller threshold sensing for more stable output"
- Documents linked from the product page: datasheet only

## Use cases
- Line detection (datasheet: "Infrared sensors for line detection")
- Edge sensor for sumo robots (SUMO:BIT and Maker Mini Sumo edge-sensor ports)

## Known limitations
- Analog output only; the threshold must be set in code
- Reversed polarity will damage the sensor (no reverse polarity protection)
- Sensing distance of 1 mm to 40 mm applies at VCC = 5 V with a black line on white; it reduces at lower VCC or low contrast
- Supply current, dimensions and sensor part number are not stated in the datasheet
- No Cytron library or code example

## Positioning (kept apart from specs)
- "Simplifying IR Reflectance Sensor for Beginner" (product page title)
- Cytron's beginner-series reflectance sensor; the newer Maker Reflect S is positioned as the more stable-output option on the same page

## Price band
RM8.00–RM9.00 across Maker Reflect / Maker Reflect S (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-maker-reflect-ir-reflectance-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit
