# Product fact sheets

## Product name
IRIV PiControl Industry 4.0 Agribox (MyAgritech Software included)

## Aliases
KIT-IRIV-AGRBX2, IRIV PiControl Industry 4.0 Agribox, IRIV PiControl Agribox, IRIV Agribox, IRIV Agribox Kit, Agribox v2, IRIV Agriculture Box, IRIV Agribox Agriculture Kit

## What it is
A Cytron smart-agriculture control kit built on an IRIV PiControl CM4 (4GB RAM / 32GB eMMC) and an IRIV IO Controller, with 5 industrial relays for DC pumps/valves and AC pumps, an RS485 soil sensor and an RS485 temperature and humidity sensor. It is sold with the MyAgritech software package for cloud dashboard monitoring, automation scheduling and alerts.

## Specs and functions
- Product code: KIT-IRIV-AGRBX2 (product page)
- Sales status: Enquiry, RM3,673.95, warranty 12 months (product page, 2026-10-21)
- Main controller: IRIV PiControl, Raspberry Pi Compute Module 4, 4GB RAM 32GB eMMC (product page)
- I/O controller: IRIV IO Controller based on Raspberry Pi RP2350 (product page)
- Input voltage: 240 VAC (product page)
- Power supply: Meanwell 24V 100W DC power supply in the packing list; technical specification line says 24 VDC, 1 A (product page)
- Relays: 5x industrial 24 VDC relays; 3 to Hangton HE21 2-pin connectors for DC pumps, lights and valves; 2 to 3-pin 16A AC sockets for high-power AC pumps (product page)
- Soil sensor: RS485 3-in-1, 24 V; temperature -40 to +60 ℃ (0.1 ℃ resolution); moisture 0–100% (1%); EC 0–20000 uS/cm (1 uS/cm) (product page)
- Temperature and humidity sensor: RS485, 24 V; -40 to 120 ℃; 0–99.9 %RH; ±0.3 ℃ and ±2 %RH at 25 ℃; 3 s sampling period (product page)
- Illuminated push button: 24 V, push button with built-in LED, NC or NO (product page)
- MyAgritech software: real-time dashboard, cloud storage and database, automation scheduling, data analysis and reporting, email alerts and notifications; reachable from PC, laptop or smartphone (product page)
- MyAgritech entitlement: 1 user account, a Getting Started Guide and a dedicated support channel upon purchase (product page)
- MyAgritech provider: [NOT STATED]
- MyAgritech licence or subscription terms: [NOT STATED]
- In the box: 1x IRIV PiControl Industry 4.0 Agribox; 1x IRIV PiControl 4GB 32eMMC; 1x IRIV IO Controller; 5x industrial relay; 3x Hangton HE21 2-pin male connectors; 2x AC sockets; 1x industrial illuminated push button; 1x RS485 industrial temperature and humidity sensor; 1x RS485 3-in-1 soil sensor; 1x Meanwell 24V 100W DC power supply (product page)
- Enclosure, IP rating, dimensions and operating temperature: [NOT STATED]

## Interfaces and compatibility
- DC pumps and valves connect through Hangton HE21 2-pin connectors or directly to the relays (product page)
- AC pumps plug into the two 3-pin 16A AC sockets (product page)
- Both sensors use RS485 Modbus; on the IRIV PiControl CM4 the RS485 port is /dev/ttyACM0 (controller datasheet)
- An earlier Cytron tutorial build (PiControl only, Node-RED) used DI0 GPIO13 for the push button, DO0/DO1 GPIO23/24 for pumps and DO2 GPIO25 for the AC socket relay, with the sensors at 9600 baud on Modbus IDs 1 (soil) and 2 (temperature/humidity) (Cytron tutorial)
- Integration targets: fertigation, aquaponics, greenhouse, open-field farming (product page)
- Pumps, valves and sprinklers are not included (product page)

## Use cases
- Smart agriculture and smart-farm upgrades (product page)
- Automatic plant watering and irrigation scheduling (product page)
- Fertiliser mixing (A/B/C or N/P/K) with DC pumps (product page)
- Soil and environment monitoring and agriculture data gathering (product page)
- Training for farmers, students and researchers (product page)

## Known limitations
- Sold by enquiry only (product page, 2026-10-21)
- Power supply rating is stated two ways (24V 100W vs 24 VDC 1 A)
- HE21 connector gender is stated inconsistently on the page
- Relay contact ratings and the box's enclosure, IP rating and size are not stated
- MyAgritech provider, subscription terms and offline behaviour are not stated
- The internal wiring between the controllers, relays and sensors is not documented

## Positioning (kept apart from specs)
- "A Complete Industrial Solution for Smart Agriculture Application" (product page)
- Upgrade an existing farm into a smart farm and manage it remotely from PC, laptop or smartphone (product page)

## Price band
RM3,673.95 (Cytron product page, availability Enquiry, read 2026-10-21)

## Product page
https://my.cytron.io/cytron-industry/p-iriv-picontrol-industry-4.0-agribox-v2-myagritech-software-included

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/cytron-industry/p-iriv-picontrol-industry-4.0-agribox-v2-myagritech-software-included
