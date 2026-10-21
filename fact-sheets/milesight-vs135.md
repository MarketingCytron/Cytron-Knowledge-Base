# Product fact sheets

## Product name
Milesight VS135 PoE Ultra ToF People Counter
## Aliases
VS135, V-LR-VS135, LR-VS135, LR-VS135-P, VS135-P, Milesight VS135, VS135 Ultra ToF People Counter, ToF people counter
## What it is
A ceiling-mounted 3D Time-of-Flight AI people counter made by Milesight and distributed by Cytron (product page). It uses depth data only, with no images or video, and comes in PoE, LoRaWAN, cellular and Wi-Fi HaLow versions with Standard or High Ceiling optics (datasheet).
## Specs and functions
- Second-generation ToF sensor, 940 nm invisible light; counting accuracy up to 99.8% (datasheet).
- Standard optics: 98° × 80°, height up to 3.5 m, detection area 2.99 × 2.18 m at 3 m (datasheet).
- High Ceiling optics: 60° × 45°, height up to 6.5 m, detection area 5.54 × 3.98 m at 6.5 m (datasheet).
- Up to 4 bi-directional lines with U-turn filtering; up to 4 regions with dwell time (datasheet).
- Group counting, child/adult, staff detection with staff tags, occlusion detection, heat maps (datasheet).
- Multi-device stitching: up to 8 units on PoE, up to 4 on other versions (datasheet).
- Local storage of one million records with CSV export (datasheet).
- PoE version: 802.3at PoE+ or 12 V / 2 A, up to 17 W (Standard) or 24 W (High Ceiling) (datasheet).
- LoRaWAN version: 12 V / 2 A DC, OTAA/ABP Class C; Cytron states AS923-2 and AS923-1 (datasheet, product page).
- 200 × 35 × 85 mm, about 410–419 g, IP40, -20 to +50 °C (datasheet).
- Cytron variants: Standard (LR-VS135, includes power adapter) and High Ceiling Mount (LR-VS135-P, includes multi-interface cable); both include 8 staff tags (product page).
## Interfaces and compatibility
- PoE version: RJ45 10/100 PoE PD, alarm I/O 1 in / 1 out, multi-interface DI/DO (DO up to 1 A @ 24 V DC) (datasheet, user guide).
- Default IPs: Wi-Fi AP 192.168.1.1; Ethernet 192.168.5.220 on the PoE version; you set the password at first login (user guide).
- PoE protocols: HTTP(S), MQTT(S), BACnet/IP, 802.1x, SSH, LLDP (datasheet).
- LoRaWAN version works with standard LoRaWAN gateways such as Milesight UG65 or UG56 and Milesight IoT Cloud (datasheet).
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page).
## Use cases
- Entrance counting in retail chains, airports, transport hubs and universities (product page).
- Queue management with zone dwell time (datasheet).
- Space utilisation and occupancy in smart buildings (product page).
- High-ceiling venues up to 6.5 m with the High Ceiling optics (datasheet).
## Known limitations
- Detection area is much smaller than the visible area; wide entrances need several stitched units (user guide).
- PoE version needs 802.3at PoE+; 802.3af is not enough (datasheet).
- Keep away from walls, 940 nm IR sources, glass and mirrors; tilt within 15° (Standard) or 10° (High Ceiling) (user guide).
- Indoor IP40, -20 to +50 °C (datasheet).
- Which connectivity version each Cytron variant is has not been confirmed (product page).
## Positioning (kept apart from specs)
- Milesight: GDPR compliant, no images collected, up to 99.8% accuracy (datasheet).
- Cytron: "far exceeding traditional camera-based systems", privacy-first smart analytics tool (product page).
## Price band
RM3,271.80 – RM3,314.85, sold on enquiry (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-vs135-poe-ultra-tof-people-counter
## Datasheet
https://resource.milesight.com/milesight/iot/document/vs135-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/vs135-datasheet-en.pdf
