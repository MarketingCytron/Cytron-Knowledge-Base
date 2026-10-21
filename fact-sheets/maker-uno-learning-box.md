# Product fact sheets

## Product name
Maker UNO Learning Box - Everything You Need to Start Making

## Aliases
KIT-MAKER-UNO-START, Maker UNO Learning Box, Maker UNO Learning Box - Everything You Need to Start Making, Maker UNO Learning Kit

## What it is
A beginner kit that packs a Maker UNO board with the LEDs, switches, resistors, transistors, diode, potentiometer, IR line sensor, SR04 ultrasonic sensor, 3 V motor and breadboard needed for the 17 projects in Cytron's "Arduino Learning Guide for Beginner Using Maker UNO". The guide is a PDF linked from the product page.

## Specs and functions
- Product code: KIT-MAKER-UNO-START
- Controller board: 1x Maker UNO (board details in the Maker UNO fact sheet)
- Lessons: 7 lessons, 17 projects
- Lesson 1 Digital Output: P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence
- Lesson 2 Digital Input: P4 On-board Pushbutton Switch; P5 External Pushbutton Switch
- Lesson 3 Analog Output: P6 Construct An LED Circuit; P7 Fade An LED
- Lesson 4 Melody Tone: P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code
- Lesson 5 Analog Input: P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line
- Lesson 6 DC Motor: P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton
- Lesson 7 Ultrasonic Sensor: P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor
- Packing list: 1x Maker UNO; 1x 3V miniature brush motor; 1x DIY 4-blade propeller (blue); 1x SR04 ultrasonic sensor; 1x IR line sensor; 3x LED 5mm red; 3x LED 5mm yellow; 3x LED 5mm green; 3x pushbutton switch; 10x 220Ω; 10x 1kΩ; 10x 10kΩ; 1x 1N4007 diode; 2x 2N2222 transistor; 1x finger preset 10K; 1x 40-way M-M jumper; 1x 40-way M-F jumper; 1x Micro B USB cable; 1x breadboard 8.5cm x 5.5cm
- Software: Arduino IDE; CH341 (CH34x) USB driver; Maker UNO default sketch on GitHub
- Warranty: 12 months
- Dimensions and weight: [NOT STATED]
- Guide: "Arduino Learning Guide For Beginner Using Maker UNO", Ver 1.3, Dec 2018, 90 pages (Lesson 0 setup + 7 lessons, 17 projects)
- Project wiring (guide): on-board LEDs pins 2–7; on-board button pin 2 (INPUT_PULLUP); external button on pin 3 with 10 kΩ pull-up; external LED + 220 Ω on pin 5; buzzer pin 8; potentiometer A0; IR sensor analog output A0; motor on pin 5 through a 2N2222 with 220 Ω base resistor and a diode; ultrasonic Trig pin 11, Echo pin 12, VCC 5V
- Prices are subject to SST from April 2026, calculated at checkout (product page)

## Interfaces and compatibility
- Power and programming over Micro USB only (Maker UNO has no DC jack and no Vin pin)
- On-board button D2 (INPUT_PULLUP), on-board piezo buzzer D8 (slide switch), PWM on ~3, ~5, ~6, ~9, ~10, ~11, analog inputs A0–A5 (Maker UNO board facts)
- IR line sensor is read as an analog input in the lessons
- Ultrasonic sensor: SR04
- Motor projects use the 2N2222 transistors and the 1N4007 diode
- Arduino IDE (arduino.cc); CH34X driver for Windows (V3.5, Mar 2019), macOS (V1.5, Mar 2019), Linux (V1.5, Mar 2019, usually preinstalled); plug the Maker UNO in during driver installation
- Default program: github.com/CytronTechnologies/MakerUno_Examples (MakerUno_DefaultSketch)

## Use cases
- Learning Arduino from zero with no electronics or coding background (students and teachers)
- Digital output: turn on, blink and sequence LEDs
- Digital input: on-board and external pushbutton switches
- Analog output: build an LED circuit and fade an LED
- Melody tone: basic tones, "Happy Birthday" melody, code optimisation
- Analog input: serial monitor values, analog IR sensor reading, black line detection
- DC motor: control a motor and its speed with a pushbutton
- Ultrasonic sensor: set up the sensor and build a car's rear bumper sensor

## Known limitations
- Power is USB only; no battery or adapter in the kit
- The guide is a PDF download; a printed copy is not listed in the packing list
- Hold the motor while testing; it may not have the torque to spin with the propeller resting on a surface
- The transistor circuit cannot reverse the motor; a motor driver is needed for direction control
- Not the Maker UNO X Learning Box: same 17-project structure but a different board and guide edition
- The 3 V motor must be driven through the supplied transistor, not directly from an I/O pin (Maker UNO I/O pin limit 20 mA)

## Positioning (kept apart from specs)
- "Everything You Need to Start Making"
- A beginner Arduino learning set created by a non-technical author, for students and teachers who lack electronics or coding experience; each lesson shows a visible result early, then gives a brief explanation of how it works
- "Arduino is the easiest platform to learn digital making."

## Price band
RM62.90 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-learning-box-everything-you-need-to-start-making

## Datasheet
https://s3-ap-southeast-1.amazonaws.com/cdn.cytron.io/makeruno/Arduino_Learning_Guide_for_Beginner_Using_Maker_UNO.pdf

## Source type
Datasheet

## Source link
[NOT STATED]

