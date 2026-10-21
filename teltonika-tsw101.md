# Teltonika TSW101 — Verified Reference

| | |
|---|---|
| Product code | `TSW101` (Teltonika model; Cytron MPN `TSW101`). Cytron code `SW-TSW-101` [PP]. Teltonika order codes `TSW101000000` (standard, no PSU), `TSW101000020` (mass packing), `TSW101000001` (Profinet Class A, no PSU) [VEN: ordering] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, features, specifications, packing list, resources) and the Teltonika product page (full technical specification, certifications, downloads and ordering tabs, compatible accessories) read. The Teltonika Wiki could not be opened (Cloudflare bot check), so no [UM] page was read. The datasheet PDF link on the Cytron page (v1.4) returns 404 |
| Primary source | Teltonika Networks TSW101 product page, "Features" technical specification, https://teltonika-networks.com/products/ethernet-switches/tsw101 (read 2026-10-21; the downloads tab lists "TSW101 DATASHEET (EN)" updated 2026-09-30, PDF not opened) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Features" technical specification on the teltonika-networks.com product page (same content as the datasheet; the PDF itself was not opened). [VEN] = the certifications, downloads, ordering and compatible-accessories parts of the same Teltonika page. [PP] = Cytron product page. No [UM] (Teltonika Wiki) page could be read on 2026-10-21: every Wiki URL stopped at a Cloudflare "Performing security verification" page. The power socket pin numbers are therefore not given here; see *Needs verification*.

## What it is
Teltonika says "No configuration needed" and describes it as "dedicated to in-vehicle applications" [DS: web]. The specification lists no firmware, WebUI or management features, so it is treated as unmanaged (inferred from the spec; Teltonika's own word is "plug-and-play").

## Specifications
| Item | Value | Src |
|---|---|---|
| Ethernet | 5 × ETH ports, 10/100/1000 Mbps, auto MDI/MDIX crossover | [DS: web] |
| IEEE 802.3 standards | 802.3i, 802.3u, 802.3ab, 802.3x, 802.3az | [DS: web] |
| Industrial protocols | Profinet Class A conformance (only with the optional order code `TSW101000001`) | [DS: web][VEN: ordering] |
| PoE+ ports | Port 1 – 4 | [DS: web] |
| PoE standards | IEEE 802.3af (PoE, Type 1) and IEEE 802.3at (PoE+, Type 2), Alternative A | [DS: web] |
| PoE max power per port (at PSE) | 30 W | [DS: web] |
| Total PoE power budget (at PSE) | 60 W | [DS: web] |
| Max Ethernet cable length | 100 m | [DS: web] |
| Bandwidth (non-blocking) | 10 Gbps | [DS: web] |
| Packet buffer | 128 KB (the page spells it "Packer buffer") | [DS: web] |
| MAC address table | 2K entries | [DS: web] |
| Jumbo frames | 9216 bytes | [DS: web] |
| Power connector | 2-pin industrial DC power socket | [DS: web] |
| Input voltage range | 9 – 30 VDC | [DS: web] |
| PoE-Out input voltage range | 9 – 30 VDC | [DS: web] |
| Power consumption | Idle 0.64 W / Max 2.31 W / PoE Max 62.3 W | [DS: web] |
| PSU | 12 V or 24 V car battery-powered; no additional PSU required | [DS: web] |
| Status LEDs | 1 × Power LED, 10 × ETH status LEDs | [DS: web] |
| Other | 1 × grounding screw | [DS: web] |
| Casing | Anodised aluminium housing and panels | [DS: web] |
| Dimensions (W × H × D) | 115 × 32 × 95 mm | [DS: web] |
| Weight | 384 g | [DS: web] |
| Mounting | DIN rail, wall mount, flat surface — **all require an additional kit** | [DS: web] |
| Operating temperature | -40 °C to 75 °C | [DS: web] |
| Operating humidity | 5 % to 95 % non-condensing | [DS: web] |
| Ingress protection | IP30 | [DS: web] |
| Standard package | TSW101, QSG (Quick Start Guide), packaging box; no PSU | [VEN: ordering] |
| HS / HTS code | 851762 / 8517.62.00 | [VEN: ordering] |
| Certifications listed | E-mark (UN ECE R10), CB Scheme, FCC, IC (ISED), Anatel, RCM, MTCTE, CE, UKCA, EAC, RoHS, REACH, CITC, Kenya, Morocco ANRT, WEEE | [VEN: certifications] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "TSW101 Automotive PoE+ Switch"; Brand Teltonika; Code SW-TSW-101; MPN TSW101; warranty 12 months; RM341.00 (cashback RM10.23); availability 1 [PP].
- Page specifications match [DS: web] for ports, 802.3 standards, PoE ports 1–4, 30 W per port, 60 W budget, 100 m, performance figures, 2-pin DC socket, 9–30 VDC, power consumption, LEDs, grounding screw, 115 × 32 × 95 mm, 384 g, -40 to 75 °C, 5–95 % RH, IP30 [PP].
- The page omits "Alternative A", the Profinet option and the "(all require additional kit)" note on mounting [PP].
- **Packing list:** 1 × TSW101 Automotive PoE+ Switch [PP]. No PSU and no mounting kit.
- **Accessories you may need:** Teltonika DIN Rail Kit, RM49.00 (sold separately) [PP].
- **Resources:** Quick Start Guide (Wiki "TSW101 First Start"), User Manual (Wiki "TSW101 Manual"), datasheet PDF `710295-tsw101-datasheet-2023-v14.pdf` (returns 404 on 2026-10-21), flyer `tsw101-flyer-2023-v11.pdf` [PP].
- Use cases named: fire-truck communication, in-vehicle device power, parcel terminal [PP]. The page also promotes Teltonika RMS with a 30-day free trial; the TSW101 itself has no configuration (see *Software support*).

## Interfaces, terminals and pin mapping
| Interface | Detail | Src |
|---|---|---|
| ETH 1–4 | RJ45, 10/100/1000 Mbps, PoE+ out (802.3af/at, Alternative A, ≤30 W each) | [DS: web] |
| ETH 5 | RJ45, 10/100/1000 Mbps, no PoE (ports 1–4 are the PoE ports) | [DS: web] |
| Power | 1 × 2-pin industrial DC power socket, 9–30 VDC | [DS: web] |
| Ground | 1 × grounding screw | [DS: web] |
| LEDs | 1 × Power, 10 × ETH status (two per port, inferred from 10 LEDs / 5 ports) | [DS: web] |

Power socket pin numbering (which pin is + and which is −) is on the Wiki page "TSW101 Power Socket Pinout" / "TSW101 Manual", which could not be read. Check polarity against the label or the Wiki before wiring to a vehicle supply (see *Needs verification*).

## Rules and gotchas (for code, wiring and tutorials)
- **No configuration, no WebUI, no IP address.** It is a plug-and-play switch; do not write login or setup steps for it [DS: web].
- **PoE is "Alternative A"** [DS: web]. In IEEE 802.3af/at, Alternative A puts power on the data pairs (pins 1-2 / 3-6); compliant powered devices accept either alternative, while passive-PoE devices wired for the spare pairs will not be powered (general IEEE 802.3 fact, inferred; not stated by Teltonika).
- **60 W total.** Four ports at 30 W would need 120 W, so at most two devices can draw full PoE+ at once. Add up the PD loads before wiring [DS: web].
- **Port 5 has no PoE.** Use it for the uplink (router) [DS: web].
- **Input 9–30 VDC covers 12 V and 24 V vehicle systems**, and PoE output works over the same 9–30 V range (unlike the TSW202, which needs ≥44 V for PoE) [DS: web].
- **Any mounting needs a kit.** The Cytron page lists the Teltonika DIN Rail Kit as the accessory; Teltonika also lists a Compact DIN rail kit, DIN rail kit adapter, surface mounting kit and a "TSW1 rear panel with DIN rail holder" [DS: web][VEN][PP].
- **No PSU in the box.** For bench use Teltonika lists 18 W 2-pin PSUs, but 18 W cannot feed meaningful PoE loads (inferred from the 62.3 W PoE max consumption) [VEN][DS: web].

## Power and electrical limits
- Input 9–30 VDC via 2-pin industrial DC socket; PoE-out input range 9–30 VDC [DS: web].
- Consumption: idle 0.64 W, max 2.31 W (no PoE), PoE max 62.3 W [DS: web].
- PoE: ≤30 W per port at PSE, 60 W total at PSE, ports 1–4 [DS: web].
- Size the supply for about 63 W plus margin when all PoE is used (inferred from 62.3 W PoE max). At 12 V that is roughly 5.2 A (inferred).
- Environment: -40 to 75 °C, 5–95 % RH non-condensing, IP30 [DS: web].

## Software support
- No firmware, OS or management interface is listed in the specification; "No configuration needed" [DS: web]. It is not a TSWOS device (TSWOS is listed for the managed TSW202, not for the TSW101) [DS: web].
- Profinet Class A conformance only on order code `TSW101000001`; the standard code `TSW101000000` does not have it [VEN: ordering]. Which code Cytron sells is not stated (MPN shown as `TSW101`).
- RMS: the Cytron page says all Teltonika devices including the TSW101 come with a 30-day RMS trial [PP]. Not confirmed by Teltonika for an unmanaged switch (see *Needs verification*).

## Compatibility and accessories
- Teltonika-listed compatible accessories: AU / EU / UK / US 2-pin power supply 18 W, Compact DIN rail kit, DIN rail kit, DIN rail kit adapter, Ethernet cable 1.5 m, RJ45 dust covers, surface mounting kit, TSW1 rear panel with DIN rail holder [VEN].
- Teltonika DIN Rail Kit (PR5MEC00) lists the TSW101 as compatible; Cytron sells it at RM49.00 (see `teltonika-din-rail-kit.md`) [VEN][PP].
- Any 802.3af/at PoE device (IP cameras, access points) can be powered from ports 1–4 [DS: web].
- Pairs with Cytron-sold Teltonika routers (e.g. RUT956) as a LAN expander in vehicles (inferred; not a Teltonika statement).

## Common mistakes / troubleshooting
- **PoE device does not start:** check it is 802.3af/at (not passive PoE), that it is on ports 1–4, and that the 60 W budget is not exceeded [DS: web].
- **Looking for a WebUI or default IP:** there is none; it is plug-and-play [DS: web].
- **Expecting a DIN clip in the box:** the packing list is the switch only; buy a mounting kit [PP][DS: web].
- **Weak bench supply:** an 18 W adapter runs the switch but not PoE loads (inferred).
- **Cytron datasheet link dead:** use the Teltonika product page downloads tab (datasheet updated 2026-09-30) [VEN].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Mounting | [DS: web] DIN rail, wall, flat surface — "all require additional kit" | [PP] DIN rail, wall mount, flat surface (no kit note) | [DS: web] wins: every option needs a kit, sold separately |
| PoE alternative | [DS: web] 802.3af/at, Alternative A | [PP] 802.3af and 802.3at (no alternative given) | [DS: web] adds detail; no contradiction |
| Casing | [DS: web] anodised aluminium housing and panels | [PP] aluminium housing | Same material; use [DS: web] wording |
| Datasheet link | [PP] v1.4 PDF (2023) | [VEN] downloads tab: datasheet updated 2026-09-30; Cytron link returns 404 | Use the Teltonika page link |

## Needs verification
- Power socket pinout (pin 1 / pin 2 polarity) and LED meanings: Wiki "TSW101 Manual" / "TSW101 Power Socket Pinout" / "TSW101 LEDs" could not be opened (Cloudflare) [UM].
- Whether the Cytron unit is order code `TSW101000000` (no Profinet) or `TSW101000001` (Profinet Class A).
- Whether an unmanaged TSW101 can be used with RMS at all (the Cytron page implies an RMS trial).
- Reverse-polarity and surge protection of the power input (not stated on the spec page).
- Datasheet PDF content (version dated 2026-09-30) not opened.

## Sources
- [DS: web] Teltonika TSW101 product page, Features tab: https://teltonika-networks.com/products/ethernet-switches/tsw101 (redirect from /products/switches/tsw101), read 2026-10-21.
- [VEN] Same page: certifications, downloads (flyer updated 2024-03-19; datasheet updated 2026-09-30), ordering and compatible accessories tabs, read 2026-10-21.
- [UM] Teltonika Wiki (not readable on 2026-10-21, Cloudflare check): https://wiki.teltonika-networks.com/view/TSW101_Manual, https://wiki.teltonika-networks.com/view/TSW101_First_Start, https://wiki.teltonika-networks.com/view/TSW101
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-tsw101-automotive-poe-plus-switch, read 2026-10-21.
- [PP] Datasheet link on the Cytron page (404 on 2026-10-21): https://teltonika-networks.com/cdn/products/2023/01/63b81b2430ba72-44074551/datasheet/710295-tsw101-datasheet-2023-v14.pdf
