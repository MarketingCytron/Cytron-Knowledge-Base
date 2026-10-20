# Robo Uno Shield — Verified Reference

| | |
|---|---|
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read plus the dimension image. Logic-level behaviour, power options, protections, motor ratings, size and package now Cytron-stated |
| Primary source | Robo Uno Shield Datasheet — **Rev 1.0, February 2025** (public Google Doc "SHIELD-ROBO-UNO Datasheet"): https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
An Arduino Uno-form-factor robotics shield with a dual-channel H-bridge DC motor driver (2 DC motors, 1 A continuous / 1.5 A peak < 5 s per channel), 4 RC servo ports, 6 Grove ports, 1 Maker Port, a piezo buzzer with mute switch, RGB LEDs, 2 programmable buttons, IO status LEDs, motor test buttons and a built-in single-cell LiPo/Li-ion charger [DS]. It is powered from 3.6–6 V through a VIN terminal block, a single-cell LiPo/Li-ion battery (JST PH2.0) or its own micro-USB port [DS]. Cytron positions it as "The All-in-One Robotics Shield" for Arduino Uno, Maker Uno and compatible boards .

## Specifications
Datasheet Table 2 is titled **"Robo Uno Shield Absolute Maximum Ratings"** [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB, LiPo or VIN) | Min 3.6 V, Max 6 V | [DS] |
| Digital input voltage, low level | 0 – 0.5 V | [DS] |
| Digital input voltage, high level | 2.7 – 5 V | [DS] |
| Digital output voltage, low level | 0 – 0.5 V | [DS] |
| Digital output voltage, high level | 4.2 – 5 V | [DS] |
| Analog input voltage | 0 – 5 V | [DS] |
| Vmotor & Vservo (only USB connected) | VUSB − 0.4 V | [DS] |
| Vmotor & Vservo (only one of LiPo or VIN connected) | VLiPo or VIN | [DS] |
| Vmotor & Vservo (USB and LiPo connected) | VUSB − 0.4 V | [DS] |
| Vmotor & Vservo (USB and VIN connected), VIN < VUSB | VUSB − 0.4 V | [DS] |
| Vmotor & Vservo (USB and VIN connected), VIN > VUSB and VIN − VUSB < 0.6 | VIN − 0.4 V | [DS] |
| Vmotor & Vservo (USB and VIN connected), VIN − VUSB > 0.6 | VIN | [DS] |
| Maximum DC motor current per channel, continuous | 1 A | [DS] |
| Maximum DC motor current per channel, peak | 1.5 A (< 5 seconds) | [DS] |
| DC motor driver PWM frequency | Max 20 kHz | [DS] |
| Total 5V output current (Grove ports) | Max 400 mA | [DS] |
| Operating temperature | −20 to 85 ℃ | [DS] |
| DC motor channels | 2 (dual-channel H-bridge) | [DS] |
| Servo ports | 4 x RC servo; V+ = power source voltage | [DS] |
| Grove ports | 6 | [DS] |
| Maker Port | 1 (QWIIC / Stemma QT / Grove with conversion cable), shared with Grove 4 | [DS] |
| RGB LEDs | User-programmable, on D13 (2 pixels in Cytron code) | [DS][GH] |
| Piezo buzzer | Bottom side, D8, with mute switch | [DS] |
| Programmable buttons | 2, on D2 and D3 | [DS] |
| Battery charger | Single-cell LiPo/Li-ion, charged via the shield's micro-USB; overcharge and over-discharge protection | [DS] |
| Reverse polarity protection | VIN terminal | [DS] |
| Motor driver IC part number | **Not stated** | [DS] |
| Dimensions | **Not stated in text** (Figure 4 drawing only) | [DS] |
| Charging current, quiescent current | **Not stated** | [DS] |

Footnotes [DS]: "Voltage for the DC motor and servo is equal to power input voltage." "It's not recommended to connect both LiPo and VIN at the same time. Although it's perfectly safe to do so."
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Specifications (page):** automatic power selection — VIN terminal block 3.6–6 V, VBAT LiPo port (1-cell LiPo/Li-ion 3.7 V), VUSB micro USB 5 V; **"VCC voltage automatically follow the microcontroller reset pin voltage"**; built-in 1-cell charger (over-charge and over-discharge protection); description adds over-current, over-voltage and short-circuit protection; power switch with status LED [PP].
- **Motors:** dual-channel H-bridge; quick-test buttons and LEDs; motor voltage 2.5–6 VDC; 1.0 A continuous, 1.5 A peak (< 5 s); up to 2 DC motors + 4 servos [PP].
- Grove ports and a Maker Port (Qwiic / STEMMA QT compatible) [PP].
- **Size:** 60.96 × 68.58 mm [PP: img dimension].
- **Packing:** 1x Robo Uno Shield, 1x small Phillips screwdriver, 4x Grove to female header cable [PP].
- Resources: datasheet (Google Doc), Getting Started tutorial, GitHub Demo_Code, 3D CAD [PP].

## Interfaces, terminals and pin mapping
| Function | Arduino pin(s) / terminal | Src |
|---|---|---|
| DC Motor Terminals (datasheet Table 1) | M1A: D4, M1B: D5, M2A: D6, M2B: D7 | [DS] |
| DC motor control in Cytron's code | Motor 1: PWM = D5, DIR = D4; Motor 2: PWM = D6, DIR = D7 (`CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);`) | [GH] |
| Servo ports (signal) | D9, D10, D11, D12 | [DS][GH] |
| Piezo buzzer | D8 | [DS][GH] |
| RGB LEDs | D13 | [DS][GH] |
| Programmable buttons | D2, D3 (Cytron code uses `INPUT_PULLUP`, pressed = LOW) | [DS][GH] |
| Grove 1 | A0, A1 | [DS] |
| Grove 2 | A2, A3 | [DS] |
| Grove 3 | A1, A3 (as printed in the datasheet table) | [DS] |
| Grove 4 | A4 (SDA), A5 (SCL) — I2C | [DS] |
| Grove 5 | D0 (RX), D1 (TX) — UART | [DS] |
| Grove 6 | D2, D3 | [DS] |
| Maker Port | A4, A5 — "shared with the Grove 4 port" | [DS] |
| Status LEDs | IO indicators for the Grove-port pins; on when the pin is high | [DS] |
| VIN terminal block | 3.6–6 V, reverse polarity protected | [DS] |
| LiPo connector | JST PH2.0, single-cell LiPo/Li-ion | [DS] |
| Micro-USB port | Power and battery charging only — no data, no code upload | [DS] |
| On/Off switch, Power LED, Reset button (resets shield and microcontroller) | — | [DS] |
| Motor test buttons / motor status LEDs | MxA: Forward*, MxB: Backward*; test runs the motor at full speed | [DS] |

**Motor driver truth table** [DS Table 3] (header printed as "Input A (GP8 / GP10)", "Input B (GP9 / GP11)" — see Conflicts):

| Input A | Input B | Output A (M1A/M2A) | Output B (M1B/M2B) | Motor |
|---|---|---|---|---|
| Low | Low | Low | Low | Brake |
| High | Low | High | Low | Forward* |
| Low | High | Low | High | Backward* |
| High | High | Hi-Z (Open) | Hi-Z (Open) | Coast |

*"Actual motor direction is dependent on the motor connection. Swapping the connection (MxA & MxB) will reverse the direction." [DS]

## Rules and gotchas (for code, wiring and tutorials)
- **Use Cytron's own motor code**: `#include "CytronMotorDriver.h"`, `CytronMD motor1(PWM_DIR, 5, 4);` and `CytronMD motor2(PWM_DIR, 6, 7);`, then `setSpeed(-255..255)` [GH]. Do not invent an A/B two-PWM mapping on D4–D7 from the datasheet table — the pin roles are an open conflict (see Conflicts).
- On Arduino Uno Rev3, `analogWrite()` PWM pins are D3, D5, D6, D9, D10, D11 [VEN] — D4 and D7 are not PWM pins, which is consistent with D5/D6 carrying PWM in Cytron's code.
- The truth-table headers "GP8 / GP10 / GP9 / GP11" are Pico-style pin names and do not exist on an Arduino Uno — never copy them into Arduino content.
- **The shield cannot be powered through the VIN pin of the microcontroller** (e.g. Arduino Uno, Maker UNO) [DS]. Power it from its own VIN terminal, LiPo port or micro-USB.
- **The shield's micro-USB cannot upload code or carry data** [DS]. Upload through the Arduino/Maker UNO's own USB port.
- **Only single-cell batteries are supported** [DS]. Do not connect 2S packs or 7.4 V batteries.
- Motor and servo voltage equals the power input voltage (or VUSB − 0.4 V on USB) [DS] — there is no separate motor supply.
- Use one power source at a time: "strongly advises to have one power source only at one time due to potential damage or malfunction" [DS] (the spec footnote also calls LiPo + VIN together "perfectly safe" — follow the precaution).
- If the board will not turn on with a battery connected, charge the battery to activate the battery protection circuit [DS].
- Motor test buttons run the motor at **full speed** — lift the wheels first [DS].
- Grove 4 and the Maker Port share A4/A5 — one I2C bus, not two [DS].
- Grove 5 uses D0/D1 (hardware UART); devices there can interfere with USB uploading on Uno-type boards (general Arduino behaviour [VEN]; not stated by Cytron).
- Buttons D2/D3 are also Grove 6 pins — using Grove 6 and the buttons at the same time shares pins [DS].
- Align the header pins vertically when stacking/removing to avoid bending them [DS].
- Brake (Low/Low) stops quickly but strains the motor; Coast (High/High) lets it spin down [DS].

## Power and electrical limits
- Power input 3.6–6 V on USB, LiPo or VIN (absolute maximum) [DS].
- Motor current 1 A continuous, 1.5 A peak (< 5 s) per channel; PWM max 20 kHz [DS].
- Total 5V output on the Grove ports: 400 mA max [DS].
- Protection stated in the datasheet: VIN reverse polarity; battery overcharge and over-discharge [DS]. Over-current, short-circuit and thermal protection of the motor driver: **not stated** [DS].
- Battery advice: choose capacity "e.g., 2000mAh or higher"; examples "3.7V with 2000mAh or more" LiPo, or 4xAA on the VIN terminal ("may drain quickly in demanding applications") [DS].
- Power tree (Figure 5.2) is an image only — rail details not readable as text [DS].

## Software support
- **Arduino IDE** — Cytron GitHub `Cytron-SHIELD-ROBO-UNO` (commit 12 Feb 2025) has Getting_Started_Guide sketches: Blink, RGB, UserButton, Buzzer, Servo, DCMotor, Read_Sensor_Analog, Read_Sensor_Digital, OLED, plus an out-of-the-box Demo_Code [GH].
- Libraries used in Cytron examples: Cytron Motor Drivers Library (`CytronMotorDriver.h`, `PWM_DIR` mode); `Servo.h`; `Adafruit_NeoPixel` (2 pixels on D13, `NEO_GRB + NEO_KHZ800`); `U8g2lib` for an SSD1315/SSD1306 OLED on Grove 4; `tone()` for the buzzer [GH].
- MicroPython / CircuitPython: **not stated**.

## Compatibility and accessories
- Datasheet names Arduino Uno and Maker UNO (in the VIN-pin note) [DS]; GitHub README lists "Arduino UNO or Maker Uno" [GH].

## Common mistakes / troubleshooting
- **Board dead on battery** → charge the battery via the shield's micro-USB to reset battery protection [DS].
- **Code won't upload through the shield's USB** → by design; use the controller board's USB [DS].
- **Shield not powered from the Uno's DC jack/VIN** → by design; power the shield's own inputs [DS].
- **Motor won't spin or only one direction works** → check you used `PWM_DIR` with (5, 4) and (6, 7) as in Cytron's code [GH]; press the motor test buttons to separate hardware from code [DS].
- **Motor runs the wrong way** → swap MxA/MxB wires [DS].
- **I2C device conflict** → Grove 4 and Maker Port are the same A4/A5 bus [DS].
- **Servos jitter / board resets under load** → battery capacity too low; DS recommends ≥ 2000 mAh single-cell [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Motor pin roles | [DS] Table 1: M1A D4, M1B D5, M2A D6, M2B D7; truth table uses Input A/Input B | [GH] `PWM_DIR`: PWM D5, DIR D4; PWM D6, DIR D7.  launch banners (image text): "PWM-1(D5)", "DIR-1(D4)", "PWM-2(D6)", "DIR-2(D7)" | Pins D4–D7 agree. Roles unresolved; in code follow [GH]. Ask [DT] |
| Truth-table input names | [DS] header "GP8 / GP10", "GP9 / GP11" | [DS] Table 1 D4–D7 (Arduino has no GP pins) | Copy-over error in DS; don't use GP names |
| Motor voltage | [DS] power input 3.6–6 V; Vmotor = input voltage |  idea doc / [3P] Pi Hut, RobotShop: "2.5V to 6V DC" | [DS] wins (3.6–6 V input) |
| Grove 1 pins | [DS] A0, A1 (UART on Grove 5: D0/D1) |  idea doc: "Grove 1: D0 & D1 (UART)" | [DS] wins (idea doc was pre-design) |
| Grove 3 pins | [DS] A1, A3 (duplicates Grove 1/2 pins) | — | Kept as printed; see Needs verification |
| GH example comments | [GH] DCMotor code `PWM_DIR, 5, 4` | [GH] same file comment "PWM 1A = Pin 4, PWM 1B = Pin 5" | Follow the code, not the comment |
| LiPo + VIN together | [DS] footnote "perfectly safe" | [DS] precaution "one power source only at one time" | Advise one source at a time |
| Status |  Launched Feb 2025 | [3P] The Pi Hut: "Discontinued" | Unresolved; check my.cytron.io |

## Needs verification
- **Motor control scheme** — whether the shield takes PWM+DIR (D5/D4, D6/D7) through on-board logic or raw A/B inputs on D4–D7. If D4 = Input A and D5 = Input B literally, Cytron's `PWM_DIR` code would not give symmetric speed in reverse (derived from [DS] table + [GH] library) — ask [DT].
- Grove 3 pin assignment (A1, A3 as printed) — confirm against the board silkscreen.
- Whether the shield powers the Arduino board, and whether "USB" in Table 2 means only the shield's micro-USB.
- mBlock extension availability and name.
- Whether fresh 4xAA alkaline cells stay within the 6 V absolute maximum (DS gives 4xAA as an example).

## Sources
- [DS] Robo Uno Shield Datasheet, Rev 1.0, February 2025 — https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit (public; PDF mirror: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-428/pdf/cytron-robo-uno-shield-for-arduino-all-in-1-robotics-shield-datasheet.pdf)
- [GH] https://github.com/CytronTechnologies/Cytron-SHIELD-ROBO-UNO (README.md, Getting_Started_Guide/*, Demo_Code/Demo_Code.ino; commit 823f5c2, 12 Feb 2025) · https://github.com/CytronTechnologies/CytronMotorDriver (CytronMotorDriver.cpp)
- [PP] Getting Started tutorial (not read — blocked): https://my.cytron.io/tutorial/getting-started-guide-with-robo-uno-shield
- [VEN] Arduino Uno Rev3 PWM pins (D3, D5, D6, D9, D10, D11) — https://docs.arduino.cc/
- [3P] (cross-check only) https://www.switch-science.com/products/10305 · https://thepihut.com/products/robo-uno-shield · https://uk.robotshop.com/products/cytron-robo-uno-shield-for-arduino-all-in-1-robotics-shield
