# Milesight LoRaWAN Smart Agriculture Kit (iBox Smart Agriculture Kit) — Verified Reference

| | |
|---|---|
| Product code | `LR-KIT-SA` (Cytron code) [PP]. Milesight name: **iBox Smart Agriculture Kit** [PP][DS-kit] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight *iBox Smart Agriculture Kit Datasheet* (full text, 8 pages) and Milesight Smart Agriculture Kit page read. iBox Quick Start Guide is image-only (not read) |
| Primary source | **Cytron product page** for what Cytron sells (packing list) [PP]; *iBox Smart Agriculture Kit Datasheet*, Milesight, http://resource.milesight.com/milesight/iot/document/ibox-kit/agriculture-kit-datesheet-en.pdf (no version/date printed) [DS-kit] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = https://my.cytron.io/Milesight/p-lorawan-smart-agriculture-kit (read 2026-10-21). [DS-kit] = Milesight *iBox Smart Agriculture Kit Datasheet* (component sheets + platform pages; no version/date). [VEN] = https://www.milesight.com/iot/product/lorawan-ibox-kit/agriculture-kit. [UM-kit] = iBox *Quick Start Guide* PDF (image-only, not read).

**Kit rule:** the components are **not** re-documented here — see `milesight-em500-smtc.md` (soil sensor) and `milesight-ug56.md` (gateway). **UC511 has no KB file**: it is a different model from the UC512 in `milesight-uc512.md` — do not substitute UC512 facts. Only kit-level facts are stated.

## What it is

## Specifications
Kit-level rows only. Component specs: see the files in the Kit rule.

| Item | Value | Src |
|---|---|---|
| Product name (Cytron) | LoRaWAN Smart Agriculture Kit | [PP] |
| Milesight kit name | iBox Smart Agriculture Kit | [PP][DS-kit] |
| Code | LR-KIT-SA | [PP] |
| Price / availability | RM5,166.00; "Enquiry" (2026-10-21) | [PP] |
| Warranty | 12 months | [PP] |
| Frequency plan of the kit | **Not stated** on the Cytron page; [DS-kit] lists CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 per model | [PP][DS-kit] |
| Platform included | 6 months (Pro1) Milesight IoT Cloud | [PP] |
| Setup / installation service | **None stated** | [PP] |

**Components (exactly as the Cytron packing list states)** [PP]
| # | Cytron packing-list line | Quantity stated | KB file |
|---|---|---|---|
| — | 1 x LoRaWAN Smart Agriculture Kit (parent line) | 1 kit | this file |
| 1 | EM500-SMTC LoRaWAN Soil Moisture, Temperature and EC Sensor | not stated per item | `milesight-em500-smtc.md` |
| 2 | UG56 Industrial LoRaWAN® Gateway (without cellular) | not stated per item | `milesight-ug56.md` |
| 3 | UC511 LoRaWAN® Solenoid Valve Controller | not stated per item | **not in KB** (UC511; ≠ UC512) |
| 4 | 6 months (Pro1) Milesight IoT Cloud | 6-month subscription | — (software) |
| 5 | Quick Start Guide | not stated | — |

**UC511 kit-level summary** (no KB file; from [DS-kit] only): LoRaWAN solenoid valve controller; Class A/B/C/C-to-B; 2 × solenoid interfaces 5/9/12 VDC switchable for **DC latching** valves; 2 × GPIO (digital input / pulse counter) for pulse water meters; M12 A-coded male connectors; power from solar (6 V, 1.7 W) with 2 rechargeable batteries, or 5–24 VDC on the external-antenna (EA) version only; internal antenna (EA version: SMA female); NFC and USB-C configuration; IP67; -20 to +60 °C; 116 × 116 × 45.5 mm; wall or pole mounting [DS-kit]. Which UC511 version is in Cytron's kit is not stated.

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "LoRaWAN Smart Agriculture Kit"; brand Milesight; Code `LR-KIT-SA`; no MPN; warranty 12 months; RM5,166.00; availability "Enquiry" (INQUIRE NOW) [PP].
- Description: UG56 at the heart; Milesight IoT Cloud for visualisation, alerts and automated control; UC511 solar-powered for irrigation based on soil conditions or schedules; EM500-SMTC IP67 soil sensor [PP].
- Features: monitoring of soil moisture, temperature, EC **"and light intensity"**; automated irrigation; IoT Cloud dashboards and analytics; industrial gateway; plug-and-play [PP].
- Spec block: UG56 (LBT, free embedded NS, BACnet); EM500-SMTC (research-grade accuracy, IP67, NFC, replaceable battery up to 10 years); UC511 (two DC latching valve outputs, two pulse meter inputs, solar + rechargeable battery, IP67 UV-resistant); Milesight IoT Cloud (free for a limited time, triggers, daily/weekly/monthly reports, drag-and-drop dashboard); **Milesight Development Platform** (open API, webhooks, central management, OTA) [PP].
- Resources: iBox Kit Datasheet, Quick Start Guide, Collection Overview (image), Milesight IoT Cloud (image) [PP].

## Interfaces, terminals and pin mapping
Kit level: none beyond the components. User-supplied DC latching solenoid valves and pulse water meters connect to the UC511's M12 connectors [DS-kit]; the EM500-SMTC probe is on a 2 m cable [DS-kit]. See component files; UC511 pinouts are not in the KB.

## Rules and gotchas (for code, wiring and tutorials)
- **UC511 drives DC latching solenoid valves only** (5/9/12 VDC selectable); not AC valves or standard (non-latching) solenoids per the kit sheet [DS-kit].
- **No valves, water meters, pipes or mounting poles are in the packing list** [PP].
- **UC511 ≠ UC512.** The KB's `milesight-uc512.md` is a different Cytron listing; do not mix specs.
- **No light sensor in the kit.** Cytron's feature line mentions "light intensity", but none of the three devices measures light [PP][DS-kit].
- **Gateway is indoor (IP30)** UG56 without cellular — it needs Ethernet or Wi-Fi backhaul and an indoor or enclosed location; field devices must be within LoRaWAN range [DS-kit][PP].
- **Frequency plan and quantities not stated** — confirm with Cytron.
- **Cloud is time-limited** (6 months Pro1) [PP].

## Power and electrical limits
Kit level: not stated. From [DS-kit]: EM500-SMTC built-in 19000 mAh battery (up to 10 years); UC511 solar 6 V 1.7 W + 2 rechargeable batteries (5–24 VDC only on the EA version); UG56 802.3af PoE or 5 V 2 A USB-C. No gateway power adapter is listed [PP].

## Software support
- **Milesight IoT Cloud — 6 months, Pro1 plan included** [PP]: custom conditions and triggers, daily/weekly/monthly report export, drag-and-drop dashboards, full-screen mode [PP][VEN].
- **Milesight Development Platform**: open API and webhooks, central management, plug-and-play Milesight device deployment, remote access and OTA [PP]. Whether a paid plan is included: **not stated**.
- **UG56 embedded network server**, BACnet/IP [DS-kit].
- Irrigation automation on time or flow (UC511 pulse counting) [VEN].
- Setup service: none stated [PP].

## Compatibility and accessories
- Other Milesight LoRaWAN field sensors on the same plan (e.g. weather station `milesight-wts506.md`) can join the gateway.
- Outdoor gateway alternative: `milesight-ug67.md`. UG56 antenna kit: `milesight-ga01.md` [VEN].

## Common mistakes / troubleshooting
- No kit-specific troubleshooting in the text sources read; Quick Start Guide is image-only.
- Valve does not switch → check it is a DC latching valve and the output voltage setting (5/9/12 V) matches it [DS-kit].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Light-intensity monitoring | [PP] features: "soil moisture, temperature, electrical conductivity, and light intensity" | [PP] packing list and [DS-kit]: no light sensor in the kit | Kit does not measure light. **Fix the Cytron page** |
| Controller model | [PP]/[DS-kit] UC511 | KB slug list has UC512 (`milesight-uc512.md`), a separate listing | Different products; UC511 not in KB |
| Frequency plan | [PP] none stated | [DS-kit] all plans | Ask Cytron |

## Needs verification
- Quantity of each component.
- Frequency plan of the kit Cytron supplies.
- UC511 version in the kit (internal vs external antenna; solar panel included).
- Pro1 plan limits, start date and renewal cost.
- Whether any setup or field-installation service is offered (none stated).
- Contents of the iBox Quick Start Guide (image-only).

## Sources
- [PP] https://my.cytron.io/Milesight/p-lorawan-smart-agriculture-kit — read 2026-10-21
- [DS-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/agriculture-kit-datesheet-en.pdf — read in full (text) 2026-10-21
- [VEN] https://www.milesight.com/iot/product/lorawan-ibox-kit/agriculture-kit — read 2026-10-21
- [UM-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/quick-start-guide-en.pdf — image-only, not read
