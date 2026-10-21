# Product fact sheets

## Product name
Milesight UC100 IoT Controller (Modbus RTU to LoRaWAN)
## Aliases
UC100, UC100-915M, UC100-915M-EA, UC100 (EA), LR-UC100, LR-UC100-EA, V-LR-UC100, Modbus RS485 to LoRaWAN converter
## What it is
[NOT STATED]

## Specs and functions
- Wireless: LoRaWAN and Milesight D2D; OTAA/ABP, Class C; LoRaWAN V1.0.2/V1.0.3 (datasheet, user guide)
- Frequency plans: CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4 (datasheet)
- Tx power 16 dBm (868 MHz) / 22 dBm (915 MHz) / 19 dBm (470 MHz); sensitivity -137 dBm @300bps (datasheet)
- Antenna: internal, or external 50 Ω SMA female on the EA version (datasheet)
- 1 × RS485 on a 2-pin 3.5 mm terminal block, 120 Ω termination switch, 1200–115200 bps, Modbus RTU and passthrough (datasheet)
- Up to 32 Modbus channels / devices, 1 or 2 registers per channel (datasheet, user guide)
- Up to 16 IF-THEN commands with up to 3 actions each, working without network (user guide)
- Data storage up to 800 entries, retrieval and retransmission; threshold and change alarms; FUOTA (datasheet)
- Power: DC 5–24 V on a 2-pin 3.5 mm terminal block (surge and reverse-polarity protected) or DC 5 V/1 A via USB Type-C; < 0.5 W (datasheet)
- 1 × system LED, 1 × internal reset button (datasheet)
- IP30, -20 to 60 °C, 0–95 %RH non-condensing, 70 × 45 × 13 mm, 32 g, PC+ABS white (datasheet)
- Cytron variants: Internal Antenna (LR-UC100, MPN UC100-915M) and External Antenna (LR-UC100-EA, MPN UC100-915M-EA) (product page)
- Packing: controller, Type-C cable (1.2 m) and power adapter, terminal block, 2 wall mounting kits, quick guide, warranty card; plus magnetic LoRaWAN antenna on the external-antenna version (product page)
## Interfaces and compatibility
- RS485 terminal, DC power terminal, USB Type-C, 120 Ω switch, SMA (EA only) (datasheet, user guide)
- Configured with Milesight ToolBox over USB Type-C or by LoRaWAN downlink (datasheet)
- Works with standard LoRaWAN gateways and network servers, e.g. Milesight UG65, UG56, UG67 (datasheet, product page)
- Milesight Development Platform for device management, API and webhooks (manufacturer page)
- Payload decoders on GitHub Milesight-IoT/SensorDecoders (user guide)
## Use cases
- Smart metering from Modbus energy, water or gas meters (datasheet)
- Smart cities and building automation (datasheet)
- Bringing legacy Modbus RTU field devices onto a LoRaWAN network without rewiring (product page)
- Local automation by IF-THEN rules when the network is down (user guide)
## Known limitations
- No on-board digital or analog I/O; data comes only through RS485 (datasheet)
- Class C only, so it needs continuous power; no battery (datasheet)
- Indoor rating IP30 (datasheet)
- Two-way pass-through disables the Modbus channels (user guide)
- Terminal pin order (A/B, +/−) is not given in the datasheet text [NOT STATED]
- The Cytron page does not state the LoRaWAN frequency plan shipped [NOT STATED]
## Positioning (kept apart from specs)
- Milesight: "Bridge the Digital Gap with UC100 IoT Controller"; "Mini but Powerful"
- Cytron: "bridges the gap between field hardware and modern cloud platforms"
## Price band
[NOT STATED]

## Product page
https://my.cytron.io/Milesight/p-uc100-iot-controller-modbus-rtu-to-lorawan
## Datasheet
https://resource.milesight.com/milesight/iot/document/uc100-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/uc100-datasheet-en.pdf
