# SmartDriveDuo-10 (MDDS10) — Verified Reference

| | |
|---|---|
| Product code | `MDDS10` (cover page: "SmartDriveDuo-10", "MDDS10", "User's Manual") [UM] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (features, packing list, resources). Dimensions, per-channel rating, regulator, reset button and power LED are now Cytron-stated |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Read note: the PDF could not be downloaded directly (proxy blocked cdn.robotshop.com for curl). Its text was read through WebFetch in four passes, with exact-quote checks on the spec table, DIP switch table, serial formats and cover page. Figures (board layout photo, wiring diagrams, dimension drawing) were not viewed.

## What it is
A dual-channel brushed DC motor driver, mainly for differential-drive robots controlled by an RC receiver; it can also be driven by a potentiometer/joystick (analog), PWM, or a microcontroller over UART (Simplified or Packetized Serial) [UM]. Bi-directional control of two brushed DC motors from a single 7–35 V supply, with a 16 kHz MOSFET switching frequency [UM].

## Specifications
Spec table ("Absolute Maximum Rating") from the User's Manual, plus the Features list.

| Item | Value | Src |
|---|---|---|
| Input voltage (motor supply voltage) | Min 7 V, Max 35 V | [UM] |
| IMAX (maximum continuous motor current) | Max 10 A. Footnote: "Depends on the room temperature." | [UM] |
| IPEAK (peak motor current) | Max 30 A. Footnote: "Must not exceed 1 second." | [UM] |
| VIOH (logic input, high level) | 1.3 V min – 5 V max | [UM] |
| VIOL (logic input, low level) | 0 V min – 0.7 V max | [UM] |
| 5V output current | Max 500 mA | [UM] |
| Dimension | 66.8 × 101.09 mm [PP]; the UM spec section has the heading with no value | [PP] |
| Motor channels | 2 (dual brushed DC; "Bi-directional control for dual brushed DC motor") | [UM] |
| Switching frequency | 16 KHz ("for quiet operation") | [UM] |
| Input modes | RC, Analog, PWM, Simplified Serial, Packetized Serial (DIP switch selected) | [UM] |
| Battery low voltage indicator | Yes (error LED, 3 blinks) | [UM] |
| Battery over voltage indicator | Yes (error LED, 4 blinks) | [UM] |
| Thermal protection | Yes: duty-cycle derating from 50 °C, shutdown above 105 °C | [UM] |
| Test buttons | On-board push buttons, one per motor, "for fast test and manual operation" | [UM] |
| Polarity protection | **None** ("No polarity protection for V motor") | [UM] |
| Over-current protection | **Not stated** in the manual | [UM] |
| Operating temperature | **Not stated** | [UM] |
| Warranty | 12 months, manufacturing defects only; misuse not covered; freight not covered | [UM] |
| Packing list | 1 × SmartDriveDuo-10, 6 × Terminal pin for 2510, 1 × 6-way Connector Housing | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Features (page): 7–35 VDC; single power; dual channel, independent or mixed; RC, analog, PWM, simplified and packetized UART; sign-magnitude and locked-antiphase PWM; 2 test buttons + 2 output LEDs per channel; Power, Error, RUN (L/R) LEDs; on-board **reset button** after changing DIP mode; full MOSFET (no external flyback diodes); regenerative braking; temperature feedback; **"up to 10A continuous each channel"** (description) at 25 °C; 30 A peak for 10 s; 16 kHz; **on-board switching voltage regulator**; battery low-voltage monitoring; **no polarity protection**; **66.8 × 101.09 mm** [PP].
- **Error LED blink codes (page):** 2 = input error; 3 = under-voltage; 4 = over-voltage (> 35 V, stops); 5 = over-temperature; 6 = shutdown (too hot, stops) [PP].
- **Packing:** 1x MDDS10, 1x 6-way connector housing, 6x terminal pins [PP].
- Resources: user's manual, 3D CAD, Fritzing, CytronMotorDriver library; tutorials — Simple Mobile Robot plug-and-play joystick + MDDS10; Arduino + PS2 shield + MDDS10; Improve MDDS10 performance with external fan; PWM from CT-UNO + MDDS10 [PP].

## Interfaces, terminals and pin mapping
Board layout labels [UM]: A Motor RIGHT LED indicator; B Motor RIGHT terminal block; C Power Supply terminal block; D Motor LEFT terminal block; E Motor LEFT LED indicator; F Mode selection DIP switch; G Motor LEFT test button; H Analog/PWM/Serial input pin; I RC input pin; J Motor RIGHT test button; K Motor RIGHT Run LED; L Error LED; M Motor LEFT Run LED.

| Pin / terminal | Function | Src |
|---|---|---|
| Power Supply terminal block | 7–35 V input. No +/− labels quoted in the text (VB+/VB− not used); no polarity protection | [UM] |
| Motor LEFT / Motor RIGHT terminal blocks | Outputs MLA/MLB and MRA/MRB. Motor wires can also be soldered to the bottom pad | [UM] |
| DIG1 | Direction for motor LEFT (sign-magnitude); **UART Rx** in Serial modes | [UM] |
| DIG2 | Direction for motor RIGHT (sign-magnitude) | [UM] |
| AN1 | Analog/PWM input for motor LEFT | [UM] |
| AN2 | Analog/PWM input for motor RIGHT | [UM] |
| +5V | 5 V output, max 500 mA. "Do not connect to another 5V source." | [UM] |
| GND | Ground | [UM] |
| RC1 | RC input: forward/reverse, or speed in Mixed mode | [UM] |
| RC2 | RC input: steering, or direction in Mixed mode | [UM] |

No UART TX pin is described; the driver only receives [UM]. UART logic level is not stated [UM].

**DIP switch (SW1–SW6)** [UM]:
- Input mode: SW1=0, SW2=0 RC; SW1=0, SW2=1 Analog; SW1=1, SW2=0 PWM; SW1=1, SW2=1, SW3=0 Simplified Serial; SW1=1, SW2=1, SW3=1 Packetized Serial.
- RC and Analog/PWM, SW3:SW4: 00 Mixed; 01 Independent Right ("Only motor Right will active, motor Left will inactive"); 10 Independent Left; 11 Independent Both ("Both motor is active and can be controlled individually through channel RC1 and RC2").
- SW5 Exponential: 0 linear (low to medium speed motors); 1 exponential, softens control around the centre zero-speed point (high speed or sensitive motors).
- SW6 in RC mode = MCU mode: 0 = centre calibrated at power-up, motor stops after 100 ms without signal; 1 = centre fixed at 1.5 ms, timeout disabled, motor keeps previous speed until a new signal.
- SW6 in Analog/PWM mode = Sign-Magnitude: 0 = Locked Anti-Phase (stop at 2.5 V); 1 = Signed Magnitude (AN1/AN2 set speed, 0 V stop, 5 V full speed; DIG1/DIG2 set direction). "SW2 must be set to 0 if Sign-Magnitude mode is turned on."
- Simplified Serial baud, SW4–SW6: 000 1200, 001 2400, 010 4800, 011 9600, 100 19200, 101 38400, 110 57600, 111 115200.
- Packetized Serial address, SW4–SW6: 000–111 = address 0–7.

**LEDs** [UM]: per motor a Run LED (on while running; blinks on a signal error for that motor) and a direction LED pair (MLA/MRA lit = current from MLA→MLB / MRA→MRB). At power-up RUN-L, ERR and RUN-R run once. Error LED blink codes: 2 Input Error (invalid or no input); 3 Under Voltage; 4 Over Voltage (>35 V, driver will not operate); 5 Over Temperature; 6 Shutdown. Code 1 is not defined.

## Rules and gotchas (for code, wiring and tutorials)
- **Input must be "stop" at power-up** in RC, Analog and PWM modes, otherwise the driver shows Input Error (2 blinks) [UM].
- **RC: switch the transmitter ON before powering the MDDS10** [UM].
- Analog/PWM range is 0–5 V. Stop point is 2.5 V in Locked Anti-Phase, 0 V in Signed Magnitude [UM].
- PWM mode low-pass filters the PWM to analog with an onboard filter capacitor; Analog mode is unfiltered. **Maximum PWM input frequency is not stated** [UM].
- Simplified Serial: one byte per command. Bit 7 = channel (0 LEFT, 1 RIGHT); table labels bit 6 Direction, bits 5–0 Speed. Values: 0 or 64 LEFT stop; 63 LEFT full forward; 127 LEFT full reverse; 128 or 192 RIGHT stop; 191 RIGHT full forward; 255 RIGHT full reverse [UM].
- Packetized Serial: 4 bytes: Header **85 decimal (hex 55)**; Address byte (bit 3 = channel 0 LEFT / 1 RIGHT, bits 2–0 = address matching DIP switch); Command 0–255 (0 full reverse, 127 stop, 255 full forward); Checksum = Header + Address + Command (0–255). Up to 8 drivers on one UART Tx [UM].
- Packetized auto-baud: send the header byte (85) once after power-up; the driver measures the baud rate from it; baud cannot change without power cycle/reset. **Wait about 1 second after power-up** before sending it (start-up can take up to 500 ms) [UM]. The error LED blinks Input Error while waiting for it [UM].
- Mixed mode: the left terminal must go to the LEFT motor and the right terminal to the RIGHT motor; if a motor runs the wrong way, swap its wires at the terminal block [UM].
- MCU mode (RC): a microcontroller "only needs to send a single pulse when the speed or direction of the motor needs to be changed" [UM].
- Do not connect the +5V pin to another 5 V source [UM].

## Power and electrical limits
- Supply 7–35 V. Above 35 V the driver will not operate (error 4) [UM].
- **No polarity protection** on the power input / V motor. "There is no polarity protection on MDDS10, please double check the connection before connecting to power source." [UM]
- **Regeneration:** a supply that cannot sink current (bench-top or AC-DC switching supply) sees its voltage rise when the motor slows. Connect a battery of the same voltage in parallel to absorb it; otherwise the driver may be permanently destroyed or the supply may trigger its protection [UM].
- Recommended sources: 6–18 cells NiMH or NiCd; 2–6 cells LiPo or Li-Ion; 7–35 V sealed lead acid; 7–35 V power supply **only in parallel with a battery of the same voltage** [UM].
- Under voltage (error 3) is a warning only; motor power is maintained. For LiPo it triggers below 3.0 V per cell; stop driving and replace/recharge the battery. For other chemistries the user judges when to replace [UM].
- 10 A continuous depends on room temperature; 30 A peak must not exceed 1 second [UM].
- Thermal derating (duty cycle vs board temperature) [UM]: <50 °C 100%; 50–55 90%; 55–60 80%; 60–65 70%; 65–70 60%; 70–80 50%; 80–85 40%; 85–90 30%; 90–95 20%; 95–100 10%; 100–105 5%; >105 °C 0% (shutdown). After shutdown the channel restarts when temperature falls below 70 °C.
- Over-current protection, heatsink requirement, wire size and fuse rating: **not stated** [UM].
- Logic: no separate logic-supply input is described; the only power input is the Power Supply terminal block [UM].

## Software support
- Arduino library **Cytron_SmartDriveDuo** ("Cytron SmartDriveDuo Series", version=1.0.0, architectures=avr), "works with SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60". Modes in the enum: RC_MCU, PWM_INDEPENDENT, PWM_MIXED, SERIAL_SIMPLIFIED, SERIAL_PACKETIZED; `control(leftSpeed, rightSpeed)` takes −100…100 [GH].
- Library notes [GH]: the RC_MCU constructor is commented out (no way to construct RC_MCU mode); serial uses hardware `Serial` only if txPin == 1, otherwise SoftwareSerial; Packetized mode needs `initialByte()` sent by the user; library README says "Related tutorials: Coming soon...".

## Compatibility and accessories
- Signal sources named by the manual: RC receiver, potentiometer, joystick, foot pedal, PWM, microcontroller UART [UM].
- 3.3 V logic: the manual's high-level range is 1.3–5 V, which includes 3.3 V, but the manual does not explicitly say "3.3 V compatible" [UM].
- Included: 6 × terminal pins for 2510 and 1 × 6-way connector housing (for the input header) [UM].

## Common mistakes / troubleshooting
- Error LED 2 blinks at power-up: input was not at "stop" (RC stick/pot off centre, analog not 2.5 V / 0 V) or the RC transmitter was off; in Packetized mode, header byte not yet received [UM].
- Driver dead after use on a bench or switching supply: regenerative voltage rise; add a same-voltage battery in parallel [UM].
- Reversed supply: no polarity protection; can damage the board [UM].
- Motor slows when hot: thermal derating starts at 50 °C; shutdown above 105 °C, restart below 70 °C [UM].
- Stall/start current above 30 A, or 30 A held longer than 1 second, is outside the rating [UM].
- Robot turns instead of driving straight in Mixed mode: left/right motors swapped or one motor polarity reversed [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Peak current duration | UM spec table: 30 A, "Must not exceed 1 second" | UM Features list: "30A peak (few seconds)" | Spec table wins: **30 A, ≤ 1 second** |
| Peak current | UM: 30 A ≤ 1 s | RobotShop [3P] description: 50 A for 5 seconds (its own spec list says 30 A for 1 s) | UM wins; 50 A is not a spec |
| Packetized header byte | UM: 85 decimal (hex 55) | Cytron_SmartDriveDuo library: `headerByte = 0x85` (133 decimal) [GH] | UM wins for MDDS10. Do not copy the library's packetized code for MDDS10 without hardware testing |
| RIGHT motor direction in Simplified Serial | UM: 191 = RIGHT full forward, 255 = RIGHT full reverse | Library sends 0xC0\|speed (192–255) for **positive** right speed [GH] | UM defines the byte meaning; the library's sign convention for the right motor is inverted relative to the UM labels (likely for mirrored motors). Check direction on hardware |
| Direction pin names | UM: DIG1 / DIG2 | Library: `in1Pin` / `in2Pin` [GH] | Use UM names DIG1/DIG2 in content |

## Needs verification
- Operating temperature, terminal wire size, recommended fuse: not stated anywhere read.
- Maximum PWM input frequency for PWM mode and the RC pulse-width range/deadband: not stated in the UM.
- UART logic level for DIG1 Rx (3.3 V UART) not explicitly stated.
- Figures (board layout photo, wiring and dimension drawings) were not viewed; label letters A–M are from the text.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Peak Current vs Continuous/Rated Current](https://my.cytron.io/tutorial/peak-current-vs-continuousrated-current) — Protip, 2016 [PP: tutorial]
- [Raspberry Pi: Control DC Motor using MDDS10](https://my.cytron.io/tutorial/raspberry-pi-control-dc-motor-using-mdds10) — Tutorial, Beginner, 2026 [PP: tutorial]
- [CT Uno + PS2 shield + MDDS10 for mobile robot control](https://my.cytron.io/tutorial/ctuno-ps2-shield-mdds10-mobile-robot-control) — Tutorial, Beginner, 2015 [PP: tutorial]
- [Let’s Arduino Control SmartDriveDuo-10 (MDDS10)](https://my.cytron.io/tutorial/lets-arduino-control-smartdriveduo-10) — Tutorial, Beginner, 2025 [PP: tutorial]
- [Improve MDDS10 Performance With External Fan](https://my.cytron.io/tutorial/improve-mdds10-performance-external-fan) — Protip, Beginner, 2015 [PP: tutorial]
- [WIFI Robot Maneuver With MDDS10](https://my.cytron.io/tutorial/wifi-robot-maneuver-with-mdds10) — Tutorial, Intermediate, 2022 [PP: tutorial]

## Sources
- SmartDriveDuo-10 MDDS10 User's Manual V1.0, June 2015 (RobotShop CDN mirror) [UM]: https://cdn.robotshop.com/media/c/cyt/rb-cyt-165/pdf/mdds10_users_manual.pdf
- Same manual, Electrokit mirror (not opened): https://www.electrokit.com/upload/product/41018/41018268/MDDS10%20User's%20Manual.pdf
- Cytron_SmartDriveDuo Arduino library [GH]: https://github.com/CytronTechnologies/Cytron_SmartDriveDuo (README.md, library.properties, src/Cytron_SmartDriveDuo.h, src/Cytron_SmartDriveDuo.cpp via raw.githubusercontent.com)
- RobotShop UK listing (cross-check only) [3P]: https://uk.robotshop.com/products/cytron-smartdriveduo-smart-dual-channel-10a-motor-driver
- Product page: not read (my.cytron.io blocked from this environment)
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
