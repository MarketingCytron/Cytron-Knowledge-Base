# Milesight WS558-LN LoRaWAN Smart Light Controller — Verified Reference

| | |
|---|---|
| Product code | `WS558-LN` (Milesight model; WS558 also exists as `WS558-Switch`, not sold by Cytron) [DS]. Cytron code `LR-WS558-LN` (no MPN shown) [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specification, packing list, resources), Milesight WS558 product page (incl. LN wiring image), WS558 datasheet (in full) and WS558 user guide (safety, hardware, quick start, LoRaWAN/general/D2D settings, reset, installation) read |
| Primary source | Milesight *WS558 Datasheet* (PDF, file dated 19 Jun 2025), https://resource.milesight.com/milesight/iot/document/ws558-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight WS558 datasheet PDF (covers WS558-LN and WS558-Switch; 4 pages; PDF created 19 Jun 2025). [UM] = Milesight *WS558 User Guide* PDF (`ws558-user-guide-en.pdf`, 33 pages; PDF revised 3 Nov 2025). The wiring diagrams inside the [UM] PDF did not render as text or image; the LN wiring figure was read from the Milesight product page image `smart-light-controller-ln.png` [VEN] at low resolution. [PP] = Cytron product page.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Circuit type | LN type (WS558-LN) | [DS] |
| Input voltage | 100–240 VAC, 50–60 Hz | [DS] |
| Output | 8 active outputs | [DS] |
| Capacitive & inductive load | Max 5 A per output, total 16 A | [DS] |
| Resistive load | Max 10 A per output, total 16 A | [DS] |
| Electrical measurement | Voltage (VAC), current (mA), power factor (%), power (W), power consumption (kW·h) | [DS] |
| Protocol | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal | [DS] |
| Frequency plans | CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 22 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm | [DS] |
| Mode | OTAA/ABP **Class C** | [DS] |
| LED | 1 × power indicator + 8 × status indicators | [DS] |
| Buttons | 1 × reset button + 8 × switch buttons | [DS] |
| USB | 1 × Type-C for configuration and console | [DS] |
| Configuration | NFC, USB Type-C or downlink | [DS] |
| Switch control | Local press or remote control | [DS] |
| Advanced features | Multicast, delay switch, overcurrent protection/alarm, Milesight D2D agent | [DS] |
| Reporting interval | 1 – 1080 min, default 20 min | [UM] |
| Colour / material | Creamy-white, ABS | [DS] |
| Operating temperature | -20 °C to 60 °C | [DS] |
| Relative humidity | ≤ 95 % (non-condensing) | [DS] |
| Dimensions | 145 × 90 × 40 mm | [DS] |
| Weight | 274 g (LN) | [DS] |
| Installation | Wall mounting, DIN rail mounting | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WS558-LN LoRaWAN Smart Light Controller", code `LR-WS558-LN`, RM602.70, "Availability: Enquiry" (Inquire Now); no warranty line and no MPN in the header [PP].
- Spec block: LN type; "Input Voltage: 100~250 VAC, 50~60 Hz"; 8 active outputs; 5 A / 10 A per output, total 16 A; electrical measurement as [DS]; LoRaWAN + D2D; "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1"; Tx 16/22/19 dBm; -137 dBm; OTAA/ABP Class C; NFC, USB Type-C or downlink; multicast, remote schedule switch, overcurrent protection, D2D agent; creamy-white ABS; -20 to 60 °C; wall/DIN rail; 145 × 90 × 40 mm [PP].
- Description: up to 18 hours turn-off delay; scenes via WS156 Smart Scene Panel and WS202 PIR & Light Sensor (D2D); power-off memory (resumes previous state after power returns) [PP].
- **Packing:** 1 × WS558-LN, 1 × wall mounting kits, 1 × quick start guide, 1 × warranty card [PP] ([UM] says 4 × wall mounting kits).
- **Resources:** WS558 datasheet, user guide, payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware download [PP].

## Interfaces, terminals and pin mapping
From the [UM] hardware overview and the [VEN] LN wiring image [UM][VEN]:
| Terminal / part | Position | Function |
|---|---|---|
| AC power interface | Top-left, 2 screw terminals **L, N** | 100–240 VAC supply |
| Type-C console port | Top-right | Configuration / console |
| NFC area | Front, top-left | ToolBox app |
| 8 light indicators + 8 buttons | Front row, numbered 1–8 | Local on/off per circuit, status |
| Power LED, reset button | Front, right | |
| Switch/output terminals | Bottom edge, 2 blocks (circuits 1–4 and 5–8) | Each circuit has a terminal pair **N** and **L<sub>n</sub>** (switched live); the lamp connects between L<sub>n</sub> and N |
The per-circuit labels (N / L1 … N / L8) were read from a low-resolution image; confirm on the unit label before writing a wiring tutorial (see *Needs verification*).

## Rules and gotchas (for code, wiring and tutorials)
- **Mains wiring:** installation and maintenance by a qualified person following local electrical rules; switch the breaker off while wiring [UM].
- **Do not swap L and N** on the LN model [UM].
- **Load limits:** 10 A resistive or 5 A capacitive/inductive per output, **16 A total across all 8** — LED drivers and fans count as capacitive/inductive (inferred) [DS].
- **Indoor only**, clean environment, -20 to 60 °C [UM][DS].
- All circuits are **off (open) by default**; press the button under each LED to test a circuit without any network [UM].
- "Return to power supply state" setting decides what the outputs do after an outage [UM].
- When using USB, do not touch the power terminals or wiring (live parts) [UM].
- Class C: always listening, so remote commands are immediate [DS].
- D2D: it works only as a **D2D agent** (receives commands from D2D controllers such as WS156 / WS202), not as a controller [DS][UM].
- For US915/AU915 with default Milesight gateways set channel index 8–15 (not relevant to AS923) [UM].

## Power and electrical limits
- Supply 100–240 VAC, 50–60 Hz on L/N [DS].
- Per output 10 A resistive, 5 A capacitive/inductive; total 16 A [DS].
- Overcurrent protection and alarm [DS].
- Self-consumption: [NOT STATED].

## Software support
- Milesight ToolBox app (NFC) and ToolBox PC software (USB Type-C); downlinks [DS][UM].
- Milesight IoT Cloud (dashboards, triggers, app), standard LoRaWAN network servers [DS][PP].
- Decoder: https://github.com/Milesight-IoT/SensorDecoders [PP].
- Firmware upgrade and config backup/restore via ToolBox [UM].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- D2D controller sold by Cytron and named on the WS558 page: `milesight-ws202.md` (PIR & light sensor). The WS156 scene panel it names is not sold by Cytron [PP].
- Related switch products: `milesight-ws50x.md` (wall switch) [VEN].

## Common mistakes / troubleshooting
- **Lamp never turns on:** lamp wired L-to-L instead of L<sub>n</sub>-to-N, or L/N swapped on the input [UM].
- **Output trips:** overcurrent protection — check per-output and 16 A total limits [DS].
- **Factory reset:** hold the reset button > 10 s until the LED blinks quickly; or reset in ToolBox app / software [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Input voltage | [DS] 100–240 VAC | [PP] 100–250 VAC | [DS] wins: 100–240 VAC |
| Wall mounting kits | [UM] 4 × wall mounting kits | [PP] 1 × wall mounting kits | Use [UM] (one kit set of 4 plugs/screws likely; minor) |

## Needs verification
- Per-circuit terminal labels and order (N / L<sub>n</sub>) on the actual unit; maximum wire size and torque.
- Warranty period (not shown on the Cytron page; other Milesight items there are 12 months).
- Whether the controller's own L/N input needs a separate breaker sized for 16 A.
- LoRaWAN plan pre-set on Cytron's unit (Cytron says Malaysia AS923-2 / Singapore AS923-1).

## Sources
- [DS] WS558 Datasheet: https://resource.milesight.com/milesight/iot/document/ws558-datasheet-en.pdf (PDF 19 Jun 2025)
- [UM] WS558 User Guide: https://resource.milesight.com/milesight/iot/document/ws558-user-guide-en.pdf (PDF revised 3 Nov 2025)
- [VEN] Milesight WS558 page and LN wiring image: https://www.milesight.com/iot/product/lorawan-sensor/ws558 , https://www.milesight.com/static/pc/en/iot/product/lorawan-sensor/ws558/part4/smart-light-controller-ln.png
- [PP] Cytron: https://my.cytron.io/Milesight/p-ws558-ln-lorawan-smart-light-controller (read 2026-10-21)
