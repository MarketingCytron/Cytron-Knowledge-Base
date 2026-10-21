# Product fact sheets

## Product name
Milesight EM400-TLD LoRaWAN ToF Laser Distance Sensor
## Aliases
EM400-TLD, LR-EM400-TLD, EM400-TLD-915M, Milesight EM400-TLD, ToF laser distance sensor, smart bin sensor
## What it is
A battery-powered LoRaWAN time-of-flight laser distance sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron (product page). It measures 2–350 cm with a 27° field of view and is designed for fill-level monitoring of small trash bins and containers (datasheet).
## Specs and functions
- ToF field of view 27°; detection range 2 ~ 350 cm with an extremely short blind zone (datasheet).
- Accuracy ± 2 cm over -20 °C ~ 70 °C; resolution 1 mm (datasheet).
- 3-axis accelerometer: Normal / Tilt status, tilt = offset of 20° or more, used for lid status (datasheet, user guide).
- NTC temperature sensor -40 ~ 125 °C, resolution 0.1 °C, for trash-burning alarms (datasheet).
- Two pre-set modes: Standard and Bin (user guide).
- LoRaWAN Class A, OTAA/ABP; Tx power 20 dBm at 915 MHz; sensitivity -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listing: Malaysia AS923-2, Singapore AS923-1; MPN EM400-TLD-915M (product page).
- Power: 2 × 9000 mAh ER26500 Li-SOCl2 replaceable batteries; around 10 years in Standard (10 min) or Bin (20 min) mode at 25 °C (datasheet).
- IP67 with damp-proof coating; -30 ~ 70 °C; ≤ 95 % RH (datasheet).
- 118 × 65 × 30 mm, 208.3 g with batteries, ABS + PC UL94 V0 (datasheet).
- Packing: device, 2 mounting kits, mirror cleaning cloth, warranty card, quick guide (product page).
## Interfaces and compatibility
- No wires or probes; NFC configuration with the Milesight ToolBox app; internal power/reset button and LED (datasheet).
- Works with standard LoRaWAN gateways and network servers and Milesight IoT Cloud; pair with e.g. milesight-ug65.md (datasheet).
- Payload decoders on github.com/Milesight-IoT/SensorDecoders (product page).
- A default ToolBox password and default LoRaWAN keys are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Fill-level monitoring of small and mini trash bins (datasheet).
- Bin lid open/close and fire (combustion) alerts (product page).
- General short-range distance measurement in Standard mode (user guide).
## Known limitations
- Optical: avoid direct sunlight or IR light in the field, glass and mirrors nearby; keep the lens clean and remove the protective film (user guide).
- Range ends at 350 cm (datasheet).
- No Parking Lot mode (user guide).
- Firmware upgrade via ToolBox works on Android only (user guide).
## Positioning (kept apart from specs)
- Milesight: "almost no blind spot" when installed on small waste bins.
- Cytron page: monitors fill level of small and mini trash bins with high accuracy.
## Price band
RM499.40 (Cytron product page, read 2026-10-21; out of stock / enquiry)
## Product page
https://my.cytron.io/Milesight/p-em400-tld-lorawan-tof-laser-distance-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em400-tld-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em400-tld-datasheet-en.pdf
