# Enhanced SmartDrive40 (MDS40B) — Verified Reference

| | |
|---|---|
| Product code | `MDS40B` (user manual title page and product page "Product Code") [UM][PP] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. In stock on my.cytron.io; the page matches the earlier www.cytron.io read and links the user manual publicly |
| Primary source | "Enhanced SmartDrive40 MDS40B User's Manual" — **Rev 1.1, July 2023** (Google Doc): https://docs.google.com/document/d/1WtfqfUlUlLCjGR_q33lZQt5xLPtft4zG0jJk5PX1A8Y/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: **No separate datasheet exists** for MDS40B; the User's Manual (which contains the "Absolute Maximum Rating" table) is the primary source [UM]. Rev 1.1 (July 2023) was read in full as text via Google Drive. The older Rev 1.0 (December 2015) PDF on the RobotShop CDN was read through a text-extraction tool only (direct download blocked) and is used to note revision differences. Manual figures (board layout photo, connection diagrams) are images and were not read. Product page read at **www.cytron.io** (my.cytron.io fetch failed). No [DT] confirmation exists.

## What it is
A single-channel brushed DC motor driver for medium to high power motors: 10–45 V motor supply, 40 A continuous and 80 A peak (must not exceed 1 second), MOSFETs switched at 16 KHz [UM]. An onboard microcontroller provides five input modes — RC, Analog, PWM, Simplified Serial and Packetized Serial — selected with an 8-position DIP switch, plus current limiting and thermal protection [UM]. It drives **one** motor; a differential-drive robot uses two units, one set to Mixed Left and one to Mixed Right [UM][PP]. It has **no reverse polarity protection** [UM][PP].

Manual framing of uses [UM]: RC mode — "standard hobby radio control transmitter and receiver, or a microcontroller generating the similar signal"; Analog mode — "the motor can be controlled by a joystick or foot pedal with potentiometer"; PWM and serial modes — microcontroller control; Mixed modes — "driving a robot with differential drive a truly plug and play experience".

## Specifications
User manual section 3 table is titled **"Absolute Maximum Rating of Enhanced SmartDrive40"** [UM].

| Item | Value | Src |
|---|---|---|
| Input Voltage (Motor Supply Voltage) | Min 10 V, Max 45 V | [UM] |
| IMAX (Maximum Continuous Motor Current) | Max 40 A — footnote "* Depends on the room temperature." | [UM] |
| IPEAK (Peak Motor Current) | Max 80 A — footnote "** Must not exceed 1 second." | [UM] |
| VIOH (Logic Input – High Level) | Min 1.3 V, Max 5 V | [UM] |
| VIOL (Logic Input – Low Level) | Min 0 V, Max 0.7 V | [UM] |
| 5V Output Current | Max 500 mA | [UM] |
| Dimension | Field present in the manual but **blank** | [UM] |
| Dimensions (product page) | "105mm (W) x 106mm(D) x 38mm(H) - Actual driver board"; "125mm (W) x 107mm (D) x 47mm (H) - together with the base" | [PP] |
| Motor channels | 1 ("Motor Channel: 1"; "Bi-directional control for a single brushed DC motor.") | [PP] |
| MOSFET switching frequency | 16 KHz | [UM] |
| Compatible input (product page) | "3.3 and 5V compatible input" | [PP] |
| PWM (Lock-Antiphase and Sign-Magnitude) | Yes | [PP] |
| RC servo signal | Yes | [PP] |
| Polarity protection | No | [UM][PP] |
| Current / thermal protection | Yes | [UM][PP] |
| Cooling fan | "No" (optional 5 V fan can be connected) | [PP][UM] |
| Warranty | 12 months, manufacturing defects only | [UM][PP] |
| Price (product page) | RM346.50, availability 113 (my.cytron.io, read 2026-10-19); www.cytron.io $62.50 ex tax (2026-10-16) | [PP] |
| Packing list | 1 × Enhanced SmartDrive40 with top and bottom cover; 2 × 2561 Servo Extension cable | [UM] |
| Operating temperature | Not stated | — |
| Weight | Not stated | — |
| Terminal wire size | Not stated in [UM] ("use wire with proper thickness to support the expected current"); product page recommends Multicore Wire AWG14 | [UM][PP] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read on my.cytron.io: Enhanced SmartDrive40 (MDS40B), improved MDS40A; single brushed DC motor; 10–45 V; regenerative braking; 80 A peak reducing to 40 A by temperature; 16 kHz switching; **NO reverse polarity protection**; LiPo low-voltage warning; thermal protection; current limiting by temperature; input modes RC, Analog, PWM, Simplified Serial, Packetized Serial; push button; 105 × 106 × 38 mm board, 125 × 107 × 47 mm with base; over-voltage protection; optional fan; pairs with a second unit for differential drive; AWG14 multicore wire recommended [PP].
- **Resources:** MDS40B 3D CAD, User's Manual (Google Doc — the same document as the KB's Rev 1.1, linked from the official page), CytronMotorDriver library, Fritzing part [PP].

## Interfaces, terminals and pin mapping
Board layout (UM section 4) [UM]:

| Label | Function |
|---|---|
| A | Power Supply Terminal block — "No polarity protection, please double check before power up." Screw terminal or solder to bottom-layer pad |
| B | Motor Terminal Block — screw terminal or solder to bottom-layer pad |
| C | Motor LED Indicator — "If LED A turns on, means current flows from output A to B. Vice versa." |
| D | Fan Connector — "for an optional 5V cooling fan. It's permanently connected to the 5V and there is no speed control available for the fan." |
| E | Analog/PWM/Serial Input Terminal Block (pins below) |
| F | RC Input Pin — "RC1 for forward/reverse and RC2 for steering." |
| G | Reset Button ("RST") |
| H, I | Motor Test Buttons — "If A is pressed, current flows from output A to B. Vice Versa." (speed not stated) |
| J | Run LED — on when motor is running |
| K | Error (ERR) LED — blink codes below |
| L | Mode Selection DIP Switch (8 positions) |
| M | Power Switch Terminal Block — "Switch for power up MDS40B's microcontroller and logic circuit. This switch is ON by default." |

Analog/PWM/Serial input terminal block [UM]: 1 = GND; 2 = 5V ("+5V output. **Do not** connect to another 5V source."); 3 = IN1 (Input 1); 4 = IN2 (Input 2).

Error LED [UM]: Off = no error; 2 blinks = Input Error ("Invalid or no input detected."); 3 = Under Voltage ("The battery voltage is low."); 4 = Over Voltage ("Supply voltage is over the limit. MDS40B will not operate."); 5 = Over Temperature ("Board temperature is high.").

DIP switch modes (0 = OFF/Down, 1 = ON/Up) [UM]:

| Mode | SW1–SW3 | Other switches |
|---|---|---|
| RC | SW1:SW2 = 00 | SW3:SW4 = 00 Independent / 10 Mixed Right / 11 Mixed Left; SW5 Exponential (0 linear, 1 exponential); SW6 MCU Mode |
| Analog | SW1:SW2 = 01 | SW3:SW4 single/mix as RC (Mixed modes: SW8 must be 0); SW5 Exponential; SW6 Sign-Magnitude (0 Locked Anti-Phase, 1 Signed Magnitude) |
| PWM | SW1:SW2 = 10 | As Analog; input is low-pass filtered to analog |
| Simplified Serial | 110 | SW4–SW6 baud: 000 = 1200, 001 = 2400, 010 = 4800, 011 = 9600, 100 = 19200, 101 = 38400, 110 = 57600, 111 = 115200 |
| Packetized Serial | 111 | SW4–SW6 = address 0–7 |

SW7 is not described anywhere in the manual; SW8 is mentioned only as "must be set to 0" in Analog/PWM Mixed modes [UM].

Manual example DIP strings (positions 1–8) [UM]: RC Independent `00000000`; RC Mixed Right `00100100`; RC Mixed Left `00110100`; Analog joystick (Mixed) `01110000` and `01100000`; PWM with microcontroller (Independent Both) `10000100`; Simplified Serial 9600 bps `11001100`; Packetized Serial address 0 `11100000`.

## Rules and gotchas (for code, wiring and tutorials)
- **One motor per board.** Two motors need two MDS40B units (product page Q&A: "it can control for a single brushed DC motor only") [PP]. Mixed Right "should be selected for the right motor of the robot differential drive system"; Mixed Left for the left motor [UM].
- Peak is **80 A, must not exceed 1 second**; 40 A continuous depends on room temperature [UM].
- **Mode is read only at power-up.** After changing the DIP switch, press "RST" or power cycle [UM].
- **Stop signal at power-up:** in RC, Analog and PWM modes the input must be "stop" when powered, or the driver shows Input Error (2 blinks) — this prevents sudden run after an accidental reset [UM]. Analog/PWM stop = 2.5 V (Sign-Magnitude off) or 0 V (Sign-Magnitude on) [UM].
- **RC:** the transmitter must be ON before powering the driver [UM]. MCU Mode off (SW6 = 0): centre calibrated at power-up; signal lost for 100 ms → motor stopped. MCU Mode on (SW6 = 1): centre fixed at 1.5 ms, timeout disabled, motor "will continue to run with previous speed if new signal is not detected" — intended for a microcontroller sending single pulses [UM].
- The manual's RC Mixed Right/Left example strings have SW6 = 1 (MCU Mode on, no timeout) even when shown with an RC receiver — check SW6 deliberately for receiver use [UM].
- **Independent mode:** "controlled by a single RC channel connected to Input 1 … Input 2 is not used" [UM].
- **Locked Anti-Phase** (SW6 = 0): stop at 2.5 V, direction by < or > 2.5 V; recommended for the joystick breakout board [UM]. **Signed Magnitude** (SW6 = 1): Input 1 = speed (0 V stop, 5 V full), Input 2 = digital direction; SW2 must be 0 [UM].
- Valid analog/PWM input range is 0–5 V [UM]. PWM input frequency range is **not stated** [UM].
- Cytron's Arduino library lists MDS40B under the PWM_DIR example and says Smart series drivers "need to be configured as Sign-Magnitude PWM Input mode" [GH] (manual example `10000100`).
- **Simplified Serial:** Input 1 = UART Rx, Input 2 = Slave Select; one byte: 127 stop, 0 full reverse, 255 full forward [UM].
- **Packetized Serial:** 4 bytes — Header 85 (0x55), Address 0–7 (must match DIP), Command (127 stop, 0 full reverse, 255 full forward), Checksum = Header + Address + Command [UM]. Auto-baud: send header 0x55 once after power-up; baud is then fixed until power cycle or reset. Allow a **one-second delay** after power-up (start-up can take up to 500 ms); error LED blinks while waiting for the header. Up to 8 units on one UART Tx pin [UM].
- Mixed-mode wiring: each terminal block to the same-side motor; if a motor runs the wrong way, reverse its polarity at the terminal block [UM]. "Left/Right is just for reference only" [UM].
- Do not connect the 5V output to another 5 V source [UM].

## Power and electrical limits
- Supply 10–45 V absolute maximum [UM]. Recommended sources (Rev 1.1): 9–18 cells NiMH/NiCd ("can up to 30 cells, but the battery low voltage warning only works for up to 18 cells"); 3–6 cells LiPo/Li-Ion ("can up to 10 cells, but … only works for up to 6 cells"); 10–45 V sealed lead acid; 10–45 V power supply "**Must be in parallel with a battery with same voltage**" [UM].
- **No reverse polarity protection** on the motor supply — stated in features, power section and safety note [UM][PP].
- **Regenerative current:** with a supply that cannot sink current ("bench top and AC to DC switching power supply"), input voltage rises while the motor slows; connect a same-voltage battery in parallel, "Else, the input voltage might rise to a level where Enhanced SmartDrive40 will be destroyed permanently or the power supply trigger protection mode." [UM]
- **Over voltage:** > 45 V → driver will not operate (4 blinks) [UM].
- **Under voltage is a warning only:** cell count detected at power-on; for LiPo, below 3.0 V per cell the ERR LED blinks but "the power to the motor will be maintained and will not be cut out" — the user must stop and replace the battery. Warning also shows for NiMH/NiCd/SLA; user judges replacement [UM].
- **Over temperature:** duty cycle reduced by board temperature — < 50 °C: 80 A; 50–70 °C: 50 A; 70–100 °C: 45 A; 100–110 °C: 40 A; > 110 °C: 35 A (5 blinks) [UM].
- Heatsink: not mentioned [UM]. Fan: optional 5 V fan on the fan connector, always on [UM]; product page says adding a fan gives "better heat dissipation, further increase maximum continuous current" (no figure) [PP].
- Power Switch Terminal Block powers the microcontroller and logic; ON by default [UM]. Product page: it can deactivate the driver, "eliminating the need for high power switch" [PP].
- 5 V output 500 mA max [UM]; product page says 5 V is from a switching regulator [PP].

## Software support
- No firmware updates, configuration software or serial protocol beyond the manual are published.
- Arduino: `CytronMotorDriver` library ("Cytron Motor Drivers Library", v1.0.1) — `CytronMD motor(PWM_DIR, 3, 4);` example lists MDS40B as compatible in Sign-Magnitude PWM Input mode [GH].
- Serial modes are byte-level UART (Simplified: 1 byte; Packetized: 4 bytes with auto-baud) — no official library example for them found [UM].
- Product page lists a "Fritzing Part" download [PP].

## Compatibility and accessories
- Logic inputs: VIOH 1.3–5 V, VIOL 0–0.7 V [UM]; product page: "3.3 and 5V compatible input"; Q&A confirms 3.3 V IO for PWM and that input pins are pulled up (NPN optocouplers usable) [PP].
- RC receiver header (RC1, RC2) and 2 × 2561 servo extension cables included [UM].
- Cytron joystick breakout board (BB-PSJ) suggested for Analog Locked Anti-Phase mode [UM].
- Product page Q&A: the onboard current sensor is not accessible [PP].
- Recommended wire: Multicore Wire AWG14 Red/Black [PP].
- Product page positioning: "After the success of MDS40A and with feedback from users, we have improved it"; enhanced features listed: increased Vin range up to 45 VDC; "Responsive current limiting sensor and algorithm"; "High Ampere screw terminals for both battery and motor connection"; additional terminal to activate/deactivate the driver; switching regulator for 5 V; option to add a fan; "Ready header for RC receiver connection"; "Protection of over voltage" [PP].

## Common mistakes / troubleshooting
- **2 blinks at power-up** — input not at stop (RC transmitter off, stick not centred, analog not at 2.5 V/0 V) or, in Packetized Serial, header byte not yet sent [UM].
- **3 blinks** — low battery warning; motor is **not** cut off — stop and replace/charge the battery [UM].
- **4 blinks** — supply > 45 V, often regeneration on a bench or switching supply with no parallel battery [UM].
- **5 blinks / reduced power** — board hot; current limit derated to as low as 35 A above 110 °C [UM].
- **DIP change ignored** — press RST or power cycle [UM].
- **Robot keeps running after signal loss** — SW6 (MCU Mode) is ON; turn it OFF for 100 ms timeout with an RC receiver [UM].
- **Packetized Serial no response** — header sent within start-up (< 1 s); address bits not matching DIP; wrong checksum [UM].
- **Board destroyed at power-up** — reversed supply; there is no polarity protection [UM].
- **Expecting two motors from one board** — it is single channel [PP].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Number of motors | [UM] feature bullet: "Bi-directional control for dual brushed DC motor." | [PP]: "Motor Channel: 1", "single brushed DC motor"; [UM] body: one Motor Terminal Block, Independent mode uses Input 1 only, Mixed Right/Left chosen per motor | **One motor per board.** The UM bullet conflicts with the UM's own mode descriptions; content must say single channel |
| Peak current duration | [UM]: 80 A, "Must not exceed 1 second" | [PP]: "80A peak, reduce to 40A gradually according to temperature" (no duration) | UM wins: **80 A for ≤ 1 s** |
| NiMH/NiCd cell range | [UM] Rev 1.0 (Dec 2015): 6–18 cells | [UM] Rev 1.1 (Jul 2023, newer): 9–18 cells (up to 30 cells, warning only to 18) | Use Rev 1.1 (newer revision of the same manual) |
| Fan connector | [UM] Rev 1.0: "Fan Input Pin", no description | [UM] Rev 1.1: optional 5 V fan, permanently on, no speed control | Rev 1.1 adds detail; no conflict in substance |
| Fan increases continuous current | [UM]: not stated | [PP]: "further increase maximum continuous current" | No figure in any source; do not quote a number |
| Number of input modes | [UM] §8: "four different types of input mode (RC, Analog, PWM and Serial)" | [UM] features/[PP]: five (Simplified and Packetized Serial counted separately) | Same content counted differently; say five modes |
| Packetized Serial Rx pin name | [UM] §8.4: "DIG1 pin is the UART Rx pin. DIG2, AN1 and AN2 pins are not used" | [UM] terminal block labels are IN1/IN2; §8.3 says Input 1 is Rx | Label naming error in both revisions; likely IN1 — see Needs verification |
| OC LED | [UM] §8: "RUN LED, ERR LED and OC LED will running once" at power-up | [UM] board layout lists no OC LED | Unresolved; do not describe an OC LED |
| Regenerative braking | [PP] lists "Regenerative Braking." | [UM]: not listed as a feature | Product-page claim only |

## Needs verification
- Which terminal is the Packetized Serial Rx pin (manual says "DIG1"; board labels IN1/IN2).
- Whether an OC LED exists on the board.
- Checksum overflow handling (whether only the low 8 bits of Header + Address + Command are used).
- Maximum PWM input frequency in PWM mode, and filter characteristics.
- Test-button motor speed; function of SW7.
- Operating temperature range, weight, terminal wire-size rating.
- Size of current increase from an optional fan; fan current limit on the 5 V output.
- Exact contents of the Rev 1.0 PDF beyond the items listed (read via text extraction only).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Controlling SmartDrive40 Using 3.3V Microcontroller (Serial Simplified Mode)](https://my.cytron.io/tutorial/controlling-smartdrive40-using-3-3v-microcontroller) — Tutorial, Intermediate, 2025 [PP: tutorial]

## Sources
- [UM] MDS40B User's Manual, Rev 1.1, July 2023 (Google Doc) — https://docs.google.com/document/d/1WtfqfUlUlLCjGR_q33lZQt5xLPtft4zG0jJk5PX1A8Y/edit
- [UM] MDS40B User's Manual, Rev 1.0, December 2015 (PDF mirror, public) — https://cdn.robotshop.com/media/c/cyt/rb-cyt-179/pdf/mds40b_user_s_manual.pdf
- [PP] Product page, "40Amp 10V-45V SmartDrive DC Motor Driver" (read 2026-10-16) — https://www.cytron.io/p-40amp-10v-45v-smartdrive-dc-motor-driver
- [GH] CytronMotorDriver README — https://raw.githubusercontent.com/CytronTechnologies/CytronMotorDriver/master/README.md
- [GH] PWM_DIR example — https://raw.githubusercontent.com/CytronTechnologies/CytronMotorDriver/master/examples/PWM_DIR/PWM_DIR.ino
- [3P] Opencircuit listing (cross-check; carries the Rev 1.1 manual link) — https://opencircuit.shop/product/40amp-10v-45v-smartdrive-dc-motor-driver
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
