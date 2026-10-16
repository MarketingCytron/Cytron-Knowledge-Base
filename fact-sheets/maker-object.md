# Product fact sheets

## Product name
Maker Object

## Aliases
MAKER-OBJECT, Maker Object, Maker Object Sensor, Cytron Maker Object, Maker Object: Simplifying Object Sensor for Beginner

## What it is
A small digital infrared object sensor. It sends modulated IR light and pulls its output LOW when it picks up IR light reflected from an object within the set range.

## Specs and functions
- Product code: MAKER-OBJECT
- VCC voltage: 4.5 V min, 5.5 V max
- Output: NPN output with internal pull-up; LOW when an object is detected (active low)
- Output voltage, object detected: 0 V min, 0.8 V max
- Output voltage, no object detected: VCC - 0.5 V min, VCC max
- Sensing distance (adjustable), white surface (A4 size): 40 cm min, 140 cm max
- Sensing distance (adjustable), black surface (A4 size): 15 cm min, 60 cm max
- Response time (based on IR sensor's datasheet): 180 µs min, 350 µs max
- IR transmitter: infrared LED that transmits modulated infrared light
- IR receiver with built-in 38kHz bandpass filter
- Sensing range trimmer, adjusted with a small Phillips head screwdriver through a small opening at the front of the sensor
- Maximum distance setting: power on, turn the trimmer clockwise until the output LED turns off, then counter-clockwise slowly until the LED just turns on
- Minimum distance setting: power on, turn the trimmer counter-clockwise until the output LED turns off, then clockwise slowly until the LED just turns on
- Power LED (on when powered); Output LED (on when an object is detected)
- Reverse polarity protection on the power input
- Gives a detected / not-detected signal only, not a distance value
- Datasheet: Rev 1.0, December 2019
- Dimensions: [NOT STATED]
- Supply current: [NOT STATED]
- IR LED / IR receiver part numbers: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- 3-pin connector: 5V (power input), GND (ground), OUT (NPN output with internal pull-up, active low)
- Not a Grove or Maker Port connector
- Read OUT as a plain digital input; no library needed
- Maker Mini Sumo Controller: 5 opponent-sensor ports, pulled up to +5V, active low, with status LEDs; MAKER-OBJECT ports on the bottom layer are wired in parallel
- Cytron Maker Sumo Library (Arduino): opponent inputs OPP_FC (D6), OPP_FL (D5), OPP_FR (D7), OPP_L (D12), OPP_R (D13); AutoSumo example treats LOW as opponent detected
- Ikedo Mini Sumo Robot V2 kit includes 5 x Maker Object Sensor (opponent)
- Compatible boards listed in the datasheet: [NOT STATED]
- MicroPython / CircuitPython / MakeCode examples: [NOT STATED]

## Use cases
- Object detection: reflected IR light from an object turns the output LOW
- Opponent sensor in sumo robots (Ikedo Mini Sumo Robot V2 kit, with the Maker Mini Sumo Controller)

## Known limitations
- VCC must be 4.5–5.5 V; not for a 3.3 V supply
- Output HIGH (no object) is VCC - 0.5 V to VCC, close to the 5 V supply
- Sensing range depends on the target: 40–140 cm on a white A4-size surface but only 15–60 cm on a black A4-size surface
- Range is set by hand with the trimmer, not in code
- Digital output only; no distance reading
- Response time figure is taken from the IR sensor's datasheet
- Supply current and output current: [NOT STATED]

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Object Sensor for Beginner"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-maker-object-simplifying-object-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1SppJcAoTFGFDSaeBXrI4Ocq24quq-5ybFpr2bNsGMOI/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1SppJcAoTFGFDSaeBXrI4Ocq24quq-5ybFpr2bNsGMOI/edit
