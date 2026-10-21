# Product fact sheets

## Product name
Milesight WS202 LoRaWAN PIR & Light Sensor
## Aliases
WS202, LR-WS202, WS202-915M, Milesight WS202, LoRaWAN PIR sensor, PIR and light sensor
## What it is
A small battery-powered LoRaWAN PIR motion and occupancy sensor with a built-in light sensor, made by Milesight and distributed by Cytron (product page). It reports occupied, vacant and bright or dark status, and can switch lights directly over Milesight D2D (datasheet).
## Specs and functions
- PIR detection 120° horizontal × 100° vertical, up to 8 m (datasheet).
- Blocking stickers narrow the view to 70° × 60° (user guide).
- Light: bright or dark status against a threshold set within 1–60000 lux (datasheet).
- LoRaWAN OTAA/ABP Class A, Milesight D2D controller; Tx up to 22 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Cytron MPN WS202-915M, stated for AS923-2 (Malaysia) and AS923-1 (Singapore) (product page).
- Power: 1 × 1650 mAh ER14335 Li-SOCl2; about 4.2 years at SF7 EU868, about 2 years at SF10 US915, with 30 min interval and 30 triggers a day (datasheet).
- Reports occupied immediately, vacant after 120 s idle, and a periodic report every 30 min by default (user guide).
- 50 × 50 × 23.8 mm, 40 g, IP30, -20 to +60 °C (datasheet).
- Packing: sensor, 2 wall mounting kits, 3M tape, 3 blocking stickers, quick guide (product page).
## Interfaces and compatibility
- No wired interfaces; NFC configuration with the Milesight ToolBox app (datasheet).
- One status LED and an internal reset button (datasheet).
- Works with LoRaWAN gateways such as Milesight UG65 or UG56, Milesight IoT Cloud and Development Platform (datasheet).
- D2D lighting control with Milesight WS50x wall switches or the WS558 light controller (product page).
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page).
## Use cases
- Automatic lighting on/off by presence and brightness (product page).
- Room occupancy and motion alarms in homes, offices, schools and warehouses (datasheet).
- Workstation occupancy with the blocking stickers (user guide).
## Known limitations
- PIR needs movement; still occupants are reported vacant after the idle time (user guide).
- Battery life falls to about 2–2.4 years at SF10 (datasheet).
- ER14335 Li-SOCl2 battery only; alkaline cells not supported (user guide).
- Indoor IP30, up to 90 % RH (datasheet).
- Default ToolBox password and LoRaWAN keys must be changed (user guide).
## Positioning (kept apart from specs)
- Milesight: compact, easy-to-install sensor for smart homes, offices, schools and warehouses (datasheet).
- Cytron: reliable presence detection for lighting control and energy saving (product page).
## Price band
RM189.40, sold on enquiry (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-ws202-lorawan-pir-and-light-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/ws202-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ws202-datasheet-en.pdf
