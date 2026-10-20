# Product fact sheets

## Product name
Maker Nano for Projects (Arduino Compatible)

## Aliases
MAKER-NANO, Maker Nano, Cytron Maker Nano, Maker Nano: Simplifying Arduino for Projects, Maker Nano for Projects

## What it is
An Arduino Nano-form-factor board whose pin header is compatible with the original Arduino Nano. It adds LEDs on D2–D13, a piezo buzzer with a mute switch, a user button on D2 and a 7.0–30.0 VDC Vin input.

## Specs and functions
- Product code: MAKER-NANO
- Datasheet: Rev 1.0, June 2020; spec table titled "Absolute Maximum Ratings"
- Power input voltage (Vin): 7.0 – 30.0 VDC
- Digital input voltage: low level 0 – 0.5 V; high level 1.7 – 5.0 V
- Analog input voltage: 0 – 5.0 V
- DC +5V maximum current (including onboard usage): 100 mA
- DC +3V3 maximum current (including onboard usage): 50 mA
- Micro USB port: upload Arduino program from PC; debugging (Serial Monitor)
- Digital IO LEDs on D2 – D13: turn on when the IO state is high
- Digital IO LEDs enable jumper (bottom): cut the trace to disable the digital IO LEDs, to save power or reduce distraction
- Power LEDs for 3V3 and 5V: turn on when powered up
- Serial port LEDs: TX on when data is transmitted from Maker Nano; RX on when data is received by Maker Nano
- Programmable piezo buzzer (bottom): can play tone or melody
- Mute switch: mutes the piezo buzzer if pin D8 is used for other purposes
- User programmable button: connected to pin D2 internally, accessible from the user program
- Reset button
- Microcontroller: ATmega328P, 16MHz; 32KB flash, 2KB SRAM, 1KB EEPROM
- I/O: 20 digital I/O, 6 PWM, 8 analog inputs (10-bit; A6 and A7 analog only), 1 UART, 1 SPI, 1 I2C, 2 external interrupts
- Power supply: Vin or USB; onboard 5V regulator
- USB-serial chip: CH340C; CH34X driver
- Dimensions: 45.80 mm × 21.09 mm (1mm longer and 3mm wider than the original Arduino Nano); header rows 15.24 mm apart
- Packing list: 1 x Maker Nano
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Pin header: "Compatible with original Arduino Nano"
- Arduino: program uploaded from PC through the Micro USB port
- Arduino IDE board: Arduino Nano (Cytron tutorial); processor/bootloader option [NOT STATED]
- Same pin arrangement as the original Arduino Nano; compatible with most Arduino Nano daughter boards; breadboard friendly
- Differences from Arduino Nano 3.x: Vin 7 – 30V (Nano 7 – 12V), CH340C instead of FTDI FT232RL, 12 programmable LEDs on D2 – D13, programmable push button on D2, piezo buzzer on D8, 21 × 46 mm
- USB Micro B cable: not included (sold separately)

## Use cases
- Building projects with an Arduino Nano-compatible board ("Simplifying Arduino for Projects")
- Playing a tone or melody on the onboard piezo buzzer
- Reading the onboard user button on D2 from the user program
- Cytron tutorial: [Heart Rate Monitor Using Pulse Sensor and Maker Nano](https://my.cytron.io/tutorial/heart-rate-monitor-using-pulse-sensor-and-maker-nano)
- Cytron tutorial: [Social Distance Alert Wristband Using Arduino (Maker Nano)](https://my.cytron.io/tutorial/social-distance-alert-wristband-using-arduino-maker-nano)
- Cytron tutorial: [Control NeoPixel RGB LED Color Code Using Keypad and Maker Nano](https://my.cytron.io/tutorial/control-neopixel-rgb-led-color-code-using-keypad-and-maker-nano)
- Cytron tutorial: [Maker Nano Heartbeat Monitoring With Mlx30102](https://my.cytron.io/tutorial/maker-nano-heartbeat-monitoring-with-mlx30102)
- Cytron tutorial: [Gas Detector Using The MQ2 Sensor on Maker NANO](https://my.cytron.io/tutorial/gas-detector-using-mq2-sensor-on-maker-nano)

## Known limitations
- DC +5V output is limited to 100 mA and DC +3V3 to 50 mA, both including onboard usage
- Vin minimum is 7.0 V; maximum 30.0 V
- Digital and analog inputs must not exceed 5.0 V
- D8 is shared with the piezo buzzer: use the mute switch when D8 is used for other purposes
- D2 is used by the onboard user button
- A6 and A7 are analog inputs only
- Needs the CH34X USB driver
- The digital IO LEDs on D2 – D13 light when a pin is high; they can only be disabled by cutting the enable-jumper trace

## Positioning (kept apart from specs)
- "Simplifying Arduino for Projects"
- "Love Maker UNO? But it's too big to fit into your project?" — a smaller board that keeps Maker UNO's learning features (LEDs, button, buzzer)

## Price band
RM37.38 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-nano-simplifying-arduino-for-projects

## Datasheet
https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view
