# 1.2Amp 7V-30V DC Motor Driver Shield for Arduino (2 Channels) — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-3AMOTOR` (manual: "Cytron 3A Motor Driver Shield (Code: SHIELD-3AMOTOR)" [UM]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "Cytron 3A Motor Driver Shield SHIELD-3AMOTOR User's Manual" — **Rev 1.0, April 2017** — public Google Doc: https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: No document titled "datasheet" exists; the Cytron **User's Manual** (linked from the product page) is the top source and was read in full as text via Google Drive. Figures (dimension drawing, board photos, DIP-switch photos, trace-cut photos) did not come through as text. [PP] = coordinator's read of the my.cytron.io page on 2026-10-16. No [DT] confirmation exists yet.

## What it is
An Arduino shield that drives two brushed DC motors bi-directionally, using the **DRV8871** IC, from a 7–30 V motor supply, rated **1.2 A continuous and 3 A peak (≤ 1 second) per channel**, with current-limit protection [UM]. A DIP switch selects sign-magnitude or locked-antiphase mode; the motor control pins are fixed to Arduino D4–D7 by default [UM].
- Manual introduction: "Cytron 3A Motor Driver Shield (Code: SHIELD-3AMOTOR) is an Arduino shield for controlling dual DC motor up to 3A for each channel. This product is an improvement from our previous Cytron 2A Motor Driver Shield. … SHIELD-3AMOTOR uses DRV8871 SMD IC and support for both signed magnitude and locked anti-phase. Compare to previous shield, SHIELD-3AMOTOR can handle higher current up to 3A together with limit current protection." [UM]
- The "3A" in the code and manual title is the **peak** rating; the product-page title's "1.2Amp" is the continuous rating [UM][PP].

## Specifications
Manual section 3 "Product Specifications", table **"Absolute Maximum Rating of SHIELD-3AMOTOR"** [UM], plus feature list and board layout.

| Item | Value | Src |
|---|---|---|
| Input voltage (motor supply voltage) | Min **7 V**, Max **30 V** — "For Input Voltage more than 12V, please refer to section 5. Power Supply" | [UM] |
| IMAX — max continuous motor current | Max **1.2 A** — "*Depends on the room temperature." (feature list: "each channel") | [UM] |
| IPEAK — peak motor current | Max **3 A** — "**Must not exceed 1 second." (each channel) | [UM] |
| VIOH — logic input HIGH level | Min **1.5 V**, Max **5 V** | [UM] |
| VIOL — logic input LOW level | Min 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | Not stated | — |
| Number of channels | 2 (Motor 1, Motor 2) | [UM] |
| Motor type | Brushed DC motors | [UM] |
| Driver IC | DRV8871 | [UM] |
| Logic level input | "Support 3.3V and 5V logic level input." | [UM] |
| Control modes | Sign-magnitude and locked-antiphase, selected by DIP switch | [UM] |
| RC / analog / serial input | Not stated | — |
| Current limit protection | **Yes** — "Current limit protection." | [UM] |
| Reverse polarity protection | **None** — "**NO POLARITY PROTECTION FOR V MOTOR.**" | [UM] |
| Thermal / under-voltage protection | Not stated | — |
| Test buttons | Motor 1 and Motor 2 test buttons (A and B each) — "Quick test switch for both channel." | [UM] |
| LEDs | Power LED; Motor 1 and Motor 2 direction LEDs | [UM] |
| Reset button | Yes — "Press this button will restart the system." | [UM] |
| Headers | Stackable Arduino header pins | [UM] |
| Extra connector | LSS05 (Auto-Calibrating Line Sensor) connector | [UM] |
| Dimensions | Drawing only ("Dimension (unit in mm)", figure not readable) — not stated in text | [UM] |
| Operating temperature | Not stated | — |
| Warranty | 12 months; manufacturing defect only; misuse and two-way freight not covered; **cutting any trace voids warranty** | [UM] |
| Packing list | 1 x Cytron 3A Motor Driver (Code: SHIELD-3AMOTOR) | [UM] |

## Interfaces, terminals and pin mapping
Board layout labels [UM]: A LSS05 connector; B Motor 2 terminal block; C Motor 1 terminal block; D power supply terminal block ("Connect to battery power source … NO POLARITY PROTECTION"); E Motor 2 LED indicator; F Motor 1 LED indicator; G power LED; H reset button; I Arduino stackable header pin; J mode selection DIP switch; K Motor 2 test button; L Motor 1 test button; M motor connection pads; N DIP switch setting example (silkscreen); O LSS05 connection pads; P PWRIN–VIN connection pad.

**Motor control pins → Arduino pins (default)** [UM, section 6.1]:

| Shield pin | Sign-Magnitude | Locked Anti-Phase |
|---|---|---|
| DIR1 | D4 | D5 |
| EN1 | D5 | D4 |
| EN2 | D6 | D7 |
| DIR2 | D7 | D6 |

Mode selection — **DIP switch, mini switches numbered 1–8** (manual: "moving the 4 mini switches on DIP switch mode") [UM]: Sign-Magnitude = switches **5, 6, 7, 8 ON**; Locked Anti-Phase = switches **1, 2, 3, 4 ON**. "Please set either Sign Magnitude or Locked Anti-Phase at a time. Mix up the setting will cause to unexpected result."

Practical reading of the table (derived from [UM]): in both modes the PWM signal lands on D5 (motor 1) and D6 (motor 2); in sign-magnitude D5/D6 are EN (speed) and D4/D7 DIR; in locked-antiphase D5/D6 drive DIR and D4/D7 drive EN.

Changing pins: "For ADVANCED user … cut the connection … at the back of the board, solder a jumper and connect to any IO." — **cutting voids warranty** [UM]. Pins are not jumper-selectable without cutting.

**LSS05 line-sensor pins (default)** [UM, section 6.2]: O1 = D13, O2 = D12, O3 = D11, O4 = D10, O5 = D9, Calibrate = D8. Changeable only by cutting traces (voids warranty).

LEDs and test buttons [UM]: LED M1A/M2A on = current from output MxA to MxB, and vice versa. Test button A → current MxA to MxB, and vice versa. (The manual's LED descriptions say "motor LEFT" for both motors — a typo.)

Terminals: Motor 1, Motor 2 and power supply screw terminal blocks [UM]. Wire size / rating not stated.

## Rules and gotchas (for code, wiring and tutorials)
- **Not a 3 A continuous driver.** 1.2 A continuous (depends on room temperature); 3 A peak only, ≤ 1 second [UM].
- **No reverse polarity protection** on the motor supply — "PLEASE DOUBLE CHECK THE CONNECTION BEFORE CONNECTING TO POWER SOURCE." [UM]
- **Above 12 V:** the PWRIN–Vin connection pad must be cut and the Arduino powered from a separate source — "Arduino Uno recommendation input voltage is 12V (max)". Cutting the trace **voids the warranty** [UM].
- By default PWRIN (shield power terminal) and Arduino Vin are connected (pad P) [UM]; so at ≤ 12 V the two supplies are joined.
- Set only one DIP-switch group (1–4 or 5–8) at a time [UM].
- Pins D4–D7 (and D8–D13 if the LSS05 connector is used) are taken by the shield [UM].
- Logic HIGH ≥ 1.5 V, max 5 V [UM].
- The manual says "Connect to battery power source" and "supports battery" [UM]; SMPS / regenerative-current guidance not stated.

## Power and electrical limits
- Motor supply 7–30 V; above 12 V requires cutting PWRIN–Vin [UM].
- 1.2 A continuous / 3 A peak (≤ 1 s) per channel [UM].
- Current limit protection fitted (DRV8871) [UM]; thermal and under-voltage behaviour not stated.
- Heatsink/fan: not stated.

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, Library Manager name "Cytron Motor Drivers Library", v1.0.1) — SHIELD-3AMOTOR is listed under the **PWM_DIR_DUAL** example [GH]. The example's pins (3, 4, 9, 10) do **not** match the shield; for sign-magnitude mode use `CytronMD motor1(PWM_DIR, 5, 4); CytronMD motor2(PWM_DIR, 6, 7);` (PWM = EN pin, DIR pin, from the [UM] table).
- The library has PWM_DIR (sign-magnitude) mode; a locked-antiphase example is not listed [GH].
- MicroPython / CircuitPython: not stated.

## Compatibility and accessories
- Arduino Uno, Leonardo, Mega, Due, Zero, 101 "and possibly other pin compatible main boards like CIKU, CT UNO and CT ARM" [UM]. Hardware-connection photos show Uno, Mega, CIKU and CT UNO [UM].
- LSS05 Auto-Calibrating Line Sensor plugs straight in [UM]; line-following robot example shown [UM].
- Other shields stack on top [UM].
- Predecessor: Cytron 2A Motor Driver Shield (SHIELD-2AMOTOR) [UM] — pin mapping for motor control is the same, LSS05 pins differ (see that file).

## Common mistakes / troubleshooting
- Motor weak or driver cuts out under load → check start/stall current against 1.2 A continuous / 3 A peak for ≤ 1 s; the shield has current limit protection [UM] (exact behaviour not stated).
- Board dead after power-up → reversed supply; no polarity protection [UM].
- Arduino damaged at > 12 V → PWRIN–Vin pad not cut [UM].
- Motors behave oddly → both DIP-switch groups ON, or library pins not 5/4 and 6/7 [UM][GH].
- Library sketch does nothing → used example pins 3/4/9/10 [GH].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Current rating in name | Code/manual title "3A" [UM] | [PP] title "1.2Amp" | Both true: 3 A peak (≤ 1 s), 1.2 A continuous [UM] |
| Introduction wording | [UM] intro: "up to 3A for each channel" | [UM] table: IMAX 1.2 A, IPEAK 3 A | Table wins; 3 A is peak only |
| LED description | [UM] E and F both say "motor LEFT" | — | Typo in manual |

## Needs verification
1. Maximum PWM frequency — not stated.
2. Current-limit threshold and behaviour (latch or auto-retry), thermal shutdown — not stated.
3. Dimensions and operating temperature — figure only / not stated.
4. Whether the shield feeds Arduino Vin when powered at ≤ 12 V (pad P joins PWRIN and Vin; the manual does not state it in those words).
5. Battery vs SMPS guidance — manual says battery only.
6. Terminal wire size.

## Sources
- [UM] Cytron 3A Motor Driver Shield SHIELD-3AMOTOR User's Manual, Rev 1.0, April 2017 (Google Doc "SHIELD-3AMOTOR User's Manual"): https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view
- [PP] Product page (read by coordinator 2026-10-16): https://my.cytron.io/p-1.2amp-7v-30v-dc-motor-driver-shield-for-arduino-2-channels
- [GH] Cytron Motor Drivers Library (README, PWM_DIR_DUAL example): https://github.com/CytronTechnologies/CytronMotorDriver
