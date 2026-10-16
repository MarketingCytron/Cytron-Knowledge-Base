# Product fact sheets

## Product name
Cytron 8 Channels RC Servo Controller Shield for Arduino (SHIELD-SERVO)

## Aliases
SHIELD-SERVO, SHIELD-Servo, Shield-Servo, Cytron Servo Shield, Servo Controller Shield, 8 Channels RC Servo Controller Shield for Arduino, Cytron 8 Channel Servo Shield

## What it is
An Arduino shield that controls up to 8 RC servo motors over a UART command protocol from an Arduino-compatible board, a PC (via UC00A/UC00C USB-to-serial) or another microcontroller. It has a built-in 5 V switching regulator (4 A continuous, 5 A peak) fed from a 7–25 V servo supply input.

## Specs and functions
- Servo channels: 8, controlled independently or simultaneously (User's Manual V1.1)
- Servo supply input VM: 7 V to 25 V; absolute maximum rating 7 V min / 25 V max, VM current 5 A max (User's Manual V1.1)
- On-board 5 V switching regulator for the servos: 4 A continuous, 5 A peak, total for all servos (User's Manual V1.1); product page states "5V at 5A (peak)"
- Servo pulse range: 0.5 ms to 2.5 ms (User's Manual V1.1)
- Position resolution: 0.25 µs; position value 0–8000 (13-bit); pulse width = (0.25 µs × position) + 0.5 ms (User's Manual V1.1)
- Speed per command: 0–100; 1 = slowest, 100 = fastest, 0 = full speed (faster than 100) (User's Manual V1.1)
- Host interface: UART, TTL/CMOS 5 V logic; factory default baud rate 9600; baud rate saved in non-volatile memory (User's Manual V1.1)
- Arduino UART pins selected by DIP switch: shield TX on D0, D2, D10 or D12; shield RX on D1, D3, D11 or D13 (User's Manual V1.1)
- Alternative 6-pin UART header for UC00A/UC00C: DTR (reset via 0.1 µF), TX, RX, VSEL (5 V in, powers the controller), CTS (not connected), GND (User's Manual V1.1)
- UART command set: activate/deactivate channel (mode 110, 2 bytes), position and speed (mode 111, 4 bytes), position reporting (mode 101, 1 byte, 2-byte reply), starting position at next start-up (mode 100, 3 bytes, reply 0x04); channel 0 = all channels (User's Manual V1.1)
- Servos are deactivated at power-up until the activate command is sent (User's Manual V1.1)
- Servo signal outputs S1–S8: TTL/CMOS 5 V logic; inputs 5 V logic-level compatible (User's Manual V1.1)
- LEDs: servo power indicator (MPWR) and small green logic power indicator (PWR) (User's Manual V1.1)
- Buttons: reset (shield controller only, not Arduino) and test (runs every connected servo in a predetermined movement) (User's Manual V1.1)
- Solder jumper K: share the Arduino 5 V for the servos or supply the Arduino from a single source (User's Manual V1.1)
- Wrong-polarity protection on the VM input (User's Manual V1.1)
- Dimension: 7.4 cm × 6.6 cm (User's Manual V1.1)
- Warranty: 6 months (User's Manual V1.1); 12 months (product page, read 2026-10-16)
- Arduino library "Cytron Servo Shield" version 2.0.0 (Arduino Library Manager / GitHub); functions init, setChannel, position, angle, getPosition, getAngle, setStartPosition, setStartAngle, registerErrorCallback (GitHub)
- Library angle() maps 0–180° to positions 156–7260; getPosition() timeout 100 ms; setStartPosition() waits up to 5 s for 0x04 (GitHub)
- PC GUI "Shield-Servo GUI" written in VB.net (Visual Studio Community 2015), source on the repository's visual-basic branch (User's Manual V1.1, GitHub)

## Interfaces and compatibility
- Arduino-compatible hosts named: Arduino/Genuino UNO, Mega, CT-UNO, CT-ARM (User's Manual V1.1)
- 10/8/6-way Arduino headers to the host (User's Manual V1.1)
- PC control through UC00A or UC00C USB-to-serial converter plugged into the 6-pin header; more than one UC00A/UC00C may be connected to control more than one shield (User's Manual V1.1)
- Any other microcontroller with 5 V TTL UART via the 6-pin header; direct connection to SKXBee mentioned (User's Manual V1.1)
- Logic power comes from the Arduino header or from UC00A/UC00C VSEL, not from VM (User's Manual V1.1)
- Servo power from VM/GND through the regulator, or from the Arduino 5 V by soldering jumper K (User's Manual V1.1)
- Software: Arduino library (hardware serial or SoftwareSerial), sample sketch "Shield Servo Example.ino" for CT-UNO, VB.net GUI for PC (User's Manual V1.1, GitHub)
- Packing list: 1 × SHIELD-Servo board; manual and sample code are downloads (User's Manual V1.1)

## Use cases
- Controlling 8 RC servo motors from an Arduino main board over UART
- Controlling servos from a computer through UC00A/UC00C and the Shield-Servo GUI
- Robotics using RC servos: humanoid robots, biologically inspired robots, robotic arms (User's Manual V1.1 framing)
- Offloading servo speed/position control from the host so the host can run other routines

## Known limitations
- Regulator output is 4 A continuous / 5 A peak total for all 8 servos (User's Manual V1.1)
- Powering servos from the Arduino 5 V (jumper K) is "strongly not recommended" for more than one small servo; Arduino 5 V is normally only 1 A max (User's Manual V1.1)
- If jumper K is used (Arduino 5 V powering servos), do NOT connect any power to VM and GND (User's Manual V1.1)
- VM absolute maximum 25 V, minimum 7 V (User's Manual V1.1)
- Servos are deactivated at start-up; the activate command must be sent first (User's Manual V1.1)
- Position reporting command with channel 0 is not executed (User's Manual V1.1)
- UART is 5 V logic; the 6-pin header TX/RX "should be interfaced to 5V logic UART" (User's Manual V1.1)
- Only UART control is described; no I2C, SPI, PWM-input or RC-receiver input (User's Manual V1.1)
- No command to change the baud rate is documented; default 9600 (User's Manual V1.1)
- Reset button resets the shield controller only, not the Arduino; do not press during operation (User's Manual V1.1)
- Manufacturing test point header must not be connected or shorted (User's Manual V1.1)
- Pulse-width-to-angle correspondence varies between servo manufacturers (User's Manual V1.1)
- GUI project needs Visual Studio Community 2015 or newer and may need the latest .NET Framework (User's Manual V1.1)

## Positioning (kept apart from specs)
- Product page: 8-channel RC servo controller shield for Arduino with built-in 5 V at 5 A (peak) switching regulator, supply 7 V to 25 V
- User's Manual: "reliable yet user friendly RC Servo motor controller to hobbyist and students"; "the enhanced version from SC08A" with on-board regulator and UC00A/UC00C interface; UART "present a flexible, fast and easy to use feature"

## Price band
RM79.80 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-8-channels-rc-servo-controller-shield-for-arduino

## Datasheet
https://docs.google.com/document/d/191P6FwTgJ_dWhAhB3eWfP0YMSbI4_7Kehgzw3pYy-AY/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/191P6FwTgJ_dWhAhB3eWfP0YMSbI4_7Kehgzw3pYy-AY/view
