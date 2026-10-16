# Product fact sheets

## Product name
MCP9700 Linear Temperature Sensor (LM35 Compatible) — BCY-TEMP-MCP9700

## Aliases
BCY-TEMP-MCP9700, MCP9700 Linear Temperature Sensor, MCP9700 Linear Temperature Sensor (LM35 Compatible), MCP9700 Temperature Sensor, Cytron MCP9700, MCP9700 Sensor by Cytron

## What it is
A small three-pin breakout board (GND, VCC, OUT) carrying a Microchip MCP9700 analog temperature sensor IC. The output voltage rises 10.0 mV per °C with 500 mV at 0 °C, and the board runs from 2.3 to 5.5 V.

## Specs and functions
- Sensor IC: MCP9700 (Cytron datasheet title and product name); MCP9700 vs MCP9700A grade [NOT STATED]
- VCC voltage: 2.3 V min, 5.5 V max (datasheet)
- Sensor output voltage (VOUT): 100 mV min, 2000 mV max (datasheet)
- Output voltage at TA = 0 °C: 500 mV typ (datasheet)
- Temperature coefficient (TC): 10 mV/°C typ (datasheet)
- Temperature range: −40 °C min, +150 °C max (datasheet)
- Current consumption: 6 µA typ, 12 µA max (datasheet)
- Output current: 100 µA max (datasheet)
- Output type: analog voltage on OUT (datasheet)
- Conversion equation: TA (°C) = (VOUT − 500 mV) / 10 mV/°C (datasheet Section 3)
- Accuracy: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Weight: [NOT STATED]
- Reverse-polarity protection: [NOT STATED]
- Datasheet: BCY-TEMP-MCP9700 Linear Temperature Sensor Datasheet, Rev 1.0, August 2023

## Interfaces and compatibility
- Pins: GND (ground), VCC (power input, 2.3–5.5 V), OUT (analog output, 10.0 mV/°C) (datasheet)
- Connector type: [NOT STATED] in datasheet text
- No I²C, SPI, Grove or Maker Port connector named; needs one ADC-capable pin on the host (datasheet)
- Compatible boards named by Cytron: Arduino UNO or Maker UNO, Raspberry Pi Pico (Cytron GitHub example README); "applicable to other microcontroller analog pin" (Cytron GitHub)
- Example code: Arduino (A0, 5 V / 10-bit ADC conversion), CircuitPython (board.GP28, 3.3 V / 65536), MicroPython (machine.ADC(28), 3.3 V / 65536) at https://github.com/CytronTechnologies/Cytron-BCY-TEMP-MCP9700 (Cytron GitHub)
- Warranty: 12 months (product page)

## Use cases
- Reading ambient temperature on an Arduino UNO / Maker UNO analog pin (Cytron GitHub example)
- Reading ambient temperature on a Raspberry Pi Pico with CircuitPython or MicroPython (Cytron GitHub example)

## Known limitations
- Analog output only; no digital interface, library or calibration register (datasheet)
- Output must be corrected for the 500 mV offset at 0 °C; the equation is TA = (VOUT − 500) / 10 (datasheet)
- Output current is limited to 100 µA max; the output is a signal for an ADC pin, not a load driver (datasheet)
- Accuracy is not stated in the Cytron datasheet
- Dimensions are not stated in the datasheet text
- Reverse-polarity protection is not stated

## Positioning (kept apart from specs)
- Product page name: "MCP9700 Linear Temperature Sensor (LM35 Compatible)" (product page); the datasheet does not mention the LM35

## Price band
RM7.77 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-mcp9700-linear-temperature-sensor-by-cytron

## Datasheet
https://docs.google.com/document/d/1Yg4krOVZN__Q0NPKvb4om0IJVZMJksBEIjuhJPlcBTM/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1Yg4krOVZN__Q0NPKvb4om0IJVZMJksBEIjuhJPlcBTM/edit
