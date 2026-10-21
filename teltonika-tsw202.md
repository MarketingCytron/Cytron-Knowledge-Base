# Teltonika TSW202 — Verified Reference

| | |
|---|---|
| Product code | `TSW202` (Teltonika model). Cytron code `SW-TSW-202`; no MPN shown on the Cytron page [PP]. Teltonika order codes `TSW202000000` (no PSU), `TSW202000300` (EU PSU without connector), `TSW202000040` (US PSU without connector), `TSW202000001` (Profinet Class B, no PSU) [VEN: ordering] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, features, packing list, resources) and the Teltonika product page (full technical specification, certifications, downloads and ordering tabs, compatible accessories) read. The Teltonika Wiki could not be opened (Cloudflare bot check), so no [UM] page was read |
| Primary source | Teltonika Networks TSW202 product page, "Features" technical specification, https://teltonika-networks.com/products/ethernet-switches/tsw202 (read 2026-10-21; the downloads tab lists "TSW202 DATASHEET (EN)" updated 2026-09-30, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the certifications, downloads, ordering and compatible-accessories parts of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page. Power socket pin numbers, default LAN IP and LED meanings are therefore not given here; see *Needs verification*.

## What it is
Power is 7–57 VDC on a 2-pin industrial DC socket, but **PoE output needs 44–57 VDC** [DS: web]. It has an anodised aluminium IP30 housing with an integrated DIN rail bracket [DS: web].

## Specifications
| Item | Value | Src |
|---|---|---|
| Ethernet | Multi-layer managed 8 × ETH ports, 10/100/1000 Mbps, auto MDI/MDIX | [DS: web] |
| Fibre | 2 × SFP ports | [DS: web] |
| IEEE 802.3 standards | 802.3i, 802.3u, 802.3ab, 802.3x, 802.3az, 802.3z, 802.3ad | [DS: web] |
| Industrial protocols | Profinet Class B conformance (optional order code `TSW202000001`); EtherNet/IP yes; MRP client and manager roles | [DS: web][VEN: ordering] |
| PoE+ ports | Port 1 – 8 | [DS: web] |
| PoE standards | IEEE 802.3af (Type 1) and 802.3at (Type 2). **Alternative A** on Batch 15 and all batches from Batch 17 on; **Alternative B** on Batches 1–14 and Batch 16 | [DS: web] |
| PoE max power per port (at PSE) | 30 W | [DS: web] |
| Total PoE power budget (at PSE) | 240 W | [DS: web] |
| PoE protection | Short-circuit and overload protection | [DS: web] |
| Max Ethernet cable length | 100 m | [DS: web] |
| Services | EtherNet/IP, SNMP v2/v3, LLDP; 802.1p CoS, 802.1x port access control, 802.1Q VLAN | [DS: web] |
| L2 / network | Loop protection, forwarding table, VLAN, STP/RSTP; LACP (802.3ad); IGMP snooping, multicast querier; port enable/disable, speed control, isolation, PoE management, EEE, port mirroring | [DS: web] |
| L3 | Static IPv4/IPv6 routing, DHCPv6 client, static IPv6 address; dynamic routing BGP, OSPF v2, RIP v1/v2, EIGRP | [DS: web] |
| DHCP | Server, client, static leases (MAC with wildcards) | [DS: web] |
| Security | PAM (preshared key, RADIUS, TACACS+), IP and login-attempt block; MAC filtering per port | [DS: web] |
| QoS | Port, DSCP, 802.1p, TOS priority; SP/WFQ/WRR scheduling; rate limiting, storm control; port-based shaping | [DS: web] |
| Diagnostics | Cable diagnostic, ping, traceroute, nslookup; ping reboot can restart PoE on a port | [DS: web] |
| Management | WebUI (HTTP/HTTPS), CLI, SSH v1/v2, FOTA, RMS, Teltonika Web API (beta), Site Manager (managed device) | [DS: web] |
| RAM / flash | 128 MB DDR3 / 16 MB serial flash | [DS: web] |
| Operating system | TSWOS (OpenWrt based Linux OS); Busybox shell, Lua, C, C++; SDK provided | [DS: web] |
| Bandwidth / forwarding | 20 Gbps non-blocking; 14.88 Mpps | [DS: web] |
| Packet buffer / MAC table / jumbo | 512 KB / 8K entries / 10000 bytes | [DS: web] |
| Power connector | 2-pin industrial DC power socket | [DS: web] |
| Input voltage range | 7 – 57 VDC; reverse polarity protection -80 V max | [DS: web] |
| PoE-Out input voltage range | 44 – 57 VDC | [DS: web] |
| Power consumption | Idle < 3 W / Max 8 W / PoE Max 248 W | [DS: web] |
| Ethernet surge | 1 kV line to ground, 1.2/50 µs, IEC 61000-4-5 | [DS: web] |
| Status LEDs | 1 × Power, 1 × Aux, 16 × ETH status, 2 × SFP status | [DS: web] |
| Reset | Software reset button | [DS: web] |
| Other | 1 × grounding screw | [DS: web] |
| Casing | Anodised aluminium housing and panels | [DS: web] |
| Dimensions (W × H × D) | 132 × 44.2 × 122.2 mm | [DS: web] |
| Weight | 610 g | [DS: web] |
| Mounting | Integrated DIN rail bracket; wall mount and flat surface need an additional kit | [DS: web] |
| Operating temperature / humidity | -40 °C to 75 °C / 5 % to 95 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| Standard package | TSW202, QSG, packaging box (PSU only on PSU order codes) | [VEN: ordering] |
| Certifications listed | CB Scheme, FCC, IC (ISED), UL/CSA Safety, Anatel, NOM, RCM, NBTC, SDPPI (POSTEL), Giteki, MTCTE, CE, UKCA, RoHS, REACH, CITC, Kenya, ICASA, Morocco ANRT, WEEE | [VEN: certifications] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "TSW202 Industrial Managed PoE+ Switch"; Brand Teltonika; Code SW-TSW-202; warranty 12 months; RM686.00 (RM665.42 for 3 or more; cashback RM20.58); availability 4 [PP].
- Features listed match [DS: web] for ports, 30 W per port, 240 W budget, 100 m, 2 × SFP, LEDs, socket, reset button, grounding screw, casing, -40 to 75 °C, 132 × 44.2 × 122.2 mm, 610 g, mounting, TSWOS, VLAN/MRP/L2/L3/DHCP/QoS features [PP].
- The page states "PoE standards: 802.3af and 802.3at Alternative B" and does **not** give the power input voltage range [PP] (see *Conflicts*).
- **Packing list:** 1 × TSW202 switch, 1 × Quick Start Guide [PP]. No PSU listed.
- **Accessories you may need:** Teltonika DIN Rail Kit, RM49.00 [PP] (Teltonika does not list that kit for the TSW202; see *Conflicts*).
- **Resources:** datasheet (Google Drive copy), Quick Start Guide (Wiki "QSG TSW202"), Teltonika community forum, User Manual (Wiki "TSW202 Manual"), Teltonika product page [PP].
- RMS 30-day free trial mentioned [PP].

## Interfaces, terminals and pin mapping
| Interface | Detail | Src |
|---|---|---|
| ETH 1–8 | RJ45, 10/100/1000 Mbps, PoE+ out on all eight (802.3af/at, ≤30 W each) | [DS: web] |
| SFP 1–2 | Fibre SFP cages, 802.3z | [DS: web] |
| Power | 1 × 2-pin industrial DC power socket, 7–57 VDC (PoE needs 44–57 VDC) | [DS: web] |
| Reset | Software reset button | [DS: web] |
| Ground | 1 × grounding screw | [DS: web] |
| LEDs | Power, Aux, 16 × ETH (two per port, inferred), 2 × SFP | [DS: web] |

Power socket pin numbering and polarity are on the Wiki ("TSW202 Power Socket Pinout" / "TSW202 Manual"), which could not be read (see *Needs verification*).

## Rules and gotchas (for code, wiring and tutorials)
- **PoE needs 44–57 VDC.** The switch boots from 7 V upward, but below 44 V it cannot power PoE devices. Use a 48 V (or 54 V) supply for PoE projects [DS: web]. The Cytron page does not mention this.
- **240 W budget, 248 W max consumption.** Size the PSU accordingly; Teltonika lists 62 W, 130 W and 250 W 2-pin PSUs [DS: web][VEN].
- **PoE Alternative depends on production batch** (A on Batch 15 and 17+, B on 1–14 and 16). Compliant 802.3af/at devices work with either; passive-PoE gear may not (inferred) [DS: web].
- **It is managed.** First access is through the WebUI; the default LAN IP and login are in the Wiki/label (the login is not copied here). Do not describe it as plug-and-play [DS: web].
- **PROFINET only on order code `TSW202000001`;** standard code has "PROFINET disabled by default" [VEN: ordering].
- **SFP modules are not included.** Teltonika lists 1.25 Gb/s SR, 20 km BiDi and copper RJ45 SFP transceivers [VEN].
- **DIN bracket is integrated;** wall and flat-surface mounting need an extra kit [DS: web].

## Power and electrical limits
- Input 7–57 VDC, reverse polarity protection to -80 V; PoE-out input range 44–57 VDC [DS: web].
- Consumption idle < 3 W, max 8 W, PoE max 248 W [DS: web].
- PoE ≤30 W per port and 240 W total at PSE, short-circuit and overload protected [DS: web].
- Ethernet surge 1 kV line-to-ground (IEC 61000-4-5) [DS: web].
- Environment -40 to 75 °C, 5–95 % RH non-condensing, IP30 [DS: web].

## Software support
- **TSWOS** (OpenWrt-based Linux OS); Busybox shell, Lua, C, C++; SDK package with build environment; GPL downloads [DS: web][VEN].
- WebUI over HTTP/HTTPS with status, configuration, FW update, CLI, logs; SSH v1/v2; FOTA; configuration profiles and backup; keep-settings firmware update [DS: web].
- RMS: firmware/configuration for many devices at once [DS: web]. Cytron page: 30-day RMS trial [PP].
- Teltonika Web API (beta), docs at developers.teltonika-networks.com [DS: web].
- Firmware downloads: Wiki "TSW202 Firmware Downloads" (not readable on 2026-10-21) [VEN].

## Compatibility and accessories
- Teltonika-listed compatible accessories: 1.25 Gb/s 20 km BiDi SFP, 1.25 Gb/s copper RJ45 SFP, 1.25 Gb/s SR SFP; 2-pin PSUs (AU/EU/UK/US 62 W and 250 W, EU 130 W); Ethernet cable 1.5 m; RJ45 dust covers; SFP dust cover [VEN].
- The Teltonika DIN Rail Kit (PR5MEC00) does **not** list the TSW202 as compatible on Teltonika's site; the TSW202 has its own integrated DIN rail bracket [VEN][DS: web]. Cytron's DIN Rail Kit page and this product page suggest it anyway [PP].
- Pairs with Cytron-sold Teltonika routers (RUT956, RUTX50 etc.) as a managed PoE LAN extension (inferred).

## Common mistakes / troubleshooting
- **PoE devices do not power up:** supply is below 44 V. Use 48–54 V within 44–57 V [DS: web].
- **Buying the DIN Rail Kit for it:** the bracket is already integrated [DS: web].
- **Expecting SFP modules or a PSU in the box:** packing list is switch + QSG [PP].
- **Cannot reach the WebUI:** check the default IP and set a PC on the same subnet (default IP not verified here; see Wiki) [UM, not read].
- **PROFINET missing:** standard units have it disabled; the Profinet variant is a separate order code [VEN].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| PoE alternative | [DS: web] Alternative A (Batch 15, 17+) or B (Batches 1–14, 16) | [PP] "802.3af and 802.3at Alternative B" | [DS: web] wins: depends on batch |
| Input voltage | [DS: web] 7–57 VDC, PoE needs 44–57 VDC | [PP] not stated | [DS: web]; Cytron page incomplete |
| DIN Rail Kit fit | [VEN] DIN Rail Kit compatible list has no TSW202; TSW202 has integrated DIN bracket [DS: web] | [PP] DIN Rail Kit listed as "Accessories you may need" and as compatible on the kit page | Teltonika wins: kit not needed/not listed for TSW202 |
| 802.3 standards | [DS: web] adds 802.3az and 802.3ad | [PP] 802.3i/u/ab/x/z | [DS: web] is the full list |

## Needs verification
- Power socket pinout and polarity, LED meanings, default LAN IP and first-login procedure: Wiki "TSW202 Manual", "QSG TSW202", "TSW202 Power Socket Pinout", "TSW202 LEDs" could not be opened (Cloudflare) [UM].
- Which order code / production batch Cytron stocks (decides Alternative A or B and whether PROFINET is present).
- Current TSWOS firmware version (Wiki firmware page not readable).
- Datasheet PDF content (2026-09-30 version) and Cytron's Google Drive datasheet copy not opened.

## Sources
- [DS: web] Teltonika TSW202 product page, Features tab: https://teltonika-networks.com/products/ethernet-switches/tsw202, read 2026-10-21.
- [VEN] Same page: certifications, downloads (flyer updated 2024-05-28; datasheet updated 2026-09-30), ordering and compatible accessories, read 2026-10-21.
- [VEN] Teltonika DIN Rail Kit page (compatible products list): https://teltonika-networks.com/products/accessories/mounting-options/din-rail-kit
- [UM] Teltonika Wiki (not readable on 2026-10-21): https://wiki.teltonika-networks.com/view/TSW202_Manual, https://wiki.teltonika-networks.com/view/QSG_TSW202, https://wiki.teltonika-networks.com/view/TSW202_Firmware_Downloads
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-tsw202-industrial-managed-poe-plus-switch, read 2026-10-21.
- [PP] Cytron datasheet copy (not opened): (Cytron document — link not public)
