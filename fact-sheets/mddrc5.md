# Product fact sheets

## Product name
MDDRC5 5 Amp 7V-30V DC Motor Driver for R/C (2 Channels)

## Aliases
MDDRC5, 5 Amp 7V-30V DC Motor Driver for R/C (2 Channels), 5 Amp 7V-30V DC Motor Driver for R/C, 5 Amp Dual Channel RC Motor Driver

## What it is
A dual-channel DC motor driver controlled directly from an R/C receiver, driving two DC motors from a 7–30 V supply. Its RC1/RC2 inputs work in Independent Mode or Mixed Mode, selected with an onboard switch.

## Specs and functions
- Product code: MDDRC5
- Datasheet: Rev 1.0, March 2026 (spec table titled "MDDRC5 Absolute Maximum Ratings")
- Power input voltage: 7–30 V (V+ positive, V- negative; datasheet: "Connect to the battery")
- Maximum motor current (per channel): 5 A continuous
- Peak motor current (per channel): 20 A, "supported for less than 1 seconds and is limited by the overcurrent protection circuit" (datasheet); product page: 20 A peak "less than 5 seconds" — datasheet value applies
- Motor channels: 2
- Motor output PWM frequency: 20 kHz
- Control input: R/C signal on RC1 and RC2
- RC input voltage (RC1 & RC2): low level 0–0.7 V, high level 1.5–15 V
- RC signal timing: frequency 10–100 Hz, deadband ±35 µs, fullscale ±435 µs
- 5V output for the RC receiver: 500 mA max; do not use it to power a servo motor
- Mixed Mode: RC1 = forward/backward speed, RC2 = turn left/right (mixed to both motors)
- Independent Mode: RC1 = left motor speed and direction, RC2 = right motor speed and direction
- Mode selection switch (IND/MIX) selects Independent or Mixed Mode
- Motor alignment potentiometers (FWD, REV) compensate for left/right motor differences so the robot drives straight
- Test button: motors run at half speed; single press and hold = both motors forward, double press and hold = both motors backward
- Onboard microcontroller: RP2040
- USB-C port: firmware updates (datasheet); product page also states it can upload custom code
- Boot and Reset buttons: hold BOOT, press and release RESET, release BOOT; board appears as RPI-RP2 USB mass storage device
- Firmware: .uf2 files on GitHub (mddrc5_v1.0.4.uf2, mddrc5_v1.0.5.uf2, mddrc5_v1.0.6.uf2 present); copy the .uf2 file to the RPI-RP2 drive
- Product page: update to the latest firmware before use
- LEDs: Power LED; Motor status LEDs (MxA = Forward, MxB = Backward, direction depends on wiring); Error LEDs (ERR1 left motor, ERR2 right motor); OC (Overcurrent) LEDs on while current limiting is active
- Error LED codes: 2 blinks = RC Input Error (no RC signal or pulse width out of range); 3 blinks = Undervoltage / MOSFET Driver Error; 4 blinks = Overvoltage Error
- Overcurrent protection with active current limiting: PWM chopped, current held at the maximum limit; current limit threshold 20 A
- Undervoltage shutdown: motor output shuts down when input drops below the lower limit
- Reverse polarity protection on the power input
- Overvoltage: detected and reported as an error (4 blinks)
- Thermal shutdown: listed on the product page; not stated in the datasheet
- Footprint: 69 × 35.5 mm (product page)
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- Terminal type and wire size: [NOT STATED]
- Undervoltage / overvoltage thresholds: [NOT STATED]
- Failsafe motor behaviour on RC signal loss: [NOT STATED]
- Calibration procedure for the transmitter: [NOT STATED]
- Packing list: [NOT STATED]
- Packing: driver, 2 × 10 cm 3-way extension wires, 4 × 7 mm nylon spacers, 2 mm screwdriver (product page)
- Battery: 2S to 6S LiPo within 7–30 V (product page)
- Update to the latest firmware before use — Cytron firmware update guide (product page)

## Interfaces and compatibility
- Power input terminal: V+, V-
- Motor output terminals: MxA, MxB per motor; swapping MxA and MxB reverses rotation
- RC input header: RC1, RC2 (signal), +5V (receiver supply, 500 mA max), GND
- USB-C (firmware update); USB-C powers the control circuit only, not the motors
- RP2040 pin mapping: RC1 = GP1, RC2 = GP0, TEST = GP3, IND/MIX = GP24, ERR1 = GP7, ERR2 = GP9, battery voltage sensor = GP29, FWD pot = GP26, REV pot = GP27
- Left motor: PWM GP11, Direction GP10, Sleep GP12, Fault GP13; Right motor: PWM GP20, Direction GP21, Sleep GP18, Fault GP17
- Works with an R/C receiver; no Arduino coding needed for normal R/C use (product page)
- 3D files on GitHub: Robot Sumo 500g R/C body and motor bracket; Robot Battle Karnival STEM files
- Tutorials: Getting Started with MDDRC5; Build a Robot Sumo 500g R/C with MDDRC5
- Arduino / MicroPython libraries or code examples: [NOT STATED]

## Use cases
- Differential drive motors in mobile robots (Mixed Mode preferred)
- Non-wheeled motors, or controlling the motors independently (Independent Mode)
- 500g R/C sumo robots
- Compact competition robots
- Compact mobile platforms
- Space-limited robotics projects
- Cytron tutorial: [Getting Started with MDDRC5](https://my.cytron.io/tutorial/getting-started-with-mddrc5)
- Cytron tutorial: [From Test Bench to Champion: MDDRC5 at ROVATION](https://my.cytron.io/tutorial/mddrc5-500g-rc-sumo-rovation-2026)
- Cytron tutorial: [Build a Robot Sumo 500g R/C with MDDRC5](https://my.cytron.io/tutorial/build-robot-sumo-500g-rc-mddrc5)

## Known limitations
- Power input absolute maximum 30 V (minimum 7 V)
- Motor current 5 A continuous per channel; 20 A peak only for less than 1 second, limited by the overcurrent protection circuit
- 5V output limited to 500 mA; do not use it to power a servo motor
- RC signal must be 10–100 Hz; missing signal or out-of-range pulse width gives an RC Input Error
- Motor output shuts down on undervoltage
- Overvoltage gives an error; with a switching power supply, connect a motor shunt regulator or a rechargeable battery with the same voltage in parallel to absorb regenerative energy from the motor during deceleration
- Motor direction depends on terminal wiring; the Forward/Backward LED labels follow the terminals
- Test button runs motors at half speed only
- USB-C does not power the motors
- Thermal shutdown is not described in the datasheet (product page only)
- No R/C failsafe behaviour or calibration procedure stated
- GitHub READMEs disagree on the latest firmware version (root README: v1.0.5; firmware README: v1.0.6); no release notes published

## Positioning (kept apart from specs)
- Product page framing: "5 Amp Dual Channel RC Motor Driver (MDDRC5)"
- Positioned as a smaller alternative inspired by MDDRC10 for direct R/C motor control in compact robots
- Compact footprint for space-limited competition robots

## Price band
RM126.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-5-amp-7v-30v-dc-motor-driver-for-r-c-2-channels

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

