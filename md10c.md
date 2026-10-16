# MD10C — Verified Reference

| | |
|---|---|
| Product code | `MD10C` ("Product Code: MD10C" on the product page [PP]; manual title [UM]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "MD10C R3.0 10Amp DC Motor Driver User's Manual Rev3.0" — **V1.0, Aug 2018** — public Google Doc (live version read 16 Oct 2026): https://docs.google.com/document/d/1rgQzn-nWn-qcWNnHjDZvIYqUrdCeBQQxXA-TU3BF0AQ/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: No document titled "datasheet" was found for MD10C; the Cytron **User's Manual** is the top source ([UM]). [UM] = the live Google Doc above. [UM-PDF] = a PDF copy of the same manual (same title, "Rev3.0 / V1.0 / Aug 2018") mirrored on robu.in — it differs from the live Google Doc on the logic-input rating (see *Conflicts*). [UM-R2] = older "MD10C 10A DC Motor Driver User's Manual Rev2.0 V2.1, July 2015" mirrored on manualzilla.com (read through a summarising fetch; only quoted lines used). [PP] = www.cytron.io / my.cytron.io product page "10Amp 5V-30V DC Motor Driver" (both read 16 Oct 2026, same content). PDF mirrors were read through a summarising web fetch, not as raw files. No [DT] confirmation exists yet.

## What it is
A single-channel, bi-directional driver for one brushed DC motor, rated 13 A continuous and 30 A peak (10 seconds), powered from a single 5–30 V motor supply with no separate logic supply ("No additional Vin is required") [UM]. Speed and direction are set by PWM and DIR inputs (sign-magnitude or locked-antiphase PWM, up to 20 kHz); it is not for RC-receiver PWM [UM]. It uses a full NMOS H-bridge ("no heat sink is required") and solid-state switching, replacing the relay-based MD10B (launched 2008) [UM]. Onboard test buttons and direction LEDs [UM].
- Manual introduction: "MD10C is another version of the MD10B(Launched in 2008, uses mechanical relays) which is designed to drive high current brushed DC motor up to 13A continuously. It offers several enhancements over the MD10B such as support for both locked-antiphase and sign-magnitude PWM signal as well as using full solid state components which result in faster response time and eliminate the wear and tear of the mechanical relay." [UM]
- Naming trap: the product title says **"10Amp"** but the rated continuous current is **13 A** [UM][PP].

## Specifications
Manual table is titled **"Absolute Maximum Rating"** [UM].

| Item | Value | Src |
|---|---|---|
| Power input voltage (Vmotor) | Min 5 V, Max 30 V ("Positive Supply (5V to 30VDC)") | [UM] |
| IMAX — maximum continuous motor current | Max 13 A — "Tested under 25℃ (room temperature) environment, without airflow and heatsink." | [UM] |
| IPEAK — peak motor current | Max 30 A — "Must not exceed 10 seconds." | [UM] |
| VIOH — logic input high level | Min 3 V, Max **30 V** (live Google Doc). PDF copy of same manual version: Min 3 V, Max **5.5 V** — see *Conflicts* | [UM] / [UM-PDF] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | 20 kHz — "Actual output frequency is same as input frequency." | [UM] |
| Number of channels | 1 ("Bi-directional control for one DC Brushed motor, single channel") | [UM] |
| Motor type | DC brushed motor (two terminals) | [UM][PP] |
| Logic supply | None separate — "powered from a single power source, the Vmotor only. No additional Vin is required." | [UM] |
| Logic level input (feature list) | "3.3V, 5V, 12V and 24V logic level input, which support signal from Arduino, Raspberry Pi, PLC and any controller that can produces PWM or logic signal from 3.3V to 30V" (live Google Doc) | [UM] |
| Control modes | Sign-Magnitude PWM and Locked-Antiphase PWM; "Support TTL PWM from microcontroller, not PWM from RC receiver" | [UM] |
| RC servo signal / analog / serial input | RC: No [PP]; analog and serial: not stated | [PP] |
| H-bridge | Full NMOS H-Bridge, "no heat sink is required" | [UM] |
| Regenerative braking | "Regenerative Braking." (feature bullet) | [PP] |
| Reverse polarity protection | **None** — "MD10C does not come with Reverse Polarity Protection." | [UM][PP] |
| Over-current / thermal / under-voltage protection | Not stated | — |
| Isolation | Not isolated; controller and motor "share the common GND" (Cytron Q&A reply, 03/07/2020) | [PP] |
| Cooling fan | No | [PP] |
| Dimensions | 75 mm x 43 mm | [UM][PP] |
| Operating temperature | Not stated (only the 25 ℃ test condition for IMAX) | — |
| Certifications | "this product comply with CE, FCC and RoHS" (Cytron Q&A reply, 18/04/2018); UL94 flammability rating not confirmed by Cytron | [PP] |
| PCB material | "standard FR4 material" (Cytron Q&A reply, 20/04/2018) | [PP] |
| Warranty | 12 months; manufacturing defects only; misuse and two-way freight not covered | [UM][PP] |
| Packing list | 1 x MD10C R3.0 10A DC Motor Driver; 1 x 2510 PCB Connector – 3 Ways (Female); 3 x 2510 Terminal Pin; 4 x plastic spacer (~7mm) | [UM][PP] |

## Interfaces, terminals and pin mapping
Board layout letters as in the manual [UM]:
- **A. Terminal block (GREEN) — power:** Pin 1 `V motor Power +` (Positive Supply, 5V to 30VDC); Pin 2 `V motor Power -` (Negative Supply or Ground terminal).
- **B. Terminal block (Black) — motor:** Pin 3 `Motor Output A`; Pin 4 `Motor Output B` ("Connect to DC brushed motor, or load").
- **C. Red LED A:** on when Output A high and Output B low (current flows A to B).
- **D. Red LED B:** on when Output A low and Output B high (current flows B to A).
- **E. Test Button A:** current flows A to B; motor turns CW (or CCW depending on connection).
- **F. Test Button B:** current flows B to A; motor turns CCW (or CW depending on connection).
- **G. Control input header (3 pins, 2510):** Pin 1 `GND` (logic ground); Pin 2 `PWM` (speed, up to 20 kHz, "not for RC PWM operation"); Pin 3 `DIR` (direction).
- **H. Green LED:** power LED.
- Wire size / terminal current rating: not stated.

Truth table [UM]:

| Pin 2 (PWM) | Pin 3 (DIR) | Output A | Output B | Operation |
|---|---|---|---|---|
| Low | X (Don't care) | Low | Low | Brake Low |
| High | Low | High | Low | Forward |
| High | High | Low | High | "Reserve" (printed; means reverse) |

Mode selection — by wiring, no jumper or switch is stated [UM]:
- **Sign-magnitude:** PWM signal to PWM pin (speed), logic level to DIR pin (direction).
- **Locked-antiphase:** PWM pin tied to logic high; PWM signal fed to DIR pin. 50% duty = stop; < 50% = CW (or CCW depending on connection); > 50% = CCW (or CW).

## Rules and gotchas (for code, wiring and tutorials)
- Single supply only: connect the motor supply to the green terminal; there is no Vin/logic supply pin [UM].
- Check polarity before power-up — no reverse polarity protection [UM][PP].
- Always connect controller GND to MD10C GND (pin 1); the board is not isolated and shares a common GND [UM][PP].
- PWM pin LOW = "Brake Low" (both outputs low), regardless of DIR [UM]. Setting PWM to 0 brakes; it does not float the outputs.
- Direction labels (Forward/CW) depend on how the motor is wired; swapping Output A/B reverses it [UM].
- Do not feed RC-receiver (servo) PWM — use TTL PWM from a microcontroller [UM][PP].
- PWM frequency up to 20 kHz; output frequency equals input frequency [UM].
- Logic voltage in tutorials: use 3.3 V or 5 V logic — this is stated by every source [UM][UM-PDF][PP]. Only the live Google Doc rates inputs to 30 V; do not tell readers to drive it from 12 V/24 V logic until *Needs verification* item 1 is resolved.
- Peak 30 A is for ≤ 10 s only; the 13 A continuous figure was measured at 25 ℃ with no airflow and no heatsink [UM].
- In text, write "Reverse" for the DIR-high row; the manual's "Reserve" is a typo.

## Power and electrical limits
- Vmotor 5–30 V DC [UM]. The manual's examples power it from a battery ("power source example battery"; Getting Started uses "12V from a SLA battery") [UM].
- Continuous 13 A, peak 30 A ≤ 10 s [UM]. Motor rated/stall current above these is outside the rating [UM].
- Battery vs switching power supply / regenerative current: **not stated in MD10C sources**. The product page lists "Regenerative Braking" [PP]. See *Needs verification*.
- Over-current, thermal, short-circuit and under-voltage behaviour: not stated in any source.
- No heatsink required per manual (NMOS H-bridge) [UM]; no derating curve or operating temperature range is given.

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, library.properties version 1.0.1, architectures=*), installable via Library Manager ("Cytron Motor Drivers Library") [GH]. MD10C is listed under the **PWM_DIR** example [GH].
  - `#include "CytronMotorDriver.h"`; `CytronMD motor(PWM_DIR, 3, 4);  // PWM = Pin 3, DIR = Pin 4.`; `motor.setSpeed(-255..255)` [GH].
  - `setSpeed(>=0)` writes PWM to pin1 and DIR LOW; negative writes DIR HIGH [GH] — so positive speed = Output A high (manual's "Forward") [UM][GH].
  - Example wiring: Arduino D3 → PWM, D4 → DIR, GND → GND [GH].
- PIC: sample code for PIC16F877A on SK40C — https://github.com/CytronTechnologies/SK40C-MD10C [UM].
- Cytron tutorials referenced by the manual: "Controlling MD10C with Arduino" (explains sign-magnitude and locked-antiphase), "Controlling 10A DC Motor Driver Using Arduino Nano", "Driving DC Brush Motor with MD10C + SK40C", "Driving Two DC Geared Motors with MD10C by Using SKPS + SK40C", "Measuring DC Motor RPM Through Built-in Hall Sensor Encoder", and "MD10C fast testing" (no controller; shows Rev1.0, test buttons serve the same purpose) [UM].
- MicroPython / CircuitPython / MicroBlocks / ROS: not stated.

## Compatibility and accessories
- Controllers: Arduino and Raspberry Pi (3.3 V logic) [UM][PP]; PIC16F877A on SK40C (programmed with UIC00A/B) [UM]; PLC listed in the live manual's feature bullet [UM] (see *Conflicts*).
- Not an Arduino shield — "can be used with Wire connection" [PP].
- Brushed DC motors only (two-terminal) [UM][PP].
- Included: 3-way 2510 female connector + 3 terminal pins for the control header; 4 plastic spacers [UM].
- Product page notes the MD13S as an SMD version with similar specs at a lower price [PP] (separate product; not an alias).

## Common mistakes / troubleshooting
- Board dead or damaged after power-up → reversed supply polarity; there is no reverse polarity protection [UM][PP].
- Motor runs at full speed or not at all from an RC receiver → RC PWM is not supported [UM].
- Motor does not move with DIR toggling only → PWM pin is LOW (Brake Low); in sign-magnitude mode PWM must carry the speed signal [UM].
- Motor does not stop in locked-antiphase → PWM pin must be tied HIGH and DIR fed at 50% duty to stop [UM].
- Erratic behaviour / no response → missing common GND between controller and driver (board is not isolated) [PP].
- Motor spins the "wrong" way → swap Motor Output A/B or invert DIR in code [UM].
- Quick hardware check without code → press Test Button A/B; Red LED A/B should light [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Logic input high max (VIOH) | Live Google Doc [UM]: 3–**30 V** | PDF copy of the same manual "Rev3.0 V1.0 Aug 2018" [UM-PDF]: 3–**5.5 V** | Live Google Doc (current Cytron document) is the main value; the version label was not changed, so the edit date is unknown. Tutorials should use 3.3 V/5 V logic (agreed by all sources). Flag for [DT] |
| Logic level feature | Live Google Doc [UM]: "3.3V, 5V, 12V and 24V logic level input … 3.3V to 30V" | [UM-PDF] and [PP]: "3.3V and 5V logic level input"; Getting Started in both copies: "can accept 3.3V to 5.0V logic, in some case, user use it with 24V logic from PLC" | [UM] live text wins in the spec table; conflict kept visible; [DT] to confirm |
| Revision vs voltage | Rev3.0 manual: "Rev 3.0 can support motor voltage range from 5V to 30V"; [UM-R2] (Rev2.0 V2.1, July 2015): "Support motor voltage ranges from 5V to 25V" | [PP] spec table: "5 to 25 (Rev 1.0) 5 to 30 (Rev 2.0)" | [UM] wins: current Rev 3.0 = 5–30 V. The product page's revision numbering does not match the manuals |
| Title current vs rating | Product title "10Amp 5V-30V DC Motor Driver" [PP]; manual title "10Amp DC Motor Driver" [UM] | IMAX 13 A continuous [UM][PP] | 13 A continuous is the rating; "10Amp" is the product name |

## Needs verification
1. **Logic input maximum** — is VIOH 30 V (live Google Doc) valid for every Rev 3.0 board shipped, or only later production? The PDF copy with the same version label says 5.5 V. Ask [DT] before writing any 12 V/24 V/PLC wiring.
2. **Battery vs SMPS** — MD10C sources say nothing about switching power supplies or regenerative current. Confirm with [DT] whether the same "use a battery / parallel battery" advice printed in the MDD10A manual applies to MD10C.
3. Over-current, thermal and under-voltage protection — not stated anywhere; confirm none exists.
4. Operating temperature range and terminal wire size/current — not stated.
5. Rev 1.0 / Rev 2.0 hardware differences beyond voltage (e.g. terminal block layout) — [UM-R2] was only read through a summarising fetch; its terminal layout description was not quoted and is not used.
6. ESP32 use of the Cytron library: the code calls `ledcWrite(_pin1, …)` with no `ledcAttach` in the constructor [GH]; whether ESP32 users must attach LEDC themselves is not documented.
7. UL94 flammability rating — Cytron reply: "for now we're not sure about that" [PP].
8. Product-page price currency is shown only as "$" on www.cytron.io.

## Sources
- [UM] MD10C Rev3.0 User's Manual (Google Doc, "MD10C R3.0 10Amp DC Motor Driver User's Manual Rev3.0, V1.0, Aug 2018"): https://docs.google.com/document/d/1rgQzn-nWn-qcWNnHjDZvIYqUrdCeBQQxXA-TU3BF0AQ/view
- [UM-PDF] PDF copy of the same manual (robu.in mirror): https://stgaws.robu.in/wp-content/uploads/2014/12/MD10C-Rev3.0-Users-Manual.pdf
- [UM-R2] MD10C 10A DC Motor Driver User's Manual Rev2.0 V2.1, July 2015 (manualzilla mirror): https://manualzilla.com/doc/5716161/user-manual
- [PP] Product page "10Amp 5V-30V DC Motor Driver": https://www.cytron.io/p-10amp-5v-30v-dc-motor-driver and https://my.cytron.io/p-10amp-5v-30v-dc-motor-driver
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver (README, library.properties, CytronMotorDriver.cpp/.h, examples/PWM_DIR/PWM_DIR.ino via raw.githubusercontent.com)
- [GH] SK40C + MD10C PIC sample: https://github.com/CytronTechnologies/SK40C-MD10C
- Tutorial: https://tutorial.cytron.io/2013/07/29/controlling-md10c-with-arduino/
