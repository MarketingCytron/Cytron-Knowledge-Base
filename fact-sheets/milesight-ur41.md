# Product fact sheets

## Product name
Milesight UR41 4G Mini Industrial Router
## Aliases
UR41, IND-UR41, UR41-L08EU, Milesight UR41, UR41 mini router
## What it is
A matchbox-sized 4G LTE Cat 4 industrial cellular router with GNSS, one Ethernet LAN port, one RS232/RS485 port and isolated digital I/O, made by Milesight and distributed in Malaysia by Cytron (product page). It has low-power standby and idle modes for battery or solar installs (datasheet).
## Specs and functions
- Cytron version: MPN UR41-L08EU (datasheet column UR41: LTE Cat 4 / WCDMA / GSM with GNSS) (product page, datasheet).
- Cellular: 1 × nano SIM (4FF), 1 × SMA female antenna connector, LTE Class 3 (datasheet).
- GNSS: GPS, GLONASS, BeiDou, Galileo and QZSS, 2.5 m CEP, SMA female connector (datasheet).
- Ethernet: 1 × RJ45 10/100 Mbps LAN port (datasheet).
- Serial: 1 × RS232 or 1 × RS485, software switchable, 300–230400 bps, 120 Ω RS485 termination switch (datasheet).
- DI/DO: 1 dry-contact input and 1 wet-contact output (max 0.3 A at 30 VDC), galvanically isolated (datasheet).
- 8-pin terminal: 1 DO OUT, 2 DI IN, 3 TX/A, 4 DC+, 5 DO COM, 6 GND, 7 RX/B, 8 DC− (user guide).
- Power: 5–24 VDC on the terminal or 5 V / 1 A on USB Type-C; at 12 V standby 6.3 mA, idle 78 mA, data 226 mA (datasheet).
- Standby mode with wake-up by schedule, SMS or DI (datasheet).
- CPU Cortex-A7 528 MHz, 128 MB RAM, 128 MB flash (datasheet).
- IP30 metal, 70 × 55 × 22 mm, 103 g, -40 °C to +60 °C (datasheet).
- Default LAN IP 192.168.1.1; the default login is not copied here (user guide).
- Packing: router, power adapter, 8-pin terminal, SIM ejector, wall bracket and kits, magnetic cellular antenna, GPS antenna, quick start guide, warranty card (product page).
## Interfaces and compatibility
- Serial modes: transparent TCP/UDP/MQTT, Modbus TCP/RTU client, Modbus RTU to TCP gateway, DLMS client (datasheet).
- DI readable and DO controllable by SMS, CLI, Modbus and MQTT (datasheet).
- USB 2.0 Type-C for power, network and debug (datasheet).
- VPN: OpenVPN, IPsec, GRE, L2TP, PPTP, DMVPN, WireGuard, ZeroTier, MilesightVPN (datasheet).
- Managed through DeviceHub and Milesight Development Platform; UR Series MQTT API and CLI documentation (datasheet, product page).
- Desktop, wall or 35 mm DIN rail mounting (datasheet, user guide).
## Use cases
- Vending machines, robots and industrial equipment needing 4G (user guide).
- Battery or solar-powered remote terminal units (product page).
- Modbus RTU devices bridged to the cloud over 4G (datasheet).
- Asset location with GNSS (datasheet).
## Known limitations
- One Ethernet port, LAN only; one SIM (datasheet).
- RS232 or RS485, not both at once (datasheet).
- DO max 0.3 A at 30 VDC; DI dry contact only (datasheet).
- Supply 5–24 VDC only (datasheet).
- Operating range -40 °C to +60 °C; IP30 (datasheet).
- The datasheet's 2-pin power block and the user guide's 8-pin power pins disagree; check the unit before wiring (datasheet, user guide).
## Positioning (kept apart from specs)
- Milesight: mini industrial cellular router for embedded IoT (Milesight page).
- Cytron: micro-sized, highly efficient M2M router for space-constrained and energy-restricted deployments (product page).
## Price band
RM1,227.00 (Cytron product page, read 2026-10-21; enquiry only)
## Product page
https://my.cytron.io/Milesight/p-ur41-4g-mini-industrial-router
## Datasheet
https://resource.milesight.com/milesight/iot/document/ur41-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ur41-datasheet-en.pdf
