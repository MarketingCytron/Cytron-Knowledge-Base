# Product fact sheets

## Product name
SUMO:BIT

## Aliases
SUMO:BIT, SUMOBIT, SUMO-BIT, SUMO BIT

## What it is
A sumo robot expansion board for the BBC micro:bit. It takes a LiPo battery, plugs in two external MD13S motor drivers, and provides opponent-sensor, edge-sensor, servo/RC, RGB LED, mode-switch and joystick connections.

## Specs and functions
- Product code: [NOT STATED]
- Power input voltage (LiPo battery): 7 V min, 25 V max; reverse polarity protection
- Vibration-proof on/off slide switch with MOSFET latching circuit; green power LED
- Battery voltage can be monitored programmatically (battery + terminal feeds an analog input)
- 2 × sockets for external MD13S motor driver boards (one per motor channel); MD13S can be removed and replaced
- With MD13S: 13 A continuous per channel, 30 A peak per channel (peak must not last longer than 10 seconds), motor PWM frequency up to 20 kHz
- 2 × motor current sensors, one for each motor channel
- 4 × red motor status LEDs (MLA/MRA forward, MLB/MRB backward)
- 5 × opponent sensor input ports, pulled up to 5V, with active-low status LEDs; voltage divider protects the micro:bit pins
- 2 × edge sensor input ports (analog sensors); voltage divider adjusts the output voltage
- 1 × general purpose port P2 (analog/digital) with active-low status LED; voltage divider reduces 5V to about 3V
- 2 × servo ports that can also be used as RC pins; servo voltage 5 V max
- 2 × WS2812B RGB LEDs, user programmable
- 1 × 4-way DIP switch for mode/tactic selection, up to 16 configurations (mode 0–15 in the MakeCode extension)
- USB-A port for wireless joystick connection; USB host output 5 V, 600 mA max
- +5V output maximum current (total): 600 mA
- Motor Alignment Module: potentiometer to balance left/right motor speed, test button runs the motors forward for 1 second, potentiometer indicator LEDs
- Firmware Update Module: USB-C port for firmware upload (not for programming) and boot button
- RP2040 co-processor at I2C address 0x09 controls motors, servos, RGB LEDs, mode switch, motor current and battery voltage (Cytron GitHub)
- Datasheet: Rev 1.0, December 2024
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Operating temperature: [NOT STATED]
- Packing: SUMO:BIT with 2 × MD13S attached, flat and Phillips screwdrivers, Dean T male connector 15 cm, sticker set; Jr Kit option adds micro:bit V2 and USB cable (product page)
- Size: 125 × 80 mm; 4 × Ø3.2 mm holes (product page image)
- Firmware (UF2) and STL files on GitHub Cytron-SUMOBIT (product page)

## Interfaces and compatibility
- micro:bit plugs into a vertical edge-connector socket with the LED matrix facing up
- Supported micro:bit versions (V1/V2): [NOT STATED]
- micro:bit pin use (MakeCode extension source): P0 right edge sensor (analog), P1 left edge sensor (analog), P2 general-purpose port, P12 opponent Right, P13 opponent Front Right, P14 opponent Front Center, P15 opponent Front Left, P16 opponent Left, I2C to the RP2040 co-processor (address 0x09)
- Servos, RGB LEDs, motors, mode switch and battery voltage are controlled through the RP2040, not micro:bit pins
- Opponent sensors: Maker Object or other digital sensors; detection is LOW
- Edge sensors: Maker Reflect or any other analog sensors; edge detected when the reading is below the calibrated threshold
- Motor drivers: MD13S × 2, inserted from the bottom of the PCB
- MakeCode extension: pxt-sumobit (search "sumobit"), https://github.com/cytrontechnologies/pxt-sumobit, v1.3.6, approved on makecode.microbit.org
- Extension blocks: DC Motors, Servos, Mode, Motor Current, Opponent Sensors, Edge Sensors, RGB LED, Battery, Robot Kit (countdown, backoff, attack, search)
- MicroPython / Arduino: [NOT STATED]
- USB joystick and RC-receiver input blocks: [NOT STATED]

## Use cases
- Sumo robot projects and competitions with the BBC micro:bit, for learners of all ages
- Selecting a tactic or mode with the DIP switch before a match
- Wireless joystick control through the USB-A port
- SUMO:BIT Robot Kit builds

## Known limitations
- Battery input must stay within 7–25 V (LiPo)
- Motor ratings apply only with the MD13S motor drivers; the board drives no motors on its own
- Peak motor current 30 A per channel must not last longer than 10 seconds
- +5V output is 600 mA total, shared by servos and other 5V loads; servo voltage 5 V max
- USB-C port is for firmware updates only, not for programming the micro:bit
- micro:bit must be inserted with the LED matrix facing up; MD13S must be inserted from the bottom of the PCB
- P2 port signal passes through a voltage divider (5V to about 3V)
- Supported micro:bit version: [NOT STATED]

## Positioning (kept apart from specs)
- Cytron launch artwork: "Beginner Friendly, Competition Ready."
- "Start your sumo journey with the SUMO:BIT Robot Kit!"

## Price band
RM198.45 board only (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-sumo-bit

## Datasheet
https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-429/pdf/sumobit-expansion-board-for-microbit-datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-429/pdf/sumobit-expansion-board-for-microbit-datasheet.pdf
