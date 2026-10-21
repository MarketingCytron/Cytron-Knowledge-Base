# Product fact sheets

## Product name
Milesight UC300 IoT Controller
## Aliases
UC300, UC300 Series, UC300-915M, UC300-L05EU, LR-UC300, LR-UC300-LTE, V-LR-UC300, UC300 IoT Controller (RS485, RS232, DI, DO to LoRaWAN)
## What it is
[NOT STATED]

## Specs and functions
- 4 × opto-isolated DI, 3–24 VDC, digital input or pulse counter up to 4000 Hz (datasheet)
- 2 × DO, SPDT relay, max 3 A @ 30 VDC or 250 VAC (datasheet)
- 2 × 4–20 mA (±5 %) and 2 × 0–10 V (±1 %) analog inputs, 12-bit (datasheet)
- 2 × PT100 RTD inputs, 2/3-wire, 12-bit, -200 to 800 °C (datasheet)
- 1 × RS232 (transparent) and 1 × RS485 (transparent, Modbus RTU), 1200–115200 bps, up to 32 Modbus devices (datasheet)
- LoRaWAN and Milesight D2D; CN470/IN865/EU868/RU864/US915/AU915/KR920/AS923-1&2&3&4; Tx 20 dBm at 915 MHz; -137 dBm; OTAA/ABP Class C (datasheet)
- Cellular version: 4G LTE Cat 1/WCDMA/GSM, Micro SIM, TCP/UDP/MQTT/AWS/Milesight IoT Cloud/SMS (datasheet)
- 1 × SMA female antenna connector, 1 × USB Type-C, SYS and ACT LEDs, internal reset button (datasheet)
- Power 5–24 VDC on a 2-pin 3.5 mm terminal block with surge and reverse-polarity protection, or 5 V via Type-C (datasheet)
- Up to 16 IF-THEN commands, data storage and retransmission on the LoRaWAN version (datasheet, user guide)
- -20 to 60 °C, 0–95 %RH, IP30, 93 × 70 × 22 mm, 142.3 g (LoRaWAN) / 186 g (cellular) (datasheet)
- Cytron versions: LoRaWAN (LR-UC300, MPN UC300-915M) and Cellular (LR-UC300-LTE, MPN UC300-L05EU) (product page)
- Packing: UC300, antenna, power adapter, 5 terminal blocks, DIN rail clip, wall bracket, 4 wall mounting kits, 4 screws (product page)
## Interfaces and compatibility
- DI pins per input: 1 = −, 2 = +, always with an external 0–24 VDC source in the loop (user guide)
- DO pins per relay: COM, NC, NO (user guide)
- 4–20 mA block: +, −, +, −; 0–10 V block: GND/A, 0-10V_1, 0-10V_2; PT100 block: GND/A, 1, 2, B, B (user guide)
- RS232/RS485 block: TX, RX, GND, A, B; DIP switch for 120 Ω termination, B pull-down and A pull-up (user guide)
- Configured with Milesight ToolBox over Type-C or by downlink (datasheet)
- Works with standard LoRaWAN gateways such as Milesight UG65, UG56, UG67 (datasheet, product page)
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page)
## Use cases
- Smart factory and building automation, indoor (datasheet)
- Remote monitoring of meters, PT100 temperatures and 4–20 mA / 0–10 V transmitters (datasheet)
- Relay control from IF-THEN rules or downlinks (user guide)
## Known limitations
- No battery: pulse counts and data are lost on power failure (product page FAQ)
- DI needs an external voltage source; DO cannot drive a DI directly (user guide, product page FAQ)
- 4–20 mA inputs need external loop power (user guide)
- One command per downlink on the LoRaWAN version (product page FAQ)
- IP30, indoor use only (datasheet)
- Power consumption [NOT STATED]
## Positioning (kept apart from specs)
- Milesight: "Rich Industrial Interfaces"; "Intelligent Trigger System"; "Autonomous Operation"
- Cytron: acts as "a central hub for sensor data management and industrial IoT automation"
## Price band
RM602.70 (LoRaWAN) – RM904.05 (Cellular) (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-uc300-iot-controller
## Datasheet
https://resource.milesight.com/milesight/iot/document/uc300-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/uc300-datasheet-en.pdf
