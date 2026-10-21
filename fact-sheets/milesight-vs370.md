# Product fact sheets

## Product name
Milesight VS370 LoRaWAN Radar Human Presence Sensor
## Aliases
VS370, LR-VS370, VS370-915M, Milesight VS370, radar occupancy sensor, mmWave presence sensor
## What it is
A battery-powered, wall-mounted LoRaWAN presence sensor made by Milesight and distributed by Cytron (product page). It combines 24 GHz mmWave radar with PIR to detect people, including slight movement, and also reports a bright/dim light status (datasheet).
## Specs and functions
- Radar: 24 GHz, 150° angle, movement up to 7.5 m, slight movement up to 4.8 m (datasheet).
- PIR: 110° area, within 7 m (datasheet).
- Recognition rate up to 99% (datasheet).
- Light status bright (≥ 700 lux) or dim (≤ 300 lux) by default (user guide).
- LoRaWAN OTAA/ABP Class A with Milesight D2D controller role; Tx up to 20 dBm; -137 dBm @ 300 bps (datasheet).
- Cytron MPN VS370-915M, stated for AS923-2 (Malaysia) and AS923-1 (Singapore) (product page).
- Power: 2 × 2700 mAh ER14505 Li-SOCl2; about 6.7 years at SF7, 4.6–5.3 years at SF10, 50 triggers a day (datasheet).
- Reporting interval 10 min by default (1–1440 min); vacancy reported 3 min after last detection (user guide).
- Ø70 × 48.5 mm, 89.6 g body, IP30, 0–30 °C (datasheet).
- Packing: sensor with batteries pre-installed, magnetic bracket, bracket adhesive, quick start guide, warranty card (product page, user guide).
## Interfaces and compatibility
- No wired interfaces; internal reset button (datasheet).
- Configured with the Milesight ToolBox app over Bluetooth or NFC, or by downlink (datasheet).
- Works with LoRaWAN gateways such as Milesight UG65 or UG56; OTAA needed for Milesight Development Platform (user guide).
- Milesight D2D: can trigger D2D agent devices such as lighting or HVAC controllers without a gateway (datasheet).
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page).
## Use cases
- Meeting and conference room occupancy (datasheet).
- Lighting and HVAC automation based on presence and brightness (product page).
- Workspace utilisation analytics in offices, schools and hospitals (product page).
## Known limitations
- Wall mounting only at 2.5–3 m, tilted 60° or 75°; no ceiling mounting (user guide).
- Cannot detect a completely still person showing only breathing (user guide).
- False triggers from fans, curtains, plants, glass walls and open doors; not for small rooms like bathrooms (user guide).
- Indoor only, 0–30 °C, IP30 (datasheet).
- ER14505 Li-SOCl2 cells only; alkaline AA not supported (user guide).
## Positioning (kept apart from specs)
- Milesight: "100% privacy protection", no images captured (datasheet).
- Cytron: next-generation, privacy-first occupancy detection for smart buildings (product page).
## Price band
RM430.50, enquiry (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-vs370-lorawan-radar-human-presence-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/vs370-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/vs370-datasheet-en.pdf
