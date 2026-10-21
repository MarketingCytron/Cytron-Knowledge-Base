# Product fact sheets

## Product name
Milesight UC512 LoRaWAN Solenoid Valve Controller
## Aliases
UC512, UC512-DI-915M, LR-UC512-DI, UC51x series, LoRaWAN irrigation valve controller
## What it is
[NOT STATED]

## Specs and functions
- LoRaWAN, OTAA/ABP, Class A or Class B (datasheet)
- CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4; Tx 20 dBm at 915 MHz; -137 dBm @300bps (datasheet)
- Internal antenna on Cytron's unit (product page)
- 2 × solenoid interfaces for 2-wire DC 12 V latching solenoids, 1.5 m cable (datasheet)
- 2 × digital inputs, 3.3 V logic, 20 mA, digital input or pulse counter ≤ 4000 Hz (datasheet)
- Up to 16 local rules (time, water volume), multicast, FUOTA (datasheet, user guide)
- Power: 3 × 9000 mAh replaceable ER26500 Li-SOCl2 batteries (datasheet)
- Battery life at 20 min reporting and 4 valve operations a day, 25 °C: Class A > 10 years; Class B about 6.2 years (SF7) or 5.8 years (SF10) (datasheet)
- IP68 (1 m, 7 days), -30 to 70 °C, 116 × 116 × 45.5 mm, 479 g (datasheet)
- Packing: UC51x device, 2 × 1.5 m M12 data cables, bracket, wall kits, screw, 2 hose clamps, warranty card, quick guide (product page)
## Interfaces and compatibility
- Solenoid & Pulse M12 interface pins: 1 = DC+/OUT1, 2 = DC-/OUT2, 3 = GND, 4 = INSERT BOOT, 5 = GND, 6 = GPIO (user guide)
- Configuration, valve control and upgrades by NFC with the Milesight ToolBox app (user guide)
- Works with standard LoRaWAN gateways such as Milesight UG65, UG56, UG67 (product page)
- Milesight IoT Cloud and Milesight Development Platform for time and flow control (datasheet)
## Use cases
- Agricultural valve control (datasheet)
- Landscape and garden irrigation (datasheet)
- Water-use monitoring with pulse water meters (product page)
- Scheduled irrigation that keeps running without network (user guide)
## Known limitations
- Only 2-wire DC 12 V latching solenoids (datasheet)
- No solar panel and no DC input on UC512; primary batteries must be replaced, not charged (datasheet, user guide)
- Class A downlinks wait for an uplink unless a response time is set (user guide)
- Configuration by NFC app only (user guide)
- Moisture-based irrigation claimed by Cytron is not a built-in function in the manufacturer documents [NOT STATED]
## Positioning (kept apart from specs)
- Milesight: "LoRaWAN® Solenoid Valve Controller" for smart irrigation
- Cytron: "rugged wireless controller designed for remote and automated irrigation valve management"
## Price band
RM731.85 (Cytron product page, read 2026-10-21; availability by enquiry)
## Product page
https://my.cytron.io/Milesight/p-uc512-lorawan-solenoid-valve-controller
## Datasheet
https://resource.milesight.com/milesight/iot/document/uc51x-series-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/uc51x-series-datasheet-en.pdf
