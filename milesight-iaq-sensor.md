# Milesight LoRaWAN Indoor Air Monitoring (IAQ) Sensor — AM102 / AM102L / AM103 / AM307 / AM308 / AM319 — Verified Reference

| | |
|---|---|
| Product code | Cytron parent code `V-LR-AM`. Variants: AM102 (with display) `LR-AM102` / MPN `AM102-915M`; AM102L (without display) `LR-AM102L-WDS` / `AM102L-915M`; AM103 `LR-AM103` / `AM103-915M`; AM307 `LR-AM307` / `AM307-915M`; AM308 `LR-AM308` / `AM308-915M`; AM319 `LR-AM319` (no MPN shown) [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (all 6 model/display combinations: code, MPN, price; spec blocks; FAQ), Milesight datasheets read in full: AM30x (AM307/AM308(L)), AM319, AM102 & AM102L, AM103 & AM103L; AM300 Series User Guide V2.2 (29 Mar 2024) and AM102(L)/AM103(L) User Guide V1.2 (31 Aug 2023) read for packing, buttons/LEDs, power supply, installation and maintenance |
| Primary source | Milesight datasheets: *AM30x* (https://resource.milesight.com/milesight/iot/document/am30x-datasheet-en.pdf), *AM319*, *AM102 & AM102L*, *AM103 & AM103L* (read 2026-10-21; no versions printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = the four Milesight datasheets named above. [UM] = Milesight AM300 Series User Guide V2.2 (AM307, AM308(L), AM319) and AM102(L) & AM103(L) User Guide V1.2. [PP] = Cytron product page, including its FAQ block. [VEN] = milesight.com AM300 product page (download links). The Cytron listing name "IAQ Sensor" covers **six sellable configurations of two Milesight families**: AM100 series (AM102, AM102L, AM103) and AM300 series (AM307, AM308, AM319).

## What it is
| Model (Cytron variant) | Measures | Display | Power | Src |
|---|---|---|---|---|
| AM102 | Temperature, humidity | 2.13" E-ink | 2 × ER14505 | [DS] |
| AM102L ("Without Display") | Temperature, humidity | none | 2 × ER14505 | [DS] |
| AM103 | Temperature, humidity, CO₂ (NDIR) | 2.13" E-ink | 2 × ER14505 | [DS] |
| AM307 | Temp, humidity, light, PIR motion, CO₂ (NDIR), TVOC, pressure | 4.2" E-ink | 4 × ER14505 or USB-C 5 V | [DS] |
| AM308 | AM307 + PM2.5, PM10 | 4.2" E-ink | 4 × ER14505 or USB-C 5 V | [DS] |
| AM319 | AM308 sensors (CO₂ photoacoustic) + **HCHO or O₃** (PN HCHO-IR / HCHO-IR-W / O3) | 4.2" E-ink | **USB-C 5 V/1 A only, no battery**; LoRaWAN **Class C** | [DS] |

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless (all) | LoRaWAN®, internal antenna; 16 dBm (868) / 22 dBm (915) / 19 dBm (470); -137 dBm @ 300 bps | [DS] |
| Frequency plans (Milesight) | CN470 / RU864 / IN865 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan (Cytron) | "Support Malaysia AS923-2, Singapore AS923-1"; MPNs `-915M` | [PP] |
| Class | AM102/AM103/AM307/AM308: OTAA/ABP Class A. **AM319: OTAA/ABP Class C** | [DS] |
| Temperature (all) | -20 ~ 60 °C; typ. ±0.3 °C (-20 ~ 0 °C), ±0.2 °C (0 ~ 60 °C); 0.1 °C | [DS] |
| Humidity (all) | 0 ~ 100 % RH; typ. ±2 % RH (25 °C); 0.5 % RH | [DS] |
| CO₂ AM103 / AM307 / AM308 | NDIR, 400 ~ 5000 ppm, ±(30 ppm + 3 % of reading) (0 ~ 50 °C), 1 ppm | [DS] |
| CO₂ AM319 | Photoacoustic, 400 ~ 2000 ppm, ±(50 ppm + 5 % of reading) (-10 ~ 60 °C) | [DS] |
| Motion (AM30x, AM319) | PIR, 80° H × 55° V, 5 m; vacant/occupied only | [DS][PP] |
| Light (AM30x, AM319) | Photodiode, 0 – 60000 lux reported as 6 levels (0–5) | [DS] |
| TVOC (AM30x) | MOX, IAQ rating 1.00 – 5.00, ±1, 0.01 | [DS] |
| TVOC (AM319) | IAQ rating 1.00 – 5.00, or concentration 0 – 2000 µg/m³ ±(20 µg/m³ + 15 %) (1–500 µg/m³) | [DS] |
| Barometric pressure (AM30x, AM319) | 260 – 1260 hPa, ±0.5 hPa, 0.1 hPa | [DS] |
| PM2.5 / PM10 (AM308, AM319) | Laser scattering, 0 – 1000 µg/m³; 0–100 ±10 µg/m³, 100–1000 ±10 % (AM319 HCHO-IR-W: PM2.5 only, different accuracy) | [DS] |
| HCHO (AM319 HCHO PNs) | Electrochemical, 0 – 1.25 mg/m³ (0 – 1 ppm), ±10 %, working life 6 years | [DS] |
| O₃ (AM319 O3 PN) | Electrochemical, 0 – 10 ppm, ±5 % FS, working life 2 years | [DS] |
| Display | AM102/AM103: 2.13" B&W E-ink; AM102L: none; AM307/AM308/AM319: 4.2" B&W E-ink | [DS] |
| Buttons | AM10x: 1 × power/reset. AM30x/AM319: 1 × power + 1 × reset | [DS] |
| LED / buzzer | AM102: status LED; AM103: traffic-light LED; AM30x/AM319: traffic-light LED + buzzer | [DS] |
| USB | AM30x/AM319: 1 × USB-C for power, configuration or console. AM10x: none | [DS] |
| Configuration | NFC (mobile app); AM30x/AM319 also PC software via NFC or USB-C; downlink | [DS] |
| Data storage | AM102 1,280; AM103 640; AM30x/AM319 18,000 entries; retransmission and retrieval | [DS] |
| Power AM10x | 2 × 2700 mAh ER14505 Li-SOCl₂ replaceable | [DS] |
| Power AM307/AM308 | 4 × 2700 mAh ER14505 Li-SOCl₂, or 5 V/1 A USB-C | [DS] |
| Power AM319 | 5 V/1 A USB-C only (cable and adapter in the box) | [DS][UM] |
| Battery life (10 min, 25 °C, SF7 lab) | AM102 > 7 y; AM102L > 9 y; AM103 ~4.5 y; AM307 ~3.9 y; AM308 ~1.3 y (shorter at SF10; e.g. AM308 ~1 y SF10 US915) | [DS] |
| Operating temperature | -20 ~ 60 °C (E-ink screen 0 ~ 40 °C) | [DS] |
| Humidity (operating) | AM10x 0 ~ 95 %; AM30x/AM319 10 ~ 90 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Dimensions | AM10x 68 × 65 × 20.5 mm; AM30x/AM319 100.8 × 114 × 22 mm | [DS] |
| Weight | AM307 182.5 g, AM308 222.6 g (with batteries); AM319 148 g; AM103 182.5 g as printed | [DS] |
| Installation | Wall mounting via 3M tape or screws | [DS] |
| Approvals | CE, CE (RED), FCC, ISED; RoHS; AM319 HCHO-IR-W adds WELL | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "LoRaWAN Indoor Air Monitoring (IAQ) Sensor"; parent code `V-LR-AM`; warranty 12 months; RM223.85 – RM1,678.95; cashback RM6.72 – RM50.37; default "Availability: Backorder Only / BACKORDER" [PP].
- Options "IAQ Sensor" AM319 / AM308 / AM307 / AM103 / AM102 and "Display" With / Without (Without = AM102L only). Variant pages: …/p-am319-lorawan-9-in-1-iaq-sensor, …/p-am308-lorawan-8-in-1-iaq-sensor, …/p-am307-lorawan-7-in-1-iaq-sensor, …/p-am103-lorawan-indoor-ambience-monitoring-sensor, …/p-am102-lorawan-2-in-1-iaq-sensor, …/p-am102-lorawan-2-in-1-iaq-sensor-without-display. Each shows "Availability: Enquiry" [PP].
- Model list on the page: AM102 (Temp, Hum); AM103 (+CO₂); AM307 (Temp, Hum, Light, Motion, CO₂, TVOC, Pressure); AM308 (+PM2.5, PM10); AM319 "(… PM2.5, PM10, Motion)" [PP].
- AM300 spec block: Class A for the series; CO₂ "NDIR / Photoacoustic (AM319)" with range 400 – 5000 ppm for all; HCHO and O₃ listed for AM319; battery life AM307 ~3 years, AM308 over 1 year; power supply line left blank [PP].
- AM100 spec block: AM102 -20 ~ +70 °C, ±0.2 °C, humidity "±0.2% RH"; AM103 ±0.3/±0.6 °C, ±3 %/±5 % RH; 2 × 2700 mAh ER14505; AM102 > 7 y, AM102L > 9 y, AM103 ~3 y; IP30; 68 × 65 × 20.5 mm [PP].
- **Packing list:** 1 × AM30x / AM10x series device, mounting bracket, 3M double-sided tape, 3 × wall mounting kits, theft-deterring screw, quick guide, warranty card [PP].
- FAQ: TVOC needs ~48 h initial power-on and outdoor clean-air auto-calibration (> 1 min), ~15 min to stabilise after each power-on; TVOC is a unitless IAQ index; PIR gives only occupied/vacant (use VS121 for counts); sensors are factory calibrated; AM319 only displays CO₂ 400 – 2000 ppm [PP].
- Resources: AM307&AM308 datasheet, AM319 datasheet, AM300 Series User Guide, AM103 datasheet and user guide, AM102/AM102L datasheet and user guide, payload decoder, firmware & SDK [PP].

## Interfaces, terminals and pin mapping
No screw terminals. **Buttons and lights** [UM]:
| Device | Action | Result / light |
|---|---|---|
| AM10x | Hold power > 3 s | Power on (Off → On) / off (On → Off) |
| AM10x | Hold power > 10 s | Factory reset (quick blinks) |
| AM103 | — | Traffic-light LED shows CO₂ level (Excellent / Polluted / Bad) when enabled |
| AM30x/AM319 | Hold power > 3 s | Power on/off |
| AM30x/AM319 | Quick press power | Refresh screen data (blinks once) |
| AM30x/AM319 | Hold reset > 10 s | Factory reset (quick blinks) |
| AM30x/AM319 | — | Traffic light: green = excellent, yellow = polluted, red = bad (threshold-based); AM319 can be blinking or always on |
**USB-C (AM30x/AM319)** is inside the rear cover: route the cable through an opening cut in the left or right side of the cover [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Pick the right model:** only AM319 has HCHO or O₃; only AM308/AM319 have PM; AM102(L) is temperature/humidity only [DS].
- **AM319 has no battery** — it needs permanent 5 V/1 A USB-C power, and it is LoRaWAN Class C [DS].
- **Batteries: ER14505 Li-SOCl₂ only** (no alkaline), correct polarity, all new cells. AM30x ships with a battery insulation sheet to remove [UM].
- **USB-C does not charge batteries;** with both fitted, external power is used first [UM].
- **E-ink screen switches off outside 0 ~ 40 °C.** Smart screen mode stops updating after 20 min vacant [UM][PP].
- **TVOC:** first power-on keep it on ~48 h; give it > 1 min of clean outdoor air to auto-calibrate (repeat after reboot/reset); ~15 min to stabilise after each power-on. TVOC on AM30x is a unitless IAQ index and cannot be converted to ppb or mg/m³ [PP].
- **Mounting:** ≥ 1.5 m above the floor; not upside down; away from windows, doors, vents, fans, AC, heat/cold sources; nothing blocking the PIR/light window; do not paint or cover the air inlets [UM].
- **Sensor maintenance (AM319):** HCHO sensor life 6 years, O₃ sensor 2 years; replacement chips from Milesight. Avoid corrosive gas, silicone vapour, high VOC levels; clean with a damp cloth only [UM].

## Power and electrical limits
- AM10x: 2 × ER14505 (2700 mAh each). AM307/AM308: 4 × ER14505 or 5 V/1 A USB-C. AM319: 5 V/1 A USB-C only [DS].
- -20 ~ 60 °C; E-ink 0 ~ 40 °C; IP30, indoor [DS].

## Software support
- Milesight ToolBox app (NFC) for all; ToolBox PC software via NFC or USB-C for AM30x/AM319 [DS].
- Thresholds, calibration, data storage/retransmission/retrieval, screen modes, button lock (AM300), CO₂ pressure compensation and TVOC mode (AM300 UM V2.2) [DS][UM].
- Milesight IoT Cloud and Development Platform; standard LoRaWAN servers. Decoders: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`. AM319 (Class C) needs a network server that supports Class C (standard).
- Kit: `milesight-iaq-kit.md` (Cytron's Indoor Air Quality Kit).
- People counting instead of occupancy: `milesight-vs121.md` (named in the Cytron FAQ).

## Common mistakes / troubleshooting
- **TVOC wrong after power-on:** follow the 48 h / outdoor-air / 15 min routine [PP].
- **Blank screen:** room below 0 °C or above 40 °C, or smart screen mode after 20 min vacancy [UM][PP].
- **AM319 dead:** no USB power (it has no battery) [DS].
- **CO₂ on AM319 stops at 2000 ppm:** that is its range [DS][PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| AM319 LoRaWAN class | [PP] AM300 series "OTAA/ABP Class A" | [DS] AM319 Class C | [DS] wins: AM319 Class C |
| AM319 power | [PP] power supply line blank; "Support batteries or DC power supply" for the series | [DS] AM319 5 V/1 A USB-C only | [DS] wins: no battery on AM319 |
| AM319 CO₂ range/accuracy | [PP] 400 – 5000 ppm, ±(30 ppm + 3 %) for the series | [DS] AM319 400 – 2000 ppm, ±(50 ppm + 5 %) | [DS] wins (the Cytron FAQ also says AM319 shows 400–2000 ppm) |
| AM102 temperature range | [PP] -20 ~ +70 °C | [DS] -20 ~ 60 °C | [DS] wins |
| AM102 humidity accuracy | [PP] ±0.2 % RH | [DS] ±2 % RH | [DS] wins |
| AM103 accuracy | [PP] ±0.3/±0.6 °C; ±3 %/±5 % RH | [DS] ±0.2/±0.3 °C; ±2 % RH | [DS] wins |
| AM319 sensor list | [PP] model list ends "PM2.5, PM10, Motion" | [DS] adds HCHO or O₃ by PN | [DS] wins |
| Battery life | [PP] AM307 ~3 y, AM308 > 1 y, AM103 ~3 y | [DS] AM307 ~3.9 y, AM308 ~1.3 y, AM103 ~4.5 y (SF7) | [DS] wins; values are SF-dependent lab figures |
| Packing list (AM319) | [PP] same list for all | [UM] AM319 also gets a 1.2 m Type-C cable and power adapter | [UM] wins |

## Needs verification
- Which AM319 part number Cytron sells (HCHO-IR, HCHO-IR-W or O3); Cytron shows no MPN.
- AM102L packing and price page say "Without Display" — confirm it is the Milesight AM102L (MPN `AM102L-915M` suggests so).
- AM103 weight "182.5 g" in [DS] looks copied from AM307 (not checked).
- AS923 sub-plan shipped for Malaysia.
- Whether the AM307/AM308 sold by Cytron include the 4 batteries and/or a USB adapter.

## Sources
- [DS] AM30x Datasheet: https://resource.milesight.com/milesight/iot/document/am30x-datasheet-en.pdf (milesight.com now also lists am30xl-datasheet-en.pdf, not read).
- [DS] AM319 Datasheet: https://resource.milesight.com/milesight/iot/document/am319-datasheet-en.pdf
- [DS] AM102 & AM102L Datasheet: https://resource.milesight.com/milesight/iot/document/am102-and-am102l-datasheet-en.pdf
- [DS] AM103 & AM103L Datasheet: https://resource.milesight.com/milesight/iot/document/am103&am103l-datasheet-en.pdf
- [UM] AM300 Series User Guide V2.2 (29 Mar 2024): https://resource.milesight.com/milesight/iot/document/am300-series-user-guide-en.pdf
- [UM] AM102(L) & AM103(L) User Guide V1.2 (31 Aug 2023): https://resource.milesight.com/milesight/iot/document/am102(l)-and-am103(l)-user-guide-en.pdf
- [VEN] Milesight AM300 product page: https://www.milesight.com/iot/product/lorawan-sensor/am300
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-lorawan-iaq-sensor (read 2026-10-21).
