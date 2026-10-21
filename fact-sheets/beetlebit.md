# Product fact sheets

## Product name
BEETLE:BIT Gripper Robot Car Kit for micro:bit

## Aliases
BEETLE:BIT, BEETLEBIT, BEETLE BIT, V-BEETLEBIT, BeetleBit, BEETLE:BIT Gripper Robot Car Kit, BEETLE:BIT Gripper Robot

## What it is
An educational gripper robot car kit for the BBC micro:bit, built on the REKA:BIT expansion board with two TT motors, a front servo gripper, an ultrasonic sensor and a Maker Line sensor. It comes with a 7-chapter booklet, a printed line track and an online Resource Hub with chapter code.

## Specs and functions
- Product code: V-BEETLEBIT
- Purchase options: with micro:bit / without micro:bit / Accessories Kit only, each with battery or without battery
- Microcontroller: BBC micro:bit (V2 in the "with micro:bit" option)
- Controller board: REKA:BIT (see the REKA:BIT fact sheet; not re-documented here)
- Motors: 2x DC gear motors with wheels (2x TT motor with 15cm wires and wheel kit)
- Gripper: non-copper PCB gripper (Robo Grip PCB with accessories, called "Robo Grip Mini" on the Resource Hub) driven by 1x TS90A micro servo
- Sensors: infrared line tracking (Maker Line), ultrasonic obstacle avoidance (Ultrasonic 3V3)
- Power: 4x AA batteries in a 4xAA battery holder with DC jack
- Control: Autonomous Mode or micro:bit RC Mode (additional micro:bit not included)
- Chassis: non-copper PCB (2x Robo Base, PCB only); no soldering
- Programming: MakeCode
- Packing list (with micro:bit, with battery): 1x BBC micro:bit V2, 1x REKA:BIT, 1x Dual Output Cable USB-A to 2.1mm DC barrel & Micro USB, 1x 4xAA battery holder with DC jack, 1x Ultrasonic 3V3, 1x Maker Line, 4x AA battery, 2x TT motor with 15cm wires and wheel kit, 1x TS90A micro servo, 1x BEETLE:BIT Booklet, 1x BEETLE:BIT Track, 1x Accessories Kit
- Accessories Kit: bracket for ultrasonic HC-SR04, W420 steel ball castor, 2x TT motor bracket, 2x Robo Base (PCB only), 3x Grove 4-pin buckled to female cable, M3 PCB stands 40/20/10/5mm, 14x M3 nut, 14x M3x6 screw, Velcro set, 4x M3x10 bolt, 1x Robo Grip PCB with accessories, 1x ping pong ball
- Booklet: "BEETLE:BIT — Build. Code. Move. Grab." Quick Start Guide (Cytron Education Team, 2026, 96 pages, works with micro:bit V1 & V2), 7 chapters plus a Setup Guide and Bonus activities
- Box contents (booklet): battery holder & USB cable, 2x Robo Base, REKA:BIT, 3x Grove cables, ultrasonic bracket, servo motor, ultrasonic sensor, Maker Line sensor, 2x DC motor bracket, 2x DC motor & wheels, M2 & M3 screwdriver, Velcro, Robo Grip Mini, 4x AA batteries, cross wrench, castor wheel, M3 PCB stands (40 mm x5, 20 mm x8, 10 mm x4, 5 mm x4), M3 bolts, nuts, lock nuts and washers, M2 bolts and nuts
- Chapters: Setup Guide (build BEETLE:BIT); 1 The Beetle's Brain (micro:bit Basics); 2 How the Beetle Moves (TT Motors); 3 The Beetle's Claw (Servo Gripper); 4 The Beetle's Eyes (Ultrasonic Sensor); 5 The Beetle Senses (Line Following); 6 Teaching the Beetle to Decide; 7 Coordinated Actions (Line + Grab); Bonus 1 Control BeetleBit Using a Controller; Bonus 2 BEETLE:BIT Input–Output Challenge
- Gripper angles in Cytron's chapter code: Chapter 3 toggles 0 and 180; Chapters 6 and 7 use 120 = open, 0 = closed, then disable the servo after a pause
- Drive speeds in Cytron's chapter code: 128 for move/turn; obstacle thresholds (booklet Ch4): under 20 cm = slow down, under 10 cm = stop; Ch4 challenge keeps a 15 cm distance
- Bonus 1 RC mode: micro:bit radio group 1; hold A = forward, hold B = backward, tilt = turn, shake = open/close gripper, upright = stop; needs an extra micro:bit V2 (V2 recommended for both to avoid latency)
- Warranty: 12 months (1 year for manufacturing defects; wear and tear, misuse, abuse or improper maintenance not covered; troubleshooting, repair and testing take 7 working days from receipt)
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Age range: [NOT STATED]
- Four kit options: with or without micro:bit V2, each with or without 4 AA batteries (product page)
- Accessories Kit: ultrasonic bracket, castor, 2 TT motor brackets, 2 Robo Base PCBs, 3 Grove-to-female cables, M3 stands/nuts/screws/bolts, Velcro set, Robo Grip PCB, ping pong ball (product page)
- RC mode needs a second micro:bit (not included) (product page)

## Interfaces and compatibility
- Motor 1: black → M1A, red → M1B (left motor in pxt-zoombit); Motor 2: red → M2A, black → M2B (right motor)
- Gripper servo: REKA:BIT servo port S1 (orange signal, red +, brown −)
- Maker Line sensor: Grove port P1:P9 (yellow AN = P1, white CAL = P9, red Vcc, black GND); on micro:bit V1 leave the white CAL wire disconnected
- Ultrasonic sensor: Grove port P2:P12 (yellow trigger = P2, white echo = P12, red Vcc, black GND)
- RGB LEDs on REKA:BIT: P8 (not used by the chapter code)
- Motors and servo are driven over I2C by the REKA:BIT co-processor (address 0x08)
- MakeCode extension: ZOOMBIT (pxt-zoombit v0.1.1 (https://github.com/cytrontechnologies/pxt-zoombit), which loads pxt-rekabit), as the booklet says; the product page names the extension as pxt-rekabit "BEETLE:BIT (ZOOM:BIT) Extension"
- MakeCode blocks, JavaScript and Python modes; MakeCode Offline App available
- micro:bit V2 is included in the "with micro:bit" option; RC mode needs a second micro:bit
- Related Cytron tutorials: colour detection bot using HuskyLens; line following robot car using motionbit; colour detection robot using TCS3200; Chapter 1: Setting Up Beetle:Bit with Huskylens 2
- MicroPython library: [NOT STATED]

## Use cases
- Display text and animation on the LED matrix and download a program
- Control BEETLE:BIT to move around with the TT motors
- Open and close the gripper with the servo
- Detect obstacles using an ultrasonic sensor
- Follow a line using the Maker Line sensor
- Make decisions and perform a complete task on its own
- Perform several actions in sequence (line following plus grabbing)
- Control BeetleBit using a controller (second micro:bit over radio)
- Input–output challenge
- Stepping stone for learners who have mastered ZOOM:BIT, Pikabot, BocoBot or OjanBot
- Cytron tutorial: [Chapter 1: Setting Up Beetle:Bit with Huskylens 2](https://my.cytron.io/tutorial/chapter-1-setting-up-beetlebit-with-huskylens-2)

## Known limitations
- The micro:bit is not included in the "without micro:bit" and "Accessories Kit only" options
- RC mode needs an additional micro:bit, which is not included
- Batteries are not included in the "without battery" options
- No kit datasheet; the booklet is the main source
- Do not force the servo gears by hand; attach Robo Grip Mini Part 3 to the first horn hole for better grip
- Two TT motors can run at different speeds, so the robot may drift; low battery and soft floors slow it down
- The product page Accessories Kit list gives fewer stands, nuts and screws than the booklet box list
- Pins used by the kit: P1 (Maker Line), P2 and P12 (ultrasonic), P8 (RGB LEDs), I2C to the REKA:BIT co-processor; servo on S1; motors on M1/M2
- Controller limits apply from REKA:BIT: 3.6–6 V input, 1 A continuous / 1.5 A peak per motor, 300 mA total on Grove +3V3, motor and servo power cut above 7 V
- All Bonus 1 programs use radio group 1, so two kits in the same room interfere unless the group is changed
- Chapter 3 Challenge uses the microphone (micro:bit V2 only)
- Ultrasonic block returns 255 when nothing is detected or the distance is over 255 cm
- No Cytron GitHub extension named "beetlebit" exists; use zoombit
- Battery chemistry, run time, dimensions, weight and age range are not stated

## Positioning (kept apart from specs)
- "Hands-on educational robotics kit"
- "Stepping stone... for those who have mastered ZOOM:BIT, Pikabot, BocoBot, or OjanBot"
- "Mobile manipulator: configurable chassis, dual TT motors, front-mounted servo gripper, ultrasonic distance sensor, line-following sensor"
- Resource Hub: a learning site for beginners in basic robotics covering building, coding and experimenting with a mobile manipulation robot

## Price band
RM99.80–RM326.45 across options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-beetlebit-gripper-robot-car-kit-for-microbit

## Datasheet
https://drive.google.com/file/d/18ZOwcWVUn0xsEVdcUNOMDvZKf5haVmz5/view

## Source type
Website

## Source link
https://beetlebit-hub.cytron.io/
