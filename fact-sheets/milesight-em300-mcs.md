# Product fact sheets

## Product name
Milesight EM300-MCS LoRaWAN Magnetic Contact Switch
## Aliases
EM300-MCS, LR-EM300-MCS, Milesight EM300-MCS, EM300 magnetic contact switch, IP67 LoRaWAN door sensor
## What it is
A rugged IP67 LoRaWAN door and window open/close sensor with built-in temperature and humidity sensing, made by Milesight and distributed by Cytron (product page). A transceiver box connects by a 1.5 m cable to a reed sensor that pairs with a separate magnet (datasheet).
## Specs and functions
- Magnet detection distance 20–30 mm; sensor cable 1.5 m (datasheet).
- Temperature -30 to +70 °C, ±0.3 °C from 0 to 70 °C; humidity 0–100 % RH, ±3 % from 10 to 90 % (datasheet).
- LoRaWAN OTAA/ABP Class A, Milesight D2D controller; Tx up to 20 dBm; -137 dBm @ 300 bps (datasheet).
- Cytron states AS923-2 (Malaysia) and AS923-1 (Singapore) (product page).
- Stores 2,800 records with retransmission after network loss (datasheet).
- Power: 1 × 4000 mAh ER18505 Li-SOCl2 (8000 mAh version optional); over 10 years at SF7, about 3.2–4.5 years at SF10, with 10 min interval and 48 triggers a day (datasheet).
- Reports every 10 min by default and sends magnet alarms on change (user guide).
- Transceiver 105.6 × 85.3 × 27 mm; magnet 31 × 14 × 7.5 mm zinc alloy (datasheet).
- IP67, UV-resistant, -30 to +70 °C (datasheet).
- Cytron's packing list shows only the device; Milesight lists mounting kits, screw caps, 3M tapes and screws (product page, user guide).
## Interfaces and compatibility
- No user wiring; the reed-sensor cable is fixed (datasheet).
- NFC configuration and power-on with the Milesight ToolBox app; internal power/reset button and LED (datasheet, user guide).
- Works with LoRaWAN gateways such as Milesight UG65, UG56 or UG67, Milesight IoT Cloud and Development Platform (datasheet).
- Payload: magnet 00 = close, 01 = open; temperature and humidity in the same uplink (user guide).
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page).
## Use cases
- Door and window intrusion alarms (product page).
- Cabinet, gate or enclosure door monitoring in harsh or outdoor locations (datasheet).
- Combined door status and room temperature/humidity monitoring in homes, offices and factories (datasheet).
## Known limitations
- Magnet must stay within 20–30 mm and away from iron objects (datasheet, user guide).
- Battery life drops to about 3.2–4.5 years at SF10 (datasheet).
- ER18505 Li-SOCl2 only; alkaline not supported (user guide).
- Default ToolBox password and LoRaWAN keys must be changed (user guide).
- Larger than the WS301 because of the separate transceiver box (datasheet).
## Positioning (kept apart from specs)
- Milesight: "3 sensors in 1", industrial-grade design for harsh environments (datasheet).
- Cytron: adds physical security monitoring against intrusion or unauthorised entry (product page).
## Price band
RM301.35, sold on enquiry (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-em300-magnetic-contact-switch
## Datasheet
https://resource.milesight.com/milesight/iot/document/em300-mcs-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em300-mcs-datasheet-en.pdf
