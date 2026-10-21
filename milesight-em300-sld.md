# Milesight EM300-SLD — Verified Reference

| | |
|---|---|
| Product code | `EM300-SLD` (Milesight model). Cytron code `LR-EM300-SLD`, MPN shown as `EM300-SLD-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight EM300-SLD/ZLD product page (specification tab, documents), EM300-SLD datasheet (full, 4 pages), EM300-SLD user guide V2.3 (full, 36 pages) and the Milesight *Water Leakage Detection Sensor Installation Guide* (full, 8 pages) read |
| Primary source | *EM300-SLD Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em300-sld-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
Sibling: `milesight-em300-zld.md` (EM300-ZLD) uses a 3 m sensing rope for zone (area) detection instead of the spot probe [DS: web].

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless technology | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan sold by Cytron | "Support Malaysia AS923-2, Singapore AS923-1" (MPN EM300-SLD-915M) | [PP] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A (fixed); LoRaWAN V1.0.2 and V1.0.3 selectable | [DS][UM] |
| Leak detection | Conducting liquid; triggers when liquid level reaches 5 mm | [DS] |
| Probe cable length | 1.5 m (customisable) | [DS] |
| Probe | Two metal pins; alarm when water touches both pins at the same time | [UM][VEN: install] |
| Temperature | -30 °C to +70 °C; ±0.3 °C (0 to +70 °C), ±0.6 °C (-30 to 0 °C); resolution 0.1 °C | [DS] |
| Humidity | 0–100 %RH; ±3 % (10–90 %RH), ±5 % (below 10 % and above 90 %RH); resolution 0.5 %RH | [DS] |
| LED / button | 1 × LED indicator (internal); 1 × power/reset button (internal) | [DS] |
| Power on/off | NFC, internal power button | [DS] |
| Configuration | NFC via mobile app (Milesight ToolBox), downlink | [DS][UM] |
| Advanced features | Threshold alarm, Milesight D2D controller, data storage (2,800 entries), data retransmission, data retrievability | [DS] |
| Power supply | 1 × 4000 mAh ER18505 Li-SOCl2 battery (8000 mAh version optional) | [DS] |
| Battery life (10 min interval + 24 triggers/day, lab test) | Over 10 years (SF7, EU868 & US915); around 5.6 years (SF10, EU868); around 4.1 years (SF10, US915) | [DS] |
| Operating temperature | -30 °C to +70 °C | [DS] |
| Relative humidity | 0–100 % (non-condensing) | [DS] |
| Ingress protection | IP67 | [DS] |
| Housing | Transceiver ABS + PC (flame retardant), white; probe stainless steel 316, white & silver | [DS] |
| Dimensions | 105.6 × 85.3 × 27 mm (transceiver) | [DS] |
| Installation | Transceiver: wall screw, 3M tape, cable tie; probe: wall screw, 3M tape | [DS] |
| Approvals | CE, FCC, ISED, RCM, Telec, ICASA; RoHS | [DS] |
| Default reporting interval | 10 min (range 1–1080 min) | [UM] |
| Application port | 85 (uplink and downlink) | [UM] |
| In the box (Milesight) | 1 × EM300-SLD, 2 × wall mounting kits, 2 × screw caps, 1 × quick guide, 1 × warranty card, 1 × 3M double-sided tape, 1 × mounting screw | [UM] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM300-SLD LoRaWAN Spot Leak Detection Sensor"; brand Milesight; Code `LR-EM300-SLD`; MPN `EM300-SLD-915M`; warranty 12 months; RM309.95; availability "Enquiry" with an INQUIRE NOW button (no Add to Cart); no reviews [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"**. No frequency variant selector [PP].
- Specification block matches [DS] (Tx power, sensitivity, OTAA/ABP Class A, 5 mm trigger, 1.5 m cable, T/H ranges and accuracy, internal LED and button, 2,800-entry storage, 4000 mAh ER18505, battery-life table, IP67, ABS+PC housing, SS316 probe, 105.6 × 85.3 × 27 mm, mounting options) [PP].
- Description and features say "up to 10 years" battery life, "up to 10 km in line-of-sight", IP67 and UV-resistant, NFC configuration, D2D [PP].
- **Packing list:** 1 × EM300-SLD device, 2 × wall mounting kits, 2 × screw caps, 1 × quick guide, 1 × warranty card, 1 × 3M double-sided tape, 1 × mounting screw (same as [UM]) [PP].
- **Resources:** EM300-SLD datasheet, EM300-SLD user guide, Water Leakage Detection Sensor Installation Guide (all resource.milesight.com PDFs), Payload Decoder (GitHub `Milesight-IoT/SensorDecoders`), Firmware & SDK download (milesight.com) [PP].
- "You May Also Need": UG65 Semi-Industrial LoRaWAN Gateway (`milesight-ug65.md`) [PP].

## Interfaces, terminals and pin mapping
No user wiring: the probe is factory-attached on a 1.5 m cable, and the device has no external terminals or USB port (the USB port was removed from hardware 3.x, [UM] revision V2.0) [DS][UM].

**Internal power button and LED** [UM]
| Function | Action | LED |
|---|---|---|
| Power on | Press and hold > 3 s | Off → On |
| Power off | Press and hold > 3 s | On → Off |
| Reset to factory default | Press and hold > 10 s | Blinks quickly |
| Check on/off status | Short press | On = device on; off = device off |

**Uplink payload (application port 85, little-endian channel/type/data)** [UM]
| Item | Channel | Type | Bytes | Decode |
|---|---|---|---|---|
| Battery level | 01 | 75 | 1 | UINT8, % (reported on join and every 6 h) |
| Temperature | 03 | 67 | 2 | INT16/10, °C |
| Humidity | 04 | 68 | 1 | UINT8/2, %RH |
| Water leakage | 05 | 00 | 1 | 00 = not leak, 01 = leaked |
| Historical data | 20 | ce | 8 | timestamp (UINT32 s) + temperature + humidity + leak status |
Decoders: https://github.com/Milesight-IoT/SensorDecoders [UM][PP].

## Rules and gotchas (for code, wiring and tutorials)
- **Conductive liquids only.** Water, weak acid and weak base; not hazardous chemicals, solvents, oil, fuel, strong acids or other corrosive liquids [VEN: install].
- **Both pins must be wet.** The alarm triggers only when the water touches both metal pins at the same time; orient the pins toward where water collects [UM][VEN: install]. Do not let the pins touch metal objects — that gives false alarms [UM].
- **Match the frequency plan to the gateway.** Cytron sells the 915M unit stated for Malaysia AS923-2 / Singapore AS923-1 [PP]; set the same plan and sub-band on the gateway/network server [UM]. ([UM] note for US915/AU915 with Milesight gateway defaults: channel index 8–15.)
- **Use OTAA for Milesight IoT Cloud / Development Platform** — required there [UM].
- **Battery:** only ER18505 Li-SOCl2; alkaline cells are not supported. Do not fit two cells in the 4000 mAh version (or one in the 8000 mAh version) — the battery calculation goes wrong [UM].
- Temperature in the uplink is always °C, whatever unit ToolBox displays [UM].
- Data storage needs the device time synced (ToolBox or LoRaWAN V1.0.3 DeviceTimeReq); ToolBox exports only the last 14 days [UM].
- Firmware upgrade via ToolBox is Android only [UM].

## Power and electrical limits
- 1 × 4000 mAh ER18505 Li-SOCl2 (optional 8000 mAh version with two cells); no external power input [DS][UM].
- Battery life (lab, 10 min interval + 24 triggers/day): > 10 years at SF7, ~5.6 years SF10 EU868, ~4.1 years SF10 US915 [DS]. Data retransmission raises uplink count and shortens battery life [UM].
- Low-battery alarm when level drops to 1 % [UM].
- Operating -30 °C to +70 °C, 0–100 %RH non-condensing [DS].

## Software support
- **Milesight ToolBox** app (Android/iOS, NFC) for power on/off, LoRaWAN settings, reporting interval (1–1080 min, default 10), thresholds, calibration, D2D, data storage/retransmission, backup/restore templates, reset and firmware upgrade (Android) [UM].
- **LoRaWAN:** OTAA/ABP, Class A, V1.0.2/V1.0.3, ADR, rejoin mode (LinkCheckReq), confirmed mode, RX2 settings [UM].
- **Alarms:** temperature threshold (below/over/within/below-or-over), water-leak alarm with alarm reporting interval and times, low-battery alarm [UM].
- **Milesight D2D:** acts as a D2D **controller** sending 2-byte commands to D2D agent devices on temperature-threshold or leak/no-leak events, optionally with a LoRaWAN uplink [UM].
- **Historical data:** stores 2,800 entries; retransmission after network loss; downlink enquiry by time point or range (max 300 records per range) [DS][UM].
- Platforms named by Milesight: Milesight IoT Cloud and Milesight Development Platform; compatible with standard LoRaWAN gateways and network servers [DS][UM].

## Compatibility and accessories
- Needs a LoRaWAN gateway and network server on the same plan: Milesight `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` (embedded network servers) [PP][VEN].
- D2D agents (for example a Milesight relay or controller) can be triggered directly; which Milesight products act as agents is in their own files [UM].
- Related leak sensors: `milesight-em300-zld.md` (3 m rope, zone detection). WS303 mini leak sensor and EM300-MLD membrane sensor are Milesight models not in the KB [VEN: install].
- Optional 8000 mAh battery version; customised cable length — via Milesight [DS].

## Common mistakes / troubleshooting
- **No join:** frequency plan or sub-band mismatch with the gateway; OTAA keys not entered on the network server [UM].
- **Leak not reported:** water touches only one pin; test by dipping the probe with the reporting interval set to 1 min, then dry it and check the status returns to "No leak" [UM].
- **False alarms:** pins touching metal [UM].
- **NFC read fails:** remove the phone case, find the phone's NFC area, move away and retry [UM].
- **Wrong battery %:** wrong cell count or a non-ER18505 cell [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [DS] over 10 years (SF7), ~5.6 / ~4.1 years at SF10; [PP] "up to 10 years" | [UM] overview: "up to 5 years" / "more than 5 years" with 4000 mAh | [DS] wins (stated with test conditions). Quote the condition |
| Wetted length to trigger | [UM] V2.3: soaking water length > 2.4 cm | [VEN: install]: > 1.1 cm | [UM] is higher authority; both agree both pins must be wet. Trigger spec stays "liquid level reaches 5 mm" [DS] |
| Frequency plans | [DS] CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M) | Not a contradiction: [PP] names the plans for Cytron's 915 MHz-band unit |
| Probe colour | [DS] white & silver | [DS: web], [PP] white | Cosmetic; [DS] |

## Needs verification
- Meaning of the `-915M` MPN suffix (assumed 915 MHz-band hardware covering AS923; inferred).
- Whether Cytron can supply the 8000 mAh version or custom cable lengths.
- Probe connector detail and whether the probe is detachable (drawings not read).
- Datasheet version/date (none printed).

## Sources
- [PP] https://my.cytron.io/Milesight/p-em300-sld-lorawan-spot-leak-detection-sensor — read 2026-10-21
- [DS] https://resource.milesight.com/milesight/iot/document/em300-sld-datasheet-en.pdf — read in full 2026-10-21
- [DS: web] https://www.milesight.com/iot/product/lorawan-sensor/em300-sld-zld — Specifications and Documents, read 2026-10-21
- [UM] https://resource.milesight.com/milesight/iot/document/em300-sld-user-guide-en.pdf — V2.3, 26 Dec 2024, read in full 2026-10-21
- [VEN: install] https://resource.milesight.com/milesight/iot/document/water-leakage-sensor-installation-guide.pdf — read in full 2026-10-21
- [VEN] Payload decoders: https://github.com/Milesight-IoT/SensorDecoders (linked, not opened)
