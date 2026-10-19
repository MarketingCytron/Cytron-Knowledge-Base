# Product fact sheets

## Product name
Ikedo Mini Sumo Robot V2

## Aliases
KIT-IKEDO-MSV2-S, Ikedo Mini Sumo Robot V2, Ikedo Mini Sumo Robot V2 Starter, Ikedo Mini Sumo Robot Starter Kit V2, Ikedo Bot Starter Kit V2, Ikedo Bot V2, Ikedo V2

## What it is
A ready-to-assemble mini sumo robot kit built around the Maker Mini Sumo Controller, with 5 Maker Object opponent sensors, 2 edge sensors, two 6 V micro metal gearmotors, a 7.4 V 450 mAh LiPo and a black 3D-printed PLA chassis. It is the upgraded version of the Ikedo Mini Sumo Robot Starter Kit, with an upgraded chassis design and more sensors.

## Specs and functions
- Product code: KIT-IKEDO-MSV2-S
- Size: 10 cm x 10 cm (product page)
- Weight: ~200 g (product page)
- Chassis: black PLA, 3D printed; parts: Main chassis, Top Cover, Motor Bracket
- Controller: Maker Mini Sumo Controller ("Arduino Nano/Uno compatible (ATmega328P)", USB-serial CH340C per the product page)
- Battery: 1 x 7.4V 450mAh LiPo, connected with a JST LiPo battery wire extension (VB+ = red, VB- = black)
- Opponent sensors: 5 x Maker Object Sensor; product page: "range 50cm adjustable"
- Edge sensors: 2 x, mounted underneath; product page: "Maker Reflect S"; Getting Started guide: "Maker Reflectance Sensor" (linked to the MAKER-REFLECT page)
- Motors: 2 x 600RPM 6V DC Micro Metal Gearmotor; product page: "6V DC motors (600rpm, 0.065kg.cm)"
- Wheels: 2 x High Grade Silicon Wheels Set (32mm x 22mm); blue from 17 Jul 2025
- Control: auto and manual control mode; RC transmitter/receiver sold separately
- Programming: through the Micro USB-B port on the right side of the assembled robot
- Getting Started components list: 1 x Maker Mini Sumo Controller, 5 x Maker Object Sensor (opponent), 2 x Maker Reflectance Sensor (edge), 2 x 600RPM 6V DC Micro Metal Gearmotor, 2 x High Grade Silicon Wheels Set (32mm x 22mm), 1 x 7.4V 450mAh LiPo Battery, 1 x Mini Sumo Robot Chassis (Top Cover), 1 x Mini Sumo Robot Chassis (Main), 1 x Mini Sumo Robot Chassis (Motor Bracket), 1 x JST LiPo Battery Wire Extension, 1 x 2561 3Ways Connector Extension Wire, 4 x M3x6 Self-Tapping Screw (Black), 6 x M2.5x20 Bolt, 1 x Tiny Phillips Screwdriver (3mm), 1 x Tiny Flat Head Screwdriver (2mm), 1 x USB Cable (FREE)
- Product page packing list (truncated on the page): 1 x Maker Mini Sumo Controller, 5 x Maker Object Sensor (opponent), 2 x Maker Reflect S (edge), 2 x 600RPM 6V DC micro metal gearmotor, 2 x silicon wheels 32mm x 22mm, 1 x 7.4V 450mAh LiPo, 3D printed parts (chassis, top cover, motor bracket), JST LiPo battery wire extension, ...
- Not included: RC transmitter/receiver; no LiPo charger in either packing list
- Assembly (Getting Started guide): edge sensor wires S = white, + = red, - = black (sensor side OUT = white, VCC = red, GND = black) to the "Front Left and Front Right" edge terminals; edge sensors fixed with 2 x M3x6 self-tapping screws; controller fixed with 2 x M3x6 self-tapping screws; motor bracket with 4 x M3x20 bolts, leaving a 1 mm gap; left motor MLA = red, MLB = black; right motor MRA = black, MRB = red; top cover with 2 x M2.5x20 bolts
- Warranty: "There is NO warranty for Sumo Robot."
- Age/syllabus: Getting Started guide says "suitable for primary and secondary school"

## Interfaces and compatibility
- Controller: see the Maker Mini Sumo Controller fact sheet (MAKER-MSUMO)
- Opponent sensor: Maker Object (MAKER-OBJECT); edge sensor: Maker Reflect S (product page) / Maker Reflectance Sensor (Getting Started guide)
- Software: Arduino IDE with the Cytron Maker Sumo Library v1.2.3 (architectures=avr, depends=Servo); examples AutoSumo, RcSumo, CalibrateEdgeSensors, TestInputs, TestOutputs
- RC (manual) mode: 2-channel RC receiver, forward/reverse channel to GPIO1 and left/right channel to GPIO2 (RcSumo example); invert the channel in the transmitter settings if the direction is reversed
- Start: onboard START button on the controller (AutoSumo waits for press-and-release; pressing START again stops the motors)
- Cytron tutorials linked from the product page: Maker Mini Sumo with Bluetooth controller; with PS2 controller; RC sumo using Maker Mini Sumo Controller
- Sibling: Ikedo Mini Sumo Robot Pro Bundle (KIT-IKEDO-MSUMO-P); predecessor: Ikedo Mini Sumo Robot Starter Kit

## Use cases
- Getting started in Sumo Robot competitions (primary and secondary school students)
- Learning robotics programming and computational skills
- Autonomous sumo robot (auto mode, AutoSumo example)
- Radio-controlled sumo robot (manual mode with a separately bought RC transmitter/receiver)

## Known limitations
- No warranty for the Sumo Robot
- RC transmitter/receiver not included; LiPo charger not listed in the kit
- Kit must be assembled; the guide says sliding the controller into the chassis "might be a little tricky"
- Motor bracket bolts must leave a 1 mm gap or "the body may bend"
- Edge sensor name differs between the product page (Maker Reflect S) and the Getting Started guide (Maker Reflectance Sensor)
- Getting Started guide lists 5 Maker Object sensors but one assembly step says "4x"
- Getting Started guide bolt sizes are inconsistent (6 x M2.5x20 in the list; 4 x M3x20 + 2 x M2.5x20 in the steps)
- Controller limits apply: 3.0 A continuous / 6.0 A peak per motor channel, Vin 7.0-18.0 V (see MAKER-MSUMO)
- Pre-loaded code: [NOT STATED]
- Arduino board selection: [NOT STATED]
- Competition weight class on the kit page: [NOT STATED]

## Positioning (kept apart from specs)
- "very beginner-friendly, and suitable for primary and secondary school"
- "a reliable choice for your kids to get started in Sumo Robot Competitions"
- Developed with the team manager of Ikedo Kogeki to "bring down the barrier for students who want to learn how to build a Sumo Robot"

## Price band
- RM418.95 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ikedo-mini-sumo-robot-v2-starter

## Datasheet
https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit
