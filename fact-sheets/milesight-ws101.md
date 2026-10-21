# Product fact sheets

## Product name
Milesight WS101 LoRaWAN Smart Button
## Aliases
WS101, LR-WS101, Milesight WS101, LoRaWAN smart button, LoRaWAN SOS button, scene button
## What it is
A small battery-powered LoRaWAN wireless push button with short, long and double press actions, an LED and a buzzer, made by Milesight and distributed by Cytron (product page). Each action can send an uplink or a Milesight D2D command to control other devices without a gateway (datasheet).
## Specs and functions
- Three press modes: short (≤ 3 s), long (> 3 s) and double press (within 3 s, can be disabled) (user guide).
- LoRaWAN OTAA/ABP Class A, Milesight D2D controller; Tx up to 22 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Cytron states AS923-2 (Malaysia) and AS923-1 (Singapore) (product page).
- Power: 1 × 1650 mAh ER14335 Li-SOCl2; about 7.1–9.5 years at a 1080 min interval and 10 presses a day (datasheet).
- LED and buzzer feedback; each can be switched off (user guide).
- 50 × 50 × 18 mm, Ø20 mm button, 38.8 g, IP30, -20 to +60 °C (datasheet).
- White Scene Button and red SOS Button versions (datasheet).
- Cytron's packing list shows only the button; Milesight lists 2 wall mounting kits, quick guide and warranty card (product page, user guide).
## Interfaces and compatibility
- No wired interfaces; NFC configuration with the Milesight ToolBox app or by downlink (datasheet).
- Internal reset button, one status LED, one buzzer (datasheet).
- Works with LoRaWAN gateways such as Milesight UG65 or UG56, Milesight IoT Cloud and Development Platform (datasheet).
- Payload: ff 2e 01 short, 02 long, 03 double press (user guide).
- Payload decoder on GitHub Milesight-IoT/SensorDecoders (product page).
## Use cases
- Triggering scenes in smart homes and offices (datasheet).
- Call or service buttons in hotels and care facilities (product page).
- Direct control of Milesight switches or light controllers over D2D (datasheet).
## Known limitations
- Not to be used as the sole emergency response tool (datasheet).
- IP30, indoor only (datasheet).
- ER14335 Li-SOCl2 battery only; alkaline not supported (user guide).
- Default ToolBox password and LoRaWAN keys must be changed (user guide).
- Button colour shipped by Cytron is not stated (product page).
## Positioning (kept apart from specs)
- Milesight: smart button for wireless controls, triggers and alarms (datasheet).
- Cytron: multi-functional, programmable and virtually maintenance-free (product page).
## Price band
RM206.65, enquiry (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-ws101-lorawan-smart-button
## Datasheet
https://resource.milesight.com/milesight/iot/document/ws101-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ws101-datasheet-en.pdf
