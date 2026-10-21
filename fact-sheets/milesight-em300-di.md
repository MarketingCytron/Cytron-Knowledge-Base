# Product fact sheets

## Product name
Milesight EM300-DI LoRaWAN Pulse Counter
## Aliases
EM300-DI, LR-EM300-DI, EM300-DI-915M, Milesight EM300-DI, LoRaWAN pulse counter, wireless meter pulse reader
## What it is
A battery-powered LoRaWAN pulse counter made by Milesight and distributed in Malaysia by Cytron (product page). It counts dry-contact pulses from reed-switch water or gas meters (or reads them as a digital input), also measures temperature and humidity, and reports over LoRaWAN Class A (datasheet).
## Specs and functions
- 1 × GPIO dry-contact input on a 1 m lead: pulse counter or digital input (datasheet).
- Pulse input up to 2000 Hz, minimum pulse width 250 µs (datasheet).
- Temperature -30 to 70 °C, ±0.3 °C (0–70 °C); humidity 0–100 % RH, ±3 % (10–90 %) (datasheet).
- LoRaWAN Class A, OTAA/ABP, Milesight D2D; internal antenna; 20 dBm at 915 MHz; -137 dBm (datasheet).
- Cytron sells the 915M version for Malaysia AS923-2 and Singapore AS923-1 (product page).
- Battery: 1 × 4000 mAh ER18505 Li-SOCl2, 5 years at a 10-minute interval (datasheet).
- Stores 1,000 records with retransmission; water flow/outage and temperature alarms (datasheet).
- IP67, ABS+PC, 105.6 × 85.2 × 27 mm, 114.2 g (datasheet).
- Configured by NFC with the Milesight ToolBox app or by downlink (datasheet).
- Packing: device, 2 wall mounting kits, 2 screw caps, quick guide, warranty card (product page).
## Interfaces and compatibility
- Pulse lead: red = GPIO, black = GND, to the two sides of the meter's reed switch (user guide).
- Works with reed-switch meters or other passive pulse meters (datasheet).
- Pulse conversion (e.g. 1 L = 40 pulses) and initial count set in ToolBox (user guide).
- Compatible with standard LoRaWAN gateways and network servers, Milesight IoT Cloud and Development Platform (datasheet).
- Payload decoder on github.com/Milesight-IoT/SensorDecoders (product page).
## Use cases
- Turning traditional water meters into wireless smart meters (datasheet).
- Agricultural irrigation, industrial water use and property meter reading (datasheet).
- Gas and electricity meters with pulse outputs (Milesight product page).
## Known limitations
- Dry-contact input only per the datasheet; no external voltage on the lead (datasheet).
- Only ER18505 Li-SOCl2 cells; alkaline not supported (user guide).
- Battery life is 5 years in the datasheet; Cytron's "up to 10 years" needs the dual-battery version (datasheet, product page).
- Listed as on enquiry; the brand card shows out of stock (product page).
## Positioning (kept apart from specs)
- Cytron: "The User Experience As Good As A Smartphone" via NFC, and "set-and-forget" deployment (product page).
- Milesight: helps building operators collect water data for ESG reporting and green-building certification (Milesight product page).
## Price band
RM275.50 (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-em300-di-lorawan-pulse-counter
## Datasheet
https://resource.milesight.com/milesight/iot/document/em300-di-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em300-di-datasheet-en.pdf
