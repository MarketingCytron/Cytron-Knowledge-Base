# Product fact sheets

## Product name
Milesight WS301 LoRaWAN Magnetic Contact Switch
## Aliases
WS301, LR-WS301, WS301-915M, Milesight WS301, LoRaWAN door sensor, door/window contact switch
## What it is
A wire-free, battery-powered LoRaWAN door and window open/close sensor with tamper detection, made by Milesight and distributed by Cytron (product page). It has a sensor unit for the frame and a separate magnet for the moving part (datasheet).
## Specs and functions
- Magnetic contact sensing with a 20 mm sensor-to-magnet detection distance (datasheet).
- Reports open/closed, tamper (installed/un-installed) and battery level (user guide).
- LoRaWAN OTAA/ABP Class A, Milesight D2D controller; Tx up to 22 dBm; -137 dBm @ 300 bps (datasheet).
- Cytron MPN WS301-915M, stated for AS923-2 (Malaysia) and AS923-1 (Singapore) (product page).
- Power: 1 × 1200 mAh ER14250 Li-SOCl2; about 6.8 years at SF7 and 3.5–4.2 years at SF10, with 1080 min interval and 30 triggers a day (datasheet).
- Alarm sent on every open/close or tamper change; periodic report every 1080 min by default (user guide).
- Sensor 50.5 × 31 × 19 mm, 27.9 g; magnet 50.5 × 13.5 × 13 mm, 13.7 g (datasheet).
- IP20, -20 to +60 °C, ≤ 90 % RH (datasheet).
- Packing: device, 3 mounting screws, warranty card, quick guide card (product page).
## Interfaces and compatibility
- No wired interfaces; NFC configuration with the Milesight ToolBox app (datasheet).
- One status LED, an internal reset button and a tamper button (datasheet).
- Works with LoRaWAN gateways such as Milesight UG65 or UG56, Milesight IoT Cloud and Development Platform (datasheet).
- Payload: magnet status 00 = closed, 01 = open (user guide).
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page).
## Use cases
- Door and window open/close monitoring in offices, homes and factories (datasheet).
- Cabinet and security-gate access alerts (product page).
- Triggering lights or HVAC directly over Milesight D2D (product page).
## Known limitations
- IP20, indoor dry locations only (datasheet).
- Sensor and magnet must be within 20 mm with notched sides facing (user guide).
- ER14250 Li-SOCl2 battery only; alkaline not supported (user guide).
- 3M tape is not included (product page).
- Default ToolBox password and LoRaWAN keys must be changed (user guide).
## Positioning (kept apart from specs)
- Milesight: minimal, compact, wire-free design for smart homes, offices and factories (datasheet).
- Cytron: "uncompromising security" with tamper detection (product page).
## Price band
RM223.85, sold on enquiry (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-ws301-lorawan-magnetic-contact-switch
## Datasheet
https://resource.milesight.com/milesight/iot/document/ws301-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ws301-datasheet-en.pdf
