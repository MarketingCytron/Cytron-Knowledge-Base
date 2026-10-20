# Product fact sheets

## Product name
MOTION:BIT

## Aliases
MOTION:BIT, MOTION-BIT, Motion:Bit, MOTIONBIT, MOTION:BIT for micro:bit, MOTION:BIT - Simplifying Motion Control with micro:bit

## What it is
A robotics and motion-control expansion board for the BBC micro:bit that drives brushed DC motors and 8 RC servos. It runs from an onboard 18650 Li-Ion battery holder (charged over micro USB) or an external 3.6–6 V input.

## Specs and functions
- Product code: MOTION-BIT (datasheet document title)
- Datasheet: Rev 1.0, February 2023 (spec table titled "Absolute Maximum Ratings")
- Power input voltage: 3.6 V min, 6 V max
- Power sources: 18650 Li-Ion battery holder; micro USB (charges the battery or powers the board, no data transmission); power input terminal for external 3.6V - 6V (external LiPo or 4x AA batteries)
- Analog input voltage: 0–3.3 V
- Total +3V3 output current (GPIO Breakout & Grove Ports): 200 mA max
- Total +5V output current: 300 mA max
- Maximum DC motor current: 1 A continuous; 1.5 A peak (< 5 seconds)
- DC motor channels: 4 (M1, M2, M3, M4) (MakeCode extension)
- Motor voltage at full speed is equal to power source voltage
- Servos: connectors for 8x RC servo motors; V+ voltage is equal to power source voltage
- Servo control in MakeCode: 0–180 degrees (500–2500 µs pulse, 50 Hz); disable servo sends no pulse
- Motor and servo outputs driven by a PCA9685 at I2C address 0x40 (MakeCode extension code)
- RGB LEDs: 2 user-programmable WS2812B RGB LEDs, connected to P8
- Ext. RGB LED connector for external WS2812B RGB LEDs, daisy-chained to the onboard RGB LEDs (Dout of RGB LED 1)
- GPIO status LEDs: on when the IO state is high
- Motor test buttons: motor runs at full speed
- Motor status LEDs: on when the motor is running
- Power/Charge LED: power on when powered; charge on while charging, off when full
- On/Off switch and Ext. On/Off switch header
- Motor driver IC: [NOT STATED]
- Buzzer: [NOT STATED]
- Dimensions: [NOT STATED] (drawing only)
- Protections (reverse polarity, over-current, thermal, battery): [NOT STATED]
- Operating temperature: [NOT STATED]
- Size: 95.2 × 57.2 mm; Ø4.8 mm holes, 72 × 48 mm pattern (product page image)
- Power: micro USB, 18650 or external Vin 3.6–6 V; USB charging and Li-ion protection circuits (Cytron comparison image)
- Motors: 1 A continuous, 1.5 A peak; total servo current 3 A; total 5 V output 300 mA (Cytron comparison image)
- Packing: board, screwdriver, 3 Grove-to-JST-SH cables, 4 bumpers; options add micro:bit V2 kit and/or a 3.7 V 2200 mAh 18650 (product page)

## Interfaces and compatibility
- micro:bit V1 and V2 (MakeCode extension README)
- micro:bit socket: plug in with the micro:bit LEDs facing out
- GPIO breakout, colour-coded GVS, 3.3V power per GPIO: P0, P1, P2, Button A, Button B, P9, P12, P13, P14, P15, P16
- Maker Ports: JST-SH 4-way, compatible with Qwiic, STEMMA QT and Grove (via conversion cable); datasheet: "These pins are available on Maker Ports: P0-P9, P1-P2, P2-P12"
- Maker Port (I2C): JST-SH 4-way, for I2C modules only
- I2C breakout: micro:bit I2C pins (P19 SCL, P20 SDA)
- P8: onboard RGB LEDs
- 5V Supply output for external sensors/modules
- Motor terminals: direction depends on polarity
- MakeCode extension: pxt-motionbit (block category "MOTION:BIT"), search "motionbit" or https://github.com/cytrontechnologies/pxt-motionbit
- MakeCode blocks: run motor (speed 0–255), brake motor, set servo position, disable servo, RGB pixel colour and brightness, external RGB pixels
- Python: [NOT STATED]

## Use cases
- Robots and motion-control projects with micro:bit ("simplifying robots & motion control projects making with micro:bit")
- Projects with mechanical movements using DC motors and servos
- Adding sensors and modules through the GPIO breakout and Maker Ports
- Cytron tutorial: [Build an Autonomous Obstacle-Avoiding Robot Car Using MOTION:BIT](https://my.cytron.io/tutorial/build-an-obstacle-avoiding-robot-car-using-motionbit)
- Cytron tutorial: [Getting Started with MOTION:BIT & Projects Guide](https://my.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide)
- Cytron tutorial: [CONTROL OMNI ROBOT CAR WITH MOTION:BIT USING BLUETOOTH APP](https://my.cytron.io/tutorial/control-omni-robot-car-with-motion:bit-using-bluetooth-app)
- Cytron tutorial: [Line Following with MOTION:BIT and Maker Line](https://my.cytron.io/tutorial/line_following_robot_car_using_motionbit)

## Known limitations
- Power input 3.6–6 V absolute maximum
- DC motor current 1 A continuous; 1.5 A peak only for < 5 seconds (per channel or total not stated)
- +5V output total 300 mA; +3V3 total 200 mA shared by GPIO breakout and Grove ports
- Analog input 0–3.3 V
- Servo V+ and motor full-speed voltage equal the power source voltage (no servo voltage selection)
- Micro USB is for power and charging only; no data transmission
- Maker Port (I2C) is for I2C modules only
- P8 is used by the RGB LEDs
- I2C address 0x40 is used by the motor/servo controller
- External On/Off switch works only when the onboard switch is Off
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring polarity

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Motion Control with micro:bit"
- "MOTION:BIT aims at simplifying robots & motion control projects making with micro:bit." (MakeCode extension README)
- "students can build projects with mechanical movements right away" (MakeCode extension README)

## Price band
RM125.00–RM241.80 across 4 options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-motionbit-board-and-kits

## Datasheet
https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit
