# Product fact sheets

## Product name
Teltonika RUT956 LTE Cat 4 Industrial Grade Router
## Aliases
RUT956, RUT-956, RUT956200100, Teltonika RUT956, RUT956 industrial cellular router
## What it is
An industrial 4G LTE Cat 4 cellular router made by Teltonika Networks and distributed in Malaysia by Cytron (product page). It combines dual SIM, Ethernet, 2.4 GHz Wi-Fi, GNSS, RS232, RS485 and digital/analog I/O, and runs RutOS, Teltonika's OpenWrt-based Linux OS (datasheet).
## Specs and functions
- Mobile: 4G LTE Cat 4 up to 150 Mbps down / 50 Mbps up; 3G up to 21 / 5.76 Mbps; 2G up to 236.8 kbps (datasheet).
- Cytron's order code RUT956200100 is the "2*****" version: LTE-FDD B1, B3, B7, B8, B20, B28A; LTE-TDD B38, B40, B41; 3G B1, B8; 2G B3, B8; UK PSU (Teltonika ordering page).
- Two Mini SIM (2FF) slots with auto failover; eSIM only on other order codes (datasheet, Teltonika ordering page).
- Ethernet: 1 × WAN and 3 × LAN, 10/100 Mbps (datasheet).
- Wi-Fi: 802.11b/g/n (Wi-Fi 4), access point and station modes, up to 100 users (datasheet).
- GNSS: GPS, GLONASS, BeiDou, Galileo and QZSS (datasheet).
- Serial: RS232 on a DB9 socket with RTS/CTS; RS485 on a 6-pin socket, 2-wire or 4-wire, 300–115200 baud (datasheet).
- Inputs: dry input 0–3 V, isolated input 0–30 V, analog input 0–24 V or 4–20 mA, plus a digital input on the 4-pin power socket (datasheet).
- Outputs: open collector 30 V 250 mA, SPST relay 40 V 4 A, plus an open collector output 30 V 300 mA on the 4-pin power socket (datasheet).
- CPU Mediatek 580 MHz MIPS 24KEc, 128 MB DDR2 RAM, 16 MB SPI flash, internal microSD up to 2 TB (datasheet).
- Power: 9–30 VDC on a 4-pin industrial socket, or passive PoE on LAN1 (Mode B, 9–30 VDC); under 2 W idle, under 7 W max (datasheet).
- Housing: aluminium with plastic panels, 110 × 50 × 100 mm, 287 g, IP30, -40 °C to 75 °C (datasheet).
- Packing: router, 9 W PSU, 2 mobile antennas, 2 Wi-Fi antennas, GNSS antenna, RS485 and I/O connector blocks, Ethernet cable, SIM adapter kit, quick start guide (product page).
## Interfaces and compatibility
- RJ45 × 4 (1 WAN, 3 LAN); LAN1 accepts passive PoE only, not IEEE 802.3af/at/bt (datasheet).
- 10-pin industrial I/O socket, 6-pin RS485 socket, DB9 RS232 socket, USB A host, 4-pin power socket with DI/DO from HW revision 1600 (datasheet).
- Antenna connectors: 2 × SMA (LTE), 2 × RP-SMA (Wi-Fi), 1 × SMA (GNSS) (datasheet).
- Protocols: Modbus RTU/TCP server and client, DNP3, BACnet, OPC UA, DLMS, MQTT, SNMP, TR-069, JSON-RPC, RMS (datasheet).
- VPN: OpenVPN, IPsec, WireGuard, ZeroTier, GRE, L2TP, PPTP, SSTP, DMVPN, Tinc (datasheet).
- Pin numbers for the power, I/O and RS485 sockets are [NOT STATED] here; they are on the Teltonika Wiki, which could not be opened (Wiki).
## Use cases
- Bus monitoring systems (product page).
- Radio broadcast links (product page).
- Grain silo connectivity (product page).
- Tailings storage facility safety monitoring in mines (product page).
- Remotely operated underwater vehicles (product page).
- Modbus RTU to cloud or MQTT gateway for serial PLCs and meters (datasheet).
## Known limitations
- Ethernet is 10/100 Mbps only (datasheet).
- Wi-Fi is 2.4 GHz Wi-Fi 4 only (datasheet).
- Passive PoE only; a standard 802.3af/at PoE switch will not power it (datasheet).
- Supply 9–30 VDC; surge protection above 31 VDC for 10 µs only (datasheet).
- Dry input is 0–3 V; the open collector outputs are limited to 30 V and 250–300 mA (datasheet).
- IP30 housing; mounting needs an extra kit (datasheet).
- Cytron's order code has no eSIM (inferred from the Teltonika ordering page).
## Positioning (kept apart from specs)
- Teltonika: "industrial cellular router" that combines cellular, Wi-Fi and wired connectivity with automatic WAN failover and GNSS (Teltonika product page).
- Cytron: serial and I/O let it integrate varied devices for equipment control, automation and event notifications (product page).
- Comes with a free 30-day trial of Teltonika RMS (product page).
## Price band
RM1,205.00, or RM1,168.85 each for 5 or more (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/m-teltonika/p-rut956-lte-cat-4-industrial-grade-router
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://teltonika-networks.com/products/routers/rut956
