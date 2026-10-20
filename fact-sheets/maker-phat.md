# Product fact sheets

## Product name
Maker pHAT: Simplifying Raspberry Pi for Education

## Aliases
HAT-MAKER, Maker pHAT, Cytron Maker pHAT, Maker pHAT: Simplifying Raspberry Pi for Education

## What it is
A Raspberry Pi Zero-size pHAT that stacks on the Raspberry Pi 40-pin GPIO header and adds a USB Micro-B socket for 5V power and a USB-to-UART serial console, 8 GPIO indicator LEDs, 3 push buttons, an active buzzer and labelled breakout pins. It needs a Raspberry Pi (not included).

## Specs and functions
- Product code: HAT-MAKER
- User's manual: Rev 1.10, Feb 2019 (no separate datasheet)
- Form factor: Raspberry Pi Zero size, standard Raspberry Pi GPIO footprint
- 8 GPIO indicator LEDs on GPIO 17, 18, 27, 22, 25, 12, 13, 19; these GPIOs can be configured as output, input or input pull-up
- 3 programmable push buttons: SW1 GPIO 21, SW2 GPIO 16, SW3 GPIO 20; configure as input pull-up (the manual's feature list says "GPIO 21, 19 and 20"; its board layout, section 7.2 and demo code say 21, 16 and 20)
- Active buzzer on GPIO 26: HIGH = on, LOW = off
- USB Micro-B socket for 5V input and USB-to-UART communication, connected to the Raspberry Pi UART (TX GPIO 14, RX GPIO 15)
- USB-serial IC: FT231X on Rev1.1 (shipping since January 2019); CH340 on the earlier Rev1.00 (product page)
- USB-serial activity indicator LED
- Labelled breakouts: 5V, 3.3V, GND; I2C SDA GPIO 2, SCL GPIO 3; UART TX GPIO 14, RX GPIO 15; SPI MOSI GPIO 10, MISO GPIO 9, SCK GPIO 11, CE0 GPIO 8, CE1 GPIO 7; GPIO 17, 18, 27, 22, 25, 12, 13, 19
- Input voltage: USB 5V, from computer, power bank or standard USB adapter
- Absolute maximum input voltage via USB connector: 4.8 – 5.2 V
- DC current for 5V pin (max continuous): limited by USB (no figure given)
- Rev1.10 has pre-soldered SMD header pins on the breakout pads
- Purple PCB
- Warranty: 1 year (user's manual); 12 months (Cytron product page)
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Raspberry Pi 3B / 3B+ / 3A+, 4B, 1 A+ and Raspberry Pi Zero / W / WH (product page); **not compatible with Raspberry Pi 5** (tested by Cytron, product page)
- Stacks directly on Raspberry Pi Zero WH
- Raspberry Pi 3 Model B / B+ need the 2x20 PC104 stacking header (included)
- Serial console: add enable_uart=1 to config.txt; terminal speed 115200 (PuTTY on Windows)
- USB-serial drivers linked in the manual for Windows 10 and macOS (CH341SER)
- Python 3 with the gpiozero library (LED, Button, Buzzer); demo code in the manual and on a Cytron gist
- In the box: 1x Maker pHAT (HAT-MAKER), 1x 2x20 Stacking Header (CN-PH-PC104)

## Use cases
- Getting started with Raspberry Pi without a monitor, keyboard or mouse (headless), using the serial console
- Remote access to the Raspberry Pi through serial, then setting up Wi-Fi and VNC
- Learning to interface with sensors and actuators and coding with the onboard LEDs, push buttons and buzzer
- Prototyping with labelled GPIO, SPI, UART and I2C breakouts
- Hardware shutdown with push buttons

## Known limitations
- Power input is USB 5V only (4.8 – 5.2 V absolute maximum)
- 5V pin current is limited by the USB source
- Push buttons need the GPIO set as input pull-up
- LEDs are only on GPIO 17, 18, 27, 22, 25, 12, 13, 19
- Do not unplug the USB cable without a proper shutdown; it might corrupt the microSD card
- The USB serial console uses the Pi UART on GPIO 14/15 and needs enable_uart=1
- Raspberry Pi 3 Model B / B+ need the stacking header to fit
- The printed demo code in the manual has an undefined variable (times) in the shutdown branch; the gist version uses range(3)
- The manual's setup steps are for Raspbian Stretch / NOOBS (2019)
- Raspberry Pi not included

## Positioning (kept apart from specs)
- "Maker pHAT is designed for anyone who want to get start with any Raspberry Pi projects"
- Designed to ease getting started with Raspberry Pi headless, and prototyping
- Addresses beginner pain points: no onboard USB-to-UART, no GPIO status indicator, unlabelled GPIO, no programmable push button for proper shutdown
- Product name tagline: "Simplifying Raspberry Pi for Education"
- "PURPLE PCB!"

## Price band
RM45.78 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-phat-simplifying-raspberry-pi-for-education

## Datasheet
https://docs.google.com/document/d/1iDYLyoQKOPJRD5m5ivu8Ivv6zyeLIc3IxUtRKOx7n8k/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1iDYLyoQKOPJRD5m5ivu8Ivv6zyeLIc3IxUtRKOx7n8k/view
