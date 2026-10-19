# Product fact sheets

## Product name
Auto Plant Watering Kit for micro:bit

## Aliases
Auto Plant Watering Kit for micro:bit, Auto Plant Watering Kit, RBT Auto Plant Watering Kit, RBT Automatic Plant Watering Kit, APW Kit, RBT APW, V-KIT-RBT-APW, KIT-RBT-APW

## What it is
A micro:bit lesson kit that builds an automatic plant-watering system: a Maker Soil Moisture Sensor reads the soil, a REKA:BIT runs a submersible pump when the soil is dry, and a micro servo aims the water pipe. It comes with a printed five-lesson guide; an IoT option adds a Grove WiFi 8266 and follows a separate Cytron Blynk IoT tutorial.

## Specs and functions
- Product code: V-KIT-RBT-APW
- Purchase options: standard / IoT version, each with micro:bit or without micro:bit
- Controller board: REKA:BIT (see the REKA:BIT entry for board specs)
- Kit contents (with micro:bit): 1x Lesson guide (English), 1x Maker Soil Moisture Sensor, 1x REKA:BIT (with micro:bit V2), 1x Micro Submersible Water Pump DC 3V-5V with Pipe, 1x Analog Micro Servo 9g (3V-6V) with horns and screws, 1x Grove 4 Pin Buckled 50cm Cable, 1x Servo Male-Female Extension Cable 30cm, 1x 4xAA battery holder with DC plug, 4x PKCELL Heavy Duty AA Battery, 1x Tiny Phillips Screwdriver, 2x Popsicle stick, 3x Cable Ties, 2x Double Sided Tapes
- IoT version: adds 1x Grove WiFi 8266
- Without-micro:bit options: REKA:BIT without micro:bit
- Lesson guide: "Auto Plant Watering Kit for micro:bit", April 2022, by Goh Hao Zhen & Cheryl Ng; softcopies in English, Malay, Chinese, Thai
- Lessons: 1 Hello! (micro:bit + MakeCode); 2 What's the Soil Moisture Level?; 3 Dry? Moist? Or Wet?; 4 Water the Plant (pump when dry); 5 Servo Motor, Direct the Pipe!; Additional Activity 1 visualise soil moisture on the LED matrix; Additional Activity 2 melodies
- Soil moisture reading: higher when the probe is dry, lower in water; the threshold is calculated by the student from three recorded readings (no fixed number)
- Lesson 4: pump runs for 5 seconds when the reading is higher than the threshold
- Lesson 5: servo sweeps 30 to 150 degrees while the pump runs
- Lesson 3 indication: REKA:BIT RGB LEDs green = moist, red = dry; micro:bit shows a smiley or sad face
- Water pump: DC 3V-5V, with pipe
- Servo: analog micro servo 9g, 3V-6V
- Battery: 4x AA in a holder with DC plug, into the REKA:BIT power jack
- Warranty: 12 months

## Interfaces and compatibility
- Maker Soil Moisture Sensor: REKA:BIT Grove port P2:P12 (50 cm Grove cable); read on analog pin P2; probe inserted up to the white line
- Water pump: MOTOR 2 terminal, black wire to M2B, red wire to M2A
- Servo: servo port S1 via the 30 cm extension cable (port pins White = S signal, Red = +, Black = -; servo lead to extension Orange-White, Red-Red, Brown-Black)
- Battery holder: REKA:BIT power jack
- Grove buzzer for micro:bit V1: port P0:P1
- MakeCode extension: rekabit (adds REKA:BIT and Neopixel drawers)
- MakeCode editor: https://makecode.microbit.org ; WebUSB one-click download needs the new Edge or Chrome and the latest micro:bit firmware
- micro:bit V1 and V2 (V2 has the built-in speaker used in Additional Activity 2)
- IoT version: Cytron tutorial "RBT Automatic Plant Watering IoT Project Using Blynk IoT" — https://my.cytron.io/tutorial/rbt-automatic-plant-watering-iot-project-using-blynk-iot
- Sample code: https://link.cytron.io/auto-plant-wateringproject-code ; project ideas: https://link.cytron.io/apw-projects

## Use cases
- Display soil moisture level on the micro:bit
- Classify soil as dry, moist or wet
- Water the plant automatically when the soil is dry
- Direct the water pipe with a servo motor
- Visualise soil moisture as a bar graph on the LED matrix
- Play melodies and sound notifications
- IoT monitoring with Blynk IoT (IoT version)

## Known limitations
- The micro:bit is not included in the "without micro:bit" options
- The step-by-step guide for the IoT project is not included in the booklet
- A higher sensor reading means drier soil; the pump trigger is reading higher than threshold
- No fixed dry/moist/wet values are given; each plant needs its own threshold
- Do not wet the Maker Soil Moisture Sensor's exposed part or the REKA:BIT; it risks damaging electronic components on the board
- micro:bit V1 has no built-in speaker; a Grove buzzer on P0:P1 is needed for sound
- Pins taken: P2 (P2:P12 port), MOTOR 2, S1, and P0:P1 if a buzzer is added
- When clamping the pump wires, clamp the exposed wire lead, not the insulator
- Electrical limits are the REKA:BIT board's (3.6 to 6 V input; motor and servo rails equal the battery voltage; over 7 V cuts motor and servo power)
- The booklet gives no battery voltage figure
- Plant, pot and water container are not included

## Positioning (kept apart from specs)
- Lesson Guide offered as a free PDF in English, Malay, Chinese and Thai
- Standard and IoT versions, each with or without the micro:bit
- Same sensor, pump and servo combination as Project 3 of the REKA:BIT RBT Project Kit

## Price band
RM108.00 to RM214.62 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-auto-plant-watering-kit-for-microbit

## Datasheet
https://static.cytron.io/download/KIT-RBT-APW/RBT_APW_KIT_Booklet_English_v1.pdf

## Source type
Datasheet

## Source link
https://static.cytron.io/download/KIT-RBT-APW/RBT_APW_KIT_Booklet_English_v1.pdf
