# Product fact sheets

## Product name
Milesight CTH01 LoRaWAN Smart Power Monitor Hub
## Aliases
CTH01, LR-CTH01, CTH01-915M, Milesight CTH01, Smart Power Monitor Hub, 12-channel LoRaWAN energy meter
## What it is
A 12-channel LoRaWAN power and energy monitoring hub made by Milesight and distributed in Malaysia by Cytron (product page). It mounts on a DIN rail in a distribution board, takes three voltage phases plus neutral and up to 12 external RJ11 current transformers, and reports power, energy and power quality over LoRaWAN Class C (datasheet).
## Specs and functions
- Measures RMS voltage and current, power factor, active/reactive/apparent power and energy (import and export), voltage unbalance, voltage and current THD (datasheet).
- Accuracy: active energy ±1 % (IEC 62053-21), reactive energy ±2 % (IEC 62053-23); 6–8 kHz sampling; 50–60 Hz (datasheet).
- Voltage: 100–500 V AC, ±1 %; max 290 Vrms N–L, 500 Vrms L–L; AWG 26–12 wire (datasheet).
- 12 current channels on RJ11, up to 4000 A with Rogowski coils; split-core CTs 100/300/500/1000 A (datasheet).
- 12 single-phase circuits, 4 three-phase groups, or mixed (datasheet).
- USB-C NTC cable-temperature sensor, -20 to 100 °C, ±1 °C (datasheet).
- LoRaWAN Class C, OTAA/ABP, SMB antenna, 20 dBm at 915 MHz (datasheet).
- Cytron sells the 915M hardware for AS923 (Malaysia/Singapore) (product page).
- Stores 20,000 records and 2,000 alarms; 12 months of energy statistics; threshold, out-of-range and power-failure alarms; FUOTA (datasheet).
- Power: 12 V DC from the included AC–DC adapter, 2-pin 5 mm terminal, reverse-polarity protected, max 5.8 W (datasheet).
- Overvoltage category III, pollution degree 2, 4 kVac insulation, IP30, -20 to 70 °C (datasheet).
- 49.3 × 98 × 90 mm, 163 g, 35 mm DIN rail or magnetic mounting (datasheet).
- Approvals: ETL (UL/CSA 61010-1, 61010-2-030), CE, FCC, SRRC (datasheet).
- Packing: hub, power adapter, power terminal wire and block, voltage terminal block, magnetic antenna, USB-C NTC sensor, 4 magnetic voltage cables, screw kits; CT clamps not included (product page).
## Interfaces and compatibility
- 4 voltage terminals (L1, L2, L3, N) on a removable push-button terminal block (user guide).
- 12 RJ11 current channels in groups of three; L1 must use the 1st channel of a group, L2 the 2nd, L3 the 3rd (user guide).
- Configured by Bluetooth with the Milesight ToolBox app; downlink commands also supported (datasheet, user guide).
- Works with RCT-RJ11 split-core CTs sold separately by Cytron (product page).
- Needs a LoRaWAN gateway on the same frequency plan, e.g. Milesight UG65 (product page).
## Use cases
- Energy sub-metering in commercial buildings, industrial plants, data centres and multi-tenant apartments (datasheet).
- Power-quality monitoring: THD, unbalance, PF anomalies (datasheet).
- Cost allocation and preventive maintenance of critical circuits (datasheet).
## Known limitations
- Current transformers are not included and must be bought per circuit (product page).
- Installation only by a qualified electrician with the board de-energized and locked out (user guide).
- Wrong voltage-to-current channel pairing gives wrong power and energy (user guide).
- Rogowski coils cannot be mixed with CTs inside one group (user guide).
- IP30, indoor use only (datasheet).
- Cytron's page names both AS923-1 and AS923-2 for Malaysia (product page).
## Positioning (kept apart from specs)
- Cytron: professional-grade hub for multi-circuit energy management with deployment "in under 30 minutes" (product page).
- Milesight: for energy savings, preventative maintenance and cost allocation in energy management systems (datasheet).
## Price band
RM1,722.00 (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-cth01-lorawan-smart-power-monitor-hub
## Datasheet
https://resource.milesight.com/milesight/iot/document/cth01-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/cth01-datasheet-en.pdf
