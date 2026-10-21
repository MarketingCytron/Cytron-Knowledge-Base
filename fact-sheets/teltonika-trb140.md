# Product fact sheets

## Product name
Teltonika TRB140 LTE Cat 4 Ethernet Gateway
## Aliases
TRB140, TRB-140, TRB140005000, Teltonika TRB140, TRB140 industrial LTE gateway
## What it is
A very small industrial 4G LTE Cat 4 gateway made by Teltonika Networks and distributed in Malaysia by Cytron (product page). It connects one Ethernet device to the mobile network, has one digital input and one digital output on its power socket, and runs RutOS, Teltonika's OpenWrt-based Linux OS (datasheet).
## Specs and functions
- Mobile: 4G LTE Cat 4 up to 150 Mbps down / 50 Mbps up; 3G up to 21 / 5.76 Mbps; 2G up to 236.8 kbps (datasheet).
- Cytron's order code TRB140005000 is the "0*****" version: LTE-FDD B1, B3, B7, B8, B20, B28A; LTE-TDD B38, B40, B41; 3G B1, B8; 2G B3, B8; Malaysia is in its region list; UK PSU (Teltonika ordering page).
- One Mini SIM (2FF) slot (datasheet).
- Ethernet: 1 × RJ45 10/100/1000 Mbps (datasheet).
- Micro USB: virtual network interface to a PC (datasheet).
- I/O on the 4-pin power socket: 1 digital input (0–6 V low, 8–30 V high) and 1 open collector output (30 V, 300 mA) (datasheet).
- ARM Cortex-A7 1.3 GHz, 128 MB DDR2 RAM, 512 MB SPI flash (datasheet).
- Power: 9–30 VDC on a 4-pin socket, or passive PoE on the Ethernet port (Mode B, 9–30 VDC); under 5 W (datasheet).
- Housing: aluminium, 74.5 × 25 × 64.4 mm, 136 g, IP30, -40 °C to 75 °C (datasheet).
- Packing: gateway, 9 W PSU, magnetic LTE antenna (SMA, 3 m), micro-USB cable, hex key, LAN cable, quick start guide (product page).
## Interfaces and compatibility
- One Gigabit RJ45 port; passive PoE only, not IEEE 802.3af/at/bt (datasheet).
- One SMA LTE antenna connector (datasheet).
- Micro USB is a device port for PC setup, not a USB host (datasheet).
- No Wi-Fi and no serial port (datasheet).
- Protocols over TCP: Modbus, DNP3, BACnet/IP, OPC UA, DLMS, MQTT, SNMP, TR-069, JSON-RPC, RMS (datasheet).
- VPN: OpenVPN, IPsec, WireGuard, ZeroTier, GRE, L2TP, PPTP, SSTP, DMVPN, Stunnel (product page).
- Pin order of the 4-pin power/I/O socket is [NOT STATED] here; it is on the Teltonika Wiki, which could not be opened (Wiki).
## Use cases
- Water quality monitoring and water purification data links (product page).
- Remote monitoring of solar power plants (product page).
- Digital signage connectivity (product page).
- Vending machine POS and parcel terminal management (product page).
- Giving a single PLC, HMI or controller a 4G link with SMS alarms from its DI (datasheet; pairing inferred).
## Known limitations
- Only one Ethernet port and static routing only (datasheet).
- Only one SIM, one antenna and one DI plus one DO (datasheet).
- Passive PoE only; a standard 802.3af/at PoE switch will not power it (datasheet).
- IP30 housing; DIN, wall or flat mounting needs an extra kit (datasheet).
- Cytron's page lists "2 x configurable I/O"; Teltonika's specification lists 1 DI and 1 DO (datasheet, product page).
## Positioning (kept apart from specs)
- Teltonika: "industrial rugged LTE gateway"; ultra-small, lightweight and energy-efficient, for projects where a single device needs reliable internet (Teltonika product page).
- Cytron: specially engineered for the industrial sector with SMS control, firewall, VPN, RMS and FOTA (product page).
- Comes with a free 30-day trial of Teltonika RMS (product page).
## Price band
RM658.00, or RM638.26 each for 5 or more (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/m-teltonika/p-trb140-lte-cat-4-ethernet-gateway
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://teltonika-networks.com/products/gateways/trb140
