# Maker Reflect S — Verified Reference

| | |
|---|---|
| Product code | `MAKER-REFLECT-S` (datasheet title [DS]; product page option "Maker Reflect S", code `MAKER-REFLECT-S` [PP]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **MAKER-REFLECT-S Datasheet — "Analog Reflectance Sensor (Line Detector)" — Rev 1.0, February 2026** (public Google Doc linked from the product page): https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: the datasheet is public (linked from the my.cytron.io product page). [PP] facts (code, price, stock, documents, the one-line description of the S variant) were read from the product page by the coordinator on 2026-10-16; the page text itself was not read here. No user manual, no Cytron GitHub example, no reseller listing and no [DT] confirmation exist for this variant (resellers checked on 2026-10-16 list only the original Maker Reflect). The datasheet is three short sections (board functions, a 5-row features table, a dimension drawing); figures are not readable as text. **Neither this datasheet nor the MAKER-REFLECT datasheet mentions the Ikedo Mini Sumo kit.**

## What it is
A tiny infrared reflectance sensor, the newer "S" variant of the Maker Reflect, with the same 3-pin VCC/GND/OUT connector [DS]. Its datasheet keeps the title "Analog Reflectance Sensor (Line Detector)" and the connector description "OUT : Analog output. Higher voltage = darker surface", but its features table says "Digital IO Compatible" and "No ADC required", with a 5 VDC operating voltage, 25 mA supply current and an optimal sensing distance of 3 mm (0.125") [DS]. The product page says "The new Maker Reflect S comes with a smaller threshold sensing for more stable output" [PP].
Positioning (marketing, not spec): sold under "Maker Reflect: Simplifying IR Reflectance Sensor for Beginner" as the "new" option [PP].

## Specifications
Datasheet Table 2 is titled **"MAKER-REFLECT-S features"** (a features list, not a min/max ratings table) [DS].

| Item | Value | Src |
|---|---|---|
| Operating voltage | 5VDC | [DS] |
| Supply current | 25mA | [DS] |
| Logic compatibility | "Digital IO Compatible" | [DS] |
| ADC | "No ADC required" | [DS] |
| Optimal sensing distance | 3mm (0.125") | [DS] |
| Sensor type | "IR Reflectance Sensor — Infrared sensors for line detection" | [DS] |
| Output (connector table) | "OUT : Analog output. Higher voltage = darker surface." | [DS] |
| Threshold | Product page: "smaller threshold sensing for more stable output" vs the original Maker Reflect; no numeric threshold stated | [PP] |
| Connector | 3 pins: VCC, GND, OUT | [DS] |
| Reverse polarity | **No protection**: "Warning: Reversed Polarity will damage the sensor" | [DS] |
| Min/max sensing distance | **Not stated** (only the 3 mm optimum) | [DS] |
| Output voltage levels (high/low or range) | **Not stated** | [DS] |
| Supply voltage range (min/max) / 3.3 V operation | **Not stated** — only "5VDC" | [DS] |
| Sensor / IR IC part number | **Not stated** | [DS] |
| Indicator LED | **None listed** in the board-functions table | [DS] |
| Dimensions | **Not stated in text** (Figure 3 drawing only) | [DS] |
| Operating temperature, weight | **Not stated** | [DS] |

## Interfaces, terminals and pin mapping
Connector [DS Table 1] (physical pin order is shown in Figure 1 only, not in text). The connector text is identical to the MAKER-REFLECT datasheet, including the name "Maker Reflect" in the VCC line:

| Pin | Function | Src |
|---|---|---|
| VCC | "Power input for the Maker Reflect." (5VDC per features table) | [DS] |
| GND | Ground | [DS] |
| OUT | "Analog output. Higher voltage = darker surface." (features table: "Digital IO Compatible", "No ADC required") | [DS] |

- No other pin, jumper, trimmer, switch or LED is listed in the datasheet [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Output can be read on a plain digital input.** The datasheet's features say "Digital IO Compatible" and "No ADC required" [DS], so `digitalRead()` is a valid way to read it; the connector text still calls OUT an analog output with higher voltage = darker surface [DS]. Until the design team clarifies (see Conflicts), describe OUT as "an output that reads HIGH on a dark surface and LOW on a light surface, usable on a digital pin or an ADC" and avoid quoting voltage levels.
- **Dark = high.** As on the original, a dark surface (black line, the dark sumo ring surface) gives the high state; a white surface gives the low state [DS]. Sumo "edge detected" logic looks for the **low** state at the white ring edge (derived from [DS]).
- **5 V sensor.** The only stated operating voltage is 5VDC [DS]. Do not state 3.3 V operation (the original Maker Reflect's 3.0–5.5 V range is a different datasheet). On a 3.3 V-logic board, check the OUT high level before wiring it to a GPIO — see Needs verification.
- **Mount close.** Optimal sensing distance is 3 mm (0.125") [DS]; no minimum/maximum range is stated — do not borrow the original's 1–40 mm.
- **No reverse-polarity protection** — reversed VCC/GND damages the sensor [DS].
- **25 mA supply current** [DS] — budget it when powering several sensors from a board's 5 V rail (e.g. Maker Mini Sumo +5V 500 mA total [DS of MAKER-MSUMO]).
- **No on-board adjustment** is listed [DS]: the "smaller threshold" of the S variant [PP] is a design property, not a user setting.
- Do not call it "Maker Reflectance Sensor S" or attach the Ikedo kit to it as a spec — no datasheet states that link.

## Power and electrical limits
- Operating voltage 5VDC [DS]; min/max supply range **not stated**.
- Supply current 25mA [DS].
- Reversed polarity will damage the sensor [DS].
- Output voltage levels, output drive capability: **not stated** [DS].

## Software support
- No Cytron library or GitHub example found. Read OUT as a digital input ("Digital IO Compatible", "No ADC required") or as an analog input ("Analog output") [DS].
- Maker Mini Sumo (`MAKER-MSUMO`): the Cytron Maker Sumo Library reads the edge ports (A0 `EDGE_L`, A1 `EDGE_R`) with `analogRead()` and compares against a threshold [GH via maker-mini-sumo.md]; this works with a sensor whose output sits high on dark and low on white (derived).

## Compatibility and accessories
- Datasheet names no compatible boards [DS]; any 5 V controller with a digital or analog input fits (derived from [DS]).
- **Maker Mini Sumo Controller / Ikedo Mini Sumo Robot V2 kit**: the Ikedo V2 product page lists the kit's 2 edge sensors as "Maker Reflect S" [PP], while the Ikedo V2 Getting Started guide calls them "Maker Reflectance Sensor" and links the older MAKER-REFLECT page . Neither Reflect datasheet mentions Ikedo — unresolved (see Needs verification).
- **SUMO:BIT** edge-sensor ports are specified for "Maker Reflect or any other analog sensors" with a voltage divider [DS of SUMO:BIT]; the S variant is not named there.
- Documents linked from the product page: datasheet only [PP]. No 3D CAD link.

## Common mistakes / troubleshooting
- **Using the original Maker Reflect's specs** (3.0–5.5 V, 1–40 mm) for the S — the S datasheet states only 5VDC, 25 mA and a 3 mm optimum [DS].
- **Sensor dead after wiring** → reversed polarity damages it [DS]; check VCC/GND.
- **No response at a few centimetres** → optimal distance is 3 mm [DS]; mount the sensor close to the surface.
- **Logic inverted** → higher/HIGH = darker surface [DS]; flip the comparison in code.
- **Running from 3.3 V** → not a stated operating voltage [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Output type | [DS] title "Analog Reflectance Sensor"; connector table "OUT : Analog output. Higher voltage = darker surface." | [DS] features table "Digital IO Compatible", "No ADC required" | Both are in the same datasheet. State both wordings; describe OUT as readable on a digital pin or an ADC, dark = high. Ask the design team whether OUT is a thresholded (digital) output |
| Threshold | [PP] "smaller threshold sensing for more stable output" | [DS] no threshold figure or adjustment listed | Use the [PP] sentence only as positioning; no numeric spec |
| Edge sensor in Ikedo V2 kit | [PP] Ikedo V2 page "Maker Reflect S" |  Ikedo V2 guide "Maker Reflectance Sensor", linking the MAKER-REFLECT page | Unresolved; neither datasheet mentions Ikedo |
| Datasheet boilerplate | [DS] VCC line says "Power input for the Maker Reflect." | [DS] title MAKER-REFLECT-S | Copied text; not a data conflict |

## Needs verification
- **Whether OUT is a true digital (thresholded) output or an analog voltage** that happens to be readable on a digital pin — the datasheet says both. Ask the design team.
- **OUT high/low voltage levels** and whether it is safe on a 3.3 V-only GPIO (RP2040, ESP32) — not stated.
- **Supply voltage min/max** (3.3 V operation?) — only "5VDC" stated.
- **Sensing range** (min/max) — only the 3 mm optimum is stated.
- **Dimensions, connector pin order, header type, mounting hole** — Figure 1/3 not readable as text; whether the board is the same size as the original (18.1 × 8.4 × 4.2 mm [3P] for MAKER-REFLECT) is unknown.
- **What physically differs from MAKER-REFLECT** (sensor part, threshold circuit) — the product page sentence is the only statement.
- **Which Reflect variant ships in the Ikedo Mini Sumo Robot V2 kit**.
- Price per option: the product page shows RM8.00–RM9.00 across the two options; which option is RM8.00 and which RM9.00 was not recorded.

## Sources
- [DS] MAKER-REFLECT-S Datasheet, "Analog Reflectance Sensor (Line Detector)", Rev 1.0, February 2026 — https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit (public)
- [PP] Product page https://my.cytron.io/p-maker-reflect-ir-reflectance-sensor-for-beginner, option "Maker Reflect S" (read by the coordinator 2026-10-16: code MAKER-REFLECT-S, RM8.00–RM9.00 depending on option, in stock, warranty 12 months, datasheet link, "The new Maker Reflect S comes with a smaller threshold sensing for more stable output")
- [DS of MAKER-REFLECT] https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit (see `maker-reflect.md`)
- [DS of MAKER-MSUMO] + [GH] Cytron Maker Sumo Library + [PP]/ Ikedo V2 kit statements via KB entry maker-mini-sumo.md · [DS of SUMO:BIT] via KB entry sumo-bit.md
- [3P] none found for this variant (RobotShop, The Pi Hut, Botland and element14 list only the original Maker Reflect as of 2026-10-16)
