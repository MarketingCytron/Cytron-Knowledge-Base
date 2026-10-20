# 27W PD 5V 5A USB-C Universal Power Adapter for Raspberry Pi — Verified Reference

| Field | Value |
|---|---|
| Product code | V-AD-27W-PD [PP]; datasheet model name AD-27W-PD-X [DS] |
| Family | Power and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. One plug per option is confirmed by the packing list; the page itself lists both 1.5 m and 1200 mm for the cable |
| Primary source | "AD-27W-PD-X Universal PSU Datasheet" (27W 5V 5A USB-C Universal Power Adapter, Datasheet), Rev 1.0, February 2024, Cytron Technologies Sdn Bhd [DS] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A 27 W AC-to-DC power supply unit with a captive USB Type-C cable and USB Power Delivery, "specifically designed to provide power to the latest Raspberry Pi 5 and other compatible development boards" [DS]. It accepts 100–240 VAC, 50–60 Hz mains "making it suitable for use around the world", supports PD outputs from "5.1V 5A up to 15V 1.8A", and uses interchangeable AC plugs; the housing is black [DS]. The product page sells it for Raspberry Pi 4 Model B and Raspberry Pi 5 with a UK (Type G), EU (Type C) or US (Type A) plug chosen at purchase [PP].

## Specifications
All rows are from the datasheet spec tables unless marked [PP]. Rows the datasheet typesets with Min/Max columns are reproduced as written.

### Output parameters [DS]
| Item | Value | Src |
|---|---|---|
| Typical output voltage | 5.1 VDC | [DS] |
| Rated output voltage, no load | 5V / 9V / 12V / 15V VDC | [DS] |
| Rated output, full load (PD profiles) | 5V 5A; 9V 3A; 12V 2.25A; 15V 1.8A | [DS] |
| PD profiles as listed on product page | 5.1V 5.0A / 9.0V 3.0A / 12.0V 2.25A / 15.0V 1.8A | [PP] |
| Rated power, continuous | 27 W | [DS] |
| Nominal load current | 5 A | [DS] |
| Ripple and noise, at full load | < 200 mV (p-p) | [DS] |
| Protection | Overcurrent Protection; Short Circuit Protection | [DS] |
| Efficiency (average) | 84.25 % (5V); 86.62 % (9V/12V/15V) | [DS] |
| Efficiency | "~82%" | [PP] |
| Electrostatic discharge | Direct discharge ± 4 kV; Air discharge ± 8 kV | [DS] |
| Output cable length | 1200 ± 50 mm | [DS] |
| Output cable length | 1.5 m | [PP] |
| Output cable type | UL 2464, 18AWG | [DS][PP] |
| After-binding length (cable drawing note) | 80 ± 20 mm | [DS] |
| Output cable connector/plug | USB Type-C ("DC Plug: Type-C") | [DS] |
| Cable colour | Black | [DS] |

### Input parameters [DS]
| Item | Value | Src |
|---|---|---|
| Rated input voltage | 100 – 240 VAC | [DS][PP] |
| Rated input frequency | 50 – 60 Hz | [DS][PP] |
| Maximum AC current | < 0.6 A | [DS] |
| Maximum inrush current, cold start | < 80 A | [DS] |
| Standby power, at 115 or 230 VAC | < 0.1 W | [DS] |
| Efficiency, average, at 115 or 230 VAC | 84.25 % (5V); 86.62 % (9V/12V/15V) | [DS] |

### Environment, compliance, commercial
| Item | Value | Src |
|---|---|---|
| Operating temperature range | 0 ~ 40 °C | [DS] |
| Storage temperature range | -25 ~ 70 °C | [DS] |
| Compliance — UKCA | EN 55032:2015/A1:2020; EN 55035:2017/A11:2020; EN IEC 61000-3-2:2019/A1:2021; EN 61000-3-3:2013/A2:2021; BS EN 55032:2015/A1:2020; BS EN 55035:2017/A11:2020; BS EN IEC 61000-3-2:2019/A1:2021; BS EN 61000-3-3:2013/A2:2021 | [DS] |
| Compliance — CE | EN 55032:2015/A1:2020; EN 55035:2017/A11:2020; EN IEC 61000-3-2:2019/A1:2020; EN 61000-3-3:2013/A2:2021; EN IEC 62368-1:2020+A11:2020 | [DS] |
| Certification basis | "All Certifications are based on MPN: HD-PD27W-wwz" | [DS] |
| AC plug options | Interchangeable plugs: EU, UK, US (dimension drawings for each) | [DS] |
| AC plug options | UK (Type G) / EU (Type C) / US (Type A), chosen at purchase; "only one included" | [PP] |
| Plugs included in the box | "includes three interchangeable AC plugs" | [DS] |
| Housing colour | Black ("sleek black color") | [DS] |
| Adapter dimensions / weight | Drawings only in datasheet section 3 (values did not extract as text) | [DS] |
| Price | RM50.00 | [PP] |
| Warranty | 12 months | [PP] |
| Appearance note | "Appearance details are subject to the actual samples." | [DS] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Features list:** 27 W PD; 5.1 V 5 A, 9 V 3 A, 12 V 2.25 A, 15 V 1.8 A; "1.5-meter 18 AWG captive cable" and, in the spec block, "Output cable: 1200±50mm UL2464 18AWG"; short-circuit and over-current protection; 100–240 V AC; ~82 % efficiency; one of three plugs (UK / EU / US) included as selected; UKCA, UL, CE, RoHS [PP].
- **Packing list:** UK, EU or US option — 1x adapter + 1x interchangeable plug of that type [PP].
- **Compatibility list (page):** Raspberry Pi 5 (4/8 GB), Pi 4 B, Pi 400, CM4 carriers [PP].

## Interfaces, terminals and pin mapping
- Output: one captive (non-detachable) cable ending in a USB Type-C plug [DS]. No other output connector, no DC barrel, no detachable cable [DS].
- Input: interchangeable AC plug heads (EU / UK / US drawings in the datasheet) [DS]. The product page sells one plug type per unit (UK Type G, EU Type C or US Type A) [PP].
- PD negotiation: the supply offers 5V/9V/12V/15V profiles; the load's PD sink controller selects the profile [DS]. Full-load currents per profile: 5 A / 3 A / 2.25 A / 1.8 A [DS].
- No data lines, switches, LEDs or indicators are described in the datasheet [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **The 5 V profile is 5 A** (datasheet "5V 5A" full load; product page "5.1V 5.0A"). This is the profile Raspberry Pi 5 needs for full USB peripheral current; do not describe this PSU as a 3 A supply [DS][PP].
- **27 W is the continuous rated power across all profiles** — 5V×5A = 25.5 W, 9V×3A = 27 W, 12V×2.25A = 27 W, 15V×1.8A = 27 W [DS]. Quote the profile currents, not "27 W at 5 V".
- **Cable is captive, 18 AWG, USB Type-C** [DS]. Length: datasheet says 1200 ± 50 mm; product page says 1.5 m — use the datasheet figure (1.2 m) in content and flag the discrepancy (see Conflicts).
- **Plug count**: the datasheet (Rev 1.0, Feb 2024) says three interchangeable plugs are included; the product page sells UK/EU/US as options with "only one included". Tell readers to choose the plug option at checkout and not to expect three plugs (see Conflicts and Needs verification).
- **Operating temperature is 0–40 °C** [DS]; do not place it in enclosed hot spaces or outdoors below 0 °C.
- **Efficiency**: datasheet 84.25 % (5V) / 86.62 % (9V/12V/15V); product page "~82%". Use the datasheet values.
- Ripple < 200 mV p-p at full load [DS] — relevant if readers power analog sensors directly from the Pi's 5 V rail.
- The datasheet does not state a PPS mode, a PD version number, or an E-marker — do not claim them.

## Power and electrical limits
- Input: 100–240 VAC, 50–60 Hz; max AC current < 0.6 A; cold-start inrush < 80 A; standby < 0.1 W [DS].
- Output: 27 W continuous; PD profiles 5V 5A, 9V 3A, 12V 2.25A, 15V 1.8A; typical output voltage 5.1 V [DS].
- Protections stated: overcurrent, short circuit [DS]. Over-voltage and over-temperature protection are not stated [DS].
- ESD: ± 4 kV direct, ± 8 kV air [DS].
- Operating 0–40 °C; storage -25–70 °C [DS].

## Software support
- None required or applicable — a PD power supply has no firmware, driver or library. Raspberry Pi 5 negotiates the 5 V 5 A profile itself; no Cytron software is stated [DS][PP].

## Compatibility and accessories
- Designed for Raspberry Pi 5 "and other compatible development boards" [DS]; product page lists Raspberry Pi 4 Model B and Raspberry Pi 5 [PP].
- Any USB-C PD sink that accepts a 5V/9V/12V/15V profile within the stated currents (datasheet: "can be used to charge many types of devices") [DS].
- Included: adapter with captive USB-C cable; AC plug head(s) — see Conflicts for one vs three [DS][PP].
- Not included / not stated: no spare cable (captive), no USB-A output, no on/off switch, no PPS [DS].
- Related Cytron product (do not confuse): 17.5W 5V 3.5A USB-C Power Adapter (V-AD-5V3P5A) — see usbc-psu-17w5.md.

## Common mistakes / troubleshooting
- Calling it "5V 3A" — it is 5V 5A on the 5 V profile [DS].
- Expecting all three plug heads in the box — the product page says only the chosen one is included [PP]; the datasheet says three [DS]. Check the actual shipment.
- Quoting the cable as 1.5 m — datasheet says 1200 ± 50 mm [DS].
- Using it above 40 °C ambient — outside the stated operating range [DS].
- Expecting a Pi 5 "low-power USB" warning to clear with any 27 W supply — the Pi must negotiate the 5 A profile; this PSU offers it [DS], but a non-PD cable or hub in between defeats negotiation (general PD behaviour; not stated by Cytron).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Output cable length | [DS] 1200 ± 50 mm; [PP] spec block 1200 ± 50 mm | [PP] features list "1.5-meter" | [DS] wins: 1.2 m. The page contradicts itself |
| Efficiency | [DS] 84.25 % (5V) / 86.62 % (9V/12V/15V) | [PP] "~82%" | [DS] wins |
| AC plugs included | [DS] "includes three interchangeable AC plugs" | [PP] plug option UK/EU/US, "only one included" | [DS] formally wins, but the page describes current selling practice; state "one plug as selected; datasheet Rev 1.0 lists three" and verify |
| Target boards | [DS] Raspberry Pi 5 and other compatible boards | [PP] Raspberry Pi 4 Model B and Raspberry Pi 5 | No contradiction; Pi 4 B is an addition on the page |
| 5 V profile voltage | [DS] typical 5.1 V; full load "5V 5A" | [PP] "5.1V 5.0A" | Same profile; quote "5.1 V typical, 5 A" |
| Product/model code | [PP] V-AD-27W-PD | [DS] AD-27W-PD-X; certification MPN HD-PD27W-wwz | V-AD-27W-PD is the Cytron SKU; AD-27W-PD-X is the datasheet model (X presumably the plug suffix — not stated); HD-PD27W-wwz is the certified MPN |

## Needs verification
- Adapter body dimensions and weight — datasheet section 3 has drawings only; numbers did not extract.
- PD version (2.0/3.0), PPS support, E-marker presence, over-voltage / over-temperature protection — not stated.
- Meaning of the "-X" suffix in AD-27W-PD-X and the "wwz" suffix in MPN HD-PD27W-wwz — not stated.
- Whether the Raspberry Pi 5 negotiates the 5 A profile and clears the low-current USB limit with this exact unit — stated only as design intent [DS]; no Cytron test record read.
- Noise/coil whine, hold-up time, line/load regulation — not stated.
- Cable length: the product page gives both 1.5 m (features) and 1200 ± 50 mm (spec block); the datasheet says 1200 ± 50 mm — ask Cytron to fix the page.

## Sources
- [DS] "AD-27W-PD-X Universal PSU Datasheet" — 27W 5V 5A USB-C Universal Power Adapter, Rev 1.0, February 2024 — https://docs.google.com/document/d/1pLMnoGWQFCbzt7I2AX8-qhGa6N6ljDat5eaFH6eBu-4/edit (Google Doc; dimension drawings did not extract)
- [PP] Product page https://my.cytron.io/p-27w-pd-5v-5a-usb-c-universal-power-adapter (read by coordinator 2026-10-19: RM50.00, in stock 88, warranty 12 months, plug options UK/EU/US)
