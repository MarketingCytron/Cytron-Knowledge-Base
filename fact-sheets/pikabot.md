# Product fact sheets

## Product name
PikaBot - Maker UNO Smart Car Kit

## Aliases
V-KIT-PIKABOT, KIT-PIKABOT, PikaBot, Pikabot, PIKABOT, PikaBot Smart Car Kit, Maker UNO Smart Car Kit, PikaBot - Maker UNO Smart Car Kit

## What it is
A DIY two-wheel robot car kit built on the Maker UNO board and the Maker Drive motor driver, with two TT gear motors, two IR line-tracking modules and an HC-SR04 ultrasonic sensor, assembled with jumper wires and powered by 4 AA batteries. It comes with a project booklet in an Arduino IDE (English) or mBlock (Bahasa Melayu) edition.

## Specs and functions
- Product code: V-KIT-PIKABOT (reseller model: KIT-PIKABOT)
- Booklet options: Arduino IDE (English); mBlock (Bahasa Melayu, v1.1)
- Controller: Maker UNO (see Maker UNO fact sheet)
- Motor driver: Maker Drive (see Maker Drive fact sheet)
- Motors: 2x 3-6VDC dual-axis TT gear motor with pre-soldered wires
- Wheels: 2x rubber wheel 63mm x 15mm
- Sensors: 2x IR line tracking module; 1x HC-SR04 ultrasonic
- Power: 4x AA batteries in a 4xAA battery holder; powers controller and motors; panel-mount rocker switch
- Breadboard: 1x mini breadboard 35x42mm; 40-way M-F jumper; 40-way M-M jumper
- Packing list (product page, truncated): 1x Maker UNO, 1x Maker Drive, 2x TT gear motor, 2x rubber wheel, 2x IR line tracking module, 1x HC-SR04 ultrasonic, 4x AA batteries, 1x 4xAA battery holder, 1x mini breadboard, 40-way M-F jumper, 40-way M-M jumper
- No soldering: assembled with jumper wires
- Arduino booklet projects: 1 Let's Move It (3 steps + Rectangle, Circle, Triangle challenges); 2 Oh No! Stop! (2 steps + challenge); 3 Black or White Line? (2 steps + challenge); 4 Music On (2 steps + Super Mario, Baby Shark, Birthday Song challenges)
- mBlock lesson series: 1 Move Around; 2 Detect Object; 3 Line Follow
- Arduino library: Cytron Motor Drivers Library (CytronMotorDriver.h), PWM_PWM mode
- Pin map (Cytron sample code): left motor D11/D10; right motor D9/D3; ultrasonic TRIG D5, ECHO D4; left IR A0, right IR A1 (digital read); start button D2 (on-board, INPUT_PULLUP); buzzer D8 (on-board)
- IR logic in code: LOW = white surface, HIGH = black line
- Ultrasonic distance in code: pulseIn(ECHO, HIGH) x 0.017 cm; lessons stop at 15 cm and avoid at 20 cm
- Warranty: [NOT STATED]
- Box dimension: 127 mm × 55 mm × 190 mm, not including motor shafts and wheels (product page); weight: [NOT STATED]
- Rocker switch = power switch; push button = start button (product page)
- Booklet options: Arduino IDE (English) or mBlock (Bahasa Melayu) (product page)

## Interfaces and compatibility
- Maker UNO: USB Micro-B for programming; no DC jack or Vin pin
- Maker Drive: PWM_PWM control, 2.5–9.5 VDC input, 1 A continuous / 1.5 A peak per channel, 5 V 200 mA output (Maker Drive datasheet)
- Arduino IDE with the Cytron Motor Drivers Library (booklet shows Arduino 1.8.10 and library 1.0.1)
- mBlock 5 (online ide.mblock.cc or offline) with the "PikaBot" extension added from the device panel; upload mode over the COM port
- CH34x USB driver for the Maker UNO (CH341SER shown in the booklet)
- pitches.h must be present as a second tab for the music projects (full file in the Resources doc)

## Use cases
- Learning electronics, microcontrollers, sensors, motors and coding with a mobile robot
- Project 1: move forward, backward, turn; drive a rectangle, circle and triangle
- Project 2: measure distance with the ultrasonic sensor; stop or avoid obstacles
- Project 3: read the IR line sensors; follow a black line; stop at a full black line
- Project 4: play melodies on the Maker UNO buzzer (toneMelody, Super Mario, Baby Shark, Birthday Song)
- Reuse the parts to build new robots from cardboard, cartons, bottles or old toys
- Cytron tutorial: [Program PikaBot Using mBlock](https://my.cytron.io/tutorial/program-pikabot-using-mblock)
- Cytron tutorial: [Control PikaBot Using a Phone Through Bluetooth](https://my.cytron.io/tutorial/control-pikabot-using-a-phone-through-bluetooth)

## Known limitations
- The booklet PDF is image-only; its wiring diagrams were not readable for this sheet
- The product page packing list is truncated in the capture; the full list is not confirmed from Cytron text
- Programs wait for the on-board D2 button before moving; the buzzer needs the D8 slide switch on
- Turn convention in Cytron code: robotMove(-200, 200) = turn left, robotMove(200, -200) = turn right; swapped motor wires reverse this
- The Maker UNO cannot take the battery directly (no DC jack, no Vin)
- The IR modules and HC-SR04 are generic modules, not Cytron Maker Line / Maker Object
- Warranty, weight and age range are not stated

## Positioning (kept apart from specs)
- DIY mobile robot kit; no soldering (jumper wires)
- "Schematics and mounting locations are printed inside the box"
- Programmable in the Arduino IDE or the block-based mBlock environment
- Cytron EDU line-up lists PikaBot beside ZOOM:BIT, Ikedo and EDU PICO; BEETLE:BIT is positioned as the next step after PikaBot

## Price band
RM128.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-pikabot-maker-uno-smart-car-kit

## Datasheet
https://drive.google.com/file/d/1G9rhCY_9ogJN4ufXdAwFmrgbaEHKP3Cp/view

## Source type
Datasheet

## Source link
[NOT STATED]

