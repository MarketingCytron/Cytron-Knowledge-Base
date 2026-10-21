# Product fact sheets

## Product name
Teltonika RUT901 LTE Cat 4 Industrial Grade Router
## Aliases
RUT901, RUT-901, RUT90100040021, RUT901000400, Teltonika RUT901, RUT901 4G dual SIM router
## What it is
An industrial 4G LTE Cat 4 dual-SIM cellular router made by Teltonika Networks and distributed by Cytron (product page). It has four Ethernet ports and 2.4 GHz Wi-Fi and runs RutOS, Teltonika's OpenWrt-based Linux OS. Unlike the RUT906 it has no GNSS, no RS232/RS485, no USB, no microSD and no 10-pin I/O socket (datasheet).
## Specs and functions
- Mobile: 4G LTE Cat 4 up to 150 Mbps down / 50 Mbps up; 3G up to 21 / 5.76 Mbps; 2G up to 236.8 kbps; 3GPP Release 9 (datasheet).
- Bands of the RUT901 0***** version (nearest match to Cytron's MPN): LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B5, B8; 2G B3, B8 (Teltonika ordering page).
- Two Mini SIM (2FF) slots with auto failover and SIM idle protection; eSIM needs different hardware (datasheet).
- Ethernet: 1 × WAN and 3 × LAN, 10/100 Mbps (datasheet).
- Wi-Fi: 802.11b/g/n (Wi-Fi 4), access point and station modes, up to 100 users, 2 RP-SMA connectors (datasheet).
- I/O on the 4-pin power socket: 1 digital input (0–6 V low, 8–30 V high) and 1 open collector output (30 V, 300 mA) (datasheet).
- CPU Mediatek 580 MHz MIPS 24KEc, 128 MB DDR2 RAM, 16 MB SPI flash (datasheet).
- Power: 9–30 VDC on a 4-pin industrial socket, or passive PoE on LAN1 (Mode B, 9–30 VDC); under 2 W idle, under 7 W max (datasheet).
- Housing: aluminium with plastic panels, 110 × 50 × 100 mm, 297 g, IP30, -40 °C to 75 °C, 10–90 % RH (datasheet).
- Packing: router, 9 W PSU, 2 swivel mobile antennas, 2 swivel Wi-Fi antennas, 1.5 m Ethernet cable, SIM adapter kit, quick start guide (product page).
## Interfaces and compatibility
- RJ45 × 4 (1 WAN, 3 LAN); LAN1 accepts passive PoE only, not IEEE 802.3af/at/bt (datasheet).
- Antenna connectors: 2 × SMA (LTE), 2 × RP-SMA (Wi-Fi) (datasheet).
- Protocols: Modbus TCP server and client, Modbus–MQTT gateway, DNP3 (TCP), BACnet/IP router, DLMS (TCP), MQTT, SNMP, TR-069, JSON-RPC, RMS; OPC UA not listed (datasheet).
- VPN: OpenVPN, IPsec, WireGuard, ZeroTier, GRE, L2TP, PPTP, SSTP, DMVPN, Stunnel, Tinc (datasheet).
- Approvals listed by Teltonika include SIRIM, RCM, IMDA, CE/RED and E-mark (Teltonika certifications page).
- Pin numbers for the 4-pin power socket are [NOT STATED] here; they are on the Teltonika Wiki, which could not be opened (Wiki).
- Sold separately by Cytron: Teltonika DIN Rail Kit and Teltonika 4G Mobile Magnetic SMA Antenna (product page).
## Use cases
- Remote management of boring and milling equipment (product page).
- Remote image control for armoured trucks (product page).
- 4G connectivity for retail sites, vending machines and parcel terminals (product page).
- Wi-Fi mesh for autonomous pallet shuttles (product page).
- Dual-SIM failover link for a small industrial LAN of up to 3 wired devices plus Wi-Fi (datasheet).
## Known limitations
- No GNSS, no RS232/RS485, no USB, no microSD; Modbus is TCP only (datasheet).
- Only one DI and one DO, both on the power socket (datasheet).
- Ethernet is 10/100 Mbps only (datasheet).
- Wi-Fi is 2.4 GHz Wi-Fi 4 only (datasheet).
- Passive PoE only; a standard 802.3af/at PoE switch will not power it (datasheet).
- IP30 housing; mounting needs an extra kit (datasheet).
- Cytron's MPN does not match a Teltonika order code and the page shows no warranty (product page, Teltonika ordering page).
## Positioning (kept apart from specs)
- Teltonika: "industrial cellular router" that delivers the top-rated features of its predecessors, the RUT950 and RUT951 (Teltonika product page).
- Cytron: compact industrial 4G router with automatic WAN failover for professional industrial use cases (product page).
- Comes with a free 30-day trial of Teltonika RMS (product page).
## Price band
RM749.00, or RM726.53 each for 3 or more (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/m-teltonika/p-rut901-lte-cat-4-industrial-grade-router
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://teltonika-networks.com/products/routers/rut901
