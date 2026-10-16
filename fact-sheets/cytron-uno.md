# Product fact sheets

## Product name
Cytron UNO - Arduino UNO Compatible

## Aliases
CT-UNO, CT UNO, Cytron UNO, CT UNO (Arduino Uno Compatible)

## What it is
A Cytron version of the Arduino UNO built on an SMD ATmega328 with the Optiboot (UNO) bootloader, programmed over USB Micro-B through an FTDI FT231X USB-serial chip. It can be powered from a 2.1 mm DC adapter socket or from USB.

## Specs and functions
- Product code: CT-UNO
- Microcontroller: SMD ATmega328 with Optiboot (UNO) bootloader (manual spec section names it ATmega328p)
- Clock speed: 16MHz
- Flash memory: 32k
- Digital I/O pins: 14 (6 PWM outputs)
- Analog inputs: 6 (can be digital I/O too)
- Peripherals: UART, SPI, external interrupts, I2C
- I/O levels: 0-5V digital outputs with 3.3V compatible inputs
- USB-to-serial: FTDI FT231X; needs the FTDI VCP driver
- USB connector: USB Micro-B socket (program upload and power)
- DC input: Adapter Socket (2.1mm)
- Input voltage via adapter (recommended): 7 V min, 15 V max
- Input voltage via adapter (limits): 6 V min, 20 V max
- If both adapter and USB are connected, the board automatically uses the adapter
- 5V regulator: 1 A max (with Vin at 12V)
- 3.3V regulator: 500 mA max
- Per-pin current: [NOT STATED] (manual: refer to the ATmega328P specification)
- LEDs: RX LED, TX LED, Power LED (green), programmable LED on pin 13 (active HIGH, orange); TX, RX, Power and pin 13 LEDs moved to the board edge
- Reset button
- ISP 6-pin header (SPI and power); for uploading the Arduino Uno bootloader with an AVR programmer (e.g. AVR USBasp)
- Extra pads for stacking on strip/donut board (0.1" pitch)
- PCB colour: white
- Packing list: 1 x CT-UNO board; USB Micro B cable and 12V 2A AC to DC Adapter are optional add-ons (cable sold separately)
- Warranty: 12 months, manufacturing defects only; misuse and freight both ways not covered
- Dimensions: [NOT STATED]
- User's Manual: V1.0, Nov 2014

## Interfaces and compatibility
- Arduino R3 standard headers; R3 shield compatible; SDA, SCL and IOREF broken out as on UNO R3
- Arduino IDE: Tools > Board > "Arduino Uno", then select the CT-UNO serial port
- Driver: FTDI VCP driver from http://www.ftdichip.com/Drivers/VCP.htm
- Manual examples: LCD Keypad shield; wireless remote omni robot with SHIELD-XBEE and FD04A-R2
- Differences from Arduino UNO R3: FTDI FT231X USB-serial, USB Micro-B socket, SMD ATmega328, 7–15 V recommended input, upgraded on-board regulator (5V 1A), LEDs moved to the edge, extra pads, white PCB
- MicroPython / CircuitPython: [NOT STATED]

## Use cases
- Stacking Arduino UNO shields (e.g. LCD Keypad shield)
- Mobile robots with shields (e.g. wireless remote omni robot with SHIELD-XBEE and FD04A-R2)
- Stacking onto strip/donut board for custom circuits

## Known limitations
- 5V regulator 1 A rating is given only with Vin at 12V
- 3.3V regulator limited to 500 mA
- Adapter input 7–15 V recommended; 6–20 V absolute limits
- Uses an FTDI FT231X: Windows driver install may fail until the FTDI VCP driver is installed
- USB cable not included
- Only one user LED (pin 13); no user button or buzzer
- Per-pin current, reverse-polarity and over-current protection: [NOT STATED]

## Positioning (kept apart from specs)
- User manual: combines "the simplicity of the UNO's Optiboot bootloader (which load program faster), the stability of the FTDI and the R3 shield compatibility of the latest Arduino UNO R3"
- User manual: "White PCB!"
- cytron.com.my product page recommends Maker UNO for beginners and students

## Price band
RM61.74 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-uno-arduino-uno-compatible

## Datasheet
https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view
