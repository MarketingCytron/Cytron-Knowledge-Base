# Milesight EM500-CO2 — Verified Reference

| | |
|---|---|
| Product code | `EM500-CO2` (Milesight model). Cytron code `LR-EM500-CO2`, MPN shown as `EM500-CO2-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight product page (download links), EM500-CO2 datasheet (full) and EM500-CO2 user guide V2.2.1 (power button, general settings, CO2/T/H/P calibration, threshold, installation, battery replacing, uplink) read |
| Primary source | *EM500-CO2 Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em500-co2-datasheet-en.pdf (no version/date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = EM500-CO2 datasheet PDF. [UM] = *EM500-CO2 User Guide* V2.2.1 (15 Aug 2024; V1.0 23 Nov 2020; V2.0 11 Apr 2022 hardware v2.x; V2.1 31 May 2023 added CO2 barometric-pressure compensation and the installation guide; V2.2 29 Mar 2024), https://resource.milesight.com/milesight/iot/document/em500-co2-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em500-co2. [PP] = Cytron product page (links the generic EM500 series user guide).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| CO2 | NDIR; 400 – 5000 ppm; ± (30 ppm + 3 % of reading) (0 – 50 °C, 0 – 85 % RH); resolution 1 ppm | [DS] |
| Temperature | MEMS; -30 °C to +70 °C; ± 0.3 °C (0 – 70 °C), ± 0.6 °C (-30 – 0 °C); resolution 0.1 °C | [DS] |
| Humidity | MEMS; 0 – 100 % RH; ± 3 % (10 – 90 % RH), ± 5 % (below 10 % / above 90 %); resolution 0.5 % RH | [DS] |
| Barometric pressure | MEMS; 300 – 1100 hPa (-40 – 85 °C); ± 1 hPa; resolution 0.1 hPa | [DS] |
| Probe / cable | None — sensors are inside the one-piece enclosure (no cable or probe listed) | [DS] |
| Wireless | LoRaWAN; internal antenna | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868) / 20 dBm (915) / 19 dBm (470) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP, Class A; port 85 | [DS][UM] |
| LED / button / USB | 1 × LED (internal); 1 × power/reset button (internal); 1 × USB Type-C (internal) for configuration and console | [DS] |
| Configuration | Mobile app (NFC), PC software (USB Type-C), downlink | [DS] |
| Advanced features | Data storage (1,000 entries), data retransmission, data retrievability, threshold alarm, calibration | [DS] |
| Power supply | 1 × 19000 mAh ER34615 Li-SOCl2 battery | [DS] |
| Battery life | 10 years (10 min interval, 25 °C; lab figure) | [DS] |
| Operating temperature | -30 °C to +70 °C | [DS] |
| Relative humidity | 0 % to 95 % (non-condensing) | [DS] |
| Ingress protection | IP65 | [DS] |
| Housing | ABS + PC, grey | [DS] |
| Weight | 434.7 g (with battery and mounting bracket) | [DS] |
| Dimension | 147.9 × 71 × 69.5 mm | [DS] |
| Installation | Pole, wall or DIN-rail mounting | [DS] |
| Approvals | CE, FCC, LoRaWAN Certified, ISED, ICASA, Telec; EMC EN 55032/55035; EMS IEC 61000-4-2 L3, -4-3 L2, -4-8 L4; RF FCC Part 15B/15.247, EN 300 330, EN 301 489-1/3, EN 300 220-1/2; safety EN62368-1; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM500-CO2 LoRaWAN Carbon Dioxide Sensor (4 in 1)"; brand Milesight; Code `LR-EM500-CO2`; MPN `EM500-CO2-915M`; warranty 12 months; RM1,033.20; availability "Enquiry" with INQUIRE NOW [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"; Tx Power "0dBm(915)"** (see *Conflicts*) [PP].
- The rest of the spec section matches [DS]: NDIR 400–5000 ppm ± (30 ppm + 3 %), MEMS T/H/P ranges and accuracies, internal LED/button/USB-C, data storage 1000 entries, calibration, ER34615 19000 mAh, 10 years, -30 ~ +70 °C, 0–95 % RH, IP65, 434.7 g, 147.9 × 71 × 69.5 mm, pole/wall/DIN rail, approvals [PP].
- Description: greenhouse, building ventilation, fruit/vegetable storage; application examples smart wine cellar (CO2 pooling at floor level) and forest-fire detection; Milesight IoT Cloud; "2 km urban / 15 km rural" range; features list "up to 10 km" line of sight and "P65 waterproof enclosure" (typo for IP65) [PP].
- **Packing list:** 1 × EM500-CO2 LoRaWAN Carbon Dioxide Sensor (4 in 1) [PP].
- **Resources:** EM500-CO2 datasheet, EM500 Series User Guide (generic), Payload Decoder, firmware download [PP].

## Interfaces, terminals and pin mapping
No terminals, probes or cables: all four sensors are built in [DS]. Inside the enclosure: power button, LED, USB Type-C for ToolBox PC software/console; NFC for the app [DS][UM].

**Power button (internal)** [UM]: hold > 3 s on/off; hold > 10 s factory reset (LED blinks quickly); quick press shows status.

**Uplink** [UM ch. 7] (little-endian): 01 75 battery %; **03 67 temperature INT16/10 °C; 04 68 humidity UINT8/2 %RH; 05 7d CO2 UINT16 ppm; 06 73 barometric pressure UINT16/10 hPa**; 83 d7 temperature mutation alarm; 20 ce historical data (timestamp + CO2 + pressure + temperature + humidity). Read failure = all ff. Downlink port 85 [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Mount low:** no higher than **12–18 inches (about 30–45 cm) above the floor**, because CO2 is heavier than air and flows down [UM ch. 5].
- **Enclosed or varied spaces need extra sensors** [UM].
- **CO2 calibration — choose one:** *Manual*: place the unit in open outdoor air for more than 10 minutes, then press Calibrate (sets the current reading to 400 ppm by default); best when the sensor will live in an unventilated space, so calibrate before installing. *Auto Background*: over 168 h (7 days) the unit takes the lowest CO2 level as 400 ppm; suits well- or semi-ventilated areas. *Restore factory calibration* clears manual calibration. Numerical offset calibration is also available [UM].
- **Barometric pressure compensation** for CO2 can be enabled; it needs the pressure sensor enabled [UM].
- **Temperature unit:** uplinks are fixed in °C [UM].
- **Default reporting interval 10 min** (1–1080 min) [UM].
- **Mounting:** wall, pole (hose clamp) or 35 mm DIN rail (clip with 2 × M3 × 6 screws); keep away from metal [UM].
- **IP65, not IP67** like most EM500 transceivers — keep it out of direct water jets/immersion (inferred from [DS] IP65).
- **Frequency plan:** Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].

## Power and electrical limits
- One ER34615 Li-SOCl2 19000 mAh battery; alkaline not supported; replace via the bottom cover with a new battery [UM ch. 6].
- 10 years at 10-min interval, 25 °C (lab) [DS].
- -30 ~ +70 °C, 0–95 % RH non-condensing; CO2 accuracy specified only for 0–50 °C, 0–85 % RH [DS].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB-C) [UM].
- Standard LoRaWAN gateways/network servers; Milesight IoT Cloud and Development Platform [DS][PP].
- Decoders: github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Indoor air quality alternative: `milesight-iaq-sensor.md`; kit context: `milesight-smart-agriculture-kit.md`, `milesight-iaq-kit.md`.
- Same EM500 family: `milesight-em500-pp.md`, `milesight-em500-pt100.md`, `milesight-em500-smtc.md`, `milesight-em500-udl.md`.

## Common mistakes / troubleshooting
- **CO2 drifts high or low:** not calibrated for the site; run Manual calibration outdoors before installing in a closed room, or enable Auto Background in ventilated areas [UM].
- **CO2 alarm misses floor-level build-up:** sensor mounted too high [UM].
- **Readings all ff:** sensor read failure [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Tx power | [DS] 16 dBm (868) / 20 dBm (915) / 19 dBm (470) | [PP] "Tx Power: 0dBm(915)" | [DS] wins: 20 dBm at 915 MHz. Cytron page typo |
| Enclosure rating | [DS] IP65 | [PP] features "P65" | Typo; IP65 |
| Frequency plans | [DS] CN470…AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M) | Not a contradiction |
| User guide | [VEN] EM500-CO2 user guide | [PP] generic EM500 series user guide | Use [UM] |
| Availability | Brand listing card: OUT OF STOCK | Product page "Enquiry" / INQUIRE NOW | Treated as out of stock |

## Needs verification
- Whether Cytron's box includes the EM500 mounting kit (bracket is included in the weight; other items not listed by Cytron).
- NDIR sensor lifetime / recalibration interval (not stated).
- `-915M` suffix (inferred 915 MHz-band hardware) and Malaysia AS923 sub-plan.

## Sources
- [DS] EM500-CO2 Datasheet: https://resource.milesight.com/milesight/iot/document/em500-co2-datasheet-en.pdf (read 2026-10-21)
- [UM] EM500-CO2 User Guide V2.2.1: https://resource.milesight.com/milesight/iot/document/em500-co2-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em500-co2
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em500-co2-lorawan-carbon-dioxide-sensor-4-in-1 (read 2026-10-21)
