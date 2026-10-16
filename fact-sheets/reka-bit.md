# Product fact sheets

## Product name
REKA:BIT

## Aliases
REKA:BIT, REKABIT, REKA-BIT, REKA BIT, REKA:BIT Simplifying Robotics with micro:bit

## What it is
A robotics expansion board for the BBC micro:bit with a built-in 2-channel DC motor driver, 4 servo ports, RGB LEDs and 6 Grove ports. It works with micro:bit V1 and V2.

## Specs and functions
- Product code: [NOT STATED]
- Power input voltage: 3.6 V min, 6 V max (DC jack)
- On/Off switch and power LED
- Low Voltage LED: blinks when the power input is below 3.6V; can be used as the low battery indicator
- Over Voltage LED: on when the power input is over 7V; power to the servos and DC motors is cut off
- 2-channel DC motor driver: 1 A continuous, 1.5 A peak (< 5 seconds) per motor; motor voltage at full speed equals the power source voltage
- Motor status LEDs: MxA forward, MxB backward
- Motor test buttons (M1A, M1B, M2A, M2B): run the motor at full speed without code
- 4 × RC servo ports; servo V+ equals the power source voltage
- WS2812B RGB LEDs, user programmable, connected to P8 (2 pixels in the MakeCode extension)
- 6 × Grove ports: 3 × analog input/digital IO, 2 × digital IO, 1 × I2C interface
- GPIO status LEDs on the Grove-port GPIOs (on when HIGH)
- Analog input voltage: 0–3.3 V
- Total +3V3 output current (Grove ports): 300 mA max
- Co-processor PIC16F1827 at I2C address 0x08 drives the motors and servos (Cytron GitHub)
- Datasheet: Rev 1.0, April 2021
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Works with micro:bit V1 & V2
- micro:bit pin use: P8 RGB LEDs; I2C to the co-processor (address 0x08) for motors, servos, power state, low-battery state, over-voltage state and input voltage
- Grove port to micro:bit pin map: [NOT STATED]
- Grove ports are 3.3 V; analog inputs 0–3.3 V
- MakeCode extension: pxt-rekabit, https://github.com/CytronTechnologies/pxt-rekabit, v1.2.3, approved on makecode.microbit.org
- Extension blocks: DC Motors (run 0–255, brake), Servos (0–180°, disable), RGB LED (clear, brightness, pixel colour)
- MakeCode Python: test program viewable in MakeCode Python mode
- REKA:BIT RBT Project Kit extension: https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit (RGB Stick, Big LED, soil moisture, ultrasonic)
- MicroPython library: [NOT STATED]

## Use cases
- Simplifying robots and projects with micro:bit
- Student projects with mechanical movement using DC motors and servos
- Adding sensors and modules through Grove ports
- REKA:BIT RBT Project Kit (STEAM and RBT projects for beginners)

## Known limitations
- Power input 3.6–6 V; above 7V the servo and DC motor power is cut off
- Below 3.6V only the Low Voltage LED blinks; no under-voltage cut-off is stated
- DC motor current 1 A continuous, 1.5 A peak for less than 5 seconds
- Servo V+ and motor voltage equal the power source voltage (not regulated)
- Grove analog input max 3.3 V; Grove +3V3 output 300 mA total
- Do not use I2C address 0x08 on the Grove I2C port (used by the co-processor)
- On micro:bit V1, P9 is shared with the LED matrix, so the P9 status LED stays lit
- Motor direction depends on wiring; swapping MxA and MxB reverses it
- Reverse-polarity protection: [NOT STATED]

## Positioning (kept apart from specs)
- "Simplifying Robotics with micro:bit"
- "REKA" comes from the Malay word "reka bentuk", which means design
- With the built-in dual-channel DC motor driver, 4x servo control and dedicated power input, students can build projects with mechanical movements right away

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-rekabit-simplifying-robotics-with-microbit

## Datasheet
https://docs.google.com/document/d/1axLhH-zaFDheOyz6gbXfYEysigGxpmMnRBC93SW-zR8/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1axLhH-zaFDheOyz6gbXfYEysigGxpmMnRBC93SW-zR8/edit
