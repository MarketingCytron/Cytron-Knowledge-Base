# 8 Channel Servo Controller (SC08A) — Verified Reference

| | |
|---|---|
| Product code | `SC08A` [PP]; document title "SC08A SERVO CONTROLLER" [UM] |
| Family | Servo and RC controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron GitHub `Arduino_SC08A` read in full (README + both sketches): the command bytes match the manual's protocol table, and the sketches add Arduino-side rules (hardware UART at 9600, speed 0 must not be used with position reporting). No SC08A manual file was found in the team reference folder, so the manual is still read only through the reseller mirror and the connector pin orders stay open — stays Medium. Earlier: 2026-10-19 master-table review of the live product page |
| Primary source | "SC08A SERVO CONTROLLER — User's Manual", **V1.0, June 2011**, Cytron Technologies Sdn. Bhd. [UM] — no separate datasheet exists; the user manual is the top-ranked source |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A stand-alone 8-channel RC servo controller board built around a PIC16F1827 microcontroller, commanded over 5 V TTL UART at 9600 baud from a PC (via UC00A USB-to-UART) or a microcontroller [UM]. It generates servo pulses from 0.5 ms to 2.5 ms with 8000-step resolution, supports per-channel activate/deactivate, 100 ramp (speed) rates, optional position reporting and a stored start-up position per channel [UM]. Two SC08A boards can be linked with a 4-way cable and a jumper setting to control 16 servos from one host [UM]. Servo power is a separate supply on a blue terminal block (no on-board regulator); the controller's own 5 V comes from the UC00A or the host [UM].

## Specifications
The manual has **no specification table and no absolute-maximum-rating table** [UM]; the rows below are the values stated in its text.

| Item | Value | Src |
|---|---|---|
| Servo channels | 8, "Servo driven independently" | [UM] |
| Expansion | "Extendable to 16 Channels: Two controller linked together to drive 16 servos" | [UM] |
| Servo pulse range | 0.5 ms to 2.5 ms (over 180° on most servos) | [UM] |
| Resolution | "8000 steps = 0.25us" (introduction and formula); protocol section prints 0.5 µs — see Conflicts | [UM] |
| Position formula | Duty cycle = (resolution × servo position) + 0.5 ms, position 0–8000 | [UM] |
| Speed / ramp | "Choose one of 100 ramp rate for each servo"; speed byte 0–100; 0 = fastest ("more faster than value '100'"), 1 = slowest | [UM] |
| Speed-vs-time (Cytron C36S, 0° to 180°) | 0 → 0.3 s; 1 → "2.0 minutes"; 16 → 14 s; 32 → 7.0 s; 48 → 4.14 s; 64 → 3.60 s; 80 → 2.80 s; 96 → 2.2 s; 99 → 1.9 s (printed values; manual says they vary by servo) | [UM] |
| UART | 9600 baud; TTL level; whether changeable is not stated | [UM] |
| Controller supply | "The standard power source is 5V for SC08A" — from UC00A (PC use) or shared from the host microcontroller board | [UM] |
| Servo supply | independent source on the blue terminal block; "4.8V to 9V (standard is 4.8V to 6.0V)"; rated servo voltage "between 4.8V and 6V. Some may need 7.2V"; "Over supply voltage may spoil the servo motor!"; must supply "several ampere" for many servos | [UM] |
| Microcontroller | PIC16F1827 (18-pin) | [UM] |
| Position reporting | optional; request the position of an individual servo; 2-byte reply | [UM] |
| Starting position | "set the initial position of any channel at the next start-up", 0–8000 | [UM] |
| LEDs | orange = servo power present; green = 5 V for PIC | [UM] |
| Buttons | servo test; reset | [UM] |
| Connectors in packing | 1 × 2510H-04 and 1 × 2561-04 connectors (with terminal pins), 1 × mini jumper for JP11 | [UM] |
| Warranty | 6 months [UM]; 12 months [PP] — see Conflicts | [UM][PP] |
| Price | RM65.10 (Cytron product page, read 2026-10-16) | [PP] |
| Dimensions | 49 mm × 46 mm | [PP] |
| Weight, current draw, servo supply maximum (board), pulse refresh rate | Not stated | — |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** 8 servo channels driven independently; extendable to 16 channels by linking two controllers over serial; host = PC with a USB-to-UART converter or any MCU with UART; any channel can be deactivated; per-channel start-up position [PP].
- **Features list:** optional position reporting; servo activation per channel; independent starting position command; optional servo ramping (one of 100 ramp rates per servo); resolution 8000 steps = 0.25 µs; UART 9600 baud; servo pulse range 0.5–2.5 ms; **dimension 49 mm × 46 mm**; free sample GUI (tested on Windows XP and 7, no support) [PP]. Protocol differs from SC16A [PP].
- No packing-list tab on the page [PP].
- **Resources:** User Manual (Google Drive PDF), Fritzing file, sample code for PIC16F877A, PIC18F4520 and SK40C, VB 2010 GUI project (GitHub), and tutorials (Arduino Due with SC08A/SC16A, XBee wireless servo controller, small robot gripper, GUI project 2) [PP].

## Interfaces, terminals and pin mapping
Board layout (manual chapter 4) [UM]:

| Label | Function |
|---|---|
| A | Servo motor power source connector (blue terminal block; called JP2 in section 5.2) |
| B | Servo motor channels — 8 channels × 3 header pins, "S" = signal; follow the labels printed at the top of each port |
| C | SC08A selection jumper **JP11**: "1-8" for a single board or the first board; "9-16" for the second board |
| D | Small orange LED — servo motor power present |
| E | Small green LED — 5 V for PIC operation |
| F | 4-way header pin and connector for UART communication (UC00A) / expansion — two of them, U_1 and U_2 |
| G | Servo test button — "the pulses generated will drive servos to the end of position" |
| H / I | Reset button and PIC16F1827 (the table and the description list swap these two labels) |

- **Reset button**: "Pressing this button will stop all pulses generation and return SC08A to initial stage"; "Without pulses generation, all servo connected to SC08A will not rotate, is free run" [UM].
- **UART connector**: the manual names TX, RX and 5 V sharing but never prints the pin order of the 4-way connector in text (figure only). Minimum 3 wires from the host; "A minimum of Transmit pin is required to send command to SC08A"; the SC08A TX pin is only needed for position reporting [UM]. TX/RX must be **cross-connected** (SC08A RX ← host TX, SC08A TX → host RX); "wrong connection will spoilt SC08A and worst the host or microcontroller" [UM].
- **Only one host** (computer or microcontroller) may be connected at a time [UM].
- **Expansion to 16 channels** [UM]: two SC08A, both set up per 5.1 (they may share a servo supply that can deliver the higher current); a separate 4-way interlink cable (polarity must be correct; "Do not use this cable to connect SC08A with microcontroller") joins either U_1 or U_2 of one board to the other; board 1 jumper at "1-8", board 2 at "9-16"; board 2's S1 is addressed as S9 (channels 9–16). The host UART cable goes to one board (which one is shown only in a figure).

UART protocol (manual 7.1) — first byte = 3 mode bits + 5-bit channel; channel 0 = all (1–8 on one board, 1–16 with two) [UM]:

| Command | Mode bits | Bytes sent | Reply |
|---|---|---|---|
| Activate / deactivate channel | `110` | 2: `110xxxxx`, then `0000000x` (bit 0: 1 = activate, 0 = deactivate) | none |
| Position and speed | `111` | 4: `111xxxxx`, position high 7 bits (`0xxxxxxx`), position low 6 bits (`00xxxxxx`), speed 0–100 | none |
| Position reporting | `101` | 1: `101xxxxx` (channel 0 ignored / not executed) | 2 bytes: high 7 bits, then low 6 bits |
| Starting position | `100` | 3: `100xxxxx`, position high 7 bits, position low 6 bits | 1 byte **0x04** |

- 13-bit position = (high byte & 0x7F) << 6 | (low byte & 0x3F) [UM].
- "The initial status for servo motor is deactivate" — the activate command must be sent before servos respond [UM].
- This command set is byte-for-byte the same as SHIELD-SERVO's; the shield's manual gives the same byte ranges (0xC0–0xC8, 0xE0–0xE8, 0xA1–0xA8, 0x80–0x88) [UM-SHIELD-SERVO, cross-reference only].

## Rules and gotchas (for code, wiring and tutorials)
- No datasheet — cite "SC08A Servo Controller User's Manual V1.0, June 2011" [UM].
- **No on-board regulator**: the servo supply on the blue terminal block goes to the servos as-is. Use 4.8–6 V unless the servo is rated higher; the manual warns that over-voltage spoils servos [UM]. (Contrast: SHIELD-SERVO regulates 7–25 V down to 5 V.)
- **Connect servo power correctly before plugging in servos**: "else all servo motor will be damaged" [UM]. Servo headers are not polarised — a servo can be plugged in backwards; "ENSURE the connection of servo is correct; else the servo may destroyed" [UM].
- The controller needs its own 5 V: from UC00A when used with a PC, or shared from the host board when used with a microcontroller [UM]. The manual does not say the servo supply can power the PIC.
- JP11 mini jumper must be at "1-8" for single-board use [UM].
- Resolution for code: use **0.25 µs** per step (0 = 0.5 ms, 8000 = 2.5 ms). The 0.5 µs figure printed in the protocol section contradicts the pulse range [UM] — see Conflicts.
- Speed byte **0 = fastest**, 1 = slowest, 100 = fast but slower than 0 [UM].
- Position report on channel 0 is not executed; it needs the SC08A TX wire connected to the host RX [UM].
- **Do not use speed 0 with position reporting:** the Cytron Arduino sketch says speed 0 makes the servo oscillate in position-reporting operation "due to limitation of software position feedback" — use speed 1–100 there [GH].
- **Arduino UNO hardware UART is shared with USB upload** (D0/D1): the Cytron sketches use it for SC08A, so the SC08A link is on the same pins the board uses for uploading [GH].
- Reset stops all pulses; servos go free-running until re-activated and commanded [UM].
- Never connect PC and microcontroller hosts at the same time; never use the expansion cable as the host cable [UM].
- When two boards are linked, add **8** to the channel number for the second board (S1 → S9). The manual's sentence "Every label should be added with 16" is an error — see Conflicts [UM].
- Test button drives servos to their end position — keep mechanisms clear before pressing [UM].

## Power and electrical limits
- Controller logic: 5 V (from UC00A or host) [UM]. Current draw not stated.
- Servo supply: independent, typically 4.8–6 V (some servos 7.2 V); section 5.1 range "4.8V to 9V" [UM]. Board maximum voltage and current for the terminal block are **not stated**; the only limit is the warning that over-voltage damages servos.
- Polarity: "check the polarity before plug in" — no reverse-polarity protection is mentioned [UM].
- UART is TTL (5 V) [UM]; 3.3 V compatibility not stated.
- Whether logic ground and servo ground are common is not stated in text [UM].

## Software support
- **Protocol**: raw UART bytes at 9600 baud (table above); there is no Arduino library for SC08A, only sample sketches [UM][GH]. The SHIELD-SERVO Arduino library uses the same command bytes but targets the shield.
- **Arduino sample sketches** [GH] — `CytronTechnologies/Arduino_SC08A` (README last updated Aug 2015; hardware: Arduino UNO or CT-Uno): "SC08A_Arduino_without_position_reporting" and "SC08A_Arduino_with_position_reporting". Both use the hardware `Serial` port (D1 = TX to SC08A RX; D0 = RX from SC08A TX, needed only for position reporting and the starting-position reply) at 9600 baud, send activate-all (`0xC0`, then `1`) in `setup()`, wait for a button on D12 to be pressed and released, then move all 8 channels between positions 7300 and 400 at speed 50 (LED on D13 shows which end). Helper functions: `on_off_motor(channel, on)` → `0xC0|ch, on`; `set_ch_pos_spd(channel, position, speed)` → `0xE0|ch, (pos>>6)&0x7F, pos&0x3F, speed`; `rd_current_pos(channel)` → sends `0xA0|ch`, reads 2 bytes, returns `(high<<6)|low`; `initial_position(channel, position)` → `0x80|ch, high, low`, then waits for the reply byte `0x04`. The README links the tutorial "Interfacing servo motors controllers (SC08A and SC16A) using Arduino" (tutorial.cytron.com.my, 2012).
- **PIC sample code** [UM][GH]: `SK40C_16F877A_SC08A.c` / `.hex`, PICC Lite, PIC16F877A on an SK40C (also works on PIC16F876A); SW1 activates all channels, SW2 sweeps every servo left-right-left. GitHub `CytronTechnologies/SC08A_PIC16F877A` holds folders "SC08A_Sample Code" (Feb 2011) and "SK40C_16F877A_SC08_Apr14" (Apr 2014) [GH].
- GitHub `CytronTechnologies/SC08A_PIC18F4520`: "Sample Code 18F4520 + SC08A May 2012" [GH].
- **PC GUI** "SC08A Servo Control Panel" (8 or 16 servo): search/refresh COM ports, connect/disconnect, "Active 8 Servo" / "Active 16 servo", per-servo A (activate) / D (deactivate), position slider, position/pulse/speed values, "Reset_Servo_Initial Position" tab with Send and RESET; shortcut named "SC08A VB project1" [UM]. GitHub `CytronTechnologies/GUI_SC08A`: "SC08A Sample GUI + Project File (VB 2010 Express) July 2012", with a tutorial "Wireless servo controller using XBee" (SC08A + XBee series 1 + SKXBee) [GH].
- PC connection uses UC00A; the driver installs automatically on first use (Windows 7 in the manual) and creates a virtual COM port, usually the highest-numbered one [UM].
- Not supported / not described: I2C, SPI, PWM input, RC receiver input, baud-rate change [UM].

## Compatibility and accessories
- Hosts: PC via UC00A USB-to-UART; any microcontroller with 5 V TTL UART (examples: SK40C with PIC16F877A/PIC16F876A, PIC18F4520, Arduino UNO / CT-Uno) [UM][GH].
- Wireless: XBee series 1 on SKXBee with the GUI (tutorial) [GH].
- Second SC08A for channels 9–16 via a 4-way interlink cable [UM].
- Packing list: 1 × SC08A main board, 1 × 2510H-04 connector (with terminal pins), 1 × 2561-04 connector (with terminal pins), 1 × mini jumper for JP11; manual and software are downloads [UM].
- Servo named in the manual: Cytron C36S (speed table) [UM].

## Common mistakes / troubleshooting
- **Servos do nothing** — channels are deactivated at power-up; send the activate command (mode `110`, 2nd byte 0x01) first [UM].
- **Orange LED off** — servo supply not connected or wrong polarity on the blue terminal block [UM].
- **Green LED off** — no 5 V to the PIC: UC00A not plugged in, or host 5 V not shared [UM].
- **No response** — TX/RX not crossed, baud not 9600, or two hosts connected [UM].
- **Position report never arrives** — SC08A TX not wired to host RX, or channel 0 used [UM].
- **Second board ignores commands** — JP11 not at "9-16", or channel numbers not offset by 8 [UM].
- **Servo destroyed** — plugged in backwards (headers are not polarised) or servo supply over-voltage [UM].
- **Servos go limp after reset** — expected: reset stops all pulses and servos free-run; re-activate [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Resolution | [UM] introduction and formula: 8000 steps = 0.25 µs | [UM] protocol section: 0.5 µs | 0.25 µs × 8000 = 2.0 ms span, matching 0.5–2.5 ms; 0.5 µs would give 4.5 ms. Use **0.25 µs**; 0.5 µs is a typo |
| Second-board channel offset | [UM] example: S1 on board 2 = S9 (offset 8) | [UM] sentence: "Every label should be added with 16" | Offset **8** is consistent with 16 channels total; "16" is an error |
| Expansion heading | [UM] index: "5.4 Expanding SC08A for 32 Channels" | [UM] section heading: "16 Channels" | 16 channels (two boards); "32" is an index typo |
| Speed table value 1 | [UM]: speed 1 = "2.0 minutes" | [UM] rest of table: 16 → 14 s, 0 → 0.3 s | Inconsistent with the monotonic trend; do not quote the "2.0 minutes" figure as a spec |
| Speed byte description | [UM]: "0-100", 1 slowest, 100 fastest | [UM]: value 0 "more faster than value '100'" | Both are in the manual: 0 is the special full-speed value; 1–100 scale slow → fast |
| Board layout labels H/I | [UM] table: H = reset button, I = PIC16F1827 | [UM] description list: H = PIC16F1827, I = reset button | Labels swapped between table and text; both items exist |
| Blue terminal block label | [UM] chapter 4: label "A" | [UM] 5.2: "JP2" | Same connector |
| Warranty | [UM] chapter 8: 6 months | [PP]: 12 months | Product page is the current commercial term (2026-10-16); manual (2011) is older; record both |
| Servo supply range | [UM] 5.1: "4.8V to 9V (standard is 4.8V to 6.0V)" | [UM] chapter 3: "between 4.8V and 6V. Some may need 7.2V" | Both are statements about servos, not a board limit; the board's own maximum is not stated |

## Needs verification
- Full verbatim text of the manual — read via a summarising fetcher from a reseller mirror; figures (connector pin order, board photo, wiring diagrams) not readable. Re-read the Cytron Drive PDF when accessible.
- Pin order of the 4-way UART/expansion connectors (which pin is 5 V, GND, TX, RX) and whether the two 4-way headers are electrically identical.
- Servo header pin order (S / + / −) and labelling S1–S8.
- Board maximum servo-supply voltage and current rating of the terminal block / PCB traces.
- Whether servo ground and logic ground are common.
- Pulse refresh rate (frame period).
- Whether the baud rate can be changed (only 9600 is stated).
- Behaviour on UART loss, and whether the stored start-up position moves the servo at power-up before activation.
- Board revision / hardware revision history — not stated anywhere read.
- Board weight — not stated (size 49 × 46 mm is from the product page).
- Re-read the user manual from the Cytron Drive PDF (linked from the product page) to replace the reseller-mirror reading — no copy is in the team reference folder yet (checked 2026-10-21).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Quadruped Robot with SC08A Servo Controller](https://my.cytron.io/tutorial/quadruped-robot-with-sc08a-servo-controller) — Tutorial, Advanced, 2022 [PP: tutorial]

## Sources
- [UM] "SC08A SERVO CONTROLLER — User's Manual", V1.0, June 2011, Cytron Technologies Sdn. Bhd. — read from the reseller mirror https://www.gotronic.fr/pj2-38783-nt-3349.pdf (Cytron's own copy, linked from the product page, is https://drive.google.com/file/d/0BzFWfMiqqjyqem1oQnlXUk4yaXc/view — not readable here)
- [PP] Product page (read by the coordinator 2026-10-16; not fetched here) — https://my.cytron.io/p-8-channel-servo-controller
- [GH] PIC16F877A sample code README — https://raw.githubusercontent.com/CytronTechnologies/SC08A_PIC16F877A/master/README.md
- [GH] PIC18F4520 sample code README — https://raw.githubusercontent.com/CytronTechnologies/SC08A_PIC18F4520/master/README.md
- [GH] GUI README — https://raw.githubusercontent.com/CytronTechnologies/GUI_SC08A/master/README.md
- [GH] Arduino sample sketches (README + 2 sketches, read 2026-10-21) — https://github.com/CytronTechnologies/Arduino_SC08A
- Cross-reference only: SHIELD-SERVO User's Manual V1.1 (same protocol) — https://docs.google.com/document/d/191P6FwTgJ_dWhAhB3eWfP0YMSbI4_7Kehgzw3pYy-AY/view
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
