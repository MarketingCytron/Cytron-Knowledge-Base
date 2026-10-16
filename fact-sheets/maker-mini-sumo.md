# Product fact sheets

## Product name
Maker Mini Sumo Controller

## Aliases
MAKER-MSUMO, Maker MSumo, Maker Mini Sumo, Maker Mini Sumo Controller

## What it is
A mini sumo robot controller based on the ATmega328P (Arduino Nano/Uno compatible), with a 2-channel motor driver and ports for opponent sensors, edge sensors, a start module, an RC servo and 2 GPIO. It is programmed from the Arduino IDE with the Cytron Maker Sumo Library.

## Specs and functions
- Product code: MAKER-MSUMO
- MCU: ATmega328P ("Arduino Nano/Uno Compatible (Powered by ATMEGA328P)")
- Programming and serial: USB Micro-B (upload Arduino program, Serial Monitor); Tx/Rx LEDs; reset button
- Cytron's Ikedo Mini Sumo Robot Pro setup guide installs the WCH CH341SER USB driver
- Power input (Vin): 7.0–18.0 VDC, through the Battery Terminal (VB+ positive, VB- negative/ground)
- Reverse polarity protection on Vin (product page: reconnect with the correct polarity and it will work again)
- On/off switch with MOSFET latching circuit: "Vibration proof" (datasheet) / "Shockproof" (product page); once on, a lost switch contact does not turn the board off
- Switching regulator for +5V; DC +5V output 500 mA max total
- Battery voltage readable in code (VB+ via voltage divider to A7, `readBatteryVoltage()`)
- Motor driver: 2 channels, 3.0 A continuous and 6.0 A peak (< 5 seconds) per channel; product page describes a "discrete MOSFETs H-Bridge design"
- Motor PWM frequency: DC to 20 kHz
- Motor truth table: PWM Low = brake; PWM High + DIR Low = forward; PWM High + DIR High = backward (actual direction depends on wiring; swapping MxA and MxB reverses it)
- Motor test buttons (run the motor at full speed without code) and motor status LEDs (MLA/MRA forward, MLB/MRB backward)
- Digital input: low 0–0.5 V, high 1.7–5.0 V; analog input 0–5.0 V
- Pins (Arduino): left motor PWM D3 / DIR D4; right motor PWM D11 / DIR D10
- 5 × opponent sensor inputs (digital, internally pulled up to +5V, active low, with status LEDs): Left D12, Right D13, Front-Center D6, Front-Left D5, Front-Right D7; MAKER-OBJECT ports on the bottom layer are wired in parallel
- 2 × edge sensor inputs (analog/digital): Left A0, Right A1
- 2 × GPIO ports (digital in/out or analog in): GPIO1 A2, GPIO2 A3
- 1 × start module input (digital) D2, in parallel with the onboard start button, pulled high to +5V, active low, with Start LED; for an external start button or IR start module
- 1 × RC servo output D9
- 1 × programmable user LED A4
- 1 × potentiometer A5
- 1 × 3-way mode selection DIP switch on A6 (up to 8 configurations; `readDipSwitch()` returns 0–7, SW1 = MSB)
- 1 × piezo buzzer D8 (bottom layer, plays tones/melody)
- Power LED
- Dimensions: 92 mm × 36 mm (product page)
- Packing list: 1 × Maker Mini Sumo Controller
- Warranty: generally 12 months (product page)
- Datasheet: Rev 1.0, November 2019

## Interfaces and compatibility
- Arduino IDE with the Cytron Maker Sumo Library (version 1.2.3, architectures=avr, depends on Servo); install via Library Manager by searching "Cytron Maker Sumo Library"; `#include "CytronMakerSumo.h"`; call `MakerSumo.begin()` first
- Official examples: AutoSumo, CalibrateEdgeSensors, RcSumo, TestInputs, TestOutputs (File > Examples > Cytron Maker Sumo Library)
- Library functions: begin, readDipSwitch, readBatteryVoltage, stop, moveForward, moveBackward, turnLeft, turnRight, setMotorSpeed, setServoPosition, playTone, playMelody, calibrateEdgeSensors, readEdgeSensorThreshold, isEdgeDetected
- Sensor, GPIO, start and servo ports: S (signal), + (+5V), - (GND); screw terminals for sensors and motors (solderless)
- Opponent sensors: Maker Object (used in the Ikedo V2 kit); edge sensors: Maker Reflect S (used in the Ikedo V2 kit)
- RC mode: RC receiver on GPIO1/GPIO2 (Cytron tutorial tested Flysky and HotRC; RcSumo example)
- PS2 controller: Cytron tutorial wires DATA→D2, CMD→D7, ATT→D6, CLK→D5 with `ps2x.config_gamepad(5, 7, 6, 2, true, true)`, with object sensors removed
- Included in the Ikedo Mini Sumo Robot V2 kit (KIT-IKEDO-MSV2-S), with 2 × 600RPM 6V DC Micro Metal Gearmotor and a 7.4V 450mAh LiPo battery
- Resources: datasheet, 3D CAD, Arduino library and examples on GitHub
- MicroBlocks / CircuitPython / MakeCode / MicroPython: [NOT STATED]

## Use cases
- Sumo robot competitions, for beginners through professional sumo robot builders
- International Sumo robot competition 500g category
- Autonomous sumo robot (AutoSumo example; Ikedo Mini Sumo Robot V2 kit)
- RC category of Sumo robot competitions, and both RC and autonomous categories with the same robot
- Mini sumo robot controlled by a PS2 controller
- Mini sumo robot controlled by a Bluetooth controller (HC-05 or HC-06)

## Known limitations
- Motor current limited to 3.0 A continuous per channel; 6.0 A peak only for < 5 seconds
- Product page: a motor of more than 3A "will cause the motor driver chip to burn" and is not covered by warranty
- Warranty does not cover board modifications (e.g. adding external components), use in competition ("intense usage"), or misuse
- Over-current, thermal or short-circuit protection is not stated; reverse polarity protection is on Vin only
- Vin must stay within 7.0–18.0 VDC
- +5V output limited to 500 mA total across all ports
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring; swap MxA/MxB to reverse
- Opponent sensor and start inputs are active low
- Almost all pins are used by onboard functions; GPIO1 (A2) and GPIO2 (A3) are the expansion ports
- `tone()` interferes with PWM on pins 3 and 11 (both motor PWM pins); use the library's melody functions
- The Servo library (always attached by `begin()`) disables `analogWrite()` on pins 9 and 10
- I²C pins A4/A5 are used by the user LED and potentiometer; SPI pins D11/D12/D13 are used by PWM_R, OPP_L and OPP_R
- A6 (DIP switch) and A7 (battery sense) are analog-only
- Edge calibration is stored in EEPROM from address 0; user EEPROM writes there overwrite it
- Library declares architectures=avr only
- README sample snippets call bare `println(...)`, which does not compile; use `Serial.println(...)`
- PS2X library default pins (13, 11, 10, 12) clash with the board's pins
- No USB cable in the packing list
- Operating temperature: [NOT STATED]
- Arduino IDE board selection: [NOT STATED]

## Positioning (kept apart from specs)
- Product page title: "Maker Mini Sumo Controller: Simplifying Sumo Robot for Beginner"
- "the ultimate board for you - Whether you are a beginner who just started learning about Sumo robots or a professional robot builder who participates in international Sumo robot competitions"
- Designed with Team Ikedo Kogeki, "the winner of multiple Sumo robot competitions locally and internationally"

## Price band
- RM114.45 on the product page (RM108.73 each for 10 or more), 16 Oct 2026

## Product page
https://my.cytron.io/p-maker-mini-sumo-controller-simplifying-sumo-robot-for-beginner

## Datasheet
https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit
