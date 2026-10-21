# Milesight GA01 60 cm Fiber-Glass S-N Antenna Kit — Verified Reference

| | |
|---|---|
| Product code | `FSN600` (Milesight P/N, "GA01 60cm LoRaWAN® Fiber-Glass S-N Antenna Kit"). Cytron code `LR-GA01-FSN600`, MPN `FSN600` [PP][DS: web] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, code, MPN, stock, spec, packing list), Milesight Optional Accessories Guide page and UG56 page accessories section (GA01 variants), UG56 Quick Guide V1.5 antenna-installation section. Milesight publishes no datasheet or user guide for GA01 |
| Primary source | Milesight *Optional Accessories Guide*, GA01 entries, https://www.milesight.com/iot/product/accessories/ (read 2026-10-21) [DS: web] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS: web] = the GA01 specification entries on Milesight's accessories guide page and in the UG56 product page's accessories section (identical text). No GA01 datasheet PDF exists. [UM] = *UG56 Quick Guide* V1.5 (24 Dec 2025), antenna installation section. [PP] = Cytron product page.

## What it is
"S-N" means the cable runs from an SMA connector (gateway side) to an N connector (antenna side). Milesight's GA01 range also includes a 130 cm S-N kit (FSN1300, UG56) and N-N kits (FNN600 for UG65, FNN1300 for UG65/UG67) [DS: web].

## Specifications
| Item | Value | Src |
|---|---|---|
| P/N | FSN600 | [DS: web][PP] |
| Antenna height | 600 mm | [DS: web] |
| Type | Omnidirectional | [DS: web] |
| Gain | 863–870 MHz: 4–5 dBi; 902–928 MHz: 4–5 dBi | [DS: web] |
| Antenna interface | N-J (N-type male) | [DS: web] |
| RF cable interface | SMA-J-N-K (SMA male to N female) | [DS: web] |
| Cable length | 1 m | [DS: web] |
| Colour | White antenna, black cable | [DS: web] |
| Applicable products | UG56 | [DS: web] |
| Cytron frequency plan statement | "Support Malaysia AS923-2, Singapore AS923-1"; lists only the 902–928 MHz gain | [PP] |
| Packing (Cytron) | 1 × fiberglass antenna, 1 × RF coaxial extension cable, 1 × mounting bracket kit | [PP] |
| Supply / IP rating / weight | [NOT STATED] | — |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "GA01 LoRaWAN Fiber Glass S-N Antenna Kit (for Milesight UG56)"; brand Milesight; Code `LR-GA01-FSN600`; MPN `FSN600`; warranty 12 months; RM215.25; "Availability: Enquiry", button INQUIRE NOW [PP].
- Description: 60 cm fiberglass kit for UG56; 360° omnidirectional; 4–5 dBi; N-type male (N-J) antenna connector; 1 m coaxial cable SMA male to N female; "weather-resistant" fiberglass for outdoor or indoor use [PP].
- Spec list matches [DS: web] for P/N, height, type, gain at 902–928 MHz, colour, interfaces, cable length and applicable model [PP].
- **Packing list:** 1 × fiberglass antenna, 1 × RF coaxial extension cable, 1 × mounting bracket kit [PP].
- No resources (datasheet) are linked [PP].

## Interfaces, terminals and pin mapping
| End | Connector | Mates with | Src |
|---|---|---|---|
| Antenna base | N-J (N male) | N-K end of the cable | [DS: web] |
| Cable, antenna side | N-K (N female) | Antenna N-J | [DS: web] |
| Cable, gateway side | SMA-J (SMA male) | UG56 LoRa connector: 50 Ω SMA, female centre pin | [DS: web][DS of UG56] |

## Rules and gotchas (for code, wiring and tutorials)
- **For UG56 only.** UG65 and UG67 have N-Female LoRa connectors and need the N-N GA01 kits (FNN600/FNN1300), not this S-N kit [DS: web].
- **Band:** gain is specified for 863–870 MHz and 902–928 MHz; AS923 (around 920–925 MHz) falls inside the 902–928 MHz range (inferred). Use it with Cytron's 915 MHz-band UG56 [PP].
- **Mounting** (UG56 quick guide): pass the fiber-glass antenna through the antenna clamp, fix it with 4 screws, wrap the U-bolt round the pole and fix the clamp with nuts; install vertically, high up, away from walls and obstacles, at least 50 cm from other antennas [UM].
- **Outdoors:** the UG56 itself is IP30 and must stay indoors or in an enclosure; only the antenna goes outside (inferred from the UG56 IP rating). Weather-seal the N connector with tape as Milesight shows for UG67 (see `milesight-ug67.md`; inferred to apply).
- Every extra metre of coax adds loss; the kit's 1 m cable is the intended length (inferred).

## Power and electrical limits
- Passive antenna; no power needed. Maximum input power is [NOT STATED]; the UG56 transmits at most 27 dBm [DS of UG56].

## Software support
- None needed. After fitting an external antenna on a gateway, check the antenna settings in the gateway's packet-forwarder radio page if present (UG65 has an antenna-type setting; UG56 has a single SMA connector) [UM of UG65/UG56].

## Compatibility and accessories
- Gateway: `milesight-ug56.md` (SMA LoRa connector) [DS: web][PP].
- Not for `milesight-ug65.md` or `milesight-ug67.md` (N-Female connectors) — use the N-N GA01 kits from Milesight [DS: web].
- Cytron's UG65 page recommends this kit under "You May Also Need"; see *Conflicts*.

## Common mistakes / troubleshooting
- **Ordering this kit for a UG65/UG67:** the SMA-male cable end will not fit their N-Female connectors [DS: web].
- **Poor range after fitting:** mount the antenna vertically and higher, away from walls and metal; check the coax connectors are tight [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Gain bands | [DS: web] 863–870 MHz and 902–928 MHz, 4–5 dBi | [PP] 902–928 MHz only | Both bands per Milesight; Cytron lists the band it sells |
| Suitable gateway | [DS: web] UG56 only | [PP] UG65 page lists this kit under "You May Also Need" | [DS: web] wins: UG56; UG65/UG67 need N-N kits |
| Stock | Brand listing card: OUT OF STOCK | [PP] product page: "Availability: Enquiry" | Page used: enquiry only |

## Needs verification
- Mounting bracket kit contents and supported pole diameter.
- Maximum power rating, VSWR, impedance (50 Ω inferred from the gateway connector) and ingress rating of the antenna.
- Whether Cytron will restock or only supply on enquiry.

## Sources
- [DS: web] Milesight Optional Accessories Guide: https://www.milesight.com/iot/product/accessories/ (GA01 entries; read 2026-10-21). Same entries on https://www.milesight.com/iot/product/lorawan-gateway/ug56 (accessories).
- [UM] UG56 Quick Guide V1.5: https://resource.milesight.com/milesight/iot/document/ug56-quick-guide-en.pdf (antenna installation).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ga01-lorawan-fiber-glass-s-n-antenna-kit-for-milesight-ug56 (read 2026-10-21).
