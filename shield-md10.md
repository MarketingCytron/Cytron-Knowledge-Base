# 10Amp 7V-30V DC Motor Driver Shield for Arduino — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-MD10` (manual title [UM]; product-page image paths [PP]); Rev 2.0 boards are labelled "SHIELD-MD10 R2" [UM] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron 3D design repo "Shield-MD10-3D" (SHIELD-MD10 R2; single commit 7 Jan 2019; STEP exported 31 Jul 2018 from SolidWorks 2015) read: all three PNG renders viewed and the STEP file parsed for the PCB solid. Settled from the board silkscreen: PWM/DIR truth table printed on the bottom (PWM 0 → both outputs LOW), terminal order + − (POWER, green 2-way block) and A B (MOTOR, black 2-way block), Optional External Control header pin-out DIR / PWM / GND, jumper rows D3 D5 D6 D9 D10 D11 (PWM) and D2 D4 D7 D8 D12 D13 (DIR), LED and button labels; PCB outline 76.2 × 55.88 × 1.6 mm derived from the model. Stays Medium — the Rev2.0 manual's 25 V table versus 30 V feature list is not settled by the model; still open: absolute-maximum voltage, protections, Rev 2.0 "improvement". Earlier: 2026-10-19 master-table review (Medium batch 4) of the live product page — 7–25 V Rev1.0 / 7–30 V Rev2.0, 10 A / 15 A (10 s), regenerative braking, 10 kHz, packing list |
| Primary source | No datasheet exists. Top source: "SHIELD-MD10 Cytron 10A Motor Driver Shield User's Manual" — **V1.0, June 2015** (the Rev2.0 manual; Drive title "SHIELD-MD10 User's_Manual REV 2") — https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view. Board-level facts (silkscreen, truth table, outline) from the Cytron 3D model "SHIELD-MD10 R2" (STEP/IGES + 3 PNG renders, GitHub, last commit Jan 2019) [DT] — https://github.com/CytronTechnologies/Shield-MD10-3D |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = Rev2.0 manual (V1.0, June 2015), read in full from the Google Doc; a PDF mirror (stgaws.robu.in, "V1.0", "JUNE 2015") matches. [UM-R1] = Rev1.0 manual, "V1.1, September 2014" (Drive title "SHIELD-MD10 User's_Manual"): https://docs.google.com/document/d/1acVuzZKuqC_79RzD5BRT9IQ7ug63zG0wpf-bUgQ7QHY/view. Note the version numbers: the *newer* Rev2.0 manual is numbered V1.0. Figures (board layout, dimension, wiring) are images and were not readable. No newer document on Drive. [PP] = my.cytron.io page read by the coordinator 2026-10-16 (name, code, stock only). [DT] = Cytron 3D design files in https://github.com/CytronTechnologies/Shield-MD10-3D ("SHIELD-MD10 R2.STEP", "SHIELD-MD10 R2.IGS", renders "SHIELD-MD10 R2 00/01/02.PNG"; one commit, 7 Jan 2019; STEP header dated 2018-07-31, SolidWorks 2015) — read 2026-10-21. Silkscreen text is read from the renders; dimensions are **derived from the 3D model** (PCB solid parsed from the STEP file, units mm) and are not printed in any Cytron document. The repo is the single-channel SHIELD-MD10 R2, not SHIELD-MDD10.

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
| Main parts in the 3D model | 4 power MOSFETs Q1–Q4 (model part "TO-252AA", i.e. D-PAK outline), 3 SOIC-8 ICs (U1–U3), inductor L1, electrolytic capacitors (largest C6, model part 10 × 10.7 mm), diodes D1–D7 — part numbers not given | [DT] |
| Logic supply | No separate logic supply stated; only RST and GND of the Arduino power header are connected to the shield | [UM] |
| Protections (over-current, thermal, under-voltage, reverse polarity) | **Not stated** | — |
| Test buttons | 2: Test Button A (current A→B, CW*) and Test Button B (current B→A, CCW*) | [UM] |
| LEDs | Red LED A, Red LED B, Green Power LED | [UM] |
| Reset button | Yes, resets the Arduino main board | [UM] |
| Dimensions | Manual: drawing only, no numbers in text [UM]. **Derived from the 3D model:** PCB outline 76.2 × 55.88 mm (3.00 × 2.20 in), PCB 1.6 mm thick, corner radius 1.52 mm; four Ø3.05 mm mounting holes whose spacing matches the Arduino UNO hole pattern (inference from positions) | [UM] / [DT] |
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
**Terminal block** — motor and power [UM]. The 3D model shows two 2-way screw terminals side by side: a green block JP1 labelled **+ / −** ("POWER" on the bottom) and a black block JP2 labelled **A / B** ("MOTOR") — order along the edge +, −, A, B, matching the manual's pins 1–4 [DT]:

| Pin | Name | Description |
|---|---|---|
| 1 | POWER + | Positive supply |
| 2 | POWER - | Negative supply |
| 3 | Motor Output A | Connect to motor terminal A |
| 4 | Motor Output B | Connect to motor terminal B |

**Arduino pin selection (mini jumpers)** [UM]:
- **PWM Pin Selector:** D3, D5, D6, D9, D10 or D11. **Default D3.** Silkscreen in the 3D model: column "PWM" with D3, D5, D6, D9, D10, D11; column "DIR" with D2, D4, D7, D8, D12, D13 (2 × 6 headers, one mini jumper each) [DT].
- **DIR Pin Selector:** D2, D4, D7, D8, D12 or D13. **Default D2.**
- "Remember to initialize the correct Arduino's digital pin accordingly in the user sketch/program."

Other board items [UM]:
- Stackable Digital I/O headers JP4 and JP6.
- **Optional External Control** — "for the use of other types of microcontroller besides Arduino." [UM]. 3-pin header near the board edge, silkscreen **DIR, PWM, GND** (square pad at GND) [DT].
- Stackable Analog Input header — not used by SHIELD-MD10 (passed through).
- Stackable Power Pins header — "Only RST and GND pins are connected to the SHIELD-MD10."
- Red LED A: on when output A high, B low (current A→B). Red LED B: on when A low, B high (current B→A). Green Power LED: on when the shield is powered. Silkscreen: DS1 "PWR", DS3 "A", DS2 "B" [DT].
- Buttons in the 3D model: S1 "RST" (Arduino reset), S2 "A" and S3 "B" (test buttons) [DT].
- Board marking: "SHIELD-MD10 R2" on top; bottom "CYTRON 10A Motor Driver Shield SHIELD-MD10 R2" and www.cytron.com.my [DT] — matches the manual's "SHIELD-MD10 R2" front and back [UM].
- Bottom silkscreen on the stacking pins: D2–D13 (with "~PWM" marks at D3, D5, D6, D9, D10, D11), GND, and on the power header only RST, GND, GND labelled — consistent with "only RST and GND pins are connected" [DT][UM].
- Wire size / terminal rating: not stated.

**PWM/DIR truth table** — not in the manuals, but printed on the bottom silkscreen of the R2 board (3D model) [DT]:

| PWM | DIR | OUT A | OUT B |
|---|---|---|---|
| 0 | X | LOW | LOW |
| 1 | 0 | HIGH | LOW |
| 1 | 1 | LOW | HIGH |

PWM low pulls both outputs LOW (motor terminals shorted to ground — brake-to-ground behaviour, inference from the table). DIR 0 gives A→B current, the same as Test Button A / LED A [DT][UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Default pins: PWM = D3, DIR = D2** [UM]. The library example uses D3/**D4** [GH] — tell readers to match code to the jumpers.
- **The shield does not power the Arduino** — only RST and GND are connected from the power header; "Don't forget about the power source for the Arduino main board too." [UM]
- **Power-up order:** "Power up the Arduino main board and load the sketch/program first before powering up the SHIELD-MD10 motor driver shield." [UM]
- Peak 15 A for ≤ 10 s — half the peak of SHIELD-MDD10/MDD10A [UM].
- PWM max **10 kHz** (not 20 kHz) [UM].
- Logic input high max 5.5 V [UM].
- Supply voltage: Rev2.0 feature list says 7–30 V, but the Rev2.0 spec table says 25 V max — until [DT] confirms, do not present 30 V as an absolute-maximum rating without noting this.
- Rev 2.0 boards carry "SHIELD-MD10 R2" on front and back — use this to tell readers which manual applies [UM][DT].
- **Truth table:** PWM 0 → A LOW, B LOW; PWM 1 + DIR 0 → A HIGH, B LOW; PWM 1 + DIR 1 → A LOW, B HIGH (bottom silkscreen) [DT]. Between PWM pulses the motor is braked, not left floating (inference).
- External-controller wiring: use the 3-pin DIR / PWM / GND header, and share GND [DT].
- Reverse polarity, battery vs SMPS, over-current behaviour: not stated in any source — do not claim protections.

## Power and electrical limits
- Motor supply 7–30 V (Rev2.0 feature list) / 7–25 V (Rev2.0 and Rev1.0 spec tables; Rev1.0 feature list) [UM][UM-R1].
- 10 A continuous; 15 A peak, must not exceed 10 s [UM].
- No heatsink required [UM]; no derating or temperature data.
- Over-current, thermal, under-voltage, reverse-polarity protection: not stated.
- Battery vs switching supply / regenerative current: not stated.

## Software support
- **Cytron example sketch** `CytronTechnologies/Cytron_ShieldMD10` (ShieldMd10Example, Rev 1.0, 22 Oct 2012; repo updated Jan 2019): PWM on **D3**, DIR on **D2** (one of the jumper-selectable pin pairs); ramps the motor from 0 to full speed and back in both directions with `analogWrite` [GH].
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, v1.0.1); SHIELD-MD10 is listed under the **PWM_DIR** example [GH]:
  - `CytronMD motor(PWM_DIR, 3, 4);` then `motor.setSpeed(-255..255)` [GH]. With the shield's default jumpers use `CytronMD motor(PWM_DIR, 3, 2);` (PWM D3, DIR D2) [UM].
- The manual points to example code on the product page [UM].
- Other languages: not stated.

## Compatibility and accessories
- "Compatible with Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo and possibly other pin compatible main boards." [UM]
- Stackable: "allows for more Arduino shields to be stacked on top of it." [UM]
- Other microcontrollers via the Optional External Control header [UM].
- 3D files (Rev 2): "SHIELD-MD10 R2.STEP", "SHIELD-MD10 R2.IGS" and three PNG renders, one commit 7 Jan 2019 [DT]: https://github.com/CytronTechnologies/Shield-MD10-3D. Derived PCB outline 76.2 × 55.88 mm — larger than an Arduino UNO (68.6 × 53.3 mm, general knowledge), so the shield extends beyond the UNO outline (inference).

## Revision history
| Revision | Manual | Differences stated |
|---|---|---|
| Rev 1.0 | V1.1, September 2014 [UM-R1] | Feature list "7V to 25V"; table 7–25 V; otherwise identical text to the Rev2.0 manual (10 A / 15 A 10 s, 10 kHz, same pins, same packing list) |
| Rev 2.0 (current) | V1.0, June 2015 [UM]; 3D model "SHIELD-MD10 R2" (repo Jan 2019) [DT] | Feature list "New!! … 7V to 30V"; "There is an improvement made in Shield MD10 Rev 2.0" (improvement not described); labelled "SHIELD-MD10 R2" front and back; bottom silkscreen truth table [DT] |

## Common mistakes / troubleshooting
- Motor does nothing → code pins do not match jumpers (defaults D3 PWM / D2 DIR) [UM].
- Arduino not powered → the shield does not supply the Arduino; power it separately [UM].
- Unexpected motor motion at start-up → power the Arduino and load the sketch before powering the shield [UM].
- Quick hardware check → press Test Button A/B; Red LED A/B should light [UM].
- Wrong direction → swap Motor Output A/B [UM], or invert DIR in code (DIR 0 = A HIGH/B LOW) [DT].
- Motor stops hard when PWM is low → expected: PWM 0 drives both outputs LOW [DT].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Max supply voltage (Rev2.0) | [UM] Rev2.0 feature list: "7V to 30V"; [PP] (read 2026-10-19): "7V to 25V (Rev1.0), 7V to 30V (Rev2.0)" | [UM] Rev2.0 Absolute Maximum Rating table: Max 25 V | Feature list and product page agree on 30 V for Rev2.0; the table is probably carried over from Rev1.0 — confirm with [DT] before quoting 30 V as an absolute maximum |
| Max supply voltage by revision | [UM-R1] (V1.1, Sep 2014): 7–25 V | [UM] Rev2.0 (V1.0, Jun 2015, newer): 7–30 V (feature list) | Rev 2.0 is current; Rev 1.0 = 25 V |
| Manual version numbers | Rev1.0 manual is "V1.1" (Sep 2014) | Rev2.0 manual is "V1.0" (Jun 2015) | Date, not version, shows which is newer |
| Terminal block form | [UM] one terminal table, pins 1–4 (POWER +, POWER −, Motor A, Motor B) | [DT] two 2-way blocks (green JP1 + / −, black JP2 A / B) | No conflict — same order; the model shows the physical split |
| Truth table | [UM] none given | [DT] bottom silkscreen: PWM 0 → A/B LOW; PWM 1 DIR 0 → A HIGH; PWM 1 DIR 1 → B HIGH | Silkscreen used; does not contradict the manual |
| Max supply voltage (Rev2.0), 3D model | [UM]/[PP] 25 V table vs 30 V feature list | [DT] 3D model: no voltage marking; capacitor ratings not modelled | Not settled by the model — stays open |
| Example DIR pin | [UM] default DIR = D2 | [GH] PWM_DIR example DIR = D4 | Both valid jumper positions; [UM] default stated in text |

## Needs verification
1. Rev2.0 absolute maximum voltage: 25 V (table) or 30 V (feature list, product name).
2. What the Rev 2.0 "improvement" is, beyond the voltage range.
3. Board dimensions: cross-check the derived 76.2 × 55.88 mm PCB outline [DT] against the manual's dimension drawing (image, not read).
4. Any protection features (over-current, thermal, under-voltage, reverse polarity) — none stated.
5. Whether the "regenerative braking" on the product page is the PWM-low LOW/LOW state shown on the silkscreen (not explained in text).
6. Part numbers of the MOSFETs and the three SOIC-8 ICs (the model gives package outlines only), and the purpose of inductor L1.

## Sources
- [GH] Example sketch: https://github.com/CytronTechnologies/Cytron_ShieldMD10 (ShieldMd10Example.ino, Rev 1.0, 22 Oct 2012; read 2026-10-21)
- [UM] SHIELD-MD10 User's Manual for Rev2.0 (V1.0, June 2015): https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view
- [UM-R1] SHIELD-MD10 User's Manual for Rev1.0 (V1.1, September 2014): https://docs.google.com/document/d/1acVuzZKuqC_79RzD5BRT9IQ7ug63zG0wpf-bUgQ7QHY/view
- PDF mirror of the Rev2.0 manual (cross-check): https://stgaws.robu.in/wp-content/uploads/2015/01/SHIELD-MD10Users_ManualREV2.pdf
- [PP] Product page: https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino
- [DT] 3D design "SHIELD-MD10 R2" (STEP AP214 exported 2018-07-31, IGES, 3 PNG renders; single commit in the CytronTechnologies repo, 7 Jan 2019), read 2026-10-21: https://github.com/CytronTechnologies/Shield-MD10-3D
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
