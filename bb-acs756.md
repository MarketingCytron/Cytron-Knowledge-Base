# 50A Current Sensor — Verified Reference

| | |
|---|---|
| Product code | `BB-ACS756` [PP]; the Cytron GitHub repo is `Cytron_BB-ACS756` and its README links the old page `cytron.com.my/p-bb-acs756` [GH] |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | **No Cytron datasheet or user manual exists.** Main source: Cytron product page https://my.cytron.io/p-50a-current-sensor (read by the coordinator 2026-10-19) [PP]. Board wiring from the Cytron schematic **`usr_attachment-BB-ACS756_Schematic.pdf`** (1 page, no revision or date printed) in the Cytron GitHub repo [DS-schematic]. Chip facts from **Allegro ACS756 datasheet, ACS756-DS Rev. 6, March 25, 2011** (`usr_attachment-ACS756_Datasheet.pdf`, same repo) [VEN] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = coordinator's browser read of the product page, 2026-10-19 (my.cytron.io was not fetched here). [DS-schematic] = the Cytron schematic PDF, rendered and read as an image here. [GH] = README of https://github.com/CytronTechnologies/Cytron_BB-ACS756 (one line only). [VEN] = Allegro chip datasheet — used only for chip-level facts, never for board facts.

## What it is
- A breakout board for the Allegro ACS756 Hall-effect linear current sensor, for AC or DC current sensing [PP].
- Typical applications listed on the page: motor control, load detection, power supplies, over-current fault protection [PP].
- The chip fitted is the X050 (50 A) version, model **ACS756KCA-050B-PFF-T** [PP].
- Comes with one set of Dean-T connector and a 3-way right-angle pin header; **"The connector is not soldered when purchased"** [PP].

## Specifications
No Cytron spec table exists; rows below are the product page "Features" list plus chip rows marked [VEN].

| Item | Value | Src |
|---|---|---|
| Sensor IC | Allegro ACS756, X050 (50 Amp) version, ACS756KCA-050B-PFF-T | [PP] |
| Current type | AC or DC; output voltage proportional to AC or DC current | [PP] |
| Primary sampled current (X050) | −50 A to +50 A (bidirectional) | [VEN] |
| Supply | 5.0 V single supply | [PP] |
| Chip supply range | 3 V min, 5.0 V typ, 5.5 V max; factory-trimmed at 5 V | [VEN] |
| Sensitivity | 40 mV/A | [PP]; [VEN] typ at TA = 25 °C |
| Sensitivity over temperature (Range K) | 37.2–42.8 mV/A | [VEN] |
| Output at 0 A | VCC/2 (bidirectional 0 A output); 2.5 V at VCC = 5 V | [VEN] |
| Total output error | 0.8% at TA = 25 °C | [PP]; [VEN] |
| Total output error over temperature (X050, Range K) | ±7.5% (−40 °C to 125 °C) | [VEN] |
| Internal conductor resistance | 130 µΩ | [PP]; [VEN] typ |
| Isolation | 3 kV RMS minimum, pins 1–3 to pins 4–5 | [PP] |
| Output rise time | 3 µs | [PP] |
| Offset / hysteresis | Factory-trimmed; stable offset; nearly zero magnetic hysteresis | [PP] |
| Chip supply current | 10 mA typ, 14 mA max (VCC = 5.0 V, output open) | [VEN] |
| Noise (X050) | 10 mV typ (TA = 25 °C, 10 nF on VIOUT) | [VEN] |
| Operating temperature (K grade) | −40 °C to 125 °C | [VEN] |
| On-board capacitors | C1 0.1 µF (VIOUT–GND), C2 0.1 µF (VCC–GND) | [DS-schematic] |
| Dimension | 1.43 x 1.435 inch | [PP] |
| Included | 1 set Dean-T connector, 1× 3-way right-angle pin header (unsoldered) | [PP] |
| Price | RM52.50 (10+ RM47.25, 30+ RM42.00) (Cytron product page, read 2026-10-19) | [PP] |
| Warranty | 12 months | [PP] |

## Interfaces, terminals and pin mapping
From the Cytron schematic [DS-schematic]:

| Connector | Pin | Connects to |
|---|---|---|
| JP1 "IN" (2-pin) | 1 (+) | ACS756 pin 4 IP+ |
| JP1 "IN" | 2 (−) | straight through to JP2 pin 2 (−) |
| JP2 "OUT" (2-pin) | 1 (+) | ACS756 pin 5 IP− |
| JP2 "OUT" | 2 (−) | straight through to JP1 pin 2 (−) |
| JP3 (3-pin) | 1 | VCC (ACS756 pin 1) |
| JP3 | 2 | GND (ACS756 pin 2) |
| JP3 | 3 | VIOUT, analog output (ACS756 pin 3) |

- Only the **positive** line passes through the sensor; the negative line goes straight from IN to OUT [DS-schematic].
- The schematic does not name the connector type for JP1/JP2; the product page says the board comes with a Dean-T connector set and a 3-way right-angle header [PP]. That JP1/JP2 are the Dean-T positions and JP3 the 3-way header is inferred — see Needs verification.
- Chip: current flowing from IP+ (pin 4) to IP− (pin 5) drives the output above VCC/2 [VEN]. With the schematic wiring, current entering at IN+ and leaving at OUT+ therefore raises the output (derived from [DS-schematic] + [VEN]).

## Rules and gotchas (for code, wiring and tutorials)
- **Connectors come unsoldered** — the Dean-T connector and 3-way header must be soldered by the user [PP].
- **Output is analog**, centred at VCC/2 at 0 A (2.5 V at 5 V); current = (VOUT − VCC/2) / 0.040 V/A at 40 mV/A [VEN; formula derived from the stated sensitivity and 0 A output].
- **Output is ratiometric** to VCC: both the 0 A level and the sensitivity scale with supply [VEN]. Measure or use the actual supply when converting.
- **Supply 5.0 V** per the product page [PP]. Allegro allows 3 V min but the part is trimmed at 5 V and Allegro says 3.3 V users should contact Allegro about accuracy [VEN] — do not present 3.3 V operation as a Cytron spec.
- **3.3 V boards:** at VCC = 5 V the output can swing above 3.3 V at the top of the range (not stated by any Cytron source — check ADC input limits before wiring to a 3.3 V MCU).
- Polarity: put the load current through IN(+) → OUT(+); reversing it makes the reading go below VCC/2 (bidirectional sensing) [VEN + DS-schematic, derived].

## Power and electrical limits
- Logic supply: 5.0 V single supply [PP]; chip absolute max VCC 8 V, reverse −0.5 V [VEN].
- Sensed current: ±50 A primary sampled current for the X050 [VEN]; the page names it a "50A Current Sensor" [PP]. Allegro states the conductor survives up to 5× overcurrent [VEN] — not a Cytron board rating.
- Chip output: source 3 mA max, sink 1 mA max; minimum load 4.7 kΩ; maximum output load capacitance 10 nF [VEN].
- Isolation 3 kV RMS min between signal pins and current path [PP]. Board-level creepage/isolation rating of the PCB is not stated by Cytron.
- Wire/connector current rating of the Dean-T connector and PCB traces: not stated.

## Software support
- No Cytron library or sample code is linked [PP][GH]. Any ADC-capable pin reads VIOUT.
- Fritzing part is linked from the product page [PP].

## Compatibility and accessories
- Any microcontroller with an analog input (derived — the output is a single analog voltage).
- Dean-T connector set and 3-way right-angle header included [PP].

## Common mistakes / troubleshooting
- Reading ≈ VCC/2 with no current is normal (0 A level), not an offset fault [VEN].
- Reading goes the "wrong way": current is flowing OUT→IN; swap the leads or flip the sign in code [VEN + DS-schematic, derived].
- Values drift with supply: output is ratiometric; a sagging 5 V rail changes both offset and gain [VEN].
- Board does nothing: connectors were not soldered (shipped loose) [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply voltage | [PP] "5.0 V single supply" | [VEN] front page "3.0 to 5.0 V single supply operation"; table 3–5.5 V | Use 5.0 V (Cytron page). Chip range is chip-level only |
| Output load capacitance | [DS-schematic] C1 0.1 µF from VIOUT to GND | [VEN] CLOAD(MAX) 10 nF (VIOUT to GND) | Not resolved — confirm C1 value/placement with Cytron design team |
| Sensitivity | [PP] 40 mV/A | [VEN] 40 mV/A typ at 25 °C; 37.2–42.8 mV/A over K range | Agree; say "40 mV/A (typical)" |

## Needs verification
- Which footprint takes the Dean-T connector and which the 3-way header (schematic shows JP1 IN, JP2 OUT 2-pin; JP3 3-pin) — inferred, not stated.
- PCB silkscreen labels for JP3 pins (VCC / GND / OUT names on the board).
- C1 0.1 µF on VIOUT vs Allegro's 10 nF max output load capacitance.
- Whether "one set of Dean-T connector" means one male+female pair or two connectors (one per side).
- Board hole/mounting dimensions, weight, PCB revision.
- Maximum continuous current the board/connector can carry (only the chip's ±50 A sensing range is stated).
- "3.3 V operation" accuracy — Allegro defers to its sales team.

## Sources
- [PP] https://my.cytron.io/p-50a-current-sensor (coordinator read, 2026-10-19; notes in local file m-pp.md)
- [GH] https://github.com/CytronTechnologies/Cytron_BB-ACS756 — README.md: "Datasheet and schematic for 50A current sensor"
- [DS-schematic] https://raw.githubusercontent.com/CytronTechnologies/Cytron_BB-ACS756/master/usr_attachment-BB-ACS756_Schematic.pdf
- [VEN] Allegro ACS756 datasheet, ACS756-DS Rev. 6 (March 25, 2011): https://raw.githubusercontent.com/CytronTechnologies/Cytron_BB-ACS756/master/usr_attachment-ACS756_Datasheet.pdf
