# Product fact sheets

## Product name
1.2Amp 7V-30V DC Motor Driver Shield for Arduino (2 Channels)

## Aliases
SHIELD-3AMOTOR, Cytron 3A Motor Driver Shield, 3A Motor Driver Shield, 1.2Amp 7V-30V DC Motor Driver Shield for Arduino, 1.2Amp 7V-30V DC Motor Driver Shield

## What it is
An Arduino shield that drives two brushed DC motors in both directions using the DRV8871 IC. A DIP switch selects sign-magnitude or locked-antiphase control.

## Specs and functions
- Channels: 2, brushed DC motors
- Motor supply voltage: 7 V to 30 V; above 12 V the PWRIN-Vin connection pad must be cut and the Arduino powered separately
- Continuous current: 1.2 A per channel (depends on room temperature)
- Peak current: 3 A per channel, must not exceed 1 second
- The "3A" in the product code and manual title is the peak rating; the product page title's "1.2Amp" is the continuous rating
- Logic input high: 1.5 V min, 5 V max; logic input low: 0 V to 0.5 V
- Supports 3.3V and 5V logic level input
- Maximum PWM frequency: [NOT STATED]
- Driver IC: DRV8871
- Control modes: Sign Magnitude and Locked Anti-Phase, selected by DIP switch (switches 5, 6, 7, 8 ON = Sign Magnitude; switches 1, 2, 3, 4 ON = Locked Anti-Phase)
- Current limit protection
- No polarity protection for V motor
- Thermal and under-voltage protection: [NOT STATED]
- Test buttons for both channels; Motor 1 and Motor 2 direction LEDs; power LED
- Reset button
- Stackable Arduino header pins
- LSS05 Auto-Calibrating Line Sensor connector
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Warranty: 12 months, manufacturing defect only; cutting any trace voids the warranty
- In the box: 1 x Cytron 3A Motor Driver (Code: SHIELD-3AMOTOR)

## Interfaces and compatibility
- Sign Magnitude: DIR1 = D4, EN1 = D5, EN2 = D6, DIR2 = D7
- Locked Anti-Phase: DIR1 = D5, EN1 = D4, EN2 = D7, DIR2 = D6
- Control pins can be changed only by cutting traces on the back and soldering jumpers (voids warranty)
- LSS05 pins: O1 = D13, O2 = D12, O3 = D11, O4 = D10, O5 = D9, Calibrate = D8
- Screw terminal blocks for Motor 1, Motor 2 and power supply
- PWRIN (shield power terminal) and Arduino Vin are joined by a connection pad by default
- Compatible with Arduino Uno, Leonardo, Mega, Due, Zero, 101 and possibly other pin compatible boards such as CIKU, CT UNO and CT ARM
- Arduino: Cytron Motor Drivers Library (PWM_DIR_DUAL example); in Sign Magnitude mode use PWM pin 5 / DIR pin 4 for motor 1 and PWM pin 6 / DIR pin 7 for motor 2

## Use cases
- Controlling dual DC motors from an Arduino
- Line following robot with the LSS05 line sensor connected directly to the shield

## Known limitations
- Continuous current is 1.2 A per channel; 3 A is peak only, for no more than 1 second
- No polarity protection on the motor supply; double check the connection before connecting power
- Supplying more than 12 V requires cutting the PWRIN-Vin trace, which voids the warranty
- Set only Sign Magnitude or Locked Anti-Phase on the DIP switch at a time; mixing the setting causes unexpected results
- The manual specifies a battery power source; SMPS use is not covered
- Uses Arduino pins D4 to D7 (and D8 to D13 when the LSS05 connector is used)

## Positioning (kept apart from specs)
- The manual describes it as "an improvement from our previous Cytron 2A Motor Driver Shield" that "can handle higher current up to 3A together with limit current protection"

## Price band
RM41.79 on offer (was RM92.40) (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-1.2amp-7v-30v-dc-motor-driver-shield-for-arduino-2-channels

## Datasheet
https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view
