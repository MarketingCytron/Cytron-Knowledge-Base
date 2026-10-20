# MDD20A — Verified Reference

| | |
|---|---|
| Product code | `MDD20A` (datasheet title [DS]; quick start guide "PM-QS-MDD20A" ; GitHub library list [GH]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. Page matches the datasheet and the earlier www.cytron.io read; price, stock and the reverse-voltage warning confirmed |
| Primary source | "MDD20A 20Amp 6V-30V DC Motor Driver (2 Channels) Datasheet" — **Rev 1.0, July 2020** — public PDF mirror of the Cytron document: https://cdn.robotshop.com/media/c/cyt/rb-cyt-287/pdf/cytron-20a-6v-30v-dual-dc-motor-driver-datasheet.pdf |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: No Cytron Google Doc of the MDD20A datasheet was found (web or Drive). [DS] = the Cytron datasheet PDF mirrored on the RobotShop CDN (title page: "MDD20A / 20Amp 6V-30V DC Motor Driver / (2 Channels) / Datasheet / Rev 1.0 / July 2020"); the same document is mirrored at download.kamami.pl. Direct download was blocked here, so the PDF was read through a text-extracting fetch with targeted quote requests; figures (board layout, dimension drawing, connection diagram, current-limit graph) were **not** readable. [PP] = www.cytron.io product page (read 16 Oct 2026).  = Cytron quick start guide PDFs on Drive. No [UM] exists in any source found; no [DT] confirmation yet.

## What it is
A dual-channel, bi-directional driver for two brushed DC motors, powered from 6–30 V and rated 20 A continuous / 60 A peak per channel [DS][PP]. Each channel is controlled by a PWM and a DIR input; the board has test buttons, motor status LEDs, an OC (overcurrent) LED and an Error LED, plus overcurrent protection with active current limiting, temperature protection and undervoltage shutdown [DS].
- Product page feature line: "Bidirectional control for two brushed DC motors." [PP]
- Example applications listed: "Automated Guided Vehicle (AGV), Solar Tracker, Game Simulator, Mobile Robot, Automation Machine." [PP]

## Specifications
Datasheet section 2, **"Table 2: Absolute Maximum Ratings"** (columns No / Parameter / Min / Max / Unit; no Typical column) [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 6 V, Max 30 V | [DS] |
| Maximum motor current, continuous (per channel) | Max 20 A | [DS] |
| Maximum motor current, peak (per channel) | Max 60 A — footnote: "Peak current is limited by the overcurrent protection circuit." "Actual current limit is depending on board temperature." "Value shown is at room temperature (25 - 30 degree Celsius)." Peak **duration not stated** | [DS] |
| Logic input voltage (PWM & DIR), low level | Min 0 V, Max 0.8 V | [DS] |
| Logic input voltage (PWM & DIR), high level | Min 1.5 V, Max 15 V — footnote: "Maximum input voltage can be extended up to 30V by connecting a 10K ohm resistor in series." | [DS] |
| PWM frequency, standard | Up to 20 kHz (row printed "Standard DC … 20 KHz"; read as DC to 20 kHz) — "(Output frequency is same as input frequency)" | [DS] |
| PWM frequency, extended | Min 20 kHz, Max 40 kHz — footnote: "When the PWM operates in extended frequency range, continuous motor current will be reduced." (amount not stated) | [DS] |
| Number of channels | 2 (bi-directional, brushed DC) | [DS][PP] |
| Logic supply | No separate logic supply or 5 V output listed; PWM/DIR header is DIRx, PWMx, GND | [DS] |
| Logic compatibility | "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." | [PP] |
| Control modes | PWM/DIR (sign-magnitude) per the datasheet truth table [DS]; "Compatible with sign-magnitude and locked-antiphase PWM operation." [PP] — locked-antiphase is not mentioned in the datasheet | [DS][PP] |
| RC / analog / serial input | Not stated | — |
| Overcurrent protection | "Overcurrent Protection with Active Current Limiting" | [DS] |
| Temperature protection | Current-limit threshold falls as board temperature rises | [DS] |
| Undervoltage shutdown | Yes — threshold value not stated | [DS] |
| Reverse polarity protection | **None** — "Connecting in reverse polarity will damage the motor driver instantaneously." [DS]; "Power input does not have reverse-voltage protection." [PP] | [DS][PP] |
| Test buttons | Present — "Press to test the functionality of the motor driver." "Motor will run at full speed." (number not stated in text) | [DS] |
| LEDs | Power LED, Motor Status LEDs (MxA / MxB), Error LED, OC (Overcurrent) LED | [DS] |
| Dimensions | In "Figure 2: MDD20A Dimension" only — values not readable in the text | [DS] |
| Weight | 89 g | [PP] |
| Operating temperature | Not stated (only the 25–30 °C reference for the peak rating) | — |
| Heatsink / fan | Not stated | — |
| Warranty | 12 months | [PP] |
| Packing list | 1 x 20Amp 6V-30V DC Motor Driver (2 Channels); 4 x PCB Spacer | [PP] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read on my.cytron.io: discrete NMOS H-bridge, 20 A per channel without heatsink (Cytron thermal-camera tested rating); 6–30 V; 20 A continuous, 60 A peak; 1.8/3.3/5/12 V logic; PWM up to 20 kHz; sign-magnitude and locked-antiphase; overcurrent limiting, temperature protection, undervoltage shutdown; weight 89 g; "Power input does not have reverse-voltage protection"; packing 1x MDD20A, 4x PCB spacer; resources datasheet, sample code, CAD [PP].

## Interfaces, terminals and pin mapping
Datasheet "Table 1: Board Functions" [DS]:

| Function | Description |
|---|---|
| Power Input Terminal | "Connect to battery." VB+ : Positive; VB- : Negative. Warning: reverse polarity damages the driver instantaneously |
| Motor Output Terminal | "Connect to motor terminal." "Motor direction is depending on the polarity." (MxA / MxB) |
| Power LED | "Turn on when powered up." |
| Motor Status LEDs | "Turn on when the motor is running." MxA : Forward*, MxB : Backward* |
| Error LED | "Turn on during undervoltage shutdown or hardware fault." |
| OC (Overcurrent) LED | "Turn on when current limiting is in action." "Current limit threshold is depending on the board temperature." |
| Test Buttons | "Press to test the functionality of the motor driver." "Motor will run at full speed." |
| PWM/DIR Input | "Control the motor with PWM & DIR signal." DIRx: Direction input; PWMx: PWM input for motor speed control; GND: Signal ground |

\* Actual motor direction depends on the motor connection; swapping MxA and MxB reverses it [DS].

Truth table, "Table 3", each channel x [DS] (identical in quick start guide R1230223 ):

| PWMx | DIRx | Output A (MxA) | Output B (MxB) | Motor x |
|---|---|---|---|---|
| Low | X (Don't care) | Low | Low | Brake |
| High | Low | High | Low | Forward* |
| High | High | Low | High | Backward* |

- Physical order of the input header pins and of the terminal block is shown only in figures — not readable; see *Needs verification*.
- Wire size / terminal current rating: not stated.
- Mode selection: no jumper or switch is described; PWM/DIR is the only input interface in the datasheet [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Check polarity before power-up** — no reverse-polarity protection; reversed battery damages the driver "instantaneously" [DS][PP].
- Logic HIGH must be ≥ 1.5 V and ≤ 15 V; up to 30 V only with a 10 kΩ resistor in series [DS]. So 3.3 V, 5 V and 12 V logic work directly; 24 V PLC outputs need the series resistor [DS][PP].
- PWMx LOW = both outputs low = **brake**, regardless of DIRx [DS].
- Keep PWM at or below 20 kHz for the full 20 A continuous rating; 20–40 kHz is allowed but reduces continuous current [DS].
- Output PWM frequency equals the input PWM frequency [DS].
- 20 A continuous / 60 A peak are **per channel**; the 60 A figure is the room-temperature value, and the real limit is set by the overcurrent circuit and board temperature [DS].
- When the OC LED lights, the driver is chopping PWM to hold current at its limit — a stall or oversized motor [DS].
- Connect controller GND to the header GND (signal ground) [DS].
- Do not describe locked-antiphase as a datasheet feature — it is a product-page claim only [PP].

## Power and electrical limits
- Supply 6–30 V on VB+/VB- ("Connect to battery") [DS].
- 20 A continuous, 60 A peak per channel; peak duration not stated; peak "limited by the overcurrent protection circuit" [DS].
- Overcurrent: "When the motor is trying to draw more current than what the motor driver can supply, the PWM to the motor will be chopped off" and "the motor current will be maintained at maximum current limit." [DS]
- Temperature: "The maximum current limiting threshold is determined by the board temperature." "The higher the board temperature, the lower the current limiting threshold." Graph "Maximum Current Limit vs Temperature Graph (Per channel)" exists but values were not readable [DS].
- Undervoltage: "The motor driver output will be shut down when the power input voltage drops below the lower limit." Error LED on [DS].
- Switching power supply / regenerative current / shunt regulator: **not stated** in any MDD20A source read.
- Overvoltage protection: not stated.

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, version 1.0.1, architectures=*) — MDD20A is listed under the **PWM_DIR_DUAL** example [GH].
  - `CytronMD motor1(PWM_DIR, 3, 4); CytronMD motor2(PWM_DIR, 9, 10);` example wiring D3 = PWM 1, D4 = DIR 1, D9 = PWM 2, D10 = DIR 2, GND = GND [GH].
  - `setSpeed(-255..255)`; positive speed = DIR LOW = Output A high (Forward* per truth table) [GH][DS].
- MicroPython / CircuitPython / ROS: not stated.

## Compatibility and accessories
- Controllers: "Arduino, Raspberry Pi, PLC, etc" with 1.8 V, 3.3 V, 5 V and 12 V logic [PP]; datasheet logic-high minimum is 1.5 V [DS].
- Brushed DC motors only [DS][PP].
- Included: 4 x PCB spacer [PP].

## Common mistakes / troubleshooting
- Board dead after first power-up → battery connected in reverse; no reverse-voltage protection [DS][PP].
- Motor weaker than expected, OC LED on → current limiting active (stall, oversized motor, or hot board lowering the limit) [DS].
- Motor stops whenever PWM is low → PWM LOW brakes the channel [DS].
- Motor runs the wrong way → swap MxA/MxB or invert DIR [DS].
- Running out of current at high PWM frequency → above 20 kHz the continuous rating is reduced [DS].
- 24 V PLC signal into PWM/DIR → exceeds 15 V; add a 10 kΩ series resistor (up to 30 V) [DS].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Locked-antiphase PWM | [DS]: not mentioned; only PWM/DIR truth table | [PP]: "Compatible with sign-magnitude and locked-antiphase PWM operation." | Not a numeric conflict; state as [PP] claim only. Confirm with [DT] |
| PWM frequency range | [DS]: standard up to 20 kHz, extended 20–40 kHz with reduced continuous current | [PP]: "PWM frequency up to 20kHz" | No conflict; [PP] omits the extended range |
| Logic levels | [DS]: high 1.5–15 V (30 V with 10 kΩ series) | [PP]: 1.8 V, 3.3 V, 5 V and 12 V logic | Consistent |

## Needs verification
1. Dimensions — only in the datasheet drawing (Figure 2), not readable as text.
2. Physical pin order of the PWM/DIR header and the power/motor terminal block (figures only).
3. Number of test buttons — not stated in [DS] text; [3P] RobotShop says "four buttons for quick testing".
4. Whether the Error and OC LEDs are one per board or one per channel (the text names one of each).
5. Locked-antiphase support ([PP] only) and how it is wired.
6. Peak-current duration; undervoltage threshold; amount of current reduction above 20 kHz; values on the current-limit-vs-temperature graph.
7. Behaviour with switching power supplies / regenerative current (not covered by MDD20A sources; the MD25HV datasheet does cover it, but that is a different product).
8. Operating temperature range, heatsink/fan requirement, terminal wire size.
9. Hardware revisions after Rev 1.0 (July 2020) — none documented.

## Sources
- [DS] MDD20A Datasheet Rev 1.0, July 2020 (public Cytron PDF mirror): https://cdn.robotshop.com/media/c/cyt/rb-cyt-287/pdf/cytron-20a-6v-30v-dual-dc-motor-driver-datasheet.pdf
- [DS] same document, second public mirror: https://download.kamami.pl/p587223-MDD20A%20Datasheet.pdf
- [PP] Product page "20Amp 6V-30V DC Motor Driver (2 Channels)": https://www.cytron.io/p-20amp-6v-30v-dc-motor-driver-2-channels (read 16 Oct 2026)
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- [3P] RobotShop product page (cross-check only): https://www.robotshop.com/products/cytron-20a-6v-30v-dual-dc-motor-driver
