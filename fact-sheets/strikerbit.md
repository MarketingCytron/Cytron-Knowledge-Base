# Product fact sheets

## Product name
STRIKER:BIT Soccer Competition Kit

## Aliases
STRIKER:BIT, STRIKERBIT, STRIKER BIT, V-STRIKERBIT, StrikerBit, STRIKER:BIT Soccer Kit, PM-GAME-STRIKER

## What it is
A classroom robot-soccer competition kit for the BBC micro:bit: four 2-wheel-drive robots built on Robobase Mini PCB chassis with a MOTION:BIT, a servo shooter and Joystick:bit remote control, plus a game field, barrier, goal posts, props and scoring sheets. A Basic Kit option contains one robot set.

## Specs and functions
- Product code: V-STRIKERBIT (scoring sheet game code: PM-GAME-STRIKER)
- Purchase options: Complete Kit / Basic Kit, each with battery or without battery
- Microcontroller: BBC micro:bit; booklet: works with micro:bit V1 & V2; kit ships micro:bit Junior Kit V2; 2 micro:bits per robot set (robot + Joystick:bit)
- Controller board: MOTION:BIT (see the MOTION:BIT fact sheet; not re-documented here)
- Motors: 2x DC gear motors with wheels per robot
- Shooter mechanism: non-copper PCB + 3D printed part with servo (Robo Grip Mini Basic Bundle; 8x 3D printed grippers in the Complete Kit)
- Power: 1x 3.7V 2200mAh 18650 Li-Ion with button top per robot
- Control: micro:bit Joystick:bit (Joystick:bit V2 Kit)
- Chassis: non-copper PCB (Robobase Mini kit for 2WD Robot); no soldering
- Programming: MakeCode
- Learning guide: STRIKER:BIT booklet (Cytron Education Team, June 2026, 100 pages): Setup Guide; Ch1 micro:bit Basics; Ch2 Team Colour Selection (RGB LED); Ch3 Basic Movement (DC Motor); Ch4 Ball Shooter (Servo Motor); Ch5 Remote Control (Joystick:bit); Ch6 Combination of Servo, Motor & Joystick; Ch7 Game Play Guide
- Packing list (Complete Kit, with batteries): 4x Robo Grip Mini Basic Bundle, 4x Robobase Mini kit for 2WD Robot, 4x micro:bit Junior Kit (V2), 4x micro servos, 4x motion:bit, 4x USB Micro B cables, 8x 3D printed grippers, 4x ping pong balls, 4x STRIKER:BIT booklet, 4x Joystick:bit V2 Kit, Velcro sets, whistle, 12x 3/4" PVC conduit pipe (34 cm), 4x elbow joints, 8x sockets, 2x goal post stickers, yellow card, red card, gameplay instruction & scoring sheet, 2x pizza box packing 315x220x70mm (goal post), gamefield map, 4x AAA battery sets, 4x 18650 battery
- Box contents per robot set (booklet): Robo Base Mini, Joystick:bit V2 Kit, 2x micro:bit, LiPo battery, Robo Grip Mini, 4xAAA battery pack, servo motor, USB Micro B cable, 3D printed shooter, MOTION:BIT, 2x TT motor bracket, 16x M3x6mm screw + 16x M3 nut, 2x TT motor with 15 cm wires and wheel, W420 steel ball castor, 4x M3 PCB stand 10 mm, 4x PCB stand 25 mm, ping pong ball, printed booklet
- Game rules (booklet Ch7): designed for 4 players; 2 halves of 2 minutes with a 1-minute halftime; no goal directly from a kickoff; yellow card for an intentional collision outside the ball-contention area; red card (robot removed) for serious damage, field damage or a second yellow; one 1-minute timeout per team
- Scoring sheet ("STRIKER:BIT SOCCER MATCH SCORE SHEET", 11 June 2026): fields for Competition / Event / Round, Date, Team A and Team B names; goals ticked per goal; yellow cards max 2 per robot; red cards max 2 per team; final score = total number of goals; signatures of Team A captain, Team B captain and Head of Referee
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Field: game field map inside a PVC barrier of 12 × 22 mm pipes (34 cm) with 8 sockets and 4 elbows; size in cm [NOT STATED]
- Age range: [NOT STATED]

## Interfaces and compatibility
- Robot: micro:bit on MOTION:BIT; 2 DC motors on MOTION:BIT motor terminals; 1 micro servo on a MOTION:BIT servo port
- Wiring (booklet): right motor M1 (red → M1A, black → M1B); left motor M3 (black → M3A, red → M3B); shooter servo on S1 (orange signal, red +, brown −)
- Remote: Joystick:bit V2 Kit with its own micro:bit; stick X/Y on P1/P2, buttons C/D/E/F on P12–P15, 2 × AAA cells
- Radio: match code sends x, y and buttons (b = 0/1/2/4/8) every 20 ms; robot on group 0; Joystick:bit channel changed with A/B and saved with A+B; each robot/remote pair needs its own group
- Robot battery: 18650 3.7V 2200mAh button top in the MOTION:BIT holder
- Controller batteries: 4 × PKCELL AAA battery sets, one per Joystick:bit V2 (Complete Kit with batteries)
- MakeCode; extensions motionbit (robot) and joystickbit (remote)
- Chapter code printed as MakeCode blocks in the booklet
- MicroPython library: [NOT STATED]

## Use cases
- Classroom-scale robot soccer competition ("4 Robots in One Package")
- Build and program a 2WD micro:bit soccer robot with a servo shooter
- Remote-control a robot with a micro:bit Joystick:bit
- Run and score matches with the game field, goal posts, cards, whistle and official score sheets

## Known limitations
- "without battery" options ship without the 18650 cells and the AAA sets; the robot needs a 3.7V button-top 18650
- Each robot set needs 2 micro:bits (booklet), so 4 robots need 8; the product page lists only 4x micro:bit Junior Kit (V2) for the Complete Kit
- The booklet's assembly steps use 40 mm and 20 mm stands that are not in its box list (10 mm and 25 mm)
- Shooter servo angles need tuning per robot (booklet: 60° close / 150° open in Ch4; 100° start, 160° open, 0° shoot in Ch6)
- Card limits: max 2 yellow cards per robot, max 2 red cards per team (score sheet)
- Controller limits apply from MOTION:BIT: 3.6–6 V input, 1 A continuous / 1.5 A peak motor current, 5 V output 300 mA, 3V3 output 200 mA
- Joystick:bit V2 is not a Cytron product; its details are not stated by Cytron sources
- Field size in cm, robot dimensions, weight and age range are not stated

## Positioning (kept apart from specs)
- "Classroom-scale soccer competition kit"
- "4 Robots in One Package"
- "4-step workflow"
- "7-chapter learning guidebook"
- Booklet tagline: "Build. Code. Move. SHOOT"

## Price band
RM370.00–RM1,675.65 across the options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-strikerbit-soccer-competition-kit

## Datasheet
https://drive.google.com/file/d/12FMdIQBJSj9FZLkH8i9N7iAjfZcL4TMG/view

## Source type
Website

## Source link
https://my.cytron.io/p-strikerbit-soccer-competition-kit
