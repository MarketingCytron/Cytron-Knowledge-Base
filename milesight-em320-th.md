# Milesight EM320-TH LoRaWAN Temperature and Humidity Sensor — Verified Reference

| | |
|---|---|
| Product code | `EM320-TH` (Milesight model). Cytron parent code `V-LR-EM320-TH`; Standard version `LR-EM320-TH` (MPN `EM320-TH-915M`); Magnetic version `LR-EM320-TH-MG` (no MPN shown) [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both versions: code, MPN, price, stock, spec, tutorials), EM320-TH datasheet read in full, EM320-TH user guide V1.2 (1 Jun 2023) read for safety, packing, button/LED, NFC quick start, installation, battery and uplink sections |
| Primary source | Milesight *EM320-TH Datasheet*, https://resource.milesight.com/milesight/iot/document/em320-th-datasheet-en.pdf (read 2026-10-21; no version printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight EM320-TH datasheet PDF. [UM] = Milesight EM320-TH User Guide V1.2, 1 Jun 2023. [PP] = Cytron product page. [PP: tutorial] = Cytron tutorials linked from the product page.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless | LoRaWAN®, OTAA/ABP Class A | [DS] |
| Frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan (Cytron) | "Support Malaysia AS923-2, Singapore AS923-1"; MPN `EM320-TH-915M` | [PP] |
| Tx power | 16 dBm (868) / 22 dBm (915) / 19 dBm (470) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Temperature range | -30 ~ +60 °C | [DS] |
| Temperature accuracy | Typ. ±0.3 °C (-30 ~ 0 °C), ±0.2 °C (0 ~ 60 °C); 0.1 °C resolution | [DS] |
| Humidity | 0 ~ 100 % RH; typ. ±2 % (25 °C); 0.5 % RH resolution | [DS] |
| Sensor | Sensirion high-precision sensor ([PP]: SHT41) | [DS][PP] |
| Power on/off | Mobile app via NFC; internal power button | [DS] |
| Configuration | Mobile app via NFC | [DS] |
| Advanced features | Threshold alarm, data storage (3,000 records), retransmission, data retrieval | [DS] |
| Power supply | 2 × 2700 mAh ER14505 Li-SOCl₂ batteries (5400 mAh total) | [DS] |
| Battery life | ≥ 10 years (10 min interval, 25 °C; lab figure). The same datasheet's intro says "up to 5 years" (see *Conflicts*) | [DS] |
| Operating temperature / humidity | -30 ~ +60 °C; ≤ 95 % | [DS] |
| Ingress protection | IP67 | [DS] |
| Housing | PC + ABS (food grade), white; FDA-approved food-contact material | [DS] |
| Dimensions / weight | 85 × 58 × 18 mm; 93.2 g (Standard), 102 g (Magnet) | [DS] |
| Installation | Standard: wall or pole mounting. Magnet: magnetic adsorption | [DS] |
| Approvals | CE, FCC, Telec, EN12830; RoHS | [DS] |
| Reporting interval | 1 – 1080 min, default 10 min | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM320 LoRaWAN Temperature and Humidity Sensor"; parent code `V-LR-EM320-TH`; warranty 12 months; RM241.10; cashback RM7.23; availability 96; ADD TO CART [PP].
- Versions: Standard `LR-EM320-TH` / `EM320-TH-915M`, 38 in stock (URL …/p-em320-temperature-and-humidity-sensor-wall-mounting); Magnetic `LR-EM320-TH-MG`, 58 in stock (URL …/p-em320-lorawan-temperature-and-humidity-sensor-magnet); same price [PP].
- Sensor named as Sensirion SHT41; "store up to 3000 sets of historical data" [PP].
- Spec block: temperature accuracy "+/- 0.2 °C" (single value), humidity ±2 %; **Tx power 20 dBm (915)**; **battery life "Over 10 years" and "10 min interval, 25 °C: Around 6.3 Years"** (see *Conflicts*) [PP].
- **Packing list:** 1 × EM320 Temperature and Humidity Sensor [PP] (the [UM] also lists quick guide, warranty card, and for the Standard version 2 × wall mounting kits, 1 × fixing screw, 1 × pole mounting plate).
- Resources: EM320-TH datasheet and user guide (resource.milesight.com), payload decoder, firmware & SDK download, Milesight IoT Cloud [PP].
- Related tutorials listed (see *Cytron tutorials*) [PP].

## Interfaces, terminals and pin mapping
No external wiring. Internal **power button and LED** (inside the housing) [UM]:
| Action | Function | LED |
|---|---|---|
| Hold > 3 s | Power on / power off | Off → On / On → Off |
| Hold > 10 s | Reset to factory default | Blinks quickly |
| Quick press | Check on/off status | On = on; off = off |
NFC area on the housing for ToolBox read/write [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Vent must not face upwards** when mounting (wall, pole or magnet) [UM].
- **Magnetic version + NFC:** take the sensor off the metal surface and hold the phone about 10 mm from the NFC area to read it [UM].
- **NFC tips:** remove the phone case; if read/write fails, move the phone away and retry; after Write, re-read to confirm [UM].
- **Battery: ER14505 Li-SOCl₂ only**, no alkaline; replace both with new cells; remove cells for long storage; open via screws behind the rubber feet [UM].
- **Frequency plan must match the gateway**; with Milesight gateways on US915/AU915 defaults use channel index 8-15 [UM].
- **Payload** (port 85): battery 01 75 (%); temperature 03 67 INT16 ×0.1 °C; humidity 04 68 UINT8 ×0.5 %RH; history 20 ce (timestamp + T + RH). Low-battery alarm at 1 % [UM].
- Not a reference instrument (Milesight disclaimer) [UM].

## Power and electrical limits
- 2 × 2700 mAh ER14505 Li-SOCl₂ [DS]; battery life is a lab guideline figure [DS].
- -30 ~ +60 °C, ≤ 95 % RH, IP67 [DS].

## Software support
- Milesight IoT Cloud and Development Platform (OTAA required); standard LoRaWAN network servers [DS][UM]. Decoders: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway on the same plan, e.g. `milesight-ug65.md` (used in Cytron's tutorial), `milesight-ug56.md`, `milesight-ug67.md`.
- Older/related model: `milesight-em300-th.md` (larger EM300 housing).
- Spare cells: ER14505 Li-SOCl₂ (not sold on this page).

## Common mistakes / troubleshooting
- **NFC will not read (Magnetic version):** remove from the metal surface first [UM].
- **No uplinks:** device still off (power on via NFC or hold the internal button > 3 s), or plan mismatch [UM].
- **Condensation/water ingress:** vent facing upwards [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Tx power at 915 MHz | [PP] 20 dBm | [DS] 22 dBm | [DS] wins: 22 dBm |
| Battery life | [PP] "Over 10 years" and "10 min interval, 25 °C: Around 6.3 Years" | [DS] spec ≥ 10 years at 10 min, 25 °C (DS intro says "up to 5 years") | [DS] spec table wins: ≥ 10 years (lab). Battery-life figures are inconsistent across Milesight and Cytron text; treat as guideline only |
| Temperature accuracy | [PP] ±0.2 °C | [DS] ±0.2 °C (0–60 °C), ±0.3 °C (-30–0 °C) | [DS] wins (full range split) |
| Packing list | [PP] sensor only | [UM] adds quick guide, warranty card and (Standard) wall kits, fixing screw, pole plate | [UM] for box contents; Cytron list is abbreviated |

## Needs verification
- MPN of the Magnetic version (not shown on the Cytron page).
- AS923 sub-plan shipped for Malaysia.
- Exact battery life at Cytron's typical interval (sources disagree: 5, 6.3, ≥10 years).

## Cytron tutorials
Add-on: Cytron tutorials that use this product. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [How to connect Milesight Sensor and Gateway to Milesight Cloud](https://my.cytron.io/tutorial/how-to-connect-milesight-sensor-and-gateway-to-mil) — Ebi Syakirin Aznan, 2 May 2025 (EM320 with UG65) [PP: tutorial]
- [Milesight IoT System Deployment and Custom Website Integration Guide](https://my.cytron.io/tutorial/milesight-iot-system-deployment-and-custom-website-integration-guide) — Hadrie Hakimi, 30 Jul 2026 [PP: tutorial]
- [Milesight-BeaverIoT Quick Start Guide](https://my.cytron.io/tutorial/milesight-beaveriot-quick-start-guide-smarthub) — Hadrie Hakimi, 9 Jul 2026 [PP: tutorial]

## Sources
- [DS] EM320-TH Datasheet: https://resource.milesight.com/milesight/iot/document/em320-th-datasheet-en.pdf (read 2026-10-21).
- [UM] EM320-TH User Guide V1.2 (1 Jun 2023): https://resource.milesight.com/milesight/iot/document/em320-th-user-guide-en.pdf
- [VEN] Milesight EM320-TH product page: https://www.milesight.com/iot/product/lorawan-sensor/em320-th
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em320-lorawan-temperature-and-humidity-sensor (read 2026-10-21).
