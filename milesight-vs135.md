# Milesight VS135 Ultra ToF People Counter — Verified Reference

| | |
|---|---|
| Product code | `VS135` (Milesight model family: VS135-P PoE, VS135-xxxM LoRaWAN, VS135-L08EU cellular, VS135-HL Wi-Fi HaLow). Cytron parent code `V-LR-VS135`; variant codes `LR-VS135` ("Standard") and `LR-VS135-P` ("High Ceiling Mount") [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both variants: code, price, stock; description, features, specifications, packing lists, resources), Milesight VS135 datasheet PDF (7 pages, read in full), VS135-P (PoE) User Guide V1.4 (May 28, 2025; product introduction, packing list, hardware, button/LED, DI/DO notes, power, installation, coverage, web access) and VS135 (LoRaWAN) User Guide V1.4 (May 28, 2025; packing list, hardware, power, web access, LoRaWAN port) |
| Primary source | Milesight *VS135 Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/vs135-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
Milesight builds VS135 in four connectivity versions — **PoE (VS135-P, 802.3at PoE+ or 12 V)**, LoRaWAN (VS135-470M/868M/915M, 12 V DC), 4G cellular (VS135-L08EU) and Wi-Fi HaLow (VS135-HL) — each with **Standard optics** (≤ 3.5 m ceiling, 98° × 80°) or **High Ceiling Mount optics** (≤ 6.5 m, 60° × 45°) [DS]. Cytron's page is titled "PoE" and offers two variants, "Standard" (code `LR-VS135`) and "High Ceiling Mount" (code `LR-VS135-P`); the codes and packing lists suggest the Standard variant may be the LoRaWAN (DC-powered) build and the High Ceiling variant the PoE build — **this is not stated and must be confirmed with Cytron** (see *Conflicts*) [PP][DS][UM].
Functions: up to 4 bi-directional lines with U-turn filtering, up to 4 regions with dwell time, group counting, child/adult differentiation, staff detection (staff tags), occlusion detection, shopping-cart fill level (not on LoRaWAN), motion and dwell heat maps, multi-device stitching, radar-based ESG power-saving mode, 3-axis tilt compensation and automatic height detection [DS]. Compare the stereo-vision `milesight-vs125.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensor | 2nd-gen ToF, 940 nm invisible light beam | [DS] |
| FoV | Standard: 98° H × 80° V; High Ceiling Mount: 60° H × 45° V | [DS] |
| Distance accuracy | Standard ±3.5 cm; High Ceiling ±6.5 cm | [DS] |
| Detection range (distance) | Standard 0.5–3.5 m; High Ceiling 2–6.5 m | [DS] |
| Installation height | Standard ≤ 3.5 m; High Ceiling ≤ 6.5 m. Minimum (1.8 m tallest person): Standard ≈ 2.335 m; High Ceiling ≈ 3.835 m | [DS][UM] |
| Counting accuracy | Up to 99.8% | [DS] |
| Detection area, Standard (1.75 m target) | 2.5 m: 1.84 × 1.34 m; 3.0 m: 2.99 × 2.18; 3.5 m: 4.14 × 3.02 m (monitored/visible area at 3.5 m: 8.05 × 5.87 m) | [DS][UM] |
| Detection area, High Ceiling | 3.5 m: 2.08 × 1.49 m; 4.5 m: 3.23 × 2.32; 5.5 m: 4.39 × 3.15; 6.5 m: 5.54 × 3.98 m (monitored at 6.5 m: 7.51 × 5.38 m) | [DS][UM] |
| Luminous mode | Auto / Always on / Schedule | [DS] |
| Lines / regions | Up to 4 bi-directional lines; up to 4 areas (10-sided each) with dwell time | [DS] |
| Other analytics | Group counting, child/adult, staff detection, occlusion detection, motion + dwell heat map; shopping-cart fill level on PoE/cellular/HaLow only | [DS] |
| Multi-device stitching | PoE: up to 8 devices; other versions: up to 4 | [DS] |
| Data retransmission | PoE/cellular/HaLow: 8 × 50000 packets; LoRaWAN: 4000 packets | [DS] |
| Video validation | 1 channel, 4 hours duration | [DS] |
| Local storage | Up to one million records; CSV export | [DS] |
| Ethernet (VS135-P) | 1 × RJ45 10/100 Mbps (PoE PD), 1.5 kV RMS isolation; HTTP, HTTPS, MQTT, MQTTS, NTP, 802.1x, SSH, LLDP, BACnet/IP | [DS] |
| LoRaWAN (VS135-470M/868M/915M) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4; Tx 16 dBm (868) / 20 dBm (915) / 19 dBm (470); -137 dBm @ 300 bps; OTAA/ABP Class C; application port default 85 | [DS][UM: LoRaWAN] |
| Cellular (VS135-L08EU) | LTE Cat 4 B1/B3/B7/B8/B20/B28; WCDMA B1/B8; GSM B3/B8; Nano SIM | [DS] |
| Wi-Fi HaLow (VS135-HL) | IEEE 802.11ah STA, 863.5–867.5 / 902.5–927.5 MHz | [DS] |
| Wi-Fi (all) | 802.11 b/g/n 2.4 GHz, AP mode for configuration | [DS] |
| Alarm I/O | PoE version only: 1 in / 1 out | [DS] |
| Power input | 1 × DC jack | [DS] |
| Power supply | PoE version: 802.3at PoE+ or DC 12 V / 2 A. Other versions: DC 12 V / 2 A | [DS] |
| Power consumption (PoE) | Standard avg 8 W, max 17 W; High Ceiling avg 10 W, max 24 W; hibernate 5 W | [DS] |
| Power consumption (LoRaWAN) | Standard avg 7 W, max 15 W; High Ceiling avg 8 W, max 20 W; hibernate 4 W | [DS] |
| Button / LED | 1 × Reset/Wi-Fi button; 1 × RGB LED | [DS] |
| Operating temperature | -20 °C to +50 °C | [DS] |
| Humidity | 0–95 % non-condensing | [DS] |
| Ingress protection | IP40 | [DS] |
| Dimensions | 200 × 35 × 85 mm | [DS] |
| Weight | PoE 419 g; cellular 412.8 g; HaLow 409.8 g; LoRaWAN 409.8 g | [DS] |
| Installation | Ceiling; extended ceiling and lintel mounting with optional multifunctional bracket | [DS] |
| Regulatory | PoE: FCC, CE, GDPR; LoRaWAN: FCC, CE, GDPR | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "VS135 PoE Ultra ToF People Counter"; brand Milesight; parent code `V-LR-VS135`; option "Version": **Standard** (`LR-VS135`, RM3,314.85, cashback RM99.45) and **High Ceiling Mount** (`LR-VS135-P`, RM3,271.80, cashback RM98.15); both out of stock; warranty 12 months [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1" [PP].
- Spec list: 2nd-gen ToF + edge AI; up to 99.8%; Standard 0.5–3.5 m, 98° × 80°; High Ceiling 2.0–6.5 m, 60° × 45°; connectivity "LoRaWAN, Wi-Fi HaLow, 4G LTE, Ethernet (PoE+)"; DC 12 V / 2 A or 802.3at PoE+; Standard 8 W typical, High Ceiling 10 W typical; IP40; -20 to +50 °C; 200 × 35 × 85 mm; ceiling, extended ceiling and lintel mounts [PP].
- Features: "up to 22.05 m²" coverage; radar ESG mode; up to 8-unit stitching; 4 lines; 4 regions; staff filtering via height thresholds / RFID tags; Milesight D2D to actuators in < 1 s [PP].
- **Packing lists:** Standard — 1 × VS135, 4 × ceiling mounting kits, 8 × staff tags, **1 × power adapter**, quick guide, warranty card. High Ceiling Mount — 1 × VS135, 4 × ceiling mounting kits, 8 × staff tags, **1 × multi-interface cable**, quick guide, warranty card [PP].
- **Resources:** VS135 datasheet, VS135 user guide (LoRaWAN), VS135-P user guide (PoE), payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
| Part | Function | Src |
|---|---|---|
| RJ45 (PoE version only) | 10/100 Ethernet, multi-device stitching, 802.3at PoE+ power input | [DS][UM: P] |
| DC jack | 12 V / 2 A input | [DS][UM] |
| Multi-interface (PoE version only) | DI / DO and RS485 (RS485 under development) | [UM: P] |
| Reset/Wi-Fi button | Hold > 3 s: Wi-Fi on/off (blue blinks 3 s; blue on = Wi-Fi on, green on = Wi-Fi off). Hold > 10 s: factory reset (green blinks until done) | [UM] |
| RGB LED | Status; can be switched off (LED indicator switch) | [UM] |

**DI/DO wiring:** the multi-interface wire assignment is a figure only in the [UM: P] and was not read. Text: DI default — contacts connected = low, open = high; DO loads up to 1 A @ 24 V DC [UM: P].

## Rules and gotchas (for code, wiring and tutorials)
- **Know which version you have.** Only the PoE version (VS135-P) has Ethernet, PoE+, alarm I/O and BACnet/IP; the LoRaWAN version is DC-only and sends uplinks over LoRaWAN Class C [DS].
- **PoE must be 802.3at (PoE+)**, not 802.3af — the PoE version draws up to 17 W (Standard) or 24 W (High Ceiling) [DS][UM: P].
- **LoRaWAN version:** select the gateway's region (Cytron states AS923-2 for Malaysia); application port default 85; a default AppKey is set at the factory (see the user guide; not copied) [UM: LoRaWAN][PP]. Pair with `milesight-ug65.md` / `milesight-ug56.md` / `milesight-ug67.md`.
- **Placement:** keep it away from walls (normal counting: x > 50 cm, y > 50 cm; normal imaging y > 60 cm, or > 75 cm over dark carpet); tilt ≤ 15° (Standard) or ≤ 10° (High Ceiling); nothing within 50 cm in front of the ToF light; avoid 940 nm IR sources, glass and mirrors; over a swinging door keep it open or mount ≥ 40 cm from the door path [UM: P].
- **Mounting:** flat ceiling > 30 mm thick; four 4 mm holes; route round cables through the rubber sleeve and keep it sealed; remove the lens film last [UM: P].
- **Detection area is much smaller than the monitored (visible) area** — plan with the detection-area table; e.g. a 6 × 3 m door zone at 3 m needs 2 × 2 = 4 Standard units [UM: P].

## Power and electrical limits
- PoE version: 802.3at PoE+ or DC 12 V / 2 A [DS][UM: P]. LoRaWAN version: DC 12 V / 2 A with the supplied adapter [DS][UM: LoRaWAN].
- Max 24 W (PoE, High Ceiling); hibernate 4–5 W in the radar ESG mode [DS].
- Ethernet isolation 1.5 kV RMS; DO up to 1 A @ 24 V DC [DS][UM: P].
- -20 to +50 °C, 0–95 % RH, IP40 [DS].

## Software support
- Web GUI over Wi-Fi (all) and Ethernet (PoE): dashboard, lines/regions, attribute filters, heat maps, stitching, data push, validation recording, system settings [UM].
- PoE: HTTP(S), MQTT(S), CGI, BACnet/IP, 802.1x, OpenVPN, SSH, LLDP; DeviceHub and Development Platform [DS][UM: P].
- LoRaWAN: standard LoRaWAN gateways/network servers, Milesight IoT Cloud, Milesight D2D [DS][PP].
- Payload decoder: GitHub `Milesight-IoT/SensorDecoders`; firmware from Milesight [PP].
- Privacy: depth data only, no images; video validation (1 channel, 4 h) exists for accuracy checks [DS].

## Compatibility and accessories
- PoE version needs an 802.3at PoE+ switch or injector (injector and adapter optional per [UM: P]; Cytron's High Ceiling packing list has no adapter or injector) [UM: P][PP].
- 8 staff tags are in the box for staff filtering [PP][UM].
- Optional multifunctional bracket (extended ceiling / lintel mount) is not sold on the Cytron page [DS].
- LoRaWAN version needs a gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.

## Common mistakes / troubleshooting
- **No power on PoE:** an 802.3af port is not enough; use 802.3at PoE+ [DS].
- **Red/abnormal preview:** obstacles in view, too close to a wall, dark floor — raise noise filtering, move the unit [UM: P].
- **Miscounts near doors:** keep the door open or mount ≥ 40 cm from its swing path [UM: P].
- **Can't reach the web page over Ethernet:** set the PC to the 192.168.5.x subnet; the unit is at 192.168.5.220 [UM: P].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| What Cytron's two variants are | [PP] title "PoE"; variants "Standard" (`LR-VS135`, with power adapter, no multi-interface cable) and "High Ceiling Mount" (`LR-VS135-P`, with multi-interface cable) | [DS] Standard / High Ceiling are optics options available on every connectivity version; "-P" = PoE version; the LoRaWAN version box has a power adapter and no multi-interface cable [UM] | **Unresolved.** Inferred: Cytron's "Standard" may be the LoRaWAN build and "High Ceiling Mount" the PoE build. Confirm the exact Milesight order codes with Cytron before quoting |
| Connectivity | [PP] lists LoRaWAN, Wi-Fi HaLow, 4G LTE and PoE+ together | [DS] each is a separate model | [DS]: one connectivity per unit |
| Frequency plan | [PP] AS923-2 / AS923-1 | [DS] LoRaWAN only; PoE has no LoRaWAN | Applies only if the unit is the LoRaWAN version |
| Stitching | [DS] PoE up to 8, others up to 4 | [UM: P] V1.4 overview "up to four-device stitching" | [DS] wins (newer feature) |
| Power consumption | [DS] avg 8 W / max 17 W (Standard PoE), avg 10 / max 24 W (High Ceiling PoE) | [PP] 8 W / 10 W "typical" | Consistent for averages; use [DS] max for PoE budgeting |
| Coverage | [PP] "up to 22.05 m²" | [DS] largest detection area 5.54 × 3.98 m ≈ 22.05 m² (High Ceiling at 6.5 m) | Consistent; [PP] quotes the High Ceiling maximum |
| D2D | [PP] Milesight D2D to actuators | [DS] does not list D2D for VS135 | [DS] does not confirm; *Needs verification* |

## Needs verification
- **Which Milesight model and order code each Cytron variant is** (LoRaWAN or PoE; Standard or High Ceiling optics).
- Multi-interface wire colours for DI/DO/RS485 (figure only).
- PoE class (802.3at stated; class not printed; inferred Class 4).
- Milesight D2D support on VS135 [PP only].
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight VS135 Datasheet: https://resource.milesight.com/milesight/iot/document/vs135-datasheet-en.pdf (read 2026-10-21).
- [UM: P] Milesight VS135-P User Guide V1.4 (May 28, 2025): https://resource.milesight.com/milesight/iot/document/vs135-p-user-guide-en.pdf (read 2026-10-21).
- [UM: LoRaWAN] Milesight VS135 User Guide V1.4 (May 28, 2025): https://resource.milesight.com/milesight/iot/document/vs135-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight VS13x page: https://www.milesight.com/iot/product/lorawan-sensor/vs133-vs135 (also VS135-HL and VS135-L08EU user guides, not opened).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-vs135-poe-ultra-tof-people-counter (read 2026-10-21; the High Ceiling variant URL ends `-high-ceiling-mount-version`).
