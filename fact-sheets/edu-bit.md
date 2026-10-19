# Product fact sheets

## Product name
EDU:BIT Training & Project Kit for micro:bit

## Aliases
V-EDUBIT, EDUBIT, EDUBIT-NB, EDU:BIT, EDU BIT, EDU-BIT, EDU:BIT Training & Project Kit, EDU:BIT Classroom Pack

## What it is
A micro:bit training and project kit: a board with built-in modules (buzzer, sensors, LEDs, buttons, servo and DC motor ports) plus a guide book of 10+1 coding lessons, game accessories, a servo motor and a DC motor. It works with micro:bit V1 and V2.

## Specs and functions
- Product code: V-EDUBIT (board code EDUBIT; reseller EDUBIT-NB)
- 1x piezo buzzer with audio jack; INT/EXT slide switch selects the onboard buzzer or external speakers/headphones on the jack (guide book)
- 1x sound sensor (micro:bit P1, analog)
- 1x potentiometer (micro:bit P2, analog)
- 1x IR sensor (micro:bit P8, digital)
- 4x programmable RGB LEDs (micro:bit P13)
- 3x big LEDs, traffic light: red P14, yellow P15, green P16
- 2x push buttons (in parallel with micro:bit buttons A and B)
- 3x servo ports and 2x DC motor ports, driven by a dedicated controller and power supply (PIC16F1937 co-processor at I2C address 0x08, Cytron GitHub)
- 1x I2C port (3.3V)
- Indicator LEDs for digital and analog IO pins; each feature and its micro:bit IO pin labelled on the board
- Modules can be broken off the board and reconnected with plug-and-play (Grove) cables
- Works out of the box: lights and melody on button press, no wiring needed
- Dimension: 157.50 mm x 124.50 mm x 19.00 mm
- Power: the supplied USB Y-cable powers EDU:BIT through a barrel plug (and the micro:bit through micro USB) from a computer USB port; power switch must be ON (guide book)
- Power input voltage range: [NOT STATED]
- Motor and servo current limits: [NOT STATED]
- Weight: [NOT STATED]
- Warranty: 12 months
- Packing list (with micro:bit V2): 1x EDU:BIT board, 1x micro:bit V2, 1x step-by-step guide book, 1x USB power and data cable, 2x game maps, 2x game accessories, 7x Grove cables, 1x servo motor, 1x DC motor, 1x pulley wheel, 1x fan blade
- Without micro:bit option: same contents minus the micro:bit
- Classroom Pack: 10 sets, each with micro:bit V2
- Guide book: "Explore STEM & Coding with EDU:BIT" (Cytron, ISBN 978-967-19475-0-0, 4th printing May 2021), 10 chapters + 1 bonus — Hello, World!; Rock, Paper, Scissors (Button Bit); Music (Music Bit); Win, Lose or Draw (Traffic Light Bit); IR Digital Dice / Snakes and Ladders (IR Bit); Tag, You're It (Potentio Bit); Applause (Sound Bit); Let's Take a Spin / Finger Twister (DC motor); Penalty Shoot-Out (servo); Mastermind (RGB Bit); Bonus: Simon Says with LEDs (radio)
- Guide book PDFs: English, Malay, Chinese, Tamil, Thai, Japanese, Hungarian, Italian, French, German, Korean, Spanish

## Interfaces and compatibility
- Works with micro:bit V1 & V2
- micro:bit pins used: P1 sound, P2 potentiometer, P8 IR, P13 RGB LEDs, P14/P15/P16 traffic light, I2C (co-processor 0x08) for servos S1–S3 and motors M1/M2
- Programmed with Microsoft MakeCode (blocks, JavaScript or Python mode) and the EDU:BIT extension pxt-edubit, https://github.com/CytronTechnologies/pxt-edubit (v1.15.0)
- Extension blocks: Sound Bit, Potentio Bit, IR Bit, RGB Bit, Traffic Light Bit, Motors & Servos (motor speed 0–255, servo 0–180°); Music Bit and Button Bit use the built-in Music and Input blocks
- Resource Hub with chapter resources and sample code: http://link.cytron.io/edubit-resource-hub
- Out-of-the-box demo code: https://link.cytron.io/edubit-demo-code
- Grove WiFi 8266 tutorial listed on the product page
- MicroPython library: [NOT STATED]

## Use cases
- Beginner micro:bit kit for STEAM and coding
- 10+1 hands-on coding lessons, each built around a classic childhood game, with a challenge at the end of each chapter
- Training kit that works with no wiring
- Custom projects using the broken-off modules
- Projects with up to 3 servo motors and 2 DC motors while playing music
- AI projects with Teachable Machine (tutorial series ch.1–6: object sorting, face recognition door, gesture-controlled fan, colour-controlled motor, object counter)
- Classroom teaching (Classroom Pack of 10)

## Known limitations
- The default EDU:BIT MakeCode extension is not compatible with Bluetooth (NeoPixel/RGB dependencies); a modified version is provided in the Teachable Machine Chapter 1 tutorial
- P1, P2, P8, P13, P14, P15 and P16 are used by the onboard modules
- Do not use I2C address 0x08 on the I2C port (used by the co-processor)
- Servos and DC motors can only be driven through the co-processor (extension blocks), not directly from micro:bit pins
- The extension resets the micro:bit when the EDU:BIT power is switched on
- RGB LED default brightness in the extension is 25 (of 255)
- The kit without micro:bit does not include a micro:bit board
- Power EDU:BIT with the supplied USB cable as shown in the guide book; other power sources, input voltage range and protection thresholds: [NOT STATED]

## Positioning (kept apart from specs)
- EDU:BIT was 575% funded on Kickstarter on Oct 22, 2020
- Specially designed to encourage kids to explore STEAM and learn coding
- "Cannot control servo motor and play music at the same time on your micro:bit? Servo motor refuses to move correctly? ... EDU:BIT takes care of these issues with its dedicated controller and power supply."
- Name-writing space on the board
- Guide books translated by volunteers into many languages

## Price band
RM156.00–RM2,390.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-edubit-training-and-project-kits-for-microbit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-edubit-training-and-project-kits-for-microbit
