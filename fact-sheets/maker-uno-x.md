# Product fact sheets

## Product name
Maker UNO X for Classrooms (Arduino Compatible)

## Aliases
MAKER-UNO-X, Maker UNO X, Maker UNO X for Classrooms, Maker UNO X for Classrooms (Arduino Compatible), Maker UNO X: Simplifying Arduino for Classrooms, Cytron Maker UNO X, Maker UNO X board, MakerUnoX

## What it is
An Arduino UNO-compatible board built on the ATmega328P, powered, programmed and connected through a USB Micro B socket. It has an LED on every digital pin, a piezo buzzer on D8, a programmable push button on D2, and an onboard perfboard and breadboard prototyping area.

## Specs and functions
- Product code: MAKER-UNO-X
- Microcontroller: ATmega328P
- Operating voltage: 5V
- Clock speed: 16MHz
- Flash memory: 32KB; SRAM: 2KB; EEPROM: 1KB
- Digital I/O pins: 20 (product page)
- PWM pins: 6 — pins 3, 5, 6, 9, 10 and 11 (marked ~); analogWrite range 0 to 255
- Analog input pins: 6 (10-bit), A0–A5 only; values 0 to 1023
- UART: 1; SPI: 1; I2C: 1
- USB to UART chip: guide driver is CH341SER and the port shows as CH340; product page links "CH34X" drivers; product page spec list writes "CH9340"; Cytron's Fritzing part artwork labels the chip "CH340C"
- USB connector: USB Micro B for power, program loading and USB communication
- Powerbank-friendly: "Enable continuous supply from most powerbanks"
- 1x programmable push button on D2 (use INPUT_PULLUP; reads LOW when pressed)
- 1x piezo buzzer on D8
- 12x LED as I/O indicators on D2 to D13
- 2x LED as UART TX/RX activity indicators on D0 & D1
- Debug mode slide switch: on = built-in LEDs and piezo buzzer enabled; off = D8 free for another I/O device
- With Debug on, LED 2 acts as an input indicator and turns off when the onboard button is pressed
- Reset button
- Onboard perfboard (donut board) prototyping area and breadboard; the breadboard is supplied loose with adhesive backing and stuck onto the board by the user (product page features say "half-size breadboard"; packing list says "mini breadboard")
- Header pins in Cytron's Fritzing part: D0/RX–D13/SCK, A0–A5 (A4/SDA, A5/SCL), separate SDA/SCL, AREF, IOREF, RESET, 3V3, 5V, GND, ICSP MISO/SCK/MOSI; no Vin connector
- Packing list: 1x Maker UNO X board, 1x mini breadboard, 1x Maker UNO pin sticker
- USB Micro B cable: optional accessory, not in the packing list
- Warranty: 12 months
- 5V and 3.3V pin output current: [NOT STATED]
- Per-I/O-pin current: [NOT STATED]
- Dimensions: [NOT STATED]
- Packing: Maker UNO X board, mini breadboard, Maker UNO pin sticker (product page)
- LEDs: 12 I/O LEDs on D2–D13; D0/D1 LEDs are the TX/RX activity LEDs (product page)

## Interfaces and compatibility
- Arduino UNO compatible; "fully compatible with Arduino UNO R3 sample code and libraries" (product page)
- Arduino IDE: select board "Arduino UNO" (product page)
- Guide v1.5 (Feb 2023) is updated to Arduino IDE 2.X; guide v1.4 is based on Arduino IDE 1.8.X
- Driver: CH34X/CH341 — Windows V3.5 (Mar 2019), Mac V1.5, Linux V1.5 on the product page; guide links CH341SER.EXE (Windows) and CH341SER_MAC.ZIP (Mac)
- Windows 7: not compatible with the USB to Serial driver; use a more recent version of Windows
- Fritzing part available from Cytron's GitHub (CytronTechnologies/MAKER-UNO-X)
- Companion book: Arduino Learning Guide for Beginners with Maker UNO X (BOK-MUNOX)
- Differences vs Maker UNO: adds the onboard perfboard and breadboard area; one Debug switch enables both the built-in LEDs and the buzzer (Maker UNO has a buzzer-only slide switch)
- Differences vs genuine Arduino UNO R3: no source lists them; sources state USB Micro B, a CH340-family USB-serial chip, no Vin connector in the Fritzing part, and onboard LEDs, buzzer, button and prototyping area
- UNO R3 shield compatibility: [NOT STATED]
- MicroPython / CircuitPython / block coding: [NOT STATED]

## Use cases
- Teaching Arduino in classrooms; students "code right away"
- The board lights up and plays a melody with a button press, no soldering
- Building circuits on the onboard breadboard and perfboard
- Portable projects powered from a powerbank
- Learning Arduino with the Arduino Learning Guide for Beginners with Maker UNO X
- Cytron tutorial: [K-Type Thermocouple With Maker UnoX And Blynk](https://my.cytron.io/tutorial/k-type-thermocouple-with-maker-uno-x-and-blynk)

## Known limitations
- USB-serial driver not compatible with Windows 7
- Built-in LEDs and buzzer work only with Debug mode switched on
- D8 is shared with the buzzer; switch Debug off to use D8 for another I/O device
- D2 is used by the onboard button and cannot be connected to other external components while in use
- PWM only on pins 3, 5, 6, 9, 10, 11; analog input only on A0–A5
- Power input is USB Micro B; no other power input is named and the Fritzing part has no Vin connector
- 5V/3.3V pin current limits and protection features: [NOT STATED]
- USB cable not included

## Positioning (kept apart from specs)
- Designed for educators and classrooms
- "the culmination of years of teaching Arduino & STEM by our education partners - Chumbaka, ARUS, and rero EDUteam"
- Predecessor Maker UNO was 1825% funded on Kickstarter (17 Apr 2018)
- "Powerbank-friendly to enable the portability of the projects"

## Price band
RM50.40 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-x-simplifying-arduino-for-classrooms

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

