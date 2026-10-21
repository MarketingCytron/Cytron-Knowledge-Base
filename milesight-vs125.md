# Milesight VS125 PoE AI Stereo Vision People Counter (Low-and-Wide Version) — Verified Reference

| | |
|---|---|
| Product code | `VS125-LW-P` (Milesight model: VS125-LW, PoE version). Cytron code `LR-VS125-LW-P` [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight VS125-LW datasheet PDF (5 pages, read in full), VS125-LW User Guide V1.2 (Sept 9, 2026; product introduction, hardware, button/LED, DI/DO notes, installation, detection area, web access, privacy settings, video validation read), and the standard VS125 datasheet (model list only) |
| Primary source | Milesight *VS125 Datasheet — VS125-LW* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/vs125-lw-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
**It is not a LoRaWAN device.** The VS125-LW comes as PoE or 4G cellular versions only; there is no LoRaWAN option in the VS125-LW datasheet [DS]. (The URL sits under milesight.com "lorawan-sensor" but that is only Milesight's site category [VEN].)
Functions: bi-directional line counting (up to 4 lines) with U-turn filtering, regional counting and dwell time (up to 4 areas), child/adult differentiation, gender recognition, group counting, staff detection (with staff lanyard, badge, epaulet or the VA05 UWB kit), heat map, view-direction detection and stitching of up to 16 devices [DS]. The standard (non-LW) VS125-P is a different model for 2.2–6 m ceilings [VEN]; the related ToF counter is `milesight-vs135.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Model (Cytron) | VS125-LW-P (PoE version) | [DS][PP] |
| Sensor | 2 × 5 MP sensor (2592 × 1744) | [DS] |
| Installation height | 1.9–3.5 m | [DS] |
| Field of view | 130° horizontal, 117° vertical | [DS] |
| Required illumination | 0 lux with IR illuminators on | [DS] |
| Accuracy | Up to 99.8% people counting accuracy | [DS] |
| Detection area (1.75 m target) | 1.9 m: 0.86 × 0.65 m; 2.0 m: 1.28 × 0.98; 2.2 m: 2.14 × 1.63; 2.5 m: 3.43 × 2.61; 3.0 m: 5.57 × 4.24; 3.5 m: 7.71 × 5.87 m (≈ 45 m²; Milesight quotes "up to 40 m²") | [DS][UM] |
| Line counting | Up to 4 detection lines, bi-directional; U-turn filtering | [DS] |
| Regional counting / dwell | Up to 4 areas (up to 10-sided polygon each) | [DS] |
| Attribute recognition | Child/adult (1.9–3.3 m), gender, group counting, staff detection, heat map, view direction | [DS][UM] |
| Staff detection accessories | Staff lanyard, staff badge, staff epaulet, UWB kit VA05 | [DS] |
| Video validation storage | 8 GB | [DS] |
| Data retransmission | 8 × 50000 packets | [DS] |
| Local storage | Up to one million data records; CSV export | [DS] |
| Multi-device stitching | Up to 16 devices | [DS] |
| Ethernet | 1 × RJ45 10/100 Mbps (PoE PD); isolation 1.5 kV RMS | [DS] |
| Network protocols | MQTT(s), HTTP(s), 802.1x, SSH, NTP, OpenVPN, BACnet/IP, etc. | [DS] |
| Wi-Fi | IEEE 802.11 b/g/n 2.4 GHz, AP mode for configuration | [DS] |
| DI / DO | 1 × DI, 2 × DO | [DS] |
| Serial | 1 × RS485 (under development); 1 × UART (for the VA05 UWB staff anchor) | [DS] |
| Power connector | 1 × DC jack | [DS] |
| Power supply | 802.3af PoE or DC 12 V / 1 A | [DS] |
| Power consumption | Avg 6.9 W, max 12 W | [DS] |
| Button / LED | 1 × Reset/Wi-Fi button; 1 × RGB LED | [DS] |
| Ingress protection | IP40 | [DS] |
| Dimensions | 185 × 85 × 34 mm | [DS] |
| Weight | 284.4 g | [DS] |
| Colour | White or black (optional) | [DS] |
| Installation | Ceiling mounting; extended ceiling and lintel mounting with optional multifunctional bracket | [DS] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Humidity | 0–95 % non-condensing | [DS] |
| MTBF | 1,510,826 hours | [DS] |
| Regulatory | CE, FCC; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "VS125 PoE AI Stereo Vision People Counter (Low-and-Wide Version)"; brand Milesight; Code `LR-VS125-LW-P`; warranty 12 months; RM3,400.95; cashback RM102.03; Availability: Out Of Stock [PP].
- Cytron spec list matches [DS]: 2 × 5 MP (2592 × 1744); 1.9–3.5 m; 130° × 117°; up to 40 m² at 3.5 m; up to 99.8%; 0 lux with IR; 16-device stitching; 1,000,000 records with CSV export; RJ45 10/100 PoE PD; 1 DI, 2 DO; 1 RS485; 802.3af PoE or 12 V / 1 A; avg 6.9 W / max 12 W; IP40; 185 × 85 × 34 mm [PP].
- Description: up to 4 lines with U-turn filtering, up to 4 zones for queue management, adults vs children, gender, groups, staff filtering "via dedicated accessories", heat map, view direction, tailgating detection, "no personal data leaves the device" [PP].
- **Packing list:** 1 × VS125-LW device, 4 × ceiling mounting sets, 1 × multi-interface cable, 1 × warranty card, 1 × quick guide card [PP]. No power adapter (the [UM] lists the adapter as optional for the PoE version).
- **Resources:** VS125 GDPR guideline (links to the milesight.com VS125 page), VS125-LW datasheet, VS125-LW user guide, payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
| Part | Function | Src |
|---|---|---|
| RJ45 (PoE PD) | 10/100 Ethernet data, multi-device stitching, 802.3af PoE power input | [DS][UM] |
| DC jack | 12 V / 1 A DC input (alternative to PoE) | [DS][UM] |
| Multi-interface cable | DI, DO (×2) and RS485 (under development) | [DS][UM] |
| Nano SIM slot | Cellular version only — not on the PoE unit | [UM] |
| Reset/Wi-Fi button | Hold 3 s: Wi-Fi on/off (blue blinks 3 s; blue on = Wi-Fi enabled, green on = Wi-Fi disabled). Hold 10 s: reset (green blinks until done) | [UM] |
| RGB LED | Red on = module or algorithm detection error; can be switched off in Hardware Settings | [UM] |
| Stereo module + IR area | Dual-camera depth sensing; IR for darkness | [UM] |

**DI/DO wiring:** the wire colours / pin assignment of the multi-interface cable are given only as a figure in the [UM] ("Figure 1. DI/DO") and were not read. Text facts: DI default — contacts connected = low level, contacts open = high level; DO loads up to 1 A @ 24 V DC [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Ethernet access:** firmware 1.0.5 and later use **DHCP by default**; find the IP in the DHCP client list or with the Milesight VS tool. If no address is obtained within 30 s after power-on, it falls back to static **192.168.5.220** (set the PC to e.g. 192.168.5.61 / 255.255.255.0) [UM].
- **PoE must be IEEE 802.3af** (or use 12 V / 1 A on the DC jack). Budget 12 W max per port [DS]. Cytron does not include a power adapter [PP].
- **Install level:** horizontal within ±10°, remove the lens protective film, keep pendant lights and downlights out of view [UM].
- **Height setting matters:** on the Rule page click *Detect* to auto-measure height; if the depth preview is mostly blue increase the height setting, mostly red decrease it, in 50 mm steps [UM].
- **Attribute functions need 1.9–3.3 m** (child/adult, gender, staff, view direction); group counting works to 3.5 m [UM].
- **Coverage per unit is small at low height** (5.57 × 4.24 m at 3 m). For wider doors, stitch devices: devices along length = coverage length ÷ x, rounded up as needed (Milesight example: 6 × 3 m at 3 m needs 2 units) [UM].
- **Not for rain-exposed or private areas** (e.g. bathrooms) [UM]. Indoor IP40 [DS].
- Gender output is a visual-feature classification only (Milesight's own statement) [UM].

## Power and electrical limits
- 802.3af PoE on the RJ45, or DC 12 V / 1 A on the DC jack [DS].
- Avg 6.9 W, max 12 W [DS]. PoE class is not stated (see *Needs verification*).
- Ethernet isolation 1.5 kV RMS [DS].
- DO: up to 1 A @ 24 V DC [UM].
- -20 to +60 °C, 0–95 % RH non-condensing, IP40 [DS].

## Software support
- Web GUI over Ethernet or Wi-Fi: dashboard (depth preview), rules (lines, regions, attributes), DO triggering, heat map, occlusion alarm, stitching, network, data recipients, reports, image, depth calibration, video validation, system [UM].
- Data push: HTTP(s) / MQTT(s) with customisable content, BACnet/IP (PoE version), 802.1x (incl. EAP-TLS), OpenVPN, SSH, NTP [DS][UM].
- Management: Milesight DeviceHub and Milesight Development Platform [DS].
- Payload decoder: GitHub `Milesight-IoT/SensorDecoders`; firmware from the Milesight download centre [PP].

### Privacy notes
- Milesight states privacy-by-design and GDPR compliance; only counting data (no personal information) is transmitted [DS][UM].
- Preview privacy setting at activation: Scene preview = video stream, static image or no image; image type monochrome or pseudo-colour; changeable later in System Management [UM].
- Detection mode RGB (better attribute analysis) or Depth ("ideal for privacy-sensitive environments") [UM].
- **The device can record video locally for accuracy validation** (8 GB, up to 50 tasks, ≤ 60 min each) [DS][UM]. Milesight's installation steps say to notify individuals, obtain consent for image collection and inform them of opt-out rights [UM]. Cytron links a "VS125 GDPR Guideline" [PP].

## Compatibility and accessories
- Needs an 802.3af PoE switch/injector or a 12 V / 1 A adapter (not in the Cytron box) [DS][PP].
- Optional from Milesight (not sold on the Cytron page): multifunctional bracket for extended-ceiling and lintel mounting; staff lanyard/badge/epaulet; VA05 UWB staff detection kit [DS].
- Compare: VS135 ToF people counter (`milesight-vs135.md`); VS121 LoRaWAN occupancy sensor (`milesight-vs121.md`).

## Common mistakes / troubleshooting
- **Cannot find the device on Ethernet:** it uses DHCP (fw ≥ 1.0.5); if none within 30 s it falls back to 192.168.5.220 [UM].
- **Abnormal depth preview:** film still on, tilt > 10°, objects too close, wrong height setting — see the blue/red rule above [UM].
- **No power from the switch:** must be 802.3af PoE; passive PoE is not mentioned [DS].
- **RS485 doesn't work:** it is "under development" [DS].
- **Red LED:** module or algorithm detection error [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Max coverage | [DS] table: 7.71 × 5.87 m at 3.5 m (≈ 45 m²) | [DS] features / [PP]: "up to 40 m²" | Inside [DS]; quote "up to 40 m²" as Milesight's figure and the table for planning |
| Packing list power adapter | [UM] PoE version: power adapter optional | [PP] no adapter listed | Not a contradiction; no adapter from Cytron |

No material conflict between the Cytron page and the datasheet.

## Needs verification
- **Multi-interface cable pin/wire colours for DI, DO1, DO2, RS485, GND** (figure only in the [UM]; not read).
- PoE class (802.3af stated; class not given). Inferred from 12 W max that a Class 0 or Class 3 port is needed.
- DO type (relay or open collector) beyond "1 A @ 24 V DC".
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight VS125-LW Datasheet: https://resource.milesight.com/milesight/iot/document/vs125-lw-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight VS125-LW User Guide V1.2 (Sept 9, 2026): https://resource.milesight.com/milesight/iot/document/vs125-lw-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight VS125 page: https://www.milesight.com/iot/product/lorawan-sensor/vs125; standard VS125 datasheet: https://resource.milesight.com/milesight/iot/document/vs125-datasheet-en.pdf (model list read).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-vs125-poe-ai-stereo-vision-people-counter-low-and-wide-version (read 2026-10-21).
