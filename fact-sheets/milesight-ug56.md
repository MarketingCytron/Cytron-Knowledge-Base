# Product fact sheets

## Product name
Milesight UG56 Industrial LoRaWAN® Gateway (without Cellular)
## Aliases
UG56, LR-UG56-NC, UG56-915M, Milesight UG56, UG56 Industrial LoRaWAN Gateway
## What it is
An 8-channel industrial LoRaWAN® gateway in a small metal IP30 housing, made by Milesight and distributed in Malaysia by Cytron (product page). It has a Semtech SX1302 chip, a quad-core ARM Cortex-A35 CPU, 10/100 Ethernet with PoE input, 2.4 GHz Wi-Fi and a built-in LoRaWAN network server (datasheet). Cytron sells the non-cellular version.
## Specs and functions
- Cytron version: MPN UG56-915M, non-cellular, frequency plan Malaysia AS923-2 / Singapore AS923-1 (product page).
- Milesight model range covers CN470, IN865, EU868, RU864, US915, AU915, KR920 and AS923-1/2/3/4 (datasheet).
- LoRa: 8 half-duplex channels, -140 dBm at 292 bps, 27 dBm max, LoRaWAN V1.0 and V1.0.2 Class A/B/C, listen-before-talk supported except AU915/US915 (datasheet).
- Capacity around 2000 Class A/B/C devices at a 10-minute uplink interval (datasheet).
- LoRa antenna: 1 × 50 Ω SMA connector (female centre pin); a magnetic LoRa antenna is in the box (datasheet, product page).
- CPU quad-core 1.3 GHz Cortex-A35, 512 MB DDR3, 8 GB eMMC, internal micro SD slot (datasheet).
- Ethernet: 1 × RJ45 WAN, 10/100 Mbps, 802.3af PoE powered device (datasheet).
- Wi-Fi: 802.11 b/g/n 2.4 GHz, internal antenna, AP or client (datasheet).
- Power: 802.3af PoE or 5 V / 2 A on USB Type-C; typical 1.8 W, max 6.9 W (datasheet).
- Metal housing, IP30, 110 × 75 × 24 mm, 186 g, -20 °C to +60 °C (datasheet).
- LEDs: SYS (off starting, red error, green running) and LoRa (on when the packet forwarder runs) (quick guide).
- Default web access: join the gateway's Wi-Fi AP and open https://192.168.1.1; the default login and Wi-Fi password are not copied here (quick guide).
- Packing: gateway, LoRaWAN magnetic antenna, wall bracket, screws, wall kits, quick start guide, warranty card; no power adapter (product page).
## Interfaces and compatibility
- RJ45 10/100 with PoE input, USB Type-C (power and console), SMA LoRa connector, internal micro SD and reset button behind the front cover (quick guide).
- Embedded network server with MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP and Modbus RTU over TCP integration (datasheet).
- Packet forwarders for The Things Stack, ChirpStack, Actility and AWS (datasheet).
- DeviceHub and Milesight Development Platform management; Python SDK and Node-RED (datasheet).
- Fits the GA01 fiber-glass S-N antenna kit for longer range (Milesight page).
- Pairs with Milesight LoRaWAN sensors and controllers on the same regional plan (product page).
## Use cases
- Smart building and smart industry LoRaWAN coverage (datasheet).
- Gateway inside a control panel, server rack or on a wall (product page).
- BMS and PLC integration over BACnet or Modbus (datasheet).
- Indoor coverage up to 3 floors up and down (product page).
## Known limitations
- IP30: indoor or cabinet use only (datasheet).
- Ethernet is 10/100 Mbps; Wi-Fi is 2.4 GHz only (datasheet).
- Operating range -20 °C to +60 °C (datasheet).
- No power adapter in the box; a PoE source or 5 V / 2 A Type-C supply is needed (product page, datasheet).
- No hot-plugging of SIM or micro SD cards (quick guide).
- DIN rail mounting only on new hardware, with an optional clip kit (datasheet).
- Cytron's version has no cellular modem (product page).
## Positioning (kept apart from specs)
- Milesight: "Industrial LoRaWAN® Gateway" with a rugged metal enclosure (datasheet).
- Cytron: compact, high-performance gateway for massive, secure IoT coverage indoors and semi-outdoors, with fast deployment and lower scaling costs (product page).
- Milesight states a 3-year warranty in the user guide; Cytron lists 12 months (user guide, product page).
## Price band
RM998.75 (Cytron product page, read 2026-10-21; backorder)
## Product page
https://my.cytron.io/Milesight/p-ug56-industrial-lorawan-gateway-without-cellular
## Datasheet
https://resource.milesight.com/milesight/iot/document/ug56-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ug56-datasheet-en.pdf
