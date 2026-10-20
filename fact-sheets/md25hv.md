# Product fact sheets

## Product name
MD25HV 25Amp 7V-58V High Voltage DC Motor Driver

## Aliases
MD25HV, Cytron MD25HV, 25Amp 7V-58V High Voltage DC Motor Driver, MD25HV High Voltage 7V-58V 25Amp DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 7–58 V and rated 25 A continuous and 60 A peak. It is controlled either by PWM/DIR signals or by a potentiometer and direction switch.

## Specs and functions
- Product code: MD25HV; datasheet Rev 1.0, Jan 2019
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage: 7 V min, 58 V max
- Maximum motor current: 25 A continuous, 60 A peak; peak duration [NOT STATED]
- 5V output voltage: 4.9 V min, 5.1 V max; 5V output maximum current: 250 mA
- Potentiometer analog input voltage (POT 2): 0 V to 5 V
- Direction switch input voltage (MA, MB): low level 0 V to 0.8 V; high level 3 V to 5 V
- Logic input voltage (PWM, DIR): low level 0 V to 0.8 V; high level 3 V to 30 V
- Logic compatibility (product page): 1.8V, 3.3V, 5V, 12V and 24V logic (Arduino, Raspberry Pi, PLC, etc); datasheet: logic input high level min 3 V
- PWM input frequency: DC to 40 kHz
- Motor driver output PWM frequency: 16 kHz, independent of input frequency
- Lock-Antiphase PWM is not supported
- Input Mode 1: PWM/DIR input; Input Mode 2: Potentiometer/Switch input; mode selection method [NOT STATED]
- Truth table (PWM/DIR): PWM Low = MA Low, MB Low (Brake, DIR don't care); PWM High + DIR Low = MA High, MB Low (Forward); PWM High + DIR High = MA Low, MB High (Backward); actual direction depends on motor connection
- Overcurrent protection with active current limiting: PWM to the motor is chopped and motor current is held at the maximum current limit; OC LED turns on
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shuts down when power input voltage drops below the lower limit
- Error LED blink codes: 2 = MOSFET Driver Error (undervoltage error or hardware failure); 3 = Overvoltage Error (power input voltage has exceeded the maximum rating); 4 = Overheat Error (board temperature over 80℃ (176℉), warning only, driver can still be safely operated)
- Test buttons MA (forward) and MB (backward): motor will run at 78% of full speed
- LEDs: Power LED, Error LED, OC (Overcurrent) LED, Motor Status LEDs MA (forward) / MB (backward)
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Packing list (product page): 1 x MD25HV, 1 x Potentiometer with connector, 1 x Rocker switch with connector, 4 x Nylon PCB Standoffs/Spacers
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Power input terminal: VB+ (positive), VB- (negative); connect to battery
- Motor output terminal: MA / MB
- PWM/DIR input: PWM (speed), DIR (direction), 5VO (5V output, can be used to power Arduino and other MCU), GND (signal ground)
- Speed control potentiometer (10KΩ): POT 1 (GND, lowest speed), POT 2 (Analog In, middle pin), POT 3 (5V, highest speed)
- Direction switch (SPDT): MA (short to GND to run forward), COM (connected to GND internally), MB (short to GND to run backward); MA and MB internally pulled high
- Compatible with Arduino, Raspberry Pi, PLC, etc (product page)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD(PWM_DIR, pwmPin, dirPin)`
- RC / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Bidirectional control for one brushed DC motor
- Control the motor with PWM/DIR signal from Arduino and other MCU
- Control the motor speed with a 10KΩ potentiometer and direction with an SPDT switch

## Known limitations
- No reverse polarity protection: connecting in reverse polarity will damage the motor driver instantaneously
- Lock-Antiphase PWM is not supported
- Output PWM is 16 kHz regardless of input PWM frequency
- Logic input high level min 3 V (datasheet), although the product page lists 1.8V logic
- Direction switch inputs (MA, MB) max 5 V
- 5V output max 250 mA
- With a switching power supply, connect a motor shunt regulator or rechargeable battery with the same voltage in parallel to absorb regenerative energy from the motor during deceleration (otherwise Overvoltage Error)
- Current limiting threshold drops as board temperature rises
- Test buttons run the motor at 78% of full speed only
- PWM Low brakes the motor regardless of DIR
- Brushed DC motors only
- Heatsink / fan requirement: [NOT STATED]

## Positioning (kept apart from specs)
- Product page features: "Buttons for quick testing." "LEDs for motor output state." "Dual Input Mode: PWM/DIR or Potentiometer/Switch Input."

## Price band
RM273.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-25amp-7v-58v-high-voltage-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1xJHVG2dc3aEtedCHf3L9NzUy5KqpxeWjeS9Lfh9XuqA/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1xJHVG2dc3aEtedCHf3L9NzUy5KqpxeWjeS9Lfh9XuqA/edit
