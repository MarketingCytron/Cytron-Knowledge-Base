# Maker Reflect — Verified Reference

| | |
|---|---|
| Product code | `MAKER-REFLECT` (datasheet title [DS]; product page code `MAKER-REFLECT`, page variant code `V-MAKER-REFLECT` [PP]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **MAKER-REFLECT Datasheet — "Analog Reflectance Sensor (Line Detector)" — Rev 1.0, November 2019** (public Google Doc linked from the product page): https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: the datasheet is public (linked from the my.cytron.io product page and from The Pi Hut, Botland and element14 listings; Farnell mirrors it as `farnell.com/datasheets/4725988.pdf`). [PP] facts (code, price, stock, documents, the "Maker Reflect S" note) were read from the product page by the coordinator on 2026-10-16; the page text itself was not read here. No user manual, no Cytron GitHub example and no [DT] confirmation exist for this product. The datasheet is three short sections (board functions, a 3-row spec table, a dimension drawing); figures are not readable as text.

## What it is
A tiny analog infrared reflectance sensor, titled "Analog Reflectance Sensor (Line Detector)" in its datasheet [DS]. An IR LED shines onto the surface and the sensor gives an **analog output voltage: higher voltage = darker surface** [DS]. It has a single 3-pin connector (VCC, GND, OUT), runs from 3.0–5.5 V and senses 1–40 mm (at VCC = 5 V, black line on white) [DS]. Sold as "Maker Reflect: Simplifying IR Reflectance Sensor for Beginner" [PP]. Cytron uses it as an **edge sensor** on sumo robots: the SUMO:BIT datasheet names "Maker Reflect" for its edge-sensor ports [DS of SUMO:BIT].
Positioning (marketing, not spec): "Simplifying IR Reflectance Sensor for Beginner" [PP]; reseller copy calls it "a tiny reflectance sensor which consists of an infra-red (IR) LED that transmits IR light onto a surface" with a phototransistor reading the reflection [3P].

## Specifications
Datasheet Table 2 is titled **"MAKER-REFLECT Absolute Maximum Ratings"** and has three rows, numbered 1, 3 and 4 (there is no row 2) [DS].

| Item | Value | Src |
|---|---|---|
| VCC voltage | Min 3.0 V, Max 5.5 V | [DS] |
| Analog output voltage | Min 0 V, Max VCC | [DS] |
| Sensing distance (VCC = 5 V, black line on white surface) | Min 1 mm, Max 40 mm | [DS] |
| Sensor type | "IR Reflectance Sensor — Infrared sensors for line detection" | [DS] |
| Output type | Analog voltage; "Higher voltage = darker surface" | [DS] |
| Output polarity (same fact, reseller wording) | "Analog Voltage (White surface = lower voltage)" | [3P] |
| Connector | 3 pins: VCC, GND, OUT | [DS] |
| Reverse polarity | **No protection**: "Warning: Reversed Polarity will damage the sensor" | [DS] |
| Supply current | **Not stated** | [DS] |
| Sensor / IR IC part number | **Not stated** | [DS] |
| Threshold / calibration | None on board — raw analog output only (no trimmer, switch or calibration is listed in the board-functions table) | [DS] |
| Indicator LED | **None listed** in the board-functions table | [DS] |
| Dimensions | **Not stated in text** (Figure 3 drawing only). [3P] 18.1 × 8.4 × 4.2 mm excluding header pin — see Needs verification | [DS] |
| Operating temperature | **Not stated** | [DS] |
| Weight | **Not stated** [DS]; [3P] element14 0.01 kg, Botland 0.002 kg | — |

Footnote [DS]: "Sensing distance may reduce if VCC is less than 5V or the line-background contrast is low."

## Interfaces, terminals and pin mapping
Connector [DS Table 1] (physical pin order is shown in Figure 1 only, not in text):

| Pin | Function | Src |
|---|---|---|
| VCC | "Power input for the Maker Reflect." (3.0–5.5 V) | [DS] |
| GND | Ground | [DS] |
| OUT | "Analog output. Higher voltage = darker surface." | [DS] |

- No other pin, jumper, trimmer, switch or LED is listed in the datasheet [DS].
- [3P] Botland: 3-pin 2.54 mm pin header; [3P] The Pi Hut: mounting hole at the centre of the board — not in the datasheet text.

## Rules and gotchas (for code, wiring and tutorials)
- **Analog only.** Read OUT with `analogRead()` / an ADC pin. The output swings 0 V to VCC [DS]; there is no digital output and no on-board threshold — the threshold is set in code (derived from [DS]). (The newer Maker Reflect S is the variant whose datasheet says "Digital IO Compatible / No ADC required" — do not mix the two up; see `maker-reflect-s.md`.)
- **Dark = high.** A black line or the dark outside of a sumo ring gives a *higher* voltage; a white surface gives a *lower* voltage [DS]. Sumo "edge detected" logic therefore looks for a reading **below** a threshold (white ring edge) — consistent with the Maker Mini Sumo library, where `isEdgeDetected()` is true when `analogRead()` is below the threshold [GH via maker-mini-sumo.md].
- **Power OUT's reference from the controller's logic voltage.** OUT can reach VCC [DS]; power the sensor at the same voltage as the ADC reference (3.3 V for a 3.3 V board) so the reading never exceeds the ADC input (derived from [DS]).
- **No reverse-polarity protection** — reversed VCC/GND damages the sensor [DS]. Check the wiring before power-up.
- **Sensing distance 1–40 mm is quoted at VCC = 5 V with a black line on white**; it shrinks at lower VCC or low contrast [DS]. Quote the conditions with the number.
- **No library, no calibration button, no line-colour switch** — do not borrow Maker Line features (calibration, EEPROM, digital outputs) when describing it.
- Do not quote an "optimal sensing distance" for MAKER-REFLECT; only [3P] element14 says "approximately 3 mm", and the Cytron datasheet that states 3 mm is the **Maker Reflect S** one.

## Power and electrical limits
- VCC 3.0 V min, 5.5 V max (absolute maximum ratings table) [DS].
- Analog output 0 V to VCC [DS].
- Reversed polarity will damage the sensor [DS].
- Supply current, output drive capability, over-voltage behaviour: **not stated** [DS].

## Software support
- No Cytron library or GitHub example found. Read OUT as an analog input from any language (Arduino `analogRead()`, MicroPython/CircuitPython ADC) — derived from [DS] (analog output only).
- Maker Mini Sumo (`MAKER-MSUMO`): the Cytron Maker Sumo Library reads the edge ports (A0 `EDGE_L`, A1 `EDGE_R`) with `analogRead()`, with `calibrateEdgeSensors()` / `isEdgeDetected()` [GH via maker-mini-sumo.md]. The datasheet does not name a compatible board.

## Compatibility and accessories
- Datasheet names no compatible boards [DS]; any controller with an analog input and a 3.0–5.5 V supply fits (derived from [DS]).
- **SUMO:BIT** edge-sensor ports: male headers for "Maker Reflect or any other analog sensors"; a voltage divider adjusts the output voltage [DS of SUMO:BIT].
- **Maker Mini Sumo Controller**: edge ports S (analog) / + (+5V) / − (GND) on A0/A1 [DS of MAKER-MSUMO]. The Ikedo Mini Sumo Robot V2 kit lists its 2 edge sensors as "Maker Reflectance Sensor"  / "Maker Reflect S" [PP] — which exact variant ships is unresolved (see Needs verification).
- Sold with option "Maker Reflect S" on the same product page: "The new Maker Reflect S comes with a smaller threshold sensing for more stable output" [PP].
- Documents linked from the product page: datasheet only [PP]. No 3D CAD link.
- Applications listed by resellers (not in the datasheet): line following, edge/border sensing in sumo robots, wall sensing in maze robots, short-distance presence detection, wheel encoders [3P].

## Common mistakes / troubleshooting
- **Reading is inverted from what the code expects** → remember higher voltage = darker surface [DS]; invert the comparison, not the wiring.
- **Reading is flat / sensor dead after wiring** → reversed polarity damages it [DS]; check VCC/GND.
- **Short range or weak contrast on 3.3 V** → expected; 1–40 mm is specified at VCC = 5 V, and reduces at lower VCC or low contrast [DS].
- **Readings vary between robots** → there is no on-board calibration; set and store the threshold in code (Maker Mini Sumo library stores it in EEPROM from address 0 [GH via maker-mini-sumo.md]).
- **Expecting a digital HIGH/LOW** → this is the analog model; the Maker Reflect S datasheet is the one that says "Digital IO Compatible" [DS of MAKER-REFLECT-S].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply voltage wording | [DS] VCC 3.0–5.5 V | [3P] The Pi Hut "3.3V and 5V Compatible" | Not a contradiction; state 3.0–5.5 V [DS] |
| Optimal sensing distance | [DS] not stated (only 1–40 mm range) | [3P] element14 "approximately 3 mm" (matches the Maker Reflect S datasheet, not this one) | Do not quote for MAKER-REFLECT; see Needs verification |
| Weight | [3P] element14 0.01 kg | [3P] Botland 0.002 kg | Neither is a spec; not stated by Cytron |
| Spec table numbering | [DS] rows numbered 1, 3, 4 | — | Row 2 is missing in the datasheet; not a data error, just note it |
| Edge sensor in Ikedo V2 kit |  Ikedo V2 guide "Maker Reflectance Sensor" (links the MAKER-REFLECT page per INDEX.md) | [PP] Ikedo V2 page "Maker Reflect S" | Unresolved; neither Reflect datasheet mentions the Ikedo kit |

## Needs verification
- **Dimensions**: [3P] The Pi Hut and Botland 18.1 × 8.4 × 4.2 mm (excluding header pin); datasheet Figure 3 not readable as text. Confirm from the drawing.
- **Supply current** — not stated (the Reflect S datasheet states 25 mA; do not transfer it).
- **IR emitter / phototransistor part number** — not stated.
- **Connector pin order** (VCC/GND/OUT left-to-right) and header type (right-angle or straight) — figure only; [3P] 2.54 mm pin header.
- **Mounting hole** position and size — [3P] The Pi Hut "at the center"; not in text.
- **Optimal sensing distance ~3 mm** — [3P] element14 only.
- **Which Reflect variant ships in the Ikedo Mini Sumo Robot V2 kit** — neither datasheet mentions Ikedo; ask the design team.
- Whether the Farnell PDF mirror (https://www.farnell.com/datasheets/4725988.pdf) is the same Rev 1.0 — not opened.
- [3P] prices (cross-check only): RobotShop USD 2.00; The Pi Hut £2.20 incl. VAT.

## Sources
- [DS] MAKER-REFLECT Datasheet, "Analog Reflectance Sensor (Line Detector)", Rev 1.0, November 2019 — https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit (public; PDF mirror listed by element14, not opened: https://www.farnell.com/datasheets/4725988.pdf)
- [PP] Product page https://my.cytron.io/p-maker-reflect-ir-reflectance-sensor-for-beginner (read by the coordinator 2026-10-16: code MAKER-REFLECT / V-MAKER-REFLECT, RM8.00–RM9.00 depending on option, in stock 1815, warranty 12 months, datasheet link, "The new Maker Reflect S comes with a smaller threshold sensing for more stable output")
- [DS of MAKER-REFLECT-S] https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit (see `maker-reflect-s.md`)
- [DS of SUMO:BIT] via KB entry sumo-bit.md · [DS of MAKER-MSUMO] + [GH] Cytron Maker Sumo Library via KB entry maker-mini-sumo.md ·  Ikedo Bot V2 Getting Started Instruction via maker-mini-sumo.md / maker-object.md
- [3P] (cross-check only) https://thepihut.com/products/maker-reflect-ir-reflectance-sensor-for-beginners · https://botland.store/sensors-odbiciowe/16056-cytron-maker-reflect-analog-ir-reflectance-sensor-5904422365981.html · https://au.element14.com/cytron/maker-reflect/simplifying-ir-reflectance-sensor/dp/4871626 · https://www.robotshop.com/products/cytron-maker-reflect-reflectance-sensor
