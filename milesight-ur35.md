# Milesight UR35 — Verified Reference

| | |
|---|---|
| Product code | `UR35` (Milesight model). Cytron parent code `V-IND-UR35`; variants: With PoE/Wi-Fi = `IND-UR35-P-W`, MPN `UR35-L0GEU-P-W`; With Wi-Fi = `IND-UR35-W`, MPN `UR35-L0GEU-W`; Without PoE/Wi-Fi = `IND-UR35`, MPN `UR35-L0GEU` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (all three variants: price, code, MPN, stock; spec, packing lists, resources), Milesight UR35 page, UR35 datasheet (7 pages, read in full), UR35 Quick Guide V2.3 (read in full, including the serial/IO/power pinout table) and UR35 user guide V2.4 (serial port, DTU mode, DO settings) |
| Primary source | Milesight *UR35 Datasheet*, https://resource.milesight.com/milesight/iot/document/ur35-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UR35 datasheet PDF. [UM] = *UR35 Quick Guide* V2.3 (31 Oct 2022) and *UR35 User Guide* V2.4 (11 Apr 2025). [VEN] = milesight.com UR35 page. [PP] = Cytron product page (the URL p-ur35-series-4g-industrial-router redirects to p-ur35-4g-industrial-router-without-poewi-fi).

## What it is
Cytron offers three variants: with PoE and Wi-Fi (`UR35-L0GEU-P-W`), with Wi-Fi (`UR35-L0GEU-W`) and without PoE/Wi-Fi (`UR35-L0GEU`) [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| CPU / memory | ARM Cortex-A7 528 MHz; 128 MB DDR3 RAM + 128 MB flash; 1 × micro SD slot | [DS] |
| Cellular | 4G LTE (Cat 4) / WCDMA / GSM, "differ as regions"; LTE Tx Class 3 (23 dBm ±2 dB) | [DS] |
| LTE bands of `-L0GEU` | [NOT STATED] | [DS] |
| Cellular antennas | 2 × 50 Ω SMA (SMA female centre pin): MAIN and AUX | [DS][UM] |
| SIM | 2 × mini SIM (2FF), 1.8 V / 3 V; dual-SIM backup | [DS] |
| Ethernet | 5 × RJ45 10/100 Mbps: 1 × WAN + 4 × LAN; auto full/half duplex; 1.5 kV RMS isolation | [DS] |
| PoE out (optional, "-P" models) | 4 × 802.3af/at PSE on LAN ports; 30 W per port, 60 W total; needs 48 V input | [DS] |
| Wi-Fi (optional, "-W" models) | IEEE 802.11 b/g/n 2.4 GHz; AP or client; up to 15 users; 1 × RP-SMA female connector; Tx 13–16 dBm ±1.5 dBm | [DS] |
| GNSS (optional by region) | GPS/GLONASS/BDS/Galileo/QZSS; 2.5 m CEP; SMA female connector; NMEA 0183, PMTK; readable via serial, MQTT, TCP client/server, UDP server | [DS] |
| Serial | 1 × RS232 + 1 × RS485 on a 3.5 mm terminal block; 300–230400 bps; 7/8 data bits, 1/2 stop bits, none/odd/even parity | [DS][UM] |
| DI / DO | 1 × DI + 1 × DO, galvanic isolation, 3.5 mm terminal block; DI dry contact; DO wet contact, max 0.3 A @ 30 VDC | [DS] |
| Serial modes | Transparent (TCP client/server, UDP server, MQTT client), Modbus server/client, Modbus gateway (RTU ↔ TCP), DLMS client, GPS forwarding | [DS][UM] |
| DI / DO functions | DI read by SMS, email, CLI, Modbus TCP/RTU server, MQTT; DO triggered by DI, SMS, CLI, Modbus TCP/RTU server, MQTT; DO modes high level, low level, pulse, custom (SMS) | [DS][UM] |
| Reset button | 1 × RESET (under the SIM slots) | [DS][UM] |
| LEDs | POWER, SYSTEM, SIM, Wi-Fi, VPN, 3 × signal strength; Ethernet link (orange) | [DS][UM] |
| Power connector | 2-pin 5.08 mm terminal block, surge and reverse-polarity protection | [DS] |
| Power input | 9–48 VDC (48 V needed for PoE) | [DS] |
| Power consumption | Typical 3.9 W, max 4.6 W (non-PoE mode) | [DS] |
| Built-in | Watchdog, timer; grounding stud | [DS][UM] |
| Ingress / housing | IP30; metal, black | [DS] |
| Weight / dimensions | 485 g; 135 × 103 × 45 mm | [DS] |
| Installation | Desktop, wall screw mounting, DIN rail (35 mm) | [DS][UM] |
| Operating temperature | -40 °C to +70 °C; reduced cellular performance above 60 °C | [DS] |
| Storage / humidity | -40 °C to +85 °C; 0–95 % non-condensing at 25 °C | [DS] |
| Approvals | CE, CE (RED), FCC, RCM, JATE, Telec; RoHS; EN 55032/55035; IEC 61000-4-2 L3, -3 L2, -4 L3, -5 L3, -6 L3, -8 L4, -11 L3; EN 62368-1 | [DS] |
| Network / VPN / management | IPv4/IPv6, PPPoE, SNMP, RIP, OSPF, VRRP, QoS, VLAN, MQTT(S), TR-069; WAN failover, dual-SIM backup; OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier; Web, CLI, SMS, HTTP(s) API, DeviceHub, Milesight Development Platform, MilesightVPN; Python SDK | [DS] |
| In the box (Milesight) | UR35, power adapter, 8-pin pluggable terminal, DIN rail kit, 2 × magnetic cellular antennas, quick start guide, warranty card; Wi-Fi antenna (Wi-Fi version), GPS antenna (GPS version); optional 2 × stubby cellular antennas | [UM][DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UR35 Series 4G Industrial Router"; brand Milesight; parent code `V-IND-UR35`; warranty 12 months; RM1,011.70 – RM1,226.95; option "Router": With PoE/Wi-Fi / With Wi-Fi / Without PoE/Wi-Fi; page status "Out Of Stock" [PP].
- **With PoE/Wi-Fi:** RM1,226.95, `IND-UR35-P-W`, MPN `UR35-L0GEU-P-W`, Enquiry. **With Wi-Fi:** RM1,068.00, `IND-UR35-W`, MPN `UR35-L0GEU-W`, Out Of Stock. **Without PoE/Wi-Fi:** RM1,011.70, `IND-UR35`, MPN `UR35-L0GEU`, Enquiry [PP].
- Spec list matches [DS]: Cortex-A7 528 MHz, 128 MB + 128 MB, micro SD, Python SDK, LTE Cat 4/WCDMA/GSM, 2 × mini SIM, 5 × RJ45 (1 WAN + 4 LAN) 10/100, PoE out 4 × 802.3af/at (30 W/port, 60 W total), Wi-Fi 2.4 GHz AP/client, 1 × RS232 + 1 × RS485 terminal block, 1 DI + 1 DO (0.3 A @ 30 VDC), IP30, 9–48 VDC, 3.9 W / 4.6 W, -40 to +70 °C, 135 × 103 × 45 mm [PP].
- **Packing list:** without PoE/Wi-Fi — router, power adapter, 8-pin pluggable terminal, DIN rail kit, 2 × magnetic cellular antennas, quick start guide, warranty card; with PoE/Wi-Fi — the same plus 1 × Wi-Fi antenna (Wi-Fi version only) [PP].
- **Resources:** UR35 datasheet, user guide and quick guide; UR Series MQTT API documentation; UR Series CLI documentation; firmware and SDK download [PP].

## Interfaces, terminals and pin mapping
Hardware overview [UM]: **front panel** — 1 Wi-Fi antenna connector, 2 AUX cellular antenna connector, 3 GPS antenna connector, 4 MAIN cellular antenna connector, 5 LED area (POWER, SYSTEM, Wi-Fi, VPN, SIM, signal strength), 6 Ethernet ports and indicators. **Left side panel** — 7 grounding stud, 8 SIM and reset button holder, 9 power connector, 10 serial port and I/O.

**8-pin serial and I/O terminal (3.5 mm pluggable)** [UM]:
| Pin | RS232 | RS485 | DI | DO | Description |
|---|---|---|---|---|---|
| 1 | — | — | IN | — | Digital input |
| 2 | GND | — | GND | — | Ground |
| 3 | — | B | — | — | Data − |
| 4 | TXD | — | — | — | Transmit data |
| 5 | — | — | — | COM | DO common ground |
| 6 | — | — | — | OUT | Digital output |
| 7 | — | A | — | — | Data + |
| 8 | RXD | — | — | — | Receive data |

Note from the quick guide: on the "-RS485" model, RXD becomes A and TXD becomes B (a second RS485 in place of RS232) [UM].

**Power terminal (2-pin, 5.08 mm)** [UM]:
| Pin | Function | Wire colour |
|---|---|---|
| 9 | Positive (+) | Red |
| 10 | Negative (−) | Black |

**LED indications** [UM]:
| LED | State | Meaning |
|---|---|---|
| POWER | Off / On | Power off / on |
| SYSTEM | Green static / slow blink / red | Starting up / running properly / error |
| VPN | Off / green | VPN disconnected / connected |
| Wi-Fi | Off / green static / green slow blink | Disabled / enabled / transferring data |
| SIM | Off | SIM1 or SIM2 registering, failed, or none |
| SIM | Green slow / rapid / static | SIM1 primary: registered / dialling / connected |
| SIM | Orange slow / rapid / static | SIM2 primary: registered / dialling / connected |
| Signal 1/2/3 | 1 / 2 / 3 lit | Weak 1–10 ASU / normal 11–20 ASU / strong 21–31 ASU |
| Ethernet link (orange) | On / blinking / off | Connected / transmitting / disconnected |

**Default access** [UM]: connect a PC to a **LAN** port (DHCP or static IP in the same subnet) and open **192.168.1.1**. A default web login is set at the factory (see the quick guide; not copied). Five wrong logins lock the page for 10 minutes.

## Rules and gotchas (for code, wiring and tutorials)
- **RS485 polarity: A = pin 7 (Data +), B = pin 3 (Data −).** RS232: TXD pin 4, RXD pin 8, GND pin 2 [UM].
- **Pin 2 GND is shared** by RS232 and the digital input; the DO has its own COM on pin 5 [UM].
- **DI is dry contact** (wire a switch/relay contact between DI pin 1 and GND pin 2); do not apply voltage (inferred from "dry contact") [DS][UM].
- **DO is wet contact, max 0.3 A @ 30 VDC**; it is galvanically isolated (OUT pin 6, COM pin 5) [DS]. Do not switch mains or larger loads directly — use an interposing relay (inferred).
- **Serial type is selected in the web GUI** (*Serial Port > Serial Type: RS232 or RS485*); set baud (300–230400), data bits, stop bits and parity to match the device [UM]. Whether RS232 and RS485 can run at the same time is not stated (see *Needs verification*).
- **Serial modes:** DTU (transparent TCP/UDP client, TCP server on port 502 by default, UDP server, Modbus RTU↔TCP gateway, MQTT client), Modbus client, Modbus server, DLMS, GPS forwarding [UM][DS].
- **Power: pin 9 = +, pin 10 = −** (red/black), 9–48 VDC; PoE output needs 48 V [UM][DS].
- **Ground the router** to the cabinet earth via the grounding stud — Milesight says it must be grounded when deployed [UM].
- **No hot-plugging** of SIM or micro SD; cut power first [UM].
- **Never publish the default login** (not copied).

## Power and electrical limits
- 9–48 VDC on the 2-pin 5.08 mm terminal (pin 9 +, pin 10 −); surge and reverse-polarity protection [DS][UM].
- Typical 3.9 W, max 4.6 W without PoE [DS].
- PoE PSE (P models): 802.3af/at, 30 W per port, 60 W total, 48 V input [DS].
- DO: max 0.3 A @ 30 VDC, galvanic isolation; DI dry contact [DS].
- Ethernet isolation 1.5 kV RMS [DS].
- -40 °C to +70 °C (cellular reduced above 60 °C), IP30 [DS].

## Software support
- Milesight router firmware: web GUI, CLI (SSH/Telnet; UR Series CLI documentation), SMS, SNMP with traps, TR-069, HTTP(s) API, MQTT API (UR Series MQTT API documentation) [DS][PP].
- Embedded Python SDK for on-device apps [DS].
- Modbus server/client and Modbus gateway; DLMS client; GNSS data forwarding (GPS models) [DS].
- VPN: OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier, MilesightVPN [DS].
- Remote management: DeviceHub, Milesight Development Platform [DS].

## Compatibility and accessories
- Serial gateway for Modbus RTU meters/PLCs and RS232 devices; cellular backhaul for LoRaWAN gateways such as `milesight-ug56.md` (inferred use).
- Milesight magnetic cellular antenna (700–960 / 1710–2700 MHz, SMA-J) lists UR35 [VEN of UG56 page].
- Related routers in this KB: `milesight-ur32.md` (UR32 Lite, no serial/I/O), `milesight-ur41.md` (mini router).

## Common mistakes / troubleshooting
- **RS485 no data:** A/B swapped (A = pin 7, B = pin 3), wrong serial type selected (RS232 vs RS485), or baud/parity mismatch [UM].
- **Factory reset:** with SYSTEM blinking, hold the reset button (under the SIM slots) more than 5 s until SYSTEM blinks rapidly, release and wait; SYSTEM goes off then blinks [UM].
- **No PoE:** not a "-P" variant, or supply below 48 V [DS].
- **SIM LED orange:** SIM2 is the active primary SIM [UM].
- **Weak signal (one bar):** check that both MAIN and AUX antennas are fitted [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Stock | Brand listing card: OUT OF STOCK; page "Out Of Stock" | Variants P-W and base show "Enquiry" | Treated as out of stock; two variants on enquiry |
| PoE / Wi-Fi as standard | [DS] optional by model | [PP] spec list shows PoE and Wi-Fi without saying which variant | Only `-P` has PoE; only `-W` has Wi-Fi (from the MPN suffixes [UM][PP]) |
| GNSS | [DS] optional by region | [PP] not mentioned; MPNs have no GPS marker | Cytron's units probably have no GNSS (inferred); confirm |
| Warranty | [UM] UR35 user guide "3-year warranty included" | [PP] 12 months | Cytron's 12 months applies to Cytron sales — confirm |

## Needs verification
- Whether RS232 and RS485 can be used at the same time (the user guide's *Serial Type* setting suggests one at a time).
- LTE bands of the `-L0GEU` variants and suitability for Malaysian operators.
- Whether Cytron's variants include GNSS.
- Datasheet version/date (none printed).

## Sources
- [DS] UR35 Datasheet: https://resource.milesight.com/milesight/iot/document/ur35-datasheet-en.pdf (read 2026-10-21).
- [UM] UR35 Quick Guide V2.3, 31 Oct 2022: https://resource.milesight.com/milesight/iot/document/ur35-quick-guide-en.pdf (read 2026-10-21).
- [UM] UR35 User Guide V2.4, 11 Apr 2025: https://resource.milesight.com/milesight/iot/document/ur35-user-guide-en.pdf (I/O and serial sections).
- [VEN] Milesight UR35 page: https://www.milesight.com/iot/product/cellular/ur35
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ur35-series-4g-industrial-router (redirects to https://my.cytron.io/Milesight/p-ur35-4g-industrial-router-without-poewi-fi; read 2026-10-21).
- [PP] UR Series MQTT API and CLI documentation: https://resource.milesight.com/milesight/iot/document/ur-series-mqtt-api-documentation-en.pdf, https://resource.milesight.com/milesight/iot/document/ur-series-cli-documentation-en.pdf (not read).
