# 50A Current Sensor — Verified Reference

| | |
|---|---|
| Product code | `BB-ACS756` [PP]; the Cytron GitHub repo is `Cytron_BB-ACS756` and its README links the old page `cytron.com.my/p-bb-acs756` [GH]; the sample-code repo `SK28A_CurrentSensorACS756` links the same old page as "50A Current sensor" [GH] |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron GitHub `SK28A_CurrentSensorACS756` (passed on as "Schematic & Sensing Circuit") read in full: README, `BBACS756/bbacs756.c` + `lcd.c`/`lcd.h`, `CurrentSense.X/CurretSense.c`, project files, full history (4 Sep – 2 Oct 2015, HEAD 16931d7, branch `master` only). It settled that Cytron sample code exists (PIC18F2550 on SK28A, sensor output on RA0/AN0, ADC referenced to VDD) and gave the conversion constants: 40 mV/A, Vref 5.04 V, zero point fixed at 510 counts or calibrated at start-up, and a rounded ×125 (0.01 A units) factor in the older example. **The repo holds no schematic or circuit file in any commit.** Stays Medium; still open: C1 0.1 µF vs 10 nF output load, connector footprints, board current rating, the old tutorials' wiring (not read). Earlier: 2026-10-19 master-table review of the live product page — no new facts, C1 question open |
| Primary source | **No Cytron datasheet or user manual exists.** Main source: Cytron product page https://my.cytron.io/p-50a-current-sensor (read by the coordinator 2026-10-19) [PP]. Board wiring from the Cytron schematic **`usr_attachment-BB-ACS756_Schematic.pdf`** (1 page, no revision or date printed) in the Cytron GitHub repo [DS-schematic]. Chip facts from **Allegro ACS756 datasheet, ACS756-DS Rev. 6, March 25, 2011** (`usr_attachment-ACS756_Datasheet.pdf`, same repo) [VEN] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = coordinator's browser read of the product page, 2026-10-19 (my.cytron.io was not fetched here). [DS-schematic] = the Cytron schematic PDF, rendered and read as an image here. [GH] = README of https://github.com/CytronTechnologies/Cytron_BB-ACS756 (one line only). [VEN] = Allegro chip datasheet — used only for chip-level facts, never for board facts. [GH SK28A] = https://github.com/CytronTechnologies/SK28A_CurrentSensorACS756 — sample C code for PIC18F2550 on the SK28A start-up kit, passed on by the marketing team as "Schematic & Sensing Circuit" but holding **no schematic or circuit drawing** (code, MPLAB project files and build output only; full history checked 2026-10-21). Its two tutorials on the old tutorial.cytron.com.my site were not read.

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
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read: ACS756KCA-050B-PFF-T (±50 A); total output error 0.8% at 25 °C; 130 µΩ conductor; 3 kV RMS isolation; 5.0 V single supply; 3 µs rise time; 40 mV/A; AC or DC; dimension 1.43 × 1.435 inch; one set of Dean-T connector and a 3-way right-angle header, not soldered; resources: Allegro datasheet (GitHub), schematic (GitHub), Fritzing file [PP]. Matches the KB.

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
- **Calibrate the zero point** rather than assuming exactly VCC/2: Cytron's AmpMeter code averages 256 samples at start-up with no current and stores that as the centre; the older example hard-codes 510 counts (≈ 2.49 V at a 5 V reference, derived) [GH SK28A].
- **Use the real ADC reference in the formula:** Cytron's code uses 5.04 V and 40 mV/A, i.e. one 10-bit count ≈ 0.123 A, so a 10-bit ADC resolves only about 0.12 A per step on this ±50 A sensor (derived) [GH SK28A].
- Do not copy the header comments of `bbacs756.c` ("RFID Sample code", "written for PIC16F877A") — the file is for PIC18F2550 [GH SK28A].

## Power and electrical limits
- Logic supply: 5.0 V single supply [PP]; chip absolute max VCC 8 V, reverse −0.5 V [VEN].
- Sensed current: ±50 A primary sampled current for the X050 [VEN]; the page names it a "50A Current Sensor" [PP]. Allegro states the conductor survives up to 5× overcurrent [VEN] — not a Cytron board rating.
- Chip output: source 3 mA max, sink 1 mA max; minimum load 4.7 kΩ; maximum output load capacitance 10 nF [VEN].
- Isolation 3 kV RMS min between signal pins and current path [PP]. Board-level creepage/isolation rating of the PCB is not stated by Cytron.
- Wire/connector current rating of the Dean-T connector and PCB traces: not stated.

## Software support
- **Cytron sample code (PIC, not Arduino)** — GitHub `SK28A_CurrentSensorACS756`, commits 4 Sep 2015 – 2 Oct 2015 [GH SK28A]. Target **PIC18F2550** on Cytron **SK28A** (device set in both project files). Two examples:
  - `BBACS756/` — for the tutorial "Current measuring using BB-ACS756 with SK28A" (tutorial.cytron.com.my, URL dated 2012/08/08); MPLAB IDE + MPLAB C18 v3.37.01.
  - `CurrentSense/CurrentSense.X/` — for the tutorial "AmpMeter using SK28A and 7-Segment Display" (URL dated 2014/08/24); MPLAB X + XC8.
- **Sensor input:** VIOUT read on **RA0 / AN0** (only analog pin enabled), 10-bit ADC, right-justified, reference **VDD/VSS** (VCFG = 00) — so the reading is ratiometric with the PIC supply, matching the sensor's ratiometric output [GH SK28A; ratiometric match is inferred].
- **BBACS756 conversion:** zero-current point hard-coded at **510 counts**; current = |count − 510| × 125, shown on a character LCD as "XX.XXA" (units of 0.01 A, sign dropped) [GH SK28A]. The factor 125 is a rounding of (5 V / 1023) / 0.040 V/A ≈ 122 per count in 0.01 A — about 2.3 % high (derived).
- **CurrentSense (AmpMeter) conversion:** constants `Vref 5.04` (V) and **0.04 V/A**; current (A) = |avg − centre| × (5.04 / 1023) / 0.04, each reading the average of 256 ADC samples [GH SK28A].
  - **Zero calibration at start-up:** with no load current, the code shows "Ctr=" and the averaged count on the LCD; pressing **SW1 (RB0)** stores it as the centre value [GH SK28A].
  - Modes: SW1 toggles Real-time / Maximum (LED on **RB1** lit in Maximum mode); whole amps shown on a 3-digit 7-segment display via BCD lines RA4, RA1, RA2, RA3 and digit latches RC0, RC1, RC2; scrolling mode text on the LCD [GH SK28A].
  - Clock: 20 MHz crystal, PLL to 48 MHz CPU (`_XTAL_FREQ 48000000`) [GH SK28A].
- **LCD wiring in both examples (SK28A):** RS = RB2, E = RB3, DB4–DB7 = RB4–RB7, 4-bit mode [GH SK28A].
- Neither example shows current direction (both take the absolute difference from the zero point) [GH SK28A].
- No Arduino library or Arduino sample is published [PP][GH]. Any ADC-capable pin reads VIOUT.
- Fritzing part is linked from the product page [PP].

## Compatibility and accessories
- Any microcontroller with an analog input (derived — the output is a single analog voltage).
- Dean-T connector set and 3-way right-angle header included [PP].

## Common mistakes / troubleshooting
- Reading ≈ VCC/2 with no current is normal (0 A level), not an offset fault [VEN].
- Reading goes the "wrong way": current is flowing OUT→IN; swap the leads or flip the sign in code [VEN + DS-schematic, derived].
- Values drift with supply: output is ratiometric; a sagging 5 V rail changes both offset and gain [VEN].
- Non-zero reading with no load: re-take the zero point (Cytron AmpMeter code averages 256 samples at start-up and stores them on an SW1 press) [GH SK28A].
- Reading never shows negative current with Cytron's PIC samples: by design, both take the absolute difference from the zero point [GH SK28A].
- Board does nothing: connectors were not soldered (shipped loose) [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply voltage | [PP] "5.0 V single supply" | [VEN] front page "3.0 to 5.0 V single supply operation"; table 3–5.5 V | Use 5.0 V (Cytron page). Chip range is chip-level only |
| Output load capacitance | [DS-schematic] C1 0.1 µF from VIOUT to GND | [VEN] CLOAD(MAX) 10 nF (VIOUT to GND) | Not resolved — confirm C1 value/placement with Cytron design team |
| Sensitivity | [PP] 40 mV/A | [VEN] 40 mV/A typ at 25 °C; 37.2–42.8 mV/A over K range | Agree; say "40 mV/A (typical)" |
| Conversion factor in sample code | [PP] 40 mV/A → (5 V / 1023) / 0.040 ≈ 0.122 A per 10-bit count (derived); [GH SK28A] AmpMeter code: Vref 5.04 V, 0.04 V/A | [GH SK28A] `bbacs756.c`: |count − 510| × 125 in 0.01 A, i.e. 0.125 A per count (≈ 39 mV/A at 5 V) | Sample rounding; use 40 mV/A with the measured reference voltage |
| Zero-current level | [VEN] VCC/2 (511.5 counts at 10 bit, derived) | [GH SK28A] `bbacs756.c` hard-codes 510 counts; AmpMeter code measures it at start-up | Calibrate at start-up as the newer Cytron code does |
| Target MCU of `bbacs756.c` | [GH SK28A] file comment: "written for PIC16F877A"; title "RFID Sample code" | [GH SK28A] same file `#include <P18F2550.h>`; project device PIC18F2550 | Copy-over comment; the code is for PIC18F2550 |
| "Schematic & Sensing Circuit" label | Marketing hand-off labelled the SK28A repo as schematic and sensing circuit | [GH SK28A] repo content: C code, MPLAB project and build files only (full history checked 2026-10-21) | The board schematic remains the PDF in `Cytron_BB-ACS756`; no sensing-circuit drawing exists in the SK28A repo |

## Needs verification
- Which footprint takes the Dean-T connector and which the 3-way header (schematic shows JP1 IN, JP2 OUT 2-pin; JP3 3-pin) — inferred, not stated.
- PCB silkscreen labels for JP3 pins (VCC / GND / OUT names on the board).
- C1 0.1 µF on VIOUT vs Allegro's 10 nF max output load capacitance.
- Whether "one set of Dean-T connector" means one male+female pair or two connectors (one per side).
- Board hole/mounting dimensions, weight, PCB revision.
- Maximum continuous current the board/connector can carry (only the chip's ±50 A sensing range is stated).
- "3.3 V operation" accuracy — Allegro defers to its sales team.
- Sensor-to-SK28A wiring for the PIC examples: only VIOUT → RA0/AN0 can be inferred from the code; power and ground wiring are in the old tutorials on tutorial.cytron.com.my (not read). No schematic exists in the SK28A repo (GitHub API listing could not be queried from this session; `git ls-remote` shows only `master`).
- Whether Cytron has an Arduino example for BB-ACS756 (none found on GitHub).

## Sources
- [PP] https://my.cytron.io/p-50a-current-sensor (coordinator read, 2026-10-19; notes in local file m-pp.md)
- [GH] https://github.com/CytronTechnologies/Cytron_BB-ACS756 — README.md: "Datasheet and schematic for 50A current sensor"
- [DS-schematic] https://raw.githubusercontent.com/CytronTechnologies/Cytron_BB-ACS756/master/usr_attachment-BB-ACS756_Schematic.pdf
- [VEN] Allegro ACS756 datasheet, ACS756-DS Rev. 6 (March 25, 2011): https://raw.githubusercontent.com/CytronTechnologies/Cytron_BB-ACS756/master/usr_attachment-ACS756_Datasheet.pdf
- [GH SK28A] SK28A_CurrentSensorACS756 — https://github.com/CytronTechnologies/SK28A_CurrentSensorACS756 (handed over as "Schematic & Sensing Circuit"; README.md, BBACS756/bbacs756.c, lcd.c, lcd.h, CurrentSense/CurrentSense.X/CurretSense.c and project files; commits 4 Sep 2015 – 2 Oct 2015, HEAD 16931d7 "Update README.md", branch `master`; read in full with full history 2026-10-21; no schematic). Tutorials it links (not read): http://tutorial.cytron.com.my/2012/08/08/current-measuring-using-bb-acs756-with-sk28a/ · http://tutorial.cytron.com.my/2014/08/24/ampmeter-using-sk28a-and-7-segment-display/
