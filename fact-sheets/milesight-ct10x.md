# Product fact sheets

## Product name
Milesight CT Series LoRaWAN Smart Current Transformer (CT101 / CT103 / CT303 / CT310)
## Aliases
CT10x, CT3xx, CT101, CT103, CT303, CT310, V-LR-CT10X, LR-CT101, LR-CT103, LR-CT303, LR-CT310, CT101-915M, CT103-915M, CT303-915M, CT310-915M, Milesight smart current transformer, LoRaWAN CT clamp
## What it is
A family of self-powered LoRaWAN smart current transformers made by Milesight and distributed in Malaysia by Cytron (product page). A split-core clamp around one phase wire harvests its own power, measures RMS current and accumulated ampere-hours, and reports over LoRaWAN; CT101/CT103 have one clamp, CT303/CT310 one transceiver with three clamps (datasheet).
## Specs and functions
- Rated primary current: CT101 100 A, CT103 250 A, CT303 300 A per CT, CT310 1000 A per CT (datasheet).
- RMS current, 3.3 kHz sampling, 50–60 Hz, 1 mA resolution (datasheet).
- Accuracy: CT101/CT103 ±1 % above 5 A and ±3 % at or below 5 A; CT303/CT310 ±1 % (datasheet).
- Minimum current to report when self-powered (1 min / 10 min interval): CT101 1.5 / 1.4 A, CT103 3 / 2.8 A, CT303 3 / 2.5 A, CT310 10 / 8.5 A; lower currents need USB power (datasheet).
- Accumulated Ah reported every interval; optional kWh calculated from a set voltage and power factor (user guide).
- USB-C NTC cable-temperature sensor, -20 to 100 °C, with threshold alarm (datasheet).
- Power: induced current from the measured conductor, or 5 V on USB-C; no battery (datasheet).
- LoRaWAN Class A, OTAA/ABP; SMA antenna; Tx 22 dBm (CT10x) or 20 dBm (CT3xx) at 915 MHz; -137 dBm sensitivity (datasheet).
- Cytron sells the 915M hardware and states AS923-2 for Malaysia and AS923-1 for Singapore (product page).
- Insulation 2.5 kVac (CT10x) or 3 kVac (CT3xx), 1 mA / 1 min; CE, FCC, UL508 (datasheet).
- IP30, indoor only; transceiver -20 to 70 °C (datasheet, user guide).
- Wire hole: CT101/CT103 Ø16 mm, CT303 Ø24.2 mm, CT310 Ø51 mm (datasheet).
- Reporting interval 1–1440 min, default 10 min (user guide).
- Packing: CT, antenna, cable temperature sensor; CT101/103 also transceiver cover and extension cable (product page).
## Interfaces and compatibility
- Split-core clamp around one phase conductor; no terminals (user guide).
- USB Type-C for 5 V power, ToolBox configuration or the NTC sensor (datasheet).
- SMA antenna connector, reboot button, status/alarm LED (datasheet).
- Configured with Milesight ToolBox over USB-C or by LoRaWAN downlink; FUOTA supported (datasheet).
- Works with standard LoRaWAN gateways and network servers, e.g. Milesight UG65/UG56/UG67 (datasheet).
- Payload decoder on github.com/Milesight-IoT/SensorDecoders (product page).
## Use cases
- Energy monitoring in smart buildings (datasheet).
- Machine failure detection and prevention from current patterns (datasheet).
- Sub-metering of three phases or three loads with CT303/CT310 (datasheet).
- Over-current and cable over-temperature alarms (product page).
## Known limitations
- Measures current only; kWh is calculated from a typed-in voltage and power factor (user guide).
- Stops reporting below the minimum current unless powered from USB (user guide).
- CT303/CT310 lose power if no CT is on phase A (user guide).
- Never put phase and neutral through the same CT (user guide).
- IP30, indoor use only; installation by a qualified person (user guide).
- The page is out of stock; variants are on enquiry (product page).
## Positioning (kept apart from specs)
- Milesight: non-invasive clamp design for quick, safe installation without de-energizing facilities (datasheet).
- Cytron: "Self-Powered: No Batteries, No Limits"; superior accuracy with 3.3 kHz sampling (product page).
## Price band
RM361.60 (CT101), RM413.30 (CT103), RM585.50 (CT303), RM1,420.65 (CT310) (Cytron product page, read 2026-10-21)
## Product page
https://my.cytron.io/Milesight/p-ct10x-smart-current-transformer
## Datasheet
[NOT STATED]

## Source type
Datasheet
## Source link
https://resource.milesight.com/milesight/iot/document/ct10x-datasheet-en.pdf
