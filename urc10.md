# URC10 Sumo Robot Controller — Verified Reference

| | |
|---|---|
| Product code | `URC10` (datasheet title "URC10 Sumo Robot Controller" [DS]; user manual cover "SUMO ROBOT CONTROLLER, CODE: URC10" [UM]) |
| Family | Cytron sumo robot controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (description, features, pin assignment, resources). Microcontroller, current limiting, PWM modes and regulator ratings are now Cytron-stated [PP] |
| Primary source | URC10 Sumo Robot Controller Datasheet, **Rev 1.0, March 2019** [DS] (local file `URC10 Datasheet.pdf`) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = URC10 Sumo Robot Controller User's Manual **V1.2, April 2019**.  = the AI Coding Pack notes (`pin-map.md`, `hardware-setup.md`, `safety-rules.md`, `troubleshooting.md`, `library-reference.md`, `product-context.md`, `source-audit.md`, `auto-kit-mode/ir-sumo-start-integration.md`). [GH] = CytronTechnologies/URC10SumoRobot sample sketch (identical to the pack's `URC10SumoRobot.ino`). "DS fig" = a fact read from a datasheet drawing or board silkscreen, not from datasheet text. [PP] here = Cytron's own "Building a Sumo Robot" guide on Hackster, linked from the UM as the build guide (the my.cytron.io product page was not read). No [DT] confirmation exists for this product.

## What it is
An Arduino UNO-compatible controller board with an onboard 2-channel brushed DC motor driver, made for sumo robots [DS][UM]. It has the Arduino UNO standard female header, 6 digital and 6 analog/digital 3-pin ports, 2 HC-SR04 ultrasonic ports, an I2C port, an ISP port, motor test buttons and motor status LEDs [DS]. It is programmed from the Arduino IDE over USB Micro-B through a CH340 USB-to-UART converter, and its sample code uses the Cytron Motor Drivers Library [UM][GH]. The bottom silkscreen names it "2x10A UNO ROBOT CONTROLLER" [DS fig].

## Specifications
Datasheet section "2. SPECIFICATIONS", Table 3 "URC10 Absolute Maximum Ratings" — every row:

| Item | Value | Src |
|---|---|---|
| Power Input Voltage (Vin) | 8 – 25 VDC | [DS] |
| Maximum Motor Current, Continuous | 10 A max | [DS] |
| Maximum Motor Current, Peak (< 10 seconds) | 30 A max | [DS] |
| Logic Input Voltage, Low Level | 0 – 0.7 V | [DS] |
| Logic Input Voltage, High Level | 1.5 – 5.0 V | [DS] |
| DC +3V3 Output Maximum Current | 500 mA | [DS] |
| DC +5V Output Maximum Current | 1000 mA | [DS] |
| IO pin Maximum Current | 20 mA | [DS] |

Other board facts:

| Item | Value | Src |
|---|---|---|
| Motor channels | 2 (Motor 1, Motor 2). Bottom silkscreen: "2x10A", "MOTOR1 (10A)", "MOTOR2 (10A)" — i.e. 10 A is per channel | [DS][DS fig] |
| Motor control interface | PWM + DIR per channel (Table 2 truth table) | [DS] |
| Board size | 99.70 mm × 75.57 mm | [DS fig 2] |
| Mounting holes | 4 × ⌀3 mm, spaced 94.62 mm × 70.49 mm | [DS fig 2] |
| USB | USB Micro B connector: upload Arduino program from PC; Serial Monitor debugging | [DS] |
| USB-to-UART chip | CH340 ("This board uses CH340 USB to UART converter") | [UM] |
| Arduino IDE board | Screenshots show Board "Arduino/Genuino Uno" | [UM fig] |
| Reverse polarity protection | **None stated.** DS warning: "Connecting in reverse polarity will damage the board instantaneously." | [DS] |
| Over-current / thermal protection | Not stated in DS or UM | [DS][UM] |
| Motor PWM frequency | Not stated in DS or UM | [DS][UM] |
| Operating temperature, weight | Not stated | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **MCU:** description: "URC10 is using **Atmega328P**, which is the same microcontroller used on official Arduino Uno board" — select Arduino/Genuino Uno in the IDE; features: "ATmega328 microcontroller with Optiboot Bootloader" [PP].
- Designed for sumo robots up to **3 kg**; Vmotor/Vin DC 8–25 V; 10 A continuous, 30 A peak per channel; **current limiting at 30 A per channel**; motor quick-test buttons; output-state LEDs; **sign-magnitude and locked-antiphase PWM; PWM up to 20 kHz**; onboard 5 V regulator 1 A max; 3.3 V regulator 500 mA max [PP].
- **Pin assignment (page):** D4, D5 Motor 1; D6, D7 Motor 2; D8, D9 Ultrasonic 1; D10, D11 Ultrasonic 2 (or other digital I/O); D2, D3, D12, D13 any digital sensors; A0–A5 analog sensors; 1x I2C port; USB Micro-B + CH340 for uploading; **no reverse polarity protection**; 75.57 × 99.7 mm [PP].
- **Packing:** 1x URC10 R1.1 [PP].
- Resources: datasheet, 3D CAD, user manual, sample code (GitHub URC10SumoRobot), URC10 Rev1.10 schematic, tutorial "Building A Sumo Robot" [PP].

## Interfaces, terminals and pin mapping
Board functions (DS Table 1 and Figure 1):
- **Power Input Terminal**: VM = positive, GND = negative. Shares one 6-way screw terminal block with the motors, order M1A, M1B, VM, GND, M2A, M2B [DS][DS fig].
- **Motors Terminal**: M1A/M1B (Motor 1), M2A/M2B (Motor 2). "Motor direction depends on the polarity." [DS]
- **Power LED**: on when powered [DS].
- **Motor Status LEDs**: M1A/M2A = Forward*, M1B/M2B = Backward*; on when the motor runs [DS].
- **TX/RX LEDs**: on when data is sent/received on the serial port [DS]. The UM says "the LED at D0 and D1" blink during upload [UM].
- **Test Buttons** (M1A, M1B, M2A, M2B): test the motor driver; "Motor will run at full speed." M1A/M2A = Forward*, M1B/M2B = Backward* [DS].
- **Reset Button**: resets the microcontroller [DS].
- **Arduino UNO Standard Female Header**: standard Arduino UNO form factor, takes compatible shields; "Pin D4, D5, D6 D7 are connected to motor driver internally. Avoid using shield that uses these pins." [DS]
- **Digital Port × 6** (3-pin: GND, +5V, Signal): D0 – D3 and D10 – D13. "Pin D0 and D1 are used for serial communication." [DS]
- **Analog/Digital Port × 6** (3-pin: Signal, +5V, GND): A0 – A5, analog input or digital I/O [DS].
- **Arduino UNO Standard ISP Port**: load program with an AVR programmer; also usable for SPI [DS].
- **HC-SR04 Ultrasonic Sensor Port × 2** (+5V, TRIG, ECHO, GND): Sensor 1 ECHO D8, TRIG D9; Sensor 2 ECHO D10, TRIG D11 [DS].
- **I2C Port**: SCL, SDA, PWR, GND. PWR voltage selectable on the bottom layer: +3V3 by default; for +5V "cut trace and solder center pad and 5V pad together" [DS].
- **Power Port**: breakout of the Arduino power pins NC, IOREF, RESET, +3V3, +5V, GND, GND, VIN [DS].
- **Motor Driver Port (connected internally)**: Motor 1 DIR D4, PWM D5; Motor 2 DIR D7, PWM D6 [DS].

\* Actual direction depends on motor wiring; swapping MA and MB reverses it [DS].

PWM/DIR truth table (DS Table 2):

| PWM | DIR | Output A (MA) | Output B (MB) | Motor |
|---|---|---|---|---|
| Low | X (don't care) | Low | Low | Brake |
| High | Low | High | Low | Forward* |
| High | High | Low | High | Backward* |

Sample-sketch pin use (URC10SumoRobot.ino, a wiring choice, not fixed hardware) [GH][UM fig]:

| Pin | Sketch name | Use |
|---|---|---|
| D0, D1 | LED0, LED1 | "Onboard LED 0/1", driven active low (HIGH = off) |
| D13 | BUTTON | Start button, `INPUT_PULLUP`, pressed = LOW |
| D12 / D11 | EDGE_L / EDGE_R | Edge sensors, `INPUT_PULLUP`, edge = LOW |
| D3 / D10 | OPPONENT_L / OPPONENT_R | Side opponent sensors, `INPUT_PULLUP`, detected = LOW |
| A0 / A1 / A2 | OPPONENT_FR / FC / FL | Front opponent sensors, read with `digitalRead()` |
| D5 + D4 | motorL | `CytronMD motorL(PWM_DIR, 5, 4)` (Motor 1) |
| D6 + D7 | motorR | `CytronMD motorR(PWM_DIR, 6, 7)` (Motor 2) |

IR Sumo Start (separate product): the pack's Auto Kit notes wire module + to 5V, − to GND and S to **D2**, read with `pinMode(2, INPUT)` (not `INPUT_PULLUP`), HIGH = run, LOW = stop . D2 is on the URC10 Digital Port, which has GND/+5V/Signal pins [DS]. See the IR Sumo Start KB entry for the module's own specs.

## Rules and gotchas (for code, wiring and tutorials)
- Never use D4, D5, D6, D7 for anything else, and avoid shields that use them — they drive the motor driver [DS].
- Motor 1 = PWM D5 / DIR D4; Motor 2 = PWM **D6** / DIR **D7**. Motor 2's PWM and DIR are in the opposite order to Motor 1 [DS]. Library order is `CytronMD(PWM_DIR, pwmPin, dirPin)` [GH].
- HC-SR04 Sensor 2 uses D10 and D11, which are also on the Digital Port. In the sample wiring D10 = OPPONENT_R and D11 = EDGE_R, so ultrasonic Sensor 2 cannot be used with that wiring [DS][GH].
- D0/D1 are the serial pins (USB upload and Serial Monitor) [DS]. The sample sketch also drives them as LEDs; do not drive D0/D1 as outputs in a sketch that uses `Serial` [GH].
- On an Arduino UNO, D0 = RX and D1 = TX [VEN]. The pack's `pin-map.md` has these reversed (see *Conflicts*).
- Sensors in the sample are active low with `INPUT_PULLUP`; a triggered sensor reads LOW [GH].
- The start button in the sample sketch is on D13 and is **not** an onboard button: the board's only buttons are the 4 motor test buttons and Reset [DS][DS fig]. Wire an external button from D13 to GND .
- The sample `startRoutine()` waits **1 s** (`delay(1000)`) before moving. The pack notes say most sumo rules require a 5 s delay; change it for competition use [GH].
- Motor test buttons run motors at **full speed** — lift the wheels first [DS].
- The I2C port's PWR pin is **3.3 V by default**; 5 V needs a solder-jumper change on the bottom layer [DS].
- Swapping a motor's two wires (MA/MB) reverses its direction; fix direction in wiring or by negating speed in code [DS].
- Program in the Arduino IDE with the CH340 COM port selected; on macOS the port appears as `/dev/cu.wchusbserial…` [UM].

## Power and electrical limits
- Battery input: **8 – 25 VDC** on VM (+) / GND (−) [DS]. The bottom silkscreen says "POWER (7-24V)" (see *Conflicts*).
- **No reverse polarity protection**: reverse connection "will damage the board instantaneously" [DS].
- Motor current: **10 A continuous, 30 A peak (< 10 seconds)** [DS], per channel ("2x10A", "MOTOR1 (10A)", "MOTOR2 (10A)" [DS fig];  also states per channel).
- +5V output: 1000 mA max; +3V3 output: 500 mA max; any IO pin: 20 mA max [DS].
- Logic input voltage: Low 0 – 0.7 V, High 1.5 – 5.0 V [DS] (the datasheet does not say which inputs this row covers).
- The 3-pin sensor ports supply +5V [DS]; their total draw comes out of the 1000 mA +5V budget [DS].
- The hackster build guide linked from the UM uses an 11.1 V 3-cell 1300 mAh LiPo and 12 V 380 RPM geared motors (2 per side, paired on one channel) [PP].

## Software support
- Arduino IDE (UM install guide shows Arduino 1.8.x) [UM].
- CH340 driver: UM links Windows `https://cdn.cytron.io/makeruno/CH341SER.EXE` and macOS `https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP` [UM].
- Motor library: **Cytron Motor Drivers Library** by Cytron Technologies (Library Manager search "cytron motor drivers library"; UM screenshot shows version 1.0.1), `#include <CytronMotorDriver.h>`, `CytronMD motor(PWM_DIR, pwm, dir)`, `setSpeed(-255…255)` [UM][GH].
- Sample code: GitHub `CytronTechnologies/URC10SumoRobot` ("Arduino example program for Sumo Robot using URC10") [UM][GH]. Behaviour: shows edge-sensor state on D0/D1 LEDs while waiting for the button; on press runs a start routine (1 s delay, ~45° turn, straight run, scan); searches in a circle; attacks at full speed when an opponent sensor triggers; backs off and turns at the ring edge; stops for good if the button is pressed again [GH].
- Older library `CytronTechnologies/URC10-Arduino-Library` (name=URC10, version 1.0.0, "Library for using Cytron Uno Robot Controller") exists; the UM does not use it [GH].
- Uploading via the ISP port with an AVR programmer is also possible [DS].
- MicroPython / CircuitPython / MakeCode: not stated.

## Compatibility and accessories
- Arduino UNO shields that do not use D4–D7 [DS].
- HC-SR04 ultrasonic sensors (2 ports) [DS]; I2C devices at 3.3 V (default) or 5 V [DS].
- Build guide parts (Cytron Hackster guide linked from UM): 4 × 12V 380RPM 1.4kgfcm DC geared motors, 2 × JSumo silicone wheel sets, 5 × IR sensors (3–80 cm), 2 × IR line tracking modules, 11.1V 1300mAh LiPo [PP].
- Packing list / USB cable included: not stated.

## Common mistakes / troubleshooting
- No COM port: install the CH340 driver; use a data-capable USB cable [UM].
- `CytronMotorDriver.h: No such file`: install the Cytron Motor Drivers Library [UM].
- Robot does nothing after upload: the sample waits in `setup()` for the D13 button press [GH].
- Wrong direction / spinning in place: swap the two wires of the motor going the wrong way [DS].
- Ultrasonic Sensor 2 reads garbage: D10/D11 already used by sensors [DS][GH].
- Board dead after battery connected backwards: reverse polarity is not protected [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Input voltage | [DS] spec table (Rev 1.0, Mar 2019): 8 – 25 VDC | [DS fig] bottom silkscreen: "POWER (7-24V)"; older Cytron "2x10A UNO Robot Controller (URC10)" manual V1.0 Sep 2017 (reseller copy) [3P]: 7–24 V in ratings, 6–24 V in intro | DS table wins: 8 – 25 VDC. The 2017 manual is older |
| Peak motor current duration | [DS]: 30 A peak, < 10 seconds | 2017 manual ratings table [3P]: peak must not exceed 1 second (intro says 10 s) | DS wins: < 10 s |
| D0/D1 roles |  pin-map.md: D0 = TX, D1 = RX | Arduino UNO convention [VEN]: D0 = RX, D1 = TX; [DS] only says "used for serial communication" | Use D0 = RX, D1 = TX; fix pin-map.md |
| Start button |  product-context.md: "1x push button (D13)" as a board feature | [DS]: buttons are 4 motor test buttons + Reset only; D13 button is external in the sample | DS wins: no onboard start button |
| Sensor ports | : "dedicated EDGE_L and EDGE_R ports"; "Front (3x), Side (2x), Edge (2x)" ports | [DS]: generic Digital Port × 6 and Analog/Digital Port × 6; sensor roles come only from the sample sketch | DS wins: no dedicated sensor ports |
| Motor terminal names |  hardware-setup.md: "Motor Left (MOTA)", "Motor Right (MOTB)" | [DS]: M1A/M1B, M2A/M2B | DS wins |
| Brushed motor voltage | [DS]: Vin 8 – 25 VDC | Cytron Tindie listing [3P]: "drive brushed motor from 6V to 24V"; RobotShop [3P]: "8V to 25V brushed motor" | DS wins |

## Needs verification
- "3.3V compatible inputs" and "LED indicator for each I/O pin" [3P]. DS fig shows LED positions marked PWR, D13, D12, D11, D10, D9, D8, D3, D2, D1, D0, but DS text describes only the Power LED and TX/RX LEDs.
- Whether the board (logic) runs from USB alone without the battery; whether Power Port **VIN** carries the raw battery voltage (up to 25 V) — matters for shields.
- Whether I2C SCL/SDA are shared with A5/A4 and whether ISP/SPI is shared with D11–D13, as on an Arduino UNO [VEN inference].
- Which inputs the "Logic Input Voltage" row applies to.
- Edge-sensor output polarity depends on the sensor module used; the sample treats LOW as "edge" [GH].
- Drive catalogue image `CATALOGUE_URC10.png` returned no text and was not read.
- Microcontroller wording: description says ATmega328P, feature list says ATmega328 — treat as ATmega328P (description) and confirm on the board marking.
- Over-heat / over-current cut-off beyond the stated 30 A current limit — not on the product page.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [1KG Autonomous Sumo Robot Starter Kit User Guide using URC10](https://my.cytron.io/tutorial/1kg_sumo_robot_urc10) — Tutorial, Beginner, 2024 (series, 4 parts) [PP: tutorial]
- [1KG Autonomous Sumo Robot using URC10](https://my.cytron.io/tutorial/1-kg-autonomous-sumo-robot-starter-kit-user-guide-using-urc10) — Tutorial, Beginner, 2025 [PP: tutorial]
- [Mastering Wireless Control with URC10](https://my.cytron.io/tutorial/mastering-wireless-control-with-urc10) — Tutorial, Beginner, 2025 (series, 4 parts) [PP: tutorial]
- [Battle Robot with URC10](https://my.cytron.io/tutorial/battle-robot-with-urc10) — Tutorial, Beginner, 2026 [PP: tutorial]
- [Line Following with Robo Base using URC10](https://my.cytron.io/tutorial/line-following-robo-base-urc10) — Project, Intermediate, 2025 [PP: tutorial]

## Sources
- [DS] URC10 Sumo Robot Controller Datasheet, Rev 1.0, March 2019 — local file `URC10 Datasheet.pdf` (AI Coding Pack `source-docs/`); no public URL found
- [UM] URC10 Sumo Robot Controller User's Manual V1.2, April 2019 — local file `URC10 Sumo Robot Controller User's Manual.pdf`
- [GH] https://github.com/CytronTechnologies/URC10SumoRobot (sketch read from https://raw.githubusercontent.com/CytronTechnologies/URC10SumoRobot/master/URC10SumoRobot/URC10SumoRobot.ino; same as local `URC10SumoRobot.ino`)
- [GH] https://github.com/CytronTechnologies/URC10-Arduino-Library (library.properties)
- [PP] https://www.hackster.io/cytron-technologies/building-a-sumo-robot-45d703
- [UM] driver links https://cdn.cytron.io/makeruno/CH341SER.EXE and https://cdn.cytron.io/makeruno/CH341SER_MAC.ZIP
- IR-SUMO-START Datasheet — local file `IR-SUMO-START Datasheet.pdf` (connection cross-check only)
- [3P] https://www.robotshop.com/products/cytron-2-channel-10a-uno-robot-controller
- [3P] https://cdn.robotshop.com/media/c/cyt/rb-cyt-230/pdf/uno-robot-controller-datasheet.pdf (older Cytron manual V1.0, Sep 2017; read via summary only)
- [3P] https://www.tindie.com/products/Cytron/sumo-robot-controller-arduino-compatible/
- Product page: not read (my.cytron.io returns 403 here)
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
