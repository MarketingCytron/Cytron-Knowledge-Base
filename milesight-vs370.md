# Milesight VS370 LoRaWAN Radar Human Presence Sensor — Verified Reference

| | |
|---|---|
| Product code | `VS370` (Milesight model). Cytron code `LR-VS370`, MPN `VS370-915M` [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight VS370 datasheet PDF (4 pages, read in full) and VS370 User Guide V1.1 (Oct 15, 2025; packing list, buttons, power, Bluetooth/NFC access, LoRaWAN and general settings, reset, installation, accuracy factors, payload read) |
| Primary source | Milesight *VS370 Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/vs370-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | Millimetre-wave radar + PIR | [DS] |
| Recognition rate | Up to 99% | [DS] |
| Radar | 24 GHz; Tx 5 dBm; detection angle 150°; movement up to 7.5 m; slight movement up to 4.8 m | [DS] |
| PIR | Detection area 110°; within 7 m | [DS] |
| Light | Bright / Dim status (defaults: bright ≥ 700 lux, dim ≤ 300 lux) | [DS][UM] |
| LoRaWAN | LoRaWAN + Milesight D2D; internal antenna | [DS] |
| Frequency plans (model) | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| LoRa Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP Class A; LoRaWAN V1.0.2 / V1.0.3; application port default 85 | [DS][UM] |
| Button | 1 × reset button (internal) | [DS] |
| Configuration | Mobile app (Milesight ToolBox) via NFC or Bluetooth; downlink | [DS] |
| Advanced | D2D controller, hibernate time, sensitivity setting, FUOTA | [DS] |
| Power supply | 2 × 2700 mAh ER14505 Li-SOCl₂ batteries | [DS] |
| Battery life (50 triggers/day, 25 °C, lab) | ~6.7 years (SF7, EU868 & US915); ~5.3 years (SF10, EU868); ~4.6 years (SF10, US915) | [DS] |
| Reporting interval | Default 10 min; range 1–1440 min; vacancy reported 3 min (1–60) after last detection | [UM] |
| Operating temperature | 0 °C to 30 °C | [DS] |
| Humidity | 0–95 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Dimensions | Ø70 × 48.5 mm | [DS] |
| Weight | Body 89.6 g; magnetic bracket 38.2 g | [DS] |
| Housing | ABS (UL94 V1), white | [DS] |
| Installation | Wall mounting via magnetic bracket (extra 30° deflection) | [DS] |
| Regulatory | CE, FCC | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "VS370 LoRaWAN Radar Human Presence Sensor"; brand Milesight; Code `LR-VS370`; MPN `VS370-915M`; warranty 12 months; RM430.50; Availability: Enquiry (INQUIRE NOW) [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1" [PP].
- Spec list matches [DS] for technology, 24 GHz, 150° / 110°, 7.5 / 4.8 / 7 m, Tx up to 20 dBm, -137 dBm, Class A, 2 × ER14505, Ø70 × 48.5 mm, 89.6 g, IP30, 0–30 °C, NFC/Bluetooth/downlink, FUOTA, Milesight Development Platform [PP]. Battery wording differs (see *Conflicts*).
- Description claims radar detects "micro-movements such as breathing and slight body shifts" (see *Conflicts*) [PP].
- **Packing list:** 1 × VS370, 1 × magnetic bracket, 1 × bracket adhesive, 1 × quick start guide, 1 × warranty card [PP][UM]. Batteries are pre-installed (UM V1.1, Oct 2025) [UM].
- **Resources:** VS370 datasheet, VS370 user guide, payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No wired interfaces [DS].
| Action | Result | Src |
|---|---|---|
| Install / remove batteries | Power on / off (no power button) | [UM] |
| Hold reset > 3 s | Reboot | [UM] |
| Hold reset > 10 s | Factory reset (LED blinks quickly); or Reset in ToolBox via NFC | [UM] |
| Battery access | Hold the back cover and rotate counter-clockwise; remove the battery insulation sheet on first use | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **Wall only, 2.5–3 m high, tilt 60° or 75°. Ceiling mounting is not supported** [UM]. Small room (≤ 4 × 4 m): 2.5 m, 60°. Medium (4 × 4 to 6 × 6 m): 2.6 m, 75°. Larger rooms: ask Milesight [UM].
- Mount opposite the usual seating position (not behind it), on the glass side of glass-walled rooms, above a display if present, not in corners or on walking-path walls; logo faces up [UM].
- **False triggers:** fans, curtains, plants, people moving outside glass walls, an open door (radar penetrates) [UM]. Not suitable for small rooms such as bathrooms (use `milesight-vs330.md`) [UM].
- **It cannot detect a person who is completely still** (only breathing/heartbeat, no limb movement) [UM].
- **Batteries: ER14505 Li-SOCl₂ only — no alkaline AA.** Replace both with new cells; remove them for long storage [UM].
- **LoRaWAN:** OTAA is required for Milesight Development Platform; match the gateway's plan (Cytron: AS923-2 Malaysia); for US915/AU915 with a Milesight gateway on defaults use channel index 8-15 [UM][PP]. A default AppKey is set at the factory (see the user guide; not copied) [UM]. Pair with `milesight-ug65.md` / `milesight-ug56.md`.
- **Time sync** from the network server needs LoRaWAN V1.0.3 (DeviceTimeReq; time only, not time zone) [UM].
- Payload (little-endian): battery `01 75` (%), occupancy `03 00` (01 occupied / 00 vacant), illumination `04 00` (01 bright / 00 dim / fe disabled); downlink port 85 [UM].

## Power and electrical limits
- 2 × ER14505 Li-SOCl₂ 2700 mAh [DS]. Battery life ~6.7 years at SF7, ~4.6–5.3 years at SF10 with 50 triggers/day at 25 °C (lab) [DS].
- Indoor, 0–30 °C only, IP30; avoid long direct sunlight [DS][UM].

## Software support
- Milesight ToolBox (Bluetooth/NFC): LoRaWAN, time, general (reporting interval, occupancy trigger and maintaining sensitivity low/middle/high, hibernate periods, vacancy time, illuminance thresholds), D2D, upgrade, backup/restore templates, reset [UM].
- Downlinks: reboot, reporting interval, sensitivities, vacancy time, illuminance, hibernate, time zone, DST, D2D [UM].
- Milesight Development Platform management and OTA (FUOTA) [DS][UM].

## Compatibility and accessories
- LoRaWAN gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- D2D agents (e.g. Milesight light controllers or switches such as `milesight-ws558-ln.md`, `milesight-ws50x.md`) can be driven directly — check each agent supports D2D (inferred from the D2D controller role) [DS].
- Related: `milesight-ws202.md` (PIR + light, cheaper), `milesight-vs121.md` (camera AI counting).

## Common mistakes / troubleshooting
- **Stays "vacant" with a seated, motionless person:** a fully still person cannot be detected; raise the maintaining sensitivity [UM].
- **False "occupied":** fans, curtains, plants, glass walls with traffic outside, open door [UM].
- **Bracket falls off:** wall must be smooth, dry, grease-free (no wallpaper); press firmly and allow 24 h for the adhesive [UM].
- **Bluetooth drops:** reconnect; only one phone at a time; 3-minute idle timeout [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Breathing detection | [UM] "cannot detect a relatively stationary human body that shows only respiration and heartbeat" | [PP] radar "detects micro-movements such as breathing" | [UM] wins (higher authority); slight limb movement only |
| Battery life | [DS] 6.7 y (SF7) / 5.3 y (SF10 EU868) / 4.6 y (SF10 US915), all at 50 triggers/day | [PP] "up to 6.7 years (typical conditions)"; "50 Triggers per day: 5.3 years"; "5–6 years" | [DS] wins; Cytron mislabels the SF10 figure |
| Frequency plans | [DS] all plans | [PP] AS923-2 / AS923-1; MPN `VS370-915M` | Not a contradiction; [PP] names Cytron's markets. Confirm AS923-2 setting on the 915M build |

## Needs verification
- That Cytron's `VS370-915M` units ship set to AS923-2.
- LED meanings beyond the reset blink (no LED table in the [UM]).
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight VS370 Datasheet: https://resource.milesight.com/milesight/iot/document/vs370-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight VS370 User Guide V1.1 (Oct 15, 2025): https://resource.milesight.com/milesight/iot/document/vs370-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight VS370 page: https://www.milesight.com/iot/product/lorawan-sensor/vs370; decoders: https://github.com/Milesight-IoT/SensorDecoders
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-vs370-lorawan-radar-human-presence-sensor (read 2026-10-21).
