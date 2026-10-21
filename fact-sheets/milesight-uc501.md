# Product fact sheets

## Product name
Milesight UC501 LoRaWAN Multi-Interface Controller with External Antenna
## Aliases
UC501, UC501-EA, UC501 (EA Version), LR-UC501-EA, UC50x series
## What it is
[NOT STATED]

## Specs and functions
- LoRaWAN, OTAA/ABP, Class A or Class C, multicast (datasheet)
- CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4; Tx 20 dBm at 915 MHz; -137 dBm @300bps (datasheet)
- External antenna version: 1 × 50 Ω SMA female; magnetic antenna in the box (datasheet, product page)
- 2 × GPIO: digital input, digital output or pulse counter; logic 0–0.8 V low, 2.5–3.3 V high; 20 mA max; ≤ 4000 Hz (datasheet)
- 1 × RS232 or RS485 (software switchable), 1200–115200 bps, Modbus RTU on RS485, 16 Modbus channels (datasheet, user guide)
- 2 × analog input, 12-bit, 4–20 mA or 0–10 V by DIP switch (datasheet, user guide)
- 1 × SDI-12 V1.4 (datasheet)
- Sensor power outputs: 2 × 3.3 V and 2 × 5/9/12 V (DIP switch), 0–10 min before collection (datasheet)
- Power: 2 × 2550 mAh ICR18650 rechargeable cells, embedded 6 V 1.7 W solar panel, or 5–24 VDC by M12 (datasheet)
- Data storage 600 entries, retrieval and retransmission; threshold and change alarms (datasheet)
- IP68 (1 m, 7 days), -20 to 60 °C, 116 × 116 × 45.5 mm, wall or pole mount (datasheet)
- Packing: UC501, 2 × 30 cm data cables, bracket, wall kits, 2 hose clamps, screw, quick guide, warranty card, magnetic antenna (product page)
## Interfaces and compatibility
- Data Interface 1 (6-pin M12): 1 = 5/9/12 V out, 2 = 3.3 V out, 3 = GND, 4 = AI1, 5 = AI2, 6 = 5–24 V DC in (user guide)
- Data Interface 2 (8-pin M12): 1 = 5/9/12 V out, 2 = 3.3 V out, 3 = GND, 4 = GPIO1, 5 = GPIO2, 6 = TXD/A, 7 = RXD/B, 8 = SDI-12 (user guide)
- Internal DIP switches set power-output voltage, analog mode and RS485 termination/bias (user guide)
- Configuration by NFC (Milesight ToolBox app) or internal USB Type-C (ToolBox software) (datasheet)
- Works with standard LoRaWAN gateways such as Milesight UG65, UG56, UG67 (product page)
## Use cases
- Smart agriculture with SDI-12 soil and weather sensors (product page, manufacturer page)
- Meter reading by pulse counting of water, gas and electricity meters (manufacturer page)
- Environmental and water monitoring at remote solar-powered sites (product page)
- Modbus RTU sensors to LoRaWAN (manufacturer page)
## Known limitations
- GPIO output is 3.3 V logic, 20 mA; it cannot drive a relay load directly (product page FAQ)
- DI cannot detect a short circuit (product page FAQ)
- RS232 and RS485 share pins; only one at a time (datasheet)
- Changing DIP switches or using USB needs the case opened (user guide)
- No charging indicator (product page FAQ)
- Battery life [NOT STATED]
## Positioning (kept apart from specs)
- Milesight: "Rich Industrial Interfaces"; "Ultra-Rugged Enclosure for Harsh Environment"
- Cytron: "a versatile sensor hub for connecting various field devices and sensors to a LoRaWAN® network"
## Price band
RM740.45 (Cytron product page, read 2026-10-21; out of stock)
## Product page
https://my.cytron.io/Milesight/p-uc501-lorawan-multi-interface-controller-with-external-antenna
## Datasheet
https://resource.milesight.com/milesight/iot/document/uc50x-series-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/uc50x-series-datasheet-en.pdf
