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
- Microcontroller: [NOT STATED]
- USB-serial chip and driver: [NOT STATED]
- Dimensions: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Pin header: "Compatible with original Arduino Nano"
- Arduino: program uploaded from PC through the Micro USB port
- Arduino IDE board to select: [NOT STATED]
- Differences from the genuine Arduino Nano: [NOT STATED] (the datasheet's comparison table is an image); stated additions are the D2 – D13 IO LEDs, buzzer with mute switch, user button on D2, power LEDs and IO-LED enable jumper
- Box contents: [NOT STATED]

## Use cases
- Building projects with an Arduino Nano-compatible board ("Simplifying Arduino for Projects")
- Playing a tone or melody on the onboard piezo buzzer
- Reading the onboard user button on D2 from the user program

## Known limitations
- DC +5V output is limited to 100 mA and DC +3V3 to 50 mA, both including onboard usage
- Vin minimum is 7.0 V; maximum 30.0 V
- Digital and analog inputs must not exceed 5.0 V
- D8 is shared with the piezo buzzer: use the mute switch when D8 is used for other purposes
- D2 is used by the onboard user button
- The digital IO LEDs on D2 – D13 light when a pin is high; they can only be disabled by cutting the enable-jumper trace

## Positioning (kept apart from specs)
- "Simplifying Arduino for Projects"

## Price band
RM37.38 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-nano-simplifying-arduino-for-projects

## Datasheet
https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view
