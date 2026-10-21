# Milesight CTH01 LoRaWAN Smart Power Monitor Hub — Verified Reference

| | |
|---|---|
| Product code | `CTH01` (Milesight model). Cytron code `LR-CTH01`, MPN `CTH01-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, MPN, description, spec, packing list, accessories, resources), CTH01 datasheet read in full, CTH01 user guide V1.0 (20 Mar 2026) read for safety, hardware, LED, wiring diagrams, installation, ToolBox interface settings and current-range downlink |
| Primary source | Milesight *CTH01 Datasheet*, https://resource.milesight.com/milesight/iot/document/cth01-datasheet-en.pdf (read 2026-10-21; no version printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight CTH01 datasheet PDF. [UM] = Milesight CTH01 User Guide V1.0, 20 Mar 2026 (resource.milesight.com). [PP] = Cytron product page (its datasheet and user-guide links point to Google Drive copies, not opened; the Milesight originals were read instead). [VEN] = milesight.com CTH01 product page (download links).

## What it is
Channels can be 12 single-phase circuits, 4 three-phase groups, or a mix [DS]. It is mains-connected equipment: Milesight requires a qualified electrician and a de-energized board for installation [UM].

## Specifications
| Item | Value | Src |
|---|---|---|
| Detection parameters | RMS voltage and current; power factor; active, reactive, apparent power; active (import/export), reactive (import/export), apparent energy; voltage three-phase unbalance; THDv; THDi | [DS] |
| Sampling frequency | 6 – 8 kHz | [DS] |
| Working frequency | 50 – 60 Hz | [DS] |
| Accuracy | Active energy ±1 % (IEC 62053-21); reactive energy ±2 % (IEC 62053-23) | [DS] |
| Voltage circuit configurations | Three-phase L1–L3 with or without neutral; single-phase L + N; mixed | [DS] |
| Voltage measuring range | 100 – 500 V AC, ±1 % | [DS] |
| Maximum voltage | 290 Vrms N–L; 500 Vrms L–L | [DS] |
| Voltage wire size | AWG 26 – 12 | [DS] |
| Current interface | 12 × current channels, RJ11; range up to 4000 A (split-core CT or Rogowski coil) | [DS] |
| CT options (sold separately) | Split-core 0–100 A, 0–300 A, 0–500 A, 0–1000 A; Rogowski coil 0–4000 A (see `milesight-cth01-ct-clamps.md`) | [DS] |
| Temperature sensor | External NTC (USB-C), -20 ~ 100 °C, ±1 °C | [DS] |
| Protocol | LoRaWAN®, OTAA/ABP, **Class C** | [DS] |
| Antenna connector | 1 × 50 Ω SMB-female external connector | [DS] |
| Frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power / sensitivity | 16 dBm (868) / 20 dBm (915) / 19 dBm (470); -137 dBm | [DS] |
| LED / button | 1 × status/alarm indicator; 1 × reset button | [DS] |
| USB | 1 × USB Type-C, for the cable temperature sensor only | [DS] |
| Configuration | Mobile app (Milesight ToolBox) via Bluetooth | [DS] |
| Advanced features | Data storage (20,000 entries, 2,000 alarms); 12 months of energy statistics; threshold, out-of-range and power-failure alarms; FUOTA | [DS] |
| Power supply | 12 V DC via the included AC–DC power adapter | [DS] |
| Power connector | 1 × 2-pin 5 mm terminal block, reverse polarity protected | [DS] |
| Insulation voltage | 4 kVac rms (1 mA / 1 min) | [DS] |
| Intrinsic consumption | max 5.8 W | [DS] |
| Pollution degree / overvoltage category / altitude | 2 / III / 2000 m max | [DS] |
| Operating temperature | -20 °C ~ 70 °C | [DS] |
| Humidity | ≤ 95 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Housing | ABS+PC (UL94 V0), starlight grey | [DS] |
| Dimensions / weight | 49.3 × 98 × 90 mm; 163 g | [DS] |
| Installation | DIN 35 rail; magnetic mounting (optional) | [DS] |
| Approvals | ETL Listed (UL/CSA 61010-1, UL/CSA 61010-2-030); CE (RED & LVD); FCC; SRRC; RoHS | [DS] |
| Reporting interval | 1 – 1440 min, default 10 min | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "CTH01 LoRaWAN® Smart Power Monitor Hub"; brand Milesight; Code `LR-CTH01`; MPN `CTH01-915M`; warranty 12 months; RM1,722.00; availability "Enquiry" [PP].
- Cytron note: "The CTH01 Hub does not include Current Transformer (CT) clamps"; buy the RCT-RJ11 split-core CTs separately [PP].
- "Accessories you may need": Split-core CT for CTH01 0–100 A RM215.25 and 0–300 A RM258.30 (both Add to Cart) [PP].
- Frequency: Features list says "Support AS923-1 Frequency Plan (suitable for Malaysia, Singapore and Japan)"; spec block says "Support Malaysia AS923-2, Singapore AS923-1" (see *Conflicts*) [PP].
- Spec block otherwise matches [DS] (SMB antenna, 20 dBm, Class C, 12 RJ11 channels, 12 V DC adapter, 2-pin 5 mm terminal, 4 kVac, 5.8 W, CAT III, IP30). Supported CT ranges listed with wire holes 100 A Ø16, 300 A Ø24, 500 A Ø36, 1000 A Ø50 mm [PP].
- **Packing list:** CTH01, power adapter, power terminal wire, power terminal block, 2 × mounting screw kits, voltage terminal block, LoRaWAN magnetic antenna, USB-C NTC sensor, 4 × magnetic voltage measuring cables, 2 × magnetic nuts (optional), warranty card, quick guide [PP] (same as [UM]).
- Resources: CTH01 datasheet and user guide (Google Drive links), payload decoder (GitHub Milesight-IoT/SensorDecoders), Milesight firmware page [PP].
- Page tags mention "BACnet Modbus"; neither protocol is in the datasheet (see *Needs verification*) [PP].

## Interfaces, terminals and pin mapping
| Interface | Detail | Src |
|---|---|---|
| Power interface | 2-pin 5 mm terminal block, 12 V DC from the included DIN-rail AC–DC adapter (adapter output → power terminal wire → CTH01); adapter input wired to a breaker in the board | [DS][UM] |
| Voltage channels | 4 voltage terminals (L1, L2, L3, N) on a removable push-button (orange button) terminal block on top; AWG 26–12 | [DS][UM][PP] |
| Current channels | 12 × RJ11, numbered Ch1–Ch12 in groups a/b/c/d of three | [DS][UM] |
| USB Type-C | USB-C NTC cable-temperature sensor | [DS][UM] |
| Antenna | SMB female, push-on ("click") | [DS][UM] |
| Reset button | Hold > 10 s = factory reset | [UM] |
| LED | On = power on; red solid = de-activated (not joined); red quick blink once = join request; red slow blink once = joined; green solid = normal; red quick blink = threshold alarm; quick blink = factory reset | [UM] |

**Voltage-to-current channel mapping (must be followed)** [UM]:
| Voltage | Must use current channel |
|---|---|
| L1 | 1st channel of any group: Ch1, Ch4, Ch7, Ch10 |
| L2 | 2nd channel of any group: Ch2, Ch5, Ch8, Ch11 |
| L3 | 3rd channel of any group: Ch3, Ch6, Ch9, Ch12 |

Wiring diagrams are given for three-phase four-wire, three-phase three-wire and single-phase two-wire (L–N); the drawings themselves were not transcribed [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Hazardous voltage. Only qualified electricians install it.** Turn off and lock out all supplies; after power-off wait at least 5 minutes for capacitors to discharge; use insulated tools and gloves; treat voltage lines as live even after power-off [UM].
- **Ensure the breaker is powered off during installation** [UM]. This applies to the voltage taps and adapter wiring; Cytron's copy says CTs install "without power interruptions" (see *Conflicts*).
- **Match voltage phase to current channel position.** L1 voltage with a Ch2 CT still shows V and I but PF, power and energy are wrong [UM].
- **Three-phase circuits must use the 3 channels of one group** (e.g. Ch1–Ch3 of group a for L1–L3) [UM].
- **Rogowski coils:** if one channel in a group uses a Rogowski coil, all three must. Setting a channel to 4000 A sets the other two in the group to 4000 A too [UM].
- **CT direction:** the arrow on the clamp points to the load side. A reversed CT gives negative current; it can be corrected in ToolBox ("Current Direction") or by downlink instead of re-wiring [UM].
- **Set the channel current range in ToolBox to the clamp fitted** (None / 100 / 300 / 500 / 1000 / 4000 A) [UM].
- **Close each clamp until it clicks, centre the conductor, push RJ11 plugs fully home.** Label CT cables by circuit [UM].
- **Wire the adapter exactly as the diagrams show**; incorrect upper/lower terminal wiring may damage the device [UM].
- **Antenna outside the metal board**, vertical, high; the magnetic base can sit on the board exterior [UM].
- Bluetooth: one phone at a time; disconnects after 3 min idle [UM].
- **CT secondary:** neither document gives a "do not open the CT secondary under load" instruction; the CT options are rated for RJ11 connection to the hub. Plug/unplug CTs with the clamp off the conductor or the circuit de-energized (inferred from general CT practice — see *Needs verification*).

## Power and electrical limits
- Supply: 12 V DC from the included AC–DC adapter, into a 2-pin 5 mm terminal block with reverse-polarity protection; max 5.8 W [DS].
- Voltage inputs: 100–500 V AC measuring range; max 290 Vrms N–L and 500 Vrms L–L; overvoltage category III; pollution degree 2; up to 2000 m [DS].
- Insulation 4 kVac rms (1 mA / 1 min) [DS].
- Current: up to 4000 A via the chosen CT/coil; split-core CTs class 0.5, ±2 % (CT table) [DS].
- Environment: -20 ~ 70 °C, ≤ 95 % RH, IP30, indoor only; do not block air circulation [DS][UM].

## Software support
- **Milesight ToolBox app** (Android/iOS) over Bluetooth: LoRaWAN settings, reporting interval, data storage and retransmission, time zone/sync, voltage wiring (3P4W / 3P3W), current circuit type, channel ranges and direction, calibration, thresholds [UM].
- Time sync from the network server needs LoRaWAN V1.0.3; DeviceTimeReq every 5 days [UM].
- Data storage and retransmission after network loss (default retransmission interval 600 s) [UM].
- Downlink commands for all settings (e.g. current interface: type, direction and range per channel) [UM].
- Milesight Development Platform (OTAA required) and third-party LoRaWAN platforms [DS][UM]. Decoders: github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- **CTs not included.** Use Milesight RCT-RJ11 split-core CTs: `milesight-cth01-ct-clamps.md` (Cytron sells 100 A and 300 A) [PP].
- Gateway: Class C needs a LoRaWAN gateway/network server on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`.
- For a simpler self-powered current-only sensor see `milesight-ct10x.md`.
- Mounting: standard 35 mm DIN rail, or magnetic nuts on a steel back plate [UM].

## Common mistakes / troubleshooting
- **Wrong power/energy but sensible V and I:** voltage phase and CT channel position do not match [UM].
- **Negative current:** CT arrow points away from the load; fix with Current Direction in ToolBox [UM].
- **Red LED solid:** not joined to the network [UM].
- **Mixed coil types in a group:** not allowed with Rogowski coils [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Frequency plan for Malaysia | [PP] Features: "AS923-1 … suitable for Malaysia, Singapore and Japan" | [PP] Specifications: "Malaysia AS923-2, Singapore AS923-1" | Internal Cytron conflict. [DS] lists AS923-1&2&3&4 for the model. Confirm the plan with the gateway/network operator |
| Installation with power on | [PP] "clamp around conductors … ensuring no power interruptions" | [UM] "Ensure the breaker is powered out during the installation"; turn off and lock out all power | [UM] wins for the hub install. Safety-critical |
| CT wire-hole sizes | [PP] 500 A Ø36 mm, 1000 A Ø50 mm | [DS] 500 A Ø36.6 mm, 1000 A Ø51 mm | [DS] wins |
| Sampling | [PP] "8 kHz high-speed sampling" | [DS] 6 – 8 kHz | [DS] wins |
| Modbus/BACnet | [PP] page tags | [DS] no Modbus or BACnet | [DS]: LoRaWAN only. Tags are not a spec |

## Needs verification
- AC input range of the included power adapter (not stated in [DS]/[UM] text).
- Whether CTs may be unplugged from the RJ11 port while clamped on a live conductor (no statement found).
- Which AS923 sub-plan Cytron's `CTH01-915M` units ship with for Malaysia.
- The 1000 A CT dimensions in the datasheet table are garbled in the text layer ("9631 × 595 × 119 mm"); likely 96.31 × 59.5 × 119 mm (inferred).
- Wiring diagram details (figure-only in [UM]).

## Sources
- [DS] CTH01 Datasheet: https://resource.milesight.com/milesight/iot/document/cth01-datasheet-en.pdf (read 2026-10-21).
- [UM] CTH01 User Guide V1.0 (20 Mar 2026): https://resource.milesight.com/milesight/iot/document/cth01-user-guide-en.pdf
- [VEN] Milesight CTH01 product page: https://www.milesight.com/iot/product/lorawan-sensor/cth01
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-cth01-lorawan-smart-power-monitor-hub (read 2026-10-21). Cytron's resource links (Google Drive, not opened): datasheet (Cytron document — link not public) user guide (Cytron document — link not public)
- [VEN] Payload decoders: https://github.com/Milesight-IoT/SensorDecoders
