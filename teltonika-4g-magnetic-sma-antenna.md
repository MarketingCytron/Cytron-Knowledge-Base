# Teltonika 4G Mobile Magnetic SMA Antenna — Verified Reference

| | |
|---|---|
| Product code | `PR1KS210` (Teltonika order code; Cytron MPN). Cytron code `ANT-4G-MGN` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, description, specifications, packing list, resources) and the Teltonika accessory page "Mobile Magnetic SMA Antenna" (technical data, full compatible-products list, downloads and ordering tabs) read. Teltonika datasheet PDF not opened (file host not approved in the browser) |
| Primary source | Teltonika Networks "MOBILE MAGNETIC SMA ANTENNA" accessory page, technical data, https://teltonika-networks.com/products/accessories/antenna-options/mobile-magnetic-sma-antenna (read 2026-10-21) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the technical data block on the Teltonika accessory page (the linked datasheet PDF was not opened). [VEN] = the compatible-products list, downloads and ordering tabs on the same page. [PP] = Cytron product page. Teltonika names the item "Mobile Magnetic SMA Antenna"; "4G" is Cytron's title wording. No Wiki page was needed; the Wiki was not reachable on 2026-10-21 (Cloudflare check).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Frequency range | 699 ~ 868 MHz, 1850 ~ 2690 MHz | [DS: web] |
| Polarisation | Linear | [DS: web] |
| Gain | 1.0 dBi | [DS: web] |
| VSWR | 3.0 | [DS: web] |
| Impedance | 50 Ω | [DS: web] |
| Cable | RG174, 3000 mm | [DS: web] |
| Connector | SMA male | [DS: web] |
| Mounting | Magnet | [DS: web] |
| IP rating | IP40 | [DS: web] |
| RoHS | Compliant | [DS: web] |
| Order code / HS / HTS | PR1KS210 / 851771 / 8517.71.00 | [VEN: ordering] |
| Downloads | Mobile Magnetic SMA Antenna 3D models (updated 2024-05-09); datasheet PDF link | [VEN] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Teltonika 4G Mobile Magnetic SMA Antenna"; Brand Teltonika; Code ANT-4G-MGN; MPN PR1KS210; RM65.00 (cashback RM1.95); availability 4; no warranty line shown [PP].
- Specifications match [DS: web]: 699 ~ 868, 1850 ~ 2690 MHz; linear; 1.0 dBi; VSWR 3.0; 50 Ω; RG174 3 m; SMA male; magnet; RoHS [PP].
- Key-features text says "698-868 MHz" and "-40°C to +85°C" operating temperature; IP40 is not mentioned [PP] (see *Conflicts*).
- Says it "is compatible with a wide range of Teltonika 4G routers, gateways, and modems" but lists no models [PP].
- **Packing list:** 1 × antenna with cable [PP].
- **Resources:** datasheet (Google Drive copy) [PP].

## Interfaces, terminals and pin mapping
| Item | Detail | Src |
|---|---|---|
| RF connector | SMA male plug on the end of a 3 m RG174 cable | [DS: web] |
| Mating connector | SMA female (the mobile antenna sockets on Teltonika routers; inferred from SMA male plug) | inferred |

One antenna = one RF port. On routers with two mobile antenna ports (MAIN and AUX/diversity), one PR1KS210 serves one port only; two are needed for MIMO/diversity on external antennas (inferred).

## Rules and gotchas (for code, wiring and tutorials)
- **Band coverage (inferred from the frequency range):** covers LTE 700 (B28), 800 (B20), 2100 (B1), 2600 (B7) and TDD 2300/2600 (B40/B38/B41). It does **not** cover 900 MHz (B8, 880–960 MHz) and only part of 1800 MHz (B3 downlink 1805–1880 MHz; uplink 1710–1785 MHz is outside). Check the local operator's bands before recommending it (inferred; not a Teltonika statement).
- **Connect to the mobile (LTE) port, not Wi-Fi or GNSS.** Teltonika routers label antenna ports; this is a mobile antenna [DS: web].
- **Magnetic base needs a ferrous metal surface** (vehicle roof, cabinet top) [DS: web: "Mounting method Magnet"; surface note inferred].
- **IP40:** indoor or sheltered use; not rated for rain [DS: web].
- **3 m RG174 adds cable loss** at 2.6 GHz; do not add extension cables needlessly (inferred).
- Tighten SMA connectors by hand; do not over-torque (general practice, inferred).

## Power and electrical limits
- Passive antenna: 50 Ω, VSWR 3.0, 1.0 dBi gain; no power rating stated [DS: web].
- Operating temperature -40 to +85 °C is stated only by Cytron [PP] (see *Needs verification*).

## Software support
Not applicable. On the router, Teltonika devices show signal strength (RSSI/RSRP/SINR) in their WebUI, which helps when placing the antenna (general RutOS feature, inferred; not read for this file).

## Compatibility and accessories
**Teltonika compatible-products list (read 2026-10-21, 42 models) [VEN]:** Calyx, Oxa, RUT200, RUT202, RUT204, RUT206, RUT241, RUT260, RUT261, RUT281, RUT286, RUT361, RUT901, RUT906, RUT951, RUT951 PoE+, RUT956, RUTC16, RUTC40, RUTC41, RUTC42, RUTM09, RUTM11, RUTX09, RUTX11, RUTX12, RUTX14, RUTXR1, TRB140, TRB141, TRB142, TRB143, TRB145, TRB160, TRB246, TRB247, TRB256, TRM142, TRM200, TRM240, TRM250, TRM282.

**Cytron-sold Teltonika models vs Teltonika's list [VEN]:**
| Model | Stated to fit? |
|---|---|
| RUT200 | Yes |
| RUT140 | Not listed |
| RUT901 | Yes |
| RUT906 | Yes |
| RUT956 | Yes |
| RUTX50 | Not listed (5G router; Teltonika sells 5G antennas for it) |
| OTD140 | Not listed |
| TRB140 | Yes |
| TSW101 | Not applicable (Ethernet switch, no cellular) |
| TSW202 | Not applicable (Ethernet switch, no cellular) |

- Teltonika also sells an "SMA cable extension" (PR2VM20M) and 5G/combo roof antennas for other models [VEN].

## Common mistakes / troubleshooting
- **Weak signal on 900 MHz or 1800 MHz networks:** outside or at the edge of the stated range (inferred); try another antenna or band.
- **Antenna on the Wi-Fi or GNSS connector:** move it to the mobile port [DS: web].
- **Magnet does not hold:** surface is not ferrous (inferred).
- **Ordered for RUTX50 / RUT140 / OTD140:** not on Teltonika's compatible list [VEN].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Lower frequency limit | [DS: web] 699 MHz | [PP] features "698-868 MHz"; spec list "699 ~ 868" | [DS: web] wins: 699–868 MHz |
| IP rating | [DS: web] IP40 | [PP] not stated | [DS: web] |
| Operating temperature | [DS: web] not stated | [PP] -40 °C to +85 °C | Cytron-only; kept in *Needs verification* |
| Product name | [DS: web] "Mobile Magnetic SMA Antenna" | [PP] "4G Mobile Magnetic SMA Antenna" | Same item (order code PR1KS210 matches) |

## Needs verification
- Operating temperature -40 to +85 °C (Cytron only; check the datasheet PDF).
- Datasheet PDF content (not opened): https://www.teltonika-networks.com/_files/ugd/063d09_25a196f2d45f43999b4530ca50d5c57d.pdf
- Real performance on LTE B3 (1800 MHz) and B8 (900 MHz), which fall partly or wholly outside the stated range; check against the bands the target operator uses (inferred concern).
- Warranty (not shown on the Cytron page).
- Whether the RUT140 and OTD140 have external SMA mobile connectors at all.

## Sources
- [DS: web] / [VEN] Teltonika "Mobile Magnetic SMA Antenna" page: https://teltonika-networks.com/products/accessories/antenna-options/mobile-magnetic-sma-antenna, read 2026-10-21.
- [VEN] Teltonika antenna options list: https://teltonika-networks.com/products/accessories/antenna-options
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-teltonika-4g-mobile-magnetic-sma-antenna, read 2026-10-21.
- [PP] Cytron datasheet copy (not opened): (Cytron document — link not public)
