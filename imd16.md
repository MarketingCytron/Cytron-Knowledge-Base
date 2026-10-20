# iMD16 — Verified Reference

| | |
|---|---|
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | "iMD16 Datasheet", **Rev 1.0, April 2026** (Google Doc last modified 2026-10-05): (Cytron document — link not public) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A single-channel, bidirectional brushed DC motor driver in a metal enclosure: "16 Amp 7-30V Industrial DC motor Driver" [DS]. Power input 7–30 V DC, 16 A continuous / 30 A peak (< 10 seconds) [DS]. Two control modes: **PWM/DIR input** from an external microcontroller or PLC, or **POT/SWITCH** standalone mode with a 10 kΩ potentiometer for speed and a 3-way rocker switch for forward/stop/reverse, needing no microcontroller [DS]. Power and motor connect by screw terminals; control signals connect by three 3-pin JST PH connectors [DS].

## Specifications
Datasheet Table 3, every row [DS]:

| Item | Value | Src |
|---|---|---|
| Power Input Voltage | Min 7 V, Max 30 V | [DS] |
| Maximum Motor Current – Continuous | Max 16 A | [DS] |
| Maximum Motor Current – Peak (Less than 10 seconds) | Max 30 A | [DS] |
| Logic Input Voltage – Low Level (PWM, DIR) | Min 0 V, Max 0.5 V | [DS] |
| Logic Input Voltage – High Level (PWM, DIR) | Min 3 V, Max 30 V | [DS] |
| Internal PWM Generator Frequency (output frequency when the potentiometer is used) | Min 9 kHz, Max 11 kHz | [DS] |
| External PWM Input Frequency (Output Frequency = Input Frequency) | DC to 20 kHz | [DS] |

Other facts:

| Item | Value | Src |
|---|---|---|
| Channels | 1 motor output (MA, MB), bidirectional | [DS] |
| Current limiting | **None.** "iMD16 does not have a current limiting function" | [DS] |
| Thermal / over-temperature protection | Not stated | [DS] |
| Reverse polarity protection | Not stated | [DS] |
| Under-voltage protection | Not stated | [DS] |
| Isolation between logic and power | Not stated | [DS] |
| Brake | PWM Low → MA Low, MB Low → Brake | [DS] |
| Enclosure | Metal enclosure; doubles as passive heatsink; fanless | [PP] |
| IP rating | Not stated | [DS][PP] |
| Dimensions (Figure 4, mm) | Length 102.00 overall (flange to flange); width 52.20; enclosure body 73.99 long; 18.46 and 9.56 flange/terminal offsets; 16.60 and 5.00 height dimensions (5.00 = flange thickness); no single overall height given | [DS] |
| Mounting | Two slotted mounting holes marked **M4**, slot centres **93.00 mm** apart, slot length dimension 24.00 mm | [DS] |
| Operating temperature | Not stated (see *Needs verification* for a lab test result) | [DS] |
| Unit weight | Not stated | — |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Spec list:** 7–30 V DC; 16 A continuous; 30 A peak (< 10 s); logic low 0–0.5 V, high 3–30 V (PWM/DIR); internal PWM 9–11 kHz; external PWM DC–20 kHz [PP].
- **Features:** metal enclosure that doubles as a heatsink (internal thermal pad); dual control — built-in potentiometer and direction switch interface, or PWM/DIR from a microcontroller/PLC; "accepts wide logic levels (up to 30V)" for 24 V PLC outputs; brake when PWM is low; status LEDs for power and motor operation; "panel-mount screw terminals" for power, motor and control signals [PP].
- **SMPS note (page):** "If an industrial switching power supply is used, please connect it parallelly with the same voltage battery" so the battery absorbs regenerative power [PP].
- **Description:** pre-wired speed potentiometer and 3-position rocker switch (Forward–OFF–Reverse) with connectors; "Use JST-PH connectors" in one paragraph, and "All critical connections are extended to panel-mount screw terminals … External control (PWM, DIR, GND), Direction switch and potentiometer" in another [PP].
- **Packing list:** 1x iMD16, 1x 10 kΩ potentiometer with connector, 1x 3-way rocker switch with connector, 1x JST PH connector for signal (PWM/DIR) control, 1x mini Phillips screwdriver, 1x Quick Start Guide card [PP].
- **Resources:** Getting Started Guide for iMD16, "Conveyor Belt Control without Code using iMD16" (Cytron tutorials), datasheet (Google Drive), 3D CAD [PP].

## Interfaces, terminals and pin mapping
Datasheet Table 1 / Figure 1 [DS]:

| No. | Function | Connector and labels | Description |
|---|---|---|---|
| 1 | Power LED | PWR | Lights when supply voltage is present |
| 2 | Power Input Terminal | 2-way screw terminal, silkscreen POWER **+ / −** | External DC supply, 7–30 V DC |
| 3 | Motor Output Terminal | 2-way screw terminal, silkscreen MOTOR **MA / MB** | DC motor, bidirectional drive |
| 4 | Motor Status LEDs | 2 LEDs labelled MA and MB | "Indicate motor operating conditions" |
| 5 | Speed Control Potentiometer | 3-pin JST PH, silkscreen SPEED POT(10K): **P3, P2, P1** | For a 10 kΩ potentiometer; analog speed input |
| 6 | Direction Switch | 3-pin JST PH, silkscreen DIR SWITCH: **MB, COM, MA** | For a 3-way rocker switch: Forward, Stop, Reverse |
| 7 | PWM/DIR Input | 3-pin JST PH, silkscreen PWM/DIR: **DIR, PWM, GND** | External PWM (speed) and DIR (direction) |

PWM/DIR truth table (Table 2) [DS]:

| PWM | DIR | MA | MB | Motor |
|---|---|---|---|---|
| Low | X (don't care) | Low | Low | Brake |
| High | Low | High | Low | Forward |
| High | High | Low | High | Reverse |

- Figure 2 (PWM/DIR mode) wires the microcontroller's DIR, PWM and GND to the PWM/DIR connector, battery to POWER, motor to MA/MB [DS].
- Figure 3 (POT/SWITCH mode) wires the potentiometer to SPEED POT and the rocker switch to DIR SWITCH; the PWM/DIR connector is left unused [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **No current limit.** 16 A continuous and 30 A peak (< 10 s) are maximum supported currents, "not an active current limit imposed by the driver. Operating above the rated current may cause the board to overheat and could damage it." [DS] Never write that the iMD16 "limits" or "protects against" over-current.
- **Back-EMF and SMPS.** Braking or direction changes make brushed DC motors generate back-EMF; with a switching power supply this "can cause voltage rails to overshoot, potentially damaging the driver or tripping the SMPS protection circuits." Use a battery where possible; if an SMPS must be used, "large electrolytic bulk capacitors or external TVS/clamping diodes must be added to the power rail." [DS]
- PWM Low = **brake** (both outputs Low), not coast [DS]. Stopping code should drive PWM Low.
- External PWM: DC to 20 kHz; the output runs at the input frequency [DS]. In POT/SWITCH mode the driver generates its own 9–11 kHz PWM [DS].
- Logic thresholds: Low 0–0.5 V, High 3–30 V [DS]. 3.3 V and 5 V microcontroller outputs and 24 V PLC outputs fall inside the High range. Voltages between 0.5 V and 3 V are undefined; do not describe the input as "0–30V logic".
- Share ground: Figure 2 wires the controller's GND to the PWM/DIR connector GND [DS]. No isolation is stated.
- "Forward"/"Reverse" are output states (MA High or MB High); actual shaft direction depends on how the motor is wired to MA/MB [DS truth table].
- Control signals use **JST PH** connectors, not screw terminals [DS] (see *Conflicts*).
- Supply must stay within 7–30 V [DS]; protection against reverse polarity or over-voltage is not stated, so tutorials must warn readers to check polarity before power-up.

## Power and electrical limits
- Motor current: 16 A continuous, 30 A peak for less than 10 seconds [DS].
- Heat: the enclosure is the heatsink; the PCB transfers heat to the chassis; no fan [PP]. Over-current causes overheating and possible damage [DS].
- Logic inputs tolerate up to 30 V (High level max) [DS].
- No over-current, thermal, reverse-polarity or under-voltage protection is stated in the datasheet [DS].

## Software support
- No firmware, no configuration and no library needed: POT/SWITCH mode is standalone [DS]; PWM/DIR mode takes a plain PWM signal plus a digital DIR level from any microcontroller or PLC [DS].
- Cytron's Arduino "Cytron Motor Drivers Library" (CytronMotorDriver) has a PWM_DIR example, but the iMD16 is **not** in its compatible-driver list as of 2026-10-16 [GH].

## Compatibility and accessories
- Controllers named by Cytron: PLCs, microcontrollers ("like Arduino or Raspberry Pi"), industrial motion controllers [PP]; "direct connection to 24V PLC outputs without the need for additional level shifters" [PP], consistent with the 3–30 V High level [DS].
- Motors: brushed DC motors [DS].

## Common mistakes / troubleshooting
- Claiming over-current or thermal protection — the datasheet states there is no current limiting and states no thermal protection [DS].
- Using a bench SMPS without bulk capacitance or TVS clamping — back-EMF can overshoot the rail and damage the driver or trip the supply [DS].
- Expecting the motor to coast when PWM goes Low — it brakes [DS].
- Wrong rotation direction — swap the motor wires on MA/MB or invert DIR [DS truth table].
- Running external PWM above 20 kHz — outside the datasheet range [DS].
- A 3.3 V signal through long cables or a series drop below 3 V is no longer a valid High [DS thresholds].
- Power LED off: no supply voltage present [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Direction Switch description | [DS] (2026-10-05): "3-pin JST PH connector for a 3-way rocker switch for motor direction control (Forward, Stop, and Reverse)" | [DS-old] (2026-06-04): "3-pin JST PH connector for a 3-way switch. Selects motor rotation direction" | [DS] newer text used. Both labelled Rev 1.0 April 2026; revision number was not bumped |
| SMPS / back-EMF caution | [DS] (2026-10-05): caution + recommendation present in section 2 | [DS-old] (2026-06-04): caution absent | [DS] newer text used |
| Control-signal connectors | [DS]: pot, switch and PWM/DIR are 3-pin JST PH connectors; [PP] packing list ships a JST PH connector for PWM/DIR | [PP] live page (read 2026-10-19): "All critical connections are extended to panel-mount screw terminals" incl. PWM/DIR/GND, switch and pot | [DS] wins: JST PH for control, screw terminals for power and motor only. Ask Cytron to correct the page |
| SMPS mitigation | [DS]: battery where possible; else large electrolytic bulk capacitors or external TVS/clamping diodes | [PP] live page: "connect it parallelly with the same voltage battery" | [DS] wins (fuller guidance); the page advice is one of the options |
| Overall height | [DS] Figure 4: 16.60 and 5.00 height dimensions, no overall height | [3P] Switch Science: 102.0 × 52.2 × 24.0 mm (max incl. flange) | [DS] values only; 24.0 mm H goes to *Needs verification* |

## Needs verification
- Overall height (24.0 mm per Switch Science [3P]); datasheet gives 16.60 and 5.00 only.
- Thermal shutdown, reverse polarity, under-voltage or short-circuit protection: none stated anywhere [DS][PP].
- IP rating and whether the enclosure is sealed: Switch Science says "sealed metal enclosure" [3P]; Cytron sources say only "protects against dust, debris, and accidental contact" [PP].
- Operating temperature: a client-commissioned lab test (SHATBL2606017H02) passed −20 °C (16 h) and 70 °C (16 h) at 24 V DC and 80 % RH at 40 °C (48 h) . This is a test result, not a rated range; [DT] needed before quoting a range.
- Mode priority: what happens if the potentiometer/switch and the PWM/DIR connector are both connected, and the driver state when PWM/DIR is left floating. Not stated [DS].
- Which SPEED POT pin (P1/P2/P3) is the wiper, and which DIR SWITCH position gives Forward.
- Which motor status LED (MA/MB) lights in which direction, and whether they show speed.
- PLC sinking (NPN) output compatibility; minimum PWM pulse width; input impedance.
- Whether CytronMotorDriver's PWM_DIR example is officially supported for iMD16 [GH].
- Unit weight.
- The Quick Start Guide card text (not online).
- Read the two Cytron iMD16 tutorials (getting started; conveyor belt without code) for wiring of the control connectors.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Getting Started with iMD16 (No Code Setup)](https://my.cytron.io/tutorial/getting-started-with-imd16) — Tutorial, Beginner, 2026 (series, 2 parts) [PP: tutorial]
- [Conveyor Belt Control without Code using iMD16](https://my.cytron.io/tutorial/imd16-conveyor-belt-control-without-code) — Tutorial, 2026 [PP: tutorial]
- [Cytron Brings its First Industrial DC Motor Driver to the Global Stage](https://my.cytron.io/tutorial/cytron-launches-imd16-industrial-dc-motor-driver) — Uncategorized, 2026 [PP: tutorial]

## Sources
- [DS] iMD16 Datasheet, Rev 1.0 April 2026, Google Doc modified 2026-10-05 (PDF export read incl. Figures 1–4): (Cytron document — link not public)
- [DS-old] iMD16 Datasheet, Rev 1.0 April 2026, Google Doc modified 2026-06-04: (Cytron document — link not public)
- [DS] IMD16 Dimension.PNG (same drawing as Figure 4): (Cytron document — link not public)
- [GH] CytronMotorDriver README: https://github.com/CytronTechnologies/CytronMotorDriver
- [3P] Switch Science listing (cross-check only): https://www.switch-science.com/products/11193
- Product page: https://cytron.io/p-16amp-7-30v-industrial-dc-motor-driver (not read: blocked)
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
