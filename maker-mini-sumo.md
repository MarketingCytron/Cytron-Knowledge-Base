# Maker Mini Sumo — Verified Reference

| | |
|---|---|
| Product code | `MAKER-MSUMO` (shown as "Code: MAKER-MSUMO" on the product page [PP]; datasheet title [DS]; library README [GH]) |
| Family | Cytron sumo robot controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Page matches the KB; the Arduino board to select is still not stated |
| Primary source | MAKER-MSUMO Datasheet **Rev 1.0, November 2019** (Google Doc linked from the product page): https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit |

**Authority rule:** Datasheet [DS] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > chip vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] also covers Cytron tutorials on my.cytron.io/tutorial and Cytron's own "Ikedo Mini Sumo Robot Pro" setup guide on Hackster (linked as "Software Setting Up" from the Ikedo V2 product page). No [DT] confirmation exists for this product yet.

## What it is
A mini sumo robot controller built on the ATmega328P, "Arduino Nano/Uno Compatible", with a 2-channel motor driver (3 A continuous / 6 A peak per channel), screw-terminal and header ports for 5 opponent sensors, 2 edge sensors, a start module, 2 GPIO ports and an RC servo, plus onboard start button, user LED, potentiometer, 3-way mode DIP switch and piezo buzzer [DS][PP]. Programmed from the Arduino IDE with the **Cytron Maker Sumo Library** [PP][GH]. Positioned for beginners through professional builders, and sized for the 500g mini sumo category [PP]. It is the controller inside the Ikedo Mini Sumo Robot V2 kit [PP].
Positioning (marketing, not spec): page title "Maker Mini Sumo Controller: Simplifying Sumo Robot for Beginner"; pitched as "the ultimate board" for beginners and "professional robot builder[s]"; designed with Team Ikedo Kogeki, "the winner of multiple Sumo robot competitions locally and internationally" [PP].

## Board facts
| Item | Value | Src |
|---|---|---|
| MCU | ATmega328P ("Arduino Nano/Uno Compatible (Powered by ATMEGA328P)") | [DS][PP] |
| Programming | Arduino IDE, via USB Micro-B (upload + Serial Monitor) | [DS][PP] |
| USB-serial driver | Cytron's Ikedo Pro setup guide installs the WCH **CH341SER** driver and refers to the "CH340" COM port (chip itself not named in the datasheet) | [PP: Hackster guide] |
| Power input (Vin) | 7.0 – 18.0 VDC (absolute maximum ratings table) | [DS] |
| Battery connection | "Battery Terminal": VB+ (positive), VB- (negative/ground) | [DS] |
| Reverse polarity protection | Yes, on Vin. PP: "If you ever connect the battery in the wrong way, just change the polarity to the correct one and it will work again." | [DS][PP] |
| Connections | Screw terminals for sensors and motors ("Solderless Connection") | [PP] |
| Power switch | On/off slide switch with MOSFET latching circuit ("vibration proof" [DS] / "shockproof" [PP]); once on, a lost contact does not turn the board off | [DS][PP] |
| +5V supply | Switching regulator | [DS] |
| +5V output current | 500 mA max **total** | [DS] |
| Motor driver | 2 channels. PP: "discrete MOSFETs H-Bridge design" | [DS][PP] |
| Motor current per channel | **3.0 A continuous, 6.0 A peak (< 5 seconds)** | [DS] |
| Motor PWM frequency | DC to 20 kHz | [DS] |
| Digital input levels | Low 0 – 0.5 V, High 1.7 – 5.0 V | [DS] |
| Analog input range | 0 – 5.0 V | [DS] |
| Over-current / thermal / short-circuit protection | **Not stated** in datasheet or product page — do not claim it | [DS][PP] |
| Dimensions | 92 mm × 36 mm (datasheet gives a drawing, Figure 3, with no values in the text) | [PP] |
| Operating temperature | Not stated | [DS] |
| In the box | 1 × Maker Mini Sumo Controller (no USB cable listed) | [PP] |
| Warranty | "Generally, it has a 12-month warranty" with exclusions (see Power) | [PP] |
| Resources | Datasheet, 3D CAD (Google Drive folder), Arduino Library and Examples (GitHub) | [PP] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- Page re-read: warranty note (12 months generally; not covered: modifications, motors over 3 A, competition use, misuse); ATmega328P, "100% compatible with Arduino Uno/Nano"; motor driver 3 A continuous, 6 A peak, 7–18 V, "discrete MOSFETs H-Bridge design"; reverse polarity protection on Vin; shock-proof on/off switch with MOSFET latching; battery voltage readable in code; switching 5 V regulator; test buttons and motor LEDs; 5 opponent inputs, 2 edge inputs, 2 GPIO, start-module input with start button, servo output, programmable LED, potentiometer, 3-way DIP switch, piezo buzzer; RC mode via the GPIO ports; packing 1x controller; resources datasheet, 3D CAD, CytronMakerSumo library [PP].

## Onboard peripherals and pins
All pins are predefined in the library header `CytronMakerSumo.h`; names below are the library constants [DS][GH].

| Function | Pin | Notes | Src |
|---|---|---|---|
| Left motor PWM / DIR | D3 (`PWM_L`) / D4 (`DIR_L`) | Terminals MLA / MLB | [DS][GH] |
| Right motor PWM / DIR | D11 (`PWM_R`) / D10 (`DIR_R`) | Terminals MRA / MRB | [DS][GH] |
| Opponent sensor Left / Right | D12 (`OPP_L`) / D13 (`OPP_R`) | Digital, internally pulled up to +5V, **active low**; status LED per port | [DS][GH] |
| Opponent sensor Front-Center / Front-Left / Front-Right | D6 (`OPP_FC`) / D5 (`OPP_FL`) / D7 (`OPP_FR`) | Same as above. MAKER-OBJECT ports on the bottom layer are wired in parallel | [DS][GH] |
| Edge sensor Left / Right | A0 (`EDGE_L`) / A1 (`EDGE_R`) | Ports S (analog), + (+5V), - (GND) | [DS][GH] |
| Start button / Start module port | D2 (`START`) | Port in parallel with onboard start button; pulled high to +5V; Start LED on when pressed/low (active low). For external start button or IR start module | [DS][GH] |
| GPIO1 / GPIO2 ports | A2 (`GPIO1`) / A3 (`GPIO2`) | Digital in/out or analog in; ports S, +5V, GND. Used for RC receiver channels | [DS][GH][PP] |
| RC servo port | D9 (`SERVO`) | S, +5V, GND. `MakerSumo.begin()` attaches the Servo library to D9 | [DS][GH] |
| User LED | A4 (`LED`) | Programmable | [DS][GH] |
| Piezo buzzer | D8 (`BUZZER`) | On bottom layer; plays tones/melody | [DS][GH] |
| Potentiometer | A5 (`POT`) | For tuning speed, thresholds, etc. | [DS][GH] |
| Mode DIP switch (3-way) | A6 (`MODE`) | Read as one analog value; `readDipSwitch()` returns 0–7 (SW1 = MSB, SW3 = LSB; 0 = OFF, 1 = ON) | [DS][GH] |
| Battery voltage sense | A7 (`VBATT`) | VB+ through a voltage divider; `readBatteryVoltage()` returns volts | [DS][GH] |
| Motor test buttons + motor status LEDs | Hardware only (no pin) | MLA/MRA = forward*, MLB/MRB = backward*; test buttons run the motor at **full speed** without code | [DS] |
| Reset button, Power LED, Tx/Rx LEDs | — | | [DS] |

*Motor truth table [DS]: PWM Low → Brake (MxA Low, MxB Low). PWM High + DIR Low → Forward* (MxA High). PWM High + DIR High → Backward* (MxB High). *Actual direction depends on wiring; swapping MxA and MxB reverses it.

## Pin rules and gotchas (for code and tutorials)
- **Always call `MakerSumo.begin();`** before other library calls — it sets pin modes, clears outputs and attaches the servo [GH].
- **Never use `tone()` for the buzzer.** On the ATmega328P, `tone()` interferes with PWM on pins 3 and 11 [VEN] — which are both motor PWM pins (D3, D11) [DS]. Use `MakerSumo.playMelody()` / `MakerSumo.playTone()`, which bit-bang the buzzer [GH].
- The library always uses the Servo library; on non-Mega boards that disables `analogWrite()` on pins 9 and 10 [VEN]. D9 is the servo and D10 is only a direction pin, so motors are unaffected — but do not move motor PWM to D9/D10 [DS][GH][VEN].
- Opponent sensors and the start input are **active low**: `LOW` = detected / pressed [DS][GH].
- Edge detection in the library: `isEdgeDetected()` is true when `analogRead()` is **below** the threshold (white edge reads lower). Default threshold 800 if uncalibrated; AutoSumo uses fixed 720 (L) / 638 (R) [GH].
- Edge calibration is stored in **EEPROM from address 0** (`EEADD_EDGE_L` = 0, `EEADD_EDGE_R` = 0 + sizeof(int)). User code writing EEPROM there will overwrite calibration [GH].
- Almost every pin is already used. Spare expansion = GPIO1 (A2) and GPIO2 (A3); D0/D1 carry USB serial [DS][VEN].
- I²C (A4/A5 on ATmega328P [VEN]) is occupied by the user LED and potentiometer, and SPI pins D11/D12/D13 [VEN] are PWM_R / OPP_L / OPP_R [DS] — don't plan I²C or SPI add-ons without re-pinning.
- A6 (MODE) and A7 (VBATT) are analog-only inputs on the ATmega328P [VEN]; read them with `analogRead()` or the library functions.
- Motor direction is wiring-dependent — verify with the onboard motor test buttons and swap MxA/MxB rather than changing code [DS][PP: Hackster].
- `moveForward()` sets both DIR pins LOW; README defines forward as left motor counter-clockwise and right motor clockwise [GH].
- `readBatteryVoltage()` = ADC × 5.0/1023 × (1 + 10/3.9) [GH]. (Derived: full ADC scale ≈ 17.8 V.)

## Power and electrical limits
- Vin **7.0–18.0 VDC**; reverse polarity protection on Vin only [DS].
- Motor current **3.0 A continuous, 6.0 A peak for < 5 s, per channel** [DS].
- +5V output **500 mA total**, shared by all sensor, GPIO, start and servo ports [DS].
- Over-current, thermal or short-circuit protection: **not stated** [DS][PP]. Treat the driver as unprotected in tutorials.
- Product page warranty exclusion (verbatim intent): "Using a higher spec motor of more than 3A (the board can run 3A continuously, 6A peak for motors) - will cause the motor driver chip to burn" — not covered. Also not covered: board modifications, use in competition ("intense usage"), misuse [PP].
- Motor test buttons drive the motor at full speed [DS].

## Software support
- **Arduino IDE.** Library: **Cytron Maker Sumo Library** (library.properties `name=Cytron Maker Sumo Library`, version 1.2.3, `architectures=avr`, `depends=Servo`) [GH].
- Install: `Sketch` → `Include Library` → `Manage Libraries...` → search `Cytron Maker Sumo Library` → Install → restart IDE [GH]. (Cytron's Hackster guide uses `Tools > Manage Libraries...` and searches "maker sumo" [PP: Hackster].)
- Include `#include "CytronMakerSumo.h"`; static instance `MakerSumo` [GH].
- Functions: `begin, readDipSwitch, readBatteryVoltage, stop, moveForward, moveBackward, turnLeft, turnRight, setMotorSpeed(MOTOR_L|MOTOR_R, -255..255), setServoPosition(0..180), playTone, playMelody, calibrateEdgeSensors, readEdgeSensorThreshold, isEdgeDetected` [GH].
- Official examples (`File > Examples > Cytron Maker Sumo Library`): `AutoSumo`, `CalibrateEdgeSensors`, `RcSumo`, `TestInputs`, `TestOutputs` [GH]. Serial examples use 115200 baud [GH].
- `RcSumo`: 2-channel RC receiver, forward/reverse channel → GPIO1, left/right → GPIO2 [GH].
- Board to select in Tools > Board: **not stated by any Cytron source** — see Needs verification.
- MicroBlocks / CircuitPython / MakeCode / MicroPython: **not stated** for this board [DS][PP][GH].
- Repo: master branch, 21 commits, last commit 2020-07-15, tags 1.0.0 → 1.2.3, MIT licence [GH].

## Compatibility and accessories
- Sensors used in Cytron's own kit: Maker Object sensor (opponent, ×5) and Maker Reflect S / Maker Reflectance sensor (edge, ×2) [PP].
- Motors: Cytron states no recommended-motor list; only the 3 A continuous limit. The Ikedo V2 kit uses 2 × 600RPM 6V DC Micro Metal Gearmotor [PP].
- Battery in the Ikedo V2 kit: 7.4V 450mAh LiPo with a JST LiPo battery wire extension to the Battery Terminal (VB+ red, VB- black) [PP]. Hackster guide: 2-cell LiPo [PP: Hackster].
- RC: RC receiver on GPIO1/GPIO2, without using any sensor port, so the same robot can enter both RC and autonomous categories [PP]; Cytron tutorial tested Flysky and HotRC [PP tutorial].
- Bluetooth: Cytron tutorial "Maker Mini Sumo with Bluetooth Controller" uses an HC-05 or HC-06 (listing summary only; wiring not read) [PP].
- PS2: Cytron tutorial wires DATA→D2 (START), CMD→D7 (OPP_FR), ATT→D6 (OPP_FC), CLK→D5 (OPP_FL), with `ps2x.config_gamepad(5, 7, 6, 2, true, true)`, and says to remove all object sensors first [PP tutorial].
- Kits: **Ikedo Mini Sumo Robot V2** (`KIT-IKEDO-MSV2-S`) packing list includes "1 x Maker Mini Sumo Controller" [PP]. Cytron's "Ikedo Mini Sumo Robot Pro" guide is built on this controller [PP: Hackster].

## Common mistakes in older tutorials / migration notes
- **Using `tone()`** stops or upsets both motors (Timer2 / pins 3 and 11). Use the library's melody functions [VEN][GH].
- **Forgetting `MakerSumo.begin()`** leaves motor pins unconfigured — motors won't respond [GH].
- **README sample code calls bare `println(...)`** in the readDipSwitch, readBatteryVoltage, readEdgeSensorThreshold and isEdgeDetected snippets — this does not compile; use `Serial.println(...)` [GH].
- **PS2X default pins (13, 11, 10, 12)** clash with OPP_R, PWM_R, DIR_R, OPP_L — use (5, 7, 6, 2) as Cytron's tutorial does [PP tutorial][DS].
- **"Motor not spinning"** checks: battery within 7–18 V and polarity, power switch on, motor test buttons spin the motor (hardware OK), `begin()` called, no `tone()`, PWM low = brake [DS][GH].
- **Motors over 3 A continuous** burn the driver and void the warranty; the 6 A figure is a < 5 s peak, not a running rating [DS][PP].
- The library declares `architectures=avr` only, so the Arduino IDE flags it as incompatible if a non-AVR board is selected [GH][VEN].
- Don't describe the start port as "pulled down" or active high — it is pulled high, active low [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Motor driver construction | [PP] description: "discrete MOSFETs H-Bridge design" | [PP] warranty note: "will cause the motor driver chip to burn" | Unresolved; [DS] silent. Say "motor driver" only. Ask design team |
| Warranty | [PP] "Generally, it has a 12-month warranty" | [3P] robu.in: 3 months | [PP] wins for Cytron sales |
| Switch wording | [DS] "Vibration proof on/off switch" | [PP] "Shockproof on/off switch" | Same feature; either wording OK |
| Library Manager menu | [GH] Sketch > Include Library > Manage Libraries | [PP: Hackster] Tools > Manage Libraries | Both open the same Library Manager |
| Kit motor wiring |  Ikedo V2 guide: left MLA=red, MLB=black; right MRA=black, MRB=red | [PP: Hackster] Ikedo Pro: red→MRA, black→MRB, then check with test buttons | Kit-specific; rule = verify with test buttons, swap if reversed |
| Edge sensor name in V2 kit |  "Maker Reflectance Sensor" | [PP] Ikedo V2 page: "Maker Reflect S" from March 2026 | Use Maker Reflect S (product page note, read 2026-10-19) |

## Needs verification
- **Arduino board to select** (Arduino Uno vs Arduino Nano, and Nano "ATmega328P (Old Bootloader)" or not) — no Cytron source states it. Critical for upload-error troubleshooting. Ask design team.
- USB-serial chip (CH340 implied by Cytron's Hackster guide; not in datasheet).
- Over-current, thermal and short-circuit protection: present or absent? Not stated anywhere.
- Motor driver: discrete MOSFET H-bridge vs driver IC (see Conflicts).
- Board height 20 mm and shipping weight 0.06 kg — [3P] robu.in only. Board weight not stated.
- Mounting hole positions/sizes — only in datasheet Figure 3 / 3D CAD (not readable as text).
- Edge port silkscreen labels — Ikedo V2 guide tells users to wire edge sensors to the "Front Left and Front Right terminals".
- Recommended or maximum motor types beyond the 3 A rule.
- Ikedo Mini Sumo Robot Pro Bundle contents (product page not read).
- Library behaviour on Arduino IDE 2.x / current AVR core (last commit 2020) — untested here.

## Sources
- [DS] MAKER-MSUMO Datasheet Rev 1.0, Nov 2019 — https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit (same Rev 1.0 PDF mirrored at https://cdn.shopify.com/s/files/1/0176/3274/files/MAKER-MSUMO_Datasheet.pdf and https://cdn.robotshop.com/media/c/cyt/rb-cyt-276/pdf/ikedo-mini-sumo-robot-pro-kit-datasheet.pdf)
- [PP] https://my.cytron.io/p-maker-mini-sumo-controller-simplifying-sumo-robot-for-beginner · 3D CAD https://drive.google.com/drive/folders/1HrNAYGAMyBuPfVD5zGpPvkgv8Eog58x3
- [PP] Ikedo V2 kit page https://my.cytron.io/p-ikedo-mini-sumo-robot-v2-starter
- [PP tutorial] https://my.cytron.io/tutorial/rc-sumo-using-maker-mini-sumo-controller · https://my.cytron.io/tutorial/maker-mini-sumo-with-ps2-controller · https://my.cytron.io/tutorial/maker-mini-sumo-with-bluetooth-controller (not read)
- [PP: Hackster] Cytron "Ikedo Mini Sumo Robot Pro" (15 Jan 2020) — https://www.hackster.io/cytron-technologies/ikedo-mini-sumo-robot-pro-7da610
- [GH] https://github.com/CytronTechnologies/CytronMakerSumo (README, library.properties, CytronMakerSumo.h/.cpp, examples/)
- [VEN] Arduino `tone()` reference — https://github.com/arduino/reference-en/blob/master/Language/Functions/Advanced%20IO/tone.adoc · Servo library — https://github.com/arduino-libraries/Servo · ATmega328P — https://www.microchip.com/en-us/product/atmega328p
- [3P] (cross-check only) https://thepihut.com/collections/cytron/products/maker-mini-sumo-controller · https://www.robotshop.com/products/cytron-maker-mini-sumo-controller · https://stg.robu.in/product/maker-mini-sumo-controller-simplifying-sumo-robot-for-beginner
