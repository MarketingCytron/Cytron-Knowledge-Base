# MOTION:BIT — Verified Reference

| | |
|---|---|
| Product code | `MOTION-BIT` (Cytron datasheet Google Doc file title "MOTION-BIT Datasheet" [DS]; RobotShop "Manufacturer #" MOTION-BIT [3P]). my.cytron.io page: p-motionbit-board-and-kits (series page, 4 options; per-option codes not shown) [PP] |
| Family | micro:bit accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read plus Cytron images (board layout, key features, dimension, and the MOTION:BIT vs MOTION:BIT Pro comparison table). Package, size, power sources and several [3P] counts are now Cytron-stated |
| Primary source | MOTION:BIT — "Simplifying Motion Control with micro:bit" — Datasheet **Rev 1.0, February 2023** (public Google Doc): https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: the datasheet was read in full from the Google Doc (via Drive) and cross-checked against the RobotShop PDF mirror (same title, Rev 1.0, February 2023). The datasheet link is **public** (linked from The Pi Hut and Switch Science product pages and mirrored on cdn.robotshop.com). No separate user manual was found. my.cytron.io / www.cytron.io pages (product page and "Getting Started with MOTION:BIT & Projects Guide" tutorial) could **not be fetched**. [GH] = CytronTechnologies/pxt-motionbit (MakeCode extension, v1.2.0). [VEN] = micro:bit Foundation (tech.microbit.org). No [DT] confirmation exists yet.

## What it is
A robotics / motion-control expansion board for the BBC micro:bit. The micro:bit plugs into a vertical socket; the board drives brushed DC motors and 8 RC servos, has 2 WS2812B RGB LEDs on P8, a colour-coded GVS breakout of 11 micro:bit I/O with status LEDs, JST-SH "Maker Ports" (Qwiic / STEMMA QT, Grove via cable) and an I2C breakout [DS][GH]. It runs from an onboard 18650 Li-Ion battery holder (charged over micro USB) or an external 3.6–6 V input [DS]. Cytron's MakeCode extension describes it as having a "built-in 4-channel DC motor driver" and says it "works with micro:bit V1 & V2" [GH].

## Specifications
Datasheet Table 2 is titled **"MOTION:BIT Absolute Maximum Ratings"** — these are absolute limits, not recommended operating points [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 3.6 V, Max 6 V | [DS] |
| Analog input voltage | Min 0 V, Max 3.3 V | [DS] |
| Total +3V3 output current (GPIO Breakout & Grove Ports) | Max 200 mA | [DS] |
| Total +5V output current | Max 300 mA | [DS] |
| Maximum DC motor current, continuous | Max 1 A (datasheet does not say per channel or total) | [DS] |
| Maximum DC motor current, peak (< 5 seconds) | Max 1.5 A | [DS] |
| DC motor channels | 4 (M1, M2, M3, M4) — not stated in the datasheet | [GH] |
| Servo ports | "Connectors for 8x RC servo motors"; V+ voltage = power source voltage | [DS] |
| Servo control | 50 Hz; 0–180° mapped to 500–2500 µs pulse; "disable" sends no pulse | [GH] |
| RGB LEDs | User-programmable WS2812B, connected to P8; 2 onboard (`RGB_LED_LENGTH = 2`) | [DS] / count [GH] |
| External RGB LED | Connector for external WS2812B, daisy-chained to the onboard LEDs (Dout of RGB LED 1) | [DS] |
| GPIO breakout | Colour-coded GVS, 3.3 V power per GPIO: P0, P1, P2, Button A, Button B, P9, P12, P13, P14, P15, P16 | [DS] |
| GPIO status LEDs | On when the IO state is high | [DS] |
| Maker Ports | JST-SH 4-way; Qwiic, STEMMA QT, Grove (via conversion cable); "These pins are available on Maker Ports: P0-P9, P1-P2, P2-P12" (printed as-is) | [DS] |
| Maker Port (I2C) | JST-SH 4-way; "for I2C modules only" | [DS] |
| I2C breakout | "Breakout of micro:bit I2C pins" | [DS] |
| 5V Supply | 5V output for external sensors/modules (total 300 mA max) | [DS] |
| Battery | 18650 Li-Ion battery holder | [DS] |
| Micro USB | Charges the battery or powers the board; **no data transmission** | [DS] |
| Power / Charge LED | Power: on when powered. Charge: on while charging, off when full | [DS] |
| Power input terminal | External 3.6–6 V; "Can be used for external LiPo or 4x AA batteries" | [DS] |
| On/Off switch + Ext. On/Off switch header | External switch works only with onboard switch Off | [DS] |
| Motor test buttons | Run the motor at full speed | [DS] |
| Motor status LEDs | On when the motor is running | [DS] |
| Motor driver IC | **Not stated** | [DS] |
| PWM / servo controller IC | PCA9685 at I2C address 0x40 (from extension code; not in datasheet) | [GH] |
| Buzzer / speaker | **Not stated** — no buzzer in the datasheet board functions | [DS] |
| Dimensions | Figure 2 drawing only, no values in the text | [DS] |
| Operating temperature | **Not stated** | [DS] |
| Protections (reverse polarity, over-current, thermal, battery) | **Not stated** | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Co-developed by makerspace.UTHM and Cytron, with ISOBOT and Elvira Systems [PP].
- **Features list:** 11 GPIO status LEDs; 11 GPIO breakout; 3 general Maker Ports (JST-SH 4-way) + 1 I2C Maker Port (Qwiic/STEMMA QT compatible [PP: img]); I2C breakout; vertical micro:bit socket; 4 motor terminals; 8 motor test buttons; 8 motor status LEDs; 8 servo ports (colour-coded); 2 RGB LEDs + external RGB LED header; 6x 5V supply pins; 18650 holder; on/off switch + external on/off switch header; micro USB; power input; power/charge LED [PP].
- **Comparison image (Cytron, MOTION:BIT column):** power from micro USB, 18650 Li-ion or external Vin; external Vin 3.6–6 V; max DC motor current 1 A continuous, 1.5 A peak; USB Li-ion charging circuit: yes; Li-ion battery protection circuit: yes; slide switch with MOSFET shock-proof circuit; total 5 V output 300 mA; servo power directly from Vin only (no selector); total servo output current 3 A; 3 Maker Ports (JST-SH 1 mm) + 11 GVS headers; I2C: 1 Maker Port + 1 4-pin header; official MakeCode extension MOTION:BIT [PP: img].
- **Key features image:** onboard 18650 rechargeable via USB; external power e.g. 4×AA; servos and DC motors powered directly from the input source [PP: img].
- **Size:** 95.2 × 57.2 mm; Ø4.8 mm holes on a 72.0 × 48.0 mm pattern [PP: img dimension].
- **Options & packing:** MOTION:BIT ONLY = 1x MOTION:BIT, 1x tiny Phillips screwdriver, 3x Grove to JST-SH (Qwiic) cable, 4x silicone bumper; + micro:bit Junior Kit (micro:bit V2 + USB micro B cable); + **3.7 V 2200 mAh 18650** with button top; or both [PP].

## Interfaces, terminals and pin mapping
| micro:bit pin | Used for | Src |
|---|---|---|
| P19 (SCL) / P20 (SDA) — the micro:bit I2C pins | PCA9685 (0x40) that drives all DC motor and servo outputs; also the I2C breakout and Maker Port (I2C) | [GH] code + [VEN] pin names + [DS] "micro:bit I2C pins" |
| P8 | Onboard WS2812B RGB LEDs (and external RGB LEDs chained after them) | [DS][GH] |
| P0, P1, P2, P9, P12, P13, P14, P15, P16, Button A, Button B | GVS breakout with status LEDs, 3.3 V power each | [DS] |
| Button A = P5, Button B = P11 | micro:bit pin numbers for the two buttons | [VEN] |
| P0/P9, P1/P2, P2/P12 | Maker Ports, as printed "P0-P9, P1-P2, P2-P12" — exact per-port pairing unclear | [DS] |

Motor and servo channels map to PCA9685 outputs, not to micro:bit pins [GH]:

| Channel | PCA9685 output(s) | Src |
|---|---|---|
| M1 | 4 (A) / 5 (B) | [GH] |
| M2 | 6 / 7 | [GH] |
| M3 | 10 / 11 | [GH] |
| M4 | 8 / 9 | [GH] |
| S1–S4 | 0, 1, 2, 3 | [GH] |
| S5–S8 | 15, 14, 13, 12 | [GH] |

## Rules and gotchas (for code, wiring and tutorials)
- Insert the micro:bit with **its LEDs facing out** [DS].
- The board's **micro USB has no data** — program the micro:bit through the micro:bit's own USB port [DS].
- Motors and servos do **not** use micro:bit GPIO pins — they are driven over I2C by a PCA9685 at **0x40** [GH]. Don't connect another I2C module at address 0x40 (derived from [GH]).
- **P8 is taken by the RGB LEDs** [DS]; it is not in the breakout list.
- Servo V+ and motor full-speed voltage **equal the power source voltage** — there is no servo voltage regulator on MOTION:BIT [DS]. Use servos rated for the supply.
- To use the external On/Off switch, the **onboard switch must be Off** [DS].
- Motor test buttons run the motor at **full speed** — lift wheels off the ground [DS].
- Motor direction depends on wiring polarity; swap the motor wires to reverse [DS].
- MakeCode `run motor` speed is **0–255** (mapped to 0–4095) [GH]; servo position is **0–180°** [GH].
- `brake motor` sets both outputs of that channel to 0 [GH]. Whether this is an electrical brake or a coast depends on the driver IC, which is not stated — see Needs verification.
- `disable servo` sends no pulse, so the servo can be turned by hand [GH].
- External RGB LEDs: call `set external RGB pixels length to` first; external pixels are numbered after the 2 onboard pixels [GH].
- Onboard RGB default brightness is 25 (of 255) in the extension [GH].
- Don't claim a buzzer, Bluetooth, or motor driver part number — none is stated [DS].

## Power and electrical limits
- Power input **3.6–6 V** absolute maximum (power input terminal, e.g. LiPo or 4x AA), or the onboard **18650 Li-Ion** holder, or micro USB [DS].
- Micro USB charges the 18650 battery; charge LED goes off when full [DS]. Charge current not stated.
- DC motor current **1 A continuous, 1.5 A peak (< 5 s)** [DS]; whether per channel or total is not stated.
- **+5V output total 300 mA**; **+3V3 total 200 mA** shared by GPIO breakout and Grove/Maker ports [DS].
- Analog inputs 0–3.3 V [DS].
- Reverse-polarity, over-current, thermal and battery protection: **not stated** in the datasheet — do not claim them.

## Software support
- **MakeCode:** extension `pxt-motionbit` (v1.2.0, MIT, "MakeCode Extension for Cytron MOTION:BIT"); block category **"MOTION:BIT"** with groups DC Motors, Servos, RGB LED, External RGB LED [GH].
- Install: MakeCode → Extensions → search **"motionbit"** or paste **https://github.com/cytrontechnologies/pxt-motionbit** [GH]. MakeCode page: https://makecode.microbit.org/pkg/CytronTechnologies/pxt-motionbit ("Approved content") [GH].
- Blocks: `brake motor`, `run motor %motor %direction at speed %speed`, `disable servo`, `set servo %servo position to %position degrees`, `clear all RGB pixels`, `set RGB pixels brightness to`, `set all RGB pixels to`, `set RGB pixel %pixel to`, plus external-RGB equivalents [GH].
- micro:bit **V1 and V2** supported [GH README].
- **Python:** not stated by Cytron. No Cytron MicroPython library found. Resellers say MakeCode's JavaScript/Python text modes can be used [3P] — see Needs verification.

## Compatibility and accessories
- micro:bit V1 & V2 [GH]. The micro:bit is not included [3P].
- Maker Ports: Qwiic, STEMMA QT, Grove (via conversion cable) [DS].
- External WS2812B RGB LEDs on the Ext. RGB LED connector [DS].
- Power: 18650 Li-Ion, external LiPo or 4x AA (3.6–6 V) [DS].
- Bigger sibling: **MOTION:BIT Pro** (7–12 V input, 3 A / 5 A motor, servo power jumper, no battery) — separate product, see `motion-bit-pro.md`. It uses the same MakeCode extension [DS Pro].
- Package contents and bundles (e.g. with 18650 battery, with micro:bit Junior kit) are listed by resellers only [3P] — see Needs verification.

## Common mistakes / troubleshooting
- **Motors/servos don't move but the micro:bit runs** → board switch Off (micro:bit can run from its own USB); turn the MOTION:BIT on. The extension re-initialises the PCA9685 on each call for this reason [GH].
- **Can't upload code through the board's USB** → that port is power/charge only [DS].
- **Servo jitters or browns out** → servos share the supply voltage; check battery charge and the 1.5 A peak / 300 mA 5V limits [DS].
- **Motor runs the wrong way** → swap motor wires [DS].
- **External switch does nothing** → onboard switch must be Off [DS].
- **I2C sensor conflicts** → avoid address 0x40 [GH].
- **Using P8 for a sensor** → it drives the RGB LEDs [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Number of motor channels | [DS] does not state a count ("Motor Terminals") | [GH] "built-in 4-channel DC motor driver", M1–M4 | No conflict; use 4 with [GH] tag |
| Servo output current | [DS] not stated (5V total 300 mA; V+ = supply) | [3P] Switch Science "3 A" servo output | Not stated as spec; Needs verification |
| Product code | [DS] doc title "MOTION-BIT" | [3P] Switch Science "CYTRON-MOTION-BIT"; RobotShop bundle MPN "CK-MOTION-BIT-B" (with 18650) | Use MOTION-BIT; confirm on my.cytron.io |
| Python support | [DS]/[GH] not stated | [3P] RobotShop/Switch Science: JavaScript or Python mode in MakeCode | Needs verification |

## Needs verification
- Maker Ports pin pairing — datasheet text "P0-P9, P1-P2, P2-P12" lists P2 twice; confirm which pins each of the 3 Maker Ports carries.
- Whether the 1 A / 1.5 A motor rating is per channel or total.
- Motor driver IC part number and whether `brake motor` (both outputs 0) brakes or coasts.
- [3P] MakeCode Python/JavaScript mode; no MicroPython (python.microbit.org) support confirmed.
- Battery charge current, charging while running, and behaviour with both battery and external input connected.
- Whether the 1 A / 1.5 A motor rating is per channel or total (comparison image does not say).
- Maker Port pin pairing — still only the datasheet text ("P0-P9, P1-P2, P2-P12").

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Build an Autonomous Obstacle-Avoiding Robot Car Using MOTION:BIT](https://my.cytron.io/tutorial/build-an-obstacle-avoiding-robot-car-using-motionbit) — Tutorial, Beginner, 2023 [PP: tutorial]
- [Getting Started with MOTION:BIT & Projects Guide](https://my.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide) — Tutorial, Beginner, 2023 (series, 8 parts) [PP: tutorial]
- [CONTROL OMNI ROBOT CAR WITH MOTION:BIT USING BLUETOOTH APP](https://my.cytron.io/tutorial/control-omni-robot-car-with-motion:bit-using-bluetooth-app) — Project, Intermediate, 2023 [PP: tutorial]
- [Line Following with MOTION:BIT and Maker Line](https://my.cytron.io/tutorial/line_following_robot_car_using_motionbit) — Tutorial, Beginner, 2026 [PP: tutorial]

## Sources
- [DS] MOTION:BIT Datasheet Rev 1.0, February 2023 — https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit (public). PDF mirror, same revision: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-424/pdf/motionbit-simplifying-motion-control-microbit-jr-kit-18650-li-ion-battery-datasheet.pdf
- [PP] https://www.cytron.io/p-motionbit (linked from the [GH] README; **not read**)
- [GH] https://github.com/CytronTechnologies/pxt-motionbit — README.md, pxt.json, motor.ts, rgb.ts (raw.githubusercontent.com, master)
- [GH] https://makecode.microbit.org/pkg/CytronTechnologies/pxt-motionbit
- [VEN] https://tech.microbit.org/hardware/edgeconnector/
- [3P] (cross-check only) https://thepihut.com/collections/cytron/products/motion-bit-for-micro-bit · https://www.switch-science.com/products/9789 · https://www.robotshop.com/products/motionbit-simplifying-motion-control · https://eu.robotshop.com/products/motionbit-18650-li-ion-battery
- Cytron tutorial (linked by The Pi Hut, **not read**): https://www.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
