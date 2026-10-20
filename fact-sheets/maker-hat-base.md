# Product fact sheets

## Product name
Maker Hat Base - HAT & GPIO Extension for Raspberry Pi 400

## Aliases
MAKER-HAT-BASE, Maker Hat Base, Cytron Maker Hat Base, Maker Hat Base - HAT & GPIO Extension for Raspberry Pi 400, HAT & GPIO Extension for Raspberry Pi 400

## What it is
A base board that connects to the Raspberry Pi 400 GPIO by a 40-way ribbon cable and extends it to a pin header for stacking a Raspberry Pi HAT, a labelled pin breakout, GPIO status LEDs, 3 Grove ports, 4 buttons and a buzzer. It has no processor of its own; every function is a Raspberry Pi GPIO.

## Specs and functions
- Product code: MAKER-HAT-BASE
- Datasheet: Rev 1.0, September 2021
- Pin header for stacking a Raspberry Pi HAT
- IDC socket for connecting to the Raspberry Pi via 40-way ribbon cable
- Raspberry Pi pins breakout for jumper cables
- GPIO status LEDs: turn on when the GPIO state is high
- 3 Grove ports: I2C (SCL GPIO3, SDA GPIO2), UART (RXD GPIO15, TXD GPIO14), GPIO (GPIO12, GPIO13)
- 4 programmable push buttons, active low, on GPIO17, 22, 23 and 27; enable the internal pull-up to use them
- Programmable fixed tone buzzer, resonant frequency 2700±300Hz, on GPIO26
- Mute switch for the buzzer, for when GPIO26 is used for other purposes
- 3.3V power LED and 5V power LED (on when powered up)
- 5V supply: supplied by Raspberry Pi
- 3.3V supply: 3.235 – 3.365 V, max 800 mA
- GPIO specification: refer to Raspberry Pi
- Dimensions: [NOT STATED]
- Status LED on each GPIO; onboard 3.3 V regulator up to 800 mA (product page)
- Packing: board, mini breadboard, 40-way F-F IDE cable 10 cm, cable clamp, 4 bumpers, PC104 2x20 header (product page)

## Interfaces and compatibility
- Designed for the Raspberry Pi 400 (datasheet)
- Cytron product page images also mention Raspberry Pi 3 and 4
- Connects to the Raspberry Pi through a 40-way ribbon cable to the IDC socket
- Accepts a stacked Raspberry Pi HAT on the pin header
- Grove I2C, UART and GPIO modules
- CAD file available (MAKER-HAT-BASE CAD.zip)

## Use cases
- Stacking a Raspberry Pi HAT on the Raspberry Pi 400
- Connecting components to the Raspberry Pi pins with jumper cables
- Connecting Grove modules over I2C, UART or GPIO
- Using the onboard buttons and buzzer as programmable inputs and output
- Cytron tutorial: [Send Temperature and Humidity Data To ThingSpeak Using micro:bit](https://my.cytron.io/tutorial/maker-hat-base-combine-hat-and-modules-on-raspberry-pi-4-2)
- Cytron tutorial: [Maker HAT Base, combine HAT and modules on Raspberry Pi 4](https://my.cytron.io/tutorial/maker-hat-base-combine-hat-and-modules-on-raspberry-pi-4)
- Cytron tutorial: [Maker HAT Base, allows you to easily access the Raspberry Pi 400 GPIO pins](https://my.cytron.io/tutorial/maker-hat-base-allows-you-to-easily-access-the-raspberry-pi-400-gpio-pins)

## Known limitations
- 5V is supplied by the Raspberry Pi; the board has no separate power input
- 3.3V supply max 800 mA
- GPIO limits follow the Raspberry Pi
- Buttons are active low and need the internal pull-up enabled
- Buzzer is fixed tone (2700±300Hz) on GPIO26; mute it with the switch if GPIO26 is used for other purposes
- A stacked HAT shares the same GPIOs as the buttons, buzzer and Grove ports
- Out of stock on my.cytron.io (2026-10-16)
- Raspberry Pi not included

## Positioning (kept apart from specs)
- Datasheet subtitle: "HAT & GPIO Extension for Raspberry Pi 400"

## Price band
RM45.78, out of stock (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-maker-hat-base-hat-and-gpio-extension-for-raspberry-pi-400

## Datasheet
https://docs.google.com/document/d/12l4vzu-r3VRBCLkCsuM00KOYnMPnQw5HxdfxjA3p5E0/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/12l4vzu-r3VRBCLkCsuM00KOYnMPnQw5HxdfxjA3p5E0/edit
