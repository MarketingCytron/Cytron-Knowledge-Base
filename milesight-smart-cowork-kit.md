# Milesight LoRaWAN Smart CoWork Kit (iBox CoWork Kit-A) — Verified Reference

| | |
|---|---|
| Product code | `LR-KIT-SC-A` (Cytron code) [PP]. Milesight name: **iBox CoWork Kit-A** (the kit datasheet and image Cytron links are Kit-A) [DS-kit][PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources) and Milesight iBox CoWork Kit-A datasheet (full text, 9 pages) and the Milesight CoWork kit page read. The iBox Quick Start Guide PDF is image-only (16 pages); only its cover and kit-overview pages were viewed |
| Primary source | **Cytron product page** for what Cytron sells (packing list) [PP]; *iBox CoWork Kit-A Datasheet*, Milesight, http://resource.milesight.com/milesight/iot/document/ibox-kit/cowork-kit-a-datesheet-en.pdf (no version/date printed) for kit-level component specs [DS-kit] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = https://my.cytron.io/Milesight/p-lorawan-smart-cowork-kit (read 2026-10-21). [DS-kit] = Milesight *iBox CoWork Kit-A Datasheet* (component summary sheets + platform pages; no version/date). [VEN] = Milesight kit page https://www.milesight.com/iot/product/lorawan-ibox-kit/cowork-smart-office-kit (also shows a different Kit-B). [UM-kit] = Milesight iBox *Quick Start Guide* PDF (image-only, not read beyond the cover and overview).

**Kit rule:** the components are **not** re-documented here — see `milesight-ug56.md` (gateway) and `milesight-vs121.md` (AI workplace occupancy sensor). VS340 and DS3604 have **no KB file** (not sold separately by Cytron in this KB). Only kit-level facts are stated.

## What it is

## Specifications
Kit-level rows only. Component specs: see the component files listed in the Kit rule.

| Item | Value | Src |
|---|---|---|
| Product name (Cytron) | LoraWAN Smart CoWork Kit | [PP] |
| Milesight kit name | iBox CoWork Kit-A | [DS-kit][PP] |
| Code | LR-KIT-SC-A | [PP] |
| Price / availability | RM4,714.00; "Enquiry" (2026-10-21) | [PP] |
| Warranty | 12 months | [PP] |
| Frequency plan of the kit | **Not stated** on the Cytron kit page; [DS-kit] lists CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 for each model | [PP][DS-kit] |
| Platform included | 6 months (Pro1) Milesight IoT Cloud | [PP] |
| Setup / installation service | **None stated** | [PP] |

**Components (exactly as the Cytron packing list states)** [PP]
| # | Cytron packing-list line | Quantity stated | KB file |
|---|---|---|---|
| — | 1 x LoraWAN Smart CoWork Kit (parent line) | 1 kit | this file |
| 1 | UG56 Industrial LoRaWAN® Gateway (without cellular) | not stated per item | `milesight-ug56.md` |
| 2 | VS121 LoRaWAN AI Workplace Occupancy Sensor | not stated per item | `milesight-vs121.md` |
| 3 | VS340 Desk & Seat Occupancy Sensor | not stated per item | **not in KB** (VS340) |
| 4 | DS3604 IoT E-Ink Display | not stated per item | **not in KB** (DS3604) |
| 5 | 6 months (Pro1) Milesight IoT Cloud | 6-month subscription | — (software) |
| 6 | Quick Start Guide | not stated | — |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "LoraWAN Smart CoWork Kit"; brand Milesight; Code `LR-KIT-SC-A`; no MPN shown; warranty 12 months; RM4,714.00; availability "Enquiry" with INQUIRE NOW; no variant selector [PP].
- Description: D2D "communication between devices in just 1 second"; VS121 (up to 98 % recognition; LoRaWAN or Ethernet versions — the Ethernet one is VS121-P); DS3604 (4.2-inch, 400 × 300, black/white/red, up to 5-year battery); VS34x (VS340 PIR, VS341 PIR + thermopile); UG56 (8-channel, SX1302, > 2000 nodes, 15 km LoS / ~2 km urban, Ethernet/Wi-Fi/cellular backhaul, embedded network server and Milesight Development Platform); 6 scenario modes (e.g. "working" to "have a break") controlling curtain, light, window, door or PC [PP].
- Features: hands-on IoT experience; integrates with multiple network-server platforms; **BACnet/IP** from the gateway for BMS integration [PP].
- Spec block: VS121 "Up to 95% Accuracy", 16 detection regions; DS3604 4.2-inch, three-pigment ink, open API, multicast, 5-year battery; desk sensor "Up to 98% Accuracy", D2D, 5-year battery; UG56 industrial-grade, gateway fleet, LBT, free embedded NS, BACnet [PP].
- Resources: iBox CoWork Kit-A Datasheet, Quick Start Guide, Collection Overview (image), Milesight IoT Cloud (image) — all on resource.milesight.com [PP].

## Interfaces, terminals and pin mapping
Kit level: none. The only wired item is the gateway (Ethernet PoE PD or USB-C 5 V 2 A per [DS-kit]); VS121 needs 5 V / 1.5 A over USB-C [DS-kit]; VS340 and DS3604 are battery devices [DS-kit]. See component files.

## Rules and gotchas (for code, wiring and tutorials)
- **This is Kit-A.** Milesight also sells a different CoWork **Kit-B** (VS121, WS101, WS301, WS156, UC100, UG56); do not mix the two lists [VEN][DS-kit].
- **Quantities are not stated** per component on the Cytron page or in [DS-kit]; say "includes" rather than giving counts until confirmed.
- **Gateway is the no-cellular UG56** — backhaul is Ethernet or Wi-Fi [PP].
- **VS121 in the kit is the LoRaWAN version** (the datasheet sheet: LoRaWAN + D2D, Class C, 5 VDC 1.5 A USB-C), not the Ethernet VS121-P [DS-kit].
- **Frequency plan:** not stated for the kit; confirm with Cytron (Malaysia normally uses AS923) before quoting.
- **Cloud is time-limited:** 6 months of Milesight IoT Cloud Pro1; after that a paid licence or another network server/platform is needed (inferred from "6 months") [PP].
- Accuracy figures differ by source (95 % vs 98 %); quote with the counting mode (see Conflicts).

## Power and electrical limits
Kit level: not stated. From [DS-kit]: UG56 802.3af PoE or 5 V 2 A USB-C; VS121 5 V 1.5 A USB-C; VS340 1 × 4000 mAh ER18505 (~5 years at 100 triggers/day); DS3604 battery (~5 years Class A, 1 refresh/day; ~1 year Class B, 12 refreshes/day). No power supplies are listed in the packing list [PP].

## Software support
- **Milesight IoT Cloud — 6 months, Pro1 plan included** [PP]. [DS-kit]: drag-and-drop dashboard widgets for real-time and historical data, remote project access, email and mobile push notifications on triggers, built on AWS, licence activation by copy-and-paste. Milesight's kit page: custom conditions and triggers, daily/weekly/monthly report export, full-screen dashboards [VEN].
- **Milesight Development Platform** (described in [DS-kit] and [PP] description): open API and webhooks, central management of devices, applications and projects, remote access and OTA. Milesight lists a free plan (limited devices) and a paid professional plan — pricing is on Milesight's site (not copied); whether any plan is included with the kit is **not stated** [DS-kit].
- **UG56 embedded network server**, compatibility with TTN, ChirpStack, Everynet, Senet, and BACnet/IP for BMS [DS-kit].
- **Milesight D2D** between kit devices (< 1 s in the same room) for scene switching [DS-kit][PP].
- Setup service: none stated [PP].

## Compatibility and accessories
- Extra sensors on the same frequency plan can join the UG56 (see LoRaWAN files in the KB).
- Gateway antenna upgrade: `milesight-ga01.md` (fibre-glass antenna kit for UG56) [VEN].

## Common mistakes / troubleshooting
- No kit-specific troubleshooting is published in the text sources read; the iBox Quick Start Guide is image-only.
- Devices do not join → check that all devices and the UG56 use the same frequency plan, and that OTAA is used for Milesight IoT Cloud (see component files).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| VS340 link on Cytron packing list | Text "VS340 Desk & Seat Occupancy Sensor" | Link target is the Milesight **UG56** page | Cytron page error — fix the link |
| VS121 accuracy | [PP] description "up to 98% recognition rate"; [PP] spec "Up to 95% Accuracy" | [DS-kit] region counting up to 95 %, line crossing and people-flow up to 98 % | [DS-kit]: depends on counting mode |
| Desk sensor accuracy | [PP] spec "Up to 98% Accuracy" | [DS-kit] VS340 recognition rate up to 95 % (headline feature "Up to 98%") | [DS-kit] table: up to 95 %; flag the marketing figure |
| Product description name | [PP] "iBox CoWork Kit" | [PP] code `-A`, [DS-kit] "Kit-A" | It is Kit-A |
| Frequency plan | [PP] none stated | [DS-kit] all plans per model | Ask Cytron |

## Needs verification
- Quantity of each component (Cytron lists items without counts).
- LoRaWAN frequency plan of the kit Cytron supplies (AS923-2 expected for Malaysia; not stated).
- Exact Milesight IoT Cloud "Pro1" plan limits, start date of the 6 months and renewal cost.
- Whether power adapters are included for the UG56 and VS121.
- Whether Cytron offers any setup or onboarding service for the kit (none stated).
- Contents of the iBox Quick Start Guide (image-only PDF).

## Sources
- [PP] https://my.cytron.io/Milesight/p-lorawan-smart-cowork-kit — read 2026-10-21
- [DS-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/cowork-kit-a-datesheet-en.pdf — read in full (text) 2026-10-21
- [VEN] https://www.milesight.com/iot/product/lorawan-ibox-kit/cowork-smart-office-kit — read 2026-10-21
- [UM-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/quick-start-guide-en.pdf — image-only, not read
- Cytron-linked images (not read): colleciton-overview-en.jpg, milesight-iot-cloud-en.jpg on resource.milesight.com
