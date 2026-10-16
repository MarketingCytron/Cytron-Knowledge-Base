# IRIV IOC MQTT Gateway — Verified Reference

| | |
|---|---|
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | *IRIV IOC MQTT Gateway — IR4.0 Industrial I/O Controller, Datasheet*, **Rev 1.0, June 2026** (Google Doc, last modified 2026-08-03), Cytron Technologies Sdn Bhd |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
An IRIV IO Controller (RP2350A industrial I/O controller) that ships **preloaded from the factory with Cytron's "MQTT Gateway Firmware"** [DS]. The firmware publishes the unit's digital inputs, analog inputs and Modbus RTU (RS485) data to an MQTT broker over Ethernet, and is configured from a web page with no coding [DS]. It is a microcontroller device, not a Linux computer [DS].

**How it differs from the IRIV IO Controller (IRIV-IOC)** (only differences a source states):
| Item | IRIV IOC MQTT Gateway | IRIV IO Controller | Src |
|---|---|---|---|
| Firmware | Preloaded "MQTT Ready Gateway" firmware. "Do not erase or overwrite it with other firmware" | User-programmed (e.g. CircuitPython UF2). The IOC DS names no firmware | [DS]; IOC KB |
| MQTT transport | Standard MQTT, port 1883; no TLS/SSL on the device | No firmware-level MQTT stated | [DS] |
| Firmware licence | Locked to the CPU ID; a factory reset keeps the licence | — | ; [DS] |
| User button (GP28) | Hold 10 s during boot until the buzzer beeps = factory reset (configuration wiped, licence kept) | Programmable button | [DS] |
| USR LED (GP29) | Shows network/MQTT status (blink patterns below) | Programmable LED | [DS] |
| Buzzer | Beeps when a factory reset is triggered | Free for user tones | [DS] |
| RTC (PCF85063A) | Fitted, but "not used by the MQTT Gateway firmware" | Usable | [DS] |
| USB-C role | "Used for configuration"; web configuration at 10.0.0.1 | Programming and configuration | [DS];  |
| Datasheet | Rev 1.0, June 2026 | Rev 1.0, July 2024 | [DS] |
All electrical specifications, pin mapping, terminals and dimensions are identical in the two datasheets.

- The story: exhibition visitors with a software/IT background, not familiar with hardware or firmware, wanted "a gateway that can send data to their server for further processing and visualization, out of the box".
- Target audience: Automation & Controls Engineers, IoT Solutions Architects & Integrators, SCADA / MES Administrators, IT / Cloud Engineers. Their industries: Manufacturing / Factory Automation, Energy & Utilities, Water & Wastewater Management, Smart Building & Facility Management.
  - Remote Asset & Utility Monitoring: flow meters, pumps and environmental sensors across distributed water or energy grids over cellular networks.
  - Factory Floor Digitalization: machine health parameters, production cycle counts and downtime alerts feeding predictive-maintenance dashboards.
  - Smart Facilities & Building Automation: HVAC performance, energy sub-metering and safety alarms across a corporate or university campus in a unified cloud interface.

## Specifications
| Item | Value | Src |
|---|---|---|
| Firmware | MQTT Ready Gateway. Uses standard MQTT (Port 1883) "to maintain fast I/O responsiveness and a minimal memory footprint". For external cloud encryption (TLS/SSL), route the data through a local secure broker or edge gateway | [DS] |
| Microcontroller | Raspberry Pi RP2350A, Dual Cortex-M33 @ 150MHz | [DS] |
| RAM | 520KB on-chip SRAM | [DS] |
| Storage | 2MB flash memory | [DS] |
| USB | 1x USB-C (For programming and configuration) | [DS] |
| Ethernet | 1x RJ45 Ethernet (via W5500 Ethernet controller); 10BaseT/100BaseTX PHY embedded | [DS] |
| RS485 | 1x isolated RS485 | [DS] |
| Digital inputs | 11x isolated digital input (up to 50V) | [DS] |
| Digital outputs | 4x isolated digital output (up to 50V) | [DS] |
| Analog inputs | 2x 12-bit analog input (0 - 10.56V / 0 - 42.58mA), non-isolated | [DS] |
| Power supply | DC 10-30V surge protected | [DS] |
| Power input, Terminal 1 | 10 – 30 VDC (Surge Protected up to 60V 20ms) | [DS] |
| Power input, USB-C | 4.9 – 5.2 VDC | [DS] |
| Power consumption | max 0.7 W | [DS] |
| DI low level (VIL) | max ±0.8 V | [DS] |
| DI high level (VIH) | ±3 to ±50 V | [DS] |
| DI maximum pulse frequency (50% duty cycle) | 5000 Hz | [DS] |
| DI isolation voltage | 3750 Vrms | [DS] |
| AI resolution | 12 bit | [DS] |
| AI voltage mode | 0 – 10.56 V | [DS] |
| AI current mode | 0 – 42.58 mA | [DS] |
| AI input impedance (voltage mode) | 32K Ω | [DS] |
| AI input impedance (current mode) | 248 Ω | [DS] |
| DO voltage | max 50 V | [DS] |
| DO current | max 500 mA | [DS] |
| DO isolation voltage | 1500 Vrms | [DS] |
| RS485 maximum baud rate | 500 kbps | [DS] |
| RS485 isolation voltage | 5000 Vrms | [DS] |
| Operating temperature | -20 to 70 ℃ | [DS] |
| Relative humidity (non-condensing) | 10 – 80 % | [DS] |
| RTC | PCF85063A, I2C address 0x51; "Insert a CR2032 coin cell to keep the RTC running when the system is powered off"; not used by the MQTT Gateway firmware | [DS §3.2] |
| Additional features | PCF85063A Real Time Clock; 1x reset button, 1x boot button & 1x programmable button; 1x programmable LED; status LED for Power, RS485, DIN & DOUT; 1x passive buzzer | [DS] |
| Enclosure | Metal enclosure, fanless design, DIN rail mountable | [DS] |
| Dimension | (L)140mm x (W)60mm x (H)36mm (metal enclosure only, excluding DIN socket & connectors) | [DS] |
| Drawing extras | DIN bracket adds 8mm; pluggable terminals stick out 15.5mm | [DS §6 drawing] |

## Interfaces, terminals and pin mapping
**RP2350A pin mapping** [DS §5.1]. The firmware owns these pins; they are listed for wiring reference and hardware understanding.
| Function | Signal | Peripheral | RP2350A pin |
|---|---|---|---|
| Digital Input | DI0 – DI10 | GPIO | GP0 – GP10 |
| Analog Input | AN0 / AN1 | ADC | GP26 / GP27 |
| Digital Output | DO0 / DO1 / DO2 / DO3 | GPIO | GP12 / GP13 / GP14 / GP15 |
| RS485 | TX / RX | UART1 | GP24 / GP25 |
| Ethernet (W5500) | INT / RESET / CSn | GPIO | GP18 / GP23 / GP21 |
| Ethernet (W5500) | MOSI / MISO / SCK | SPI0 | GP19 / GP20 / GP22 |
| Real Time Clock (PCF85063) | SDA / SCL | I2C0 | GP16 / GP17 |
| User Programmable Button | — | GPIO | GP28 |
| User Programmable LED | — | GPIO | GP29 |
| Passive Buzzer | — | GPIO/PWM | GP11 |

**Terminal 1** (left pluggable block; read from the DS §5.2 drawings) [DS]: left row V-, DGND, S/S0..4, DI0, DI1, DI2, DI3, DI4. Right row V+ (10-30V), A, B, G (RS485), AGND, AGND, AN0, AN1.
**Terminal 2** (right pluggable block) [DS]: left row DGND, S/S5..10, DI5, DI6, DI7, DI8, DI9, DI10. Right row DO0, DO1, DO2, DO3, two contacts each.
**Bottom DIP switches** [DS]: RS485 R-Term (ON connects the 120 Ω termination resistor; only needed on the first and last device in the chain) and AN-IN MODE (voltage or current). The drawing shows separate AN0 and AN1 switches.
**Front panel** [DS]: USB-C (PROG), RESET and BOOT (pinhole, press with a paperclip), USER button, status LEDs, RJ45 (ETH).

**USR LED network status** (MQTT Gateway firmware) [DS]:
| Pattern | Meaning |
|---|---|
| Slow Blink | Ethernet down |
| Solid On | Ethernet up, MQTT disabled |
| Single Pulse every 1.5s | Ethernet up, MQTT enabled but not reachable |
| Two Pulses every 3s | Ethernet up, MQTT connected |
Other LEDs: PWR on when powered; 485 on when there is RS485 activity; DOUT 0-3 on when the output is activated; DIN 0-10 on when the input is triggered [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Plain MQTT on port 1883, no TLS on the device** [DS]. For encrypted cloud links, route through a local secure broker or edge gateway [DS]. Do not write that the device itself connects securely or over TLS to cloud brokers.
- **Factory reset:** hold the USER button for 10 seconds during boot until the buzzer beeps. This wipes the configuration but keeps the licence [DS].
- **Use the USR LED for status checks**, e.g. two pulses every 3s = MQTT connected [DS].
- The RTC is not used by the firmware, so do not promise RTC timestamps from it [DS].
- **Wiring is the same as the IRIV IO Controller:**
  - DI groups: Group 1 = DI0–DI4 with S/S0..4 on Terminal 1; Group 2 = DI5–DI10 with S/S5..10 on Terminal 2. Inputs are active high [DS].
  - Dry contacts go between DGND and DIx. For PNP sensors, the external supply − goes to S/S; for NPN sensors, the supply + goes to S/S. PNP and NPN can be used at the same time on different groups [DS].
  - DOs are solid-state-relay dry contacts, active high, isolated from the system and from each other, DC or AC load ≤ 50V 500mA. Fit a flyback diode across inductive loads (optional, because the outputs have built-in surge protection) [DS].
  - Analog inputs are **not isolated** (AGND = system GND). The voltage/current mode is set with the bottom DIP switch [DS].
  - RS485 has automatic direction control. Wire A, B and also G for noise immunity [DS].
- No earth connection is required [DS].

## Power and electrical limits
- Terminal 1: 10–30 VDC, surge protected up to 60V for 20ms, with a **500 mA PTC** that may open on a surge or overcurrent. Wait for it to cool down; if the unit still fails, contact Cytron support [DS].
- Power consumption max 0.7 W [DS].
- DI: VIH ±3 to ±50 V, VIL max ±0.8 V, 5000 Hz max (50% duty), 3750 Vrms isolation [DS].
- DO: max 50 V / 500 mA, 1500 Vrms isolation [DS]. RS485: 500 kbps, 5000 Vrms isolation [DS].
- AI: 0–10.56 V (32K Ω) or 0–42.58 mA (248 Ω), 12-bit, non-isolated. Voltage scale: MCU = AN × 5/16 [DS schematic].
- Environment: -20 to 70 ℃, 10–80 % RH non-condensing [DS].

## Software support
- **Firmware:** Cytron "MQTT Gateway Firmware", preloaded at the factory [DS]. It was developed in-house by Cytron (RH2T) .
  - Dashboard: device uptime, free heap memory and a live I/O state panel.
  - Digital Inputs: point-and-click MQTT topic configuration with QoS and data retention toggles.
  - MQTT Broker: host and port setup with security authentication toggles.
  - Diagnostics: "Test Publish" and manual Modbus RTU register reads.
- **Ethernet stack** (W5500) [DS]: hardwired TCP, UDP, ICMP, IPv4, ARP, IGMP and PPPoE; 8 sockets; 32Kbytes Tx/Rx buffer; auto negotiation; SPI up to 80MHz. The DS states OT (MODBUS TCP) and IT (MQTT/HTTP) support at the W5500 level. It does not say that the gateway firmware offers MODBUS TCP.
- No user programming environment applies (see Rules).

## Compatibility and accessories
- RS485 for Modbus RTU field devices ; termination only at the bus ends [DS].
- DIN rail mountable [DS]. 3D CAD: "Same as IRIV IOC" .

## Common mistakes / troubleshooting
- **Writing CircuitPython/Arduino steps for this SKU.** Wrong: the factory firmware must not be overwritten [DS].
- **Claiming TLS/SSL or "secure" direct cloud connections.** The DS says standard MQTT port 1883; use a local secure broker or edge gateway for encryption [DS].
- **MQTT not connecting:** read the USR LED. One pulse every 1.5s means MQTT is enabled but the broker is not reachable; slow blink means Ethernet is down [DS].
- **Forgotten configuration:** hold USER for 10 s during boot until the beep (factory reset; the licence is kept) [DS].
- **Unit won't power up:** the 500 mA PTC opened; let it cool [DS].
- **Analog reads wrong:** check the AN-IN MODE switch; full scale is 10.56 V / 42.58 mA, not 10 V / 40 mA [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| User button / USR LED role | [DS] features + pin map: "programmable" button/LED | [DS] layout: user button = factory reset; USR LED = network status | Both in DS. Under the MQTT firmware, the layout-table functions apply |
| USB-C role | [DS] features "For programming and configuration" | [DS] layout "Used for configuration" | Both in DS; for this SKU, treat USB-C as configuration + power |
| MCU | [DS] RP2350A |  product idea "RP2350" | [DS] wins |
| RTC | [DS] features list the PCF85063A RTC | [DS] layout: "not used by the MQTT Gateway firmware" | Both true: fitted but unused |

## Needs verification
- Whether isolated I/O works on USB-C power only. Warranty, certifications, and whether the CR2032 is included.

## Sources
- [DS] IRIV IOC MQTT Gateway Datasheet, Rev 1.0, June 2026 (Google Doc, modified 2026-08-03; read in full, including the PDF export figures): (Cytron document — link not public)
- Comparison base: local KB file /home/claude/kb/iriv-io-controller.md (IRIV IO Controller Datasheet Rev 1.0, July 2024)
- [PP] Product page: not found and not read (cytron.io blocked).
