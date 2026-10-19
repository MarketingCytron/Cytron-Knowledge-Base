# Product fact sheets

## Product name
URC10 Sumo Robot Controller

## Aliases
URC10, URC10 Sumo Robot Controller, 2x10A UNO Robot Controller, Cytron Uno Robot Controller

## What it is
An Arduino UNO-compatible controller board with an onboard 2-channel brushed DC motor driver, made for sumo robots. It is programmed from the Arduino IDE over USB Micro-B through a CH340 USB-to-UART converter.

## Specs and functions
- Product code: URC10
- Power Input Voltage (Vin): 8 – 25 VDC (datasheet spec table), on the Power Input Terminal: VM = positive, GND = negative
- Bottom-layer silkscreen reads "POWER (7-24V)"; the datasheet spec table value (8 – 25 VDC) applies
- No reverse polarity protection: connecting in reverse polarity "will damage the board instantaneously"
- Motor driver: 2 channels (Motor 1, Motor 2), PWM + DIR control; silkscreen "2x10A", "MOTOR1 (10A)", "MOTOR2 (10A)"
- Maximum Motor Current: 10 A continuous, 30 A peak (< 10 seconds), per channel
- Motor truth table: PWM Low = brake; PWM High + DIR Low = forward; PWM High + DIR High = backward (actual direction depends on wiring; swapping MA and MB reverses it)
- Motor Driver Port (connected internally): Motor 1 DIR D4, PWM D5; Motor 2 DIR D7, PWM D6
- Logic Input Voltage: Low 0 – 0.7 V, High 1.5 – 5.0 V
- DC +3V3 Output Maximum Current: 500 mA
- DC +5V Output Maximum Current: 1000 mA
- IO pin Maximum Current: 20 mA
- USB Micro B connector: upload Arduino program from PC; Serial Monitor debugging
- USB-to-UART: CH340
- Power LED; Motor Status LEDs (M1A/M2A forward, M1B/M2B backward); TX/RX LEDs
- Test Buttons M1A, M1B, M2A, M2B (run the motor at full speed); Reset Button
- Board size: 99.70 mm × 75.57 mm; 4 × ⌀3 mm mounting holes spaced 94.62 mm × 70.49 mm
- Datasheet: Rev 1.0, March 2019; User's Manual: V1.2, April 2019
- Microcontroller: [NOT STATED]
- Over-current / thermal protection: [NOT STATED]
- Motor PWM frequency: [NOT STATED]
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- Packing list: [NOT STATED]

## Interfaces and compatibility
- Arduino UNO Standard Female Header: takes compatible Arduino shields, except shields that use D4, D5, D6, D7 (connected to the motor driver internally)
- Power + motor screw terminal block order: M1A, M1B, VM, GND, M2A, M2B
- Digital Port × 6 (GND, +5V, Signal): D0 – D3 and D10 – D13; D0 and D1 are used for serial communication
- Analog/Digital Port × 6 (Signal, +5V, GND): A0 – A5
- HC-SR04 Ultrasonic Sensor Port × 2 (+5V, TRIG, ECHO, GND): Sensor 1 ECHO D8, TRIG D9; Sensor 2 ECHO D10, TRIG D11
- I2C Port (SCL, SDA, PWR, GND): PWR is +3V3 by default; +5V by cutting the trace and soldering the center pad to the 5V pad on the bottom layer
- Power Port: NC, IOREF, RESET, +3V3, +5V, GND, GND, VIN
- Arduino UNO Standard ISP Port: load program with an AVR programmer; also usable for SPI
- Arduino IDE; user manual screenshots show Board "Arduino/Genuino Uno"
- CH340 driver from Cytron: Windows CH341SER.EXE, macOS CH341SER_MAC.ZIP
- Cytron Motor Drivers Library (Library Manager: "cytron motor drivers library"); `#include <CytronMotorDriver.h>`; `CytronMD motorL(PWM_DIR, 5, 4)` and `CytronMD motorR(PWM_DIR, 6, 7)`; `setSpeed()` from -255 to 255
- Sample code: GitHub CytronTechnologies/URC10SumoRobot (edge sensors D12/D11, side opponent sensors D3/D10, front opponent sensors A0/A1/A2, external start button D13, LEDs on D0/D1 driven active low)
- IR Sumo Start module (pack's Auto Kit notes): S to D2, + to 5V, − to GND; read D2 with `INPUT` (HIGH = run, LOW = stop)
- Cytron's Hackster build guide uses an 11.1V 3-cell 1300mAh LiPo, 4 × 12V 380RPM DC geared motors (two per side on one channel), 5 × IR opponent sensors and 2 × IR line tracking modules
- MicroPython / CircuitPython / MakeCode: [NOT STATED]

## Use cases
- Sumo robot controller
- Autonomous sumo robot (Cytron URC10SumoRobot sample: search, attack and edge back-off)
- "Building a Sumo Robot" with URC10 (Cytron Hackster guide linked from the user manual)
- Auto sumo robot started and stopped by an IR Sumo Start module (pack's Auto Kit notes)

## Known limitations
- No reverse polarity protection; reverse connection damages the board instantly
- Vin must stay within 8 – 25 VDC
- Motor current: 10 A continuous; 30 A peak only for < 10 seconds
- D4, D5, D6, D7 are taken by the motor driver; avoid shields that use them
- D0 and D1 are the serial pins (upload and Serial Monitor)
- HC-SR04 Sensor 2 uses D10 and D11, the same pins as the Digital Port's D10/D11 (used by the right opponent and right edge sensors in the sample code)
- +5V output limited to 1000 mA, +3V3 to 500 mA, each IO pin to 20 mA
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring; swap MA/MB to reverse
- No onboard start button; the sample code's start button on D13 is external
- Sample code start delay is 1 s; the pack notes say most sumo rules require 5 s
- I2C port PWR is 3.3 V by default; 5 V needs a solder-jumper change
- Needs the CH340 driver for USB programming
- Over-current and thermal protection: [NOT STATED]

## Positioning (kept apart from specs)
- Named "Sumo Robot Controller" on the datasheet and user manual; the board silkscreen calls it "2x10A UNO ROBOT CONTROLLER"

## Price band
RM156.24 (Cytron product page "Sumo Robot Controller R1.1", read 2026-10-19)

## Product page
https://my.cytron.io/p-sumo-robot-controller-r1.1

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

