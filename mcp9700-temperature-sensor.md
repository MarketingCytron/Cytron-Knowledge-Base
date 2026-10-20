# MCP9700 Linear Temperature Sensor (LM35 Compatible) — Verified Reference

| | |
|---|---|
| Product code | `BCY-TEMP-MCP9700` (datasheet title [DS]; product page [PP]; Switch Science lists "CYTRON-BCY-TEMP-MCP9700" [3P]) |
| Family | Sensors and modules |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Page read directly; header type and 3.3/5 V host compatibility (incl. micro:bit) are now Cytron-stated |
| Primary source | **BCY-TEMP-MCP9700 Linear Temperature Sensor Datasheet, Rev 1.0, August 2023** (public Google Doc linked from the product page): https://docs.google.com/document/d/1Yg4krOVZN__Q0NPKvb4om0IJVZMJksBEIjuhJPlcBTM/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: no user manual and no [DT] confirmation exist for this product. The datasheet is a public Google Doc linked from the public product page, so it may go in the public KB edition. [PP] facts (code, price, stock, warranty, linked documents, "LM35 Compatible" in the name) come from the coordinator's read of the product page on 2026-10-16; the page itself was not fetched here. [GH] = Cytron example-code repository. [3P] = Switch Science, cross-check only. The Microchip MCP9700 datasheet [VEN] was **not** read for this entry.

## What it is
A small breakout board carrying a Microchip MCP9700 linear analog temperature sensor IC [DS title; PP]. It has three pins — GND, VCC and OUT — and gives an analog output voltage that rises 10.0 mV for every 1 °C, with 500 mV at 0 °C [DS]. It runs from 2.3–5.5 V and draws 6 µA typical [DS]. The temperature is calculated from the output voltage with a single subtraction and division (Section 3 of the datasheet) [DS]. Cytron provides example code for Arduino, CircuitPython and MicroPython [GH].
Positioning (marketing, not spec): the product page name adds "(LM35 Compatible)" [PP]; the datasheet itself does not mention the LM35.

## Specifications
Every row of the datasheet "2. SPECIFICATIONS" table (Table 2, which the datasheet captions "BCY-TEMP-MCP9700 Absolute Ratings"), exact numbers and units, plus the pin table (Table 1).

| Item | Value | Src |
|---|---|---|
| VCC Voltage (VCC) | 2.3 min, 5.5 max VDC | [DS] |
| Sensor Output Voltage (VOUT) | 100 min, 2000 max mV | [DS] |
| Output Voltage, TA = 0 °C | 500 typ mV | [DS] |
| Temperature Coefficient, TC | 10 typ mV/°C (pin table: "10.0 mV/°C") | [DS] |
| Temperature Range | −40 min, +150 max °C | [DS] |
| Current Consumption | 6 typ, 12 max µA | [DS] |
| Output Current | 100 max µA | [DS] |
| Output type | Analog voltage on OUT | [DS] |
| Conversion equation | TA = (VOUT − V0°C) / TC, with V0°C = 500 mV and TC = 10 mV/°C; TA in °C, VOUT in mV | [DS] |
| Sensor IC | MCP9700 (in the product name and datasheet title). Whether it is the MCP9700 or MCP9700A grade is not stated — example code comments say "MCP9700/A" | [DS][GH] |
| Accuracy | **Not stated** in the Cytron datasheet | [DS] |
| Pins | 3: GND, VCC, OUT | [DS] |
| Connector type | Not named in the datasheet text; "3 pin headers" per Switch Science [3P] — see Needs verification | [DS] |
| Dimensions | Datasheet section "4. DIMENSION" is a drawing only (Figure 3); no values in the text | [DS] |
| Operating temperature of the board | Not stated separately from the sensing range | [DS] |
| Weight | Not stated | [DS] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Description:** designed and manufactured by Cytron; MCP9700 IC; works with 3.3 V and 5 V systems — NodeMCU, ESP32, micro:bit, Raspberry Pi, Arduino; −40 to 150 °C; 2.3–5.5 V; any system that reads an analog voltage [PP].
- **Features list:** **3-pin male header** (breadboard / jumper friendly); linear sensor with analog output; 10 mV/°C; 2.3–5.5 V; −40 to 150 °C; 6 µA typical [PP].
- **Packing list:** 1x sensor [PP]. **Resources:** datasheet, Cytron GitHub examples, 3D CAD [PP]. Pinout and dimension images on the page — not read.

## Interfaces, terminals and pin mapping
- **Pins (Table 1)** [DS]:
  - **GND** — Ground.
  - **VCC** — Power input for the sensor (2.3–5.5 V).
  - **OUT** — Analog Output (10.0 mV/°C).
- Physical left-to-right order of the three pins is shown only in the board-layout figures (Figure 1 front view, Figure 2 back view), not in the text — see Needs verification.
- No I²C, SPI, Grove or Maker Port connector is named in the datasheet [DS]. It is a plain analog sensor: wire OUT to any ADC-capable pin.
- Pins used in Cytron's examples [GH]: Arduino UNO **A0**; Raspberry Pi Pico **GP28** (CircuitPython `board.GP28`, MicroPython `machine.ADC(28)`).

## Rules and gotchas (for code, wiring and tutorials)
- **The 500 mV offset is the whole story.** TA = (VOUT − 500 mV) / 10 mV/°C [DS]. At 25 °C the output is about 750 mV (derived from the datasheet equation). Code written for a sensor that outputs 0 mV at 0 °C (the LM35 family) and not corrected for the 500 mV offset will read about 50 °C too high — the "LM35 Compatible" label [PP] means the same 10 mV/°C slope, not the same zero point. Always subtract 500 mV.
- **Convert the ADC reading to millivolts using the real ADC reference and resolution.** Cytron's Arduino example uses `vout = raw * 5 * 1000 / 1023` (5 V reference, 10-bit) [GH]; the Pico examples use `raw * 3.3 * 1000 / 65536` (3.3 V, 16-bit scaled `read_u16()` / `AnalogIn.value`) [GH]. Using the Arduino constants on a 3.3 V board (or vice versa) gives wrong temperatures.
- **Output never exceeds 2000 mV** [DS], so it fits a 3.3 V ADC input across the full −40 to +150 °C range (derived from the datasheet VOUT range). No divider needed on 3.3 V boards.
- **Low-current output.** Output current is 100 µA max [DS]. Treat OUT as a high-impedance signal: do not load it with LEDs, low-value pull-downs or long cables without checking; connect it straight to an ADC pin.
- **2.3–5.5 V supply** [DS] — works from 3.3 V and 5 V rails. Supply current is only 6 µA typ / 12 max [DS], so it can be powered from a GPIO or a small battery.
- **Accuracy is not stated in the Cytron datasheet** [DS]. Do not quote "±1 °C", "±2 °C" or "±4 °C" from memory; the Microchip MCP9700 vs MCP9700A grades differ and the fitted grade is not stated. See Needs verification.
- **Read in millivolts, not raw counts.** The datasheet equation uses mV; keep VOUT in mV before subtracting 500.
- The CircuitPython example comment says "convert raw ADC 10-bit input value" but the arithmetic correctly divides by 65536 (16-bit) [GH] — follow the arithmetic, not the comment.
- The datasheet labels its spec table "Absolute Ratings" [DS]; treat VCC 2.3–5.5 V and the −40 to +150 °C range as the limits, not as a guarantee of accuracy over that range.

## Power and electrical limits
- VCC: 2.3 V min, 5.5 V max [DS].
- Current consumption: 6 µA typ, 12 µA max [DS].
- Output voltage range: 100–2000 mV [DS]; 500 mV typ at 0 °C [DS].
- Output current: 100 µA max [DS].
- Temperature range: −40 to +150 °C [DS].
- Reverse-polarity protection: **not stated** [DS] — wire GND/VCC correctly.

## Software support
- No library needed: read OUT with any ADC and apply the datasheet equation [DS].
- **Cytron example code** [GH] https://github.com/CytronTechnologies/Cytron-BCY-TEMP-MCP9700 — "example code for Arduino, CircuitPython and MicroPython":
  - `Arduino/BCY-TEMP-MCP9700/BCY-TEMP-MCP9700.ino` — tested on Arduino UNO; A0; constants `vout0 = 500`, `tc = 10`; prints ambient temperature every 1 s at 9600 baud.
  - `CircuitPython/code.py` — tested on Raspberry Pi Pico; `analogio.AnalogIn(board.GP28)`; prints every 1 s.
  - `MicroPython/main.py` — tested on Raspberry Pi Pico; `machine.ADC(28).read_u16()`; prints every 1 s.
  - README hardware list: BCY-TEMP-MCP9700, Arduino UNO or Maker UNO, Raspberry Pi Pico. "This code applicable to other microcontroller analog pin."
- MakeCode (micro:bit) example: **not stated** by any Cytron source read.

## Compatibility and accessories
- Datasheet names no compatible boards [DS]. Needs a 2.3–5.5 V supply and one ADC input [DS].
- Cytron examples target Arduino UNO / Maker UNO and Raspberry Pi Pico [GH].
- 3D CAD files: Google Drive folder linked from the product page [PP] https://drive.google.com/drive/folders/1bJI6YPCDpRLlHm4FVG3a8iIew17D2P1b (not opened).
- Switch Science says it works with 3.3 V and 5 V controllers such as NodeMCU, ESP32, micro:bit, Raspberry Pi and Arduino [3P] — consistent with the 2.3–5.5 V supply [DS], but Raspberry Pi (no ADC) is a [3P] claim only.

## Common mistakes / troubleshooting
- **Reads ~50 °C too high:** the 500 mV offset was not subtracted (LM35-style code) [DS].
- **Reads wildly wrong / negative:** ADC reference or resolution constant does not match the board (5 V/1023 vs 3.3 V/65536) [GH].
- **Reading jumps around:** OUT is a high-impedance 100 µA output [DS]; keep wires short, add averaging in code, and do not share the ADC pin with other loads.
- **Reads ~−50 °C (output ≈ 0 V):** OUT not connected, or VCC/GND swapped — reverse-polarity protection is not stated [DS].
- **Expecting a digital or I²C sensor:** it is analog only [DS]; there is no address, no library and no calibration register.
- Do not quote an accuracy figure — none is stated [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Name | [DS] "BCY-TEMP-MCP9700 Linear Temperature Sensor" | [PP] "MCP9700 Linear Temperature Sensor (LM35 Compatible)" | Use the [DS] name for specs; "(LM35 Compatible)" is a product-page label and is not a datasheet claim |
| Spec table title | [DS] Table 2 is captioned "Absolute Ratings" but contains typ values (6 µA, 500 mV, 10 mV/°C) | — | No conflict with another source; noted so writers do not call typ values "absolute maximums" |
| CircuitPython comment | [GH] comment says "10-bit" | [GH] code divides by 65536 | Follow the code (16-bit scaled); the comment is a typo |

No numeric disagreement was found between the datasheet, the product page facts given, the GitHub examples and Switch Science (10 mV/°C, 2.3–5.5 V, −40 to 150 °C, 6 µA all match).

## Needs verification
- **Accuracy (°C).** Not stated in the Cytron datasheet; the Microchip datasheet was not read, and whether the MCP9700 or MCP9700A grade is fitted is not stated.
- **Dimensions.** Datasheet Figure 3 is a drawing only; no values readable as text. Confirm from the drawing or the 3D CAD folder.
- **Pin order** (GND / VCC / OUT left-to-right) and **connector type** ("3 pin headers" [3P] Switch Science; whether supplied soldered) — only in the datasheet figures.
- **Reverse-polarity protection** and any on-board decoupling capacitor — not stated.
- micro:bit use: the page lists micro:bit as compatible (analog read); no MakeCode extension or example is linked.

## Sources
- [DS] BCY-TEMP-MCP9700 Linear Temperature Sensor Datasheet, Rev 1.0, August 2023 (public Google Doc) — https://docs.google.com/document/d/1Yg4krOVZN__Q0NPKvb4om0IJVZMJksBEIjuhJPlcBTM/edit
- [PP] https://my.cytron.io/p-mcp9700-linear-temperature-sensor-by-cytron (read by the coordinator 2026-10-16: RM7.77, in stock 192, warranty 12 months; linked documents: datasheet, example code, 3D CAD)
- [GH] https://github.com/CytronTechnologies/Cytron-BCY-TEMP-MCP9700 (README.md, Arduino/BCY-TEMP-MCP9700/BCY-TEMP-MCP9700.ino, CircuitPython/code.py, MicroPython/main.py)
- [PP link, not opened] 3D CAD — https://drive.google.com/drive/folders/1bJI6YPCDpRLlHm4FVG3a8iIew17D2P1b
- [3P] https://www.switch-science.com/products/9791
