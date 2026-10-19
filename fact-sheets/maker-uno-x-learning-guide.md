# Product fact sheets

## Product name
Learning Guide for Beginners with Maker Uno X compatible with Arduino

## Aliases
BOK-MUNOX, Maker UNO X Learning Guide, Maker Uno X Learning Guide book, Learning Guide for Beginners with Maker Uno X, Arduino Learning Guide for Beginners Using Maker UNO X, Maker UNO X guide book

## What it is
A printed beginner's guidebook (v1.5, February 2023, published by Cytron Technologies, written by ET Tan) that teaches Arduino on the Maker UNO X board through Lesson 0 Setting Up plus 7 lessons and 17 projects. It is designed for the Maker Uno X Learning Box and sold on its own as one book.

## Specs and functions
- Product code: BOK-MUNOX
- Format: printed book; packing: 1x book
- Edition read: v1.5, February 2023 ("Arduino Learning Guide For Beginners — MAKER UNO X"; "Explore STEM and Coding with Maker UNO Xperiment Kit"); earlier edition v1.4, February 2020
- Written by ET Tan (Tan Eng Tong, Co-founder and CEO, Cytron Technologies); edited by Cheryl Ng; illustrated by Suhana Azmi; revised by Hairil and 'Awatif (v1.5)
- Target board: Maker UNO X (with the Maker UNO X Learning Box)
- Lesson 0 Setting Up: pin-label stickers, breadboard stuck onto the board, micro USB cable; Arduino IDE download; CH341 driver for Windows (CH341SER.EXE) and Mac (CH341SER_MAC.ZIP)
- Lesson 1 Digital Output: P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence
- Lesson 2 Digital Input: P4 On-board Pushbutton Switch; P5 External Pushbutton Switch
- Lesson 3 Analog Output: P6 Construct An LED Circuit; P7 Fade An LED
- Lesson 4 Melody Tone: P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code
- Lesson 5 Analog Input: P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line
- Lesson 6 DC Motor: P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton
- Lesson 7 Ultrasonic Sensor: P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor
- Project pins (as stated in the guide): P1–P3 LEDs on pins 7 and 2–7; P4 on-board switch pin 2 (INPUT_PULLUP) and LED 4; P5 external pushbutton on pin 3 with a 10 kΩ pull-up; P6–P7 external LED with 220 Ω on pin 5 (PWM); P8–P10 piezo buzzer on pin 8 via tone(); P11 potentiometer on A0; P12–P13 IR sensor VCC 5V, GND, A0 to A0; P14 DC motor on pin 5 through a 2N2222 transistor, 220 Ω resistor and a diode
- Tone values taught: Do 262, Re 294, Mi 330, Fa 349, So 392, La 440, Ti 494, high Do 523 Hz; delay 30 % longer than the note duration
- IR threshold rule: (reading on white + reading on black) / 2; author's example 500
- Motor speed demo: analogWrite(5, 255) for 3 s then analogWrite(5, 80) for 3 s; kit motor rated 3–6 V
- Each project links a demo video by QR code; each lesson ends with a Task and a summary
- Page count, size, ISBN: [NOT STATED]
- Warranty: 12 months

## Interfaces and compatibility
- For the Maker UNO X board: on-board LEDs on pins 2–13, piezo buzzer on pin 8, on-board switch on pin 2, "Debug" mode slide switch that enables the built-in LEDs and buzzer, PWM on pins 3, 5, 6, 9, 10, 11, analog input on A0–A5
- Software: Arduino IDE from arduino.cc (Windows 10+ 64-bit installer recommended; Mac package); CH341 driver; Mac port shown as /dev/cu.usbserial-220
- Not the guide for the Maker UNO Learning Box (that kit uses the Maker UNO edition of the guide)

## Use cases
- A student (or teacher) learning Arduino for the first time
- Turn on, blink and sequence LEDs
- Read the on-board and an external pushbutton; pull-up and pull-down circuits
- Build an LED circuit and fade it with PWM
- Play tones and the "Happy Birthday" melody; use the toneMelody example
- Read a potentiometer and an IR sensor; detect a black line
- Control a DC motor and its speed
- Set up an ultrasonic sensor and build a car's rear bumper sensor

## Known limitations
- Written for the Maker UNO X: Debug mode must be on for the built-in LEDs and buzzer; switch it off to use pin 8 for another device
- The on-board switch occupies pin 2 and cannot be shared with other components while in use
- P6 blinks forever once the switch is pressed until reset; P9 plays once because the code is in setup()
- The motor may lack torque if its blades rest on a surface; applying voltage beyond the motor's rating shortens its life
- Projects 15–17 and the total page count were not read for this sheet
- The product page does not state which edition ships

## Positioning (kept apart from specs)
- "I wrote this guide with you in mind - a student (or teacher), learning Arduino for the first time."
- "I just added explanation on some aspects that I initially struggled with and I also simplified the technical part for better understanding."
- "Simplifying Digital Making"

## Price band
RM39.00 (5+ RM37.10, 10+ RM35.10) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-arduino-learning-guide-for-beginners-with-maker-uno-x

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

