# Maker Soil Moisture Sensor (Capacitive) — Verified Reference

| | |
|---|---|
| Product code | `MAKER-SOIL-MOISTURE` (datasheet figure/table captions [DS]; product page code `MAKER-SOIL-MOISTURE` [PP]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Still out of stock. The packing list, "no voltage regulator on board" and the DIS behaviour (HIGH = disabled) are now Cytron-stated |
| Primary source | **MAKER SOIL MOISTURE SENSOR Datasheet — Rev 1.0, January 2022** (public Google Doc linked from the product page): https://docs.google.com/document/d/1XErDF1j2W9LaeTdB7ySIbm4T83_ov0TZtVC47lmC7Pg/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: the datasheet is public (linked from the my.cytron.io product page and from The Pi Hut and Core Electronics; RobotShop's CDN mirrors the same Rev 1.0, January 2022 PDF — read and matched). [PP] facts (code, price, stock, documents) were read from the product page by the coordinator on 2026-10-16; the page text itself was not read here. The product page also links a 3D CAD file ("3D CAD - MAKER-SOIL-MOISTURE.zip", Google Drive, 5.4 MB, dated 2022; not opened). No user manual and no [DT] confirmation exist. [GH] = Cytron board example repos that read this sensor (via KB entries robo-pico.md, robo-esp32.md, maker-uno-rp2040.md). Cytron's self-watering-pot tutorial (tutorial.cytron.io, 2022-03-25) could not be fetched here.

## What it is
A capacitive soil-moisture sensor on a probe-shaped PCB with a 4-pin Grove port (GND, VCC, DIS, OUT) [DS]. The capacitive probe detects the presence of water in soil and the board gives an **analog output voltage: higher voltage = less moisture** [DS]. Three LED indicators (Blue = WET, Green = MOIST, Red = DRY) turn on according to the output voltage, and a DIS pin disables the sensor (HIGH = disabled) to cut current to the 100 µA range [DS]. It runs from 2.5–7.0 VDC [DS]. Sold as "Maker Soil Moisture Sensor (Capacitive)" with Grove cable options [PP].
Positioning (marketing, not spec): reseller copy — corrosion-resistant capacitive probe, double-sided probe "more sensitive to moisture changes", for automatic plant watering and smart/IoT gardens [3P].

## Specifications
Datasheet Table 2 is titled **"MAKER-SOIL-MOISTURE Absolute Ratings"** [DS]. Every row:

| Item | Value | Src |
|---|---|---|
| VCC voltage (VCC) | Min 2.5 VDC, Max 7.0 VDC | [DS] |
| Analog output voltage (OUT) | Min 1.0 V, Max 5.2 V | [DS] |
| Disable pin threshold voltage (DIS) | Min VCC − 0.8 V, Max — (not stated) | [DS] |
| LED turn-on output voltage @ VCC = 3.3 V — Blue (WET) | 1.4 – 1.8 V | [DS] |
| LED turn-on output voltage @ VCC = 3.3 V — Green (MOIST) | 1.8 – 2.1 V | [DS] |
| LED turn-on output voltage @ VCC = 3.3 V — Red (DRY) | 2.1 – 2.3 V | [DS] |
| LED turn-on output voltage @ VCC = 5.0 V — Blue (WET) | 2.3 – 2.7 V | [DS] |
| LED turn-on output voltage @ VCC = 5.0 V — Green (MOIST) | 2.7 – 3.1 V | [DS] |
| LED turn-on output voltage @ VCC = 5.0 V — Red (DRY) | 3.1 – 3.6 V | [DS] |
| Current consumption, VCC = 3.3 V | 5.4 – 5.6 mA | [DS] |
| Current consumption, VCC = 5.0 V | 3.6 – 3.7 mA | [DS] |
| Current consumption when disabled, VCC = 3.3 V | 80 – 140 µA | [DS] |
| Current consumption when disabled, VCC = 5.0 V | 140 – 180 µA | [DS] |
| Sensing method | Capacitive probe "used to detect the presence of water in soil" | [DS] |
| Output type | Analog; "Higher voltage = less moisture" | [DS] |
| Disable pin | DIS: "HIGH signal disables the sensor" | [DS] |
| Indicators | LED indicators: "Turns on depending on the value of the output" — Blue (WET), Green (MOIST), Red (DRY) | [DS] |
| Connector | Grove port: GND, VCC, DIS, OUT | [DS] |
| Sensor IC | **Not stated** | [DS] |
| On-board voltage regulator | **Not stated** in [DS]; reseller copy: "no onboard voltage regulator, so the LEDs are approximate and might fluctuate with the power supply" [3P] | — |
| Calibration / threshold adjustment | **None listed** (no trimmer or button in the board-functions table) | [DS] |
| Reverse polarity protection | **Not stated** | [DS] |
| Dimensions | **Not stated in text** (Figure 2 drawing only). [3P] board 100 × 25 mm, probe 65 × 20.5 mm — see Needs verification | [DS] |
| Maximum insertion depth | "Soil Limit" marker — [3P] only; not in the datasheet text | — |
| Operating temperature, weight | **Not stated** | [DS] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Description:** capacitive sensing; analog output, higher moisture = lower voltage; works with power only if the LED indicators are enough; LED levels are approximate and may fluctuate with supply "since the sensor does not have a voltage regulator on board"; **disable pin: HIGH disables the sensor** (power saving); qualitative, not quantitative, measurement [PP].
- **Features list:** 2.5–7.0 V; analog output; Grove port; dry/moist/wet LEDs; "Soil Limit" marking; double-sided capacitive probe (corrosion resistant); disable pin [PP].
- **Packing list:** 1x Maker Soil Moisture sensor, 1x 50 cm Grove-to-Grove cable [PP].
- **Resources:** datasheet, 3D CAD, 3D images; tutorials "Battery Powered Maker Soil Moisture Sensor" and "Self Watering Pot Featuring Maker Soil Moisture Sensor" [PP].

## Interfaces, terminals and pin mapping
Grove port [DS Table 1] (the physical pin order on the Grove connector is shown in Figure 1 only, not in text):

| Pin | Function | Src |
|---|---|---|
| GND | Ground | [DS] |
| VCC | Power input for the sensor (2.5–7.0 VDC) | [DS] |
| DIS | Disable pin. HIGH signal disables the sensor. Threshold: VCC − 0.8 V min | [DS] |
| OUT | Analog output. Higher voltage = less moisture. 1.0–5.2 V | [DS] |

- Cytron board examples wire it to a **Grove analog port**: Robo Pico Grove 6 (GP27) [GH via robo-pico.md]; Robo ESP32 Grove 7 (OUT = D36) [GH via robo-esp32.md]; Maker Uno RP2040 example repo uses the "Maker Soil Sensor" [GH via maker-uno-rp2040.md].
- The datasheet does not say whether DIS has an internal pull-down (i.e. whether it may be left unconnected — on a standard Grove analog port the second signal pin is often unused). See Needs verification.

## Rules and gotchas (for code, wiring and tutorials)
- **Higher voltage = drier soil** [DS]. Code that maps "higher reading = wetter" is backwards. Dry → Red LED, Moist → Green, Wet → Blue [DS].
- **OUT can exceed 3.3 V.** The output range is 1.0–5.2 V [DS]. At VCC = 5 V the DRY band alone is 3.1–3.6 V [DS] — above a 3.3 V ADC's full scale. For a 3.3 V board (Pico/RP2040, ESP32), power the sensor from 3.3 V so the LED bands sit at 1.4–2.3 V [DS], or check that the port can take the voltage (derived from [DS]; Core Electronics also notes a divider "may be needed" [3P]).
- **Output is relative, not a percentage.** The datasheet gives LED turn-on voltage bands, not a moisture-percentage calibration [DS]; "this sensor can only qualitatively test the humidity of the soil and cannot measure quantitatively" [3P]. Tutorials should set a threshold from the user's own dry/wet readings.
- **LED bands depend on VCC.** The three bands are specified separately at 3.3 V and 5.0 V [DS]; quote the supply voltage with any threshold number.
- **DIS: HIGH disables.** Drive DIS HIGH (at least VCC − 0.8 V) to disable; current drops from 3.6–5.6 mA to 80–180 µA [DS]. Use this for battery projects — read, then disable between readings. Leaving DIS LOW keeps the sensor on.
- **DIS threshold tracks VCC.** With VCC = 5 V, DIS needs ≥ 4.2 V to disable (VCC − 0.8 V [DS]) — a 3.3 V GPIO may not reach it. Power the sensor from 3.3 V if a 3.3 V board must drive DIS (derived from [DS]).
- **Current is higher at 3.3 V than at 5 V** (5.4–5.6 mA vs 3.6–3.7 mA) [DS] — counter-intuitive; quote the right pair.
- **Supply range 2.5–7.0 VDC** [DS]: a 3×AAA pack (4.5 V) or a 2S Li-ion (7.4 V) — the latter is above the 7.0 V maximum; do not suggest it.
- Do not state reverse-polarity protection, an on-board regulator, a sensor IC, a probe depth or dimensions as specs — none are in the datasheet text.

## Power and electrical limits
- VCC 2.5–7.0 VDC (absolute ratings table) [DS].
- Current 5.4–5.6 mA at 3.3 V; 3.6–3.7 mA at 5.0 V; disabled 80–140 µA at 3.3 V, 140–180 µA at 5.0 V [DS].
- OUT 1.0–5.2 V [DS]. DIS threshold VCC − 0.8 V min [DS].
- Reverse polarity protection, output drive capability, ESD: **not stated** [DS].

## Software support
- No library needed; read OUT with `analogRead()` / an ADC, drive DIS with a digital output if used (derived from [DS]).
- Cytron board examples that read it: Robo Pico "Analog_Read" (CircuitPython, Grove 6 / GP27) [GH via robo-pico.md]; Robo ESP32 Arduino `AnalogRead` (Grove 7, D36) [GH via robo-esp32.md]; Maker Uno RP2040 examples [GH via maker-uno-rp2040.md].
- Cytron tutorial "3D Printed Self-Watering Pot featuring Maker Soil Moisture Sensor" (2022-03-25, uses Maker Pi RP2040 per The Pi Hut's summary) — https://tutorial.cytron.io/2022/03/25/3d-printed-self-watering-pot-featuring-maker-soil-moisture-sensor/ [PP tutorial; not fetched here].

## Compatibility and accessories
- Datasheet names no compatible boards [DS]. It needs a Grove port (or 4 wires) with one analog input, and a supply of 2.5–7.0 VDC [DS].
- Cytron boards with examples: Robo Pico, Robo ESP32, Maker Uno RP2040 [GH]; Maker Pi RP2040 (tutorial) [3P summary of Cytron tutorial].
- Sold with Grove cable options [PP]; reseller packing list: 1 × Maker Soil Moisture Sensor, 1 × 50 cm Grove-to-Grove cable [3P] — not confirmed from the Cytron page.
- 3D CAD: "3D CAD - MAKER-SOIL-MOISTURE.zip" — https://drive.google.com/file/d/1stZDBLdZ1141wIdrRsNFRAVAT8iRiCNg/view [PP link; file not opened].
- Printable mounting enclosure on Thingiverse (thing:5278599) linked by The Pi Hut [3P].

## Common mistakes / troubleshooting
- **Reading goes up when watering** → expected to go *down*; higher voltage = less moisture [DS]. Check which direction the code maps.
- **ADC reads full scale on a 3.3 V board at VCC = 5 V** → OUT can reach 5.2 V [DS]; power the sensor from 3.3 V or check the input limit.
- **LEDs flicker between colours near a band edge** → bands are narrow (e.g. Green 1.8–2.1 V at 3.3 V) [DS] and reseller copy says LED indication is approximate without an on-board regulator [3P]; use hysteresis in code.
- **Sensor seems dead** → DIS is HIGH (≥ VCC − 0.8 V) [DS]; drive it LOW or leave it per the board's wiring.
- **DIS does not disable from a 3.3 V pin with VCC = 5 V** → threshold is VCC − 0.8 V = 4.2 V [DS]; use 3.3 V VCC or a 5 V-level signal.
- **Different readings in different pots / soils** → the output is qualitative; recalibrate thresholds per installation (derived from [DS] bands; [3P] "cannot measure quantitatively").

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Stock | [PP] out of stock on my.cytron.io 2026-10-16 | [3P] The Pi Hut "Only 11 units left"; Core Electronics "lead time applies" | Status follows [PP]; resellers may hold stock |
| Price | [PP] RM20.58 | [3P] The Pi Hut £5.20 incl. VAT; Core Electronics AUD 12.88 incl. GST | [PP] price is the only Cytron price |
| Dimensions | [DS] drawing only, no values in text | [3P] Core Electronics: board 100 × 25 mm, probe 65 × 20.5 mm | Not a spec until confirmed from the drawing or 3D CAD |
| Voltage regulator | [DS] not stated | [3P] "no onboard voltage regulator" (The Pi Hut, Core Electronics; wording reads as Cytron product-page copy) | Not stated as spec; noted in gotchas with [3P] tag |

## Needs verification
- **Dimensions** (board, probe length, thickness) and the "Soil Limit" marker position / probe depth scale — [3P] Core Electronics: board 100 × 25 mm, probe 65 × 20.5 mm, "10 to 60 mm depth scale"; datasheet Figure 2 is a drawing only. The 3D CAD zip on Drive could confirm.
- **Grove pin order** (which Grove pin is DIS vs OUT; whether OUT is on Grove signal pin 1) — figure only. Needed to say which signal pin a board's Grove analog port reads.
- **DIS default state** (internal pull-down? may it float?) — not stated.
- The Cytron self-watering-pot tutorial (board, code, DIS usage) — URL not fetchable here.
- Whether the "Maker Soil Sensor" named in the Maker Uno RP2040 repo is this product — assumed by name only.
- Reverse polarity protection and sensor IC / oscillator — not stated (no on-board regulator, per the product page).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Monitor Soil Moisture With Maker Nano RP2040 And Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/maker-nano-rp2040-with-maker-soil-moisture-sensor) — Tutorial, Beginner, 2022 [PP: tutorial]
- [3D Printed Battery Holder for Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/3d-printed-battery-holder-for-maker-soil-moisture-sensor) — Tutorial, Beginner, 2022 [PP: tutorial]
- [3D Printed Self-Watering Pot with Maker Soil Moisture Sensor](https://my.cytron.io/tutorial/3d-printed-self-watering-pot-featuring-maker-soil-moisture-sensor) — Tutorial, Beginner, 2022 [PP: tutorial]

## Sources
- [DS] MAKER SOIL MOISTURE SENSOR Datasheet, Rev 1.0, January 2022 — https://docs.google.com/document/d/1XErDF1j2W9LaeTdB7ySIbm4T83_ov0TZtVC47lmC7Pg/edit (public; PDF mirror, same revision and tables, read: https://cdn.robotshop.com/media/c/cyt/rb-cyt-361/pdf/maker-soil-moisture-sensor-capacitive-datasheet.pdf)
- [PP] Product page https://my.cytron.io/p-maker-soil-moisture-sensor (read by the coordinator 2026-10-16: code MAKER-SOIL-MOISTURE, RM20.58, out of stock, warranty 12 months, Grove cable options, datasheet + 3D CAD links)
- [PP] 3D CAD — https://drive.google.com/file/d/1stZDBLdZ1141wIdrRsNFRAVAT8iRiCNg/view ("3D CAD - MAKER-SOIL-MOISTURE.zip"; not opened)
- [PP tutorial, not fetched] https://tutorial.cytron.io/2022/03/25/3d-printed-self-watering-pot-featuring-maker-soil-moisture-sensor/
- [GH] via KB entries robo-pico.md (Grove 6 / GP27), robo-esp32.md (Grove 7 / D36), maker-uno-rp2040.md
- [3P] (cross-check only) https://thepihut.com/products/maker-soil-moisture-sensor-capacitive · https://core-electronics.com.au/maker-soil-moisture-sensor.html · https://www.robotshop.com/products/maker-soil-moisture-sensor-capacitive
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
