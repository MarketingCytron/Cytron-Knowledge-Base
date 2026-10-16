# 30Amp 5V-30V DC Motor Driver (MD30C) — Verified Reference

| | |
|---|---|
| Product code | `MD30C` (manual title [UM]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "MD30C 30A DC Motor Driver User's Manual" — **V1.4, December 2017** — public Google Doc: https://docs.google.com/document/d/178uDa3dmoG0ZX859rWUOS2Xyafkd8hSsSET5-ZLXMYQ/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A single-channel, bi-directional driver for one brushed DC motor, rated 30 A continuous and 80 A peak (1 second), powered from 5–30 V [UM]. It can be controlled by PWM + DIR from a microcontroller (sign-magnitude or locked-antiphase, up to 20 kHz) or run standalone from its onboard PWM generator using the onboard (or external) switches and speed potentiometer [UM]. Fully NMOS H-bridge; "no heatsink or fan is required"; reverse polarity protection [UM].
- Manual introduction: "MD30C is the successor of MD30B which is designed to drive medium to high power DC Brushed motor with current capacity up to 80A peak and 30A continuously." [UM]
- "MD30C also incorporates some user friendly features such as reverse polarity protection and onboard PWM generator which allows it to operate without a host controller." [UM]

## Specifications
Manual section 3.0 "Product Specification and Limitations", table **"Absolute Maximum Rating"** (Typical column blank for every row) [UM].

| Item | Value | Src |
|---|---|---|
| Power input voltage (motor supply voltage) | Min 5 V, Max 30 V. Feature list: "Motor Voltage: 5V - ~~25V~~ 30V." (25 V struck through) | [UM] |
| IMAX — maximum continuous motor current | Max 30 A | [UM] |
| IPEAK — peak motor current | Max 80 A — "Must not exceed 1 second." | [UM] |
| IIDLE — idle current | Max 100 mA | [UM] |
| VIOH — logic input high level | Min 3 V, Max **5.5 V** | [UM] |
| VIOL — logic input low level | Min 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | 20 KHz — "Actual output frequency is same as input frequency when external PWM is selected." | [UM] |
| Logic level input | "3.3V and 5V logic level input." (feature list) | [UM] |
| Number of channels | 1 — "Bi-directional control for 1 brushed DC motor." | [UM] |
| Logic supply | No separate logic supply input described; power via the power terminal block only | [UM] |
| Control modes | Sign-magnitude and locked-antiphase "for external PWM operation"; onboard PWM generator (internal or external potentiometer + switches) for standalone operation | [UM] |
| Mode selection | Jumpers JP4 and JP6 (see table below) | [UM] |
| RC / analog-voltage / serial input | PWM input "is not RC (Radio Control) PWM"; analog-voltage and serial control not stated (speed pot is a 10K Ohm potentiometer input, not a voltage input) | [UM] |
| Internal PWM generator frequency | Not stated | — |
| H-bridge | "Fully NMOS H-Bridge for better efficiency and no heatsink is required." Intro: "no heatsink or fan is required." | [UM] |
| Reverse polarity protection | **Yes** — "Reverse polarity protection." (feature list) | [UM] |
| Over-current / thermal / under-voltage protection | Not stated | — |
| Test buttons | 2 (Test Button A, Test Button B); external switches can be connected | [UM] |
| LEDs | Red LED A, Red LED B, Green Power LED | [UM] |
| Dimensions | Not stated in text — section 5.0 "Dimension" is a figure only (not readable here) | [UM] |
| Operating temperature | Not stated | — |
| Warranty | "Product warranty is valid for 6 months." Manufacturing defects only; misuse and two-way freight not covered | [UM] |
| Packing list | 1 x MD30C 30A DC Motor Driver; 2 x Mini Jumper; 1 x 2510 PCB Connector - 3 Ways (Female); 3 x 2510 Terminal Pin | [UM] |
| Certificates | CE, FCC and RoHS certificates are linked on the product page (not opened) | [PP] |

## Interfaces, terminals and pin mapping
Board layout items as numbered in the manual [UM]:
1. **Power Terminal Block** — connect to power source. "For high current application, please solder the wire directly to the pad at bottom layer."
2. **Input** (3-pin, 2510): pin 1 GND (Ground); pin 2 PWM ("PWM input for speed control" — "this is not RC (Radio Control) PWM"); pin 3 DIR (Direction Input).
3. **PWM Source Selector** (JP4, JP6).
4. **Internal PWM Potentiometer** — speed control when PWM source is the internal potentiometer.
5. **External PWM Potentiometer Port** (JP5) — connect a **10K Ohm** potentiometer.
6. **Test Button A** — current flows A to B, motor turns CW (or CCW depending on connection); an external switch can be connected.
7. **Test Button B** — current flows B to A, motor turns CCW (or CW); an external switch can be connected.
8. **Motor Terminal Block** — connect to motor; solder to bottom-layer pad for high current.
9. **Red LED A** — on when output B low and output A high (current A to B).
10. **Red LED B** — on when output A low and output B high (current B to A).
11. **Green Power LED** — on when powered.

External switches connect to **JP7 and JP8**; external potentiometer to **JP5** (may be soldered directly; keep pads clean of flux and solder balls) [UM].

PWM source selector [UM]:

| PWM source | JP4 | JP6 |
|---|---|---|
| Internal potentiometer | INT POT | INT PWM |
| External potentiometer | EXT POT | INT PWM |
| External PWM signal (microcontroller) | X (Don't Care) | EXT PWM |

Truth table (JP6 = EXT PWM) [UM]:

| PWM | DIR | Output A | Output B | Motor state |
|---|---|---|---|---|
| Low | X (Don't Care) | Low | Low | Brake |
| High | Low | High | Low | CW |
| High | High | Low | High | CCW |

- Wire size / terminal current rating: not stated; for > 20 A the manual recommends soldering wires directly to the bottom-layer pads [UM].
- Locked-antiphase is listed as supported for external PWM, but the MD30C manual does not describe how to wire it [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Battery recommended.** "We recommend to use battery as power source to MD30C." [UM]
- **SMPS needs a battery in parallel.** "If Switching Power Supply is being used as power source for MD30C, we recommend parallel it with same voltage battery. This is to absorb the re-gen power from motor. DC brushed motor will become generator when it is slow down and rotate by external force." [UM]
- **Battery on the motor port burns the MOSFETs.** "Connecting battery to the motor port will burn the MOSFETs on MD30C and this is not covered under warranty." [UM]
- **Power-up state:** "Please do note that to set either DIR or PWM pin at LOW condition first when power is on." [UM] (The Cytron library constructor drives both pins LOW [GH].)
- Logic inputs: 3.3 V or 5 V; VIOH max **5.5 V** [UM]. Not for 12 V/24 V logic.
- PWM LOW = brake (both outputs low) regardless of DIR [UM].
- For microcontroller control, JP6 **must** be EXT PWM; JP4 is then don't care [UM].
- With JP4 = EXT POT, the onboard potentiometer has no effect [UM].
- Not for RC-receiver PWM [UM].
- 80 A peak only for ≤ 1 second; 30 A continuous [UM].
- > 20 A: solder wires to the bottom-layer pads rather than using the terminal block [UM].
- Direction (CW/CCW) depends on motor wiring [UM].

## Power and electrical limits
- Motor supply 5–30 V (earlier feature text showed 25 V, struck through to 30 V) [UM].
- 30 A continuous; 80 A peak, must not exceed 1 second [UM]. No temperature condition or derating curve stated.
- Idle current up to 100 mA [UM].
- Reverse polarity protection: yes [UM]. Over-current, thermal, short-circuit and under-voltage behaviour: not stated.
- No heatsink or fan required (manual) [UM]; operating temperature not stated.
- Starting/stall current: not addressed beyond the 80 A / 1 s peak rating [UM].

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, version 1.0.1, architectures=*), Library Manager name "Cytron Motor Drivers Library"; MD30C is listed under the **PWM_DIR** example [GH] — https://github.com/CytronTechnologies/CytronMotorDriver
  - `CytronMD motor(PWM_DIR, 3, 4);` (example: PWM = D3, DIR = D4, GND to GND); `setSpeed(-255..255)`; positive speed = DIR LOW [GH].
- Getting-started example with SK40C (PIC) in manual section 6.3 [UM].
- MicroPython / CircuitPython / ROS: not stated.

## Compatibility and accessories
- Any controller with 3.3 V or 5 V logic PWM + DIR outputs [UM]; SK40C example [UM]; Arduino via Cytron library [GH].
- Standalone (no controller) with onboard or external 10K Ohm potentiometer and external switches [UM].
- Brushed DC motors only [UM].
- Included: 2 mini jumpers; 3-way 2510 female connector + 3 terminal pins [UM].
- Predecessor: MD30B [UM].

## Common mistakes / troubleshooting
- Motor does not turn when a test button is pressed in standalone mode → speed may be too low; "Try turning the on board potentiometer CW (clock wise) for a few round while pressing down one of the switch" [UM].
- Microcontroller PWM has no effect → JP6 still on INT PWM; set JP6 = EXT PWM [UM].
- Onboard pot has no effect → JP4 set to EXT POT [UM].
- MOSFETs burnt after wiring → battery connected to motor port (not covered by warranty) [UM].
- Supply problems when the motor slows or is back-driven → SMPS cannot absorb regenerative power; parallel a same-voltage battery [UM].
- Terminal heating at high current → for > 20 A solder directly to bottom-layer pads [UM].
- Motor jumps at power-up → set PWM or DIR LOW first at power-on [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Max motor voltage | [UM] spec table: 30 V | [UM] feature list: "5V - ~~25V~~ 30V" | Same document; 25 V struck through, 30 V current. Use 30 V |
| Product name voltage | [PP] name "30Amp 5V-30V" | [UM] 5–30 V | Agree |
| No other conflicts found | — | — | Product page facts read were stock, prices and links only |

## Needs verification
1. Board dimensions and mounting holes — section 5.0 is a figure only; not readable as text.
2. Internal PWM generator frequency — not stated (MD10-POT's 9–11 kHz must not be assumed).
3. How to wire locked-antiphase on MD30C — supported per feature list, wiring not described.
4. Over-current, thermal, under-voltage protection — not stated; confirm with [DT] none exists.
5. Terminal block wire size and current rating — not stated.
6. Operating temperature range — not stated.
7. What changed in hardware Revision 2.0 (January 2016) vs earlier — not documented (only voltage 25 V → 30 V implied).
8. Warranty: manual V1.4 says 6 months; current Cytron warranty policy may differ — confirm.
9. Single-unit price: [PP] shows only quantity-tier prices (from RM148.76 at 20+).

## Sources
- [UM] MD30C User's Manual (Google Doc, "MD30C 30A DC Motor Driver User's Manual, V1.4, December 2017"): https://docs.google.com/document/d/178uDa3dmoG0ZX859rWUOS2Xyafkd8hSsSET5-ZLXMYQ/view
- PDF mirrors of the same manual (cross-check only): https://www.farnell.com/datasheets/4726005.pdf ; https://cdn.robotshop.com/media/c/cyt/rb-cyt-133/pdf/md30c-1.4-users-manual.pdf
- [PP] Product page "30Amp 5V-30V DC Motor Driver": https://my.cytron.io/p-30amp-5v-30v-dc-motor-driver (read by coordinator 2026-10-16)
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
