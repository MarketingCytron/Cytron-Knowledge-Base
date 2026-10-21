# Milesight LoRaWAN Indoor Air Quality Kit (iBox IAQ Kit) — Verified Reference

| | |
|---|---|
| Product code | `LR-KIT-IAQ` (Cytron code) [PP]. Milesight name: **iBox IAQ Kit** ("iBox Smart IAQ Kit") [PP][DS-kit] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight *iBox IAQ Kit Datasheet* (full text, 9 pages) and Milesight IAQ Kit page read. iBox Quick Start Guide is image-only (not read) |
| Primary source | **Cytron product page** for what Cytron sells (packing list) [PP]; *iBox IAQ Kit Datasheet*, Milesight, http://resource.milesight.com/milesight/iot/document/ibox-kit/iaq-kit-datasheet-en.pdf (no version/date printed) [DS-kit] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = https://my.cytron.io/Milesight/p-lorawan-indoor-air-quality-kit (read 2026-10-21). [DS-kit] = Milesight *iBox IAQ Kit Datasheet* (component sheets; no version/date). [VEN] = https://www.milesight.com/iot/product/lorawan-ibox-kit/iaq-kit. [UM-kit] = iBox *Quick Start Guide* PDF (image-only, not read).

**Kit rule:** the components are **not** re-documented here — the four AM sensors are all options of Cytron's multi-model listing `milesight-iaq-sensor.md` ("LoRaWAN Indoor Air Monitoring (IAQ) Sensor": AM319 / AM308 / AM307 / AM103 / AM102, with or without display), and the gateway is `milesight-ug56.md`. Only kit-level facts are stated.

## What it is

## Specifications
Kit-level rows only. Component specs: `milesight-iaq-sensor.md`, `milesight-ug56.md`.

| Item | Value | Src |
|---|---|---|
| Product name (Cytron) | LoRaWAN Indoor Air Quality Kit | [PP] |
| Milesight kit name | iBox IAQ Kit / iBox Smart IAQ Kit | [PP][DS-kit] |
| Code | LR-KIT-IAQ | [PP] |
| Price / availability | RM6,715.80; "Enquiry" (2026-10-21) | [PP] |
| Warranty | 12 months | [PP] |
| Frequency plan of the kit | **Not stated** on the Cytron page; [DS-kit] lists CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 per model | [PP][DS-kit] |
| Platform included | 6 months (Pro1) Milesight IoT Cloud | [PP] |
| Setup / installation service | **None stated** | [PP] |

**Components (exactly as the Cytron packing list states)** [PP]
| # | Cytron packing-list line | Quantity stated | KB file |
|---|---|---|---|
| — | 1 x LoRaWAN Indoor Air Quality Kit (parent line) | 1 kit | this file |
| 1 | UG56 Industrial LoRaWAN® Gateway (without cellular) | not stated per item | `milesight-ug56.md` |
| 2 | AM102 LoRaWAN 2-in-1 IAQ Sensor | not stated per item | `milesight-iaq-sensor.md` (AM102 option; [DS-kit] sheet is **AM102L**) |
| 3 | AM103 LoRaWAN 3-in-1 IAQ Sensor | not stated per item | `milesight-iaq-sensor.md` (AM103 option) |
| 4 | AM307 LoRaWAN 7-in-1 IAQ Sensor | not stated per item | `milesight-iaq-sensor.md` (AM307 option) |
| 5 | AM319 LoRaWAN 9-in-1 IAQ Sensor | not stated per item | `milesight-iaq-sensor.md` (AM319 option) |
| 6 | 6 months (Pro1) Milesight IoT Cloud | 6-month subscription | — (software) |
| 7 | Quick Start Guide | not stated | — |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "LoRaWAN Indoor Air Quality Kit"; brand Milesight; Code `LR-KIT-IAQ`; no MPN; warranty 12 months; RM6,715.80; availability "Enquiry" (INQUIRE NOW) [PP].
- Description: also known as the iBox Smart IAQ Kit; monitors temperature, humidity, CO2, PM2.5, PM10, TVOC "and more"; AM102(L) 2-in-1 (T/H, > 7 years on 2 batteries); AM103 (T/H/CO2, e-ink, > 3 years); UG56 (8-channel, SX1302, > 2000 nodes, 15 km LoS / ~2 km urban, embedded NS, Milesight Development Platform). The "9-in-1 IAQ Sensor" paragraph repeats the AM103 text [PP].
- Features: hands-on IoT; integrates with multiple NS platforms; BACnet/IP to BMS [PP].
- Spec block: AM102L (traffic light, no e-ink, anti-theft, up to 9 years); AM103 (2.13-inch e-ink, emoticons, traffic light, hibernation/smart screen, up to 4 years); AM307/AM319 "9-in-1" (WELL-aligned AM319, 4.2-inch e-ink, traffic light and buzzer, anti-theft); UG56 (LBT, free embedded NS, BACnet) [PP].
- Resources: iBox Kit Datasheet, Quick Start Guide, Collection Overview (image), Milesight IoT Cloud (image) [PP].

## Interfaces, terminals and pin mapping
Kit level: none. Per [DS-kit], AM102L and AM103 run on batteries; AM307 and AM319 take 5 V / 1 A over USB Type-C (AM307 also battery-capable, ~3 years); UG56 802.3af PoE or 5 V 2 A USB-C. See component files.

## Rules and gotchas (for code, wiring and tutorials)
- **Four different sensors, one KB file:** use the matching model rows in `milesight-iaq-sensor.md`; AM307 and AM319 differ (AM319 adds HCHO or O3 as a build option, Class C; AM307 is Class A) [DS-kit].
- **AM102 vs AM102L:** Cytron lists "AM102"; Milesight's kit sheet and kit page show **AM102L** (no e-ink screen). Confirm the model shipped.
- **AM307 is 7-in-1 or 9-in-1 depending on the source** (see Conflicts).
- **AM319 / AM307 need USB power** for continuous operation (AM319 Class C) — no adapters are listed in the packing list [DS-kit][PP].
- **Frequency plan and quantities not stated** — confirm with Cytron.
- **Cloud is time-limited** (6 months Pro1) [PP].

## Power and electrical limits
Kit level: not stated. [DS-kit]: AM102L 2 × 2700 mAh ER14505 (over 9 years); AM103 replaceable batteries (up to 3 years); AM307 USB-C 5 V/1 A or battery (~3 years); AM319 USB-C 5 V/1 A; UG56 PoE or 5 V 2 A USB-C. Power adapters are not listed [PP].

## Software support
- **Milesight IoT Cloud — 6 months, Pro1 plan included** [PP]; Milesight's kit page: custom conditions and triggers, report export, drag-and-drop dashboard [VEN]; [DS-kit] (platform pages shared across iBox datasheets): email and push notifications, AWS hosting.
- **Milesight Development Platform** mentioned with the UG56 [PP]; plan inclusion not stated.
- **UG56 embedded network server**, BACnet/IP to a BMS [PP][DS-kit].
- AM319 carries the "Works with WELL" mark (IWBI) per Milesight [VEN].
- Setup service: none stated [PP].

## Compatibility and accessories
- Other LoRaWAN devices on the same plan can join the UG56; e.g. HVAC control through a controller in the KB.
- UG56 antenna kit `milesight-ga01.md` [VEN].

## Common mistakes / troubleshooting
- No kit-specific troubleshooting in the text sources read; Quick Start Guide is image-only.
- AM319/AM307 screen blank or not reporting → check USB power (component file).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| AM307 rating | [PP] packing list "AM307 LoRaWAN 7-in-1 IAQ Sensor"; [VEN] kit page lists a "7-in-1" and a "9-in-1" sensor | [DS-kit] and [PP] spec block: "AM307/AM319 9-in-1" | AM307 has no HCHO/O3 option per [DS-kit] (AM319 only); treat AM307 as 7-in-1 and confirm in `milesight-iaq-sensor.md` |
| 2-in-1 model | [PP] packing list "AM102" | [DS-kit], [VEN], [PP] spec block "AM102L" | Confirm model shipped |
| 9-in-1 description | [PP] "9-in-1 IAQ Sensor" paragraph | Text is the AM103 paragraph repeated | Cytron page copy error. **Fix the Cytron page** |
| AM103 battery life | [PP] description "more than 3 years"; [DS-kit] "up to 3-Year" | [PP] spec block and [VEN] "up to 4 Years" | [DS-kit]: up to 3 years |
| AM102(L) battery life | [DS-kit] over 9 years | [PP] description "more than 7 years" | [DS-kit] |
| Frequency plan | [PP] none stated | [DS-kit] all plans | Ask Cytron |

## Needs verification
- Quantity of each component.
- Frequency plan of the kit Cytron supplies.
- AM102 vs AM102L; whether AM319 ships with the HCHO or the O3 module.
- Whether USB power adapters are included for AM307/AM319 and the UG56.
- Pro1 plan limits, start date and renewal cost.
- Whether any setup/commissioning service is offered (none stated).
- Contents of the iBox Quick Start Guide (image-only).

## Sources
- [PP] https://my.cytron.io/Milesight/p-lorawan-indoor-air-quality-kit — read 2026-10-21
- [DS-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/iaq-kit-datasheet-en.pdf — read in full (text) 2026-10-21
- [VEN] https://www.milesight.com/iot/product/lorawan-ibox-kit/iaq-kit — read 2026-10-21
- [PP: sensor] https://my.cytron.io/Milesight/p-lorawan-iaq-sensor — header only read (model options AM319/AM308/AM307/AM103/AM102), to map the components to `milesight-iaq-sensor.md`
- [UM-kit] http://resource.milesight.com/milesight/iot/document/ibox-kit/quick-start-guide-en.pdf — image-only, not read
