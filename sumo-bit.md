# SUMO:BIT — Verified Reference

| Field | Value |
|---|---|
| Product code | `SUMO-BIT` — model code of the my.cytron.io page "SUMO:BIT - Sumo Robot Expansion Board for micro:bit" (p-sumo-bit), from the Cytron tutorial shop links [PP: tutorial]. Not stated in the datasheet; datasheet titles use "SUMO:BIT" and "SUMO-BIT"; Cytron marketing artwork shows "SUMOBIT" [DS] |
| Family | micro:bit accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (features, specifications, packing lists, resources, FAQ) plus the dimension image. Package, MD13S inclusion, size and firmware location are now Cytron-stated |
| Primary source | SUMO:BIT Datasheet, Rev 1.0, December 2024 (Cytron Technologies Sdn Bhd) — public PDF mirror on RobotShop CDN |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A sumo robot expansion board for the BBC micro:bit: "A micro:bit based sumo robot board" [DS]. The micro:bit plugs into a vertical edge-connector socket; the board takes a LiPo battery (7–25 V), provides 5 opponent-sensor ports, 2 edge-sensor ports, 1 general-purpose port (P2), 2 servo/RC ports, 2 RGB LEDs, a 4-way mode DIP switch, a motor alignment module and a USB-A port for a wireless joystick receiver [DS].

It does not drive motors by itself: it has "2x sockets for external MD13S motor driver boards", one per motor channel, which plug in from the bottom of the PCB and can be removed and replaced if one fails [DS]. All motor ratings in the datasheet are "with MD13S" [DS]. An onboard RP2040 co-processor (I2C address 0x09) handles motors, servos, RGB LEDs, mode switch, motor current and battery voltage; the micro:bit talks to it over I2C [GH].

## Specifications
Datasheet "Table 4: SUMO-BIT Absolute Maximum Ratings" (section 3, Specification) — every row. No typical values are given [DS].

| Item | Value | Src |
|---|---|---|
| Power Input Voltage (LiPo Battery) | Min 7 V, Max 25 V | [DS] |
| Motor PWM Frequency (with MD13S) | Max 20 kHz | [DS] |
| Maximum DC Motor Current per channel (with MD13S) | Max 13 A (continuous) | [DS] |
| Peak Motor Current per channel (with MD13S) | Max 30 A — peak must not last longer than 10 seconds | [DS] |
| USB Host Output Voltage | Max 5 V | [DS] |
| USB Host Output Current | Max 600 mA | [DS] |
| Servo Voltage | Max 5 V | [DS] |
| +5V Output Maximum Current (Total) | Max 600 mA | [DS] |
| VBAT input (feature list) | "7V to 25V, with reverse polarity protection" | [DS] |
| Motor channels | 2 (2 × MD13S sockets); "13A continuous, 30A peak (<10 second)" | [DS] |
| Motor current sensing | "2x motor current sensors, one for each motor channel" | [DS] |
| Opponent sensor inputs | 5, pulled up to 5V, with status LEDs | [DS] |
| Edge sensor inputs | 2 (analog sensors) | [DS] |
| General purpose port | 1 × P2 (analog/digital) with status LED | [DS] |
| Servo/RC ports | 2 ("can also be as RC pins") | [DS] |
| RGB LEDs | 2 × WS2812B, user programmable | [DS] |
| Motor status LEDs | 4 (red) | [DS] |
| Mode switch | 1 × 4-way DIP switch, up to 16 configurations | [DS] |
| Joystick | USB-A port for wireless joystick connection | [DS] |
| Firmware update | USB-C port + boot button (USB-C "not for programming") | [DS] |
| Co-processor | RP2040, I2C slave address 0x09 | [GH] code comment; "RP2040" on launch artwork  |
| Dimensions | 125.00 × 80.00 mm; 4x Ø3.20 mm holes (product-page dimension image); datasheet Figure 4 drawing only | [PP: img] |
| Weight, operating temperature, quiescent current | Not stated | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Options & packing:** Board ONLY = 1x SUMO:BIT **with 2x MD13S motor drivers attached**, 1x small flat screwdriver, 1x Phillips screwdriver, 1x Dean T male connector with 18AWG wire 15 cm, [free] SUMO:BIT sticker set (early adopters). With micro:bit Junior Kit = the same plus 1x micro:bit Junior Kit (BBC micro:bit V2 + USB micro B cable) [PP].
- **Features:** co-processed by Raspberry Pi RP2040; detachable MD13S; mode interchangeable without reprogramming; USB host for a wireless USB joystick; onboard motor alignment adjust and calibration; 4-way DIP switch for 16 strategies [PP].
- **Specifications:** LiPo 7–25 V; PWM 20 kHz with MD13S; 13 A per channel continuous, 30 A peak (≤10 s) with MD13S; USB host 5 V 600 mA; servo 5 V; +5 V total 600 mA [PP] (matches [DS]).
- **Size:** 125.00 × 80.00 mm; 4x Ø3.20 mm mounting holes, 119.70 mm apart [PP: img dimension].
- **FAQ (page):** programmable with MakeCode and MicroPython [PP] — no MicroPython library is linked, so treat MicroPython as unconfirmed.
- **Resources:** datasheet; pxt-sumobit; sample code; 3D CAD; GitHub Cytron-SUMOBIT (firmware UF2, STL files); SUMO:BIT Robot Kit slide guides (Assemble, Checking, Maintenance, Autonomous, RC); Telegram support group [PP].

## Interfaces, terminals and pin mapping
Datasheet section 2 "Board Layout and Function" items [DS]:
1. Power switch — "Vibration proof on/off switch with MOSFET latching circuit"; switches the board and motor drivers.
2. Power LED (green).
3. micro:bit socket — vertical edge connector; insert the micro:bit with the **LED matrix facing up**.
4. USB joystick port — USB-A, for the wireless joystick receiver.
5. Mode DIP switch — 4-way, up to 16 configurations, to select tactic/mode.
6. Opponent sensor ports — male headers, +5V internal pull-ups, for Maker Object or other digital sensors; voltage divider protects the micro:bit pins.
7. Opponent sensor status LEDs — active low (light when the signal is LOW; with Maker Object, when an opponent is detected).
8. Edge sensor ports — male headers for Maker Reflect "or any other analog sensors"; voltage divider adjusts the output voltage.
9. P2 port — male header, general-purpose I/O to micro:bit P2, digital I/O or analog input; active-low status LED; voltage divider reduces 5V to about 3V.
10. Motor alignment module — (a) potentiometer to balance left/right motor speed, (b) test button runs the motors forward for 1 second, (c) potentiometer indicator LEDs.
11. Firmware update module — USB-C to a computer for firmware upload; not for programming.
12. Boot button — enters bootloader mode.
13. RGB LEDs — WS2812B, user programmable.
14. Motor status LEDs — red; MLA/MRA = forward, MLB/MRB = backward.
15. Servo/RC ports — male headers for servos or an RC receiver.
16. MD13S socket (top) — insert the MD13S **from the bottom of the PCB**.
17. Battery terminal (bottom) — + and −; + also feeds an analog input for battery-voltage reading.
18. Motor terminals (bottom) — see the datasheet connection guide.
19. MD13S socket (bottom view).

micro:bit pin usage — from the official MakeCode extension source (pxt-sumobit v1.3.6) [GH]; the datasheet text gives no pin numbers except P2:

| micro:bit pin | Function | Src |
|---|---|---|
| P0 | Right edge sensor (analog read) | [GH] |
| P1 | Left edge sensor (analog read) | [GH] |
| P2 | General-purpose port (digital I/O or analog in) | [DS][GH] |
| P12 | Opponent sensor Right | [GH] |
| P13 | Opponent sensor Front Right | [GH] |
| P14 | Opponent sensor Front Center | [GH] |
| P15 | Opponent sensor Front Left | [GH] |
| P16 | Opponent sensor Left | [GH] |
| I2C (micro:bit I2C bus) | RP2040 co-processor at address 0x09: motors (PWM/DIR/acceleration per channel), 2 servos, 2 RGB LEDs, motor current ×2, battery voltage, DIP mode, reset | [GH] |

Servos, RGB LEDs, motors, mode switch and battery voltage are **not** on micro:bit pins — they are registers on the RP2040 [GH].

## Rules and gotchas (for code, wiring and tutorials)
- Insert the micro:bit with the LED matrix facing up; insert each MD13S from the bottom of the PCB [DS].
- The USB-C port is for SUMO:BIT firmware updates only — "not for programming". Program the micro:bit through the micro:bit's own USB [DS].
- Opponent sensors are active LOW: the status LED lights and the extension's "detect opponent" block returns true when the input is LOW (0) [DS][GH]. The extension also sets software pull-ups on P12–P16 [GH].
- Edge sensors are analog: the extension reads P0 (right) and P1 (left) with analogRead; "detect edge" is true when the reading is **below** the threshold [GH].
- `calibrate edge sensor` sets threshold = current reading × (coefficient × 0.1); coefficient 1–9, default 5 [GH]. Run it with the sensors over the black ring surface.
- Motor speed 0–255, acceleration factor 1–9 (higher = faster speed change) [GH]. "Right" motor = channel 1, "left" = channel 2 in the extension [GH].
- Servo position 0–180°, speed 1–5; "disable" stops the servo pulse [GH].
- Mode block returns 0–15 from the 4-way DIP switch [GH] (README text says "0-16" — see Conflicts).
- Battery voltage block returns volts to 2 decimal places [GH]. README example warns at < 11 V [GH] — an example, not a rated cut-off.
- Peak 30 A per channel must not last longer than 10 seconds [DS].
- Servo/RC ports run at 5 V max; the total +5V output is 600 mA max (shared) [DS].
- The P2 port has a voltage divider (5V to about 3V) — expect reduced signal levels [DS].

## Power and electrical limits
- Battery: LiPo, 7–25 V, reverse polarity protection [DS]. Cell count is not stated.
- The MD13S itself is rated 6–30 V [MD13S UM, see kb/md13s.md]; the SUMO:BIT limit of 7–25 V is the binding range.
- Per channel (with MD13S): 13 A continuous, 30 A peak for < 10 s, PWM up to 20 kHz [DS].
- +5V rail: 600 mA total; USB host output 5 V / 600 mA; servo voltage 5 V [DS].
- Battery voltage is measured by an analog input from the + terminal [DS].
- Power switch is a slide switch with MOSFET latching circuit, "vibration proof" [DS].

## Software support
- Microsoft MakeCode extension **pxt-sumobit** (search "sumobit" or https://github.com/cytrontechnologies/pxt-sumobit in Extensions), v1.3.6, "Approved content" on makecode.microbit.org [GH].
- Block groups: DC Motors, Servos, Mode, Motor Current, Opponent Sensors, Edge Sensors, RGB LED, Battery, Robot Kit (countdown 3 s / 5 s, preset backoff, attack and search routines) [GH]. Motor-current blocks are hidden in the toolbox (`blockHidden`) in the current code; range 0.00–20.00 [GH].
- MakeCode JavaScript/Python views, MicroPython, Arduino: not stated by any Cytron source.
- No extension blocks exist for the USB joystick or RC-receiver input [GH]; how the joystick works is not stated.

## Compatibility and accessories
- Motor drivers: MD13S × 2, plugged into the sockets [DS].
- Opponent sensors: Maker Object "or other digital sensors" [DS]. Edge sensors: Maker Reflect "or any other analog sensors" [DS].
- micro:bit version (V1/V2): not stated by any source — see Needs verification.
- 3D CAD files: offered by a reseller page — see Needs verification.

## Common mistakes / troubleshooting
- Trying to upload code through the SUMO:BIT USB-C → it is for firmware updates only [DS].
- micro:bit inserted backwards → LED matrix must face up [DS].
- Opponent logic inverted in code → detection is LOW [DS][GH].
- Edge never/always detected → recalibrate the threshold on the ring surface; detection is "reading < threshold" [GH].
- Robot does not drive straight → adjust the alignment potentiometer and check with the test button (motors run forward 1 s) [DS].
- Motors do not run → check both MD13S are seated (inserted from the bottom), battery 7–25 V, power switch on, motor status LEDs MLA/MLB/MRA/MRB [DS].
- Servo jitter/brown-out with several loads → +5V total is 600 mA [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery range | [DS] 7–25 V (LiPo) |  Dec 2024 launch artwork (OCR) shows a "BATTERY 12V-24V" label | [DS] wins: 7–25 V. Check whether the label is board silkscreen or artwork |
| Mode range | [GH] code: 0–15; [DS] 16 configurations | [GH] README: "DIP switch state (0-16)" | 0–15 (16 values) |
| Edge port wiring | [DS] "Internally connected to the micro:bit digital pins" | [DS] same item: for "analog sensors"; [GH] analogRead on P0/P1 | Read as analog on P0 (right) / P1 (left) |
| Package contents | [DS] MD13S described as "external" boards in sockets; no package list | [3P] Makers Electronics: "SUMO:BIT with 2 MD13S motor drivers attached", screwdrivers, Dean T connector, sticker set | Not confirmed — Needs verification |
| Co-processor | [DS] names no chip | [GH] RP2040; [3P] RobotShop "Utilizes Raspberry Pi RP2040" | RP2040 [GH] |

## Needs verification
- Supported micro:bit versions (V1 and/or V2) — no source states it.
- LiPo cell count recommendation; behaviour at low battery.
- How the USB joystick and RC-receiver inputs are used in code (no extension blocks).
- Telegram "SUMO:BIT Support Group" — named in the datasheet, no link.
- Per-option shop codes for the two options (the page model code `SUMO-BIT` is known from the tutorial shop links [PP: tutorial]).
- MicroPython support named in the page FAQ — no library or example linked.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Build Sumo Robot with micro:bit (SUMO:BIT)](https://my.cytron.io/tutorial/build-sumo-robot-with-sumobit) — Tutorial, Beginner, 2024 (series, 7 parts) [PP: tutorial]
- [2 Wheel Robot Battle with SUMO:BIT](https://my.cytron.io/tutorial/2-wheel-robot-battle-with-sumobit) — Tutorial, Beginner, 2025 [PP: tutorial]
- [Getting started with Soccer Robot using SUMO:BIT](https://my.cytron.io/tutorial/soccer-robot-using-sumo-bit) — Tutorial, Beginner, 2025 [PP: tutorial]
- [Robot Battle RC Mode with HotRC](https://my.cytron.io/tutorial/SUMO:BIT_RC_Mode_with_HOT_RC) — Tutorial, Beginner, 2026 [PP: tutorial]
- [4 Wheel Robot Battle with SUMO:BIT](https://my.cytron.io/tutorial/4-wheel-robot-battle-with-sumobit) — Tutorial, Beginner, 2025 [PP: tutorial]
- [SUMO:BIT Autonomous Mode (DIP)](https://my.cytron.io/tutorial/SUMO:BIT_Autonomous_Mode_(DIP)) — Tutorial, Beginner, 2026 [PP: tutorial]
- [Joystick Pairing with SUMO:BIT and Motion 2350 Pro](https://my.cytron.io/tutorial/joystick-pairing-with-sumobit-and-motion-2350-pro) — Tutorial, 2026 [PP: tutorial]

## Sources
- [DS] SUMO:BIT Datasheet, Rev 1.0, December 2024, Cytron Technologies Sdn Bhd — public mirror: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-429/pdf/sumobit-expansion-board-for-microbit-datasheet.pdf (read as text; figures not read). Also mirrored at https://makerselectronics.com/wp-content/uploads/2025/08/SUMO_BIT-Datasheet.pdf (not opened). No Cytron Google Doc found.
- [GH] MakeCode extension: https://github.com/CytronTechnologies/pxt-sumobit — README, pxt.json (v1.3.6), main.ts, motor.ts, opponent.ts, edge.ts, mode.ts, servo.ts, battery.ts, motorcurrent.ts, robot.ts via https://raw.githubusercontent.com/CytronTechnologies/pxt-sumobit/master/
- [GH] MakeCode approved-extension page: https://makecode.microbit.org/pkg/cytrontechnologies/pxt-sumobit
- [MD13S UM] via KB file `kb/md13s.md`
- [PP] https://www.cytron.io/p-sumo-bit — product page not read (fetch failed); my.cytron.io also not reachable
- [3P] (cross-check only) https://www.robotshop.com/products/sumobit-expansion-board-for-microbit-1 ; https://makerselectronics.com/product/cytron-sumo-bit-expansion-board-with/
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
