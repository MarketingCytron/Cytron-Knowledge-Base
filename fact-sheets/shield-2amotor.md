# Product fact sheets

## Product name
0.8Amp 5V-26V DC Motor Driver Shield for Arduino (2 Channels)

## Aliases
SHIELD-2AMOTOR, Cytron 2A Motor Driver Shield, 2A Motor Driver Shield, 0.8Amp 5V-26V DC Motor Driver Shield for Arduino, 0.8Amp 5V-26V DC Motor Driver Shield

## What it is
An Arduino shield that drives two brushed DC motors in both directions using the L298P IC. Mini jumpers select sign-magnitude or locked-antiphase control and the motor power source.

## Specs and functions
- Channels: 2, brushed DC motors
- Motor supply voltage: 5 V to 26 V
- Continuous current: 0.8 A per channel
- Peak current: 2 A per channel; the spec table carries the footnote "*Must not exceed 10 seconds" without marking which row it applies to
- The "2A" in the product code and manual title is the peak rating; the product page title's "0.8Amp" is the continuous rating
- Logic input high: 3.3 V min, 5.5 V max; logic input low: 0 V to 0.5 V
- 3.3V and 5V logic level input
- Maximum PWM frequency: 10 kHz
- Driver IC: L298P
- Control modes: Signed Magnitude (default) and Locked Anti-Phase, selected by moving 4 mini jumpers
- Power source selection: external (PWRIN) or internal (VIN, from the Arduino power source)
- Reverse polarity protection on the external power (PWRIN) input
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Test switch for both channels; PWR LED (motor power indicator)
- Reset button for the Arduino main board
- Stackable I/O header pins
- LSS05 connector
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Warranty: 12 months, manufacturing defect only
- In the box: 1 x SHIELD-2AMOTOR, 5 x mini jumper
- Power source jumper: from the Arduino (VIN, 6.5–12 V) or an external supply (5–26 V); external supply recommended (product page)

## Interfaces and compatibility
- Signed Magnitude: DIR 1 = D4, EN 1 = D5, EN 2 = D6, DIR 2 = D7
- Locked Anti-Phase: DIR 1 = D5, EN 1 = D4, EN 2 = D7, DIR 2 = D6
- LSS05 pins: 5V, GND, A1 = O1, A2 = O2, A3 = O3, A4 = O4, A5 = O5, D8 = Cal
- MOTOR1 and MOTOR2 terminal blocks; PWRIN terminal for external power
- Compatible with Arduino Uno, Leonardo, Mega, Due and possibly other pin compatible main boards
- Arduino: Cytron Motor Drivers Library (PWM_DIR_DUAL example); in Signed Magnitude mode use PWM pin 5 / DIR pin 4 for motor 1 and PWM pin 6 / DIR pin 7 for motor 2

## Use cases
- Controlling dual brushed DC motors with an Arduino Uno, Leonardo, Mega or Due
- Connecting the LSS05 line sensor directly to the Arduino through the shield

## Known limitations
- Continuous current is 0.8 A per channel; 2 A is peak only
- Motor supply maximum 26 V
- Reverse polarity protection covers the PWRIN input only
- Maximum PWM frequency 10 kHz; logic input maximum 5.5 V
- Uses Arduino pins D4 to D7 (and A1 to A5 and D8 when the LSS05 connector is used)

## Positioning (kept apart from specs)
[NOT STATED]

## Price band
RM55.44 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-0.8amp-5v-26v-dc-motor-driver-shield-for-arduino-2-channels

## Datasheet
https://docs.google.com/document/d/1EiQAE_9VpDDm4rjZrySAoGjQldJnTk6rJIsUkqCT37w/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1EiQAE_9VpDDm4rjZrySAoGjQldJnTk6rJIsUkqCT37w/view
