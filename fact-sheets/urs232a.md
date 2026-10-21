# Product fact sheets

## Product name
TTL UART to RS232 Converter (URS232A)

## Aliases
URS232A, TTL UART to RS232 Converter, Cytron TTL UART to RS232 Converter, UART to RS232 Converter, Cytron URS232A

## What it is
A level-shifter board between a microcontroller's TTL UART and RS232 (DB9) devices such as a GSM modem or RFID reader. It uses the MAX232 and comes pre-soldered with a male DB9 connector, the MAX232 and capacitors.

## Specs and functions
- Level-shifter IC: MAX232 (product page)
- RS232 connector: DB9-Male (PC side) (product page)
- Signals supported: Tx, Rx, CTS and RTS (product page)
- Assembly: pre-soldered male DB9 connector, MAX232 and capacitors (product page)
- Warranty: 12 months (product page)
- Supply voltage: +5 V only, no on-board regulator (Cytron schematic)
- TTL logic level: 5 V (MAX232 outputs); 3.3 V support not stated
- Baud rate range: [NOT STATED]
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Microcontroller side: 4-way header JP1 pin 1 RX_TTL, 2 TX_TTL, 3 GND, 4 +5V; 6-way header JP2 pin 1 GND, 2 CTS_TTL, 3 +5V, 4 RX_TTL, 5 TX_TTL, 6 RTS_TTL (Cytron schematic)
- Wiring: MCU TX to RX_TTL, MCU RX to TX_TTL, MCU RTS to RTS_TTL, MCU CTS to CTS_TTL — RX_TTL/RTS_TTL are board inputs (Cytron schematic)
- DB9 pins: 2 RX, 3 TX, 5 GND, 7 RTS, 8 CTS (standard PC pin-out); 4 and 6 tied together; 1 and 9 not connected (Cytron schematic)
- JP2 pin order does not match the UC00A/UC00C socket order; wire each signal by name
- Device side: DB9-Male (PC side) RS232 connector (product page)
- Works with Cytron UC00A or UC00C to make a USB-to-RS232 converter (product page)
- UC00C's 6-way socket has no RTS pin, so RTS handshake is not available from UC00C as documented (UC00C user manual, via KB)
- Not a USB device: the board has no USB chip; USB needs a separate USB-UART board (Cytron schematic)
- Software: none needed on the board

## Use cases
- Interfacing a microcontroller with RS232 devices such as a GSM modem or RFID reader
- Making a USB-to-RS232 converter together with UC00A or UC00C

## Known limitations
- No Cytron datasheet or user manual; the product page and the Cytron schematic are the only Cytron sources
- 5 V board: outputs are 5 V level; use a level shifter for 3.3 V-only UARTs
- DTR/DSR, DCD and RI are not supported (DB9 pins 4 and 6 only looped together; 1 and 9 open)
- The DB9 is male (PC side), with the same gender and pin-out as a PC serial port, so a PC needs a null-modem cable
- The product page's "Serial Loopback Test" tutorial link returns 404

## Positioning (kept apart from specs)
- Product page frames it as the way to connect microcontroller projects to RS232 devices and, with UC00A or UC00C, to build a USB-to-RS232 converter

## Price band
RM22.05 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ttl-uart-to-rs232-converter

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-ttl-uart-to-rs232-converter
