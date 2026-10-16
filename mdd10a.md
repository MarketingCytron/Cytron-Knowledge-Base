# MDD10A — Verified Reference

| | |
|---|---|
| Product code | `MDD10A` (manual title [UM]; packing list "1 x MDD10A Rev2.0" and page tag [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "MDD10A Dual Channel 10A DC Motor Driver User's Manual" — **V2.0, June 2017** — public Google Doc: https://docs.google.com/document/d/1ol8nICCTTw5dAHHE_hju08cCVH2GN5_Y3cGC6B4Gbas/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: No document titled "datasheet" was found for MDD10A; the Cytron **User's Manual** is the top source ([UM], read in full from the Google Doc). A PDF mirror of the same manual (makermotor.com, "V2.0, June 2017") was read through a summarising fetch and matches. [PP] = www.cytron.io product page "10Amp 5V-30V DC Motor Driver (2 Channels)" (read 16 Oct 2026; the my.cytron.io copy failed to load). No [DT] confirmation exists yet.

## What it is
A dual-channel, bi-directional driver for two brushed DC motors, rated 10 A continuous and 30 A peak (10 seconds) for each channel, powered from 5–30 V (Rev 2.0) [UM]. Each channel is controlled by PWM and DIR inputs (sign-magnitude or locked-antiphase PWM, up to 20 kHz); it is not for RC-receiver PWM [UM]. Full NMOS H-bridge ("no heat sink is required"), solid-state switching, onboard test buttons and direction LEDs [UM]. The manual describes it as "the dual-channel version of MD10C" [UM].
- Manual introduction: "MDD10A is the dual-channel version of MD10C, which is designed to drive 2 brushed DC motors with high current up to 10A continuously. Just like MD10C, the MDD10A also supports locked-antiphase and sign-magnitude PWM signal. It is also using full solid state components, which result in faster response time and eliminate the wear and tear of the mechanical relay." [UM]
- Manual also lists "Onboard push button to control the motor manually." [UM]

## Specifications
Manual section "Product Specification and Limitations", table **"Absolute Maximum Rating"** [UM].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 5 V, Max 30 V — "Rev2.0 has upgraded to support 30V maximum power input voltage" | [UM] |
| IMAX — maximum continuous motor current | Max 10 A — "Tested in room temperature at 25°C"; feature list: "10A continuous … for each channel" | [UM] |
| IPEAK — peak motor current | Max 30 A — "Must not exceed 10 seconds." (per channel) | [UM] |
| VIOH — logic input high level | Min 3 V, Max **5.5 V** | [UM] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | 20 kHz — "Actual output frequency is the same as input frequency" | [UM] |
| Number of channels | 2 (Motor 1, Motor 2) | [UM] |
| Motor type | Brushed DC motors | [UM] |
| Logic supply | No separate logic supply pin in the board layout; power is POWER+/POWER- only | [UM] |
| Logic level input | "Support 3.3V and 5V logic level input (for PWM and DIR), compatible with Arduino and Raspberry Pi." | [PP] |
| Control modes | Sign-Magnitude PWM and Locked-Antiphase PWM; "Support TTL PWM from the microcontroller, NOT PWM from the RC receiver" | [UM] |
| RC servo signal / analog / serial input | RC: No [PP]; analog and serial: not stated | [PP] |
| H-bridge | "A fully NMOS H-Bridge for better efficiency, and no heat sink is required" | [UM] |
| Regenerative braking | "Regenerative Braking." (feature bullet) | [PP] |
| Reverse polarity protection | **None** — "No Reverse Polarity Protection at Vmotor, please double check the polarity before power up." (manual does not mention it) | [PP] |
| Over-current / thermal / under-voltage protection | Not stated | — |
| Isolation | Not stated | — |
| Cooling fan | No | [PP] |
| Test buttons | 4 (M1A, M1B, M2A, M2B); [PP]: "2 activation buttons for manual activation or fast test on each channel" | [UM][PP] |
| Dimensions | 84.5 mm x 62 mm | [UM][PP] |
| Operating temperature | Not stated (only the 25°C test condition) | — |
| Warranty | 12 months; manufacturing defects only; misuse and two-way freight not covered | [UM][PP] |
| Packing list | 1 x MDD10A Dual Channel 10A DC Motor Driver; 1 x 2510 PCB Connector – 5 Ways (Female); 5 x 2510 Terminal Pin | [UM] ([PP]: "1 x MDD10A Rev2.0") |

## Interfaces, terminals and pin mapping
**Input header (5 pins, 2510)** [UM]:

| Pin | Name | Description |
|---|---|---|
| 1 | GND | Ground |
| 2 | PWM2 | PWM input for speed control (Motor 2) — not for RC PWM |
| 3 | DIR2 | Direction input (Motor 2) |
| 4 | PWM1 | PWM input for speed control (Motor 1) — not for RC PWM |
| 5 | DIR1 | Direction input (Motor 1) |

**Terminal block (6 pins) — motor and power** [UM]:

| Pin | Name | Description |
|---|---|---|
| 1 | Motor 1 Output B | Motor 1 terminal B |
| 2 | Motor 1 Output A | Motor 1 terminal A |
| 3 | POWER + | Positive supply (positive terminal of battery) |
| 4 | POWER - | Negative supply (negative terminal of battery) |
| 5 | Motor 2 Output A | Motor 2 terminal A |
| 6 | Motor 2 Output B | Motor 2 terminal B |

Note the order: Motor 1 is wired **B then A** (pins 1–2); Motor 2 is **A then B** (pins 5–6) [UM].

Truth table, same for Motor 1 and Motor 2 [UM]:

| PWM | DIR | Output A | Output B |
|---|---|---|---|
| Low | X (Don't care) | Low | Low |
| High | Low | High | Low |
| High | High | Low | High |

LEDs and buttons [UM]:
- Red LED M1A / M2A: on when MxA high and MxB low (current A to B). Red LED M1B / M2B: on when MxA low and MxB high (current B to A).
- Green LED: power LED.
- Test Button M1A / M2A: current A to B, motor turns CW (or CCW depending on connection). Test Button M1B / M2B: current B to A, motor turns CCW (or CW).
- Wire size / terminal rating: not stated.

Mode selection — by wiring, no jumper or switch is stated [UM]:
- **Sign-magnitude:** PWM to PWMx (speed), logic level to DIRx (direction).
- **Locked-antiphase:** PWMx tied to logic high; PWM signal to DIRx. 50% duty = stop; < 50% = CW (or CCW depending on connection); > 50% = CCW (or CW).

## Rules and gotchas (for code, wiring and tutorials)
- **Use a battery.** "Please use the battery when driving an inductive load, such as the DC brush motor. Due to the protection circuit of most power supplies (switching), it will shut down when regenerative current from the motor is detected." If a switching supply is needed, "a battery with the same rated voltage needs to be parallel with the power supply to absorb the regenerative current." [UM]
- Logic inputs: 3.3 V or 5 V only — VIOH max **5.5 V** [UM]. Do not drive from 12 V/24 V logic.
- Check polarity before power-up — no reverse polarity protection [PP].
- Connect controller GND to header pin 1 (GND) [UM].
- PWMx LOW = both outputs low (brake), regardless of DIRx [UM].
- Not for RC-receiver PWM [UM][PP].
- 10 A continuous / 30 A peak (≤ 10 s) is **per channel** [UM]; continuous rating tested at 25°C [UM].
- Header order is PWM2/DIR2 before PWM1/DIR1 (pins 2–5) — easy to swap channels by mistake [UM].
- Direction labels depend on motor wiring; swap MxA/MxB to reverse [UM].

## Power and electrical limits
- Supply 5–30 V on Rev 2.0 (boards shipped after Jan 2017); earlier boards: 25 V max ("5V to ~~25V~~ 30V (Rev2.0)") [UM].
- Continuous 10 A per channel, peak 30 A per channel for ≤ 10 s [UM].
- Switching power supplies may shut down on regenerative current — battery, or battery in parallel with the SMPS [UM].
- Over-current, thermal, short-circuit and under-voltage behaviour: not stated in any source.
- No heatsink required per manual [UM]; no derating curve or operating temperature range given.

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, version 1.0.1, architectures=*), Library Manager name "Cytron Motor Drivers Library" [GH]. MDD10A is listed under the **PWM_DIR_DUAL** example [GH].
  - `CytronMD motor1(PWM_DIR, pwmPin, dirPin);` one object per channel; `setSpeed(-255..255)`; positive speed = DIR LOW = Output A high [GH][UM].
- Tutorial: "Using MDD10A with Arduino UNO" (example sketch at the end of the tutorial) [UM] — https://tutorial.cytron.io/2015/04/05/using-mdd10a-with-arduino-uno/
- Getting started with SK40C (PIC) is a section of the manual [UM].
- MicroPython / CircuitPython / MicroBlocks / ROS: not stated.

## Compatibility and accessories
- Controllers: Arduino and Raspberry Pi (3.3 V and 5 V logic) [PP]; SK40C [UM].
- Not an Arduino shield — "can be used with wire connection" [PP].
- Brushed DC motors only [UM].
- Included: 5-way 2510 female connector + 5 terminal pins for the input header [UM].

## Common mistakes / troubleshooting
- Supply cuts out when motors brake or reverse → switching power supply tripping on regenerative current; use a battery or a battery in parallel [UM].
- Board damaged at power-up → reversed polarity; no reverse polarity protection [PP].
- Driving inputs from PLC/12 V logic → exceeds VIOH 5.5 V [UM].
- Wrong motor responds → PWM1/DIR1 are header pins 4–5, PWM2/DIR2 are pins 2–3 [UM].
- No response from an RC receiver → RC PWM not supported [UM].
- Quick check without code → press test buttons M1A/M1B/M2A/M2B; matching red LED should light [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Voltage by revision | [UM]: Rev2.0 (shipped after Jan 2017) 5–30 V; earlier 25 V max | [PP] spec table: "5 to 25 (Rev 1.0) 5 to 30 (Rev 2.0)" | Agree (Rev 1.0 = 25 V implied by [UM] strike-through); no conflict in values |
| Test button count wording | [UM]: four buttons M1A, M1B, M2A, M2B | [PP]: "2 activation buttons … on each channel" | Same (2 per channel = 4) |
| Reverse polarity | [UM]: not mentioned | [PP]: "No Reverse Polarity Protection at Vmotor" | No conflict; [PP] fills the gap |

## Needs verification
1. Over-current, thermal and under-voltage protection — not stated; confirm with [DT] that none exists.
2. Isolation between logic and motor GND — not stated for MDD10A.
3. Operating temperature range and terminal wire size/current — not stated.
4. Rev 1.0 vs Rev 2.0 differences other than max voltage — none documented.
5. ESP32 use of the Cytron library: `ledcWrite(_pin1, …)` with no `ledcAttach` in the constructor [GH]; behaviour on ESP32 not documented.
6. Single-unit price: [PP] shows only volume tiers; currency shown only as "$".

## Sources
- [UM] MDD10A User's Manual (Google Doc, "MDD10A Dual Channel 10A DC Motor Driver User's Manual, V2.0, June 2017"): https://docs.google.com/document/d/1ol8nICCTTw5dAHHE_hju08cCVH2GN5_Y3cGC6B4Gbas/edit
- PDF mirror of the same manual (cross-check): https://makermotor.com/content/cytron/pn00218-cyt4/MDD10A%20User's%20Manual.pdf
- [PP] Product page "10Amp 5V-30V DC Motor Driver (2 Channels)": https://www.cytron.io/p-10amp-5v-30v-dc-motor-driver-2-channels (my.cytron.io copy https://my.cytron.io/p-10amp-5v-30v-dc-motor-driver-2-channels failed to load)
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- Tutorial: https://tutorial.cytron.io/2015/04/05/using-mdd10a-with-arduino-uno/
