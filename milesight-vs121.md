# Milesight VS121 LoRaWAN AI Workplace Occupancy Sensor — Verified Reference

| | |
|---|---|
| Product code | `VS121` (Milesight model; LoRaWAN version). Cytron code `LR-VS121`; no MPN shown on the Cytron page [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources, FAQ), Milesight VS121/VS121-P datasheet PDF (7 pages, read in full), VS121 User Guide V2.0 (Feb 10, 2026; product introduction, hardware, power, installation, web access, LoRaWAN settings read) and the milesight.com product page (marketing text) |
| Primary source | Milesight *VS121 / VS121-P Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/vs121-vs121-p-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
The datasheet also describes **VS121-P**, a different model with Ethernet (802.3af PoE or 5 V terminal), DI/DO and RS485 and HTTP(S)/MQTT(S)/BACnet/IP output [DS]. Cytron sells the LoRaWAN VS121 [PP]. Milesight's own people counters for doorways are the PoE VS125 (`milesight-vs125.md`) and VS135 (`milesight-vs135.md`).

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensing | AI vision (lens), counts based on heads and shoulders; only counter values transmitted | [DS][UM][PP: FAQ] |
| Field of view | 190° horizontal, 112° vertical | [DS] |
| Installation height | 2.3 m to 4 m | [DS] |
| Recommended height | Sitting objects > 2.5 m (region counting); standing objects > 3 m, optimum 3 m (line crossing, people flow) | [DS][UM] |
| Detection area by height | 2.0 m: 4.4 × 1.8 m; 2.3 m: 7.4 × 2.8; 2.5 m: 9.6 × 3.6; 2.7 m: 10.7 × 4.3; 3.0 m: 12.3 × 5.0; 3.2 m: 14.7 × 6.0; 3.5 m: 18.6 × 7.6; 4.0 m: 19.3 × 8.3 m (actual range varies with the person's height) | [DS][UM] |
| Recognition rate | Up to 95% (tested for line-crossing within the recommended range) | [DS] |
| Regions | Up to 16 areas, up to 10 sides each, for regional people counting and dwell time | [DS] |
| Line crossing | Bi-directional counting; U-turn filtering | [DS] |
| People flow analysis | Traffic of different directions, at most 4 edges | [DS] |
| Privacy | Normal or blur live-view mode; up to 8 privacy masks; no images collected (GDPR) | [DS][UM] |
| Data retransmission | 1000 retransmission packets | [DS] |
| LoRaWAN protocol | LoRaWAN, Milesight D2D | [DS] |
| Frequency plans (model) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP, Class C | [DS] |
| Application port | Default 85 (range 1–223) | [UM] |
| Wi-Fi | IEEE 802.11 b/g/n, 2.4 GHz, AP mode for configuration only | [DS] |
| Buttons | 1 × Reset, 1 × Wi-Fi | [DS] |
| LED | 1 × status (multi-colour) | [DS][UM] |
| Power supply | Type-C 5 V / 3 A DC | [DS] |
| Power consumption | 9.4 W | [DS] |
| Ingress protection | IP30 | [DS] |
| Housing | PC + cast aluminium; white or black (optional); 130 g | [DS] |
| Dimensions | 85 × 85 × 20 mm | [DS] |
| Installation | Ceiling mounting | [DS] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Relative humidity | 0–95 % non-condensing | [DS] |
| Regulatory | CE, FCC, SRRC, GDPR; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "VS121 LoRaWAN AI Workplace Occupancy Sensor"; brand Milesight; Code `LR-VS121`; warranty 12 months; RM1,592.85; Availability: Enquiry (INQUIRE NOW) [PP].
- **Frequency plan sold:** "Support Malaysia AS923-2, Singapore AS923-1". No frequency variants are offered on the page [PP].
- Cytron spec list: FOV 190° H / 112° V; full monitored area 78 m² (R = 5 m, H = 3 m); installation height 2.5–4 m; detection rate up to 95% (region and line crossing), up to 98% (people flow analysis); 16 areas; 8 privacy masks; 3000 retransmission packets; Class C; Wi-Fi AP for configuration; 1 reset + 1 Wi-Fi button; 1 Wi-Fi LED; 5 VDC / 1.5 A by Type-C; 3.5 W; -5 to +55 °C; storage -20 to +60 °C; white, 126.9 g; 85 × 85 × 20 mm; ceiling mounting. Several of these differ from [DS]; see *Conflicts* [PP].
- Description mentions a "high ceiling mount version" covering 126 m² [PP]; Milesight removed that version from the user guide in V2.0 (Feb 2026) [UM].
- **Packing list:** 1 × VS121, 1 × power adapter, 1 × Type-C cable, 1 × wall mounting kit, 1 × mounting sticker, 1 × quick start guide, 1 × warranty card [PP].
- **Resources:** VS121/VS121-P datasheet, VS121 user guide, VS121/VS121-P whitepaper (resource.milesight.com PDFs), payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download (milesight.com) [PP].
- **FAQ on the page:** USB power cables over 5 m may fail to power it (use an active USB cable or hub); Wi-Fi is for configuration only, not data; per-zone count not supported (total only — this is older than the [DS] 16-region feature); no gender/age detection [PP].

## Interfaces, terminals and pin mapping
No wiring terminals on the LoRaWAN VS121 [DS][UM].
| Part | Function | Src |
|---|---|---|
| USB Type-C power port | 5 V power input (adapter and 1 m Type-C cable in the box) | [UM] |
| Wi-Fi button | Hold > 3 s to turn Wi-Fi on (LED off → green) or off (green → off) | [UM] |
| Reset button | Hold > 10 s: reset to factory default (LED blinks 6 times) | [UM] |
| Indicator LED | Multi-colour; red = device abnormal | [UM] |
| LoRa antenna | Internal dedicated LoRa antenna | [UM] |
| Extension interface | Rounded-rectangle interface with two positioning holes for expansion accessories | [UM] |
| Mounting holes | Four keyhole holes at the corners | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **Wi-Fi does not carry data.** Counts go out only over LoRaWAN (Class C) [PP: FAQ][DS].
- **Region must match the gateway.** Pick the same Region/channel plan as the gateway (Cytron sells for Malaysia AS923-2); for CN470/US915/AU915 with a Milesight gateway on default settings use channel index 8-15 [UM][PP]. Pair with a Milesight gateway such as `milesight-ug65.md` or `milesight-ug56.md`.
- **OTAA is required for Milesight IoT Cloud** [UM]. Default application port is 85 [UM]. A default AppKey is set at the factory (see the user guide; not copied) — change it for security [UM].
- **Mount facing straight down**, in line with the ceiling, on a flat ceiling at least 30 mm thick (4 × 6 mm holes, wall plugs, screws) [UM].
- **Lighting:** region counting needs > 20 lux; line crossing and people flow need > 50 lux. Avoid direct sunlight, mirrors and moving objects (doors) in the counting area [UM].
- When both trigger and periodic reporting are on, set the periodic interval above 30 s [UM]. Reporting interval range 5–86400 s (per revision history) [UM].
- Payload decoding: Milesight's decoder repository on GitHub (`Milesight-IoT/SensorDecoders`) [PP].

## Power and electrical limits
- Type-C 5 V; the datasheet says 5 V / 3 A and 9.4 W; the user guide says 5 V, 2 A with the provided adapter [DS][UM]. Use the supplied adapter.
- USB cables longer than 5 m may not power it; use an active USB cable or hub [PP: FAQ].
- Indoor only; -20 to +60 °C, 0–95 % RH non-condensing, IP30 [DS][UM].

## Software support
- LoRaWAN OTAA/ABP Class C; works with Milesight and mainstream LoRaWAN network servers; Milesight D2D controller role (sends control commands to D2D agent devices without a gateway) [DS][UM].
- Web GUI over Wi-Fi: live view (normal or blur), people-counting setup, LoRaWAN, D2D, WLAN, user, time, maintenance, security and log pages [UM].
- Uplinks: basic information, periodic data, real-time data; downlink commands for general, people counting, LoRaWAN and D2D settings and historical data query [UM].
- Management: Milesight IoT Cloud, Milesight Development Platform [DS][PP].
- Firmware: Milesight download centre [PP].

## Compatibility and accessories
- Needs a LoRaWAN gateway on the same plan (AS923-2 in Malaysia) and a network server. Cytron-sold gateways: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- In the box: power adapter, Type-C cable, mounting kit and sticker [PP][UM].
- Cytron's description and the [UM] mention optional accessories/extension interface; none are sold on the Cytron page [PP][UM].
- Related Cytron-sold occupancy sensors: VS330 bathroom occupancy (`milesight-vs330.md`), VS370 radar presence (`milesight-vs370.md`), WS202 PIR (`milesight-ws202.md`).

## Common mistakes / troubleshooting
- **Won't power up on a long USB cable:** over 5 m needs an active cable or USB hub [PP: FAQ].
- **Cannot find the Wi-Fi AP:** hold the Wi-Fi button > 3 s until the LED is green [UM].
- **Undercounting:** check lux (> 20 / > 50), WDR setting, mounting height and that the device faces straight down; dark floors, hair/clothes the same colour as the floor and strong backlight reduce accuracy [UM].
- **False counts:** keep doors, mirrors and moving objects out of the counting line [UM].
- **No uplinks:** region and channels must match the gateway; OTAA for Milesight IoT Cloud [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Power supply | [DS] Type-C 5 V / 3 A; [UM] 5 V, 2 A adapter | [PP] 5 VDC / 1.5 A | [DS] wins: 5 V / 3 A; use the supplied adapter |
| Power consumption | [DS] 9.4 W | [PP] 3.5 W | [DS] wins |
| Operating temperature | [DS] -20 to +60 °C | [PP] -5 to +55 °C | [DS] wins |
| Installation height | [DS] 2.3–4 m | [PP] 2.5–4 m | [DS] wins |
| Data retransmission | [DS] 1000 packets | [PP] 3000 packets | [DS] wins |
| Weight | [DS] 130 g | [PP] 126.9 g | [DS] wins |
| Recognition rate | [DS] up to 95% | [UM] overview: up to 98%; [PP] 95% (region, line) and 98% (people flow) | [DS] wins: up to 95% |
| High ceiling mount version | [PP] description: 126 m² high-ceiling version | [UM] V2.0 (Feb 2026): high ceiling mount version deleted | [UM] wins; not available |
| Coverage | [PP] 78 m² (R = 5 m, H = 3 m) | [DS] 12.3 × 5.0 m at 3 m; [VEN] "up to 127.84 m²" | [DS] table wins |
| Frequency plans | [PP] AS923-2 (Malaysia), AS923-1 (Singapore) | [DS] CN470…AS923-1/2/3/4 | Not a contradiction: [PP] names the plans relevant to Cytron's markets |
| Per-zone counts | [PP: FAQ] "only detect the total people" | [DS] up to 16 regions, per-region uplinks (UM V1.4) | [DS] wins; the FAQ is outdated |
| Packing list | [PP] 1 wall mounting kit | [UM] 4 wall mounting screw sets | Minor; trust the box |

## Needs verification
- Which exact frequency hardware Cytron ships (no MPN on the page; the page states AS923-2/AS923-1).
- Datasheet version/date (none printed).
- LED colour meanings beyond green (Wi-Fi), red (abnormal) and reset blink.
- Optional accessories for the extension interface (none listed by Cytron).

## Sources
- [DS] Milesight VS121/VS121-P Datasheet: https://resource.milesight.com/milesight/iot/document/vs121-vs121-p-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight VS121 User Guide V2.0 (Feb 10, 2026): https://resource.milesight.com/milesight/iot/document/vs121-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight VS121 page: https://www.milesight.com/iot/product/lorawan-sensor/vs121; whitepaper: https://resource.milesight.com/milesight/iot/document/milesight-vs121-ai-workplace-occupancy-sensor-whitepaper-en.pdf (not opened); payload decoder: https://github.com/Milesight-IoT/SensorDecoders
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-vs121-lorawan-ai-workplace-occupancy-sensor (read 2026-10-21).
