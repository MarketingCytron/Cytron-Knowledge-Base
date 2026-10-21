# Milesight EM400-MUD — Verified Reference

| | |
|---|---|
| Product code | `EM400-MUD` (Milesight model). Cytron code `LR-EM400-MUD`, MPN shown as `EM400-MUD-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features/specification, packing list, resources), Milesight product page (features, models, download links), Milesight EM400-MUD datasheet (full, 5 pages) and user guide V1.1 (full text: hardware, power button, NFC, settings, calibration, threshold, maintenance, installation, LoRaWAN uplink/downlink) read |
| Primary source | *EM400-MUD Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em400-mud-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight EM400-MUD datasheet PDF (no version/date printed). [UM] = *EM400-MUD User Guide*, Milesight, V1.1 (15 Jun 2023; V1.0 30 Mar 2023), https://resource.milesight.com/milesight/iot/document/em400-mud-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em400-mud (features, models and download tabs; it has no separate specification table). [PP] = Cytron product page. The hardware-overview and dimension figures in [DS]/[UM] are drawings only and were not read as text.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensing principle | Ultrasonic distance detection, small blind zone | [DS] |
| Detection range | 3 ~ 450 cm | [DS] |
| Blind zone | Below 3 cm (inferred from the 3 cm lower range limit; [DS] says only "small blind zone") | [DS] |
| Detection accuracy | ± (1 + 0.3 % × S) cm, S = distance (-15 °C ~ 60 °C) | [DS] |
| Detection resolution | 1 mm | [DS] |
| Beam angle | 60° (beam-pattern drawing on DS p5) | [DS] |
| Device position | Normal / Tilt (3-axis accelerometer; Tilt = horizontal offset angle ≥ 20°) | [DS][UM] |
| Temperature sensor | NTC; range -40 ~ 125 °C, resolution 0.1 °C | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A (fixed); LoRaWAN V1.0.2 or V1.0.3 selectable; application port 85 by default | [DS][UM] |
| LED / button | 1 × LED indicator (internal); 1 × power/reset button (internal) | [DS] |
| Power on/off | NFC or internal power button | [DS] |
| Configuration | Mobile app (Milesight ToolBox via NFC), downlink commands | [DS][UM] |
| Advanced features | Calibration, threshold alarm, Tilt & Distance switch | [DS] |
| Power supply | 2 × 9000 mAh ER26500 Li-SOCl2 batteries (replaceable) | [DS] |
| Battery life (LoRaWAN, lab conditions) | Standard mode > 10 years (10 min interval, 25 °C); Bin mode > 10 years (20 min interval, 25 °C); Parking lot mode 5 years (12 triggers per day, 25 °C) | [DS] |
| Operating temperature | -30 °C ~ 70 °C | [DS] |
| Relative humidity | ≤ 95 % (non-condensing) | [DS] |
| Ingress protection | IP67; damp-proof (conformal) coating inside | [DS] |
| Dimension | 118 × 65 × 32.5 mm | [DS] |
| Weight | 181.4 g (batteries included) | [DS] |
| Housing | ABS + PC (UL94 V0), black gray | [DS] |
| Installation | On flat surfaces with screws | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM400-MUD LoRaWAN Ultrasonic Distance Sensor"; brand Milesight; Code `LR-EM400-MUD`; MPN `EM400-MUD-915M`; warranty 12 months; RM499.40; availability "Enquiry" with an INQUIRE NOW button (no Add to Cart); no reviews [PP].
- **Frequency plan on the Cytron page: "Support Malaysia AS923-2, Singapore AS923-1"** [PP]. No frequency variant selector.
- Page spec matches [DS]: range 3–450 cm, accuracy ± (1 + 0.3 % × S) cm, resolution 1 mm, Normal/Tilt, temperature -40 ~ 125 °C / 0.1 °C, 2 × 9000 mAh ER26500, battery-life figures, -30 ~ 70 °C, ≤ 95 % RH, IP67, 118 × 65 × 32.5 mm, ABS + PC flame retardant, screw installation. The beam angle (60°) and weight are **not** on the Cytron page [PP].
- Description: smart parking (vehicle in/out reports) and smart waste (fill level of medium or large bins, lid status via accelerometer, trash-combustion detection via NTC); three pre-set modes; IP67 with PCBA conformal coating; Milesight IoT Cloud dashboard/app; NFC configuration; screw mounting [PP].
- **Packing list:** 1 × EM400-MUD LoRaWAN Ultrasonic Distance Sensor module [PP]. Milesight's packing list is 1 × device, 2 × mounting kits, 1 × warranty card, 1 × quick guide [UM].
- **Resources:** EM400-MUD Datasheet and User Guide (Google Drive copies), Payload Decoder (github.com/Milesight-IoT/SensorDecoders), Firmware & SDK download (milesight.com download center) [PP].
- "You may also need": UG65 Semi-Industrial LoRaWAN Gateway (`milesight-ug65.md`) [PP].

## Interfaces, terminals and pin mapping
There are no terminals, cables or external probes. The ultrasonic transducer ("ultrasonic horn") faces the target; the power/reset button and LED are inside the housing; configuration is by NFC [DS][UM].

**Power button (internal)** [UM §2.4]
| Function | Action | LED indication |
|---|---|---|
| Switch on | Press and hold > 3 s | Off → On |
| Switch off | Press and hold > 3 s | On → Off |
| Reset to factory default | Press and hold > 10 s | Quickly blinks |
| Check on/off status | Quick press | Light on = device on; light off = device off |

**LoRaWAN uplink channels (LoRaWAN version)** [UM §6.1.1] — little-endian, Channel + Type + Data:
| Channel/Type | Data |
|---|---|
| 01 75 | Battery level, UINT8, % |
| 03 67 | Temperature, INT16, × 0.1 °C |
| 04 82 | Distance, INT16, mm |
| 05 00 | Device position: 00 Normal (offset < 20°), 01 Tilt (≥ 20°) |
| 83 67 / 84 82 | Temperature / distance threshold alarm: value + alarm status byte (00 dismiss, 01 alarm) |

Downlink (port 85): reboot, reporting interval, device mode (00 Standard / 01 Bin / 02 Parking Lot), Tilt & Distance switch, ultrasonic sensor enable, threshold alarm, parking height threshold, installation height [UM §6.1.2]. Decoders: github.com/Milesight-IoT/SensorDecoders [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Mount it horizontally, above the target, with a clear path.** The device must sit in a horizontal position above the object it measures [UM §5].
- **Keep at least 30 cm from side walls**, with nothing blocking the ultrasonic signal. If it must go on a side wall, keep the ultrasonic horn away from the wall [UM §5]. The beam is 60° wide, so nearby walls and bin edges can echo [DS].
- **Bin mode:** fit the device in the centre of the bin. Milesight's recommended size example: for an 88 cm tall bin, minimum radius 24 cm [UM §5].
- **Mounting:** drill two holes in the container lid, put the device under the lid and bolt through from the other side; or fix with two M4 screws and wall plugs [UM §5].
- **Parking Lot mode** uses Installation Height (default 3 m, range 0.030–4.500 m) and a threshold Δ (default 1 m): Height − Distance > Δ reports occupied; < Δ reports vacant, immediately on change. Collecting interval default 20 s (1–600 s); reporting interval default 1080 min [UM §4.2].
- **Default reporting intervals (LoRaWAN):** Standard 10 min, Bin 20 min (range 1–1080 min) [UM §4.2].
- **Tilt & Distance switch:** when enabled, the distance sensor turns off when the offset angle is > 20° [UM §4.2].
- Threshold alarms apply only in Bin and Standard modes; the collecting interval must be ≤ the reporting interval [UM §4.4.2].
- **Calibration:** numerical offset, or "measure outlier" re-measurement when a reading jumps outside a set range [UM §4.4.1].
- **LoRaWAN join:** OTAA or ABP; a default App EUI and a default AppKey / session keys are set at the factory (see the user guide; not copied). Use OTAA for Milesight IoT Cloud; only OTAA supports rejoin mode. Device EUI is on the label [UM §4.3.1].
- **Frequency plan:** set the channel plan to match the gateway. Cytron states Malaysia AS923-2 and Singapore AS923-1 [PP]; Milesight's [DS] lists AS923-1/2/3/4 among others.
- Firmware upgrade via ToolBox is **Android only**; config templates (backup) only copy between devices of the same model and frequency band [UM §4.5].

## Power and electrical limits
- Two ER26500 Li-SOCl2 9000 mAh batteries, built in and replaceable; no external power input [DS].
- Fit **two new batteries together**, or battery life will be reduced [UM safety].
- Battery-life figures are lab-tested guideline values at 25 °C (see Specifications) [DS].
- Operating -30 ~ 70 °C, ≤ 95 % RH non-condensing [DS].

## Software support
- Configuration: Milesight ToolBox app (Android and iOS) over NFC; Milesight's dedicated NFC reader is an alternative [UM].
- Network: works with standard LoRaWAN gateways and network servers; compatible with Milesight IoT Cloud (OTAA) [DS][UM].
- Payload decoders: github.com/Milesight-IoT/SensorDecoders [UM][PP].
- Firmware: Milesight download center; upgrade by ToolBox (Android) [UM][PP].

## Compatibility and accessories
- Needs a LoRaWAN gateway on the same frequency plan, e.g. `milesight-ug65.md` (Cytron "you may also need"), `milesight-ug56.md` or `milesight-ug67.md` [PP].
- Related distance/level sensors: `milesight-em400-tld.md` (ToF laser, shorter range), `milesight-em410-rdl.md` (radar), `milesight-em500-udl.md` (ultrasonic level, longer range).
- Mounting kits come in Milesight's box [UM]; Cytron's packing list names the sensor only [PP].

## Common mistakes / troubleshooting
- **Wrong or jumping distance:** device mounted near a side wall (< 30 cm) or at an angle; the 60° beam hits the wall. Re-mount level and centred [UM §5][DS].
- **Distance reading stops when tilted:** Tilt & Distance switch is enabled and offset > 20° [UM].
- **No join:** frequency plan/sub-band mismatch with the gateway, or AppKey not matching the network server entry [UM].
- **NFC will not read:** move the phone's NFC area over the device, remove the phone case, move away and retry [UM].
- **Short battery life:** mixed old/new batteries, or very short reporting intervals [UM][DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plans | [DS] CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN EM400-MUD-915M) | Not a contradiction: the [PP] names the plans relevant to Cytron's 915 MHz-band unit. Use [PP] for what Cytron sells; confirm the sub-plan on the network server |
| Packing list | [UM] device, 2 × mounting kits, warranty card, quick guide | [PP] 1 × sensor module | [UM] is Milesight's box content; confirm with Cytron whether mounting kits are included |
| Availability | Brand listing card: OUT OF STOCK | Product page: "Availability: Enquiry", INQUIRE NOW | Treated as out of stock (no Add to Cart) |

## Needs verification
- Exact blind zone in cm ([DS] says only "small blind zone"; 3 cm is the stated minimum range).
- Meaning of the `-915M` MPN suffix (assumed 915 MHz-band hardware covering AS923; inferred) and which AS923 sub-plan Malaysian deployments should use (Cytron says AS923-2).
- Hardware-overview drawing (position of the internal button, LED and NFC area) — figure not read.
- Whether Cytron's box includes Milesight's 2 mounting kits.

## Sources
- [DS] EM400-MUD Datasheet: https://resource.milesight.com/milesight/iot/document/em400-mud-datasheet-en.pdf (read 2026-10-21)
- [UM] EM400-MUD User Guide V1.1: https://resource.milesight.com/milesight/iot/document/em400-mud-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em400-mud
- [VEN] Decoders: https://github.com/Milesight-IoT/SensorDecoders
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em400-mud-lorawan-ultrasonic-distance-sensor (read 2026-10-21)
