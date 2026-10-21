# Milesight UG65 — Verified Reference

| | |
|---|---|
| Product code | `UG65` (Milesight model). Cytron parent code `V-LR-UG65`; variants: With Cellular = Cytron code `LR-UG65`, MPN `UG65-L08GL-915M-EA`; Without Cellular = Cytron code `LR-UG65-NC`, MPN `UG65-915M-EA` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both variants: price, code, MPN, stock; spec, features, packing list, resources, FAQ), Milesight UG65 product page, UG65 datasheet (7 pages, read in full) and UG65 user guide V2.14 (Chapter 1, Chapter 2 web access, radio/packet-forwarder pages, factory reset) and UG65 Quick Guide V2.5 (packing list, hardware overview, LEDs, reset, installation) |
| Primary source | Milesight *UG65 Datasheet* (global model, except North America), https://resource.milesight.com/milesight/iot/document/ug65-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UG65 datasheet PDF (global model). [UM] = Milesight *UG65 User Guide* V2.14, 15 Apr 2026, and *UG65 Quick Guide* V2.5, 24 Dec 2025 (https://resource.milesight.com/milesight/iot/document/ug65-quick-guide-en.pdf; hosted by Milesight but not linked from the product pages). [DS: web] = the specification block on the milesight.com UG65 page (same values as the PDF). [VEN] = other parts of the milesight.com UG65 page (features, accessories, FAQ). [PP] = Cytron product page.

## What it is
Cytron sells two versions: **With Cellular** (MPN `UG65-L08GL-915M-EA`) and **Without Cellular** (MPN `UG65-915M-EA`) [PP]. Both are 915 MHz-band hardware ("915M" in the MPN); Cytron states the frequency plan as Malaysia AS923-2 / Singapore AS923-1 [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| CPU | Quad-core 1.5 GHz, 64-bit ARM Cortex-A53 (NXP per the web page) | [DS][VEN] |
| Memory / storage | 512 MB DDR4 RAM; 8 GB eMMC | [DS] |
| LoRa chip | Semtech SX1302 | [DS] |
| LoRa channels | 8 (half/full-duplex) | [DS] |
| LoRa frequency bands (model range) | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 (the available plans depend on the hardware model) | [DS][UM] |
| Cytron frequency plan | "Support Malaysia AS923-2, Singapore AS923-1"; both MPNs are "915M" hardware | [PP] |
| LoRa antenna | 2 × internal antennas + 1 × 50 Ω N-Female external connector | [DS] |
| Sensitivity | -140 dBm @ 292 bps | [DS] |
| LoRa Tx power | 27 dBm max | [DS] |
| LoRaWAN protocol | V1.0 Class A/B/C and V1.0.2 Class A/B/C | [DS] |
| Device capacity | Around 2000 Class A/B/C devices (10 min uplink interval) | [DS] |
| Range | Line of sight up to 15 km; about 2 km in urban areas | [DS][UM] |
| Ethernet | 1 × RJ45 WAN port, PoE PD supported; 10/100/1000 Base-T, auto MDI/MDIX, auto full/half duplex; 1.5 kV RMS isolation | [DS] |
| Wi-Fi | Internal antenna; IEEE 802.11 b/g/n, 2.4 GHz; AP or Client mode; AP WPA-PSK/WPA2-PSK, client also WPA/WPA2-Enterprise; Tx 13–18 dBm ±2 dBm by rate | [DS] |
| Cellular (optional) | 4G LTE; Tx power Class 3 (23 dBm ±2 dB); internal antenna; 1 × mini SIM (2FF) slot | [DS] |
| LTE bands | [NOT STATED] in the global datasheet | [DS] |
| USB | 1 × USB Type-C for power supply and console | [DS] |
| Reset button | 1 × RST | [DS] |
| LEDs | POWER, STATUS, LoRa, Wi-Fi, LTE, ETH | [DS] |
| Power connector | 1 × DC male jack, 2.1 × 5.5 mm | [DS] |
| Power input | (1) DC 9–24 V on the power jack; (2) IEEE 802.3af PoE; (3) 5 V / 1 A on USB Type-C | [DS] |
| Power consumption | Typical 2.9 W, max 4.2 W | [DS] |
| Built-in | Watchdog, RTC, timer | [DS] |
| Ingress protection | IP65 | [DS] |
| Material / colour | PC+ABS (UL94 V0), white and black | [DS] |
| Weight | 548 g | [DS] |
| Dimensions | 180 × 110 × 55.5 mm | [DS] |
| Installation | Desktop, wall or pole mounting | [DS] |
| Operating temperature | -40 °C to +70 °C; reduced cellular performance above 60 °C | [DS] |
| Storage temperature | -40 °C to +85 °C | [DS] |
| Humidity | 0–95 % non-condensing at 25 °C | [DS] |
| Approvals | CE, CE (RED), Telec, JATE, RCM; RoHS | [DS] |
| Embedded network server | Built-in Milesight codec library and custom codecs; Gateway Fleet (acts as network server for other Milesight gateways); multicast downlink; FUOTA for supported end devices | [DS] |
| Integration | MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP, Modbus RTU over TCP | [DS] |
| Packet forwarder | Noise analyzer, packet filter (white/black list), data retransmission after network recovery (some forwarder types only) | [DS] |
| Network / VPN | PPPoE, SNMP v1/v2c/v3, DHCP, DDNS, SNTP, Telnet, SSH etc.; OpenVPN, IPsec, PPTP, L2TP, GRE, DMVPN, WireGuard; firewall (ACL, DMZ, DNAT, MAC binding, IP/domain filtering); WAN failover | [DS] |
| Management | Web, CLI (SSH/Telnet), SMS, on-demand dial-up, SNMP, HTTP API, MQTT API, Milesight Development Platform, DeviceHub | [DS] |
| Apps | Python SDK, Node-RED | [DS] |
| In the box (Milesight) | 1 × DC jack power adapter, 1 × mounting bracket, 2 × bracket fixing screws, 4 × wall mounting kits, 1 × LoRaWAN antenna (18 cm) | [DS] |
| Optional antenna | 60 cm LoRaWAN fiber-glass N-N antenna kit (GA01 FNN600, for UG65); 130 cm GA01 FNN1300 (for UG65/UG67) | [DS][VEN] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UG65 Semi-Industrial LoRaWAN® Gateway (with or without Cellular)"; brand Milesight; parent code `V-LR-UG65`; warranty 12 months; 1 rating; option "Gateway Options": With Cellular / Without Cellular [PP].
- **With Cellular:** RM1,945.85, code `LR-UG65`, MPN `UG65-L08GL-915M-EA`, availability 17. **Without Cellular:** RM1,610.05, code `LR-UG65-NC`, MPN `UG65-915M-EA`, availability 2 [PP].
- Spec list matches [DS] for CPU, RAM, eMMC, LoRa antenna (2 internal + N-Female), 8 channels, -140 dBm, 27 dBm, LoRaWAN V1.0/V1.0.2 Class A/B/C, Gigabit PoE-PD port, 2.4 GHz Wi-Fi, mini SIM, LEDs, 2.1 × 5.5 mm jack, 9–24 VDC / 802.3af PoE / 5 V 1 A Type-C, 2.9 W / 4.2 W, IP65, -40 to +70 °C, approvals. It adds "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1" and "Supports: 2G, 3G & 4G" [PP].
- The Cytron description and feature list add claims that are not in [DS]: "dual-band Wi-Fi (2.4GHz & 5GHz)", "LTE Cat-4 with fallback to 3G/2G", DIN-rail mounting, and AWS IoT Core compatibility (see *Conflicts*) [PP].
- **Packing list:** "1 x UG65 Semi-Industrial LoRaWAN® Gateway with or without cellular (Based on the option chosen)" — accessories are not listed [PP].
- **Resources:** UG65 datasheet and user guide (resource.milesight.com), payload decoder (github.com/Milesight-IoT/SensorDecoders), firmware and SDK download (milesight.com download centre) [PP].
- **FAQ (Cytron page):** NTP renewal interval is fixed at 1 hour; the packet-forwarder Keep Alive Interval is a UDP pull request for Semtech-type servers, not a TCP keep-alive; FUOTA of the gateway via CUPS on AWS IoT Core for LoRaWAN is not supported — use Milesight DeviceHub for remote upgrades [PP].
- Related Cytron tutorials: "How to access Milesight UG65 Web UI" and "How to connect Milesight Sensor and Gateway to Milesight IoT Cloud" (Ebi Syakirin Aznan, 02 May 2025); "Milesight-BeaverIoT Quick Start Guide" (Hadrie Hakimi, 09 Jul 2026) [PP].
- "You May Also Need" lists the GA01 LoRaWAN Fiber Glass S-N Antenna Kit (for Milesight UG56) and the EM320 and UC100 sensors/controllers [PP].

## Interfaces, terminals and pin mapping
The UG65 has no terminal block or serial pins. Its connectors [DS]:

| Connector | Function | Src |
|---|---|---|
| RJ45 (WAN) | 10/100/1000 Ethernet backhaul; IEEE 802.3af PoE powered device input | [DS] |
| DC jack (2.1 × 5.5 mm, male) | 9–24 VDC power input | [DS] |
| USB Type-C | 5 V / 1 A power input and console | [DS] |
| N-Female (50 Ω) | External LoRa antenna | [DS] |
| Mini SIM (2FF) slot | Cellular version only | [DS] |
| RST button | Reboot / factory reset (hold more than 5 s until STATUS blinks) | [DS][UM] |

Quick-guide layout [UM]: **front panel** = LED area (POWER, STATUS, LoRa, Wi-Fi, LTE, ETH) and the LoRaWAN antenna connector ("only for external antenna version"); **rear panel** = bracket mounting screws, SIM slot (under a protective cover opened with a screwdriver), Type-C port, Ethernet port (PoE), power connector, reset button, waterproof silicone and cable groove.

**LED indications** [UM]:
| LED | State | Meaning |
|---|---|---|
| POWER | Off / On | Power off / on |
| STATUS | Static blue / red | Running properly / system error |
| LoRa | Off / blue | Packet forwarder off / running well |
| Wi-Fi | Off / blue | Wi-Fi disabled / enabled |
| LTE | Off | SIM registering, failed, or no SIM |
| LTE | Blue blinking slowly / rapidly / static | Registered and ready / dialling up / dialled up |
| ETH | Off / static blue | Disconnected / connected |

Internal antennas: 2 × LoRa, Wi-Fi and LTE are internal [DS]. The [UM] radio page has an "Antenna" setting to choose the antenna transmission type "when using EA version"; Cytron's MPNs both end in `-EA` (meaning of the suffix inferred, see *Needs verification*).

**Default access** [UM]:
- Wired (firmware v60.0.0.46 or earlier only): connect a PC to the ETH port (directly or through a PoE injector), set a static IP in the same subnet and open **192.168.23.150**.
- Since UG V2.11 the WAN port defaults to DHCP [UM].
- Gateway EUI format: ETH port MAC address with "FFFE" inserted in the middle; not editable [UM]. (Device-specific values are not copied.)

## Rules and gotchas (for code, wiring and tutorials)
- **Pick the right regional plan.** The hardware is band-specific (Cytron's units are "915M"). Select the matching LoRaWAN "Region" in *Packet Forwarder > Radios*; the available plans depend on the model [UM]. Cytron states AS923-2 for Malaysia and AS923-1 for Singapore [PP]; end devices must use the same plan.
- **Fit the external LoRa antenna (N-Female) before transmitting** when the antenna type is set to external; UG V2.4 changed the default antenna type to external [UM]. The 18 cm LoRa antenna is in Milesight's standard box [DS].
- **Wi-Fi is 2.4 GHz only** (802.11 b/g/n) per [DS]; Cytron's "dual-band 5 GHz" text is wrong (see *Conflicts*).
- **PoE is 802.3af** (standard PoE), not passive PoE [DS]. If DC and PoE are both connected, DC power is used [UM].
- **Outdoors (eaves etc.):** pass the Ethernet and power cables through the waterproof silicone opening, lay them in the cable grooves and screw the rear protective cover back on; do not compress or damage the silicone [UM].
- **Embedded-antenna mode:** do not let the front panel face a wall [UM].
- **SIM:** only units whose PN contains "-Lxxxx" have cellular (Cytron's `UG65-L08GL-915M-EA`) [UM][PP].
- **Cellular is internal-antenna, mini SIM (2FF)**, on the With Cellular version only [DS][PP].
- **Do not run the noise analyzer while forwarding packets**: Milesight says it affects downlink transmission [UM].
- For data to a server, use the embedded network server with MQTT(s)/HTTP(s) integration, or a packet forwarder (Semtech UDP, Basic Station, ChirpStack, etc.) to an external LNS [DS][UM].

## Power and electrical limits
- DC 9–24 V on the 2.1 × 5.5 mm jack, IEEE 802.3af PoE on the RJ45, or 5 V / 1 A on USB Type-C [DS].
- Consumption: typical 2.9 W, max 4.2 W [DS].
- Ethernet isolation 1.5 kV RMS [DS].
- Environment: -40 °C to +70 °C (cellular performance reduced above 60 °C), 0–95 % RH non-condensing, IP65 [DS].
- A DC jack power adapter is in Milesight's standard package [DS]; Cytron's packing list does not mention it (see *Needs verification*).

## Software support
- Web GUI (HTTPS), CLI over SSH/Telnet, SMS, SNMP, HTTP API and MQTT API [DS].
- Embedded LoRaWAN network server with built-in Milesight payload codecs, custom codecs, multicast, FUOTA, Gateway Fleet; integrations MQTT(s), HTTP(s), BACnet/IP, BACnet/SC (UM V2.13), Modbus TCP, Modbus RTU over TCP; Modbus server added in UM V2.10 [DS][UM].
- Packet forwarder to external servers; compatible with The Things Stack, ChirpStack, Actility, AWS and others (datasheet); Cytron also names TTN and AWS IoT Core [DS][PP].
- Remote management: Milesight DeviceHub, Milesight Development Platform; Cytron also names Milesight IoT Cloud and Yeastar Workplace [DS][PP].
- Apps on the gateway: Python SDK and Node-RED [DS].
- Firmware files are `.bin`; upgrade in *Maintenance > Upgrade*; Milesight suggests contacting its support before upgrading [UM].
- Payload decoders for Milesight sensors: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- End devices: any LoRaWAN V1.0 / V1.0.2 Class A/B/C device on the same regional plan, e.g. Milesight sensors and controllers in this KB: `milesight-em320-th.md`, `milesight-em300-th.md`, `milesight-uc100.md`, `milesight-ws101.md`, `milesight-ft101.md` (field tester) [DS][PP].
- Antennas: Milesight lists the GA01 60 cm fiber-glass N-N antenna kit (FNN600, UG65) and the GA01 130 cm N-N kit (FNN1300, UG65/UG67) as accessories [DS][VEN]. Cytron's GA01 listing (`milesight-ga01.md`) is the **S-N** kit "for Milesight UG56"; check the connector before pairing it with a UG65 (N-Female) [PP].
- Optional Milesight 12000 mAh IP67 UPS battery kit (Type-C version) lists UG65 as applicable [VEN].
- Other Milesight gateways in this KB: `milesight-ug56.md` (industrial, IP30), `milesight-ug67.md` (outdoor, IP67).

## Common mistakes / troubleshooting
- **Cannot open the web GUI by cable:** on current firmware the default access is over the gateway's Wi-Fi AP at https://192.168.1.1; wired access at 192.168.23.150 applies only to firmware v60.0.0.46 or earlier [UM].
- **Login page locked:** five wrong logins lock it for 10 minutes [UM].
- **Factory reset:** web *Maintenance > Backup and Restore > Reset*, or, with STATUS static blue, hold the reset button for more than 5 s until STATUS blinks rapidly, release and wait; STATUS goes off then static blue [UM].
- **Sensors do not join:** check that the gateway Region and the device plan match (AS923-x vs others) and that the external antenna is fitted [UM].
- **Gateway remote upgrade through AWS CUPS fails:** not supported; use DeviceHub [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Wi-Fi band | [DS] IEEE 802.11 b/g/n, 2.4 GHz only | [PP] description/features "dual-band Wi-Fi (2.4GHz & 5GHz)" (the [PP] spec table says 2.4 GHz) | [DS] wins: 2.4 GHz only |
| Cellular generations | [DS] "4G LTE" (no category, no 2G/3G stated) | [PP] "LTE Cat-4 with fallback to 3G/2G", "Supports: 2G, 3G & 4G"; [UM] "global 2G/3G/LTE options" | [DS] wording used; Cat 4 and 2G/3G fallback unconfirmed (see *Needs verification*) |
| Mounting | [DS] desktop, wall or pole | [PP] "wall-mounted, DIN rail mounted, or placed on a desktop" | [DS] wins; DIN rail not stated by Milesight |
| Warranty | [UM] "3-year warranty included" | [PP] warranty 12 months | Cytron's 12 months is the sale warranty stated for Cytron purchases; manufacturer terms may differ — confirm with Cytron |
| Product name | [DS][UM] "Semi-Industrial LoRaWAN® Gateway" | [VEN] milesight.com "Indoor LoRaWAN® Gateway" | Same product; Milesight renamed the web title. IP65 in all sources |
| Packing list | [DS][UM] DC jack power adapter, bracket, 2 bracket screws, 4 wall kits, 18 cm LoRa antenna, quick start guide, warranty card | [PP] "1 x UG65 … gateway" only | Unresolved: confirm with Cytron what is in the box |
| Antenna kit recommended | [PP] recommends GA01 S-N kit "for UG56" | [DS][VEN] UG65 has an N-Female connector; Milesight lists N-N GA01 kits for UG65 | Check the connector; the S-N kit is meant for UG56 (inferred) |

## Needs verification
- Exact LoRaWAN plan for Malaysia: Cytron says AS923-2; confirm against the LoRa Alliance regional-parameters country table and Cytron's shipped configuration.
- LTE category and bands of `UG65-L08GL-915M-EA` (not in the global datasheet); whether 2G/3G fallback exists.
- Meaning of the `-EA` MPN suffix (inferred: external-antenna version) and of `L08GL`.
- What Cytron ships in the box (adapter, bracket, LoRa antenna) — [PP] lists the gateway only.
- Datasheet version/date (none printed).

## Sources
- [DS] UG65 Datasheet (global model): https://resource.milesight.com/milesight/iot/document/ug65-datasheet-en.pdf (read 2026-10-21). North America model datasheet (not read): https://resource.milesight.com/milesight/iot/document/ug65-datasheet-north-america-en.pdf
- [UM] UG65 User Guide V2.14, 15 Apr 2026: https://resource.milesight.com/milesight/iot/document/ug65-user-guide-en.pdf (read 2026-10-21: preface, revision history, Chapter 1, Chapter 2, radios/packet forwarder, factory reset, firmware upgrade).
- [UM] UG65 Quick Guide V2.5, 24 Dec 2025: https://resource.milesight.com/milesight/iot/document/ug65-quick-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight UG65 page: https://www.milesight.com/iot/product/lorawan-gateway/ug65 (features, accessories, documents; read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ug65-semi-industrial-lorawan-gateway-with-without-cellular (read 2026-10-21).
- [PP] Payload decoders: https://github.com/Milesight-IoT/SensorDecoders
