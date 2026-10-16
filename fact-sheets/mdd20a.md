# Product fact sheets

## Product name
MDD20A 20Amp 6V-30V DC Motor Driver (2 Channels)

## Aliases
MDD20A, Cytron MDD20A, 20Amp 6V-30V DC Motor Driver (2 Channels), 20A 6V-30V Dual DC Motor Driver, Dual Channel 20A DC Motor Driver

## What it is
A dual-channel, bi-directional driver for two brushed DC motors, powered from 6–30 V and controlled with a PWM and a DIR signal per channel. Each channel is rated 20 A continuous and 60 A peak.

## Specs and functions
- Product code: MDD20A; datasheet Rev 1.0, July 2020
- Channels: 2 (bi-directional, brushed DC motors)
- Power input voltage: 6 V min, 30 V max
- Maximum motor current per channel: 20 A continuous, 60 A peak
- Peak current is limited by the overcurrent protection circuit; actual current limit depends on board temperature; value shown is at room temperature (25 - 30 degree Celsius); peak duration [NOT STATED]
- Logic input voltage (PWM & DIR): low level 0 V to 0.8 V; high level 1.5 V to 15 V; maximum input voltage can be extended up to 30V by connecting a 10K ohm resistor in series
- Logic compatibility (product page): 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)
- PWM frequency: standard up to 20 kHz; extended 20 kHz to 40 kHz, where continuous motor current will be reduced; output frequency is same as input frequency
- Control: PWM & DIR per channel (PWMx = speed, DIRx = direction)
- Truth table (each channel): PWMx Low = MxA Low, MxB Low (Brake, DIRx don't care); PWMx High + DIRx Low = MxA High, MxB Low (Forward); PWMx High + DIRx High = MxA Low, MxB High (Backward); actual direction depends on motor connection
- Locked-antiphase PWM: "Compatible with sign-magnitude and locked-antiphase PWM operation" (product page; not mentioned in the datasheet)
- Overcurrent protection with active current limiting: PWM to the motor is chopped and motor current is held at the maximum current limit; OC LED turns on
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shuts down when power input voltage drops below the lower limit; Error LED turns on
- Test buttons: motor will run at full speed
- LEDs: Power LED, Motor Status LEDs (MxA forward, MxB backward), Error LED (undervoltage shutdown or hardware fault), OC (Overcurrent) LED
- Weight: 89g (product page)
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Packing list (product page): 1 x 20Amp 6V-30V DC Motor Driver (2 Channels), 4 x PCB Spacer
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Power input terminal: VB+ (positive), VB- (negative); connect to battery
- Motor output terminals: MxA / MxB per channel
- PWM/DIR input per channel: DIRx (direction input), PWMx (PWM input for motor speed control), GND (signal ground)
- No 5V output or separate logic supply listed
- Compatible with Arduino, Raspberry Pi, PLC, etc (product page)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR_DUAL example, one `CytronMD(PWM_DIR, pwmPin, dirPin)` object per channel
- RC / analog / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Bidirectional control for two brushed DC motors
- Automated Guided Vehicle (AGV)
- Solar Tracker
- Game Simulator
- Mobile Robot
- Automation Machine

## Known limitations
- No reverse polarity protection: connecting in reverse polarity will damage the motor driver instantaneously
- Logic input high level max 15 V; up to 30 V only with a 10K ohm resistor in series
- Continuous motor current is reduced when PWM operates in the extended 20–40 kHz range
- Peak current is limited by the overcurrent protection circuit and the limit drops as board temperature rises
- PWM Low brakes the channel regardless of DIR
- Motor direction depends on motor wiring
- Brushed DC motors only
- Switching power supply / regenerative current guidance: [NOT STATED]
- Heatsink / fan requirement: [NOT STATED]

## Positioning (kept apart from specs)
- Product page features: "Buttons for quick testing." "LEDs for motors output state."

## Price band
- www.cytron.io volume prices: 5 or more $33.25; 20 or more $31.50; 50 or more $29.75 (read 16 Oct 2026); single-unit price [NOT STATED]

## Product page
https://www.cytron.io/p-20amp-6v-30v-dc-motor-driver-2-channels

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-287/pdf/cytron-20a-6v-30v-dual-dc-motor-driver-datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-287/pdf/cytron-20a-6v-30v-dual-dc-motor-driver-datasheet.pdf
