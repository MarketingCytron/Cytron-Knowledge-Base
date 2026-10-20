# Product fact sheets

## Product name
ZOOM:BIT Robot Car Kit for micro:bit

## Aliases
ZOOM:BIT, ZOOMBIT, ZOOM BIT, ZOOM:BIT Robot Car Kit, ZOOM:BIT Robot Car

## What it is
A robot car kit for the BBC micro:bit, built on a REKA:BIT controller board with a line sensor, an ultrasonic sensor, two LED headlights, two DC motors and a servo-driven head. It comes with a printed building and coding guide book and a line following track.

## Specs and functions
- Product code: [NOT STATED]
- Purchase options: ZOOM:BIT with micro:bit V2 included; ZOOM:BIT without micro:bit; ZOOM:BIT Classroom Pack (10x with micro:bit V2 included)
- Controller board: REKA:BIT (with or without micro:bit)
- Kit contents: Zoom Track, REKA:BIT (with or without micro:bit), Maker Line Sensor, Grove Cable x4, Ultrasonic Sensor, LED Module x2, DC Motor & Wheel x2, Screwdriver, Screw & Nut x4, Castor, Double-sided Tape x5, Power & Data Cable, Servo Motor, White Rivet x4, Black Rivet x8, AA Battery x4, Battery Holder; printed guide book
- Guide book: 9 chapters plus a bonus chapter (product page: "10-lesson guide book")
- Battery: AA Battery x4 in a battery holder
- REKA:BIT power input voltage: 3.6 – 6 V (absolute maximum ratings)
- REKA:BIT analog input voltage: 0 – 3.3 V
- REKA:BIT total +3V3 output current (Grove ports): 300 mA max
- DC motor current: 1 A continuous, 1.5 A peak (< 5 seconds)
- DC motor voltage at full speed and servo V+: equal to the power source voltage
- Low voltage LED blinks below 3.6 V; over voltage LED lights above 7 V and power to the servos and DC motors is cut off
- Drive motors: left = M1, right = M2 (REKA:BIT motor channels)
- Motor test buttons on REKA:BIT run a motor at full speed (MxA forward, MxB backward)
- Maker Line sensor: 5 IR sensors (S1–S5) with LED indicators, calibration button, line-colour switch ("DARK" for a black line); read on P1 (analog)
- Ultrasonic sensor: trigger P2, echo P12; MakeCode block returns 1 – 255 cm, 255 if over 255 cm or no echo
- Headlights (LED modules): left P13, right P15
- RGB LEDs: 2 x WS2812B on REKA:BIT, on P8, labelled "0" and "1"
- Head: 180 degree servo motor on a REKA:BIT servo port
- Motors and servos are controlled by the REKA:BIT co-processor over I2C (address 0x08)
- Power switch: slide OFF then ON to reset
- Warranty: 12 months
- Options: with micro:bit V2, without micro:bit, Classroom Pack (10 kits), AI version with HuskyLens (with or without micro:bit V2) (product page)
- Packing (V2 kit): micro:bit V2, REKA:BIT, USB power/data cable, 9+1 lesson guide book, Zoom track, Maker Line, ultrasonic sensor, 2 × 10 mm LED modules, 2 × DC motors with wheels, micro servo, 4 Grove-to-female cables, 4xAA holder with DC plug, 4 AA batteries, castor, screwdriver, rivets, double-sided tape (product page)
- Ultrasonic sensor linked on the packing list: Cytron 3V-5.5V SR04P (HC-SR04P) module (product page)
- AI version adds a HuskyLens and a Grove-to-Gravity cable; rechargeable AA cells advised (product page)

## Interfaces and compatibility
- micro:bit V1 and V2; V1 has no built-in speaker, so sound needs a Grove buzzer on Port P0:P1
- Sound expression and built-in speaker blocks are for micro:bit V2 only
- I2C port: guide book suggests adding a Grove OLED Display
- MakeCode extension: zoombit — https://github.com/cytrontechnologies/pxt-zoombit (search "zoombit" under Extensions)
- The zoombit extension loads the REKA:BIT extension (pxt-rekabit), whose blocks appear in the REKA:BIT category
- MakeCode Block, JavaScript and Python modes
- ZOOM:BIT blocks: headlights (set / toggle), move, turn, set motors speed (-255 to 255), brake, line detected on (far left / left / center / right / far right / all / none), line position (-100 to 100), ultrasonic distance (cm)
- WebUSB download needs the new Edge or Chrome browser and the latest micro:bit firmware
- Quick Start Guide in 5 languages

## Use cases
- Display text and animation
- Play simple melodies
- When dark, turn on headlights
- Move & turn on command
- Signal using RGB LEDs
- Control head movement/angle
- Detect and avoid obstacles
- Follow the line & stay on track
- Change from one mode to another
- Remote control (bonus chapter)
- ZOOM:BIT with HuskyLens (Cytron video content and workshops)

## Known limitations
- The micro:bit is not included in the "ZOOM:BIT without micro:bit" option
- micro:bit V1 has no built-in speaker; a Grove buzzer is needed for sound
- Pins used by the kit: P1 (Maker Line), P2 and P12 (ultrasonic), P13 and P15 (headlights), P8 (RGB LEDs), plus the I2C bus to the REKA:BIT co-processor
- Power input values are absolute maximum ratings: 3.6 – 6 V; over 7 V cuts power to the servos and DC motors
- DC motor current: 1 A continuous, 1.5 A peak for under 5 seconds
- Grove +3V3 total: 300 mA max
- Motor direction depends on the motor connection; if the wheels don't spin in the direction of the red arrows, correct the DC motor connections
- Motor test buttons run the motor at full speed without any code
- The Maker Line sensor needs calibration before line following, and again if the sensor height, the line or the background colour changes
- Ultrasonic block returns 255 when nothing is detected or the distance is over 255 cm
- The guide book does not state the battery voltage or chemistry
- The guide book does not mention Python; Python is through MakeCode's Python mode
- Assembly: wires face inwards with the notch facing outwards; clamp the exposed wire lead, not the insulator

## Positioning (kept apart from specs)
- "Looking for a solution to introduce robotics and coding to your kids?"
- "This kit comes with a step-by-step building guide written in simple language and a generous dose of graphics to help young learners to follow along."
- "You can easily program ZOOM:BIT using open-sourced Microsoft MakeCode Editor."
- Classroom Pack: "Save more with this Classroom Pack!"

## Price band
From RM262.50 (default option; Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-zoombit-robot-car-kit-for-microbit

## Datasheet
https://static.cytron.io/download/ZOOMBIT/ZOOMBIT-Quick-Start-Guide-Book-EN-v1.1-2022.pdf

## Source type
Datasheet

## Source link
https://static.cytron.io/download/ZOOMBIT/ZOOMBIT-Quick-Start-Guide-Book-EN-v1.1-2022.pdf
