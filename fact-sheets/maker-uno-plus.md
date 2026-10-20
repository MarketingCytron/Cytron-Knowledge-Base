# Product fact sheets

## Product name
Maker UNO Plus for Education (Arduino Compatible)

## Aliases
MAKER-UNO-PLUS, Maker UNO Plus, Maker UNO+, Cytron Maker UNO Plus, Maker UNO Plus: Simplifying Arduino for Education, Maker UNO Plus for Education

## What it is
An Arduino UNO R3-compatible board built on the SMD ATmega328P, powered and programmed through a USB Micro-B socket via an FT231X USB-to-serial chip. It adds LEDs on the digital pins, a piezo buzzer on pin 8 with a slide switch and a programmable push button on pin 2.

## Specs and functions
- Product code: MAKER-UNO-PLUS
- User's Manual: Rev 1.0, Oct 2018 (no separate datasheet)
- Microcontroller: SMD ATmega328P (the same microcontroller as the Arduino UNO) with Optiboot (UNO) bootloader
- USB-to-serial: FT231X
- USB connector: USB Micro-B socket (main supply, program upload, Serial Monitor)
- Operating voltage: 5V
- Input voltage via USB connector: 4.8 V min, 5.2 V max; "5V (USB only)"
- 5V current: "USB source"
- 3.3V voltage regulator: 500mA maximum; DC current for 3.3V pin 500 mA max continuous
- DC current per I/O pin: 20 mA max
- I/O levels: 0-5V outputs with 3.3V compatible inputs
- Digital I/O pins: 14 (6 PWM outputs); analog inputs: 6
- UART, SPI, I2C: 1, 1, 1; external interrupts: 2
- Flash, SRAM, EEPROM: 32KB, 2KB, 1KB
- Clock speed: 16MHz
- ISP 6-pin (2x3) header, for AVR programmer; also usable for SPI
- LED array for 5V, 3.3V, TX, RX and the digital pins; 12 programmable indicator LEDs at pins 2 – 13 (product page: "12x LED"); standard LED on pin 13
- Pin LEDs driven through a series of MOSFETs, so each LED can be controlled as an output or act as an input indicator, even for input pull-up
- USB-serial LED shows upload and Serial Monitor data
- Programmable push button: pin 2 to GND, configure as INPUT_PULLUP
- Piezo buzzer: pin 8, through a slide switch (on = buzzer; off = pin 8 free for other uses)
- Reset button
- FCC, CE, RoHS: Yes
- PCB colour: purple
- Packing list: 1 × Maker Uno Plus (Code: MAKER-UNO-PLUS), 1 × Micro USB cable, 1 × Pin Header Sticker
- Warranty: 12 months (product page, current); the 2018 user manual said 6 months
- Dimensions: [NOT STATED]
- USB-serial confirmed FT231X by the product page ("upgraded to FT231X from CH340")

## Interfaces and compatibility
- Arduino UNO R3-standard female headers; R3 shield compatible; SDA, SCL and IOREF broken out as on UNO R3
- No Vin pin: Arduino shields that require Vin are not compatible, unless the shield can select an external power source instead of Vin
- Arduino IDE: select "Arduino/Genuino UNO" and the correct COM port; compatible with Arduino UNO example code and libraries
- Cytron learning guide: Windows installs the driver automatically; macOS 10.11 and later does not need the FTDI driver
- Portable power: power bank or Cytron LiPo Power Shield
- Differences from Arduino Uno: input 5V USB only (Uno: 7 - 12V recommended, 6 - 20V limit via adapter); 5V current "USB source" (Uno: 1A); 3.3V current 500mA (Uno: 50mA); USB-serial FT231X (Uno: ATmega16U2); SMD ATmega328P; USB Micro-B; no DC jack; no Vin; onboard LEDs, button and buzzer
- Differences from Maker UNO (user manual table): USB-serial FT231X (Maker UNO: CH340G); FCC, CE, RoHS Yes (Maker UNO: No)

## Use cases
- Students learning coding and microcontrollers
- Learning digital input, output and PWM (piezo buzzer and LED brightness) with just the board
- Playing tones with the onboard buzzer (Arduino example toneMelody)

## Known limitations
- Power through USB only: the DC jack (12V adapter input) and the 5V linear regulator were removed
- No Vin pin; shields that need Vin and cannot select another power source are not compatible (example: GPRS Shield V3.0)
- 5V current is limited by the USB source; 3.3V pin 500 mA max; 20 mA max per I/O pin
- Pin 8 is shared with the buzzer: slide the switch off to use pin 8 for other purposes
- Pin 2 is used by the onboard button
- Use only 1 power source at a time
- Warranty: use the product page's 12 months (the 2018 manual's 6 months is out of date)

## Positioning (kept apart from specs)
- "Simplifying Arduino for Education"
- Designed and developed specially for students to learn coding and microcontroller
- Named Maker UNO Plus "to encourage everyone to be a maker"
- Redesign of CT-UNO with ARUS and rero, "more affordable, and more beginner friendly"

## Price band
RM75.60 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-plus-simplifying-arduino-for-education

## Datasheet
https://docs.google.com/document/d/1M2sYWbmmt-Auyq963b5VpsdONsfrjwCBTLAf0VuP6zk/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1M2sYWbmmt-Auyq963b5VpsdONsfrjwCBTLAf0VuP6zk/edit
