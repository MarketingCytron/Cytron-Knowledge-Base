# Milesight WS50x LoRaWAN Smart Wall Switch — Verified Reference

| | |
|---|---|
| Product code | `WS50x` series: `WS501` (1-gang) and `WS502` (2-gang); Milesight PNs `3W-W12-US` (WS501, 120 type), `3W-W11-EU` (WS501 and WS502, 86 type) [DS][UM]. Cytron codes `LR-WS501` (MPN `WS501-915M`) and `LR-WS502` (MPN `WS502-915M`); parent listing code `V-LR-WS50X` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both options: code, MPN, price, stock; description, features, specification, packing list, resources), Milesight WS50x product page, WS50x datasheet (in full, including the wiring-diagram figure rendered as an image) and WS50x user guide (applicability, safety, revision history, packing, LED patterns, installation, quick start, LoRaWAN settings, general settings, D2D controller/agent, dual-control example, upgrade, reset) read; the uplink/downlink payload chapter was not read |
| Primary source | Milesight *WS50x Series Datasheet* (PDF, file dated 27 Apr 2025), https://resource.milesight.com/milesight/iot/document/ws50x-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight WS50x Series datasheet PDF (4 pages; PDF created 27 Apr 2025); its p4 wiring diagram was rendered and read as an image. [UM] = Milesight *WS50x User Guide* PDF (`ws50x-user-guide-en.pdf`, 33 pages, V1.3 of 23 Apr 2025; PDF revised 29 Sep 2025), read except the payload chapter. [VEN] = Milesight WS50x product page. [PP] = Cytron product page.

## What it is
Cytron sells **WS501 (1-button)** and **WS502 (2-button)** on one page [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Circuit type | 3-wire (neutral required) | [DS] |
| Switch indicator | Ice blue | [DS] |
| Input voltage | 100–250 VAC, 50–60 Hz | [DS] |
| Maximum current | Inductive: 5 A per gang, total 10 A; resistive: 10 A per gang, total 10 A | [DS] |
| Rated load | Max 1000 W per gang, total 0–2000 W | [DS] |
| Terminal | SPST | [DS] |
| Variants | 86 type: 1-gang / 2-gang; 120 type: 1-gang | [DS] |
| Measurement | Voltage (VAC), current (mA), power factor (%), active power (W), power consumption (kWh) | [DS] |
| Measurement accuracy | Typical ±3 %, maximum ±5 % (±1 % customizable) | [DS] |
| Technology | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal | [DS] |
| Frequency plans | CN470/IN865/RU864/EU868/US915/AU915/KR920/AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 22 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm | [DS] |
| Mode | OTAA/ABP **Class C** | [DS] |
| Configuration | Mobile app via NFC or downlink | [DS] |
| Switch control | Local press or remote control | [DS] |
| Advanced features | Delay switch, switch lock, overcurrent protection, multicast, Milesight D2D agent, Milesight D2D controller | [DS] |
| Reporting interval | 1 – 1080 min, default 20 min | [UM] |
| Ingress protection | IP20 | [DS] |
| Material / colour | Polycarbonate (UL94 V0), white (customizable) | [DS] |
| Weight | 86 type: 94 g (1-gang), 103 g (2-gang); 120 type: 100.4 g | [DS] |
| Dimensions | 86 type: 86 × 86 × 40 mm; 120 type: 118 × 72 × 46.9 mm | [DS] |
| Operating temperature | -20 °C to 60 °C | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Installation | Wall mounting | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
| Ordering | WS501 3W-W12-US: 1-gang for 118/120 square pattress box; WS501 3W-W11-EU: 1-gang for 86 mm square pattress box; WS502: 2-gang for 86 mm square pattress box | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WS50x LoRaWAN Smart Wall Switch", option "WS50X Options": 1-Button (WS501) / 2-Button (WS502), warranty 12 months [PP].
- WS501: code `LR-WS501`, MPN `WS501-915M`, RM258.30, "Availability: Enquiry". WS502: code `LR-WS502`, MPN `WS502-915M`, RM258.30, "Availability: Enquiry". Parent page "Out Of Stock" with Notify Me [PP].
- Spec block matches [DS] except: Tx power listed as 22 dBm (915 MHz) only; "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1"; weight only "86 Type: 103 g (2-Gang)"; dimensions only 86 type; operating temperature printed "20°C ~ 60°C (-4°F ~ 140°F)" [PP].
- **Packing:** 1 × WS50x (1-button / 2-button), 2 × mounting screws, 1 × quick start guide, 1 × warranty card [PP][UM].
- **Resources:** WS50x datasheet, user guide, payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware download [PP].

## Interfaces, terminals and pin mapping
Rear screw terminals, read from the [DS] wiring diagram (left → right as drawn) [DS]:
| Model | Terminals | Wiring |
|---|---|---|
| WS502 (86 type, 2-gang) | **N, L, L1, L2** | Mains N and L to N and L; lamp 1 between L1 and N; lamp 2 between L2 and N |
| WS501 (86 type, 1-gang) | **N, L, L1** (4 terminal positions drawn) | Mains N and L; lamp between L1 and N |
| WS501 (120 type, US) | **G, N, L, L1** | Ground to G, then as above |
No USB or other connectors; NFC is used through the front [DS].

**LED patterns** [UM]
| Event | Indicator |
|---|---|
| Power on | Off → on |
| Join request sent | Blinks once quickly |
| Joined network | All blink twice slowly |
| Reset to factory default (hold any button > 10 s) | Blinks |

## Rules and gotchas (for code, wiring and tutorials)
- **Neutral is required** (3-wire). Many old switch boxes have only L and the switched lamp wire — check a neutral is present before buying [DS][UM].
- **Installation by a qualified electrician**, breaker off, nothing left inside the box [UM].
- **Load limits:** 1000 W per gang, 10 A total (both gangs together on WS502); inductive loads 5 A per gang [DS].
- **Indoor, IP20 only** [DS].
- **Fit:** 86 type = 86 mm square pattress (the common Malaysian/UK-style box; inferred); 120 type = 118/120 box [DS].
- Class C: always listening; remote commands act immediately [DS].
- D2D controller **and** agent: one WS50x can switch another Milesight D2D device (dual-control) without a gateway. Both devices need the same RX2 data rate, RX2 frequency and D2D key; the agent maps up to 16 2-byte commands to actions; for dual control set the agent's action to "Inverse". Do not press the button repeatedly while a D2D packet is sending [UM].
- **Button Lock** disables local on/off and the button reset; "When Power is Restored" sets the state after an outage; the button LED can be disabled [UM].
- Firmware upgrade is by the ToolBox app over NFC [UM].
- Configuration needs an NFC phone with the Milesight ToolBox app; remove the phone case [UM].

## Power and electrical limits
- 100–250 VAC, 50–60 Hz, 3-wire with neutral [DS].
- Per gang 1000 W, 10 A resistive / 5 A inductive; total 10 A and 0–2000 W [DS].
- Overcurrent protection [DS].
- Self-consumption: [NOT STATED].

## Software support
- Milesight ToolBox app over NFC (Android/iOS); LoRaWAN downlinks [DS][UM].
- Milesight IoT Cloud and Milesight Development Platform (OTAA required) [DS][UM].
- Decoder: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- D2D partners sold by Cytron: `milesight-ws558-ln.md` (8-circuit light controller, D2D agent), `milesight-ws202.md` (PIR & light sensor) [DS][VEN].

## Common mistakes / troubleshooting
- **Switch does not power up:** no neutral wired [DS].
- **Lamp flickers or switch trips:** overload or inductive load above 5 A per gang [DS].
- **NFC read fails:** move the phone away and back; remove the phone case [UM].
- **Factory reset:** hold any button > 10 s until the indicator blinks quickly (not possible while Button Lock is on), or ToolBox app Reset [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Operating temperature | [DS] -20 °C to 60 °C | [PP] "20°C ~ 60°C (-4°F ~ 140°F)" (minus sign missing) | [DS] wins: -20 to 60 °C |
| Stock | [PP] parent "Out Of Stock" | [PP] options "Enquiry" | Treat as out of stock; order by enquiry |

## Needs verification
- Which WS501 hardware Cytron supplies (86-type `3W-W11-EU` or 120-type `3W-W12-US`); MPN `WS501-915M` does not say. The 86 type fits Malaysian 86 mm boxes (inferred).
- Which of the 4 terminal positions on the 86-type WS501 takes L1 (drawing ambiguous).
- Uplink/downlink payload chapter of the [UM] (not read; use the SensorDecoders repo).
- LoRaWAN plan pre-set on Cytron's units (Cytron says Malaysia AS923-2 / Singapore AS923-1).

## Sources
- [DS] WS50x Series Datasheet: https://resource.milesight.com/milesight/iot/document/ws50x-datasheet-en.pdf (PDF 27 Apr 2025)
- [UM] WS50x User Guide: https://resource.milesight.com/milesight/iot/document/ws50x-user-guide-en.pdf (V1.3, 23 Apr 2025; PDF revised 29 Sep 2025)
- [VEN] Milesight WS50x page: https://www.milesight.com/iot/product/lorawan-sensor/ws50x
- [PP] Cytron: https://my.cytron.io/Milesight/p-ws50x-lorawan-smart-wall-switch (options `p-ws501-lorawan-smart-wall-switch`, `p-ws502-lorawan-smart-wall-switch`; read 2026-10-21)
