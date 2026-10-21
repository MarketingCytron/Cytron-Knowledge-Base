# Milesight UR41 — Verified Reference

| | |
|---|---|
| Product code | `UR41` (Milesight model; sister model UR41L is LTE Cat 1 without GNSS). Cytron code `IND-UR41`, MPN `UR41-L08EU` [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (price, code, MPN, stock, description, spec, packing list, resources), Milesight UR41 page, UR41(L) datasheet (7 pages, read in full) and UR41(L) user guide V1.6 (Chapters 1–4: packing, hardware overview drawing, serial/IO/power pinout, LEDs, reset, installation, web access) |
| Primary source | Milesight *UR41(L) Datasheet*, https://resource.milesight.com/milesight/iot/document/ur41-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UR41(L) datasheet PDF (two columns: UR41L and UR41; this file uses the UR41 column). [UM] = Milesight *UR41(L) User Guide* V1.6 (9 Jul 2026). [VEN] = milesight.com UR41 page. [PP] = Cytron product page.

## What it is
Cytron sells the UR41 (Cat 4, with GNSS), MPN `UR41-L08EU` [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| CPU / memory | ARM Cortex-A7 528 MHz; 128 MB DDR3 RAM + 128 MB flash | [DS] |
| Cellular | UR41: 4G LTE (Cat 4) / WCDMA / GSM; UR41L: 4G LTE Cat 1. LTE Tx Class 3 (23 dBm ±2 dB) | [DS] |
| LTE bands of `UR41-L08EU` | [NOT STATED]; band selection configurable in the web GUI (UM V1.3+) | [DS][UM] |
| Cellular antenna | 1 × 50 Ω SMA (SMA female centre pin) | [DS] |
| SIM | 1 × nano SIM (4FF), ejector-tool tray | [DS][UM] |
| Ethernet | 1 × RJ45 10/100 Mbps **LAN** port; auto full/half duplex; 1.5 kV RMS isolation | [DS] |
| GNSS (UR41 only) | GPS/GLONASS/BeiDou/Galileo/QZSS; 2.5 m CEP; 1 × SMA female; NMEA 0183, PMTK; readable via serial, MQTT, TCP client/server, UDP server | [DS] |
| Serial | 1 × RS232 **or** 1 × RS485 (software switchable); 3.5 mm terminal block; 300–230400 bps; 120 Ω RS485 termination switch | [DS] |
| DI / DO | 1 × DI + 1 × DO, galvanic isolation, 3.5 mm terminal block; DI dry contact; DO wet contact, max 0.3 A @ 30 VDC | [DS] |
| Serial modes | Transparent (TCP client/server, UDP server, MQTT client), Modbus TCP/RTU client, Modbus gateway (RTU ↔ TCP), DLMS client | [DS] |
| DI / DO functions | DI read by SMS, email, CLI, Modbus TCP/RTU server, MQTT; DO triggered by DI, SMS, CLI, Modbus TCP/RTU server, MQTT | [DS] |
| USB | 1 × USB 2.0 Type-C for power supply, network supply and debug | [DS] |
| Button | 1 × RESET (bottom panel; also wakes the router from standby) | [DS][UM] |
| LEDs | SYSTEM (power and system) and SIM/LTE; Ethernet link (orange) and rate (green) | [DS][UM] |
| Power input | (1) 5–24 VDC on the terminal block; (2) 5 V / 1 A on USB Type-C | [DS] |
| Power connector | [DS]: "1 × 2-pin 3.5 mm terminal block, with surge protection and reverse polarity protection"; [UM]: DC+ / DC− are pins 4 and 8 of the 8-pin serial/IO/power terminal (see *Conflicts*) | [DS][UM] |
| Power consumption (UR41, lab) | Standby 6.3 mA @ 12 V; idle 78 mA @ 12 V; data link 226 mA @ 12 V (UR41L: 6.3 / 70 / 157 mA) | [DS] |
| Power management | Standby mode; wake by schedule, SMS, DI, etc. | [DS] |
| Built-in | Watchdog, timer | [DS] |
| Ingress / housing | IP30; metal, black | [DS] |
| Weight / dimensions | 103 g; 70 × 55 × 22 mm (antenna connectors excluded) | [DS] |
| Installation | Desktop, wall, DIN rail (35 mm; DIN clip kit optional) | [DS][UM] |
| Operating temperature | -40 °C to +60 °C | [DS] |
| Storage / humidity | -40 °C to +85 °C; 0–95 % non-condensing | [DS] |
| Approvals (UR41) | CE, CE (RED), FCC; RoHS | [DS] |
| Network / VPN / management | IPv4/IPv6, SNMP v1/v2c/v3, RIP, OSPF, VRRP, QoS, MQTT(S), TR-069; WAN failover; OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier; AAA; Web, CLI, SMS, DeviceHub, Milesight Development Platform, MilesightVPN | [DS] |
| In the box (Milesight) | UR41, power adapter, 8-pin pluggable terminal, SIM ejector tool, wall bracket with screws, 4 × wall mounting kits, warranty card, quick start guide, magnetic cellular antenna, GPS antenna (UR41 only); optional 108 mm and mini stubby cellular antennas, USB 2.0 cable, DIN rail kit | [UM][DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UR41 4G Mini Industrial Router"; brand Milesight; Code `IND-UR41`; MPN `UR41-L08EU`; warranty 12 months; RM1,227.00; "Availability: Enquiry", INQUIRE NOW [PP].
- Spec list matches [DS] for CPU, memory, LTE Cat 4 / WCDMA / GSM, nano SIM, SMA female, GNSS constellations, 1 × RJ45 10/100 LAN, RS232 or RS485 (software switchable, 3.5 mm terminal block), DI dry / DO wet 0.3 A @ 30 VDC with galvanic isolation, USB 2.0 Type-C, IP30, 103 g, "5–24 VDC (2-pin 3.5mm Terminal Block or 5V/1A via USB Type-C", standby 6.3 mA, idle 70–78 mA, data 157–226 mA @ 12 V, -40 to +60 °C, 70 × 55 × 22 mm [PP].
- **Packing list:** UR41 device, power adapter, 8-pin pluggable terminal, SIM card ejector tool, wall mounting bracket with screws, 4 × wall mounting kits, warranty card, quick start guide, magnetic cellular antenna, GPS antenna [PP].
- **Resources:** UR41 datasheet and user guide (resource.milesight.com, http links), UR Series MQTT API and CLI documentation, firmware and SDK download [PP].
- Description: ultra-low power, "Instant Network Awakening" by alarms, serial activity or timers; suited to solar or battery installations [PP].

## Interfaces, terminals and pin mapping
Hardware overview [UM] (drawing): front — GNSS antenna connector (UR41 only), cellular antenna connector, LED area, Ethernet port, **Serial & IO & Power connector** (8-pin), USB Type-C port, SIM card tray; bottom — 120 Ω terminal resistor switch (RS485) and reset button.

**8-pin serial / IO / power terminal (3.5 mm pluggable)** [UM]:
| Pin | RS232 / RS485 | DI | DO | Power | Description |
|---|---|---|---|---|---|
| 1 | — | — | OUT | — | Digital output |
| 2 | — | IN | — | — | Digital input |
| 3 | TX / A | — | — | — | Transmit data (RS232) / A (RS485) |
| 4 | — | — | — | DC+ | Positive supply |
| 5 | — | — | COM | — | DO common ground |
| 6 | GND | GND | — | — | Ground (serial and DI) |
| 7 | RX / B | — | — | — | Receive data (RS232) / B (RS485) |
| 8 | — | — | — | DC− | Negative supply |

**LED indications** [UM]:
| LED | State | Meaning |
|---|---|---|
| SYSTEM | Off | Power off |
| SYSTEM | Orange static | Powered, in standby mode |
| SYSTEM | Orange blinking 3 times | Starting up |
| SYSTEM | Green static / red static | Running properly (about 1 minute after power-up) / error |
| LTE | Off | SIM registering, failed, or no SIM |
| LTE | Green blinking rapidly / static | Dialling / connected to 4G |
| LTE | Orange static | Connected to 3G/2G |
| Ethernet link (orange) | Off / on / blinking | Disconnected / connected / transmitting |
| Ethernet rate (green) | Off / on | 10 Mbps / 100 Mbps |


## Rules and gotchas (for code, wiring and tutorials)
- **Power and signals share one 8-pin plug:** DC+ is pin 4 and DC− is pin 8, next to the serial and I/O pins. Double-check before applying 5–24 VDC [UM]. (The datasheet describes a 2-pin power block — see *Conflicts*.)
- **Serial is RS232 or RS485, not both:** choose the type in the web GUI. Pin 3 = TX (RS232) or A (RS485); pin 7 = RX (RS232) or B (RS485); GND pin 6 [DS][UM].
- **RS485 termination:** switch on the 120 Ω terminator (bottom panel) only at the end of a long or fast bus [UM].
- **DI is dry contact** between pin 2 and GND pin 6; **DO is wet contact, max 0.3 A @ 30 VDC**, OUT pin 1, COM pin 5; both isolated [DS][UM].
- **The single Ethernet port is LAN**; the WAN is cellular [DS]. Use it to connect a PLC, camera or gateway behind the router.
- **Supply range is 5–24 VDC** (not 9–48 V like UR32/UR35) or 5 V / 1 A on USB-C [DS].
- **Standby:** when standby mode is on, hold the reset button for 3 s to wake the router for 1 hour (SYSTEM orange → green) [UM].
- **No hot-plugging** of the nano SIM; use the ejector tool with power off [UM].
- **Start-up takes about 1 minute** before SYSTEM turns green [UM].
- **Never publish the default login** (not copied).

## Power and electrical limits
- 5–24 VDC (terminal) with surge and reverse-polarity protection, or 5 V / 1 A via USB Type-C [DS].
- UR41 at 12 V: standby 6.3 mA, idle 78 mA, data link 226 mA (lab figures) [DS].
- DO max 0.3 A @ 30 VDC; DI dry contact; galvanic isolation [DS].
- Ethernet isolation 1.5 kV RMS [DS].
- -40 °C to +60 °C, IP30 [DS].

## Software support
- Milesight router firmware: web GUI (HTTPS), CLI (UR Series CLI documentation), SMS control, SNMP with traps, TR-069, MQTT (UR Series MQTT API documentation) [DS][PP].
- Serial DTU modes, Modbus TCP/RTU client, Modbus RTU↔TCP gateway, DLMS client [DS].
- GNSS output over serial, MQTT, TCP or UDP [DS].
- Power management: standby with wake by schedule, SMS or DI [DS].
- VPN: OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier, MilesightVPN; DeviceHub and Milesight Development Platform [DS].
- UM V1.4 adds DI level-change trigger and SNMP trap reporting; UM V1.5 adds traffic statistics, PLMN selection and SMS limits [UM].

## Compatibility and accessories
- Optional Milesight 12000 mAh IP67 UPS battery kit (Type-C version) lists UR41 [VEN of UG65 page].
- Milesight magnetic cellular antenna (SMA-J) lists UR41 [VEN of UG56 page].
- Related routers in this KB: `milesight-ur35.md` (dual SIM, 5 Ethernet, RS232 + RS485), `milesight-ur32.md` (UR32 Lite, no serial).

## Common mistakes / troubleshooting
- **Router dead after wiring:** check DC+ on pin 4 and DC− on pin 8 of the 8-pin plug; 5–24 VDC only [UM][DS].
- **Factory reset:** with SYSTEM static, hold reset more than 5 s until SYSTEM blinks, release and wait; SYSTEM goes off then static green [UM].
- **SYSTEM orange and no traffic:** the router is in standby; hold reset 3 s to wake it for 1 hour, or check the wake schedule [UM].
- **RS485 errors on a long bus:** enable the 120 Ω terminator; check A (pin 3) / B (pin 7) [UM].
- **IPv6 missing on cellular:** the user guide notes that the L0GEU version does not support cellular IPv6 [UM]. Cytron's MPN is `L08EU`, so check this on the unit (see *Needs verification*).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Power connector | [DS] "1 × 2-pin 3.5 mm terminal block"; [PP] repeats "2-pin 3.5mm Terminal Block" | [UM] V1.6 drawing labels one "Serial & IO & Power Connector"; pin table puts DC+ on pin 4 and DC− on pin 8 of the 8-pin terminal; the box has only an 8-pin plug | Unresolved and wiring-critical. [DS] normally wins, but the [UM] pinout is the only pin-level source. Check the unit's silk-screen before wiring |
| Stock | Brand listing card: VIEW | [PP] page: "Availability: Enquiry" | Page used: enquiry only |

## Needs verification
- Power terminal: 2-pin block (datasheet) or pins 4/8 of the 8-pin terminal (user guide) — confirm on the hardware.
- LTE bands of `UR41-L08EU` and suitability for Malaysian operators; whether cellular IPv6 is supported on this variant.
- Manufacturer warranty: the UR41 user guide states none (UR32S/UR35 guides say 3 years); Cytron lists 12 months.
- Datasheet version/date (none printed).

## Sources
- [DS] UR41(L) Datasheet: https://resource.milesight.com/milesight/iot/document/ur41-datasheet-en.pdf (read 2026-10-21).
- [UM] UR41(L) User Guide V1.6, 9 Jul 2026: https://resource.milesight.com/milesight/iot/document/ur41-user-guide-en.pdf (Chapters 1–4 read 2026-10-21).
- [VEN] Milesight UR41 page: https://www.milesight.com/iot/product/cellular/ur41
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ur41-4g-mini-industrial-router (read 2026-10-21).
- [PP] UR Series MQTT API and CLI documentation (not read): https://resource.milesight.com/milesight/iot/document/ur-series-mqtt-api-documentation-en.pdf, https://resource.milesight.com/milesight/iot/document/ur-series-cli-documentation-en.pdf
