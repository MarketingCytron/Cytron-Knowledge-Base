# Product fact sheets

## Product name
Milesight VS125 PoE AI Stereo Vision People Counter (Low-and-Wide Version)
## Aliases
VS125-LW-P, LR-VS125-LW-P, VS125-LW, VS125 Low-and-Wide, Milesight VS125, 3D people counter
## What it is
A ceiling-mounted 3D stereo-vision AI people counter for low ceilings, made by Milesight and distributed by Cytron (product page). The version Cytron sells is PoE powered and sends data over Ethernet; it is not a LoRaWAN device (datasheet).
## Specs and functions
- 2 × 5 MP sensors (2592 × 1744), stereo depth with IR, works at 0 lux (datasheet).
- Installation height 1.9–3.5 m; FoV 130° horizontal × 117° vertical (datasheet).
- Detection area 5.57 × 4.24 m at 3 m and 7.71 × 5.87 m at 3.5 m for a 1.75 m person; Milesight quotes up to 40 m² (datasheet).
- Counting accuracy up to 99.8% (datasheet).
- Up to 4 bi-directional lines with U-turn filtering; up to 4 regions with dwell time (datasheet).
- Child/adult, gender, group counting, staff detection, heat map, view direction (datasheet).
- Stitching of up to 16 devices; local storage of one million records with CSV export (datasheet).
- Power: 802.3af PoE or 12 V / 1 A DC; avg 6.9 W, max 12 W (datasheet).
- 185 × 85 × 34 mm, 284.4 g, IP40, -20 to +60 °C (datasheet).
- Packing: device, 4 ceiling mounting sets, multi-interface cable, warranty card, quick guide; no power adapter (product page).
## Interfaces and compatibility
- 1 × RJ45 10/100 Mbps PoE PD, 1.5 kV isolation (datasheet).
- 1 × DI, 2 × DO (up to 1 A @ 24 V DC), 1 × RS485 (under development) on a multi-interface cable (datasheet, user guide).
- Wi-Fi 2.4 GHz AP for configuration at 192.168.1.1 (user guide).
- Ethernet uses DHCP by default and falls back to 192.168.5.220 after 30 s (user guide).
- Protocols: HTTP(s), MQTT(s), BACnet/IP, 802.1x, OpenVPN, SSH, NTP (datasheet).
- Managed with Milesight DeviceHub or Development Platform (datasheet).
## Use cases
- Footfall counting at retail store and boutique entrances with low ceilings (product page).
- Queue management with zone dwell time (product page).
- Shopper insights: adults vs children, groups, staff filtering (product page).
- Subway and office entrance counting (datasheet).
## Known limitations
- No LoRaWAN; PoE (Ethernet) or a separate cellular version only (datasheet).
- Small coverage at low heights, so wide entrances need stitched units (user guide).
- Attribute recognition needs 1.9–3.3 m height (user guide).
- RS485 is under development (datasheet).
- Indoor IP40; not for rain-exposed or private areas (datasheet, user guide).
- PoE must be 802.3af; no power adapter in the Cytron box (datasheet, product page).
## Positioning (kept apart from specs)
- Milesight: privacy-by-design, GDPR compliant, "up to 99.8%" accuracy (datasheet).
- Cytron: GDPR-certified people counting and shopper insights for low-ceiling retail (product page).
## Price band
RM3,400.95, out of stock (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-vs125-poe-ai-stereo-vision-people-counter-low-and-wide-version
## Datasheet
https://resource.milesight.com/milesight/iot/document/vs125-lw-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/vs125-lw-datasheet-en.pdf
