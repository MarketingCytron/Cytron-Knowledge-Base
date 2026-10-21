# Milesight GS301 — Verified Reference

| | |
|---|---|
| Product code | `GS301` (Milesight model). Cytron code `LR-GS301`, MPN shown as `GS301-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight GS301 product page (features, specification tab, documents), GS301 datasheet (full, 4 pages) and GS301 user guide V1.1 (full, 36 pages) read |
| Primary source | *GS301 Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/gs301-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Protocol | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 19 dBm (470 MHz) / 22 dBm (915 MHz) | [DS] |
| Sensitivity | -137 dBm | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A (fixed); V1.0.2 / V1.0.3 | [DS][UM] |
| NH3 | Solid polymer electrochemical; 0–10 ppm; ±5 % FS (-40 to 35 °C); drift < 1 %/month; resolution 0.01 ppm | [DS] |
| H2S | Solid polymer electrochemical; 0–5 ppm; ±5 % FS (-40 to 35 °C); drift < 1 %/month; resolution 0.001 ppm | [DS] |
| Temperature | -40 to 85 °C; ±0.2 °C; 0.1 °C | [DS] |
| Humidity | 0–100 %RH; ±2 %; 0.5 %RH | [DS] |
| LED & buzzer | 1 × status/alarm indicator + 1 × buzzer | [DS] |
| Button | 1 × reset/reboot (power) button, external | [DS] |
| Configuration | Mobile app (Milesight ToolBox) via NFC; downlink | [DS][UM] |
| Advanced features | Milesight D2D controller, threshold alarm | [DS] |
| Power supply | 4 × 4000 mAh ER18505 Li-SOCl2, replaceable | [DS] |
| Sensor life | > 3 years | [DS] |
| Battery life | Around 3 years (10 min interval, 25 °C) | [DS] |
| Operating temperature | -40 °C to 55 °C | [DS] |
| Relative humidity | 0–95 % (non-condensing) | [DS] |
| Ingress protection | IP30 | [DS] |
| Housing | PC + ABS (flame retardant), white; damp-proof coating inside | [DS] |
| Weight | 221.4 g with batteries | [DS] |
| Dimensions | 120 × 85 × 32.5 mm | [DS] |
| Installation | Wall screw mounting (bracket) | [DS][UM] |
| Approvals | CE, FCC; EN62368(-1); RoHS | [DS][DS: web] |
| Default reporting interval | 10 min (1–1080 min) | [UM] |
| Sensor warm-up | About 30 min polarisation after power-on or reboot before NH3/H2S data | [UM] |
| In the box (Milesight) | 1 × GS301, 2 × wall mounting kits, 1 × quick guide, 1 × warranty card | [UM] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "GS301 LoRaWAN Bathroom Odor Detector"; brand Milesight; Code `LR-GS301`; MPN `GS301-915M`; warranty 12 months; RM2,023.35; availability "Enquiry" (INQUIRE NOW); product video present [PP].
- **No frequency plan is stated on this page** (unlike other Milesight listings) [PP].
- Spec block: NH3 0–10 ppm, ±5 % (-40–35 °C), 0.01 ppm; H2S 0–5 ppm, ±5 %, **0.01 ppm**; temperature -40–85 °C, ±0.2 °C, **0.01 °C**; humidity 0–100 %RH, ±2 %, 0.5 %; 4 × ER18505; up to 3 years at 10 min; LoRaWAN & D2D; NFC; IP30; -40–55 °C; 0–95 %RH; 120 × 85 × 32.5 mm; flame-retardant PC+ABS, white; wall-mounted [PP].
- Features: buzzer and LED "traffic light" status indicator; damp-proof coating; for commercial buildings, malls, hospitals, airports, public restrooms [PP].
- **Packing list:** 1 × GS301 LoRaWAN Bathroom Odor Detector [PP].
- **Resources:** GS301 datasheet, GS301 user guide, Payload Decoder (GitHub), Firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No wiring: battery-powered, no terminals or external power input [DS].

**Button and LED** [UM]
| Function | Action | LED |
|---|---|---|
| Power on / off | Hold power button > 3 s | Off → green on / green on → off |
| Check status | Short press | Green blinks once = on; off = off |
| Reset to factory default | Hold > 10 s | Green blinks quickly |
| Threshold alarm | NH3 or H2S over threshold | Red blinks quickly (with buzzer if enabled) |

**Uplink payload (port 85)** [UM]: battery 01 75 (UINT8 %); temperature 02 67 (INT16/10 °C); humidity 03 68 (UINT8/2 %RH); NH3 04 7d (UINT16/100 ppm); H2S 06 7d (UINT16/1000 ppm; older firmware used 05 7d with /100); value ffff/ff = collection error, fffe = polarising. Sensor ID string ff 7c (not sent at SF10 or higher on US915/AU915/AS923). Decoders: https://github.com/Milesight-IoT/SensorDecoders.

## Rules and gotchas (for code, wiring and tutorials)
- **Wait ~30 minutes after power-on or reboot** — NH3/H2S show "Polarizing" until the electrochemical cells settle; temperature and humidity report normally [UM].
- **Above 35 °C, alarms stop.** LED, buzzer, threshold alarm and D2D are disabled while temperature is above 35 °C and resume at 35 °C or below [UM]. Milesight recommends operation below 35 °C [VEN].
- **Indoor, IP30.** Do not install outdoors, near heat/sunlight, in dusty places, beside doors/windows/vents/fans, or where alcohol, perfume, air fresheners, hair spray or paint are sprayed [UM]. Mount at breathing height, about 6.5–8.2 ft (≈2.0–2.5 m) above the floor [UM]. Ventilate newly decorated rooms before installing [UM].
- **Sensor life 3 years** — replace the device after that; a downlink enquiry reports normal / close to end / end of life [UM].
- **Buzzer stops by itself** when both gases fall below threshold; to silence it earlier, disable the buzzer [UM].
- **Zero-point calibration** of NH3/H2S (in clean air) needs sensor module version 1.1.2.7 or later [UM].
- **Frequency plan:** the Cytron page names none; MPN -915M implies 915 MHz-band hardware (inferred). Set the plan to match the gateway [UM].
- Do not paint or cover the unit; wipe with a dry cloth only — no wet cloth, alcohol or detergents [UM].

## Power and electrical limits
- 4 × 4000 mAh ER18505 Li-SOCl2 only; alkaline not supported; replace all cells with new ones [DS][UM].
- About 3 years at 10 min reporting, 25 °C [DS]. Low-battery alarm at 1 % [UM].
- Operating -40 °C to 55 °C, 0–95 %RH; storage/transport keep within 35 °C (not over 55 °C) and ≥ 15 %RH [DS][UM].

## Software support
- Milesight ToolBox (NFC): LoRaWAN settings, reporting interval, LED and buzzer enable, thresholds for NH3/H2S with exceed-threshold reporting interval, numerical calibration (T/H), zero-point calibration (NH3/H2S), D2D, backup/restore, reset, upgrade (Android only) [UM].
- D2D controller: sends a 2-byte command for "abnormal odour" (either gas over its value) and "normal odour" (both at or below) — for direct fan/ventilation control [UM].
- Platforms: Milesight IoT Cloud (OTAA required) and standard LoRaWAN network servers [DS][UM].
- [UM] appendix gives odour-level guidance bands for NH3 (e.g. 2–10 ppm "strong") and H2S (0.06–0.7 ppm "strong").

## Compatibility and accessories
- LoRaWAN gateway/network server, e.g. `milesight-ug65.md`, `milesight-ug56.md` [VEN].
- D2D agent devices (e.g. a Milesight controller or switch driving an exhaust fan) — see their own files.
- Milesight's iBox Smart Restroom Kit includes GS301 (not sold by Cytron) [VEN].

## Common mistakes / troubleshooting
- **NH3/H2S read "Polarizing" or fffe:** wait ~30 min after power-up [UM].
- **No alarm on a hot day:** above 35 °C the alarm functions pause [UM].
- **High readings after cleaning or decorating:** solvent, aerosol or paint vapours; ventilate first [UM].
- **No join:** plan mismatch or OTAA keys missing on the network server [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| H2S resolution | [DS] 0.001 ppm ([UM] V1.1 added 0.001 ppm reporting) | [PP] 0.01 ppm | [DS]: 0.001 ppm |
| Temperature resolution | [DS] 0.1 °C | [PP] 0.01 °C | [DS]: 0.1 °C |
| Gas accuracy | [DS] ±5 % FS | [PP] ±5 % | [DS]: ±5 % of full scale |
| Packing list | [UM] GS301, 2 × wall mounting kits, quick guide, warranty card | [PP] GS301 only | [UM] for Milesight's box; confirm Cytron's |
| Frequency plan | [DS] full list | [PP] none stated (MPN -915M) | Ask Cytron which plan the stock is set for (normally AS923 in Malaysia) |

## Needs verification
- Frequency plan of Cytron's stock (page states none).
- Cytron box contents (mounting kit included?).
- Whether the 3-year sensor life is covered by Cytron's 12-month warranty only.
- Datasheet version/date (none printed).

## Sources
- [PP] https://my.cytron.io/Milesight/p-gs301-lorawan-bathroom-odor-detector — read 2026-10-21
- [DS] https://resource.milesight.com/milesight/iot/document/gs301-datasheet-en.pdf — read in full 2026-10-21
- [DS: web] / [VEN] https://www.milesight.com/iot/product/lorawan-sensor/gs301 — read 2026-10-21
- [UM] https://resource.milesight.com/milesight/iot/document/gs301-user-guide-en.pdf — V1.1, 18 Dec 2024, read in full 2026-10-21
