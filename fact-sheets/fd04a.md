# Product fact sheets

## Product name
1.5Amp 7V-15V DC Motor Driver (4 Channels)

## Aliases
FD04A, FD04A Rev2.0, FD04A R2, FD04A-R2, 1.5Amp 7V-15V DC Motor Driver, 4 Channel Motor Driver

## What it is
A four-channel bi-directional driver for four brushed DC motors, built on the L298P IC. Each channel is controlled by a direction pin and an enable/speed-control pin.

## Specs and functions
- Channels: 4 (M1, M2, M3, M4), brushed DC motors
- Motor supply voltage: 7 V to 15 V (user manual). Product page title says 7V-15V; product page URL slug says "7v-25v"
- Continuous current: 1.5 A per channel (user manual spec table)
- Peak current: 2.5 A (user manual spec table; duration not stated)
- Manual introduction also says "up to 2A for each channel"; the spec table gives 1.5 A continuous and 2.5 A peak
- Logic input high: 3.3 V min, 5.5 V max; logic input low: 0 V to 0.5 V
- 3.3V and 5V logic level input
- Maximum PWM frequency: 10 kHz
- Control per channel: direction pin and enable/Speed Control pin; Enable 0 = both outputs LOW; Enable 1 + Direction 0 = OUT A HIGH, OUT B LOW; Enable 1 + Direction 1 = OUT A LOW, OUT B HIGH
- Driver IC: L298P
- Onboard 5V voltage regulator supplies the transistors and L298P and the V pin (5 V output)
- Reverse polarity protection on the motor supply
- Schottky clamping diodes
- Power toggle switch; feature list also states "Solid state switch for power"
- Test switches (A and B) for every channel
- Power indicator LED and motor status indicator LEDs
- 3 mm mounting holes for standard PCB stands
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Warranty: 12 months, manufacturing defects only
- In the box: 1 x FD04A Rev2.0 board, 1 x 14 way IDE cable connector

## Interfaces and compatibility
- Control pins through a 7 x 2 (14-way) IDE socket or through extra solder pads
- Control pins 1-8: Motor 1 direction, Motor 1 enable/Speed Control, Motor 2 direction, Motor 2 enable/Speed Control, Motor 3 direction, Motor 3 enable/Speed Control, Motor 4 direction, Motor 4 enable/Speed Control; V = 5V output; G = ground; x = not connected
- POWER terminal block for motor supply; four MOTOR terminal blocks M1 to M4
- IDE connector compatible with FD04A Rev1.0; can replace FD04A Rev1.0 in the PR19
- 5V from the V pin can supply the PR19 main board; do not supply another 5V into the V pin
- Arduino: Cytron Motor Drivers Library (PWM_DIR_DUAL example)
- PIC sample code: DIY-PR19-PIC16F777 on GitHub

## Use cases
- Driving four brushed DC motors from one board
- Replacing FD04A Rev1.0 in the PR19 robot or other FD04A projects

## Known limitations
- Motor supply maximum is 15 V
- Continuous current is 1.5 A per channel; peak 2.5 A
- Maximum PWM frequency 10 kHz
- Logic input maximum 5.5 V
- Do not supply 5V into the V pin
- Over-current, thermal and under-voltage protection are not stated

## Positioning (kept apart from specs)
- The manual describes FD04A Rev2.0 as "an enhanced version of FD04A Rev1.0"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-1.5amp-7v-25v-dc-motor-driver-4-channels

## Datasheet
https://docs.google.com/document/d/1SWq9YtW6gsr8n9eIz2X8ek8Na8KoJ30whM5HsOdCnSc/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1SWq9YtW6gsr8n9eIz2X8ek8Na8KoJ30whM5HsOdCnSc/edit
