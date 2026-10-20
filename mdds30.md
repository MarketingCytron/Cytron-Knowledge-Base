# SmartDriveDuo-30 (MDDS30) — Verified Reference

| | |
|---|---|
| Product code | `MDDS30` (cover page: "SmartDriveDuo-30", "MDDS30", "User's Manual") [UM] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read for the first time. Sale status, size, packing list, error-LED codes and the board revision history (Rev 1.2 vertical RC header, Rev 1.3 RC-jerk fix) are now Cytron-stated |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tags: [UM] = Rev 1.2 (Sep 2023). Older Cytron manuals checked for differences: [UM-1.0] Rev 1.0, April 2017 (RobotShop mirror) and [UM-1.11] Rev 1.11, July 2019 (DroneBot Workshop forum mirror). Rev 1.2 was read in full as text; figures (dimension drawings, board photo, DIP switch pictures, wiring diagrams) were not viewed. The older PDFs were read through WebFetch with targeted questions.

## What it is
A dual-channel brushed DC motor driver from Cytron's SmartDriveDuo series, "designed specially for controlling differential drive mobile robot using RC controller"; it can also be controlled by an analog joystick or a microcontroller (PWM, Serial) [UM]. It drives two brushed DC motors bi-directionally from one 7–35 V supply, with MOSFETs switched at 18 KHz and an on-board microcontroller for input modes and thermal protection [UM].

## Specifications
"Absolute Maximum Rating of SmartDriveDuo-30" table plus the Features list [UM].

| Item | Value | Src |
|---|---|---|
| Input Voltage (Motor Supply Voltage) | Min 7 V, Max 35 V | [UM] |
| IMAX (Max Continuous Motor Current) | Max 30 A. Footnote: "Depends on the room temperature." Features: "30A continuously, each channel" | [UM] |
| IPEAK (Peak Motor Current) | Max 80 A. Footnote: "Must not exceed 1 second." Features: "80A peak (1 second) ... each channel" | [UM] |
| VIOH (Logic Input – HIGH Level) | 1.3 V min – 5 V max | [UM] |
| VIOL (Logic Input – LOW Level) | 0 V min – 0.7 V max | [UM] |
| Input Dead-Band (RC, Analog & PWM Mode only) | ±10% (row present in Rev 1.2 only) | [UM] |
| Motor channels | 2 ("Bi-directional control for dual brushed DC motor") | [UM] |
| Switching frequency | 18 KHz ("for quiet operation") | [UM] |
| Input modes | RC, Analog/PWM (Analog and PWM selected separately), Serial Simplified, Serial Packetized; DIP switch selected | [UM] |
| Battery low voltage indicator / over voltage indicator | Yes / Yes | [UM] |
| Thermal protection | Yes (max current reduced with temperature, see Power section) | [UM] |
| Current limit protection | Yes (Features list); OC LED per channel "Light up if overcurrent happened" | [UM] |
| Test buttons | On-board push buttons per motor "for fast test and manual operation" | [UM] |
| Polarity protection | **None** ("NO POLARITY PROTECTION FOR V MOTOR") | [UM] |
| 5V output current | **Not stated** (no row in the table; no +5V pin listed) | [UM] |
| Dimension | Given only as drawings ("Dimension (unit in mm)": main board, height, bottom cover); numbers not readable in text | [UM] |
| Operating temperature | **Not stated** | [UM] |
| Warranty | 12 months, manufacturing defects only; misuse not covered; freight both ways not covered | [UM] |
| Packing list | 1 × SmartDriveDuo-30 (MDDS30); 2 × Grove 4 Pin Buckled 20cm Cable (WR-EX-GROVE); 2 × 2561 3 Ways Connector Extension Wire (WR-EX-2561-03) | [UM] |
| Optional external fan (not included) | 1 × DC5V Brushless Fan 40 x 40 x 20mm (FAN-05-040040020); 4 × PCB Stand (Screw & Screw) 30mm (SD-SS-30); 4 × Bolt M3 x 25mm (HD-PM-M3-25); 4 × M3 Nut (HD-PM-M3-NUT) | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Revision notes:** "Since Rev 1.2, the 2x3 header pins for RC input has been changed from horizontal to vertical"; "Latest revision is Rev 1.3 and it fixed a potential problem in RC mode. In some cases, motors might jerk when operating in RC mode" — contact Cytron support if seen [PP].
- **Description:** RC, PWM, analog (pot/joystick) or UART control, set by DIP switch; default configuration **RC, Mixed mode**; 2x3 RC header with 2 RC extension cables included; 7–35 V (two SLA in series, 3S or 6S LiPo); battery low-voltage warning [PP].
- **Features list:** dual brushed DC; 7–35 V; 80 A peak (1 s), 30 A continuous per channel; MOSFETs switched at 18 kHz; regenerative braking; error LEDs per channel — input error (2 blinks), undervoltage warning (3), overvoltage protection (4), over-temperature protection (5); thermal protection; current-limit protection; 3-pin fan connector; PWM/DIR sign-magnitude and locked-antiphase; serial simplified or packetized; Grove-compatible control connectors; push buttons; LEDs for error, RUN, over-current, motor output per channel; **NO polarity protection for V motor**; **81.28 (W) × 101.60 (L) × 42 (H) mm** [PP].
- **Suitable motors (page):** 2-terminal brushed DC, 7–35 V, rated ≤ 30 A, peak ≤ 80 A (e.g. SPG50, SPG30/SPG30E, IG45, IG42, IG32, DKM 40 W/120 W, 350/450 W scooter motors, power-window motors) [PP].
- **Packing list:** 1x MDDS30, 2x Grove 4-pin buckled 20 cm cable, 2x 2561 3-way extension wire [PP].
- **Resources:** User's Manual (Google Doc), CytronMotorDriver library, 3D CAD, introduction tutorial; examples with analog joystick, Arduino PWM, Pixhawk [PP].

## Interfaces, terminals and pin mapping
Board layout labels [UM]: A Motor RIGHT LED indicator; B Motor RIGHT terminal block; C Power Supply terminal block; D Motor LEFT terminal block; E Motor LEFT LED indicator; F Cooling fan connector; G Heat sink ("This area might be hot"); H Right channel LED indicator; I Left channel LED indicator; J Power LED indicator; K Motor LEFT test button; L Motor RIGHT test button; M RC input pin; N Analog/PWM input pin (Grove); O Digital/Serial input pin (Grove); P Mode selection DIP switch; Q Reset button.

| Pin / terminal | Function | Src |
|---|---|---|
| Power Supply terminal block (C) | "Connect to battery power source." Screw terminal or solder to bottom pad. NO POLARITY PROTECTION. "Please use wire with proper thickness to support the expected current." | [UM] |
| Motor LEFT / RIGHT terminal blocks (D / B) | Outputs MLA/MLB and MRA/MRB. Screw terminal or solder to bottom pad | [UM] |
| Grove N: AN1 / AN2 / NC | AN1 = Analog/PWM for motor LEFT; AN2 = Analog/PWM for motor RIGHT; NC = Not Connected | [UM] |
| Grove O: IN1 / IN2 / NC | IN1 = direction for motor LEFT, "or can be used for Serial mode" (UART receive); IN2 = direction for motor RIGHT; NC = Not Connected | [UM] |
| RC input pin (M): RC1 / RC2 | RC1 forward/reverse; RC2 steering | [UM] |
| Cooling fan connector (F) | Left to right: NC, +ve (5V), -ve. Fan "automatically ON when the board's temperature exceeds 50°C" | [UM] |
| Reset button (Q) | Restarts the system; use it to change mode without power cycling | [UM] |

Pin names on MDDS30 are **IN1/IN2** (MDDS10 and MDDS60 use DIG1/DIG2). No UART TX pin is described; the driver only receives [UM].

**LEDs** [UM]: per channel RUN (on while that motor runs; blinks on a signal error for that motor), ERR (blinks a code), OC (lights on over-current); motor direction LEDs (MLA/MRA lit = current from MLA→MLB / MRA→MRB); Power LED. At power-up RUN (Left), ERR (Left), RUN (Right), ERR (Right) run once. Error blink codes: 2 Input Error; 3 Under Voltage Warning; 4 Over Voltage Protection (>35 V, will not operate); 5 Over Temperature Protection. No code 6 (Shutdown) is listed for MDDS30.

**DIP switch (8 positions, SW1–SW8)** — from the detailed mode tables [UM]:
- Input mode SW1:SW2 — 00 RC; 01 Analog; 10 PWM; 11 + SW3=0 Serial Simplified; 11 + SW3=1 Serial Packetized.
- RC and Analog/PWM, SW3:SW4 — 00 Mixed; 01 Independent Right; 10 Independent Left; 11 Independent Both.
- SW5 Exponential — 0 linear (low to medium speed motor); 1 exponential, softens control around centre (high speed / very sensitive motor).
- SW6 in RC mode — Rev 1.00 board: **MCU mode** (0 = centre calibrated at power-up, stop after 100ms signal loss; 1 = centre fixed at 1.5ms, timeout disabled, keeps previous speed). Rev 1.10 board: **Full Range mode** replaces MCU mode (0 = max speed reached at about half throttle, e.g. 1.25ms/1.75ms, "the default mode in Rev1.00"; 1 = max speed at full throttle, 1ms/2ms).
- SW6 in Analog/PWM mode — 0 Locked Anti-Phase (stop at 2.5V; <2.5V one direction, >2.5V the other); 1 Signed Magnitude (AN1/AN2 speed, 0V stop, 5V full; IN1/IN2 direction). "SW2 must be set to 0 if Sign-Magnitude mode is turned on."
- Serial Simplified baud SW4–SW6: 000 1200, 001 2400, 010 4800, 011 9600, 100 19200, 101 38400, 110 57600, 111 115200.
- Serial Packetized address SW4–SW6: 000–111 = address 0–7.
- SW7:SW8 Battery Monitor (shown in the RC row of the summary table): 00 LiPo, 01 NiMH, 10 SLA, 11 Off.
- Mode is read at power-up only; change the DIP switch then press RESET or power cycle.

## Rules and gotchas (for code, wiring and tutorials)
- **Input must be "stop" at power-up/reset** in RC, Analog and PWM modes, else Input Error (2 blinks) [UM]. Stop = Analog: 0V (Sign-Magnitude) / 2.5V (Locked Anti-Phase); PWM: 0% duty (Sign-Magnitude) / 50% duty (Locked Anti-Phase) [UM].
- **RC transmitter must be ON before powering up** the MDDS30 [UM].
- **Do not use an external BEC/regulator for the RC receiver**; if one is required, disconnect the middle (red) wire of the cables between receiver and driver [UM].
- Mixed RC: "Do not enable the mixing in the RC Transmitter." RC1 = speed, RC2 = direction [UM].
- Analog range 0–5V; PWM accepts "TTL PWM from 1.3 to 5V for HIGH level". PWM mode low-pass filters the input with an on-board capacitor; Analog mode is unfiltered [UM]. **Maximum PWM input frequency is not stated** [UM].
- Analog/PWM Mixed: AN1 = speed, AN2 = direction. Independent: IN1 & AN1 = LEFT, IN2 & AN2 = RIGHT [UM].
- Serial Simplified (IN1 = UART receive; IN2, AN1, AN2 unused): one byte; bit 7 channel (0 LEFT, 1 RIGHT), bit 6 direction (0 CW, 1 CCW), bits 5–0 speed 0–63. Examples: 0/64 LEFT stop; 63 LEFT full CW; 127 LEFT full CCW; 128/192 RIGHT stop; 191 RIGHT full CW; 255 RIGHT full CCW [UM].
- Serial Packetized: 4 bytes — Header **0x55 (85)**; Channel & Address (bit 3 channel 0 LEFT/1 RIGHT, bits 2–0 address = DIP, bits 4–7 not used); Command 0–255 (0 full reverse, 127 stop, 255 full forward); Checksum = Header + Address + Command. Up to 8 units on one MCU UART Tx [UM].
- **Auto-baud on MDDS30 uses a dummy byte 128 (0x80)**, not the 85 header used by MDDS10/MDDS60. Send it once after power-up; baud cannot change without power cycle or reset. Wait **one second** after power (start-up up to 500ms). Autobaud range 4800–115200 bps. Error LED shows Input Error while waiting [UM].
- Mixed mode wiring: left terminal block to LEFT motor, right to RIGHT; reverse a motor's wires if it runs the wrong way [UM].
- Fan, if fitted, turns on only when the driver gets hot (>50°C) [UM].

## Power and electrical limits
- Supply 7–35 V; >35 V → driver will not operate (error 4) [UM].
- **No polarity protection** — "THERE IS NO POLARITY PROTECTION ON MDDS30, PLEASE DOUBLE CHECK THE CONNECTION BEFORE CONNECTING TO THE BATTERY." [UM]
- Recommended sources: 6–18 cells NiMH or NiCd; 3–6 cells LiPo or Li-Ion; 7–35 V sealed lead acid; 7–35 V power supply "MUST BE IN PARALLEL WITH A BATTERY WITH SAME VOLTAGE" [UM].
- **Regeneration:** with a supply that cannot sink current (bench-top, AC-to-DC switching supply), input voltage rises when the motor slows or is pushed by external force; connect a same-voltage battery in parallel, or the driver may be "destroyed permanently" or the supply may trip [UM].
- **Pushing the robot with no battery connected "might burn the motor driver"**: generated voltage has nowhere to go; damage counts as misuse and is not covered by warranty. Connect the battery, disconnect the motors, or carry the robot (recommended) [UM].
- Under voltage: cell count detected at power-up; with LiPo set, warns below 3.0V per cell; motor power is maintained (warning only). Other chemistries still show the warning; user judges when to replace [UM].
- Over temperature (error 5) — table "TEMPERATURE (°C) / MAX CURRENT (A)": <50 → 80; 50–70 → 50; 70–100 → 40; >100 → 30 [UM]. No shutdown temperature or restart temperature is stated for MDDS30 [UM].
- 30 A continuous depends on room temperature; 80 A peak must not exceed 1 second [UM].
- Heat sink area "might be hot"; optional 5V fan auto-on above 50°C. A fan is optional, not stated as required [UM].
- Logic supply: no separate logic input is described; the only power input is the Power Supply terminal block [UM].
- Wire size: "use wire with proper thickness to support the expected current"; no gauge stated. Fuse: not stated [UM].

## Software support
- Arduino library **Cytron_SmartDriveDuo** ("Cytron SmartDriveDuo Series", version=1.0.0, architectures=avr), "works with SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60"; linked from the UM [GH][UM]. Modes: RC_MCU (constructor commented out), PWM_INDEPENDENT, PWM_MIXED, SERIAL_SIMPLIFIED, SERIAL_PACKETIZED; `control(left, right)` −100…100 [GH].
- Examples (written for MDDS30): MDDSPWMTest (DIP 0b10110100; Uno pins 4→IN1, 5→AN1, 6→AN2, 7→IN2), MDDSSerialSimpleTest (DIP 0b11001100, 9600 bps, pin 4→IN1), MDDSSerialPacketTest (DIP 0b11100000, address 0; `initialByte(0x80); // MDDS30`, `//initialByte(0x55); // MDDS10 or MDDS60`) [GH].
- UM sample connections use CT UNO / Arduino Uno with Base Shield V2 (Grove) [UM].

## Compatibility and accessories
- Signal sources: RC transmitter/receiver, analog joystick, microcontroller (PWM, analog, UART) [UM].
- 3.3 V logic: VIOH 1.3–5 V includes 3.3 V, but the UM does not explicitly say "3.3V compatible" [UM].
- Grove connectors for control; 2 Grove cables and 2 × 2561 3-way extension wires included [UM].
- Optional fan kit (FAN-05-040040020 + SD-SS-30 stands + M3 hardware), assembled inside the bottom PCB; use the original short standoffs to mount the driver so the fan intake has clearance [UM].

## Common mistakes / troubleshooting
- ERR 2 blinks at power-up: input not at stop, RC transmitter off, or (Packetized) dummy byte not yet received [UM].
- Packetized mode not responding: sending 0x55 as the auto-baud byte (MDDS10/60 habit) instead of 0x80; sending before the 1 s start-up delay; baud outside 4800–115200 [UM].
- Mode change ignored: DIP read only at power-up — press RESET or power cycle [UM].
- Burnt driver after bench supply or pushing the robot: regenerative voltage rise [UM].
- OC LED on: over-current / current limit acting [UM]. Motor weaker when hot: max current reduced from 50°C [UM].
- RC behaviour differs between boards: SW6 is MCU mode on Rev1.00 and Full Range mode on Rev1.10 (revision sticker on board) [UM].
- Receiver with own BEC/regulator connected with red wire: not allowed [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Peak current duration | UM spec table: 80 A, "Must not exceed 1 second"; Features: "80A peak (1 second)" | UM Introduction: "80A peak (few seconds)" | Spec table wins: **80 A, ≤ 1 second** |
| Packet header value | UM: Header 0x55 (85) | Library `headerByte = 0x85` (133) [GH] | UM wins. Test library packetized code on hardware before publishing |
| Auto-baud byte | UM: dummy byte 128 (0x80) | (MDDS10/60 UMs use header 85) | MDDS30 = 0x80; library example agrees [GH] |
| RC SW6 function | UM-1.0: MCU mode | UM-1.11 / UM Rev 1.2: Full Range mode on Rev1.10 boards (Jan 2019), MCU mode on Rev1.00 | Depends on board revision; Rev 1.2 manual wins |
| Fan behaviour | UM-1.0: no on/off temperature given | UM: auto ON above 50°C | Rev 1.2 wins |
| Input dead-band | UM-1.0 / UM-1.11: no row | UM Rev 1.2: ±10% | Rev 1.2 wins (newer) |
| Input mode count | UM Rev 1.2 intro: "four different types" | Features list names RC, Analog/PWM, Serial Simplified, Serial Packetized; DIP has separate Analog and PWM | Same set; describe as RC, Analog, PWM, Serial Simplified, Serial Packetized |
| Right-motor direction in library | UM: 191 = RIGHT full CW | Library sends 0xC0\|speed (CCW bit) for positive right speed; PWM mode sets IN2 HIGH for positive right [GH] | UM defines bytes; library mirrors the right motor. Check direction on hardware |

## Needs verification
- Logic level: Switch Science [3P] says logic voltage "5 V or 3.3 V" and logic power from the motor supply; UM gives only VIOH 1.3–5 V.
- Over-current trip level and behaviour (current limit value, latch or auto-recover) not stated.
- Whether SW7–SW8 battery monitor applies in Analog/PWM/Serial modes (summary table shows it only on the RC row; the table also appears column-shifted in the text export).
- Fourth Grove pin on each connector: UM text lists only three entries (AN1/AN2/NC, IN1/IN2/NC).
- Maximum PWM input frequency, RC pulse range (beyond 1–2ms examples), operating temperature, fuse rating, terminal wire gauge.
- Shutdown temperature for MDDS30 (MDDS10/60 shut down >105°C; MDDS30 table ends at ">100 → 30 A").
- Rev 1.3 board changes (RC-mode jerk fix) are not in the Rev 1.2 manual (Sep 2023) — ask whether a newer manual exists.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Introducing 30A Dual Channel DC Motor Driver with Smart Features - SmartDriveDuo-30](https://my.cytron.io/tutorial/introducing-30a-dual-channel-dc-motor-driver-smart-features-smartdriveduo-30) — Protip, Beginner, 2026 [PP: tutorial]
- [Control MDDS30 In Serial Simplified Mode Using Raspberry Pi](https://my.cytron.io/tutorial/control-mdds30-in-serial-simplified-mode-using-raspberry-pi) — Project, Intermediate, 2019 [PP: tutorial]
- [Getting Started with Cytron Motor Driver](https://my.cytron.io/tutorial/getting-started-with-cytron-motor-driver) — Tutorial, Beginner, 2025 (series, 2 parts) [PP: tutorial]
- [Remote Raspberry Pi Using Maker pHAT](https://my.cytron.io/tutorial/control-mdds30-in-serial-simplified-mode-using-raspberry-pi-2) — Tutorial, Beginner, 2026 [PP: tutorial]

## Sources
- SmartDriveDuo-30 MDDS30 User's Manual Rev 1.2, Sept 2023 (public Google Doc) [UM]: https://docs.google.com/document/d/1OstW8T0kRIopWSuMEOyG2h9KNhQ3O4yowwjnp40Z23o/view
- SmartDriveDuo-30 User's Manual Rev 1.11, July 2019 (forum mirror) [UM-1.11]: https://forum.dronebotworkshop.com/wp-content/uploads/wpforo/attachments/5360/6077-MDDS30UserManual.pdf
- SmartDriveDuo-30 User's Manual Rev 1.0, April 2017 (RobotShop mirror) [UM-1.0]: https://cdn.robotshop.com/media/c/cyt/rb-cyt-220/pdf/smartdriveduo-smart-dual-channel-30a-motor-driver-datasheet.pdf
- Cytron_SmartDriveDuo Arduino library [GH]: https://github.com/CytronTechnologies/Cytron_SmartDriveDuo (src, library.properties, examples; last commit Jul 2023)
- Switch Science listing (cross-check only) [3P]: https://www.switch-science.com/products/3609
- Product page: not read (https://www.cytron.io/p-mdds30 linked from the UM packing list; blocked from this environment)
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
