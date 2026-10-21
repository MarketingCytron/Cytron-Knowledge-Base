# Teltonika DIN Rail Kit — Verified Reference

| | |
|---|---|
| Product code | `PR5MEC00` (Teltonika order code; Cytron MPN). Cytron code `HD-BK-DIN-TL` [PP][VEN] |
| Family | Industrial networking (Teltonika) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, stock, features, compatibility list, packing list) and the Teltonika accessory page (technical data, full compatible-products list, downloads and ordering tabs) read. Teltonika datasheet PDF not opened (file host not approved in the browser) |
| Primary source | Teltonika Networks "DIN RAIL KIT" accessory page, technical data, https://teltonika-networks.com/products/accessories/mounting-options/din-rail-kit (read 2026-10-21) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet / technical specification [DS] > manufacturer user manual (Teltonika Wiki) [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the "Technical data" block on the Teltonika accessory page (the linked datasheet PDF was not opened). [VEN] = the compatible-products list, downloads and ordering tabs on the same page. [PP] = Cytron product page. No Wiki page is needed for this mechanical accessory, and the Wiki was not reachable on 2026-10-21 (Cloudflare check).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Mounting type | 35 mm DIN rail | [DS: web] |
| Material | Low carbon steel | [DS: web] |
| Dimensions | 65.2 × 44.2 × 1.5 mm | [DS: web] |
| Screws included | Philips pan head screw #6-32 × 3/16, 2 pcs | [DS: web] |
| Weight | 57 g | [DS: web] |
| RoHS | Compliant | [DS: web] |
| Order code / HS / HTS | PR5MEC00 / 830249 / 8302.49.00 | [VEN: ordering] |
| Downloads | DIN rail kit 3D models (updated 2024-06-17); datasheet PDF link on the page | [VEN] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Teltonika DIN Rail Kit"; Brand Teltonika; Code HD-BK-DIN-TL; MPN PR5MEC00; RM49.00 (cashback RM1.47); availability 2; no warranty line shown [PP].
- Features: 35 mm DIN rail; low carbon steel; Philips pan head screw #6-32 × 3/16 (2 pcs); dimensions 82 mm × 46 mm × 20 mm; RoHS yes; 57 g [PP].
- Compatible list on the Cytron page: RUT200, RUT901, RUT906, RUT956, RUTM51, RUTX50, TSW202, TSW101 [PP].
- **Packing list:** 1 × DIN rail mounting, 1 × set of screws [PP].
- No resources/datasheet link on the Cytron page [PP]. Cytron offers it as "Accessories you may need" on the TSW101 and TSW202 pages [PP].

## Interfaces, terminals and pin mapping
No electrical interface. Mechanical only: the bracket fixes to the device with the two #6-32 × 3/16 pan head screws and clips onto a 35 mm DIN rail [DS: web]. The hole positions per device are not stated on the page (see *Needs verification*).

## Rules and gotchas (for code, wiring and tutorials)
- **Check the device is on Teltonika's compatible list** (below) before recommending the kit. Teltonika lists separate kits for some models (Compact DIN rail kit, DIN rail kit adapter, TSW1 rear panel with DIN rail holder) [VEN].
- **The TSW202 does not need it:** it has an integrated DIN rail bracket, and Teltonika's list does not include the TSW202 [DS: web of TSW202][VEN].
- **35 mm rail only** (standard top-hat rail) [DS: web].
- Screws are imperial #6-32; do not replace them with longer screws that could reach inside the device (caution, inferred).

## Power and electrical limits
Not applicable: passive steel bracket, no electrical rating [DS: web].

## Software support
Not applicable.

## Compatibility and accessories
**Teltonika compatible-products list (read 2026-10-21) [VEN]:** NTP001, RUT200, RUT202, RUT204, RUT206, RUT241, RUT260, RUT261, RUT271, RUT276, RUT286, RUT301, RUT361, RUT901, RUT906, RUT951, RUT951 PoE+, RUT956, RUT976, RUT981, RUT986, RUTC16, RUTC40, RUTC41, RUTC42, RUTC50, RUTC54, RUTM08, RUTM09, RUTM10, RUTM11, RUTM16, RUTM20, RUTM30, RUTM50, RUTM50 JAPAN, RUTM51, RUTM52, RUTM54, RUTM55, RUTM56, RUTM59, RUTX08, RUTX09, RUTX10, RUTX11, RUTX12, RUTX14, RUTX50, TRB140, TRB141, TRB142, TRB143, TRB145, TRB160, TRB236, TRB246, TRB247, TRB256, TRB501, TRM142, TRM200, TRM240, TRM250, TRM282, TRM500, TSW100, TSW101, TSW110.

**Cytron-sold Teltonika models vs Teltonika's list [VEN]:**
| Model | Stated to fit? |
|---|---|
| RUT200 | Yes |
| RUT140 | Not listed |
| RUT901 | Yes |
| RUT906 | Yes |
| RUT956 | Yes |
| RUTX50 | Yes |
| OTD140 | Not listed |
| TRB140 | Yes |
| TSW101 | Yes |
| TSW202 | Not listed (has integrated DIN bracket) |

- Teltonika lists the BAT120 uninterruptible power supply as a compatible accessory of this kit [VEN].

## Common mistakes / troubleshooting
- **Ordering the kit for a TSW202:** not needed; the bracket is built in [DS: web of TSW202].
- **Ordering it for RUT140 or OTD140:** neither is on Teltonika's list; check the device's own accessories page [VEN].
- **Wrong rail:** fits 35 mm DIN rail only [DS: web].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Dimensions | [DS: web] 65.2 × 44.2 × 1.5 mm | [PP] 82 × 46 × 20 mm | [DS: web] wins (the Cytron figure may include the clip or packaging; unconfirmed) |
| TSW202 compatibility | [VEN] not on the list; TSW202 has an integrated DIN bracket | [PP] TSW202 listed as compatible | Teltonika wins: not stated to fit |
| Compatible list length | [VEN] 69 models | [PP] 8 models | Not a contradiction except TSW202; use the Teltonika list |

## Needs verification
- Whether the kit physically fits the TSW202 at all (Cytron says yes, Teltonika does not list it).
- Warranty (not shown on the Cytron page).
- Datasheet PDF content (not opened): https://www.teltonika-networks.com/_files/ugd/814ec4_5f8ef6796a14494fb0042497a19178b1.pdf
- Origin of Cytron's 82 × 46 × 20 mm dimension.

## Sources
- [DS: web] / [VEN] Teltonika DIN RAIL KIT page: https://teltonika-networks.com/products/accessories/mounting-options/din-rail-kit, read 2026-10-21.
- [VEN] Teltonika datasheet PDF link (not opened): https://www.teltonika-networks.com/_files/ugd/814ec4_5f8ef6796a14494fb0042497a19178b1.pdf
- [VEN] Teltonika TSW202 product page (integrated DIN rail bracket): https://teltonika-networks.com/products/ethernet-switches/tsw202
- [PP] Cytron product page: https://my.cytron.io/m-teltonika/p-teltonika-dinrail-kit, read 2026-10-21.
