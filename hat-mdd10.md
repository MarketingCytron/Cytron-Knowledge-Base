# 10Amp 6V-24V DC Motor Driver HAT for Raspberry Pi (2 Channels) — Verified Reference

| | |
|---|---|
| Product code | `HAT-MDD10` (manual title [UM]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 4): live my.cytron.io product page read (description, features, packing list, resources). Page independently confirms the manual (6–24 V, 10 A without heatsink at 25 °C, 30 A peak 10 s, current limiting at 30 A, 20 kHz, 67.5 × 59 mm) |
| Primary source | No datasheet exists. Top source: "HAT-MDD10 10Amp DC Motor Driver for Raspberry Pi User's Manual" — **V1.0, "Mac 2017"** (sic; March 2017) — https://docs.google.com/document/d/19JLDnzU0y-9FKH4ZXm0lk4xtMJKtaKTDBT5ulGgj8UI/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] read in full from the Google Doc (Drive title "Hat-MDD10 User's Manual"); a PDF mirror on electrokit.com (same title, V1.0, "Mac 2017") matches. Figures (board photo, dimension, connection diagram) are images and were not readable. No newer document on Drive. [GH] = sample code repo Cytron_MDD10_Hat (last commit Feb 2023). [PP] = my.cytron.io page read by the coordinator 2026-10-16 (name, code, stock only).

## What it is
A Raspberry Pi HAT that drives two brushed DC motors at up to 10 A continuous each from a 6–24 V supply, controlled by PWM and DIR signals on fixed Raspberry Pi GPIOs [UM]. It supports sign-magnitude and locked-antiphase PWM, has test buttons and per-output LEDs, and uses a fully NMOS H-bridge with "no heat sink is required" [UM].

## Specifications
Manual section 4 "Product Specification and Limitations", table **"Absolute Maximum Rating"**, plus feature list [UM].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 6 V, Max 24 V (terminal table: "6V to 24V", "*1: Absolute Maximum") | [UM] |
| IMAX — maximum continuous motor current | Max 10 A — feature list: "10A continuous (without heatsink at 25℃)"; table footnote "Tested in room temperature." | [UM] |
| IPEAK — peak motor current | Max 30 A — "Must not exceed 10 seconds." | [UM] |
| Current limiting | "Current limiting at 30A." (feature list; no further detail) | [UM] |
| VIOH — logic input high level | Min 3 V, Max 5.5 V | [UM] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | 20 kHz — "Actual output frequency is same as input frequency." | [UM] |
| Logic level | "3.3V and 5V logic level input." | [UM] |
| Number of channels | 2 ("Bi-directional control for two brushed DC motor") | [UM] |
| Control modes | Sign-magnitude PWM and locked-antiphase PWM; "Support TTL PWM from microcontroller, not PWM from RC receiver." Analog / serial: not stated | [UM] |
| H-bridge | "Fully NMOS H-Bridge for better efficiency and no heat sink is required." | [UM] |
| Thermal / under-voltage / reverse-polarity protection | **Not stated** | — |
| Test buttons | M1A, M1B, M2A, M2B test switches ("Manual/test button to fast verification") | [UM] |
| LEDs | M1A/M1B, M2A/M2B indicators; Power LED | [UM] |
| Dimensions | 67.5 mm x 59 mm | [UM] |
| Operating temperature | Not stated (only 25 ℃ / room-temperature test conditions) | — |
| Packing list | 1 x Hat-MDD10 10A DC Motor Driver; 1 x PC104 Header Pin (2x20) (CN-PH-PC104) | [UM] |
| Warranty | 12 months; manufacturing defects only; misuse and two-way freight not covered | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** dual-channel 10 A continuous driver for Raspberry Pi; sign-magnitude PWM control; solid-state; "current limiting sensor and auto cut set at 30A peak" [PP].
- **Features list:** 6–24 VDC; test buttons; LED per output; 10 A continuous (without heatsink at 25 °C), 30 A peak (10 s); current limiting at 30 A; Raspberry Pi connector; NMOS H-bridge, no heatsink; regenerative braking; PWM up to 20 kHz (output = input frequency from the Pi); sign-magnitude PWM; TTL PWM from a microcontroller, not RC-receiver PWM; **dimension 67.5 mm × 59 mm** [PP].
- No packing-list tab on the page [PP].
- **Resources:** User's Manual (Google Doc), 3D CAD, Raspberry Pi sample code (GitHub `Cytron_MDD10_Hat`) [PP].

## Interfaces, terminals and pin mapping
**Terminal block** [UM]:

| Pin | Name | Description |
|---|---|---|
| 1 | M1A | Motor 1 terminal A |
| 2 | M1B | Motor 1 terminal B |
| 3 | VM | Positive supply (6 V to 24 V, absolute maximum) |
| 4 | GND | Negative supply |
| 5 | M2A | Motor 2 terminal A |
| 6 | M2B | Motor 2 terminal B |

**Input / Raspberry Pi GPIO mapping** (BCM numbering) [UM][GH]:

| Pin | Name | Raspberry Pi GPIO | Description |
|---|---|---|---|
| 1 | GND | — | Logic ground |
| 2 | PWM1 | **GPIO12** | Motor 1 speed (not for RC PWM) |
| 3 | DIR1 | **GPIO26** | Motor 1 direction |
| 4 | PWM2 | **GPIO13** | Motor 2 speed (not for RC PWM) |
| 5 | DIR2 | **GPIO24** | Motor 2 direction |

- No jumper or pin selector is described; GPIO assignment is fixed in the manual [UM].
- Raspberry Pi connector on the board; a 2x20 PC104 header is supplied [UM].

Truth table (each channel) [UM]:

| PWM | DIR | Output A | Output B |
|---|---|---|---|
| Low | X (don't care) | Low | Low |
| High | Low | High | Low |
| High | High | Low | High |

LEDs and test switches [UM]: MxA LED on when output A high and B low (current A→B); MxB LED on when A low and B high (current B→A). MxA test switch: current A→B, motor CW (or CCW depending on connection); MxB: current B→A, CCW (or CW). Power LED on when powered. Wire size: not stated.

## Rules and gotchas (for code, wiring and tutorials)
- **GPIO numbers are BCM:** PWM1 = GPIO12, DIR1 = GPIO26, PWM2 = GPIO13, DIR2 = GPIO24 [UM]; the sample code uses `GPIO.setmode(GPIO.BCM)` [GH].
- **Sign-magnitude:** PWM pin = speed, DIR pin = direction [UM].
- **Locked-antiphase:** PWM pin held HIGH (enable), PWM signal on the DIR pin; 50% duty = stop, < 50% = CW*, > 50% = CCW* [UM]. The sample `HatMDD10LA.py` does exactly this (drives PWM on GPIO26/24, holds GPIO12/13 high) [GH].
- PWM LOW = both outputs low regardless of DIR [UM].
- Supply 6–24 V is stated as the **absolute maximum** [UM]; no separate recommended operating range is given. Do not suggest supplies above 24 V.
- Peak 30 A for no more than 10 s [UM].
- Not for RC receiver PWM [UM].
- Whether the HAT powers the Raspberry Pi is **not stated** — do not tell readers it does.
- Sample code is **Python 2** syntax (`print "Forward"`) with RPi.GPIO software PWM at 100 Hz [GH]; it needs `print()` edits to run on Python 3.

## Power and electrical limits
- 6–24 V on VM/GND (absolute maximum) [UM].
- 10 A continuous per channel without heatsink at 25 ℃; 30 A peak ≤ 10 s; current limiting at 30 A [UM].
- Thermal shutdown, under-voltage shutdown, reverse-polarity protection: not stated.
- Battery vs switching power supply / regenerative current: not stated.

## Software support
- Sample code (Python, RPi.GPIO) [GH] https://github.com/CytronTechnologies/Cytron_MDD10_Hat:
  - `Example Code/Raspberry PI 3/HatMDD10SM.py` — sign-magnitude.
  - `Example Code/Raspberry PI 3/HatMDD10LA.py` — locked-antiphase.
  - Both: `GPIO.setmode(GPIO.BCM)`, `GPIO.PWM(pin, 100)` (100 Hz software PWM), Python 2 `print` statements [GH].
- README requirement: "Raspberry pi 3" [GH].
- No dedicated Python library, MicroPython or other language support stated.

## Compatibility and accessories
- Raspberry Pi controller with "Raspberry Pi compatible connector"; manual and repo name Raspberry Pi 3 [UM][GH]. Other Pi models (Pi 4, Pi 5, Zero): not stated.
- Input logic 3.3 V and 5 V [UM].
- Included: 2x20 PC104 header (CN-PH-PC104) [UM].

## Common mistakes / troubleshooting
- Motor does not respond → using physical pin numbers instead of BCM (GPIO12/26/13/24) [UM][GH].
- Sample script fails with SyntaxError → Python 2 `print` statements; run under Python 2 or change to `print()` [GH].
- Wrong motor or direction → check M1A/M1B vs M2A/M2B wiring; swap A/B to reverse [UM].
- No response from RC receiver → RC PWM not supported [UM].
- Quick check without code → press M1A/M1B/M2A/M2B test switches; matching LED lights [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Voltage range | [UM]: 6–24 V | [PP] product name "6V-24V"; [3P] RobotShop "6VDC to 24VDC" | Agree |
| PWM frequency | [UM]: up to 20 kHz | [GH] sample uses 100 Hz software PWM | Not a conflict — 100 Hz is the sample's choice, within the 20 kHz limit |

## Needs verification
1. Whether the HAT back-powers the Raspberry Pi (5 V regulator?) — not stated.
2. Compatibility with Raspberry Pi 4 / 5 / Zero and with RPi.GPIO alternatives (RPi.GPIO does not support Pi 5 per Raspberry Pi docs [VEN] — confirm with [DT] before writing Pi 5 tutorials).
3. Protection beyond "current limiting at 30A" (thermal, under-voltage, reverse polarity).
4. Whether the 5-pin input header can be used without a Pi (external controller) — header exists in pin table, use not described.
5. Operating temperature, terminal wire size; mounting-hole positions (drawing only).

## Sources
- [UM] HAT-MDD10 User's Manual, V1.0, "Mac 2017": https://docs.google.com/document/d/19JLDnzU0y-9FKH4ZXm0lk4xtMJKtaKTDBT5ulGgj8UI/view
- PDF mirror of the same manual (cross-check): https://www.electrokit.com/upload/product/41018/41018269/Hat-MDD10%20User's%20Manual.pdf
- [PP] Product page: https://my.cytron.io/p-10amp-6v-24v-dc-motor-driver-hat-for-rpi-2-channels
- [GH] Sample code: https://github.com/CytronTechnologies/Cytron_MDD10_Hat
- [3P] RobotShop listing (cross-check only): https://www.robotshop.com/products/cytron-2x10a-motor-driver-hat-for-raspberry-pi
