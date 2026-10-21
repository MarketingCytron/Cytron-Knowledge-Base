# Milesight WT304 LoRaWAN Smart Fan Coil Thermostat (with display) — Verified Reference

| | |
|---|---|
| Product code | `WT304` (Milesight model, WT30x series with `WT303`) [DS]. Cytron code `LR-WT304`, MPN `WT304-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specification, packing list, resources), Milesight WT303/WT304 product page, WT303&304 datasheet (in full, WT304 wiring diagrams rendered as images) and WT30x user guide V1.1 (safety, compatibility table, packing, LED patterns, installation, general and installation settings, screen protection) read |
| Primary source | Milesight *WT303&304 Datasheet* (PDF, file dated 17 Jul 2026), https://resource.milesight.com/milesight/iot/document/wt303-wt304-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight WT303&304 datasheet PDF (7 pages; PDF created 17 Jul 2026). The terminal names below come from the WT304 wiring diagram (DS p4 "2-pipe, 0-10V valve, 3 speed fan"), rendered and read as an image. [UM] = Milesight *WT30x User Guide* PDF (`wt303-wt304-user-guide-en.pdf`, 96 pages, V1.1 of 4 Aug 2025; PDF revised 20 Oct 2025); its wiring figures were not read. [VEN] = Milesight WT303/WT304 product page. [PP] = Cytron product page.

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Compatibility (WT304) | 2-pipe FCUs: 3-speed fans with a 0–10 V proportional valve; EC fans (0–10 V) with a 2-wire or 3-wire on/off motorized valve or 0–10 V proportional valve. 4-pipe FCUs: 3-speed fans with a 0–10 V proportional valve; EC fans with a 2-wire on/off motorized valve | [DS][UM] |
| Valve & fan relay | Resistive 4 A, inductive 3 A; capacitive loads not supported | [DS] |
| Temperature control range | 5 °C to 35 °C | [DS] |
| Control modes | Heat, Cool, Ventilation | [DS] |
| Fan modes | Low, Medium, High, Auto | [DS] |
| Inputs | 1 × 10 kΩ ±1 % 3950 NTC input; 1 × DI (dry contact) for key-card or magnet switches (physical switches/buttons only) | [DS] |
| Advanced (thermostat) | Local control schedule (8 plans × 16 schedules), freeze protection, open-window detection, fan delay, temp. control and dehumidify | [DS] |
| Temperature sensor | Digital CMOSens (MEMS); -20 to 60 °C; ±0.5 °C (0–60 °C), ±1 °C (-20–0 °C); 0.1 °C resolution | [DS] |
| Humidity sensor | Digital CMOSens (MEMS); 0–100 %RH; typ. ±2 %RH, max ±5 %RH; 0.1 %RH resolution | [DS] |
| Protocol | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal antennas | [DS] |
| Frequency plans | CN470/EU868/RU864/IN865/AU915/US915/KR920/AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 19 dBm (470 MHz) / 22 dBm (915 MHz) | [DS] |
| Sensitivity | -137 dBm | [DS] |
| Mode | OTAA/ABP **Class C** | [DS] |
| Display | 2.7-inch black & white e-ink | [DS] |
| Buttons | 5 external buttons: FCU system on/off, temperature up/down, control-mode switch, fan-mode switch, reboot and reset | [DS] |
| LED | 1 × reset/reboot indicator | [DS] |
| USB | 1 × Type-C port for console | [DS] |
| Configuration | NFC via mobile app or downlink | [DS] |
| Advanced (software) | Threshold alarm, child lock, multicast, Milesight D2D controller, D2D agent, external sensor mode, D2D sensor data receiving, FUOTA; BACnet via Milesight LoRaWAN gateways | [DS] |
| Reporting interval | 1 – 1440 min, default 10 min | [UM] |
| Power supply | 100–240 VAC, 50–60 Hz | [DS] |
| Power consumption | < 2 W (without loads) | [DS] |
| Operating temperature | -20 °C to 60 °C (e-ink screen: 0 °C to 40 °C) | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Ingress protection | IP20 | [DS] |
| Colour & material | White, PC + ABS (UL94 V0) | [DS] |
| Dimensions | 86 × 86 × 42 mm | [DS] |
| Wire connection | AWG 14–26 | [DS] |
| Installation | 86 mm square or European 60 mm round box; 118 or 120 wall box via optional wall plate | [DS] |
| Approvals | CE, FCC | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WT304 LoRaWAN Smart Fan Coil Thermostat (with display)", code `LR-WT304`, MPN `WT304-915M`, RM516.60, "Availability: Enquiry" (Inquire Now), warranty 12 months; no variants [PP].
- Spec block: 2-pipe and 4-pipe FCUs; 0–10 V proportional valves and 2/3-wire on/off valves; 3-speed or EC (0–10 V) fans; 5–35 °C; heat/cool/ventilation; relay 4 A resistive / 3 A inductive; built-in temperature -20 to 60 °C (±0.5) and humidity 0–100 % (±2 %); 10 kΩ B3950 NTC input; DI dry contact; LoRaWAN Class C + D2D; "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1"; "Configuration: NFC via Mobile App, Downlink, or USB Type-C Console Port"; FUOTA, threshold alarms, child lock, multicast, fan delay; 100–240 VAC; "Power Consumption: < 2 (without external loads)"; 2.7-inch e-ink; 5 buttons; IP20 PC+ABS UL94 V0; 86 mm square / 60 mm round / 118/120 boxes via optional plate; 86 × 86 × 42 mm [PP].
- **Packing:** 1 × smart fan coil thermostat, 2 × wall mounting screws (M4×25), 1 × 2-pin signal cable, 1 × anti-theft fixing screw (M2×4), 1 × quick guide, 1 × warranty card [PP]. The [UM] lists an NTC temperature sensor and a wall plate kit as optional extras (not in Cytron's list).
- **Resources:** WT30x datasheet, user guide, payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware page [PP].

## Interfaces, terminals and pin mapping
Mains terminal block on the back (top → bottom as drawn in the WT304 diagram) [DS]:
| Terminal | Function |
|---|---|
| N | Neutral, 100–240 VAC 50/60 Hz |
| L | Live, 100–240 VAC 50/60 Hz (also the common feed for the relays) |
| Q1 | Relay output — fan Low (3-speed fan) |
| Q2 | Relay output — fan Medium |
| Q3 | Relay output — fan High (in EC-fan diagrams Q3 is drawn as the fan "Power" feed) |
| AO1 | 0–10 V analog output — cooling/heating valve (2-pipe) |
| AO2 | 0–10 V analog output — second valve (4-pipe) or EC fan speed (inferred from the diagrams) |
| GND | Analog ground for the 0–10 V outputs |
Low-voltage 3-pin socket (separate, drawn as **GND, DI, NTC**) for the supplied 2-pin signal cable (DI) and the optional NTC probe [DS][PP].
The relays switch L to Q1–Q3 (drawn as switches from L); the fan's other side goes to N [DS].

**DI behaviour** [UM]: key card — card inserted = DI and GND connected; card removed = open. Magnetic contact — selectable NO or NC type.

**Buttons / LED** [UM]: hold buttons 1 and 3 > 3 s = reboot (LED slowly blinks); > 10 s = reset (LED quickly blinks). Button 1 = increase target temperature (rest of the button map not copied).

## Rules and gotchas (for code, wiring and tutorials)
- **Mains device:** a qualified person installs it; power off first; insulate and secure unused wires [UM].
- **Relay limits:** 4 A resistive / 3 A inductive per relay; **capacitive loads not supported** [DS][UM].
- **After wiring, select the System Type** (2-pipe/4-pipe, valve type, fan type) and enable DI in ToolBox or by downlink — the thermostat will not drive the right outputs otherwise [UM].
- WT304 for EC fans: set the 0–10 V percentage for Low/Medium/High in Installation Settings [UM].
- **Mount 1.5 m above the floor**, away from sun, ducts, drafts and metal objects when using the built-in sensor; otherwise choose another data source (NTC, Milesight sensor via D2D, or network-server data) [UM].
- **E-ink screen works 0–40 °C**: outside that for 6 readings, the screen turns off and buttons lock until the temperature returns (internal sensor used) [UM].
- Freeze protection can turn heating on even when the system is off [UM].
- Class C: always listening; reporting interval default 10 min [DS][UM].
- Wire size AWG 14–26 [DS].

## Power and electrical limits
- 100–240 VAC, 50–60 Hz; < 2 W without loads [DS].
- Relays: 4 A resistive / 3 A inductive; no capacitive loads [DS].
- 0–10 V outputs for valve and EC fan [DS].
- NTC: 10 kΩ ±1 %, B3950 [DS].
- -20 to 60 °C (screen 0–40 °C), IP20, indoor [DS].

## Software support
- Milesight ToolBox app over NFC; downlinks; FUOTA [DS][UM].
- Milesight Development Platform; BACnet object list via Milesight LoRaWAN gateways [DS][UM].
- D2D: controller, agent and receiving sensor data from Milesight sensors (external sensor mode) [DS].
- Decoder: https://github.com/Milesight-IoT/SensorDecoders [PP].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` (BACnet is via Milesight gateways) [DS][PP].
- Door/window contact for open-window detection: any dry-contact magnetic switch on the DI [UM].
- Optional NTC probe and wall plate kit (for 118/120 boxes) are Milesight accessories, not in Cytron's packing list [UM][PP].

## Common mistakes / troubleshooting
- **Fan or valve does nothing after wiring:** System Type not set to match the wiring [UM].
- **Screen blank, buttons dead:** room outside 0–40 °C (over-temperature protection) [UM].
- **Wrong room temperature:** poor mounting spot; use NTC or another data source [UM].
- **Relay damage:** capacitive or oversized load [DS].
- **Reset:** hold buttons 1 and 3 > 10 s, or ToolBox Reset [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Configuration via USB | [DS] configuration: NFC or downlink; USB Type-C "for console" | [PP] "NFC via Mobile App, Downlink, or USB Type-C Console Port" | [DS] wins: configure by NFC or downlink; USB is a console port |
| Power consumption unit | [DS] < 2 W (without loads) | [PP] "< 2 (without external loads)" | [DS]: < 2 W |
| Stock | [PP] catalogue card OUT OF STOCK | [PP] product page "Availability: Enquiry" | Order by enquiry |

## Needs verification
- Which 0–10 V output (AO1/AO2) drives the EC fan in each EC-fan diagram; and the 4-pipe valve allocation (cooling vs heating) — the [UM] figures were not read.
- [UM] magnetic contact table lists "DI and GND connected = door/window open" for both NO and NC — check the actual logic before writing a tutorial.
- Pin order of the 3-pin low-voltage socket (drawn GND, DI, NTC) and wire colours of the 2-pin signal cable.
- LoRaWAN plan pre-set on Cytron's `WT304-915M` (Cytron says Malaysia AS923-2 / Singapore AS923-1).

## Sources
- [DS] WT303&304 Datasheet: https://resource.milesight.com/milesight/iot/document/wt303-wt304-datasheet-en.pdf (PDF 17 Jul 2026)
- [UM] WT30x User Guide: https://resource.milesight.com/milesight/iot/document/wt303-wt304-user-guide-en.pdf (V1.1, 4 Aug 2025; PDF revised 20 Oct 2025)
- [VEN] Milesight WT303/WT304 page: https://www.milesight.com/iot/product/lorawan-sensor/wt303-wt304
- [PP] Cytron: https://my.cytron.io/Milesight/p-wt304-lorawan-smart-fan-coil-thermostat-with-display (read 2026-10-21)
