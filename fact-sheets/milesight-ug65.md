# Product fact sheets

## Product name
Milesight UG65 Semi-Industrial LoRaWAN® Gateway (with or without Cellular)
## Aliases
UG65, V-LR-UG65, LR-UG65, LR-UG65-NC, UG65-L08GL-915M-EA, UG65-915M-EA, Milesight UG65, UG65 Indoor LoRaWAN Gateway
## What it is
An 8-channel LoRaWAN® gateway made by Milesight and distributed in Malaysia by Cytron (product page). It has a Semtech SX1302 chip, a quad-core ARM Cortex-A53 CPU, Gigabit Ethernet with PoE, 2.4 GHz Wi-Fi, optional 4G LTE and a built-in LoRaWAN network server, in an IP65 enclosure for indoor and sheltered outdoor use (datasheet).
## Specs and functions
- Cytron sells two versions: With Cellular (MPN UG65-L08GL-915M-EA, RM1,945.85) and Without Cellular (MPN UG65-915M-EA, RM1,610.05) (product page).
- Frequency plan sold by Cytron: Malaysia AS923-2, Singapore AS923-1, on 915 MHz-band hardware (product page).
- Milesight model range covers CN470, IN865, EU868, RU864, US915, AU915, KR920 and AS923-1/2/3/4 (datasheet).
- LoRa: 8 half/full-duplex channels, -140 dBm sensitivity at 292 bps, 27 dBm max Tx power, LoRaWAN V1.0 and V1.0.2 Class A/B/C (datasheet).
- Capacity around 2000 Class A/B/C devices at a 10-minute uplink interval; up to 15 km line of sight, about 2 km urban (datasheet).
- LoRa antennas: 2 internal plus 1 × 50 Ω N-Female external connector; an 18 cm LoRa antenna is in Milesight's standard package (datasheet).
- CPU quad-core 1.5 GHz 64-bit ARM Cortex-A53, 512 MB DDR4 RAM, 8 GB eMMC (datasheet).
- Ethernet: 1 × RJ45 WAN, 10/100/1000 Mbps, PoE powered device (802.3af), 1.5 kV isolation (datasheet).
- Wi-Fi: 802.11 b/g/n 2.4 GHz, internal antenna, AP or client mode (datasheet).
- Cellular (optional): 4G LTE, internal antenna, 1 × mini SIM (2FF) (datasheet).
- Power: DC 9–24 V on a 2.1 × 5.5 mm jack, 802.3af PoE, or 5 V / 1 A on USB Type-C; typical 2.9 W, max 4.2 W (datasheet).
- Embedded network server with Milesight codecs, multicast, FUOTA and Gateway Fleet; MQTT(s), HTTP(s), BACnet/IP, BACnet/SC, Modbus TCP and Modbus RTU over TCP integration (datasheet).
- IP65, PC+ABS, 180 × 110 × 55.5 mm, 548 g, -40 °C to +70 °C (datasheet).
- Default web access: join the gateway's Wi-Fi AP and open https://192.168.1.1; the default login and Wi-Fi password are set at the factory and are not copied here (user guide).
## Interfaces and compatibility
- RJ45 Gigabit WAN with 802.3af PoE input, DC jack, USB Type-C (power and console), N-Female LoRa antenna connector, mini SIM slot on the cellular version, reset button (datasheet).
- LEDs: POWER, STATUS, LoRa, Wi-Fi, LTE, ETH (datasheet).
- Works with The Things Stack, ChirpStack, Actility and AWS through packet forwarders (datasheet).
- Managed through Milesight DeviceHub and Milesight Development Platform; Python SDK and Node-RED on the gateway (datasheet).
- Pairs with Milesight LoRaWAN sensors and controllers on the same regional plan, such as EM320-TH and UC100 (product page).
- Optional GA01 fiber-glass N-N antenna kits (60 cm or 130 cm) for longer range (Milesight page).
## Use cases
- Smart office and smart building LoRaWAN coverage (datasheet).
- Building management integration over BACnet or Modbus (datasheet).
- Smart city, industrial automation and smart agriculture sensor networks (product page).
- Indoor air quality, HVAC, energy, cold chain and space management (Milesight page).
## Known limitations
- Wi-Fi is 2.4 GHz only (datasheet).
- Only one Ethernet port (WAN) (datasheet).
- Cellular antenna is internal; reduced cellular performance above 60 °C (datasheet).
- The gateway hardware is band-specific; Cytron's units are 915 MHz-band (product page).
- LTE bands are not stated in the global datasheet (datasheet).
- Cytron's packing list names only the gateway; Milesight's standard box adds an adapter, bracket and antenna (product page, datasheet).
## Positioning (kept apart from specs)
- Milesight: "Semi-Industrial LoRaWAN® Gateway" in the datasheet; "Indoor LoRaWAN® Gateway" on its current web page (datasheet, Milesight page).
- Cytron: high-performance, reliable gateway for smart cities, industrial automation, smart agriculture and intelligent buildings (product page).
- Milesight states a 3-year warranty in the user guide; Cytron lists 12 months (user guide, product page).
## Price band
RM1,610.05 (Without Cellular) to RM1,945.85 (With Cellular) (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-ug65-semi-industrial-lorawan-gateway-with-without-cellular
## Datasheet
https://resource.milesight.com/milesight/iot/document/ug65-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ug65-datasheet-en.pdf
