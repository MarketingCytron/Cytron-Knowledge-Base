# Product fact sheets

## Product name
LiPo Power Shield

## Aliases
SHIELD-LIPO, LiPo Power Shield, Cytron LiPo Power Shield, Shield LiPo, Shield-LiPo, LiPo Shield for Arduino

## What it is
An Arduino shield that powers a stacked Arduino from a single-cell 3.7 V LiPo battery through an onboard 5 V boost converter, with an integrated 500 mA charger fed from the shield's own micro-USB port or from the Arduino's USB port. It has a power switch, charge/full/low-battery/power LEDs, under-voltage protection and a solder jumper for reading the battery voltage from the Arduino.

## Specs and functions
- Product code: SHIELD-LIPO
- Primary source: Cytron LiPo Power Shield User's Manual V1.0, January 2016 (no datasheet exists)
- Output voltage: 5 V
- Output current: user manual — "Output current: 1A" (Features list) and "at least 500mA current, and peak at 1A"; product page — 1000 mA continuous, 700 mA at start-up, over-current cut-off about 1100 mA (sources differ; see the KB file)
- Battery: 3.7 V 1300 mAh LiPo (single cell)
- Integrated charger, charging current: 500 mA
- Charging input: onboard micro-USB port (USB Micro B cable) or the USB port on the Arduino
- Low battery indicator threshold: 3.3 V
- Under-voltage protection cut-out: 2.4 V
- LEDs: Low power (battery below 3.3 V), Power (green), Full (fully charged), Charge (charging)
- Power switch: switches the battery on/off
- Main board reset button (Arduino needs around 30 ms to be ready after reset)
- VBATT solder jumper on the back of the shield: solder the pads to monitor battery voltage from the Arduino
- Stackable side headers
- ICSP header: not passed through (the battery is in the way)
- Packing list: 1 x SHIELD-LIPO
- Warranty: 12 months
- Dimensions: 80 mm × 54 mm, excluding the toggle switch (product page)
- Boost converter / charger IC: [NOT STATED]
- Arduino pins used: 5V and GND only; optional battery-voltage monitoring through pads to A0–A6 (product page)
- Battery connector type: [NOT STATED]
- Boost input: 3.0–4.2 V LiPo/Li-ion to 5 V (product page)
- Works with UNO-layout boards incl. Mega, Leonardo and Due (product page)

## Interfaces and compatibility
- Compatible boards: Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo and possibly other pin-compatible main boards; hardware example uses Arduino UNO / CT-UNO
- Can be stacked with shields on top, or placed on top of other shields; shields that use ICSP for data (e.g. Ethernet Shield) must be below the LiPo shield
- Charging from the Arduino's USB port requires the shield's power switch to be OFF; charging from the onboard USB port works with the switch ON or OFF
- Battery voltage monitoring: bridge the VBATT solder jumper, then read it with the Arduino and view it in the Arduino IDE Serial Monitor (example sketch in the manual)
- Battery sold separately as an option (3.7 V 1300 mAh LiPo, Lip-3.7-1300) on the product page
- No Cytron library or GitHub repository for this product

## Use cases
- Taking an Arduino anywhere with portable LiPo power
- Charging the LiPo battery from the onboard USB port or the Arduino's USB port
- Monitoring the battery voltage from the Arduino via the VBATT solder jumper

## Known limitations
- Output current at least 500 mA continuous, 1 A peak (Features line states 1 A)
- Single-cell 3.7 V LiPo only; under-voltage cut-out at 2.4 V
- ICSP header is not passed through; ICSP-dependent shields must sit below it
- Battery does not charge from the Arduino's USB port while the shield is switched ON
- Battery voltage monitoring requires soldering the VBATT jumper
- Battery not in the manual's packing list (separate item)
- Arduino pins used, dimensions and the monitoring analog pin are not stated in the manual text

## Positioning (kept apart from specs)
- "You can take your Arduino anywhere you wish with this LiPo Power Shield."

## Price band
RM57.75, battery sold separately (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-lipo-power-shield

## Datasheet
https://docs.google.com/document/d/1SKOewuQDMKS-EQSgeAn7w-p6xtPRtCQVZl9MHfjzGYo/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1SKOewuQDMKS-EQSgeAn7w-p6xtPRtCQVZl9MHfjzGYo/view
