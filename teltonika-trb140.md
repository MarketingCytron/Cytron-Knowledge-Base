# Teltonika TRB140 — Verified Reference

| | |
|---|---|
| Product code | `TRB140` (Teltonika model). Cytron code `TRB-140`, MPN / Teltonika order code `TRB140005000` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full technical specification, ordering/versions tab, downloads tab) read. The Teltonika Wiki could not be opened (Cloudflare bot check), so the power socket / I/O pinout [UM] was not read |
| Primary source | Teltonika Networks TRB140 product page, "Features" technical specification, https://teltonika-networks.com/products/gateways/trb140 (read 2026-10-21; the downloads tab lists "TRB140 DATASHEET (EN)" updated 2026-09-30, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the ordering and downloads tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page.

## What it is
The unit Cytron sells is order code `TRB140005000`: the "TRB140 0*****" hardware version, whose region list includes **Malaysia**, standard package with UK PSU [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 4G LTE Cat 4 up to 150 DL / 50 UL Mbps; 3G up to 21 DL / 5.76 UL Mbps; 2G up to 236.8 DL / 236.8 UL kbps | [DS: web] |
| 3GPP release | Release 11 | [DS: web] |
| Bands (TRB140 0***** version, Cytron's MPN) | LTE-FDD B1, B3, B7, B8, B20, B28A; LTE-TDD B38, B40, B41; 3G B1, B8; 2G B3, B8. Region: Europe, Middle East, Africa, Korea, Thailand, India, Malaysia, Singapore | [VEN: ordering] |
| SIM | 1 × SIM slot (Mini SIM – 2FF), 1.8 V / 3 V | [DS: web] |
| Ethernet | 1 × RJ45, 10/100/1000 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| USB | 1 × virtual network interface via micro USB | [DS: web] |
| Input | 1 × digital input: 0–6 V = logic low, 8–30 V = logic high | [DS: web] |
| Output | 1 × digital output, open collector, max 30 V, 300 mA | [DS: web] |
| I/O location | 1 × DI and 1 × DO on the 4-pin power connector | [DS: web] |
| CPU | ARM Cortex-A7, 1.3 GHz | [DS: web] |
| RAM | 128 MB, DDR2 | [DS: web] |
| Flash | 512 MB, SPI Flash | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Routing | Static routing | [DS: web] |
| Power connector | 4-pin industrial DC power socket | [DS: web] |
| Input voltage | 9–30 VDC, reverse polarity protection; surge protection >31 VDC 10 µs max | [DS: web] |
| Passive PoE | Power through the LAN1 port, Mode B, 9–30 VDC; not compatible with IEEE 802.3af, 802.3at or 802.3bt | [DS: web] |
| Power consumption | < 5 W | [DS: web] |
| Antenna connector | 1 × SMA for LTE | [DS: web] |
| Status LEDs | 3 × connection type, 5 × connection strength, 2 × LAN status, 1 × power | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| Housing | Aluminium housing | [DS: web] |
| Dimensions (W × H × D) | 74.5 × 25 × 64.4 mm | [DS: web] |
| Weight | 136 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface (all require additional kit) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "TRB140 LTE Cat 4 Ethernet Gateway"; brand Teltonika; Code `TRB-140`; MPN `TRB140005000`; warranty 12 months; RM658.00, RM638.26 for 5 or more; cashback RM19.74; availability 19; 2 ratings (5 out of 5). No "Accessories you may need" block [PP].
- Description: ultra-small, lightweight, energy-efficient industrial gateway with LTE Cat 4, Gigabit Ethernet, digital I/O and micro-USB; SMS control, firewall, OpenVPN, IPsec, RMS and FOTA [PP].
- Hardware list: LTE Cat 4 up to 150 Mbps; **3G up to 42 Mbps**; **CPU "Qualcomm, ARM Cortex A7, 1.2 GHz"**; 512 MB flash (200 MB for userspace); 128 MB RAM (50 MB for userspace); 4-pin power socket 9–30 VDC; 1 × external SIM holder (2FF); 1 × SMA; 1 × 10/100/1000 Ethernet; **"2 x Digital input / Digital open collector output (configurable)" on the 4-pin socket**; 1 × Micro USB Slave; LEDs (3 connection type, 5 signal strength, 2 Ethernet, 1 power); -40 °C to 75 °C; "Aluminium housing with DIN rail mounting option"; 74.5 × 25 × 64.4 mm; **134 g** [PP].
- Software list: RutOS; Auto APN, band lock, operator list, data/SMS limits; protocols; firewall; security; VPN (OpenVPN, IPsec, GRE, PPTP, SSTP, Stunnel, DMVPN, L2TP, ZeroTier, WireGuard); WebUI/CLI/SSH/call/SMS/TR-069/SNMP/JSON-RPC/MQTT/MODBUS/RMS; cloud (RMS, FOTA, Azure IoT Hub, Cloud of Things, Cumulocity, ThingWorx); SMS features incl. send/read SMS via HTTP POST/GET, email-to-SMS, SMPP [PP].
- **Packing list:** TRB140, 9W power supply, 1 × mobile antenna (magnetic, SMA male, 3 m), micro-USB cable (0.8 m), hex key, LAN cable, Quick Start Guide [PP]. This matches Teltonika's standard package [VEN].
- RMS: free 30-day RMS trial [PP].
- **Resources:** Quick Start Guide (Wiki QSG_TRB140), Configuration examples, Manual (Wiki TRB140_Manual), Crowd Support Forum, Datasheet (…/trb140-datasheet-2023-v11.pdf, not opened), Flyer, Teltonika product page [PP].
- Use cases listed: water quality monitoring, solar power plant monitoring, digital signage, water purification data, vending machine POS, parcel terminals [PP].

## Interfaces, terminals and pin mapping
**Exact pin numbers were not read.** The Wiki pages "TRB140 Power Socket Pinout" and "TRB140 Input/Output" could not be opened (Cloudflare bot check). What the specification says [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 4-pin industrial DC power socket | Power input 9–30 VDC, plus 1 × digital input (0–6 V low / 8–30 V high) and 1 × open collector output (30 V, 300 mA) | [DS: web] |
| RJ45 × 1 | 10/100/1000 Mbps Ethernet; also accepts passive PoE (Mode B, 9–30 VDC) | [DS: web] |
| Micro USB | Virtual network interface to a PC (USB device, not host) | [DS: web][PP] |
| SMA × 1 | LTE antenna | [DS: web] |
| SIM × 1 | Mini SIM (2FF) | [DS: web] |

The hex key in the box is for the housing (the SIM tray sits behind a cover) — inferred from the packing list; not verified.

## Rules and gotchas (for code, wiring and tutorials)
- **Get the 4-pin pin order from the Teltonika Wiki before wiring** (not read here). The same plug carries power, the DI and the DO.
- **Use the Teltonika I/O count: 1 DI + 1 DO.** The Cytron page says "2 x Digital input / Digital open collector output (configurable)"; the Teltonika specification for the current version says one fixed DI and one fixed DO (see *Conflicts*) [DS: web].
- **DI levels:** 0–6 V reads low, 8–30 V reads high. Leave 6–8 V undefined [DS: web].
- **DO is open collector, max 30 V, 300 mA.** It sinks current to ground; the load needs its own supply (standard OC behaviour, inferred) [DS: web].
- **Only one Ethernet port.** The TRB140 is a gateway for one device or one switch, not a multi-port router [DS: web]. Routing is static only [DS: web].
- **Micro USB is a USB device port** (virtual network interface to a PC for setup), not a host port — no USB storage or serial adapters [DS: web][PP].
- **Passive PoE only** on the Ethernet port, 9–30 VDC Mode B; not 802.3af/at [DS: web].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–30 VDC on the 4-pin socket, reverse polarity protected, surge protection >31 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B, 9–30 VDC [DS: web].
- Consumption: < 5 W. A 9 W PSU is in the box [DS: web][PP]. Cytron's MPN is the UK-plug PSU version [VEN].
- DI: 0–6 V low, 8–30 V high. DO: open collector, max 30 V, 300 mA [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI HTTP/HTTPS, CLI, SSH, SMS and call control (including output on/off by call), TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS, FOTA [DS: web].
- I/O: events by email, RMS, SMS; I/O juggler to trigger actions from I/O conditions [DS: web].
- Industrial protocols over TCP: Modbus server/client, Modbus–MQTT gateway, DNP3, BACnet/IP router, OPC UA, DLMS/COSEM client [DS: web].
- Data to server (HTTP(S), MQTT, Azure MQTT) with Lua scripting; ThingWorx, Cumulocity, Azure IoT Hub, AWS IoT Core [DS: web].
- Development: SDK; Busybox shell, Lua, C, C++, and Python through the Package Manager; Web API (beta) at https://developers.teltonika-networks.com [DS: web].

## Compatibility and accessories
- In the box: 9 W PSU, magnetic LTE antenna (SMA), micro-USB cable, hex key, LAN cable [PP][VEN].
- DIN rail, wall or flat mounting needs an extra kit [DS: web]. Cytron lists a Teltonika DIN Rail Kit on other Teltonika pages (not on this page); fit to the TRB140 not checked [PP].
- Band fit: Teltonika names Malaysia in the region list for the 0***** version Cytron sells [VEN].
- Teltonika also lists a separate "TRB140*2****" datasheet and flyer (dated 2020-12-03) for another hardware variant; not read [VEN].

## Common mistakes / troubleshooting
- **Expecting two configurable I/O:** the current Teltonika spec gives 1 DI + 1 DO [DS: web].
- **No power from a standard PoE switch:** the Ethernet port takes passive PoE only [DS: web].
- **Treating micro-USB as a USB host:** it is a virtual network interface for a PC [DS: web].
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| I/O on the 4-pin socket | [PP] "2 x Digital input / Digital open collector output (configurable)" | [DS: web] 1 × digital input + 1 × digital output (open collector) | [DS: web] wins: 1 DI + 1 DO. Cytron wording may come from another hardware variant (see *Needs verification*). Material for wiring |
| CPU | [PP] "Qualcomm, ARM Cortex A7, 1.2 GHz" | [DS: web] "ARM Cortex-A7 1.3 GHz" | [DS: web] wins: 1.3 GHz |
| 3G downlink | [PP] up to 42 Mbps | [DS: web] up to 21 Mbps | [DS: web] wins: 21 Mbps |
| Weight | [PP] 134 g | [DS: web] 136 g | [DS: web] wins: 136 g |
| Mounting | [PP] "Aluminium housing with DIN rail mounting option" | [DS: web] DIN rail, wall, flat surface "(all require additional kit)" | [DS: web] wins: needs a kit |
| USB | [PP] "1 x Micro USB Slave" | [DS: web] "1 x Virtual network interface via micro USB" | Consistent: a USB device port used as a network interface |

## Needs verification
- **4-pin power socket pin order** (V+, GND, DI, DO) — Wiki not readable on 2026-10-21.
- Whether any TRB140 hardware revision (e.g. the TRB140*2**** variant with its own 2020 datasheet) has two configurable I/O, as the Cytron page says.
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG).
- LED meaning table (Wiki "TRB140 LEDs" not read).
- What the hex key opens (SIM cover or housing) — inferred only.
- Datasheet PDF "2023 v1.1" linked by Cytron vs Teltonika's current file (updated 2026-09-30) — PDF not opened.

## Sources
- [DS: web] Teltonika TRB140 product page, Features (technical specification): https://teltonika-networks.com/products/gateways/trb140 (read 2026-10-21).
- [VEN] Same page, Ordering tab (standard package, versions, order codes) and Downloads tab (flyer updated 2026-06-04, datasheet updated 2026-09-30; TRB140*2**** flyer and datasheet dated 2020-12-03) (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-trb140-lte-cat-4-ethernet-gateway (read 2026-10-21).
- [PP] Datasheet link on the Cytron page (not opened): https://teltonika-networks.com/cdn/products/2023/01/63b7fd4e13ec84-61325030/trb140-datasheet-2023-v11.pdf
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/TRB140_Manual, https://wiki.teltonika-networks.com/view/TRB140_Power_Socket_Pinout, https://wiki.teltonika-networks.com/view/QSG_TRB140
