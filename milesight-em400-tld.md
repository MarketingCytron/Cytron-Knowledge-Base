# Milesight EM400-TLD — Verified Reference

| | |
|---|---|
| Product code | `EM400-TLD` (Milesight model). Cytron code `LR-EM400-TLD`, MPN shown as `EM400-TLD-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features/specification, packing list, resources), Milesight product page (download links), Milesight EM400-TLD datasheet (full, 4 pages) and user guide V1.1 (hardware, power button, NFC, settings, threshold, maintenance, installation, LoRaWAN uplink) read |
| Primary source | *EM400-TLD Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em400-tld-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight EM400-TLD datasheet PDF (no version/date printed). [UM] = *EM400-TLD User Guide*, Milesight, V1.1 (15 Jun 2023; V1.0 23 Feb 2023), https://resource.milesight.com/milesight/iot/document/em400-tld-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em400-tld. [PP] = Cytron product page. Hardware-overview and dimension drawings were not read as text.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensing principle | ToF (time of flight) laser | [DS] |
| ToF field of view | 27° | [DS] |
| Detection range | 2 ~ 350 cm | [DS] |
| Blind zone | "Extremely short blind zone" / "almost no blind spot" (no figure; below 2 cm inferred from the range limit) | [DS] |
| Detection accuracy | ± 2 cm (-20 °C ~ 70 °C) | [DS] |
| Detection resolution | 1 mm | [DS] |
| Device position | Normal / Tilt (3-axis accelerometer; Tilt = horizontal offset angle ≥ 20°) | [DS][UM] |
| Temperature sensor | NTC; range -40 ~ 125 °C, resolution 0.1 °C | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A; LoRaWAN V1.0.2 / V1.0.3; application port 85 by default | [DS][UM] |
| LED / button | 1 × LED indicator (internal); 1 × power/reset button (internal) | [DS] |
| Power on/off | NFC, internal power button | [DS] |
| Configuration | Mobile app (ToolBox via NFC), downlink | [DS] |
| Advanced features | Threshold alarm, Tilt & Distance switch | [DS] |
| Power supply | 2 × 9000 mAh ER26500 Li-SOCl2 batteries (replaceable) | [DS] |
| Battery life (LoRaWAN, lab conditions) | Standard mode around 10 years (10 min interval, 25 °C); Bin mode around 10 years (20 min interval, 25 °C) | [DS] |
| Operating temperature | -30 °C ~ 70 °C | [DS] |
| Relative humidity | ≤ 95 % (non-condensing) | [DS] |
| Ingress protection | IP67; damp-proof coating inside | [DS] |
| Dimension | 118 × 65 × 30 mm | [DS] |
| Weight | 208.3 g (batteries included) | [DS] |
| Housing | ABS + PC (UL94 V0), black gray | [DS] |
| Installation | On flat surfaces with screws | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM400-TLD LoRaWAN ToF Laser Distance Sensor"; brand Milesight; Code `LR-EM400-TLD`; MPN `EM400-TLD-915M`; warranty 12 months; RM499.40; availability "Enquiry" with INQUIRE NOW; no reviews [PP].
- **Frequency plan on the Cytron page: "Support Malaysia AS923-2, Singapore AS923-1"; Tx Power 20 dBm (915 MHz)** [PP].
- Page spec matches [DS]: FoV 27°, 2–350 cm, ±2 cm (-20 ~ 70 °C), 1 mm, Normal/Tilt, -40 ~ 125 °C / 0.1 °C, 2 × 9000 mAh ER26500, around 10 years in both modes, -30 ~ 70 °C, ≤ 95 % RH, IP67, 118 × 65 × 30 mm, ABS + PC, screw installation [PP].
- **Packing list:** 1 × EM400-TLD device, 2 × mounting kits, 1 × mirror cleaning cloth, 1 × warranty card, 1 × quick guide (same as [UM]) [PP].
- **Resources:** EM400-TLD Datasheet and User Guide (resource.milesight.com), Payload Decoder (github.com/Milesight-IoT/SensorDecoders), Firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No terminals, cables or probes. The ToF lens faces the target; the power/reset button and LED are internal; configuration is by NFC [DS][UM].

**Power button (internal)** [UM §2.4]
| Function | Action | LED indication |
|---|---|---|
| Switch on | Press and hold > 3 s | Off → On |
| Switch off | Press and hold > 3 s | On → Off |
| Reset to factory default | Press and hold > 10 s | Quickly blinks |
| Check on/off status | Quick press | Light on = on; light off = off |

**LoRaWAN uplink channels** [UM §6.1.1] — same layout as EM400-MUD: 01 75 battery %, 03 67 temperature (× 0.1 °C), 04 82 distance (mm), 05 00 position (00 Normal / 01 Tilt), 83 67 and 84 82 threshold alarms (value + status byte). Little-endian. Decoders: github.com/Milesight-IoT/SensorDecoders [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Optical sensor rules:** avoid strong light (direct sunlight, IR LEDs) in the detection area; do not install close to glass or mirrors; **remove the protective film** after installation and adjustment; do not touch the lens; clean dust off the lens with the supplied mirror cleaning cloth [UM §5].
- **Mount level, on top of the object, with a clear path** to it [UM §5].
- **Bin mode sizing:** place in the centre of the bin. Recommended minimum radius: 10 cm for a 40 cm tall bin; 19 cm for an 80 cm tall bin [UM §5].
- **Installation Height (Bin mode):** optional; range 0.02–3.5 m (device to bin bottom). Milesight suggests enabling it when the bin is in strong light and has bags inside; if two readings exceed the installation height, the sensor reports the installation height [UM §4.2].
- **Default reporting intervals (LoRaWAN):** Standard 10 min, Bin 20 min (range 1–1080 min) [UM §4.2].
- **Tilt & Distance switch:** turns off distance measurement when offset > 20° [UM §4.2].
- **Mounting:** two holes through the bin lid, device under the lid, bolts from the other side; or two M4 screws and wall plugs [UM §5].
- **Frequency plan:** match the gateway; Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].
- Firmware upgrade via ToolBox: Android only. Templates only copy between same model and frequency band [UM §4.5].

## Power and electrical limits
- Two ER26500 Li-SOCl2 9000 mAh batteries, replaceable; no external power input [DS].
- Battery life is a lab guideline figure at 25 °C (around 10 years in Standard or Bin mode at default intervals) [DS].
- Operating -30 ~ 70 °C; accuracy is specified over -20 ~ 70 °C [DS].

## Software support
- Milesight ToolBox app (Android/iOS) over NFC, or Milesight's NFC reader [UM].
- Standard LoRaWAN gateways and network servers; Milesight IoT Cloud [DS].
- Payload decoders: github.com/Milesight-IoT/SensorDecoders [PP][UM].

## Compatibility and accessories
- Needs a LoRaWAN gateway on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Related: `milesight-em400-mud.md` (ultrasonic, 3–450 cm, 60° beam, adds Parking Lot mode; for medium/large bins), `milesight-em410-rdl.md` (radar), `milesight-em500-udl.md` (ultrasonic level).
- Mounting kits and mirror cleaning cloth included [PP][UM].

## Common mistakes / troubleshooting
- **Erratic or short readings:** protective film left on the lens, dust or fingerprints on the lens, sunlight/IR in the field of view, or glass/mirror nearby [UM §5].
- **Readings beyond the bin bottom with bags inside:** enable Installation Height in Bin mode [UM §4.2].
- **No distance when tilted:** Tilt & Distance switch active and offset > 20° [UM].
- **No join:** plan/sub-band or AppKey mismatch with the network server [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plans | [DS] CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M) | Not a contradiction: [PP] names the plans for Cytron's 915 MHz-band unit |
| Availability | Brand listing card: OUT OF STOCK | Product page: "Enquiry", INQUIRE NOW | Treated as out of stock |

No spec conflict between the Cytron page and the datasheet.

## Needs verification
- Exact blind zone in cm (not stated; 2 cm is the minimum range).
- Meaning of the `-915M` suffix (inferred: 915 MHz-band hardware) and which AS923 sub-plan to use in Malaysia (Cytron says AS923-2).
- Hardware-overview drawing (lens, button, LED, NFC area positions) — figure not read.

## Sources
- [DS] EM400-TLD Datasheet: https://resource.milesight.com/milesight/iot/document/em400-tld-datasheet-en.pdf (read 2026-10-21)
- [UM] EM400-TLD User Guide V1.1: https://resource.milesight.com/milesight/iot/document/em400-tld-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em400-tld
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em400-tld-lorawan-tof-laser-distance-sensor (read 2026-10-21)
