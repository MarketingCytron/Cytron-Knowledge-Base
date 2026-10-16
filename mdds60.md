# SmartDriveDuo-60 (MDDS60) — Verified Reference

| | |
|---|---|
| Product code | `MDDS60` (cover page: "SmartDriveDuo-60", "MDDS60", "User's Manual") [UM] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tags: [UM] = Rev 1.1 (July 2019), read in full as text; figures (dimension drawing, board photos, wiring diagrams, power-switch rework photos) were not viewed. [UM-1.0] = Product User's Manual Rev 1.0, August 2015 (Tindie mirror), checked through WebFetch for differences; none found on the points checked.

## What it is
A dual-channel brushed DC motor driver from Cytron's SmartDriveDuo series for medium-power motors, "designed specially for controlling differential drive mobile robot using RC controller"; it can also be controlled by an analog joystick or a microcontroller (PWM, Serial) [UM]. It drives two brushed DC motors bi-directionally from one 10–45 V supply, with MOSFETs switched at 16 KHz, an on-board cooling fan and top/bottom covers [UM].

## Specifications
"Absolute Maximum Rating of SmartDriveDuo-60" table plus the Features list [UM].

| Item | Value | Src |
|---|---|---|
| Input Voltage (Motor Supply Voltage) | Min 10 V, Max 45 V | [UM] |
| IMAX (Maximum Continuous Motor Current) | Max 60 A. Footnote: "Depends on the room temperature." Features: "60A continuously, each channel" | [UM] |
| IPEAK (Peak Motor Current) | Max 100 A. Footnote: "Must not exceed 1 second." Features: "100A peak (1 second) ... each channel" | [UM] |
| VIOH (Logic Input – High Level) | 1.3 V min – 5 V max | [UM] |
| VIOL (Logic Input – Low Level) | 0 V min – 0.7 V max | [UM] |
| 5V Output Current | Max 500 mA | [UM] |
| Motor channels | 2 ("Bi-directional control for dual brushed DC motor") | [UM] |
| Switching frequency | 16 KHz ("for quiet operation") | [UM] |
| Input modes | RC, Analog, PWM, Simplified Serial, Packetized Serial (DIP switch selected) | [UM] |
| Battery low voltage indicator / over voltage indicator | Yes / Yes | [UM] |
| Thermal protection | Yes: duty-cycle derating from 50 °C, shutdown above 105 °C | [UM] |
| Over-current / current-limit protection | **Not stated** in the UM | [UM] |
| Test buttons | On-board push buttons, one per motor, "for fast test and manual operation" | [UM] |
| Polarity protection | **None** ("No polarity protection for V motor") | [UM] |
| Cooling | Cooling fan: "Once MDDS60 is powered up, this fan will blow the board." | [UM] |
| Dimension | Heading "Dimension:" present; value only in a drawing, not readable in text | [UM] |
| Operating temperature | **Not stated** | [UM] |
| Warranty | 12 months, manufacturing defects only; misuse not covered; freight both ways not covered | [UM] |
| Packing list | 1 × SmartDriveDuo-60 with top and bottom cover; 2 × 2561 Servo Extension cable | [UM] |
| Hardware revision | Rev1.10 shipped since January 2019: "component changes on the circuit. The modification does not affect the performance or the interface." | [UM] |

## Interfaces, terminals and pin mapping
Board layout labels [UM]: A Motor LEFT terminal block; B Power Supply terminal block; C Motor RIGHT terminal block; D Motor LEFT LED indicator; E Motor RIGHT LED indicator; F Power Switch terminal block; G Cooling fan; H Run and Error LED; I Motor LEFT test button; J Motor RIGHT test button; K Mode selection DIP switch; L RC input pin; M Analog/PWM/Serial input terminal block. (Components in blue font in the figure are on the middle board.)

| Pin / terminal | Function | Src |
|---|---|---|
| Power Supply terminal block (B) | 10–45 V. Screw terminal or solder to bottom pad. "No polarity protection." "Please use wire with proper thickness to support the expected current." | [UM] |
| Motor LEFT / RIGHT terminal blocks (A / C) | Outputs to LEFT / RIGHT motor (direction LEDs MLA/MLB, MRA/MRB). Screw terminal or solder to bottom pad | [UM] |
| Power Switch terminal block (F) | "Switch for power up MDDS60's microcontroller and logic circuit. This switch is ON by default." To use an external switch, connect it to this terminal and cut/unsolder the link under it on the bottom layer | [UM] |
| Input terminal block (M) pin 1 DIG1 | Direction for motor LEFT; Serial Simplified / Serial Packetized UART Rx | [UM] |
| pin 2 DIG2 | Direction for motor RIGHT | [UM] |
| pin 3 AN1 / pin 4 AN2 | Analog/PWM signal for motor LEFT / RIGHT | [UM] |
| pin 5 +5V | +5V output (max 500 mA). "Do not connect to another 5V source." | [UM] |
| pin 6 GND | Ground | [UM] |
| RC input pin (L): RC1 / RC2 | RC1 forward/reverse; RC2 steering | [UM] |
| "RST" reset button | Named in the Input Mode section ("press the 'RST' reset button") to change mode without power cycling; not listed in the board layout table | [UM] |

No UART TX pin is described; the driver only receives [UM].

**LEDs** [UM]: RUN_L / RUN_R (on while that motor runs; blink on a signal error for that motor); motor direction LEDs (MLA/MRA lit = current from MLA→MLB / MRA→MRB). At power-up RUN-L, ERR and RUN-R run once. Error LED: Off no error; 2 Input Error; 3 Under Voltage; 4 Over Voltage ("MDDS60 will not operate"); 5 Over Temperature; 6 Shutdown ("Motor automatically stop").

**DIP switch** (8 positions shown in the setting figures; SW7–SW8 not described and shown as 0) [UM]:
- Input mode SW1:SW2 — 00 RC; 01 Analog; 10 PWM; 11 + SW3=0 Simplified Serial; 11 + SW3=1 Packetized Serial.
- RC and Analog/PWM, SW3:SW4 — 00 Mixed; 01 Independent Right; 10 Independent Left; 11 Independent Both ("Recommended this mode if controlled using Microcontroller").
- SW5 Exponential — 0 linear (low to medium speed motor); 1 exponential (high speed / very sensitive motor).
- SW6 in RC mode = MCU mode: 0 = centre calibrated at power-up, stop after 100ms signal loss; 1 = centre fixed at 1.5ms, timeout disabled, motor keeps previous speed; MCU "only needs to send a single pulse when the speed or direction of the motor needs to be changed."
- SW6 in Analog/PWM mode = Sign-Magnitude: 0 Locked Anti-Phase (stop at 2.5V); 1 Signed Magnitude (AN1/AN2 speed, 0V stop, 5V full; DIG1/DIG2 direction). "SW2 must be set to 0 if Sign-Magnitude mode is turned on."
- Simplified Serial baud SW4–SW6: 000 1200, 001 2400, 010 4800, 011 9600, 100 19200, 101 38400, 110 57600, 111 115200.
- Packetized Serial address SW4–SW6: 000–111 = 0–7.
- Example settings (SW1→SW8): RC Mixed 00000000; RC with MCU Independent Both 00110100; Analog joystick Mixed 01000000; PWM MCU Independent Both 10110100; Simplified Serial 9600 bps 11001100; Packetized address 0 11100000.

## Rules and gotchas (for code, wiring and tutorials)
- **Input must be "stop" at power-up** in RC, Analog and PWM modes, else Input Error (2 blinks). Analog/PWM stop = 2.5V if Sign-Magnitude is off, 0V otherwise [UM].
- **RC transmitter must be ON before powering up** the MDDS60 [UM].
- Analog/PWM valid range 0–5V; PWM is low-pass filtered by an on-board capacitor, Analog is unfiltered. **Maximum PWM input frequency is not stated** [UM].
- Simplified Serial (DIG1 = UART Rx; DIG2, AN1, AN2 unused): one byte; bit 7 channel (0 LEFT, 1 RIGHT), bits 6–0 direction and speed. 0 or 64 LEFT stop; 63 LEFT full forward; 127 LEFT full reverse; 128 or 192 RIGHT stop; 191 RIGHT full forward; 255 RIGHT full reverse [UM].
- Packetized Serial: 4 bytes — Header **85 (hex 55)**; Channel & Address (bit 3 channel 0 LEFT/1 RIGHT, bits 2–0 address = DIP); Command 0–255 (0 full reverse, 127 stop, 255 full forward); Checksum = Header + Address + Command. Up to 8 units on one UART Tx [UM].
- Auto-baud: send the header byte (85 / 0x55) once after power-up; baud cannot change without power cycle or reset. Wait **one second** after power (start-up up to 500ms). Error LED shows Input Error while waiting [UM]. (MDDS30 differs: it uses dummy byte 0x80.)
- Mixed mode: left terminal block to LEFT motor, right to RIGHT; reverse a motor's wires if it runs the wrong way [UM].
- Mode is read at power-up; change the DIP switch then press "RST" or power cycle [UM].
- Do not connect +5V to another 5V source [UM].

## Power and electrical limits
- Supply 10–45 V; >45 V → driver will not operate (error 4) [UM].
- **No polarity protection** — "There is no polarity protection on MDDS60, please double check the connection before connecting to power source." [UM]
- Recommended sources: 6–18 cells NiMH or NiCd; 3–6 cells LiPo or Li-Ion; 10V–45V sealed lead acid; 10V–45V power supply "(Must be in parallel with a battery with same voltage)" [UM].
- **Regeneration:** with a supply that cannot sink current (bench-top, AC-to-DC switching supply), input voltage rises when the motor slows; connect a same-voltage battery in parallel, or the driver may be "destroyed permanently" or the supply may trip [UM].
- Under voltage (error 3): cell count detected at power-up; with LiPo, warns below 3.0V per cell; motor power is maintained (warning only) [UM].
- Thermal derating (duty cycle vs temperature) [UM]: <50 °C 100%; 50–55 90%; 55–60 80%; 60–65 70%; 65–70 60%; 70–80 50%; 80–85 40%; 85–90 30%; 90–95 20%; 95–100 10%; 100–105 5%; >105 °C 0% (shutdown, error 6). The channel restarts when temperature falls below 70 °C.
- 60 A continuous depends on room temperature; 100 A peak must not exceed 1 second [UM].
- Logic: the power switch terminal powers the microcontroller and logic circuit from the main supply; no separate logic-supply input is described [UM].
- Over-current protection, fuse rating and wire gauge: **not stated** [UM].

## Software support
- Arduino library **Cytron_SmartDriveDuo** (version=1.0.0, architectures=avr), "works with SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60" [GH]. Modes RC_MCU (constructor commented out), PWM_INDEPENDENT, PWM_MIXED, SERIAL_SIMPLIFIED, SERIAL_PACKETIZED; `control(left, right)` −100…100 [GH].
- Examples are written for MDDS30 and say "also compatible with MDDS10 and MDDS60"; for MDDS60 the packetized example's commented line `initialByte(0x55); // MDDS10 or MDDS60` applies [GH]. Example pin names IN1/IN2 = MDDS60 DIG1/DIG2.

## Compatibility and accessories
- Signal sources named by the UM: RC transmitter/receiver, joystick or foot pedal with potentiometer, Cytron "Breakout board with Joystick soldered" (BB-PSJ), microcontroller (PWM, UART) [UM].
- 3.3 V logic: VIOH 1.3–5 V includes 3.3 V, but the UM does not explicitly say "3.3V compatible" [UM].
- External power switch: wire to the Power Switch terminal block after cutting/unsoldering the bottom-layer link [UM].

## Common mistakes / troubleshooting
- ERR 2 blinks at power-up: input not at stop, RC transmitter off, or (Packetized) header byte not yet received [UM].
- External power switch does nothing: the bottom-layer link under the terminal was not cut/unsoldered [UM].
- Driver dead after use on a bench or switching supply: regenerative voltage rise; add a same-voltage battery in parallel [UM].
- Reversed supply: no polarity protection [UM].
- Motor slows when hot: derating from 50 °C; shutdown above 105 °C (6 blinks), restart below 70 °C [UM].
- Stall/start current above 100 A, or 100 A held longer than 1 second, is outside the rating [UM].
- Packetized mode silent: using 0x80 (MDDS30 habit) instead of 85 as the first byte, or not waiting 1 s after power-up [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Peak current duration | UM spec table: 100 A, "Must not exceed 1 second"; Features: "(1 second)" | UM Introduction: "100A peak (few seconds)" | Spec table wins: **100 A, ≤ 1 second** |
| Minimum supply voltage | UM and UM-1.0: 10 V–45 V | Switch Science [3P] "DC 7 ～ 45 V"; ThingBits [3P] "7V to 45V DC" | UM wins: **10–45 V** |
| Packet header byte | UM: 85 (hex 55) | Library `headerByte = 0x85` (133) [GH] | UM wins. Test library packetized code on hardware before publishing |
| Analog/PWM Mixed / Independent channels | UM Analog/PWM table: Mixed "speed ... channel RC1 and direction ... channel RC2"; Independent Left "Motor Right is controlled by channel RC1" | Pin table and Sign-Magnitude text: AN1/DIG1 = LEFT, AN2/DIG2 = RIGHT | Likely copy errors in the UM table; use AN1/AN2 (see Needs verification) |
| Current limiting | UM: not stated | Switch Science [3P]: current limiting by temperature feedback | UM wins: only thermal derating is a spec |
| Power-switch rework | UM board-layout text: "cut the PCB track at the bottom layer" | UM section 7: "unsolder it like shown in the figure" | Same step described two ways; figure not viewed |

## Needs verification
- Dimensions: only a drawing in the UM. Switch Science [3P]: 121.92 (L) × 190.5 (W) × 48 mm (H); ThingBits [3P]: approx. 190 × 121 × 45 mm.
- Logic level: Switch Science [3P] says logic voltage "5 V or 3.3 V"; UM gives only VIOH 1.3–5 V.
- Number of fans: Switch Science [3P] says two brushless fans on the top cover; UM says "this fan".
- Switch Science [3P] also lists a high-efficiency switching regulator and a reset button "for restarting the MCU when changing control mode"; the UM names the "RST" button only in text.
- Function of DIP SW7–SW8 (not described; shown as 0 in all examples).
- Analog/PWM Mixed mode inputs: UM table says RC1/RC2; expected AN1 (speed)/AN2 (direction) as on MDDS30 — confirm on hardware.
- 6-cell NiMH (nominal 7.2 V) is listed as a recommended source but is below the 10 V minimum; confirm the intended cell range.
- Maximum PWM input frequency, RC pulse range, operating temperature, fuse rating, terminal wire gauge.
- Product page specs, price and status (my.cytron.io not reachable).

## Sources
- SmartDriveDuo-60 MDDS60 User's Manual Rev 1.1, July 2019 (public Google Doc) [UM]: https://docs.google.com/document/d/15ICHc5CqQL8oXdU-n3ZL0_o8Vm4wQCnWOHHEfrEDDaI/view
- MDDS60 Product User's Manual Rev 1.0, August 2015 (Tindie mirror) [UM-1.0]: https://media.tindie.com/datasheets/5716/2015-09-10-06-59-28/MDDS60UsersManual.pdf
- Cytron_SmartDriveDuo Arduino library [GH]: https://github.com/CytronTechnologies/Cytron_SmartDriveDuo
- Switch Science listing (cross-check only) [3P]: https://www.switch-science.com/collections/cytron/products/3610 (also links a quick start guide and Fritzing file on Drive; quick start guide not accessible)
- ThingBits listing (cross-check only) [3P]: https://www.thingbits.in/products/cytron-mdds60-smartdrive-dc-motor-driver-60a-7v-to-45v-dual-channel
- Product page: not read (https://www.cytron.io/p-mdds60 per Switch Science; blocked from this environment)
