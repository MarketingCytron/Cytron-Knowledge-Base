# Product fact sheets

## Product name
Milesight EM500-PT100 LoRaWAN Industrial Temperature Sensor (T200)
## Aliases
EM500-PT100, EM500-PT100-T200, LR-EM500-PT100-T200, EM500-PT100-915M (T200), Milesight PT100 sensor
## What it is
A battery-powered LoRaWAN PT100 platinum RTD temperature sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron, which sells the T200 range variant (product page). An IP67 EM500 transceiver reads a 3-wire stainless-steel probe on a 1.5 m Teflon cable (datasheet).
## Specs and functions
- PT100, 3-wire connection; T200 range -50 °C ~ 200 °C (datasheet).
- Accuracy Class A, typical ± 0.6 °C over -50 ~ 200 °C; resolution 0.1 °C (datasheet).
- Probe: 304 stainless steel straight tube Φ4 × 30 mm, IP67; contact installation (datasheet).
- Cable: Teflon, rated -200 ~ 290 °C, 1.5 m (datasheet).
- LoRaWAN Class A, OTAA/ABP, plus Milesight D2D; internal antenna; 20 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listing: Malaysia AS923-2, Singapore AS923-1 (product page).
- Data storage 1,000 entries, retransmission, retrievability, threshold and change alarms (datasheet).
- Power: 1 × 19000 mAh ER34615 Li-SOCl2 battery; 10 years at 10-min interval, 25 °C (datasheet).
- Transceiver IP67, -30 ~ 70 °C, 0–100 % RH, 105.4 × 71 × 69.5 mm, 362.7 g with probe (datasheet).
- Pole, wall or DIN-rail mounting (datasheet).
## Interfaces and compatibility
- Internal terminal block: pin 1 white GND, pins 4 and 5 red PT1 (user guide).
- Internal USB Type-C for ToolBox PC software; NFC for the ToolBox app (datasheet).
- Uplink temperature in °C (INT16/10); 0xFFFD = out of range (user guide).
- Works with standard LoRaWAN gateways and Milesight IoT Cloud; pair with e.g. milesight-ug65.md (datasheet).
- A default ToolBox password and default LoRaWAN keys are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Industrial machine and pipe temperature (datasheet).
- Oven, cooking, chimney and boiler temperature (datasheet).
- Liquid or gas temperature, medical or laboratory use (datasheet).
## Known limitations
- T200 range ends at 200 °C; hotter processes need Milesight's T500 or T800 variants, which Cytron does not list (datasheet).
- The transceiver must stay within -30 ~ 70 °C (datasheet).
- ER34615 Li-SOCl2 battery only (user guide).
## Positioning (kept apart from specs)
- Cytron page: industrial-grade, UV- and vibration-resistant, for precise temperature control.
- Milesight: corrosion-resistant cable and multiple probe options.
## Price band
RM671.60 (Cytron product page, read 2026-10-21; sold on enquiry)
## Product page
https://my.cytron.io/Milesight/p-em500-pt100-industrial-temperature-sensor
## Datasheet
https://resource.milesight.com/milesight/iot/document/em500-pt100-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em500-pt100-datasheet-en.pdf
