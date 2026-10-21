# Milesight UC502 LoRaWAN Multi-Interface Controller — Verified Reference

| | |
|---|---|
| Product code | `UC502` (Milesight model, UC50x series) [DS]. Cytron codes `LR-UC502` (internal antenna, MPN `UC502-915M`) and `LR-UC502-EA` (external antenna, MPN "UC502-915M , PN:EA"); parent listing code `V-LR-UC502` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both antenna variants: code, MPN, price, stock; description, features, specification, packing list, resources), Milesight UC50x product page, UC50x series datasheet (in full) and UC50x series user guide (hardware, pin tables, DIP switches, power button, operation guide, installation) read |
| Primary source | Milesight *UC50x Series Datasheet* (PDF, file dated 26 Jun 2025), https://resource.milesight.com/milesight/iot/document/uc50x-series-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UC50x Series datasheet PDF (covers UC501 and UC502; PDF created 26 Jun 2025). [UM] = Milesight *UC50x Series User Guide* PDF (38 pages; PDF dated 17 Oct 2025); the Data Interface 1 pin table and M12 face drawing were read from a rendered page image. [VEN] = Milesight UC50x product page. [PP] = Cytron product page. The UC50x communication protocol PDF was not read.

## What it is
Cytron sells an **internal-antenna** (`UC502-915M`) and an **external-antenna "EA"** version [PP]. For the solar/Class C sibling see `milesight-uc501.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Protocol | LoRaWAN® | [DS] |
| Antenna | Internal or external (hardware option); EA version: 1 × 50 Ω SMA female connector | [DS] |
| Frequency plans | CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @300bps | [DS] |
| Work mode | OTAA/ABP **Class A** (UC502) | [DS] |
| Interface type | M12 A-coded male | [DS] |
| GPIO | 2 × GPIO; logic low 0–0.8 V, high 2.5–3.3 V; max current 20 mA; digital input / digital output / pulse counter (software switchable); suggested ≤ 4000 Hz | [DS] |
| Serial | 1 × RS232 or RS485 (software switchable), 1200–115200 bps; transparent (RS232/RS485), Modbus RTU (RS485); 16 Modbus channels | [DS][UM] |
| Analog input | 2 × analog input, 12-bit, 4–20 mA or 0–10 V (DIP switch; default 4–20 mA) | [DS][UM] |
| SDI-12 | 1 × SDI-12, V1.4, transparent | [DS] |
| Power output | 2 × 3.3 V, 2 × 5/9/12 V (switchable; default 12 V); continuous (3.3 V) or 0–10 min before collection (5/9/12 V); current setting 0–60 mA | [DS][UM] |
| Button / USB / LED | 1 × power/reset button (internal); 1 × Type-C (internal) for configuration and console; 1 × reboot/reset LED (internal) | [DS] |
| Configuration | Mobile app via NFC, PC software via USB Type-C, downlink | [DS] |
| Advanced features | Threshold alarm, change alarm, data storage (600 entries), data retrievability, data retransmission (no multicast) | [DS] |
| Reporting interval | 10 – 64800 s, default 1200 s | [UM] |
| Power supply | 1. 3 × 9000 mAh replaceable ER26500 Li-SOCl2 batteries; 2. DC 5–24 V by M12 connector | [DS] |
| Operating temperature | -30 °C to 70 °C | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Ingress protection | IP68 (1 m underwater, 7 days) | [DS] |
| Dimensions | 116 × 116 × 45.5 mm (connectors excluded) | [DS] |
| Installation | Wall or pole mounting | [DS] |
| Approvals | CE, FCC, ISED; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UC502 LoRaWAN Multi-Interface Controller", option "Antenna": External Antenna / Internal Antenna, warranty 12 months [PP].
- External: code `LR-UC502-EA`, MPN shown as "UC502-915M , PN:EA", RM757.70, "Availability: Enquiry". Internal: code `LR-UC502`, MPN `UC502-915M`, RM706.00, "Availability: Enquiry". Parent page: "Out Of Stock", Notify Me [PP].
- Spec block: EA SMA female; "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1"; Tx 20 dBm (915 MHz); -137 dBm; OTAA/ABP Class A; M12 A-coded male; GPIO as [DS]; RS232 or RS485; power outputs as [DS]; power on/off by NFC app, PC software or internal button; 3 × 9000 mAh ER26500 Li-SOCl2 + 5–24 VDC; -30 to 70 °C; IP68 (1 m, 7 days); 116 × 116 × 45.5 mm [PP].
- **Packing (EA):** 1 × UC502-EA, 2 × data cables (30 cm), 1 × mounting bracket, 4 × wall mounting kits, 2 × hose clamps, 1 × fixing screw, 1 × quick guide, 1 × warranty card, 1 × LoRaWAN® magnetic antenna. **Internal antenna:** the same without the antenna (Cytron's list still says "1 × UC502-EA Device") [PP].
- **Resources:** UC50x datasheet, user guide, communication protocol, firmware page [PP].

## Interfaces, terminals and pin mapping
Same connectors as UC501 [UM]:

**Data Interface 1** (6-pin M12): 1 = 5V/9V/12V OUT (switchable), 2 = 3.3V OUT, 3 = GND, 4 = Analog Input 1, 5 = Analog Input 2, 6 = 5–24V DC IN. M12 face (from the drawing): 1 top-right, 2 right, 3 bottom, 4 left, 5 top-left, 6 centre [UM].

**Data Interface 2** (8-pin M12): 1 = 5V/9V/12V OUT, 2 = 3.3V OUT, 3 = GND, 4 = GPIO1, 5 = GPIO2, 6 = RS232 TXD / RS485 A, 7 = RS232 RXD / RS485 B, 8 = SDI-12 [UM].

**Internal DIP switches** (switch 1 / 2 / 3) [UM]: power output 12 V on/off/off (default), 9 V off/on/off, 5 V off/off/on; analog 4–20 mA off/on/on (default), 0–10 V on/off/off; RS485 120 Ω on/off/off, 1 kΩ pull-up on A off/on/off, 1 kΩ pull-down on B off/off/on.

**Power button (internal):** hold > 3 s on/off; > 10 s reset; quick press shows state [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **On UC502 the DC input cannot charge the batteries** — they are primary Li-SOCl2 cells; replace them, never recharge [UM][DS].
- External DC has priority over the batteries when both are connected [UM].
- **Class A only:** downlinks are delivered only after an uplink, so remote control of GPIO outputs is slow (inferred from Class A); no multicast [DS].
- GPIO is 3.3 V logic, 20 mA max — not a relay; add an external relay for loads (Cytron FAQ on the UC501 page applies to the series) [DS][PP].
- Sensor power outputs switch on only around each collection; long warm-up times and frequent reporting drain the battery (inferred) [UM].
- RS232/RS485 share pins 6/7 (choose in software) [DS].
- Open the case for DIP switches / USB; refit the cover in cross order to keep IP68 [UM].

## Power and electrical limits
- 3 × 9000 mAh ER26500 Li-SOCl2, replaceable; or DC 5–24 V on Data Interface 1 pin 6 (GND pin 3) [DS][UM].
- Sensor power out 3.3 V and 5/9/12 V, current setting 0–60 mA [UM].
- GPIO: 20 mA max, 3.3 V logic [DS].
- Battery life: [NOT STATED].
- Operating -30 to 70 °C, IP68 [DS].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB Type-C); downlink configuration [DS][UM].
- Milesight IoT Cloud / Development Platform; standard LoRaWAN network servers [UM][VEN].
- UC50x communication protocol and Milesight SensorDecoders for payload decoding [PP].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- Solar / Class C sibling: `milesight-uc501.md`. Mains-powered: `milesight-uc300.md`, `milesight-uc100.md` [VEN].
- Magnetic antenna only with the EA variant [PP].

## Common mistakes / troubleshooting
- **Analog wrong:** DIP left at 4–20 mA for a 0–10 V sensor [UM].
- **Output command arrives late:** Class A — the downlink waits for the next uplink (inferred) [DS].
- **Batteries flat early:** high report rate, retransmission enabled, or long sensor warm-up on the 12 V output [UM].
- **Factory reset:** hold the internal power button > 10 s, or reset in ToolBox [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Ingress protection | [DS] IP68 (1 m, 7 days) | [UM] IP67; [PP] description "IP67-rated enclosure" (its spec says IP68) | [DS] wins: IP68 |
| Wireless options | [DS] LoRaWAN | [PP] description: "simplifies the deployment … of LoRaWAN® or cellular networks" | Cytron sells LoRaWAN variants only (MPN `UC502-915M`); Milesight's LTE UC50x is a separate model |
| Analog input row | [DS] 2 × AI, 4–20 mA or 0–10 V, 12-bit; SDI-12 separate | [PP] "Analog Input: Ports: 2 × Analog Input, Protocol: SDI-12 V1.4, Transparent" | [DS] wins; Cytron merged two rows |
| Packing, internal-antenna version | [UM] 1 × UC50x device | [PP] "1 × UC502-EA Device" | Copy-paste error on [PP]; internal version ships a UC502 without antenna |
| Stock | [PP] parent "Out Of Stock" | [PP] variants "Enquiry" | Treat as out of stock; order by enquiry |

## Needs verification
- Which M12 connector is Interface 1 vs 2 on the case, and the data-cable wire colours.
- Battery life at typical reporting intervals.
- Pre-set LoRaWAN plan on Cytron's `UC502-915M` (Cytron says Malaysia AS923-2 / Singapore AS923-1).

## Sources
- [DS] UC50x Series Datasheet: https://resource.milesight.com/milesight/iot/document/uc50x-series-datasheet-en.pdf (PDF 26 Jun 2025)
- [UM] UC50x Series User Guide: https://resource.milesight.com/milesight/iot/document/uc50x-series-user-guide-en.pdf (PDF 17 Oct 2025)
- [VEN] Milesight UC50x page: https://www.milesight.com/iot/product/iot-controller/uc50x
- [PP] Cytron: https://my.cytron.io/Milesight/p-uc502-multi-interface-controllers (variants `…-multi-interface-controller-with-external-antenna`, `…-lorawan-multi-interface-controller-without-external-antenna`; read 2026-10-21)
