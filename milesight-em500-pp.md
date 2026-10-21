# Milesight EM500-PP — Verified Reference

| | |
|---|---|
| Product code | `EM500-PP` (Milesight model). Cytron code `LR-EM500-PP`, MPN shown as `EM500-PP-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight product page (download links), EM500-PP datasheet (full) and EM500-PP user guide V2.2.1 (packing list, terminal-block pinout, power button, sensor assembly, NFC/USB access, general settings, installation incl. pipe-sensor rules, battery replacing, uplink/downlink) read |
| Primary source | *EM500-PP Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em500-pp-datasheet-en.pdf (no version/date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = EM500-PP datasheet PDF. [UM] = *EM500-PP User Guide* V2.2.1 (15 Aug 2024; V1.0 23 Nov 2020; V2.0 11 Apr 2022 hardware v2.x, added model EM500-PP-G1/2M-4842; V2.1 31 May 2023; V2.2 29 Mar 2024), https://resource.milesight.com/milesight/iot/document/em500-pp-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em500-pp. [PP] = Cytron product page (it links the older generic EM500 series user guide, not the EM500-PP guide).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Pressure type | Vented gauge (liquids and gases) | [DS][PP] |
| Range | 0 – 1600 kPa (16 bar) | [DS] |
| Accuracy | ± 0.5 % FS (= ± 8 kPa at full scale, inferred) | [DS] |
| Resolution | 1 kPa (0.01 bar) | [DS] |
| Overload | 150 % FS | [DS] |
| Long-term stability | ± 0.3 % FS/year | [DS] |
| Process connection | G 1/2" male | [DS] |
| Probe cable | 1.5 m | [DS] |
| Wireless | LoRaWAN; internal antenna | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP, Class A; port 85 | [DS][UM] |
| LED / button / USB | 1 × LED (internal); 1 × power/reset button (internal); 1 × USB Type-C (internal) for configuration and console | [DS] |
| Configuration | Mobile app (NFC), PC software (USB Type-C), downlink | [DS] |
| Advanced features | Data storage (1,000 entries), data retransmission, data retrievability, threshold alarm, Milesight D2D controller | [DS] |
| Power supply | 1 × 19000 mAh ER34615 Li-SOCl2 battery (replaceable) | [DS] |
| Battery life | 10 years (10 min interval, 25 °C; lab figure) | [DS] |
| Operating temperature | Transceiver -30 °C ~ 70 °C; pipe pressure sensor -10 °C ~ 70 °C | [DS] |
| Relative humidity | 0 % to 100 % (non-condensing) | [DS] |
| Ingress protection | Transceiver IP67; pipe pressure sensor IP65 | [DS] |
| Housing | Transceiver ABS + PC, grey; sensor stainless steel 316L, silver | [DS] |
| Weight | Transceiver 328 g (with battery and bracket); sensor 187 g (with cable) | [DS] |
| Dimension | Transceiver 105.4 × 71 × 69.5 mm; sensor 60.5 × Ф27 mm | [DS] |
| Installation | Pole, wall or DIN-rail mounting (transceiver) | [DS] |
| Approvals | CE, FCC, ISED, ICASA, Telec; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM500-PP LoRaWAN Pipe Pressure Sensor"; brand Milesight; Code `LR-EM500-PP`; MPN `EM500-PP-915M`; warranty 12 months; RM1,136.50; availability "Enquiry" with INQUIRE NOW; no reviews [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"; Tx power 20 dBm (915 MHz)** [PP].
- Page spec matches [DS]: vented gauge, 0–1600 kPa, ±0.5 % FS, 1 kPa, 150 % FS overload, ±0.3 % FS/year, 1.5 m cable, ER34615 19,000 mAh, up to 10 years, transceiver -30 ~ +70 °C / sensor -10 ~ +70 °C, 0–100 % RH, IP67/IP65, ABS+PC / SS316L, pole/wall/DIN rail. The **G1/2" male process connection, weights and dimensions are not on the Cytron page** [PP].
- Description: pipelines, tanks, HVAC pipe networks, water mains, oil and gas lines, pump systems; NFC or USB-C configuration; "up to 10 km" line of sight [PP].
- **Packing list:** 1 × EM500-PP LoRaWAN Pipe Pressure Sensor [PP]. Milesight's list: EM500 device with mounting bracket, 4 × wall mounting kits, 4 × screw caps, 2 × fixing screws, 1 × hose clamp, 1 × DIN rail clip kit (optional), quick guide, warranty card [UM].
- **Resources:** EM500-PP datasheet, **EM500 Series User Guide** (generic), Payload Decoder, firmware download [PP].
- "You may also need": UG65 gateway (`milesight-ug65.md`) [PP].

## Interfaces, terminals and pin mapping
**Sensor terminal block (inside the transceiver)** [UM §3 Hardware Overview]
| Pin | Wire / signal |
|---|---|
| 1 | White / GND |
| 2 | Red / AIN (analog input from the sensor) |
| 3 | — (not used) |
| 4 | — (not used) |
| 5 | — (not used) |
| 6 | Black / VOUT = 12 V (sensor supply from the transceiver) |

- **The pipe sensor cable has two red wires — connect either one** to pin 2 [UM ch. 4].
- Sensor wires pass through the **waterproof cable gland in the bottom cover** [UM ch. 4].
- USB Type-C (internal, under the enclosure) for ToolBox PC software and console [DS][UM].

**Power button (internal)** [UM]: hold > 3 s on/off (LED Off→On / On→Off); hold > 10 s factory reset (blinks quickly); quick press shows status (LED on = on).

**Uplink** [UM ch. 8] (little-endian): 01 75 battery % (on join and every 24 h; low-battery alarm at 1 %); **03 7b pressure, UINT16, kPa** (the report unit is fixed as kPa); 20 ce historical data (timestamp + pressure). **0xFFFF = read failure; 0xFFFD = outside range.** Downlink port 85 [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Sensor assembly:** remove the bracket and bottom cover, feed wires through the gland, screw wires to the terminal block per the label (pin 1 white GND, pin 2 red AIN, pin 6 black 12 V), tug-test, refit the bottom cover with the **red arrow facing the front**, and fit the rubber seal and rubber screw caps to keep water out [UM ch. 4].
- **Pipe location:** on a straight run where the medium flows straight; avoid bends, splits, dead corners and places where vortices form [UM ch. 6].
- **Keep it away from valves and pumps** — open/close and start/stop surges can damage the diaphragm. **Fit a damper** on high-pressure hydraulic or liquid equipment to stop spikes [UM].
- **Low-vibration location**; **anti-freeze measures outdoors** (ice in the pressure port can damage the sensor); **for steam or hot gas add a condenser/buffer coil** so the sensor stays within -10 ~ 70 °C [UM][DS].
- **Never poke the diaphragm** to simulate pressure (permanent damage); clean regularly in corrosive or dusty sites [UM].
- **Overload limit 150 % FS (2400 kPa)** — inferred from [DS] 150 % × 1600 kPa.
- **Pressure unit:** ToolBox display unit can be changed, but **uplinks are always kPa**; update thresholds if the unit is changed [UM].
- **Default reporting interval 10 min** (1–1080 min) [UM].
- **Transceiver mounting:** wall, pole (hose clamp) or 35 mm DIN rail (clip with 2 × M3 × 6 screws); keep away from metal [UM].
- **Frequency plan:** Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].

## Power and electrical limits
- One ER34615 Li-SOCl2 19000 mAh battery; alkaline not supported; replace via the bottom cover with a new battery [UM ch. 7].
- The transceiver supplies **12 V to the sensor on pin 6** [UM]. No external power input is listed [DS].
- 10 years at 10-min interval, 25 °C (lab) [DS].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB-C); firmware upgrade via either [UM].
- Standard LoRaWAN gateways/network servers; Milesight IoT Cloud and Development Platform (OTAA) [DS][UM].
- Decoders: github.com/Milesight-IoT/SensorDecoders [PP].
- Milesight D2D controller mode (default D2D key set at the factory; not copied) [DS][UM].

## Compatibility and accessories
- Gateway: `milesight-ug65.md` (Cytron suggestion), `milesight-ug56.md`, `milesight-ug67.md`.
- Same EM500 transceiver family: `milesight-em500-pt100.md`, `milesight-em500-smtc.md`, `milesight-em500-udl.md`, `milesight-em500-co2.md`.
- Damper, buffer coil, thread adapters: not supplied (inferred; [UM] recommends a damper/condenser where needed).

## Common mistakes / troubleshooting
- **Reads 0 or 0xFFFF:** sensor wire loose or on the wrong terminal; check pin 1/2/6 [UM].
- **Water inside the transceiver:** bottom cover refitted without the seal/screw caps or arrow misaligned [UM].
- **Damaged diaphragm:** sensor mounted next to a pump/valve without a damper, frozen outdoors, or poked [UM].
- **Thresholds behave oddly after changing units:** reset the thresholds; uplinks stay in kPa [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plans | [DS] CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M) | Not a contradiction: [PP] names the plans for Cytron's unit |
| Packing list | [UM] device with bracket, wall kits, screw caps, fixing screws, hose clamp, DIN clip (optional), quick guide, warranty card | [PP] 1 × sensor | Confirm with Cytron; [UM] is Milesight's standard box |
| User guide | [VEN] EM500-PP user guide | [PP] links the generic EM500 series user guide | Use the EM500-PP guide [UM] |
| Stock | Product page "Enquiry" / INQUIRE NOW | Brand listing card "View" | Treated as Active per the listing card |

## Needs verification
- The `-915M` suffix (inferred 915 MHz-band hardware) and Malaysia AS923 sub-plan.
- Whether Cytron's unit is the standard EM500-PP or the EM500-PP-G1/2M-4842 model named in [UM] V2.0.
- Whether the box includes the mounting kit and DIN clip.

## Sources
- [DS] EM500-PP Datasheet: https://resource.milesight.com/milesight/iot/document/em500-pp-datasheet-en.pdf (read 2026-10-21)
- [UM] EM500-PP User Guide V2.2.1: https://resource.milesight.com/milesight/iot/document/em500-pp-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em500-pp
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em500-pp-lorawan-pipe-pressure-sensor (read 2026-10-21)
