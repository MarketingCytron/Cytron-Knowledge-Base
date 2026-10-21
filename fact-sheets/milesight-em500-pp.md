# Product fact sheets

## Product name
Milesight EM500-PP LoRaWAN Pipe Pressure Sensor
## Aliases
EM500-PP, LR-EM500-PP, EM500-PP-915M, Milesight EM500-PP, LoRaWAN pipe pressure sensor
## What it is
A battery-powered LoRaWAN pipe pressure sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron (product page). It pairs an IP67 EM500 transceiver with a stainless-steel vented-gauge pressure sensor on a 1.5 m cable, for pipe, tank and pump pressure monitoring (datasheet).
## Specs and functions
- Vented gauge pressure for liquids and gases; range 0 – 1600 kPa (16 bar) (datasheet).
- Accuracy ± 0.5 % FS; resolution 1 kPa (0.01 bar); overload 150 % FS; long-term stability ± 0.3 % FS per year (datasheet).
- Process connection G 1/2" male; stainless steel 316L sensor, IP65, 60.5 × Ф27 mm, 187 g with cable (datasheet).
- Cable length 1.5 m (datasheet).
- LoRaWAN Class A, OTAA/ABP; internal antenna; 20 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listing: Malaysia AS923-2, Singapore AS923-1; MPN EM500-PP-915M (product page).
- Data storage 1,000 entries, retransmission, retrievability, threshold alarm, D2D controller (datasheet).
- Power: 1 × 19000 mAh ER34615 Li-SOCl2 battery; 10 years at 10-min interval, 25 °C (datasheet).
- Transceiver IP67, -30 ~ 70 °C, 105.4 × 71 × 69.5 mm, 328 g; sensor -10 ~ 70 °C; 0–100 % RH (datasheet).
- Pole, wall or DIN-rail mounting (datasheet).
## Interfaces and compatibility
- Internal terminal block: pin 1 white GND, pin 2 red AIN, pin 6 black 12 V sensor supply; pins 3–5 unused; either of the two red wires may be used (user guide).
- Internal USB Type-C for ToolBox PC software; NFC for the ToolBox app (datasheet).
- Uplink pressure is always in kPa; 0xFFFD = out of range, 0xFFFF = read failure (user guide).
- Works with standard LoRaWAN gateways and Milesight IoT Cloud; pair with e.g. milesight-ug65.md (product page).
- A default ToolBox password and default LoRaWAN keys are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Water mains and pipeline pressure monitoring (product page).
- Tank and pump pressure monitoring (datasheet).
- Water leak detection and oil and gas lines (datasheet).
- HVAC pipe networks (product page).
## Known limitations
- Install on a straight run, away from bends, valves and pumps; use a damper on high-pressure hydraulic systems (user guide).
- Sensor rated -10 ~ 70 °C; use a buffer coil for steam and anti-freeze measures outdoors (user guide).
- Sensor assembly is IP65 while the transceiver is IP67 (datasheet).
- Never push objects into the diaphragm (user guide).
- ER34615 Li-SOCl2 battery only (user guide).
## Positioning (kept apart from specs)
- Cytron page: industry-grade pressure monitoring that helps pre-empt failures, leaks and bursts.
- Milesight: high precision and corrosion resistance.
## Price band
RM1,136.50 (Cytron product page, read 2026-10-21; enquiry)
## Product page
https://my.cytron.io/Milesight/p-em500-pp-lorawan-pipe-pressure-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em500-pp-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em500-pp-datasheet-en.pdf
