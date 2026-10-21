# Milesight UG56 — Verified Reference

| | |
|---|---|
| Product code | `UG56` (Milesight model). Cytron code `LR-UG56-NC`, MPN `UG56-915M` (non-cellular version) [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, code, MPN, stock, spec, packing list, resources), Milesight UG56 product page (spec and accessories), UG56 datasheet (7 pages, read in full), UG56 Quick Guide V1.5 (read in full: packing, hardware overview, LEDs, reset, installation, power, web access) and UG56 user guide V1.7 (introduction, LBT) |
| Primary source | Milesight *UG56 Datasheet*, https://resource.milesight.com/milesight/iot/document/ug56-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UG56 datasheet PDF. [UM] = Milesight *UG56 Quick Guide* V1.5 (24 Dec 2025) and *UG56 User Guide* V1.7 (15 Apr 2026). [VEN] = milesight.com UG56 page (accessories section). [PP] = Cytron product page.

## What it is
Cytron sells only the **non-cellular** version, MPN `UG56-915M` (915 MHz-band hardware), and states the frequency plan as Malaysia AS923-2 / Singapore AS923-1 [PP]. Milesight also makes a cellular version (PN contains "-Lxxxx") with an external cellular antenna [UM].

## Specifications
| Item | Value | Src |
|---|---|---|
| CPU | Quad-core 1.3 GHz, 64-bit ARM Cortex-A35 | [DS] |
| Memory / storage | 512 MB DDR3 RAM; 8 GB eMMC; 1 × internal micro SD slot | [DS] |
| LoRa chip | Semtech SX1302 | [DS] |
| LoRa channels | 8 (half-duplex) | [DS] |
| LoRa frequency bands (model range) | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| Cytron frequency plan | "Support Malaysia AS923-2, Singapore AS923-1"; MPN UG56-915M | [PP] |
| LoRa antenna connector | 1 × 50 Ω SMA connector (centre pin: SMA female) | [DS] |
| Sensitivity / Tx power | -140 dBm @ 292 bps; 27 dBm max | [DS] |
| LoRaWAN protocol | V1.0 and V1.0.2, Class A/B/C | [DS] |
| LBT (listen before talk) | Supported; not on AU915 or US915; disabled by default, RSSI target default -80 | [DS][UM] |
| Device capacity | Around 2000 Class A/B/C devices (10 min uplink interval) | [DS] |
| Range | Line of sight up to 15 km; about 2 km urban | [DS] |
| Ethernet | 1 × RJ45 WAN port, PoE PD; 10/100 Base-T, auto MDI/MDIX; 1.5 kV RMS isolation | [DS] |
| Wi-Fi | Internal antenna; IEEE 802.11 b/g/n, 2.4 GHz; AP or client mode | [DS] |
| Cellular (optional version) | 4G LTE, Class 3 (23 dBm ±2 dB), 1 × 50 Ω SMA (female centre pin), 1 × mini SIM (2FF) — not on Cytron's UG56-915M | [DS][PP] |
| USB | 1 × USB Type-C for power supply and console | [DS] |
| Reset button | 1 × RST (internal, behind the front cover) | [DS][UM] |
| LEDs | SYSTEM, LoRa (plus Ethernet link/rate LEDs on the port) | [DS][UM] |
| Built-in | Watchdog, timer | [DS] |
| Power input | (1) IEEE 802.3af PoE; (2) 5 V / 2 A on the Type-C port | [DS] |
| Power consumption | Typical 1.8 W, max 6.9 W | [DS] |
| Ingress protection | IP30 | [DS] |
| Housing | Metal, black; 186 g | [DS] |
| Dimensions | 110 × 75 × 24 mm | [DS] |
| Installation | Desktop, wall mounting, DIN rail mounting (DIN rail only on new hardware; optional clip kit) | [DS][UM] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Storage temperature | -40 °C to +85 °C | [DS] |
| Humidity | 0–95 % non-condensing at 25 °C | [DS] |
| Approvals | CE, CE (RED), RCM, FCC, ISED; RoHS | [DS] |
| Embedded network server | Milesight codec library and custom codecs; Gateway Fleet; multicast; FUOTA | [DS] |
| Integration | MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP, Modbus RTU over TCP | [DS] |
| Network / VPN / management | Same software set as UG65: PPPoE, SNMP, DDNS, OpenVPN/IPsec/PPTP/L2TP/GRE/DMVPN/WireGuard, firewall, WAN failover; Web, CLI, SMS, HTTP API, MQTT API, DeviceHub, Milesight Development Platform; Python SDK, Node-RED | [DS] |
| In the box (Milesight) | UG56, LoRaWAN magnetic antenna, wall mounting bracket, 2 × M3 bracket screws, 4 × wall mounting kits, quick start guide, warranty card; cellular magnetic antenna (cellular version only). Optional: Type-C cable (1 m) and power adapter; DIN rail clip kit | [UM][DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UG56 Industrial LoRaWAN® Gateway (without Cellular)"; brand Milesight; Code `LR-UG56-NC`; MPN `UG56-915M`; warranty 12 months; RM998.75; cashback RM29.96; "Availability: Backorder Only — Estimate 1 units available on 30 Oct 2026"; button BACKORDER [PP].
- Spec list matches [DS] (Cortex-A35 1.3 GHz, 512 MB DDR3, 8 GB eMMC, micro SD, SMA LoRa connector, 8 half-duplex channels, LBT, 10/100 PoE-PD port, 2.4 GHz Wi-Fi, SYSTEM and LoRa LEDs, internal reset, 802.3af PoE or 5 V 2 A Type-C, 1.8 W / 6.9 W, IP30, metal black, 186 g, -20 to +60 °C, 110 × 75 × 24 mm) and adds "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1" [PP].
- Approvals on [PP]: "CE, FCC, ISED" (shorter than [DS]) [PP].
- **Packing list:** 1 × UG56 device, 1 × LoRaWAN magnetic antenna, 1 × wall mounting bracket, 2 × bracket fixing screws, 4 × wall mounting kits, 1 × quick start guide, 1 × warranty card. No power adapter is listed [PP].
- **Resources:** UG56 datasheet, user guide and quick user guide (resource.milesight.com), payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware and SDK download [PP].
- Description: coverage "up to 3 floors up and down inside buildings", 2 km urban, 15 km rural; BACnet and Modbus for BMS; FUOTA; Gateway Fleet [PP].

## Interfaces, terminals and pin mapping
No terminal block or serial pins. Hardware overview from the quick guide [UM]:

| # | Item | Notes | Src |
|---|---|---|---|
| 1 | LoRaWAN antenna connector | 50 Ω SMA, female centre pin | [UM][DS] |
| 2 | SIM slot | Mini SIM (2FF); cellular version only; behind the front cover | [UM] |
| 3 | Micro SD slot | Behind the front cover | [UM] |
| 4 | Reset button | Behind the front cover | [UM] |
| 5 | Cellular antenna connector | Cellular version only (SMA) | [UM][DS] |
| 6 | LED indicators | SYS, LoRa | [UM] |
| 7 | Type-C port | 5 V power and console | [UM] |
| 8 | Ethernet port (PoE) | 10/100, 802.3af PD | [UM] |

**LED indications** [UM]:
| LED | State | Meaning |
|---|---|---|
| SYS | Off | System starting up |
| SYS | Red | System error |
| SYS | Green | Running properly |
| LoRa | Off / On | Packet forwarder not running / running well |
| Ethernet link (yellow) | Off / On / Blinking | Disconnected / connected / transmitting |
| Ethernet rate (green) | Off / On | Other modes / 100 Mbps |

**Default access** [UM]:
- Wired: only for firmware versions before 56.0.0.6 — static IP on the PC and open **192.168.23.150**.

## Rules and gotchas (for code, wiring and tutorials)
- **No power adapter in Cytron's box.** Power it from an 802.3af PoE switch/injector or a 5 V / 2 A Type-C supply; Milesight's Type-C cable and adapter are optional [DS][UM][PP].
- **PoE wins when both are connected** [UM].
- **Plug the Ethernet cable into the UG56 first**, then into the PoE switch/injector; Milesight warns that the other order can damage the PoE device or gateway [UM].
- **No hot-plugging** of SIM or micro SD: power off first. Open the front cover to reach the slots and reset button [UM].
- **Antenna placement:** vertical, magnetic base on metal, away from walls and obstacles, high up or near a window indoors, at least 50 cm between antennas [UM].
- **Region must match the end devices.** Set channels in *Packet Forwarder > Radio*; the gateway, network server and end devices must use the same channels [UM]. Cytron's unit is AS923-2 for Malaysia per [PP].
- **LBT is off by default** and not available on AU915/US915 [UM].
- **Ethernet is 10/100 only** and Wi-Fi is 2.4 GHz only [DS].
- **DIN rail:** only new hardware supports it, with the optional clip kit; the rail is 35 mm [DS][UM].

## Power and electrical limits
- 802.3af PoE on the RJ45, or 5 V / 2 A on USB Type-C [DS].
- Consumption: typical 1.8 W, max 6.9 W [DS].
- Ethernet isolation 1.5 kV RMS [DS].
- Environment: -20 °C to +60 °C, 0–95 % RH non-condensing, IP30 [DS].

## Software support
- Web GUI (HTTPS), CLI (SSH/Telnet), SMS, SNMP, HTTP API, MQTT API [DS].
- Embedded LoRaWAN network server with Milesight codecs, multicast, FUOTA, Gateway Fleet; MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP, Modbus RTU over TCP [DS].
- Built-in packet forwarders including Semtech and ChirpStack; compatible with The Things Stack, ChirpStack, Actility, AWS [DS][UM].
- Milesight IoT Cloud mode (enables the embedded NS and locks other NS settings) [UM].
- DeviceHub and Milesight Development Platform for remote management; Python SDK and Node-RED [DS].
- Payload decoders: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- Antennas: GA01 fiber-glass **S-N** antenna kits are made for the UG56 (SMA cable end): 130 cm FSN1300 and 60 cm FSN600 [VEN]. Cytron sells one: `milesight-ga01.md` [PP]. The supplied magnetic antenna (SMA-J, 868M/915M) also fits UC300 [VEN].
- Optional SP01 Type-C cable (1 m) and 5 V 1.5 A power adapter (P/N C1000) lists UG56 as applicable [VEN] — note the datasheet asks for 5 V / 2 A (see *Conflicts*).
- Optional 12000 mAh IP67 UPS battery kit (Type-C) lists UG56 [VEN].
- End devices: Milesight LoRaWAN sensors and controllers on the same plan, e.g. `milesight-em320-th.md`, `milesight-uc100.md`, `milesight-ft101.md`.
- Other gateways: `milesight-ug65.md` (IP65, Gigabit, optional LTE), `milesight-ug67.md` (outdoor IP67).

## Common mistakes / troubleshooting
- **Gateway does not power up:** no adapter in the box; check the PoE source is 802.3af or use a 5 V / 2 A Type-C supply [DS][PP].
- **Factory reset:** with SYS steady green, hold the reset button (behind the front cover) for more than 5 s until SYS blinks rapidly, release and wait; SYS goes off then steady green when reset is complete [UM].
- **Cannot reach 192.168.23.150:** wired default access applies only to firmware before 56.0.0.6; use the Wi-Fi AP and https://192.168.1.1 [UM].
- **IP conflict when changing the Ethernet IP:** change the WLAN subnet first [UM].
- **Using Wi-Fi as backhaul:** after joining a Wi-Fi network in client mode, set wlan0 as the main interface in *Network > Failover > WAN Failover* [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Type-C supply rating | [DS] 5 V / 2 A | [VEN] optional SP01 adapter 5 V / 1.5 A lists UG56 | [DS] wins: use 5 V / 2 A |
| Approvals | [DS] CE, CE(RED), RCM, FCC, ISED | [PP] CE, FCC, ISED | [DS] wins; [PP] list is shorter, not contradictory |
| Warranty | [UM] user guide "3-year warranty included" | [PP] 12 months | Cytron's 12 months applies to Cytron sales; confirm with Cytron |
| Backhaul list | [DS] intro "Ethernet, Wi-Fi and cellular" | [PP] non-cellular version: Ethernet and Wi-Fi only | Both right: cellular is a separate Milesight version, not Cytron's MPN |
| Stock status | Card list for this task: "cart" | [PP] 2026-10-21: "Backorder Only", estimate 1 unit on 30 Oct 2026 | Live page used: backorder |

## Needs verification
- Exact LoRaWAN plan for Malaysia (Cytron says AS923-2); confirm against the LoRa Alliance regional-parameters country table and Cytron's shipped configuration.
- Whether Cytron's stock is "new hardware" that accepts the DIN rail clip.
- Datasheet version/date (none printed).

## Sources
- [DS] UG56 Datasheet: https://resource.milesight.com/milesight/iot/document/ug56-datasheet-en.pdf (read 2026-10-21).
- [UM] UG56 Quick Guide V1.5, 24 Dec 2025: https://resource.milesight.com/milesight/iot/document/ug56-quick-guide-en.pdf (read in full 2026-10-21).
- [UM] UG56 User Guide V1.7, 15 Apr 2026: https://resource.milesight.com/milesight/iot/document/ug56-user-guide-en.pdf (introduction, LBT section).
- [VEN] Milesight UG56 page: https://www.milesight.com/iot/product/lorawan-gateway/ug56 (accessories; read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ug56-industrial-lorawan-gateway-without-cellular (read 2026-10-21).
