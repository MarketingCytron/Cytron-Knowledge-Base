# Product fact sheets

## Product name
Ikedo Mini Sumo Robot Pro Bundle

## Aliases
KIT-IKEDO-MSUMO-P, Ikedo Mini Sumo Robot Pro Bundle, Ikedo Mini Sumo Robot Pro Kit, Ikedo Mini Sumo Robot Pro, Ikedo Pro Bundle, Ikedo Pro

## What it is
The higher-specification Ikedo mini sumo robot kit: the Maker Mini Sumo Controller, 5 Maker Object opponent sensors, 2 Maker Reflect S edge sensors, a 7.4 V 450 mAh LiPo and a 10 cm x 10 cm black PLA chassis, with 800 RPM 3.1 kg.cm motors, a laser-cut stainless steel shield, a 4" stainless steel razor blade and a copper weight base. It supports auto and manual (RC) mode; the RC transmitter/receiver is sold separately.

## Specs and functions
- Product code: KIT-IKEDO-MSUMO-P
- Size: 10 cm x 10 cm
- Weight: 350 g
- Chassis: black PLA; packing list: 1 x chassis (main), 1 x 3D printed motor bracket
- Controller: Maker Mini Sumo Controller (ATmega328P; USB-serial CH340C per the product page)
- Battery: 1 x 7.4V 450mAh LiPo, JST LiPo wire extension
- Opponent sensors: 5 x Maker Object; product page: "range 50cm adjustable"
- Edge sensors: 2 x Maker Reflect S (product page links "Datasheet for Edge Sensor (MAKER-REFLECT-S)")
- Motors: 2 x 800RPM 6V DC micro metal gearmotor; "6V DC motors (800rpm, 3.1kg.cm)"
- Wheels: 2 x silicon wheels 32x22mm; blue from July 2025
- Armour: 1 x laser-cut stainless steel shield, 1 x 4" stainless steel razor blade, 1 x copper weight base
- Control: auto and manual mode; RC transmitter/receiver sold separately; on-board start button (controller START, active low)
- USB cable: free, included from 25 Aug 2024
- Packing list (truncated on the product page): 1 x Maker Mini Sumo Controller, 5 x Maker Object, 2 x Maker Reflect S, 2 x 800RPM 6V DC micro metal gearmotor, 1 x 3D printed motor bracket, 2 x silicon wheels 32x22mm, 1 x 7.4V 450mAh LiPo, 1 x chassis (main), 1 x laser-cut stainless steel shield, 1 x 4" stainless steel razor blade, 1 x copper weight base, JST LiPo wire extension, 2561 3-way connector extension wire, ...
- Not included: RC transmitter/receiver; no LiPo charger in the visible packing list
- Differences from the Ikedo Mini Sumo Robot V2 (KIT-IKEDO-MSV2-S): 800 RPM 3.1 kg.cm motors instead of 600 RPM "0.065kg.cm"; 350 g instead of ~200 g; adds steel shield, 4" razor blade and copper weight base; RM693.00 instead of RM418.95
- Warranty: "NO warranty for Sumo Robot."

## Interfaces and compatibility
- Controller: see the Maker Mini Sumo Controller fact sheet (MAKER-MSUMO); opponent sensor Maker Object (MAKER-OBJECT); edge sensor Maker Reflect S (MAKER-REFLECT-S)
- Software: Arduino IDE with the Cytron Maker Sumo Library v1.2.3 (architectures=avr, depends=Servo), linked from the product page; examples AutoSumo, RcSumo, CalibrateEdgeSensors, TestInputs, TestOutputs
- RC (manual) mode: 2-channel RC receiver, forward/reverse channel to GPIO1 and left/right channel to GPIO2 (RcSumo example); robot stops when no pulse is received
- Battery wiring: VB+ = red, VB- = black at the controller's Battery Terminal (shared with the V2 Getting Started guide); Cytron's Pro guide uses a 2-cell LiPo
- Edge sensor wiring: S/OUT = white, +/VCC = red, -/GND = black, using the 2561 3-way wire cut in two (shared with the V2 Getting Started guide)
- Motor wiring: Cytron's Pro guide wires red to MRA and black to MRB, then checks direction with the motor test buttons and swaps if reversed
- Programming: Micro USB-B on the controller; Windows uses the WCH CH341SER driver (CH340 COM port)
- Cytron tutorials linked from the product page include SumoRobot1KG

## Use cases
- Competition mini sumo robot builds ("Pro" bundle with shield, blade and weight base)
- Autonomous sumo robot (auto mode, AutoSumo example)
- Radio-controlled sumo robot (manual mode with a separately bought RC transmitter/receiver)
- One robot entering both RC and autonomous categories (RC receiver on GPIO1/GPIO2 leaves the sensor ports free)

## Known limitations
- No warranty for the Sumo Robot
- RC transmitter/receiver not included; LiPo charger not in the visible packing list
- Product page specifications and packing list are truncated; top cover, screws and screwdrivers are not confirmed
- No Pro-specific assembly document; the Ikedo Bot V2 Getting Started Instruction covers the V2 Starter only
- Controller limits apply: 3.0 A continuous / 6.0 A peak (< 5 s) per motor channel; motors over 3 A are not covered by the controller's warranty (see MAKER-MSUMO)
- 800 RPM motor current rating: [NOT STATED]
- Whether 350 g includes battery, shield, blade and copper base: [NOT STATED]
- Pre-loaded code and Arduino board selection: [NOT STATED]
- Competition weight class on the kit page: [NOT STATED]

## Positioning (kept apart from specs)
- "Pro" bundle of the Ikedo mini sumo line, with armour and weight base added over the V2 Starter
- Controller positioned by Cytron for beginners through professional builders in international Sumo robot competitions (Maker Mini Sumo product page)

## Price band
- RM693.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ikedo-mini-sumo-robot-pro-kit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-ikedo-mini-sumo-robot-pro-kit
