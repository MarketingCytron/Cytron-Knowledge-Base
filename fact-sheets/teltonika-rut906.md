# Product fact sheets

## Product name
Teltonika RUT906 LTE Cat 4 Industrial Grade Router
## Aliases
RUT906, RUT-906, RUT906000400, Teltonika RUT906, RUT906 4G LTE RS232/RS485 Router, RUT906 Cellular Router
## What it is
An industrial 4G LTE Cat 4 dual-SIM cellular router with GNSS, RS232, RS485, USB and I/O, made by Teltonika Networks and distributed by Cytron (product page). It runs RutOS, Teltonika's OpenWrt-based Linux OS. Compared with the RUT901 it adds GNSS, RS232, RS485, USB host, microSD and a 10-pin I/O socket on the same platform (datasheet).
## Specs and functions
- Mobile: 4G LTE Cat 4 up to 150 Mbps down / 50 Mbps up; 3G up to 21 / 5.76 Mbps; 2G up to 236.8 kbps; 3GPP Release 9 (datasheet).
- Cytron's order code RUT906000400 is the "0*****" version: LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B8; 2G B2, B8; Universal PSU; no eSIM (Teltonika ordering page).
- Two Mini SIM (2FF) slots with auto failover and SIM idle protection (datasheet).
- Ethernet: 1 × WAN and 3 × LAN, 10/100 Mbps (datasheet).
- Wi-Fi: 802.11b/g/n (Wi-Fi 4), access point and station modes, up to 100 users (datasheet).
- GNSS: GPS, with GLONASS, BeiDou, Galileo and QZSS listed as under development; NMEA 0183, NTRIP, geofencing (datasheet).
- Serial: RS232 on a DB9 socket with RTS/CTS, 300–115200 baud; RS485 on a 6-pin socket, 2-wire or 4-wire, 300–230400 baud (datasheet).
- Inputs: dry input 0–3 V, isolated input 0–30 V, analog input 0–24 V or 4–20 mA, plus a digital input on the 4-pin power socket (0–5 V low, 8–30 V high) (datasheet).
- Outputs: open collector 30 V 250 mA, SPST relay 40 V 4 A, plus an open collector output 30 V 300 mA on the 4-pin power socket (datasheet).
- USB 2.0 host and internal microSD up to 2 TB (datasheet).
- CPU Mediatek 580 MHz MIPS 24KEc, 128 MB DDR2 RAM, 16 MB SPI flash (datasheet).
- Power: 9–30 VDC on a 4-pin industrial socket, or passive PoE on LAN1 (Mode B, 9–30 VDC); under 2 W idle, under 7 W max (datasheet).
- Housing: aluminium with plastic panels, 109.5 × 50 × 100 mm, 295 g, IP30, -40 °C to 75 °C, 10–90 % RH (datasheet).
- Packing: router, 9 W PSU, 2 magnetic mobile antennas, 2 magnetic Wi-Fi antennas, GNSS antenna, RS485 and I/O connector blocks, Ethernet cable, SIM adapter kit, quick start guide (product page).
## Interfaces and compatibility
- RJ45 × 4 (1 WAN, 3 LAN); LAN1 accepts passive PoE only, not IEEE 802.3af/at/bt (datasheet).
- 10-pin industrial I/O socket, 6-pin RS485 socket, DB9 RS232 socket, USB A host, 4-pin power socket with DI/DO (datasheet).
- Antenna connectors: 2 × SMA (LTE), 2 × RP-SMA (Wi-Fi), 1 × SMA (GNSS) (datasheet).
- Protocols: Modbus RTU/TCP server and client, Modbus–MQTT gateway, DNP3 (serial, TCP, USB), BACnet (IP and RS485/USB), OPC UA, DLMS (serial, TCP), MQTT, SNMP, TR-069, JSON-RPC, RMS (datasheet).
- VPN: OpenVPN, IPsec, WireGuard, ZeroTier, GRE, L2TP, PPTP, SSTP, DMVPN, Stunnel, Tinc (datasheet).
- Approvals listed by Teltonika include SIRIM, RCM, IMDA, CE/RED and E-mark (Teltonika certifications page).
- Pin numbers for the power, I/O and RS485 sockets are [NOT STATED] here; they are on the Teltonika Wiki, which could not be opened (Wiki).
- Sold separately by Cytron: Teltonika DIN Rail Kit and Teltonika 4G Mobile Magnetic SMA Antenna (product page).
## Use cases
- Connectivity for mobile agricultural machines (product page).
- Remote access to Siemens PLCs (product page).
- Control of a wastewater treatment plant (product page).
- Remote vending machine and parcel terminal management (product page).
- Modbus RTU to cloud or MQTT gateway for serial PLCs and meters (datasheet).
- Vehicle or asset tracking with GNSS and geofencing (datasheet).
## Known limitations
- GNSS is GPS only for now; other constellations are listed as under development (datasheet).
- Ethernet is 10/100 Mbps only (datasheet).
- Wi-Fi is 2.4 GHz Wi-Fi 4 only (datasheet).
- Passive PoE only; a standard 802.3af/at PoE switch will not power it (datasheet).
- Dry input is 0–3 V; the open collector outputs are limited to 30 V and 250–300 mA (datasheet).
- IP30 housing; mounting needs an extra kit (datasheet).
- Cytron's order code has no eSIM, and Teltonika's region list for it does not name Malaysia (Teltonika ordering page).
## Positioning (kept apart from specs)
- Teltonika: "4G LTE RS232/RS485 Router" for industrial IoT, with GNSS and failsafe features such as dual SIM, auto-failover and backup WAN (Teltonika product page).
- Cytron: designed for industrial IoT applications with serial interfaces, MQTT and BACnet, I/O and Ethernet (product page).
- Comes with a free 30-day trial of Teltonika RMS (product page).
## Price band
RM821.00, or RM796.37 each for 3 or more (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/m-teltonika/p-rut906-lte-cat-4-industrial-grade-router
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://teltonika-networks.com/products/routers/rut906
