# Product fact sheets

## Product name
Maker UNO Edu Kit (Arduino Compatible)

## Aliases
V-KIT-MUNO-EDU, KIT-MAKER-UNO-EDU, Maker UNO Edu Kit, Maker UNO Edu Kit (Arduino Compatible), Maker UNO EduKit, Maker UNO Edu Kit School Package 10+1

## What it is
A classroom kit built around the Maker UNO (an Arduino UNO-compatible board with on-board LEDs, a piezo buzzer and a programmable button), sold with a Getting Started Module of 10 lessons and 2 projects and a Teacher Guidebook for the Malaysian Form 2 RBT syllabus.

## Specs and functions
- Product code: V-KIT-MUNO-EDU (my.cytron.io); older Cytron page: KIT-MAKER-UNO-EDU
- Purchase options: Maker UNO Edu Kit (single set); School Package 10+1 ("10 sets + 1 free set (Get 11 sets for the price of 10)")
- Controller board: Maker UNO (ATmega328P, CH340 USB-serial, Micro USB, no DC jack) — board details in the Maker UNO fact sheet
- On-board I/O used in lessons: "12x LEDs, 1x piezo buzzer and 1x programmable button"
- Pin-label stickers included (user peels and applies them)
- Box has an opening for the USB cable so the board can stay in the box
- Getting Started Module lessons: 1 The LED (Digital Output); 2 LED Blinking; 3 LED Output (PWM); 4 Push Button as Digital Input; 5 Serial Write; 6 Serial Read; 7 Tone Melody; 8 Potentiometer as Analog Input; 9 LDR as Analog Input; 10 Controlling Motor
- Getting Started Module projects: Interactive Traffic Light; Light Theremin
- Lesson pins: LED pin 7 (L1, L2, L6); LED pin 3 PWM (L3); LED pin 4 + button pin 2 INPUT_PULLUP (L4); Serial 9600 baud (L5, L6); 10 kΩ potentiometer on A0 + LED 13 (L8); LDR with 10 kΩ on A0 + LED 13, threshold 600 (L9); motor from pin 6 through 220 Ω and a transistor, speeds 255/123/50/0 (L10)
- Interactive Traffic Light: vehicle green pin 5, yellow pin 6, red pin 7; pedestrian green pin 3, red pin 4; button pin 2; 5 x 220 Ω; yellow 2 s, red, pedestrian green 5 s
- Light Theremin: LDR + 10 kΩ on A0, piezo buzzer pin 8 via tone(), LED 13 shows calibration, calibration for the first 5 s after power-up
- Teacher Guidebook: 4 units, 10 hours total — Unit 1 Microcontroller Theory (2 h), Unit 2 Output (3 h), Unit 3 Input (2 h), Unit 4 Combination of Input and Output (3 h); learning standards 2.4.1–2.4.8; assessment Tier 1–6; Appendix 1 programming from Android (USB OTG Checker, ArduinoDroid)
- Software: Arduino IDE (module written for 1.8.x); CH340/CH341 USB driver for Windows and macOS
- Packing list per set: Maker UNO ×1; USB Micro B cable ×1; LED 5 mm red ×3, yellow ×3, green ×3; breadboard (small) ×1; 40-way male-to-male jumper wire ×1; resistor 0.25 W 5% 220 Ω ×10, 1 kΩ ×5, 10 kΩ ×5; LDR (small) ×1; transistor 2N2222 ×1; finger-adjust preset 10 kΩ ×1; 3 V miniature brush motor without gear ×1; DIY 4-blade 56 mm motor propeller ×1; Maker Box ×1 (product page image)
- Warranty: [NOT STATED] (blank on product page)
- Dimensions and weight: [NOT STATED]

## Interfaces and compatibility
- Power and programming over Micro USB only (Maker UNO has no DC jack and no Vin pin)
- Button: D2 with INPUT_PULLUP (pressed = LOW)
- Buzzer: D8 through the on-board slide switch (on to use the buzzer, off to free pin 8)
- PWM pins: ~3, ~5, ~6, ~9, ~10, ~11
- Analog inputs used: A0
- Arduino libraries and code compatible; Arduino UNO R3 shields except those needing Vin (see Maker UNO fact sheet)
- Documents linked: Maker UNO User's Manual, Getting Started Module PDF, schematic, Fritzing part, CH341 drivers, DSKP KSSM RBT Tingkatan 2, Teacher's Guide, Student's Class Module, Answer Scheme, Bahasa Malaysia versions
- Default sketch: github.com/CytronTechnologies/MakerUno_Examples (MakerUno_DefaultSketch)

## Use cases
- Teaching Arduino coding in class with the Maker UNO's on-board LEDs, buzzer and button before building circuits
- Form 2 RBT (DSKP KSSM) microcontroller unit: theory, output, input, combined input/output, project creation
- Digital output, PWM fading, push button input, serial write/read, tone melody, potentiometer and LDR analog input, DC motor speed control
- Interactive Traffic Light project
- Light Theremin project
- School Package 10+1 for a class set

## Known limitations
- Power is USB only; no DC jack and no Vin pin on the Maker UNO
- The on-board button occupies D2 and the buzzer occupies D8 (slide switch)
- analogWrite() works only on PWM pins ~3, ~5, ~6, ~9, ~10, ~11
- Pin-label stickers must be applied by the user
- Teacher Guidebook units 2.4, 3.4 and 4.3 need internet access; each student needs a Maker UNO; some topics need laptops or phones
- The Getting Started Module has no printed version or date
- Warranty is not stated for the kit
- No flyback diode is listed for the motor lesson

## Positioning (kept apart from specs)
- "Many students lack basic electronics knowledge and struggle with circuit diagrams, often spending much of a lesson wiring and troubleshooting."
- "The kit lets students skip building basic circuits at first and start coding quickly, with a project that lights the board and plays a melody on a button press."
- "The onboard LEDs act as both outputs and indicators, showing pin activity so students can tell whether a problem comes from wiring or code."
- School Package: "Get 11 sets for the price of 10"

## Price band
RM60.00 (single kit) to RM689.92 (School Package 10+1) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-edu-kits-arduino-compatible

## Datasheet
https://cdn.cytron.io/makeruno/Maker_Uno_Edu_Kit_Module.pdf

## Source type
Datasheet

## Source link
https://cdn.cytron.io/makeruno/Maker_Uno_Edu_Kit_Module.pdf
