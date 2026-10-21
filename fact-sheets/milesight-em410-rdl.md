# Product fact sheets

## Product name
Milesight EM410-RDL LoRaWAN Radar Distance / Level Sensor with External Antenna
## Aliases
EM410-RDL, EM410-RDL-EA, LR-EM410-RDL-EA, EM410-RDL-915M-EA, EM41x-RDL, Milesight radar level sensor
## What it is
A battery-powered LoRaWAN 60 GHz millimetre-wave radar distance and liquid-level sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron, which sells the external-antenna version (product page). It measures 0.3–12 m with an 8° beam in a PVDF IP68 housing for sewers, wells, rivers and tanks (datasheet).
## Specs and functions
- 60 GHz millimetre-wave radar; target liquids or smooth-surface solids (datasheet).
- Beam angle 8°; detection distance 0.3 ~ 12 m; blind zone 30 cm (datasheet, user guide).
- Accuracy up to ± 2 mm on a still liquid or perfectly smooth flat solid; resolution 1 mm (datasheet).
- 3-axis accelerometer: Normal / Tilt, tilt = offset of 15° or more (user guide).
- Scenario modes: General, Rainwater Well, Wastewater Well, Tank; Tank mode reports liquid height from the bottom (user guide).
- Alarms: distance threshold, distance change, blind zone; radar-echo curve and diagnostic; 2,000-entry local storage with retransmission (datasheet).
- LoRaWAN Class A, OTAA/ABP; 20 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listing: Malaysia AS923-2, Singapore AS923-1 (product page).
- External antenna: 1 × 50 Ω SMB male connector, SMB magnetic antenna and cable gland supplied (datasheet, product page).
- Power: 1 × 19000 mAh ER34615 Li-SOCl2 battery; around 7 years at 15-min collection and 24-h reporting, 25 °C (datasheet).
- IP68 (1 m, 48 h); -40 ~ 70 °C; 0–100 % RH non-condensing (datasheet).
- Ф 101 × 87 mm, 400 g, PVDF UL94 V0, G1½" tank thread; wall bracket or tank thread installation (datasheet).
- Packing: sensor, bracket, bubble level, waterproof tape, G1½ nut, screw kit, O-ring, battery, SMB magnetic antenna, cable gland (product page).
## Interfaces and compatibility
- No signal wiring; SMB antenna connector; two metal contacts for reboot (over 3 s) and factory reset (over 10 s) (user guide).
- Configure with the Milesight ToolBox app over Bluetooth or NFC (datasheet).
- Works with standard LoRaWAN gateways; pair with e.g. milesight-ug65.md (product page).
- Management and OTA upgrade via Milesight Development Platform (datasheet).
- A default ToolBox/Bluetooth password and default LoRaWAN keys are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Sewer, rainwater-well and wastewater-well level monitoring (user guide).
- Storage tank and reservoir level, with threshold and sudden-rise alerts (product page).
- River level and salt-mist sites such as seawater or brine (datasheet).
## Known limitations
- Nothing is measured inside the 30 cm blind zone (user guide).
- Mount at least 20 cm from tank walls, perpendicular to the liquid (user guide).
- Tighten the G1½ nut to no more than 4 N·m (user guide).
- ER34615 Li-SOCl2 battery only; alkaline cells are not supported (user guide).
- Default reporting interval is 24 h; faster reporting shortens battery life (user guide).
## Positioning (kept apart from specs)
- Cytron page: millimetre-level accuracy where ultrasonic or float sensors fall short.
- Milesight: less affected by dust, condensate, temperature and acoustic noise.
## Price band
RM1,334.55 (Cytron product page, read 2026-10-21; out of stock / enquiry)
## Product page
https://my.cytron.io/Milesight/p-em410-rdl-lorawan-radar-distance-level-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em410-rdl-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em410-rdl-datasheet-en.pdf
