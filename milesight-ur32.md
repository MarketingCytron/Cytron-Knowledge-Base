# Milesight UR32 Lite Series (UR32L / UR32S) — Verified Reference

| | |
|---|---|
| Product code | `UR32L` and `UR32S` (Milesight "UR32 Lite Series"). Cytron parent code `V-IND-UR32`; variants: UR32L = Cytron code `IND-UR32L`, MPN `UR32L-L0GEU`; UR32S = Cytron code `IND-UR32S`, MPN `UR32S-L0GEU` [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (both variants: price, code, MPN, stock; description, spec, packing lists, resources), Milesight UR32 Lite page, UR32S and UR32L datasheets (read in full), UR32L Quick Start Guide V1.2 (read in full, plus the hardware-overview drawing for power polarity) and UR32S user guide V1.7 (web access, PoE settings, cellular band). The UR32S Quick Guide PDF is an image without a text layer and was not read |
| Primary source | Milesight *UR32S Datasheet* and *UR32L Datasheet* (Lite Series), https://resource.milesight.com/milesight/iot/document/ur32s-datasheet-en.pdf and …/ur32l-datasheet-en.pdf (no version or date printed; read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight UR32S and UR32L datasheet PDFs (identical except Wi-Fi). [UM] = *UR32L Quick Start Guide* V1.2 (30 Apr 2026) and *UR32S User Guide* V1.7 (30 Apr 2026). [VEN] = milesight.com UR32 Lite page (https://www.milesight.com/iot/product/cellular/ur32lite). [PP] = Cytron product page (the URL p-ur32-series-4g-industrial-router redirects to p-ur32s-4g-industrial-router).

## What it is
This is Milesight's **UR32 Lite** series. It is not the full Milesight UR32 router: the Lite models have **no RS232, RS485, digital input or digital output terminals and no GNSS** [DS][PP]. For serial and I/O, see `milesight-ur35.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| CPU | ARM Cortex-A7, 528 MHz (NXP industrial processor) | [DS] |
| Memory | 128 MB DDR3 RAM + 128 MB flash | [DS] |
| Cellular | 4G LTE (Cat 4) / WCDMA / GSM, "differ as regions"; LTE Tx Class 3 (23 dBm ±2 dB) | [DS] |
| LTE speed | Up to 150 Mbps down / 50 Mbps up | [VEN][PP] |
| LTE bands of `-L0GEU` | [NOT STATED] (band selection is configurable in the web GUI) | [UM] |
| Cellular antenna | 1 × 50 Ω SMA connector (centre pin: SMA female) | [DS] |
| SIM | 1 × mini SIM (2FF), 1.8 V / 3 V | [DS] |
| Ethernet | 2 × RJ45 10/100 Mbps; 1 × WAN + 1 × LAN or 2 × LAN (port LAN1/WAN is switchable); auto full/half duplex; 1.5 kV RMS isolation | [DS][UM] |
| PoE out (optional models) | 2 × 802.3af/at PSE on LAN ports, 30 W per port, 60 W total; needs 48 V input; only models with "-P" in the name, hardware version 4.0 or later | [DS][UM] |
| Wi-Fi (UR32S only) | IEEE 802.11 b/g/n 2.4 GHz; AP or client; up to 15 clients; 1 × 50 Ω connector (RP-SMA female); Tx 13–16 dBm ±1.5 dBm | [DS] |
| Serial / I/O / GNSS | None on UR32L or UR32S | [DS][PP] |
| Reset button | 1 × RESET (under the SIM slot cover) | [DS][UM] |
| LEDs | POWER, SYSTEM, SIM, 3 × signal strength; Ethernet link LED (orange) | [DS][UM] |
| Power connector | 1 × 2-pin 5.08 mm terminal block, surge and reverse-polarity protection | [DS] |
| Power input | 9–48 VDC (48 V needed for PoE output) | [DS] |
| Power consumption | Typical 1.8 W, max 2.2 W (non-PoE mode) | [DS] |
| Built-in | Watchdog, timer | [DS] |
| Ingress protection / housing | IP30; metal, black | [DS] |
| Dimensions | 108 × 90 × 26 mm | [DS] |
| Weight | UR32L 206 g; UR32S 214 g | [PP] |
| Installation | Desktop, wall or DIN rail (35 mm); optional side DIN-mount bracket | [DS][UM] |
| Operating temperature | -40 °C to +70 °C; reduced cellular performance above 60 °C | [DS] |
| Storage temperature | -40 °C to +85 °C | [DS] |
| Humidity | 0–95 % non-condensing at 25 °C | [DS] |
| Approvals | CE, CE (RED), FCC, RCM, Telec; RoHS; EMC EN 55032/55035; EMS IEC 61000-4-2 L3, -3 L2, -4 L2, -5 L2, -6 L3, -8 L1, -11 L3; safety EN 62368-1 | [DS] |
| Network software | IPv4/IPv6, PPPoE, SNMP v1/v2c/v3, DHCP, RIPv1/v2, OSPF, DDNS, VRRP, QoS, VLAN, SSH, MQTT, MQTTS, TR-069; static/policy routing; IP passthrough; WAN failover | [DS] |
| VPN | OpenVPN (clients + server), IPsec (clients + server), GRE, L2TP client, PPTP client, DMVPN spoke, WireGuard, ZeroTier; MilesightVPN | [DS] |
| Security | ACL, DMZ, port mapping, MAC binding, SPI firewall, DoS/DDoS protection, IP/domain filtering; AAA (RADIUS, TACACS+, LDAP, local, 802.1x); multilevel users | [DS] |
| Management | Web, CLI (SSH/Telnet), SMS, on-demand dial-up, SNMP, TR-069, DeviceHub, Milesight Development Platform, HTTP(s) API | [DS] |
| In the box (Milesight) | Router, magnetic cellular antenna, power adapter, DIN rail clip kit, 4 × wall mounting kits, warranty card, quick start guide; optional stubby cellular antenna and DIN mounting bracket kit | [DS][UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "UR32 Series 4G Industrial Router"; brand Milesight; parent code `V-IND-UR32`; warranty 12 months; RM533.00 – RM603.00; option "Router": UR32L / UR32S; "Availability: Out Of Stock", NOTIFY ME! [PP].
- **UR32L:** RM603.00, code `IND-UR32L`, MPN `UR32L-L0GEU`, out of stock. **UR32S:** RM533.00, code `IND-UR32S`, MPN `UR32S-L0GEU`, out of stock [PP].
- Shared spec on [PP] matches [DS]: Cortex-A7 528 MHz, 128 MB + 128 MB, LTE Cat 4 150/50 Mbps, 2 × RJ45 10/100, IP30 metal, 9–48 VDC with surge and reverse-polarity protection, 1.8 W / 2.2 W, -40 to +70 °C, 108 × 90 × 26 mm; VPNs incl. ZeroTier, WireGuard, MilesightVPN; MQTT, SNMP, TR-069, VRRP, OSPF, RIP [PP].
- Version notes on [PP]: UR32L — 1 × mini SIM, 1 × SMA female, "Wi-Fi / GPS / Serial: Not supported", "PoE Out: Not supported", 206 g. UR32S — 1 × mini SIM, SMA female cellular + RP-SMA female Wi-Fi, 802.11b/g/n 2.4 GHz AP/client, "PoE Out (Optional): 2 × 802.3af/at PoE PSE on LAN ports (30W max per port, 60W max total)", 214 g [PP].
- **Packing list:** UR32L — router, magnetic cellular antenna, power adapter, DIN rail kit, 4 × wall mounting kits, warranty card, quick start guide. UR32S — the same plus 1 × stubby cellular antenna and 1 × stubby Wi-Fi antenna [PP].
- **Resources:** UR32L and UR32S datasheets, user guides and quick guides (resource.milesight.com), payload decoder, firmware and SDK download [PP].

## Interfaces, terminals and pin mapping
Hardware overview (UR32L quick guide; UR32S adds a Wi-Fi RP-SMA connector) [UM]:
| # | Item | Src |
|---|---|---|
| 1 | Cellular antenna connector (SMA female) | [UM][DS] |
| 2 | LED area: POWER, SYSTEM, SIM, signal strength (3 bars) | [UM] |
| 3 | Ethernet LAN1/WAN port | [UM] |
| 4 | Ethernet LAN2 port | [UM] |
| 5 | Power connector: 2-pin 5.08 mm terminal block marked "DC 9-48V" | [UM][DS] |
| 6 | SIM and reset button holder (screw cover) | [UM] |

**Power terminal (2-pin, 5.08 mm)** — read from the UR32L quick-guide drawing [UM]: the block is marked **"DC 9-48V"** with **"−" on the pin nearer the LAN2 port and "+" on the pin nearer the housing corner/mounting ear**. Check the marking on the unit before wiring.

**No serial or I/O terminals** on UR32L/UR32S [DS][PP].

**LED indications** [UM]:
| LED | State | Meaning |
|---|---|---|
| POWER | Off / On | Power off / on |
| SYSTEM | Green static | Starting up |
| SYSTEM | Green blinking slowly | Running properly |
| SYSTEM | Red | System error |
| SIM | Off | Registering, failed, or no SIM |
| SIM | Green blinking slowly / rapidly / static | Registered, ready / dialling up / dialled up |
| Signal 1/2/3 | Off | No signal |
| Signal 1/2/3 | 1 lit / 2 lit / 3 lit | Weak 1–10 ASU (check antenna) / normal 11–20 ASU / strong 21–31 ASU |
| Ethernet link (orange) | On / blinking / off | Connected / transmitting / disconnected |


## Rules and gotchas (for code, wiring and tutorials)
- **No RS232/RS485/DI/DO.** Do not write Modbus-serial or I/O wiring steps for UR32L/UR32S; use UR35 or another router with serial [DS][PP].
- **Power polarity:** follow the "−/+" marking on the 2-pin terminal (see above); the input is reverse-polarity protected, 9–48 VDC [DS][UM].
- **PoE output needs a "-P" model, hardware v4.0+ and a 48 V supply**, and works only when LAN1/WAN is set as a LAN port [UM][DS]. Cytron's MPNs (`-L0GEU`) have no "-P" (inferred: no PoE out) — see *Conflicts*.
- **WAN setup:** *Network > Interface > Port* to change LAN1 to WAN, configure *Network > Interface > WAN*, then raise WAN priority in *Link Failover* [UM].
- **Cellular setup:** set APN/PIN in *Network > Interface > Cellular > Cellular Setting*, enable the SIM in *Link Failover*; SIM LED static green = connected [UM]. Bands can be restricted in the cellular settings [UM].
- **SIM:** unscrew the SIM cover, insert the mini SIM, screw the cover back; the reset button is under the SIM cover [UM].
- **Wi-Fi (UR32S)** is 2.4 GHz only, up to 15 clients [DS].
- **Never publish the default login** (not copied).

## Power and electrical limits
- 9–48 VDC on the 2-pin 5.08 mm terminal block; surge and reverse-polarity protected [DS].
- Typical 1.8 W, max 2.2 W without PoE [DS].
- PoE PSE (PoE models only): 802.3af/at, 30 W per port, 60 W total, 48 V input required [DS].
- Ethernet isolation 1.5 kV RMS [DS].
- -40 °C to +70 °C (cellular reduced above 60 °C), IP30 [DS].
- Mounting screws: M3 × 6 flat head, recommended 1.0 N·m, max 1.2 N·m [UM].

## Software support
- Milesight router firmware with web GUI (HTTPS), CLI, SMS control and configuration, SNMP v1/v2c/v3 with traps, TR-069, HTTP(s) API [DS].
- VPN: OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier, MilesightVPN [DS].
- Remote management: Milesight DeviceHub, Milesight Development Platform, MilesightVPN [DS].
- Diagnostics: ping, traceroute, tcpdump, QXDM, log server, cellular AT command debugger, iptables debugger [DS].

## Compatibility and accessories
- Backhaul for Milesight LoRaWAN gateways without cellular, e.g. `milesight-ug56.md` (connect the gateway's WAN to the router LAN) (inferred use).
- Milesight's magnetic cellular antenna (700–960 / 1710–2700 MHz, SMA-J, 2 m) lists UR32 [VEN of UG56 page].
- Related Milesight routers in this KB: `milesight-ur35.md` (serial + I/O + GNSS), `milesight-ur41.md` (mini router).

## Common mistakes / troubleshooting
- **Factory reset:** with SYSTEM blinking, hold the reset button (under the SIM cover) for more than 5 s until SYSTEM blinks rapidly, release and wait; SYSTEM goes off and then blinks again when reset is done [UM].
- **No Internet over Ethernet:** LAN1 is a LAN port by default; change it to WAN and raise its priority in Link Failover [UM].
- **Weak cellular (one signal bar, 1–10 ASU):** check the antenna is fitted and move it [UM].
- **No PoE on LAN ports:** not a "-P" model, input below 48 V, hardware before v4.0, or LAN1/WAN set to WAN [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Serial / I/O on "UR32" | Task brief expected RS232/RS485/DI/DO terminals | [DS][PP] Cytron's "UR32 Series" is the UR32 **Lite** (UR32L/UR32S): no serial, I/O or GNSS | [DS] wins: no serial/I/O on Cytron's units |
| PoE out on UR32L | [DS] UR32L datasheet: "PoE (Optional) 2 × 802.3af/at PSE" | [PP] UR32L "PoE Out: Not supported" | PoE is a separate "-P" model [UM]; Cytron's `UR32L-L0GEU` has no PoE (inferred) |
| PoE out on Cytron's UR32S | [PP] "PoE Out (Optional)" listed for UR32S | [UM] only "-P" models; Cytron MPN `UR32S-L0GEU` | Cytron's unit has no PoE out (inferred from MPN); ask Cytron to qualify |
| UR32S box antennas | [DS] magnetic cellular antenna; stubby cellular optional; no Wi-Fi antenna listed | [PP] adds stubby cellular and stubby Wi-Fi antennas | Unresolved: confirm with Cytron (a Wi-Fi antenna is needed for UR32S Wi-Fi) |
| Cellular generations | [DS] 4G LTE Cat 4 / WCDMA / GSM, region-dependent | [PP] "global 4G LTE Cat 4" | [DS] |
| Warranty | [UM] UR32S user guide "3-year warranty included" | [PP] 12 months | Cytron's 12 months applies to Cytron sales |
| Price order | [PP] UR32S (with Wi-Fi) RM533.00 | [PP] UR32L (no Wi-Fi) RM603.00 | As listed on [PP]; looks inverted, confirm with Cytron |

## Needs verification
- LTE/3G/2G bands of the `-L0GEU` variants and whether they suit Malaysian operators (the "EU" suffix suggests a Europe band set — inferred).
- Power terminal polarity was read from a small drawing; confirm on the unit's label.
- UR32S hardware overview (Quick Guide PDF has no text layer).
- Whether Cytron's UR32S ships with a Wi-Fi antenna.

## Sources
- [DS] UR32S Datasheet: https://resource.milesight.com/milesight/iot/document/ur32s-datasheet-en.pdf; UR32L Datasheet: https://resource.milesight.com/milesight/iot/document/ur32l-datasheet-en.pdf (read 2026-10-21).
- [UM] UR32L Quick Start Guide V1.2, 30 Apr 2026: https://resource.milesight.com/milesight/iot/document/ur32l-quick-guide-en.pdf (read 2026-10-21).
- [UM] UR32S User Guide V1.7, 30 Apr 2026: https://resource.milesight.com/milesight/iot/document/ur32s-user-guide-en.pdf (web access, PoE settings, cellular settings). Not read (image only): https://resource.milesight.com/milesight/iot/document/ur32s-quick-guide-en.pdf; UR32L user guide https://resource.milesight.com/milesight/iot/document/ur32l-user-guide-en.pdf.
- [VEN] Milesight UR32 Lite page: https://www.milesight.com/iot/product/cellular/ur32lite (read 2026-10-21).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ur32-series-4g-industrial-router (redirects to https://my.cytron.io/Milesight/p-ur32s-4g-industrial-router; read 2026-10-21).
