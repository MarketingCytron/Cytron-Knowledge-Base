# Cytron 8 Channels RC Servo Controller Shield for Arduino (SHIELD-SERVO) — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-SERVO` [PP]; document title "SHIELD-Servo" / "Shield-Servo" [UM] |
| Family | Servo and RC controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). Product page agrees with the user manual (4 A continuous / 5 A peak, 7–25 V, 0.5–2.5 ms, 0.25 µs, 9600 default) and adds the board size |
| Primary source | "SHIELD-Servo — Servo Controller Shield — User's Manual", **V1.1, April 2018** (Cytron Google Doc) [UM] — no separate datasheet exists; the user manual is the top-ranked source for this product |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
An Arduino-form-factor shield that controls up to 8 RC servo motors independently (or simultaneously) from a host over a serial (UART) command protocol, with a built-in 5 V switching regulator for the servos (4 A continuous, 5 A peak) fed from a 7–25 V VM input [UM]. The host is an Arduino-compatible board (Arduino/Genuino UNO, Mega, CT-UNO, CT-ARM, etc.) via the shield header, or a PC / other microcontroller via a 6-pin UART header for a UC00A/UC00C USB-to-serial converter (the manual also mentions connecting directly to SKXBee) [UM]. The shield generates servo pulses from 0.5 ms to 2.5 ms with 0.25 µs resolution (position 0–8000), supports per-channel speed, position reporting and a stored start-up position; the manual describes it as "the enhanced version from SC08A" with the regulator and UC00A/UC00C interface added [UM].

## Specifications
The manual has an "Absolute Maximum Rating" table (two rows) plus feature statements; there is no full electrical-characteristics table [UM].

| Item | Value | Src |
|---|---|---|
| VM voltage (absolute maximum rating) | Min 7 V, Max 25 V | [UM] |
| VM current (absolute maximum rating) | Max 5 A | [UM] |
| Servo supply range (feature text) | 7 V to 25 V, through built-in 5 V regulator | [UM][PP] |
| Regulator output | 5 V switching regulator; "maximum current output of 4A (peak 5A)"; feature list: "up to 5A (peak) and 4A (continuous) of total current" | [UM] |
| Regulator output (product page) | "built-in 5V at 5A (peak)" — continuous figure not given on page | [PP] |
| Servo channels | 8, independent | [UM][PP] |
| Servo pulse range | 0.5 ms to 2.5 ms ("greater than the range of most Servos… full range of 180 degrees") | [UM] |
| Position resolution | 0.25 µs; position value 0–8000 (13-bit) | [UM] |
| Pulse width formula | Duty cycle = (0.25 µs × servo position) + 0.5 ms | [UM] |
| Speed setting | 0–100 per command; 1 = slowest, 100 = fastest, **0 = faster than 100** (full speed) | [UM] |
| Host interface | UART (TTL/CMOS 5 V logic); factory default baud **9600**; baud rate "saved in non-volatile memory" | [UM] |
| Logic inputs | 5 V logic-level compatible | [UM] |
| Servo signal outputs S1–S8 | TTL/CMOS logic (5 V and 0 V) | [UM] |
| Arduino UART pins (DIP-switch selectable) | Shield TX → D0, D2, D10 or D12; shield RX ← D1, D3, D11 or D13 | [UM] |
| Alternative UART port | 6-pin UC00A/UC00C header (DTR, TX, RX, VSEL, CTS, GND) | [UM] |
| Dimension | 7.4 cm × 6.6 cm | [UM][PP] |
| Position reporting | optional; host requests the position of an individual servo | [UM] |
| Start-up position | independent starting-position command per channel, applied at next start-up | [UM] |
| Reverse-polarity protection on VM | "Shield-Servo provides protection against wrong polarity for this input" (type not stated) | [UM] |
| Warranty | 6 months [UM]; 12 months [PP] — see Conflicts | [UM][PP] |
| Price | RM79.80 (Cytron product page, read 2026-10-16) | [PP] |
| Pulse refresh rate / frame period | Not stated for the shield (general servo text says "approximately fifty times per second") | — |
| Operating temperature, weight, quiescent current, regulator part number | Not stated | — |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** first servo shield for Arduino with a built-in 5 V, 5 A (peak) switching regulator; supply 7–25 V; 8 independent RC servos; pulses 0.5–2.5 ms; UART interface to an Arduino-compatible board (UNO, Mega, CT-UNO, CT-ARM) or a 6-pin UART header for UC00A/UC00B/UC00C or another MCU [PP].
- **Features list:** activate each servo independently; position and speed control per servo; sample code for Arduino and VB.net; **5 A peak and 4 A continuous total**; 7–25 V input with built-in 5 V switching regulator; optional position reporting; 5 V logic-level inputs; independent starting position per channel; pulse range 0.5–2.5 ms; **pulse resolution 0.25 µs**; baud rate saved in non-volatile memory (factory default 9600) [PP].
- **Dimension:** 7.4 cm × 6.6 cm [PP].
- **Packing list:** 1x Servo Shield [PP].
- **Resources:** User's Manual (Google Doc) and example code (GitHub `Cytron_Servo_Shield`) [PP].

## Interfaces, terminals and pin mapping
Board layout labels (manual chapter 4) [UM]:

| Label | Function |
|---|---|
| A | UART selector — DIP switch that selects which Arduino pins carry TX and RX |
| B | 8-way connector block for the servo motors |
| C | Servo motor power indicator LED (1 LED, called **MPWR** in chapter 5) |
| D | Manufacturing test point — header not soldered; "DO NOT connect or shorted any of these pins" |
| E | UC00A/UC00C communication header (also for other microcontrollers) |
| F | Push button to **reset** the shield's servo controller (NOT the Arduino reset) — do not press during operation |
| G | Push button to **test** — on press-and-release, every connected servo runs a predetermined movement and speed |
| H | Small green LED, VCC (logic power) indicator — logic power comes from the Arduino main board or from UC00A/UC00C (called **PWR** in chapter 5) |
| I | Power input source for the servos (VM, GND) |
| J | 10/8/6-way Arduino headers to the host |
| K | Solder jumper — solder it to share power from the Arduino 5 V, or to supply the Arduino from a single power source |

Power input pins [UM]:
- **VM** — servo supply voltage, positive terminal of the power source; feeds the servos (through the regulator). Polarity protection is provided but the user must still check voltage and polarity before applying power.
- **GND** — common ground for logic and servo power.
- PWR LED lights when power is connected correctly.

Arduino signal pins [UM]:
- **TX** (shield output → Arduino input): D0, D2, D10 or D12.
- **RX** (Arduino output → shield input): D1, D3, D11 or D13.
- The DIP switch pairs them as D0/D1 (hardware serial), D2/D3, D10/D11 or D12/D13 (SoftwareSerial). In Arduino terms, the shield's TX lands on the Arduino's receive pin and the shield's RX on the Arduino's transmit pin.

UC00A/UC00C 6-pin header [UM]:

| Pin | Definition | Function |
|---|---|---|
| DTR | Reset via 0.1 µF capacitor | Connected to the shield controller's reset pin through 0.1 µF — usable as a software reset |
| TX | UART transmit (host side) | Connected to the shield's receive pin; 5 V logic; connect to the host's transmit pin |
| RX | UART receive (host side) | Connected to the shield's transmit pin; 5 V logic; connect to the host's receive pin |
| VSEL | System 5 V | "Should be supplied from UC00A/UC00C. It is to power the shield servo controller." |
| CTS | NC | Not connected |
| GND | System ground | Common ground for logic and servo power |

The manual notes that TX and RX between the shield and UC00A/UC00C are cross-connected [UM]. Servo header pin order (signal/+/−) is only shown in figures and could not be read.

UART protocol (manual 7.2) — first byte = 3 mode bits + 5-bit channel; channel 1–8, channel **0 = all channels** [UM]:

| Command | Mode bits | Bytes sent | Byte values | Reply |
|---|---|---|---|---|
| Activate / deactivate channel | `110` | 2: `110xxxxx`, then `0000000x` (1 = activate, 0 = deactivate) | 1st byte 0xC0–0xC8 (printed as "193–200 / C1–C8"); 2nd byte 0x00 or 0x01 | none |
| Position and speed | `111` | 4: `111xxxxx`, position high 7 bits (`0xxxxxxx`, 0–127), position low 6 bits (`00xxxxxx`, 0–63), speed (`0xxxxxxx`, 0–100) | 1st byte 0xE0–0xE8 (printed "224–232 / E1–E8") | none |
| Position reporting | `101` | 1: `101xxxxx` (channel 1–8; channel 0 → "command not executed") | 0xA1–0xA8 (printed "161–168") | 2 bytes: position high 7 bits, then low 6 bits |
| Starting position | `100` | 3: `100xxxxx`, position high 7 bits, position low 6 bits | 0x81–0x88 (printed "129–136"); channel 0 sets all | 1 byte **0x04** |

- 13-bit position = (2nd byte & 0x7F) << 6 | (3rd byte & 0x3F); bits 12–6 in the 2nd byte, bits 5–0 in the 3rd byte [UM].
- Initial state of every servo is **deactivated**; the host must send the activate command before servos move [UM].
- Bytes are sent one by one; the shield translates the 4-byte packet into channel, position, speed [UM].

## Rules and gotchas (for code, wiring and tutorials)
- There is **no datasheet** — cite the User's Manual V1.1 (April 2018) [UM].
- Regulator budget is for **all servos combined**: 4 A continuous, 5 A peak, total [UM]. Product page quotes only "5A (peak)" [PP] — do not write 5 A continuous.
- VM input is **7–25 V** (absolute max 25 V) [UM][PP]. The regulator output to the servos is fixed 5 V; the manual does not describe any way to run servos at VM directly or at 6 V [UM].
- Alternative: power the servos from the Arduino 5 V by soldering jumper **K** — manual says this is "strongly not recommended" for more than one small servo because the Arduino 5 V is "normally only 1A max". **If jumper K is used, do NOT connect any power to VM and GND** [UM].
- Logic power for the shield controller comes from the Arduino (via header) or from UC00A/UC00C VSEL — not from VM. With a PC/UC00A set-up, "only power source for Servo motor is needed" in addition [UM].
- UART pins are chosen with the DIP switch (A). If D0/D1 are in use by another shield, choose D2/D3, D10/D11 or D12/D13 and use SoftwareSerial [UM].
- Default baud is **9600**; the manual states the baud rate is saved in non-volatile memory but documents **no command to change it** — treat 9600 as the only known value [UM].
- Servos start **deactivated** — send the activate command (mode `110`) first [UM]. Position report on channel 0 is not executed [UM].
- Speed byte: 0 is the special full-speed value and is faster than 100 [UM]. The library default `spd = 0` is therefore full speed [GH].
- Position 0 = 0.5 ms, 8000 = 2.5 ms (0.25 µs steps). Pulse-to-angle mapping "varies from one Servo manufacturer to another" [UM]. The library's `angle()` maps 0–180° to positions **156–7260** (0.539–2.315 ms), not 0–8000 [GH].
- Reset button (F) resets the shield controller only, not the Arduino; do not press it during operation [UM]. DTR on the UC00A header gives a capacitor-coupled software reset [UM].
- Test button (G) drives every connected servo in a predetermined movement [UM]; an external switch can be wired as a test (S1) or reset (S2) switch (manual 5.3; wiring is in a figure not read) [UM].
- Manufacturing test point (D) must be left unconnected [UM].
- Multiple shields on one PC: the manual says you may connect more than one UC00A/UC00C and control more than one shield at a time [UM]. Stacking two shields on one Arduino is not described.

## Power and electrical limits
- VM absolute maximum: 7 V min, 25 V max; VM current 5 A max [UM].
- On-board switching converter: VM → 5 V, 4 A max continuous, 5 A peak, shared by all 8 servos [UM]. Regulator IC, efficiency and switching frequency are not stated.
- Wrong-polarity protection on VM is stated; the mechanism is not [UM].
- Servo outputs S1–S8 and the Arduino TX/RX are 5 V TTL/CMOS logic; inputs are "5V logic level compatible" [UM]. 3.3 V host compatibility is **not stated**.
- The 6-pin header's TX/RX "should be interfaced to 5V logic UART" [UM].
- No over-current, thermal or under-voltage protection is described for the regulator [UM].

## Software support
- Library API (`src/CytronServoShield.h` / `.cpp`) [GH]: `init(HardwareSerial*)`, `init(SoftwareSerial*, listenCallback)` (AVR) or `init(Stream*, cb)` (other cores); `setChannel(chnl, ON/OFF)`; `position(chnl, pos 0–8000, spd = 0)`; `angle(chnl, 0–180, spd = 0)`; `getPosition(chnl)`; `getAngle(chnl)`; `setStartPosition(chnl, pos)`; `setStartAngle(chnl, angle)`; `registerErrorCallback(cb)`. Constants `ALL_CHANNELS`, `CHANNEL_1`…`CHANNEL_8`, `ON`, `OFF`; status codes `CYTRON_SHIELD_SERVO_OK` (0), `CYTRON_SHIELD_SERVO_TIMEOUT_ERROR` (−1), `CYTRON_SHIELD_SERVO_CHECKSUM_ERROR` (−2).
- Library behaviour [GH]: `position()` clamps pos to 8000; `setChannel()` ignores channel values > 8; `getPosition()` waits up to `CYTRON_SHIELD_SERVO_TIMEOUT` = 100 ms for 2 reply bytes and returns 0 on error (calling the error callback); `setStartPosition()` waits up to 5 s for the 0x04 acknowledgement; angle mapping caps are 156 (lower) and 8000 − 740 = 7260 (upper). The library does **not** call `begin()` on the serial port — the sketch must open it (baud not set by the library). Header comment lists "Cytron Servo Shield Version: 1.0.0" hardware and IDE Arduino 1.8.1.
- The library's `examples/` folder exists but its sketch names could not be listed (GitHub directory pages blocked) [GH]. The manual names a single sample sketch, **"Shield Servo Example.ino"**, written for CT-UNO using software UART [UM].
- **PC GUI**: "Shield-Servo GUI" written in VB.net with Microsoft Visual Studio Community 2015 (older versions may not open the project); distributed with source on the repository's `visual-basic` branch (`setup.exe`, may need the latest .NET Framework); requires UC00A/UC00C and Visual Studio Express 2015 or above; lets the user turn motors on/off, activate/deactivate individual motors, change position, set speed and reset the servo initial position; default baud 9600 [UM][GH].
- No I2C, SPI, PWM-input or RC-receiver-input control is described — UART only [UM].

## Compatibility and accessories
- Hosts named: Arduino/Genuino UNO, Mega, CT-UNO, CT-ARM "etc." via the shield headers [UM]; any microcontroller with 5 V TTL UART via the 6-pin header [UM].
- USB-to-serial: UC00A, UC00B or UC00C (manual intro lists UC00A/UC00B/UC00C; the rest of the manual and the GUI README say UC00A/UC00C) [UM][GH]. Direct SKXBee connection is mentioned for wireless UART [UM].
- Packing list: 1 × SHIELD-Servo board (assembled and tested); manual and sample code are downloads [UM].
- Related Cytron products the manual contrasts it with: SC08A and SC16A [UM].
- Positioning (product page): 8-channel RC servo controller shield for Arduino with built-in 5 V/5 A (peak) regulator, 7–25 V supply [PP].

## Common mistakes / troubleshooting
- **Servos do not move at all** — they are deactivated at power-up; send the activate command (`setChannel(ALL_CHANNELS, ON)` or 0xC0 0x01) first [UM][GH].
- **MPWR LED off** — VM/GND not connected or wrong polarity; check with a multimeter before powering [UM].
- **PWR (green) LED off** — no logic 5 V; it must come from the Arduino header or from UC00A/UC00C VSEL [UM].
- **No response / garbage** — DIP switch (A) set to a pin pair different from the one the sketch uses; TX/RX not crossed on the UC00A header; baud not 9600 [UM].
- **Servos twitch or brown out** — total load over 4 A continuous / 5 A peak, or servos powered from the Arduino 5 V via jumper K [UM].
- **Board resets unexpectedly** — reset button (F) pressed during operation, or DTR toggled by the host's serial port (0.1 µF capacitor to reset) [UM].
- **`getPosition()` returns 0** — reply timed out (100 ms) or incomplete; the error callback reports `TIMEOUT_ERROR` / `CHECKSUM_ERROR` [GH].
- **Position report never answered** — channel 0 is not valid for the reporting command [UM].
- **Damage from VM and jumper K together** — never feed VM while jumper K is soldered [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Regulator current | [UM] V1.1: 4 A continuous, 5 A peak (total) | [PP] description: "5V at 5A (peak)"; [PP] features list (read 2026-10-19): "5A (peak) and 4A (continuous) of total current" | Agree: write **4 A continuous / 5 A peak** total |
| Warranty | [UM] chapter 8: 6 months | [PP]: 12 months | Product page is the current commercial term (read 2026-10-16); manual (2018) is older. Record both; do not state warranty as a spec |
| Activate-command 1st byte range | [UM] table: "193–200 / C1–C8" | [UM] text: channel 0 (= all) is valid, i.e. 0xC0 = 192 | Printed range omits channel 0; the bit pattern `110xxxxx` with channel 0–8 (0xC0–0xC8) is authoritative |
| Position/speed 1st byte range | [UM] table: decimal "224–232" | [UM] same table: hex "E1–E8" (= 225–232) | 224 = 0xE0 is channel 0 (all); use 0xE0–0xE8 |
| Starting-position 1st byte | [UM] table: "129–136 / 81–88" | [UM] text: channel 0 "to set all servo motor" (0x80 = 128) | Use 0x80–0x88 |
| Section cross-reference | [UM] 1.1 refers to "section 7.4, Shield-Servo UART Protocol" | [UM] protocol is section 7.2 | Numbering error in V1.1 |
| USB-serial converters | [UM] intro: UC00A/UC00B/UC00C | [UM] elsewhere and [GH]: UC00A/UC00C | All are UART converters; UC00B not mentioned again |
| Library hardware version | [GH] header: "Cytron Servo Shield Version: 1.0.0" | [UM] document V1.1 | Different things (board rev vs manual rev); board revision is not stated anywhere |

## Needs verification
- Board revision / hardware version and revision history — not stated in the manual or on the product page.
- Servo header pin order (signal/+/−) and the dimension drawing (hole positions) — only in figures not readable here.
- Pulse refresh rate (frame period) generated by the shield — not stated.
- How the "non-volatile baud rate" is changed — no command documented; whether rates other than 9600 are supported.
- Whether 3.3 V hosts can drive the RX input (manual says 5 V logic only).
- Regulator IC, quiescent current, thermal/over-current behaviour.
- Behaviour on UART loss or host reset (servos hold, free-run?) — not stated.
- Example sketch names in the library `examples/` folder (directory listing blocked); whether the example opens the serial port at 9600.
- Whether two shields can be stacked on one Arduino using different DIP-switch pin pairs — not described.
- The external switch wiring of manual 5.3 (figure not readable).

## Sources
- [UM] "SHIELD-Servo — Servo Controller Shield — User's Manual", V1.1, April 2018 (Cytron Google Doc, linked from the product page) — https://docs.google.com/document/d/191P6FwTgJ_dWhAhB3eWfP0YMSbI4_7Kehgzw3pYy-AY/view
- [PP] Product page (read by the coordinator 2026-10-16; not fetched here) — https://my.cytron.io/p-cytron-8-channels-rc-servo-controller-shield-for-arduino
- [GH] Library repository — https://github.com/CytronTechnologies/Cytron_Servo_Shield
- [GH] `library.properties` — https://raw.githubusercontent.com/CytronTechnologies/Cytron_Servo_Shield/master/library.properties
- [GH] `src/CytronServoShield.h` — https://raw.githubusercontent.com/CytronTechnologies/Cytron_Servo_Shield/master/src/CytronServoShield.h
- [GH] `src/CytronServoShield.cpp` — https://raw.githubusercontent.com/CytronTechnologies/Cytron_Servo_Shield/master/src/CytronServoShield.cpp
- [GH] `keywords.txt` — https://raw.githubusercontent.com/CytronTechnologies/Cytron_Servo_Shield/master/keywords.txt
- [GH] Visual Basic GUI branch README — https://raw.githubusercontent.com/CytronTechnologies/Cytron_Servo_Shield/visual-basic/README.md
- [GH] Duplicate repository README — https://raw.githubusercontent.com/CytronTechnologies/Cytron_Servo_Shield_Library/master/README.md
