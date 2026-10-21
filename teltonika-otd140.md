# Teltonika OTD140 — Verified Reference

| | |
|---|---|
| Product code | `OTD140` (Teltonika model; Teltonika standard order code `OTD140000000`). Cytron code `RUT-OTD-140`, MPN shown as `OTD140` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, MPN, description, specifications, packing list, resources) and the Teltonika product page (full technical specification, ordering/versions tab, downloads tab) read. The Teltonika Wiki could not be opened (Cloudflare bot check), so the port-labelling and LED pages [UM] were not read |
| Primary source | Teltonika Networks OTD140 product page, "Features" technical specification, https://teltonika-networks.com/products/routers/otd140 (read 2026-10-21; the downloads tab lists "OTD140 DATASHEET (EN)" updated 2026-09-24, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the ordering and downloads tabs of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Mobile module | 4G LTE up to 150 DL / 50 UL Mbps; 3G up to 21 DL / 5.76 UL Mbps; 2G up to 236.8 DL / 236.8 UL | [DS: web] |
| 3GPP release | Release 9 | [DS: web] |
| Bands (OTD140 0***** version, the only version listed) | LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B5, B8; 2G B3, B8. Region: Australia, Europe, Asia-Pacific | [VEN: ordering] |
| SIM | 2 × SIM slots (Mini SIM – 2FF), 1.8 V / 3 V; auto-switch on weak signal, data limit, SMS limit, roaming, no network, network denied, data connection fail, SIM idle protection | [DS: web] |
| Ethernet | 2 × RJ45 10/100 Mbps (both can be configured as WAN), IEEE 802.3, 802.3u, 802.3az, auto MDI/MDIX | [DS: web] |
| PoE in | 1 × PoE-in port, IEEE 802.3af/at | [DS: web] |
| PoE out | 1 × PoE-out port, IEEE 802.3af Alternative B, 15 W max per port at the PSE (power supply unit dependent) | [DS: web] |
| Power connector | RJ45 socket (PoE in) | [DS: web] |
| Input voltage (PoE) | 42.5–57.0 VDC, reverse polarity protection, voltage surge/transient protection | [DS: web] |
| Power consumption | Idle < 2.5 W; max < 6 W; with PoE out at max < 21 W | [DS: web] |
| Antennas | 2 × internal, 698–960 / 1710–2690 MHz, 50 Ω, VSWR < 3, gain < 4.5 dBi, omnidirectional | [DS: web] |
| Status LEDs | 3 × mobile connection type, 3 × mobile connection strength, 4 × ETH status | [DS: web] |
| Reset | Reboot / user default reset / factory reset button | [DS: web] |
| CPU | Mediatek, 580 MHz, MIPS 24KEc | [DS: web] |
| RAM | 128 MB | [DS: web] |
| Flash | 16 MB | [DS: web] |
| Operating system | RutOS (OpenWrt based Linux OS) | [DS: web] |
| Housing | Plastic (PC+ASA) | [DS: web] |
| Dimensions (W × H × D) | 110 × 49.30 × 235 mm | [DS: web] |
| Weight | 315 g | [DS: web] |
| Mounting | Mounting bracket (vertical flat surface or pole) | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 10 % to 90 % non-condensing | [DS: web] |
| Ingress protection | **IP55** | [DS: web] |
| HS code | 851762 (HTS 8517.62.00) | [VEN: ordering] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "OTD140 LTE Cat 4 Industrial Grade Outdoor Router"; brand Teltonika; Code `RUT-OTD-140`; MPN `OTD140`; warranty 12 months; RM701.00, RM679.97 for 3 or more; cashback RM21.03; availability 6; no reviews [PP].
- "Accessories you may need": Teltonika 4G Mobile Magnetic SMA Antenna (RM65.00) — but the OTD140 has internal antennas only and no SMA connector is listed (see *Conflicts*) [PP][DS: web].
- Description: IP55 plastic housing, -40 °C to 75 °C, integrated bracket for vertical surfaces or poles, LTE Cat 4 150/50 Mbps, dual SIM with automatic failover, one PoE-in and one PoE-out Ethernet port, firewall and VPN (OpenVPN, IPsec, GRE, PPTP, L2TP, DMVPN, SSTP, ZeroTier, WireGuard, Tinc), RMS. Suggested for construction sites, security surveillance, agriculture and public Wi-Fi zones [PP].
- Specifications on the page: 2 × Mini SIM 1.8/3 V; 2 × RJ45 10/100; PoE-in 802.3af/at; PoE-out 802.3af Alternative B max 15 W; 2 × internal omnidirectional antennas (698–960 / 1710–2690 MHz, gain < 4.5 dBi); power 42.5–57.0 VDC via RJ45 with reverse polarity and surge protection; idle < 2.5 W, max < 6 W, PoE max < 21 W; 110 × 49.3 × 235 mm; **weight 855 g**; integrated bracket; 10–90 % RH; IP55 [PP].
- **Packing list:** 1 × OTD140 Router only [PP]. Teltonika's standard package is router, router holder, QSG and box [VEN]. **No PSU or PoE injector is in either list.**
- RMS: free 30-day RMS trial [PP].
- **Resources:** Quick Start Guide (Wiki QSG_OTD140), Datasheet (…/otd140-datasheet-v11.pdf, not opened), User Manual (Wiki OTD140_Manual), SDK downloads, Firmware downloads, Flyer (…/otd140-flyer-2024-v18.pdf) [PP].
- Use cases listed: underground EV charging station, construction site CCTV and portable office [PP].

## Interfaces, terminals and pin mapping
There are no screw terminals. All wiring is through two RJ45 ports [DS: web]:

| Port | Role | Electrical | Src |
|---|---|---|---|
| ETH (PoE in) | Powers the router; data LAN/WAN | IEEE 802.3af/at PD input, 42.5–57.0 VDC, reverse polarity and surge/transient protected | [DS: web] |
| ETH (PoE out) | Powers a downstream device (camera, AP); data LAN/WAN | IEEE 802.3af Alternative B, 15 W max, depends on the upstream PSU | [DS: web] |

Which physical port is PoE-in and which is PoE-out (port labels, cable gland arrangement) was **not read** — the Wiki pages could not be opened. SIM slots, reset button and LEDs are inside/under the housing per Teltonika's usual outdoor design — not verified (see *Needs verification*).

## Rules and gotchas (for code, wiring and tutorials)
- **Budget a PoE source.** The OTD140 has no DC barrel/terminal input; it is powered only through the PoE-in RJ45 at 42.5–57.0 VDC (802.3af/at). Cytron and Teltonika list no injector in the box, so a separate 802.3af/at PoE injector or PoE switch is needed — inferred from the power spec and packing lists [DS: web][PP][VEN].
- **PoE-out needs an 802.3at (PoE+) source to deliver its full 15 W** — inferred: the spec says PoE-out is "power supply unit dependent" and total PoE consumption can reach < 21 W, above the 802.3af input class [DS: web].
- **PoE-out is 802.3af Alternative B** (spare pairs 4/5 and 7/8 per the 802.3 standard — the pair note is inferred from the standard, not stated by Teltonika). Check the camera/AP accepts 802.3af [DS: web].
- **Do not connect passive 24 V PoE** — the input is 42.5–57.0 VDC 802.3af/at [DS: web].
- **No external antenna connectors** are listed; the two LTE antennas are internal [DS: web].
- **IP55** covers dust and water jets per IEC 60529 (standard definition, not a Teltonika statement); seal the cable entries as the QSG shows (QSG not read) [DS: web].
- **No Wi-Fi.** "Public Wi-Fi zones" on the Cytron page means pairing it with a PoE access point on PoE-out — inferred [PP][DS: web].
- **Never publish the default login.** The device's default login is printed on its label / in the Wiki (not copied here).

## Power and electrical limits
- Input: 42.5–57.0 VDC through the PoE-in RJ45 (802.3af/at), reverse polarity and surge/transient protected [DS: web].
- Consumption: idle < 2.5 W, max < 6 W, max < 21 W when PoE-out is loaded [DS: web].
- PoE-out: 15 W max at the PSE, 802.3af Alternative B, dependent on the upstream supply [DS: web].
- Environment: -40 °C to 75 °C, 10–90 % RH non-condensing, IP55 [DS: web].

## Software support
- **RutOS** (OpenWrt-based Linux). WebUI HTTP/HTTPS, CLI, SSH, email alerts, SMS and call control, TR-069, SNMP v1/v2/v3, JSON-RPC, MQTT broker/publisher, RMS, FOTA [DS: web].
- Industrial protocols over TCP only: Modbus server/client, Modbus–MQTT gateway, DNP3, BACnet/IP router, OPC UA, DLMS/COSEM client [DS: web].
- Network: static and dynamic routing (BGP, OSPF, RIP, EIGRP, NHRP), VLAN, hotspot captive portal, failover over VRRP or wired WAN, 802.1x server [DS: web].
- VPN: OpenVPN, IPsec, GRE, PPTP, L2TP, Stunnel, DMVPN, SSTP, ZeroTier, WireGuard, Tinc [DS: web].
- Development: SDK; Busybox shell, Lua, C, C++, and Python and Java through the Package Manager; Web API (beta) [DS: web].

## Compatibility and accessories
- Needs an IEEE 802.3af/at PoE injector or PoE switch (not included) — inferred [DS: web][PP][VEN].
- Downstream PoE devices: 802.3af, up to 15 W [DS: web].
- The Teltonika 4G Mobile Magnetic SMA Antenna suggested by Cytron has no listed connector to attach to (see *Conflicts*).
- Region of the only listed version: Australia, Europe, Asia-Pacific [VEN].

## Common mistakes / troubleshooting
- **Router does not power up:** it needs 802.3af/at PoE at 42.5–57.0 VDC on the PoE-in port. A passive 12/24 V injector or the PoE-out port will not work [DS: web].
- **Camera on PoE-out does not start:** PoE-out is 802.3af Alt B, 15 W max, and depends on the upstream PSU budget [DS: web].
- **Weak signal:** antennas are internal; mount the unit high and clear of metal — inferred.
- **Cannot reach the WebUI or log in:** use the address and login printed on the device label / in the Wiki QSG (not copied here). A factory reset restores the default IP and login [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Weight | [PP] 855 g | [DS: web] 315 g | [DS: web] wins: 315 g. 855 g may be a shipping weight — unconfirmed |
| Suggested accessory | [PP] "Accessories you may need: Teltonika 4G Mobile Magnetic SMA Antenna" | [DS: web] antennas: 2 × internal; no external antenna connector listed | [DS: web] wins: no SMA port is listed. Ask Cytron to review the accessory link |
| Package contents | [PP] 1 × OTD140 Router | [VEN] router, router holder, QSG, box | [VEN] lists more items; confirm what Cytron ships. Neither includes a PoE injector |
| MPN | [PP] MPN "OTD140" | [VEN] standard order code OTD140000000 | Not a conflict; Cytron shows the model name as MPN |

## Needs verification
- **Which RJ45 is PoE-in and which is PoE-out** (port labels) — Wiki not readable on 2026-10-21.
- Location of SIM slots, reset button and LEDs inside the housing; cable gland / sealing procedure (Wiki QSG not read).
- Default LAN IP address and WebUI URL (not read; take from the Wiki QSG).
- Whether an 802.3af (not at) source is enough to run the router with PoE-out loaded (spec implies PoE-out is PSU dependent).
- Whether Cytron ships the router holder/bracket (Cytron packing list shows only the router).
- Datasheet PDF v1.1 linked by Cytron vs Teltonika's current file (updated 2026-09-24) — PDF not opened.

## Sources
- [DS: web] Teltonika OTD140 product page, Features (technical specification): https://teltonika-networks.com/products/routers/otd140 (read 2026-10-21).
- [VEN] Same page, Ordering tab (standard package, version, order code) and Downloads tab (flyer updated 2024-05-07, datasheet updated 2026-09-24) (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-otd140-lte-cat-4-industrial-grade-outdoor-router (read 2026-10-21).
- [PP] Datasheet link on the Cytron page (not opened): https://teltonika-networks.com/cdn/products/2023/12/657ab778107bc7-23956832/datasheet-pdf/otd140-datasheet-v11.pdf
- [UM] Not read (Cloudflare bot check): https://wiki.teltonika-networks.com/view/OTD140_Manual, https://wiki.teltonika-networks.com/view/QSG_OTD140
