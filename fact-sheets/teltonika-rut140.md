# Product fact sheets

## Product name
Teltonika RUT140 Industrial Ethernet Router
## Aliases
RUT140, RUT-140, RUT140000000, Teltonika RUT140, RUT140 Industrial Modbus Router
## What it is
A compact industrial Ethernet router with Wi-Fi and no cellular modem, made by Teltonika Networks and distributed by Cytron (product page). It isolates and connects end devices on an industrial network and runs RutOS, Teltonika's OpenWrt-based Linux OS (datasheet).
## Specs and functions
- No mobile module and no SIM slot (datasheet).
- Ethernet: 1 × WAN and 1 × LAN, 10/100 Mbps, IEEE 802.3az (datasheet).
- Wi-Fi: 802.11b/g/n (Wi-Fi 4), access point and station modes, up to 50 users, one RP-SMA connector (datasheet).
- CPU Mediatek 580 MHz MIPS 24KEc, 128 MB DDR2 RAM, 16 MB serial NOR flash (datasheet).
- Power: 9–30 VDC on a 3-position pluggable terminal block, or passive PoE on LAN1 (Mode B, 9–30 VDC); idle under 1 W, max under 2 W (datasheet).
- Status LEDs: WAN type, LAN type, power (datasheet).
- Grounding screw and integrated DIN rail bracket (datasheet).
- Housing: anodised aluminium, 113.10 × 25 × 68.6 mm, 142.3 g, IP30, -40 °C to 75 °C, 10–90 % RH (datasheet).
- Packing: router, 3-pin power connector, quick start guide; no power supply and no Wi-Fi antenna listed (product page, Teltonika ordering page).
## Interfaces and compatibility
- RJ45 × 2 (1 WAN, 1 LAN); LAN1 accepts passive PoE only, not IEEE 802.3af/at/bt (datasheet).
- 3-pin pluggable power terminal; pin order [NOT STATED] here (Wiki could not be opened).
- Protocols: Modbus TCP server and client, Modbus–MQTT gateway, DNP3 (TCP), BACnet/IP router, OPC UA, DLMS (TCP), MQTT, SNMP, TR-069, JSON-RPC, RMS (datasheet).
- VPN: OpenVPN, IPsec, WireGuard, ZeroTier, GRE, L2TP, PPTP, SSTP, DMVPN, Stunnel, Tinc, EoIP (datasheet).
- IoT platforms: Cumulocity – Cloud of Things, Azure IoT Hub (datasheet).
- Cytron suggests a 4G Mobile Magnetic SMA Antenna as an accessory, but this model has no cellular port (product page, datasheet).
## Use cases
- Network segmentation that isolates end devices on an industrial network (product page).
- Wired-to-Wi-Fi bridge or Wi-Fi client uplink for a machine (datasheet).
- Modbus TCP, DNP3, DLMS or OPC UA data to an MQTT or HTTP server (datasheet).
- Small DIN-rail VPN gateway into a control cabinet (datasheet).
## Known limitations
- No cellular, no SIM, no SMS or call control (datasheet).
- No I/O, no serial port, no USB (datasheet).
- Ethernet is 10/100 Mbps only, with just 2 ports (datasheet).
- Wi-Fi is 2.4 GHz Wi-Fi 4 only (datasheet).
- No power supply in the box; a 9–30 VDC source is needed (product page, Teltonika ordering page).
- Passive PoE only; a standard 802.3af/at PoE switch will not power it (datasheet).
- SIRIM is not in Teltonika's certifications list for this model (Teltonika certifications page).
## Positioning (kept apart from specs)
- Teltonika: "Industrial Modbus Router" with industrial protocols and RMS (Teltonika product page).
- Cytron: compact industrial Ethernet router that enhances security through network isolation (product page).
- Comes with a free 30-day trial of Teltonika RMS (product page).
## Price band
RM312.00, or RM302.64 each for 3 or more (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/m-teltonika/p-rut140-industrial-ethernet-router
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://teltonika-networks.com/products/routers/rut140
