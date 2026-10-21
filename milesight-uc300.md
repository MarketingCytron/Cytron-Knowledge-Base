# Milesight UC300 IoT Controller — Verified Reference

| | |
|---|---|
| Product code | `UC300` (Milesight model; series models `UC300-470M/868M/915M` LoRaWAN, `UC300-L0xx` cellular) [DS]. Cytron codes `LR-UC300` (LoRaWAN, MPN `UC300-915M`) and `LR-UC300-LTE` (cellular, MPN `UC300-L05EU`); parent listing code `V-LR-UC300` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both versions: code, MPN, price, stock; description, specification, packing list, FAQ, resources), Milesight UC300 product page (downloads), UC300 series datasheet (in full) and UC300 LoRaWAN user guide (hardware, wiring-example figures, LED, installation, operation guide to IF-THEN) read |
| Primary source | Milesight *UC300 Series Datasheet* (PDF, file dated 7 Nov 2025), https://resource.milesight.com/milesight/iot/document/uc300-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UC300 Series datasheet PDF (5 pages, no revision printed; PDF created 7 Nov 2025). [UM] = Milesight *UC300 (LoRaWAN®) User Guide* PDF (`uc300-lora-user-guide-en.pdf`, 32 pages; PDF dated 17 Oct 2025). The wiring examples in [UM] §2.3 are figures; they were rendered and read as images. [VEN] = Milesight UC300 product page. [PP] = Cytron product page (its specification block and FAQ). The cellular user guide and the cellular communication protocol were not read.

## What it is
Cytron sells two versions on one page: **LoRaWAN** (`UC300-915M`) and **Cellular 3/4G LTE** (`UC300-L05EU`) [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Interface type | 3.5 mm terminal block | [DS] |
| Digital I/O | 4 × DI + 2 × DO | [DS] |
| Digital input | Opto-isolated, 3–24 VDC; work mode digital input or pulse counter; input frequency ≤ 4000 Hz | [DS] |
| Digital output | SPDT relay, contact rating max 3 A @ DC 30 V or AC 250 V | [DS] |
| Serial ports | 1 × RS232 + 1 × RS485 | [DS] |
| Baud rate | 1200 – 115200 bps (1200/2400/4800/9600/14400/19200/38400/57600/115200) | [DS][UM] |
| Serial protocols | RS232: transparent; RS485: transparent, Modbus RTU | [DS] |
| Modbus | Reads 32 Modbus registers / up to 32 Modbus devices (32 channels); quantity fixed at 1 register per channel in the LoRaWAN UG | [DS][UM] |
| Analog input | 2 × 4–20 mA + 2 × 0–10 V, 12-bit; accuracy 4–20 mA ±5 %, 0–10 V ±1 % | [DS] |
| RTD input | 2 × PT100, 2- or 3-wire, 12-bit, range -200 °C to 800 °C | [DS] |
| LoRaWAN | LoRaWAN®, Milesight D2D; CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4; Tx 16 dBm (868) / 20 dBm (915) / 19 dBm (470); sensitivity -137 dBm @300bps; OTAA/ABP Class C | [DS] |
| Cellular version | 4G LTE (Cat 1)/WCDMA/GSM (differs by region); 1 × Micro SIM (3FF) 1.8 V/3 V; TCP/UDP/MQTT/AWS/Milesight IoT Cloud/SMS | [DS] |
| Antenna connector | 1 × 50 Ω SMA (centre pin SMA female) | [DS] |
| Configuration port | 1 × USB Type-C for power supply, configuration and console | [DS] |
| Button | 1 × reset button (internal) | [DS] |
| LEDs | 1 × System (SYS), 1 × ACT | [DS][UM] |
| Power connector | 1 × 3.5 mm 2-pin terminal block, surge protection and reverse-polarity protection | [DS] |
| Power supply | 1. 5–24 VDC by terminal block; 2. 5 V by Type-C USB | [DS] |
| Advanced features (LoRaWAN) | Threshold alarm, data storage, data retrievability, data retransmission, Milesight D2D controller and agent, IF-THEN command | [DS] |
| Advanced features (cellular) | Threshold alarm, IF-THEN command | [DS] |
| IF-THEN | Up to 16 commands; up to 2 conditions and 3 actions per command | [UM] |
| Reporting interval | 1 – 1080 min, default 20 min (RS232 data does not follow it) | [UM] |
| Operating temperature | -20 °C to 60 °C | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Case | Black, metal; IP30 | [DS][PP] |
| Weight | 142.3 g (LoRaWAN) / 186 g (cellular) | [DS] |
| Dimensions | 93 × 70 × 22 mm (antenna connector excluded) | [DS] |
| Installation | Desktop, wall mounting, DIN rail mounting | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UC300 IoT Controller (RS485, RS232, DI, DO to LoRaWAN)", warranty 12 months, option "Version": Cellular / LoRaWAN® [PP].
- LoRaWAN: code `LR-UC300`, MPN `UC300-915M`, RM602.70, availability 51, Add to Cart. Cellular: code `LR-UC300-LTE`, MPN `UC300-L05EU`, RM904.05, "Availability: Enquiry", Inquire Now. (The parent page, before a version is chosen, shows "Availability: 51" with a "NOTIFY ME!" button; the Cytron catalogue card showed OUT OF STOCK.) [PP]
- Cytron spec block: LoRaWAN version "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1"; Tx power 22 dBm (915 MHz); DI 3–24 VDC with pulse counter; DO SPDT relay 3 A @ DC 30 V / AC 250 V; RS485 Modbus RTU, RS232 transparent; 2 × 4–20 mA + 2 × 0–10 V; 2 × PT100 2/3-wire -200 to 800 °C; Type-C; SYS and ACT LEDs; watchdog and timer; 5–24 VDC; black metal IP30; 93 × 70 × 22 mm [PP].
- Features text: "Supports connectivity with up to 32 channels … Note: The cellular version supports only 16 channels" [PP].
- **Packing:** 1 × UC300 (chosen version), 1 × antenna, 1 × power adapter, 5 × terminal blocks, 1 × DIN rail mounting clip, 1 × wall mounting bracket, 4 × wall mounting kits, 4 × fixing screws [PP]. The [UM] adds 1 × quick start guide and 1 × warranty card.
- **Resources:** datasheet, LoRaWAN user guide, cellular user guide, payload decoder (GitHub Milesight-IoT/SensorDecoders), firmware download, cellular communication protocol [PP].
- **FAQ:** D2D works while joined to a gateway; DO wired straight to DI does not work (see Milesight's DI/DO wiring note); one command per downlink on UC300-LoRa; cellular version can be configured by SMS or server; pulse counts are not kept through power loss [PP].

## Interfaces, terminals and pin mapping
Terminal positions from the [UM] hardware overview: **front face** (top → bottom) PT100, 0–10V, 4–20mA, RS485/RS232, DC power interface; **other face** DO block and DI block; Type-C console port and LED on top; SMA antenna connector on the top end [UM].

Pin tables below are read from the [UM] §2.3 wiring-example figures [UM].

**DI** (per input, 2 pins): pin 1 = −, pin 2 = +. Both the "dry contact" and "wet contact" examples use an **external 0–24 VDC source**: dry contact = switch in series with the source across −/+; wet contact = source directly across −/+ [UM].

**DO** (per relay, 3 pins): 1 = COM, 2 = NC, 3 = NO. Example load: max 250 VAC / 30 VDC source in series with the load via COM and NO/NC [UM].

**4–20 mA** (4 pins): 1 = +, 2 = −, 3 = +, 4 = − (channel 1 = pins 1/2, channel 2 = pins 3/4; inferred from the labels). **External loop power is needed.** 3-wire sensor: sensor V+ to supply +, sensor signal to pin 1 (+), pin 2 (−) to supply −. 2-wire sensor: supply + → sensor → pin 1 (+), pin 2 (−) → supply − [UM].

**0–10 V** (3 pins): 1 = GND/A, 2 = 0-10V_1, 3 = 0-10V_2. Sensor − to pin 1, sensor + to pin 2 (or 3) [UM].

**PT100** (5 pins): 1 = GND/A, 2 = "1", 3 = "2", 4 = B, 5 = B. 3-wire example: RTD lead A to pin 1, the two B leads to pins 4 and 5. 2-wire example: lead A to pin 1, lead B to pin 4 with pins 4 and 5 bridged [UM]. How channel 2 is selected (pins 2 "1" and 3 "2") is not shown (see *Needs verification*).

**RS232/RS485** (5 pins): 1 = TX, 2 = RX, 3 = GND, 4 = A, 5 = B. RS232: UC300 TX → device RX, RX → device TX, GND → GND. RS485: A → A, B → B [UM].

**RS485 DIP switch** [UM]
| DIP 1 / 2 / 3 | Effect |
|---|---|
| on / off / off | Add 120 Ω resistor between A and B |
| off / on / off | Add pull-down resistor on B |
| off / off / on | Add pull-up resistor on A |

**DC power interface:** 2-pin 3.5 mm block, 5–24 VDC [DS]; polarity order not printed in the [UM] figures.

**LED indications** [UM]
| LED | Status | Meaning |
|---|---|---|
| SYS | Static on | System works (also "static on = system error" in the same table) |
| SYS | Slowly blinks | Fails to acquire data from data interfaces |
| ACT | Off | Not joined |
| ACT | Blinks as requests | Sending join requests |
| ACT | Blinks twice → static on | Joined |
| ACT | Blinks once | Uplink sent |
| ACT | Blinks twice | Uplink failed / downlink received |

## Rules and gotchas (for code, wiring and tutorials)
- **DI needs a voltage, not just a contact.** The UG examples always place an external 0–24 VDC source in the DI loop; the datasheet input range is 3–24 VDC. Do not wire a bare dry contact without a source [UM][DS].
- **Do not wire a UC300 DO straight into a DI** — the relay is a volt-free contact; add a source in the loop (Cytron FAQ) [PP].
- **4–20 mA inputs are passive**: supply the loop from an external source [UM].
- **Relay limits:** 3 A at 30 VDC or 250 VAC per contact [DS].
- **Pulse counter:** up to 4000 Hz; enable the digital filter when the pulse period is > 250 µs; press Start in ToolBox or the counter value will not change; reboot does not reset the count, but **power loss does** [DS][UM][PP].
- DO state after power restore is configurable (normally open / normally closed) [UM].
- **Class C LoRaWAN**, so continuous power. One command per downlink on the LoRaWAN version [DS][PP].
- RS232 is transparent only and uses its own LoRaWAN port (2–84, 86–223), separate from the application port (default 85) [UM].
- Two-way RS485 pass-through disables the Modbus channels and their IF-THEN rules [UM].
- Single-Channel Mode must be enabled for Milesight DS7610 gateways (not sold by Cytron) [UM].
- Analog scaling in ToolBox: Ov = (Osh − Osl) × (Iv − Isl) / (Ish − Isl) + Osl [UM]. PT100 values are always reported in °C [UM].

## Power and electrical limits
- 5–24 VDC on the 2-pin 3.5 mm terminal block (surge and reverse-polarity protected), or 5 V via USB Type-C [DS]. A power adapter is in the box [PP].
- Power consumption: [NOT STATED] in the datasheet.
- DI 3–24 VDC, opto-isolated, ≤ 4000 Hz. DO SPDT relay 3 A @ 30 VDC / 250 VAC [DS].
- No battery; data and pulse counts are lost on power failure [PP].
- Operating -20 to 60 °C, 0–95 %RH non-condensing, IP30 indoor [DS].

## Software support
- Milesight IoT Cloud / Development Platform; any standard LoRaWAN network server [DS].
- Payload decoder: https://github.com/Milesight-IoT/SensorDecoders [PP].
- Firmware upgrade and JSON config backup via ToolBox [UM].
- Cellular version: TCP/UDP/MQTT/AWS/Milesight IoT Cloud/SMS [DS].

## Compatibility and accessories
- LoRaWAN gateways sold by Cytron: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- Battery-powered alternatives: `milesight-uc501.md`, `milesight-uc502.md`; Modbus-only: `milesight-uc100.md`; valve control: `milesight-uc512.md` [PP][VEN].
- PT100 probes, 4–20 mA / 0–10 V sensors and their loop supply are not included [PP].
- DIN rail mounting clip in the box; the UG states the rail width as 3.5 cm (35 mm) [PP][UM].

## Common mistakes / troubleshooting
- **DI never changes:** no source in the DI loop, or source below 3 V [UM][DS].
- **4–20 mA reads 0:** loop not powered from an external supply [UM].
- **RS485 errors:** set DIP 1 on (120 Ω) at bus ends; use DIP 2/3 bias only if the bus has no bias [UM].
- **SYS LED slowly blinking:** a configured interface cannot be read [UM].
- **Counter lost after outage:** expected — no battery backup [PP].
- **Factory reset:** hold the internal reset button > 10 s until SYS blinks rapidly, release and wait [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Tx power at 915 MHz | [DS] 20 dBm | [PP] 22 dBm | [DS] wins: 20 dBm |
| Modbus channels, cellular version | [DS] 32 Modbus devices (no version split) | [PP] "cellular version supports only 16 channels" | Use 32 for LoRaWAN. Cellular limit unconfirmed (cellular UG not read) |
| Stock status | [PP] catalogue card: OUT OF STOCK; parent page "NOTIFY ME!" | [PP] LoRaWAN variant: availability 51, Add to Cart | Variant page wins: LoRaWAN in stock; cellular by enquiry |

## Needs verification
- PT100 terminal: how the "1" and "2" pins select channel 1 vs channel 2, and the full 3-wire wiring for channel 2.
- DC power terminal polarity order (+/−) and DI/DO block pin numbering on the case label.
- Exact LoRaWAN plan pre-set on Cytron's `UC300-915M` units (Cytron page says "Malaysia AS923-2, Singapore AS923-1").
- Power consumption.
- Cellular version (`UC300-L05EU`) LTE bands and suitability for Malaysian networks (the suffix suggests an EU-band module; inferred).

## Sources
- [DS] UC300 Series Datasheet: https://resource.milesight.com/milesight/iot/document/uc300-datasheet-en.pdf (PDF 7 Nov 2025)
- [UM] UC300 (LoRaWAN®) User Guide: https://resource.milesight.com/milesight/iot/document/uc300-lora-user-guide-en.pdf (PDF 17 Oct 2025)
- [VEN] Milesight UC300 page: https://www.milesight.com/iot/product/iot-controller/uc300 ; cellular user guide https://resource.milesight.com/milesight/iot/document/uc300-cellular-user-guide-en.pdf (not read)
- [PP] Cytron: https://my.cytron.io/Milesight/p-uc300-iot-controller (variants `…-rs485-rs232-di-do-to-lorawan`, `…-rs485-rs232-di-do-to-3-4g-lte`; read 2026-10-21)
