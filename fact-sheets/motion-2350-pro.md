# Product fact sheets

## Product name
MOTION 2350 Pro

## Aliases
MOTION-2350-PRO, Cytron MOTION 2350 Pro, MOTION 2350 Pro Rev 2.0, MOTION2350 Pro

## What it is
A robot controller board built on the Raspberry Pi RP2350, with a 4-channel brushed DC motor driver, 8 servo ports and 3 Maker Ports. The current board is Rev 2.0.

## Specs and functions
- MCU: RP2350
- Datasheet: Rev 2.0, September 2025; its spec table is titled "Absolute Maximum Ratings"
- Revision ID: Rev 2.0 has a "REV 2.0" silkscreen label just below the "MOTION 2350 PRO" logo; its bottom side has fewer IC chips
- Power input voltage (USB or VIN): 3.6 – 16 V; absolute maximum VIN 18 V, recommended maximum 16 V
- VIN terminal: external 3.6V – 16V DC; can be powered by an external LiPo or 4x AA batteries
- USB-C: program upload and power
- On/Off switch, plus an Ext. On/Off switch header (onboard switch must be Off to use it)
- Overvoltage protection: above 18V the board shuts down, and resumes once the voltage is back in the safe range
- DC motor driver: 4 channels (M1–M4), 5 A continuous and 10 A peak (< 5 seconds) per channel, PWM frequency max 20 kHz
- Motor driver has overcurrent and overtemperature protection: shutdown threshold 150 ℃, thermal hysteresis (recovery) 60 ℃; the datasheet text says it resumes below a safe temperature (typically 100°C)
- Motor pins: M1A = GP8, M1B = GP9, M2A = GP10, M2B = GP11, M3A = GP12, M3B = GP13, M4A = GP14, M4B = GP15
- Vmotor: USB only → VUSB - 0.4 V to VUSB; VIN only → VIN; USB + VIN: VIN < VUSB → VUSB - 0.4 V to VUSB, VIN > VUSB and VIN - VUSB < 0.6 V → VIN - 0.4 V, VIN - VUSB > 0.6 V → VIN
- Motor test buttons (run the motor at full speed) and motor status LEDs
- Servo ports: 8 x RC servo, signal on GP0 – GP7, header marked GND / 5V / SIG
- 5V servo supply: VIN > 5.8 V → 5 V from a buck converter; VIN < 5.5 V → follows VIN (Schmitt-trigger switching)
- Total +5V output current (servo ports): 3 A when VIN < 5.8 V, 2.5 A when VIN > 5.8 V
- Total +3V3 output current (GPIO breakout & Maker Ports): 200 mA max
- Maker Ports: 3 x JST-SH 4-way, on GP16/GP17, GP26/GP27, GP28/GP29
- GPIO breakout: 8 pins (GP16 – GP19, GP26 – GP29) in colour-coded GVS format with 3.3V
- USB host (Type-A): D+ = GP24, D- = GP25; 5 V, 100 mA max
- RGB LEDs: 2 x WS2812B (NeoPixel compatible) on GP23
- User buttons: GP20 and GP21
- Piezo buzzer: GP22, with buzzer mute switch
- Measure VIN jumper: solder it to read VIN on GP29 (ADC3); formula as printed "VIN = VADC / 6.1"
- GPIO/servo status LEDs: on when the IO is high
- Debug header: SWDIO, GND, SWCLK; BOOT and RST buttons
- Digital input: low -0.3 – 0.8 V, high 2.0 – 5.5 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃
- Flash: 2 MB (product page)
- Board size: 95.2 × 57.2 × 8 mm (product page)
- Rev 2.0 adds overvoltage and overcurrent protection (product page)
- Packing: board, STEMMA QT/Qwiic cable 150 mm, 2 Grove-to-JST-SH cables 200 mm, silicone bumpers, 4 friction pins, mini screwdriver (product page)

## Interfaces and compatibility
- Maker Ports: compatible with Qwiic, STEMMA QT and Grove (via conversion cable)
- USB host for a USB joystick/gamepad
- 4 brushed DC motor terminals, 8 servo ports, 8-pin GPIO breakout, VIN terminal, USB-C
- CircuitPython: preloaded with a demo program; firmware is board "cytron_motion_2350_pro" on circuitpython.org (board.M1A – board.M4B, NEOPIXEL, VOLTAGE_MONITOR; NeoPixel, Motor and SimpleIO libraries built in)
- MicroPython: official board CYTRON_MOTION_2350_PRO (pin names M1A – M4B, BTN1, BTN2, NEOPIXEL)
- C/C++: listed on the product page
- Arduino: supported — the product page lists Arduino and links a Cytron "Getting Started with MOTION 2350 Pro using Arduino IDE" tutorial; the arduino-pico (Earle Philhower) core includes the board "Cytron Motion 2350 Pro"
- Product page: compatible with the existing Raspberry Pi Pico ecosystem

## Use cases
- Building an advanced robot while minimizing effort on electronics and focusing on mechanics
- Robots with mecanum wheels using the 4-channel driver
- Robots controlled by a USB joystick/gamepad through the USB host port

## Known limitations
- Rev 2.0 ratings (5 A continuous / 10 A peak) apply to Rev 2.0 only; Rev 1.0 is rated 3 A continuous / 5 A peak and has no motor overcurrent protection
- my.cytron.io now states the Rev 2.0 figures (5 A continuous / 10 A peak); Cytron's GitHub pinout image still shows 3 A per channel (Rev 1 figures)
- Thermal shutdown may occur even if current is below the rated value; a heatsink or better airflow helps
- Spec values are absolute maximum ratings
- Connecting USB and VIN at the same time is not recommended (the datasheet says it is safe)
- Servo 5V rail follows VIN when VIN is below 5.5 V
- Maker Ports and the GPIO breakout share GP16, GP17, GP26, GP27, GP28, GP29; free user GPIO is GP16 – GP19 and GP26 – GP29 only
- With the VIN jumper soldered, GP29 is used and its GPIO LED stays on
- Motor test buttons run the motor at full speed without any code
- The ext. switch header works only with the onboard switch Off
- USB host output: 100 mA max
- The datasheet has no motor-driver truth table (brake/coast not stated)
- arduino-pico maps LED_BUILTIN to GP2 (a servo pin), Serial1 to GP0/GP1 and SPI to GP4 – GP7 (servo pins)
- Cytron's demo code comment says the NeoPixels are on GP18; the code and datasheet use GP23

## Positioning (kept apart from specs)
- Datasheet tagline: "An Advanced Robotics Controller for Beginners"
- Product page: "Built for beginner and intermediate users to experience the Pro version of the board"
- Product page: "Maker" features such as silkscreen GPIO references, colored headers, quick test buttons and motor output LEDs

## Price band
RM131.15 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-motion-2350-pro

## Datasheet
https://www.farnell.com/datasheets/4726021.pdf

## Source type
Datasheet

## Source link
https://www.farnell.com/datasheets/4726021.pdf
