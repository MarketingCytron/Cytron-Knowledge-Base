# Product fact sheets

## Product name
Maker Drive

## Aliases
MAKER-DRIVE, Maker Drive, Maker Drive: Simplifying H-Bridge Motor Driver for Beginner

## What it is
A 2-channel, bi-directional H-bridge motor driver for two brushed DC motors or one stepper motor, powered from 2.5–9.5 VDC. Each motor is controlled by two PWM inputs (A and B).

## Specs and functions
- Product code: MAKER-DRIVE
- Datasheet: Rev 1.0, Feb 2019 (spec table titled "Absolute Maximum Ratings")
- Power input voltage: 2.5–9.5 VDC (VB+ positive, VB- negative; datasheet: "Connect to battery")
- Maximum motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds)
- Channels: 2 (Motor 1, Motor 2), bi-directional
- Logic input voltage (M1A, M1B, M2A, M2B): low 0–0.5 V, high 1.7–6 V
- PWM frequency: DC to 20 kHz (output frequency is same as input frequency)
- DC +5V output (5VO): 200 mA max, can power the microcontroller; product listing: buck-boost regulator, 5V from input as low as 2.5V
- Input truth table per motor: Low/Low = Brake; High/Low = Forward; Low/High = Backward; High/High = Coast (outputs Hi-Z/open)
- Actual direction depends on motor wiring; swapping MA and MB reverses it
- Control: two PWM inputs per motor (no DIR pin); no RC, analog or serial mode stated
- 4 test buttons (2 per channel): M1A/M2A forward, M1B/M2B backward; motor runs at full speed
- 4 motor status LEDs (2 per channel): M1A/M2A forward, M1B/M2B backward
- Power LED
- Reverse polarity protection on the power input
- Temperature protection: H-bridge IC cuts output to the motor when its internal temperature is over 150 °C
- Dimensions: 43 mm (W) × 35 mm (L) × 14 mm (H) (product listing; datasheet gives a drawing only)
- Driver IC part number: [NOT STATED]
- Over-current / short-circuit protection: [NOT STATED]
- Under-voltage protection: [NOT STATED]
- Operating temperature: [NOT STATED]
- Terminal type and wire size: [NOT STATED]

## Interfaces and compatibility
- Pins: VB+, VB- (power input terminal); motor output terminals; M1A, M1B, M2A, M2B (PWM inputs); 5VO; GND
- Logic: "Inputs compatible with 1.8V, 3.3V and 5V logic (Arduino, Raspberry Pi, etc)." (product listing)
- Motors: brushed DC motors (2) or one stepper motor (datasheet connection diagrams)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), `#include "CytronMotorDriver.h"`, `CytronMD motor1(PWM_PWM, pinA, pinB);`, `setSpeed(-255..255)`; `setSpeed(0)` gives Brake
- Official example: PWM_PWM_DUAL (lists MAKER-DRIVE and MDD3A); wiring D3 → 1A, D9 → 1B, D10 → 2A, D11 → 2B, GND → GND
- Host GND must connect to the driver GND
- MicroPython / CircuitPython / MakeCode: [NOT STATED]
- Packing list: [NOT STATED]

## Use cases
- Beginner motor driver projects ("designed for simplicity and with the beginner in mind")
- Replacing an L298N motor driver
- Line following ("Most application perform better in Regen braking for example line following")
- Driving two brushed DC motors
- Driving a stepper motor ("additional bonus feature")
- Powering the project from a single power source (5V output powers the controller)

## Known limitations
- Power input absolute maximum 9.5 VDC (minimum 2.5 VDC)
- Motor current 1 A continuous per channel; 1.5 A peak only for < 5 seconds
- Logic input high level absolute maximum 6 V (not for 12 V/24 V logic)
- High/High on the inputs gives Coast, not Brake; use Low/Low for Brake
- No DIR pin: PWM+DIR (PWM_DIR) code does not suit this board; both A and B pins need PWM for speed in both directions
- 5VO limited to 200 mA
- Thermal cut-off at 150 °C IC temperature; over-current and short-circuit protection not stated
- Reverse polarity protection is on the power input only
- Test buttons run the motor at full speed
- Motor direction depends on wiring
- Datasheet says to connect a battery; SMPS/bench supply guidance not stated

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying H-Bridge Motor Driver for Beginner"
- Product listing: "ideal to replace the L298N"
- "Maker Drive is designed for simplicity and with the beginner in mind!"
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay"
- "Regenerative Braking"

## Price band
- USD 3.80 on Cytron's Tindie store ("Sold out since Nov 17, 2022"), checked 16 Oct 2026

## Product page
https://www.cytron.io/p-maker-drive

## Datasheet
https://docs.google.com/document/d/1XakJWz9DAtrMc_Jf75FnDXs4gwT_osCSj3Rbx1OU7bM/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1XakJWz9DAtrMc_Jf75FnDXs4gwT_osCSj3Rbx1OU7bM/edit
