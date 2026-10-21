# Milesight EM500-UDL — Verified Reference

| | |
|---|---|
| Product code | `EM500-UDL` (Milesight model) in two Cytron listings: **W050** — Cytron code `LR-EM500-UDL-W050`; **W100** — Cytron code `LR-EM500-UDL-W100`. No MPN is shown on either page [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: both Cytron product pages (W050 and W100: price, stock, code, description, features, specification, packing list, resources, FAQ), Milesight product page (download links), EM500-UDL datasheet (full, incl. beam-pattern page viewed as an image) and EM500-UDL user guide V2.2.1 (hardware overview figure, power button, NFC/USB access, LoRaWAN and general settings, threshold, D2D, maintenance, installation, battery replacing, uplink) read |
| Primary source | *EM500-UDL Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em500-udl-datasheet-en.pdf (no version/date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = EM500-UDL datasheet PDF. [UM] = *EM500-UDL User Guide* V2.2.1 (15 Aug 2024; V1.0 23 Nov 2020, V2.0 11 Apr 2022 for hardware v2.x, V2.1 31 May 2023, V2.2 29 Mar 2024), https://resource.milesight.com/milesight/iot/document/em500-udl-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em500-udl. [PP: W050] / [PP: W100] = the two Cytron product pages; [PP] = both.

## What it is

**The two Cytron listings are two range variants of the same product** [DS][PP]:
| Variant | Range | Accuracy | Operating temp. | Cytron code | Price |
|---|---|---|---|---|---|
| **W050** | **0.3 – 5 m** | ± 1 % FS | -30 °C to +65 °C | `LR-EM500-UDL-W050` | RM1,851.15 |
| **W100** | **0.5 – 10 m** | ± 1 % FS | -30 °C to +65 °C | `LR-EM500-UDL-W100` | RM1,980.30 |

Pick W050 for tanks and pits up to 5 m (smaller dead zone, 30 cm); W100 for deeper wells, rivers or silos up to 10 m (dead zone 50 cm). Both W models support temperature compensation and suit direct sun or large temperature swings (Cytron FAQ) [PP: W050]. Milesight also makes C050/C100 variants (0.25–5 m / 0.25–10 m, ± (1 + 0.3 % × S) cm, -15 ~ 60 °C), which Cytron does not list [DS].

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensing | Ultrasonic, non-contact distance or level | [DS] |
| Range & accuracy | W050: 0.3 – 5 m, ± 1 % FS; W100: 0.5 – 10 m, ± 1 % FS (C050: 0.25 – 5 m and C100: 0.25 – 10 m, ± (1 + 0.3 % × S) cm — not sold by Cytron) | [DS] |
| Blind zone | Below the minimum range: 0.3 m (W050), 0.5 m (W100) (inferred from the range; readings outside the range are reported as 0xFFFD) | [DS][UM] |
| Resolution | 1 mm | [DS] |
| Beam | Beam-pattern charts only (C050/C100 polar plot; W050/W100 "typical beam pattern for 30 cm target"); no angle in degrees stated | [DS] |
| Wireless | LoRaWAN, Milesight D2D; internal antenna | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP, Class A; LoRaWAN V1.0.2 / V1.0.3; port 85 | [DS][UM] |
| LED / button / USB | 1 × LED (internal); 1 × power/reset button (internal); 1 × USB Type-C (internal) for configuration and console | [DS] |
| Configuration | Mobile app (NFC), PC software (USB Type-C), downlink | [DS] |
| Advanced features | Data storage (1,000 entries), data retransmission, data retrievability, threshold alarm, change alarm, Milesight D2D controller | [DS] |
| Power supply | 1 × 19000 mAh ER34615 Li-SOCl2 battery (replaceable; alkaline not supported) | [DS][UM] |
| Battery life | 10 years (10 min interval, 25 °C; lab figure with Milesight's standard battery) | [DS] |
| Operating temperature | W050/W100: -30 °C to +65 °C | [DS] |
| Relative humidity | 0 % to 80 % (non-condensing) | [DS] |
| Ingress protection | IP67 | [DS] |
| Housing / colour | ABS + PC; grey (W050/W100) | [DS] |
| Weight | W050/W100: 370.4 g (with battery and mounting bracket) | [DS] |
| Dimension | 156.1 × 71 × 69.5 mm | [DS] |
| Installation | Pole, wall or DIN-rail mounting | [DS] |
| Approvals | CE, FCC, ISED, Telec, LoRaWAN Certified; EMC EN 55032/55035; EMS IEC 61000-4-2 L3, -4-3 L2, -4-8 L4; RF FCC Part 15B/15.247, EN 300 330, EN 301 489-1/3, EN 300 220-1/2; safety EN62368-1; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- **W100 page:** title "EM500-UDL Ultrasonic Distance / Level Sensor (W100)"; Code `LR-EM500-UDL-W100`; warranty 12 months; RM1,980.30; "Enquiry"/INQUIRE NOW. Spec: 0.5–10 m, ±1 % FS, 1 mm, AS923-2 (Malaysia) / AS923-1 (Singapore), Tx 16/20/19 dBm, -137 dBm, internal antenna, NFC/USB-C/downlink, 19,000 mAh ER34615, up to 10 years, -30 ~ +65 °C, 0–80 % RH, IP67, ABS + PC, 156.1 × 71 × 69.5 mm, 370.4 g, pole/wall/DIN rail. Features list "up to 10 km (line of sight)". **Packing list:** 1 × EM500 device, 4 × wall mounting kit, 4 × screw caps, 2 × fixing screw, 1 × hose clamp, 1 × quick guide, 1 × warranty card, 1 × DIN rail clip kit. Resources: EM500-UDL datasheet and **EM500-UDL user guide**, decoder, firmware link (milesight.com/support/resources/firmware) [PP: W100].
- **W050 page:** title "EM500-UDL Ultrasonic Distance / Level Sensor (W050)"; Code `LR-EM500-UDL-W050`; warranty 12 months; RM1,851.15; "Enquiry"/INQUIRE NOW. Spec: W050 0.3–5 m, ±1 % FS, 1 mm, AS923-2/AS923-1, NFC/power button, USB-C, D2D controller, 19000 mAh ER34615, 10 years (10 min, 25 °C), -30 ~ +65 °C, 0–80 % RH, IP67, ABS + PC, grey, 370.4 g. **Packing list:** 1 × EM500-UDL (W050) only. Resources link the generic **EM500 series user guide** (em500-series-user-guide-en.pdf) [PP: W050].
- **W050 FAQ** (Cytron page): use W050/W100 for direct sun or large temperature differences (temperature compensation); not suggested for septic tanks with ammonia or methane (probe corrosion, explosion-proof requirements); suits most liquids and hard solids — for snow use EM500-UDL-S050; "detection range is about 60° in front of ultrasonic probe" and container radius should be more than 30 cm [PP: W050].

## Interfaces, terminals and pin mapping
No external terminals or probe cable: the ultrasonic horn is part of the unit [UM figure]. Inside the enclosure: power button, LED, **USB Type-C** (configuration/console, reached by removing the enclosure) [DS][UM]. NFC area on the front [UM figure].

**Power button (internal)** [UM]
| Function | Action | LED |
|---|---|---|
| Power on | Press and hold > 3 s | Off → On |
| Power off | Press and hold > 3 s | On → Off |
| Reset to factory default | Press and hold > 10 s | Blinks quickly |
| Check on/off | Quick press once | On = device on; off = device off |

**Uplink** [UM ch. 7] (little-endian): 01 75 battery % (on join and every 24 h; low-battery alarm at 1 %); **03 82 distance, UINT16, mm**; 83 e9 distance-shift alarm (distance + shift + 02); 20 ce historical data (timestamp + distance); ff 1b measuring range. **0xFFFF = failed to collect; 0xFFFD = outside measuring range.** Downlink port 85: reboot, collect interval, re-collect, report interval, data storage/retransmission, time zone, device time, LNS sync [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Mount vertically on top of the object** with a clear path to it [UM ch. 5].
- **Keep more than 30 cm from the side wall** with no internal obstructions in the beam [UM]; Cytron FAQ: container radius more than 30 cm [PP: W050].
- **Do not mount in the centre of arched or circular tank tops** (multiple echoes) and **not above the inlet** [UM ch. 5].
- **Respect the blind zone:** the target must stay farther than 0.3 m (W050) or 0.5 m (W100) from the horn face; plan the mounting height so the maximum level never enters it (inferred from [DS] ranges).
- **Mounting:** wall (two holes + plugs, bracket screws, two fixing screws), pole (hose clamp through the bracket slots), or **DIN rail (35 mm) with the clip kit fixed by 2 × M3 × 6 flat-head screws** [UM]. Keep the transceiver away from metal for radio range [UM].
- **Default reporting interval 10 min** (range 1–1080 min); the collect interval should be shorter than the reporting interval [UM].
- **Data storage** needs time sync (ToolBox app or LNS DeviceTimeReq with LoRaWAN V1.0.3); ToolBox exports at most the last 14 days. Retransmission requires storage enabled and shortens battery life; default retransmission interval 600 s [UM].
- **D2D controller mode:** sends a 2-byte command to Milesight D2D agents on threshold events without a gateway; a default D2D key is set at the factory (see the user guide; not copied) — set your own [UM].
- **Not for ammonia/methane septic tanks or hazardous areas**; for snow use the S050 model (not sold by Cytron) [PP: W050 FAQ].
- **Frequency plan:** Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].

## Power and electrical limits
- One ER34615 Li-SOCl2 19000 mAh battery; replace by removing the bottom cover; alkaline not supported; use a new battery; remove it for long storage [UM ch. 6].
- 10 years at 10-min interval, 25 °C (lab) [DS].
- W050/W100 -30 ~ +65 °C, 0–80 % RH non-condensing, IP67 [DS].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB Type-C); firmware upgrade via either [UM].
- Standard LoRaWAN gateways/network servers; Milesight IoT Cloud and Milesight Development Platform (OTAA required) [DS][UM].
- Decoders: github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Related level sensors: `milesight-em410-rdl.md` (60 GHz radar, 0.3–12 m, IP68, better for foam/steam), `milesight-em400-mud.md` (bins/parking, 3–450 cm).
- Same EM500 body family: `milesight-em500-pp.md`, `milesight-em500-pt100.md`, `milesight-em500-smtc.md`, `milesight-em500-co2.md`.
- Mounting kit, hose clamp and DIN clip kit per the W100 page and Milesight's list (DIN clip "optional" in [UM]) [PP: W100][UM].

## Common mistakes / troubleshooting
- **Reads 0xFFFD:** target is inside the blind zone or beyond the range — check mounting height vs the variant's range [UM][DS].
- **Reads 0xFFFF:** sensor collection failed [UM].
- **Unstable readings:** mounted near a wall (< 30 cm), at the centre of a domed lid, or above the inlet stream [UM].
- **Stored data has wrong timestamps:** time not synced [UM].
- **Wrong variant ordered:** W050 cannot measure beyond 5 m; W100 cannot measure closer than 0.5 m [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plans | [DS] CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" | Not a contradiction: [PP] names the plans Cytron supplies |
| Packing list | [PP: W100] and [UM]: device with bracket, 4 wall kits, 4 screw caps, 2 fixing screws, hose clamp, DIN clip kit, quick guide, warranty card | [PP: W050]: 1 × sensor only | Use [UM]/[PP: W100]; confirm with Cytron that W050 ships with the same kit |
| User guide linked | [PP: W100]: EM500-UDL user guide | [PP: W050]: generic EM500 series user guide | Use the EM500-UDL user guide [UM] |
| Beam / detection angle | [DS]: beam-pattern charts only, no angle | [PP: W050] FAQ "about 60° in front of ultrasonic probe" | No [DS] figure in degrees; 60° stays in *Needs verification* |
| Availability | Brand listing cards: OUT OF STOCK | Product pages: "Enquiry", INQUIRE NOW | Treated as out of stock |

## Needs verification
- Beam angle in degrees for W050/W100 (Cytron FAQ "about 60°"; [DS] gives charts only).
- Whether the W050 listing includes the mounting kit, hose clamp and DIN clip kit.
- Exact Milesight part numbers/MPNs for Cytron's units (no MPN shown) and the frequency band hardware.
- Which AS923 sub-plan Malaysian deployments use (Cytron says AS923-2).

## Sources
- [DS] EM500-UDL Datasheet: https://resource.milesight.com/milesight/iot/document/em500-udl-datasheet-en.pdf (read 2026-10-21)
- [UM] EM500-UDL User Guide V2.2.1: https://resource.milesight.com/milesight/iot/document/em500-udl-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em500-udl
- [PP: W100] https://my.cytron.io/Milesight/p-em500-udl-ultrasonic-distance-level-sensor-w100 (read 2026-10-21)
- [PP: W050] https://my.cytron.io/Milesight/p-em500-udl-ultrasonic-distance-level-sensor-w050 (read 2026-10-21)
