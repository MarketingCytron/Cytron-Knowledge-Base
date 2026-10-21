# Teltonika RUT906 — Verified Reference

| | |
|---|---|
| Product code | `RUT906` (Teltonika model). Cytron code `RUT-906`, MPN / Teltonika order code `RUT906000400` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full "Features" technical specification, Ordering, Downloads and Certifications tabs) read. The Teltonika Wiki could not be opened (Cloudflare bot check on every Wiki URL), so no [UM] pinout, LED, RS232/RS485 or QSG page was read |
| Primary source | Teltonika Networks RUT906 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/rut906 (read 2026-10-21; the Downloads tab lists "RUT906 DATASHEET (EN)" updated 2026-09-24, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the Ordering, Downloads and Certifications tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page, so exact pin numbers for the power, I/O and RS485 sockets, LED meanings and the default LAN address are not given here; see *Needs verification*.

## What it is
**RUT906 vs RUT901 (same CPU, memory, mobile module, dual SIM, 4 Ethernet, Wi-Fi 4 with 2 RP-SMA, 4-pin 9–30 VDC power with DI/DO, < 7 W):** the RUT906 **adds** GNSS (third antenna connector, SMA), RS232 (DB9), RS485 (6-pin), USB 2.0 host, internal microSD (up to 2 TB) and a 10-pin I/O socket (isolated DI, dry DI, analog input, open collector output, SPST relay). That brings Modbus RTU, DNP3, DLMS and BACnet over serial, and OPC UA (not listed for RUT901). It also ships with magnetic-mount antennas, a GNSS antenna and the RS485 and I/O plugs [DS: web][VEN]. Size and weight are almost identical (109.5 × 50 × 100 mm, 295 g vs 110 × 50 × 100 mm, 297 g) [DS: web]. Choose the RUT901 (`teltonika-rut901.md`) when only cellular + Ethernet + Wi-Fi is needed.
The unit Cytron sells is order code `RUT906000400`: the "RUT906 0*****" hardware version (Europe, Middle East, Africa, Thailand, Australia, New Zealand bands), standard package with Universal PSU, without eSIM [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 4G LTE Cat 4 up to 150 DL / 50 UL Mbps; 3G up to 21 DL / 5.76 UL Mbps; 2G up to 236.8 DL / 236.8 UL kbps | [DS: web] |
| 3GPP release | Release 9 | [DS: web] |
| Bands (RUT906 0***** version, Cytron's MPN) | LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B8; 2G B2, B8 | [VEN: ordering] |
| SIM | 2 × SIM slots (Mini SIM – 2FF), 1.8 V / 3 V, external SIM holders; eSIM "availability varies by order code" (only the 03**** codes are listed with eSIM) | [DS: web][VEN] |
| SIM switch | Auto-switch on weak signal, data limit, SMS limit, roaming, no network, network denied, data connection fail, SIM idle protection | [DS: web] |
| Wi-Fi | 802.11b/g/n (Wi-Fi 4), Access Point (AP), Station (STA); up to 100 simultaneous users; WPA2/WPA3 options; mesh 802.11s, 802.11r/k/v | [DS: web] |
| Ethernet WAN | 1 × WAN port 10/100 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Ethernet LAN | 3 × LAN ports 10/100 Mbps (IEEE 802.3, 802.3u), auto MDI/MDIX | [DS: web] |
| GNSS | GPS. GLONASS, BeiDou, Galileo and QZSS "under development"; NMEA 0183; NTRIP; coordinates via WebUI, SMS, TAVL, RMS; geofencing | [DS: web] |
| RS232 | DB9 connector, RS232 with RTS/CTS flow control, 300–115200 baud | [DS: web] |
| RS485 | 6-pin industrial socket; Full Duplex (4 wires) and Half Duplex (2 wires); 300–230400 baud | [DS: web] |
| Serial functions | Console, Serial over IP, Modem | [DS: web] |
| USB | 1 × USB A host port, USB 2.0; Samba share, USB-to-serial; external HDD, flash drive, additional modem, printer, USB-serial adapter; FAT, FAT32, exFAT, NTFS (read-only), ext2/3/4 | [DS: web] |
| SD card | Micro SD (internal), up to 2 TB; FAT32, NTFS, ext2/3/4; Samba, storage expansion, DLNA | [DS: web] |
| Inputs | 1 × digital dry input (0–3 V); 1 × galvanically isolated digital input (0–30 V); 1 × analog input (0–24 V, with 4–20 mA capability); 1 × non-isolated digital input on the 4-pin power connector (0–5 V = logic low, 8–30 V = logic high) | [DS: web] |
| Outputs | 1 × digital open collector output (30 V, 250 mA); 1 × SPST relay output (40 V, 4 A); 1 × digital open collector output on the 4-pin power connector (30 V, 300 mA) | [DS: web] |
| I/O sockets | 1 × 10-pin industrial socket for inputs/outputs; 1 DI + 1 DO on the 4-pin power connector | [DS: web] |
| I/O events | Email, RMS, SMS; I/O juggler | [DS: web] |
| CPU | Mediatek, 580 MHz, MIPS 24KEc | [DS: web] |
| RAM | 128 MB, DDR2 | [DS: web] |
| Flash | 16 MB, SPI Flash | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Power connector | 4-pin industrial DC power socket | [DS: web] |
| Input voltage | 9–30 VDC, reverse polarity protection; surge protection >31 VDC 10 µs max | [DS: web] |
| Passive PoE | Passive PoE over spare pairs, power through LAN1 port, Mode B, 9–30 VDC; not compatible with IEEE 802.3af, 802.3at or 802.3bt | [DS: web] |
| Power consumption | < 2 W idle, < 7 W max | [DS: web] |
| Antenna connectors | 2 × SMA for LTE, 2 × RP-SMA for Wi-Fi, 1 × SMA for GNSS | [DS: web] |
| Status LEDs | 1 × bi-colour connection status, 5 × mobile connection strength, 4 × ETH status, 1 × power | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| Housing | Aluminium housing, plastic panels | [DS: web] |
| Dimensions (W × H × D) | 109.5 × 50 × 100 mm | [DS: web] |
| Weight | 295 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface (all require additional kit) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
| Approvals (APAC list) | RCM, NBTC, SIRIM, IMDA, SDPPI (POSTEL), ETA-WPC, MTCTE; also CE/RED, UKCA, E-mark, UN ECE R10, CB Scheme, RoHS, REACH and others | [VEN: certifications] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "RUT906 LTE Cat 4 Industrial Grade Router"; brand Teltonika; Code `RUT-906`; MPN `RUT906000400`; warranty 12 months; RM821.00, RM796.37 for 3 or more; cashback RM24.63; availability 2; 1 rating (5 out of 5) [PP].
- "Accessories you may need" (sold separately): Teltonika DIN Rail Kit (RM49.00), Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00) [PP].
- Hardware list matches [DS: web] for CPU, memory, storage, power (4-pin, 9–30 VDC), SIM, antennas, Ethernet, Wi-Fi, I/O summary ("2 x Inputs and 2 x Outputs on 10-pin industrial socket, 1 x Digital input and 1 x Digital output on 4-pin power connector"), serial, USB, LEDs, temperature, housing, size and weight. Differences (3G speed, GNSS constellations, eSIM) are under *Conflicts* [PP].
- Software list: RutOS; auto APN, band lock, SIM switch, operator black/white list, data/SMS limits; routing, failover, firewall, DHCP, DDNS, QoS/SQM, load balancing, VoIP passthrough, SSHFS; WebUI, CLI, SSH, call, SMS, TR-069, SNMP, JSON-RPC, MQTT, BACnet, DNP3, OPC UA, MODBUS, RMS; VPNs; cloud platforms; fast roaming, Relayd; hotspot; GNSS NMEA forwarding, NTRIP, AVL, geofencing [PP].
- **Packing list:** 1 × Router RUT906, 1 × 9 W PSU, 2 × mobile antennas (magnetic mount, SMA male, 3 m cable), 2 × Wi-Fi antennas (magnetic mount, RP-SMA male, 1.5 m cable), 1 × GNSS antenna (adhesive, SMA male, 3 m cable), 1 × RS485 connector block, 1 × I/O connector block, 1 × Ethernet cable (1.5 m), 1 × SIM adapter kit, 1 × Quick Start Guide [PP]. This matches Teltonika's standard package (plus packaging box) [VEN].
- RMS: free 30-day trial for every Teltonika device [PP].
- **Resources:** Quick Start Guide (Wiki `QSG_RUT906`), Configuration examples (Wiki `RUT906_Configuration_Examples`), Manual (Wiki `RUT906_Manual`), Crowd Support Forum, Datasheet and Flyer (Google Drive copies), Teltonika product page link, and a Quick Start Guide video [PP].
- Use cases listed: mobile agricultural machines, remote access to Siemens PLCs, wastewater treatment plant control, Wi-Fi mesh for pallet shuttles, vending machine POS, parcel terminals [PP].

## Interfaces, terminals and pin mapping
**Exact pin numbers were not read.** The Teltonika Wiki pages "RUT906 Power Socket Pinout", "RUT906 Input/Output", "RUT906 RS232/RS485" and "RUT906 LEDs" could not be opened (Cloudflare bot check). What the specification says about each connector [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 4-pin industrial DC power socket | Power input 9–30 VDC, plus 1 × non-isolated digital input (0–5 V low / 8–30 V high) and 1 × open collector output (30 V, 300 mA) | [DS: web] |
| 10-pin industrial socket | Isolated DI (0–30 V), dry DI (0–3 V), analog input (0–24 V or 4–20 mA), open collector output (30 V, 250 mA), SPST relay output (40 V, 4 A) | [DS: web] |
| 6-pin industrial socket | RS485, full duplex (4-wire) or half duplex (2-wire), 300–230400 baud | [DS: web] |
| DB9 socket | RS232 with RTS/CTS flow control, 300–115200 baud | [DS: web] |
| RJ45 × 4 | 1 WAN (configurable as LAN [PP]) + 3 LAN, 10/100 Mbps; LAN1 also accepts passive PoE (Mode B) | [DS: web][PP] |
| USB A | USB 2.0 host | [DS: web] |
| SMA × 2 / RP-SMA × 2 / SMA × 1 | LTE main/aux, Wi-Fi × 2, GNSS | [DS: web] |
| SIM × 2 | Mini SIM (2FF) external holders | [DS: web] |
| microSD | Internal slot | [DS: web] |

Mating plugs for the 10-pin I/O and 6-pin RS485 sockets are in the box ("I/O connector block", "RS485 connector block") [PP][VEN].

## Rules and gotchas (for code, wiring and tutorials)
- **Get pin numbers from the Teltonika Wiki before wiring.** This file does not give them (not read). Use "RUT906 Power Socket Pinout", "RUT906 Input/Output" and "RUT906 RS232/RS485".
- **The 4-pin power socket also carries I/O** (one DI, one OC output). Do not treat the extra pins as spare [DS: web].
- **Input ranges differ per input:** dry input 0–3 V, isolated input 0–30 V, analog 0–24 V (or 4–20 mA), 4-pin DI 0–5 V low / 8–30 V high. Do not wire 24 V to the dry input [DS: web].
- **Outputs:** OC output on the 10-pin socket 30 V / 250 mA; OC output on the 4-pin socket 30 V / 300 mA; relay SPST 40 V / 4 A [DS: web]. An open collector output switches a load that has its own supply (inferred).
- **RS485 mode:** 4-wire full duplex or 2-wire half duplex; set the mode in RutOS to match the wiring. Baud 300–230400 [DS: web].
- **RS232 is a DB9 socket with RTS/CTS**, 300–115200 baud [DS: web].
- **GNSS is GPS today**; other constellations are listed by Teltonika as "under development" [DS: web]. Mount the adhesive GNSS antenna with sky view (inferred).
- **Passive PoE on LAN1 is not 802.3af/at/bt** [DS: web].
- **Wi-Fi is 2.4 GHz only** (802.11b/g/n) [DS: web].
- **eSIM:** Cytron's order code (RUT906000400) is not an eSIM version (eSIM is listed only for the 03**** codes) — inferred from the Ordering tab [VEN].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–30 VDC on the 4-pin socket, reverse polarity protected, surge protection >31 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B (spare pairs), 9–30 VDC [DS: web].
- Consumption: < 2 W idle, < 7 W max [DS: web]. A 9 W PSU is in the box; Cytron's MPN is the Universal PSU version [PP][VEN].
- I/O limits: OC 30 V / 250 mA (10-pin), OC 30 V / 300 mA (4-pin), relay 40 V / 4 A; inputs as above [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI over HTTP/HTTPS, CLI, SSH v1/v2, SMS and call control, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS [DS: web].
- Industrial protocols: Modbus server/client over RTU (RS232, RS485), TCP and USB; Modbus–MQTT gateway; DNP3 station/outstation (RS232, RS485, TCP, USB); BACnet router (IP, RTU over RS485/USB); OPC UA client/server (TCP); DLMS/COSEM client (RS232, RS485, TCP) [DS: web].
- Data to server: HTTP(S), MQTT, Azure MQTT, custom Lua. IoT platforms: ThingWorx, Cumulocity, Azure IoT Hub, AWS IoT Core [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP (incl. L2TPv3), Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc [DS: web].
- Location: GNSS coordinates via WebUI, SMS, TAVL, RMS; NMEA 0183; NTRIP; geofencing [DS: web].
- Development: SDK with build environment; Busybox shell, Lua, C, C++, plus Python and Java via the Package Manager; GPL customisation; Teltonika Networks Web API (beta) [DS: web].
- Firmware: update from file, FOTA, RMS; keep settings on update; factory reset [DS: web].
- RMS 30-day free trial [PP].

## Compatibility and accessories
- Sold separately by Cytron: Teltonika DIN Rail Kit (RM49), Teltonika 4G Mobile Magnetic SMA Antenna (RM65) [PP]. DIN rail, wall or flat-surface mounting all need an extra kit [DS: web].
- In the box: 9 W PSU, 2 × LTE magnetic antennas (SMA, 3 m), 2 × Wi-Fi magnetic antennas (RP-SMA, 1.5 m), GNSS adhesive antenna (SMA, 3 m), RS485 and I/O connector blocks, 1.5 m Ethernet cable, SIM adapter kit [PP][VEN].
- Bands of Cytron's version: see *Specifications*. Teltonika lists the 0***** version for Europe, the Middle East, Africa, Thailand, Australia and New Zealand; Malaysia is not named [VEN]. SIRIM appears in the approvals list [VEN].
- USB host accepts storage, a second modem, a printer or a USB-serial adapter [DS: web].
- Related Cytron-sold Teltonika models: RUT901 (same platform without GNSS, serial, USB, SD and 10-pin I/O), RUT200 (single SIM, 2 Ethernet), RUT140 (no cellular); a RUT956 file also exists in this KB (`teltonika-rut956.md`) [DS: web].

## Common mistakes / troubleshooting
- **No power over PoE from a standard PoE switch:** passive PoE only (Mode B, 9–30 VDC) [DS: web].
- **Wrong input range:** the dry input is 0–3 V, not a 24 V input [DS: web].
- **RS485 no data:** check 2-wire vs 4-wire mode and baud rate (300–230400) in RutOS [DS: web].
- **No GNSS fix or only GPS satellites:** GNSS is GPS (others under development); check the GNSS antenna is on the SMA GNSS port with sky view [DS: web].
- **Backup SIM blocked by the operator:** turn on SIM idle protection [DS: web].
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 3G speed | [PP] "3G – Up to 42 Mbps" | [DS: web] 3G up to 21 DL / 5.76 UL Mbps | [DS: web] wins: 21 Mbps down |
| GNSS constellations | [PP] "GPS, GLONASS, BeiDou, Galileo and QZSS" | [DS: web] "GPS. (GLONASS, BeiDou, Galileo and QZSS - under development)" | [DS: web] wins: GPS only for now |
| eSIM | [PP] "eSIM (Optional)" | [VEN] eSIM only on 03**** order codes; Cytron MPN RUT906000400 is a 0***** code. [DS: web] physical SIM line lists no eSIM | Cytron's unit has no eSIM (inferred from the order code) |
| Number of inputs on the 10-pin socket | [DS: web] Physical interfaces and [PP]: "2 x Inputs and 2 x Outputs on 10-pin industrial socket" | [DS: web] Input/Output section: 3 inputs (dry, isolated, analog) + 2 outputs (OC, relay) besides the 4-pin pair | Inside [DS: web]. Use the detailed I/O list; confirm on the Wiki pinout |
| 4-pin DI low threshold | [DS: web] RUT906: 0–5 V low | [DS: web] RUT901 / RUT200: 0–6 V low | Not a conflict for this model; RUT906 value is 0–5 V low, 8–30 V high |

## Needs verification
- **All pin numbers**: 4-pin power socket (V+, GND, DI, DO order), 10-pin I/O socket, 6-pin RS485 socket, DB9 RS232 pin use — Wiki not readable on 2026-10-21 (Cloudflare check).
- Whether the 10-pin isolated DI / OC output need a common or external supply (wiring drawings in the Wiki not read).
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG or the device label).
- LED meaning table (Wiki "RUT906 LEDs" not read).
- Band fit for Malaysian operators: the 0***** version region list does not name Malaysia or Asia-Pacific [VEN].
- Datasheet PDF version (Teltonika lists 2026-09-24; the Cytron Google Drive copy was not opened).

## Sources
- [DS: web] Teltonika RUT906 product page, Features (technical specification): https://teltonika-networks.com/products/routers/rut906 (read 2026-10-21).
- [VEN] Same page: Ordering tab (standard package, versions and order codes, HS code), Downloads tab (flyer updated 2026-06-03, datasheet updated 2026-09-24), Certifications tab (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-rut906-lte-cat-4-industrial-grade-router (read 2026-10-21).
- [PP] Datasheet and flyer links on the Cytron page (Google Drive, not opened): (Cytron document — link not public) (Cytron document — link not public)
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/RUT906_Manual, https://wiki.teltonika-networks.com/view/RUT906_Input/Output, https://wiki.teltonika-networks.com/view/QSG_RUT906, https://wiki.teltonika-networks.com/view/RUT906_Configuration_Examples
