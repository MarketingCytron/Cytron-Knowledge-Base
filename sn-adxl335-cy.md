# 3-Axis Accelerometer — Verified Reference

| | |
|---|---|
| Product code | `SN-ADXL335-CY` [PP] (schematic file name `SN-ADXL335-CY-Sch.pdf` [PP link]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | **No Cytron datasheet or user manual exists.** Main source: Cytron product page https://my.cytron.io/p-3-axis-accelerometer (read by the coordinator 2026-10-19) [PP]. Chip facts from **Analog Devices ADXL335 datasheet, Rev. B (1/10)**, the copy Cytron links on Google Drive [VEN]. The Cytron schematic `SN-ADXL335-CY-Sch.pdf` could not be read (see Needs verification) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = coordinator's browser read, 2026-10-19 (my.cytron.io not fetched here). [VEN] = ADXL335 datasheet read as text from Cytron's Drive copy; chip-level facts only. The schematic PDF (Drive, 2017) has no text layer and could not be downloaded for rendering here, so **no board pinout is confirmed**. [3P] = RobotShop (RB-Cyt-217), cross-check only.

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
- **Board pin labels and order: not confirmed** — not in the product page text and the schematic could not be read.
- Chip pins [VEN]: XOUT (12), YOUT (10), ZOUT (8), ST self-test (2), VS (14, 15), COM (3, 5, 6, 7). Whether ST is broken out on the board is not stated.
- Outputs are analog: one ADC channel per axis is needed (derived from [VEN] analog outputs).

## Rules and gotchas (for code, wiring and tutorials)
- **Supply the board 2.5 V–6.0 V** [PP]; the chip itself runs at 1.8–3.6 V behind the on-board 3.3 V regulator [PP][VEN]. Do not quote the chip's 3.6 V limit as the board limit.
- **Outputs are ratiometric to the chip supply (VS)**: 0 g ≈ VS/2 and sensitivity scales with VS [VEN]. The board's chip supply is the regulator output, not the board input — the resulting 0 g voltage on this board is not stated by Cytron (see Needs verification).
- **Bandwidth is 50 Hz per axis** with the fitted 0.1 µF capacitors [PP] (agrees with [VEN] Table 4).
- **Calibrate** zero-g and 1 g per axis in code; [VEN] gives only typical 0 g and sensitivity with tolerances (270–330 mV/g; 0 g 1.35–1.65 V X/Y, 1.2–1.8 V Z at 3 V).
- **Self-test (chip):** ST to VS shifts outputs (−325 mV X, +325 mV Y, +550 mV Z at 3 V); ST can be left open or tied to COM; never drive ST above VS + 0.3 V [VEN].
- Out of stock — check availability before writing new content around it [PP].

## Power and electrical limits
- Board input: 2.5V–6.0V; typical current 300 µA / 320 µA (page states both) [PP].
- Chip absolute maximum VS −0.3 V to +3.6 V [VEN] (protected by the board regulator per [PP] 2.5–6 V rating).
- Regulator part number, dropout and reverse-polarity protection: not stated.

## Software support
- No Cytron library or sample code is linked [PP]. Tutorials linked: "Accelerometer ADXL335 Fast Test and Angle Test" (now returns 404) and "Measuring Tilt Angle with Gyro and Accelerometer" [PP] — content not read here.

## Compatibility and accessories
- Any microcontroller with three analog inputs (derived from analog outputs [VEN]).
- Documents linked from the page: ADXL335 datasheet (Drive), SN-ADXL335-CY schematic (Drive) [PP]. The resources list mislabels the datasheet "ADXL355 Datasheet" [PP].

## Common mistakes / troubleshooting
- Wrong part: ADXL335 (analog, this board) vs ADXL355/ADXL345 (different parts) — the page's own resource list says "ADXL355" by mistake [PP].
- Readings noisy or slow: bandwidth fixed at 50 Hz by the fitted 0.1 µF capacitors [PP]; changing it means changing those capacitors [VEN formula].
- Z axis reads about 1 g when flat — that is gravity, not an offset fault [VEN Figure 24].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply current | [PP] features "typical current 300 µA" | [PP] description "only 320uA"; [VEN] 350 µA typ at VS = 3 V | Page is inconsistent; quote [PP] 300 µA typical and flag; chip figure is [VEN] only |
| Supply voltage | [PP] board 2.5V–6.0V (on-board 3.3V regulator) | [VEN] chip 1.8–3.6 V | Different levels (board vs chip); use 2.5–6.0 V for the board |
| Datasheet label | [PP] resource list "ADXL355 Datasheet" | File is "ADXL335 Datasheet.pdf" (Analog Devices ADXL335 Rev. B) | Typo on page; part is ADXL335 |

## Needs verification
- **Board pinout** (labels and order) — read the schematic `SN-ADXL335-CY-Sch.pdf` (Drive 0BzFWfMiqqjyqa3V4U1lUWXFIcDA); it has no text layer and the file could not be downloaded for rendering here.
- Whether ST (self-test) is broken out to a pin.
- Regulator part number; 0 g output voltage on this board (depends on the regulator output feeding VS).
- Whether the board's 2.5 V lower limit is valid given a 3.3 V regulator (dropout not stated).
- Tutorial content ("Measuring Tilt Angle with Gyro and Accelerometer") — not read.
- Weight; mounting holes; header supplied or soldered.
- [3P] RobotShop (RB-Cyt-217) repeats the page facts and lists it out of stock; it gives no pinout.

## Sources
- [PP] https://my.cytron.io/p-3-axis-accelerometer (coordinator read, 2026-10-19; notes in local file m-pp.md)
- [VEN] Analog Devices ADXL335 datasheet Rev. B (Cytron Drive copy): https://drive.google.com/file/d/0BzFWfMiqqjyqVFRHTEJKQXotVXM/view
- Schematic (not readable here): https://drive.google.com/file/d/0BzFWfMiqqjyqa3V4U1lUWXFIcDA/view
- [3P] https://uk.robotshop.com/products/cytron-adxl335-3-axis-accelerometer
