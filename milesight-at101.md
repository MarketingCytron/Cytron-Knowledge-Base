# Milesight AT101 — Verified Reference

| | |
|---|---|
| Product code | `AT101` (Milesight model). Cytron code `LR-AT101`, MPN shown as `AT101-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources, FAQ), Milesight AT101 product page (features, specification tab, documents), AT101 datasheet (full, 4 pages) and AT101 user guide V1.0 (hardware, quick start, operation, installation and payload sections) read |
| Primary source | *AT101 Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/at101-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Protocol | LoRaWAN® | [DS] |
| Antenna | Internal | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan sold by Cytron | "Support Malaysia AS923-2, Singapore AS923-1" (MPN AT101-915M) | [PP] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A (fixed); V1.0.2 / V1.0.3 / V1.0.4 | [DS][UM] |
| GNSS accuracy | 5.0 m CEP (direct line of sight); resolution 0.000001° | [DS] |
| GNSS TTFF | Cold start 37 s average; hot start 1 s average | [DS] |
| GNSS sensitivity | Tracking -167 dBm; reacquisition -160 dBm; cold start -148 dBm; hot start -159 dBm | [DS] |
| Wi-Fi positioning | AP scanning only (does not connect); reports BSSID, RSSI; 802.11b/g/n 2.4 GHz | [DS] |
| Motion | Normal / Tilt status (3-axis accelerometer) | [DS] |
| Temperature | -40 to 125 °C; 0.1 °C (NTC) | [DS] |
| Button | 1 × tamper button (plus internal power button) | [DS][UM] |
| Power on/off | NFC, internal power button | [DS] |
| Configuration | NFC, Bluetooth® 5.3, downlink | [DS] |
| Advanced features | Geofence, tilt threshold alarm, tamper alarm, data storage (1000 entries), retransmission, retrievability | [DS] |
| Power supply | 4 × 2700 mAh ER14505 Li-SOCl2, replaceable | [DS] |
| Battery life (25 °C, lab) | Twice-daily fixes 15+ years; ten-daily 8+ years; hourly 4+ years | [DS] |
| Operating temperature | -30 °C to +70 °C | [DS] |
| Relative humidity | 0–95 % (non-condensing) | [DS] |
| Material / colour | PC, black; UV protection | [DS] |
| Ingress / impact protection | IP67 / IK09 | [DS] |
| Dimensions / weight | 110 × 70 × 30 mm / 202 g with batteries | [DS] |
| Installation | Wall screw, 3M tape, cable tie | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
| Default reporting interval | 1440 min (1–1440 min) in periodic mode | [UM] |
| GNSS fix timeout | Default 3 min (1–5 min) | [UM] |
| In the box (Milesight) | 1 × AT101, 2 × mounting kits, 1 × 3M tape, 1 × quick guide, 1 × warranty card | [UM] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "AT101 LoRaWAN Outdoor Asset Tracker"; brand Milesight; Code `LR-AT101`; MPN `AT101-915M`; warranty 12 months; RM559.65; availability "Enquiry" (INQUIRE NOW); product video [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"**; Tx 20 dBm (915 MHz) [PP].
- Spec block matches [DS] (GNSS figures, Wi-Fi scanning, tilt, temperature, NFC/BT 5.3, 4 × 2700 mAh ER14505, battery-life table, -30 to +70 °C, IP67, IK09, 110 × 70 × 30 mm, 202 g, mounting) [PP].
- Features list adds geofencing, three modes, 1000 stored records with retransmission, NFC and Bluetooth, Milesight IoT Cloud management [PP].
- **Packing list:** 1 × AT101, 2 × mounting kits, 1 × 3M tape, 1 × warranty card, 1 × quick guide (same as [UM]) [PP].
- **Resources:** AT101 datasheet, AT101 user guide, Firmware & SDK download [PP].
- **FAQ:** "AT101 Display Coordinates of the Opposite side of the Earth" — fixed by the latest AT101 firmware (Milesight download centre, `#firmware-at101`); **upgrade it over Bluetooth, not NFC** [PP].

## Interfaces, terminals and pin mapping
No wiring. Internal power button and LED (power on/off hold > 3 s; reset hold > 10 s, LED blinks quickly; short press shows status) [UM]. **Tamper button** on the back: pressed = installed, released = removed; when using 3M tape, align the tape hole with the tamper button [UM].

**Uplink highlights (port 85)** [UM]: battery 01 75 (%); temperature 03 67 (INT16/10 °C); GNSS location 04 88 (latitude/1000000, longitude/1000000, geofence + motion status byte); tilt 05 00; Wi-Fi scan results 06 d9 (BSSID + RSSI per AP); tamper status 07 00 (00 installed / 01 removed; always a confirmed packet). Alarm packets for geofence, tilt, tamper (with last location) and temperature [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Positioning strategy:** GNSS (outdoor, open sky), Wi-Fi scan (indoor or dense streets) or Wi-Fi then GNSS fallback (most power). Wi-Fi scan results need an external Wi-Fi geolocation lookup to become coordinates — the device only reports BSSIDs [UM][DS].
- **Work modes:** Periodic (default every 1440 min), Motion (separate stationary and moving intervals, start/stop detection) and Timing (up to 5 fixed times per day; sync time first) [UM].
- **Geofence:** circular, GNSS only; alarm when > 10 m outside the radius, dismiss when > 10 m back inside; takes effect after the next fix [UM].
- **Tilt alarm:** any axis > 20° from the set initial position [UM].
- **Firmware:** the "opposite side of the Earth" coordinate bug is fixed by newer firmware, which must be loaded over **Bluetooth** [PP].
- **Frequency plan:** Cytron's 915M unit is stated for AS923-2 / AS923-1; the asset must stay inside coverage of a gateway on the same plan [PP].

## Power and electrical limits
- 4 × 2700 mAh ER14505 Li-SOCl2, replaceable; no external power [DS].
- Battery life (25 °C): 15+ years at 2 fixes/day, 8+ years at 10/day, 4+ years hourly; Wi-Fi + GNSS mode uses the most power; retransmission shortens life [DS][UM].
- Operating -30 °C to +70 °C; IP67; IK09 [DS].

## Software support
- Milesight ToolBox app over **NFC or Bluetooth**: LoRaWAN, time sync, positioning strategy and timeouts, work mode, data storage/retransmission, geofence, tilt, tamper, backup/restore templates, reset, firmware upgrade [UM].
- Data storage 1000 records; export last 14 days via ToolBox; retransmission after outages; downlink enquiry [DS][UM].
- Time sync by ToolBox or LoRaWAN V1.0.3 DeviceTimeReq [UM].
- Platforms: Milesight IoT Cloud (OTAA required) and standard LoRaWAN network servers [DS][UM].

## Compatibility and accessories
- LoRaWAN gateway coverage on the same plan along the asset's route, e.g. `milesight-ug67.md` (outdoor), `milesight-ug65.md`, `milesight-ug56.md` [VEN].
- Typical assets per Milesight: community patrol cars, construction sites, warehouses, construction bins, golf carts, farm animals [DS].

## Common mistakes / troubleshooting
- **Coordinates on the opposite side of the Earth:** update firmware over Bluetooth [PP].
- **No GNSS fix indoors:** use Wi-Fi scan or Wi-Fi + GNSS strategy; GNSS times out after the set duration (default 3 min) and a "positioning failed" packet is sent [UM].
- **Geofence alarm never fires:** geofence needs GNSS positioning and only applies after the next fix [UM].
- **Tamper alarm after mounting with tape:** tape hole not aligned with the tamper button [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plans | [DS] CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [PP] AS923-2 / AS923-1 (MPN -915M) | Not a contradiction: [PP] = what Cytron sells |
| GNSS constellations | [VEN] GPS, GLONASS, Galileo and BeiDou simultaneously | [DS] constellations not listed | [VEN] only; quote as Milesight marketing |
No other mismatch: the Cytron specification and packing list match [DS]/[UM].

## Needs verification
- Firmware version that fixes the coordinate bug (Cytron FAQ gives no number).
- Meaning of the `-915M` suffix (inferred 915 MHz-band hardware).
- Datasheet version/date (none printed).

## Sources
- [PP] https://my.cytron.io/Milesight/p-at101-outdoor-asset-tracker — read 2026-10-21
- [DS] https://resource.milesight.com/milesight/iot/document/at101-datasheet-en.pdf — read in full 2026-10-21
- [DS: web] / [VEN] https://www.milesight.com/iot/product/lorawan-sensor/at101 — read 2026-10-21
- [UM] https://resource.milesight.com/milesight/iot/document/at101-user-guide-en.pdf — V1.0, 19 Jun 2023
- [VEN] Firmware: https://www.milesight.com/iot/resources/download-center/#firmware-at101 (linked from [PP], not opened)
