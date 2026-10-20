# 0.8Amp 5V-26V DC Motor Driver Shield for Arduino (2 Channels) — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-2AMOTOR` (manual: "SHIELD-2AMOTOR Cytron 2A Motor Driver Shield" [UM]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 4): live my.cytron.io product page read (description, features, packing list, resources). Page independently confirms the manual (L298P, 0.8 A / 2 A, pins 4–7, sign-magnitude or locked anti-phase by jumper) and states the power-source jumper and the VIN vs external voltage ranges |
| Primary source | "SHIELD-2AMOTOR Cytron 2A Motor Driver Shield User's Manual" — **V1.1, Feb 2015** — public Google Doc: https://docs.google.com/document/d/1EiQAE_9VpDDm4rjZrySAoGjQldJnTk6rJIsUkqCT37w/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: No document titled "datasheet" exists; the Cytron **User's Manual** (linked from the product page) is the top source and was read in full as text via Google Drive. Figures (dimension drawing, board photo, jumper photos) did not come through as text. The 3D CAD file linked from the product page was not read. [PP] = coordinator's read of the my.cytron.io page on 2026-10-16. No [DT] confirmation exists yet.

## What it is
An Arduino shield that drives two brushed DC motors bi-directionally, using the **L298P** IC, from a 5–26 V motor supply, rated **0.8 A continuous and 2 A peak** per channel [UM]. Mini jumpers select sign-magnitude or locked-antiphase mode and the motor power source (external PWRIN or Arduino VIN) [UM].
- Manual introduction: "SHIELD-2AMOTOR is an Arduino shield for controlling dual DC motor up to 2A (peak) for each channel. It is compatible with Arduino Uno, Arduino Leonardo, Arduino Mega, Arduino Due and possibly other pin compatible main boards. SHIELD-2AMOTOR uses L298P SMD IC and support for both signed magnitude and locked anti-phase. SHIELD-2AMOTOR shield has stackable side headers which allows for more Arduino shields to be stacked on top of it." [UM]
- The "2A" in the code is the **peak** rating; the product-page title's "0.8Amp" is the continuous rating [UM][PP].
- Its successor is the Cytron 3A Motor Driver Shield (SHIELD-3AMOTOR), which the 3A manual calls "an improvement from our previous Cytron 2A Motor Driver Shield" [UM of SHIELD-3AMOTOR].

## Specifications
Manual section 3 "Product Specification and Limitations", table **"Absolute Maximum Rating"** [UM], plus feature list and board layout.

| Item | Value | Src |
|---|---|---|
| Power input voltage (motor supply voltage) | Min **5 V**, Max **26 V** | [UM] |
| IMAX — maximum continuous motor current | Max **0.8 A** | [UM] |
| IPEAK — peak motor current | Max **2 A** — table footnote "*Must not exceed 10 seconds" (the asterisk is not shown on a row; it sits under the table) | [UM] |
| VIOH — logic input high level | Min 3.3 V, Max **5.5 V** | [UM] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | **10 kHz** | [UM] |
| Number of channels | 2 (MOTOR1, MOTOR2) | [UM] |
| Motor type | Brushed DC motors | [UM] |
| Driver IC | L298P | [UM] |
| Logic level input | "3.3V and 5V logic level input." | [UM] |
| Control modes | Signed Magnitude (default) and Locked Anti-Phase, selected by moving 4 mini jumpers | [UM] |
| RC / analog / serial input | Not stated | — |
| Reverse polarity protection | **External power (PWRIN) only** — "External power (PWRIN) reverse polarity protection circuit … will protect the shield from broken." Feature list: "External voltage polarity protector." | [UM] |
| Over-current / thermal / under-voltage protection | Not stated | — |
| Power source selection | External (PWRIN) or internal (VIN, the Arduino power source) | [UM] |
| Test buttons | "Test switch for both channel." (button A and button B) | [UM] |
| LEDs | PWR LED — "Motor power indicator." Motor direction LEDs: not stated | [UM] |
| Reset button | Yes — "User can press this button to restart Arduino program." | [UM] |
| Headers | Stackable I/O header pins | [UM] |
| Extra connector | LSS05 connector | [UM] |
| Dimensions | Drawing only (figure not readable) — not stated in text | [UM] |
| Operating temperature | Not stated | — |
| Warranty | 12 months; manufacturing defect only; misuse and two-way freight not covered | [UM] |
| Packing list | 1 x SHIELD-2AMOTOR; 5 x mini jumper | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** L298P; two 5–26 V brushed DC motors at 0.8 A continuous per channel; stacks on UNO, Duemilanove, Leonardo, Mega and CIKU (PIC18F4550); motor-power polarity protection; test buttons per channel; LSS05 socket; PWM on pins 5 and 6, enable on pins 4 and 7 (sign-magnitude); locked anti-phase configurable by jumpers and program; **the shield can be powered from the Arduino or an external source (jumper selects); external supply strongly encouraged** [PP].
- **Spec list:** logic 5 V from the Arduino; polarity protection on the external motor input; 2 test buttons and 2 LEDs per channel; motor voltage **6.5–12 VDC from VIN**, **5.0–26 VDC from an external source**; 0.8 A continuous (2 A peak) per channel; pins 4, 5, 6, 7 used [PP].
- No packing-list tab on the page [PP].
- **Resources:** User's Manual (Google Doc), CytronMotorDriver library, tutorials (serial control, LM35 temperature-controlled motor, CIKU + LSS05 line follower, Arduino Edubot, sign-magnitude vs locked anti-phase, stepper motor with this shield), 3D CAD, Fritzing [PP].

## Interfaces, terminals and pin mapping
Board layout labels [UM]: A reset button for Arduino main board; B motor connectors; C external power (PWRIN) connector; D PWR LED; E power source selection; F external power (PWRIN) reverse polarity protection circuit; G L298P driver motor IC; H motor control mode selection; I test switch; J LSS05 connector; K Arduino pinout.

**Motor control pins → Arduino pins** (section 6.1, set by 4 mini jumpers) [UM]:

| Shield pin | Signed Magnitude | Locked Anti-Phase |
|---|---|---|
| DIR 1 | D4 | D5 |
| EN 1 | D5 | D4 |
| EN 2 | D6 | D7 |
| DIR 2 | D7 | D6 |

Default setting is **Signed Magnitude** [UM]. Pins are jumper-selectable only between these two mappings; no other pins are offered in the manual.

Practical reading (derived from [UM]): the PWM signal goes on D5 (motor 1) and D6 (motor 2) in both modes.

**LSS05 line-sensor pins** (section 6.2) [UM]: 5V–5V, GND–GND, A1–O1, A2–O2, A3–O3, A4–O4, A5–O5, D8–Cal. (Differs from SHIELD-3AMOTOR, which uses D13–D9.)

Test switch [UM]: button A → current A to B, motor CW (or CCW depending on connection); button B → current B to A, CCW (or CW).

Terminals [UM]: MOTOR1 and MOTOR2 terminal blocks; PWRIN terminal for external power. Wire size not stated.

## Rules and gotchas (for code, wiring and tutorials)
- **Not a 2 A continuous driver.** 0.8 A continuous; 2 A peak (≤ 10 s per the footnote) [UM].
- Select the power source: "Make sure correct power source is selected (VIN or PWRIN). VIN will connect to the Arduino power source, while PWRIN needs external power source connected to the PWRIN terminal." [UM]
- Reverse polarity protection covers the **PWRIN** input only [UM].
- Move all 4 mode jumpers together (default Signed Magnitude) [UM].
- Pins D4–D7 are used by the shield; A1–A5 and D8 if the LSS05 connector is used [UM].
- Max PWM 10 kHz [UM].
- Battery vs SMPS / regenerative current: not stated.

## Power and electrical limits
- Motor supply 5–26 V [UM].
- 0.8 A continuous / 2 A peak per channel [UM].
- Over-current, thermal, under-voltage: not stated. Heatsink/fan: not stated.
- Whether the shield powers the Arduino from PWRIN: not stated.

## Software support
- Manual: "Arduino library and example code can be downloaded from the SHIELD-2AMOTOR product page at Cytron's website." [UM]
- Current library: **Cytron Motor Drivers Library** (`CytronMotorDriver`, Library Manager name "Cytron Motor Drivers Library", v1.0.1) — SHIELD-2AMOTOR is listed under the **PWM_DIR_DUAL** example [GH]. Example pins (3, 4, 9, 10) do **not** match the shield; in Signed Magnitude mode use `CytronMD motor1(PWM_DIR, 5, 4); CytronMD motor2(PWM_DIR, 6, 7);` (PWM = EN pin, DIR pin, from the [UM] table).
- MicroPython / CircuitPython: not stated.

## Compatibility and accessories
- Arduino Uno, Leonardo, Mega, Due "and possibly other pin compatible main boards" [UM].
- LSS05 Auto-Calibrating Line Sensor plugs straight in [UM].
- Other shields stack on top [UM].
- Included: 5 mini jumpers [UM].

## Common mistakes / troubleshooting
- Motors do not move → power source jumper on PWRIN with nothing on the PWRIN terminal, or on VIN with no Arduino supply [UM].
- Motors behave oddly → mode jumpers mixed, or library pins not 5/4 and 6/7 [UM][GH].
- Motor struggles under load → check start/stall current against 0.8 A continuous / 2 A peak [UM].
- Quick check without code → press test switch A/B [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Current rating | Code/manual title "2A"; feature list "Maximum current up to 2A per channel" [UM] | [UM] table IMAX 0.8 A, IPEAK 2 A; [PP] title "0.8Amp" | Table wins: 0.8 A continuous, 2 A peak |
| Peak duration | [UM] footnote "*Must not exceed 10 seconds" | No asterisk on any table row | Taken as applying to IPEAK; flagged in *Needs verification* |
| Polarity protection | Feature list "External voltage polarity protector" [UM] | Board layout: protection on PWRIN only [UM] | Same claim; protection is on PWRIN |

## Needs verification
1. That the 10 s footnote applies to IPEAK (asterisk missing in the table).
2. Whether PWRIN also feeds Arduino Vin.
3. Over-current / thermal protection, dimensions, operating temperature, wire size.
4. Whether the product currently shipping matches manual V1.1 (Feb 2015); no newer revision found.
5. Which of the 5 mini jumpers selects the power source (page: Arduino VIN or external, "jumper to select"; manual uses 4 for mode).

## Sources
- [UM] SHIELD-2AMOTOR Cytron 2A Motor Driver Shield User's Manual, V1.1, Feb 2015 (Google Doc "SHIELD-2AMOTOR User's_Manual"): https://docs.google.com/document/d/1EiQAE_9VpDDm4rjZrySAoGjQldJnTk6rJIsUkqCT37w/view
- [UM of successor] SHIELD-3AMOTOR User's Manual Rev 1.0 (April 2017): https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view
- [PP] Product page (read by coordinator 2026-10-16): https://my.cytron.io/p-0.8amp-5v-26v-dc-motor-driver-shield-for-arduino-2-channels
- 3D CAD (linked from product page, not read): https://drive.google.com/file/d/1hUJLOzfb7xKmHvsU8E0-wktE0yNElOcW/view
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
