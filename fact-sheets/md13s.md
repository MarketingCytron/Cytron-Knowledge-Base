# Product fact sheets

## Product name
MD13S 13Amp 6V-30V DC Motor Driver

## Aliases
MD13S, Cytron MD13S, 13Amp 6V-30V DC Motor Driver, 13Amp DC Motor Driver, MD13S 13Amp DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 6 V to 30 V and controlled with a PWM and a DIR signal from a microcontroller. It is rated 13 A continuous and 30 A peak for up to 10 seconds.

## Specs and functions
- Product code: MD13S; user's manual V1.1, June 2018
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage: 6 V to 30 V
- Maximum continuous motor current: 13 A (without heatsink at 25℃)
- Peak motor current: 30 A, must not exceed 10 seconds
- Current limiting at 30A; OC LED lights when output current is over the 30A limit
- Logic input high level: 3 V min, 5.5 V max
- Logic input low level: 0 V min, 0 V typical, 0.5 V max
- 3.3V and 5V logic level input
- Maximum PWM frequency: 20 KHz; actual output frequency is same as input frequency
- Control modes: sign-magnitude PWM (PWM = speed, DIR = direction) and locked-antiphase PWM (PWM pin held high, PWM signal on DIR; 50% duty cycle = motor stops); selected by wiring
- Truth table: PWM Low = both outputs low (DIR don't care); PWM High + DIR Low = A high, B low; PWM High + DIR High = A low, B high
- Fully NMOS H-Bridge; manual states no heat sink is required
- Regenerative Braking (product page)
- 2 test switches (MA, MB)
- LEDs: MA, MB (current direction), Power, OC (Over Current), ERR (fault detected in on-board MOSFET driver)
- GROVE compatible connector
- SMD compatible
- RoHS, FCC and CE compliance (product page)
- Dimensions: 61 mm x 33 mm
- Packing list (user's manual): 1 x MD13S 13A DC Motor Driver; 2 x Terminal socket, Black for power and Green for Motor; Grove connector with cable
- Packing list (product page): 1 x MD13S motor driver board; 1 x Green + Black 2-way terminal blocks (Normally Black is for Motor, Green is for Power); 1 x Grove connector (Grove to Grove)
- Warranty: 12 months, manufacturing defects only
- Thermal protection: [NOT STATED]
- Under-voltage protection: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Terminal block: POWER + (6V to 30V), POWER -, Motor Output A, Motor Output B
- Input pins: GND (logic ground), PWM (speed control, not for RC PWM), DIR (direction control)
- Grove-compatible input connector; Grove pinout [NOT STATED]
- Works with TTL PWM from a microcontroller at 3.3 V or 5 V logic
- Not an Arduino shield; can be used with wire connection
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, 3, 4)`
- RC servo signal: not supported
- Analog input / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive a high current brushed DC motor up to 13A continuously
- Bi-directional control for one brushed DC motor with PWM and DIR signals from a microcontroller
- Test the motor manually with the onboard MA and MB test switches

## Known limitations
- No polarity protection (product page): check polarity before power-up
- Logic inputs 5.5 V max (not for 12 V or 24 V logic)
- Not for RC receiver PWM (TTL PWM from a microcontroller only)
- Peak 30 A only for 10 seconds or less; 13 A continuous stated without heatsink at 25℃
- Current limiting at 30A; behaviour beyond the limit [NOT STATED]
- One brushed DC motor only
- PWM Low sets both outputs low regardless of DIR
- Motor direction depends on wiring
- Battery vs switching power supply guidance: [NOT STATED] in the user's manual
- Terminal socket colours differ between user's manual (Black for power, Green for Motor) and product page (Normally Black is for Motor, Green is for Power)
- Back in stock on my.cytron.io (availability 73, 19 Oct 2026); three options: pre-soldered terminal blocks, loose terminal blocks, or pin headers for SUMO:BIT

## Positioning (kept apart from specs)
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay"
- "Fully NMOS H-Bridge for better efficiency and no heat sink is required"

## Price band
RM64.26 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-13amp-6v-30v-dc-motor-driver

## Datasheet
https://www.electrokit.com/upload/product/41018/41018267/MD13S%20User's%20Manual.pdf

## Source type
Datasheet

## Source link
https://www.electrokit.com/upload/product/41018/41018267/MD13S%20User's%20Manual.pdf
