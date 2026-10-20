# 10 Amp 7V-30V Potentiometer & Switch Control DC Motor Driver (MD10-POT) — Verified Reference

| | |
|---|---|
| Product code | `MD10-POT` (datasheet title [DS]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). Packing list, board size, locked-antiphase support, regenerative braking and the lack of reverse-polarity protection are now Cytron-stated |
| Primary source | "MD10-POT Potentiometer and Switch Control 10Amp DC Motor Driver Datasheet" — **Rev 1.0, Oct 2018** — public Google Doc: https://docs.google.com/document/d/1U_dn6OCEw76pqJaIzZYuWqWoU1C9APwpNp8qztaJ1uA/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A single-channel brushed DC motor driver, 7–30 V input, 10 A continuous and 30 A peak (less than 10 seconds), that can be controlled either by a 10KΩ potentiometer (speed) and an SPDT switch (direction), or by PWM/DIR signals from a controller [DS]. It has an internal PWM generator (9–11 KHz) used when the potentiometer controls speed [DS].
- Datasheet title: "Potentiometer and Switch Control 10Amp DC Motor Driver" [DS].

## Specifications
Datasheet section 2, **"Table 3: MD10-POT Absolute Maximum Ratings"** [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 7 V, Max 30 V | [DS] |
| Maximum motor current — continuous | Max 10 A | [DS] |
| Maximum motor current — peak | Max 30 A — "(Less than 10 seconds)" | [DS] |
| Logic input voltage — low level (PWM, DIR) | Min 0 V, Max 0.5 V | [DS] |
| Logic input voltage — high level (PWM, DIR) | Min 3 V, Max **30 V** | [DS] |
| Internal PWM generator frequency | Min 9 KHz, Max 11 KHz — "(Output frequency when potentiometer is used)" | [DS] |
| External PWM input frequency | DC to 20 KHz — "(Output Frequency = Input Frequency)" | [DS] |
| Number of channels | 1 (one Motor Output Terminal; single truth table) | [DS] |
| Logic supply | No separate logic supply described; power via Power Input Terminal | [DS] |
| Control modes | Speed: 10KΩ potentiometer or PWM signal; direction: SPDT switch or DIR pin. Sign-magnitude PWM (PWM + DIR) per truth table | [DS] |
| Locked-antiphase PWM | Not stated | — |
| RC / analog-voltage / serial input | Not stated | — |
| How the control source is selected (pot/switch vs PWM/DIR) | Not stated | — |
| Protections (reverse polarity, over-current, thermal, under-voltage) | Not stated | — |
| Test buttons | "Test Buttons — Press to test the functionality of the motor / driver." (count not stated in text) | [DS] |
| LEDs | Power LED ("Turn on when power up"); Motor Status LEDs ("Turn on when the motor is running") | [DS] |
| Dimensions | 81.28 mm × 48.26 mm | [PP] |
| Operating temperature | Not stated | — |
| Packing list | 1x MD10-POT, 1x 10 kΩ potentiometer with connector, 1x 3-way rocker switch with connector, 1x Quick Start Guide card | [PP] |
| Warranty | 12 months | [PP] |
| 3D printable case | STL file linked on the product page | [PP] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Features list:** bidirectional control of one brushed DC motor; run/brake and direction with a **3-way rocker switch (included)**; speed with a **potentiometer (included)**; 7–30 V; **10 A continuous, 30 A peak**; test buttons; motor output LEDs; PWM and DIR inputs; **compatible with sign-magnitude and locked-antiphase PWM**; **regenerative braking**; **no reverse polarity protection**; **dimension 81.28 mm × 48.26 mm** [PP].
- **Description:** no microcontroller or programming needed; switch = activation and direction, potentiometer = speed [PP].
- **Packing list:** 1x MD10-POT, 1x 10 kΩ potentiometer with connector, 1x 3-way rocker switch with connector, 1x Quick Start Guide card [PP].
- **Resources:** datasheet (Google Doc), sample code (CytronMotorDriver library), 3D CAD, 3D-printable case STL and CAD [PP]. A wiring image is on the page (not read).

## Interfaces, terminals and pin mapping
"Table 1: MD10-POT Board Functions" [DS]:

| Function | Description |
|---|---|
| Power Input Terminal | Connect to battery. |
| Motor Output Terminal | Connect to motor. |
| Power LED | Turn on when power up. |
| Motor Status LEDs | Turn on when the motor is running. |
| Test Buttons | Press to test the functionality of the motor / driver. |
| Speed Control Potentiometer | Connect to 10KΩ potentiometer for motor speed control. |
| Direction Switch | Connect to SPDT Switch for motor direction control. |
| PWM/DIR Input | Use this to control the motor with PWM signal. DIR pin is used for direction control. |

"Table 2: PWM/DIR Input Truth Table" [DS]:

| PWM | DIR | Output A (MA) | Output B (MB) | Motor |
|---|---|---|---|---|
| Low | X (Don't Care) | Low | Low | Brake |
| High | Low | High | Low | Forward |
| High | High | Low | High | Reverse |

- Pin order of the PWM/DIR header, potentiometer and switch connectors: shown only in Figure 1 (not readable as text) [DS].
- Motor outputs are labelled MA and MB [DS].
- Wire size / terminal rating: not stated.

## Rules and gotchas (for code, wiring and tutorials)
- Power Input Terminal: "Connect to battery." [DS] — the datasheet does not discuss switching power supplies or regenerative current.
- Logic high accepted from **3 V up to 30 V** on PWM and DIR [DS] — unlike MD10C/MD30C (5.5 V max). Logic low must be ≤ 0.5 V [DS].
- External potentiometer value: **10KΩ** [DS]; direction switch: **SPDT** [DS].
- Internal PWM is 9–11 KHz when the potentiometer is used; external PWM up to 20 KHz, output follows input [DS].
- PWM LOW = brake (both outputs low) regardless of DIR [DS].
- 30 A peak only for less than 10 seconds; 10 A continuous [DS] (no temperature condition stated).
- "Forward"/"Reverse" in the truth table depend on motor wiring.
- Do not describe reverse-polarity, over-current or thermal protection in content — none is stated.

## Power and electrical limits
- Power input 7–30 V [DS].
- 10 A continuous; 30 A peak for less than 10 seconds [DS].
- Protections (reverse polarity, over-current, thermal, under-voltage): not stated in any source read.
- Heatsink/fan requirement, derating, operating temperature: not stated.
- SMPS / regenerative current guidance: not stated (only "Connect to battery.").

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, version 1.0.1, architectures=*); MD10-POT is listed under the **PWM_DIR** example [GH] — https://github.com/CytronTechnologies/CytronMotorDriver
  - `CytronMD motor(PWM_DIR, 3, 4);` (example: PWM = D3, DIR = D4, GND to GND); `setSpeed(-255..255)`; positive speed = DIR LOW = Output A high [GH][DS].
- No code is needed for potentiometer/switch control [DS].
- MicroPython / CircuitPython / ROS: not stated.

## Compatibility and accessories
- External 10KΩ potentiometer and SPDT switch for standalone control [DS] (whether they are included is not stated).
- PWM/DIR from a controller; logic high 3–30 V [DS].
- 3D printable case (STL) linked on the product page [PP].

## Common mistakes / troubleshooting
- Using a potentiometer of a different value → datasheet specifies 10KΩ [DS].
- Expecting the motor to run with PWM LOW → PWM LOW brakes [DS].
- Peak current held too long → 30 A only for less than 10 seconds [DS].
- Quick functional check → press the Test Buttons; Motor Status LEDs turn on when the motor is running [DS].
- Supply below 7 V → outside the 7–30 V range [DS].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Voltage / current in name | [PP] name "10 Amp 7V-30V" | [DS] 7–30 V, 10 A continuous | Agree |
| Direction switch | [DS]: "SPDT switch" | [PP]: "3-way rocker switch" for run/brake and direction | Same part described two ways (a centre-off rocker); say "3-way rocker switch (included)" |

## Needs verification
1. Connector pin order (PWM/DIR header, potentiometer, switch) — Figure 1 only.
2. How the driver chooses between potentiometer/switch and PWM/DIR input (jumper, priority, or automatic) — not stated.
3. Number of test buttons and Motor Status LEDs — plural only.
4. SMPS / regenerative-current guidance, operating temperature, wire size, warranty — not stated.
5. Mounting-hole positions (board size 81.28 × 48.26 mm is on the product page).
6. Over-current, thermal and under-voltage protection — not stated (the page says there is no reverse-polarity protection).
7. How locked-antiphase mode is wired with the PWM/DIR inputs — the page says it is supported; the datasheet gives no truth table for it.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [MD10-POT: Controlling DC Motor without Writing Code](https://my.cytron.io/tutorial/md10-pot-controlling-dc-motor-without-writing-code) — Tutorial, Beginner, 2025 [PP: tutorial]
- [Make Turntable using MD10-POT Motor Driver](https://my.cytron.io/tutorial/turntable-md10pot) — Tutorial, Beginner, 2024 [PP: tutorial]
- [MD10-POT Conveyor Belt Control without Code](https://my.cytron.io/tutorial/MD10-POT_Conveyor_Belt_Control_without_Code) — Tutorial, Beginner, 2026 [PP: tutorial]

## Sources
- [DS] MD10-POT Datasheet (Google Doc, "MD10-POT Potentiometer and Switch Control 10Amp DC Motor Driver Datasheet, Rev 1.0, Oct 2018"): https://docs.google.com/document/d/1U_dn6OCEw76pqJaIzZYuWqWoU1C9APwpNp8qztaJ1uA/view
- PDF mirror of the same datasheet (cross-check only): https://www.farnell.com/datasheets/4726001.pdf
- [PP] Product page "10 Amp 7V-30V Potentiometer & Switch Control DC Motor Driver": https://my.cytron.io/p-10-amp-7v-30v-potentiometer-and-switch-control-dc-motor-driver (read by coordinator 2026-10-16)
- [PP] 3D printable case STL (linked from product page, not opened): https://drive.google.com/file/d/1-sOq8sI3cUeYis4u52VVhTNf2r8fR8o3/view
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
