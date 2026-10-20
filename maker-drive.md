# Maker Drive — Verified Reference

| | |
|---|---|
| Product code | `MAKER-DRIVE` (datasheet title [DS]; Cytron GitHub README link text "MAKER-DRIVE" [GH]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. In stock on my.cytron.io; the page carries the same text the KB had from Cytron's Tindie listing, so those facts are now [PP] my.cytron.io |
| Primary source | MAKER-DRIVE Datasheet — "Simplifying H-Bridge Motor Driver for Beginner" — **Rev 1.0, Feb 2019** (public Google Doc, last modified 2021-08-20): https://docs.google.com/document/d/1XakJWz9DAtrMc_Jf75FnDXs4gwT_osCSj3Rbx1OU7bM/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = my.cytron.io product page, read 2026-10-19 (same text as Cytron's Tindie listing). [PP: Tindie] = Cytron Technologies' own Tindie listing, read 2026-10-16 before the my.cytron.io page was reachable.

## What it is
A 2-channel, bi-directional H-bridge motor driver for small brushed DC motors (or one stepper motor), powered from 2.5–9.5 VDC, rated 1 A continuous / 1.5 A peak (< 5 s) per channel [DS]. Each motor is controlled by two PWM inputs (A and B) — there is no separate DIR pin [DS]. It has a 5V output (200 mA max) to power the host microcontroller, a test button and status LED for each motor direction, reverse polarity protection on the power input, and H-bridge IC over-temperature cut-off at 150 °C [DS]. Cytron positions it as a beginner-friendly replacement for the L298N [PP: Tindie].

## Specifications
Datasheet Table 2 is titled **"MAKER-DRIVE Absolute Maximum Ratings"** — these are absolute limits, not recommended operating points [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 2.5 VDC, Max 9.5 VDC | [DS] |
| Maximum motor current (per channel), continuous | Max 1 A | [DS] |
| Maximum motor current (per channel), peak | Max 1.5 A, for **< 5 seconds** | [DS] |
| Logic input voltage (M1A, M1B, M2A, M2B), low level | 0 – 0.5 V | [DS] |
| Logic input voltage (M1A, M1B, M2A, M2B), high level | 1.7 – 6 V | [DS] |
| PWM frequency | DC – 20 kHz ("Output frequency is same as input frequency") | [DS] |
| DC +5V output maximum current | 200 mA | [DS] |
| Number of channels | 2 (Motor 1, Motor 2); "Dual channel, Bi-directional control motor driver" | [DS][PP: Tindie] |
| Motor types | Brushed DC motor (Figure 3) and stepper motor (Figure 4) connection diagrams | [DS] |
| Logic compatibility | "Inputs compatible with 1.8V, 3.3V and 5V logic (Arduino, Raspberry Pi, etc)." | [PP: Tindie] |
| 5V regulator | "Buck-boost regulator to produce 5V output from input voltage as low as 2.5V" | [PP: Tindie] |
| Test buttons | 4 (2 per channel): M1A/M2A forward, M1B/M2B backward; motor runs at full speed | [DS][PP: Tindie] |
| Motor status LEDs | 4 (2 per channel): M1A/M2A forward, M1B/M2B backward; on when the motor is running | [DS][PP: Tindie] |
| Power LED | On when powered | [DS] |
| Reverse polarity protection | Power input (VB+/VB-) | [DS] |
| Temperature protection | H-bridge IC built-in: output to motor cut off when IC internal temperature is over 150 °C | [DS] |
| Over-current / short-circuit protection | **Not stated** | [DS] |
| Under-voltage protection | **Not stated** | [DS] |
| Dimensions | 43 mm (W) × 35 mm (L) × 14 mm (H) (my.cytron.io product page). Datasheet has a dimension drawing (Figure 2) only, no values in the text | [PP: Tindie] / [DS] figure |
| Operating temperature | **Not stated** | [DS] |
| Driver IC part number | **Not stated** ("H-Bridge IC") | [DS] |
| Terminal type / wire size | **Not stated** (named "Power Input Terminal", "Motor Output Terminal") | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Features list:** dual-channel bi-directional; motor voltage 2.5–9.5 V; 1.0 A continuous, 1.5 A peak (< 5 s); 5 V output 200 mA; inputs compatible with 1.8 V, 3.3 V and 5 V logic; solid-state; regenerative braking; PWM up to 20 kHz (output = input frequency); **43 × 35 × 14 mm** [PP].
- **Description:** reverse polarity protection on Vin/Vmotor/Vbatt; 4 test buttons and 4 indicator LEDs; buck-boost regulator gives 5 V (200 mA) from 2.5–9.5 V; supports a stepper motor; "Maker Drive is not an Arduino Shield" but works with Maker UNO, Maker UNO Plus, CT-UNO, Arduino UNO R3, Mega 2560, Nano, Pro Mini, Raspberry Pi, micro:bit, BeagleBone, ESP8266, ESP32 [PP].
- **Suitable motors (page):** 2-terminal brushed DC, 2.5–9.5 V, rated ≤ 1.0 A, peak ≤ 1.5 A — e.g. 6 V 85 RPM micro metal gearmotor, 6 V 225 RPM 0.35 kgf·cm, TT motor kits, Tamiya double / twin-motor gearbox "(Although the stall current is 2.10A)", 3 V toy motor [PP].
- **Suggested power:** 2/3/4 × AA or AAA, 1 or 2 × 18650, 1 or 2 × 14500 Li-ion with holders [PP].
- **Packing list:** 1x Maker Drive board [PP]. **Resources:** datasheet, CytronMotorDriver library (PWM_PWM_DUAL example), line-following robot tutorial, Fritzing, 3D files [PP].

## Interfaces, terminals and pin mapping
| Terminal / pin | Function | Src |
|---|---|---|
| VB+ / VB- (Power Input Terminal) | "Connect to battery." VB+ positive, VB- negative | [DS] |
| Motor Output Terminal (per motor, outputs A and B) | Connect to motor terminal; motor direction depends on the polarity | [DS] |
| M1A | PWM Input A for motor 1 | [DS] |
| M1B | PWM Input B for motor 1 | [DS] |
| M2A | PWM Input A for motor 2 | [DS] |
| M2B | PWM Input B for motor 2 | [DS] |
| 5VO | DC +5V output, maximum 200 mA; "can be used to power the microcontroller" | [DS] |
| GND | Ground | [DS] |

**Input truth table (per motor)** [DS Table 3]:

| Input A (M1A/M2A) | Input B (M1B/M2B) | Output A | Output B | Motor |
|---|---|---|---|---|
| Low | Low | Low | Low | **Brake** |
| High | Low | High | Low | Forward* |
| Low | High | Low | High | Backward* |
| High | High | Hi-Z (Open) | Hi-Z (Open) | **Coast** |

*"Actual motor direction is depending on the motor connection. Swapping the connection (MA & MB) will reverse the direction." [DS]

Control mode: two-PWM-per-motor (Input A = forward speed, Input B = backward speed) [DS][GH]. No PWM+DIR (sign-magnitude) pin set, no locked-antiphase mode, no RC, analog or serial input, and no mode selector are described [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Both inputs Low = Brake; both inputs High = Coast (outputs open).** This is the opposite of what many readers assume, and it is **different from MDD3A**, where High/High = Brake [DS].
- Use the **Cytron Motor Drivers Library** in **`PWM_PWM`** mode: `CytronMD motor1(PWM_PWM, pinA, pinB);` then `motor1.setSpeed(-255..255)` [GH]. With this library, `setSpeed(0)` writes 0 to both pins → Low/Low → **Brake** per the truth table (derived from [GH] code + [DS] table).
- Both A and B pins must be PWM-capable if you want speed control in both directions — the library calls `analogWrite()` on both pins [GH]. Cytron's example uses Arduino D3, D9, D10, D11 [GH].
- Connect host **GND to Maker Drive GND** (Cytron example wiring includes "Arduino GND - Motor Driver GND") [GH].
- Logic high must stay **≤ 6 V** (absolute max) — do not drive inputs from 12 V/24 V PLC outputs [DS].
- Motor direction depends on wiring: check with the test buttons and swap the motor wires rather than changing code [DS].
- Test buttons run the motor at **full speed** — have the robot wheels off the ground [DS].
- 5VO is limited to **200 mA** — check the host board's current draw before powering it from 5VO [DS].
- Don't call it a relay module — it uses "Solid state components" [PP: Tindie]. Don't call it an Arduino shield either (the "not an Arduino Shield" statement is [3P] only — see Needs verification).
- Don't name the driver chip (e.g. MX1508) in content — no Cytron source names it (see Needs verification).

## Power and electrical limits
- Power input **2.5–9.5 VDC** (absolute maximum). The datasheet says "Connect to battery" [DS].
- **1 A continuous, 1.5 A peak (< 5 seconds) per channel** [DS]. A motor whose starting or stall current exceeds 1.5 A, or that runs above 1 A continuously, is outside the datasheet ratings.
- Thermal protection: output cut off above 150 °C IC internal temperature [DS]. The datasheet does not say whether it recovers automatically.
- Over-current, short-circuit and under-voltage protection: **not stated** — do not claim them [DS].
- Reverse polarity protection on the power input only [DS].
- SMPS / bench power supply guidance, regenerative energy handling, heatsink: **not stated** [DS]. The datasheet only says to connect a battery.

## Software support
- **Arduino:** Cytron Motor Drivers Library (`name=Cytron Motor Drivers Library`, version 1.0.1, `architectures=*`, category Device Control). Install via Library Manager, search "Cytron Motor Drivers Library" [GH].
- Header `#include "CytronMotorDriver.h"`; class `CytronMD(MODE mode, uint8_t pin1, uint8_t pin2)`; modes `PWM_DIR`, `PWM_PWM`; method `setSpeed(int16_t speed)`, clamped to −255…255 [GH].
- Example for this board: **PWM_PWM_DUAL** — README lists MAKER-DRIVE and MDD3A as the compatible drivers. Wiring in the example: D3 → PWM 1A, D9 → PWM 1B, D10 → PWM 2A, D11 → PWM 2B, GND → GND [GH].
- On `ARDUINO_ARCH_ESP32` the library calls `ledcWrite(pin, …)` instead of `analogWrite()`, and the constructor only does `pinMode`/`digitalWrite` [GH] — ESP32 behaviour not verified (see Needs verification).
- MicroPython / CircuitPython / MakeCode / Raspberry Pi Python examples: **not stated** by any Cytron source read.

## Compatibility and accessories
- Logic: "compatible with 1.8V, 3.3V and 5V logic (Arduino, Raspberry Pi, etc)" [PP: Tindie]; datasheet high-level threshold 1.7 V min, 6 V max [DS].
- Motors: brushed DC (2 motors) or one stepper motor [DS]. Stepper type (unipolar/bipolar) not stated in the datasheet.
- Resources linked by Cytron: datasheet (Google Doc), source code (GitHub CytronMotorDriver), design files (Google Drive), video [PP: Tindie].
- Packing list, cables, headers: **not stated** by a Cytron source read.

## Common mistakes / troubleshooting
- **Motor won't stop / freewheels when both pins are HIGH** → that is Coast by design. Use Low/Low (or `setSpeed(0)`) for Brake [DS][GH].
- **Code written for PWM+DIR drivers** (MD10C-style `PWM_DIR`) does not suit this board — use `PWM_PWM` [GH].
- **Motor runs the wrong way** → swap the motor wires (MA/MB) [DS].
- **Motor stops when hot** → thermal cut-off at 150 °C IC temperature; the motor is likely over the 1 A continuous rating [DS].
- **Nothing works** → check battery polarity (protected, but the board won't run reversed), voltage 2.5–9.5 V, common GND, then press the test buttons to separate hardware from code [DS].
- **Host board browns out** → 5VO max 200 mA [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Driver IC | [DS] unnamed "H-Bridge IC" | [3P] Botland product title "Cytron Maker Drive MX1508" | Unresolved — don't name the chip. Ask [DT] |
| Stop behaviour wording | [DS] Low/Low = Brake, High/High = Coast | [PP: Tindie] feature "Regenerative Braking" | Not a contradiction; use [DS] truth table terms in content |
| Library menu name | [GH] library.properties `Cytron Motor Drivers Library` | [GH] README: File → Examples → "Cytron DC Motors Library" | Search Library Manager for "Cytron Motor Drivers Library" |
| Price | [PP] my.cytron.io (read 2026-10-19): RM18.90, in stock | [PP: Tindie] USD 3.80 (sold out since Nov 17, 2022); [3P] The Pi Hut £4.80 | Quote the my.cytron.io price with date |

## Needs verification
- **Driver IC is MX1508?** — [3P] only (Botland title). The task brief also assumes MX1508. Confirm with [DT].
- Whether thermal cut-off auto-recovers when the IC cools.
- Over-current / short-circuit behaviour of the IC (not stated).
- Whether a bench supply / SMPS is acceptable or a battery is required (datasheet says "Connect to battery"; regen braking is advertised).
- Stepper type supported (unipolar/bipolar) and any stepper library/example — the datasheet shows a diagram only.
- Dimension drawing values, mounting holes, terminal type and wire gauge — Figure 2 not readable as text.
- Operating temperature range.
- [3P] The Pi Hut suggests Tamiya gearboxes "Although the stall current is 2.10A" — above the 1.5 A peak rating; confirm Cytron's guidance before repeating.
- ESP32: library calls `ledcWrite(pin, duty)` without `ledcAttach()` — whether this works on ESP32 Arduino core 3.x unmodified is untested.
- Tamiya gearboxes are listed as suitable "although the stall current is 2.10A" (above the 1.5 A peak) — ask Cytron how users should limit stall current.

## Sources
- [DS] MAKER-DRIVE Datasheet Rev 1.0, Feb 2019 — https://docs.google.com/document/d/1XakJWz9DAtrMc_Jf75FnDXs4gwT_osCSj3Rbx1OU7bM/edit (PDF mirror, same revision: https://www.electrokit.com/upload/quick/48/3d/70a9_MAKER-DRIVE-Datasheet.pdf)
- [PP] Product page https://www.cytron.io/p-maker-drive (URL as linked from Cytron GitHub README; my.cytron.io **not read**)
- [PP: Tindie] Cytron Technologies Tindie listing — https://www.tindie.com/products/cytron/maker-drive-1a-dual-channel-h-bridge-motor-driver/ · design files (Cytron document — link not public) (not opened)
- [GH] https://github.com/CytronTechnologies/CytronMotorDriver (README.md, library.properties, CytronMotorDriver.h/.cpp, examples/PWM_PWM_DUAL/PWM_PWM_DUAL.ino)
- [3P] (cross-check only) https://thepihut.com/products/maker-drive-simplifying-h-bridge-motor-driver · https://botland.com.pl/en/motor-drivers-modules/13999-cytron-maker-drive-mx1508-two-channel-motor-controller-95v1a.html (title only; page timed out)
