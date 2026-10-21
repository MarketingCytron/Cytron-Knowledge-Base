# Milesight UG67 — Verified Reference

| | |
|---|---|
| Product code | `UG67` (Milesight model). Cytron code `LR-UG67`, MPN `UG67-L08GL-915M` (cellular version) [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, code, MPN, stock, description, spec, packing list, resources), Milesight UG67 page, UG67 datasheet (7 pages, read in full), UG67 Quick Guide V1.7 (packing, hardware overview, M12 DC pinout, LEDs, reset, installation, weather and lightning protection) and UG67 user guide V1.15 (introduction, web access, factory reset) |
| Primary source | Milesight *UG67 Datasheet*, https://resource.milesight.com/milesight/iot/document/ug67-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UG67 datasheet PDF. [UM] = Milesight *UG67 Quick Guide* V1.7 (24 Dec 2025; https://resource.milesight.com/milesight/iot/document/ug67-quick-guide-en.pdf, not linked from the product pages but hosted by Milesight) and *UG67 User Guide* V1.15 (15 Apr 2026). [VEN] = milesight.com UG67 page. [PP] = Cytron product page.

## What it is
Cytron sells the cellular version, MPN `UG67-L08GL-915M` (915 MHz-band hardware), and states the plan as Malaysia AS923-2 / Singapore AS923-1 [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| CPU | Quad-core 1.5 GHz, 64-bit ARM Cortex-A53 | [DS] |
| Memory / storage | 512 MB DDR4 RAM; 8 GB eMMC | [DS] |
| LoRa chip | Semtech SX1302 (SF5 and SF6 supported per Cytron/Milesight web text) | [DS][PP] |
| LoRa channels | 8 (half/full-duplex) | [DS] |
| LoRa frequency bands (model range) | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| Cytron frequency plan | "Support Malaysia AS923-2, Singapore AS923-1"; MPN UG67-L08GL-915M | [PP] |
| LoRa antenna connectors | 2 × 50 Ω N-Female external connectors (ANT1, ANT2) | [DS][UM] |
| Sensitivity / Tx power | -140 dBm @ 292 bps; 27 dBm max | [DS] |
| LBT | Supported; not on AU915 or US915 | [DS] |
| LoRaWAN protocol | V1.0 and V1.0.2, Class A/B/C | [DS] |
| Device capacity | Around 2000 Class A/B/C devices (10 min uplink interval) | [DS] |
| Range | Line of sight up to 15 km | [DS] |
| Ethernet | 1 × RJ45 WAN port, PoE PD; 10/100/1000 Base-T, auto MDI/MDIX; 1.5 kV RMS isolation | [DS] |
| Wi-Fi | Internal antenna; IEEE 802.11 b/g/n, 2.4 GHz; AP or client | [DS] |
| Cellular | 4G LTE; Class 3 (23 dBm ±2 dB); internal antenna; 1 × mini SIM (2FF) | [DS] |
| LTE bands | [NOT STATED] in the datasheet | [DS] |
| GNSS | GPS/GLONASS/QZSS/SBAS, internal antenna; -161 dBm tracking, -149 dBm acquisition, -161 dBm re-acquisition; 2.5 m CEP | [DS] |
| LEDs | SYS, LoRa, LTE | [DS] |
| Reset button | 1 × RST (in the LED/interface area under a clear cover) | [DS][UM] |
| USB | 1 × Type-C for console | [DS] |
| Power connector | 1 × M12 A-coded connector | [DS] |
| Power supply | (1) IEEE 802.3af PoE; (2) 6–12 VDC via M12 connector (also used for solar supply) | [DS][UM] |
| Power consumption | Typical 3.6 W, max 4.8 W | [DS] |
| Power-fail alarm | Built-in capacitor for sending alarms on power failure; Cytron/Milesight web text: keeps working about 1 minute | [DS][PP] |
| Built-in | Watchdog, RTC, timer | [DS] |
| Ingress protection | IP67 | [DS] |
| Material / colour | PC (UL94 V0) + ADC-12 aluminium, white | [DS] |
| Weight | 1463 g | [DS] |
| Dimensions | 240 × 164 × 90.9 mm | [DS] |
| Installation | Wall or pole mounting | [DS] |
| Operating temperature | -40 °C to +70 °C; reduced cellular performance above 60 °C | [DS] |
| Storage temperature | -40 °C to +85 °C | [DS] |
| Humidity | 0–95 % non-condensing at 25 °C | [DS] |
| Approvals | CE, CE (RED), FCC, TELEC; RoHS | [DS] |
| Embedded network server / integration | Milesight codecs and custom codecs, Gateway Fleet, multicast, FUOTA; MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP, Modbus RTU over TCP | [DS] |
| Network / VPN / management | PPPoE, SNMP, DDNS; OpenVPN/IPsec/PPTP/L2TP/GRE/DMVPN/WireGuard; firewall; WAN failover; Web, CLI, SMS, HTTP API, MQTT API, DeviceHub, Milesight Development Platform; Python SDK, Node-RED; event alarm includes Power On/Off | [DS] |
| In the box (Milesight) | UG67, PoE injector, mounting bracket, 4 × wall mounting kits, 2 × LoRaWAN antennas (60 cm), M12 DC power cable (30 cm), antenna coaxial cable (1 m), short mounting backboard kit, warranty card, quick start guide | [UM][DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UG67 Outdoor LoRaWAN® Gateway (With Cellular)"; brand Milesight; Code `LR-UG67`; MPN `UG67-L08GL-915M`; RM3,788.40; cashback RM113.65; availability 8; ADD TO CART. No warranty period is shown on this page [PP].
- Spec list matches [DS] for CPU, RAM, eMMC, 2 × N-Female, 8 channels, -140 dBm, 27 dBm, LBT, Gigabit PoE-PD port, 2.4 GHz Wi-Fi, 4G LTE with mini SIM, PoE or 6~12 VDC via M12, 3.6 W / 4.8 W, IP67, 1463 g, 240 × 164 × 90.9 mm, wall or pole, -40 to +70 °C. It adds "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1" and lists the GPS tracking sensitivity as -167 dBm (see *Conflicts*) [PP].
- **Packing list:** 1 × UG67 with cellular; accessories 2 × antenna, 1 × antenna coaxial cable, 1 × PoE injector, 1 × M12 DC power cable, 1 × mounting kit, 1 × mounting bracket, 1 × RJ cable gland, 1 × cable gland plug, 1 × SIM dust cover [PP].
- **Resources:** UG67 datasheet and user guide (resource.milesight.com), payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware and SDK download [PP].
- Description text includes a supercapacitor that keeps the gateway "working for 1 minute to send an alert while a power outage happens", "Support SF5 & SF6", Milesight IoT Cloud, Gateway Fleet, FUOTA, BACnet and Modbus BMS integration, RPS auto-provisioning, and an installation board for antennas. It names "5 GHz 64-bit Quad-Core Processor" (the spec says 1.5 GHz) and backhaul "via Ethernet and Wi-Fi" [PP].

## Interfaces, terminals and pin mapping
Hardware overview [UM]:
| # | Item | Src |
|---|---|---|
| 1 | LoRaWAN antenna connectors (ANT1, ANT2; N-Female) | [UM][DS] |
| 2 | Vent plug | [UM] |
| 3 | SIM slot (under a black SIM dust cover) | [UM] |
| 4 | LED area, Type-C port and reset button (under a clear LED/interface cover) | [UM] |
| 5 | DC power connector (M12; also the solar connector) | [UM] |
| 6 | Ethernet port (PoE), through a cable gland | [UM] |
| 7 | Grounding stud | [UM] |

**M12 DC power connector pinout** (supply 6–12 V or solar) [UM]:
| Pin | Cable colour | Function |
|---|---|---|
| 1 | Black | GND |
| 2 | White | Reserved |
| 3 | Yellow | Reserved |
| 4 | Red | +12V |

Assembly torques [UM]: LED/interface cover 0.7 N·m; SIM dust cover 0.7 N·m; cable gland 1.1 N·m; the installation steps say not to exceed 1.6 N·m when tightening the SIM cover or cable gland.

**LED indications** [UM]:
| LED | State | Meaning |
|---|---|---|
| SYS | Static green / red | Running properly / system error |
| LoRa | Off / green | Packet forwarder off / running well |
| LTE | Off | SIM registering, failed to register, or no SIM |
| LTE | Green blinking slowly | SIM registered, ready to dial up |
| LTE | Green blinking rapidly | SIM registered, dialling up |
| LTE | Green static | Dialled up successfully |


## Rules and gotchas (for code, wiring and tutorials)
- **M12 power: pin 1 = GND (black), pin 4 = +12V (red); pins 2 and 3 are reserved — leave them unconnected.** Supply range 6–12 VDC [UM][DS]. Do not feed 24 V.
- **PoE is 802.3af**; a PoE injector is in the box [DS][UM][PP].
- **Seal everything outdoors:** pass the Ethernet cable through the cable gland, keep the SIM dust cover and connector caps on, and wrap antenna and cable connectors (insulation tape, then 3M waterproof tape, then insulation tape, each overlapping 50 %) [UM].
- **Lightning protection:** earth the grounding stud (earthing wire thicker than 10 AWG cross-section), add lightning arresters on antenna connectors and PoE surge protectors, keep the gateway below the building's highest point or within a lightning rod's protection [UM].
- **Antennas:** mount vertically; keep the two antennas at least 35 cm apart and at least 35 cm from walls; in strong wind, use the coaxial cable instead of fitting an antenna directly to the gateway. One antenna goes on ANT2 directly, the other via the coax on ANT1 [UM].
- **Region must match end devices** (Cytron: AS923-2 for Malaysia) [PP][UM].
- **SIM:** check that the PN on the label contains "-Lxxxx" (cellular version); Cytron's MPN does [UM][PP]. Open the SIM dust cover with the wrench.
- **Do not power the device while installing** [UM].

## Power and electrical limits
- 802.3af PoE on the RJ45, or 6–12 VDC on the M12 A-coded connector (pin 4 +12V, pin 1 GND) [DS][UM].
- Consumption: typical 3.6 W, max 4.8 W [DS].
- Ethernet isolation 1.5 kV RMS [DS].
- Built-in capacitor for a power-failure alarm (about 1 minute of operation per [PP]) [DS][PP].
- Environment: -40 °C to +70 °C (cellular reduced above 60 °C), 0–95 % RH, IP67 [DS].

## Software support
- Same Milesight gateway software as UG65/UG56: web GUI (HTTPS), CLI, SMS, SNMP, HTTP and MQTT APIs [DS].
- Embedded network server (codecs, multicast, FUOTA, Gateway Fleet), MQTT(s)/HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP, Modbus RTU over TCP [DS].
- Packet forwarders to The Things Stack, ChirpStack, Actility, AWS; Cytron also names Everynet and The Things Industries [DS][PP].
- DeviceHub, Milesight Development Platform, Milesight IoT Cloud; RPS auto-provisioning [DS][PP].
- Python SDK and Node-RED on the gateway [DS].
- Firmware `.bin`, upgrade in *Maintenance > Upgrade* [UM].

## Compatibility and accessories
- Antennas: two 60 cm LoRa antennas and a 1 m coaxial cable are in the box [UM][PP]. Milesight's GA01 130 cm N-N kit (FNN1300) lists UG65/UG67 [VEN of UG65 page]. Cytron's GA01 listing (`milesight-ga01.md`) is the S-N kit for UG56 — not the UG67 connector type (inferred).
- End devices: Milesight LoRaWAN sensors on the same plan, e.g. `milesight-em500-smtc.md`, `milesight-wts506.md`, `milesight-em300-th.md`; field tester `milesight-ft101.md`.
- Other gateways: `milesight-ug65.md` (IP65 semi-industrial), `milesight-ug56.md` (IP30 industrial).

## Common mistakes / troubleshooting
- **Factory reset:** with SYS static green, hold reset more than 5 s until SYS blinks rapidly; release and wait; SYS goes off then static green [UM].
- **No LTE:** check the LTE LED (off = SIM not registered or missing) and the APN in *Network > Interface > Cellular* [UM].
- **Water ingress:** caps, dust covers or gland not tightened, or connectors not taped [UM].
- **Cannot reach 192.168.23.150:** wired default access only for firmware v60.0.0.46 or earlier; use the Wi-Fi AP [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| GNSS tracking sensitivity | [DS] -161 dBm @ tracking | [PP] -167 dBm @ tracking | [DS] wins: -161 dBm |
| GNSS constellations | [DS] GPS/GLONASS/QZSS/SBAS | [PP] "GPS" only | [DS] wins |
| CPU clock in description | [DS] 1.5 GHz | [PP] description "5 GHz 64-bit Quad-Core Processor" (spec table says 1.5 GHz) | Typo on [PP]; 1.5 GHz |
| Backhaul | [DS] Ethernet, cellular (4G) and Wi-Fi | [PP] description "Ethernet and Wi-Fi" | [DS] wins; Cytron's unit has LTE |
| Packing list | [UM] includes short mounting backboard kit, 4 wall kits | [PP] adds RJ cable gland, cable gland plug, SIM dust cover (fitted to the gateway by default per [UM] V1.6) | Compatible; the gland and covers come fitted |
| Warranty | [UM] "3-year warranty included" | [PP] not stated | Confirm Cytron's warranty |
| Approvals | [DS] CE, CE (RED), FCC, TELEC | [PP] none listed | [DS] |

## Needs verification
- Cytron warranty period for UG67 (not shown on the page).
- LTE category and bands of `UG67-L08GL-915M`.
- Exact LoRaWAN plan for Malaysia (Cytron says AS923-2).
- Whether a 12 V solar/battery supply on the M12 needs any external regulation (the guide says "6-12 V or solar supply").
- Datasheet version/date (none printed).

## Sources
- [DS] UG67 Datasheet: https://resource.milesight.com/milesight/iot/document/ug67-datasheet-en.pdf (read 2026-10-21).
- [UM] UG67 Quick Guide V1.7, 24 Dec 2025: https://resource.milesight.com/milesight/iot/document/ug67-quick-guide-en.pdf (read 2026-10-21).
- [UM] UG67 User Guide V1.15, 15 Apr 2026: https://resource.milesight.com/milesight/iot/document/ug67-user-guide-en.pdf (introduction, web access, factory reset).
- [VEN] Milesight UG67 page: https://www.milesight.com/iot/product/lorawan-gateway/ug67 (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ug67-outdoor-lorawan-gateway-with-cellular (read 2026-10-21).
