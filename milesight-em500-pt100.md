# Milesight EM500-PT100 — Verified Reference

| | |
|---|---|
| Product code | `EM500-PT100` (Milesight model), **T200 range variant**. Cytron code `LR-EM500-PT100-T200`, MPN shown as `EM500-PT100-915M (T200)` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, code/MPN, description, features, specification, packing list, resources), Milesight product page (download links), EM500-PT100 datasheet (full, incl. ordering table) and EM500-PT100 user guide V2.2.1 (packing list, terminal-block pinout, power button, NFC/USB access, general settings, installation, battery replacing, uplink) read |
| Primary source | *EM500-PT100 Datasheet*, Milesight, https://resource.milesight.com/milesight/iot/document/em500-pt100-datasheet-en.pdf (no version/date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = EM500-PT100 datasheet PDF incl. its ordering-information table. [UM] = *EM500-PT100 User Guide* V2.2.1 (15 Aug 2024; V1.0 23 Nov 2020; V2.0 11 Apr 2022 hardware v2.x; V2.1 31 May 2023; V2.2 29 Mar 2024), https://resource.milesight.com/milesight/iot/document/em500-pt100-user-guide-en.pdf. [VEN] = Milesight product page https://www.milesight.com/iot/product/lorawan-sensor/em500-pt100. [PP] = Cytron product page (links the generic EM500 series user guide).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Sensor | PT100 platinum RTD, 3-wire connection | [DS] |
| Range (Cytron's T200) | -50 °C ~ 200 °C | [DS][PP] |
| Accuracy (T200) | Class A, typ. ± 0.6 °C (-50 °C ~ 200 °C) | [DS] |
| Resolution | 0.1 °C | [DS] |
| Probe (T200) | Straight tube, 304 stainless steel, Φ4 × 30 mm, IP67 | [DS] |
| Cable (T200) | Teflon, rated -200 °C ~ 290 °C; length 1.5 m (customizable) | [DS] |
| Installation (probe) | Contact | [DS] |
| Other Milesight ranges (not sold by Cytron) | T050 -200 ~ 50 °C (Class B; probe IP30); T500 -50 ~ 500 °C (probe IP30, fiberglass cable); T800 -50 ~ 800 °C (316 SS Φ5 × 50 mm, IP30, fiberglass cable); customizable -200 ~ 800 °C | [DS] |
| Wireless | LoRaWAN, Milesight D2D; internal antenna | [DS] |
| LoRaWAN frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP, Class A; port 85 | [DS][UM] |
| LED / button / USB | 1 × LED (internal); 1 × power/reset button (internal); 1 × USB Type-C (internal) for configuration and console | [DS] |
| Configuration | Mobile app (NFC), PC software (USB Type-C), downlink | [DS] |
| Advanced features | Data storage (1,000 entries), data retransmission, data retrievability, threshold alarm, change alarm, Milesight D2D controller | [DS] |
| Power supply | 1 × 19000 mAh ER34615 Li-SOCl2 battery | [DS] |
| Battery life | 10 years (10 min interval, 25 °C; lab figure) | [DS] |
| Transceiver operating temperature | -30 °C ~ 70 °C | [DS] |
| Relative humidity | 0 % to 100 % (non-condensing) | [DS] |
| Ingress protection | Transceiver IP67 | [DS] |
| Housing | ABS + PC, grey | [DS] |
| Weight | 362.7 g (with battery, mounting bracket and probe) | [DS] |
| Dimension (transceiver) | 105.4 × 71 × 69.5 mm | [DS] |
| Installation (transceiver) | Pole, wall or DIN-rail mounting | [DS] |
| Approvals | CE, FCC, ISED, ICASA, Telec; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "EM500-PT100 LoRaWAN Industrial Temperature Sensor"; brand Milesight; Code `LR-EM500-PT100-T200`; MPN `EM500-PT100-915M (T200)`; warranty 12 months; RM671.60; availability "Enquiry" with INQUIRE NOW [PP].
- **Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1"** [PP].
- Spec section matches [DS] for T200: 3-wire, -50 ~ +200 °C, typically ±0.6 °C, 0.1 °C, 304 SS Φ4 × 30 mm IP67 probe, Teflon cable -200 ~ 290 °C, 1.5 m, contact installation, transceiver -30 ~ 70 °C, 0–100 % RH, IP67, 362.7 g, 105.4 × 71 × 69.5 mm [PP].
- The **features list says "precision of ±0.5 °C"** (see *Conflicts*) and describes UV and vibration resistance [PP].
- **Packing list:** 1 × EM500-PT100 Industrial Temperature Sensor [PP]. Milesight's list: EM500 device with bracket, 4 × wall mounting kits, 4 × screw caps, 2 × fixing screws, hose clamp, DIN rail clip kit (optional), quick guide, warranty card [UM].
- **Resources:** EM500-PT100 datasheet, EM500 Series User Guide (generic), Payload Decoder, firmware download [PP].
- "You may also need": UG65 gateway (`milesight-ug65.md`) among unrelated Cytron products [PP].

## Interfaces, terminals and pin mapping
**Sensor terminal block (inside the transceiver)** [UM §3 Hardware Overview]
| Pin | Wire / signal |
|---|---|
| 1 | White / GND |
| 2 | — |
| 3 | — |
| 4 | Red / PT1 |
| 5 | Red / PT1 |
| 6 | — |

The 3-wire PT100 probe uses one white wire (pin 1) and two red wires (pins 4 and 5) [UM]. The probe comes connected; the user guide has no field-assembly chapter for this model [UM].

**Power button (internal)** [UM]: hold > 3 s on/off; hold > 10 s factory reset (LED blinks quickly); quick press shows status.

**Uplink** [UM ch. 7] (little-endian): 01 75 battery %; **03 67 temperature, INT16/10, °C** (report unit fixed at °C); 83 d7 temperature mutation alarm (temperature + mutation + 02); 20 ce historical data; ff 1b measuring range. 0xFFFF = read failure; 0xFFFD = outside the measuring range. Downlink port 85 [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Only the probe and cable go into the hot zone.** The transceiver is rated -30 ~ 70 °C; the Teflon cable -200 ~ 290 °C; the T200 measurement range ends at 200 °C [DS].
- **Contact installation:** the probe measures by contact — fit it in a thermowell or against the surface being measured (thermowell is inferred; [DS] says "Contact") [DS].
- **If re-wiring the probe:** white to pin 1 (GND), both reds to pins 4 and 5 (PT1) [UM].
- **Temperature unit:** ToolBox display can change, uplinks stay in °C; reset thresholds if the unit changes [UM].
- **Default reporting interval 10 min** (1–1080 min) [UM].
- **Transceiver mounting:** wall, pole (hose clamp) or 35 mm DIN rail (clip with 2 × M3 × 6 screws); keep away from metal [UM].
- **Frequency plan:** Cytron states Malaysia AS923-2 / Singapore AS923-1 [PP].

## Power and electrical limits
- One ER34615 Li-SOCl2 19000 mAh battery; alkaline not supported; replace via the bottom cover with a new battery [UM].
- 10 years at 10-min interval, 25 °C (lab) [DS].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB-C) [UM].
- Standard LoRaWAN gateways/network servers; Milesight IoT Cloud and Development Platform (OTAA) [DS][UM].
- Decoders: github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Gateway: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- Same EM500 transceiver family: `milesight-em500-pp.md`, `milesight-em500-smtc.md`, `milesight-em500-udl.md`, `milesight-em500-co2.md`.
- Ambient temperature/humidity instead: `milesight-em320-th.md`, `milesight-em300-th.md`.

## Common mistakes / troubleshooting
- **Reads 0xFFFD:** temperature outside the T200 range (-50 ~ 200 °C) [UM][DS].
- **Reads 0xFFFF or wild values:** a PT100 wire loose on pin 1/4/5 [UM].
- **Transceiver failure near ovens/boilers:** transceiver placed in the hot zone (limit 70 °C) [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Accuracy (T200) | [DS] typ. ± 0.6 °C (-50 ~ 200 °C), Class A | [PP] features list "precision of ±0.5 °C" (its spec section says ±0.6 °C) | [DS] wins: ± 0.6 °C typical. ±0.5 °C applies to other range variants in parts of their range |
| Frequency plans | [DS] CN470…AS923-1&2&3&4 | [PP] "Support Malaysia AS923-2, Singapore AS923-1" (MPN -915M) | Not a contradiction |
| Packing list | [UM] device with bracket, mounting kits, hose clamp, DIN clip (optional), quick guide, warranty card | [PP] 1 × sensor | Confirm with Cytron |
| User guide | [VEN] EM500-PT100 user guide | [PP] generic EM500 series user guide | Use [UM] |
| Availability | Brand listing card: OUT OF STOCK | Product page "Enquiry" / INQUIRE NOW | Treated as out of stock |

## Needs verification
- Probe immersion/thermowell guidance and maximum process pressure (not stated).
- Whether the probe can be detached/replaced in the field (no assembly chapter in [UM]).
- `-915M` suffix meaning (inferred 915 MHz-band hardware) and Malaysia AS923 sub-plan.

## Sources
- [DS] EM500-PT100 Datasheet: https://resource.milesight.com/milesight/iot/document/em500-pt100-datasheet-en.pdf (read 2026-10-21)
- [UM] EM500-PT100 User Guide V2.2.1: https://resource.milesight.com/milesight/iot/document/em500-pt100-user-guide-en.pdf (read 2026-10-21)
- [VEN] Milesight product page: https://www.milesight.com/iot/product/lorawan-sensor/em500-pt100
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-em500-pt100-industrial-temperature-sensor (read 2026-10-21)
