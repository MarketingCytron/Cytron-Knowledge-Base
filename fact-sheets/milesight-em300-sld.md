# Product fact sheets

## Product name
Milesight EM300-SLD LoRaWAN Spot Leak Detection Sensor
## Aliases
EM300-SLD, LR-EM300-SLD, EM300-SLD-915M, Milesight EM300-SLD, EM300 spot leak sensor, spot leakage detection sensor
## What it is
A battery-powered LoRaWAN spot leak detection sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed by Cytron (product page). A 1.5 m stainless-steel probe with two pins detects conductive liquids, and the transceiver also measures temperature and humidity (datasheet).
## Specs and functions
- LoRaWAN and Milesight D2D, internal antenna, OTAA/ABP Class A (datasheet).
- Cytron unit: MPN EM300-SLD-915M, stated for Malaysia AS923-2 and Singapore AS923-1 (product page).
- Milesight plans: CN470, IN865, RU864, EU868, US915, AU915, KR920, AS923-1/2/3/4 (datasheet).
- Tx power 16 dBm (868 MHz), 20 dBm (915 MHz), 19 dBm (470 MHz); sensitivity -137 dBm at 300 bps (datasheet).
- Leak detection of conducting liquid when the level reaches 5 mm; probe cable 1.5 m, customisable (datasheet).
- Temperature -30 to +70 °C, ±0.3 °C (0 to 70 °C), ±0.6 °C (-30 to 0 °C), 0.1 °C resolution (datasheet).
- Humidity 0–100 %RH, ±3 % (10–90 %RH), ±5 % outside that, 0.5 %RH resolution (datasheet).
- Threshold alarm, D2D controller, 2,800-entry data storage, retransmission and retrievability (datasheet).
- One 4000 mAh ER18505 Li-SOCl2 battery (8000 mAh version optional); over 10 years at SF7 with 10 min interval and 24 triggers per day (datasheet).
- IP67, ABS+PC flame-retardant transceiver, SS316 probe, 105.6 × 85.3 × 27 mm, -30 to +70 °C (datasheet).
- Default reporting interval 10 min (1–1080 min); application port 85 (user guide).
- In the box: device, 2 wall mounting kits, 2 screw caps, quick guide, warranty card, 3M tape, mounting screw (product page).
## Interfaces and compatibility
- No external terminals or USB; internal power/reset button and LED (datasheet).
- Configured by NFC with the Milesight ToolBox app, or by LoRaWAN downlink (user guide).
- Works with standard LoRaWAN gateways and network servers, e.g. Milesight UG65 or UG56 (datasheet, product page).
- Uplink fields: battery, temperature, humidity, water leak status, historical data; decoders on GitHub Milesight-IoT/SensorDecoders (user guide).
- A default device password and default LoRaWAN keys are set at the factory; they are not copied here (user guide).
## Use cases
- Pipe leakage monitoring (datasheet).
- Basement flooding detection (datasheet).
- Pump failure monitoring (datasheet).
- Drain pans, floor drains, pits and narrow corners (installation guide).
- Data centres, utility rooms, warehouses and water tanks (product page).
## Known limitations
- Detects conductive liquids only; not oil, fuel, solvents or strong acids (installation guide).
- Both probe pins must be wet to trigger (user guide).
- Battery life at SF10 drops to about 4–6 years (datasheet).
- Firmware upgrade through ToolBox is Android only (user guide).
- Frequency plan is fixed by hardware; match it to the gateway (product page).
## Positioning (kept apart from specs)
- "Reliable, real-time leak detection for commercial, industrial, and smart building applications" (product page).
- Cost-effective, long-range, maintenance-friendly leak detection (product page).
## Price band
RM309.95 (Cytron product page, availability Enquiry, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-em300-sld-lorawan-spot-leak-detection-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em300-sld-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em300-sld-datasheet-en.pdf
