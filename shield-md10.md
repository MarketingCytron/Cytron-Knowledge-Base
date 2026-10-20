# 10Amp 7V-30V DC Motor Driver Shield for Arduino — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-MD10` (manual title [UM]; product-page image paths [PP]); Rev 2.0 boards are labelled "SHIELD-MD10 R2" [UM] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 4): live my.cytron.io product page read (description, features, packing list, resources). Page lists 7–25 V for Rev1.0 and 7–30 V for Rev2.0, 10 A / 15 A (10 s), regenerative braking, 10 kHz and the packing list; the Rev2.0 25 V absolute-maximum table is still unexplained, so it stays Medium |
| Primary source | No datasheet exists. Top source: "SHIELD-MD10 Cytron 10A Motor Driver Shield User's Manual" — **V1.0, June 2015** (the Rev2.0 manual; Drive title "SHIELD-MD10 User's_Manual REV 2") — https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = Rev2.0 manual (V1.0, June 2015), read in full from the Google Doc; a PDF mirror (stgaws.robu.in, "V1.0", "JUNE 2015") matches. [UM-R1] = Rev1.0 manual, "V1.1, September 2014" (Drive title "SHIELD-MD10 User's_Manual"): https://docs.google.com/document/d/1acVuzZKuqC_79RzD5BRT9IQ7ug63zG0wpf-bUgQ7QHY/view. Note the version numbers: the *newer* Rev2.0 manual is numbered V1.0. Figures (board layout, dimension, wiring) are images and were not readable. No newer document on Drive. [PP] = my.cytron.io page read by the coordinator 2026-10-16 (name, code, stock only).

## What it is
A single-channel Arduino shield that drives one brushed DC motor at up to 10 A continuous, using PWM (speed) and DIR (direction) inputs on jumper-selectable Arduino pins [UM]. Fully NMOS H-bridge, "no heat sink is required", with test buttons, output LEDs and stackable headers [UM]. Rev 2.0 is the current revision ("there will be only Shield MD10 Rev 2.0") [UM].

## Specifications
Rev2.0 manual, section 3.0 "Product Specification and Limitations", table **"Absolute Maximum Rating"**, plus feature list [UM].

| Item | Value | Src |
|---|---|---|
| Power input voltage (motor supply) | Feature list: "New!! Support motor voltage ranges from 7V to 30V." — **the same manual's Absolute Maximum Rating table still says Min 7 V, Max 25 V** (see *Conflicts*) | [UM] |
| IMAX — maximum continuous motor current | Max 10 A | [UM] |
| IPEAK — peak motor current | Max 15 A — "Must not exceed 10 seconds" | [UM] |
| VIOH — logic input high level | Min 3 V, Max 5.5 V | [UM] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | 10 kHz | [UM] |
| Logic level | "3.3V and 5V logic level input." | [UM] |
| Number of channels | 1 ("Bi-directional control for 1 brushed DC motor") | [UM] |
| Control mode | PWM pin (speed) + DIR pin (direction). Locked-antiphase, RC, analog, serial: not stated | [UM] |
| H-bridge | "Fully NMOS H-Bridge for better efficiency and no heat sink is required." | [UM] |
| Logic supply | No separate logic supply stated; only RST and GND of the Arduino power header are connected to the shield | [UM] |
| Protections (over-current, thermal, under-voltage, reverse polarity) | **Not stated** | — |
| Test buttons | 2: Test Button A (current A→B, CW*) and Test Button B (current B→A, CCW*) | [UM] |
| LEDs | Red LED A, Red LED B, Green Power LED | [UM] |
| Reset button | Yes, resets the Arduino main board | [UM] |
| Dimensions | Drawing only; no numbers in text | [UM] |
| Operating temperature | Not stated | — |
| Packing list | 1 x SHIELD-MD10 shield; 2 x mini jumper | [UM] |
| Warranty | 12 months; manufacturing defects only; misuse and two-way freight not covered | [UM] |

\* "or CW/CCW depending on the connection" [UM].
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** single-channel shield for one brushed DC motor up to 10 A continuous; stacks on UNO-form-factor boards (Arduino UNO R3, Mega 2560 R3, Maker UNO / Maker UNO Plus, Leonardo, CT-UNO, CT-ARM); solid-state H-bridge; stackable headers; two mini jumpers select the PWM and DIR pins, so shields can be stacked [PP].
- **Features list:** 7–25 V (Rev1.0), **7–30 V (Rev2.0)**; 10 A continuous, 15 A peak (10 seconds); 3.3 V and 5 V logic; fully NMOS H-bridge, no heatsink; **regenerative braking**; PWM up to 10 kHz; selectable PWM/DIR pins [PP].
- **Packing list:** 1x Shield-MD10 (components soldered, two mini jumpers) [PP].
- **Resources:** User's Manuals for Rev1.0 and Rev2.0, CytronMotorDriver library, Fritzing files, 3D design (GitHub) [PP].

## Interfaces, terminals and pin mapping
**Terminal block** — motor and power [UM]:

| Pin | Name | Description |
|---|---|---|
| 1 | POWER + | Positive supply |
| 2 | POWER - | Negative supply |
| 3 | Motor Output A | Connect to motor terminal A |
| 4 | Motor Output B | Connect to motor terminal B |

**Arduino pin selection (mini jumpers)** [UM]:
- **PWM Pin Selector:** D3, D5, D6, D9, D10 or D11. **Default D3.**
- **DIR Pin Selector:** D2, D4, D7, D8, D12 or D13. **Default D2.**
- "Remember to initialize the correct Arduino's digital pin accordingly in the user sketch/program."

Other board items [UM]:
- Stackable Digital I/O headers JP4 and JP6.
- **Optional External Control** — "for the use of other types of microcontroller besides Arduino." (header pin-out not given in text)
- Stackable Analog Input header — not used by SHIELD-MD10 (passed through).
- Stackable Power Pins header — "Only RST and GND pins are connected to the SHIELD-MD10."
- Red LED A: on when output A high, B low (current A→B). Red LED B: on when A low, B high (current B→A). Green Power LED: on when the shield is powered.
- Wire size / terminal rating: not stated.

A PWM/DIR truth table is **not given** in the SHIELD-MD10 manuals.

## Rules and gotchas (for code, wiring and tutorials)
- **Default pins: PWM = D3, DIR = D2** [UM]. The library example uses D3/**D4** [GH] — tell readers to match code to the jumpers.
- **The shield does not power the Arduino** — only RST and GND are connected from the power header; "Don't forget about the power source for the Arduino main board too." [UM]
- **Power-up order:** "Power up the Arduino main board and load the sketch/program first before powering up the SHIELD-MD10 motor driver shield." [UM]
- Peak 15 A for ≤ 10 s — half the peak of SHIELD-MDD10/MDD10A [UM].
- PWM max **10 kHz** (not 20 kHz) [UM].
- Logic input high max 5.5 V [UM].
- Supply voltage: Rev2.0 feature list says 7–30 V, but the Rev2.0 spec table says 25 V max — until [DT] confirms, do not present 30 V as an absolute-maximum rating without noting this.
- Rev 2.0 boards carry "SHIELD-MD10 R2" on front and back — use this to tell readers which manual applies [UM].
- Reverse polarity, battery vs SMPS, over-current behaviour: not stated in any source — do not claim protections.

## Power and electrical limits
- Motor supply 7–30 V (Rev2.0 feature list) / 7–25 V (Rev2.0 and Rev1.0 spec tables; Rev1.0 feature list) [UM][UM-R1].
- 10 A continuous; 15 A peak, must not exceed 10 s [UM].
- No heatsink required [UM]; no derating or temperature data.
- Over-current, thermal, under-voltage, reverse-polarity protection: not stated.
- Battery vs switching supply / regenerative current: not stated.

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, v1.0.1); SHIELD-MD10 is listed under the **PWM_DIR** example [GH]:
  - `CytronMD motor(PWM_DIR, 3, 4);` then `motor.setSpeed(-255..255)` [GH]. With the shield's default jumpers use `CytronMD motor(PWM_DIR, 3, 2);` (PWM D3, DIR D2) [UM].
- The manual points to example code on the product page [UM].
- Other languages: not stated.

## Compatibility and accessories
- "Compatible with Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo and possibly other pin compatible main boards." [UM]
- Stackable: "allows for more Arduino shields to be stacked on top of it." [UM]
- Other microcontrollers via the Optional External Control header [UM].
- 3D files (Rev 2): "SHIELD-MD10 R2.STEP", "SHIELD-MD10 R2.IGS" and PNG renders [GH]: https://github.com/CytronTechnologies/Shield-MD10-3D

## Revision history
| Revision | Manual | Differences stated |
|---|---|---|
| Rev 1.0 | V1.1, September 2014 [UM-R1] | Feature list "7V to 25V"; table 7–25 V; otherwise identical text to the Rev2.0 manual (10 A / 15 A 10 s, 10 kHz, same pins, same packing list) |
| Rev 2.0 (current) | V1.0, June 2015 [UM] | Feature list "New!! … 7V to 30V"; "There is an improvement made in Shield MD10 Rev 2.0" (improvement not described); labelled "SHIELD-MD10 R2" front and back |

## Common mistakes / troubleshooting
- Motor does nothing → code pins do not match jumpers (defaults D3 PWM / D2 DIR) [UM].
- Arduino not powered → the shield does not supply the Arduino; power it separately [UM].
- Unexpected motor motion at start-up → power the Arduino and load the sketch before powering the shield [UM].
- Quick hardware check → press Test Button A/B; Red LED A/B should light [UM].
- Wrong direction → swap Motor Output A/B [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Max supply voltage (Rev2.0) | [UM] Rev2.0 feature list: "7V to 30V"; [PP] (read 2026-10-19): "7V to 25V (Rev1.0), 7V to 30V (Rev2.0)" | [UM] Rev2.0 Absolute Maximum Rating table: Max 25 V | Feature list and product page agree on 30 V for Rev2.0; the table is probably carried over from Rev1.0 — confirm with [DT] before quoting 30 V as an absolute maximum |
| Max supply voltage by revision | [UM-R1] (V1.1, Sep 2014): 7–25 V | [UM] Rev2.0 (V1.0, Jun 2015, newer): 7–30 V (feature list) | Rev 2.0 is current; Rev 1.0 = 25 V |
| Manual version numbers | Rev1.0 manual is "V1.1" (Sep 2014) | Rev2.0 manual is "V1.0" (Jun 2015) | Date, not version, shows which is newer |
| Example DIR pin | [UM] default DIR = D2 | [GH] PWM_DIR example DIR = D4 | Both valid jumper positions; [UM] default stated in text |

## Needs verification
1. Rev2.0 absolute maximum voltage: 25 V (table) or 30 V (feature list, product name).
2. What the Rev 2.0 "improvement" is, beyond the voltage range.
3. Board dimensions (drawing only) and Optional External Control header pin-out.
4. Any protection features (over-current, thermal, under-voltage, reverse polarity) — none stated.
5. Truth table / brake behaviour when PWM is low — not stated for this shield.

## Sources
- [UM] SHIELD-MD10 User's Manual for Rev2.0 (V1.0, June 2015): https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view
- [UM-R1] SHIELD-MD10 User's Manual for Rev1.0 (V1.1, September 2014): https://docs.google.com/document/d/1acVuzZKuqC_79RzD5BRT9IQ7ug63zG0wpf-bUgQ7QHY/view
- PDF mirror of the Rev2.0 manual (cross-check): https://stgaws.robu.in/wp-content/uploads/2015/01/SHIELD-MD10Users_ManualREV2.pdf
- [PP] Product page: https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino
- [GH] 3D design: https://github.com/CytronTechnologies/Shield-MD10-3D
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
