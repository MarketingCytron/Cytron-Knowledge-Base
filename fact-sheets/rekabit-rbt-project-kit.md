# Product fact sheets

## Product name
REKA:BIT RBT Project Kit

## Aliases
REKA:BIT RBT Project Kit, REKA:BIT RBT Project Kits, REKABIT RBT Project Kit, REKA:BIT RBT Project Bundle, RBT Project Kit, Kit Projek RBT REKA:BIT, V-KIT-REKABIT-RBT, KIT-REKABIT-RBT, KIT-REKABIT-RBT-NB

## What it is
A micro:bit project kit for the Malaysian RBT Year 5 and Year 6 syllabus, built on the REKA:BIT expansion board with a servo, RGB stick, two Big LED modules, a Maker Soil Moisture Sensor, a submersible water pump, an ultrasonic sensor and two DC motors with wheels. It comes with a printed Quick Start Guide covering 5 projects and 7 components, programmed in MakeCode with the REKA:BIT RBT Project Kit extension.

## Specs and functions
- Product code: V-KIT-REKABIT-RBT (product page); kit codes KIT-REKABIT-RBT (with micro:bit V2) and KIT-REKABIT-RBT-NB (without micro:bit)
- Purchase options: with micro:bit V2 included; without micro:bit
- Controller board: REKA:BIT (see the REKA:BIT entry for board specs)
- Kit contents (with micro:bit): 1x micro:bit v2, 1x REKA:BIT expansion board, 1x USB power and data cable, 1x quick start guide book, 1x Maker Soil Moisture Sensor, 1x RGB LED Stick, 1x Ultrasonic sensor, 2x 10mm LED module, 2x DC motor with wheel, 1x Micro servo motor, 1x Submersible Water Pump, 4x Grove to female header cable, 1x 4xAA battery holder with DC plug, 4x AA battery, 1x Castor, 1x Mini screwdriver, double-sided tapes
- Without-micro:bit option: same contents minus the micro:bit
- Guide book list: REKA:BIT (with or without micro:bit), micro servo motor, RGB board, soil moisture sensor, Big LED module x2, water pump, ultrasonic sensor, USB cable (power & data), Grove cable x4, AA battery x4, battery holder, ball caster, DC motor with wheels x2, mini screwdriver, adhesive tape x5
- Guide book: Quick Start Guide, 5 projects + 7 components; softcopies in English, Malay, Chinese (Spanish on the resource hub)
- Projects: 1 Boom Barrier Gate; 2 Interactive Robot; 3 Auto Plant Watering Robot (two code versions, 3a and 3b); 4 Coin-Eating Robot; 5 Mobile Robot Car
- RGB stick: 8 LEDs labelled 0 to 7; brightness 0 to 255
- Servo: channels S1 to S4; angle 0 to 180 degrees; disable-servo block stops jitter
- Water pump: motor channel M1 or M2; speed 0 to 255; works in either direction
- DC motor: channel M1 or M2; speed 0 to 255 (relative value)
- Ultrasonic block: 1 to 300 cm; returns 300 when out of range or no echo
- Soil moisture block: 0 to 1023; reading rises as the soil dries
- Battery: 4x AA in a battery holder with DC plug
- Power switch: slide OFF then ON to restart
- Age: 10+; Syllabus: RBT Y5&Y6; Platform: micro:bit
- Warranty: 12 months (manufacturing defects; wear and tear and misuse excluded)
- Prices are subject to SST from April 2026, calculated at checkout (product page)

## Interfaces and compatibility
- MakeCode extension: pxt-rekabit-rbt-project-kit (search "rekabit rbt project") — https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit ; it loads the REKA:BIT extension (pxt-rekabit) with it
- Block categories: RGB Stick, Big LED, Soil Moisture, Ultrasonic (plus REKA:BIT motor and servo blocks)
- RGB stick and Big LED pin choices: P0, P1, P2, P13, P15 (README examples: RGB stick P0, Big LED P13)
- Soil moisture pin choices: P0, P1, P2 (README example P2; Project 3 uses port P2:P12)
- Ultrasonic Trig/Echo pairs: P0/P1, P1/P9, P2/P12, P13/P14, P15/P16 (README example Trig P2, Echo P12)
- Water pump: MOTOR terminal (Project 3: motor terminal 2)
- Mobile Robot Car: left wheel MOTOR 1, right wheel MOTOR 2
- Servo: REKA:BIT servo terminal S1 to S4 (wire labels s = signal, +, -)
- micro:bit V1 and V2 (V1 has no built-in buzzer; add a Grove Buzzer module)
- MakeCode Blocks, JavaScript and Python modes; MakeCode Offline App supported
- WebUSB download needs the latest Edge or Chrome; otherwise drag the .hex file to the MICROBIT drive
- Resource hub: https://rekabit-rbt-hub.cytron.io/ (project videos, sample code, printable A4 templates)

## Use cases
- Boom Barrier Gate (servo + RGB stick)
- Interactive Robot (two Big LEDs + servo)
- Auto Plant Watering Robot (soil moisture sensor + water pump)
- Coin-Eating Robot (servo + ultrasonic sensor)
- Mobile Robot Car (two DC motors, ultrasonic sensor, LED headlights, RGB stick)
- RBT Year 5 and Year 6 classroom projects

## Known limitations
- The micro:bit is not included in the "without micro:bit" option
- micro:bit V1 has no built-in piezo buzzer; a Grove Buzzer module is needed for sound
- The pin set in a block must match the REKA:BIT port the module is plugged into
- RGB Stick and Ultrasonic blocks need their init block at the start of every program
- Ultrasonic block returns 300 when nothing is detected
- The soil moisture threshold (README example 550) is an example, not a calibrated value
- Disable an unused servo to prevent jitter
- The pump and DC motor pages in the guide carry a warning symbol
- All electrical limits are the REKA:BIT board's (3.6 to 6 V input; 1 A continuous / 1.5 A peak per motor; 300 mA Grove 3V3; over 7 V cuts motor and servo power)
- Cardboard, hot glue, Blu Tack, plastic container and steel hanger used in the projects are not included
- New MakeCode extensions may need an internet connection to compile even in the offline app
- The guide's per-project wiring is shown in diagrams; port labels for the RGB stick, Big LEDs, ultrasonic sensor and servo in each project are not stated in text

## Positioning (kept apart from specs)
- "with the aim to lower the learning curve for beginners who wants to build STEAM (and RBT) projects with micro:bit"
- Hardcopy Quick Start Guide plus online resources with example code and a step-by-step building video per project
- For RBT Y5 and Y6 (Reka Bentuk dan Teknologi Tahun 5 & 6)

## Price band
RM219.00–RM295.00 across 2 options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-rekabit-rbt-project-kits

## Datasheet
https://static.cytron.io/download/REKABIT-RBT-Project-Kit/REKABIT-RBT-Project-Kit-Quick-Start-Guide-BM-v1.0.pdf

## Source type
Datasheet

## Source link
https://static.cytron.io/download/REKABIT-RBT-Project-Kit/REKABIT-RBT-Project-Kit-Quick-Start-Guide-BM-v1.0.pdf
