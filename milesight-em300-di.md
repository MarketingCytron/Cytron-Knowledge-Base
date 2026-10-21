# Milesight EM300-DI LoRaWAN Pulse Counter — Verified Reference

| | |
|---|---|
| Product code | `EM300-DI` (Milesight model). Cytron code `LR-EM300-DI`, MPN `EM300-DI-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page, EM300-DI datasheet read in full, EM300-DI user guide V1.1 (31 Oct 2023) read for safety, hardware, GPIO wiring figure (rendered and read), button/LED, interface settings, installation, battery and uplink sections; milesight.com overview text read |
| Primary source | Milesight *EM300-DI Datasheet*, https://resource.milesight.com/milesight/iot/document/em300-di-datasheet-en.pdf (read 2026-10-21; no version printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight EM300-DI datasheet PDF. [UM] = Milesight EM300-DI User Guide V1.1, 31 Oct 2023 (it shares EM300-series installation text, including EM300-ZLD/SLD/MCS sections that do not apply here). [PP] = Cytron product page (its datasheet/user-guide links are Google Drive copies, not opened). [VEN] = milesight.com EM300-DI product page overview and FAQ text.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless | LoRaWAN®, Milesight D2D; internal antenna | [DS] |
| Frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan (Cytron) | "Support Malaysia AS923-2, Singapore AS923-1"; MPN `EM300-DI-915M` | [PP] |
| Tx power / sensitivity | 16 dBm (868) / 20 dBm (915) / 19 dBm (470); -137 dBm @ 300 bps | [DS] |
| Mode | OTAA/ABP Class A | [DS] |
| GPIO port | 1 × GPIO interface, dry contact | [DS] |
| Work mode | Pulse counter or digital input | [DS] |
| Input frequency | ≤ 2000 Hz | [DS] |
| Minimum pulse width | 250 µs | [DS] |
| Cable | 1 m (customizable); wire connection 3.5 mm | [DS] |
| Applicable meters | Reed-switch meters or any other passive pulse meters | [DS] |
| Temperature | -30 ~ +70 °C; ±0.3 °C (0 ~ 70 °C), ±0.6 °C (-30 ~ 0 °C); 0.1 °C resolution | [DS] |
| Humidity | 0 ~ 100 % RH; ±3 % (10 ~ 90 % RH), ±5 % outside; 0.5 % RH resolution | [DS] |
| LED / button | 1 × LED (internal); 1 × power/reset button (internal) | [DS] |
| Power on/off | NFC or internal power button | [DS] |
| Configuration | NFC via mobile app (Milesight ToolBox); downlink | [DS] |
| Advanced features | D2D controller, data storage (1,000 entries), retransmission, data retrieval, temperature threshold alarms, water flow/outage alarms | [DS] |
| Power supply | 1 × 4000 mAh ER18505 Li-SOCl₂ battery (8000 mAh version optional) | [DS] |
| Battery life | 5 years (10 min interval, 25 °C; lab figure) | [DS] |
| Operating temperature / humidity | -30 ~ +70 °C; ≤ 95 % non-condensing | [DS] |
| Ingress protection | IP67 | [DS] |
| Housing | ABS + PC (flame retardant), white | [DS] |
| Dimensions / weight | 105.6 × 85.2 × 27 mm; 114.2 g with 1 battery and wire | [DS] |
| Installation | Wall screws, 3M tape, cable tie | [DS] |
| Approvals | CE, FCC, ISED, RCM, Telec; RoHS | [DS] |
| Reporting interval | 1 – 1080 min (default shown as "10 80", read as 1080 min — see *Needs verification*) | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM300-DI LoRaWAN Pulse Counter"; Code `LR-EM300-DI`; MPN `EM300-DI-915M`; RM275.50; availability "Enquiry"; no warranty line shown [PP].
- Spec block: LoRaWAN Class A + Milesight D2D; 1 × GPIO dry contact (pulse counter / digital input); "Support Malaysia AS923-2, Singapore AS923-1"; temperature -30 ~ 70 °C ±0.3 °C; humidity 0–100 % ±3 %; "1 × 4000 mAh replaceable battery"; **battery life "Up to 10 Years (with dual batteries and standard interval)"**; IP67 [PP].
- Description claims up to 10 km transmission and up to 10-year battery; 1 m fly lead for reed switches or passive pulse meters [PP].
- **Packing list:** EM300-DI, 2 × wall mounting kits, 2 × screw caps, quick guide, warranty card [PP] (same as [UM]).
- Resources: datasheet and user guide (Google Drive links), payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
**Pulse cable (1 m fly lead)** — from the user guide "GPIO Wiring" figure (rendered and read) [UM]:
| Wire | Signal | Connect to |
|---|---|---|
| Red | GPIO | One side of the meter's reed switch / dry contact |
| Black | GND | Other side of the reed switch / dry contact |

Internal **power button and LED** (open the housing) [UM]:
| Action | Function | LED |
|---|---|---|
| Hold > 3 s | Power on / power off | Off → On / On → Off |
| Hold > 10 s | Reset to factory default | Blinks quickly |
| Quick press | Check on/off status | On = on; off = off |

## Rules and gotchas (for code, wiring and tutorials)
- **Dry contact only, per the datasheet.** Wire a reed switch or passive (volt-free) pulse output between red (GPIO) and black (GND). Do not apply external voltage to the lead [DS][UM]. Milesight's web page also mentions open-collector outputs (see *Needs verification* for polarity).
- **Pulse limits:** ≤ 2000 Hz, ≥ 250 µs pulse width. The optional pulse filter counts only pulses longer than 250 µs [DS][UM].
- **Interface type:** Counter or Digital, set in ToolBox [UM]. In counter mode you can set an initial count and a pulse conversion (e.g. "1 L = 40 pulses") [UM].
- **Battery: ER18505 Li-SOCl₂ only** (no alkaline). Do not fit two cells in the 4000 mAh version (or one in the 8000 mAh version) — battery level would be wrong. Fit the cell in the upper position to reduce NFC interference; observe polarity [UM].
- **NFC configuration:** hold the phone's NFC area on the device in ToolBox (NFC mode). Data storage export via ToolBox covers at most the last 14 days [UM].
- **Payload** (port 85): battery 01 75 (%); temperature 03 67 INT16/10 °C; humidity 04 68 UINT8/2 %RH; digital input 05 00; pulse counter 05 c8 UINT32 (and 05 e1 with conversion value after V1.1). Use the official decoder [UM].
- Mount away from metal objects; screw holes on a horizontal line [UM].

## Power and electrical limits
- 1 × ER18505 Li-SOCl₂ 4000 mAh (8000 mAh optional) — 5 years at 10-min interval, 25 °C (lab) [DS]. Retransmission and short intervals shorten life [UM].
- Pulse input: dry contact; ≤ 2000 Hz; ≥ 250 µs [DS].
- -30 ~ +70 °C, ≤ 95 % RH, IP67 [DS].

## Software support
- Milesight D2D: acts as a D2D controller to send commands to Milesight D2D agents without a gateway [DS][UM].
- Milesight IoT Cloud and Development Platform; standard LoRaWAN network servers [DS]. Decoders: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Meters: reed-switch water/gas meters or other passive pulse meters [DS]. For electrical current without a meter, see `milesight-ct10x.md`.
- Spare cell: ER18505 Li-SOCl₂ (not sold on this page).

## Common mistakes / troubleshooting
- **Count too high / noisy:** enable the pulse filter (> 250 µs) [UM].
- **Wrong battery %:** wrong cell count for the version, old cells, or non-ER18505 cells [UM].
- **No uplinks after install:** device not powered on (NFC or hold the internal button > 3 s) or plan mismatch with the gateway [UM][DS].
- **NFC read fails:** battery in the lower slot can interfere; align the phone's NFC area [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [PP] "Up to 10 Years (with dual batteries and standard interval)" while listing "1 × 4000 mAh" | [DS] 5 years, 1 × 4000 mAh, 10-min interval, 25 °C (8000 mAh version optional) | [DS] wins: 5 years for the 4000 mAh unit. 10 years would need the optional 8000 mAh (two-cell) version (inferred) |
| Accepted pulse outputs | [VEN] web page: dry contact, reed switch and open collector | [DS] dry contact; reed-switch or other passive pulse meters | [DS] wins for spec; open collector to *Needs verification* |
| Range claim | [PP] "up to 10 km" | [DS] "line of sight of 10km" | Consistent; line-of-sight figure |

## Needs verification
- Default reporting interval: the guide text reads "Default: 10 80 minutes" (likely 1080 min; possibly a typo).
- Open-collector support and required polarity (red = collector, black = emitter/GND — inferred, not stated).
- Which EM300-DI battery version Cytron's `EM300-DI-915M` is (4000 mAh assumed from the Cytron spec line).
- Warranty period (not shown on the Cytron page).
- AS923 sub-plan shipped for Malaysia.

## Sources
- [DS] EM300-DI Datasheet: https://resource.milesight.com/milesight/iot/document/em300-di-datasheet-en.pdf (read 2026-10-21).
- [UM] EM300-DI User Guide V1.1 (31 Oct 2023): https://resource.milesight.com/milesight/iot/document/em300-di-user-guide-en.pdf
- [VEN] Milesight EM300-DI product page: https://www.milesight.com/iot/product/lorawan-sensor/em300-di
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em300-di-lorawan-pulse-counter (read 2026-10-21). Cytron's Google Drive copies (not opened): (Cytron document — link not public) (Cytron document — link not public)
