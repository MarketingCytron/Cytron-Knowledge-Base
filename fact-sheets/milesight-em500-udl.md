# Product fact sheets

## Product name
Milesight EM500-UDL Ultrasonic Distance / Level Sensor (W050 and W100)
## Aliases
EM500-UDL, EM500-UDL-W050, EM500-UDL-W100, LR-EM500-UDL-W050, LR-EM500-UDL-W100, Milesight ultrasonic level sensor
## What it is
A battery-powered LoRaWAN ultrasonic distance and level sensor made by Milesight (Xiamen Milesight IoT Co., Ltd.) and distributed in Malaysia by Cytron in two listings, W050 and W100 (product page). It is one IP67 unit with the ultrasonic horn under the transceiver body, for tank, well, river and silo level monitoring (datasheet).
## Specs and functions
- W050: range 0.3 – 5 m, accuracy ± 1 % FS (datasheet).
- W100: range 0.5 – 10 m, accuracy ± 1 % FS (datasheet).
- Resolution 1 mm for both (datasheet).
- Blind zone is the minimum range: 0.3 m (W050) or 0.5 m (W100) (datasheet, inferred).
- W models have temperature compensation for direct sun or large temperature swings (product page FAQ).
- LoRaWAN Class A, OTAA/ABP, plus Milesight D2D; internal antenna; 20 dBm at 915 MHz; -137 dBm @ 300 bps (datasheet).
- Frequency on the Cytron listings: Malaysia AS923-2, Singapore AS923-1 (product page).
- Data storage 1,000 entries, retransmission, retrievability, threshold alarm, change alarm, D2D controller (datasheet).
- Power: 1 × 19000 mAh ER34615 Li-SOCl2 replaceable battery; 10 years at 10-min interval, 25 °C (datasheet).
- IP67; -30 °C to +65 °C; 0–80 % RH (datasheet).
- 156.1 × 71 × 69.5 mm; 370.4 g with battery and bracket; ABS + PC, grey (datasheet).
- Wall, pole or 35 mm DIN-rail mounting (user guide).
## Interfaces and compatibility
- No probe cable or terminals; internal power button, LED and USB Type-C for configuration and console (datasheet).
- Configure by NFC with the Milesight ToolBox app or by USB-C with ToolBox PC software (datasheet).
- Works with standard LoRaWAN gateways, Milesight IoT Cloud and Milesight Development Platform; pair with e.g. milesight-ug65.md (datasheet).
- Uplink distance in mm; 0xFFFD means outside the range, 0xFFFF means read failure (user guide).
- A default ToolBox password, default LoRaWAN keys and a default D2D key are set at the factory; see the user guide (not copied) (user guide).
## Use cases
- Water, oil or chemical tank levels and overflow detection (product page).
- Reservoir, pit, sump, river and flood monitoring (product page).
- Grain silos and solid materials (hard solids) (product page).
## Known limitations
- Mount vertically, more than 30 cm from side walls, not at the centre of a domed lid and not above an inlet (user guide).
- Target must stay outside the blind zone (0.3 m W050, 0.5 m W100) (datasheet).
- Not suggested for septic tanks with ammonia or methane, or for snow (use S050) (product page FAQ).
- Accuracy is a percentage of full scale: ± 5 cm for W050 and ± 10 cm for W100 at full scale (datasheet, inferred).
- ER34615 Li-SOCl2 battery only (user guide).
## Positioning (kept apart from specs)
- Cytron page: rugged, low-maintenance non-contact sensing for corrosive liquids, wastewater and chemicals.
- Milesight: object distance or level detection without touch in harsh environments.
## Price band
W050 RM1,851.15; W100 RM1,980.30 (Cytron product pages, read 2026-10-21; out of stock / enquiry)
## Product page
[NOT STATED]

## Datasheet
https://resource.milesight.com/milesight/iot/document/em500-udl-datasheet-en.pdf
## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/em500-udl-datasheet-en.pdf
