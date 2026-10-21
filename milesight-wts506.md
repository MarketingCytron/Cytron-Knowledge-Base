# Milesight WTS506 LoRaWAN IoT Weather Station — Verified Reference

| | |
|---|---|
| Product code | `WTS506` (Milesight model). Cytron code `LR-WTS506`, MPN `WTS506-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page, WTS506 datasheet read in full, WTS506 user guide V1.1 (5 Sep 2023) read for safety, packing, button/LED, power supply, reporting interval, installation, maintenance and uplink sections |
| Primary source | Milesight *WTS506 Datasheet*, https://resource.milesight.com/milesight/iot/document/wts506-datasheet-en.pdf (read 2026-10-21; no version printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight WTS506 datasheet PDF (three spec blocks: WTS sensor, WTS hub, solar panel). [UM] = Milesight WTS506 User Guide V1.1, 5 Sep 2023. [PP] = Cytron product page.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Temperature | Thermistor, -40 ~ 85 °C, ±0.3 °C, 0.1 °C | [DS] |
| Humidity | Capacitive, 0 – 100 % RH, ±3 % RH, 0.5 % RH | [DS] |
| Wind direction | Ultrasonic, 0 – 360°, ±3°, 0.1° | [DS] |
| Wind speed | Ultrasonic, 0 – 60 m/s, ±0.3 m/s or ±3 % (whichever is greater), 0.1 m/s | [DS] |
| Barometric pressure | Piezoresistive, 500 – 1100 hPa, ±0.5 hPa, 0.1 hPa | [DS] |
| Rainfall | Piezoelectric, 0 – 1000 mm, ±0.5 mm (< 10 mm) / ±5 % (> 10 mm), 0.01 mm | [DS] |
| Sensor head | Aluminium alloy, white; 2.15 kg; Ø160 × 263 × Ø73 mm; -40 ~ 85 °C; 0 – 100 % RH non-condensing; **IP65**; pole mounting | [DS] |
| Hub wireless | LoRaWAN®, internal antenna, OTAA/ABP **Class A**; 16 dBm (868) / 22 dBm (915) / 19 dBm (470); -137 dBm @ 300 bps | [DS] |
| Frequency plans (Milesight) | CN470 / RU864 / IN865 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan (Cytron) | "Support Malaysia AS923-2, Singapore AS923-1"; MPN `WTS506-915M` | [PP] |
| Hub connectors | M12 A-coded male: 1 × 2-pin power connector (15 V), 1 × data connector for the WTS sensor | [DS] |
| Hub button / USB / LED | 1 × power/reset button (internal); 1 × USB Type-C (internal) for configuration and console; 1 × reboot/reset LED (internal) | [DS] |
| Hub configuration | Mobile app via NFC, or PC software via USB-C; power on/off also by internal button | [DS] |
| Hub advanced features | Data storage (19,000 entries), retransmission, retrieval, threshold alarm | [DS] |
| Hub power | External solar (15 W, 1 A) with 2 × 2550 mAh ICR18650 rechargeable backup batteries | [DS] |
| Hub environment | -20 ~ 60 °C; 0 – 95 % RH non-condensing; **IP67** | [DS] |
| Hub dimensions / install | 116 × 116 × 45.5 mm (connectors excluded); screw mounting | [DS] |
| Solar panel | Monocrystalline; Voc 18 V ±0.3 V; rated 15 V, 1 A; max 15 W; 50 cm cable with 2-pin M12 A-coded male; -20 ~ 80 °C; 1 kg (2.2 kg with bracket); 343 × 283 × 16.5 mm; pole mounting | [DS] |
| Reporting interval | 1 – 1080 min, default 10 min | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WTS506 LoRaWAN IoT Weather Station"; Code `LR-WTS506`; MPN `WTS506-915M`; warranty 12 months; RM12,915.00; availability "Enquiry" [PP].
- Spec block matches [DS] for ranges and accuracies, 22 dBm, 19,000 entries, 15 W / 18 V Voc panel, 2 × 2550 mAh ICR18650, M12 A-coded data plug and 2-pin power input, internal Type-C, reset button, NFC; hub IP67; dimensions [PP]. It does not give the sensor head's IP65 rating or the hub's -20 ~ 60 °C range [PP].
- Description: three parts (sensor head, hub box, solar panel), aluminium alloy, local storage with automatic resend, NFC setup; "No Moving Parts for Wind" (ultrasonic); rain by acoustic vibration instead of a tipping bucket [PP].
- **Packing list:** WTS sensor, WTS hub, solar panel (with bracket), solar panel mounting bracket, sensor cable, WTS hub mounting bracket, 5 × fixing screws, 4 × solar panel screw kits, 2 × "house clamps" (hose clamps), mounting bracket, bent pipe, 3 × hex socket cap mounting screws, quick start guide, warranty card [PP] (same as [UM]).
- Resources: WTS506 datasheet and user guide (resource.milesight.com), payload decoder, firmware & SDK [PP].

## Interfaces, terminals and pin mapping
| Hub interface | Connects to | Src |
|---|---|---|
| **Left** M12 A-coded 2-pin power connector (15 V) | Solar panel 50 cm cable | [DS][UM] |
| **Right** M12 A-coded data connector | WTS506 sensor head via the sensor cable (run through the bent pipe and bracket) | [DS][UM] |
| Internal USB-C | PC configuration/console | [DS] |
| Internal power button | Hold > 3 s on/off; quick press (< 3 s) = check status (LED on/off); hold > 10 s = factory reset (LED blinks 3 times) | [UM] |
| NFC | ToolBox app read/write, power on/off, reset | [UM] |
M12 pin assignments are not published [DS][UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Sensor arrow must face north** (use a compass) — wind direction depends on it [UM].
- **Siting:** within gateway range; distance to the nearest obstacle ideally 10 × its height; > 2 m from radar/transmitters; away from chimneys and vents; no plants > 1 m high within 10 m [UM].
- **Solar panel tilt:** bracket allows 20°, 40° or 60° [UM]. Clean the panel regularly (dust, sand, bird droppings) [UM].
- **Battery charging stops above 45 °C** hub temperature; avoid direct sun on the hub [UM]. Note the hub is rated only -20 ~ 60 °C, narrower than the sensor head [DS].
- **Do not chip ice/snow off the sensor**; let it melt [UM]. Clean with a soft damp cloth and mild detergent [UM].
- **Payload** (port 85): battery 01 75; temperature 03 67 INT16/10 °C; humidity 04 68 UINT8/2; wind direction 05 84 INT16/10 °; pressure 06 73 UINT16/10 hPa; wind speed 07 92 UINT16/10 m/s; rainfall 08 ec UINT32/100 mm accumulated + frame counter (payload changed in UM V1.1) [UM].

## Power and electrical limits
- Solar 15 W (rated 15 V, 1 A; Voc 18 V) into the hub's 15 V 2-pin M12 input; 2 × 2550 mAh ICR18650 rechargeable backup [DS].
- No charging above 45 °C [UM].
- Sensor head -40 ~ 85 °C, IP65; hub -20 ~ 60 °C, IP67; panel -20 ~ 80 °C [DS].

## Software support
- Milesight IoT Cloud / Development Platform; standard LoRaWAN servers. Decoders: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway on the same plan, e.g. outdoor `milesight-ug67.md`, or `milesight-ug65.md` / `milesight-ug56.md`.
- Agriculture use alongside `milesight-em500-smtc.md` (soil) and `milesight-smart-agriculture-kit.md` (inferred pairing; not stated by Cytron).
- Pole and hose clamps for mounting are included; the pole itself is not (inferred from the packing list).

## Common mistakes / troubleshooting
- **Wind direction offset:** sensor arrow not aligned to north [UM].
- **Battery not charging on hot days:** hub above 45 °C; shade the hub [UM].
- **Low solar charge:** dirty panel or wrong tilt [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Ingress protection | [PP] "Hub Box Rating: IP67" only | [DS] hub IP67, sensor head IP65 | [DS]: both values; the sensor head is IP65 |
| Rain sensing wording | [PP] "acoustic vibration" | [DS] piezoelectric | Consistent in substance; use [DS] term |
| Operating temperature | [PP] -40 ~ 85 °C (temperature tracking range only) | [DS] hub -20 ~ 60 °C; panel -20 ~ 80 °C | [DS]: the -40 ~ 85 °C figure is the sensor head only |

## Needs verification
- M12 connector pin assignments (not published).
- Pole diameter range for the hose clamps (not stated).
- AS923 sub-plan shipped for Malaysia.

## Sources
- [DS] WTS506 Datasheet: https://resource.milesight.com/milesight/iot/document/wts506-datasheet-en.pdf (read 2026-10-21).
- [UM] WTS506 User Guide V1.1 (5 Sep 2023): https://resource.milesight.com/milesight/iot/document/wts506-user-guide-en.pdf
- [VEN] Milesight WTS506 product page: https://www.milesight.com/iot/product/lorawan-sensor/wts506
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-lorawan-iot-weather-station (read 2026-10-21).
