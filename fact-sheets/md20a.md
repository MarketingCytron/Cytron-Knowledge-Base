# Product fact sheets

## Product name
MD20A 20Amp 6V-30V DC Motor Driver

## Aliases
MD20A, Cytron MD20A, 20Amp 6V-30V DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 6 V to 30 V and controlled with a PWM and a DIR signal. It is rated 20 A continuous and 60 A peak, with overcurrent current limiting, temperature-dependent current limit and undervoltage shutdown.

## Specs and functions
- Product code: MD20A; datasheet Rev 1.0, Feb 2019
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage: 6 V min, 30 V max
- Maximum motor current: 20 A continuous
- Peak motor current: 60 A, limited by the overcurrent protection circuit; actual current limit depends on board temperature; value shown is at room temperature (25 - 30 degree Celsius)
- Peak current duration: [NOT STATED]
- Logic input voltage (PWM & DIR) low level: 0 V min, 0.8 V max
- Logic input voltage (PWM & DIR) high level: 1.5 V min, 15 V max
- Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (product page)
- PWM frequency, standard: DC to 20 KHz; output frequency is same as input frequency
- PWM frequency, extended: 20 to 40 KHz; continuous motor current will be reduced in the extended range
- Product page states PWM frequency up to 20kHz
- Control: PWM & DIR inputs; compatible with sign-magnitude and locked-antiphase PWM operation (product page)
- Truth table: PWM Low = MA Low, MB Low (Brake), DIR don't care; PWM High + DIR Low = MA High, MB Low (Forward); PWM High + DIR High = MA Low, MB High (Backward)
- Overcurrent protection with active current limiting: PWM is chopped and motor current is held at the maximum current limit; OC LED on
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shut down when power input drops below the lower limit; ERR LED on
- Test buttons MA (Forward) and MB (Backward); motor runs at full speed
- LEDs: Power, Motor Status (MA, MB), Error (undervoltage shutdown or hardware fault), OC (Overcurrent)
- Packing list: 1 x 20Amp 6V-30V DC Motor Driver; 4 x PCB Spacer
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Power Input Terminal: VB+ (positive), VB- (negative); connect to battery
- Motor Output Terminal: MA, MB
- PWM/DIR Input: DIR (direction input), PWM (PWM input for motor speed control), GND (signal ground)
- Compatible with Arduino, Raspberry Pi, PLC, etc (product page)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, 3, 4)`
- RC, analog and serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Bidirectional control for one brushed DC motor
- Control the motor with PWM & DIR signal from Arduino, Raspberry Pi or PLC
- Test the functionality of the motor driver with the onboard test buttons

## Known limitations
- Power input does not have reverse-voltage protection; connecting in reverse polarity will damage the motor driver instantaneously
- Peak current is limited by the overcurrent protection circuit and the limit falls as board temperature rises
- Continuous motor current is reduced when PWM operates in the extended 20 to 40 KHz range
- Undervoltage threshold: [NOT STATED]
- Logic inputs 15 V max
- One brushed DC motor only
- PWM Low brakes the motor regardless of DIR
- Motor direction depends on motor connection; swapping MA and MB reverses it
- Battery vs switching power supply guidance: [NOT STATED] beyond "Connect to battery."

## Positioning (kept apart from specs)
- "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." (product page)
- Overcurrent protection "prevents the motor driver from damage when the motor stalls or an oversized motor is hooked up" (datasheet)

## Price band
RM97.44 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-20amp-6v-30v-dc-motor-driver

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-254/pdf/md20a_datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-254/pdf/md20a_datasheet.pdf
