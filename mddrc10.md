# MDDRC10 — Verified Reference

| | |
|---|---|
| Product code | `MDDRC10` (datasheet title page [DS], product page "Product Code" [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | MDDRC10 Datasheet — "10Amp 7V-30V DC Motor Driver for R/C (2 Channels)" — **Rev 1.0, August 2020** (Cytron PDF, public mirror): https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: The datasheet PDF could not be downloaded here (proxy blocked the CDN); it was read through a text-extraction tool from two public mirrors (RobotShop CDN and aws.robu.in), both with the same title page (Rev 1.0, August 2020). Its figures (Figure 1 board layout, Figure 2 dimension, Figure 3 Mixed Mode connection diagram, Figure 4 RC Tx input vs robot movement, Figure 5 current limit vs temperature graph) are images and could **not** be read. The original Google Doc was not found. Product page read at **www.cytron.io** (my.cytron.io fetch failed). No user manual, [DT] confirmation or GitHub repo for MDDRC10 exists (github.com/CytronTechnologies/mddrc10 returns 404). Not to be confused with the newer, smaller **MDDRC5** (5 A, RP2040-based) — see /home/claude/kb/mddrc5.md.

## What it is
A dual-channel brushed DC motor driver controlled directly from an R/C receiver, with no microcontroller or coding needed [DS][PP]. It drives two DC motors from a 7–30 V supply at 10 A continuous and 30 A peak per channel (peak limited by the over-current circuit and dependent on board temperature) [DS]. RC1/RC2 work in Independent Mode or Mixed Mode, chosen with an onboard mode selection switch; Mixed Mode is preferred for differential-drive mobile robots [DS]. Neutral points are auto-calibrated at every power-up [DS]. It has test buttons, motor status LEDs and a 5 V / 500 mA output for the receiver [DS]. The power input has **no reverse-polarity protection** [DS][PP].

## Specifications
Datasheet Table 2 is titled **"MDDRC10 Absolute Maximum Ratings"** [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 7 V, Max 30 V | [DS] |
| Maximum motor current (per channel), continuous | Max 10 A | [DS] |
| Maximum motor current (per channel), peak | Max 30 A — footnote *¹: "Peak current is limited by the overcurrent protection circuit. Actual current limit is depending on board temperature. Value shown is at room temperature (25 - 30 degree Celsius)." **No duration stated** | [DS] |
| Motor output PWM frequency | 20 KHz (single value; its column is unclear in the extracted text) | [DS] |
| RC input voltage (RC1 & RC2), low level | 0 – 0.7 V | [DS] |
| RC input voltage (RC1 & RC2), high level | 1.5 – 15 V | [DS] |
| RC signal timing, frequency | 10 – 100 Hz | [DS] |
| RC signal timing, deadband | ±35 µs | [DS] |
| RC signal timing, fullscale | ±435 µs | [DS] |
| 5V output maximum current | 500 mA ("5V output for RC receiver (500mA max, do not use this to power the servo motor)") | [DS] |
| Number of motor channels | 2 ("Bidirectional control for two brushed DC motor.") | [DS][PP] |
| Heatsink | 10 A per channel continuous "without any additional heatsink" | [PP] |
| 5 V regulator type | "Onboard 5V switching regulator" | [PP] |
| Dimensions | Figure 2 only (not readable); product page "Dimensions" also image-only | [DS][PP] |
| Packing list | 1 × 10Amp 7V-30V DC Motor Driver for R/C (2 Channels); 2 × 2561 3-way connector extension wire; 4 × PCB Spacer | [PP] |
| Warranty | 12 months | [PP] |
| Price (product page) | $39.00 ex tax; 5 or more $37.05; 20 or more $35.10; 50 or more $31.20 (www.cytron.io, read 2026-10-16, Out of Stock) | [PP] |
| Operating temperature | Not stated | — |
| Weight | Not stated | — |
| Terminal type / wire size | Not stated | — |
| Neutral (centre) pulse width | Not stated — captured automatically at power-up | [DS] |

## Interfaces, terminals and pin mapping
Board functions (datasheet Table 1) [DS]:
- **Power Input Terminal** — "Connect to battery." VB+ positive, VB- negative. "Connecting in reverse polarity will damage the motor driver instantaneously."
- **Motor Output Terminal** — "Motor direction is depending on the polarity." Swapping MxA and MxB reverses direction.
- **Motor Status LEDs** — on when the motor runs: MxA = Forward*, MxB = Backward* (*actual direction depends on motor connection).
- **Power LED** — on when powered up.
- **Error LED** — blinks when there is an error (chapter 7).
- **OC (Overcurrent) LED** — on when current limiting is in action; "Current limit threshold is depending on the board temperature."
- **Test Buttons** — "Press to test the functionality of the motor driver. Motor will run at full speed." (Which button maps to which direction is shown only in Figure 1.)
- **Mode Selection Switch** — "Select the RC input mode (Independent or Mixed Mode)".
- **RC Input** — RC1/RC2 signal; +5V output for the receiver (500 mA max, not for servos); GND.

Channel mapping [DS]:

| Mode | RC1 (Channel 1) | RC2 (Channel 2) |
|---|---|---|
| Independent | Left motor speed and direction | Right motor speed and direction |
| Mixed | Forward/backward speed | Turn left/right (mixed to both motors) |

Error LED codes (datasheet Table 4) [DS]:

| ERR LED blinks | Meaning |
|---|---|
| 2 | RC Input Error — "No RC signal is detected or the pulse width is out of acceptable range." |
| 4 | Overvoltage Error — "Power input voltage has exceeded the maximum rating." (switching-supply note below) |

No microcontroller pin map, USB port or firmware is described for MDDRC10 [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Turn on the transmitter first, sticks centred, then power the driver.** Neutral points and offsets are calibrated at every power-up: the driver "waits for a valid RC signal and captures it as the neutral point" [DS].
- **No reverse-polarity protection** — a reversed battery damages the driver instantly [DS][PP]. (MDDRC5 *does* have reverse polarity protection — do not copy MDDRC5 wording.)
- Peak is **30 A at 25–30 °C room temperature**, limited by over-current protection and reduced as the board heats up; the datasheet gives **no peak duration** [DS]. Do not write "30 A for 1 s" or similar.
- 10 A is **per channel**, continuous [DS].
- The +5V pin on the RC header is for the **receiver only** — 500 mA max, never power a servo from it [DS].
- Mixed Mode: RC1 = forward/backward, RC2 = left/right. Independent Mode: RC1 = left motor, RC2 = right motor [DS].
- Mixed Mode is preferred for differential-drive mobile robots; Independent Mode "is usually used for non-wheeled motors or when you want to control the motor independently" [DS].
- RC signal must be 10–100 Hz; missing or out-of-range pulses give the 2-blink RC Input Error [DS].
- Motor status LED Forward/Backward labels follow the terminal; fix real direction by swapping MxA/MxB [DS].
- Test buttons run the motor at **full** speed — lift the robot first (MDDRC5's test button is half speed) [DS].
- No coding needed for normal R/C use [PP].

## Power and electrical limits
- Input 7–30 V absolute maximum; datasheet says connect the power input to the battery [DS].
- **Overcurrent protection with active current limiting** — when the motor tries to draw more than the driver can supply, PWM is chopped and current held at the maximum limit; protects against a stalled or oversized motor; OC LED on while limiting [DS].
- **Temperature protection** — "The higher the board temperature, the lower the current limiting threshold" (graph per channel in Figure 5, values not readable) [DS].
- **Undervoltage shutdown** — output shuts down below the lower limit so MOSFETs fully turn on and do not overheat; ERR LED blinks [DS]. Numeric threshold not stated.
- **Overvoltage** — reported as 4 blinks [DS]. Numeric threshold not stated.
- **Switching power supplies / regenerative energy** — "If a switching power supply is being used, connect a motor shunt regulator or rechargeable battery with the same voltage in parallel with the power supply. This is to absorb the regenerative energy from the motor during deceleration." [DS]
- **Reverse polarity** — not protected [DS][PP].
- 5 V receiver output: 500 mA max [DS], from an onboard switching regulator [PP].

## Software support
- None required — the board is controlled from the RC receiver directly; "No coding or programming is needed." [PP]
- No firmware, library, GitHub repository or update procedure is published for MDDRC10 (none found).

## Compatibility and accessories
- R/C receiver: signal on RC1/RC2, powered from the board's +5V (500 mA max) and GND [DS]. Two 2561 3-way extension wires included [PP].
- Two brushed DC motors [DS][PP].
- The datasheet's RC high-level range (1.5–15 V) includes 3.3 V and 5 V signal levels, but the datasheet does not state that driving RC1/RC2 from a microcontroller is supported [DS].
- Product page example applications: "RC Lawn Mower, Combat Robot, Sumo Robot, RC Toy." [PP]
- Product page positioning: "Building a RC vehicle or mobile robot without any microcontroller? MDDRC10 is what you need."; "Plug & play, controlled from RC directly." [PP]

### Differences from MDDRC5 (as stated in each datasheet)

| Item | MDDRC10 [DS Rev 1.0, Aug 2020] | MDDRC5 [DS Rev 1.0, Mar 2026] |
|---|---|---|
| Continuous / peak per channel | 10 A / 30 A (temperature-dependent, no duration) | 5 A / 20 A (< 1 s) |
| Reverse polarity | Not protected — damages driver instantly | Reverse polarity protection |
| Temperature protection | Yes — current limit falls with board temperature | Not listed in datasheet |
| RC auto-calibration at power-up | Yes | Not stated |
| Test buttons | Full speed | Single button, half speed |
| Microcontroller / USB-C / firmware | Not described | RP2040, USB-C, UF2 firmware |
| Motor alignment pots | None described | FWD/REV pots |
| Power terminal labels | VB+ / VB- | V+ / V- |
| Same in both | 7–30 V input; 20 kHz PWM; RC low 0–0.7 V / high 1.5–15 V; 10–100 Hz; ±35 µs deadband; ±435 µs fullscale; 5 V 500 mA; error codes 2/3/4 blinks | |

## Common mistakes / troubleshooting
- **Robot creeps or one motor turns at neutral** — driver was powered before the transmitter, or sticks were off-centre at power-up; re-power with transmitter on and sticks centred [DS].
- **2 blinks** — no RC signal / pulse out of range: check receiver binding, power and RC1/RC2 wiring [DS].
- **4 blinks** — overvoltage, often a switching or bench supply pushed up by motor regeneration; add a shunt regulator or same-voltage rechargeable battery in parallel [DS].
- **OC LED on / weak motors when hot** — current limiting; the limit drops as the board heats [DS].
- **Board dead after first connection** — reversed battery; there is no reverse-polarity protection [DS].
- **Receiver browns out** — do not power servos from the +5V pin [DS].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Peak current conditions | [DS]: 30 A peak, limited by OC circuit, temperature-dependent, value at 25–30 °C | [PP]: "10A continuous, 30A peak" (no conditions) | Consistent value; always give the [DS] conditions |
| Regenerative braking | [PP] Q&A asks; Cytron answer refers the customer to support | [DS]: not stated | Unknown — Needs verification |

No numeric conflicts were found between the datasheet and the product page.

## Needs verification
- Dimensions and mounting-hole spacing (Figure 2 not readable; product page dimensions are image-only).
- Current-limit vs temperature values (Figure 5 not readable).
- Failsafe behaviour on RC signal loss (stop/brake/coast) — not stated.
- Whether the mode switch is read only at power-up.
- Brake vs coast at neutral; regenerative braking.
- Numeric undervoltage and overvoltage thresholds.
- Operating temperature, weight, terminal type and wire size.
- "Discrete NMOS H-Bridge design" — stated only by a reseller (Robokits India) [3P].
- Location of the original Cytron Google Doc datasheet and whether a newer revision exists.
- Exact column placement of the 20 KHz PWM value in Table 2 (text extraction ambiguous).

## Sources
- [DS] MDDRC10 Datasheet, "10Amp 7V-30V DC Motor Driver for R/C (2 Channels)", Rev 1.0, August 2020 — public mirror: https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf
- [DS] Same datasheet, second public mirror — https://aws.robu.in/wp-content/uploads/2021/03/Cytron-10Amp-7V-30V-DC-Motor-Driver-for-RC-2-Channels-MDDRC10-1.pdf
- [PP] Product page, "10Amp 7V-30V DC Motor Driver for R/C (2 Channels)" (read 2026-10-16) — https://www.cytron.io/p-10amp-7v-30v-dc-motor-driver-for-rc-2-channels
- [PP] my.cytron.io copy (not read — fetch failed) — https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-for-rc-2-channels
- [3P] Robokits India listing (cross-check only) — https://robokits.co.in/motor-drives-drivers/rhino-cytron-dc-motor-drivers/cytron-10amp-7v-30v-dc-motor-driver-for-r-c-2-channel-mddrc10-original
- Comparison basis: /home/claude/kb/mddrc5.md (MDDRC5 Datasheet Rev 1.0, March 2026)
