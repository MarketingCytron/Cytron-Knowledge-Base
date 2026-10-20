# 17.5W 5V 3.5A USB-C Power Adapter for Raspberry Pi — Verified Reference

| Field | Value |
|---|---|
| Product code | V-AD-5V3P5A [PP]; datasheet model name AD-5V3P5-3P [DS] |
| Family | Power and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Size, warranty and protections are now Cytron-stated; the Cytron Pi 5 tutorial was read (works, with a reduced-current warning) |
| Primary source | "17.5W 5V 3.5A Universal USB-C PSU Datasheet" (17.5W 5V 3.5A USB-C Universal Power Adapter, AD-5V3P5-3P, Datasheet), Rev 2.0, October 2024, Cytron Technologies Sdn Bhd [DS] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A 17.5 W single-voltage (5 V, 3.5 A) AC-to-DC power supply with a captive USB Type-C cable, "specifically designed to provide power to the latest Raspberry Pi 4 Model B and other compatible development boards" [DS]. It accepts 100–240 VAC, 50–60 Hz, ships with ONE interchangeable AC plug (default UK), and is finished in black [DS]. It is not a USB Power Delivery supply: the datasheet lists a single 5 V output and no PD profiles [DS]. The product page recommends it for Raspberry Pi 4 Model B, Pi 400 and CM4 carrier boards with USB-C, says it is "suitable for 24-hour operation", and also lists Raspberry Pi 5 in its compatibility list [PP].

## Specifications
All rows are from the datasheet spec tables unless marked [PP].

### Output parameters [DS]
| Item | Value | Src |
|---|---|---|
| Typical output voltage | 5.1 VDC | [DS] |
| Rated output voltage, no load | 4.75 – 5.4 VDC | [DS] |
| Rated output voltage, full load (Iout = 3.5 A) | 4.75 – 5.4 VDC | [DS] |
| Rated power, continuous | 17.5 W | [DS][PP] |
| Nominal load current | 3.5 A | [DS][PP] |
| Ripple and noise, at full load | < 200 mV (p-p) | [DS] |
| Protection | Overcurrent Protection; Short Circuit Protection | [DS] |
| Efficiency (average) | 82.32 % | [DS] |
| Electrostatic discharge | Direct discharge ± 4 kV; Air discharge ± 8 kV | [DS] |
| Output cable length | 1500 ± 50 mm | [DS] |
| Output cable type | UL 2464, 20AWG | [DS] |
| Output cable connector/plug | USB Type-C | [DS] |
| Cable colour | Black | [DS] |

### Input parameters [DS]
| Item | Value | Src |
|---|---|---|
| Rated input voltage | 100 – 240 VAC | [DS][PP] |
| Absolute min/max input voltage | 90 – 264 VAC | [DS] |
| Rated input frequency | 50 – 60 Hz | [DS][PP] |
| Maximum AC current | < 0.6 A | [DS] |
| Maximum inrush current, cold start | < 60 A | [DS] |
| Standby power, at 115 or 230 VAC | < 0.1 W | [DS] |
| Efficiency, average, at 115 or 230 VAC | 82.32 % | [DS] |

### Environment, compliance, commercial
| Item | Value | Src |
|---|---|---|
| Operating temperature range | 0 ~ 40 °C | [DS] |
| Storage temperature range | -25 ~ 70 °C | [DS] |
| Mean Time Between Failures (MTBF) | 30000 hours | [DS] |
| Compliance — UKCA | BS EN 62368-1:2014+A11:2017; "EN 62378-1:2014+A11:2017" (as printed) | [DS] |
| Compliance — UL | IEC 62368-1:2014 | [DS] |
| Compliance — CE | EN 55032:2015/A11:2020; EN 55035:2017; EN IEC 61000-3-2:2019; EN 61000-3-3:2013/A1:2019 | [DS] |
| Compliance — RoHS | IEC 62321-1:2013; IEC 62321-2:2021; IEC 62321-3-1:2013; IEC 62321-4:2013+A1:2017; IEC 62321-5:2013; IEC 62321-6:2015; IEC 62321-7-1:2015; IEC 62321-7-2:2017; IEC 62321-8:2017 | [DS] |
| Certification basis | "All Certifications are based on MPN: HT24A-0503500BS" | [DS] |
| AC plug | ONE interchangeable AC plug included, default UK; "The PSU shipped from 23rd October 2024 onwards, this PSU only comes with UK Plug." | [DS] |
| AC plug options | UK / EU (chosen at purchase) | [PP] |
| Housing colour | Black ("sleek black color") | [DS] |
| Adapter dimensions / weight | Drawing "With UK Plug" and cable drawing only (values did not extract as text) | [DS] |
| Duty | "suitable for 24-hour operation" | [PP] |
| Price | RM32.00 | [PP] |
| Warranty | 12 months | [PP] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Features list:** 17.5 W; 5.1 V, 3.5 A; 1.5 m 20 AWG captive cable (spec: 1500 ± 50 mm UL2464 20 AWG); **short-circuit and over-current protection**; 100–240 V AC, 50/60 Hz, 0.6 A max; no-load 0.1 W max; ~82 % efficiency; ripple 200 mVp-p at 3.5 A; one interchangeable plug — UK (Type G) or EU (Type C) as selected; **47.8 × 89.8 × 65.95 mm with plug**; UKCA, UL, CE, RoHS [PP].
- **Compatibility list (page):** Raspberry Pi 5 (2/4/8 GB), Pi 4 B (1/2/4/8 GB), Pi 400, CM4 carrier boards, several Pi 4 cases [PP].
- **Packing list:** adapter main module + 1 interchangeable plug (UK or EU, as selected) [PP].
- **Cytron tutorial "Can 3A/3.5A PSU power Raspberry Pi 5?" (12 Oct 2023):** yes, a 3 A / 3.5 A PSU boots a Pi 5; the Pi shows "This power supply is not capable of supplying 5A. Power to peripherals will be restricted", and USB 3 ports are limited to 600 mA (1.6 A with the official 5 A PSU) [PP: tutorial].

## Interfaces, terminals and pin mapping
- Output: one captive cable ending in a USB Type-C plug; single fixed 5 V output [DS].
- Input: interchangeable AC plug head; UK plug by default, and UK only for units shipped from 23 October 2024 [DS].
- No PD profiles, no data lines, no switches or indicators are described [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **It is a 5 V 3.5 A supply, not 5 A.** Rated power 17.5 W, nominal load current 3.5 A [DS]. Never present it as a Raspberry Pi 5 full-power (5 A) supply.
- **Raspberry Pi 5 caveat.** The datasheet names Raspberry Pi 4 Model B as the design target [DS]; the product page's compatibility list includes Raspberry Pi 5 [PP] and links a Cytron tutorial "Can 3A/3.5A PSU power Raspberry Pi 5" [PP] — that tutorial could not be read in this session, so do not quote its test results. A Pi 5 on a non-5 A supply limits USB peripheral current (Raspberry Pi documentation behaviour; not stated by Cytron) — say so with that attribution, not as a Cytron spec.
- **Cable is captive, 1.5 m, 20 AWG** [DS] — thinner than the 27 W unit's 18 AWG. Output voltage is specified 4.75–5.4 V at the full 3.5 A load [DS].
- **Plug**: units shipped from 23 Oct 2024 come with the UK plug only [DS]; the product page still offers UK / EU options [PP] — tell readers to confirm plug availability at checkout (see Conflicts).
- **Operating temperature 0–40 °C** [DS].
- The datasheet lists no Raspberry Pi 5-specific statement, no PD, no PPS, no USB-A port — do not claim them.
- Datasheet compliance line "EN 62378-1:2014+A11:2017" appears to be a typographical variant of EN 62368-1; reproduce it as printed or omit, do not "correct" it silently.

## Power and electrical limits
- Input: rated 100–240 VAC, absolute 90–264 VAC, 50–60 Hz; max AC current < 0.6 A; cold-start inrush < 60 A; standby < 0.1 W [DS].
- Output: 5.1 V typical, 4.75–5.4 V no-load and full-load window, 3.5 A nominal, 17.5 W continuous; ripple < 200 mV p-p [DS].
- Protections stated: overcurrent, short circuit [DS]. Over-voltage and over-temperature protection are not stated [DS].
- ESD ± 4 kV direct / ± 8 kV air; MTBF 30000 hours; operating 0–40 °C; storage -25–70 °C [DS].

## Software support
- None required or applicable — fixed-output supply with no PD negotiation, firmware, driver or library [DS].

## Compatibility and accessories
- Designed for Raspberry Pi 4 Model B "and other compatible development boards" [DS].
- Product page recommendation: Raspberry Pi 4 Model B, Raspberry Pi 400, CM4 carrier boards with USB-C [PP]. Product page compatibility list additionally includes Raspberry Pi 5 (8/4/2GB), Pi 4 B (1–8GB), Pi 400, many CM4 carriers, Jetson Nano developer kit, VisionFive 2 [PP].
- Cytron tutorial linked from the product page: "Can 3A/3.5A PSU power Raspberry Pi 5" — https://my.cytron.io/tutorial/can-3a-3.5a-psu-power-raspberry-pi-5 (not readable in this session) [PP].
- Included: adapter with captive USB-C cable and one AC plug (UK default; UK only from 23 Oct 2024) [DS].
- Not included / not stated: spare plugs beyond the one, detachable cable, USB-A output, PD/PPS [DS].
- Related Cytron product (do not confuse): 27W PD 5V 5A USB-C Universal Power Adapter (V-AD-27W-PD) — see usbc-psu-27w-pd.md.

## Common mistakes / troubleshooting
- Treating it as a Pi 5 "27 W-class" supply — it is 17.5 W / 3.5 A [DS].
- Expecting an EU plug after 23 Oct 2024 — datasheet says UK only from that date [DS].
- Quoting the output as "exactly 5.1 V" — specified window is 4.75–5.4 V [DS]; 5.1 V is typical.
- Mixing up cable gauge with the 27 W unit — this one is 20 AWG, 1500 ± 50 mm [DS].
- Running above 40 °C ambient — outside the stated operating range [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| AC plug options | [DS] Rev 2.0 (Oct 2024): one plug, default UK; from 23 Oct 2024 UK plug only | [PP] options UK / EU | [DS] wins (and is dated Oct 2024); page option list may be stale — verify before promising an EU plug |
| Target board | [DS] Raspberry Pi 4 Model B and other compatible boards | [PP] compatibility list includes Raspberry Pi 5; recommended for Pi 4 B, Pi 400, CM4 carriers | Not a numeric conflict; state Pi 4 B as the design target and Pi 5 as "listed compatible on the product page, with reduced USB current" (attribute the latter to Raspberry Pi documentation, not Cytron) |
| Product/model code | [PP] V-AD-5V3P5A | [DS] AD-5V3P5-3P; certification MPN HT24A-0503500BS | V-AD-5V3P5A is the Cytron SKU; AD-5V3P5-3P is the datasheet model; HT24A-0503500BS is the certified MPN |
| UKCA standard name | [DS] "BS EN 62368-1:2014+A11:2017" | [DS] "EN 62378-1:2014+A11:2017" (same list) | Likely typo for EN 62368-1 within the datasheet; reproduce as printed, flagged |

## Needs verification
- Whether the EU plug option on the product page is still shipped after 23 Oct 2024 [DS] vs [PP].
- Over-voltage / over-temperature protection — not stated.
- Correct standard number behind the datasheet's "EN 62378-1:2014+A11:2017".
- The "3P" suffix meaning in AD-5V3P5-3P — not stated.
- Adapter weight — not stated.

## Sources
- [DS] "17.5W 5V 3.5A Universal USB-C PSU Datasheet" — AD-5V3P5-3P, Rev 2.0, October 2024 — https://docs.google.com/document/d/1xhmvk4w7S_FsKjmb7wwx1S1RvuXo-jRydAW7l1R8mxY/edit (Google Doc; dimension drawings did not extract)
- [PP] Product page https://my.cytron.io/p-5v-3p5a-usb-c-universal-power-adapter (read by coordinator 2026-10-19: RM32.00, in stock 142, plug options UK / EU)
- [PP] Cytron tutorial "Can 3A/3.5A PSU power Raspberry Pi 5" — https://my.cytron.io/tutorial/can-3a-3.5a-psu-power-raspberry-pi-5 (linked from the product page; not read — fetch blocked)
