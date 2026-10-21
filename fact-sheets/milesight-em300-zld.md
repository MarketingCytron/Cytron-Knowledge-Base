# Product fact sheets

## Product name
Milesight EM300-ZLD LoRaWAN Zone Leak Detection Sensor
## Aliases
EM300-ZLD, LR-EM300-ZLD, EM300-ZLD-915M, Milesight EM300-ZLD, EM300 zone leak sensor, rope leak detection sensor
## What it is
A battery-powered LoRaWAN zone leak detection sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed by Cytron (product page). A 3 m sensing rope detects conductive liquid anywhere along its length, and the transceiver also measures temperature and humidity (datasheet).
## Specs and functions
- LoRaWAN and Milesight D2D, internal antenna, OTAA/ABP Class A (datasheet).
- Cytron unit: MPN EM300-ZLD-915M, stated for Malaysia AS923-2 and Singapore AS923-1 (product page).
- Tx power 16 dBm (868 MHz), 20 dBm (915 MHz), 19 dBm (470 MHz); sensitivity -137 dBm at 300 bps (datasheet).
- Triggers when conductive liquid reaches 5 mm; at least 3 cm of cable wet and 1 mm deep (datasheet, user guide).
- Sensing cable 3 m, PE + steel wire, customisable length (datasheet).
- Temperature -30 to +70 °C (±0.3 / ±0.6 °C); humidity 0–100 %RH (±3 / ±5 %) (datasheet).
- Threshold alarm, D2D controller, 2,800-entry storage, retransmission, retrievability (datasheet).
- One 4000 mAh ER18505 Li-SOCl2 battery (8000 mAh version optional); over 10 years at SF7, 10 min interval, 24 triggers per day (datasheet).
- IP67, UV resistant, 105.6 × 85.3 × 27 mm, -30 to +70 °C (datasheet).
- Default reporting interval 10 min (1–1080 min) (user guide).
- Packing per Cytron: device with sensor, wall mounting kit, quick guide, warranty card (product page).
## Interfaces and compatibility
- Sensing cable screws onto a single connector; it cannot be chained to a second cable (user guide).
- NFC configuration with Milesight ToolBox; downlink configuration (datasheet).
- Standard LoRaWAN gateways and network servers, e.g. Milesight UG65 or UG56 (datasheet).
- Uplink: battery, temperature, humidity, leak status, historical data; decoders on GitHub Milesight-IoT/SensorDecoders (user guide).
- A default device password and default LoRaWAN keys are set at the factory; not copied here (user guide).
## Use cases
- Pipe leakage monitoring by wrapping the rope around pipes (datasheet, user guide).
- Basement flooding and floor-wetness detection (datasheet).
- Pump failure and water spillage alerts (datasheet).
- Large-area leak monitoring along walls and floors (user guide).
## Known limitations
- Does not locate the leak along the cable (user guide).
- Conductive liquids only; cannot detect diesel or oil (product page FAQ).
- Wet connectors or air-conditioning outlets cause false alarms (user guide).
- Cable extension needs a custom or double-ended cable from Milesight (user guide).
- Warranty not stated on the Cytron page (product page).
## Positioning (kept apart from specs)
- "Compact zone leakage detection sensor for detecting large area presence of water" (datasheet).
- Industrial-grade design for harsh environments (product page).
## Price band
RM413.30 (Cytron product page, availability Enquiry, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-em300-zld-lorawan-leak-detection-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em300-zld-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em300-zld-datasheet-en.pdf
