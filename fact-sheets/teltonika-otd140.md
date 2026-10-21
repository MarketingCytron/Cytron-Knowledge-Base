# Product fact sheets

## Product name
Teltonika OTD140 LTE Cat 4 Industrial Grade Outdoor Router
## Aliases
OTD140, RUT-OTD-140, OTD140000000, Teltonika OTD140, OTD140 outdoor 4G router
## What it is
An outdoor 4G LTE Cat 4 router made by Teltonika Networks and distributed in Malaysia by Cytron (product page). It has an IP55 plastic housing with a pole/wall bracket, internal antennas, dual SIM and two Ethernet ports, one PoE-in that powers the router and one PoE-out that powers a downstream device, and runs RutOS (datasheet).
## Specs and functions
- Mobile: 4G LTE Cat 4 up to 150 Mbps down / 50 Mbps up; 3G up to 21 / 5.76 Mbps; 2G up to 236.8 kbps (datasheet).
- Bands of the only listed version (OTD140 0*****): LTE-FDD B1, B3, B5, B7, B8, B20, B28; LTE-TDD B38, B40, B41; 3G B1, B5, B8; 2G B3, B8 (Teltonika ordering page).
- Two Mini SIM (2FF) slots with automatic failover (datasheet).
- Ethernet: 2 × RJ45 10/100 Mbps, both configurable as WAN (datasheet).
- PoE-in: IEEE 802.3af/at, 42.5–57.0 VDC, reverse polarity and surge protection; this is the only power input (datasheet).
- PoE-out: IEEE 802.3af Alternative B, up to 15 W, depending on the upstream power supply (datasheet).
- Power consumption: idle under 2.5 W, max under 6 W, under 21 W with PoE-out loaded (datasheet).
- Antennas: 2 internal omnidirectional LTE antennas, 698–960 / 1710–2690 MHz, gain under 4.5 dBi (datasheet).
- CPU Mediatek 580 MHz MIPS 24KEc, 128 MB RAM, 16 MB flash (datasheet).
- Housing: PC+ASA plastic, IP55, 110 × 49.3 × 235 mm, 315 g, -40 °C to 75 °C, 10–90 % RH (datasheet).
- Mounting: integrated bracket for a vertical flat surface or a pole (datasheet).
- Packing: 1 × OTD140 router; no PSU or PoE injector listed (product page).
## Interfaces and compatibility
- Two RJ45 ports only: PoE-in and PoE-out; no DC terminal, no Wi-Fi, no serial port, no I/O and no USB are listed (datasheet).
- Needs a separate IEEE 802.3af/at PoE injector or PoE switch (inferred from the datasheet and packing list).
- Powers 802.3af cameras or access points up to 15 W from PoE-out (datasheet).
- Protocols over TCP: Modbus, DNP3, BACnet/IP, OPC UA, DLMS, MQTT, SNMP, TR-069, JSON-RPC, RMS (datasheet).
- VPN: OpenVPN, IPsec, WireGuard, ZeroTier, GRE, L2TP, PPTP, SSTP, DMVPN, Tinc (datasheet).
- Which RJ45 is PoE-in and which is PoE-out is [NOT STATED] here; it is on the Teltonika Wiki, which could not be opened (Wiki).
## Use cases
- Construction site CCTV and portable offices (product page).
- Underground EV charging stations (product page).
- Security surveillance and agriculture sites (product page).
- Public Wi-Fi zones, paired with a PoE access point (product page; pairing inferred).
## Known limitations
- Powered only by 802.3af/at PoE at 42.5–57.0 VDC; passive 12/24 V PoE will not work (datasheet).
- PoE-out is limited to 15 W and depends on the upstream supply (datasheet).
- Ethernet is 10/100 Mbps only (datasheet).
- No Wi-Fi, no serial, no I/O, no external antenna connector (datasheet).
- LTE Cat 4 (3GPP Release 9) only (datasheet).
## Positioning (kept apart from specs)
- Teltonika: "IP55 pioneer" outdoor 4G router that is easy to deploy and withstands outdoor conditions (Teltonika product page).
- Cytron: robust outdoor router for reliable connectivity in challenging environments (product page).
- Comes with a free 30-day trial of Teltonika RMS (product page).
## Price band
RM701.00, or RM679.97 each for 3 or more (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/m-teltonika/p-otd140-lte-cat-4-industrial-grade-outdoor-router
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://teltonika-networks.com/products/routers/otd140
