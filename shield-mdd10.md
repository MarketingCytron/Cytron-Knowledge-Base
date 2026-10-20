# 10Amp 7V-30V DC Motor Driver Shield for Arduino (2 Channels) — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-MDD10` (datasheet title [DS]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 3): live my.cytron.io product page read (description, features, packing list, resources). Page agrees with the datasheet and adds stepper use, packing and warranty; the PWM/DIR jumper options are figure-only, so it stays Medium |
| Primary source | "SHIELD-MDD10 Datasheet" — **Rev 1.0, May 2019** — public Google Doc: https://docs.google.com/document/d/1QHlQbs6f5fY_BMBs3hJRg1QLFe4yqy4nyH3mBavZ2-0 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] read in full as text from the Google Doc (figures 1–5 are images and were not readable: board-layout labels, pin-selector options, dimension drawing, current-limit-vs-temperature graph). A PDF mirror on cdn.robotshop.com (same title, "Rev 1.0", "May 2019") matches. No newer revision found on Drive. [PP] = my.cytron.io product page as read by the coordinator on 2026-10-16 (name, code, stock only). [3P] = Cytron's own Tindie listing (cross-check only). No [DT] confirmation yet.

## What it is
An Arduino-shield-form-factor driver for two brushed DC motors, 10 A continuous per channel, powered from a 7–30 V battery [DS]. Each channel is controlled by a PWM input (speed) and a DIR input (direction), routed to Arduino pins through a jumper-style "PWM/DIR Input Pin Selector" [DS]. It has active current limiting, temperature-dependent current limit, undervoltage shutdown, and a built-in 5 V buck regulator that powers the Arduino by default [DS].

## Specifications
Datasheet section 2, *Table 3: SHIELD-MDD10 Absolute Maximum Ratings* [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 7 V, Max 30 V | [DS] |
| Maximum motor current, continuous (per channel) | Max 10 A | [DS] |
| Maximum motor current, peak (per channel) | Max 30 A — footnote *¹: "Peak current is limited by the overcurrent protection circuit. Actual current limit is depending on board temperature. Value shown is at room temperature (25 - 30 degree Celsius)." **No peak duration is stated.** | [DS] |
| Logic input voltage (PWM & DIR), low level | Min 0 V, Max 0.8 V | [DS] |
| Logic input voltage (PWM & DIR), high level | Min 1.5 V, Max 5.5 V | [DS] |
| PWM frequency, standard | DC to 20 kHz — "Output frequency is same as input frequency" | [DS] |
| PWM frequency, extended | 20 to 40 kHz — footnote *²: "When the PWM operates in extended frequency range, continuous motor current will be reduced." (amount not stated) | [DS] |
| DC +5V output maximum current | Max 500 mA | [DS] |
| Number of channels | 2 (Motor 1, Motor 2; terminals MxA/MxB) | [DS] |
| Motor type | Brushed DC (product name "DC Motor Driver") | [DS][PP] |
| Control mode | PWM + DIR per channel (truth table, Table 4). Locked-antiphase operation is **not stated** in the datasheet. RC, analog, serial: not stated (none) | [DS] |
| Logic supply | No separate logic supply input; built-in 5 V buck regulator from VB+ | [DS] |
| Protections | Overcurrent protection with active current limiting; temperature protection (current-limit threshold falls as board temperature rises); undervoltage shutdown | [DS] |
| Reverse polarity protection | **None** — "Connecting in reverse polarity will damage the motor driver instantaneously." | [DS] |
| Undervoltage shutdown threshold | Not stated ("drops below the lower limit") | [DS] |
| Test buttons | Yes, MA (forward*) and MB (backward*) — "Motor will run at full speed." | [DS] |
| LEDs | Power LED; motor status LEDs MA/MB; Error (ERR) LED; OC (overcurrent) LED | [DS] |
| Arduino reset button | Yes | [DS] |
| Dimensions | Drawing only (Figure 3); no numbers readable in text | [DS] |
| Operating temperature | Not stated | — |
| Wire size / terminal rating | Not stated | — |
| Warranty | Not stated in [DS] | — |

\* "Actual motor direction is depending on the motor connection. Swapping the connection (MA & MB) will reverse the direction." [DS]
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** 2-channel shield for two brushed DC motors **or one bipolar/unipolar stepper motor**, 7–30 V; discrete NMOS H-bridge, 10 A per channel continuous without heatsink; test buttons and motor LEDs; 5 V buck regulator to power the Arduino; PWM/DIR Arduino pins selectable by jumper; overcurrent protection with current limiting; temperature-dependent current limit; "Power input does not have reverse-voltage protection" [PP].
- **Features list:** Arduino shield form factor; 7–30 V; 10 A continuous, 30 A peak; **5 V buck output 500 mA max**; test buttons; motor LEDs; selectable PWM/DIR pins; PWM/DIR inputs compatible with 1.8 V, 3.3 V and 5 V logic; PWM up to 20 kHz (output = input frequency); overcurrent protection with active current limiting; temperature protection; undervoltage shutdown [PP].
- **Packing list:** 1x SHIELD-MDD10 [PP].
- **Resources:** datasheet (Google Doc), CytronMotorDriver sample code, 3D CAD [PP]. Interface/truth-table and dimension images on the page — not read.

## Interfaces, terminals and pin mapping
Board functions, top (Table 1) [DS]:
- **Power Input Terminal** — "Connect to battery." VB+ = positive, VB- = negative.
- **Motor Output Terminal** — connect to motor; "Motor direction is depending on the polarity."
- **Power LED** — on at power-up.
- **Motor Status LEDs** — on when the motor is running: MA = forward*, MB = backward*.
- **OC (Overcurrent) LED** — "Turn on when current limiting is in action. Current limit threshold is depending on the board temperature."
- **Arduino Reset Button** — resets the Arduino.
- **Test Buttons** — MA forward*, MB backward*, full speed.
- **PWM/DIR Input Pin Selector** — "Select the Arduino pin for PWM & DIR signal." DIR = direction input, PWM = PWM input for speed. **Which Arduino pins can be chosen, and the defaults, are only in Figure 1 (image) — not stated in text.**
- **Arduino Female Header** — "Connect to other shield." (stackable)

Board functions, bottom (Table 2) [DS]:
- **5V Output Solder Jumper** — "SHIELD-MDD10 has a built-in 5V buck regulator to power the Arduino by default. If you want to power the Arduino from the other source, cut the track to disconnect the regulator from the Arduino 5V pin."
- **Arduino Male Header** — connect to Arduino or on top of other shield.

PWM/DIR truth table (Table 4), per channel x [DS]:

| PWMx | DIRx | Output A (MxA) | Output B (MxB) | Motor x |
|---|---|---|---|---|
| Low | X (don't care) | Low | Low | Brake |
| High | Low | High | Low | Forward* |
| High | High | Low | High | Backward* |

## Rules and gotchas (for code, wiring and tutorials)
- **Polarity:** no reverse-polarity protection; reversed battery "will damage the motor driver instantaneously" [DS].
- **The shield powers the Arduino** through the Arduino 5 V pin by default (buck regulator, 500 mA max) [DS]. To power the Arduino from another source, cut the 5V Output solder-jumper track [DS]. Do not budget more than 500 mA for the Arduino plus anything else on 5 V [DS].
- **Peak 30 A has no time rating** — it is the current-limit level at 25–30 °C, and it drops as the board heats [DS]. Do not copy the "30 A peak (10 seconds)" wording from MDD10A/HAT-MDD10.
- PWM LOW = brake (both outputs low), regardless of DIR [DS].
- Above 20 kHz PWM, continuous current is reduced (by how much: not stated) [DS].
- Logic high threshold is 1.5 V min, 5.5 V max [DS] — works with 3.3 V and 5 V boards; never feed 12 V/24 V logic.
- Check the jumper positions on the PWM/DIR Input Pin Selector before writing pin numbers in code; the selectable pins are not in the datasheet text (see *Needs verification*).
- Direction words are nominal; swap MA/MB to reverse [DS].

## Power and electrical limits
- Supply 7–30 V on VB+/VB- [DS]. The datasheet says "Connect to battery." [DS]
- 10 A continuous per channel; 30 A peak per channel = current limit at 25–30 °C [DS].
- Current limiting chops the PWM and holds current at the limit; "This prevents the motor driver from damage when the motor stalls or an oversized motor is hooked up." OC LED shows when active [DS].
- Temperature protection: "The higher the board temperature, the lower the current limiting threshold." (graph values not readable) [DS].
- Undervoltage shutdown: output shuts down when input drops below the lower limit, "to make sure the MOSFETs have sufficient voltage to fully turn on and do not overheat"; ERR LED on [DS].
- Battery vs switching power supply / regenerative current: **not stated** in [DS].
- Heatsink: not stated in [DS] ([3P] Tindie: "10 Amp per channel continuously without any additional heatsink").

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, v1.0.1, Library Manager name "Cytron Motor Drivers Library"); SHIELD-MDD10 is listed under the **PWM_DIR_DUAL** example [GH].
  - `CytronMD motor1(PWM_DIR, pwmPin, dirPin); CytronMD motor2(PWM_DIR, pwmPin, dirPin);` then `setSpeed(-255..255)` [GH]. The example uses D3/D4 and D9/D10 — match these to the shield's jumper positions [GH].
- MicroPython / CircuitPython / other: not stated.

## Compatibility and accessories
- Arduino shield form factor with male (bottom) and female (top, stackable) headers [DS].
- Logic levels: 1.5–5.5 V high [DS] → 3.3 V and 5 V Arduino-format boards; specific board list not stated in [DS].
- 3D CAD file linked from the product page [PP]: https://drive.google.com/file/d/18IeHeClKaeR9m6IYLeJMBFOqRB_HbYEg
- Packing list: not stated in [DS].

## Common mistakes / troubleshooting
- Board dead after first power-up → battery connected reversed; no protection [DS].
- Motor slows / OC LED on → active current limiting (stall, oversized motor, or hot board lowering the limit) [DS].
- Arduino and a second 5 V source fighting → the shield already feeds Arduino 5 V; cut the 5V Output solder jumper [DS].
- Motor runs with no code → test buttons drive full speed; check LEDs MA/MB [DS].
- Code runs but motor does not → PWM/DIR pin numbers in code do not match the selector jumpers.

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Logic compatibility wording | [DS]: high level 1.5–5.5 V | [3P] Tindie: "compatible with 1.8V, 3.3V and 5V logic" | Consistent; [DS] numbers used |
| Peak current | [DS]: 30 A, limited by OC circuit, no duration | [3P] Tindie: "10A continuous, 30A peak" | Same value; [DS] context used |

[PP] (read 2026-10-19) agrees with [DS]: 7–30 V, 10 A / 30 A, 1.8/3.3/5 V logic, 20 kHz, current limiting, temperature protection, undervoltage shutdown, no reverse-voltage protection. The Tindie [3P] lines above repeat the Cytron product page text.

## Needs verification
1. **PWM/DIR Input Pin Selector options and defaults** for PWM1, DIR1, PWM2, DIR2 — only in Figure 1 (image). [3P] Tindie says "configurable via jumpers"; no pin list in text.
2. Board dimensions and mounting holes (Figure 3 image only).
3. Current limit vs temperature values (Figure 5 image only) and the undervoltage threshold.
4. Locked-antiphase support — not stated in [DS] (sibling MDD10A/HAT-MDD10 support it).
5. Battery vs SMPS / regenerative current guidance — not stated in [DS].
6. Operating temperature range and terminal wire size — not stated.
7. How to drive a stepper with the two channels (wiring, library) — the page says it can; no Cytron example read.

## Sources
- [DS] SHIELD-MDD10 Datasheet, Rev 1.0, May 2019 (Google Doc): https://docs.google.com/document/d/1QHlQbs6f5fY_BMBs3hJRg1QLFe4yqy4nyH3mBavZ2-0
- PDF mirror of the same datasheet (cross-check): https://cdn.robotshop.com/media/c/cyt/rb-cyt-273/pdf/cytron-10a-7-30v-dual-channel-dc-motor-driver-shield-datasheet.pdf
- [PP] Product page: https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino-2-channels
- [PP] 3D CAD (Drive): https://drive.google.com/file/d/18IeHeClKaeR9m6IYLeJMBFOqRB_HbYEg
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- [3P] Cytron Tindie listing (cross-check only): https://www.tindie.com/products/cytron/10amp-dual-dc-motor-driver-shield-for-arduino
