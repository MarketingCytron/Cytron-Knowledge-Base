# Product fact sheets

## Product name
MDD10A 10Amp 5V-30V DC Motor Driver (2 Channels) (Rev 2.0)

## Aliases
MDD10A, MDD10A Rev2.0, Cytron MDD10A, 10Amp 5V-30V DC Motor Driver (2 Channels), Dual Channel 10A DC Motor Driver

## What it is
A dual-channel, bi-directional driver for two brushed DC motors, powered from 5–30 V and controlled with a PWM and a DIR signal per channel from a microcontroller. Each channel is rated 10 A continuous and 30 A peak for up to 10 seconds.

## Specs and functions
- Product code: MDD10A; current revision Rev 2.0 (boards shipped after Jan 2017)
- Channels: 2 (bi-directional, brushed DC motors)
- Power input voltage: 5 V to 30 V (Rev 2.0); earlier boards 25 V max
- Maximum continuous motor current: 10 A per channel, tested in room temperature at 25°C
- Peak motor current: 30 A per channel, must not exceed 10 seconds
- Logic input high level: 3 V min, 5.5 V max
- Logic input low level: 0 V min, 0 V typical, 0.5 V max
- Logic level input: 3.3V and 5V (for PWM and DIR) (product page)
- Maximum PWM frequency: 20 kHz; actual output frequency is the same as input frequency
- Control modes: Sign-Magnitude PWM (PWM = speed, DIR = direction) and Locked-Antiphase PWM (PWM pin tied to logic high, PWM signal on DIR; 50% duty = stop); selected by wiring
- Truth table (each channel): PWM Low = both outputs low (DIR don't care); PWM High + DIR Low = A high, B low; PWM High + DIR High = A low, B high
- Fully NMOS H-Bridge; manual states no heat sink is required
- Solid-state components (no mechanical relay)
- Regenerative Braking (product page)
- 4 test buttons (M1A, M1B, M2A, M2B), 2 per channel
- Red LEDs M1A, M1B, M2A, M2B show current direction; green power LED
- Dimensions: 84.5 mm x 62 mm
- Packing list: 1 x MDD10A; 1 x 2510 PCB connector 5-way female; 5 x 2510 terminal pin
- Warranty: 12 months, manufacturing defects only
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Input header (2510, 5 pins): pin 1 GND, pin 2 PWM2, pin 3 DIR2, pin 4 PWM1, pin 5 DIR1
- Terminal block (6 pins): 1 Motor 1 Output B, 2 Motor 1 Output A, 3 POWER +, 4 POWER -, 5 Motor 2 Output A, 6 Motor 2 Output B
- Compatible with Arduino and Raspberry Pi (3.3V and 5V logic)
- Not an Arduino shield; connect with wires
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR_DUAL example, one `CytronMD(PWM_DIR, pwmPin, dirPin)` object per channel
- Getting started with SK40C (PIC) in the user's manual
- RC servo signal: not supported
- Analog input / serial input: [NOT STATED]
- Isolation: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive 2 brushed DC motors with high current up to 10A continuously
- Control the motors manually with the onboard test buttons
- Control two DC motors from Arduino UNO
- Control two DC motors from SK40C
- Cytron tutorial: [Using MDD10A with Arduino UNO](https://my.cytron.io/tutorial/using-mdd10a-arduino-uno)
- Cytron tutorial: [Getting Started with Cytron Motor Driver](https://my.cytron.io/tutorial/getting-started-with-cytron-motor-driver)

## Known limitations
- Use a battery when driving an inductive load such as a DC brush motor; most switching power supplies shut down when regenerative current from the motor is detected
- If a switching power supply is needed, a battery with the same rated voltage must be in parallel with it to absorb the regenerative current
- No reverse polarity protection at Vmotor (product page): check polarity before power-up
- Logic inputs 5.5 V max (not for 12 V or 24 V logic)
- Peak 30 A per channel only for 10 seconds or less; 10 A continuous tested at 25°C
- Not for RC PWM (TTL PWM from a microcontroller only)
- Brushed DC motors only
- PWM Low brakes the channel (both outputs low) regardless of DIR
- Motor direction depends on wiring
- Header order is PWM2/DIR2 (pins 2–3) before PWM1/DIR1 (pins 4–5)
- Boards shipped before Jan 2017 are limited to 25 V
- Over-current, thermal and under-voltage protection: [NOT STATED]

## Positioning (kept apart from specs)
- "the dual-channel version of MD10C" (user's manual)
- Solid-state components "result in faster response time and eliminate the wear and tear of the mechanical relay"

## Price band
RM108.78 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-5v-30v-dc-motor-driver-2-channels

## Datasheet
https://docs.google.com/document/d/1ol8nICCTTw5dAHHE_hju08cCVH2GN5_Y3cGC6B4Gbas/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1ol8nICCTTw5dAHHE_hju08cCVH2GN5_Y3cGC6B4Gbas/edit
