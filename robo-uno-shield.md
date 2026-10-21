# Robo Uno Shield — Verified Reference

| | |
|---|---|
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron GitHub `Cytron-SHIELD-ROBO-UNO` (supplied by the marketing team as "Schematic & Design Files") read in full: README, all 9 Getting_Started_Guide sketches and Demo_Code, full commit history (2 Jan – 12 Feb 2025, HEAD 823f5c2, branch `main` only). It settled the 10 IO-LED pins (D0–D3, A0–A5), the example wiring on Grove 1/4/6, and added a DCMotor header block that names D4 DIR 1, D5 PWM 1, D6 PWM 2, D7 DIR 2. **The repo holds no schematic, PCB or PDF in any commit**, so the motor-control scheme stays a [DS] vs [GH] conflict. Stays Medium; still open: motor control scheme and driver IC (needs [DT]), Grove 3 pins, button pull-ups. Earlier: 2026-10-19 master-table review of the live product page (logic levels, power options, protections, motor ratings, size and package Cytron-stated) |
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
| GPIO status LEDs | 10 ("2x RGB LEDs / 10x GPIO LEDs"), on D0, D1, D2, D3, A0, A1, A2, A3, A4, A5 (Cytron Blink sketch drives exactly these 10 pins as "IO LEDs") | [GH] |
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
| Status LEDs | IO indicators for the Grove-port pins; on when the pin is high [DS]. The 10 LED pins are D0–D3 and A0–A5 [GH Blink sketch] | [DS][GH] |
| VIN terminal block | 3.6–6 V, reverse polarity protected | [DS] |
| LiPo connector | JST PH2.0, single-cell LiPo/Li-ion | [DS] |
| Micro-USB port | Power and battery charging only — no data, no code upload | [DS] |
| On/Off switch, Power LED, Reset button (resets shield and microcontroller) | — | [DS] |
| Motor test buttons / motor status LEDs | MxA: Forward*, MxB: Backward*; test runs the motor at full speed | [DS] |

**Example connections in Cytron's Getting Started sketches** [GH]:

| Sketch | Port | Wiring as written |
|---|---|---|
| Read_Sensor_Analog_Arduino | Grove 1 | Maker Soil: GND, VCC, A0 – DIS, A1 – OUT (table); the code reads A0 and calls it "OUT" — see Conflicts |
| Read_Sensor_Digital_Arduino | Grove 6 | Ultrasonic sensor: D3 – TRIG, D2 – ECHO |
| OLED_Arduino | Grove 4 | Grove OLED: A4 – SDA, A5 – SCL; U8g2 `U8G2_SSD1306_128X64_NONAME_F_SW_I2C` (software I2C on SCL/SDA) |
| UserButton_Arduino | on-board | Button D2 lights the A2 LED, button D3 lights the A5 LED |

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
- Buttons D2/D3 are also Grove 6 pins — using Grove 6 and the buttons at the same time shares pins [DS]. The Grove 6 ultrasonic example uses D3 = TRIG, D2 = ECHO, so the buttons and that sensor cannot be used together [GH].
- **IO LEDs sit on D0–D3 and A0–A5** [GH]: whatever drives those pins (a Grove module, the buttons, UART traffic) also lights the LED, since it is on when the pin is high [DS].
- **D0/D1 are the UART** (Grove 5) and also carry IO LEDs. Demo_Code starts `Serial.begin(9600)` and then drives D0/D1 as LED outputs [GH]; on an Uno that interferes with serial output (general Arduino behaviour [VEN]; inferred). Do not blink D0/D1 in a sketch that uses Serial.
- **Buttons:** Cytron sketches set `INPUT_PULLUP` and read pressed = LOW [GH]. The Buzzer sketch reads D3 without setting `pinMode(3, INPUT_PULLUP)` — always set it for both buttons (whether the board has its own pull-ups is not stated).
- **RGB LEDs:** `Adafruit_NeoPixel(2, 13, NEO_GRB + NEO_KHZ800)`; Cytron dims them in code (Demo_Code `setBrightness(25)`, commented "10%") [GH].
- **Servo sweep bug:** the Servo sketch's return loop starts at 200, above 180 — use 180. The sketch notes that on a 360° continuous-rotation servo `write()` sets speed (≈90 stop, 0 and 180 full speed opposite ways) [GH].
- **Comment errors in the sketches — do not copy:** "pin GP25" (RGB sketch, really D13), "3.3V is the board's voltage reference" (analog sketch; the code correctly uses 5.0 V), "Button connected to pin D2" on the D3 line (Buzzer sketch), "PWM 1A = Pin 4, PWM 1B = Pin 5" and "4 PWM pins (2 for each motor)" (DCMotor sketch) [GH].
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
- **Arduino IDE** — Cytron GitHub `Cytron-SHIELD-ROBO-UNO` (sketches added 2 Jan 2025; Demo_Code added 12 Feb 2025; HEAD 823f5c2, branch `main`, no tags or other branches) has Getting_Started_Guide sketches: Blink, RGB, UserButton, Buzzer, Servo, DCMotor, Read_Sensor_Analog, Read_Sensor_Digital, OLED, plus an out-of-the-box Demo_Code [GH]. README hardware list: Robo Uno Shield, Arduino UNO or Maker Uno, OLED Display SSD1306; setup points to the "Getting Started Guide with Robo Uno Shield" tutorial; its "Resources" tutorial bullets are empty [GH].
- **Demo_Code (out-of-the-box) sequence** [GH]: Happy Birthday melody on D8 → IO LEDs one by one (D0–D3, then A0–A5) and all together → RGB colour cycle → servos on D9 and D10 sweep 180°→0°→180° (RGB green, then red) → both motors 50 % forward/reverse twice with tones → loop: D2 = cyan/magenta RGB + rising C-E-G tones, D3 = yellow/green RGB + falling G-E-C. Serial 9600 prints "Robo Uno Shield OOTB Demo". Servos D11/D12 are not used in the demo.
- Serial monitor examples (analog and ultrasonic sketches) use 9600 baud; the analog sketch converts with `raw × 5.0 / 1023` [GH].
- Libraries used in Cytron examples: Cytron Motor Drivers Library (`CytronMotorDriver.h`, `PWM_DIR` mode); `Servo.h`; `Adafruit_NeoPixel` (2 pixels on D13, `NEO_GRB + NEO_KHZ800`); `U8g2lib` (`U8G2_SSD1306_128X64_NONAME_F_SW_I2C`, code adapted from the Seeed Grove OLED 0.96" SSD1315 wiki) for the OLED on Grove 4; `tone()` / `noTone()` for the buzzer [GH].
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
| GH example comments | [GH] DCMotor code `PWM_DIR, 5, 4` and the file's CONNECTIONS header "D4 – DIR 1, D5 – PWM 1, D6 – PWM 2, D7 – DIR 2" | [GH] same file: inline comment "PWM 1A = Pin 4, PWM 1B = Pin 5" and description "4 PWM pins (2 for each motor)" | Follow the code and the CONNECTIONS header, not the other comments |
| OLED controller in examples | [GH] README: "OLED Display SSD1306" (0.96" 128×64); code uses the U8g2 SSD1306 128×64 constructor | [GH] OLED sketch header: "OLED Display SSD1315" (Seeed Grove) | Both are 128×64 I2C OLEDs driven by the same U8g2 SSD1306 constructor in Cytron's code; name the module actually used |
| Grove 1 analog example | [GH] wiring table: A0 – DIS, A1 – OUT (Maker Soil) | [GH] code: `sensorPin = A0` commented "OUT pin" | Unresolved in source; check which Grove signal the module puts its output on before reading A0 or A1 |
| "Schematic & Design Files" label | Marketing hand-off labelled the GitHub repo as schematic and design files | [GH] repo content: README + Arduino sketches only, no design file in any commit (checked 2026-10-21) | No [DT] source exists yet; ask the design team for the schematic |
| LiPo + VIN together | [DS] footnote "perfectly safe" | [DS] precaution "one power source only at one time" | Advise one source at a time |
| Status |  Launched Feb 2025 | [3P] The Pi Hut: "Discontinued" | Unresolved; check my.cytron.io |

## Needs verification
- **Motor control scheme** — whether the shield takes PWM+DIR (D5/D4, D6/D7) through on-board logic or raw A/B inputs on D4–D7. If D4 = Input A and D5 = Input B literally, Cytron's `PWM_DIR` code would not give symmetric speed in reverse (derived from [DS] table + [GH] library). The DCMotor sketch's CONNECTIONS header (D4 DIR 1, D5 PWM 1, D6 PWM 2, D7 DIR 2) adds [GH] weight to PWM/DIR but cannot override [DS] — ask [DT] for the schematic.
- **Schematic / design files** — none in the Cytron-SHIELD-ROBO-UNO GitHub repo (full history and all branches checked 2026-10-21; the GitHub API listing could not be queried from this session, but `git ls-remote` shows only `main`). Ask the design team.
- Whether buttons D2/D3 have on-board pull-up resistors (Cytron code always enables `INPUT_PULLUP`, except D3 in the Buzzer sketch).
- Grove 3 pin assignment (A1, A3 as printed) — confirm against the board silkscreen. No Cytron sketch uses Grove 3, and the 10 IO-LED pins (D0–D3, A0–A5) are exactly the Grove 1, 2, 4, 5 and 6 pins [GH], so the GitHub code gives no separate Grove 3 pins (inference).
- Whether the shield powers the Arduino board, and whether "USB" in Table 2 means only the shield's micro-USB.
- mBlock extension availability and name.
- Whether fresh 4xAA alkaline cells stay within the 6 V absolute maximum (DS gives 4xAA as an example).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Getting Started with Robo Uno Shield](https://my.cytron.io/tutorial/getting-started-guide-with-robo-uno-shield) — Tutorial, Beginner, 2025 (series, 24 parts) [PP: tutorial]
- [Display Animation on OLED with Maker UNO and Robo UNO Shield](https://my.cytron.io/tutorial/display-animation-on-oled-with-maker-uno-and-robo-uno-shield) — Tutorial, Beginner, 2025 [PP: tutorial]

## Sources
- [DS] Robo Uno Shield Datasheet, Rev 1.0, February 2025 — https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit (public; PDF mirror: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-428/pdf/cytron-robo-uno-shield-for-arduino-all-in-1-robotics-shield-datasheet.pdf)
- [GH] Cytron-SHIELD-ROBO-UNO — https://github.com/CytronTechnologies/Cytron-SHIELD-ROBO-UNO (handed over by marketing as "Schematic & Design Files"; contains README.md, Getting_Started_Guide/* (9 sketches) and Demo_Code/Demo_Code.ino only; commits 2 Jan 2025 – 12 Feb 2025, HEAD 823f5c2 "Update README.md", branch `main`; read in full with full history 2026-10-21; no schematic or design file) · https://github.com/CytronTechnologies/CytronMotorDriver (CytronMotorDriver.cpp)
- [PP] Getting Started tutorial (not read — blocked): https://my.cytron.io/tutorial/getting-started-guide-with-robo-uno-shield
- [VEN] Arduino Uno Rev3 PWM pins (D3, D5, D6, D9, D10, D11) — https://docs.arduino.cc/
- [3P] (cross-check only) https://www.switch-science.com/products/10305 · https://thepihut.com/products/robo-uno-shield · https://uk.robotshop.com/products/cytron-robo-uno-shield-for-arduino-all-in-1-robotics-shield
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
