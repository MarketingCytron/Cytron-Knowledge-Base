# MD20A — Verified Reference

| | |
|---|---|
| Product code | `MD20A` (datasheet title [DS]; "Product Code MD20A" on product page [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. Page matches the datasheet and the earlier www.cytron.io read; price, stock and the reverse-voltage warning confirmed |
| Primary source | "MD20A 20Amp 6V-30V DC Motor Driver Datasheet" — **Rev 1.0, Feb 2019** (Cytron Technologies, 5 pages) — public PDF mirror: https://cdn.robotshop.com/media/c/cyt/rb-cyt-254/pdf/md20a_datasheet.pdf |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Cytron datasheet Rev 1.0, Feb 2019, read from the RobotShop CDN mirror (linked from the RobotShop product page, public) through a text-extracting fetch; figures (Figure 1 board functions photo, Figure 2 dimension drawing, Figure 3 input connection diagram, Figure 4 current-limit-vs-temperature graph) were **not readable**. No user manual was found. [PP] = www.cytron.io page "20Amp 6V-30V DC Motor Driver" (read 16 Oct 2026; the copy served also carried an old "Raya Holiday 11th–18th May" banner, so it may be cached; the my.cytron.io copy failed to load).  = Drive print file "PM-QS-MD20A (front).pdf" (quick start card artwork; text extraction garbled, cross-check only). No [DT] confirmation exists yet.

## What it is
A single-channel, bi-directional driver for one brushed DC motor, rated 20 A continuous and 60 A peak, powered from 6 V to 30 V [DS]. It is controlled by PWM and DIR inputs that accept logic-high from 1.5 V to 15 V [DS] ("compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)" [PP]). It has overcurrent protection with active current limiting, temperature-dependent current limit, undervoltage shutdown, test buttons, and Power, MA/MB, OC and Error LEDs [DS].

## Specifications
Datasheet section 2 "Specifications", **"Table 2: MD20A Absolute Maximum Ratings"** (columns No, Parameters, Min, Max, Unit) [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 6 V, Max 30 V | [DS] |
| Maximum motor current — continuous | Max 20 A | [DS] |
| Maximum motor current — peak | Max 60 A — "*¹ Peak current is limited by the overcurrent protection circuit. Actual current limit is depending on board temperature. Value shown is at room temperature (25 - 30 degree Celsius)." | [DS] |
| Peak current duration | Not stated (peak is set by the current-limit circuit, not a time limit) | [DS] |
| Logic input voltage (PWM & DIR) — low level | Min 0 V, Max 0.8 V | [DS] |
| Logic input voltage (PWM & DIR) — high level | Min 1.5 V, Max **15 V** | [DS] |
| PWM frequency — Standard | Min "DC", Max 20 KHz — "(Output frequency is same as input frequency)" | [DS] |
| PWM frequency — Extended | Min 20, Max 40 KHz — "*² When the PWM operates in extended frequency range, continuous motor current will be reduced." | [DS] |
| Number of channels | 1 — "Bidirectional control for one brushed DC motor." | [PP] |
| Logic compatibility (marketing wording) | "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." | [PP] |
| Control modes | PWM & DIR inputs [DS]; "Compatible with sign-magnitude and locked-antiphase PWM operation." [PP] (the datasheet does not mention locked-antiphase) | [DS][PP] |
| RC / analog / serial input | Not stated | — |
| Logic supply | No separate logic supply input; board functions are power input, motor output, LEDs, test buttons, PWM/DIR input only | [DS] |
| Overcurrent protection | "Overcurrent Protection with Active Current Limiting" — PWM is chopped and current held at the maximum limit; OC LED on | [DS] |
| Temperature protection | Current-limit threshold falls as board temperature rises (Figure 4, values not readable) | [DS] |
| Undervoltage | "Undervoltage Shutdown" — output shut down below "the lower limit" (threshold not stated); ERR LED on | [DS] |
| Reverse polarity protection | **None** — "Warning : Connecting in reverse polarity will damage the motor driver instantaneously." [DS]; "Power input does not have reverse-voltage protection." [PP] | [DS][PP] |
| Test buttons | MA, MB — "Motor will run at full speed." | [DS] |
| LEDs | Power, Motor Status (MA, MB), Error, OC (Overcurrent) | [DS] |
| H-bridge / heatsink / fan | Not stated in [DS] or [PP] | — |
| Dimensions | Shown only as a drawing (Figure 2) — values not readable; not stated in [PP] | — |
| Operating temperature | Not stated (only the 25 - 30 °C reference for peak current) | — |
| Warranty | 12 months | [PP] |
| Packing list | 1 x 20Amp 6V-30V DC Motor Driver; 4 x PCB Spacer | [PP] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read on my.cytron.io: discrete NMOS H-bridge, 20 A without heatsink; 6–30 V; 20 A continuous, 60 A peak; 1.8/3.3/5/12 V logic; PWM up to 20 kHz; sign-magnitude and locked-antiphase; overcurrent limiting, temperature protection, undervoltage shutdown; "Power input does not have reverse-voltage protection"; packing 1x MD20A, 4x PCB spacer; resources datasheet, sample code, CAD [PP]. Dimension image only.

## Interfaces, terminals and pin mapping
**"Table 1: MD20A Board Functions"** [DS]:

| Function | Description |
|---|---|
| Power Input Terminal | "Connect to battery." VB+ : Positive; VB- : Negative. "Warning : Connecting in reverse polarity will damage the motor driver instantaneously." |
| Motor Output Terminal | "Connect to motor terminal." "Motor direction is depending on the polarity." (outputs MA / MB) |
| Power LED | "Turn on when power up." |
| Motor Status LEDs | "Turn on when the motor is running." MA : Forward*; MB : Backward* |
| OC (Overcurrent) LED | "Turn on when current limiting is in action." "Current limit threshold is depending on the board temperature." |
| Test Buttons | "Press to test the functionality of the motor driver." "Motor will run at full speed." MA : Forward*; MB : Backward* |
| PWM/DIR Input | "Control the motor with PWM & DIR signal." DIR : Direction input; PWM : PWM input for motor speed control; GND : Signal ground |

\* "Actual motor direction is depending on the motor connection. Swapping the connection (MA & MB) will reverse the direction." [DS]

**"Table 3: PWM/DIR Input Truth Table"** [DS]:

| PWM | DIR | Output A (MA) | Output B (MB) | Motor |
|---|---|---|---|---|
| Low | X (Don't Care) | Low | Low | Brake |
| High | Low | High | Low | Forward* |
| High | High | Low | High | Backward* |

- Input connection is shown in "Figure 3: PWM & DIR Input Connection Diagram" (not readable) [DS].
- Physical order of DIR / PWM / GND on the input header and terminal type / wire size: not stated in text.
- Mode selection: by wiring; no jumper or switch is described [DS]. Locked-antiphase wiring is not described in [DS]; [PP] only says it is compatible.

## Rules and gotchas (for code, wiring and tutorials)
- **Check polarity before power-up** — reverse polarity "will damage the motor driver instantaneously" [DS]; no reverse-voltage protection [PP].
- Power input: "Connect to battery." [DS].
- Logic inputs accept 1.5–15 V high, 0–0.8 V low [DS] — unlike MD10C/MDD10A/MD13S (5.5 V max), 12 V PLC logic is within range. Do not exceed 15 V on PWM/DIR.
- PWM LOW = both outputs low = **Brake**, regardless of DIR [DS].
- 60 A is a peak set by the overcurrent circuit, at 25 - 30 °C; the limit falls as the board heats [DS]. Do not quote a "60 A for N seconds" figure — no duration is stated.
- Above 20 kHz (extended range up to 40 kHz) the continuous current is reduced [DS]; the reduced value is not stated.
- Connect controller GND to the input GND ("Signal ground") [DS].
- Test buttons run the motor at full speed — keep the mechanism clear before pressing [DS].
- Direction depends on motor wiring; swap MA/MB to reverse [DS].

## Power and electrical limits
- Supply 6–30 V [DS].
- Continuous 20 A; peak 60 A limited by the overcurrent protection circuit and dependent on board temperature [DS].
- Overcurrent: "When the motor is trying to draw more current than what the motor driver can supply, the PWM to the motor will be chopped off and the motor current will be maintained at maximum current limit. This prevents the motor driver from damage when the motor stalls or an oversized motor is hooked up. OC LED will turn on when current limiting is in action." [DS]
- Temperature: "The maximum current limiting threshold is determined by the board temperature. The higher the board temperature, the lower the current limiting threshold." [DS]
- Undervoltage: "The motor driver output will be shut down when the power input voltage drops below the lower limit. This is to make sure the MOSFETs have sufficient voltage to fully turn on and do not overheat. ERR LED will turn on during undervoltage shutdown." [DS] Threshold value not stated.
- Battery vs switching power supply / regenerative current: [DS] says only "Connect to battery." for the power input; no SMPS or regenerative-current warning is stated.

## Software support
- Arduino: **Cytron Motor Drivers Library** (version 1.0.1, architectures=*), Library Manager name "Cytron Motor Drivers Library". MD20A is listed under the **PWM_DIR** example [GH].
  - `CytronMD motor(PWM_DIR, 3, 4);  // PWM = Pin 3, DIR = Pin 4.` then `motor.setSpeed(-255..255)`; positive speed writes DIR LOW (= Forward*, MA high per truth table) [GH][DS].
  - Example wiring comment: Arduino D3 → PWM, D4 → DIR, GND → GND [GH].
- Other platforms (MicroPython, PLC ladder examples): not stated.

## Compatibility and accessories
- Controllers named by [PP]: "Arduino, Raspberry Pi, PLC, etc" (1.8 V, 3.3 V, 5 V and 12 V logic).
- One brushed DC motor [PP].
- Included: 4 x PCB Spacer [PP].
- Do not confuse with **MDD20A** (separate 2-channel product, documented elsewhere).

## Common mistakes / troubleshooting
- Board dead after first power-up → reversed battery polarity; damage is instantaneous [DS].
- OC LED on and motor weak → current limiting active (stall, oversized motor, or hot board lowering the limit) [DS].
- Motor runs weaker at high PWM frequency → above 20 kHz the continuous current is reduced [DS].
- Motor brakes instead of coasting at PWM LOW → by design (Brake) [DS].
- Quick check without code → press MA/MB test buttons; motor runs at full speed and MA/MB LED lights [DS].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| PWM frequency | [DS]: Standard DC–20 KHz; Extended 20–40 KHz (continuous current reduced) | [PP]: "PWM frequency up to 20kHz" | [DS] wins (up to 40 kHz in extended range, with derating); [PP] describes the standard range only |
| Logic levels | [DS]: high 1.5–15 V, low 0–0.8 V | [PP]: "compatible with 1.8V, 3.3V, 5V and 12V logic" | Consistent; [DS] numbers used in text |
| Locked-antiphase | [DS]: not mentioned | [PP]: "Compatible with sign-magnitude and locked-antiphase PWM operation." | No value conflict; locked-antiphase tagged [PP] |
| Peak current | [DS]: 60 A, limited by OC circuit, temperature dependent, at 25 - 30 °C | [PP]: "20A continuous, 60A peak" | Consistent; [DS] conditions kept |

## Needs verification
1. Dimensions and mounting holes — only in Figure 2 drawing, not readable; not on [PP].
2. Current-limit-vs-temperature values (Figure 4) and the continuous current in the extended 20–40 kHz range.
3. Undervoltage shutdown threshold ("the lower limit") — not stated.
4. Physical order of DIR/PWM/GND on the input header and terminal type/wire size; connection diagram (Figure 3).
5. Locked-antiphase wiring and behaviour (50% = stop?) — only [PP] claims support.
6. Battery vs SMPS / regenerative current guidance beyond "Connect to battery." — confirm with [DT].
7. Operating temperature range, H-bridge type, heatsink requirement — not stated.
9. Board revisions — only datasheet Rev 1.0 (Feb 2019) found; no newer datasheet or user manual located.

## Sources
- [DS] MD20A 20Amp 6V-30V DC Motor Driver Datasheet, Rev 1.0, Feb 2019 (Cytron), public PDF mirror: https://cdn.robotshop.com/media/c/cyt/rb-cyt-254/pdf/md20a_datasheet.pdf (linked from https://jp.robotshop.com/en/products/cytron-20a-6-30v-single-dc-motor-controller)
- [PP] Product page "20Amp 6V-30V DC Motor Driver": https://www.cytron.io/p-20amp-6v-30v-dc-motor-driver (read 16 Oct 2026; https://my.cytron.io/p-20amp-6v-30v-dc-motor-driver failed to load)
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- [3P] RobotShop listing (cross-check): https://www.robotshop.com/products/cytron-20a-6-30v-single-dc-motor-controller
