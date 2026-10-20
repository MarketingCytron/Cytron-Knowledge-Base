# Product fact sheets

## Product name
MDDRC10 10Amp 7V-30V DC Motor Driver for R/C (2 Channels)

## Aliases
MDDRC10, 10Amp 7V-30V DC Motor Driver for R/C (2 Channels), 10Amp 7V-30V DC Motor Driver for R/C

## What it is
A dual-channel brushed DC motor driver controlled directly from an R/C receiver, driving two DC motors from a 7–30 V supply. Its RC1/RC2 inputs work in Independent Mode or Mixed Mode, selected with an onboard switch.

## Specs and functions
- Product code: MDDRC10
- Datasheet: Rev 1.0, August 2020 (spec table titled "MDDRC10 Absolute Maximum Ratings")
- Power input voltage: 7–30 V (VB+ positive, VB- negative; datasheet: "Connect to battery.")
- Maximum motor current (per channel): 10 A continuous
- Peak motor current (per channel): 30 A, limited by the overcurrent protection circuit; actual current limit depends on board temperature; value shown is at room temperature (25–30 °C); peak duration [NOT STATED]
- Motor channels: 2 (bidirectional control for two brushed DC motors)
- Motor output PWM frequency: 20 KHz
- Control input: R/C signal on RC1 and RC2
- RC input voltage (RC1 & RC2): low level 0–0.7 V, high level 1.5–15 V
- RC signal timing: frequency 10–100 Hz, deadband ±35 µs, fullscale ±435 µs
- 5V output for the RC receiver: 500 mA max, from an onboard switching regulator; do not use it to power a servo motor
- RC input auto-calibration: neutral points and offsets calibrated automatically at every power-up (captures the first valid RC signal as neutral)
- Mixed Mode: RC1 = forward/backward speed, RC2 = turn left/right
- Independent Mode: RC1 = left motor speed and direction, RC2 = right motor speed and direction
- Mode selection switch selects Independent or Mixed Mode
- Test buttons: motor runs at full speed
- LEDs: Power LED; Motor status LEDs (MxA = Forward, MxB = Backward, actual direction depends on motor connection); Error LED; OC (Overcurrent) LED on while current limiting is active
- Error LED codes: 2 blinks = RC Input Error (no RC signal or pulse width out of range); 3 blinks = Undervoltage / MOSFET Driver Error; 4 blinks = Overvoltage Error
- Overcurrent protection with active current limiting: PWM chopped, current held at the maximum limit
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shuts down when input drops below the lower limit
- Reverse polarity protection: none (reverse polarity damages the driver instantaneously)
- 10 A per channel continuously without any additional heatsink (product page)
- Packing list (product page): 1 x 10Amp 7V-30V DC Motor Driver for R/C (2 Channels), 2 x 2561 3-way connector extension wire, 4 x PCB Spacer
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- Terminal type and wire size: [NOT STATED]
- Undervoltage / overvoltage thresholds: [NOT STATED]
- Failsafe motor behaviour on RC signal loss: [NOT STATED]
- Discrete NMOS H-bridge; 5 V BEC 500 mA; auto calibration at power-up (product page)
- In stock on my.cytron.io (availability 193, read 2026-10-19)

## Interfaces and compatibility
- Power input terminal: VB+, VB-
- Motor output terminals: MxA, MxB per motor; swapping MxA and MxB reverses rotation
- RC input header: RC1, RC2 (signal), +5V (receiver supply, 500 mA max), GND
- Works with an R/C receiver; no coding or programming needed
- Microcontroller, USB, firmware or software library: [NOT STATED]
- Differences from MDDRC5 (per each datasheet): MDDRC10 is 10 A continuous / 30 A peak per channel vs MDDRC5 5 A / 20 A; MDDRC10 has no reverse polarity protection (MDDRC5 has); MDDRC10 lists temperature protection and RC auto-calibration; MDDRC10 test buttons run at full speed (MDDRC5 half speed); MDDRC10 has no RP2040, USB-C or alignment potentiometers described

## Use cases
- Differential drive motors in mobile robots (Mixed Mode preferred)
- Non-wheeled motors, or controlling the motors independently (Independent Mode)
- RC vehicle or mobile robot without any microcontroller
- RC Lawn Mower
- Combat Robot
- Sumo Robot
- RC Toy
- Cytron tutorial: [Build 1KG RC Sumo Robot using MDDRC10](https://my.cytron.io/tutorial/rcsumo1kg-mddrc10)
- Cytron tutorial: [1KG RC Sumo Robot Starter Kit User Guide using MDDRC10](https://my.cytron.io/tutorial/1kg_sumo_robot_mddrc10)
- Cytron tutorial: [1KG RC Sumo Robot Using MDDRC10](https://my.cytron.io/tutorial/1kg-rc-sumo-robot-using-mddrc10)

## Known limitations
- Power input 7–30 V absolute maximum
- No reverse polarity protection; connecting the battery in reverse polarity damages the motor driver instantaneously
- Motor current 10 A continuous per channel; 30 A peak is current-limited and falls as the board temperature rises (30 A at 25–30 °C)
- 5V output limited to 500 mA; do not use it to power a servo motor
- RC transmitter must be on with sticks at neutral before switching on the driver, because neutral is captured at power-up
- RC signal must be 10–100 Hz; missing signal or out-of-range pulse width gives an RC Input Error
- Motor output shuts down on undervoltage
- Overvoltage gives an error; with a switching power supply, connect a motor shunt regulator or a rechargeable battery with the same voltage in parallel to absorb regenerative energy from the motor during deceleration
- Test buttons run the motor at full speed
- Motor direction depends on terminal wiring; the Forward/Backward LED labels follow the terminals
- No failsafe behaviour or peak current duration stated

## Positioning (kept apart from specs)
- Product page: "Building a RC vehicle or mobile robot without any microcontroller? MDDRC10 is what you need."
- "Plug & play, controlled from RC directly."

## Price band
RM180.18 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-for-rc-2-channels

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf
