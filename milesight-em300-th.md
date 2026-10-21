# Milesight EM300-TH LoRaWAN Temperature and Humidity Sensor — Verified Reference

| | |
|---|---|
| Product code | `EM300-TH` (Milesight model). Cytron code `LR-EM300-TH`, MPN `EM300-TH-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page, EM300-TH datasheet read in full, EM300-TH user guide V2.3 (26 Dec 2024) read for packing, button/LED, reporting interval, installation, battery and uplink sections |
| Primary source | Milesight *EM300-TH Datasheet*, https://resource.milesight.com/milesight/iot/document/em300-th-datasheet-en.pdf (read 2026-10-21; no version printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight EM300-TH datasheet PDF. [UM] = Milesight EM300-TH User Guide V2.3, 26 Dec 2024 (the milesight.com download; Cytron links the general "EM300 Series User Guide", not opened). [PP] = Cytron product page.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless | LoRaWAN®, Milesight D2D; internal antenna | [DS] |
| Frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan (Cytron) | "Support Malaysia AS923-2, Singapore AS923-1"; MPN `EM300-TH-915M` | [PP] |
| Tx power / sensitivity | 16 dBm (868) / 20 dBm (915) / 19 dBm (470); -137 dBm @ 300 bps | [DS] |
| Mode | OTAA/ABP Class A | [DS] |
| Temperature | -30 ~ +70 °C; typ. ±0.6 °C (-30 ~ 0 °C), ±0.3 °C (0 ~ 70 °C); 0.1 °C resolution | [DS] |
| Humidity | 0 ~ 100 % RH; typ. ±3 % (10–90 % RH @ 25 °C), ±5 % (0–10 % and 90–100 % RH @ 25 °C); 0.5 % RH resolution | [DS] |
| LED / button | 1 × LED (internal); 1 × power/reset button (internal) | [DS] |
| Power on/off / configuration | NFC or internal power button / NFC via mobile app, downlink | [DS] |
| Advanced features | Threshold alarm, Milesight D2D controller, data storage (2,800 entries), retransmission, data retrieval | [DS] |
| Power supply | 1 × 4000 mAh ER18505 Li-SOCl₂ (8000 mAh version optional) | [DS] |
| Battery life (10 min, 25 °C, lab) | Over 10 years (SF7, EU868 & US915); around 5.8 years (SF10, EU868); around 4.2 years (SF10, US915) | [DS] |
| Operating temperature / humidity | -30 ~ +70 °C; 0 ~ 100 % non-condensing | [DS] |
| Ingress protection | IP67 (UV-resistant enclosure) | [DS] |
| Housing | ABS + PC (flame retardant), white | [DS] |
| Dimensions / weight | 88.5 × 85.3 × 27 mm; 95.6 g with 1 battery | [DS] |
| Installation | Wall screws, 3M tape, cable tie | [DS] |
| Approvals | CE, FCC, ISED, RCM, Telec, ICASA, EN12830; RoHS | [DS] |
| Reporting interval | 1 – 1080 min, default 10 min | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM300-TH LoRaWAN Temperature and Humidty Sensor" (typo in title); Code `LR-EM300-TH`; MPN `EM300-TH-915M`; warranty 12 months; RM223.85; availability "Enquiry" [PP].
- Description: "can work up to 5 years with 4000 mAh battery"; "1 × ER18505 4000 mAh … more than 5 years"; "Available for over 10 years (Dual Battery Holders, One Battery by Default)"; 2,800 historical records; EN12830 [PP].
- Spec block matches [DS] (20 dBm, ranges/accuracy, IP67, 88.5 × 85.3 × 27 mm) except battery life "10 years (10 min interval)" and "1 × 4000 mAh … (extendable to 2 batteries)"; installation "Wall Mounting" [PP].
- **Packing list:** sensor, 2 × wall mounting kit, 2 × screw caps, quick guide, warranty card [PP] (same as [UM]).
- Resources: EM300-TH datasheet, EM300 Series User Guide (resource.milesight.com), payload decoder, firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No external wiring (hardware 3.x removed the USB port, per [UM] V2.0). Internal **power button and LED** [UM]:
| Action | Function | LED |
|---|---|---|
| Hold > 3 s | Power on / power off | Off → On / On → Off |
| Hold > 10 s | Reset to factory default | Blinks quickly |
| Quick press | Check on/off status | On = on; off = off |

## Rules and gotchas (for code, wiring and tutorials)
- **Battery:** ER18505 Li-SOCl₂ only, no alkaline. Do not put 2 cells in the 4000 mAh version (or 1 in the 8000 mAh version) — battery % would be wrong. Fit the cell in the upper slot to reduce NFC interference [UM].
- **The second battery holder does not double the life of a 4000 mAh unit by itself**: the 8000 mAh is a separate version per Milesight [UM][DS] (see *Conflicts*).
- **Battery life depends on spreading factor:** > 10 years only at SF7; ~4.2 years at SF10 on US915 [DS]. Distant gateways shorten life.
- **Mounting:** away from metal objects; screw holes on a horizontal line; cover screws with caps [UM].
- **Payload** (port 85): battery 01 75; temperature 03 67 INT16/10 °C; humidity 04 68 UINT8/2 %RH; history 20 ce [UM].

## Power and electrical limits
- 1 × 4000 mAh ER18505 Li-SOCl₂ (8000 mAh version optional) [DS].
- -30 ~ +70 °C; 0–100 % RH non-condensing; IP67 [DS].

## Software support
- Milesight IoT Cloud and Development Platform; standard LoRaWAN network servers [DS]. Decoders: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Newer, slimmer, more accurate alternative with food-grade housing: `milesight-em320-th.md`.
- Part of the EM300 family (same housing as `milesight-em300-di.md`).

## Common mistakes / troubleshooting
- **Battery % wrong after replacement:** cell count does not match the version, or old cells [UM].
- **NFC read fails:** battery in the lower slot; phone case on [UM].
- **Short battery life:** high SF (far from gateway) or short interval [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [PP] "up to 5 years" (description) and "10 years (10 min interval)" (spec) | [DS] > 10 years at SF7; ~5.8 years SF10 EU868; ~4.2 years SF10 US915 | [DS] wins; life depends on SF. Lab figures only |
| Second battery | [PP] "extendable to 2 batteries" / "Dual Battery Holders, One Battery by Default" | [UM] 4000 mAh and 8000 mAh are separate versions; do not add a second cell to the 4000 mAh version | [UM] wins: do not add a cell to the 4000 mAh unit |
| Humidity range wording | [PP] 0–100 % non-condensing | [DS] same | Consistent |

## Needs verification
- Whether Cytron's units are the 4000 mAh version (assumed from the Cytron spec).
- AS923 sub-plan shipped for Malaysia.
- Content of the "EM300 Series User Guide" linked by Cytron (not opened; the model-specific V2.3 guide was read).

## Sources
- [DS] EM300-TH Datasheet: https://resource.milesight.com/milesight/iot/document/em300-th-datasheet-en.pdf (read 2026-10-21).
- [UM] EM300-TH User Guide V2.3 (26 Dec 2024): https://resource.milesight.com/milesight/iot/document/em300-th-user-guide-en.pdf
- [PP] Cytron-linked user guide (not opened): https://resource.milesight.com/milesight/iot/document/em300-series-user-guide-en.pdf
- [VEN] Milesight EM300-TH product page: https://www.milesight.com/iot/product/lorawan-sensor/em300-th
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em300-th-lorawan-temperature-and-humidty-sensor (read 2026-10-21).
