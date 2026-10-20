# MDD3A — Verified Reference

| | |
|---|---|
| Product code | `MDD3A` (datasheet title [DS]; Cytron GitHub README link text [GH]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (description, features, packing list, resources). The page text matches the Tindie copy already used; "3 Amp per channel" is now [PP] |
| Primary source | MDD3A Datasheet — "3Amp 4V-16V DC Motor Driver (2 Channels)" — **Rev 1.0, March 2019** (public Google Doc, last modified 2019-03-15): https://docs.google.com/document/d/1ax3gSo0srTzoSr2bo8ETLym0OqrYjlk_JCZK4kxtfXg/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: the my.cytron.io product page was read on 2026-10-19 [PP]; its text matches the Tindie copy. [PP: Tindie] = Cytron Technologies' own store listing on Tindie (seller "Cytron Technologies", written by Cytron, links the same datasheet Google Doc); it stands in for the product page and ranks below [DS]. No separate user manual exists — the datasheet is the only Cytron document. No [DT] confirmation exists yet. The PDF mirrors on electrokit.com and cdn.shopify.com carry the same title (electrokit copy checked: Rev 1.0, March 2019).

## What it is
A 2-channel, bi-directional motor driver for two brushed DC motors or one stepper motor, powered from 4–16 VDC, with a maximum motor current of 3 A continuous / 5 A peak (< 5 s) [DS]; Cytron states 3 A is per channel, "continuously without any additional heatsink" [PP: Tindie]. Each motor is controlled by two PWM inputs (A and B), there is a 5V output (200 mA max) for the host controller, test buttons and status LEDs for each direction, and reverse polarity protection on the power input [DS]. Built with a "discrete MOSFETs H-Bridge design" [PP: Tindie].

## Specifications
Datasheet Table 2 is titled **"MDD3A Absolute Maximum Ratings"** — these are absolute limits, not recommended operating points [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (Vin) | Min 4 VDC, Max 16 VDC | [DS] |
| Maximum motor current, continuous | Max 3 A (table does not say "per channel"; [PP: Tindie]: "3 Amp per channel continuously without any additional heatsink") | [DS][PP: Tindie] |
| Maximum motor current, peak | Max 5 A, for **< 5 seconds** | [DS] |
| Logic input voltage (M1A, M1B, M2A, M2B), low level | 0 – 0.5 V | [DS] |
| Logic input voltage (M1A, M1B, M2A, M2B), high level | 1.7 – 12 V | [DS] |
| PWM frequency | DC – 20 kHz ("Output frequency is same as input frequency") | [DS] |
| DC +5V output maximum current | 200 mA | [DS] |
| Number of channels | 2 (Motor 1, Motor 2) | [DS] |
| Motor types | Brushed DC motor (Figure 3) and stepper motor (Figure 4) connection diagrams; "Bidirectional control for two brushed DC motor", "Control one unipolar/bipolar stepper motor" | [DS][PP: Tindie] |
| Output stage | "discrete MOSFETs H-Bridge design" | [PP: Tindie] |
| Logic compatibility | "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." | [PP: Tindie] |
| 5V regulator | "Buck-boost regulator which produces 5V output from input as low as 4V can be used to power the host controller" | [PP: Tindie] |
| Test buttons | M1A/M2A forward, M1B/M2B backward; motor runs at full speed | [DS] |
| Motor status LEDs | M1A/M2A forward, M1B/M2B backward; on when the motor is running | [DS] |
| Power LED | On when powered | [DS] |
| Reverse polarity protection | "Power Input Reversed Polarity Protection" | [DS] |
| Thermal / over-temperature protection | **Not stated** | [DS][PP: Tindie] |
| Over-current / short-circuit protection | **Not stated** | [DS][PP: Tindie] |
| Under-voltage protection | **Not stated** | [DS] |
| Heatsink | Not needed for 3 A per channel continuous ("without any additional heatsink") | [PP: Tindie] |
| Dimensions | **Not stated** in text — datasheet has a drawing (Figure 2 "MDD3A Dimension") only | [DS] |
| Operating temperature | **Not stated** | [DS] |
| Terminal type / wire size | **Not stated** (named "Power Input Terminal", "Motor Output Terminal") | [DS] |
| Packing list | "1 x 3Amp 4V-16V DC Motor Driver (2 Channels)" | [PP: Tindie] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Description: discrete-MOSFET H-bridge, "able to support **3 Amp per channel** continuously without any additional heatsink"; two brushed DC motors or one bipolar/unipolar stepper, 4–16 V [PP].
- Features: 3 A continuous, 5 A peak; buck-boost regulator 5 V output (200 mA max); test buttons; motor output LEDs; inputs compatible with 1.8 V, 3.3 V, 5 V and 12 V logic; PWM up to 20 kHz (output = input frequency); **reverse polarity protection** [PP].
- Packing: 1x MDD3A [PP]; a product image shows the packaging doubles as a casing [PP: img name].
- Resources: datasheet, sample code (CytronMotorDriver), 3D CAD (zip) [PP].

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
| High | High | High | High | **Brake** |

*"Actual motor direction is depending on the motor connection. Swapping the connection (MA & MB) will reverse the direction." [DS]

Control mode: two-PWM-per-motor (Input A = forward speed, Input B = backward speed) [DS][GH]. No PWM+DIR (sign-magnitude) pin set, no locked-antiphase mode, no RC, analog or serial input and no mode selector are described [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Both Low = Brake and both High = Brake.** There is no coast state in the truth table. This differs from Maker Drive, where High/High = Coast [DS].
- Use the **Cytron Motor Drivers Library** in **`PWM_PWM`** mode: `CytronMD motor1(PWM_PWM, pinA, pinB);` then `motor1.setSpeed(-255..255)` [GH]. `setSpeed(0)` writes 0 to both pins → Brake [GH][DS].
- Both A and B pins need PWM for speed control in both directions (library calls `analogWrite()` on both) [GH]. Cytron's example uses Arduino D3, D9, D10, D11 [GH].
- Connect host **GND to MDD3A GND** (example wiring "Arduino GND - Motor Driver GND") [GH].
- Logic high up to **12 V** absolute max, low ≤ 0.5 V [DS] — so 3.3 V, 5 V and 12 V logic all work [PP: Tindie]; 24 V PLC outputs exceed the rating [DS].
- The datasheet current table does **not** say "per channel"; quote it as "3 A continuous per channel" only with the product-listing source, and the 5 A peak without "per channel" (see Conflicts).
- Do **not** claim thermal or over-current protection — only reverse polarity protection is stated [DS]. Don't copy Maker Drive's 150 °C thermal cut-off onto MDD3A.
- Motor direction depends on wiring: check with the test buttons and swap motor wires [DS].
- Test buttons run the motor at **full speed** [DS].
- 5VO is limited to **200 mA** — check the host board's draw before powering it from 5VO [DS].

## Power and electrical limits
- Vin **4–16 VDC** (absolute maximum). The datasheet says "Connect to battery" [DS].
- Motor current **3 A continuous, 5 A peak (< 5 seconds)** [DS]. A motor whose starting or stall current exceeds 5 A, or that runs above 3 A continuously, is outside the datasheet ratings.
- No thermal, over-current, short-circuit or under-voltage protection is stated [DS] — treat the driver as unprotected against overload in tutorials.
- Reverse polarity protection on the power input only [DS].
- SMPS / bench power supply guidance and regenerative-current handling: **not stated** [DS]. The datasheet only says to connect a battery.

## Software support
- **Arduino:** Cytron Motor Drivers Library (`name=Cytron Motor Drivers Library`, version 1.0.1, `architectures=*`). Install via Library Manager, search "Cytron Motor Drivers Library" [GH].
- `#include "CytronMotorDriver.h"`; `CytronMD(MODE mode, uint8_t pin1, uint8_t pin2)`; modes `PWM_DIR`, `PWM_PWM`; `setSpeed(int16_t)` clamped to −255…255 [GH].
- Example: **PWM_PWM_DUAL** — README lists MAKER-DRIVE and MDD3A as compatible. Wiring: D3 → PWM 1A, D9 → PWM 1B, D10 → PWM 2A, D11 → PWM 2B, GND → GND [GH].
- On `ARDUINO_ARCH_ESP32` the library calls `ledcWrite(pin, …)`; the constructor only sets `pinMode`/`digitalWrite` [GH] — ESP32 behaviour not verified (see Needs verification).
- MicroPython / CircuitPython / MakeCode / PLC examples: **not stated** by any Cytron source read.

## Compatibility and accessories
- Host controllers named by Cytron: Arduino, Raspberry Pi, PLC [PP: Tindie].
- Motors: two brushed DC motors, or one unipolar/bipolar stepper motor [DS][PP: Tindie].
- Resources linked by Cytron: datasheet (Google Doc), source code (GitHub CytronMotorDriver) [PP: Tindie].

## Common mistakes / troubleshooting
- **Using PWM+DIR code** (`PWM_DIR`, MD10C-style) — MDD3A needs two PWM inputs per motor → use `PWM_PWM` [GH].
- **Expecting coast with both inputs High** — MDD3A brakes in both Low/Low and High/High [DS].
- **Motor runs the wrong way** → swap the motor wires (MA/MB) [DS].
- **Driver damaged by a large motor** → stall/starting current above 5 A, or above 3 A continuous, is beyond ratings, and no over-current protection is stated [DS].
- **Nothing works** → check battery polarity (protected, but the board won't run reversed), voltage 4–16 V, common GND, then press the test buttons to separate hardware from code [DS].
- **Host board browns out** → 5VO max 200 mA [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Current "per channel" | [DS] Table 2: "Maximum Motor Current" 3 A / 5 A, no "per channel" | [PP: Tindie] "3 Amp per channel continuously"; [3P] thingbits: 5 A peak per channel | Use [DS] numbers; "3 A per channel" with [PP: Tindie] attribution; 5 A peak per channel is [3P]-only → Needs verification |
| Hardware revision | [DS] Rev 1.0, March 2019 |  box artwork BOX-MDD3A.pdf text "210818 MDD3A v2 (R1080323)" | Unresolved — datasheet wins; ask [DT] whether v2 changes any spec |
| Library menu name | [GH] library.properties `Cytron Motor Drivers Library` | [GH] README: File → Examples → "Cytron DC Motors Library" | Search Library Manager for "Cytron Motor Drivers Library" |
| Price | [PP: Tindie] USD 7.00 (sold out since Aug 02, 2026) | [3P] RobotShop USD 8.50 | Quote Cytron prices only, with date |

## Needs verification
- **"MDD3A v2"**: what changed from the Rev 1.0 (March 2019) datasheet board, if anything.
- Whether the 5 A peak is per channel ([3P] thingbits says yes; [DS] silent).
- Thermal / over-current behaviour of the discrete MOSFET bridge (none stated).
- Whether a bench supply / SMPS is acceptable or a battery is required (datasheet says "Connect to battery").
- Dimensions, mounting holes, terminal type and wire gauge — Figure 2 not readable as text.
- Operating temperature range.
- Stepper drive method/library — the datasheet shows a connection diagram only.
- ESP32: library calls `ledcWrite(pin, duty)` without `ledcAttach()` — whether this works on ESP32 Arduino core 3.x unmodified is untested.

## Sources
- [DS] MDD3A Datasheet Rev 1.0, March 2019 — https://docs.google.com/document/d/1ax3gSo0srTzoSr2bo8ETLym0OqrYjlk_JCZK4kxtfXg/edit (PDF mirrors: https://www.electrokit.com/upload/product/41018/41018266/MDD3A%20Datasheet.pdf — same Rev 1.0, March 2019; https://cdn.shopify.com/s/files/1/0176/3274/files/MDD3A_Datasheet.pdf — not opened)
- [PP] Product page https://www.cytron.io/p-mdd3a (URL as linked from Cytron GitHub README; my.cytron.io **not read**)
- [PP: Tindie] Cytron Technologies Tindie listing — https://www.tindie.com/products/cytron/3amp-2-channel-4v-16v-dc-motor-driver/
- [GH] https://github.com/CytronTechnologies/CytronMotorDriver (README.md, library.properties, CytronMotorDriver.h/.cpp, examples/PWM_PWM_DUAL/PWM_PWM_DUAL.ino)
- [3P] (cross-check only) https://robotshop.com/en/cytron-3a-4-16v-dual-channel-dc-motor-driver.html · https://thingbits.in/products/4-16v-3a-dual-channel-dc-motor-driver
