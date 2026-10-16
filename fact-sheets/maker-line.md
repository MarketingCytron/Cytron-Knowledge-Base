# Product fact sheets

## Product name
Maker Line

## Aliases
MAKER-LINE, Maker Line, Maker Line: Simplifying Line Sensor for Beginner, Maker Line Sensor, Cytron Maker Line

## What it is
A line sensor with 5 infrared sensors that gives 5 digital outputs (one per sensor) and 1 analog output for line position. It runs from 3.0–5.5 V and is calibrated with one button.

## Specs and functions
- Product code: MAKER-LINE
- Datasheet: Rev 1.0, July 2019 (spec table titled "Absolute Maximum Ratings")
- VCC voltage: 3.0–5.5 V; reverse polarity protection on VCC and GND
- Sensors: 5 infrared line sensors (S1–S5)
- Digital outputs D1–D5: one per sensor, High when the line is detected; low level 0–0.5 V, high level 0.7×VCC to VCC
- Analog output AN: 0 to VCC; voltage represents line position
- Analog output vs position: line not found < 0.1 × Vcc; Left 0.1 × Vcc; Center Vcc / 2; Right 0.9 × Vcc; cross detected (all sensors on) > 0.9 × Vcc
- Analog output at Vcc = 5 V: 0–0.5 V not found, 0.5 V left, 2.5 V center, 4.5 V right, 4.5–5 V cross; at Vcc = 3.3 V: 0–0.33 V, 0.33 V, 1.65 V, 2.97 V, 2.97–3.3 V
- Sensing distance: 4–40 mm (VCC = 5V, black line on white surface); may reduce if VCC is less than 5V or contrast is low
- Sensor refresh rate: 200 Hz
- Recommended line width: 13–30 mm
- Line Color Switch: Light / Dark
- Digital truth table: Light switch + light surface = High; Light + dark = Low; Dark + light = Low; Dark + dark = High
- Calibration: mount the sensor as used and power up; set the line colour switch; press and hold the calibrate button for more than 2 seconds; all 5 LEDs blink in calibration mode; move the sensor across the line so all sensors see it; press the button again to exit
- Calibration result: running light = successful; fast blink = failed (contrast too low or sensor too high)
- Calibration can also be entered/exited by shorting CAL to GND
- Calibration data saved in EEPROM, kept after power-off; recalibrate only if sensor height, line or background colour changes
- Indicators: power LED; 5 sensor LEDs (on when the line is detected)
- Dimensions: [NOT STATED]
- Current consumption: [NOT STATED]
- Sensor spacing: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- I/O connector pins: VCC, GND, AN, CAL, D1, D2, D3, D4, D5
- Product listing: "DC 3.3V and 5V compatible (With reverse polarity protection)"
- Product listing: "Support wide range of controllers such as Arduino, Raspberry Pi, etc."
- Connection diagrams for digital output and analog output in the datasheet
- Software library / example code: [NOT STATED]
- Packing list: 1 x Maker Line; 2 x 5mm PCB stand (screw and nut); 2 x 10mm PCB stand (screw and nut); 2 x M3 screw 4mm; 2 x M3 nut

## Use cases
- Line following mobile robot for school project or competition
- Automated Guided Vehicle (AGV) for industrial use
- Precise line-following control such as PID using the analog output

## Known limitations
- VCC absolute maximum 5.5 V (minimum 3.0 V)
- Sensing distance 4–40 mm is specified at VCC = 5V with a black line on white; it may reduce at lower VCC or low contrast
- Recommended line width 13–30 mm
- Digital outputs swing to VCC (high level 0.7×VCC to VCC); analog output spans 0 to VCC
- Must be calibrated before use; sensor height must not change during calibration; recalibrate after changing height, line colour or background colour
- Calibration fails if contrast is too low or the sensor is too high from the surface
- Analog output below 0.1 × Vcc means line not found; above 0.9 × Vcc means cross detected

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Line Sensor for Beginner"
- Product listing: no need to adjust a potentiometer for each sensor; "easy calibration process"
- Product listing: "Analog output also offers higher resolution compared to individual digital outputs"

## Price band
- USD 9.90 on Cytron's Tindie store (sold out since Jan 28, 2024), checked 16 Oct 2026

## Product page
https://my.cytron.io/p-maker-line-simplifying-line-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1wZwWl72CKkajTDIyiMxSQ3bwXbWbqW0eq7rdg2MUPeU/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1wZwWl72CKkajTDIyiMxSQ3bwXbWbqW0eq7rdg2MUPeU/edit
