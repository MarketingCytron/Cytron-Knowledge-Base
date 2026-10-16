# Rotary Encoder Kit (RE08A) — Verified Reference

| | |
|---|---|
| Product code | `RE08A` [PP]; manual title "RE08A Rotary Encoder Kit" [UM] |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **No Cytron datasheet exists for this product.** Highest source is the Cytron user manual: "RE08A Rotary Encoder Kit — User's Manual **V1.2, September 2008**" [UM], read from the RobotShop PDF mirror of the Cytron document (the Drive PDF linked from the product page was not readable here). The manual's specification table was recovered from text extraction and cross-checked twice; cells that stayed ambiguous are listed under *Needs verification* |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A simple single-channel optical rotary encoder kit: a sensor board with a slotted-disc opto interrupter and a slotted disc with 8 slots that gives 16 transitions per revolution [UM]. The board has a 3-pin interface (+5, Gnd, Sig), a green indicator LED, and a pulse output that is internally pulled up to 5 V, so no soldering or external components are needed [UM]. It is meant to be mounted on a motor shaft or gear output so a microcontroller can count pulses for rotation, speed or distance [UM].

## Specifications
Manual section 3 "Product Specification" [UM]. The table was read from PDF text extraction; columns were recovered consistently in two independent passes. Cells marked (?) could not be assigned with certainty and are repeated under *Needs verification*.

| Item | Value | Src |
|---|---|---|
| +5 — sensor board supply voltage | Min 4.5 V, Typ 5 V, Max 5.5 V | [UM] |
| Gnd — system ground | 0 V | [UM] |
| Sig — signal output | 0 V to 5 V pulse ("The generated pulses are a 0 to 5V output"); table max 5.3 V (?) | [UM] |
| Vlow — voltage during low state (+5 = 5 V) | Min 0 V, Typ 0.8 V, Max 1.0 V | [UM] |
| Vhigh — voltage during high state (+5 = 5 V) | Min 4.5 V, Typ 4.7 V, Max 4.9 V | [UM] |
| f — output frequency | Up to 1 kHz ("Up to 1 KHz (1000 pulse/sec)") | [UM] |
| Ion — current at low state | Min 25 mA, Typ 30 mA, Max 40 mA | [UM] |
| Ioff — current at high state | Min 5 uA, Typ 10 uA, Max 20 uA | [UM] |
| TOPR — operating temperature | Min 0 °C, Typ 25 °C, Max 75 °C | [UM] |
| Disc | 8 slots → 16 transitions per revolution | [UM] |
| Disc size | 35 mm outer diameter x 3 mm inner diameter | [UM] |
| Sensor board size | 12 mm (height) x 35 mm (length) x 15 mm (width) | [UM] |
| Interface | 3 pins: +5, Gnd, Sig | [UM] |
| Output pull-up | Sig internally pulled up to 5 V | [UM] |
| Indicator | Green LED, ON when the disc does not block the optical sensor | [UM] |
| Packing list | 1 x RE08A sensor board; 1 x 8-slot disc | [UM] |
| Price | RM38.85 | [PP] |
| Warranty | 12 months [PP]; manual (2008) says 6 months [UM] — see Conflicts | [PP][UM] |

## Interfaces, terminals and pin mapping
Board layout labels [UM section 4]:

| Label | Item | Description |
|---|---|---|
| A | Optical sensor | Slotted opto interrupter; senses the disc slots and generates pulses on Sig |
| B | +5 | Supply input pin; connect 5 V (+) |
| C | Gnd | Ground of the 5 V supply (negative terminal) |
| D | Sig | Signal / pulse output; internally pulled up to 5 V, no extra component needed |
| E | LED | Indicator; lights when the disc does not block the sensor |

**Output truth table** [UM]:

| Optical beam | LED | Sig |
|---|---|---|
| Unblocked (slot in front of sensor) | ON | 0 V (low) |
| Blocked (solid part of disc) | OFF | +5 V (high) |

Wiring [UM section 5]: connect "+5" and "Gnd" to a 5 V supply and "Sig" to a microcontroller counter / clock / encoder-capable input; mount the 8-slot disc on the motor shaft or gear output so the disc passes through the sensor gap. The microcontroller then reads the 0-5-0 V pulse train and counts pulses to obtain rotation, speed or distance; software configuration is not covered and depends on the controller [UM section 6].

## Rules and gotchas (for code, wiring and tutorials)
- **16 pulses (transitions) per revolution**, not 8: the 8-slot disc gives 16 transitions [UM]. Count edges accordingly, and say whether you count rising edges, falling edges or both.
- **Single channel only** — one Sig line, so it gives speed/distance but **cannot determine direction** (derived: the manual lists only one signal output and no quadrature).
- **Output is active-low for a slot**: Sig is 0 V when the beam is unblocked and 5 V when blocked; LED on = unblocked [UM]. Do not describe "slot = high".
- **5 V part**: supply 4.5–5.5 V and a 5 V pull-up on Sig [UM]. For a 3.3 V controller the Sig line needs level shifting or a divider (derived from [UM] levels).
- **Max output frequency 1 kHz** [UM] — at 16 pulses/rev that caps measurable shaft speed at about 3750 rpm (derived: 1000 x 60 / 16). Do not mount it on a fast motor shaft without gearing down.
- **Do not reverse the supply polarity** — it can damage the sensor; there is no stated polarity protection [UM].
- **Do not break the disc slots** during installation [UM].
- No library, no GitHub example and no wiring diagram for Arduino/Pi exist from Cytron; treat it as a plain digital pulse input.

## Power and electrical limits
- Supply 4.5–5.5 V, 5 V typical [UM].
- Output low 0–1.0 V (0.8 V typ); output high 4.5–4.9 V (4.7 V typ), with +5 = 5 V [UM].
- Current: 25–40 mA (30 mA typ) at low state; 5–20 uA (10 uA typ) at high state [UM].
- Operating temperature 0–75 °C [UM].
- Reverse polarity: not protected; may damage the sensor [UM].

## Software support
- None from Cytron: the manual says software configuration "is not covered and depends on the specific microcontroller's datasheet" [UM]. No Cytron GitHub repository or library found for RE08A (checked raw.githubusercontent.com, 2026-10-16).
- Use any digital input with edge counting, an external-interrupt pin, or a timer/counter clock input [UM wording: "counter, clock, or encoder input"].

## Compatibility and accessories
- Kit contents: sensor board and 8-slot disc; "ready to use without further soldering" [UM].
- Disc inner diameter 3 mm [UM] — fits a 3 mm shaft; the manual says "motor shaft or gear output" without naming a motor.
- Any 5 V microcontroller with a digital input [UM].

## Common mistakes / troubleshooting
- **Count is double what you expected** → 16 transitions/rev, not 8 [UM].
- **No pulses** → disc not passing through the sensor gap, or Sig wired to an analog-only pin; check the LED toggles as the disc turns [UM].
- **Missed counts at speed** → above the 1 kHz output limit [UM].
- **Sensor dead after wiring** → reversed polarity [UM].
- **Direction wrong / unknown** → single-channel encoder; direction must come from the motor command, not the encoder (derived).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Warranty | [UM] (2008) "valid for 6 months" | [PP] 12 months (2026) | Commercial term: use the current product page's 12 months and cite [PP]; the manual figure is historical |
| Product name | [UM] "RE08A Rotary Encoder Kit" | [PP] "Rotary Encoder Kit (RE08A)"; [3P] RobotShop "Cytron Simple Rotary Encoder Kit" | Use the Cytron name; the RobotShop name is an alias only |

## Needs verification
- Spec-table cells recovered from text extraction with lower confidence: Sig "max 5.3 V"; Gnd row values; whether f has a stated minimum. Confirm against the original PDF page 5.
- Whether Ion/Ioff are output-stage currents or board supply currents — the manual's wording ("Current at low state / high state") does not say.
- Whether the product-page Drive PDF (0BzFWfMiqqjyqdlpDUTc5ektndlE) is the same V1.2 Sept 2008 revision as the RobotShop mirror.
- Mounting: whether the disc is a press fit on a 3 mm shaft, and whether the sensor board has mounting holes (not stated).
- Debounce/hysteresis of the output (not stated); pull-up resistor value (not stated).
- [3P] RobotShop lists SKU RB-Cyt-39, USD 9.25, "industrial-grade PCB" — not used as spec.

## Sources
- [UM] RE08A Rotary Encoder Kit — User's Manual V1.2, September 2008 — PDF mirror https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-39/pdf/cytron-simple-rotary-encoder-kit-users-manual.pdf (same document as the product-page link https://drive.google.com/file/d/0BzFWfMiqqjyqdlpDUTc5ektndlE/view — not opened; second mirror https://manualzilla.com/doc/5847835/user-s-manual)
- [VEN] Opto interrupter sensor datasheet — https://drive.google.com/file/d/1W325u-x-zk5iBvhIYAIK9lkwc46noYFn/view (not opened)
- [PP] Product page https://my.cytron.io/p-rotary-encoder-kit (read by coordinator 2026-10-16: RM38.85, in stock 2, warranty 12 months)
- [3P] (cross-check only) https://www.robotshop.com/products/cytron-simple-rotary-encoder-kit
