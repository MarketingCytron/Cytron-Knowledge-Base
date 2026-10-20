# Product fact sheets

## Product name
IR Sumo Start

## Aliases
IR-SUMO-START, IR Sumo Start, IR Sumo Start Module

## What it is
An infrared receiver module that gives a sumo robot a START/STOP signal from an IR remote. It outputs one digital signal: LOW in READY and STOP, HIGH in RUN, which the robot's controller reads to start or stop the motors.

## Specs and functions
- Product code: IR-SUMO-START
- Power input voltage (+): 3.0 V min, 5.5 V max (absolute maximum ratings); "compatible with 3V3 and 5V"
- Output signal (S): digital, 0 or 1 logic; HIGH level equals the power input voltage (Vs = Vin)
- Output signal voltage: 0–5 V at 5V power input; 0–3.3 V at 3.3V power input
- Output signal current: max 2.27 mA at 5V power input; max 1.50 mA at 3.3V power input
- IR receiver with built-in 38kHz bandpass filter
- Responds to IR signals from any IR remote; three remote buttons are bound to READY, RUN and STOP
- Power-up: LED GREEN for 1 second, then off; S = LOW (Receive Mode)
- READY: LED blinks PINK fast, then solid BLUE; S stays LOW
- RUN: LED solid GREEN; S = HIGH ("should trigger the sumo robot to start")
- STOP: LED blinks RED slowly, indefinitely; S = LOW ("should stop the robot immediately"); module must be manually reset before the next round
- Bind mode: hold the bind button more than 1 second; LED blinks BLUE, GREEN, RED (100ms each) three times, then off
- Binding: press remote button 1 (READY, LED blinks BLUE 3×), button 2 (RUN, GREEN 3×), button 3 (STOP, RED 3×); the module then returns to Receive Mode automatically
- Internal competition deck: IR noise makes the LED flash bright BLUE with no change to the output
- 1 × RGB indicator LED, 1 × bind button, 1 × Ø3.0 mm mounting hole (optional mounting)
- Dimensions (datasheet Figure 2): 14.0 mm wide; board body 21.0 mm; mounting-hole tab 5.4 mm; 23.3 mm from mounting-hole centre to bottom edge; header pins extend ~6.0 mm
- Datasheet: Rev 1.0, April 2025
- Supply current: [NOT STATED]
- Operating temperature: [NOT STATED]
- IR receiving range and angle: [NOT STATED]
- Packing: module, 10 cm GVS female-to-female extension, 3D-printed case; no IR remote (product page)
- Size 32.4 × 14 × 10 mm, 2 g (product page)
- Works at 5 V and 3.3 V (product page)

## Interfaces and compatibility
- 3-pin header, left to right: − (GND), + (power input, 3.3V or 5V), S (output signal); power is the middle pin
- Read S as a digital input: HIGH = RUN, LOW = READY / STOP / power-up
- Cytron PIRC 2025 sample code (Arduino, Cytron Maker Sumo library, "based on Ikedo Mini V2") uses `pinMode(IR_SUMO_START, INPUT)` with `#define IR_SUMO_START 9`
- PIRC 2025 deck photos show the module plugged into robots built on the Maker Mini Sumo controller with a 3-wire jumper cable
- URC10 1KG Autonomous Sumo Robot Starter Kit (Auto Kit Mode, internal integration notes): + to 5V, − to GND, S to D2, `pinMode(..., INPUT)`
- Works with any IR remote (e.g. a TV remote); remote included: [NOT STATED]
- Supported IR protocols: [NOT STATED]
- Libraries / MicroPython / CircuitPython / MakeCode: [NOT STATED]

## Use cases
- Giving START/STOP to an autonomous sumo robot through a TV remote (IR signal)
- Sumo robot competitions where both robots must start at the same time, with no early start
- Stopping a robot wirelessly for safety
- PIRC 2025 competition robots
- URC10 1KG Autonomous Sumo Robot Starter Kit (Auto Kit Mode)

## Known limitations
- Power input must stay within 3.0–5.5 V; the output HIGH level equals the supply voltage, so a 5V supply gives a 5 V signal
- Output signal current max 2.27 mA (5V) / 1.50 mA (3.3V) — logic signal only
- STOP latches: the module must be manually reset to be used again for the next round
- READY keeps the output LOW; only RUN gives HIGH
- Remote buttons must be bound before use; whether bindings are kept after power-off is [NOT STATED]
- Reverse-polarity protection: [NOT STATED]
- Must be mounted away from noise, easy to access, and at the best angle to receive the judge's signal
- The robot's code must keep checking S to stop when STOP is sent; the module does not stop motors itself

## Positioning (kept apart from specs)
- Internal PIRC 2025 deck: "2 robot yang berlawan bergerak serentak. Tiada isu robot bergerak lebih awal." (the two opposing robots move at the same time; no early-start issue)
- "Keselamatan lebih terjamin. Robot boleh dihentikan secara wireless." (safer; the robot can be stopped wirelessly)

## Price band
RM23.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ir-sumo-start-module

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

