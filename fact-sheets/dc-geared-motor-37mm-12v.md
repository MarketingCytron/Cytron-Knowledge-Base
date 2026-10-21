# Product fact sheets

## Product name
12V 37mm DC Geared Motor (SPG30 / SPG30E)

## Aliases
V-SPG30, SPG30, SPG30E, SPG30-GR30, SPG30-GR56, SPG30-GR131, SPG30-GR270, SPG30-GR506, SPG30E-GR30, SPG30E-GR56, SPG30E-GR131, SPG30E-GR270, SPG30E-GR506, 12V 37MM DC Geared Motor, 37mm spur gear motor, SPG30 with encoder

## What it is
A Cytron OEM 12 V brushed DC motor with a Ø37 mm spur gearbox and a 6 mm D-shaft, sold in five gear ratios (1:30 to 1:506), each with or without a 16 PPR Hall-sensor quadrature encoder (product page).

## Specs and functions
- Series code V-SPG30; variant codes SPG30-GRxx (no encoder) and SPG30E-GRxx (with encoder) (product page)
- Rated voltage 12 V DC (datasheet)
- No-load speed: 333 / 178 / 76 / 37 / 20 rpm ±10% for GR30 / GR56 / GR131 / GR270 / GR506 (datasheet)
- Rated speed: 266 / 140 / 60 / 29 / 16 rpm at rated load 2.8 / 4 / 8.6 / 11 / 14 kg·cm (datasheet)
- Max torque (stall prohibited): 14 / 20 / 43 / 56 / 56 kgf·cm (datasheet)
- Currents, all ratios: no-load ≤160 mA, rated 1288 mA, stall 5800 mA (datasheet); the product page lists 120 mA / 400 mA / 1.2 A instead (conflict, datasheet wins)
- Starting voltage 2.0 V, starting current 75 mA, shaft end play 0.05–0.5 mm (datasheet)
- GR506 must not be stalled (product page)
- Shaft: Ø6 mm D-shaft (flat 5.5 mm), 21 mm from the gearbox face; offset 7 mm from the gearbox centre (datasheet drawing)
- Gearbox Ø37 mm, length 22 / 24 / 26.5 / 26.5 / 29 mm by ratio; motor Ø34.5 × 30.3 mm; encoder version 47 mm motor+encoder length (datasheet drawing, product page image)
- Gearbox face: 6 × M3 threaded holes on a Ø31 mm circle (datasheet drawing)
- Encoder: incremental Hall, 16 PPR, 3.3–5 V, output resolution 16 × gear ratio, 2.54 mm female header, wires not detachable (product page)
- Weight: [NOT STATED]
- Warranty: [NOT STATED] (field hidden on the product page)

## Interfaces and compatibility
- Encoder version wires: Red motor +, Black motor −, Green encoder GND, Blue encoder VCC (3.3–5 V), Yellow signal A, White signal B (product page wire chart)
- Non-encoder version: two solder tabs on the motor rear (datasheet drawing)
- Bracket: DC Geared Motor Bracket (SPG30/SPG50) HD-BK-SPG (product page)
- Shaft hubs: Metal Key Hub 6mm CO-SPG; 6mm Key Hub for 60mm Mecanum Wheel CO-MEC-06
- Driver: size for the 5.8 A stall current — MDD10A (suggested on the page), MD10C or MD10-POT; MDD3A only if stalls are avoided (inferred from datasheet currents)

## Use cases
- Drive wheels of small and medium mobile robots with a key hub and wheel (product page)
- Speed or position feedback with the encoder version (product page)
- Encoder-based product counting in a conveyor system (linked Cytron tutorial "Product Counting in Continuous Feed Systems")

## Known limitations
- The product page's current and torque table disagrees with the Cytron datasheets; use the datasheet values
- GR506 must never be stalled; the datasheet marks maximum torque on all ratios as stall prohibited
- Encoder wires are not detachable
- SPG30E-GR30 was out of stock on 2026-10-21
- Weight, warranty and the original motor maker are not stated

## Positioning (kept apart from specs)
- "Well-labeled RPM and torque" so you can pick the motor for your speed or torque need; available with or without encoder (product page)

## Price band
RM49.00 without encoder, RM76.00 with encoder (Cytron product page, read 2026-10-21)

## Product page
https://my.cytron.io/cytron-oem/p-12v-37mm-dc-geared-motor

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

