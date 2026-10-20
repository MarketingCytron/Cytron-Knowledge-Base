# Product fact sheets

## Product name
MOTION:BIT Pro

## Aliases
MOTION:BIT Pro, MOTION-BIT-PRO, Motion:Bit Pro, MOTIONBIT PRO, MOTION:BIT Pro for micro:bit, MOTION:BIT Pro - 12V Robotics Expansion Board for micro:bit

## What it is
A higher-voltage robotics and motion-control expansion board for the BBC micro:bit, powered from an external 7–12 V input, that drives brushed DC motors and 8 RC servos. It is programmed with the same MOTION:BIT MakeCode extension as MOTION:BIT.

## Specs and functions
- Product code: MOTION-BIT-PRO (datasheet document title)
- Datasheet: Rev 1.0, April 2024 (spec table titled "Absolute Maximum Ratings")
- Power input terminal: external 7V - 12V (external LiPo or 4x AA batteries)
- Power input voltage absolute maximum: 6 V min, 16 V max
- Analog input voltage: 0–3.3 V
- Total +3V3 output current (GPIO Breakout & Grove Ports): 200 mA max
- Maximum DC motor current: 3 A continuous; 5 A peak (< 5 seconds)
- DC motors controlled with the MOTION:BIT MakeCode extension (channels M1–M4 in the extension)
- Motor voltage at full speed is equal to power source voltage
- Servos: connectors for 8x RC servo motors
- RGB LEDs: user-programmable WS2812B RGB LEDs, connected to P8
- Ext. RGB LED connector for external WS2812B RGB LEDs, daisy-chained (Dout of RGB LED 1)
- GPIO status LEDs: on when the IO state is high
- Motor test buttons: motor runs at full speed
- Motor status LEDs: on when the motor is running
- On/Off switch and Ext. On/Off switch header
- Battery holder: none listed in the datasheet
- Motor driver IC: [NOT STATED]
- Buzzer: [NOT STATED]
- Dimensions: [NOT STATED] (drawing only)
- Protections (reverse polarity, over-current, thermal): [NOT STATED]
- Operating temperature: [NOT STATED]
- Power: external Vin 7–12 V terminal block only; no micro USB, no battery holder, no charging (product page, Cytron comparison image)
- Motors: 4 channels, 3 A continuous, 5 A peak; total 5 V output 3 A; servo power selectable 5 V or Vin; total servo current 3 A (Cytron comparison image)
- Packing: board, screwdriver, 3 Grove-to-JST-SH cables, 4 bumpers, 4 building-block pins (product page)

## Interfaces and compatibility
- micro:bit versions: [NOT STATED]
- micro:bit socket: plug in with the micro:bit LEDs facing out
- GPIO breakout, colour-coded GVS, 3.3V power per GPIO: P0, P1, P2, Button A, Button B, P9, P12, P13, P14, P15, P16
- Maker Ports: JST-SH 4-way, compatible with Qwiic, STEMMA QT and Grove (via conversion cable); datasheet: "These pins are available on Maker Ports: P0-P9, P1-P2, P2-P12"
- Maker Port (I2C): JST-SH 4-way, for I2C modules only
- I2C breakout: micro:bit I2C pins (P19 SCL, P20 SDA)
- P8: onboard RGB LEDs
- 5V Supply output for external sensors/modules
- Motor terminals MA and MB: swapping the connection reverses the direction
- MakeCode: "Add MOTION:BIT Extension in MakeCode Editor to control the DC Motors and Servo Motors"; https://makecode.microbit.org/pkg/CytronTechnologies/pxt-motionbit (search "motionbit" in Extensions)
- Python: [NOT STATED]

## Use cases
- Controlling DC motors and servo motors with micro:bit ("Simplifying Motion Control with micro:bit")
- Adding sensors and modules through the GPIO breakout and Maker Ports
- Cytron tutorial: [Getting Started with MOTION:BIT Pro](https://my.cytron.io/tutorial/getting-started-with-motion-bit-pro)

## Known limitations
- External input 7–12 V; absolute maximum 6–16 V
- DC motor current 3 A continuous; 5 A peak only for < 5 seconds (per channel or total not stated)
- +5V output total 3 A; +3V3 total 200 mA shared by GPIO breakout and Grove ports
- Analog input 0–3.3 V
- If the servo jumper is set to VIN, the servo voltage rating must be compatible with VIN, else it might damage the servo
- Motor full-speed voltage equals the power source voltage
- No battery holder listed in the datasheet
- Maker Port (I2C) is for I2C modules only
- P8 is used by the RGB LEDs
- External On/Off switch works only when the onboard switch is Off
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Motion Control with micro:bit"
- Datasheet header: "Simplifying Digital Making"

## Price band
RM166.95 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-motion-bit-pro-12v-robotics-expansion-board-for-micro-bit

## Datasheet
https://drive.google.com/file/d/17kkl6oBU0n-gQtyQ84ylxg2KX3E9Ma0_/view

## Source type
Datasheet

## Source link
https://drive.google.com/file/d/17kkl6oBU0n-gQtyQ84ylxg2KX3E9Ma0_/view
