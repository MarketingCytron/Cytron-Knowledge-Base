# Milesight EM300-ZLD — Verified Reference

| | |
|---|---|
| Product code | `EM300-ZLD` (Milesight model). Cytron code `LR-EM300-ZLD`, MPN shown as `EM300-ZLD-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources, FAQ), Milesight EM300-SLD/ZLD product page (specification tab, documents), EM300-ZLD datasheet (full, 4 pages), EM300-ZLD user guide V2.3 (hardware, quick start, settings, installation, battery, uplink sections), EM300 series user guide V2.5 (applicability, packing list, settings) and the *Water Leakage Detection Sensor Installation Guide* (full) read |
| Primary source | *EM300-ZLD Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em300-zld-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
Sibling: `milesight-em300-sld.md` (EM300-SLD) is the spot version with a two-pin probe on 1.5 m of cable [DS: web].

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless technology | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan sold by Cytron | "Support Malaysia AS923-2, Singapore AS923-1" (MPN EM300-ZLD-915M) | [PP] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A (fixed); V1.0.2 / V1.0.3 | [DS][UM] |
| Leak detection | Conducting liquid; triggers when liquid level reaches 5 mm | [DS] |
| Sensing cable | 3 m (customisable); PE + steel wire, yellow & black; one connector end | [DS][UM] |
| Wetting needed to trigger | Soaking length ≥ 3 cm and depth ≥ 1 mm on the cable | [UM][VEN: install] |
| Temperature | -30 °C to +70 °C; ±0.3 °C (0 to +70 °C), ±0.6 °C (-30 to 0 °C); 0.1 °C | [DS] |
| Humidity | 0–100 %RH; ±3 % (10–90 %RH), ±5 % otherwise; 0.5 %RH | [DS] |
| LED / button | 1 × LED (internal), 1 × power/reset button (internal) | [DS] |
| Power on/off; configuration | NFC, internal button; NFC via mobile app, downlink | [DS] |
| Advanced features | Threshold alarm, D2D controller, data storage (2,800 entries), retransmission, retrievability | [DS] |
| Power supply | 1 × 4000 mAh ER18505 Li-SOCl2 (8000 mAh version optional) | [DS] |
| Battery life (10 min + 24 triggers/day, lab) | Over 10 years (SF7, EU868 & US915); ~5.6 years (SF10, EU868); ~4.1 years (SF10, US915) | [DS] |
| Operating temperature / humidity | -30 °C to +70 °C; 0–100 % non-condensing | [DS] |
| Ingress protection | IP67 | [DS] |
| Housing | ABS + PC (flame retardant), white | [DS] |
| Dimensions | 105.6 × 85.3 × 27 mm (transceiver) | [DS] |
| Installation | Transceiver: wall screw, 3M tape, cable tie; cable: 3M tape, cable tie | [DS] |
| Approvals | CE, FCC, ISED, RCM, Telec, ICASA; RoHS | [DS] |
| Default reporting interval | 10 min (1–1080 min) | [UM] |
| In the box (Milesight) | 1 × EM300-ZLD (sensing cable included), 2 × wall mounting kits, 2 × screw caps, 1 × quick guide, 1 × warranty card | [UM] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM300-ZLD LoRaWAN Zone Leak Detection Sensor"; brand Milesight; Code `LR-EM300-ZLD`; MPN `EM300-ZLD-915M`; RM413.30; availability "Enquiry" with INQUIRE NOW (no Add to Cart). **No warranty line** in the header or description [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"**; Tx power listed only as 20 dBm (915) [PP].
- Spec block: technology listed as "LoRaWAN®" only; detection cable 3 m; T/H as [DS]; configuration "NFC Configuration via Mobile App"; power "1 × 4000mAh ER18505 Li-SOCL2 battery (extendable to 2 batteries)"; battery life "10 years (10 min interval + 24 triggers per day)"; IP67; 105.6 × 85.3 × 27 mm; installation "Wall Mounting" [PP].
- Description (older Milesight copy) says "up to 5 years with a 4000mAh battery", 2 km urban / 15 km rural range, 2,800 records; the features list says "more than 5 years" and "3,000 historical records" [PP] — see Conflicts.
- **Packing list:** 1 × EM300-ZLD LoRaWAN Zone Leak Detection Device with Sensor, 1 × wall mounting kit, 1 × quick guide, 1 × warranty card [PP].
- **Resources:** EM300-ZLD datasheet, **EM300 Series User Guide** (not the ZLD-specific guide), Water Leakage Detection Sensor Installation Guide, Payload Decoder (GitHub), Firmware & SDK download; link to Milesight IoT Cloud [PP].
- **FAQ on the page:** cannot detect diesel or oil (non-conductive); detects water, weak acid and weak base liquids; cable installed by wrapping a column or with cable ties; cable length can be customised [PP].

## Interfaces, terminals and pin mapping
No user wiring. The sensing cable has one connector that screws onto the EM300-ZLD connector; tighten it. The supplied cable cannot be daisy-chained — for more length, order a custom length or a cable with connectors on both ends to replace the default one [UM][VEN: install].

**Internal power button and LED** [UM]: power on/off = hold > 3 s (LED off→on / on→off); reset to factory default = hold > 10 s (LED blinks quickly); short press shows on/off status.

**Uplink payload (port 85)** [UM]: battery 01 75 (UINT8 %); temperature 03 67 (INT16/10 °C); humidity 04 68 (UINT8/2 %RH); water leakage 05 00 (00 = not leak, 01 = leaked); historical data 20 ce (8 bytes). Decoders: https://github.com/Milesight-IoT/SensorDecoders.

## Rules and gotchas (for code, wiring and tutorials)
- **Zone, not location:** the rope tells you *that* a leak happened along its 3 m, not *where* [UM].
- **Conductive liquids only:** water, weak acid, weak base. Not diesel, oil, fuel, solvents or strong acids [PP FAQ][VEN: install].
- **Keep the connectors dry** and keep the cable away from air-conditioning outlets or damp spots — both cause false alarms [UM].
- **Fixing:** attach flat to floors/walls with cable clips, or wrap around pipes with cable ties; do not use glue or metal fixings, do not coil or bunch the cable [UM].
- **After a leak:** dry the cable and confirm the status returns to "No Leak"; clean with alcohol or soapy water after removing it from the connector [UM].
- **Frequency plan:** Cytron's 915M unit is stated for AS923-2 (Malaysia) / AS923-1 (Singapore); match the gateway [PP][UM].
- Battery: ER18505 Li-SOCl2 only; correct cell count for the 4000/8000 mAh version [UM].

## Power and electrical limits
- 1 × 4000 mAh ER18505 Li-SOCl2 (8000 mAh two-cell version optional); no external power [DS][UM].
- Battery life over 10 years at SF7 (10 min interval + 24 triggers/day, lab), ~4.1–5.6 years at SF10 [DS].
- -30 °C to +70 °C operating [DS].

## Software support
- Milesight ToolBox app over NFC: LoRaWAN settings, reporting interval, temperature threshold, leak alarm interval/times, calibration, D2D controller, storage/retransmission, backup/restore, reset, upgrade (Android) [UM].
- LoRaWAN OTAA/ABP Class A; OTAA needed for Milesight IoT Cloud / Development Platform [UM].
- D2D controller: sends 2-byte commands to D2D agents on threshold or leak/no-leak events [UM].
- Historical data: 2,800 records, retransmission, enquiry by downlink [DS][UM].

## Compatibility and accessories
- LoRaWAN gateway/network server on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [VEN].
- Spot version: `milesight-em300-sld.md`. Milesight related products named on its page: WS303 (not in KB), UC300 (`milesight-uc300.md`), UG65 [VEN].
- Custom cable length; double-ended replacement cable; 8000 mAh version — through Milesight [DS][UM].

## Common mistakes / troubleshooting
- **Constant leak alarm:** wet connector, cable near an AC outlet or damp area, or cable not dried after a test [UM].
- **No alarm on a small spill:** less than 3 cm of cable wet, or depth under 1 mm [UM].
- **No join:** plan/sub-band mismatch; OTAA keys not on the network server [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [DS] over 10 years (SF7), ~5.6 / ~4.1 years at SF10; [PP] spec "10 years" | [UM] "up to 5 years"; [PP] description "up to 5 years", features "more than 5 years" | [DS] wins, quote with test conditions |
| Stored records | [DS][UM] 2,800 entries; [PP] description 2,800 | [PP] features "3, 000 historical records" | [DS]: 2,800 |
| Technology | [DS] LoRaWAN®, Milesight D2D | [PP] spec "LoRaWAN®" only (D2D in description) | [DS]: D2D supported |
| Packing list | [UM] device with cable, **2** wall mounting kits, **2 screw caps**, quick guide, warranty card | [PP] device with sensor, **1** wall mounting kit, quick guide, warranty card | [UM] for Milesight's box; confirm Cytron's box contents |
| Battery count | [DS] 1 × 4000 mAh (8000 mAh version optional) | [PP] "(extendable to 2 batteries)" | Same idea: two-cell = the separate 8000 mAh version; do not add a second cell to a 4000 mAh unit [UM] |
| Frequency plans | [DS] full list | [PP] AS923-2 / AS923-1 (MPN -915M) | Not a contradiction: [PP] = what Cytron sells |
| Range wording | [DS] up to 10 km line of sight | [PP]/[DS: web] 2 km urban, 15 km rural | Marketing ranges; quote with conditions |

## Needs verification
- Warranty for this listing (not shown on the Cytron page; Milesight products elsewhere on the site show 12 months).
- Cytron box contents vs Milesight's (screw caps, number of mounting kits).
- Meaning of the `-915M` suffix (assumed 915 MHz-band hardware covering AS923; inferred).
- Whether Cytron offers longer cables.

## Sources
- [PP] https://my.cytron.io/Milesight/p-em300-zld-lorawan-leak-detection-sensor — read 2026-10-21
- [DS] https://resource.milesight.com/milesight/iot/document/em300-zld-datasheet-en.pdf — read in full 2026-10-21
- [DS: web] https://www.milesight.com/iot/product/lorawan-sensor/em300-sld-zld — read 2026-10-21
- [UM] https://resource.milesight.com/milesight/iot/document/em300-zld-user-guide-en.pdf — V2.3, 26 Dec 2024
- [UM: series] https://resource.milesight.com/milesight/iot/document/em300-series-user-guide-en.pdf — V2.5, 31 Oct 2023
- [VEN: install] https://resource.milesight.com/milesight/iot/document/water-leakage-sensor-installation-guide.pdf
