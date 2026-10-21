# Product fact sheets

## Product name
Milesight AT101 LoRaWAN Outdoor Asset Tracker
## Aliases
AT101, LR-AT101, AT101-915M, Milesight AT101, LoRaWAN GPS tracker, outdoor asset tracker
## What it is
A battery-powered LoRaWAN outdoor asset tracker made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed by Cytron (product page). It locates itself by GNSS and Wi-Fi access-point scanning, adds tilt, temperature and tamper sensing, and reports over LoRaWAN (datasheet).
## Specs and functions
- LoRaWAN, internal antenna, OTAA/ABP Class A (datasheet).
- Cytron unit: MPN AT101-915M, stated for Malaysia AS923-2 and Singapore AS923-1 (product page).
- Tx power 16 dBm (868 MHz), 20 dBm (915 MHz), 19 dBm (470 MHz); sensitivity -137 dBm at 300 bps (datasheet).
- GNSS 5.0 m CEP line of sight; cold start 37 s, hot start 1 s average (datasheet).
- Wi-Fi positioning by 2.4 GHz AP scanning, reports BSSID and RSSI, does not connect to Wi-Fi (datasheet).
- 3-axis accelerometer for motion and tilt; NTC temperature -40 to 125 °C (datasheet).
- Geofence, tilt and tamper alarms; 1000-record storage with retransmission (datasheet).
- Periodic, motion and timing tracking modes (user guide).
- Four 2700 mAh ER14505 Li-SOCl2 batteries: 15+ years at 2 fixes per day, 4+ years hourly (datasheet).
- IP67, IK09, -30 to +70 °C, 110 × 70 × 30 mm, 202 g (datasheet).
- In the box: AT101, 2 mounting kits, 3M tape, warranty card, quick guide (product page).
## Interfaces and compatibility
- No wiring; tamper button on the back detects removal (user guide).
- Configured by NFC or Bluetooth 5.3 with Milesight ToolBox, or by downlink (datasheet).
- Standard LoRaWAN gateways and network servers; Milesight IoT Cloud with OTAA (datasheet, user guide).
- A default device password and default LoRaWAN keys are set at the factory; not copied here (user guide).
## Use cases
- Patrol cars, golf carts and other vehicles in a community (datasheet).
- Construction sites, construction bins and warehouses (datasheet).
- Farm animal tracking (datasheet).
- Geofenced asset security (product page).
## Known limitations
- Wi-Fi scan results need an external geolocation service to give coordinates (datasheet).
- Location reports need LoRaWAN gateway coverage on the same plan (product page).
- A firmware bug placed coordinates on the opposite side of the Earth; fix by updating firmware over Bluetooth (product page FAQ).
- Geofence works only with GNSS positioning (user guide).
## Positioning (kept apart from specs)
- "An exceptional outdoor tracker" (datasheet).
- "Protect and Manage Critical Assets Anytime Anywhere" (Milesight product page).
## Price band
RM559.65 (Cytron product page, availability Enquiry, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-at101-outdoor-asset-tracker
## Datasheet
https://resource.milesight.com/milesight/iot/document/at101-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/at101-datasheet-en.pdf
