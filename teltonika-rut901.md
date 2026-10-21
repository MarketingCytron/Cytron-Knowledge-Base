# Teltonika RUT901 — Verified Reference

| | |
|---|---|
| Product code | `RUT901` (Teltonika model). Cytron code `RUT-901`, MPN shown as `RUT90100040021` (not a Teltonika order code; see *Conflicts*) [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full "Features" technical specification, Ordering, Downloads and Certifications tabs) read. The Teltonika Wiki could not be opened (Cloudflare bot check on every Wiki URL), so no [UM] pinout, LED or QSG page was read |
| Primary source | Teltonika Networks RUT901 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/rut901 (read 2026-10-21; the Downloads tab lists "RUT901 DATASHEET (EN)" updated 2026-09-24, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the Ordering, Downloads and Certifications tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page, so exact pin numbers, LED meanings and the default LAN address are not given here; see *Needs verification*.

## What it is
**RUT901 vs RUT906 (same housing size, same CPU, same mobile module, same dual SIM, 4 Ethernet and Wi-Fi):** the RUT901 has **no GNSS, no RS232, no RS485, no USB, no microSD and no 10-pin I/O socket**. Its only I/O is the DI/DO pair on the 4-pin power socket, and its industrial protocols run over TCP only (no Modbus RTU). Teltonika's RUT901 specification also does not list OPC UA, which the RUT906 has. The RUT901 ships with swivel antennas; the RUT906 ships with magnetic-mount antennas, a GNSS antenna and RS485/I/O plugs [DS: web][VEN]. Choose the RUT906 (`teltonika-rut906.md`) when serial devices, GNSS or wider I/O are needed.
Cytron's MPN `RUT90100040021` does not match a Teltonika order code; the nearest listed code is `RUT901000400` ("RUT901 0*****" version, Europe / Asia-Pacific / Australia bands, standard package with Universal PSU) (inferred) [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 4G LTE Cat 4 up to 150 DL / 50 UL Mbps; 3G up to 21 DL / 5.76 UL Mbps; 2G up to 236.8 DL / 236.8 UL kbps | [DS: web] |
| 3GPP release | Release 9 | [DS: web] |
| Bands (RUT901 0***** version, nearest match to Cytron's MPN) | LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B5, B8; 2G B3, B8 | [VEN: ordering] |
| SIM | 2 × SIM slots (Mini SIM – 2FF), 1.8 V / 3 V, external SIM holders; eSIM optional — "different hardware required" (only the 02**** codes are listed with eSIM) | [DS: web][VEN] |
| SIM switch | Auto-switch on weak signal, data limit, SMS limit, roaming, no network, network denied, data connection fail, SIM idle protection | [DS: web] |
| Wi-Fi | 802.11b/g/n (Wi-Fi 4), Access Point (AP), Station (STA); up to 100 simultaneous users; WPA2/WPA3 options; mesh 802.11s, 802.11r/k/v | [DS: web] |
| Ethernet WAN | 1 × WAN port 10/100 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Ethernet LAN | 3 × LAN ports 10/100 Mbps (IEEE 802.3, 802.3u), auto MDI/MDIX | [DS: web] |
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
| Power consumption | < 2 W idle, < 7 W max | [DS: web] |
| Antenna connectors | 2 × SMA for LTE, 2 × RP-SMA for Wi-Fi | [DS: web] |
| Status LEDs | 1 × bi-colour connection status, 5 × mobile connection strength, 4 × ETH status, 1 × power | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| Housing | Aluminium housing, plastic panels | [DS: web] |
| Dimensions (W × H × D) | 110 × 50 × 100 mm | [DS: web] |
| Weight | 297 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface (all require additional kit) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
| Approvals (APAC list) | RCM, NCC, NBTC, SIRIM, IMDA, SDPPI (POSTEL), ETA-WPC, MTCTE; also CE/RED, UKCA, E-mark, UN ECE R10, CB Scheme, RoHS, REACH and others | [VEN: certifications] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "RUT901 LTE Cat 4 Industrial Grade Router"; brand Teltonika; Code `RUT-901`; MPN `RUT90100040021`; RM749.00, RM726.53 for 3 or more; cashback RM22.47; availability 2; no ratings. **No warranty field** is shown in the header and the description has no "Warranty Period" line (the other three Teltonika pages show 12 months) [PP].
- "Accessories you may need" (sold separately): Teltonika DIN Rail Kit (RM49.00), Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00) [PP].
- Hardware list matches [DS: web] for mobile speeds (3G 21 Mbps), CPU, memory, storage, power (4-pin, 9–30 VDC), SIM (2 × 2FF, eSIM optional), antennas (2 × SMA female LTE, 2 × RP-SMA female Wi-Fi), Ethernet (4 × RJ45), Wi-Fi, I/O (1 DI + 1 DO on the 4-pin connector), LEDs, housing, size and weight. The temperature line has a typo (see *Conflicts*) [PP].
- Software list: RutOS; SIM switch, SMS, black/white list, band management, APN, bridge, passthrough; firewall, DHCP, QoS/SQM, DDNS, backup, load balancing, SSHFS; static and dynamic routing (BGP, OSPF v2, RIP, NHRP); OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard; WebUI, FOTA, SSH, SMS, call, TR-069, MQTT, SNMP, JSON-RPC, MODBUS, RMS; RMS, Cloud of Things, ThingWorx, Cumulocity, Azure IoT Hub; hotspot; SMS features [PP].
- **Packing list:** 1 × Router RUT901, 1 × 9 W PSU, 2 × mobile antennas (swivel, SMA male), 2 × Wi-Fi antennas (swivel, RP-SMA male), 1 × Ethernet cable (1.5 m), 1 × SIM adapter kit, 1 × QSG [PP]. This matches Teltonika's standard package (plus packaging box) [VEN].
- RMS: free 30-day trial for every Teltonika device [PP].
- **Resources:** Quick Start Guide (Wiki `QSG_RUT901`), Configuration examples (Wiki `RUT901_Configuration_Examples`), Manual (Wiki `RUT901_Manual`), Crowd Support Forum, RUT901 Datasheet and Flyer (Google Drive copies), and a link to the Teltonika product page [PP].
- Use cases listed: boring and milling equipment, armoured-truck image control, 4G for retail, Wi-Fi mesh for pallet shuttles, vending machine POS, parcel terminals [PP].

## Interfaces, terminals and pin mapping
**Exact pin numbers were not read.** The Teltonika Wiki pages "RUT901 Power Socket Pinout", "RUT901 Input/Output" and "RUT901 LEDs" could not be opened (Cloudflare bot check). What the specification says about each connector [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 4-pin industrial DC power socket | Power input 9–30 VDC, plus 1 × digital input (0–6 V low / 8–30 V high) and 1 × open collector output (30 V, 300 mA) | [DS: web] |
| RJ45 × 4 | 1 WAN + 3 LAN, 10/100 Mbps; LAN1 also accepts passive PoE (Mode B, 9–30 VDC) | [DS: web] |
| SMA × 2 | LTE antennas (main and auxiliary) | [DS: web] |
| RP-SMA × 2 | Wi-Fi antennas | [DS: web] |
| SIM × 2 | Mini SIM (2FF) external holders | [DS: web] |
| Reset button | Reboot / user default / factory reset | [DS: web] |

## Rules and gotchas (for code, wiring and tutorials)
- **Get pin numbers from the Teltonika Wiki before wiring the 4-pin plug.** This file does not give them (not read).
- **The 4-pin power socket also carries I/O** (one DI, one open collector DO). Do not treat the extra pins as spare [DS: web].
- **DI thresholds:** 0–6 V low, 8–30 V high [DS: web]. **DO:** open collector, 30 V / 300 mA max [DS: web].
- **No serial port.** Modbus, DNP3, DLMS and BACnet run over TCP/IP only. For RS232/RS485 field devices use the RUT906 [DS: web].
- **No GNSS** and no USB or microSD [DS: web].
- **Passive PoE on LAN1 is not 802.3af/at/bt** [DS: web].
- **Wi-Fi is 2.4 GHz only** (802.11b/g/n) [DS: web].
- **SIM idle protection:** the router can periodically use the unused SIM so the operator does not block it; enable it if the backup SIM is prepaid [DS: web].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–30 VDC on the 4-pin socket, reverse polarity protected, surge protection >31 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B (spare pairs), 9–30 VDC [DS: web].
- Consumption: < 2 W idle, < 7 W max [DS: web]. A 9 W PSU is in the box [PP][VEN].
- I/O limits: DI 0–6 V low / 8–30 V high; DO open collector 30 V, 300 mA [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI over HTTP/HTTPS, CLI, SSH v1/v2, SMS and call control, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS [DS: web].
- Industrial protocols: Modbus TCP server/client; Modbus–MQTT gateway; DNP3 station/outstation (TCP); BACnet router (IP); DLMS/COSEM client (TCP). OPC UA is not listed for RUT901 [DS: web].
- Data to server: HTTP(S), MQTT, Azure MQTT, custom Lua. IoT platforms: ThingWorx, Cumulocity, Azure IoT Hub, AWS IoT Core [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP (incl. L2TPv3), Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc [DS: web].
- Network extras: port mirroring; SSHFS "not available in standard FW" [DS: web].
- Development: SDK with build environment; Busybox shell, Lua, C, C++; Package Manager; GPL customisation; Teltonika Networks Web API (beta) [DS: web].
- Firmware: update from file, FOTA, RMS; keep settings on update; factory reset [DS: web].
- RMS 30-day free trial [PP].

## Compatibility and accessories
- Sold separately by Cytron: Teltonika DIN Rail Kit (RM49), Teltonika 4G Mobile Magnetic SMA Antenna (RM65) [PP]. DIN rail, wall or flat-surface mounting all need an extra kit [DS: web].
- In the box: 9 W PSU, 2 × LTE swivel antennas (SMA), 2 × Wi-Fi swivel antennas (RP-SMA), 1.5 m Ethernet cable, SIM adapter kit [PP][VEN].
- Bands: see *Specifications* (0***** version, Europe / Asia-Pacific / Australia; Malaysia not named individually) [VEN]. SIRIM appears in the approvals list [VEN].
- Related Cytron-sold Teltonika models: RUT906 (same platform plus GNSS, RS232, RS485, USB, microSD, 10-pin I/O), RUT200 (single SIM, 2 Ethernet), RUT140 (no cellular) [DS: web].

## Common mistakes / troubleshooting
- **No power over PoE from a standard PoE switch:** passive PoE only (Mode B, 9–30 VDC) [DS: web].
- **Backup SIM blocked by the operator:** turn on SIM idle protection [DS: web].
- **Input never reads high:** the DI needs 8–30 V for logic high [DS: web].
- **Cannot connect a serial meter/PLC:** RUT901 has no RS232/RS485; use RUT906 or a Modbus TCP gateway [DS: web].
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Order code | [PP] MPN `RUT90100040021` | [VEN] ordering tab: no such code; nearest is `RUT901000400` (Universal PSU) | Unresolved. Likely a Cytron entry error (inferred); confirm the label on stock |
| Operating temperature | [PP] "-40 °C to -75 °C" | [DS: web] -40 °C to 75 °C | [DS: web] wins. Typo on the Cytron page |
| Warranty | [PP] not shown on this page | [PP] the RUT200, RUT140 and RUT906 pages show 12 months | Unresolved. Ask Cytron to add the warranty field |
| Software label swap | [PP] "Network Protocols" lists features (VoIP, firewall, DHCP…) and "Network Features" lists protocols (TCP, UDP…) | [DS: web] keeps them separate correctly | Cosmetic; [DS: web] wording used |

## Needs verification
- **All pin numbers** of the 4-pin power socket (V+, GND, DI, DO order) — Wiki not readable on 2026-10-21 (Cloudflare check).
- The real order code of Cytron's stock (label) and whether it has the Universal PSU.
- Warranty period for this listing (not on the page).
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG or the device label).
- LED meaning table (Wiki "RUT901 LEDs" not read).
- Band fit for Malaysian operators (operator fit inferred from the band list, not stated) [VEN].
- Datasheet PDF version (Teltonika lists 2026-09-24; the Cytron Google Drive copy was not opened).

## Sources
- [DS: web] Teltonika RUT901 product page, Features (technical specification): https://teltonika-networks.com/products/routers/rut901 (read 2026-10-21).
- [VEN] Same page: Ordering tab (standard package, versions and order codes, HS code), Downloads tab (flyer updated 2026-06-03, datasheet updated 2026-09-24), Certifications tab (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-rut901-lte-cat-4-industrial-grade-router (read 2026-10-21).
- [PP] Datasheet and flyer links on the Cytron page (Google Drive, not opened): (Cytron document — link not public) (Cytron document — link not public)
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/RUT901_Manual, https://wiki.teltonika-networks.com/view/QSG_RUT901, https://wiki.teltonika-networks.com/view/RUT901_Configuration_Examples
