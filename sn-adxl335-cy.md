# 3-Axis Accelerometer — Verified Reference

| | |
|---|---|
| Product code | `SN-ADXL335-CY` [PP] (schematic file name `SN-ADXL335-CY-Sch.pdf` [PP link]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: Cytron schematic SN-ADXL335-CY-Sch.pdf (Rev 1, 4/9/2013) read through the Drive viewer, plus the product photo. Board pinout confirmed (3V3, 5V, GND, X, Y, Z, ST), regulator = MCP1825S-3302E/DB on the 5V pin, 3V3 pin feeds the chip rail directly, ST broken out, green power LED. Tagged [DS-schematic] |
| Primary source | **No Cytron datasheet or user manual exists.** Main source: Cytron product page https://my.cytron.io/p-3-axis-accelerometer (read by the coordinator 2026-10-19) [PP]. Chip facts from **Analog Devices ADXL335 datasheet, Rev. B (1/10)**, the copy Cytron links on Google Drive [VEN]. Cytron schematic `SN-ADXL335-CY-Sch.pdf` (Rev 1, dated 4/9/2013) read visually on 2026-10-19 [DS-schematic] (see Needs verification) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = coordinator's browser read, 2026-10-19 (my.cytron.io not fetched here). [VEN] = ADXL335 datasheet read as text from Cytron's Drive copy; chip-level facts only. [DS-schematic] = Cytron schematic "3-Axis Accelerometer, SN-ADXL335-CY, Rev 1" (title-block date 4/9/2013), read through the Google Drive viewer 2026-10-19. [PP: photo] = product photo (pin labels on the silkscreen). [3P] = RobotShop (RB-Cyt-217), cross-check only.

## What it is
- A breakout board for the Analog Devices ADXL335 3-axis MEMS accelerometer, ±3 g [PP].
- On-board 3.3 V regulator, so the board runs from 2.5 V to 6 V [PP].
- Fully assembled and tested; the included 0.1 µF capacitors set each axis bandwidth to 50 Hz [PP].
- Outputs are analog voltages proportional to acceleration, one per axis [VEN].
- **Out of stock** on my.cytron.io at 2026-10-19 [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensor IC | Analog Devices ADXL335 | [PP] |
| Axes | 3 | [PP] |
| Range | ±3g | [PP]; [VEN] ±3 g min, ±3.6 g typ |
| Regulator | On-board 3.3V regulator | [PP] |
| Operating voltage | 2.5V–6.0V | [PP] |
| Typical current | 300 µA (features); "only 320uA" (description) | [PP] — see Conflicts |
| Bandwidth | Adjustable with one capacitor per axis; included 0.1 µF capacitors set 50 Hz per axis | [PP] |
| Dimension | 19.5mm x 22mm | [PP] |
| Regulator | Microchip **MCP1825S-3302E/DB** (3.3 V LDO), input from the **5V** pin; 22 µF 10 V input cap, 0.1 µF output cap | [DS-schematic] |
| Chip supply filter | +3V3 → 100 Ω (R2) → ADXL335 VS, with 22 µF + 0.1 µF to GND | [DS-schematic] |
| Axis filter caps | 0.1 µF on each of XOUT, YOUT, ZOUT (C3–C5) | [DS-schematic] |
| Power LED | Green LED with 330 Ω from +3V3 | [DS-schematic] |
| Header | 7-way JP1: 3V3, 5V, GND, XOUT, YOUT, ZOUT, ST (silkscreen: 3V3, 5V, GND, X, Y, Z, ST) | [DS-schematic][PP: photo] |
| Chip supply range | 1.8 V to 3.6 V | [VEN] |
| Chip supply current | 350 µA typ at VS = 3 V | [VEN] |
| Sensitivity | 300 mV/g typ (270–330) at VS = 3 V; ratiometric to VS | [VEN] |
| 0 g output | 1.5 V typ at VS = 3 V; nominally VS/2 at all supply voltages | [VEN] |
| Bandwidth formula | F−3dB = 1/(2π × 32 kΩ × C); 0.10 µF → 50 Hz (Table 4) | [VEN] |
| Max bandwidth (no filter) | X, Y 1600 Hz; Z 550 Hz | [VEN] |
| Noise density | X, Y 150 µg/√Hz rms; Z 300 µg/√Hz rms | [VEN] |
| Operating temperature | −40 °C to +85 °C | [VEN] |
| Shock survival | 10,000 g | [VEN] |
| Price | RM38.85 (10+ RM35.70, 30+ RM31.08) (Cytron product page, read 2026-10-19) | [PP] |
| Warranty | 12 months | [PP] |

## Interfaces, terminals and pin mapping
| JP1 pin | Silkscreen | Net / function | Src |
|---|---|---|---|
| 1 | 3V3 | +3V3 rail — regulator output; also a direct 3.3 V supply input (bypasses the regulator) | [DS-schematic][PP: photo] |
| 2 | 5V | Regulator (MCP1825S-3302) input | [DS-schematic][PP: photo] |
| 3 | GND | Ground | [DS-schematic][PP: photo] |
| 4 | X | XOUT (analog) | [DS-schematic][PP: photo] |
| 5 | Y | YOUT (analog) | [DS-schematic][PP: photo] |
| 6 | Z | ZOUT (analog) | [DS-schematic][PP: photo] |
| 7 | ST | ADXL335 self-test input | [DS-schematic][PP: photo] |
- Axis arrows for X and Y and a Z (out of board) mark are printed on the board [PP: photo].
- Chip pins [VEN]: XOUT (12), YOUT (10), ZOUT (8), ST self-test (2), VS (14, 15), COM (3, 5, 6, 7). ST is broken out to header pin 7 [DS-schematic].
- Outputs are analog: one ADC channel per axis is needed (derived from [VEN] analog outputs).

## Rules and gotchas (for code, wiring and tutorials)
- **Two ways to power it** [DS-schematic]: (a) up to 6.0 V on the **5V** pin, through the MCP1825S 3.3 V regulator [PP: 2.5–6.0 V]; or (b) a regulated 3.3 V on the **3V3** pin, which feeds the chip rail directly — never put more than 3.6 V on 3V3 (chip absolute maximum) [VEN]. Never feed both.
- The page's 2.5 V lower limit applies to the 5V pin, but below about 3.3 V plus dropout the regulator output (and so VS) falls — outputs stay ratiometric, but scale and 0 g shift [VEN].
- **Outputs are ratiometric to the chip supply (VS)**: 0 g ≈ VS/2 and sensitivity scales with VS [VEN]. On this board VS = the +3V3 rail through a 100 Ω filter resistor [DS-schematic], so 0 g ≈ 1.65 V and sensitivity ≈ 330 mV/g nominal when the rail is 3.3 V (derived from [VEN] ratiometric behaviour; calibrate).
- **Bandwidth is 50 Hz per axis** with the fitted 0.1 µF capacitors [PP] (agrees with [VEN] Table 4).
- **Calibrate** zero-g and 1 g per axis in code; [VEN] gives only typical 0 g and sensitivity with tolerances (270–330 mV/g; 0 g 1.35–1.65 V X/Y, 1.2–1.8 V Z at 3 V).
- **Self-test:** ST is on header pin 7 [DS-schematic]. ST to VS shifts outputs (−325 mV X, +325 mV Y, +550 mV Z at 3 V); ST can be left open or tied to COM; never drive ST above VS + 0.3 V [VEN].
- Out of stock — check availability before writing new content around it [PP].

## Power and electrical limits
- Board input: 2.5V–6.0V; typical current 300 µA / 320 µA (page states both) [PP].
- Chip absolute maximum VS −0.3 V to +3.6 V [VEN] (protected by the board regulator per [PP] 2.5–6 V rating).
- Regulator: MCP1825S-3302E/DB on the 5V pin [DS-schematic]; no reverse-polarity protection is shown in the schematic [DS-schematic].
- The 3V3 pin bypasses the regulator: 3.3 V regulated supply only [DS-schematic][VEN].

## Software support
- No Cytron library or sample code is linked [PP]. Tutorials linked: "Accelerometer ADXL335 Fast Test and Angle Test" (now returns 404) and "Measuring Tilt Angle with Gyro and Accelerometer" [PP] — content not read here.

## Compatibility and accessories
- Any microcontroller with three analog inputs (derived from analog outputs [VEN]).
- Documents linked from the page: ADXL335 datasheet (Drive), SN-ADXL335-CY schematic (Drive, read) [PP]. The resources list mislabels the datasheet "ADXL355 Datasheet" [PP].

## Common mistakes / troubleshooting
- Wrong part: ADXL335 (analog, this board) vs ADXL355/ADXL345 (different parts) — the page's own resource list says "ADXL355" by mistake [PP].
- Readings noisy or slow: bandwidth fixed at 50 Hz by the fitted 0.1 µF capacitors [PP]; changing it means changing those capacitors [VEN formula].
- Z axis reads about 1 g when flat — that is gravity, not an offset fault [VEN Figure 24].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply current | [PP] features "typical current 300 µA" | [PP] description "only 320uA"; [VEN] 350 µA typ at VS = 3 V | Page is inconsistent; quote [PP] 300 µA typical and flag; chip figure is [VEN] only |
| Supply voltage | [PP] board 2.5V–6.0V (on-board 3.3V regulator) | [VEN] chip 1.8–3.6 V; [DS-schematic] the 3V3 pin bypasses the regulator | 2.5–6.0 V applies to the **5V pin** only; the 3V3 pin takes 3.3 V regulated |
| Datasheet label | [PP] resource list "ADXL355 Datasheet" | File is "ADXL335 Datasheet.pdf" (Analog Devices ADXL335 Rev. B) | Typo on page; part is ADXL335 |

## Needs verification
- Regulator dropout at low input (MCP1825S figures are Microchip's, not stated by Cytron) — affects the page's 2.5 V lower limit.
- Header pin numbering direction on the PCB (schematic JP1 order matches the silkscreen order; confirm pin 1 marking on the board).
- Tutorial content ("Measuring Tilt Angle with Gyro and Accelerometer") — not read; "Accelerometer ADXL335 Fast Test and Angle Test" returns 404.
- Weight; mounting-hole size (two holes visible in the photo); header supplied or soldered.
- [3P] RobotShop (RB-Cyt-217) repeats the page facts and lists it out of stock.

## Sources
- [PP] https://my.cytron.io/p-3-axis-accelerometer (coordinator read, 2026-10-19; notes in local file m-pp.md)
- [VEN] Analog Devices ADXL335 datasheet Rev. B (Cytron Drive copy): https://drive.google.com/file/d/0BzFWfMiqqjyqVFRHTEJKQXotVXM/view
- [DS-schematic] SN-ADXL335-CY schematic, Rev 1, 4/9/2013 (read through the Drive viewer 2026-10-19): https://drive.google.com/file/d/0BzFWfMiqqjyqa3V4U1lUWXFIcDA/view
- [3P] https://uk.robotshop.com/products/cytron-adxl335-3-axis-accelerometer
