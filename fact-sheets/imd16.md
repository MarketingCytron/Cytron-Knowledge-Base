# Product fact sheets

## Product name
iMD16 (16 Amp 7-30V Industrial DC motor Driver)

## Aliases
IMD16, 16Amp 7-30V Industrial DC Motor Driver, 16 Amp 7-30V Industrial DC Motor Driver, iMD16 Industrial Motor Driver

## What it is
A single-channel, bidirectional brushed DC motor driver in a metal enclosure, rated 7–30 V DC input, 16 A continuous and 30 A peak (less than 10 seconds). It is controlled either by an external PWM/DIR signal or standalone with the included potentiometer and 3-way rocker switch.

## Specs and functions
- Product code: IMD16; launched 25 June 2026
- Power Input Voltage: 7 V min, 30 V max (POWER + / − screw terminal)
- Maximum Motor Current – Continuous: 16 A
- Maximum Motor Current – Peak (Less than 10 seconds): 30 A
- Logic Input Voltage – Low Level (PWM, DIR): 0 V to 0.5 V
- Logic Input Voltage – High Level (PWM, DIR): 3 V to 30 V
- Internal PWM Generator Frequency (output frequency when the potentiometer is used): 9 kHz to 11 kHz
- External PWM Input Frequency (Output Frequency = Input Frequency): DC to 20 kHz
- 1 motor output (MA, MB), bidirectional
- PWM/DIR truth table: PWM Low, DIR don't care → MA Low, MB Low → Brake; PWM High, DIR Low → MA High, MB Low → Forward; PWM High, DIR High → MA Low, MB High → Reverse
- Two control modes: PWM/DIR input (external microcontroller) and POT/SWITCH input (standalone, potentiometer for speed, 3-way switch for stop/forward/reverse, no microcontroller needed)
- Power LED (lights when supply voltage is present) and Motor Status LEDs (MA, MB; indicate motor operating conditions)
- No current limiting function
- Metal enclosure that also works as a passive heatsink; fanless
- Dimensions (datasheet Figure 4, mm): 102.00 overall length, 52.20 width, 73.99 enclosure body length, 5.00 flange thickness, 16.60 height dimension above the flange
- Mounting: two M4 slotted holes, slot centres 93.00 mm apart
- Packing box 72 × 118 × 46 mm; 157 g fully packed
- Certifications: CE (EMC EN 55032, EN IEC 61000-3-2, EN 61000-3-3, EN 55035; safety EN IEC 62368-1), UKCA, FCC Part 15 Subpart B Supplier's Declaration of Conformity, RoHS (CE and UKCA)
- Thermal, reverse polarity, under-voltage protection: [NOT STATED]
- Isolation: [NOT STATED]
- IP rating: [NOT STATED]
- Operating temperature: [NOT STATED]
- Unit weight: [NOT STATED]
- Packing: iMD16, 10 kΩ potentiometer and 3-way rocker switch with connectors, JST PH PWM/DIR connector, mini screwdriver, Quick Start Guide card (product page)
- Also sold by co-launch partners in Australia, China, India, Japan and the USA (product page)

## Interfaces and compatibility
- Power Input Terminal: 2-way screw terminal, POWER + / −, 7–30 V DC
- Motor Output Terminal: 2-way screw terminal, MOTOR MA / MB
- Speed Control Potentiometer: 3-pin JST PH connector (SPEED POT(10K): P3, P2, P1) for a 10 kΩ potentiometer
- Direction Switch: 3-pin JST PH connector (DIR SWITCH: MB, COM, MA) for a 3-way rocker switch (Forward, Stop, Reverse)
- PWM/DIR Input: 3-pin JST PH connector (DIR, PWM, GND); the controller's GND connects to GND
- Works with PLCs, microcontrollers (Arduino or Raspberry Pi named) and industrial motion controllers; direct connection to 24V PLC outputs without additional level shifters
- In the box: 1 × iMD16; 1 × 10k Ohm Potentiometer with connector; 1 × 3-Way Rocker Switch with connector; 1 × JST PH2.0-3P with Wires – 20cm; 1 × Phillips Screwdriver; 1 × Quick Start Guide
- Resources: Getting Started Guide for iMD16, datasheet, 3D CAD
- No firmware or configuration needed
- Arduino library support: [NOT STATED] (iMD16 is not in the CytronMotorDriver library's compatible-driver list)

## Use cases
- Conveyor systems
- Automated feeders
- Small industrial machines
- AGV / robotics subsystems
- Pumps, rollers, fans, and lifters
- Test and measurement equipment
- Custom automation systems
- Agricultural equipment
- Conveyor and material handling systems
- Custom OEM machinery
- Standalone field-deployed equipment
- Doors, actuators, and reversible conveyors
- Cytron tutorial: [Getting Started with iMD16 (No Code Setup)](https://my.cytron.io/tutorial/getting-started-with-imd16)
- Cytron tutorial: [Conveyor Belt Control without Code using iMD16](https://my.cytron.io/tutorial/imd16-conveyor-belt-control-without-code)
- Cytron tutorial: [Cytron Brings its First Industrial DC Motor Driver to the Global Stage](https://my.cytron.io/tutorial/cytron-launches-imd16-industrial-dc-motor-driver)

## Known limitations
- No current limiting function: 16 A continuous and 30 A peak (< 10 seconds) are maximum supported operating currents, not an active current limit; operating above the rated current may cause the board to overheat and could damage it
- Peak 30 A only for less than 10 seconds
- Back-EMF during braking or direction changes can make a switching power supply (SMPS) rail overshoot, potentially damaging the driver or tripping the SMPS protection; use a battery where possible, or add large electrolytic bulk capacitors or external TVS/clamping diodes to the power rail if an SMPS must be used
- Power input limited to 7–30 V
- External PWM limited to DC–20 kHz
- Logic Low must be 0–0.5 V and High 3–30 V
- PWM Low brakes the motor (both outputs Low)
- Control signals use JST PH connectors; screw terminals are for power and motor only
- Single motor channel
- Thermal, reverse polarity and under-voltage protection are not stated

## Positioning (kept apart from specs)
- "Meet Cytron's first industrial motor driver, the iMD16"
- "Industrial Motor Driver. Ready to Install."
- "Deployment-Ready with Integrated Controls and Protective Enclosure"
- Created "to bridge the gap between development motor drivers and complex industrial motor controllers"
- Positioned for 12V and 24V systems ("covering both 12V and 24V systems")
- Target audience: system integrators, existing Cytron MD users, machine makers, industrial engineers / technicians

## Price band
RM163.80 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-16amp-7-30v-industrial-dc-motor-driver

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

