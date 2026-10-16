# Product fact sheets

## Product name
10 Amp 7V-30V Potentiometer & Switch Control DC Motor Driver (MD10-POT)

## Aliases
MD10-POT, MD10POT, Cytron MD10-POT, 10 Amp 7V-30V Potentiometer & Switch Control DC Motor Driver, Potentiometer and Switch Control 10Amp DC Motor Driver

## What it is
A single-channel brushed DC motor driver, 7–30 V input, 10 A continuous and 30 A peak for less than 10 seconds. Speed and direction are set with a 10KΩ potentiometer and an SPDT switch, or with PWM and DIR signals from a controller.

## Specs and functions
- Product code: MD10-POT
- Channels: 1
- Power input voltage: 7 V min, 30 V max
- Maximum motor current, continuous: 10 A
- Maximum motor current, peak: 30 A (less than 10 seconds)
- Logic input voltage, low level (PWM, DIR): 0 V min, 0.5 V max
- Logic input voltage, high level (PWM, DIR): 3 V min, 30 V max
- Internal PWM generator frequency: 9 KHz min, 11 KHz max (output frequency when potentiometer is used)
- External PWM input frequency: DC to 20 KHz (output frequency = input frequency)
- Speed control: 10KΩ potentiometer or PWM signal; direction control: SPDT switch or DIR pin
- Truth table: PWM Low = both outputs low (brake, DIR don't care); PWM High + DIR Low = MA high, MB low (forward); PWM High + DIR High = MA low, MB high (reverse)
- Test buttons to test the functionality of the motor / driver
- Power LED; Motor Status LEDs (turn on when the motor is running)
- 3D printable case STL file linked on the product page
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Protections (reverse polarity, over-current, thermal, under-voltage): [NOT STATED]
- Packing list: [NOT STATED]
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Power Input Terminal: connect to battery
- Motor Output Terminal: connect to motor (outputs MA and MB)
- Speed Control Potentiometer connector: 10KΩ potentiometer
- Direction Switch connector: SPDT switch
- PWM/DIR Input: PWM signal for speed, DIR pin for direction
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, pwmPin, dirPin)`
- Connector pin order: [NOT STATED]
- Locked-antiphase PWM: [NOT STATED]
- RC, analog voltage or serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Control a DC motor's speed with a 10KΩ potentiometer and its direction with an SPDT switch
- Control the motor with a PWM signal and a DIR pin
- Test the functionality of the motor / driver with the test buttons

## Known limitations
- Power input 7 V minimum, 30 V maximum
- Peak 30 A only for less than 10 seconds; 10 A continuous
- Logic low must be 0.5 V or below
- PWM Low brakes the motor regardless of DIR
- Single channel, brushed DC motor
- Forward/reverse depends on motor wiring
- Protections (reverse polarity, over-current, thermal, under-voltage): [NOT STATED]
- Switching power supply / regenerative current guidance: [NOT STATED]

## Positioning (kept apart from specs)
[NOT STATED]

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-10-amp-7v-30v-potentiometer-and-switch-control-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1U_dn6OCEw76pqJaIzZYuWqWoU1C9APwpNp8qztaJ1uA/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1U_dn6OCEw76pqJaIzZYuWqWoU1C9APwpNp8qztaJ1uA/view
