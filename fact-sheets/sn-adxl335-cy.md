# Product fact sheets

## Product name
3-Axis Accelerometer — SN-ADXL335-CY

## Aliases
SN-ADXL335-CY, 3-Axis Accelerometer, Cytron 3-Axis Accelerometer, Cytron ADXL335 Breakout, ADXL335 3-Axis Accelerometer Breakout

## What it is
A breakout board for the Analog Devices ADXL335 ±3 g 3-axis analog accelerometer, with an on-board 3.3 V regulator so it runs from 2.5 V to 6 V. It is out of stock on my.cytron.io (2026-10-19).

## Specs and functions
- Sensor IC: Analog Devices ADXL335 (product page)
- Axes: 3 (product page)
- Range: ±3g (product page)
- Regulator: on-board 3.3V regulator, MCP1825S-3302E/DB, fed from the 5V pin (product page, Cytron schematic)
- Operating voltage: 2.5V–6.0V (product page)
- Typical current: 300 µA (product page features); the page description says "only 320uA" (product page)
- Bandwidth: adjustable with one capacitor per axis; the included 0.1 µF capacitors set each axis to 50 Hz (product page)
- Fully assembled and tested (product page)
- Dimension: 19.5mm x 22mm (product page)
- Chip sensitivity: 300 mV/g typ at VS = 3 V, ratiometric to supply (ADXL335 vendor datasheet, chip-level)
- Chip 0 g output: nominally VS/2 (ADXL335 vendor datasheet, chip-level)
- Chip operating temperature: −40 °C to +85 °C (ADXL335 vendor datasheet, chip-level)
- Board pinout (7-way): 3V3, 5V, GND, X, Y, Z, ST (Cytron schematic Rev 1, product photo)
- Power LED: green (Cytron schematic)
- Weight: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Outputs: analog voltage per axis (X, Y, Z) (ADXL335 vendor datasheet); needs three ADC inputs
- Power options: up to 6 V on the 5V pin (through the regulator), or regulated 3.3 V on the 3V3 pin (bypasses the regulator; 3.6 V chip maximum) (Cytron schematic)
- Self-test: ST broken out on pin 7 (Cytron schematic)
- Library / sample code: [NOT STATED]

## Use cases
- Tilt-angle measurement (Cytron tutorial title "Measuring Tilt Angle with Gyro and Accelerometer", product page)

## Known limitations
- Out of stock on my.cytron.io (2026-10-19)
- Bandwidth is set to 50 Hz per axis by the fitted 0.1 µF capacitors (product page)
- Analog outputs are ratiometric to the chip supply, so zero-g and sensitivity scale with it (ADXL335 vendor datasheet)
- The product page states two current figures (300 µA and 320 µA)
- The page's resource list mislabels the datasheet as "ADXL355 Datasheet" (product page)
- One linked tutorial ("Accelerometer ADXL335 Fast Test and Angle Test") returns 404

## Positioning (kept apart from specs)
- "only 320uA" current draw (product page)

## Price band
RM38.85 (10+ RM35.70, 30+ RM31.08) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-3-axis-accelerometer

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-3-axis-accelerometer
