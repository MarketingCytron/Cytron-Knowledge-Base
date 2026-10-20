# Product fact sheets

## Product name
UC00A (FTDI) USB to UART Converter

## Aliases
UC00A, UC00A Rev3.0, UC00A R3, FTDI USB to UART Converter, Cytron UC00A, Cytron USB to UART Converter UC00A

## What it is
A USB-powered USB-to-UART converter built on an FTDI chip that gives a computer a virtual COM port and connects directly to a 3.3 V or 5 V TTL UART device. Rev3.0 (current) has a USB Micro-B socket, a 3.3V/5V slide switch and a standard 6-way header socket for Arduino-style bootloader headers.

## Specs and functions
- USB-to-UART chip: "FTDI chip" (user manual); FT232RL (Rev3.0 schematic linked from product page)
- USB connector: USB Micro-B socket
- Power: USB powered, no external source required
- UART logic level: 3.3 V or 5 V TTL, set by Vsel slide switch (label G); default Vsel is 5V
- Standard 6-way header socket: DTR, RXI, TXO, VCC, CTS, GND (DTR marked Green, GND marked Black)
- VCC pin: 3.3 V or 5 V output, follows Vsel
- Extra UART pins (JP4/JP6): 5V, GND, CTS, DCD, DSR, RI, RX, RTS, DTR, TX; logic level follows Vsel
- 5V pin: constant 5 V from USB, not affected by Vsel; maximum current "limited from USB port, normally is 900mA"
- DTR: used for auto-reset on Arduino-compatible boards
- CTS, DCD, DSR, RI, RTS: "unused under normal UART operation"
- LEDs: Power LED (green), FTDI TX indicator LED, FTDI RX indicator LED
- Driver: plug and play, FTDI driver needed for first-time use only; appears as a Virtual COM port
- Operating systems stated: Windows XP, Vista, 7, 8 and 10
- Dimension (Rev3.0): 4.4 cm x 2 cm
- Packing list: 1 x UC00A Rev3.0 (USB Micro-B cable optional, not included)
- Warranty: 6 months (Rev3.0 user manual, Dec 2018); 12 months (product page, 2026-10-16)
- Revision history: Rev1.0 (2008) USB-A plug, 5 V only, 4-way 2510 pin header, 5V max 200 mA; Rev2.0 (2012) Mini USB, Vsel solder jumper, 4-way 2510 connector plus 6-way socket, 5V max 250 mA, 3.3V max 50 mA, 3.9 cm x 2 cm; Rev3.0 (current) Micro-B, slide switch, 6-way socket plus JP4/JP6, no 2510 connector
- Baud rate range, VCC output current (Rev3.0), supply current, operating temperature: [NOT STATED]
- Rev3.0 since June 2016; 3.3 V regulator 500 mA max (product page)
- Size 45.2 × 21.3 × 4.2 mm (product page)

## Interfaces and compatibility
- Host: PC USB port (Micro-B cable)
- Target: "any device which offer 3.3V/5V UART interface, this includes microcontroller, RFID reader, XBee, Bluetooth, WiFi, wireless module and more"
- Bootloader compatible: BBFuino, Boarduino, Arduino Mini Pro "etc."; 6-way socket used for loading program to Arduino Pro Mini, BBFuino, Fio and others
- Program loading stated for Arduino Pro Mini, Arduino FIO, ArduPilot, Rainbow LED Ring V3, BBFuino
- Arduino Pro Mini wiring: DTR (Green) to RESET, RX to TXD, TX to RXD, Vsel to 5V, CTS to GND, GND (Black) to GND
- PC-to-PC link: two UC00A cross-wired RXI to TXO, TXO to RXI, GND to GND, same baud on both PCs
- Drivers: FTDI VCP driver; manual links Driver Installation Guide for Win 7 https://drive.google.com/file/d/12HDo0o2ygGj9s0I90drnNp0FnFZG2jAx/view and FTDI driver page http://www.ftdichip.com/FTDrivers.htm
- Schematic Rev3.0: https://drive.google.com/file/d/15aQuzmaxM7FiHtMJkuptoebEAMuz-Wip/view

## Use cases
- Serial communication between a microcontroller or UART module and a PC through a virtual COM port
- Loading program into Arduino boards without an onboard USB chip (Arduino Pro Mini, FIO, BBFuino, ArduPilot, Rainbow LED Ring V3)
- Testing a UART device (example: SKPS PS2 controller converter) from a PC terminal
- Communication between two PCs using two UC00A boards
- Cytron tutorial: [Getting Started with Arduino – PRO Mini](https://my.cytron.io/tutorial/getting-started-arduino-pro-mini)

## Known limitations
- "Vsel" and "5V" are supplied directly from the computer's USB port; it is advised not to use this power to power application circuits or devices; wrong polarity, wrong voltage or a short might permanently damage the computer
- Handshake pins CTS, DCD, DSR, RI, RTS and DTR are "unused under normal UART operation"
- USB powered only; no external power input
- TTL UART only; does not provide RS232 levels
- Rev3.0 has no 4-way 2510 connector (Rev1.0/Rev2.0 cables do not apply)
- The user manual names only Windows XP to Windows 10; Windows 11 and current macOS support are not stated
- Driver installation is required once before the COM port appears
- Warranty differs between user manual (6 months) and product page (12 months)

## Positioning (kept apart from specs)
- "Low cost, easy to use USB to UART converter" aimed at development between computer and microcontroller (user manual)
- "USB plug and play, direct interface with microcontroller and it provides 5V power supply from USB port" (user manual)

## Price band
RM43.05 (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-uc00a-ftdi-usb-to-uart-converter

## Datasheet
https://docs.google.com/document/d/1pFK7DSRuZB7SeP3aCmjYzWB0i7aT-C_W_D-x25WLops/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1pFK7DSRuZB7SeP3aCmjYzWB0i7aT-C_W_D-x25WLops/view
