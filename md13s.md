# MD13S — Verified Reference

| | |
|---|---|
| Product code | `MD13S` (manual title [UM]; "Product Code: MD13S" on product page [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (features, three purchase options and packing lists, resources). Back in stock; option list and terminal-colour wording re-read |
| Primary source | "MD13S 13Amp DC Motor Driver User's Manual" — **V1.1, June 2018** (Cytron Technologies; title page "Product User's Manual – MD13S") — public PDF mirror: https://www.electrokit.com/upload/product/41018/41018267/MD13S%20User's%20Manual.pdf |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A single-channel, bi-directional driver for one brushed DC motor, rated 13 A continuous and 30 A peak (10 seconds), powered from 6 V to 30 V [UM]. It is controlled by PWM and DIR inputs (sign-magnitude or locked-antiphase PWM, up to 20 kHz) from a microcontroller at 3.3 V or 5 V logic, and is not for RC-receiver PWM [UM]. It has a fully NMOS H-bridge ("no heat sink is required"), a Grove-compatible input connector, test switches, and MA/MB, Power, OC and ERR LEDs [UM].
- Manual introduction: "MD13S is designed to drive high current brushed DC motor up to 13A continuously. It offers several enhancements such as support for both locked-antiphase and sign-magnitude PWM signal because it uses full solid state components which is able to provide faster response time and eliminate the wear and tear of the mechanical relay." [UM]

## Specifications
Manual section 4 "Product Specification", table **"Absolute Maximum Rating"** (columns No., Parameters, Min, Typical, Max, Unit) [UM].

| Item | Value | Src |
|---|---|---|
| Power input voltage | Min 6 V, Max 30 V | [UM] |
| IMAX (maximum continuous motor current) | Max 13 A; feature list: "13A continuous (without heatsink at 25℃)" | [UM] |
| IPEAK (peak motor current) | Max 30 A — "* Must not exceed 10 seconds." | [UM] |
| Current limiting | "Current limiting at 30A." (feature list) | [UM] |
| VIOH (logic input – high level) | Min 3 V, Max **5.5 V** | [UM] |
| VIOL (logic input – low level) | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | 20 KHz — "** Actual output frequency is same as input frequency." | [UM] |
| Table note | "*** Tested in room temperature." (row it attaches to not readable in the extracted text) | [UM] |
| Number of channels | 1 — "Bi-directional control for one brushed DC motor." | [UM] |
| Logic level input | "3.3V and 5V logic level input." | [UM] |
| Control modes | Locked-antiphase and sign-magnitude PWM; "Support TTL PWM from microcontroller, not PWM from RC receiver." | [UM] |
| RC servo signal / analog / serial (UART) input | RC servo signal: No [PP]; analog and serial: not stated in [UM] or [PP] | [PP] |
| H-bridge | "Fully NMOS H-Bridge for better efficiency and no heat sink is required." | [UM] |
| Regenerative braking | "Regenerative Braking" (feature bullet) | [PP] |
| Grove | "GROVE compatible connector." | [UM] |
| SMD compatible | "SMD Compatible" (board label J; Eagle CAD library footprint in Dimension section) | [UM] |
| Logic supply | No separate logic supply pin; terminal block has POWER+ / POWER- only, input header GND/PWM/DIR | [UM] |
| Reverse polarity protection | **None** — spec table "Polarity Protection: NO" | [PP] |
| Over-current protection | "Current limiting at 30A"; OC LED "Output current is over 30A limit." Behaviour (limit vs shutdown) not described | [UM] |
| Thermal / under-voltage protection | Not stated | — |
| Fault indication | ERR LED "will illuminate when fault detected in on board MOSFET driver." | [UM] |
| Cooling fan | No | [PP] |
| Test buttons | 2 (MA, MB) | [UM] |
| Dimensions | 61 mm x 33 mm | [UM][PP] |
| Operating temperature | Not stated (only "25℃" / "room temperature" test conditions) | — |
| Compliance | "RoHS, FCC and CE compliance" | [PP] |
| Warranty | 12 months; manufacturing defects only; misuse and two-way freight not covered | [UM][PP] |
| Packing list | 1 x MD13S 13A DC Motor Driver; 2 x Terminal socket, "Black for power and Green for Motor"; Grove connector with cable | [UM] (see *Conflicts* for colours) |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Options & packing:** (1) MD13S with pre-soldered terminal blocks — board with 1 green + 1 black 2-way terminal block, 1 Grove-to-Grove cable; (2) non-soldered terminal blocks — board, 1 green + 1 black 2-way terminal block (loose), 1 Grove-to-Grove cable; (3) **pre-soldered pin headers (for SUMO:BIT)** — board only [PP].
- Page note: "The terminal block, normally Black is for Motor, and Green is for Power" [PP] (manual says the opposite — see *Conflicts*).
- Features: 1 brushed motor; 6–30 VDC; 13 A continuous, 30 A peak (10 s); GROVE compatible; 3.3 V and 5 V logic; NMOS H-bridge, no heatsink; regenerative braking; PWM up to 20 kHz; locked-antiphase and sign-magnitude, not RC PWM; SMD compatible; RoHS, FCC and CE; 61 × 33 mm [PP].
- Resources: user's manual, CytronMotorDriver library, MD10C tutorial (MD10C and MD13S are compatible), EAGLE footprint, Fritzing, RoHS/FCC/CE certificates, CAD [PP].

## Interfaces, terminals and pin mapping
**Board labels (manual section 3 "Board Layout")** [UM]: A terminal block; B MA LED; C MB LED; D MA test switch; E MB test switch; F input pins; G power LED; H OC LED; I ERR LED; J SMD compatible.

**Terminal block (4 pins)** [UM]:

| Name | Description |
|---|---|
| POWER + | "Positive Supply (6V to 30V)" |
| POWER - | Negative supply |
| Motor Output A | Motor terminal A |
| Motor Output B | Motor terminal B |

Exact physical pin order on the block was not readable from the extracted text.

**Input pins** [UM]:

| Name | Description |
|---|---|
| GND | "Logic ground." |
| PWM | "PWM input for speed control" — "it is not for RC PWM operation" |
| DIR | "Direction control." |

The board is "GROVE compatible" and ships with a Grove cable, but **no Grove pinout (which Grove wire is PWM/DIR) is given** in [UM] or [PP].

Truth table [UM]:

| PWM | DIR | Output A | Output B |
|---|---|---|---|
| Low | X (Don't care) | Low | Low |
| High | Low | High | Low |
| High | High | Low | High |

LEDs and buttons [UM]:
- MA LED: "Turns on when the output A is high and output B is low" (current A to B). MB LED: on when output A is low and output B is high (current B to A).
- Power LED: "Should be on when the board is powered on."
- OC LED: "OC (Over Current) LED Indicator, Output current is over 30A limit."
- ERR LED: "Error LED Indicator, it will illuminate when fault detected in on board MOSFET driver."
- MA test switch: "current flows from output A to B and motor will turn CW"; MB test switch: "current flows from output B to A and motor will turn CCW" (actual direction depends on motor wiring).
- Wire size / terminal current rating: not stated.

Mode selection — by wiring, no jumper or switch [UM]:
- **Sign-magnitude:** two signals; PWM pin = speed, DIR pin = direction.
- **Locked-antiphase:** one signal; PWM pin held high, PWM signal on DIR. "When the PWM signal has 50% duty cycle, the motor stops running." Below and above 50% turn the motor in opposite directions (CW/CCW depends on connection).

## Rules and gotchas (for code, wiring and tutorials)
- Logic inputs: 3.3 V or 5 V only — VIOH max **5.5 V** [UM]. Do not drive from 12 V/24 V (PLC) logic.
- Check polarity before power-up — "Polarity Protection: NO" [PP].
- Connect controller GND to the input GND ("Logic ground") [UM].
- PWM LOW = both outputs low regardless of DIR [UM].
- Not for RC-receiver PWM [UM][PP].
- 13 A continuous is stated "without heatsink at 25℃"; 30 A peak must not exceed 10 seconds [UM].
- The OC LED lights above the 30 A limit [UM]; what the driver then does is not stated — do not promise "auto shutdown" or "auto recovery" in content.
- Grove cable is included, but the Grove pin mapping is not documented — show wiring with GND/PWM/DIR labels, not Grove wire colours.
- Terminal colours: manual says black = power, green = motor; product page says the opposite — see *Conflicts*; tell readers to follow the board's POWER/MOTOR labels.
- Direction labels depend on motor wiring; swap Output A/B to reverse [UM].

## Power and electrical limits
- Supply 6–30 V [UM].
- Continuous 13 A (without heatsink at 25℃), peak 30 A for ≤ 10 s, current limiting at 30 A [UM].
- Battery vs switching power supply / regenerative current: **not stated** in [UM] or [PP] spec text. [PP] lists "Regenerative Braking" as a feature. A Cytron reply in the product-page Q&A (11/12/2020) says: "you may consider LiPo or SLA battery" [PP].
- Thermal protection, under-voltage behaviour: not stated in any source.
- No heatsink required per manual [UM]; no derating curve or operating temperature range given.

## Software support
- Arduino: **Cytron Motor Drivers Library** (version 1.0.1, architectures=*), Library Manager name "Cytron Motor Drivers Library". MD13S is listed under the **PWM_DIR** example [GH].
  - `CytronMD motor(PWM_DIR, 3, 4);  // PWM = Pin 3, DIR = Pin 4.` then `motor.setSpeed(-255..255)`; positive speed writes DIR LOW (Output A high per truth table) [GH][UM].
  - Example wiring comment: Arduino D3 → PWM, D4 → DIR, GND → GND [GH].
- MicroPython / CircuitPython / tutorials: none stated in [UM] or [PP].

## Compatibility and accessories
- Controllers: any microcontroller with 3.3 V or 5 V TTL PWM [UM]; [PP]: "Arduino Shield: No- can be used with Wire connection".
- Grove-compatible connector; Grove-to-Grove cable included [UM][PP].
- Brushed DC motors only, one motor [UM].
- Eagle CAD library footprint referenced in Dimension section [UM] (file location not stated).

## Common mistakes / troubleshooting
- Board damaged at power-up → reversed polarity; no polarity protection [PP].
- Driving inputs from 12 V/PLC logic → exceeds VIOH 5.5 V [UM].
- No response from an RC receiver → RC PWM not supported [UM].
- OC LED on → output current over the 30 A limit (stall, oversized motor) [UM].
- Quick check without code → press MA/MB test switches; the matching MA/MB LED should light [UM].
- Motor spins the wrong way → swap Output A/B or invert DIR in code [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Terminal socket colours | [UM]: "2 x Terminal socket, Black for power and Green for Motor" | [PP]: "1 x Green + Black 2-way terminal blocks (Normally Black is for Motor, Green is for Power)" | [UM] wins in text; colour assignment flagged for [DT] confirmation |
| Packing list wording | [UM]: "Grove connector with cable" | [PP]: "1 x Grove connector (Grove to Grove)" | Same item; no value conflict |
| Dimensions | [UM][PP]: 61 mm x 33 mm | [3P] Farnell/element14 (Seeed 108070021): "65mm x35mm x15mm" | [UM] wins; [3P] not used |
| Channels | [UM][PP]: 1 | [3P] Farnell/element14: "Motor Channel 2" | [UM] wins; [3P] error |

## Needs verification
1. Grove connector pinout (which pins carry PWM, DIR, GND; whether the Grove VCC pin is connected) — not stated.
2. Over-current behaviour at the 30 A limit (current limiting vs shutdown, recovery) — only "Current limiting at 30A" and the OC LED are stated.
3. Thermal protection and under-voltage behaviour — not stated.
4. Battery vs SMPS / regenerative current guidance — no warning in [UM]; confirm with [DT] whether the MDD10A/MD10C-style "use a battery" warning applies.
5. Which table row the "*** Tested in room temperature." note attaches to; physical pin order on the terminal block; connection diagram in section 6 (figures not readable).
6. Terminal socket colours (see *Conflicts*).
7. Operating temperature range, wire size and terminal current rating — not stated.
8. Revision history — the manual (V1.1) has no revision table; board revisions not documented.
9. [3P]-only: G.W 22.5 g, height 15 mm (Farnell/element14).

## Sources
- [UM] MD13S 13Amp DC Motor Driver User's Manual, V1.1, June 2018 (Cytron), public PDF mirror: https://www.electrokit.com/upload/product/41018/41018267/MD13S%20User's%20Manual.pdf
- [UM] mirror linked from RobotShop (could not be opened): https://cdn.robotshop.com/media/c/cyt/rb-cyt-212/pdf/MD13S_User-Mannual.pdf
- [PP] Product page "13Amp 6V-30V DC Motor Driver": https://my.cytron.io/p-13amp-6v-30v-dc-motor-driver (read 16 Oct 2026; www.cytron.io/p-md13s and www.cytron.io/p-13amp-6v-30v-dc-motor-driver failed to load)
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
- [3P] RobotShop listing (cross-check): https://jp.robotshop.com/en/products/cytron-13a-dc-motor-driver-grove-compatible
- [3P] Farnell/element14 page for Seeed 108070021 (cross-check only): https://www.farnell.com/datasheets/3708173.pdf
