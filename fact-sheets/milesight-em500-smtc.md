# Product fact sheets

## Product name
Milesight EM500-SMTC LoRaWAN Soil Moisture, Temperature and EC Sensor
## Aliases
EM500-SMTC, LR-EM500-SMTC, EM500-SMTC-915M, Milesight soil sensor, soil conductivity sensor
## What it is
A battery-powered LoRaWAN soil moisture, temperature and electrical-conductivity sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron (product page). An IP67 EM500 transceiver powers and reads a buried IP68 soil probe on a 2 m cable (datasheet).
## Specs and functions
- Soil moisture 0 – 100 %; ± 2 % (0–50 %), ± 3 % (50–100 %); resolution 0.01 % (datasheet).
- Soil temperature -40 ~ 80 °C; ± 0.5 °C; resolution 0.1 °C (datasheet).
- EC 0 – 20000 µS/cm; ± 3 % up to 10000, ± 5 % above; resolution 10 or 50 µS/cm (datasheet).
- Soil probe 88 × 68 × 26 mm, 50 mm prongs, epoxy + stainless steel, IP68, 138 g with cable; cable 2 m (datasheet).
- LoRaWAN Class A, OTAA/ABP, plus Milesight D2D; internal antenna; 20 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listing: Malaysia AS923-2, Singapore AS923-1 (product page).
- Data storage 1,000 entries, retransmission, retrievability, threshold and temperature change alarms (datasheet).
- Power: 1 × 19000 mAh ER34615 Li-SOCl2 battery; up to 10 years at 10-min interval (around 8 years at SF10 US915) (datasheet).
- Transceiver IP67, -30 ~ 70 °C, 105.4 × 71 × 69.5 mm, 328 g; pole, wall or DIN-rail mounting (datasheet).
## Interfaces and compatibility
- Internal terminal block: pin 1 black GND, pin 4 white B, pin 5 yellow A, pin 6 red 12 V; the green probe wire is unused (user guide).
- Internal USB Type-C for ToolBox PC software; NFC for the ToolBox app (datasheet).
- Uplink: temperature °C, moisture %, conductivity µS/cm (user guide).
- Works with standard LoRaWAN gateways and Milesight IoT Cloud; pair with e.g. milesight-ug65.md (datasheet).
- A default ToolBox password and default LoRaWAN keys are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Irrigation control and greenhouse control (datasheet).
- Smart agriculture and smart horticulture (datasheet).
- Golf course maintenance (datasheet).
## Known limitations
- Prongs must be fully buried in undisturbed soil without air gaps or roots (user guide).
- Do not pull the probe out by its cable; avoid sideways force on the prongs (user guide).
- Battery life drops to about 8 years at SF10 on US915 (datasheet).
- The Cytron page lists a 4000 mAh battery and IP66; the datasheet says 19000 mAh and IP67/IP68 (product page, datasheet).
## Positioning (kept apart from specs)
- Cytron page: real-time data for better irrigation, fertilisation and crop yield.
- Milesight: high precision for multiple kinds of soil, corrosion-resistant tough probe.
## Price band
RM2,135.30 (Cytron product page, read 2026-10-21; sold on enquiry)
## Product page
https://my.cytron.io/Milesight/p-em500-smtc-soil-moisture-temperature-and-ec-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em500-smtc-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em500-smtc-datasheet-en.pdf
