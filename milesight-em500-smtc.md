# Milesight EM500-SMTC — Verified Reference

| | |
|---|---|
| Product code | `EM500-SMTC` (Milesight model). Cytron code `LR-EM500-SMTC`, MPN shown as `EM500-SMTC-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight product page (download links), EM500-SMTC datasheet (full) and EM500-SMTC user guide V2.3 (terminal-block pinout, power button, sensor assembly, general/threshold settings, soil-sensor installation, battery, uplink) read |
| Primary source | *EM500-SMTC Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em500-smtc-datasheet-en.pdf (no version/date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = EM500-SMTC datasheet PDF. [UM] = *EM500-SMTC User Guide* V2.3 (27 Nov 2024; V1.0 23 Nov 2020; V2.0 11 Apr 2022 hardware v2.x with soil type selection; V2.1 31 May 2023; V2.2 29 Mar 2024; V2.2.1 15 Aug 2024), https://resource.milesight.com/milesight/iot/document/em500-smtc-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em500-smtc. [PP] = Cytron product page (links the generic EM500 series user guide).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Soil moisture | 0 % ~ 100 %; accuracy ± 2 % (0–50 %), ± 3 % (50–100 %); resolution 0.01 % | [DS] |
| Soil temperature | -40 °C ~ 80 °C; accuracy ± 0.5 °C; resolution 0.1 °C | [DS] |
| Electrical conductivity | 0 ~ 20000 µS/cm; accuracy ± 3 % (0–10000), ± 5 % (10000–20000 µS/cm); resolution 10 µS/cm (0–10000), 50 µS/cm (10000–20000) | [DS] |
| Probe | Soil sensor 88 × 68 × 26 mm, probe (prong) length 50 mm; epoxy resin + stainless steel, white + silver; 138 g with cable; IP68; buried installation | [DS] |
| Cable length | 2 m | [DS] |
| Wireless | LoRaWAN, Milesight D2D; internal antenna | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP, Class A; port 85 | [DS][UM] |
| LED / button / USB | 1 × LED (internal); 1 × power/reset button (internal); 1 × USB Type-C (internal) for configuration and console | [DS] |
| Configuration | Mobile app (NFC), PC software (USB Type-C), downlink | [DS] |
| Advanced features | Data storage (1,000 entries), data retransmission, data retrievability, threshold alarm, temperature change alarm, Milesight D2D controller (soil-moisture threshold alarm added in [UM] V2.3) | [DS][UM] |
| Power supply | 1 × 19000 mAh ER34615 Li-SOCl2 battery | [DS] |
| Battery life (10 min interval, 25 °C) | Up to 10 years (SF7 & SF10, EU868); up to 10 years (SF7, US915); around 8 years (SF10, US915) — lab figures | [DS] |
| Operating temperature | -30 °C ~ 70 °C | [DS] |
| Relative humidity | 0 % to 100 % (non-condensing) | [DS] |
| Ingress protection | Transceiver IP67; soil sensor IP68 | [DS] |
| Transceiver | ABS + PC, grey; 105.4 × 71 × 69.5 mm; 328 g with battery and bracket; pole, wall or DIN-rail mounting | [DS] |
| Approvals | CE, FCC, ISED, ICASA, Telec; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM500-SMTC LoRaWAN Soil Moisture, Temperature and EC Sensor"; brand Milesight; Code `LR-EM500-SMTC`; MPN `EM500-SMTC-915M`; warranty 12 months; RM2,135.30; availability "Enquiry" with INQUIRE NOW [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"** [PP].
- Spec: moisture 0–100 % (±2 % / ±3 %), temperature -40 ~ +80 °C (±0.5 °C), EC 0–20000 µS/cm, LoRaWAN, **"4000 mAh Li-SOCL2 battery"**, up to 10 years, 2 m cable, IP67 (transceiver) & IP68 (soil sensor), -30 ~ +70 °C, transceiver 105.4 × 71 × 69.5 mm, soil sensor 88 × 68 × 26 mm [PP].
- Features text says **"IP66-rated enclosure"** [PP] (see *Conflicts*).
- **Packing list:** 1 × EM500-SMTC [PP]. Milesight's EM500 box: device with bracket, wall mounting kits, screw caps, fixing screws, hose clamp, DIN rail clip kit (optional), quick guide, warranty card [UM].
- **Resources:** EM500-SMTC datasheet, EM500 Series User Guide (generic), Payload Decoder, firmware and SDK download [PP].

## Interfaces, terminals and pin mapping
**Sensor terminal block (inside the transceiver)** [UM §3 Hardware Overview]
| Pin | Wire / signal |
|---|---|
| 1 | Black / GND |
| 2 | — |
| 3 | — |
| 4 | White / B |
| 5 | Yellow / A |
| 6 | Red / VOUT = 12 V (probe supply) |

- The probe is a digital A/B (RS485-style) sensor powered at 12 V from the transceiver (bus type inferred from the A/B labels; [UM] does not name the protocol) [UM].
- **The probe's green wire is not used — cut it off or insulate it** [UM ch. 4].
- Wires enter through the waterproof cable gland in the bottom cover [UM].

**Power button (internal)** [UM]: hold > 3 s on/off; hold > 10 s factory reset (LED blinks quickly); quick press shows status.

**Uplink** [UM ch. 8] (little-endian): 01 75 battery %; **03 67 temperature INT16/10 °C; 04 ca soil moisture UINT16/100 %; 05 7f conductivity UINT16 µS/cm**; 83 d7 temperature mutation alarm; 20 ce historical data (timestamp + EC + temperature + moisture). Read failure = all ff. Downlink port 85 [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Sensor assembly:** remove bracket and bottom cover, feed wires through the gland, screw to the terminal block (1 black GND, 4 white B, 5 yellow A, 6 red 12 V), insulate the green wire, refit with the **red arrow to the front**, and fit the rubber seal and screw caps [UM ch. 4].
- **Site choice:** representative soil type, terrain and yield; away from field edges and large metal objects; check lightning protection; use two or more sensors at different depths for deep-rooted crops [UM ch. 6].
- **Horizontal install:** dig a trench a few cm deeper than the target depth, shave to undisturbed soil, push the prongs fully in, backfill to natural density [UM].
- **Vertical install:** drill to depth, push the sensor into undisturbed soil at the bottom, backfill without damaging the over-moulding or cable [UM].
- **Prongs must be fully in the soil** (air exposure gives abnormal data); avoid sticks, roots, air gaps and over-compaction; wet or loosen hard soil; **no sideways force** (prongs break); prong tips are sharp [UM].
- **Never pull the sensor out by its cable** — it can break internal connections [UM].
- **Units:** uplink temperature is fixed in °C [UM].
- **Default reporting interval 10 min** (1–1080 min); collect interval should be less than reporting interval [UM].
- **Frequency plan:** Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].

## Power and electrical limits
- One ER34615 Li-SOCl2 19000 mAh battery (not 4000 mAh — see *Conflicts*); alkaline not supported [DS][UM].
- The transceiver supplies 12 V to the probe on pin 6 [UM].
- Battery life depends on spreading factor: up to 10 years at SF7/SF10 EU868 or SF7 US915; about 8 years at SF10 US915 (10-min interval, 25 °C) [DS].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB-C) [UM].
- Standard LoRaWAN gateways/network servers; Milesight IoT Cloud and Development Platform (OTAA) [DS][UM].
- Decoders: github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Same EM500 transceiver family: `milesight-em500-pp.md`, `milesight-em500-pt100.md`, `milesight-em500-udl.md`, `milesight-em500-co2.md`.
- Valve control for irrigation: `milesight-uc512.md`; kit context: `milesight-smart-agriculture-kit.md`.

## Common mistakes / troubleshooting
- **Abnormal moisture/EC values:** prongs partly in air, air gaps, roots or stones between prongs, or over-compacted backfill [UM].
- **Readings all ff:** probe wiring wrong (A/B swapped, 12 V not on pin 6) or loose [UM].
- **Water in the transceiver:** seal or screw caps missing, cover misaligned [UM].
- **Broken sensor after removal:** pulled out by the cable [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery capacity | [DS] 1 × 19000 mAh ER34615 Li-SOCl2 | [PP] spec "4000 mAh Li-SOCL2 battery" | [DS] wins: 19000 mAh ER34615. Cytron page should be corrected |
| Enclosure rating | [DS] transceiver IP67, soil sensor IP68 | [PP] features text "IP66-rated enclosure" (its spec section says IP67/IP68) | [DS] wins |
| Frequency plans | [DS] CN470…AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M) | Not a contradiction |
| User guide | [VEN] EM500-SMTC user guide | [PP] generic EM500 series user guide | Use [UM] |
| Availability | Brand listing card: OUT OF STOCK | Product page "Enquiry" / INQUIRE NOW | Treated as out of stock |

## Needs verification
- The soil-type selection setting added in [UM] V2.0 (options and where it is set) — not found in the settings text read.
- Probe bus protocol (RS485/Modbus inferred from A/B labels).
- Whether the box includes the mounting kit and DIN clip.
- `-915M` suffix (inferred 915 MHz-band hardware) and Malaysia AS923 sub-plan.

## Sources
- [DS] EM500-SMTC Datasheet: https://resource.milesight.com/milesight/iot/document/em500-smtc-datasheet-en.pdf (read 2026-10-21)
- [UM] EM500-SMTC User Guide V2.3: https://resource.milesight.com/milesight/iot/document/em500-smtc-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em500-smtc
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em500-smtc-soil-moisture-temperature-and-ec-sensor (read 2026-10-21)
