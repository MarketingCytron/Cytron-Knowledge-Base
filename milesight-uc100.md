# Milesight UC100 IoT Controller (Modbus RTU to LoRaWAN) — Verified Reference

| | |
|---|---|
| Product code | `UC100` (Milesight model). Cytron codes `LR-UC100` (internal antenna, MPN `UC100-915M`) and `LR-UC100-EA` (external antenna, MPN `UC100-915M-EA`); parent listing code `V-LR-UC100` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both antenna variants: code, MPN, price, stock; description, features, packing list, resources), Milesight UC100 product page, UC100 datasheet (in full) and UC100 user guide V2.0 (preface, hardware, operation guide, installation, start of uplink chapter) read |
| Primary source | Milesight *UC100 Datasheet* (PDF, file dated 16 Jun 2025), https://resource.milesight.com/milesight/iot/document/uc100-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UC100 datasheet PDF (4 pages, no revision number printed; PDF created 16 Jun 2025). [UM] = Milesight *UC100 User Guide* PDF (`uc100-ea-user-guide-en.pdf`, 60 pages, latest revision V2.0 of 19 Jun 2025; PDF metadata revised 17 Sep 2025). [VEN] = Milesight UC100 product page (https://www.milesight.com/iot/product/iot-controller/uc100). [PP] = Cytron product page. The hardware-overview figure in the [UM] was viewed as a rendered image; it names the ports but not the terminal pin order.

## What it is
Cytron sells two hardware options: **internal antenna** (`UC100-915M`) and **external antenna "EA"** (`UC100-915M-EA`, with SMA connector and a magnetic LoRaWAN antenna) [PP][UM]. The Cytron page also mentions a cellular (4G LTE) variant in its description, but Cytron only sells LoRaWAN variants (see *Conflicts*) [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Wireless technology | LoRaWAN®, Milesight D2D | [DS] |
| Antenna | Internal antenna or external antenna (hardware option); external: 1 × 50 Ω SMA connector (center pin: SMA female) | [DS] |
| Frequency plans | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 22 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @300bps | [DS] |
| LoRaWAN mode | OTAA / ABP, **Class C** (fixed) | [DS][UM] |
| LoRaWAN version | V1.0.2 and V1.0.3 selectable | [UM] |
| Data port | 1 × RS485 | [DS] |
| RS485 connector | 2-pin 3.5 mm terminal block | [DS] |
| RS485 termination | 1 × 120 Ω resistor switch | [DS] |
| Baud rate | 1200 – 115200 bps (1200/2400/4800/9600/19200/38400/57600/115200) | [DS][UM] |
| Serial format | Data bits 8; stop bits 1 or 2; parity None/Odd/Even | [UM] |
| Protocol | Modbus RTU, Passthrough | [DS] |
| Modbus channels | 32 channels (each reads 1 or 2 registers; types incl. coil, discrete, input/holding register; INT16/INT32/Float/INT64/Double with selectable byte order) | [UM] |
| USB | 1 × Type-C for power supply, configuration and console | [DS] |
| Reset button | 1 × reset button (internal) | [DS] |
| LED | 1 × System | [DS] |
| Power connector | 1 × 3.5 mm 2-pin terminal block, with surge protection and reverse polarity protection | [DS] |
| Power supply | 1. DC 5–24 V by power connector; 2. DC 5 V / 1 A by Type-C port | [DS] |
| Power consumption | < 0.5 W | [DS] |
| Configuration | USB Type-C (Milesight ToolBox) or LoRaWAN downlink | [DS][UM] |
| Advanced features | Threshold alarm, change alarm, data storage (up to 800 entries), data retrievability, data retransmission, Milesight D2D controller and agent, IF-THEN command, FUOTA | [DS] |
| IF-THEN rules | Up to 16 commands, up to 3 actions each | [UM] |
| Reporting interval | 1 – 1080 min, default 20 min | [UM] |
| Material / colour | PC+ABS, white | [DS] |
| Weight | 32 g | [DS] |
| Ingress protection | IP30 | [DS] |
| Operating temperature | -20 °C to 60 °C | [DS] |
| Relative humidity | 0 – 95 % (non-condensing) | [DS] |
| Dimensions | 70 × 45 × 13 mm (connectors excluded) | [DS] |
| Installation | Desktop, wall screw mounting | [DS] |
| Range (marketing) | Up to 15 km line of sight [DS]; "up to 2 km in urban areas and 15 km in rural areas" [VEN] | [DS][VEN] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UC100 IoT Controller (Modbus RTU to LoRaWAN)", brand Milesight, warranty 12 months. Option "Antenna": External Antenna / Internal Antenna [PP].
- External Antenna: code `LR-UC100-EA`, MPN `UC100-915M-EA`, RM249.70, availability 62. Internal Antenna: code `LR-UC100`, MPN `UC100-915M`, RM223.85, availability 112 [PP].
- The page does not name a LoRaWAN frequency plan; the MPN suffix `915M` is Milesight's 915 MHz-band hardware (inferred), which covers AS923 used in Malaysia (see *Needs verification*) [PP].
- Description: Modbus RTU to LoRaWAN or cellular (4G LTE); "Modbus Master to collect data from up to 16 Modbus slave devices"; IF-THEN command rules; USB Type-C and Milesight ToolBox configuration; D2D on the LoRaWAN version [PP].
- **Packing (without external antenna):** 1 × UC100 controller, 1 × Type-C cable (1.2 m) & power adapter, 1 × terminal block, 2 × wall mounting kits, 1 × quick guide, 1 × warranty card. **With external antenna:** the same plus 1 × LoRaWAN® magnetic antenna [PP].
- **Resources:** UC100 datasheet, UC100 user guide (both Milesight PDFs), Firmware & SDK download page [PP].

## Interfaces, terminals and pin mapping
| Interface | Detail | Src |
|---|---|---|
| RS485 | 2-pin 3.5 mm terminal block (RS485 A/B) | [DS] |
| DC power interface | 2-pin 3.5 mm terminal block, DC 5–24 V, surge and reverse-polarity protected | [DS] |
| USB Type-C | 5 V / 1 A power, ToolBox configuration, console | [DS] |
| 120 Ω terminal resistor switch | Slide switch on the side of the case; adds 120 Ω termination for high baud rates or long cables | [UM] |
| LoRaWAN antenna connector | SMA female (centre pin), EA version only | [DS][UM] |
| LED | 1 × system/work-status LED on top | [UM] |
| Reset button | Inside the device | [UM] |

Port positions from the [UM] hardware-overview figure: Type-C port, DC power interface and RS485 on one short end; the 120 Ω switch on the long side; the SMA connector on the opposite end (EA only). The figure does **not** label which terminal is A/B or +/−; the supplied terminal block is a single plug drawn with several positions (see *Needs verification*) [UM].

**LED indications** [UM]
| State | LED |
|---|---|
| System working properly | Static on |
| Failed to acquire data from data interfaces | Slowly blinks |
| Device upgrade or system error | Static on |
| Reboot (hold reset > 3 s) | Slowly blinks |
| Reset to factory (hold reset > 10 s) | Quickly blinks |

## Rules and gotchas (for code, wiring and tutorials)
- **It is a LoRaWAN end device, not a gateway.** It needs a LoRaWAN gateway and network server in range (e.g. `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md`), or Milesight D2D to talk directly to other Milesight devices [DS][UM].
- **Class C only** (always listening), so it is mains/USB powered; there is no battery [DS][UM].
- **Modbus role:** the UC100 is the RTU **master/client**; the field devices are slaves. Serial settings (baud, parity, stop bits) must match the slaves; data bits are fixed at 8 [UM].
- **Turn the 120 Ω switch on** only when the UC100 sits at an end of the RS485 bus and the line is long or fast [UM].
- **Two-way pass-through disables Modbus channels** and the IF-THEN rules that depend on them [UM].
- Pass-through uses a separate LoRaWAN application port (range 2–84, 86–223); the normal data port defaults to 85 [UM].
- Uplink format: Channel–Type–Data records, little-endian. Use the official decoders at https://github.com/Milesight-IoT/SensorDecoders [UM].
- Set the LoRaWAN channel mask to match the gateway; for AS923 pick the same sub-plan as the gateway [UM].
- For time-based IF-THEN rules sync the clock (ToolBox "Sync", or LoRaWAN V1.0.3 DeviceTimeReq — time only, no time zone) [UM].
- Backup/restore (JSON template) works only between devices of the same model and frequency band [UM].

## Power and electrical limits
- DC 5–24 V on the 2-pin power terminal block (surge and reverse-polarity protected), or DC 5 V / 1 A on USB Type-C [DS].
- Power consumption < 0.5 W [DS].
- A 5 V power adapter with Type-C cable (1.2 m) is in the box [PP][UM]. An "AC/DC-DC Power Converter Kit" is an optional Milesight accessory, not in Cytron's packing list [UM][PP].
- No battery; no isolation rating for RS485 is stated [DS].
- Operating -20 to 60 °C, 0–95 %RH non-condensing, IP30 (indoor) [DS].

## Software support
- Configuration: **Milesight ToolBox** (PC software) over USB Type-C, or LoRaWAN downlink commands [DS][UM].
- Firmware update: via ToolBox (Maintenance > Upgrade) or **FUOTA** over LoRa [DS][UM][VEN].
- Cloud / platforms: Milesight Development Platform (plug-and-play templates, API and webhooks) [DS][VEN]; any standard LoRaWAN network server [DS].
- Payload decoders: https://github.com/Milesight-IoT/SensorDecoders [UM].
- User-guide revisions: V1.0 May 2022 → V1.2 Jan 2024 (32 Modbus channels, data storage) → V1.3 Jan 2025 → V2.0 Jun 2025 (external antenna version, INT64/Double, 2 registers per channel, time zone/DST, IF-THEN commands) [UM].

## Compatibility and accessories
- Gateways: any standard LoRaWAN gateway; Cytron sells `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [DS][PP].
- D2D peers: other Milesight D2D devices, e.g. `milesight-ws50x.md`, `milesight-ws558-ln.md`, `milesight-uc300.md`, `milesight-uc501.md`, `milesight-uc502.md` (D2D support on each is per that product's own file) [UM][VEN].
- Related Milesight controllers: `milesight-uc300.md`, `milesight-uc501.md`, `milesight-uc502.md`, `milesight-uc512.md` [VEN].
- Antenna: magnetic LoRaWAN antenna included only with the EA variant [PP][UM].

## Common mistakes / troubleshooting
- **LED slowly blinking** in normal running = it cannot read data from the RS485 devices: check A/B wiring, slave ID, baud/parity, and use "Fetch" in ToolBox to test a channel [UM].
- **No data reaches the server:** check the channel mask and sub-band match the gateway, and that the device is joined (OTAA keys entered on the network server) [UM].
- **Unreliable RS485 on long cable:** enable the 120 Ω switch at bus ends; lower the baud rate [UM].
- **Modbus channels stopped working** after enabling pass-through: two-way pass-through disables them [UM].
- **Factory reset:** hold the internal reset button > 10 s until the LED blinks quickly, or ToolBox Maintenance > Backup and Reset > Reset [UM].
- Do not touch ToolBox during a firmware upgrade [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Number of Modbus devices | [DS][UM] up to 32 Modbus RTU devices / 32 channels | [PP] "up to 16 Modbus slave devices" | [DS] wins: 32. Cytron page text is out of date (16 IF-THEN commands is a different limit) |
| Registers | [DS] "reading 32 Modbus registers" | [VEN] "Data Collection Up to 64 Registers" | Both consistent with [UM]: 32 channels × up to 2 registers = 64. Use 32 channels |
| Cellular variant | [PP] description: "Available in both LoRaWAN® and Cellular (4G LTE) variants" | [DS] LoRaWAN only; Cytron variants are LoRaWAN (MPN `UC100-915M`, `-EA`) | Cytron sells LoRaWAN only. Do not promise a 4G version from Cytron |

## Needs verification
- Terminal pin order on the power and RS485 blocks (which pin is A/B, +/−): not printed in [DS] text or the [UM] figure. Read it from the device label / quick guide.
- LoRaWAN regional plan Cytron's `915M` units ship with (AS923-1 vs other AS923 sub-plan, or another plan) — the Cytron page does not state it. Confirm the default and set it to match the local gateway.
- Whether the Type-C cable and power adapter count as "1 item" (packing list writes "Type-C Cable (1.2m) & Power Adapter") and the adapter plug type for Malaysia.
- RS485 isolation, maximum number of physical nodes on the bus and cable length: not stated.

## Sources
- [DS] UC100 Datasheet: https://resource.milesight.com/milesight/iot/document/uc100-datasheet-en.pdf (PDF created 16 Jun 2025)
- [UM] UC100 User Guide: https://resource.milesight.com/milesight/iot/document/uc100-ea-user-guide-en.pdf (V2.0, 19 Jun 2025; PDF revised 17 Sep 2025)
- [VEN] Milesight UC100 product page: https://www.milesight.com/iot/product/iot-controller/uc100 (read 2026-10-21)
- [VEN] Firmware download: https://www.milesight.com/support/resources/firmware ; decoders: https://github.com/Milesight-IoT/SensorDecoders
- [PP] Cytron: https://my.cytron.io/Milesight/p-uc100-iot-controller-modbus-rtu-to-lorawan (variant URLs `…-with-internal-antenna`, `…-with-external-antenna`; read 2026-10-21)
