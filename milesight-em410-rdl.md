# Milesight EM410-RDL — Verified Reference

| | |
|---|---|
| Product code | `EM410-RDL` (Milesight model, external-antenna "EA" version). Cytron code `LR-EM410-RDL-EA`, MPN shown as `EM410-RDL-915M-EA` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight product page (now "EM41x-RDL"), EM410-RDL datasheet (Cytron-linked, full), EM41x-RDL datasheet (current, full), EM410-RDL user guide V1.2 (hardware, LED/contacts, battery, antenna, NFC/Bluetooth, general settings, calibration, threshold, installation, LoRaWAN sensor data) and the EM41x-RDL LoRaWAN user guide revision history (V1.3) read |
| Primary source | *EM410-RDL Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em410-rdl-datasheet-en.pdf (no version/date printed; linked from the Cytron page; read 2026-10-21), cross-checked against the newer *EM41x-RDL Datasheet* https://resource.milesight.com/milesight/iot/document/em41x-rdl-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = EM410-RDL datasheet; [DS: 41x] = the newer combined EM41x-RDL datasheet (EM411-RDL ATEX, EM410-RDL, EM410-RDL-L0CEU cellular). [UM] = *EM410-RDL User Guide* V1.2 (16 Jan 2025; V1.0 12 Sep 2024, V1.1 29 Nov 2024), https://resource.milesight.com/milesight/iot/document/em410-rdl-user-guide-en.pdf. [UM: 41x] = *EM41x-RDL LoRaWAN User Guide* V1.3 (28 Nov 2025), https://resource.milesight.com/milesight/iot/document/em41x-rdl-lora-user-guide-en.pdf (revision history read). [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em41x-rdl (the em410-rdl URL redirects there). [PP] = Cytron product page. Dimension and hardware-overview drawings not read as text.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | Millimetre-wave radar, 60 GHz band | [DS] |
| Target | Liquids or smooth-surface solids | [DS] |
| Detection angle (beam) | 8° | [DS] |
| Detection distance | 0.3 m ~ 12 m | [DS] |
| Blind zone | 30 cm (the blind-zone alarm reports "no target within 30 cm"; matches the 0.3 m minimum) | [UM §6.1.2][DS] |
| Accuracy | Up to ± 2 mm (perfectly smooth flat solid or still liquid surface) | [DS] |
| Accuracy, rougher surfaces | Up to ± 5 mm (relatively smooth surface or stable liquid) — [DS: 41x] only; which model column it applies to is not clear in the text | [DS: 41x] |
| Resolution | 1 mm | [DS] |
| Device position | Normal / Tilt (Tilt = horizontal offset ≥ 15°) | [DS][UM] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| LoRaWAN mode | OTAA / ABP, Class A; application port 85 | [DS][UM] |
| Antenna | Internal or external (hardware option). **EA version: 1 × 50 Ω SMB male connector**; SMB magnetic antenna and cable gland supplied | [DS][UM] |
| LED | 1 × LED indicator (internal) | [DS] |
| Configuration | Mobile app via NFC or Bluetooth; downlink | [DS] |
| Advanced features | Distance threshold alarm, distance change alarm, blind zone alarm, radar-echo curve, diagnostic, data storage (2,000 entries), data retrievability (LoRaWAN), data retransmission | [DS] |
| Power supply | 1 × 19000 mAh ER34615 Li-SOCl2 battery (alkaline not supported) | [DS][UM] |
| Battery life (LoRaWAN) | Around 7 years (15-min collection interval + 1440-min report interval, 25 °C; lab figure) | [DS] |
| Operating temperature | -40 °C ~ 70 °C (LoRaWAN version) | [DS] |
| Relative humidity | 0 ~ 100 % (non-condensing) | [DS] |
| Ingress protection | IP68 (1 m underwater, 48 hours) | [DS] |
| Dimension | Ф 101 × 87 mm | [DS] |
| Weight | 400 g | [DS] |
| Housing | PVDF (UL94 V0), blue + grey | [DS] |
| Tank thread | G1½" ([DS: 41x] adds an NPT 1½" hardware option) | [DS][DS: 41x] |
| Installation | Wall bracket mounting; tank threaded installation | [DS] |
| Approvals | CE, FCC (LoRaWAN version); RoHS in [DS: 41x] | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM410-RDL LoRaWAN Radar Distance / Level Sensor with External Antenna"; brand Milesight; Code `LR-EM410-RDL-EA`; MPN `EM410-RDL-915M-EA`; warranty 12 months; RM1,334.55; availability "Enquiry" with INQUIRE NOW; no variant selector [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"; Tx power 20 dBm**; external antenna 1 × 50 Ω SMB male [PP].
- Page spec matches [DS]: 60 GHz, 8°, 0.3–12 m, up to ±2 mm, 1 mm, Normal/Tilt, ER34615 19000 mAh, around 7 years, -40 ~ 70 °C, 0–100 % RH, IP68 (1 m, 48 h), Ф101 × 87 mm, 400 g, PVDF, G1½", wall bracket or tank thread, CE/FCC [PP].
- Description: wastewater systems, underground tanks, industrial reservoirs; measures through plastics/plants, less affected by snow, dirt, dust, steam; scenario modes (standard, rainwater well, sewage well, storage tank); threshold and sudden-rise alerts (Storage Tank mode only per the page note) [PP].
- **Packing list:** 1 × sensor, mounting bracket, bubble level, waterproof tape, G1½ nut, wall mount screw kit, O-ring seal, **1 × ER34615 battery**, SMB magnetic antenna with screw kit, antenna cable gland, warranty card, quick start guide [PP].
- **Resources:** EM410-RDL datasheet and user guide (resource.milesight.com), Payload Decoder, Firmware & SDK download [PP].
- "You may also need": UG65 gateway (`milesight-ug65.md`) and unrelated Cytron controllers [PP].

## Interfaces, terminals and pin mapping
No signal wiring. Connections: **SMB (50 Ω, male) antenna connector** for the supplied magnetic antenna through a waterproof cable gland; battery compartment under a screw-off top cover; **two metal contacts** used as the "button" [UM].

**LED and contact actions** [UM §2.4]
| Function | Action | LED |
|---|---|---|
| Power on | Install a new battery | Lights for 3 s |
| Power off | Remove battery | Off |
| Reboot | Short the two metal contacts > 3 s | Blinks slowly |
| Reset to factory default | Short the two metal contacts > 10 s | Blinks quickly |
| Check on/off | Short the two metal contacts < 3 s | On = device on; off = device off |

**LoRaWAN sensor data** [UM §6.1.2] (little-endian): 01 75 battery %; 04 82 distance/liquid level (INT16, mm); 05 00 position (00 Normal / 01 Tilt ≥ 15°); 06 c7 radar signal strength (INT16 × 0.01 dBm); 84 82 threshold alarm; 94 82 level-shift alarm; b4 82 blind-zone alarm (fffd = no target within 30 cm or target not collected; ffff = sensor abnormal); 20 ce historical data (timestamp + level + temperature + mutation + alarm bits). Decoders: github.com/Milesight-IoT/SensorDecoders.

## Rules and gotchas (for code, wiring and tutorials)
- **Scenario modes:** General (calm liquid), Rainwater Well, Wastewater Well, Tank (LoRaWAN only). **Tank mode reports liquid height from the bottom (needs Tank Depth); other modes report device-to-surface distance** [UM §4.2].
- **Default reporting interval 1440 min (24 h)**, range 1–1440 min; collecting interval must be ≤ reporting interval [UM §4.2, §4.4.2].
- **Tilt & Distance switch:** distance measuring turns off when offset > 15° [UM §4.2].
- **Blind-zone calibration:** run it after installation with nothing in the blind zone; it then reports an alarm if the level enters the blind zone [UM §4.4.1].
- **One-click diagnosis / radar echo curve** only over Bluetooth; manual tuning of echo signal quality, threshold sensitivity and peak sorting (nearest vs strongest) for foam or clutter. Higher signal quality = more power use [UM §4.4.1].
- **Bracket install:** avoid metal objects, water outlets, stairs; level the bracket with the bubble level; drill 4 holes; pick the bracket position by height (1–2 m → position 1; 2.1–3 m → 2; 3.1–6 m → 3); fix the device with the G1½ nut at **≤ 4 N·m torque** [UM §5.1].
- **Tank install:** more than **20 cm from the tank wall**, perpendicular to the liquid, no obstacles; use the supplied O-ring; adapters for other tank openings are sold separately [UM §5.2].
- Avoid strong vibration, direct sunlight, rain/snow exposure, intense heat, strong EM fields; put the magnetic antenna on a manhole cover or other metal surface for good signal [UM §5.2].
- **Battery:** ER34615 Li-SOCl2 only, no alkaline; remove it if stored long-term. Close the waterproof cover by aligning the two red dots, then screw the top cover until the edge marks align [UM §3].
- **LoRaWAN keys:** default App EUI / AppKey are set at the factory (see the user guide; not copied).
- **Frequency plan:** match the gateway; Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].

## Power and electrical limits
- One ER34615 Li-SOCl2 19000 mAh battery; no external power [DS][UM].
- Around 7 years at 15-min collection + 24-h reporting, 25 °C (lab figure) [DS].
- -40 ~ 70 °C; 0–100 % RH non-condensing; IP68 1 m / 48 h [DS].

## Software support
- Milesight ToolBox app over Bluetooth or NFC [UM].
- Standard LoRaWAN gateways/network servers; management and OTA upgrade via Milesight Development Platform [DS].
- Local storage of 2,000 records with retrieval and retransmission (LoRaWAN) [DS].
- Decoders: github.com/Milesight-IoT/SensorDecoders [PP][UM].

## Compatibility and accessories
- Gateway on the same plan: `milesight-ug65.md` (Cytron suggestion), `milesight-ug56.md`, `milesight-ug67.md`.
- Related level sensors: `milesight-em500-udl.md` (ultrasonic, up to 10 m), `milesight-em400-mud.md`, `milesight-em400-tld.md`.
- Supplied: bracket, bubble level, nut, O-ring, battery, SMB magnetic antenna and cable gland [PP][UM]. Tank adapters are sold separately [UM].

## Common mistakes / troubleshooting
- **Wrong level on foamy or cluttered liquid:** use the Bluetooth radar-echo curve and one-click diagnosis; adjust signal quality / sensitivity / peak sorting [UM].
- **Reads 0xFFFD:** nothing beyond the 30 cm blind zone or no target found; **0xFFFF:** sensor abnormal [UM].
- **Tank mode values look inverted:** Tank mode reports height from the bottom, not distance [UM].
- **Measurement stops:** tilt > 15° with Tilt & Distance switch enabled [UM].
- **Weak LoRa link from a manhole:** mount the magnetic antenna on the metal cover [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plans | [DS] CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M-EA) | Not a contradiction: [PP] names the plans for Cytron's 915 MHz-band unit |
| Battery in the box | [PP] and [UM] V1.2: 1 × ER34615 battery listed in packing | [UM: 41x] V1.3 (Nov 2025): battery pre-installed and removed from the packing list | Either way a battery is supplied; newer stock ships it pre-installed |
| Tank thread opening | [DS] G1½" | [UM §5.2] "G1½" and G2½" thread opening" | [DS] wins for the stated spec (G1½"); G2½" needs checking |
| Product page name | Cytron "EM410-RDL" | Milesight page now "EM41x-RDL" (EM410/EM411) | Same product family; Cytron sells EM410-RDL (not the ATEX EM411) |
| Availability | Brand listing card: OUT OF STOCK | Product page: "Enquiry", INQUIRE NOW | Treated as out of stock |

## Needs verification
- Which column the "±5 mm" accuracy in [DS: 41x] applies to.
- Whether a G2½" thread is also usable ([UM] text vs [DS]).
- Exact "two metal contacts" location (figure not read).
- `-915M` suffix meaning (inferred 915 MHz-band hardware) and Malaysia AS923 sub-plan (Cytron says AS923-2).

## Sources
- [DS] EM410-RDL Datasheet: https://resource.milesight.com/milesight/iot/document/em410-rdl-datasheet-en.pdf (read 2026-10-21)
- [DS: 41x] EM41x-RDL Datasheet: https://resource.milesight.com/milesight/iot/document/em41x-rdl-datasheet-en.pdf (read 2026-10-21)
- [UM] EM410-RDL User Guide V1.2: https://resource.milesight.com/milesight/iot/document/em410-rdl-user-guide-en.pdf (read 2026-10-21)
- [UM: 41x] EM41x-RDL LoRaWAN User Guide V1.3: https://resource.milesight.com/milesight/iot/document/em41x-rdl-lora-user-guide-en.pdf (revision history read)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em41x-rdl
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em410-rdl-lorawan-radar-distance-level-sensor (read 2026-10-21)
