# Product fact sheets

## Product name
Cytron PS2 Shield

## Aliases
SHIELD-PS2, Shield-PS2, Cytron PS2 Shield, PS2 Shield, PS2 Shield for Arduino

## What it is
An Arduino-form-factor shield that converts a SONY PS2 (DualShock) controller, wired or wireless, into a simple UART protocol so the Arduino can read button and joystick states and drive the controller's vibration motors. It is powered from the Arduino main board (5 V) and has stackable headers with jumper-selectable UART pins and baud rate.

## Specs and functions
- Product code: SHIELD-PS2
- Primary source: Shield-PS2 User's Manual V1.0, September 2013 (no datasheet exists)
- Input voltage (logic operation voltage): 4.5 V min, 5.5 V max
- Current consumption: 100 mA min, 150 mA typical, 500 mA max
- VIOH (logic input high level): 3.5 V min, 5.0 V typical, 5.5 V max
- VIOL (logic input low level): 0 V min, 0 V typical, 1.0 V max
- Power source: powered from the Arduino main board; "5V powered, low current consumption"
- Logic level: 5 V
- UART baud rate (jumper-selectable): 4800, 9600, 57600, 115200; the shield must be reset after changing the jumper
- UART RX pin (jumper-selectable): D0, D2, D8 or D10; default D2
- UART TX pin (jumper-selectable): D1, D3, D9 or D11; default D3
- Shield reset line: Arduino A1 (pull low to reset the shield)
- Controllers: SONY PS2 controller, wired or wireless; the controller automatically operates in analog mode
- Vibration motors: controllable (motor 1 on/off; motor 2 speed 0–255)
- Status LED (orange): blinking = no controller detected; steady low brightness = controller detected; steady high brightness = digital button pressed
- Power LED (green)
- Buttons: Arduino main board reset button (Arduino needs around 30 ms to be ready after reset); PS2 RST button (resets the shield only)
- Headers: stackable analog, power and digital I/O headers (JP4, JP7)
- Protocol: Arduino sends one command byte (decimal); 0–15 = digital buttons (reply 0 = pressed, 1 = not pressed); 16–19 = joystick X/Y axes (0–255, 128 neutral); 20–27 = joystick up/down/left/right values (0–100); 28 = connection status (1 = detected); 29 + value = motor 1 on/off; 30 + value = motor 2 speed 0–255; 31 = all buttons and joysticks in 6 bytes
- Packing list: 1 x Shield-PS2, 3 x mini jumper
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Onboard interface IC: [NOT STATED]

## Interfaces and compatibility
- Compatible boards: Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo and possibly other pin-compatible main boards; library README uses CT UNO
- Hardware serial option: D0/D1 (unplug the PS2 controller before uploading code); software serial options: D2/D3 (default), D8/D9, D10/D11
- SoftwareSerial RX restriction from the manual: Mega RX only on 10, 11, 12, 13, 50–53, 62–69; Leonardo RX only on 8, 9, 10, 11, 14, 15, 16
- PS2 connector socket for a wired controller or wireless receiver; no modification needed
- Arduino library: Cytron_PS2Shield — https://github.com/CytronTechnologies/Cytron_PS2Shield (ZIP install; examples ReadButton and ReadJoystick)
- Library API: Cytron_PS2Shield(rxpin, txpin) or Cytron_PS2Shield() for hardware serial; begin(baudrate); readButton(key); readAllButton() with ps_data[6]; vibrate(motor, value); reset(1/0); SERIAL_ERR flag
- Library constants: PS2_SELECT … PS2_SQUARE (digital), PS2_JOYSTICK_LEFT_X_AXIS … PS2_JOYSTICK_RIGHT_RIGHT (analog), PS2_CONNECTION_STATUS, PS2_MOTOR_1, PS2_MOTOR_2, PS2_BUTTON_JOYSTICK
- On Leonardo the library maps Serial to Serial1 for the hardware-serial constructor
- Controller sold separately: Cytron wired (PS-GP-1) or wireless (PS-GP-2) PS2 controller

## Use cases
- Reading joystick and button states of a PS2 controller as easily as reading UART data
- Remote-controlling Arduino robots with a wired or wireless PS2 controller
- Controlling the PS2 controller's vibration motors from the Arduino

## Known limitations
- Powered only from the Arduino's 5 V (4.5–5.5 V); up to 500 mA consumption
- Baud rate must match the jumper and the shield must be reset after changing the baud jumper
- Using hardware serial (D0/D1): programming may fail unless the PS2 controller is unplugged first
- On Mega and Leonardo only certain pins support SoftwareSerial RX (see manual table)
- A1 is used as the shield reset line
- Joystick analog values are not linear and have a large dead zone near the centre
- Compatibility is not guaranteed for PS2 controllers from other sources; the controller is not included
- Logic input high level minimum 3.5 V (3.3 V hosts not stated)

## Positioning (kept apart from specs)
- "a compact yet reliable PS2 Controller Converter"
- "Reading Joy-stick and button's state of PS2 controller will be as easy as reading UART data"

## Price band
- RM65.10 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-ps2-shield

## Datasheet
https://docs.google.com/document/d/1cifT1XqOquLffnu5J961wpKakSO8_LpV35v4sKSaIQU/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1cifT1XqOquLffnu5J961wpKakSO8_LpV35v4sKSaIQU/edit
