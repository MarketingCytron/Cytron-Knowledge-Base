# Milesight WS301 LoRaWAN Magnetic Contact Switch — Verified Reference

| | |
|---|---|
| Product code | `WS301` (Milesight model). Cytron code `LR-WS301`, MPN `WS301-915M` [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight WS301 datasheet PDF (3 pages, read in full) and WS301 User Guide V1.4 (Apr 22, 2026; hardware overview, LED table, power/battery, NFC access, LoRaWAN and general settings, installation, payload read) |
| Primary source | Milesight *WS301 Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/ws301-datasheet-en.pdf [DS] |

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
| Detection distance (sensor–magnet) | 20 mm | [DS] |
| Buttons | 1 × reset (internal), 1 × tamper button | [DS] |
| LED | 1 × status/alarm indicator | [DS] |
| Configuration | NFC via mobile app (Milesight ToolBox) | [DS] |
| Advanced | Milesight D2D controller, tamper alarm, open/close status alarm | [DS] |
| Power supply | 1 × 1200 mAh ER14250 Li-SOCl₂ | [DS] |
| Battery life (1080 min interval + 30 triggers/day, 25 °C, lab) | ~6.8 years (SF7, EU868 and US915); ~4.2 years (SF10, EU868); ~3.5 years (SF10, US915) | [DS] |
| Reporting interval | Default 1080 min (1–1080); alarms sent on every magnet or tamper change; low-battery uplink once at 1 % | [UM] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Humidity | ≤ 90 % non-condensing | [DS] |
| Ingress protection | IP20 | [DS] |
| Dimensions | Sensor 50.5 × 31 × 19 mm; magnet 50.5 × 13.5 × 13 mm | [DS] |
| Weight | Sensor 27.9 g with battery; magnet 13.7 g | [DS] |
| Colour | White | [DS] |
| Installation | Flat surfaces with screws or 3M tape | [DS] |
| Regulatory | CE, FCC, Telec, LoRaWAN Certified, ISED; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WS301 LoRaWAN® Magnetic Contact Switch"; brand Milesight; Code `LR-WS301`; MPN `WS301-915M`; warranty 12 months; RM223.85; Availability: Enquiry [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1" [PP].
- Cytron spec list: reed switch / magnetic contact; detection distance 15–20 mm; Class A + D2D; 2 km urban / 15 km rural; NFC, downlink, FUOTA; 1 × 1200 mAh ER14250; ≥ 4 years; tamper switch; status LED; ABS + PC (UL94 V0), "IP30"; -20 to +60 °C; 50.5 × 31 × 13.5 mm (see *Conflicts*) [PP].
- D2D: "gateway-free communication with secondary controllers (e.g., HVAC units or light switches) in < 1 second" [PP].
- **Packing list:** 1 × WS301 device, 3 × mounting screws, 1 × warranty card, 1 × quick guide card [PP][UM]. No 3M tape is listed.
- **Resources:** WS301 datasheet, WS301 user guide, payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No wired interfaces [DS].
| Event / action | LED | Src |
|---|---|---|
| Power on (pull the battery insulating sheet) | Green for 3 s | [UM] |
| Open/close change, not joined / joined | Red blinks once / green blinks once | [UM] |
| Join request / joined | Red blinks once / green blinks twice | [UM] |
| Tamper: un-installed / installed | Red blinks once / green blinks once | [UM] |
| Hold internal reset > 3 s / > 10 s | Reboot (slow blink) / factory reset (quick blink) | [UM] |

Sensor parts: NFC detection area, LED, mounting holes, tamper button (on the back), induction area. Magnet parts: induction area, mounting holes [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Sensor on the fixed frame, magnet on the moving door/window**; for double doors put one part on each leaf [UM].
- **Notched sides face each other**; gap ≤ 20 mm and height offset < 20 mm, or open/close sensing becomes unreliable [UM].
- **Tamper:** the tamper button on the back reports "un-installed" when the sensor is removed from its surface [UM].
- **3M tape (bought separately, not in the box):** clean with alcohol, apply at 20–40 °C (pre-warm tape to ~30 °C in the cold), press ≥ 30 s, cure 24 h; otherwise use the screws [UM][PP].
- **LoRaWAN:** OTAA is required for Milesight Development Platform; a default AppKey is set at the factory (see the user guide; not copied) — ask the seller for random keys if needed. Region must match the gateway (Cytron: AS923-2 Malaysia); for US915/AU915 with Milesight gateway defaults use channel index 8-15 [UM][PP]. Pair with `milesight-ug65.md` / `milesight-ug56.md`.
- Payload (little-endian): battery `01 75` (%), magnet `03 00` (**00 = switch close, 01 = switch open**), tamper `04 00` (00 installed / 01 un-installed); downlink port 85: reboot `ff10ff`, report interval `ff03` (s) [UM].

## Power and electrical limits
- 1 × ER14250 Li-SOCl₂ 1200 mAh only — **not alkaline**; replace with a new cell; remove for long storage; open the back cover with a flat screwdriver [UM].
- Battery life ~3.5–6.8 years depending on SF and plan (1080 min interval + 30 triggers/day) [DS].
- -20 to +60 °C, ≤ 90 % RH, **IP20** — indoor, dry locations only [DS].

## Software support
- Milesight IoT Cloud and Milesight Development Platform [DS].
- Decoders: GitHub `Milesight-IoT/SensorDecoders` [UM][PP].

## Compatibility and accessories
- LoRaWAN gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- D2D agents (e.g. `milesight-ws50x.md`, `milesight-ws558-ln.md`) can be triggered by open/close (inferred from the D2D controller role) [DS].
- 3M tape is not in the box [PP][UM].
- Related: `milesight-em300-mcs.md` (IP67 contact switch with temperature/humidity), `milesight-ws101.md` (smart button).

## Common mistakes / troubleshooting
- **Always "open":** gap > 20 mm or notches not aligned [UM].
- **Tamper alarm on install:** the back must sit flat so the tamper button is pressed [UM].
- **Falls off the door:** wrong surface or temperature for 3M tape; use screws [UM].
- **Inverted logic in a dashboard:** 00 = closed, 01 = open [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Ingress protection | [DS] IP20 | [PP] IP30 | [DS] wins |
| Dimensions | [DS] sensor 50.5 × 31 × 19 mm; magnet 50.5 × 13.5 × 13 mm | [PP] 50.5 × 31 × 13.5 mm | [DS] wins |
| Detection distance | [DS] 20 mm | [PP] 15–20 mm | [DS] wins (max 20 mm) |
| Battery life | [DS] ~3.5–6.8 years; [DS]/[UM] text "more than 5 years" | [PP] "≥ 4 years" | [DS] table wins |
| FUOTA | [PP] FUOTA support | [DS] not listed; [UM] upgrade via ToolBox | Not confirmed by [DS]; *Needs verification* |
| Housing | [PP] ABS + PC (UL94 V0) | [DS] colour only | [PP] only; *Needs verification* |
| Frequency plans | [DS] "AS923" | [PP] AS923-2 / AS923-1, MPN `WS301-915M` | Not a contradiction; confirm AS923-2 on the 915M build |

## Needs verification
- That Cytron's `WS301-915M` units ship set to AS923-2.
- FUOTA support and housing material [PP only].
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight WS301 Datasheet: https://resource.milesight.com/milesight/iot/document/ws301-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight WS301 User Guide V1.4 (Apr 22, 2026): https://resource.milesight.com/milesight/iot/document/ws301-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight WS301 page: https://www.milesight.com/iot/product/lorawan-sensor/ws301; decoders: https://github.com/Milesight-IoT/SensorDecoders
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ws301-lorawan-magnetic-contact-switch (read 2026-10-21).
