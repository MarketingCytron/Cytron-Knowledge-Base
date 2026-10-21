# Milesight FT101 LoRaWAN Field Tester — Verified Reference

| | |
|---|---|
| Product code | `FT101` (Milesight model). Cytron code `LR-FT101`, MPN `FT101-915M` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, code, MPN, stock, description, spec, packing list, resources), Milesight FT101 page, FT101 datasheet (3 pages, read in full) and FT101 user guide V1.1 (read in full: packing list, SIM/SD, buttons, signal-test modes, LoRaWAN settings, upgrade, maintenance, uplink protocol) |
| Primary source | Milesight *FT101 Datasheet*, https://resource.milesight.com/milesight/iot/document/ft101-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight FT101 datasheet PDF. [UM] = Milesight *FT101 User Guide* V1.1 (20 Jan 2025). [VEN] = milesight.com FT101 page (https://www.milesight.com/product/accessories/ft101). [PP] = Cytron product page. The user guide's hardware-overview figure (button and port positions) is a drawing without text and was not read.

## What it is
Cytron sells MPN `FT101-915M` (915 MHz-band antenna/hardware) and states the plan as Malaysia AS923-2 / Singapore AS923-1 [PP]. Different LoRaWAN bands need different antennas [DS].

## Specifications
| Item | Value | Src |
|---|---|---|
| Display | 5.72-inch TP LCD touch screen, 1440 × 720 | [DS] |
| CPU | Octa-core MTK6762, 2 GHz | [DS] |
| Memory | 4 GB RAM + 64 GB ROM | [DS] |
| OS | Android 12.0 | [DS] |
| NFC | ISO/IEC 14443A, reading distance 1–3 cm | [DS] |
| Storage expansion | 1 × micro SD slot, up to 256 GB | [DS] |
| LoRa module | Built-in one-channel SX1262 | [DS] |
| LoRaWAN channels | 1 | [DS] |
| LoRa antenna connector | 1 × 50 Ω SMA female | [DS] |
| Frequency bands | CN470 / IN865 / EU868 / RU864 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 (different antennas for different frequencies) | [DS] |
| Cytron frequency plan | "Support Malaysia AS923-2, Singapore AS923-1"; MPN FT101-915M | [PP] |
| Sensitivity | -137 dBm @ 125 kHz (Cytron adds SF=12) | [DS][PP] |
| Max output power | 19 dBm (470 MHz) / 16 dBm (868 MHz) / 22 dBm (915 MHz) | [DS] |
| LoRaWAN protocol / mode | V1.0.3; OTAA Class A | [DS] |
| Configurable | Band/channels, SF or ADR, Tx power (native or "mock sensor" of a Milesight model), packet interval 6–60 s (default 10 s), AppKey | [UM] |
| Wi-Fi | IEEE 802.11 b/g/n 2.4 GHz; 802.11 a/n/ac 5 GHz | [DS] |
| Bluetooth | Bluetooth 4.0 (BLE) | [DS] |
| GNSS | GPS / GLONASS / BeiDou / Galileo (works outdoors only) | [DS][UM] |
| USB | 1 × USB 3.0 Type-C for power and OTG | [DS] |
| SIM / SD tray | Nano SIM (4FF) or micro SD in a card tray under a rubber plug | [UM] |
| Power | Built-in 4.3 V / 4300 mAh rechargeable lithium battery; 5 V ⎓ 2 A by USB Type-C; Type-C power bank charging supported | [DS] |
| Battery life | Around 8 hours; standby > 300 h (lab conditions) | [DS] |
| Operating temperature | -10 °C to 50 °C | [DS] |
| Storage temperature | -20 °C to 60 °C | [DS] |
| Humidity | 95 % non-condensing | [DS] |
| Ingress protection | IP65 | [DS] |
| Colour / size / weight | Black; 178 × 83 × 17 mm; 242 g without antenna | [DS] |
| Approvals | CE | [DS] |
| In the box (Milesight) | FT101, LoRaWAN stubby antenna, Type-C cable (1 m) and power adapter, card ejector tool, screen protector, lanyard, warranty card | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "FT101 LoRaWAN Field Tester"; brand Milesight; Code `LR-FT101`; MPN `FT101-915M`; warranty 12 months; RM2,539.95; "Availability: Enquiry", button INQUIRE NOW [PP].
- Spec list matches [DS] for display, CPU, memory, Android 12, NFC, micro SD, 1 channel, SMA female, -137 dBm, output power, V1.0.3 OTAA Class A, Wi-Fi 2.4/5 GHz, BLE 4.0, GNSS, USB 3.0 Type-C, 4.3 V 4300 mAh battery, 5 V 2 A, ~8 h / >300 h, -10 to 50 °C, 178 × 83 × 17 mm, 242 g. It adds "Frequency Plan: Support Malaysia AS923-2, Singapore AS923-1" and does not list IP65 or approvals [PP].
- Description: real-time RSSI, SNR and packet-loss display; coverage mapping; per-SF testing; noise scan; ping-pong test with two units; GPS-tagged results; report export over USB Type-C; Milesight ToolBox for NFC sensor configuration; "testing of different frequencies by swapping out various antennas" [PP].
- **Packing list:** "1 x FT101 LoRaWAN Field Tester" only [PP] (see *Conflicts*).
- **Resources:** FT101 datasheet, FT101 user guide (resource.milesight.com), firmware and SDK download [PP].

## Interfaces, terminals and pin mapping
No wiring terminals. Physical interfaces [DS][UM]:
| Interface | Detail | Src |
|---|---|---|
| SMA female (50 Ω) | LoRa antenna; swap antennas for different bands | [DS] |
| USB 3.0 Type-C | 5 V 2 A charging, OTG, file transfer (reports, firmware) | [DS][UM] |
| Card tray | Nano SIM (4FF) or micro SD; behind a rubber plug, opened with the ejector tool | [UM] |
| Buttons | Power (hold 3 s on/off/restart), Volume up, Volume down; Volume down + Power = screenshot | [UM] |
| NFC area | ISO/IEC 14443A, 1–3 cm | [DS] |

**Test modes** in the Field Tester app [UM]:
| Situation | Mode | What it does |
|---|---|---|
| No gateway on site | Noise Scan | Scans channel noise, shows RSSI graph/table, CSV export; scan at least 1 hour for accurate results |
| No gateway on site | PingPong | Two FT101s (Master and Slave, same kit ID, SF, Tx power and frequency) simulate node and gateway; shows up/down counts, average RSSI/SNR, packet loss |
| Gateway on site | Signal Evaluation | Sends packets at each SF for about 1 minute and recommends the best SF |
| Gateway on site | Real-time Testing | Sends confirmed packets at a fixed SF or ADR; minimum 1 minute; results and CSV export |

**Joining a network** [UM]: the tester is an OTAA Class A device. Its DevEUI and AppKey are shown in the app under *Settings > Basic Information*; the JoinEUI is fixed by Milesight and a default AppKey is set at the factory (see the user guide; not copied). Add it on the network server (e.g. a UG65's embedded NS, *Network Server > Device*) with an OTAA-Class A profile; Signal Evaluation and Real-time Testing buttons appear only after it has joined.

## Rules and gotchas (for code, wiring and tutorials)
- **Match the band to the gateway.** Set *Band* in the app's LoRaWAN settings to the gateway's plan (Cytron: AS923-2 in Malaysia); for CN470/AU915/US915 enter the enabled channel indexes. Changing any LoRaWAN parameter makes the tester rejoin [UM].
- **Use the antenna for the band.** The SMA antenna is band-specific; Cytron's MPN is the 915 MHz version [DS][PP].
- **Change the default AppKey** if the network requires unique keys; never publish the default AppKey or the device EUI (not copied here).
- **GNSS coordinates only outdoors.** Turn on Location in Android Settings; Milesight suggests the "GPS Test" app if no fix [UM].
- **Mock sensor:** set Tx power mode to a Milesight model to simulate that sensor's radio capability, for realistic results [UM].
- **Uplink payload** (for decoders): channel–type–data records, little-endian. Coordinate `03 a1` (INT32/1e6 longitude then latitude); signal `04 a2` (RSSI INT16/10 dBm, SNR INT16/10 dB); SF `05 a3` (7–12, FF = ADR); Tx power `06 a4` (INT16/100 dBm); device info on channel `ff` (power on, protocol, hardware and firmware versions, class, SN). Decoders: github.com/Milesight-IoT/SensorDecoders [UM].
- **Packet-loss bands** used by the app's signal-quality guide: strong ≤ 5 %, medium 5–10 %, weak 10–50 %, abnormal ≥ 50 % (each with per-SF RSSI limits) [UM].

## Power and electrical limits
- Internal 4.3 V / 4300 mAh lithium battery; do not remove it [DS][UM].
- Charge with 5 V ⎓ 2 A over USB Type-C (adapter in Milesight's box) or a Type-C power bank [DS][UM].
- Do not charge above 45 °C or below -10 °C; charge every 3 months when stored [UM].
- Operating -10 °C to 50 °C; IP65 [DS]. The touch screen responds slowly in the cold (normal) [UM].

## Software support
- Android 12 with the Milesight Field Tester app (pre-installed) and the Milesight ToolBox app for NFC/Bluetooth configuration of Milesight sensors [DS][UM].
- Firmware upgrade: download from Milesight, copy to the tester over Type-C, then *Settings > Basic Information > Select file > Upgrade*. App upgrade: *App Upgrade* (Internet) or install the apk from the device folder [UM].
- Results: CSV logs on the tester; *Settings > Historical Reports* [UM].
- Works with any standard LoRaWAN gateway and network server [DS].

## Compatibility and accessories
- Gateways: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` (the user guide uses a UG65 as the example) [UM].
- Configures Milesight sensors over NFC via ToolBox, e.g. `milesight-em320-th.md`, `milesight-em300-th.md`, `milesight-ws101.md` [DS].
- Other-band antennas: Milesight says different frequencies need different antennas; part numbers [NOT STATED] [DS].

## Common mistakes / troubleshooting
- **Signal Evaluation / Real-time Testing buttons missing:** the tester has not joined; add it to the network server as OTAA Class A with the DevEUI and AppKey shown in the app [UM].
- **No coordinates:** indoors, or Location is off in Android settings [UM].
- **PingPong gets nothing:** both units must share band, frequency, SF, Tx power and kit ID, with one Master and one Slave [UM].
- **Inaccurate noise scan:** scan for at least 1 hour [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Packing list | [UM] tester, stubby antenna, Type-C cable and adapter, ejector tool, screen protector, lanyard, warranty card | [PP] "1 x FT101 LoRaWAN Field Tester" | [UM] is the manufacturer box; confirm with Cytron |
| IP rating / approvals | [DS] IP65; CE | [PP] not listed | [DS] |
| Stock | Brand listing card: VIEW | [PP] page: "Availability: Enquiry" | Page used: enquiry only |

## Needs verification
- What the nano SIM (4FF) slot is for: the datasheet lists no cellular interface, but the user guide describes SIM installation.
- Per-SF RSSI limits of the signal-quality guide (the PDF table text is partly garbled; only packet-loss bands are given here).
- Part numbers for other-band antennas.
- Datasheet version/date (none printed).

## Sources
- [DS] FT101 Datasheet: https://resource.milesight.com/milesight/iot/document/ft101-datasheet-en.pdf (read 2026-10-21).
- [UM] FT101 User Guide V1.1, 20 Jan 2025: https://resource.milesight.com/milesight/iot/document/ft101-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight FT101 page: https://www.milesight.com/product/accessories/ft101
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ft101-lorawan-field-tester (read 2026-10-21).
