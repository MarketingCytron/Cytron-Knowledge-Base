# Product fact sheets

## Product name
Robo Uno Shield

## Aliases
SHIELD-ROBO-UNO, Robo Uno Shield, Robo Uno Shield for Arduino, Robo Uno, Robo Uno Shield: The All-in-One Robotics Shield

## What it is
An Arduino Uno-form-factor robotics shield with a 2-channel DC motor driver, 4 servo ports, 6 Grove ports, a Maker Port and a built-in single-cell LiPo/Li-ion charger. It is powered from 3.6–6 V through its own VIN terminal, LiPo port or micro-USB.

## Specs and functions
- Product code: SHIELD-ROBO-UNO
- Datasheet: Rev 1.0, February 2025 (spec table titled "Absolute Maximum Ratings")
- Power input voltage (USB, LiPo or VIN): 3.6–6 V
- VIN terminal block: 3.6–6 V, reverse polarity protection
- LiPo connector: JST PH2.0, single-cell LiPo / Li-ion; rechargeable via the shield's micro-USB port; protected from overcharge and over-discharge
- Micro-USB port: powers the shield and charges the battery only; no data or code upload
- Digital input voltage: low 0–0.5 V, high 2.7–5 V
- Digital output voltage: low 0–0.5 V, high 4.2–5 V
- Analog input voltage: 0–5 V
- Motor and servo voltage: equal to the power input voltage (VUSB − 0.4 V when powered from USB; VLiPo or VIN when only one of those is connected)
- DC motor driver: dual-channel H-bridge, 2 DC motors
- Maximum DC motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds)
- DC motor driver PWM frequency: 20 kHz max
- Motor driver truth table: Low/Low = Brake; High/Low = Forward; Low/High = Backward; High/High = Coast (outputs Hi-Z)
- Motor test buttons (motor runs at full speed) and motor status LEDs: MxA forward, MxB backward
- Servo ports: 4 x RC servo, signal on D9, D10, D11, D12; V+ equal to the power source voltage
- Total 5V output current (Grove ports): 400 mA max
- Grove ports: 6; Maker Port: 1 (shared with Grove 4)
- RGB LEDs on D13 (user-programmable)
- Piezo buzzer on D8 (bottom side) with mute switch
- Programmable buttons on D2 and D3
- Status LEDs for the Grove-port pins (on when the pin is high); launch material: "2x RGB LEDs / 10x GPIO LEDs"
- On/Off switch, power LED, reset button (resets the shield and the microcontroller)
- Operating temperature: −20 to 85 ℃
- Motor driver IC: [NOT STATED]
- Dimensions: [NOT STATED]
- Charging current: [NOT STATED]

## Interfaces and compatibility
- DC motor pins: datasheet Table 1 lists M1A D4, M1B D5, M2A D6, M2B D7; Cytron's example code uses Motor 1 PWM = D5, DIR = D4 and Motor 2 PWM = D6, DIR = D7 (`CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);`)
- Grove 1: A0, A1; Grove 2: A2, A3; Grove 3: A1, A3 (as printed in the datasheet); Grove 4: A4 (SDA), A5 (SCL); Grove 5: D0 (RX), D1 (TX); Grove 6: D2, D3
- Maker Port: A4, A5; compatible with QWIIC / Stemma QT / Grove (with conversion cable)
- Datasheet and GitHub name Arduino Uno and Maker UNO
- Launch compatible-board list: Maker Uno / Maker Uno X / Maker Uno Plus; Maker Uno RP2040; Cytron Uno; Uno Compatible (CH340); Official Arduino Uno Rev3; Official Arduino Uno R4 Minima; Official Arduino Mega 2560 Rev3; Wifi Uno ESP8266; Official Arduino Zero, Leonardo and GIGA R1 listed as "Not tested"
- Libraries in Cytron examples: Cytron Motor Drivers Library (CytronMotorDriver.h), Servo, Adafruit_NeoPixel, U8g2
- Packing list: 1x Robo Uno Shield board, 1x Small Philips Screwdriver, 4x Grove to Female Header Cable

## Use cases
- Building robots using Arduino Uno, Arduino Mega, Maker Uno, or compatible boards
- Mobile robot projects for the RBT syllabus (light, sound and movement)
- Teaching robotics with simplified wiring and power options (educators and training centres)
- Adding sensors and modules through Grove ports and the Maker Port without messy wiring
- Troubleshooting wiring vs code with status LEDs and motor test buttons

## Known limitations
- Power input 3.6–6 V only (absolute maximum); only single-cell batteries are supported
- Cannot be powered through the VIN pin of the microcontroller (e.g. Arduino Uno, Maker UNO)
- The shield's micro-USB port cannot be used for data communication or uploading code
- Motor and servo voltage equals the power input voltage; no separate motor supply
- Motor current 1 A continuous per channel; 1.5 A peak only for < 5 seconds
- Total 5V output on the Grove ports limited to 400 mA
- Datasheet advises one power source at a time (LiPo and VIN together not recommended)
- If the board will not turn on with a battery connected, the battery must be charged to activate the protection circuit
- Grove 4 and the Maker Port share A4/A5; buttons D2/D3 share pins with Grove 6
- Motor test buttons run the motor at full speed; motor direction depends on wiring
- Protection stated in the datasheet is limited to VIN reverse polarity and battery overcharge / over-discharge

## Positioning (kept apart from specs)
- "The All-in-One Robotics Shield"
- Launch pitch: "Designed for Beginners and Intermediate Learners"
- "Simply add your preferred microcontroller, motor, robot base, and sensors"
- Part of Cytron's Robo series (alongside Robo Pico)

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit
