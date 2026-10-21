# Teltonika RUT140 — Verified Reference

| | |
|---|---|
| Product code | `RUT140` (Teltonika model). Cytron code `RUT-140`, MPN / Teltonika order code `RUT140000000` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, features, packing list, resources) and the Teltonika product page (full "Features" technical specification, Ordering, Downloads and Certifications tabs) read. The Teltonika Wiki could not be opened (Cloudflare bot check on every Wiki URL), so no [UM] pinout, LED or QSG page was read |
| Primary source | Teltonika Networks RUT140 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/rut140 (read 2026-10-21; the Downloads tab lists "RUT140 DATASHEET (EN)" updated 2026-09-29, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the Ordering, Downloads and Certifications tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page, so the 3-pin terminal pin order, LED meanings and the default LAN address are not given here; see *Needs verification*.

## What it is
Teltonika's page title calls it an "Industrial Modbus Router"; Cytron's title is "Industrial Ethernet Router". Its stated purpose is network isolation (segmentation) for end devices, plus industrial protocols (Modbus, DLMS, DNP3, OPC UA) and RMS remote management [DS: web][PP].
Compared with the RUT200 (`teltonika-rut200.md`), it has no LTE, no SIM and no I/O, uses a 3-pin terminal block instead of the 4-pin socket, and draws much less power (< 2 W max) [DS: web].
The unit Cytron sells is order code `RUT140000000`, the only version Teltonika lists ("RUT140 0*****", standard package) [PP][VEN].

## Specifications
| Item | Value | Src |
|---|---|---|
| Cellular | None (Ethernet + Wi-Fi router; no mobile module, no SIM slot) | [DS: web] |
| Wi-Fi | 802.11b/g/n (Wi-Fi 4), Access Point (AP), Station (STA); up to 50 simultaneous users; WPA2/WPA3 options; mesh 802.11s, 802.11r/k/v | [DS: web] |
| Ethernet WAN | 1 × WAN port 10/100 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Ethernet LAN | 1 × LAN port 10/100 Mbps (IEEE 802.3, 802.3u, 802.3az), auto MDI/MDIX | [DS: web] |
| Network backup | Wi-Fi WAN, VRRP, wired options as automatic failover (no mobile) | [DS: web] |
| CPU | Mediatek, 580 MHz, MIPS 24KEc | [DS: web] |
| RAM | 128 MB, DDR2 | [DS: web] |
| Flash | 16 MB serial NOR flash | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Power connector | 3-pos pluggable terminal block | [DS: web] |
| Input voltage | 9–30 VDC, reverse polarity protection, surge protection >31 VDC 10 µs max | [DS: web] |
| Passive PoE | Passive PoE over spare pairs, power through LAN1 port, Mode B, 9–30 VDC; not compatible with IEEE 802.3af, 802.3at or 802.3bt | [DS: web] |
| Power consumption | Idle < 1 W; max < 2 W | [DS: web] |
| Antenna connectors | 1 × RP-SMA for Wi-Fi | [DS: web] |
| Status LEDs | 1 × WAN type LED, 1 × LAN type LED, 1 × power LED | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| Other | 1 × grounding screw | [DS: web] |
| Housing | Anodised aluminium housing and panels | [DS: web] |
| Dimensions (W × H × D) | 113.10 × 25 × 68.6 mm | [DS: web] |
| Weight | 142.3 g | [DS: web] |
| Mounting | Integrated DIN rail bracket; wall mount and flat surface need an additional kit | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
| Approvals | CB Scheme, FCC, IC (ISED), RCM, ETA-WPC, CE/RED, UKCA, RoHS, REACH, Kenya, ICASA, ANRT (SIRIM not listed) | [VEN: certifications] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "RUT140 Industrial Ethernet Router"; brand Teltonika; Code `RUT-140`; MPN `RUT140000000`; warranty 12 months; RM312.00, RM302.64 for 3 or more; cashback RM9.36; availability 1; 1 rating [PP].
- "Accessories you may need": Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00) — see *Conflicts*: this model has no cellular modem and no SMA port [PP].
- Hardware list matches [DS: web] for CPU, memory, storage, power (3-pos pluggable terminal, 9–30 VDC), antenna (1 × RP-SMA), Ethernet (1 WAN, 1 LAN), Wi-Fi, grounding screw, LEDs, temperature, housing, size and weight [PP].
- Software list: RutOS; network protocols; OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc; WebUI, CLI, SSH, SMS, Call, Email, TR-069, SNMP, JSON-RPC, MQTT, RMS; RMS, FOTA, Azure IoT Hub, Cloud of Things, Cumulocity; captive-portal hotspot [PP].
- **Packing list:** 1 × Router RUT140, 1 × 3-pin power connector, 1 × Quick Start Guide [PP]. This matches Teltonika's standard package (plus packaging box) [VEN]. **No power supply and no Wi-Fi antenna are listed** by either source.
- RMS: the page says every Teltonika device, including this one, comes with a free 30-day RMS trial [PP].
- **Resources:** Quick Start Guide (Wiki `QSG_RUT140`), Manual (Wiki `RUT140_Manual`), Crowd Support Forum, Datasheet (teltonika-networks.com `_files/ugd/…pdf`), Flyer (`rut140-flyer-2023-v11.pdf`), and a link to the Teltonika product page [PP].
- Use case listed: network segmentation with an industrial Ethernet router [PP].

## Interfaces, terminals and pin mapping
**Exact pin order of the 3-pin terminal was not read.** The Teltonika Wiki pages "RUT140 Manual" / power and LED pages could not be opened (Cloudflare bot check). What the specification says about each connector [DS: web]:

| Connector | What is on it | Src |
|---|---|---|
| 3-pos pluggable terminal block | Power input 9–30 VDC (mating 3-pin plug in the box) | [DS: web][PP] |
| RJ45 × 2 | 1 WAN + 1 LAN, 10/100 Mbps; LAN1 also accepts passive PoE (Mode B, 9–30 VDC) | [DS: web] |
| RP-SMA × 1 | Wi-Fi antenna | [DS: web] |
| Grounding screw | Chassis earth | [DS: web] |
| Reset button | Reboot / user default / factory reset | [DS: web] |

## Rules and gotchas (for code, wiring and tutorials)
- **No cellular.** There is no LTE modem or SIM slot. Internet comes from the WAN port, Wi-Fi as a client (STA / Wi-Fi WAN) or passthrough from another router [DS: web].
- **Bring your own power supply.** The box has only the 3-pin plug, not a PSU; use 9–30 VDC [PP][VEN][DS: web].
- **Bring a Wi-Fi antenna.** Neither the Cytron packing list nor Teltonika's standard package lists one; the RP-SMA port is empty out of the box (inferred from both package lists) [PP][VEN].
- **Get the 3-pin terminal pin order from the Teltonika Wiki before wiring.** Not read here.
- **Passive PoE on LAN1 is not 802.3af/at/bt.** Use a passive injector in the 9–30 VDC range [DS: web].
- **Wi-Fi is 2.4 GHz only** (802.11b/g/n) [DS: web].
- **No I/O, no serial, no USB.** Modbus, DNP3, DLMS and BACnet are over TCP/IP only [DS: web].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Supply: 9–30 VDC on the 3-pos pluggable terminal block, reverse polarity protected, surge protection >31 VDC for 10 µs max [DS: web].
- Passive PoE: LAN1, Mode B (spare pairs), 9–30 VDC [DS: web].
- Consumption: idle < 1 W, max < 2 W [DS: web]. No PSU in the box [PP][VEN].
- Grounding screw provided [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP30 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI over HTTP/HTTPS, CLI, SSH v1/v2, email alerts, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS [DS: web].
- Industrial protocols: Modbus TCP server/client; Modbus–MQTT gateway; DNP3 station/outstation (TCP); BACnet router (IP); OPC UA client/server (TCP); DLMS/COSEM client (TCP) [DS: web].
- Data to server: HTTP(S), MQTT, Azure MQTT, custom Lua. IoT platforms: Cumulocity – Cloud of Things, Azure IoT Hub [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP (incl. L2TPv3), Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc, EoIP [DS: web].
- Network: static and dynamic routing (BGP, OSPF v2, RIP, EIGRP, NHRP), VLAN, firewall, DHCP, QoS/SQM, DDNS, DNS over HTTPS, VRRP, load balancing, hotspot, 802.1x [DS: web].
- Development: SDK with build environment; Busybox shell, Lua, C, C++; Package Manager; GPL customisation; Teltonika Networks Web API (beta) [DS: web].
- Firmware: update from file, FOTA, RMS; keep settings on update; factory reset [DS: web].
- RMS 30-day free trial [PP].

## Compatibility and accessories
- Needs: a 9–30 VDC supply (or passive PoE injector) and a 2.4 GHz Wi-Fi antenna with RP-SMA male plug if Wi-Fi is used (inferred from the package lists) [PP][VEN].
- Cytron's suggested accessory (4G Mobile Magnetic SMA Antenna) does not fit any port on this model (inferred: SMA vs RP-SMA, and no cellular) [PP][DS: web].
- DIN rail bracket is integrated; wall or flat-surface mounting needs an extra kit [DS: web].
- Related Cytron-sold Teltonika models: RUT200 (adds 4G LTE, 1 SIM), RUT901 / RUT906 (dual-SIM 4G, 4 Ethernet) [DS: web].

## Common mistakes / troubleshooting
- **Router does not power up out of the box:** no PSU is included; wire 9–30 VDC to the 3-pin plug [PP][VEN].
- **Weak or no Wi-Fi:** fit an RP-SMA Wi-Fi antenna; none is listed in the box [PP][VEN].
- **No power over PoE from a standard PoE switch:** passive PoE only (Mode B, 9–30 VDC) [DS: web].
- **Looking for SMS or call control:** there is no modem; Teltonika lists email alerts, not SMS/call, under Monitoring & Management for this model [DS: web].
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Monitoring via SMS / Call | [PP] Monitoring and Management lists "SMS, Call" | [DS: web] Monitoring & Management lists WebUI, FOTA, SSH, Email, TR-069, MQTT, SNMP, JSON-RPC, RMS — no SMS or Call; the model has no modem | [DS: web] wins: no SMS/Call management |
| Suggested accessory | [PP] "Accessories you may need: Teltonika 4G Mobile Magnetic SMA Antenna" | [DS: web] no mobile module; only 1 × RP-SMA (Wi-Fi) | [DS: web]. The 4G antenna is not usable with RUT140 |
| Product name | [PP] "Industrial Ethernet Router" | [VEN] page title "Industrial Modbus Router" | Not a spec conflict; both describe the same model |
| Housing | [PP] "Aluminium housing with integrated DIN rail" | [DS: web] "Anodised aluminium housing and panels"; integrated DIN rail bracket | Consistent; [DS: web] wording used |

## Needs verification
- **3-pin terminal pin order** (V+, GND and the third pin's function) — Wiki not readable on 2026-10-21 (Cloudflare check).
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG or the device label).
- LED meaning table (Wiki not read).
- Whether a Wi-Fi antenna is in the box (neither source lists one).
- SIRIM approval: not in Teltonika's certifications list for RUT140 (RUT200/901/906 list it) [VEN]. Check before quoting for Malaysian projects that need it.
- Datasheet PDF version (Teltonika lists 2026-09-29; the Cytron link was not opened).

## Sources
- [DS: web] Teltonika RUT140 product page, Features (technical specification): https://teltonika-networks.com/products/routers/rut140 (read 2026-10-21).
- [VEN] Same page: Ordering tab (standard package, version and order code, HS code), Downloads tab (flyer updated 2024-04-12, datasheet updated 2026-09-29), Certifications tab (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-rut140-industrial-ethernet-router (read 2026-10-21).
- [PP] Datasheet link on the Cytron page (not opened; redirects to a Wix file host): https://www.teltonika-networks.com/_files/ugd/814ec4_7b6b76e72de64e759351a2dcf2a246f4.pdf
- [PP] Flyer link on the Cytron page (not opened): https://teltonika-networks.com/cdn/products/2024/01/65b8bac000a865-65776724/flyers/rut140-flyer-2023-v11.pdf
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/RUT140_Manual, https://wiki.teltonika-networks.com/view/QSG_RUT140
