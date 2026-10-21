# Product fact sheets

## Product name
Milesight UR35 Series 4G Industrial Router
## Aliases
UR35, V-IND-UR35, IND-UR35, IND-UR35-W, IND-UR35-P-W, UR35-L0GEU, UR35-L0GEU-W, UR35-L0GEU-P-W, Milesight UR35
## What it is
A 4G LTE Cat 4 industrial cellular router with dual SIM, five Ethernet ports, RS232 and RS485 serial and one digital input and output, made by Milesight and distributed in Malaysia by Cytron (product page). Wi-Fi and PoE output are optional by variant (datasheet).
## Specs and functions
- Cytron variants: With PoE/Wi-Fi (UR35-L0GEU-P-W, RM1,226.95), With Wi-Fi (UR35-L0GEU-W, RM1,068.00), Without PoE/Wi-Fi (UR35-L0GEU, RM1,011.70) (product page).
- Cellular: 4G LTE Cat 4 / WCDMA / GSM by region, 2 × mini SIM with dual-SIM backup, 2 × SMA female antenna connectors (datasheet).
- Ethernet: 5 × RJ45 10/100 Mbps, 1 WAN + 4 LAN (datasheet).
- PoE output on -P models: 4 × 802.3af/at PSE, 30 W per port, 60 W total, 48 V input needed (datasheet).
- Wi-Fi on -W models: 802.11 b/g/n 2.4 GHz, AP or client, up to 15 users (datasheet).
- Serial: 1 × RS232 + 1 × RS485 on a 3.5 mm terminal block, 300–230400 bps (datasheet).
- DI/DO: 1 dry-contact input and 1 wet-contact output (max 0.3 A at 30 VDC), galvanically isolated (datasheet).
- 8-pin terminal: 1 DI, 2 GND, 3 RS485 B, 4 RS232 TXD, 5 DO COM, 6 DO OUT, 7 RS485 A, 8 RS232 RXD (quick guide).
- Power: 9–48 VDC on a 2-pin 5.08 mm terminal (pin 9 positive red, pin 10 negative black), surge and reverse-polarity protected; typical 3.9 W, max 4.6 W (datasheet, quick guide).
- CPU Cortex-A7 528 MHz, 128 MB RAM, 128 MB flash, micro SD slot, Python SDK (datasheet).
- IP30 black metal, 135 × 103 × 45 mm, 485 g, -40 °C to +70 °C (datasheet).
- Default LAN IP 192.168.1.1; the default login is not copied here (quick guide).
- Packing: router, power adapter, 8-pin terminal, DIN rail kit, 2 magnetic cellular antennas, quick start guide, warranty card; Wi-Fi antenna on Wi-Fi versions (product page).
## Interfaces and compatibility
- Serial modes: transparent TCP/UDP/MQTT, Modbus server and client, Modbus RTU to TCP gateway, DLMS client (datasheet).
- DI readable and DO controllable by SMS, CLI, Modbus and MQTT (datasheet).
- VPN: OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier, MilesightVPN (datasheet).
- Managed through DeviceHub and Milesight Development Platform; HTTP(s) API, MQTT API and CLI documentation available (datasheet, product page).
- Desktop, wall or 35 mm DIN rail mounting; grounding stud (datasheet, quick guide).
## Use cases
- Remote field equipment and automation cabinets needing cellular Internet (product page).
- Modbus RTU meters and PLCs bridged to Modbus TCP or MQTT over 4G (datasheet).
- Powering IP cameras on site with the PoE variant (product page).
- Alarm input and remote output switching by SMS or MQTT (datasheet).
## Known limitations
- Ethernet is 10/100 Mbps; Wi-Fi is 2.4 GHz only (datasheet).
- DO max 0.3 A at 30 VDC; DI is dry contact only (datasheet).
- PoE output only on -P variants and only with a 48 V supply (datasheet).
- IP30: indoor or cabinet use (datasheet).
- No hot-plugging of SIM or micro SD (quick guide).
- LTE bands of the -L0GEU variants are not stated (datasheet).
## Positioning (kept apart from specs)
- Milesight: industrial 4G LTE router for mission-critical IoT (Milesight page).
- Cytron: rugged router that bridges legacy serial equipment and remote infrastructure, with centralized fleet management (product page).
- Milesight states a 3-year warranty in the UR35 user guide; Cytron lists 12 months (user guide, product page).
## Price band
RM1,011.70 (Without PoE/Wi-Fi) to RM1,226.95 (With PoE/Wi-Fi) (Cytron product page, read 2026-10-21; out of stock or enquiry)
## Product page
https://my.cytron.io/Milesight/p-ur35-series-4g-industrial-router
## Datasheet
https://resource.milesight.com/milesight/iot/document/ur35-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ur35-datasheet-en.pdf
