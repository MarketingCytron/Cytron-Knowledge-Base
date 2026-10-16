# MD25HV — Verified Reference

| | |
|---|---|
| Product code | `MD25HV` (datasheet title [DS]; product page packing list "1 x MD25HV" [PP]; GitHub library list [GH]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "MD25HV High Voltage 7V-58V 25Amp DC Motor Driver Datasheet" — **Rev 1.0, Jan 2019** — public Google Doc: https://docs.google.com/document/d/1xJHVG2dc3aEtedCHf3L9NzUy5KqpxeWjeS9Lfh9XuqA/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] read in full as text from the public Google Doc (found via web search); the same Rev 1.0 Jan 2019 document is mirrored as PDF on the RobotShop CDN and download.kamami.pl (footnote cross-checked). Figures (board layout, dimension drawing, connection diagrams, current-limit-vs-temperature graph) are images and were **not** readable. [PP] = www.cytron.io product page (read 16 Oct 2026).  = quick start guide PDFs on Drive (OCR largely garbled; used only for the truth table). No [UM] found; no [DT] confirmation yet.

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 7–58 V and rated 25 A continuous / 60 A peak [DS][PP]. It has two input modes — PWM/DIR from a controller, or a 10 kΩ potentiometer plus SPDT direction switch with no controller — a 5 V output (250 mA max) for the host controller, test buttons, status LEDs with blink-coded errors, and overcurrent (active current limiting), temperature and undervoltage protection [DS].
- Product page feature line: "Bidirectional control for one brushed DC motor." and "Dual Input Mode: PWM/DIR or Potentiometer/Switch Input." [PP]

## Specifications
Datasheet section 2, **"Table 2: MD25HV Absolute Maximum Ratings"** (columns No / Parameters / Min / Max / Unit) [DS].

| Item | Value | Src |
|---|---|---|
| 1 Power input voltage | Min 7 V, Max 58 V | [DS] |
| 2 Maximum motor current (continuous) | Max 25 A | [DS] |
| 3 Maximum motor current (peak) | Max 60 A — peak duration **not stated** | [DS] |
| 4 5V output voltage | Min 4.9 V, Max 5.1 V | [DS] |
| 5 5V output maximum current | Max 250 mA | [DS] |
| 6 Potentiometer analog input voltage (POT 2) | Min 0 V, Max 5 V | [DS] |
| 7 Direction switch input voltage – low level (MA, MB) | Min 0 V, Max 0.8 V | [DS] |
| 8 Direction switch input voltage – high level (MA, MB) | Min 3 V, Max 5 V | [DS] |
| 9 Logic input voltage – low level (PWM, DIR) | Min 0 V, Max 0.8 V | [DS] |
| 10 Logic input voltage – high level (PWM, DIR) | Min **3 V**, Max **30 V** | [DS] |
| 11 PWM input frequency | DC to 40 kHz — footnote: "Lock-Antiphase PWM is not supported." | [DS] |
| 12 Motor driver output PWM frequency | 16 kHz — "(Output frequency is independent of input frequency)" | [DS] |
| Number of channels | 1 | [DS][PP] |
| Control modes | Input Mode 1: PWM/DIR (sign-magnitude); Input Mode 2: Potentiometer/Switch. **Locked-antiphase not supported** | [DS] |
| Mode selection | Not stated (no jumper or switch described) | — |
| RC / serial input | Not stated | — |
| Logic compatibility | "PWM/DIR Inputs compatible with 1.8V, 3.3V, 5V, 12V and 24V logic (Arduino, Raspberry Pi, PLC, etc)." — see *Conflicts* (1.8 V) | [PP] |
| Overcurrent protection | Active current limiting; OC LED on while limiting | [DS] |
| Temperature protection | Current-limit threshold falls as board temperature rises; overheat warning above 80 ℃ (176 ℉) | [DS] |
| Undervoltage shutdown | Yes — threshold value not stated | [DS] |
| Overvoltage | Error indication (ERR LED 3 blinks); shutdown behaviour not stated | [DS] |
| Reverse polarity protection | **None** — "Connecting in reverse polarity will damage the motor driver instantaneously." [DS]; "Power input does not have reverse-voltage protection." [PP] | [DS][PP] |
| Test buttons | MA (Forward*) and MB (Backward*); "Motor will run at 78% of full speed." | [DS] |
| LEDs | Power LED, Error LED (blink codes), OC LED, Motor Status LEDs MA / MB | [DS] |
| Dimensions | In "Figure 2: MD25HV Dimension" only — values not readable in the text | [DS] |
| Operating temperature | Not stated | — |
| Heatsink / fan | Not stated | — |
| Warranty | 12 months | [PP] |
| Packing list | 1 x MD25HV; 1 x Potentiometer with connector; 1 x Rocker switch with connector; 4 x Nylon PCB Standoffs/Spacers | [PP] |

## Interfaces, terminals and pin mapping
Datasheet "Table 1: MD25HV Board Functions" [DS]:

| Function | Pins / description |
|---|---|
| Power Input Terminal | "Connect to battery." VB+ : Positive; VB- : Negative. Reverse polarity damages the driver instantaneously |
| Motor Output Terminal | MA / MB — "Motor direction is depending on the polarity." |
| PWM/DIR Input | PWM: PWM input for motor speed control; DIR: direction input; **5VO**: 5 V output, "Can be used to power Arduino and other MCU"; GND: signal ground |
| Speed Control Potentiometer | For a 10 KΩ pot: POT 1 (GND) → pot pin 1 (lowest speed); POT 2 (Analog In) → pot middle pin; POT 3 (5V) → pot pin 3 (highest speed) |
| Direction Switch | For an SPDT switch; MA and MB internally pulled high. MA: short to GND to run forward*; COM: common pin, connected to GND internally; MB: short to GND to run backward* |
| Power LED | On when powered up |
| Error LED | Blinks when there is an error (codes below) |
| OC (Overcurrent) LED | On when current limiting is in action; threshold depends on board temperature |
| Motor Status LEDs | On when motor running — MA: Forward*, MB: Backward* |
| Test Buttons | "Motor will run at 78% of full speed." MA: Forward*, MB: Backward* |

\* Actual motor direction depends on the motor connection; swapping MA and MB reverses it [DS].

PWM/DIR truth table, "Table 3" [DS] (same on quick start card ):

| PWM | DIR | Output A (MA) | Output B (MB) | Motor |
|---|---|---|---|---|
| Low | X (Don't care) | Low | Low | Brake |
| High | Low | High | Low | Forward* |
| High | High | Low | High | Backward* |

Error LED blink codes, "Table 4" [DS]:

| ERR blinks | Meaning |
|---|---|
| 3 | Overvoltage Error — power input exceeded the maximum rating. With a switching power supply, connect a motor shunt regulator or rechargeable battery of the same voltage in parallel to absorb regenerative energy during deceleration |
| 4 | Overheat Error — board temperature over 80 ℃ (176 ℉); "This is just served as a warning. The motor driver can still be safely operated." |

- Physical pin order on headers/terminals is shown only in figures — not readable. Wire size not stated.

## Rules and gotchas (for code, wiring and tutorials)
- **Locked-antiphase PWM is not supported** — use sign-magnitude PWM/DIR only [DS]. (Unlike MDD10A/MD10C.)
- Output PWM is **fixed at 16 kHz**, independent of the input PWM frequency (input DC–40 kHz) [DS][PP].
- Logic HIGH on PWM/DIR must be **≥ 3 V** (max 30 V) [DS]. 3.3 V, 5 V, 12 V and 24 V logic are within the datasheet range; 1.8 V is below the 3 V minimum despite the product page claim [DS][PP].
- Direction switch inputs MA/MB are 0–5 V (high level 3–5 V), not 30 V-tolerant like PWM/DIR [DS].
- 5VO supplies at most 250 mA — enough to power an Arduino-class MCU, not servos or motors [DS].
- **Use a battery or add a shunt regulator.** With a switching supply, regenerative energy during deceleration can push the input over the maximum (ERR 3 blinks); connect a motor shunt regulator or a rechargeable battery of the same voltage in parallel [DS].
- **Check polarity before power-up** — no reverse-polarity protection [DS][PP].
- PWM LOW = brake (both outputs low) regardless of DIR [DS].
- Test buttons run the motor at 78% speed, not 100% [DS].
- Overheat (ERR 4 blinks, > 80 ℃) is a warning only; the current limit is already being reduced by temperature [DS].

## Power and electrical limits
- Supply 7–58 V on VB+/VB- ("Connect to battery") [DS].
- 25 A continuous, 60 A peak; peak duration not stated [DS].
- Overcurrent: "When the motor is trying to draw more current than what the motor driver can supply, the PWM to the motor will be chopped off and the motor current will be maintained at maximum current limit. This prevents the motor driver from damage when the motor stalls or an oversized motor is hooked up." [DS]
- Temperature: "The higher the board temperature, the lower the current limiting threshold." Figure 5 "Maximum Current Limit vs Temperature Graph" — values not readable [DS].
- Undervoltage: output shut down when the input drops below the lower limit, "to make sure the MOSFETs have sufficient voltage to fully turn on and do not overheat"; ERR LED on [DS].
- Overvoltage (e.g. regenerative energy from an SMPS-powered setup): flagged by ERR 3 blinks [DS].

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, version 1.0.1, architectures=*) — MD25HV is listed under the **PWM_DIR** example [GH].
  - `CytronMD motor(PWM_DIR, 3, 4);` example wiring D3 = PWM, D4 = DIR, GND = GND [GH]; `setSpeed(-255..255)`, positive = DIR LOW = Output A high (Forward*) [GH][DS].
- Potentiometer/Switch mode needs no code [DS].
- MicroPython / CircuitPython / ROS: not stated.

## Compatibility and accessories
- Controllers: "Arduino, Raspberry Pi, PLC, etc" [PP]; datasheet logic-high range 3–30 V [DS].
- Brushed DC motors only, one motor [DS][PP].
- Included potentiometer and rocker switch (with connectors) for Input Mode 2 [PP].
- Shunt regulator or rechargeable battery in parallel when using a switching supply [DS].

## Common mistakes / troubleshooting
- Board dead after first power-up → reversed battery; no reverse-voltage protection [DS][PP].
- ERR LED blinks 3 times when the motor slows or stops on an SMPS → regenerative overvoltage; add a shunt regulator or parallel battery [DS].
- ERR LED blinks 2 times → undervoltage or hardware failure [DS].
- OC LED on, motor weak → current limiting (stall, oversized motor, hot board) [DS].
- Locked-antiphase code (50% duty = stop) does not work → not supported [DS].
- Motor runs slower on test buttons → buttons run at 78% speed by design [DS].
- 1.8 V controller does not trigger the inputs → below the 3 V logic-high minimum [DS].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Lowest logic level supported | [DS]: logic input high level min 3 V | [PP]: "compatible with 1.8V, 3.3V, 5V, 12V and 24V logic" | [DS] wins: 3 V minimum; 1.8 V logic not supported by the datasheet. Flag for [DT] |
| ERR LED in undervoltage | [DS] §6: "ERR LED will turn on during undervoltage shutdown" | [DS] Table 4: undervoltage = ERR blinks 2 times (MOSFET Driver Error) | Same document; read as ERR LED blinking 2 times |
| PWM frequency | [DS]: input DC–40 kHz, output 16 kHz independent | [PP]: "up to 40kHz (Output frequency is fixed at 16kHz)" | Consistent |

## Needs verification
1. Dimensions — only in the datasheet drawing (Figure 2), not readable as text.
2. How the input mode is selected (PWM/DIR vs Potentiometer/Switch) — not stated; Figures 3/4 not readable.
3. Physical pin order of headers and terminals; terminal wire size.
4. Peak-current duration; undervoltage threshold; values on the current-limit-vs-temperature graph.
5. Whether overvoltage shuts the output down or only flags the error.
6. Operating temperature range; heatsink/fan requirement.
7. Hardware revisions after Rev 1.0 (Jan 2019) — none documented.
8. Single-unit price: [PP] shows only volume tiers ($56.05 at 5+, $53.10 at 10+, $50.15 at 30+); currency shown only as "$".

## Sources
- [DS] MD25HV Datasheet Rev 1.0, Jan 2019 (public Google Doc): https://docs.google.com/document/d/1xJHVG2dc3aEtedCHf3L9NzUy5KqpxeWjeS9Lfh9XuqA/edit
- [DS] same document, public PDF mirrors: https://cdn.robotshop.com/media/c/cyt/rb-cyt-271/pdf/cytron-25a-7-58v-single-brushed-dc-motor-driver-datasheet.pdf and https://download.kamami.pl/p578535-MD25HV%20Datasheet.pdf
- [PP] Product page "25Amp 7V-58V High Voltage DC Motor Driver": https://www.cytron.io/p-25amp-7v-58v-high-voltage-dc-motor-driver (read 16 Oct 2026)
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- [3P] RobotShop product page (cross-check only): https://www.robotshop.com/products/cytron-25a-7-58v-single-brushed-dc-motor-driver
