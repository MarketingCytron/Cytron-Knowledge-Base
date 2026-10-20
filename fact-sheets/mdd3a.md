# Product fact sheets

## Product name
MDD3A 3Amp 4V-16V DC Motor Driver (2 Channels)

## Aliases
MDD3A, 3Amp 4V-16V DC Motor Driver, 3Amp 2 Channel 4V-16V DC Motor Driver

## What it is
A 2-channel, bi-directional motor driver for two brushed DC motors or one stepper motor, powered from 4–16 VDC. Each motor is controlled by two PWM inputs (A and B).

## Specs and functions
- Product code: MDD3A
- Datasheet: Rev 1.0, March 2019 (spec table titled "Absolute Maximum Ratings")
- Power input voltage (Vin): 4–16 VDC (VB+ positive, VB- negative; datasheet: "Connect to battery")
- Maximum motor current: 3 A continuous, 5 A peak (< 5 seconds) (datasheet); product listing: "3 Amp per channel continuously without any additional heatsink"
- Channels: 2 (Motor 1, Motor 2), bi-directional
- Output stage: "discrete MOSFETs H-Bridge design" (product listing)
- Logic input voltage (M1A, M1B, M2A, M2B): low 0–0.5 V, high 1.7–12 V
- PWM frequency: DC to 20 kHz (output frequency is same as input frequency)
- DC +5V output (5VO): 200 mA max, can power the microcontroller; product listing: buck-boost regulator, 5V from input as low as 4V
- Input truth table per motor: Low/Low = Brake; High/Low = Forward; Low/High = Backward; High/High = Brake
- Actual direction depends on motor wiring; swapping MA and MB reverses it
- Control: two PWM inputs per motor (no DIR pin); no RC, analog or serial mode stated
- Test buttons: M1A/M2A forward, M1B/M2B backward; motor runs at full speed
- Motor status LEDs: M1A/M2A forward, M1B/M2B backward
- Power LED
- Reverse polarity protection on the power input
- Thermal protection: [NOT STATED]
- Over-current / short-circuit protection: [NOT STATED]
- Under-voltage protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Terminal type and wire size: [NOT STATED]
- Packing list: 1 x 3Amp 4V-16V DC Motor Driver (2 Channels) (product listing)
- 3 A per channel continuous, 5 A peak; reverse polarity protection (product page)

## Interfaces and compatibility
- Pins: VB+, VB- (power input terminal); motor output terminals; M1A, M1B, M2A, M2B (PWM inputs); 5VO; GND
- Logic: "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." (product listing)
- Motors: two brushed DC motors, or one unipolar/bipolar stepper motor
- Arduino: Cytron Motor Drivers Library (version 1.0.1), `#include "CytronMotorDriver.h"`, `CytronMD motor1(PWM_PWM, pinA, pinB);`, `setSpeed(-255..255)`; `setSpeed(0)` gives Brake
- Official example: PWM_PWM_DUAL (lists MAKER-DRIVE and MDD3A); wiring D3 → 1A, D9 → 1B, D10 → 2A, D11 → 2B, GND → GND
- Host GND must connect to the driver GND
- MicroPython / CircuitPython / MakeCode / PLC examples: [NOT STATED]

## Use cases
- Small size mobile robot for competition or school projects
- Motor driver for a mobile robot
- Driving a stepper motor (one unipolar/bipolar stepper)
- Bidirectional control of two brushed DC motors
- Host controllers such as Arduino, Raspberry Pi or PLC

## Known limitations
- Power input absolute maximum 16 VDC (minimum 4 VDC)
- Motor current 3 A continuous; 5 A peak only for < 5 seconds
- Datasheet current table does not say "per channel"; the per-channel 3 A figure comes from the product listing
- Logic input high level absolute maximum 12 V
- No coast state: both Low/Low and High/High give Brake
- No DIR pin: PWM+DIR (PWM_DIR) code does not suit this board; both A and B pins need PWM for speed in both directions
- 5VO limited to 200 mA
- Only reverse polarity protection is stated (power input only); thermal and over-current protection not stated
- Test buttons run the motor at full speed
- Motor direction depends on wiring
- Datasheet says to connect a battery; SMPS/bench supply guidance not stated

## Positioning (kept apart from specs)
- Product listing: "Looking for a motor driver for your mobile robot?"
- "it's compatible with wide variety of host controller (e.g. Arduino, Raspberry Pi, PLC)"
- Reverse polarity protection pitched against "a very common mistake done by a lot of makers even for the very experienced one" (datasheet)

## Price band
- RM39.06 on my.cytron.io, availability 90 (read 2026-10-19); USD 7.00 on Cytron's Tindie store (sold out there since 2 Aug 2026)

## Product page
https://my.cytron.io/p-mdd3a

## Datasheet
https://docs.google.com/document/d/1ax3gSo0srTzoSr2bo8ETLym0OqrYjlk_JCZK4kxtfXg/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1ax3gSo0srTzoSr2bo8ETLym0OqrYjlk_JCZK4kxtfXg/edit
