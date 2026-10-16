# Product fact sheets

## Product name
Advanced Auto-Calibrating Line Sensor (LSA08)

## Aliases
LSA08, Advance Line Following Sensor Bar, LSA08 Line Sensor, Cytron LSA08, Advanced Auto Calibrating Line Sensor, Auto-Calibrating Line Sensor Bar

## What it is
An 8-sensor line-following sensor bar with sensors spaced 16 mm apart, an on-board 2x8 LCD with SEL and MODE buttons, and auto-calibration. It outputs the line position over UART, as an analog voltage, or as 8 parallel digital lines, and provides a junction pulse and junction counter.

## Specs and functions
- Sensors: 8 sensor pairs (S0–S7) spaced at 16 mm (user manual)
- Operating voltage: 7.5 V min, 12 V typical, 20 V max (user manual); typical wiring 9–12 V (user manual)
- Current consumption at 12 V: 25.3 mA min, 25.5 mA typical, 130 mA max; "typically around 26mA" (user manual)
- Input signal VIH 2–5 V; VIL 0–0.8 V; output signal 5 V (user manual)
- Maximum current per I/O signal pin: 20 mA (user manual)
- Sensing distance from board: 1 cm min, 3 cm typical, 5 cm max (user manual)
- Minimum line width: 15 mm (user manual)
- Refresh rate: 100 Hz (user manual); Cytron Tindie listing says up to 200 Hz
- Line position: 0 (sensor 0) to 70 (sensor 7), 35 = between S3 and S4, linear (user manual)
- Analog output: 0 V to 4.5 V = position 0 to 70; 5 V = no line; Position = (AN voltage / 4.5 V) x 70 (user manual)
- UART: 1 start bit, 8 data bits, no parity, 1 stop bit; baud settings 0 = 9600, 1 = 19200, 2 = 38400, 3 = 57600, 4 = 115200, 5 = 230400 (user manual)
- UART output modes: 0 = no output; 1 = one byte of sensor digital values (LSB = sensor 0, MSB = sensor 7); 2 = one byte line position 0–70, 255 = no line; 3 = 9-byte raw packet, header 0x00 + 8 raw sensor bytes (user manual)
- UART data streams from TX only while UEN is pulled low (user manual)
- UART command packet: ADDRESS, COMMAND, DATA, CHECKSUM (lower byte of ADDRESS + COMMAND + DATA); max 20 ms between bytes; setting commands answered with "OK" (user manual)
- UART commands: C 0x43 calibrate (0); L 0x4C line mode (0 = Light-On, 1 = Dark-On); T 0x54 threshold (0–7); J 0x4A junction width (3–8); A 0x41 UART address (0–255); B 0x42 LCD backlight (0–10); S 0x53 LCD contrast (0–255); R 0x52 baud setting (0–5); D 0x44 UART output mode (0–3); 0x50 junction information (0 = clear counter, 1 = read counter); 0x4F line/sensor information (1 = sensor byte, 2 = line position) (user manual)
- Default settings: Line Mode Light On; Threshold 4; Junction width 5; UART address 1; Baudrate 0 (9600); UART mode 0; LCD backlight 2 (user manual)
- Calibration: MODE twice to CALB, SEL to start, swing the sensors across bright and dark surfaces; values saved to non-volatile memory; also started by UART command C (user manual)
- Junction pulse (JPULSE): pulse generated each time the bar crosses a junction at least Junction Width sensors wide; internal junction counter readable over UART (user manual)
- LCD: shows line position and bar chart; "****" = no line; backlight 0–10 (0 = off) (user manual)
- Power polarity protection (user manual)
- Dimensions: PCB 135 mm x 45.7 mm; mounting holes 127.3 mm x 38 mm apart; sensor pitch 16 mm (user manual drawing)
- Packing list: 1 x LSA08 PCB, 1 x LSA08 cable connector (user manual)

## Interfaces and compatibility
- Port A (10 pins, pin 1 = square pad): 1 TX, 2 RX, 3 UEN (active low), 4 AN, 5 JPULSE, 6–8 not used, 9 VIN (12 V), 10 GND (user manual)
- Port B (10 pins): 1–8 O0–O7 digital outputs (5 V = line detected), 9 VIN (12 V), 10 GND (user manual)
- Board can be powered from VIN/GND of either Port A or Port B; both ports may be used at once (user manual)
- TX is floating/high-impedance when not sending; RX is weakly pulled up (user manual)
- Multiple LSA08 on one UART by giving each a unique address; multiple on analog need one ADC channel each (user manual)
- Manual example controllers: SK40C with MD10C, MC40A, IFC system (IFC-MB00, IFC-PC00, IFC-AI08, IFC-DI08, IFC-BH02, IFC-BL02, IFC-CP04), MC40SE; DC Geared Mobile Robot Base Set HD-BSC-SPG-G (user manual)
- Software: Cytron LSA08 C library (LSA08.h) for PIC with C Library Manual V1.1 Jan 2013; example projects for SK40C+MD10C, MC40A (analog and UART PID), IFC in GitHub repo https://github.com/CytronTechnologies/Cytron_LSA08 (user manual, GitHub)
- Library position convention: -35 to 35 with centre 0; 127 = no line (library manual)

## Use cases
- Line following for embedded systems or robots (user manual)
- Cross-junction detection and counting using JPULSE or the UART junction counter (user manual)
- Line following on reflective or glossy surfaces and on red, green, blue, white, black or grey surfaces (user manual)
- PID line-following robots with SK40C, MC40A or IFC controllers (user manual)

## Known limitations
- Operating voltage 7.5–20 V; not a 5 V or 3.3 V-powered board (user manual)
- Outputs are 5 V signals; I/O pins limited to 20 mA (user manual)
- Minimum line width 15 mm; sensing distance 1–5 cm (user manual)
- Refresh rate 100 Hz (user manual)
- Default UART mode is 0 (no output); UART data only streams while UEN is low (user manual)
- Incomplete UART packets are discarded after 20 ms (user manual)
- Polling line position by command is slower than streaming with UEN (user manual)
- Only one Cytron library exists and it is for PIC C; no Arduino library (library manual, GitHub)
- Hidden debug mode exits only by power cycling (user manual)
- Manual (2012) states warranty 6 months; product page states 12 months

## Positioning (kept apart from specs)
- "Advance" line sensor bar with LCD and on-board buttons for instant configuration without a computer (user manual)
- Auto-calibration minimises setup effort for line-following robots (user manual)
- Low current consumption and polarity protection (user manual)

## Price band
RM204.75 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-advanced-auto-calibrating-line-sensor

## Datasheet
https://drive.google.com/file/d/0BzFWfMiqqjyqXzFaMTNHMy1pWUE/view

## Source type
Datasheet

## Source link
https://raw.githubusercontent.com/CytronTechnologies/Cytron_LSA08/master/LSA08_User_Manual.pdf
