# Product fact sheets

## Product name
Milesight EM400-MUD LoRaWAN Ultrasonic Distance Sensor
## Aliases
EM400-MUD, LR-EM400-MUD, EM400-MUD-915M, Milesight EM400-MUD, multifunctional ultrasonic distance sensor
## What it is
A battery-powered LoRaWAN ultrasonic distance sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron (product page). It measures 3–450 cm, adds tilt and temperature sensing, has Standard, Bin and Parking Lot modes, and is aimed at waste bins and parking spaces (datasheet).
## Specs and functions
- Detection range 3 ~ 450 cm with a small blind zone (datasheet).
- Accuracy ± (1 + 0.3 % × S) cm, S = distance, over -15 °C ~ 60 °C; resolution 1 mm (datasheet).
- Beam angle 60° (datasheet).
- 3-axis accelerometer: Normal / Tilt status, tilt = offset angle of 20° or more (datasheet, user guide).
- NTC temperature sensor -40 ~ 125 °C, resolution 0.1 °C, for trash-burning alarms (datasheet).
- LoRaWAN Class A, OTAA/ABP; Tx power 16 dBm (868 MHz) / 20 dBm (915 MHz) / 19 dBm (470 MHz); sensitivity -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listing: Malaysia AS923-2, Singapore AS923-1; MPN EM400-MUD-915M (product page).
- Power: 2 × 9000 mAh ER26500 Li-SOCl2 replaceable batteries (datasheet).
- Battery life: Standard mode over 10 years (10 min interval), Bin mode over 10 years (20 min interval), Parking lot mode 5 years (12 triggers per day), all at 25 °C (datasheet).
- IP67 with internal damp-proof coating; -30 ~ 70 °C; ≤ 95 % RH (datasheet).
- 118 × 65 × 32.5 mm, 181.4 g with batteries, ABS + PC UL94 V0 housing (datasheet).
- Internal power/reset button and LED; NFC on/off and configuration (datasheet).
- Packing: 1 × sensor module (product page); Milesight's box adds 2 mounting kits, warranty card and quick guide (user guide).
## Interfaces and compatibility
- No wires or probes; configure by NFC with the Milesight ToolBox app (user guide).
- Works with standard LoRaWAN gateways and network servers and with Milesight IoT Cloud (datasheet).
- Pairs with a Milesight gateway such as milesight-ug65.md (product page).
- Payload decoders on github.com/Milesight-IoT/SensorDecoders (product page).
- A default ToolBox password and default LoRaWAN keys are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Fill-level monitoring of medium or large trash bins (datasheet).
- Parking space occupancy detection (datasheet).
- General distance and level measurement in Standard mode (product page).
## Known limitations
- Must be mounted level, above the target, with a clear path, at least 30 cm from side walls (user guide).
- Range ends at 450 cm; below 3 cm is not measured (datasheet).
- Firmware upgrade via ToolBox works on Android only (user guide).
- Threshold alarms only in Bin and Standard modes (user guide).
- Replace both batteries together (user guide).
## Positioning (kept apart from specs)
- Milesight: "multifunctional ultrasonic distance sensor" with small blind spots and three pre-set modes.
- Cytron page: cost-effective and reliable option for smart waste and smart parking.
## Price band
RM499.40 (Cytron product page, read 2026-10-21; out of stock / enquiry)
## Product page
https://my.cytron.io/Milesight/p-em400-mud-lorawan-ultrasonic-distance-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em400-mud-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em400-mud-datasheet-en.pdf
