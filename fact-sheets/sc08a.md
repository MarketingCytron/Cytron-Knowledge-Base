# Product fact sheets

## Product name
8 Channel Servo Controller (SC08A)

## Aliases
SC08A, SC08A Servo Controller, 8 Channel Servo Controller, Cytron SC08A, SC08A 8 Channel Servo Controller

## What it is
A stand-alone 8-channel RC servo controller board (PIC16F1827) commanded over 5 V TTL UART at 9600 baud from a PC via UC00A or from a microcontroller. Two boards can be linked to control 16 servos; servo power is a separate supply on a terminal block and there is no on-board regulator.

## Specs and functions
- Servo channels: 8, driven independently (User's Manual V1.0)
- Extendable to 16 channels: two controllers linked together to drive 16 servos (User's Manual V1.0)
- Servo pulse range: 0.5 ms to 2.5 ms (User's Manual V1.0)
- Resolution: 8000 steps = 0.25 µs; pulse width = (0.25 µs × position) + 0.5 ms, position 0–8000 (User's Manual V1.0)
- Optional servo ramping: one of 100 ramp rates per servo; speed byte 0–100, 1 = slowest, 100 = fastest, 0 = faster than 100 (User's Manual V1.0)
- Servo activation for each channel: any channel can be activated or deactivated; initial status is deactivated (User's Manual V1.0)
- Optional position reporting: request the position of an individual servo; 2-byte reply (User's Manual V1.0)
- Independent starting position command for each channel, applied at the next start-up, 0–8000; reply byte 0x04 (User's Manual V1.0)
- UART: 9600 baud rate, TTL level (User's Manual V1.0)
- UART command set: activate/deactivate (mode 110, 2 bytes), position and speed (mode 111, 4 bytes), position reporting (mode 101, 1 byte), starting position (mode 100, 3 bytes); channel 0 = all channels (User's Manual V1.0)
- Controller supply: 5 V, from UC00A (PC use) or shared from the host microcontroller board (User's Manual V1.0)
- Servo supply: independent source on the blue terminal block; 4.8 V to 9 V (standard 4.8 V to 6.0 V); some servos need 7.2 V (User's Manual V1.0)
- Microcontroller: PIC16F1827 (User's Manual V1.0)
- JP11 mini jumper: "1-8" for a single board or the first board, "9-16" for the second board (User's Manual V1.0)
- LEDs: orange servo power indicator; green 5 V for PIC indicator (User's Manual V1.0)
- Buttons: servo test (drives servos to the end position); reset (stops all pulse generation, servos free-run) (User's Manual V1.0)
- Connectors: two 4-way UART/expansion headers (U_1, U_2) (User's Manual V1.0)
- Packing list: 1 × SC08A main board, 1 × 2510H-04 connector with terminal pins, 1 × 2561-04 connector with terminal pins, 1 × mini jumper for JP11 (User's Manual V1.0)
- Warranty: 6 months (User's Manual V1.0); 12 months (product page, read 2026-10-16)
- Size: 49 mm × 46 mm (product page)
- Ramping: one of 100 ramp rates per servo; resolution 0.25 µs (8000 steps); UART 9600 baud (product page)

## Interfaces and compatibility
- Arduino sample sketches (CytronTechnologies/Arduino_SC08A): Arduino UNO or CT-Uno on the hardware UART (D1 TX → SC08A RX; D0 RX ← SC08A TX for position reporting), 9600 baud; activate all channels first, then send position and speed
- PC: UC00A USB-to-UART converter plugged into the 4-way UART connector; driver creates a virtual COM port; SC08A takes its 5 V from the UC00A (User's Manual V1.0)
- Microcontroller: 5 V TTL UART and 5 V supply, minimum 3 wires; TX/RX cross-connected; SC08A TX only needed for position reporting (User's Manual V1.0)
- Only one host (computer or microcontroller) may be connected at a time (User's Manual V1.0)
- Expansion: second SC08A joined by a separate 4-way interlink cable via U_1 or U_2; board 2 jumper at "9-16"; board 2 channel S1 is addressed as S9 (User's Manual V1.0)
- Sample code: SK40C_16F877A_SC08A (PICC Lite, PIC16F877A on SK40C, also PIC16F876A) (User's Manual V1.0); GitHub SC08A_PIC16F877A (Feb 2011, Apr 2014) and SC08A_PIC18F4520 (May 2012) (GitHub)
- PC GUI "SC08A Servo Control Panel" for 8 or 16 servos; GitHub GUI_SC08A, VB 2010 Express project, July 2012 (User's Manual V1.0, GitHub)
- Wireless servo control tutorial with XBee series 1 and SKXBee (GitHub)
- Servo named in the manual's speed table: Cytron C36S (User's Manual V1.0)

## Use cases
- Driving 8 RC servos from a PC through UC00A and the SC08A Servo Control Panel
- Driving RC servos from a PIC microcontroller (SK40C) over UART
- Linking two boards for 16-servo projects
- Wireless servo control over XBee (Cytron tutorial)
- Robotics using RC servos: humanoid robots, biologically inspired robots, robotic arms (User's Manual framing)
- Cytron tutorial: [Quadruped Robot with SC08A Servo Controller](https://my.cytron.io/tutorial/quadruped-robot-with-sc08a-servo-controller)

## Known limitations
- Do not use speed 0 with position reporting; the servo oscillates (Cytron Arduino sketch note)
- No on-board regulator: the servo supply goes directly to the servos; over-supply voltage may spoil the servo motor (User's Manual V1.0)
- Servo power must be connected correctly before servos are plugged in, else all servo motors will be damaged (User's Manual V1.0)
- Servo headers are not polarised; a servo plugged in backwards may be destroyed (User's Manual V1.0)
- Controller needs its own 5 V from the UC00A or the host (User's Manual V1.0)
- Only one host may be connected at a time (User's Manual V1.0)
- The expansion cable must not be used to connect the SC08A to a microcontroller (User's Manual V1.0)
- Wrong UART connection can spoil the SC08A and the host (User's Manual V1.0)
- Position reporting is not executed for channel 0 (User's Manual V1.0)
- Reset stops all pulses; servos free-run until re-activated (User's Manual V1.0)
- Only UART at 9600 baud is described; no I2C, SPI, PWM-input or RC receiver input, and no baud-rate change command (User's Manual V1.0)
- Pulse-width-to-angle correspondence varies between servo manufacturers (User's Manual V1.0)
- Speed-vs-time figures are approximate and vary with the servo (User's Manual V1.0)

## Positioning (kept apart from specs)
- User's Manual: 8-channel servo controller, extendable to 16 channels, with position reporting, per-channel activation, start-up position and ramping, for RC servo robotics (humanoid, biologically inspired robots, robotic arms)

## Price band
RM65.10 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-8-channel-servo-controller

## Datasheet
https://drive.google.com/file/d/0BzFWfMiqqjyqem1oQnlXUk4yaXc/view

## Source type
Datasheet

## Source link
https://www.gotronic.fr/pj2-38783-nt-3349.pdf
