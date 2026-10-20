# IRIV EdgeAI Safety Box Kit — Verified Reference

| | |
|---|---|
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: live product page, Quick Start Guide (17 Aug 2026), OSHMP30 article (12 Oct 2026) and GitHub landing page read. Team answers relayed by marketing (19 Oct 2026): one-time price, no licence or subscription; no accuracy figure published; assembled box −20 to 60 ℃; alarm outputs PPE = DO0, Zones = DO1 (web UI screenshot). Still no kit datasheet or user manual |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is


## Specifications
Kit-level rows. All other controller specs: `kb/iriv-edgeai-cm5.md` [DS-CM5].

| Item | Value | Src |
|---|---|---|
| Product code | KIT-IRIV-EAI-PPE | [PP] |
| Price / availability | RM7,999.00; availability "Enquiry" (2026-10-19) | [PP] |
| Licence / subscription | **One-time purchase** — no licence or subscription fee after buying | [DT] |
| Detection accuracy | **No accuracy figure is published** — results depend on site conditions Cytron cannot control (lighting, camera angle / point of view) | [DT] |
| Warranty | 12 months | [PP] |
| Processor | Raspberry Pi Compute Module 5, Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) @ 2.4GHz | [DS-CM5] |
| Ethernet (controller) | 2x RJ45 Gigabit (10/100/1000M) | [DS-CM5] |
| Digital outputs | 2x isolated, dry contact (solid state relay), max 50 V (DC or AC load), max 500 mA, 1500 Vrms isolation | [DS-CM5] |
| Kit power supply | 1x "Industry Switching Power Supply 24V 36W, Wide DC and AC Input Voltage" [PP] — the same name as Cytron product **PS-36W-24V** (brand Mornsun, LM35-23BxxR2 series, 24 V model LM35-23B24R2) [PP: PS-36W-24V][VEN: Mornsun] | [PP] |
| PSU input | 80–305 VAC (47–63 Hz) or 100–430 VDC on the same terminals; input current 0.8 A at 115 VAC, 0.6 A at 230 VAC | [PP: PS-36W-24V][VEN: Mornsun] |
| PSU output | 24 V, 1.5 A, 36 W (adjustable 22.8–27.6 V); efficiency 88.5% typ. at 230 VAC | [PP: PS-36W-24V][VEN: Mornsun] |
| PSU protection | Short circuit (hiccup, self-recovery, <3 s), over-current 120–200% Io, over-voltage ≤33.6 V; 4000 VAC input–output isolation; Class I (case must be earthed) | [VEN: Mornsun] |
| PSU environment | Operating −40 to +85 ℃ with derating above +50 ℃ (2.5 %/℃ from +50 to +70 ℃); 20–90 %RH non-condensing; free-air convection cooling — "for applications in closed environment please consult Mornsun FAE"; 99 × 65 × 30 mm, 150 g | [VEN: Mornsun] |
| Enclosure | "Ready-to-Deploy IP67 ABS Industrial Enclosure" | [PP] |
| Enclosure dimensions | 250mm × 350mm × 160mm | [PP] |
| Controller dimensions | 139mm × 88mm × 38mm (metal enclosure only, excl. antenna, DIN socket & connectors) | [DS-CM5] |
| Camera stream capacity | Up to 6 RTSP IP camera sub-streams, 640x360 @ 15–25 FPS, H.264/H.265 | [PP] |
| Status display | Front OLED shows the box's IP address for first sign-in | [QSG] |
| Operating temperature | **Assembled box: −20 to 60 ℃** [DT] (team first wrote "30–60 ℃"; marketing confirmed −20 to 60 ℃, matching the controller). Parts: controller −20 to 60 ℃ [DS-CM5]; PSU −40 to +85 ℃ with derating above +50 ℃ [VEN: Mornsun] | [DT][DS-CM5][VEN: Mornsun] |
| Controller power consumption | Max 11 W (stress-ng CPU test, USB load excluded; AI HAT+/NVMe load not stated) | [DS-CM5] |
| Weight, humidity, certifications, kit power consumption | Not stated | — |

## Interfaces, terminals and pin mapping
The kit's alarm outputs are the controller's DO0/DO1 [PP]. The web UI names them **"Digital output · PPE (DO0)"** and **"Digital output · Zones (DO1)"** [DT: UI]. Each has a **Status** on/off switch and a **Timing** choice of **Hold** or **Pulse**, with **Pulse duration (seconds)** (shown at 1 s) [DT: UI]. The UI shows no option to swap which alarm uses which output. Controller mapping from DS-CM5 §5.1 (full table in `kb/iriv-edgeai-cm5.md`):

| Function | Channel | Raspberry Pi CM5 | Kit use |
|---|---|---|---|
| Digital Output | DO0 | GPIO23 | **PPE alarm** — "Digital output · PPE (DO0)"; on/off, Hold or Pulse [DT: UI] |
| Digital Input | DI0 / DI1 | GPIO22 / GPIO27 | No kit function stated |
| RS485 | — | `/dev/ttyACM0` | No kit function stated |
| LED driver | L0 / L1 | GPIO12 / GPIO13 | No kit function stated |

Pluggable terminal (DS-CM5): top row VIN · RS485 A/B/G · DO0 (2 contacts) · L0 +/−; bottom row GND · S/S · DI0 · DI1 · DO1 (2 contacts) · L1 +/−.

How the 24V PSU, fan, DIN terminal block and controller VIN are wired inside the box is **not documented** in any source read.

## Rules and gotchas (for code, wiring and tutorials)
- **DO0/DO1 are dry contacts (SSR), not voltage outputs** — max 50 V DC or AC, 500 mA; the siren/stack light needs its own supply [DS-CM5]. The live page wording "can directly trigger 50V DC industrial stack lights" and "up to 50V DC" [PP] must not be read as "the DO supplies 50 V". For inductive loads Cytron recommends a flyback diode [DS-CM5].
- **AI accelerator is Hailo-8, 26 TOPS** — not the 13 TOPS (Hailo-8L) option of the standalone controller [PP][VEN]. It sits on the PCIe port as the AI HAT+; never call it an M.2 module — the M.2 Key-M socket holds the 128GB SSD [PP][DS-CM5].
- **Kit PSU vs controller input:** the live page puts "(DC 10V–30V wide input range with surge protection)" after the 24V 36W PSU [PP], but 10–30 V DC is the controller's VIN [DS-CM5] and the packing list calls the PSU "Wide DC and AC Input Voltage" [PP]. Do not quote 10–30 V as the kit's mains input.
- **Camera inputs:** the live page lists "2 x MIPI CSI ports" under Camera Connectivity [PP], but the kit software is documented only for RTSP IP cameras [PP][QSG]. Do not say the kit works with CSI cameras.
- Do not mix kit specs into IRIV EdgeAI CM5 content, and do not call the kit "IRIV EdgeAI CM5".

## Power and electrical limits
- Kit mains input: UK plug cord with 13A fuse (C13) into an IEC fused, switched inlet; 24V 36W PSU (PS-36W-24V / Mornsun LM35-23B24R2) accepts 80–305 VAC 47–63 Hz or 100–430 VDC; 0.6 A input at 230 VAC [PP: PS-36W-24V][VEN: Mornsun].
- PSU output 24 V 1.5 A feeds the controller (VIN 10–30 V) and the 24V fan; the exact wiring through the 6P terminal block is not documented.
- The PSU is rated for free-air convection; Mornsun asks users to consult them for closed enclosures [VEN: Mornsun] — the assembled box (with fan) is rated −20 to 60 ℃ by the Cytron team [DT].
- Controller VIN: 10–30 VDC, surge protected up to 60 V for 20 ms; max 11 W under CPU stress (USB load excluded) [DS-CM5].
- DO: 50 V / 500 mA per channel, isolation 1500 Vrms [DS-CM5].

## Software support
- **Export:** "audit-ready CSV/PDF reports" [PP]; Reports tab generates PDF; Events has export [QSG]; the landing page lists CSV plus snapshots and optional clips [LP].
- **Five tabs** [QSG]: Live View (camera grid with detections drawn live; zones drawn here), Analytics (charts and summaries over time), Events (record with evidence, filters and export), Reports (generate a PDF safety report for a period), Settings (cameras, models, alerts, users, system).
- **Live View controls** [QSG]: layouts Auto, Grid, Focus, Single; camera list with Start/Stop (a stopped camera produces no detections or events); tile full screen, previous/next camera (← →), camera settings; **Smart Live** switch — an idle tile stops sending pictures after about 30 seconds and resumes on motion or a detection; status strip with violation status and alert counts by PPE type and zone; recent-events rail with snapshot preview.
- **Offline operation:** all inference is on the device; video does not leave the site and the system keeps working without internet [QSG].
- **Reports** [PP: tutorial]: a ready-made "Workplace Safety Audit" report on demand, or by email every month; each situation is saved once with a photo and a short video.
- No "SmartHub" dashboard feature is mentioned in any Safety Box source read (see Needs verification).
- Cytron articles: Quick Start Guide https://my.cytron.io/tutorial/iriv-edgeai-safety-box-quick-start-guide [QSG]; OSHMP30 article https://my.cytron.io/tutorial/iriv-edgeai-safety-box-ready-for-oshmp30 [PP: tutorial]. Product-page resources also link the CM5 "Getting Started" video and guide and a "Bookworm OS For IRIV Edge AI" image (controller-level, not kit-specific) [PP].

## Compatibility and accessories
- Controller expansion still available: 1x mPCIe (USB 2.0 only, 4G/LoRa), 2x MIPI CSI, 2x USB 3.0, RS485, DI [DS-CM5]. Not stated as supported by the Safety Box software.

## Common mistakes / troubleshooting
- No published troubleshooting for the kit. Controller-level items (4 A fuse, Boot/Run switch, `/dev/ttyACM0`) are in `kb/iriv-edgeai-cm5.md` [DS-CM5].
- Stack light does not light when DO switches → DO is a dry contact; the light needs its own supply in series [DS-CM5].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| DO rating | Live [PP] (still): "Isolated Digital Outputs (up to 50V DC)", "can directly trigger 50V DC industrial stack lights" | DS-CM5: dry contact, max 50 V DC **or AC**, 500 mA | DS-CM5 wins; dry contact, load needs own supply. **Fix the live page** |
| Power input | Live [PP]: "24V 36W Industrial Switching Power Supply (DC 10V–30V wide input range with surge protection)" | Live packing list [PP]: PSU "Wide DC and AC Input Voltage"; DS-CM5: 10–30 V DC is the controller VIN | 10–30 V is the controller VIN; kit is mains-fed via the PSU. **Fix the live page** |
| Camera inputs | Live [PP] Camera Connectivity: "2 x RJ45 Gigabit Ethernet + 2 x MIPI CSI ports" | Live [PP] note and [QSG]: kit "requires IP cameras with RTSP streaming support" | Kit software is documented for RTSP only; CSI ports are controller hardware. Ask whether to drop CSI from the kit page |
| Live View layouts | [LP]: "Smart, Grid, Focus, Single" | [QSG]: Auto, Grid, Focus, Single + separate Smart Live switch | [QSG] (more detailed, Cytron tutorial) |

## Needs verification
- Team answer (2026-10-19): the kit uses the same controller as the IRIV EdgeAI CM5, so the CM5 datasheet is the controller spec [DT]. Still no kit-level sheet for the assembled box. IP67 rating as stated applies to the ABS enclosure; whether it holds for the assembled kit with fan, filters and RJ45 pass-throughs is not stated.
- Humidity range of the assembled box, weight, certifications, total kit power consumption.
- Confirm the kit ships the PS-36W-24V (Mornsun LM35-23B24R2) — identified by its identical product name.
- Internal wiring (PSU → controller VIN, fan, 6P terminal block); whether the fan is temperature-controlled.
- Three live product-page errors to fix (DO "directly trigger 50V DC", PSU "DC 10V–30V", "2 x MIPI CSI" under camera connectivity) — see Conflicts.
- Any "SmartHub" dashboard feature — no Safety Box source mentions it; IRIV SmartHub CM5 is a separate product. Do not claim a link.
- Whether "EAI-W832-26TOPS" is the controller SKU.
- OS image / software version and update channel. (Licence: one-time purchase, no subscription [DT].)

## Sources
- [PP] https://my.cytron.io/p-iriv-edgeai-safety-box-kit — read 2026-10-19 (RM7,999.00, Enquiry, 12-month warranty, description, features, hardware specs, packing list, resources)
- [QSG] IRIV EdgeAI Safety Box: Quick Start Guide (Asri Ruslan, 17 Aug 2026) — https://my.cytron.io/tutorial/iriv-edgeai-safety-box-quick-start-guide
- [PP: PS-36W-24V] Industry Switching Power Supply 24V 36W, Wide DC and AC Input Voltage (Mornsun, RM89.00) — https://my.cytron.io/p-industry-switching-power-supply-24v-36w-wide-dc-and-ac-input-voltage
- [VEN: Mornsun] LM35-23BxxR2 datasheet 2023.07.14-A/1 (linked from that page) — https://drive.google.com/file/d/1A2HJg8hk1-A60YMEfViTI_Fh13rufIcy/view
- [PP: tutorial] IRIV EdgeAI Safety Box: Ready for OSHMP30 (Asri Ruslan, 12 Oct 2026) — https://my.cytron.io/tutorial/iriv-edgeai-safety-box-ready-for-oshmp30
- [LP] Landing page — https://marketingcytron.github.io/iriv-edgeai-safety-box/ (also https://my.cytron.io/iriv-edgeai-safety-box)
- [VEN] Raspberry Pi AI HAT+ (Hailo-8 26 TOPS / Hailo-8L 13 TOPS) — https://www.raspberrypi.com/documentation/accessories/ai-hat-plus.html
