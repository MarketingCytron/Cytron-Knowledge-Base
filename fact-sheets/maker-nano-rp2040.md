# Product fact sheets

## Product name
Maker Nano RP2040

## Aliases
MAKER-NANO-RP2040, Cytron Maker Nano RP2040, MakerNanoRP2040

## What it is
An Arduino Nano form-factor microcontroller board built on the Raspberry Pi RP2040. It has GPIO status LEDs, two RGB LEDs, a piezo buzzer, a user button and two Maker Ports.

## Specs and functions
- Product code: MAKER-NANO-RP2040
- MCU: Raspberry Pi RP2040
- Datasheet: Rev 1.1, July 2024; its spec table is titled "Absolute Maximum Ratings"
- Flash: [NOT STATED] in the Cytron datasheet
- USB: Micro USB port, for program upload and power
- Power input voltage (Vin): 7.0 – 30.0 VDC
- DC +5V max current (including onboard usage): 110 mA powered from Vin, 500 mA powered from USB
- DC +3V3 max current (including onboard usage): 110 mA powered from Vin, 500 mA powered from USB
- RGB LEDs: 2 x WS2812B, user programmable, on GP11
- User programmable button: GP20
- Boot button (hold while resetting to enter bootloader mode) and Reset button
- Piezo buzzer: GP22, able to play tone or melody, with mute switch
- Digital IO LEDs: on when the IO state is high (14 LEDs, 85 µA each); the datasheet table lists GP0 – GP9, GP16 – GP18
- Digital IO LEDs enable jumper: cut the trace to disable the LEDs (~1.19 mA saved); solder it to re-enable
- 5V and 3.3V power LEDs
- Maker Port 0: JST-SH 4-way, GPIO, I2C, UART
- Maker Port 1: JST-SH 4-way, GPIO, I2C, Analog In
- Analog inputs: A0 – A3 = GP26 – GP29
- Header (silkscreen GP numbers): D2 – D9 = GP2 – GP9, D10 = GP17, D11 = GP19, D12 = GP16, D13 = GP18, A4 – A7 = GP12 – GP15; AREF position is NC; GP0 and GP1 sit at the Nano TX/RX positions
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- USB VID 0x2E8A, PID 0x100F (CircuitPython & Arduino Core)
- Flash 2 MB, RAM 264 KB (product page)
- Maker Port 0 = GP0/GP1; Maker Port 1 = GP26/GP27 (Cytron pinout image)
- GP19 has a status LED; 14 status LEDs in total (product page, pinout image)
- Packing: board + 2 Grove-to-JST-SH cables (product page)

## Interfaces and compatibility
- Pin header: "Compatible with original Arduino Nano"
- Maker Ports: compatible with Qwiic, STEMMA QT and Grove (via conversion cable)
- CircuitPython: Cytron firmware at circuitpython.org board "cytron_maker_nano_rp2040", with NeoPixel and simpleio built in; pin names LED (GP2), RGB/NEOPIXEL (GP11), BUTTON (GP20), BUZZER (GP22), A0 – A3
- MicroPython: loaded using the Raspberry Pi guide (no Cytron-specific firmware)
- Arduino: Arduino IDE upload per the datasheet; the arduino-pico (Earle Philhower) core has the board "Cytron Maker Nano RP2040"
- Cytron GitHub: CircuitPython and MicroPython examples; a new board's code.py is the demo program

## Use cases
- Projects that need an Arduino Nano form factor with an RP2040 MCU
- Connecting Qwiic, STEMMA QT or Grove modules through the Maker Ports
- Cytron tutorial: [Control DC motor using Maker Drive and CircuitPython on RP2040](https://my.cytron.io/tutorial/control-dc-motor-using-maker-drive-and-circuitpython-on-rp2040)
- Cytron tutorial: [Display Images on Graphic LCD with Maker Nano RP2040](https://my.cytron.io/tutorial/display-image-on-the-graphic-lcd-using-maker-nano-rp2040-and-circuitpython)
- Cytron tutorial: [Monitor Soil Moisture With Maker Nano RP2040 And Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/maker-nano-rp2040-with-maker-soil-moisture-sensor)
- Cytron tutorial: [Gesture Control With Maker Nano RP2040 And APDS9960](https://my.cytron.io/tutorial/gesture-control-with-makernanorp2040-and-apds9960)

## Known limitations
- 3.3 V logic: digital input high level max 3.6 V, so 5 V signals can't drive the pins directly
- Only A0 – A3 (GP26 – GP29) are analog inputs; A4 – A7 (GP12 – GP15) have no ADC; AREF position is NC
- Code uses GP numbers, not Arduino D numbers
- Default I2C/UART in CircuitPython is GP0/GP1 and arduino-pico Wire is on GP0/GP1, not A4/A5
- board.LED / PIN_LED is GP2, a header pin; there is no separate user LED
- +5V and +3V3 are limited to 110 mA each when powered from Vin
- Spec values are absolute maximum ratings
- The datasheet does not state the Maker Port pin assignments
- The datasheet's Digital IO LED list (GP0 – GP9, GP16 – GP18) does not match its own count of 14 LEDs
- The datasheet's mute-switch text refers to "pin D8", while the buzzer is on GP22
- The setup-circuitpython.md guide in Cytron's Maker Nano GitHub repo is copied from Maker Pi RP2040 and links that board's firmware
- No protection features are stated in the datasheet

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Projects with Raspberry Pi RP2040"
- GitHub README: "a small but powerful MCU for your project"

## Price band
RM41.58 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-nano-rp2040

## Datasheet
https://docs.google.com/document/d/15IMxlESQE43sP7brZpqlfHVTAdX1N_XenzpvfP8cT_8/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/15IMxlESQE43sP7brZpqlfHVTAdX1N_XenzpvfP8cT_8/edit
