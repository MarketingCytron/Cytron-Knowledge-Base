# Product fact sheets

## Product name
Milesight UG67 Outdoor LoRaWAN® Gateway (With Cellular)
## Aliases
UG67, LR-UG67, UG67-L08GL-915M, Milesight UG67, UG67 Outdoor LoRaWAN Gateway
## What it is
An 8-channel outdoor LoRaWAN® gateway in an IP67 housing, made by Milesight and distributed in Malaysia by Cytron (product page). It has a Semtech SX1302 chip, a quad-core ARM Cortex-A53 CPU, two external LoRa antenna connectors, Gigabit Ethernet with PoE, 2.4 GHz Wi-Fi, 4G LTE, GNSS and a built-in LoRaWAN network server (datasheet).
## Specs and functions
- Cytron version: MPN UG67-L08GL-915M with 4G LTE, frequency plan Malaysia AS923-2 / Singapore AS923-1 (product page).
- Milesight model range covers CN470, IN865, EU868, RU864, US915, AU915, KR920 and AS923-1/2/3/4 (datasheet).
- LoRa: 8 half/full-duplex channels, -140 dBm at 292 bps, 27 dBm max, LoRaWAN V1.0 and V1.0.2 Class A/B/C, listen-before-talk except AU915/US915 (datasheet).
- Capacity around 2000 Class A/B/C devices; line of sight up to 15 km (datasheet).
- LoRa antennas: 2 × 50 Ω N-Female connectors; two 60 cm antennas and a 1 m coaxial cable in the box (datasheet, quick guide).
- CPU quad-core 1.5 GHz Cortex-A53, 512 MB DDR4, 8 GB eMMC (datasheet).
- Ethernet: 1 × RJ45 WAN, 10/100/1000 Mbps, 802.3af PoE powered device (datasheet).
- Wi-Fi 802.11 b/g/n 2.4 GHz and 4G LTE with mini SIM, both with internal antennas (datasheet).
- GNSS: GPS/GLONASS/QZSS/SBAS, internal antenna, 2.5 m CEP (datasheet).
- Power: 802.3af PoE (injector included) or 6–12 VDC on an M12 A-coded connector; typical 3.6 W, max 4.8 W (datasheet, product page).
- M12 power pinout: pin 1 black GND, pin 2 white reserved, pin 3 yellow reserved, pin 4 red +12V (quick guide).
- Built-in capacitor keeps the gateway running long enough to send a power-failure alarm (datasheet).
- IP67, PC + aluminium, 240 × 164 × 90.9 mm, 1463 g, -40 °C to +70 °C (datasheet).
- LEDs: SYS, LoRa, LTE; reset by holding the button more than 5 s (quick guide).
- Default web access: join the gateway's Wi-Fi AP and open https://192.168.1.1; the default login and Wi-Fi password are not copied here (user guide).
## Interfaces and compatibility
- RJ45 Gigabit with PoE input through a cable gland, M12 DC/solar power connector, 2 × N-Female LoRa connectors, Type-C console, SIM slot under a dust cover, grounding stud (quick guide).
- Embedded network server with MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP and Modbus RTU over TCP integration (datasheet).
- Packet forwarders for The Things Stack, ChirpStack, Actility and AWS (datasheet).
- DeviceHub, Milesight Development Platform and Milesight IoT Cloud; Python SDK and Node-RED (datasheet, product page).
- Packing: gateway, 2 antennas, coaxial cable, PoE injector, M12 DC cable, mounting kit and bracket, cable gland and plug, SIM dust cover (product page).
## Use cases
- Smart agriculture and smart metering over wide outdoor areas (datasheet).
- Outdoor wall or pole-mounted LoRaWAN coverage for campuses and cities (datasheet).
- BMS integration through BACnet or Modbus (product page).
- Remote sites with cellular backhaul (datasheet).
## Known limitations
- Supply on the M12 connector is 6–12 VDC only; pins 2 and 3 are reserved (quick guide).
- Wi-Fi is 2.4 GHz only (datasheet).
- Cellular performance is reduced above 60 °C (datasheet).
- Outdoor use needs connector taping, earthing and lightning protection (quick guide).
- LTE bands are not stated in the datasheet (datasheet).
- Heavy (1463 g) and needs wall or pole mounting (datasheet).
## Positioning (kept apart from specs)
- Milesight: robust outdoor gateway with an IP67 waterproof case for harsh environments (datasheet).
- Cytron: exceptional performance, new-generation LoRa chip, flexible internal and external antennas, easy antenna installation (product page).
- Milesight states a 3-year warranty in the user guide; the Cytron page shows no warranty period (user guide, product page).
## Price band
RM3,788.40 (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-ug67-outdoor-lorawan-gateway-with-cellular
## Datasheet
https://resource.milesight.com/milesight/iot/document/ug67-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ug67-datasheet-en.pdf
