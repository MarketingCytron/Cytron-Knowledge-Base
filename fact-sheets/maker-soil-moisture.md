# Product fact sheets

## Product name
Maker Soil Moisture Sensor (Capacitive) (MAKER-SOIL-MOISTURE)

## Aliases
MAKER-SOIL-MOISTURE, Maker Soil Moisture Sensor, Maker Soil Moisture Sensor (Capacitive), Maker Soil Moisture, Maker Soil Sensor, Maker Soil, Cytron Maker Soil Moisture Sensor, Cytron Soil Moisture Sensor

## What it is
A capacitive soil-moisture sensor on a probe-shaped board with a 4-pin Grove port (GND, VCC, DIS, OUT). It gives an analog output voltage that is higher when the soil has less moisture, has three LED indicators (Blue WET, Green MOIST, Red DRY), and a DIS pin that disables the sensor when HIGH.

## Specs and functions
- Sensing method: capacitive probe used to detect the presence of water in soil (datasheet)
- VCC voltage: 2.5 VDC min, 7.0 VDC max (datasheet absolute ratings)
- Analog output voltage (OUT): 1.0 V min, 5.2 V max (datasheet)
- Output rule: higher voltage = less moisture (datasheet)
- Disable pin threshold voltage (DIS): VCC − 0.8 V min; HIGH signal disables the sensor (datasheet)
- LED turn-on output voltage at VCC = 3.3 V: Blue (WET) 1.4–1.8 V; Green (MOIST) 1.8–2.1 V; Red (DRY) 2.1–2.3 V (datasheet)
- LED turn-on output voltage at VCC = 5.0 V: Blue (WET) 2.3–2.7 V; Green (MOIST) 2.7–3.1 V; Red (DRY) 3.1–3.6 V (datasheet)
- Current consumption: 5.4–5.6 mA at VCC = 3.3 V; 3.6–3.7 mA at VCC = 5.0 V (datasheet)
- Current consumption when disabled: 80–140 µA at VCC = 3.3 V; 140–180 µA at VCC = 5.0 V (datasheet)
- LED indicators turn on depending on the value of the output (datasheet)
- Calibration or threshold adjustment on board: none listed (datasheet)
- Sensor IC: [NOT STATED]
- Reverse polarity protection: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Operating temperature: [NOT STATED]
- Datasheet: MAKER SOIL MOISTURE SENSOR Datasheet, Rev 1.0, January 2022
- Warranty: 12 months (product page)
- No on-board voltage regulator; DIS HIGH disables the sensor (product page)
- Packing: sensor and 50 cm Grove-to-Grove cable (product page)

## Interfaces and compatibility
- Grove port, 4 pins: GND (ground), VCC (power input), DIS (disable pin, HIGH disables), OUT (analog output)
- Read OUT with any analog input (ADC); drive DIS from a digital output if power saving is needed; no library needed
- Compatible boards named in the datasheet: [NOT STATED]
- Cytron board examples that read it on a Grove analog port: Robo Pico (Grove 6, GP27), Robo ESP32 (Grove 7, D36), Maker Uno RP2040 example repo (Cytron GitHub)
- Sold with Grove cable options (product page)
- Documents linked from the product page: datasheet and 3D CAD (https://drive.google.com/file/d/1stZDBLdZ1141wIdrRsNFRAVAT8iRiCNg/view)

## Use cases
- Detect the presence of water in soil (datasheet)
- Soil moisture reading on a Grove analog port of a Cytron board (Cytron GitHub examples)
- Cytron tutorial: 3D Printed Self-Watering Pot featuring Maker Soil Moisture Sensor (2022-03-25)
- Cytron tutorial: [Monitor Soil Moisture With Maker Nano RP2040 And Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/maker-nano-rp2040-with-maker-soil-moisture-sensor)
- Cytron tutorial: [3D Printed Battery Holder for Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/3d-printed-battery-holder-for-maker-soil-moisture-sensor)
- Cytron tutorial: [3D Printed Self-Watering Pot with Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/3d-printed-self-watering-pot-featuring-maker-soil-moisture-sensor)

## Known limitations
- Output voltage can reach 5.2 V; at VCC = 5.0 V the DRY band (3.1–3.6 V) is above a 3.3 V ADC's full scale
- DIS threshold is VCC − 0.8 V, so at VCC = 5 V a 3.3 V GPIO may not reach it
- LED turn-on bands differ between VCC = 3.3 V and VCC = 5.0 V; the output is a relative reading, not a moisture percentage
- Current draw is higher at 3.3 V (5.4–5.6 mA) than at 5.0 V (3.6–3.7 mA)
- Maximum supply is 7.0 VDC
- Sensor IC, reverse polarity protection, dimensions and probe depth are not stated in the datasheet
- Out of stock on my.cytron.io (2026-10-16)

## Positioning (kept apart from specs)
- Cytron "Maker" series sensor: a capacitive (not resistive) soil moisture sensor with Grove connection and LED moisture indicators

## Price band
RM20.58, out of stock (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-maker-soil-moisture-sensor

## Datasheet
https://docs.google.com/document/d/1XErDF1j2W9LaeTdB7ySIbm4T83_ov0TZtVC47lmC7Pg/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1XErDF1j2W9LaeTdB7ySIbm4T83_ov0TZtVC47lmC7Pg/edit
