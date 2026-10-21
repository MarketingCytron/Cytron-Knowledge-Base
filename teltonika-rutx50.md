# Teltonika RUTX50 — Verified Reference

| | |
|---|---|
| Product code | `RUTX50` (Teltonika model). Cytron code `RUT-X50`, MPN / Teltonika order code `RUTX50000100` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full technical specification, ordering/versions tab, downloads tab) read. The Teltonika Wiki could not be opened (Cloudflare bot check), so the power socket pinout [UM] was not read |
| Primary source | Teltonika Networks RUTX50 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/rutx50 (read 2026-10-21; the downloads tab lists "RUTX50 DATASHEET (EN)" updated 2026-09-25, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the ordering and downloads tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page.

## What it is
The unit Cytron sells is order code `RUTX50000100`: the "RUTX50 0*****" hardware version (Europe, Middle East, Africa, Oceania, Brazil), standard package with UK PSU [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 5G Sub-6 GHz SA/NSA 2.1/3.3 Gbps DL (4×4 MIMO), 900/600 Mbps UL (2×2); 4G LTE Cat 20 up to 2.0 Gbps DL / 200 Mbps UL; 3G up to 42 DL / 5.76 UL Mbps | [DS: web] |
| 3GPP release | Release 15/16 depending on the hardware version | [DS: web] |
| Bands (RUTX50 0***** version, Cytron's MPN) | 5G NR NSA and SA: n1, n3, n5, n7, n8, n20, n28, n38, n40, n41, n77, n78; LTE-FDD B1, B3, B5, B7, B8, B20, B28, B32; LTE-TDD B38, B40, B41, B42, B43; 3G B1, B5, B8 | [VEN: ordering] |
| SIM | 2 × SIM slots (Mini SIM – 2FF), 1.8 V / 3 V; eSIM only on order codes that include it (the 32**** versions) | [DS: web][VEN] |
| SIM switch | Dual SIM; auto-switch on weak signal, data limit, SMS limit, roaming, no network, network denied, data connection fail, SIM idle protection | [DS: web] |
| Wi-Fi | 802.11b/g/n/ac Wave 2 (Wi-Fi 5), up to 867 Mbps, dual band, MU-MIMO; 802.11r fast transition; AP and STA; up to 150 simultaneous users | [DS: web] |
| Ethernet WAN | 1 × WAN 10/100/1000 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Ethernet LAN | 4 × LAN 10/100/1000 Mbps, auto MDI/MDIX | [DS: web] |
| GNSS | GPS, GLONASS, BeiDou, Galileo and QZSS; NMEA 0183; NTRIP; geofencing | [DS: web] |
| USB | 1 × USB A host port, USB 2.0 | [DS: web] |
| Input | 1 × digital input on the 4-pin power socket: 0–6 V = logic low, 8–30 V = logic high | [DS: web] |
| Output | 1 × digital output, open collector, max 30 V, 300 mA, on the 4-pin power socket | [DS: web] |
| Security hardware | TPM 2.0 identification and authentication module | [DS: web] |
| CPU | Quad-core ARM Cortex A7, 717 MHz | [DS: web] |
| RAM | 256 MB | [DS: web] |
| Flash | 256 MB | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Power connector | 4-pin industrial DC power socket | [DS: web] |
| Input voltage | 9–50 VDC, reverse polarity protection; surge protection >51 VDC 10 µs max | [DS: web] |
| Passive PoE | Power through the LAN1 port, Mode B, 9–50 VDC; not compatible with IEEE 802.3af, 802.3at or 802.3bt | [DS: web] |
| Power consumption | Idle < 4 W, max < 16.5 W | [DS: web] |
| Antenna connectors | 4 × SMA for mobile, 2 × RP-SMA for Wi-Fi, 1 × SMA for GNSS | [DS: web] |
| Status LEDs | 4 × WAN type, 3 × mobile connection type, 3 × mobile connection strength, 10 × Ethernet port status, 1 × power, 2 × 2.4G and 5G Wi-Fi | [DS: web] |
| Other | 1 × grounding screw; reboot / user default / factory reset button | [DS: web] |
| Housing | Anodised aluminium housing and panels | [DS: web] |
| Dimensions (W × H × D) | 132 × 44.2 × 95.1 mm | [DS: web] |
| Weight | 533 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface (all require additional kit) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "RUTX50 5G Industrial Grade Router"; brand Teltonika; Code `RUT-X50`; MPN `RUTX50000100`; warranty 12 months; RM2,688.00, RM2,607.36 for 3 or more; cashback RM80.64; availability 3; no reviews [PP].
- "Accessories you may need" (sold separately): Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00), Teltonika DIN Rail Kit (RM49.00) [PP].
- Hardware list: 5G Sub-6 GHz up to 3 Gbps; LTE Cat 20 up to 2 Gbps; 3G up to 43 Mbps; quad-core ARM Cortex A7 717 MHz; storage 256 MB (80 MB for userspace); memory 256 MB (100 MB for userspace); 4-pin power socket 9–50 VDC with surge protection; 2 × Mini SIM; 4 × SMA mobile, 2 × RP-SMA Wi-Fi, 1 × SMA GNSS; 5 × RJ45 10/100/1000; Wi-Fi 5 with 802.11r; 1 DI + 1 OC output on the 4-pin socket; LEDs; -40 °C to 75 °C; "Aluminium housing with DIN rail mounting option on both sides"; 132 × 44.2 × 95.1 mm; 533 g [PP].
- Software list: RutOS, mobile features, network protocols, security, VPN (OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc), WebUI/CLI/SSH/SMS/TR-069/SNMP/JSON-RPC/MQTT/MODBUS/RMS, cloud (RMS, FOTA, Azure IoT Hub, Cloud of Things, Cumulocity, ThingWorx), GNSS/NMEA/NTRIP/TAVL/geofencing [PP].
- **Packing list:** RUTX50 router, 18W power supply, 4 × mobile antennas (swivel, SMA male), 2 × Wi-Fi antennas (magnetic, RP-SMA male, 1.5 m), 1 × GNSS antenna (adhesive, SMA male, 3 m), Ethernet cable (1.5 m), SIM adapter kit, Quick Start Guide [PP]. This matches Teltonika's standard package [VEN].
- RMS: free 30-day RMS trial [PP]. Page embeds a third-party review video (ExploreVan UK) [PP].
- **Resources:** Quick Start Guide (Wiki QSG_RUTX50), Configuration examples, Manual (Wiki RUTX50_Manual), Crowd Support Forum, Datasheet (…/625048-rutx50-datasheet-v14.pdf, not opened), Flyer (…/560033-rutx50-flyer-2023-v10.pdf), Teltonika product page [PP].
- Use cases listed: RV internet and camping Wi-Fi, warehouse automation, predictive maintenance, Wi-Fi mesh for pallet shuttles, vending machine POS management, parcel terminal management [PP].

## Interfaces, terminals and pin mapping
**Exact pin numbers were not read.** The Wiki page "RUTX50 Power Socket Pinout" could not be opened (Cloudflare bot check). What the specification says [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 4-pin industrial DC power socket | Power input 9–50 VDC, plus 1 × digital input (0–6 V low / 8–30 V high) and 1 × open collector output (30 V, 300 mA) | [DS: web] |
| RJ45 × 5 | 1 WAN + 4 LAN, 10/100/1000 Mbps; LAN1 also accepts passive PoE (Mode B, 9–50 VDC) | [DS: web] |
| USB A | USB 2.0 host (storage, extra modem, printer, USB-serial adapter) | [DS: web] |
| SMA × 4 / RP-SMA × 2 / SMA × 1 | Mobile (5G 4×4), Wi-Fi × 2, GNSS | [DS: web] |
| SIM × 2 | Mini SIM (2FF) | [DS: web] |
| Grounding screw | Chassis earth | [DS: web] |

## Rules and gotchas (for code, wiring and tutorials)
- **Get the 4-pin pin order from the Teltonika Wiki before wiring** (not read here).
- **The power socket also carries one DI and one OC output.** Do not assume the extra two pins are spare [DS: web].
- **No serial ports.** RS232/RS485 Modbus, DNP3, BACnet RTU and DLMS need a USB-serial adapter on the USB port; the spec lists their connection types as TCP and USB only [DS: web].
- **All four mobile antennas should be fitted** for 4×4 MIMO 5G — inferred from "4 × SMA for mobile" and "4×4 MIMO" [DS: web]. The box has 4 swivel antennas [PP].
- **Passive PoE on LAN1 is not 802.3af/at/bt** [DS: web].
- **5G speed figures are peak values** (2.1/3.3 Gbps DL depending on SA/NSA and network) [DS: web].
- **eSIM:** Cytron's order code (RUTX50000100) is not an eSIM version (eSIM is listed for 32**** codes) — inferred from the ordering tab [VEN].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–50 VDC on the 4-pin socket, reverse polarity protected, surge protection >51 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B, 9–50 VDC [DS: web].
- Consumption: idle < 4 W, max < 16.5 W. An 18 W PSU is in the box [DS: web][PP]. Cytron's MPN is the UK-plug PSU version [VEN].
- DI: 0–6 V low, 8–30 V high. DO: open collector, max 30 V, 300 mA [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI HTTP/HTTPS, CLI, SSH, SMS and call control, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS, FOTA [DS: web].
- Industrial protocols: Modbus server/client over TCP and USB, Modbus–MQTT gateway, DNP3 (TCP, USB), BACnet router (IP, RTU over USB), OPC UA client/server, DLMS/COSEM client (TCP, USB) [DS: web].
- Data to server (HTTP(S), MQTT, Azure MQTT) with custom Lua scripting; IoT platforms ThingWorx, Cumulocity, Azure IoT Hub, AWS IoT Core [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc, Tailscale [DS: web].
- Site Manager: central management of Teltonika TAP access points and managed switches [DS: web].
- Development: SDK; Busybox shell, Lua, C, C++, and Python and Java through the Package Manager; Web API (beta) at https://developers.teltonika-networks.com [DS: web].

## Compatibility and accessories
- Sold separately by Cytron: Teltonika 4G Mobile Magnetic SMA Antenna (RM65), Teltonika DIN Rail Kit (RM49) [PP]. DIN rail, wall or flat mounting needs an extra kit [DS: web].
- In the box: 4 × 5G swivel antennas, 2 × Wi-Fi, 1 × GNSS, 18 W PSU, Ethernet cable, SIM adapter kit [PP][VEN].
- Region of Cytron's version per Teltonika: Europe, Middle East, Africa, Oceania, Brazil; Malaysia is not named [VEN].

## Common mistakes / troubleshooting
- **No Modbus RTU port:** the RUTX50 has no RS232/RS485. Use a USB-serial adapter, or pick the RUT956 [DS: web].
- **No power from a standard PoE switch:** LAN1 takes passive PoE only [DS: web].
- **Low 5G speed:** check that all 4 mobile antennas are fitted and the band is supported (see *Specifications*) — inferred.
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Mounting | [PP] "Aluminium housing with DIN rail mounting option on both sides" | [DS: web] "DIN rail, wall mount, flat surface (all require additional kit)" | [DS: web] wins: DIN mounting needs the DIN Rail Kit (Cytron sells it separately, RM49) |
| 5G peak downlink | [PP] "up to 3Gbps" | [DS: web] 2.1/3.3 Gbps DL (4×4 MIMO) | [DS: web] figures used |
| 3G downlink | [PP] up to 43 Mbps | [DS: web] up to 42 Mbps | [DS: web] wins: 42 Mbps |
| eSIM | [PP] does not mention eSIM | [VEN] eSIM only on 32**** codes; Cytron's MPN is a 0***** code | No conflict: Cytron's unit has no eSIM (inferred) |
| Userspace memory | [PP] 80 MB flash / 100 MB RAM for userspace | [DS: web] 256 MB / 256 MB, no userspace figure | Not a conflict; userspace figures are [PP] only |

## Needs verification
- **4-pin power socket pin order** (V+, GND, DI, DO) — Wiki not readable on 2026-10-21.
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG).
- LED meaning table (Wiki "RUTX50 LEDs" not read).
- Band fit for Malaysian 5G/LTE operators: the 0***** region list does not name Malaysia [VEN].
- Datasheet PDF v1.4 linked by Cytron vs Teltonika's current file (updated 2026-09-25) — PDF not opened.

## Sources
- [DS: web] Teltonika RUTX50 product page, Features (technical specification): https://teltonika-networks.com/products/routers/rutx50 (read 2026-10-21).
- [VEN] Same page, Ordering tab (standard package, versions, order codes) and Downloads tab (flyer updated 2026-10-01, datasheet updated 2026-09-25) (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-rutx50-5g-industrial-grade-router (read 2026-10-21).
- [PP] Datasheet link on the Cytron page (not opened): https://teltonika-networks.com/cdn/products/2023/01/63b7f88131a497-19366814/datasheets/625048-rutx50-datasheet-v14.pdf
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/RUTX50_Manual, https://wiki.teltonika-networks.com/view/QSG_RUTX50, https://wiki.teltonika-networks.com/view/RUTX50_Configuration_Examples
