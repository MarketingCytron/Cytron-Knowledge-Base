# Milesight VS330 LoRaWAN Bathroom Occupancy Sensor — Verified Reference

| | |
|---|---|
| Product code | `VS330` (Milesight model). Cytron code `LR-VS330`, MPN `VS330-915M` [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight VS330 datasheet PDF (4 pages, read in full) and VS330 User Guide V1.0 (Jan 12, 2023; packing list, button/LED, NFC, LoRaWAN settings, basic settings, reset, installation, payload read) |
| Primary source | Milesight *VS330 Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/vs330-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Protocol | LoRaWAN, internal antenna | [DS] |
| Frequency plans (model) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 19 dBm (470 MHz) / 22 dBm (915 MHz) | [DS] |
| Sensitivity | -137 dBm | [DS] |
| Mode | OTAA / ABP Class A; LoRaWAN V1.0.2 or V1.0.3 | [DS][UM] |
| Application port | Default 85 | [UM] |
| ToF | FoV 27°; range 0.040–3.500 m; accuracy ±2 cm; resolution 1 mm | [DS] |
| PIR | Detection area 80°; distance max 2.5 m | [DS] |
| Sensor angle | Adjustable 0°, 15°, 30°, 45°, 60°, 75° | [DS] |
| Accuracy | "exceeding 99.5%" (overview); "over 99%" (features) | [DS] |
| LED / button | 1 × status/test indicator; 1 × power/reset button | [DS] |
| Power on/off, configuration | Mobile app via NFC, or power button | [DS] |
| Power supply | 3 × 4000 mAh ER18505 Li-SOCl₂ replaceable batteries | [DS] |
| Battery life (90 users, within 7 consecutive hours per day; lab test) | ~4.2 years (SF7, EU868 & US915); ~3.4 years (SF10, EU868); ~3.3 years (SF10, US915) | [DS] |
| Reporting interval | Default 1080 min; range 1–1080 min; also reports on every occupancy change | [UM] |
| Occupancy update | PIR triggers first, then ToF samples at 5 s intervals | [PP] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Humidity | 0–95 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Dimensions | Ø100 × 24 mm | [DS] |
| Housing | PC + ABS (flame retardant), white | [DS] |
| Weight | 150 g with batteries | [DS] |
| Installation | Ceiling or wall, screws or 3M tape | [DS] |
| Regulatory | CE, FCC, Telec; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "VS330 LoRaWAN Bathroom Occupancy Sensor"; brand Milesight; Code `LR-VS330`; MPN `VS330-915M`; warranty 12 months; RM387.45; Availability: Enquiry (INQUIRE NOW) [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1"; Tx power 22 dBm [PP]. The MPN is the 915 MHz hardware build (Milesight's 915M build covers the 915 MHz-band plans incl. AS923 — inferred from the Tx power table; see *Needs verification*).
- Spec list matches [DS] (ToF 27°, 0.04–3.5 m, ±2 cm; PIR 80°, 2.5 m; 0–75° in 15° steps; 3 × ER18505; IP30; Ø100 × 24 mm) except battery life "around 4 years" (see *Conflicts*) [PP].
- Description: PIR + ToF reconfirmation and self-calibration; "minimum of 4 years" battery; conformal coating; range "up to 2 km in urban areas and 15 km in rural areas"; Milesight IoT Cloud with app [PP].
- **Packing list:** 1 × VS330 sensor, 2 × wall mounting kits, 1 × mirror cleaning cloth, 1 × quick start guide, 1 × warranty card [PP][UM].
- **Resources:** datasheet, user guide, accuracy report (resource.milesight.com PDFs), payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No wired interfaces; NFC for configuration [DS].
| Action (power button) | Result / LED | Src |
|---|---|---|
| Hold > 3 s | Power on (LED off → on) / power off (on → off) | [UM] |
| Quick press | Shows on/off status (light on = device on) | [UM] |
| Hold > 10 s | Reset to factory default (LED blinks quickly); the reset button is inside the device | [UM] |
| Test mode (enabled in app, lasts 10 min) | LED blinks twice on each occupied ↔ vacant change | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **LoRaWAN keys:** a default AppKey (and ABP session keys) are set at the factory (see the user guide; not copied); Milesight changed the default AppKey scheme in Q4 2025. Change them, or ask the seller for random keys before purchase [UM]. Device EUI is on the label [UM].
- **Use OTAA for Milesight IoT Cloud**; only OTAA supports rejoin mode [UM]. Region and channels must match the gateway (Cytron: AS923-2 for Malaysia) [UM][PP]. Pair with `milesight-ug65.md` or `milesight-ug56.md`.
- **Ceiling mount:** 2.5–3 m high, sensor facing the front of the toilet, sensor angle 0°, centre 10–20 cm from the toilet centre [UM].
- **Wall mount:** on the wall behind the toilet, sensor facing down, above the standing toilet-lid height; do not aim at the door or include the door in the detection area [UM].
- Use **test mode** to check that opening/closing the door does not change the result; adjust "People Existing Height" (default 12 cm, 10–50 cm) if needed [UM].
- Avoid sunlight and IR LEDs in view, glass and mirrors; remove the protective film; keep the lens clean with the supplied cloth [UM].
- Payload (little-endian): battery `01 75` (%), distance `02 82` (mm, INT16), occupancy `03 8e` (00 vacant / 01 occupied), calibration `04 8e` [UM]. Decoders: GitHub `Milesight-IoT/SensorDecoders` [UM][PP].

## Power and electrical limits
- 3 × ER18505 Li-SOCl₂ 4000 mAh, replaceable [DS].
- Battery life ~4.2 years at SF7 (EU868/US915), ~3.3–3.4 years at SF10, for 90 users within 7 hours a day (lab estimate) [DS].
- -20 to +60 °C, 0–95 % RH, IP30 — not for wet spray zones [DS][UM].

## Software support
- Downlinks (port 85): collecting interval, reporting interval, reboot, people-existing height, test mode [UM].
- Milesight IoT Cloud (add by SN with a Milesight gateway online) [UM].

## Compatibility and accessories
- Needs a LoRaWAN gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- Optional dedicated NFC reader from Milesight (not sold on the Cytron page) [UM].
- Related occupancy sensors: `milesight-vs370.md` (radar presence), `milesight-ws202.md` (PIR + light), `milesight-gs301.md` (bathroom odour detector).

## Common mistakes / troubleshooting
- **NFC read fails:** remove the phone case, move the phone away and back [UM].
- **Door causes false occupied:** re-aim so the door is outside the detection area; check with test mode [UM].
- **Poor accuracy over time:** dust or fingerprints on the lens — clean with the mirror cloth [UM].
- **No join:** OTAA keys/region must match the network server and gateway [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [DS] ~4.2 years (SF7), 3.3–3.4 years (SF10) | [PP] "around 4 years", "minimum of 4 years" | [DS] wins; 4 years is only at SF7 |
| Accuracy | [DS] features "over 99%", overview "exceeding 99.5%" | [PP] "over 99.5%" | Inside [DS]; quote "over 99%" conservatively |
| MPN vs plan | [PP] MPN `VS330-915M` | [PP] "AS923-2 / AS923-1" | Not a contradiction if the 915M build is set to AS923 (inferred); confirm with Cytron |
| Rotation on mounting plate | [UM] up to 15° rotation on the plate | [DS] sensor angle 0–75° | Different adjustments: plate twist vs probe tilt |

## Needs verification
- That Cytron's `VS330-915M` units ship set to AS923-2 (inferred possible from the 915 MHz hardware).
- Accuracy report details (PDF linked, not opened).
- Datasheet version/date (none printed).

## Sources
- [DS] Milesight VS330 Datasheet: https://resource.milesight.com/milesight/iot/document/vs330-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight VS330 User Guide V1.0 (Jan 12, 2023): https://resource.milesight.com/milesight/iot/document/vs330-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight VS330 page: https://www.milesight.com/iot/product/lorawan-sensor/vs330; accuracy report: https://resource.milesight.com/milesight/iot/document/vs330-accuracy-report-en.pdf (not opened).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-vs330-lorawan-bathroom-occupancy-sensor (read 2026-10-21).
