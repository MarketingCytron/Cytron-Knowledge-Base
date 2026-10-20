# Product fact sheets

## Product name
MD10C 10Amp 5V-30V DC Motor Driver (Rev 3.0)

## Aliases
MD10C, MD10C R3.0, MD10C Rev3.0, Cytron MD10C, 10Amp 5V-30V DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from one 5–30 V supply and controlled with PWM and DIR signals from a microcontroller. It is rated 13 A continuous and 30 A peak for up to 10 seconds.

## Specs and functions
- Product code: MD10C; current revision Rev 3.0 (packing list "1 x MD10C Rev3.0")
- Channels: 1 (bi-directional, one DC brushed motor, two terminals)
- Power input voltage (Vmotor): 5 V to 30 V (Rev 3.0)
- Single power source: "powered from a single power source, the Vmotor only. No additional Vin is required."
- Maximum continuous motor current: 13 A, tested under 25℃ room temperature without airflow and heatsink
- Peak motor current: 30 A, must not exceed 10 seconds
- Logic input high level: 3 V min, 30 V max (user's manual, live Google Doc); 3 V min, 5.5 V max (PDF copy of the same manual version); product page: "3.3 and 5V"
- Logic input low level: 0 V min, 0 V typical, 0.5 V max
- Maximum PWM frequency: 20 kHz; output frequency is the same as input frequency
- Control modes: Sign-Magnitude PWM (PWM pin = speed, DIR pin = direction) and Locked-Antiphase PWM (PWM pin tied to logic high, PWM signal on DIR; 50% duty = stop); selected by wiring
- Truth table: PWM Low = Brake Low (both outputs low, DIR don't care); PWM High + DIR Low = Forward (A high, B low); PWM High + DIR High = reverse (A low, B high)
- Full NMOS H-Bridge; manual states no heat sink is required
- Solid-state components (replaces the relay-based MD10B, launched 2008)
- Regenerative Braking (product page)
- Test Button A and Test Button B to run the motor without a controller
- Red LED A / Red LED B show current direction; green power LED
- Dimensions: 75 mm x 43 mm
- Certifications (Cytron product page Q&A reply): CE, FCC and RoHS
- PCB: standard FR4 (Cytron product page Q&A reply)
- Packing list: 1 x MD10C R3.0; 1 x 2510 PCB connector 3-way female; 3 x 2510 terminal pin; 4 x plastic spacer (~7 mm)
- Warranty: 12 months, manufacturing defects only
- Operating temperature: [NOT STATED]
- Packing: MD10C Rev3.0, 2510 3-way connector + 3 pins, 4 plastic spacers (product page)

## Interfaces and compatibility
- Green terminal block: pin 1 V motor Power + (5V to 30VDC), pin 2 V motor Power - (ground)
- Black terminal block: pin 3 Motor Output A, pin 4 Motor Output B
- Control header (2510, 3 pins): pin 1 GND, pin 2 PWM (up to 20 kHz), pin 3 DIR
- Compatible with Arduino and Raspberry Pi (3.3V logic PWM)
- Not an Arduino shield; connect with wires
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, 3, 4);`, `setSpeed(-255 to 255)`
- PIC: SK40C + PIC16F877A sample code (github.com/CytronTechnologies/SK40C-MD10C)
- Not isolated: controller and motor share a common GND
- RC servo signal: not supported
- Analog input / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive high current brushed DC motor up to 13A continuously
- Use MD10C even without any controller (test buttons)
- Control a DC motor from Arduino (sign-magnitude and locked-antiphase)
- Control a DC motor from SK40C with PIC16F877A
- Driving two DC geared motors with MD10C by using SKPS + SK40C
- Measuring DC motor RPM through built-in Hall sensor encoder
- Cytron tutorial: [Controlling MD10C DC Motor Driver Using Arduino Nano](https://my.cytron.io/tutorial/controlling-10a-dc-motor-driver-using-arduino-nano)
- Cytron tutorial: [MD10C Fast Testing](https://my.cytron.io/tutorial/md10c-fast-testing)
- Cytron tutorial: [Getting Started with Cytron Motor Driver](https://my.cytron.io/tutorial/getting-started-with-cytron-motor-driver)

## Known limitations
- No reverse polarity protection: check polarity before power-up
- Peak 30 A only for 10 seconds or less; 13 A continuous tested only at 25℃ without airflow or heatsink
- Not for RC PWM (TTL PWM from a microcontroller only)
- Brushed DC motors only
- Not isolated; controller and motor share a common GND
- PWM pin Low brakes the motor (Brake Low) regardless of DIR
- Motor direction depends on wiring
- Logic-input maximum differs between copies of the user's manual (30 V vs 5.5 V); product page states 3.3 and 5V
- Product name says "10Amp" but the continuous rating is 13 A
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Battery vs switching power supply guidance: [NOT STATED]

## Positioning (kept apart from specs)
- "another version of the MD10B … It offers several enhancements over the MD10B such as support for both locked-antiphase and sign-magnitude PWM signal as well as using full solid state components which result in faster response time and eliminate the wear and tear of the mechanical relay"
- Product page points to MD13S as an SMD version with similar specs at a lower price

## Price band
RM64.26 on my.cytron.io (read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-5v-30v-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1rgQzn-nWn-qcWNnHjDZvIYqUrdCeBQQxXA-TU3BF0AQ/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1rgQzn-nWn-qcWNnHjDZvIYqUrdCeBQQxXA-TU3BF0AQ/view
