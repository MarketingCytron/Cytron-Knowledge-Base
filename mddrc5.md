# MDDRC5 — Verified Reference

| | |
|---|---|
| Product code | `MDDRC5` (datasheet title [DS]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read directly (earlier page facts were relayed). Sale status, packing list, 69 × 35.5 mm, 2S–6S LiPo and the firmware-update and getting-started tutorials are now read; the < 5 s vs < 1 s peak-duration conflict remains |
| Primary source | MDDRC5 Datasheet — "5 Amp 7V-30V DC Motor Driver for R/C (2 Channels)" — **Rev 1.0, March 2026** (Google Doc): (Cytron document — link not public) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: my.cytron.io returned an error, so the product page was **not read** directly. Product-page facts below come from Cytron's internal summary `hardware-mddrc5.md` (read 2026-09-08 by its author), tagged **[PP]**. No separate user manual exists; no [DT] confirmation exists. The datasheet was read as text: its figures (Figure 1 board layout, Figure 2 dimension drawing, Figure 3 connection diagram, Figure 4 RC Tx input vs robot movement) are images and could **not** be read. Do not confuse with the older, larger **MDDRC10** (10 A).

## What it is
A dual-channel DC motor driver controlled directly from an R/C receiver. It drives two DC motors from a 7–30 V supply at up to 5 A continuous / 20 A peak per channel (peak < 1 s, limited by over-current protection) [DS]. RC1/RC2 inputs work in Independent Mode or Mixed Mode, chosen with an onboard mode selection switch; Mixed Mode is preferred for differential-drive mobile robots [DS]. It has an onboard RP2040 microcontroller (datasheet chapter 8 "RP2040 Pin Mapping"), a USB-C port for firmware updates, BOOT/RESET buttons for BOOTSEL (UF2) mode, a test button, motor alignment potentiometers, a 5 V / 500 mA output for the receiver, and status/error/OC LEDs [DS].

## Specifications
Datasheet Table 2 is titled **"MDDRC5 Absolute Maximum Ratings"** — these are absolute limits, not recommended operating points [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 7 V, Max 30 V | [DS] |
| Maximum motor current (per channel), continuous | Max 5 A | [DS] |
| Maximum motor current (per channel), peak | Max 20 A — "supported for less than 1 seconds and is limited by the overcurrent protection circuit" (footnote *¹) | [DS] |
| Peak current duration (product page) | 20 A peak "less than 5 seconds" — conflicts with [DS]; datasheet wins | [PP] |
| Motor output PWM frequency | 20 kHz (table gives a single value) | [DS] |
| RC input voltage (RC1 & RC2), low level | 0 – 0.7 V | [DS] |
| RC input voltage (RC1 & RC2), high level | 1.5 – 15 V | [DS] |
| RC signal timing, frequency | 10 – 100 Hz | [DS] |
| RC signal timing, deadband | ±35 µs | [DS] |
| RC signal timing, fullscale | ±435 µs | [DS] |
| 5V output maximum current | 500 mA ("5V output for RC receiver… do not use this to power the servo motor") | [DS] |
| Number of motor channels | 2 | [DS] |
| OC current-limit threshold | 20 A | [DS] |
| Microcontroller | RP2040 (pin-map chapter title) | [DS] |
| Footprint (product page) | 69 × 35.5 mm | [PP] |
| Operating temperature | Not stated | — |
| Weight | Not stated | — |
| Terminal type / wire size | Not stated | — |
| Neutral (centre) pulse width | Not stated (deadband/fullscale given only as ± values) | — |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Page notes:** "200 units sold out within 1 hour after launch!"; "Please update your MDDRC5 to the latest firmware before use" — Firmware Update Guide (Cytron tutorial `mddrc5-firmware-programming`) [PP].
- **Story/positioning:** for 500 g RC mini-sumo (All Japan Robot Sumo Tournament opened the 500 g class to international entrants in 2024); smaller version of MDDRC10 [PP].
- **Key features:** 5 A continuous, 20 A peak per channel; **69 × 35.5 mm**; motor alignment potentiometers (forward/reverse balance); test buttons; USB-C to update firmware or reprogram the onboard controller; Independent / Mixed mode slide switch; 7–30 V, **2S to 6S LiPo**; LEDs for power, motor outputs and errors [PP].
- **Technical specifications:** 7–30 V; 2 channels; 5 A continuous; **20 A peak (less than 5 seconds)**; RC PWM input; protection: reverse polarity, overcurrent (with LED), thermal shutdown [PP].
- **Packing list:** 1x MDDRC5, 2x 10 cm 3-way connector extension wire, 4x 7 mm nylon PCB spacer, 1x 2 mm flat-head screwdriver [PP].
- **Resources:** datasheet (Google Doc), CAD, Getting Started tutorial [PP].

## Interfaces, terminals and pin mapping
Board functions (datasheet Table 1) [DS]:
- **Power input terminal** — connect to the battery. V+ positive, V- negative.
- **USB-C port** — "Used for firmware updates." Product page adds it can upload custom code [PP].
- **Motor output terminals** — one per motor; rotation direction depends on polarity. Swapping MxA and MxB reverses rotation.
- **Motor status LEDs** — on when the motor runs: MxA = Forward*, MxB = Backward* (*actual direction depends on motor wiring).
- **Power LED** — on when the board is powered.
- **Error LEDs** — blink when an error is detected (codes below).
- **OC (Overcurrent) LEDs** — on while current limiting is active; threshold 20 A.
- **Test button** — motors run at half speed. Single press and hold: both motors forward. Double press and hold: both motors backward.
- **Boot and Reset buttons** — BOOTSEL: hold BOOT, press and release RESET, release BOOT; board appears as **RPI-RP2** USB mass storage.
- **Mode selection switch** (label IND/MIX) — Independent or Mixed Mode.
- **Motor alignment potentiometers** (FWD and REV) — compensate for left/right motor differences so the robot drives straight.
- **RC input** — RC1/RC2 signal; +5V output for the receiver (500 mA max, not for servos); GND.

Channel mapping [DS]:

| Mode | RC1 (Channel 1) | RC2 (Channel 2) |
|---|---|---|
| Independent | Left motor speed and direction | Right motor speed and direction |
| Mixed | Forward/backward speed | Turn left/right (mixed internally to both motors) |

Error LED codes (datasheet Table 4) [DS]:

| ERR LED blinks | Meaning |
|---|---|
| 2 | RC Input Error — no RC signal detected, or pulse width out of acceptable range |
| 4 | Overvoltage Error — input exceeded the maximum rating (see switching-supply note below) |

RP2040 pin mapping (datasheet chapter 8) [DS]:

| Function | Board label | RP2040 pin | Direction |
|---|---|---|---|
| RC channel 1 | RC1 | GP1 | Input |
| RC channel 2 | RC2 | GP0 | Input |
| Test button | TEST | GP3 | Input |
| Mode selection switch | IND/MIX | GP24 | Input |
| Error LED, left motor | ERR1 | GP7 | Output |
| Error LED, right motor | ERR2 | GP9 | Output |
| Battery voltage sensor (voltage divider) | — | GP29 | Input |
| Motor alignment pot | FWD | GP26 | Input |
| Motor alignment pot | REV | GP27 | Input |
| Left motor PWM / Direction / Sleep / Fault | — | GP11 / GP10 / GP12 / GP13 | Out / Out / Out / In |
| Right motor PWM / Direction / Sleep / Fault | — | GP20 / GP21 / GP18 / GP17 | Out / Out / Out / In |

OC LED, power LED and motor status LED pins are not in the pin map [DS].

## Rules and gotchas (for code, wiring and tutorials)
- Peak is **20 A for < 1 s** (datasheet). Do not write "< 5 s" — that figure is only on the product page [DS][PP].
- 5 A is **per channel**, continuous [DS].
- The 5V pin on the RC header is for the **receiver only** — 500 mA max, never power a servo from it [DS].
- RC1 = GP1 and RC2 = GP0 — the GPIO order is reversed relative to the labels [DS].
- Mixed Mode: RC1 = forward/backward, RC2 = left/right. Independent Mode: RC1 = left motor, RC2 = right motor [DS].
- Mixed Mode is the preferred mode for differential-drive mobile robots; Independent Mode is "usually used for non-wheeled motors or when you want to control the motor independently" [DS].
- RC signal must be 10–100 Hz; out-of-range or missing pulses give the 2-blink RC Input Error [DS].
- Motor status LED "Forward/Backward" labels follow the terminal, not the real shaft direction — fix direction by swapping MxA/MxB [DS].
- Test button runs both motors at **half** speed [DS].
- Firmware update procedure (UF2) [DS][GH]: disconnect battery, motors and R/C devices [GH]; connect a data-capable USB-C cable [GH]; hold BOOT, press and release RESET, release BOOT [DS]; wait for the **RPI-RP2** drive [DS]; copy the MDDRC5 `.uf2` file to it; the board restarts and the drive disconnects; do not unplug during copying [GH].
- USB-C powers the control circuit for updating; it does **not** power the motors [GH].
- After flashing, with motors and receiver disconnected: PWR LED on, and both ERR LEDs repeat double blinks (= no valid R/C input). This does not identify the firmware version [GH].
- Product page tells users to update to the latest firmware before use (bug fixes and improvements) [PP].
- Before a motor test, raise the robot so its wheels are clear of the surface [GH].
- Product page states normal R/C use needs no Arduino coding [PP].

## Power and electrical limits
- Input 7–30 V absolute maximum [DS]; datasheet says connect the power input to the battery [DS].
- **Overcurrent protection with active current limiting** — when the motor tries to draw more than the driver can supply, PWM is chopped and current is held at the maximum limit; protects against stall or oversized motors; OC LED on while limiting [DS]. Threshold 20 A [DS].
- **Undervoltage shutdown** — output shuts down when input drops below the lower limit (so MOSFETs fully turn on and do not overheat); ERR LED blinks [DS]. Numeric threshold not stated.
- **Reverse polarity protection** — reversed input is blocked from flowing through the circuit [DS].
- **Overvoltage** — detected and reported as a 4-blink error [DS]. Numeric threshold not stated.
- **Switching power supplies / regenerative current** — "If a switching power supply is being used, connect a motor shunt regulator or rechargeable battery with the same voltage in parallel with the power supply. This is to absorb the regenerative energy from the motor during deceleration." [DS]
- **Thermal shutdown** — listed on the product page [PP]; **not stated in the datasheet** (no threshold or behaviour).
- 5 V receiver output: 500 mA max [DS]. Its regulator type is not stated.

## Software support
- No coding is required for R/C use [PP]; the board runs Cytron firmware on the RP2040 [DS].
- Firmware is distributed as `.uf2` files on GitHub `CytronTechnologies/mddrc5` (branches `main` and `master` hold identical files). Files present on 2026-10-16: `mddrc5_v1.0.4.uf2`, `mddrc5_v1.0.5.uf2`, `mddrc5_v1.0.6.uf2` [GH]. The READMEs disagree on the latest version — see Conflicts.
- No release notes, firmware source code, build instructions or licence file are published in the repo [GH].
- Custom code upload via USB-C is mentioned on the product page [PP]; no Arduino/MicroPython library, examples or programming guide are published by Cytron for it (none found).
- Datasheet pin map (above) is the only published hardware reference for custom firmware [DS].

## Compatibility and accessories
- R/C receiver: signal on RC1/RC2, powered from the board's +5V (500 mA max) and GND [DS].
- Two DC motors [DS] (brushless motors and steppers are not mentioned).
- GitHub 3D files: Robot Sumo 500g R/C body (`Sumo500gRCBody.stl`) and motor bracket (`Sumo500gRCBracket.stl`), plus Robot Battle Karnival STEM STL files [GH]. In `SHA256SUMS` the Sumo body/bracket hashes are identical to BattleBody/BattleBracket, i.e. the same files under new names [GH].
- Tutorials linked from GitHub: "Getting Started with MDDRC5" and "Build a Robot Sumo 500g R/C with MDDRC5" on my.cytron.io [GH] (not read here).
- Product page positions it for 500 g R/C sumo robots, compact competition robots (compact footprint for space-limited robots), compact mobile platforms and space-limited robotics projects [PP].
- Product-page title "5 Amp 7V-30V DC Motor Driver for R/C (2 Channels)"; framing "5 Amp Dual Channel RC Motor Driver (MDDRC5)"; positioned as a smaller alternative inspired by MDDRC10 for direct R/C motor control in compact robots [PP]. MDDRC10 is a different product — never use it as an alias.

## Common mistakes / troubleshooting
- **2 blinks** — no RC signal / pulse out of range: check receiver is bound and powered, wired to RC1/RC2, and the signal is 10–100 Hz [DS]. This is also the normal state with no receiver connected [GH].
- **4 blinks** — overvoltage: often a switching power supply or bench supply pushed up by motor regeneration; add a shunt regulator or a same-voltage rechargeable battery in parallel [DS].
- **OC LED on** — motor stalled or oversized; driver is current-limiting at 20 A [DS].
- **Robot drives in the wrong direction / spins** — swap MxA/MxB on the affected motor; check mode switch (IND vs MIX) and that RC1/RC2 are on the intended transmitter channels [DS].
- **Robot drifts** — adjust the FWD/REV motor alignment potentiometers [DS].
- **Servo browns out the receiver** — do not power servos from the 5V output [DS].
- **Motors do not move on USB** — USB-C does not power the motors [GH].
- **UF2 drive does not appear** — use a data-capable USB-C cable and the BOOT/RESET sequence [DS][GH].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Peak current duration | [DS] Rev 1.0 (Mar 2026): 20 A for "less than 1 seconds", limited by OC circuit | [PP] (read 2026-10-19): "Peak Current: 20 A (less than 5 seconds)" | Datasheet wins: **< 1 s**. Product page should be corrected |
| Latest firmware version | [GH] root `README.md`: "v1.0.5 is the highest-numbered firmware"; `SHA256SUMS` lists only v1.0.4 and v1.0.5 | [GH] `firmware/README.md`: v1.0.6 is "Highest-numbered supplied version" (lists v1.0.6 and v1.0.4, omits v1.0.5) | All three files exist on both branches; **v1.0.6** is the highest-numbered file present. v1.0.6 is not covered by `SHA256SUMS` (its SHA-256 is 83720b94…5df3). Which is the recommended release is not confirmed — see Needs verification |
| Thermal shutdown | [DS]: not listed under Protection Features | [PP] (read 2026-10-19): "Thermal Shutdown" listed | Not stated as a datasheet spec; do not claim a threshold |
| Dimensions | [PP] (read 2026-10-19): 69 × 35.5 mm |  reading of DS Figure 2: 69.115 × 35.635 mm | Consistent (rounded); figure not re-read here |
| Datasheet cross-reference | [DS] Table 1 says error LEDs are in "Chapter 7" | [DS] error LED table is in chapter 6; chapters go 6 → 8 and Table 3 is missing | Internal numbering error in Rev 1.0; content is in chapter 6 |

## Needs verification
- Which firmware version is the current recommended release (v1.0.5 vs v1.0.6), and release notes for each.
- Failsafe behaviour: datasheet gives the 2-blink RC Input Error but does **not** state what the motors do on signal loss (stop/brake/coast).
- Neutral pulse width and any transmitter calibration / endpoint-learning procedure — not stated in any source read.
- Whether the mode switch is read at power-up only or live.
- How the FWD/REV alignment pots are adjusted (direction, range).
- Numeric undervoltage and overvoltage thresholds.
- Motor driver IC part number (pin map shows PWM/Direction/Sleep/Fault per motor; IC not named).
- Brake vs coast behaviour at zero throttle / in deadband.
- Whether a microcontroller's servo-style PWM can drive RC1/RC2 (electrically within 1.5–15 V high level, but not stated as supported).
- Operating temperature, weight, terminal type — not stated.
- Read the Cytron "MDDRC5 firmware programming" and "Getting Started with MDDRC5" tutorials (failsafe, neutral calibration, custom code).

## Sources
- [DS] MDDRC5 Datasheet, "5 Amp 7V-30V DC Motor Driver for R/C (2 Channels)", Rev 1.0, March 2026 — (Cytron document — link not public)
- [PP] Product page (not read — fetch failed) — https://my.cytron.io/p-5-amp-7v-30v-dc-motor-driver-for-r-c-2-channels
- [GH] Repository — https://github.com/CytronTechnologies/mddrc5
- [GH] Root README — https://raw.githubusercontent.com/CytronTechnologies/mddrc5/main/README.md
- [GH] Firmware README — https://raw.githubusercontent.com/CytronTechnologies/mddrc5/main/firmware/README.md
- [GH] SHA256SUMS — https://raw.githubusercontent.com/CytronTechnologies/mddrc5/main/SHA256SUMS
- [GH] Sumo 3D README — https://raw.githubusercontent.com/CytronTechnologies/mddrc5/main/3d-files/robot-sumo-500g-rc/README.md
- [GH] Firmware files — https://raw.githubusercontent.com/CytronTechnologies/mddrc5/main/firmware/mddrc5_v1.0.6.uf2 (also v1.0.4, v1.0.5)
