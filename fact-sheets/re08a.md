# Product fact sheets

## Product name
Rotary Encoder Kit (RE08A)

## Aliases
RE08A, Rotary Encoder Kit, RE08A Rotary Encoder Kit, Cytron Rotary Encoder Kit, Simple Rotary Encoder Kit, 8-slot Rotary Encoder Kit

## What it is
A single-channel optical rotary encoder kit made of a sensor board with a slotted opto interrupter and an 8-slot disc that gives 16 transitions per revolution. It has a 3-pin interface (+5, Gnd, Sig), a green indicator LED and a pulse output internally pulled up to 5 V.

## Specs and functions
- Disc: 8 slots giving 16 transitions per revolution (user manual)
- Disc size: 35 mm outer diameter x 3 mm inner diameter (user manual)
- Sensor board size: 12 mm (height) x 35 mm (length) x 15 mm (width) (user manual)
- Supply voltage (+5): 4.5 V min, 5 V typical, 5.5 V max (user manual)
- Output: 0 V to 5 V pulses; low 0–1.0 V (0.8 V typical), high 4.5–4.9 V (4.7 V typical) with +5 = 5 V (user manual)
- Output frequency: up to 1 kHz (1000 pulses/sec) (user manual)
- Current at low state: 25 mA min, 30 mA typical, 40 mA max (user manual)
- Current at high state: 5 uA min, 10 uA typical, 20 uA max (user manual)
- Operating temperature: 0 °C to 75 °C, 25 °C typical (user manual)
- Sig is internally pulled up to 5 V; no external component needed (user manual)
- Truth table: beam unblocked (slot) = LED ON, Sig 0 V; beam blocked = LED OFF, Sig 5 V (user manual)
- Packing list: 1 x RE08A sensor board, 1 x 8-slot disc (user manual)
- Ready to use without further soldering (user manual)

## Interfaces and compatibility
- 3-pin header: +5 (5 V supply), Gnd (supply negative), Sig (pulse output) (user manual)
- Board labels: A optical sensor, B +5, C Gnd, D Sig, E indicator LED (user manual)
- Connect Sig to a microcontroller counter, clock or encoder input; mount the disc on a motor shaft or gear output so it passes through the sensor gap (user manual)
- Software setup depends on the microcontroller and is not covered by the manual (user manual)
- No Cytron library or GitHub example found

## Use cases
- Counting pulses to measure shaft rotation, speed or distance on a motor shaft or gear output (user manual)

## Known limitations
- 5 V device: supply 4.5–5.5 V and 5 V output levels (user manual)
- Single signal output; no second channel listed (user manual)
- Output frequency limited to 1 kHz (user manual)
- Reversed supply polarity can damage the sensor (user manual)
- Disc slots must not be broken during installation (user manual)
- Manual (2008) states warranty 6 months; product page states 12 months

## Positioning (kept apart from specs)
- Simple 3-pin interface and on-board LED indicator; ready to use without soldering (user manual)

## Price band
RM38.85 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-rotary-encoder-kit

## Datasheet
https://drive.google.com/file/d/0BzFWfMiqqjyqdlpDUTc5ektndlE/view

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-39/pdf/cytron-simple-rotary-encoder-kit-users-manual.pdf
