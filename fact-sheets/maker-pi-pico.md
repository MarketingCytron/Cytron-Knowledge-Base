# Product fact sheets

## Product name
Maker Pi Pico

## Aliases
MAKER-PI-PICO, Cytron Maker Pi Pico, Maker Pi Pico: Simplifying Raspberry Pi Pico for Beginners

## What it is
A beginner project board for the Raspberry Pi Pico, with the Pico soldered onboard. It breaks out all Pico pins and adds LEDs, buttons, a buzzer, audio out, a microSD socket, an ESP-01 socket and 6 Grove ports.

## Specs and functions
- Product code: MAKER-PI-PICO
- Datasheet: Rev 1.2, March 2021 (covers MAKER-PI-PICO and MAKER-PI-PICO-NB); its spec table is titled "Absolute Maximum Ratings"
- Host board: Raspberry Pi Pico, soldered onboard (product page packing list)
- Power input voltage (USB): 4.5 – 5.5 VDC
- Micro USB port: used to power up the Maker Pi Pico and upload programs from PC
- 3V3 power LED
- GPIO LEDs: LED indicator for Raspberry Pi Pico GPIO, on when the GPIO state is high (product page: "LED indicators on all GPIO pins")
- WS2812B RGB LED: 1, on GP28
- Programmable buttons: 3, on GP20, GP21 and GP22; Rev1.0.0 to 1.1.0 = enable internal pull-up in software; Rev1.2.0 = pulled-up permanently on hardware with debouncing capacitor
- Reset button: resets the Raspberry Pi Pico
- Piezo buzzer: GP18, with buzzer mute switch
- Audio out: non amplified, 3.5mm stereo audio jack; Left channel GP18, Right channel GP19
- Micro SD card socket: GP10 CLK / SCK, GP11 CMD / SDI, GP12 DAT0 / SDO, GP13 DAT1 / X, GP14 DAT2 / X, GP15 CD/DAT3 / CSn (SD mode / SPI mode); unused pins must be configured as internal pull-ups
- ESP-01 socket: for ESP-01 ESP8266 WiFi module, GP16-17 (product page)
- Grove ports: 6 (product page)
- GPIO breakout: two 20 ways pin headers, male pin headers on MAKER-PI-PICO
- Debugging port breakout
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.62 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃

## Interfaces and compatibility
- Micro USB (power and programming), 6 Grove ports, 3.5mm stereo audio jack, micro SD card socket, ESP-01 socket, debugging port breakout, two 20-way GPIO pin headers
- Programming: CircuitPython, MicroPython and C/C++; programs upload over USB by drag and drop
- Cytron out-of-the-box demo code in CircuitPython and MicroPython on GitHub (CytronTechnologies/MAKER-PI-PICO)
- RGB LED on GP28 is driven with the Pico's PIO feature (product page Q&A)
- Grove: official or compatible Grove 4-pin cables recommended (product page Q&A)
- Pico W: product page Q&A says Maker Pi Pico with an ESP-01 module "Can achieve the same purpose, but code and library will not be the same"
- Packing list: 1 x Maker Pi Pico (Raspberry Pi Pico soldered onboard, with CircuitPython loaded), 1x Pinout reference card

## Use cases
- Learning Raspberry Pi Pico for beginners
- STEM & robotics projects
- Real-Time Multitasking on Maker Pi Pico Using pyRTOS
- Building Line Following Robot Using Maker Pi Pico, Maker Drive and Maker Line
- Play MP3 File on Maker Pi Pico Using CircuitPython
- Read and Display Environment Sensor Data Using Raspberry Pi Pico and CircuitPython
- Metronome with Maker Pi Pico, programmed with CircuitPython
- Ultrasonic HC-SR04P Using Raspberry Pi Pico
- IoT-enabling a project with an ESP-01 module

## Known limitations
- Spec values are absolute maximum ratings
- Power input is USB only, 4.5 – 5.5 VDC
- Audio output is not amplified; connect an earphone or amplified speaker
- GP18 is shared by the piezo buzzer and the left audio channel
- Unused microSD pins must be configured as internal pull-ups
- On PCB Rev1.0.0 to 1.1.0 the button pull-ups must be enabled in software
- The RGB LED on GP28 needs the Pico's PIO feature to drive it
- The ESP-01 module is not included in the packing list
- The datasheet names the Raspberry Pi Pico only

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Raspberry Pi Pico for Beginner"
- Product page: "It is a compact yet feature-packed board designed to sit at the heart of your STEM & robotics projects."
- Product page: "Work out-of-the-box. No soldering!"

## Price band
RM48.00 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-pi-pico

## Datasheet
https://docs.google.com/document/d/1JoHsZk5IipQPCLXWbZYpDKjGlnkyACOJ1taUrKVsRg8/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1JoHsZk5IipQPCLXWbZYpDKjGlnkyACOJ1taUrKVsRg8/edit
