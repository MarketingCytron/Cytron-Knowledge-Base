# Milesight EM300-MCS LoRaWAN Magnetic Contact Switch — Verified Reference

| | |
|---|---|
| Product code | `EM300-MCS` (Milesight model). Cytron code `LR-EM300-MCS`; no MPN shown [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight EM300-MCS datasheet PDF (4 pages, read in full) and EM300-MCS User Guide V2.3 (Dec 26, 2024; packing list, power button/LED, quick start, LoRaWAN/general/threshold/alarm/D2D settings, installation, battery, payload read) |
| Primary source | Milesight *EM300-MCS Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/em300-mcs-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | LoRaWAN, Milesight D2D; internal antenna | [DS] |
| Frequency plans (model) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP Class A; LoRaWAN V1.0.2 / V1.0.3; application port default 85 | [DS][UM] |
| Range | Up to 10 km line of sight | [DS] |
| Door magnet | Detection distance 20–30 mm; cable length 1.5 m | [DS] |
| Temperature | -30 to +70 °C; ±0.3 °C (0 to 70 °C), ±0.6 °C (-30 to 0 °C); 0.1 °C resolution | [DS] |
| Humidity | 0–100 % RH; ±3 % (10–90 %), ±5 % (below 10 / above 90 %); 0.5 % resolution | [DS] |
| LED / button | 1 × LED (internal); 1 × power/reset button (internal) | [DS] |
| Power on/off | NFC or internal power button | [DS] |
| Configuration | NFC via mobile app (Milesight ToolBox); downlink | [DS] |
| Advanced | Threshold alarm, D2D controller, data storage (2,800 entries), retransmission, retrievability | [DS] |
| Power supply | 1 × 4000 mAh ER18505 Li-SOCl₂ (8000 mAh version optional) | [DS] |
| Battery life (10 min interval + 48 triggers/day, lab) | Over 10 years (SF7, EU868 & US915); ~4.5 years (SF10, EU868); ~3.2 years (SF10, US915) | [DS] |
| Reporting interval | Default 10 min (1–1080 min); battery reported at join and every 6 h | [UM] |
| Operating temperature | -30 °C to +70 °C | [DS] |
| Humidity (operating) | 0–100 % non-condensing | [DS] |
| Ingress protection | IP67 (UV-resistant) | [DS] |
| Housing | Transceiver ABS + PC (flame retardant), white; magnet zinc alloy, silver grey | [DS] |
| Dimensions | Transceiver 105.6 × 85.3 × 27 mm; magnet 31 × 14 × 7.5 mm | [DS] |
| Installation | Transceiver: wall screws, 3M tape, cable tie (pole); magnet: screws or 3M tape | [DS][UM] |
| Regulatory | CE, FCC, ISED, RCM, Telec, ICASA; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM300-MCS LoRaWAN Magnetic Contact Switch"; brand Milesight; Code `LR-EM300-MCS`; warranty 12 months; RM301.35; Availability: Enquiry [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1" [PP]. No MPN or frequency variant shown.
- Spec list matches [DS] for magnet distance 20–30 mm, 1.5 m cable, T/H ranges and accuracy, Tx power, Class A, IP67, -30 to +70 °C, ER18505 4000 mAh "extendable to 2 batteries" and "10 years (10 min interval + 48 triggers per day)" [PP].
- Description: "upto 5 years with 4000 mAh battery"; Sensirion industrial-grade T/H sensor; 2 km urban / 15 km rural range [PP].
- Copy errors on the page: a feature line "Remotely turn on/off the electrical appliance from your mobile phone", and a storage line naming "EM320-TH" (see *Conflicts*) [PP].
- **Packing list:** "1 x EM300 Magnetic Contact Switch" only [PP]. The [UM] lists device, 2 wall mounting kits, 2 screw caps, quick guide, warranty card, 2 × 3M double-sided tapes, 4 mounting screws.
- **Resources:** EM300-MCS datasheet, EM300 Series user guide, payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download; also links Milesight IoT Cloud [PP].

## Interfaces, terminals and pin mapping
No user wiring: the reed-sensor cable (1.5 m) is part of the device [DS]. Internal power button and LED [UM]:
| Action | LED | Src |
|---|---|---|
| Hold > 3 s | Power on (off → on) / power off (on → off) | [UM] |
| Quick press | Status: light on = device on, off = device off | [UM] |
| Hold > 10 s | Factory reset (blinks quickly) | [UM] |
Power on can also be done from the ToolBox app by NFC [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Quick start:** ToolBox app → read by NFC → tap the power button in the app and touch the phone to the device to power on → write settings [UM].
- **LoRaWAN keys:** a default AppKey is set at the factory (see the user guide; not copied); ask for random keys before purchase if needed. OTAA is required for Milesight IoT Cloud / Development Platform. Set the plan to match the gateway (Cytron: AS923-2 Malaysia); for US915/AU915 with Milesight gateway defaults use channel index 8-15 [UM][PP]. Pair with `milesight-ug65.md` / `milesight-ug56.md` / `milesight-ug67.md`.
- **Magnet install:** align the two magnet parts with their holes facing outward; keep them off or away from iron objects; fix with 3M tape or screws [UM].
- **Transceiver install:** keep away from metal objects and obstacles (radio); two screw holes on a horizontal line, screw caps over the screws; or 3M tape or cable tie to a pole [UM].
- **Battery:** ER18505 Li-SOCl₂ only (no alkaline). Do not fit two cells in the 4000 mAh version or one in the 8000 mAh version (wrong battery %); fit the cell in the upper position to reduce NFC interference [UM].
- **Magnet alarm** repeats per "Alarm Reporting Interval" and "Alarm Reporting Times" until dismissed [UM].
- **Data storage/retransmission:** sync the time first; ToolBox exports the last 14 days as CSV; retransmission (default every 600 s) shortens battery life [UM].
- Payload (little-endian): battery `01 75` (%), temperature `03 67` (INT16/10 °C), humidity `04 68` (UINT8/2 %RH), magnet `06 00` (**00 = close, 01 = open**); historical `20 ce` with timestamp; downlinks on port 85 [UM].

## Power and electrical limits
- 1 × ER18505 Li-SOCl₂ 4000 mAh (8000 mAh two-cell version optional) [DS][UM].
- Over 10 years at SF7, ~3.2–4.5 years at SF10 (10 min interval + 48 triggers/day) [DS].
- -30 to +70 °C, 0–100 % RH, IP67, UV-resistant — suitable for outdoor/harsh sites [DS].

## Software support
- Downlinks: reboot, collect/report intervals, calibration, thresholds, alarm settings, D2D, historical data enquiry [UM].
- Milesight IoT Cloud and Milesight Development Platform [DS].

## Compatibility and accessories
- LoRaWAN gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- 8000 mAh version is a separate Milesight option, not offered on the Cytron page [DS][PP].
- Same EM300 enclosure family: `milesight-em300-th.md`, `milesight-em300-sld.md`, `milesight-em300-zld.md`, `milesight-em300-di.md`.

## Common mistakes / troubleshooting
- **Device seems dead out of the box:** power it on with the ToolBox app (NFC) or hold the internal button > 3 s [UM].
- **Unreliable open/close:** gap over 20–30 mm, misaligned parts, or magnet on an iron door frame [DS][UM].
- **Wrong battery %:** cell count does not match the version [UM].
- **Inverted status:** 00 = close, 01 = open [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [DS] over 10 years only at SF7; ~4.5 / ~3.2 years at SF10 | [PP] "10 years"; [PP]/[UM] text "up to 5 years" | [DS] table wins; quote the SF condition |
| Range | [DS] 10 km line of sight | [PP] 2 km urban / 15 km rural | [DS] wins |
| Packing list | [UM] device, 2 wall kits, 2 screw caps, 2 × 3M tapes, 4 screws, guide, warranty card | [PP] "1 x EM300 Magnetic Contact Switch" | [UM] for contents; confirm with Cytron |
| Remote appliance control | [PP] "Remotely turn on/off the electrical appliance" | [DS] sensor only (D2D controller can trigger agents) | [DS] wins; [PP] line is a copy error |
| Storage text | [PP] "EM320-TH can store up to 2800 sets" | [DS] EM300-MCS stores 2,800 entries | Same figure; [PP] names the wrong model |
| User guide linked | [PP] EM300 Series User Guide | [VEN] EM300-MCS User Guide V2.3 | Use the EM300-MCS guide |

## Needs verification
- Exact contents of Cytron's box (page lists only the device).
- Which frequency build Cytron ships (no MPN; page states AS923-2 / AS923-1).
- "Sensirion" T/H sensor brand [PP only].
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight EM300-MCS Datasheet: https://resource.milesight.com/milesight/iot/document/em300-mcs-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight EM300-MCS User Guide V2.3 (Dec 26, 2024): https://resource.milesight.com/milesight/iot/document/em300-mcs-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight EM300-MCS page: https://www.milesight.com/iot/product/lorawan-sensor/em300-mcs; EM300 Series User Guide (linked by Cytron, not opened): https://resource.milesight.com/milesight/iot/document/em300-series-user-guide-en.pdf
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em300-magnetic-contact-switch (read 2026-10-21).
