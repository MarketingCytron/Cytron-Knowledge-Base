# Product fact sheets

## Product name
Maker UNO

## Aliases
MAKER-UNO, Maker UNO, Maker UNO: Simplifying Arduino for Education

## What it is
An Arduino UNO-compatible board built on the ATmega328P, powered and programmed through a USB Micro-B socket via a CH340 USB-to-serial chip. It adds LEDs on the digital pins, a piezo buzzer on pin 8 and a programmable push button on pin 2.

## Specs and functions
- Product code: MAKER-UNO
- Microcontroller: SMD ATmega328P (the same microcontroller as the Arduino UNO) with Optiboot (UNO) bootloader
- Clock speed: 16MHz
- Flash memory: 32k
- Digital I/O pins: 14 (6 PWM outputs)
- Analog inputs: 6
- I/O levels: 0-5V outputs with 3.3V compatible inputs
- USB-to-serial: CH340 (board layout names the chip CH340G)
- USB connector: USB Micro-B socket (main power, program upload, debugging)
- Input voltage via USB connector: 4.8 V min, 5.2 V max
- Power: USB 5V from computer, power bank or standard USB adapter; Cytron LiPo Power Shield for portable use
- 3.3V voltage regulator: 500mA maximum; DC current for 3.3V pin 500 mA max continuous
- DC current per I/O pin: 20 mA max
- 5V output current: [NOT STATED]
- LEDs: LED array for 5V, 3.3V, TX, RX and all digital pins; standard LED on pin 13 (user manual: a programmable LED on every digital pin, D0 to D13; product page: "12x LEDs")
- Pin LEDs are driven through a series of MOSFETs, so an LED can be controlled or act as an indicator for an input, even a pull-up input
- USB-serial LED shows upload and Serial Monitor activity
- Programmable push button: pin 2 to GND, configure as INPUT_PULLUP
- Piezo buzzer: pin 8, through a slide switch (on = buzzer, off = pin 8 free for other uses)
- Reset button
- ISP 6-pin (2x3) header for AVR programmers; also usable for SPI
- PCB colour: purple
- Packing list: 1 × Maker Uno (Code: MAKER-UNO); product page: pin header label stickers included
- Warranty: 6 months, manufacturing defects only (user manual Rev 1.0); product page: 12 months
- Dimensions: [NOT STATED]
- User's Manual: Rev 1.0, Dec 2017; board package section updated 21 March 2018
- Packing: Maker UNO + GPIO labeling sticker (product page)
- Warranty: 12 months (current product page; manual Rev 1.0 says 6 months)

## Interfaces and compatibility
- Arduino UNO R3-standard female headers; R3 shield compatible
- SDA, SCL and IOREF pins are broken out as on the UNO R3
- No Vin pin: Arduino shields that require Vin are not compatible
- No DC jack: power through USB only (product page)
- Differences from Arduino UNO: CH340 instead of ATmega16u2 (product page: "to bring down the cost"), USB Micro-B, no DC jack, no Vin pin, onboard LEDs, buzzer and button
- Arduino IDE: select board "Arduino/Genuino Uno" and the correct COM port (Cytron advises this board "for safety purpose")
- Optional Cytron board package "Maker Uno" (Boards Manager URL https://cytrontechnologies.github.io/package_cytron_makeruno_index.json); it sets all digital pins to OUTPUT by default; latest version in the index 1.1.0-rc2
- CH340 driver needed; port appears as "USB-SERIAL CH340 (COMx)" in Device Manager
- MicroPython / CircuitPython: [NOT STATED]

## Use cases
- Arduino learning in classrooms (boards "used in classes are powered using USB")
- Testing code without external parts using the onboard LEDs, buzzer and button
- Troubleshooting with pin LEDs that show input state
- Portable projects powered by a power bank or Cytron LiPo Power Shield
- Cytron tutorial: [Installing CH340 Driver on Mac OS](https://my.cytron.io/tutorial/CH340_MacOS)
- Cytron tutorial: [Car Reverse Beep System Using Ultrasonic Sensor & Maker UNO](https://my.cytron.io/tutorial/measuring-distance-using-ultrasonic-sensor)
- Cytron tutorial: [Build a Robotic Arm with Servo, Joystick and Arduino Maker UNO](https://my.cytron.io/tutorial/robotic-arm)
- Cytron tutorial: [Getting Started with 4 Channel Motor Driver and Arduino](https://my.cytron.io/tutorial/getting-started-4-channel-motor-driver-arduino)
- Cytron tutorial: [Controlling LED on Arduino using IR Remote](https://my.cytron.io/tutorial/controlling-led-on-arduino-using-ir-remote)

## Known limitations
- Power from USB only, 4.8–5.2 V; no DC jack and no Vin pin
- Shields that need Vin do not work
- 3.3V pin limited to 500 mA; each I/O pin to 20 mA
- Pin 8 is shared with the buzzer; switch the buzzer off to use pin 8 for other purposes
- Pin 2 is shared with the onboard button
- With board "Arduino/Genuino Uno", floating input pins can make the pin LEDs light up randomly
- The Maker Uno board package sets all digital pins to OUTPUT by default
- Use one power source at a time
- Needs the CH340 driver for USB programming
- 5V output current and protection features: [NOT STATED]

## Positioning (kept apart from specs)
- Product page: "an Arduino Compatible board specially designed to simplify building your projects"
- User manual: "PURPLE PCB !"; three extra features that make it "more suitable for beginner"

## Price band
RM37.80 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-simplifying-arduino-for-education

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-250/pdf/cytron-maker-uno-microcontroller-datasheet1.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-250/pdf/cytron-maker-uno-microcontroller-datasheet1.pdf
