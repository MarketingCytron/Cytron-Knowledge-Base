# Milesight UC512 LoRaWAN Solenoid Valve Controller — Verified Reference

| | |
|---|---|
| Product code | `UC512` (Milesight model, UC51x series) [DS]. Cytron code `LR-UC512-DI`, MPN `UC512-DI-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specification, packing list, resources), Milesight UC51x product page, UC51x series datasheet (in full) and UC51x series user guide V4.3 (revision history, hardware, pin tables, power, installation, general/GPIO/rule settings) read |
| Primary source | Milesight *UC51x Series Datasheet* (PDF, file dated 23 Apr 2026), https://resource.milesight.com/milesight/iot/document/uc51x-series-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UC51x Series datasheet PDF (covers UC511 and UC512 and their EA / AI versions; 7 pages; PDF created 23 Apr 2026). [UM] = Milesight *UC51x User Guide* PDF (`uc51x-series-user-guide-en.pdf`, 87 pages, V4.3 of 30 Apr 2026, hardware 4.x). Pin tables were taken from the PDF text. [VEN] = Milesight UC51x product page. [PP] = Cytron product page.

## What it is
Cytron sells the internal-antenna unit `UC512-DI-915M` [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | LoRaWAN® (UC512; Milesight D2D is UC511 only) | [DS] |
| Antenna | Internal antenna or external antenna (hardware option); EA version 1 × 50 Ω SMA female. Cytron unit: internal | [DS][PP] |
| Frequency plans | CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @300bps | [DS] |
| Working mode | OTAA/ABP, **Class A, Class B** (UC512) | [DS][UM] |
| Interface type | M12 A-coded male | [DS] |
| Solenoid interface | 2 × solenoid interfaces; 2-wire **DC 12 V latching** solenoids; cable length 1.5 m (by default) | [DS] |
| GPIO interface | 2 × digital inputs; logic low 0–0.8 V, high 2.5–3.3 V; max current 20 mA; digital input or pulse counter; suggested ≤ 4000 Hz | [DS] |
| Pressure interface | AI version only (PS02 sensor for UC512) — not the Cytron unit | [DS] |
| Button / USB / LED | 1 × power/reset button (internal); 1 × Type-C (internal) for console; 1 × reboot/reset LED (internal) | [DS] |
| Power on/off | Mobile app via NFC, power button (internal), cable connection ("wiring switch") | [DS][UM] |
| Configuration | Mobile app via NFC (ToolBox PC software removed in UG V4.1) | [DS][UM] |
| Advanced features | Multicast, local rules (max 16), water pressure alarm (AI version), FUOTA | [DS][UM] |
| Reporting interval | 1 – 1080 min, default 360 min | [UM] |
| Power supply | 3 × 9000 mAh replaceable ER26500 Li-SOCl2 batteries | [DS] |
| Battery life (20 min interval, valve controlled 4×/day, 25 °C) | Class A > 10 years; Class B around 6.2 years (SF7), around 5.8 years (SF10) | [DS] |
| Operating temperature | -30 °C to 70 °C | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Ingress protection | IP68 (1 m underwater, 7 days) | [DS] |
| Dimensions | 116 × 116 × 45.5 mm (connectors excluded) | [DS] |
| Weight (with batteries) | Internal-antenna version 479 g; EA version 521 g | [DS] |
| Installation | Wall or pole mounting | [DS] |
| Approvals | CE, FCC; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UC512 LoRaWAN Solenoid Valve Controller", code `LR-UC512-DI`, MPN `UC512-DI-915M`, RM731.85, "Availability: Enquiry" (Inquire Now), warranty 12 months; no variants [PP].
- Spec block: internal antenna; "Frequency: Support Malaysia AS923-2, Singapore AS923-1"; Tx 16/20/19 dBm; -137 dBm; OTAA/ABP Class A, Class B; M12 A-coded male; 2 × solenoid (2-wire DC 12 V latching, 1.5 m cable); 2 × DI dry contact (0–0.8 V / 2.5–3.3 V, 20 mA, ≤ 4000 Hz); internal power/reset button, Type-C console, LED; NFC configuration; multicast, local rules; 3 × 9000 mAh ER26500; battery life Class A > 10 years, Class B ~6.2 years (SF7) / ~5.8 years (SF10); -30 to 70 °C; IP68; 116 × 116 × 45.5 mm; 479 g [PP].
- Description/features: up to 2 DC 12 V latching valves, 2 dry-contact DIs for pulse water meters or valve status, "time-based, volume-based, and moisture-based irrigation", 16 schedule events, water-flow alarms, rain-delay irrigation, multicast [PP].
- **Packing:** 1 × UC51x device, 2 × 1.5 m M12 data cables, 1 × mounting bracket, 4 × wall mounting kits, 1 × fixing screw, 2 × hose clamps, 1 × warranty card, 1 × quick guide card [PP][UM].
- **Resources:** UC511/UC512 datasheet, user guide, firmware page [PP].

## Interfaces, terminals and pin mapping
Two "Solenoid & Pulse" M12 interfaces (interface 1 = valve 1 + GPIO1, interface 2 = valve 2 + GPIO2; inferred from the per-interface table and "Interface 1 Only / Interface 2 Only" reporting option). Each is wired through the supplied 1.5 m M12 data cable with bare wires at the far end [UM].

**Solenoid & Pulse Interface** (per M12 connector) [UM]
| Pin | Function |
|---|---|
| 1 | DC+/OUT1 of solenoid valve |
| 2 | DC-/OUT2 of solenoid valve |
| 3 | GND |
| 4 | INSERT BOOT (as printed in the UG) |
| 5 | GND |
| 6 | GPIO interface |

AI interface and DC power connector exist only on AI / UC511-EA versions, not on Cytron's UC512 [UM].

**Power button (internal)** [UM]: long press 3 s = on/off; 10 s = reset (LED blinks); short press shows on/off state.

## Rules and gotchas (for code, wiring and tutorials)
- **Only DC 12 V latching (bistable) solenoids, 2-wire.** A normal (non-latching) 12/24 VDC or AC solenoid will not work: the controller pulses the coil and the valve holds its state [DS].
- Valve wiring: solenoid wires to pins 1 and 2 (polarity reverses to open/close). Water meter pulse or valve-feedback contact between pin 6 (GPIO) and GND (pin 3 or 5) — dry contact (inferred from "dry contact" [PP] and pin table [UM]).
- **Insulate unused wires** of the data cable and waterproof the bare-wire joints outdoors [UM].
- **"Wiring Switch"**: if enabled, plugging a data cable into a solenoid interface turns the device on [UM].
- **Class A downlink latency:** valve commands wait for the next uplink; set "Response Time" (0–64800 s) so the device opens a receive window regularly, at a battery cost; or use Class B [UM].
- Class B falls back to Class A after 120 min without beacons [UM].
- "When power is restored": Last working status / Device on, valve off / Device on, valve on [UM].
- Pulse counter (water volume counter) survives reboot/rejoin, rolls over at 4294967295 [UM].
- **Batteries:** ER26500 Li-SOCl2 only, not alkaline; always new cells; correct polarity [UM].
- Data storage / retransmission were removed in UG V4.2 (only on firmware before V1.4) [UM].
- Refit the back cover in crisscross order to 4.5–5 kgf·cm to keep IP68 [UM].

## Power and electrical limits
- 3 × 9000 mAh ER26500 Li-SOCl2 (replaceable, primary). No solar panel and no DC input on UC512 [DS][UM].
- Solenoid drive: for 2-wire DC 12 V latching solenoids [DS]; maximum coil current/pulse energy [NOT STATED].
- DI: 3.3 V logic, 20 mA max [DS].
- -30 to 70 °C, IP68 [DS].

## Software support
- Milesight ToolBox app over NFC (Android and iOS) for configuration, valve on/off, time sync, rules and upgrades [UM].
- FUOTA (UG V4.2+), downlink command set for valves, GPIO, rules, multicast and work-mode switching [UM].
- Milesight IoT Cloud / Milesight Development Platform for time and flow control [DS].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- Other Milesight controllers sold by Cytron: `milesight-uc501.md`, `milesight-uc502.md`, `milesight-uc300.md`, `milesight-uc100.md` [VEN].
- Soil sensing for irrigation decisions: `milesight-em500-smtc.md` (via network server or cloud rules; inferred).
- Valves, pulse water meters and PS02 pressure sensors are not included [PP].

## Common mistakes / troubleshooting
- **Valve does not move:** non-latching or wrong-voltage solenoid; check 2-wire DC 12 V latching type [DS].
- **Remote command delayed hours:** Class A with Response Time = 0 — set a response time or Class B [UM].
- **Water count jumps:** set the pulse filter; check meter contact is dry [UM][PP].
- **Device turned itself on in storage:** Wiring Switch enabled and a cable plugged in [UM].
- **Factory reset:** internal power button 10 s, or ToolBox app reset [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Moisture-based irrigation | [DS][UM] rules: time, water volume, D2D (UC511); no soil-moisture input | [PP] "time-based, volume-based, and moisture-based irrigation" | Not a built-in function; moisture logic would run on a server/cloud with a separate sensor (Needs verification) |
| MPN "DI" suffix | [DS] versions UC512, UC512 (EA), UC512 (AI), UC512 (EA-AI) | [PP] MPN `UC512-DI-915M` | Treat as the standard internal-antenna UC512 with DI (GPIO) interfaces; confirm with Milesight |
| Stock | [PP] catalogue card OUT OF STOCK | [PP] product page "Availability: Enquiry" | Order by enquiry |

## Needs verification
- Meaning of the "DI" in Cytron's MPN `UC512-DI-915M` and the hardware version shipped (UG V4.x covers hardware 4.x).
- Solenoid pulse voltage/duration and max coil current.
- Pin 4 "INSERT BOOT" function, and M12 data-cable wire colours.
- LoRaWAN plan pre-set on Cytron's unit (Cytron says Malaysia AS923-2 / Singapore AS923-1).

## Sources
- [DS] UC51x Series Datasheet: https://resource.milesight.com/milesight/iot/document/uc51x-series-datasheet-en.pdf (PDF 23 Apr 2026)
- [UM] UC51x User Guide: https://resource.milesight.com/milesight/iot/document/uc51x-series-user-guide-en.pdf (V4.3, 30 Apr 2026)
- [VEN] Milesight UC51x page: https://www.milesight.com/iot/product/iot-controller/uc51x
- [PP] Cytron: https://my.cytron.io/Milesight/p-uc512-lorawan-solenoid-valve-controller (read 2026-10-21)
