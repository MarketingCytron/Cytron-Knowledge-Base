# Teltonika RUT956 — Verified Reference

| | |
|---|---|
| Product code | `RUT956` (Teltonika model). Cytron code `RUT-956`, MPN / Teltonika order code `RUT956200100` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full technical specification, ordering/versions tab, downloads tab) read. The Teltonika Wiki could not be opened (Cloudflare bot check), so no [UM] pinout page was read. The datasheet PDF link on the Cytron page returns 404 |
| Primary source | Teltonika Networks RUT956 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/rut956 (read 2026-10-21; the downloads tab lists "RUT956 DATASHEET (EN)" updated 2026-09-24, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the ordering and downloads tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page. Pin numbers are therefore not given here; see *Needs verification*.

## What it is
The unit Cytron sells is order code `RUT956200100`: the "RUT956 2*****" hardware version (Europe, Middle East, Africa, Korea, Thailand bands), standard package with UK PSU [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 4G LTE Cat 4 up to 150 DL / 50 UL Mbps; 3G up to 21 DL / 5.76 UL Mbps; 2G up to 236.8 DL / 236.8 UL kbps | [DS: web] |
| 3GPP release | Release 11 | [DS: web] |
| LTE bands (RUT956 2***** version, Cytron's MPN) | LTE-FDD B1, B3, B7, B8, B20, B28A; LTE-TDD B38, B40, B41; 3G B1, B8; 2G B3, B8 | [VEN: ordering] |
| SIM | 2 × SIM slots (Mini SIM – 2FF), 1.8 V / 3 V, external SIM holders; eSIM only on order codes that include it (the *3**** versions) | [DS: web][VEN] |
| SIM switch | Dual SIM; auto-switch on weak signal, data limit, SMS limit, roaming, no network, network denied, data connection fail, SIM idle protection | [DS: web] |
| Wi-Fi | 802.11b/g/n (Wi-Fi 4), Access Point (AP), Station (STA); up to 100 simultaneous users; WPA2/WPA3 options; mesh 802.11s, 802.11r/k/v | [DS: web] |
| Ethernet WAN | 1 × WAN port 10/100 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Ethernet LAN | 3 × LAN ports 10/100 Mbps (IEEE 802.3, 802.3u), auto MDI/MDIX | [DS: web] |
| GNSS | GPS, GLONASS, BeiDou, Galileo and QZSS; NMEA 0183; NTRIP; geofencing | [DS: web] |
| RS232 | DB9 connector, RS232 with RTS/CTS flow control | [DS: web] |
| RS485 | 6-pin industrial socket; Full Duplex (4 wires) and Half Duplex (2 wires); 300–115200 baud | [DS: web] |
| Serial functions | Console, Serial over IP, Modem, MODBUS gateway, NTRIP Client | [DS: web] |
| USB | 1 × USB A host port, USB 2.0 (external HDD, flash drive, additional modem, printer, USB-serial adapter) | [DS: web] |
| SD card | Micro SD (internal), up to 2 TB; FAT32, NTFS, ext2/3/4 | [DS: web] |
| Inputs | 1 × digital dry input (0–3 V); 1 × galvanically isolated digital input (0–30 V); 1 × analog input (0–24 V, with 4–20 mA capability); 1 × non-isolated digital input on the 4-pin power connector (0–5 V = logic low, 8–30 V = logic high) | [DS: web] |
| Outputs | 1 × digital open collector output (30 V, 250 mA); 1 × SPST relay output (40 V, 4 A); 1 × digital open collector output on the 4-pin power connector (30 V, 300 mA) | [DS: web] |
| I/O sockets | 10-pin industrial socket for inputs/outputs; 1 DI + 1 DO on the 4-pin power connector "available from HW revision 1600" | [DS: web] |
| CPU | Mediatek, 580 MHz, MIPS 24KEc | [DS: web] |
| RAM | 128 MB, DDR2 | [DS: web] |
| Flash | 16 MB, SPI Flash | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Power connector | 4-pin industrial DC power socket | [DS: web] |
| Input voltage | 9–30 VDC, reverse polarity protection; surge protection >31 VDC 10 µs max | [DS: web] |
| Passive PoE | Passive PoE over spare pairs on LAN1, Mode B, 9–30 VDC; not compatible with IEEE 802.3af, 802.3at or 802.3bt | [DS: web] |
| Power consumption | < 2 W idle, < 7 W max | [DS: web] |
| Antenna connectors | 2 × SMA for LTE, 2 × RP-SMA for Wi-Fi, 1 × SMA for GNSS | [DS: web] |
| Status LEDs | 1 × bi-colour connection status, 5 × mobile connection strength, 4 × ETH status, 1 × power | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| Housing | Aluminium housing, plastic panels | [DS: web] |
| Dimensions (W × H × D) | 110 × 50 × 100 mm | [DS: web] |
| Weight | 287 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface (all require additional kit) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "RUT956 LTE Cat 4 Industrial Grade Router"; brand Teltonika; Code `RUT-956`; MPN `RUT956200100`; warranty 12 months; RM1,205.00, RM1,168.85 for 5 or more; cashback RM36.15; availability 4; 3 ratings (5 out of 5) [PP].
- "Accessories you may need" (sold separately): Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00), Teltonika DIN Rail Kit (RM49.00) [PP].
- Hardware list matches [DS: web] for mobile, CPU, memory, storage, power (4-pin, 9–30 VDC), SIM, antennas, Ethernet, Wi-Fi, GNSS, serial, USB, LEDs, temperature, housing, size and weight. It lists SIM as "eSIM (Optional)" and the 10-pin I/O as isolated DI, dry DI, analog input, "isolated open collector output (requires external voltage)" and non-latching relay output [PP].
- Software list: RutOS; Auto APN, band lock, SIM switch, operator black/white list, data/SMS limits; routing, failover, firewall, DHCP, DDNS, QoS/SQM, load balancing, VoIP passthrough, SSHFS; WebUI, CLI, SSH, call, SMS, TR-069, SNMP, JSON-RPC, MQTT, BACnet, DNP3, OPC UA, MODBUS, RMS; Modbus TCP slave/master, RTU master, RTU gateway, Modbus over MQTT [PP].
- **Packing list:** router (printed as "RUT906", see *Conflicts*), 9W PSU, 2 × mobile antennas (magnetic, SMA male, 3 m), 2 × Wi-Fi antennas (magnetic, RP-SMA male, 1.5 m), 1 × GNSS antenna (adhesive, SMA male, 3 m), RS485 connector block, I/O connector block, Ethernet cable (1.5 m), SIM adapter kit, Quick Start Guide, packaging box [PP]. This matches Teltonika's standard package [VEN].
- RMS: the page says every Teltonika device, including this one, comes with a free 30-day RMS trial [PP].
- **Resources:** Datasheet (teltonika-networks.com/cdn/…/717017-rut956-datasheet-2024-v11.pdf — returned 404 on 2026-10-21), Quick Start Guide (Wiki QSG_RUT956), Certificate & Approval, Firmware download, SDK download, 3D drawing (all on wiki.teltonika-networks.com) [PP].
- Use cases listed: bus monitoring, radio broadcasts, grain silo connectivity, mine safety (TSF), remotely operated underwater vehicles [PP].

## Interfaces, terminals and pin mapping
**Exact pin numbers were not read.** The Teltonika Wiki pages "RUT956 Power Socket Pinout", "RUT956 Input/Output" and the RS485 page could not be opened (Cloudflare bot check). What the specification says about each connector [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 4-pin industrial DC power socket | Power input 9–30 VDC, plus 1 × non-isolated digital input (0–5 V low / 8–30 V high) and 1 × open collector output (30 V, 300 mA). I/O on this socket only from HW revision 1600 | [DS: web] |
| 10-pin industrial socket | Isolated DI (0–30 V), dry DI (0–3 V), analog input (0–24 V or 4–20 mA), open collector output (30 V, 250 mA), SPST relay output (40 V, 4 A) | [DS: web] |
| 6-pin industrial socket | RS485, full duplex (4-wire) or half duplex (2-wire), 300–115200 baud | [DS: web] |
| DB9 socket | RS232 with RTS/CTS flow control | [DS: web] |
| RJ45 × 4 | 1 WAN (configurable as LAN [PP]) + 3 LAN, 10/100 Mbps; LAN1 also accepts passive PoE (Mode B) | [DS: web][PP] |
| USB A | USB 2.0 host | [DS: web] |
| SMA × 2 / RP-SMA × 2 / SMA × 1 | LTE main/aux, Wi-Fi × 2, GNSS | [DS: web] |
| SIM × 2 | Mini SIM (2FF) holders on the housing | [DS: web] |

Mating plugs for the 10-pin I/O and 6-pin RS485 sockets are in the box ("I/O connector block", "RS485 connector block") [PP][VEN].

## Rules and gotchas (for code, wiring and tutorials)
- **Get pin numbers from the Teltonika Wiki before wiring.** This file does not give them (not read). Use the "RUT956 Power Socket Pinout", "RUT956 Input/Output" and RS485 pages on wiki.teltonika-networks.com.
- **The 4-pin power socket also carries I/O** (one DI, one OC output) on HW revision 1600 and later. Do not assume the extra pins are spare [DS: web].
- **Input ranges differ per input:** dry input 0–3 V, isolated input 0–30 V, analog 0–24 V (or 4–20 mA), 4-pin DI 0–5 V low / 8–30 V high. Do not wire 24 V to the dry input [DS: web].
- **Outputs:** OC output on the 10-pin socket is 30 V / 250 mA; OC output on the 4-pin socket is 30 V / 300 mA; the relay is SPST 40 V / 4 A [DS: web]. Cytron says the 10-pin OC output "requires external voltage" [PP].
- **RS485 mode:** the port supports both 4-wire full duplex and 2-wire half duplex; match the mode in RutOS to the wiring [DS: web]. Baud range 300–115200 [DS: web].
- **RS232 is a DB9 socket with RTS/CTS**; use a matching DB9 cable [DS: web].
- **Passive PoE on LAN1 is not 802.3af/at/bt.** An 802.3af/at PoE switch will not power it. Use a passive injector in the 9–30 VDC range [DS: web].
- **Wi-Fi is 2.4 GHz only** (802.11b/g/n) [DS: web].
- **eSIM:** Cytron's order code (RUT956200100) is not an eSIM version (eSIM is listed only for the *3**** codes) — inferred from the ordering tab [VEN].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–30 VDC on the 4-pin socket, reverse polarity protected, surge protection >31 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B (spare pairs), 9–30 VDC [DS: web].
- Consumption: < 2 W idle, < 7 W max [DS: web]. Cytron and Teltonika both list a 9 W PSU in the box [PP][VEN]; Cytron's MPN is the UK-plug PSU version [VEN].
- I/O limits: see *Specifications* (30 V / 250 mA OC, 30 V / 300 mA OC, 40 V / 4 A relay) [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI over HTTP/HTTPS, CLI, SSH v1/v2, SMS and call control, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS [DS: web].
- Industrial protocols: Modbus server/client over RTU (RS232, RS485), TCP and USB; Modbus–MQTT gateway; DNP3 station/outstation (RS232, RS485, TCP, USB); BACnet router (IP, RTU over RS485/USB); OPC UA client/server; DLMS/COSEM client (RS232, RS485, TCP) [DS: web].
- Data to server: HTTP(S), MQTT, Azure MQTT. IoT platforms: ThingWorx, Cumulocity, Azure IoT Hub, AWS IoT Core [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc [DS: web].
- Development: SDK with build environment; Busybox shell, Lua, C, C++; Package Manager; GPL customisation; Teltonika Networks Web API (beta) at https://developers.teltonika-networks.com [DS: web].
- Firmware: update from file, FOTA, RMS; keep settings on update; factory reset restores IP address, PIN and user data [DS: web].
- RMS (Remote Management System) 30-day free trial [PP].

## Compatibility and accessories
- Sold separately by Cytron: Teltonika 4G Mobile Magnetic SMA Antenna (RM65), Teltonika DIN Rail Kit (RM49) [PP]. DIN rail, wall or flat-surface mounting all need an extra kit [DS: web].
- Antennas in the box: 2 × LTE (SMA), 2 × Wi-Fi (RP-SMA), 1 × GNSS (SMA) [PP][VEN].
- Bands of Cytron's version: see *Specifications*. Teltonika lists this version for Europe, the Middle East, Africa, Korea and Thailand; Malaysia is not named [VEN].
- USB host accepts storage, a second modem, a printer or a USB-serial adapter [DS: web].

## Common mistakes / troubleshooting
- **No power over PoE from a standard PoE switch:** the RUT956 only takes passive PoE (Mode B, 9–30 VDC), not 802.3af/at [DS: web].
- **I/O pins on the power plug do nothing:** they exist only from HW revision 1600 [DS: web]. Check the label.
- **Wrong input range:** the dry input is 0–3 V, not a 24 V input [DS: web].
- **RS485 no data:** check 2-wire vs 4-wire mode and baud rate (300–115200) in RutOS [DS: web].
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].
- **Datasheet link 404:** the PDF link on the Cytron page is dead; use the Teltonika product page downloads tab [PP][VEN].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Model in packing list | [PP] packing list "1 x Router RUT906" | [PP] title / [VEN] package "RUT956 router" | Typo on the Cytron page. The box holds a RUT956 |
| eSIM | [PP] "eSIM (Optional)" | [VEN] eSIM only on *3**** order codes; Cytron MPN RUT956200100 is a 2***** code | Cytron's unit has no eSIM (inferred from the order code). Ask Cytron to drop or qualify "eSIM (Optional)" |
| 10-pin open collector output isolation | [PP] "Isolated open collector output (requires external voltage)" | [DS: web] "digital open collector output (30 V, 250 mA)" — isolation not stated | [DS: web] wording used. Isolation unconfirmed (see *Needs verification*) |
| Number of inputs on the 10-pin socket | [DS: web] Physical interfaces: "2 x Inputs and 2 x Outputs on 10-pin industrial socket" | [DS: web] Input/Output section and [PP]: 3 inputs (isolated, dry, analog) + 2 outputs | Inside [DS: web]. Use the detailed I/O list (3 in + 2 out); confirm on the Wiki pinout |
| Datasheet link | [PP] links …/717017-rut956-datasheet-2024-v11.pdf | Link returns 404 (2026-10-21); [VEN] downloads tab lists datasheet updated 2026-09-24 | Use the Teltonika product page downloads tab |

## Needs verification
- **All pin numbers**: 4-pin power socket (V+, GND, DI, DO order), 10-pin I/O socket, 6-pin RS485 socket — Wiki not readable on 2026-10-21 (Cloudflare check).
- Whether the 10-pin OC output is galvanically isolated ([PP] says isolated; [DS: web] does not say).
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG).
- LED meaning table (Wiki "RUT956 LEDs" not read).
- Whether Cytron stock is HW revision 1600 or later (needed for the 4-pin DI/DO).
- Band fit for Malaysian operators: the 2***** version region list does not name Malaysia [VEN].
- Datasheet PDF version (the Cytron link name says "2024 v1.1"; Teltonika's current file is dated 2026-09-24) — PDF not opened.

## Sources
- [DS: web] Teltonika RUT956 product page, Features (technical specification): https://teltonika-networks.com/products/routers/rut956 (read 2026-10-21).
- [VEN] Same page, Ordering tab (standard package, versions and order codes) and Downloads tab (flyer updated 2026-06-03, datasheet updated 2026-09-24) (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-rut956-lte-cat-4-industrial-grade-router (read 2026-10-21).
- [PP] Datasheet link on the Cytron page (404 on 2026-10-21): https://teltonika-networks.com/cdn/products/2022/12/63a031f9d449e5-38028829/datasheet/717017-rut956-datasheet-2024-v11.pdf
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/RUT956, https://wiki.teltonika-networks.com/view/RUT956_Power_Socket_Pinout, https://wiki.teltonika-networks.com/view/RUT956_Input/Output, https://wiki.teltonika-networks.com/view/QSG_RUT956
