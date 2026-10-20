# Product fact sheets

## Product name
10Amp 6V-24V DC Motor Driver HAT for Raspberry Pi (2 Channels)

## Aliases
HAT-MDD10, Cytron HAT-MDD10, 10Amp DC Motor Driver for Raspberry Pi, MDD10 HAT for Raspberry Pi

## What it is
A Raspberry Pi HAT that drives two brushed DC motors at up to 10 A continuous each from a 6–24 V supply. Each motor is controlled by a PWM and a DIR signal on fixed Raspberry Pi GPIOs.

## Specs and functions
- Power input voltage: 6 V to 24 V (absolute maximum)
- Maximum continuous motor current: 10 A (without heatsink at 25 ℃)
- Peak motor current: 30 A, must not exceed 10 seconds
- Current limiting at 30 A
- 2 channels, bi-directional
- Logic input high level (VIOH): 3 V min, 5.5 V max
- Logic input low level (VIOL): 0 V min, 0 V typical, 0.5 V max
- 3.3V and 5V logic level input
- Maximum PWM frequency: 20 kHz (actual output frequency is same as input frequency)
- Sign-magnitude PWM and locked-antiphase PWM
- Truth table: PWM low = both outputs low; PWM high + DIR low = A high, B low; PWM high + DIR high = A low, B high
- Fully NMOS H-Bridge; no heat sink is required
- Test switches M1A, M1B, M2A, M2B; LED indicators per output; power LED
- Dimension: 67.5 mm x 59 mm
- Packing list: 1 x Hat-MDD10, 1 x PC104 Header Pin (2x20) (CN-PH-PC104)
- Warranty: 12 months, manufacturing defects only
- Thermal, under-voltage, reverse-polarity protection: [NOT STATED]
- Product page confirms 6–24 V, 10 A continuous / 30 A peak (10 s), current limiting at 30 A, 20 kHz, 67.5 × 59 mm

## Interfaces and compatibility
- PWM1 = GPIO12, DIR1 = GPIO26, PWM2 = GPIO13, DIR2 = GPIO24 (BCM numbering)
- Terminal block: M1A, M1B, VM, GND, M2A, M2B
- Raspberry Pi compatible connector; Raspberry Pi 3 named in the manual and sample code
- Python sample code (RPi.GPIO) for sign-magnitude (HatMDD10SM.py) and locked-antiphase (HatMDD10LA.py) on GitHub; written in Python 2 syntax
- Whether it powers the Raspberry Pi: [NOT STATED]

## Use cases
- Driving two high-current brushed DC motors with a Raspberry Pi as the controller

## Known limitations
- Supports TTL PWM from a microcontroller, not PWM from an RC receiver
- 24 V is the absolute maximum supply
- Peak 30 A must not exceed 10 seconds
- 10 A continuous rating is without heatsink at 25 ℃
- GPIO pins are fixed (no pin selector described)
- Sample code uses Python 2 print statements

## Positioning (kept apart from specs)
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay."

## Price band
RM129.36 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-6v-24v-dc-motor-driver-hat-for-rpi-2-channels

## Datasheet
https://docs.google.com/document/d/19JLDnzU0y-9FKH4ZXm0lk4xtMJKtaKTDBT5ulGgj8UI/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/19JLDnzU0y-9FKH4ZXm0lk4xtMJKtaKTDBT5ulGgj8UI/view
