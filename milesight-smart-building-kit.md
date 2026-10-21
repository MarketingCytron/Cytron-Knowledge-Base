# Milesight LoRaWAN Smart Building Kit (iBox Smart Building Kit) — Verified Reference

| | |
|---|---|
| Product code | `LR-KIT-SB` (Cytron code) [PP]. Milesight name: **iBox Smart Building Kit** [PP][DS-kit] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight *iBox Smart Building Datasheet* (full text, 12 pages) and Milesight Smart Building Kit page read. iBox Quick Start Guide is image-only (not read) |
| Primary source | **Cytron product page** for what Cytron sells (packing list) [PP]; *iBox Smart Building Datasheet*, Milesight, http://resource.milesight.com/milesight/iot/document/ibox-kit/smart-building-kit-datesheet-en.pdf (no version/date printed) [DS-kit] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = https://my.cytron.io/Milesight/p-lorawan-smart-building-kit (read 2026-10-21). [DS-kit] = Milesight *iBox Smart Building Datasheet* (component sheets + platform pages; no version/date). [VEN] = https://www.milesight.com/iot/product/lorawan-ibox-kit/smart-building-kit. [UM-kit] = iBox *Quick Start Guide* PDF (image-only, not read).

**Kit rule:** the components are **not** re-documented here — see `milesight-ws101.md`, `milesight-ws558-ln.md`, `milesight-iaq-sensor.md` (AM103 is one option of that listing), `milesight-ws301.md`, `milesight-ug56.md` and `milesight-uc300.md`. WS303 has **no KB file**. Only kit-level facts are stated.

## What it is

## Specifications
Kit-level rows only. Component specs: see the files in the Kit rule.

| Item | Value | Src |
|---|---|---|
| Product name (Cytron) | LoRaWAN Smart Building Kit | [PP] |
| Milesight kit name | iBox Smart Building Kit | [PP][DS-kit] |
| Code | LR-KIT-SB | [PP] |
| Price / availability | RM5,166.00; "Enquiry" (2026-10-21) | [PP] |
| Warranty | 12 months | [PP] |
| Frequency plan of the kit | **Not stated** on the Cytron page; [DS-kit] lists CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923 plans per model | [PP][DS-kit] |
| Platform included | 6 months (Pro1) Milesight IoT Cloud | [PP] |
| Setup / installation service | **None stated** | [PP] |

**Components (exactly as the Cytron packing list states)** [PP]
| # | Cytron packing-list line | Quantity stated | KB file |
|---|---|---|---|
| — | 1 x LoRaWAN Smart Building Kit (parent line) | 1 kit | this file |
| 1 | Smart Button (WS101) | not stated per item | `milesight-ws101.md` |
| 2 | Smart Light Controller (WS558) | not stated per item | `milesight-ws558-ln.md` (Cytron's WS558-LN listing; the kit's variant — [DS-kit] sheet "WS558-Switch" — is not confirmed) |
| 3 | 3-in-1 IAQ Sensor (AM103) | not stated per item | `milesight-iaq-sensor.md` (AM103 option) |
| 4 | Magnetic Contact Switch (WS301) | not stated per item | `milesight-ws301.md` |
| 5 | Mini Leak Dectection Sensor (WS303) [sic] | not stated per item | **not in KB** (WS303) |
| 6 | Industrial LoRaWAN Gateway (UG56) | not stated per item | `milesight-ug56.md` |
| 7 | Smart IoT Controller (UC300) | not stated per item | `milesight-uc300.md` |
| 8 | 6 months (Pro1) Milesight IoT Cloud | 6-month subscription | — (software) |
No Quick Start Guide line on this packing list (the other three kits list one) [PP].

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "LoRaWAN Smart Building Kit"; brand Milesight; Code `LR-KIT-SB`; no MPN; warranty 12 months; RM5,166.00; availability "Enquiry" (INQUIRE NOW) [PP].
- Description: AM103 (CO2, temperature, humidity, 2.13-inch e-ink, emoticons, up to 3-year battery); WS558 (up to 8 lighting circuits, scheduling, power-consumption measurement, power-off memory); WS301 (door/window open-close, IP67, up to 5-year battery); WS303 (0.5 mm leak trigger, IP67, up to 5 years); UG56 (Ethernet/Wi-Fi/cellular backhaul, embedded NS, LBT, BACnet); UC300 (RS232, RS485, DI/DO, AI, relay; autonomous trigger operation) [PP].
- Features: environmental monitoring, LoRaWAN, smart light and IoT controller automation, Milesight IoT Cloud dashboards/widgets/triggers/alerts, plug-and-play PoC [PP].
- Spec block per component, including WS101 (single/double/long press, 5-year battery, D2D) and "6 months (Pro1) Milesight IoT Cloud: real time alarm notification, custom trigger conditions, Android & iOS versions" [PP].
- Resources: iBox Kit Datasheet, Quick Start Guide, Collection Overview (image), Milesight IoT Cloud (image) [PP].

## Interfaces, terminals and pin mapping
Kit level: none. Mains wiring applies to the WS558 (100–240 VAC, per [DS-kit]) and field wiring to the UC300 (3.5 mm terminal block, 5–24 VDC, DI/DO/AI/RS232/RS485/PT100 per [DS-kit]) — see their component files before any wiring tutorial.

## Rules and gotchas (for code, wiring and tutorials)
- **WS558 switches mains lighting circuits** (100–240 VAC; 5 A resistive / 10 A per switch as printed in [DS-kit]) — installation must be done by a qualified electrician; use the component file for ratings.
- **Variant check:** the kit datasheet shows "WS558-Switch"; the KB WS558 file covers Cytron's WS558-LN listing. Do not assume they are the same variant.
- **AM103 is one option** of Cytron's multi-model IAQ sensor listing (`milesight-iaq-sensor.md`); use the AM103 rows only.
- **WS301 spec on the Cytron page is wrong** (copied from AM103) — use `milesight-ws301.md` / [DS-kit] (see Conflicts).
- **Quantities not stated;** frequency plan not stated — confirm with Cytron.
- **Cloud is time-limited** (6 months Pro1) [PP].

## Power and electrical limits
Kit level: not stated. From [DS-kit]: WS101, WS301, WS303 and AM103 are battery devices; WS558 is mains-powered (100–240 VAC, 50–60 Hz); UC300 5–24 VDC; UG56 802.3af PoE or 5 V 2 A USB-C. No power supplies are listed in the packing list [PP].

## Software support
- **Milesight IoT Cloud — 6 months, Pro1 plan included** [PP]: dashboards and widgets, triggers, real-time alarm notification, Android and iOS apps [PP]; [DS-kit] adds drag-and-drop widgets, email and mobile push notifications, AWS hosting, licence activation by copy-and-paste.
- **Milesight Development Platform** (described in [DS-kit]): open API, webhooks, central device/application management; free and paid plans on Milesight's site (pricing not copied). Whether a plan is included: **not stated** [DS-kit].
- **UG56 embedded network server**; TTN, ChirpStack, Everynet, Senet compatible; **BACnet/IP** to a BMS [DS-kit][PP].
- **Milesight D2D** among WS101, WS301, WS303, WS558 and UC300 (controller/agent roles per [DS-kit]) for gateway-free scene control.
- Setup service: none stated [PP].

## Compatibility and accessories
- More LoRaWAN devices on the same plan can join the UG56.
- Gateway antenna kit `milesight-ga01.md` [VEN].

## Common mistakes / troubleshooting
- No kit-specific troubleshooting in the text sources read; Quick Start Guide is image-only.
- Devices not joining → check one frequency plan across all devices and the gateway (component files).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| WS301 specification | [PP] spec block: "Monitors CO₂ concentration, temperature, and humidity… 2.13-inch E-ink… up to 3 years" | [DS-kit] WS301: open/close + tamper, 10–15 mm detection distance, IP20, over 5-year battery; [PP] description: IP67, up to 5 years | [PP] spec block is a copy error (AM103 text). **Fix the Cytron page** |
| WS301 ingress | [DS-kit] IP20 | [PP] description and [VEN] kit page: IP67 | [DS-kit] is higher; confirm in `milesight-ws301.md` |
| WS558 model | [DS-kit] "WS558-Switch" (8 passive switches) | KB file `milesight-ws558-ln.md` (Cytron WS558-LN listing) | Variant in the kit not confirmed |
| Quick Start Guide | [PP] Resources link it; [VEN] kit contents list it | [PP] packing list omits it | Probably included; confirm |
| Frequency plan | [PP] none stated | [DS-kit] all plans | Ask Cytron |

## Needs verification
- Quantity of each component.
- Frequency plan of the kit Cytron supplies.
- WS558 variant in the kit (Switch vs LN).
- Pro1 plan limits, start date and renewal cost.
- Whether any setup/commissioning service is offered (none stated).
- Contents of the iBox Quick Start Guide (image-only).

## Sources
- [PP] https://my.cytron.io/Milesight/p-lorawan-smart-building-kit — read 2026-10-21
- [DS-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/smart-building-kit-datesheet-en.pdf — read in full (text) 2026-10-21
- [VEN] https://www.milesight.com/iot/product/lorawan-ibox-kit/smart-building-kit — read 2026-10-21
- [UM-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/quick-start-guide-en.pdf — image-only, not read
