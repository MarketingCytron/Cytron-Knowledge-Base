# REKA:BIT — Verified Reference

| Field | Value |
|---|---|
| Product code | Not stated in the datasheet. Resellers list "REKABIT-NB" / "CYTRON-REKABIT-NB" [3P] — see Needs verification. Related kit codes KIT-REKABIT-RBT-NB / KIT-REKABIT-RBT (REKA:BIT RBT Project Kit)  |
| Family | micro:bit accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read plus the Cytron pinout diagram image. Grove-to-pin map, package, protections and status are now Cytron-stated |
| Primary source | REKA:BIT "Simplifying Robotics with micro:bit" Datasheet, Rev 1.0, April 2021 (Cytron Technologies Sdn Bhd) — public Google Doc |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A robotics expansion board for the BBC micro:bit — "Simplifying Robotics with micro:bit" [DS]. It has a built-in 2-channel DC motor driver, 4 RC servo ports, a dedicated power input (3.6–6 V), WS2812B RGB LEDs on P8, and 6 Grove ports (3 × analog input/digital IO, 2 × digital IO, 1 × I2C) with GPIO status LEDs [DS]. Cytron's MakeCode extension states "REKA:BIT works with micro:bit V1 & V2" [GH]. "REKA" comes from the Malay "reka bentuk", meaning design [GH].

Motors and servos are driven by an onboard PIC16F1827 co-processor that the micro:bit controls over I2C (address 0x08) [GH].

## Specifications
Datasheet "Table 2: REKA:BIT Absolute Maximum Ratings" — every row (no Typ column) [DS]:

| Item | Value | Src |
|---|---|---|
| Power Input Voltage | Min 3.6 V, Max 6 V | [DS] |
| Analog Input Voltage | Min 0 V, Max 3.3 V | [DS] |
| Total +3V3 Output Current (Grove Ports) | Max 300 mA | [DS] |
| Maximum DC Motor Current, Continuous | Max 1 A | [DS] |
| Maximum DC Motor Current, Peak (< 5 seconds) | Max 1.5 A | [DS] |
| Over Voltage LED | On if power input is over 7V; power to servos and DC motors is cut off | [DS] |
| Low Voltage LED | Blinks when power input is below 3.6V; "Can be used as the low battery indicator" | [DS] |
| DC motor output | Motor voltage at full speed = power source voltage | [DS] |
| Servo ports | 4 × RC servo; V+ = power source voltage | [DS] |
| RGB LEDs | WS2812B, user programmable, connected to P8; 2 pixels in the extension | [DS]; count [GH] |
| Grove ports | 3 × Analog Input/Digital IO, 2 × Digital IO, 1 × I2C Interface | [DS] |
| GPIO status LEDs | On Grove-port GPIOs; on when the GPIO is HIGH | [DS] |
| Motor test buttons | Run the motor at full speed; MxA forward, MxB backward (M1A, M1B, M2A, M2B) | [DS]; names [GH] |
| Co-processor | PIC16F1827, I2C address 0x08 | [GH] |
| Dimensions | Product page: "10.4mm x 72mm x 15mm" (the 10.4 is a typo for ≈104 mm); datasheet Figure 2 drawing only | [PP][DS] |
| Weight, operating temperature | Not stated | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Features (page):** 2 DC motor terminals with built-in quick-test buttons; 4 servo ports; 2 RGB LEDs (Neopixel compatible); 6 Grove ports (3.3 V); 3 analog-input/digital-IO ports; 2 digital-IO ports; 1 I2C; DC jack 3.6–6 VDC; on/off switch; power-on indicator; **under-voltage (LOW) indicator & protection; over-voltage (HIGH) indicator & protection**; "Dimension: 10.4mm x 72mm x 15mm" as printed (see *Conflicts*) [PP].
- **Packing (with micro:bit V2):** 1x micro:bit V2, 1x REKA:BIT, 1x USB power and data cable, 1x 4×AA battery holder, 1x mini screwdriver, 3x Grove to female header cable, 2x building-block 1×9 lift arm, 4x building-block friction pin. The "without micro:bit" option is the same list minus the micro:bit [PP].
- **Pinout diagram (Cytron image):** Grove P0:P1 = P0 (yellow) + P1 (white), both analog in + LED; Grove P1:P9 = P1 (analog in, LED — **shared with P0:P1**) + P9 (LED); Grove P2:P12 = P2 (analog in, LED) + P12 (LED); Grove I2C = P19 SCL + P20 SDA; Grove P15:P16 = P15 (LED, MOSI) + P16 (LED); Grove P13:P14 = P13 (LED, SCK) + P14 (LED, MISO); every Grove port 3V3 + GND. Neopixel [0] and [1] chained on **P8**. Servo signal 3.3 V logic, servo V+ = VIN. Motors M1A/M1B, M2A/M2B. DC barrel jack 3.6–6 V; USB micro B for programming (micro:bit). Power LEDs POWER / LOW / HIGH. "GPIO 3.3V tolerant only" [PP: img].
- Product links printed on the pinout: cytron.io/p-rekabit and cytron.io/p-rekabit-nb (no micro:bit) [PP: img].
- Resources: datasheet, MakeCode extension and test/demo program (pxt-rekabit), pinout diagram, 3D CAD; community Arduino library by Jacques Mattheij [PP].

## Interfaces, terminals and pin mapping
Datasheet "Table 1: REKA:BIT Board Functions" [DS]: Power Input; micro:bit slot; On/Off Switch; Power LED; Low Voltage LED; Over Voltage LED; RGB LEDs (WS2812) on P8; Grove Ports; GPIO Status LEDs; Motor Status LEDs (MxA forward, MxB backward); DC Motor Terminals; Motor Test Buttons; Servo Ports (4).

micro:bit pin usage:

| micro:bit pin | Function | Src |
|---|---|---|
| P8 | WS2812B RGB LEDs (2 pixels) | [DS]; pixel count [GH] |
| I2C bus | PIC16F1827 co-processor at 0x08: servos S1–S4, motors M1/M2 (A/B), power state, low-battery state, over-voltage state, input voltage | [GH] |
| P0, P1, P2 | Analog-capable Grove signal pins (analog-in choices in the RBT kit extension) | [GH] |
| Grove signal pairs (yellow / white) | P0/P1, P1/P9, P2/P12, P13/P14, P15/P16 — derived from the RBT Project Kit extension's ultrasonic Trig/Echo options and its "yellow pin" list (P0, P1, P2, P13, P15) | [GH] inferred; not in datasheet text |
| I2C Grove port | micro:bit I2C (pins not stated in datasheet text) | [DS] |

The Cytron pinout diagram on the product page confirms these pairs (see *Product page facts*) [PP: img].

## Rules and gotchas (for code, wiring and tutorials)
- Power input must stay within 3.6–6 V [DS]. Above 7 V the Over Voltage LED lights and servo/motor power is cut [DS]; below 3.6 V the Low Voltage LED blinks [DS]. The datasheet states no low-voltage cut-off.
- Servo V+ equals the power source voltage, not a regulated 5 V [DS]. Size servos for the actual battery voltage.
- Motor direction depends on wiring: "Swapping the connection (MxA & MxB) will reverse the direction" [DS].
- Grove analog inputs: 0–3.3 V max [DS]; the Grove 3V3 rail supplies 300 mA total [DS].
- Do not put an I2C Grove device at address 0x08 — the onboard co-processor uses it [GH].
- On micro:bit V1, P9 is shared with the LED matrix, so the P9 status LED lights constantly [GH].
- The extension restarts the micro:bit when the REKA:BIT power switch goes from off to on (it polls the power state) [GH].
- Motor speed 0–255 (127 ≈ 50%) [GH]; "brake motor" sets both outputs to 0 [GH].
- Servo position 0–180°; "disable servo" stops the pulse so the horn can be turned by hand [GH].
- RGB default brightness in the extension is 25 (of 255); use `set RGB brightness` to change [GH].
- Motor test buttons M1A/M1B/M2A/M2B run the motors at full speed without code [DS][GH].

## Power and electrical limits
- Power input 3.6–6 V [DS]; connector is a DC jack ("external power input DC jack") [GH]. Battery type is not stated in the datasheet.
- Motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds) [DS].
- Motor voltage at full speed = supply voltage; servo V+ = supply voltage [DS].
- +3V3 to Grove ports: 300 mA total [DS].
- Over-voltage (> 7 V) cuts servo and motor power [DS]. Reverse-polarity protection: not stated [DS].

## Software support
- Microsoft MakeCode extension **pxt-rekabit** (https://github.com/CytronTechnologies/pxt-rekabit), v1.2.3, "Approved content" on makecode.microbit.org; depends on pxt-neopixel; supports target microbit; locales zh-CN and ja [GH].
- Blocks: DC Motors (run, brake), Servos (set position, disable), RGB LED (clear, brightness, set pixel, set all, colours) [GH]. Power-state, low-battery, over-voltage and input-voltage functions exist but are hidden blocks [GH].
- Test program (https://makecode.microbit.org/_X6WCMYY2VWzK) is written in Python and viewable in MakeCode Python mode; compatible with micro:bit V1 & V2 [GH]. REKA:BIT (with micro:bit) ships with the default micro:bit out-of-box demo [GH].
- REKA:BIT RBT Project Kit extension: https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit (RGB Stick, Big LED, soil moisture, ultrasonic; depends on pxt-rekabit) [GH].
- MicroPython library: none found from Cytron.

## Compatibility and accessories
- micro:bit V1 and V2 [GH].
- Grove modules (3.3 V) on the 6 Grove ports [DS].
- REKA:BIT RBT Project Kit (product page https://www.cytron.io/p-rekabit-rbt-project-kits) [GH]; kit codes KIT-REKABIT-RBT-NB / KIT-REKABIT-RBT .
- 3D CAD: https://cdn.cytron.io/REKABIT/REKABIT-3DCAD.zip (linked by a reseller; not opened) [3P].

## Common mistakes / troubleshooting
- Motors/servos dead, Over Voltage LED on → input above 7 V; use 3.6–6 V [DS].
- Low Voltage LED blinking → input below 3.6 V; replace/charge batteries [DS].
- Motor turns the wrong way → swap MxA and MxB wires [DS].
- Check motor wiring without code → press the M1A/M1B/M2A/M2B test buttons [DS][GH].
- micro:bit program restarts when the power switch is turned on → expected extension behaviour [GH].
- P9 LED always on with micro:bit V1 → shared with LED matrix, not a fault [GH].
- Analog sensor reads wrong → Grove analog input max 3.3 V [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Under-voltage handling | [DS] Low Voltage LED blinks below 3.6V (indicator only) | [3P] Elektor: "Undervoltage (LOW) indicator and protection" | [DS] wins: indicator only; do not claim under-voltage protection |
| Number of RGB LEDs | [DS] "User programmable WS2812B RGB LED" (singular; heading "RGB LEDs") | [GH] 2 pixels; [3P] "2x NeoPixel RGB LEDs" | 2 [GH]; datasheet gives no count |
| Dimensions | [DS] figure only; product page prints "10.4mm x 72mm x 15mm" | [3P] Tom's Hardware 103.8 × 71.8 mm; [3P] Elektor "10.4 x 72 x 15 mm" (copied from the page) | Width 72 mm and height 15 mm per [PP]; length ≈104 mm — the page's "10.4" is a typo. Report to the web team |
| Python | [GH] MakeCode Python mode (test program) | [3P] Tom's Hardware: "MicroPython" | Only MakeCode Python is confirmed |

## Needs verification
- Board dimensions and mounting holes; motor driver IC ([3P] Tom's Hardware: MX1515H).
- Buzzer — none stated; how the test program's melody is produced on V1 is not stated.
- Exact board length: the page prints "10.4mm x 72mm x 15mm" (10.4 must be ~104 mm; Tom's Hardware [3P] 103.8 × 71.8 mm).
- Reverse-polarity protection on the DC jack (page lists under/over-voltage protection only).

## Sources
- [DS] REKA:BIT Datasheet, Rev 1.0, April 2021 — public Google Doc: https://docs.google.com/document/d/1axLhH-zaFDheOyz6gbXfYEysigGxpmMnRBC93SW-zR8/edit (linked from the public Switch Science product page; read in full as text, figures not read). Same document mirrored at https://www.farnell.com/datasheets/3685793.pdf and https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6147/REKABIT.pdf
- [GH] https://github.com/CytronTechnologies/pxt-rekabit — README, pxt.json (v1.2.3), main.ts, motor.ts, power.ts, rgb.ts, test.ts via https://raw.githubusercontent.com/CytronTechnologies/pxt-rekabit/master/
- [GH] https://makecode.microbit.org/pkg/cytrontechnologies/pxt-rekabit
- [GH] https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit — README, big_led.ts, soil_moisture.ts, ultrasonic.ts
- [PP] https://www.cytron.io/p-rekabit-simplifying-robotics-with-microbit — not read
- [3P] (cross-check only) https://www.switch-science.com/products/8349 ; https://www.elektor.com/products/cytron-reka-bit-robotics-with-micro-bit ; https://www.tomshardware.com/reviews/cytron-rekabit ; https://www.robotshop.com/products/rekabit-w-o-microbit
