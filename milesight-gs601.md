# Milesight GS601 — Verified Reference

| | |
|---|---|
| Product code | `GS601` (Milesight model). Cytron code `LR-GS601`, MPN shown as `GS601-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight GS601 product page (features, specification tab, accessories, documents), GS601 datasheet (full, 4 pages) and GS601 user guide V1.0 (full text, 39 pages) read |
| Primary source | *GS601 Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/gs601-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | LoRaWAN® | [DS] |
| Antenna | Internal | [DS] |
| LoRaWAN frequency plans (Milesight) | RU864 / IN865 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 (no CN470) | [DS] |
| Frequency plan sold by Cytron | "Support Malaysia AS923-2, Singapore AS923-1" (MPN GS601-915M) | [PP] |
| Tx power | 16 dBm (868 MHz) / 22 dBm (915 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, **Class C** (fixed); V1.0.2 / V1.0.3 | [DS][UM] |
| Temperature | Digital CMOSens (MEMS); -20 to 60 °C; ±0.2 °C; 0.1 °C | [DS] |
| Humidity | Digital CMOSens (MEMS); 0–100 %RH; ±2 %RH; 0.5 %RH | [DS] |
| Vape index | Laser scattering; 0–100; ±10; resolution 1 | [DS] |
| TVOC | MOX (MEMS); 0–2000 µg/m³; 20 µg/m³ ±15 % of reading (1–500 µg/m³); 1 µg/m³ | [DS] |
| PM1.0 / PM2.5 / PM10 | Laser scattering; 0–1000 µg/m³; PM1.0 & PM2.5 ±10 µg/m³ (0–100) / ±10 % (100–1000); PM10 ±25 µg/m³ (0–100) / ±25 % (100–1000); 1 µg/m³ | [DS] |
| Button | 1 × reset button (external) | [DS] |
| LED & buzzer | 1 × status/alarm indicator + 1 × buzzer, 70 dB @ 1 m | [DS] |
| USB | 1 × USB Type-C (power) | [DS] |
| Configuration | Mobile app via NFC, downlink | [DS] |
| Advanced features | Threshold alarm, tamper alarm, calibration, FUOTA; multicast groups | [DS][UM] |
| Power supply | 5 V / 1 A via Type-C, or optional PoE splitter | [DS] |
| Operating temperature | -5 °C to 45 °C | [DS] |
| Relative humidity | 0–95 % (non-condensing) | [DS] |
| Ingress protection | IP30 | [DS] |
| Colour / weight | White / 178.6 g | [DS] |
| Dimensions | Ø128 × 40 mm | [DS] |
| Installation | Ceiling mounting | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
| Default reporting interval | 10 min (1–1440 min) | [UM] |
| In the box (Milesight) | 1 × GS601, 4 × ceiling mounting kits, 1 × Type-C cable (1.2 m) & power adapter, 1 × PoE splitter (optional), 1 × quick guide, 1 × warranty card | [UM] |
| Optional accessory | PS2401 Gigabit Type-C PoE splitter, 5 V 2.4 A output (also for UG63/HL31) | [VEN] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "GS601 LoRaWAN Vape Detector" (URL slug `p-gs601-vape-detector`); brand Milesight; Code `LR-GS601`; MPN `GS601-915M`; warranty 12 months; RM947.10; availability "Enquiry" (INQUIRE NOW); product video [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"** [PP].
- Spec block (short): 5 V/1 A Type-C; -5 to 45 °C; 0–95 %RH; IP30; Ø128 × 40 mm; temperature -20 to 60 °C; humidity 0–100 %RH; vape 0–100; TVOC 0–2000 µg/m³; PM 0–1000 µg/m³ [PP].
- Features: multi-sensor (e-cigarette vapour, traditional smoke, TVOC, T/H, PM), buzzer and LED status alerts, water-vapour and gas-interference resistance, adjustable buzzer hibernation, "Instant Flame Alarming: Monitors temperatures ranging from -20°C to 60°C", vibration-sensor anti-tamper, NFC, standard LoRaWAN gateways; integrates with Milesight gateways and the **Milesight Development Platform** [PP].
- **Packing list:** 1 × GS601 Vape Detector [PP].
- **Resources:** GS601 datasheet, GS601 user guide, Payload Decoder (GitHub), Firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
Power only: one **USB Type-C** port (5 V / 1 A) fed from the supplied adapter or from a PoE splitter [DS][UM]. No other wiring.

**Button and LED** [UM]
| Function | Action | LED |
|---|---|---|
| Power on / off | Connect / disconnect power (no power switch) | Green static on / off |
| Reboot | Hold reset > 3 s | Blinks slowly |
| Reset to factory default | Hold > 10 s | Blinks quickly |
| Alarm (threshold or tamper) | Any value over threshold, or device tampered | Red static on |

**Uplink (port 85; command-ID format, not channel/type)** [UM]: periodic report 01 vape index (0–100), 03 PM1.0, 05 PM2.5, 07 PM10 (UINT16 µg/m³), 09 temperature (INT16 × 0.1 °C), 0b humidity (UINT16 × 0.1 %), 0d TVOC (UINT16 µg/m³), 0f tamper status, 11 buzzer status. Alarm reports 02/04/06/08/0a/0c/0e/10 include threshold, collection-failed, under/over-range, **water-vapour interference** (vape) and **burning alarm** (temperature > 70 °C or a > 15 °C rise within 15 s). Decoders: https://github.com/Milesight-IoT/SensorDecoders.

## Rules and gotchas (for code, wiring and tutorials)
- **Needs constant 5 V power.** It is not battery-powered; plan a USB adapter or PoE splitter at the ceiling [DS][UM].
- **Class C** — always listening for downlinks; supports multicast groups for bulk control [DS][UM].
- **Mounting:** ceiling, 2.4–3 m high, where smoking may occur; 30–70 cm from exhaust fans; more than 30 cm (further in strong airflow) from doors, windows, AC vents or fans; without ventilation, one unit per 1.5 m radius; in cubicles with full-height partitions, one per cubicle [UM].
- **Buzzer hibernate periods** (two schedules) stop vape alarms sounding during set times; "Stop Buzzer" lets the reset button silence an alarm; tamper alarms stay silent for a set mute time after power-up (default 15 min) but still report and light red [UM].
- **TVOC drift after storage:** keep powered in clean air before trusting TVOC — at least 2 days (stored < 1 month), 3 days (1–6 months), 7 days (> 6 months) [UM]. Needs good ventilation for TVOC accuracy [UM].
- **Burning alarm** is a temperature-rate/temperature alarm (> 70 °C or > 15 °C in 15 s), not a flame sensor [UM].
- Do not expose to corrosive gas, silicone vapour or high VOCs; clean with a damp then dry cloth, no solvents [UM].
- **Frequency plan:** Cytron states AS923-2 (Malaysia) / AS923-1 (Singapore); match the gateway [PP].

## Power and electrical limits
- 5 V / 1 A over USB Type-C; optional PoE splitter (Milesight PS2401: Type-C out, 5 V 2.4 A) [DS][VEN].
- Operating -5 °C to 45 °C, 0–95 %RH, IP30 — indoor only [DS].

## Software support
- Milesight ToolBox (NFC): LoRaWAN settings, multicast groups, reporting interval (1–1440 min), LED, buzzer and hibernate periods, tamper alarm, time zone/DST, calibration, thresholds with alarm reporting times and dismiss reports, backup/restore, reset, upgrade [UM].
- FUOTA (firmware update over the air) [DS].
- Platforms: Milesight Development Platform (OTAA required) and standard LoRaWAN network servers [DS][UM].

## Compatibility and accessories
- LoRaWAN gateway/network server on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [VEN].
- PoE splitter PS2401 (Milesight accessory; not listed by Cytron, not in KB) [VEN].

## Common mistakes / troubleshooting
- **No power-on button:** it powers on as soon as the USB supply is connected [UM].
- **Frequent false vape alarms during deployment:** use buzzer hibernate; check airflow placement rules [UM].
- **TVOC reading odd after unboxing:** run powered in clean air for 2–7 days [UM].
- **Tamper alarm on installation:** expected within the mute window; it still reports [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Packing list | [UM] GS601, 4 × ceiling mounting kits, Type-C cable (1.2 m) & power adapter, optional PoE splitter, quick guide, warranty card | [PP] 1 × GS601 Vape Detector | [UM] for Milesight's box; confirm whether Cytron supplies the adapter |
| Flame / burning alarm | [UM] burning alarm at > 70 °C or > 15 °C rise in 15 s; temperature range -20 to 60 °C | [PP] "Instant Flame Alarming: Monitors temperatures ranging from -20°C to 60°C"; [VEN] "(20°C - 60°C)" | [UM] defines the trigger; the -20–60 °C figure is the temperature sensor range |
| Ceiling height | [UM] 2.4–3 m, screw-fixed mounting plate | [VEN] "3M adhesive for 2.7-3m ceilings" | [UM] for installation; adhesive option is [VEN] only |
| Frequency plans | [DS] list without CN470 | [PP] AS923-2 / AS923-1 (MPN -915M) | Not a contradiction |

## Needs verification
- Whether Cytron's unit ships with the Type-C cable and power adapter.
- Detection performance for cigarettes vs vapes (no distance or response-time spec published).
- Meaning of the `-915M` suffix (inferred 915 MHz-band hardware).
- Datasheet version/date (none printed).

## Sources
- [PP] https://my.cytron.io/Milesight/p-gs601-vape-detector — read 2026-10-21
- [DS] https://resource.milesight.com/milesight/iot/document/gs601-datasheet-en.pdf — read in full 2026-10-21
- [DS: web] / [VEN] https://www.milesight.com/iot/product/lorawan-sensor/gs601 — read 2026-10-21
- [UM] https://resource.milesight.com/milesight/iot/document/gs601-user-guide-en.pdf — V1.0, 30 Sep 2024, read in full 2026-10-21
