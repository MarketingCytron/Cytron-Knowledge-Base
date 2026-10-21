# Milesight UC501 LoRaWAN Multi-Interface Controller (External Antenna) — Verified Reference

| | |
|---|---|
| Product code | `UC501` (Milesight model, UC50x series; EA = external-antenna hardware) [DS]. Cytron code `LR-UC501-EA` (no MPN shown) [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specification, packing list, FAQ, resources), Milesight UC50x product page, UC50x series datasheet (in full) and UC50x series user guide (hardware, pin tables, DIP switches, power button, operation guide, installation) read |
| Primary source | Milesight *UC50x Series Datasheet* (PDF, file dated 26 Jun 2025), https://resource.milesight.com/milesight/iot/document/uc50x-series-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UC50x Series datasheet PDF (covers UC501 and UC502; 5 pages; PDF created 26 Jun 2025). [UM] = Milesight *UC50x Series User Guide* PDF (`uc50x-series-user-guide-en.pdf`, 38 pages; PDF dated 17 Oct 2025); the Data Interface 1 pin table and M12 face drawing were read from a rendered page image, Data Interface 2 and the DIP table from the PDF text. [VEN] = Milesight UC50x product page. [PP] = Cytron product page. The UC50x communication protocol PDF was not read.

## What it is
Cytron lists only the **external-antenna (EA)** version of UC501 [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Protocol | LoRaWAN® | [DS] |
| Antenna | Internal or external (hardware option); EA version: 1 × 50 Ω SMA female connector | [DS] |
| Frequency plans | CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @300bps | [DS] |
| Work mode | OTAA/ABP, **Class A or Class C** (UC501) | [DS] |
| Multicast | Supported (UC501 only), up to 4 groups, Class C required | [DS][UM] |
| Interface type | M12 A-coded male | [DS] |
| GPIO | 2 × GPIO; logic low 0–0.8 V, high 2.5–3.3 V; max current 20 mA; modes digital input / digital output / pulse counter (software switchable); input frequency suggested ≤ 4000 Hz | [DS] |
| Serial | 1 × RS232 **or** RS485 (software switchable), 1200–115200 bps; transparent (RS232/RS485), Modbus RTU (RS485) | [DS] |
| Modbus channels | 16 channels, 1 register each (quantity fixed to 1) | [UM] |
| Analog input | 2 × analog input, 12-bit, 4–20 mA or 0–10 V (switchable by DIP; default 4–20 mA) | [DS][UM] |
| SDI-12 | 1 × SDI-12, SDI-12 V1.4, transparent; 16 channels, up to 16 commands each | [DS][UM] |
| Power output | 2 × 3.3 V, 2 × 5/9/12 V (switchable by DIP; default 12 V); power time before collection: continuous (3.3 V) or 0–10 min (5/9/12 V); supply current setting 0–60 mA | [DS][UM] |
| Button | 1 × power/reset button (internal) | [DS] |
| USB | 1 × Type-C (internal) for configuration and console | [DS] |
| LED | 1 × reboot/reset LED (internal) | [DS] |
| Configuration | Mobile app via NFC, PC software via USB Type-C, downlink | [DS] |
| Advanced features | Threshold alarm, change alarm, multicast, data storage (600 entries), data retrievability, data retransmission | [DS] |
| Reporting interval | 10 – 64800 s, default 1200 s (20 min) | [UM] |
| Power supply | 1. 2 × 2550 mAh ICR18650 chargeable batteries; 2. embedded solar power (6 V, 1.7 W); 3. DC 5–24 V by M12 connector | [DS] |
| Operating temperature | -20 °C to 60 °C | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Ingress protection | IP68 (1 m underwater, 7 days) | [DS] |
| Dimensions | 116 × 116 × 45.5 mm (connectors excluded) | [DS] |
| Installation | Wall or pole mounting | [DS] |
| Approvals | CE, FCC, ISED; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UC501 LoRaWAN Multi-Interface Controller with External Antenna", code `LR-UC501-EA`, RM740.45, "Availability: Out Of Stock" with Notify Me, warranty 12 months; no variants and no MPN shown [PP].
- Spec block: Class A / Class C, OTAA/ABP, external antenna (SMA female), "Frequency Bands: Support Malaysia AS923-2, Singapore AS923-1", Tx up to 20 dBm, -137 dBm, up to 15 km LOS; 2 × GPIO (DI/DO/pulse counter, 0–0.8 V / 2.5–3.3 V, 20 mA, ≤ 4000 Hz); 1 × RS232 or RS485; 2 analog channels 4–20 mA / 0–10 V 12-bit; 1 × SDI-12 V1.4; 2 × 3.3 V and 2 × 5/9/12 V outputs, 0–10 min delay; IP68; -20 to 60 °C; 116 × 116 × 45.5 mm; wall/pole mount; USB Type-C; 2 × 2550 mAh Li-ion + built-in solar panel (6 V, 1.7 W); external DC 5–24 VDC [PP].
- **Packing:** 1 × UC501, 2 × data cable (30 cm), 1 × mounting bracket, 4 × wall mounting kits, 2 × hose clamp, 1 × fixing screw, 1 × quick guide, 1 × warranty card, 1 × LoRaWAN® magnetic antenna (EA only), 1 × solar panel kit (optional) [PP].
- **FAQ:** no direct charge indicator (watch the battery level rise); DI cannot detect a short-circuit; GPIO can be controlled by downlink or by MQTT on a Milesight UG6x gateway or Node-RED; **the DO cannot work as a relay output — add an external relay**; RS485 supports up to 16 sensors when one value is read per sensor [PP].
- **Resources:** UC501 & UC502 datasheet, user guide, communication protocol, firmware page, Milesight FAQ "How to Remotely Control Milesight Controller via MQTT in Milesight Gateway" [PP].

## Interfaces, terminals and pin mapping
Two M12 A-coded male connectors on the bottom edge ("Data & Power Interface"); NFC area on the front label; SMA antenna on top (EA) [UM].

**Data Interface 1** (6-pin M12) [UM]
| Pin | Function |
|---|---|
| 1 | 5V/9V/12V OUT (switchable) |
| 2 | 3.3V OUT |
| 3 | GND |
| 4 | Analog Input 1 |
| 5 | Analog Input 2 |
| 6 | 5–24V DC IN |
M12 face drawing (pins seen from the connector face): 1 top-right, 2 right, 3 bottom, 4 left, 5 top-left, 6 centre [UM].

**Data Interface 2** (8-pin M12) [UM]
| Pin | Function |
|---|---|
| 1 | 5V/9V/12V OUT (switchable) |
| 2 | 3.3V OUT |
| 3 | GND |
| 4 | GPIO1 |
| 5 | GPIO2 |
| 6 | RS232 TXD / RS485 A |
| 7 | RS232 RXD / RS485 B |
| 8 | SDI-12 |

**Internal DIP switches** (inside the back cover) [UM]
| Function | Setting (switch 1 / 2 / 3) |
|---|---|
| Power output 12 V (default) | on / off / off |
| Power output 9 V | off / on / off |
| Power output 5 V | off / off / on |
| Analog input 4–20 mA (default) | off / on / on |
| Analog input 0–10 V | on / off / off |
| RS485: 120 Ω between A and B | on / off / off |
| RS485: 1 kΩ pull-up on A | off / on / off |
| RS485: 1 kΩ pull-down on B | off / off / on |
Interface 1 power output feeds the analog sensors; interface 2 power output feeds serial and SDI-12 devices [UM].

**Power button (internal)** [UM]: hold > 3 s = turn on / turn off; hold > 10 s = reset (LED blinks); quick press shows on/off state (LED on = device on).

## Rules and gotchas (for code, wiring and tutorials)
- **Open the case to change DIP switches or use USB.** Power off first, use tweezers (protect the waterproof film), and refit the back cover in cross order (4.5–5 kgf, first to 80–90 % then fully) to keep IP68 [UM].
- **GPIO is 3.3 V logic, 20 mA max.** It is not a relay or an industrial 24 V input; add an external relay for loads and keep DI signals within 0–3.3 V levels (inferred from the logic-level spec) [DS][PP].
- **Pulse counter:** choose pull-down (counts rising edges) or pull-up/none (falling edges); enable the digital filter when the pulse period is > 250 µs; enable "keep last value when power off"; press Start or the count will not change [UM].
- **Sensor power outputs are only on around each collection**, not continuously (except 3.3 V when set continuous). For a proof-of-concept, power slaves externally [UM].
- **RS232 and RS485 share pins 6/7**; select one in software. RS232 uses its own LoRaWAN port [UM][DS].
- Modbus RS485 bridge is active pass-through only (server asks, device answers) [UM].
- **External DC has priority over the batteries** when both are present [UM].
- Multicast needs Class C and matching application ports on all group members [UM].
- NFC: Android or iOS Milesight ToolBox app; firmware upgrade from the app works on Android only [UM].

## Power and electrical limits
- 2 × 2550 mAh ICR18650 rechargeable cells; embedded solar panel 6 V, 1.7 W; DC 5–24 V on Data Interface 1 pin 6 (GND pin 3) [DS][UM].
- Sensor power out: 3.3 V and 5/9/12 V on each interface; current setting 0–60 mA [UM].
- GPIO: 20 mA max; logic levels 0–0.8 V low, 2.5–3.3 V high [DS].
- Battery life: [NOT STATED] in the datasheet. Data retransmission shortens battery life [UM].
- Operating -20 to 60 °C (rechargeable-cell model), IP68 [DS].

## Software support
- Milesight ToolBox app (NFC, Android/iOS) and ToolBox PC software (USB Type-C) [UM].
- LoRaWAN V1.0.2/V1.0.3, OTAA/ABP; Milesight IoT Cloud and Milesight Development Platform [UM][VEN].
- Decoders: Milesight-IoT SensorDecoders (GitHub) and the UC50x communication protocol [UM][PP].
- Remote GPIO control via downlink, or via MQTT on a Milesight gateway / Node-RED (Cytron FAQ) [PP].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- Battery-only sibling: `milesight-uc502.md`. Mains-powered controllers: `milesight-uc300.md`, `milesight-uc100.md`. Valve controller: `milesight-uc512.md` [VEN].
- Two 30 cm M12 data cables included; the solar panel kit is listed as optional in the packing list although the solar panel is built in [PP][UM].

## Common mistakes / troubleshooting
- **Analog reads wrong:** DIP still on 4–20 mA (default) while a 0–10 V sensor is wired, or the ToolBox signal type not changed after the DIP change [UM].
- **Sensor gets no power:** the power output is timed to collection; set "power time before collect" long enough (0–600 s) [UM].
- **Water ingress after opening:** back cover not refitted with the sealing ring clean and screws in cross order [UM].
- **Is it charging?** No indicator — check the battery level over time [PP].
- **Factory reset:** open the case and hold the power button > 10 s, or ToolBox software / app reset [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Ingress protection | [DS][VEN] IP68 (1 m, 7 days) | [UM] overview and features: IP67 | [DS] wins: IP68 |
| Battery type | [DS] 2 × 2550 mAh ICR18650 chargeable | [PP] "2 × 2550mAh Rechargeable Li-ion" | Consistent (ICR18650 is Li-ion) |
| Solar panel | [DS] embedded solar power | [PP] packing "1 x Solar Panel Kit (Optional)" | Panel is built in [DS]; the optional kit is an extra Milesight accessory |

## Needs verification
- Which physical M12 connector (left or right) is Data Interface 1 vs 2, and the wire colours of the supplied 30 cm data cables.
- LoRaWAN plan pre-set on Cytron's unit (Cytron says Malaysia AS923-2 / Singapore AS923-1) and the hardware band (no MPN shown; 915 MHz-band hardware inferred).
- Battery life figures and solar charging current.
- Charging temperature limits for the 18650 cells.

## Sources
- [DS] UC50x Series Datasheet: https://resource.milesight.com/milesight/iot/document/uc50x-series-datasheet-en.pdf (PDF 26 Jun 2025)
- [UM] UC50x Series User Guide: https://resource.milesight.com/milesight/iot/document/uc50x-series-user-guide-en.pdf (PDF 17 Oct 2025)
- [VEN] Milesight UC50x page: https://www.milesight.com/iot/product/iot-controller/uc50x ; communication protocol https://resource.milesight.com/milesight/iot/document/uc50x-series-communication-protocol-en.pdf (not read)
- [VEN] Milesight FAQ (via Cytron): https://milesight-iot.freshdesk.com/support/solutions/articles/73000514236-how-to-remotely-control-lorawan-nodes-from-milesight-gateway-
- [PP] Cytron: https://my.cytron.io/Milesight/p-uc501-lorawan-multi-interface-controller-with-external-antenna (read 2026-10-21)
