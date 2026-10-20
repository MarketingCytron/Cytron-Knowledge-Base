# Product fact sheets

## Product name
10Amp 7V-30V DC Motor Driver Shield for Arduino

## Aliases
SHIELD-MD10, SHIELD-MD10 R2, Cytron SHIELD-MD10, Cytron 10A Motor Driver Shield, Shield MD10 Rev 2.0

## What it is
A single-channel Arduino shield that drives one brushed DC motor at up to 10 A continuous. Speed and direction come from a PWM pin and a DIR pin selected with mini jumpers.

## Specs and functions
- Motor supply voltage (Rev 2.0): feature list "7V to 30V"; the same manual's Absolute Maximum Rating table says 7 V min, 25 V max (both from the Rev2.0 user manual)
- Rev 1.0: 7 V to 25 V
- Maximum continuous motor current: 10 A
- Peak motor current: 15 A, must not exceed 10 seconds
- 1 channel, bi-directional
- Logic input high level (VIOH): 3 V min, 5.5 V max
- Logic input low level (VIOL): 0 V min, 0 V typical, 0.5 V max
- 3.3V and 5V logic level input
- Maximum PWM frequency: 10 kHz
- Fully NMOS H-Bridge; no heat sink is required
- Test Button A (current A to B) and Test Button B (current B to A)
- Red LED A, Red LED B, Green Power LED
- Reset button for the Arduino main board
- Rev 2.0 boards labelled "SHIELD-MD10 R2" on front and back
- Packing list: 1 x SHIELD-MD10 shield, 2 x mini jumper
- Warranty: 12 months, manufacturing defects only
- Over-current, thermal, under-voltage, reverse-polarity protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Product page: 7–25 V (Rev1.0), 7–30 V (Rev2.0); 10 A continuous, 15 A peak for 10 s; regenerative braking; PWM up to 10 kHz

## Interfaces and compatibility
- PWM pin selectable: D3, D5, D6, D9, D10 or D11 (default D3)
- DIR pin selectable: D2, D4, D7, D8, D12 or D13 (default D2)
- Terminal block: POWER +, POWER -, Motor Output A, Motor Output B
- Stackable digital, analog and power headers; only RST and GND of the power header connect to the shield
- Optional External Control header for microcontrollers other than Arduino
- Compatible with Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo "and possibly other pin compatible main boards"
- Arduino library: Cytron Motor Drivers Library, PWM_DIR example
- 3D files (STEP, IGS) for SHIELD-MD10 R2 on GitHub

## Use cases
- Controlling one high-current brushed DC motor from an Arduino UNO, Duemilanove, Mega or Leonardo
- Controlling the motor from other microcontrollers through the Optional External Control header

## Known limitations
- Single channel only
- Peak 15 A for no more than 10 seconds
- PWM frequency up to 10 kHz
- The shield does not power the Arduino; the Arduino needs its own power source
- Power up the Arduino and load the sketch before powering the shield
- Rev2.0 manual states two different maximum voltages (30 V feature list, 25 V table)
- Rev 1.0 boards: 25 V maximum
- No protection features stated

## Positioning (kept apart from specs)
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay."

## Price band
RM67.20 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino

## Datasheet
https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view
