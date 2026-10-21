# Teltonika RUT200 — Verified Reference

| | |
|---|---|
| Product code | `RUT200` (Teltonika model). Cytron code `RUT-200`, MPN / Teltonika order code `RUT200015000` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full "Features" technical specification, Ordering, Downloads and Certifications tabs) read. The Teltonika Wiki could not be opened (Cloudflare bot check on every Wiki URL), so no [UM] pinout, LED or QSG page was read |
| Primary source | Teltonika Networks RUT200 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/rut200 (read 2026-10-21; the Downloads tab lists "RUT200 DATASHEET (EN)" updated 2026-09-24, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the Ordering, Downloads and Certifications tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page, so exact pin numbers, LED meanings and the default LAN address are not given here; see *Needs verification*.

## What it is
It is the smallest cellular router in this Cytron range: single SIM, no GNSS, no serial port, no USB and no I/O socket beyond the power plug. The RUT140 (`teltonika-rut140.md`) is the Ethernet + Wi-Fi only sibling with no cellular modem; the RUT901 adds dual SIM and 4 Ethernet ports [DS: web].
The unit Cytron sells is order code `RUT200015000`: the "RUT200 *1****" hardware version (Europe, Australia, Asia-Pacific bands), standard package with Universal PSU, without eSIM [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 4G LTE Cat 4 up to 150 DL / 50 UL Mbps; 3G up to 21 DL / 5.76 UL Mbps; 2G up to 236.8 DL / 236.8 UL kbps | [DS: web] |
| 3GPP release | Release 9 | [DS: web] |
| Bands (RUT200 *1**** version, Cytron's MPN) | LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B5, B8; 2G B3, B8 | [VEN: ordering] |
| SIM | 1 × SIM slot (Mini SIM – 2FF), 1.8 V / 3 V, external SIM holder | [DS: web] |
| eSIM | Consumer eSIM, up to 7 profiles, no data plan included — "feature availability varies by order code"; only the 31**** and 34**** versions are listed with eSIM | [DS: web][VEN] |
| Wi-Fi | 802.11b/g/n (Wi-Fi 4), Access Point (AP), Station (STA); up to 50 simultaneous users; WPA2/WPA3 options; mesh 802.11s, 802.11r/k/v | [DS: web] |
| Ethernet WAN | 1 × WAN port 10/100 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Ethernet LAN | 1 × LAN port 10/100 Mbps (IEEE 802.3, 802.3u), auto MDI/MDIX | [DS: web] |
| Digital input | 1 × DI on the 4-pin power connector: 0–6 V = logic low, 8–30 V = logic high | [DS: web] |
| Digital output | 1 × open collector output on the 4-pin power connector, max 30 V, 300 mA | [DS: web] |
| I/O events | Email, RMS, SMS; I/O juggler | [DS: web] |
| CPU | Mediatek, 580 MHz, MIPS 24KEc | [DS: web] |
| RAM | 128 MB, DDR2 | [DS: web] |
| Flash | 16 MB, SPI Flash | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Power connector | 4-pin industrial DC power socket | [DS: web] |
| Input voltage | 9–30 VDC, reverse polarity protection; surge protection >31 VDC 10 µs max | [DS: web] |
| Passive PoE | Passive PoE over spare pairs, power through LAN1 port, Mode B, 9–30 VDC; not compatible with IEEE 802.3af, 802.3at or 802.3bt | [DS: web] |
| Power consumption | < 6.5 W max | [DS: web] |
| Antenna connectors | 2 × SMA for LTE, 1 × RP-SMA for Wi-Fi | [DS: web] |
| Status LEDs | 3 × connection type, 5 × connection strength, 2 × LAN status, 1 × power | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| Housing | Aluminium housing, plastic panels | [DS: web] |
| Dimensions (W × H × D) | 83 × 25 × 74 mm | [DS: web] |
| Weight | 125 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface (all require additional kit) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
| Approvals (APAC list) | RCM, NCC, Thailand NBTC, SIRIM, IMDA, SDPPI (POSTEL), ETA-WPC, NTC, MTCTE; also CE/RED, UKCA, RoHS, REACH, CB Scheme, GCF, UN ECE R10/R118 and others | [VEN: certifications] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "RUT200 LTE Cat 4 Industrial Grade Router"; brand Teltonika; Code `RUT-200`; MPN `RUT200015000`; warranty 12 months; RM566.00, RM549.02 for 3 or more; cashback RM16.98; availability 17; 3 ratings (5 out of 5) [PP].
- "Accessories you may need" (sold separately): Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00), Teltonika DIN Rail Kit (RM49.00) [PP].
- Hardware list matches [DS: web] for CPU, memory, storage, power (4-pin, 9–30 VDC), SIM (1 × external 2FF holder), antennas, Ethernet, Wi-Fi, I/O, LEDs, temperature, size and weight. Differences are listed under *Conflicts* (3G speed, regions) [PP].
- Software list: RutOS; Auto APN, band lock; failover, VLAN, QoS, load balancing; OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard; WebUI, CLI, SSH, call, SMS, TR-069, SNMP, JSON-RPC, MQTT, MODBUS, RMS; RMS, FOTA, Azure IoT Hub, Cloud of Things, Cumulocity, ThingWorx; DDNS, VRRP, WOL, web filter, UPnP, traffic logging [PP].
- **Packing list:** 1 × Router RUT200, 1 × 9W power supply, 2 × mobile antennas (swivel, SMA male), 1 × Wi-Fi antenna (swivel, RP-SMA male), 1 × Quick Start Guide [PP]. This matches Teltonika's standard package (which also lists the packaging box) [VEN].
- RMS: the page says every Teltonika device, including this one, comes with a free 30-day RMS trial [PP].
- **Resources:** Quick Start Guide (Wiki `QSG_RUT200`), Configuration examples (Wiki `RUT200_Configuration_Examples`), Manual (Wiki `RUT200_Manual`), Crowd Support Forum (community.teltonika.lt), Datasheet (Google Drive copy), Flyer, and a link to the Teltonika product page [PP].
- Use cases listed: cross-industry monitoring cloud, predictive maintenance, energy storage systems, Wi-Fi mesh for pallet shuttles, vending machine POS management, parcel terminal management [PP].

## Interfaces, terminals and pin mapping
**Exact pin numbers were not read.** The Teltonika Wiki pages "RUT200 Power Socket Pinout", "RUT200 Input/Output" and "RUT200 LEDs" could not be opened (Cloudflare bot check). What the specification says about each connector [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 4-pin industrial DC power socket | Power input 9–30 VDC, plus 1 × digital input (0–6 V low / 8–30 V high) and 1 × open collector output (30 V, 300 mA) | [DS: web] |
| RJ45 × 2 | 1 WAN (configurable as LAN [PP]) + 1 LAN, 10/100 Mbps; LAN1 also accepts passive PoE (Mode B, 9–30 VDC) | [DS: web][PP] |
| SMA × 2 | LTE antennas (main and auxiliary) | [DS: web] |
| RP-SMA × 1 | Wi-Fi antenna | [DS: web] |
| SIM × 1 | Mini SIM (2FF) external holder | [DS: web] |
| Reset button | Reboot / user default / factory reset | [DS: web] |

## Rules and gotchas (for code, wiring and tutorials)
- **Get pin numbers from the Teltonika Wiki before wiring the 4-pin plug.** This file does not give them (not read). Use "RUT200 Power Socket Pinout" / "RUT200 Input/Output" on wiki.teltonika-networks.com.
- **The 4-pin power socket also carries I/O** (one DI, one open collector DO). Do not treat the extra pins as spare [DS: web].
- **DI thresholds:** 0–6 V reads low, 8–30 V reads high; 6–8 V is undefined [DS: web].
- **DO is open collector, 30 V / 300 mA max.** It switches a load to ground; the load needs its own supply (inferred from "open collector") [DS: web].
- **Passive PoE on LAN1 is not 802.3af/at/bt.** A standard PoE switch will not power it. Use a passive injector in the 9–30 VDC range [DS: web].
- **Wi-Fi is 2.4 GHz only** (802.11b/g/n) with a single RP-SMA antenna [DS: web].
- **Single SIM.** Failover is to Wi-Fi WAN or wired WAN, not to a second SIM; Cytron's order code has no eSIM (inferred from the Ordering tab) [DS: web][VEN].
- **Modbus is TCP only** (no serial port on this model) [DS: web].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–30 VDC on the 4-pin socket, reverse polarity protected, surge protection >31 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B (spare pairs), 9–30 VDC [DS: web].
- Consumption: < 6.5 W max [DS: web]. A 9 W PSU is in the box; Cytron's MPN is the Universal PSU version [PP][VEN].
- I/O limits: DI 0–6 V low / 8–30 V high; DO open collector 30 V, 300 mA [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI over HTTP/HTTPS, CLI, SSH v1/v2, SMS and call control, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS [DS: web].
- Mobile features: SIM status, SMS (email/HTTP/SMS forwarding, scheduled SMS, autoreply, SMPP), USSD, operator block/allow list, multiple PDN, band lock, SIM PIN management, auto APN, bridge and passthrough modes [DS: web].
- Industrial protocols: Modbus TCP server/client; Modbus–MQTT gateway; DNP3 station/outstation (TCP); BACnet router (IP); OPC UA client/server (TCP); DLMS/COSEM client (TCP) [DS: web].
- Data to server: HTTP(S), MQTT, Azure MQTT, custom Lua. IoT platforms: ThingWorx, Cumulocity, Azure IoT Hub, AWS IoT Core [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP (incl. L2TPv3), Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc [DS: web].
- Development: SDK with build environment; Busybox shell, Lua, C, C++; Package Manager; GPL customisation; Teltonika Networks Web API (beta) at https://developers.teltonika-networks.com [DS: web].
- Firmware: update from file, FOTA, RMS; keep settings on update; factory reset restores IP address, PIN and user data [DS: web].
- RMS (Remote Management System) 30-day free trial [PP].

## Compatibility and accessories
- Sold separately by Cytron: Teltonika 4G Mobile Magnetic SMA Antenna (RM65), Teltonika DIN Rail Kit (RM49) [PP]. DIN rail, wall or flat-surface mounting all need an extra kit [DS: web].
- In the box: 9 W PSU, 2 × LTE swivel antennas (SMA), 1 × Wi-Fi swivel antenna (RP-SMA) [PP][VEN].
- Bands of Cytron's version: see *Specifications*. Teltonika lists the *1**** version for Europe, Australia and Asia-Pacific; Malaysia is not named individually [VEN]. SIRIM appears in the approvals list [VEN].
- Related Cytron-sold Teltonika models: RUT140 (Ethernet + Wi-Fi only, no cellular, 3-pin terminal power), RUT901 (dual SIM, 4 Ethernet), RUT906 (dual SIM, 4 Ethernet, GNSS, RS232/RS485, USB, 10-pin I/O) [DS: web].

## Common mistakes / troubleshooting
- **No power over PoE from a standard PoE switch:** the RUT200 only takes passive PoE (Mode B, 9–30 VDC), not 802.3af/at [DS: web].
- **No mobile data:** check that the SIM is in the single 2FF holder, that the APN is right (auto APN can be overridden) and that the operator's band is in the *1**** band list [DS: web][VEN].
- **Input never reads high:** the DI needs 8–30 V for logic high [DS: web].
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset (reset button) restores the default IP and login [DS: web].
- **Expecting dual SIM or serial:** this model has one SIM and no RS232/RS485; choose RUT901 or RUT906 [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 3G speed | [PP] "3G – Up to 42 Mbps" | [DS: web] 3G up to 21 DL / 5.76 UL Mbps | [DS: web] wins: 21 Mbps down |
| Network coverage | [PP] "compatibility spans networks in Asia, CIS, the Middle East, Africa, and South America" | [VEN] Cytron's *1**** version is listed for Europe, Australia, Asia-Pacific; regional availability excludes Russia, Belarus and Iran; Latin America is a different version (*2****) | [VEN] for the unit sold. The [PP] sentence describes the model family, not Cytron's order code |
| "SMS Features" line | [PP] lists DDoS and port-scan prevention under "SMS Features" (copy of the Security line) | [DS: web] SMS: status, configuration, email/HTTP/SMS forwarding, scheduled SMS, autoreply, SMPP | [DS: web]. Copy error on the Cytron page |
| WAN port role | [PP] "1 x WAN (configurable as LAN)" | [DS: web] "1 x WAN port" (no statement on reassignment) | Not a contradiction; [PP] only. Confirm in the Wiki manual |

## Needs verification
- **All pin numbers** of the 4-pin power socket (V+, GND, DI, DO order) — Wiki not readable on 2026-10-21 (Cloudflare check).
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG or the device label).
- LED meaning table (Wiki "RUT200 LEDs" not read).
- Whether the open collector DO needs an external pull-up / supply (inferred yes from "open collector").
- Band fit for Malaysian operators (the *1**** list includes B1, B3, B5, B8, B28, B38, B40, B41; operator fit inferred, not stated) [VEN].
- Datasheet PDF version/date (Teltonika lists 2026-09-24; the Cytron Google Drive copy was not opened).

## Sources
- [DS: web] Teltonika RUT200 product page, Features (technical specification): https://teltonika-networks.com/products/routers/rut200 (read 2026-10-21).
- [VEN] Same page: Ordering tab (standard package, versions and order codes, HS code), Downloads tab (flyer updated 2024-06-11, datasheet updated 2026-09-24), Certifications tab (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-rut200-lte-cat-4-industrial-grade-router (read 2026-10-21).
- [PP] Datasheet link on the Cytron page (Google Drive, not opened): (Cytron document — link not public)
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/RUT200, https://wiki.teltonika-networks.com/view/RUT200_Manual, https://wiki.teltonika-networks.com/view/RUT200_Power_Socket_Pinout, https://wiki.teltonika-networks.com/view/QSG_RUT200, https://wiki.teltonika-networks.com/view/RUT200_Configuration_Examples
