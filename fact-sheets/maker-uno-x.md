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
- USB to UART chip: CH340C (schematic REV 1.0.0, silkscreen and assembly diagram); guide driver is CH341SER and the port shows as CH340; product page links "CH34X" drivers; product page spec list writes "CH9340" (unconfirmed)
- USB connector: USB Micro B for power, program loading and USB communication
- Powerbank-friendly: "Enable continuous supply from most powerbanks"; done by an always-on 555-timer power bank keep-alive load with a red PWRBANK LED (schematic)
- 3.3V regulator: RT9013-33GB, part value "3.3V 500mA", fed from USB 5V (schematic)
- USB 5V goes straight to the 5V rail: no fuse or polarity diode on the schematic
- VIN header pin: fed from 5V through a Schottky diode (output only); no DC jack (schematic)
- 16MHz crystal; ATmega328P-AU (TQFP)
- 1x programmable push button on D2 (use INPUT_PULLUP; reads LOW when pressed)
- 1x piezo buzzer on D8
- 12x LED as I/O indicators on D2 to D13
- 2x LED as UART TX/RX activity indicators on D0 & D1
- Debug mode slide switch: on = built-in LEDs and piezo buzzer enabled; off = D8 free for another I/O device. The switch powers the LED/buzzer rail from 3.3V; each LED and the buzzer is driven by a MOSFET from its pin, so the LEDs do not load the pins (schematic)
- TX/RX LEDs work regardless of the Debug switch; green power LEDs for 5V and 3.3V
- With Debug on, LED 2 acts as an input indicator and turns off when the onboard button is pressed
- Reset button
- Onboard perfboard (donut board) prototyping area and breadboard; the breadboard is supplied loose with adhesive backing and stuck onto the board by the user (product page features say "half-size breadboard"; packing list says "mini breadboard")
- Headers (schematic): power header NC, IOREF (5V), RESET, 3.3V, 5V, GND, GND, VIN; A0–A5; SCL, SDA, AREF, GND, D13–D8; D7–D0; 2x3 ICSP (MISO, 5V, SCK, MOSI, RST, GND). Cytron's Fritzing part omits VIN
- Perfboard section: 400 plated holes linked in a breadboard pattern (30 rows of a–e and f–j, plus four +/− rails) (board file)
- Packing list: 1x Maker UNO X board, 1x mini breadboard, 1x Maker UNO pin sticker
- USB Micro B cable: optional accessory, not in the packing list
- Warranty: 12 months
- 5V and 3.3V pin output current: [NOT STATED] (3.3V regulator part value "3.3V 500mA")
- Per-I/O-pin current: [NOT STATED]
- Dimensions: board outline 127.0 x 88.9 mm overall; the UNO-shaped controller section is about 62 x 69 mm (measured from Cytron's board file)
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
- Differences vs genuine Arduino UNO R3: no source lists them; the design files show USB Micro B, a CH340C USB-serial chip, no DC jack, VIN as an output only (fed from 5V through a diode), IOREF at 5V, a power bank keep-alive load, and onboard LEDs, buzzer, button and prototyping area
- UNO R3 shield compatibility: [NOT STATED] by Cytron; the headers follow the UNO R3 pin order, but physical fit is unverified and shields cannot power the board through VIN
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
- Power input is USB Micro B only; no DC jack, and VIN is an output (fed from 5V through a diode), so the board cannot be powered through VIN
- No fuse or polarity protection on the USB 5V rail (schematic); 5V/3.3V pin current limits: [NOT STATED]
- The power bank keep-alive load is always on (red PWRBANK LED blinks) and adds some current draw
- D2–D13 each have a 3.3 MΩ pull-down through the Debug LED driver, so unconnected inputs read LOW
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

