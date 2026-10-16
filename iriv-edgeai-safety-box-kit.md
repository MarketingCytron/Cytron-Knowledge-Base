# IRIV EdgeAI Safety Box Kit — Verified Reference

| | |
|---|---|
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is


## Specifications
Kit-level rows. All other controller specs: `kb/iriv-edgeai-cm5.md` [DS-CM5].

| Item | Value | Src |
|---|---|---|
| Processor | Raspberry Pi Compute Module 5, Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) @ 2.4GHz | [DS-CM5] |
| Ethernet (controller) | 2x RJ45 Gigabit (10/100/1000M) | [DS-CM5] |
| Digital outputs | 2x isolated, dry contact (solid state relay), max 50 V (DC or AC load), max 500 mA, 1500 Vrms isolation | [DS-CM5] |
| Controller dimensions | 139mm × 88mm × 38mm (metal enclosure only, excl. antenna, DIN socket & connectors) | [DS-CM5] |
| Controller power consumption | Max 11 W (stress-ng CPU test, USB load excluded; AI HAT+/NVMe load not stated) | [DS-CM5] |
| Weight, humidity, certifications, kit power consumption | Not stated | — |

## Interfaces, terminals and pin mapping

| Function | Channel | Raspberry Pi CM5 | Kit use |
|---|---|---|---|
| Digital Input | DI0 / DI1 | GPIO22 / GPIO27 | No kit function stated |
| RS485 | — | `/dev/ttyACM0` | No kit function stated |
| LED driver | L0 / L1 | GPIO12 / GPIO13 | No kit function stated |

Pluggable terminal (DS-CM5): top row VIN · RS485 A/B/G · DO0 (2 contacts) · L0 +/−; bottom row GND · S/S · DI0 · DI1 · DO1 (2 contacts) · L1 +/−.

How the 24V PSU, fan, DIN terminal block and controller VIN are wired inside the box is **not documented** in any source read.

## Rules and gotchas (for code, wiring and tutorials)
- Do not mix kit specs into IRIV EdgeAI CM5 content, and do not call the kit "IRIV EdgeAI CM5".

## Power and electrical limits
- Controller VIN: 10–30 VDC, surge protected up to 60 V for 20 ms; max 11 W under CPU stress (USB load excluded) [DS-CM5].
- DO: 50 V / 500 mA per channel, isolation 1500 Vrms [DS-CM5].

## Software support
- No "SmartHub" dashboard feature is mentioned in any Safety Box source read (see Needs verification).

## Compatibility and accessories
- Controller expansion still available: 1x mPCIe (USB 2.0 only, 4G/LoRa), 2x MIPI CSI, 2x USB 3.0, RS485, DI [DS-CM5]. Not stated as supported by the Safety Box software.

## Common mistakes / troubleshooting
- No published troubleshooting for the kit. Controller-level items (4 A fuse, Boot/Run switch, `/dev/ttyACM0`) are in `kb/iriv-edgeai-cm5.md` [DS-CM5].
- Stack light does not light when DO switches → DO is a dry contact; the light needs its own supply in series [DS-CM5].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|

## Needs verification
- A kit datasheet or user manual (none found). IP67 rating as stated applies to the ABS enclosure; whether it holds for the assembled kit with fan, filters and RJ45 pass-throughs is not stated.
- Kit operating temperature, humidity, weight, certifications, PSU AC/DC input range, total kit power consumption.
- Internal wiring (PSU → controller VIN, fan, 6P terminal block); whether the fan is temperature-controlled.
- Which DO the PPE alarm uses (DO0 implied, not stated) and whether DO assignment is configurable.
- Any "SmartHub" dashboard feature — no Safety Box source mentions it; IRIV SmartHub CM5 is a separate product. Do not claim a link.
- Whether "EAI-W832-26TOPS" is the controller SKU; price; live product-page content after 2026-09-18.
- OS image / software version, update channel, licence terms; whether a subscription is needed.

## Sources
- [PP] https://my.cytron.io/p-iriv-edgeai-safety-box-kit and landing page https://my.cytron.io/iriv-edgeai-safety-box — not reachable 2026-10-16; facts via  KB below
- [VEN] Raspberry Pi AI HAT+ (Hailo-8 26 TOPS / Hailo-8L 13 TOPS) — https://www.raspberrypi.com/documentation/accessories/ai-hat-plus.html
