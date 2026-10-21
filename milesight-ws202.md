# Milesight WS202 LoRaWAN PIR & Light Sensor — Verified Reference

| | |
|---|---|
| Product code | `WS202` (Milesight model). Cytron code `LR-WS202`, MPN `WS202-915M` [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight WS202 datasheet PDF (3 pages, read in full) and WS202 User Guide V1.3 (May 15, 2023; packing list, LED patterns, power, NFC access, LoRaWAN/general/threshold/D2D settings, reset, installation, battery replacement, payload read) |
| Primary source | Milesight *WS202 Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/ws202-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | LoRaWAN, Milesight D2D; internal antenna | [DS] |
| Frequency plans (model) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923 | [DS] |
| Tx power | 16 dBm (868 MHz) / 22 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP Class A; LoRaWAN V1.0.2 / V1.0.3; application port default 85 | [DS][UM] |
| Range | Up to 15 km line of sight | [DS] |
| PIR | Detection area 120° horizontal, 100° vertical; distance max 8 m ("6-8 m" in the overview); Fresnel lens Ø17.2 mm | [DS] |
| PIR with blocking stickers | 70° horizontal, 60° vertical (3 stickers supplied) | [UM] |
| Light | Bright / Dark status, threshold set anywhere in 1–60000 lux | [DS] |
| LED / button | 1 × status LED; 1 × reset button (internal) | [DS] |
| Configuration | Mobile app via NFC (card emulation supported) | [DS] |
| Advanced | Milesight D2D controller, threshold alarm | [DS] |
| Power supply | 1 × 1650 mAh ER14335 Li-SOCl₂ | [DS] |
| Battery life (30 min interval + 30 triggers/day, 25 °C, lab) | ~4.2 years (SF7, EU868); ~2.4 years (SF10, EU868); ~3.9 years (SF7, US915); ~2 years (SF10, US915) | [DS] |
| Reporting interval | Default 30 min (1–1080 min); Occupied reported immediately; Vacant after 120 s idle (default) | [UM] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Humidity | 0–90 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Dimensions | 50 × 50 × 23.8 mm | [DS] |
| Weight | 40 g with battery | [DS] |
| Material / colour | Anti-flaming polycarbonate, white | [DS] |
| Installation | Flat surfaces with screws or 3M tape; wall or ceiling | [DS][UM] |
| Regulatory | CE, FCC, RoHS, LoRaWAN Certified; safety EN62368-1 | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WS202 LoRaWAN PIR & Light Sensor"; brand Milesight; Code `LR-WS202`; MPN `WS202-915M`; warranty 12 months; RM189.40; Availability: Enquiry [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1"; Tx power "20 dBm (915MHz)" (see *Conflicts*) [PP].
- Spec list otherwise matches [DS]: PIR 120° × 100°, max 8 m; light 1–60000 lux threshold; NFC; D2D controller; 1 × 1650 mAh ER14335; ~4 years (30 min + 30 triggers/day); -20 to +60 °C; ≤ 90 % RH; IP30; 50 × 50 × 23.8 mm; CE, FCC, RoHS [PP].
- Description: light-sensor resolution "1 lux" over 1–60,000 lux; works with Milesight WS50x wall switch or WS558 light controller for automatic lighting [PP].
- **Packing list:** 1 × WS202 sensor, 2 × wall mounting kits, 1 × 3M tape, 3 × blocking stickers, 1 × quick guide [PP][UM].
- **Resources:** WS202 datasheet, WS202 user guide, payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No wired interfaces [DS].
| Event / action | LED | Src |
|---|---|---|
| Power on (pull out the battery insulating sheet) | Green for 3 s | [UM] |
| PIR triggered, not joined / joined | Red blinks once / green blinks once | [UM] |
| Join request sent / joined | Red blinks once / green blinks twice | [UM] |
| Hold reset > 3 s | Reboot (slow blink) | [UM] |
| Hold reset > 10 s | Factory reset (quick blink) | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **LoRaWAN keys:** a default AppKey is set at the factory (see the user guide; not copied); ask the seller for random keys if needed. OTAA is required for Milesight IoT Cloud / Development Platform. Match the gateway's plan (Cytron: AS923-2 Malaysia); for US915/AU915 with Milesight gateway defaults use channel index 8-15 [UM][PP]. Pair with `milesight-ug65.md` / `milesight-ug56.md`.
- **PIR is motion-only:** "Occupied" needs someone moving across zones; a still person turns into "Vacant" after the idle time (default 120 s) [UM]. Use `milesight-vs370.md` (radar) for seated occupancy.
- **Mount 1.5–2.5 m** on a wall or ceiling; keep fans, waving trees and curtains out of view [UM].
- **Blocking stickers** narrow the view to 70° × 60° for workstations (manual pasting adds error) [UM].
- **3M tape:** dry, smooth, grease-free wall (not wallpaper); press firmly, allow 24 h; otherwise use screws [UM].
- **Light threshold logic:** with illuminance collection on, a PIR trigger is sent immediately only if the light status meets the threshold [UM].
- **D2D:** set RX2 data rate/frequency, a D2D key matching the agent, and a 2-byte command per status; enable "LoRa Uplink" if the gateway should also get the alarm [UM].
- Payload (little-endian): battery `01 75` (%), PIR `03 00` (01 occupied / 00 vacant), light `04 00` (01 bright / 00 dark); low battery uplink once below 10 % (per V1.1 notes); downlinks on port 85: reboot `ff10ff`, reporting interval `ff03` (s), threshold `ff06` [UM].

## Power and electrical limits
- 1 × ER14335 Li-SOCl₂ 1650 mAh only — **no alkaline** cells; observe polarity [UM].
- Battery life ~4.2 years (SF7 EU868) down to ~2 years (SF10 US915) at 30-min interval + 30 triggers/day [DS].
- -20 to +60 °C, ≤ 90 % RH, IP30 (indoor) [DS].

## Software support
- Network time sync needs LoRaWAN V1.0.3 (DeviceTimeReq every 5 days) [UM].
- Milesight IoT Cloud and Milesight Development Platform [DS].

## Compatibility and accessories
- LoRaWAN gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- D2D lighting control with `milesight-ws50x.md` (wall switch) or `milesight-ws558-ln.md` (light controller) [PP].
- Related: `milesight-vs370.md` (radar presence), `milesight-vs330.md` (cubicle occupancy).

## Common mistakes / troubleshooting
- **No LED at power-up:** the battery insulating sheet is still in [UM].
- **Room shows vacant while people sit still:** PIR limitation; lengthen "Time to Report Vacancy" or use radar [UM].
- **False triggers:** fans, trees, curtains in the detection area [UM].
- **Join fails (red blinks):** region/channels and keys must match the network server [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Tx power at 915 MHz | [DS] 22 dBm | [PP] 20 dBm | [DS] wins |
| Battery life | [DS] ~4.2 y SF7 EU868 … ~2 y SF10 US915 (also a summary line "around 4 years") | [PP] "around 4 years" | [DS] wins; 4 years only at SF7 |
| Frequency plans | [DS] lists "AS923" (no sub-plans) | [PP] AS923-2 / AS923-1, MPN `WS202-915M` | Not a contradiction; confirm AS923-2 setting on the 915M build |

## Needs verification
- That Cytron's `WS202-915M` units ship set to AS923-2.
- Light sensor resolution "1 lux" [PP only].
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight WS202 Datasheet: https://resource.milesight.com/milesight/iot/document/ws202-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight WS202 User Guide V1.3 (May 15, 2023): https://resource.milesight.com/milesight/iot/document/ws202-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight WS202 page: https://www.milesight.com/iot/product/lorawan-sensor/ws202; decoders: https://github.com/Milesight-IoT/SensorDecoders
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ws202-lorawan-pir-and-light-sensor (read 2026-10-21).
