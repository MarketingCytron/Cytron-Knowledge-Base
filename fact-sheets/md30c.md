# Product fact sheets

## Product name
30Amp 5V-30V DC Motor Driver (MD30C)

## Aliases
MD30C, MD30C Rev2.0, Cytron MD30C, 30Amp 5V-30V DC Motor Driver, MD30C 30A DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 5–30 V and rated 30 A continuous and 80 A peak for up to 1 second. It takes PWM and DIR signals from a microcontroller or runs standalone from its onboard PWM generator with switches and a speed potentiometer.

## Specs and functions
- Product code: MD30C; hardware Revision 2.0 since January 2016
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage (motor supply): 5 V min, 30 V max
- Maximum continuous motor current: 30 A
- Peak motor current: 80 A, must not exceed 1 second
- Idle current: 100 mA max
- Logic input high level: 3 V min, 5.5 V max
- Logic input low level: 0 V min, 0.5 V max
- Logic level input: 3.3V and 5V
- Maximum PWM frequency: 20 KHz; actual output frequency is same as input frequency when external PWM is selected
- PWM source selected by jumpers: internal potentiometer = JP4 INT POT + JP6 INT PWM; external potentiometer = JP4 EXT POT + JP6 INT PWM; external PWM signal = JP4 don't care + JP6 EXT PWM
- Truth table: PWM Low = both outputs low (brake, DIR don't care); PWM High + DIR Low = A high, B low (CW); PWM High + DIR High = A low, B high (CCW)
- Fully NMOS H-Bridge; manual states no heatsink or fan is required
- Reverse polarity protection
- 2 test buttons (A and B); external switches can be connected
- Red LED A, Red LED B (current direction), Green Power LED
- Packing list: 1 x MD30C; 2 x Mini Jumper; 1 x 2510 PCB Connector 3 Ways (Female); 3 x 2510 Terminal Pin
- Warranty: 6 months, manufacturing defects only
- CE, FCC and RoHS certificates linked on the product page
- Internal PWM generator frequency: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Reverse polarity protection for Vin/Vmotor; brakes when PWM is low (product page)
- Size ~94 × ~79 mm; CE, FCC and RoHS certificates linked (product page)

## Interfaces and compatibility
- Input header (2510, 3 pins): pin 1 GND, pin 2 PWM (not RC PWM), pin 3 DIR
- Power terminal block and motor terminal block; for current above 20A, solder wires directly to the pads at the bottom layer
- JP4 and JP6: PWM source selector jumpers
- JP5: external 10K Ohm potentiometer port
- JP7 and JP8: external switches
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, pwmPin, dirPin)`
- Getting started with SK40C in the user's manual
- Works with 3.3V and 5V logic controllers
- RC (Radio Control) PWM: not supported
- Analog voltage input / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive medium to high power DC brushed motor with current capacity up to 80A peak and 30A continuously
- Operate without a host controller using the onboard switches and speed potentiometer
- Mount external switches and potentiometer at an easy to reach place
- Control the motor from a microcontroller (example with SK40C)

## Known limitations
- Battery recommended as the power source
- If a switching power supply is used, parallel it with a same-voltage battery to absorb the re-gen power from the motor
- Connecting the battery to the motor port will burn the MOSFETs and is not covered under warranty
- Set either DIR or PWM pin LOW first when power is on
- Logic inputs 5.5 V max (not for 12 V or 24 V logic)
- Peak 80 A only for 1 second or less
- Not for RC (Radio Control) PWM
- For current above 20A, solder wires to the bottom-layer pads instead of using the terminal block
- JP6 must be EXT PWM for microcontroller control; with JP4 on EXT POT the onboard potentiometer has no effect
- PWM Low brakes the motor regardless of DIR
- Brushed DC motor only, one channel
- Motor direction depends on wiring

## Positioning (kept apart from specs)
- "the successor of MD30B"
- "user friendly features such as reverse polarity protection and onboard PWM generator which allows it to operate without a host controller"
- "Fully NMOS design not only provides faster switching time, it is also more efficient and no heatsink or fan is required."

## Price band
RM161.70 (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-30amp-5v-30v-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/178uDa3dmoG0ZX859rWUOS2Xyafkd8hSsSET5-ZLXMYQ/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/178uDa3dmoG0ZX859rWUOS2Xyafkd8hSsSET5-ZLXMYQ/view
