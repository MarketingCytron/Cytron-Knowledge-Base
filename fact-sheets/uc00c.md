# Product fact sheets

## Product name
UC00C (CH340) USB to UART Converter

## Aliases
UC00C, UC00C CH340, CH340 USB to UART Converter, Cytron UC00C, Cytron USB to UART Converter UC00C

## What it is
A small USB-powered converter board that gives a computer a virtual COM port and connects it directly to a microcontroller's TTL UART at 3.3 V or 5 V logic. It plugs onto Arduino-style bootloader headers (Pro Mini, BBFuino, Fio) for program loading.

## Specs and functions
- USB-to-UART chip: "USB to UART chip", not named (user manual); CH340 (product page title); the manual photo shows a WCH chip with a separate crystal
- USB connector: USB Micro-B socket
- Power: USB powered, no external source required; "5V from USB port is available for user"
- UART logic level: 3.3 V or 5 V TTL, set by the VCC selectable slide switch (label F)
- VCC output pin: 3.3 V or 5 V, follows the switch (switch marked 5V and 3V3)
- 6-way header socket: DTR, RX, TX, VCC, CTS, GND; female right-angle socket with the ends marked GREEN (TX LED side) and BLACK (RX LED side); order from the GREEN end: DTR, RXI, TXO, VCC, CTS, GND (product page pinout image); DTR and CTS are active low
- DTR: used for auto-reset on Arduino-compatible boards
- CTS: hardware handshaking pin
- LEDs: Power LED (green), RX LED, TX LED (RX/TX LEDs work only when connected to a PC over USB)
- Driver: plug and play, driver needed for first-time use only; appears as a Virtual COM port
- Operating systems stated: Windows 7, 8 and 10
- Dimension: 3.9 cm x 2 cm
- Packing list: 1 x UC00C (USB Micro-B cable optional, not included)
- Warranty: 1 year (user manual); 12 months (product page)
- VCC current: 3.3 V setting max 500 mA; 5 V setting = whatever the USB port supplies (product page)
- Baud rate range, supply current, operating temperature: [NOT STATED]
- LEDs: red = TX, orange = RX (product page)
- Size: 39.8 × 21.2 × 5.6 mm (product page)
- Tested on Windows 7, 8, 8.1 and 10 (product page)
- Packing: 1 × UC00C (product page)

## Interfaces and compatibility
- Host: PC USB port (Micro-B cable)
- Target: any 3.3 V or 5 V TTL UART device; "development between computer and microcontroller, 3.3V or 5V logic"
- Bootloader compatible: BBFuino, Boarduino, Arduino Mini Pro "etc."; header socket reserved for loading program to Arduino Mini Pro, BBFuino, Fio and others
- Driver links (product page): Windows CH341SER V3.5 Mar2019 https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view ; Mac CH341SER_MAC V1.5 Mar2019 https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view ; Linux CH341SER_LINUX V1.5 Mar2019 https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view ; Mac troubleshooting https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf
- User manual (2016) states "Linux normally pre-installed with the proper driver"

## Use cases
- Serial communication between a microcontroller and a PC through a virtual COM port
- Loading program into Arduino boards without an onboard USB chip (Arduino Mini Pro, BBFuino, Fio, Boarduino)
- Replacing the old PC serial port (DB9) plus RS232 level shifter path with a USB connection

## Known limitations
- "Vsel" and "5V" are supplied directly from the computer's USB port; it is advised not to use this power to power application circuits or devices; wrong polarity, wrong voltage or a short might permanently damage the computer
- Only CTS is broken out as a handshake pin; RTS, DSR, DCD and RI are not on the 6-way socket
- USB powered only; no external power input
- Does not provide RS232 levels (TTL UART only)
- The user manual names only Windows 7, 8 and 10; Windows 11 and current macOS support are not stated
- Driver installation is required once before the COM port appears

## Positioning (kept apart from specs)
- "Low cost, easy to use USB to UART converter" aimed at development between computer and microcontroller (user manual)
- "USB plug and play, direct interface with microcontroller" (user manual)

## Price band
RM15.75 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-uc00c-ch340-usb-to-uart-converter

## Datasheet
https://docs.google.com/document/d/1adRsDAq_2xHbCvTTBw_mdcA3iCzYsW2S5WuDaZOizjc/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1adRsDAq_2xHbCvTTBw_mdcA3iCzYsW2S5WuDaZOizjc/view
