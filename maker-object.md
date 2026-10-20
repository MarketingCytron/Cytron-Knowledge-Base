# Maker Object — Verified Reference

| | |
|---|---|
| Product code | `MAKER-OBJECT` (datasheet title [DS]; "Manufacturer #: MAKER-OBJECT" on RobotShop [3P]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. Sale status, price, reverse-polarity protection, the 90° pin header and packing are now Cytron-stated |
| Primary source | **MAKER-OBJECT Datasheet, "Simplifying Object Sensor for Beginner", Rev 1.0, December 2019** (public Google Doc): https://docs.google.com/document/d/1SppJcAoTFGFDSaeBXrI4Ocq24quq-5ybFpr2bNsGMOI/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: no user manual and no [DT] confirmation exist for this product. The datasheet is public: it is found by public web search and linked from Switch Science and The Pi Hut product pages, so it may go in the public KB edition. The Cytron product page could not be read, so no [PP] facts are used. [3P] = reseller pages, cross-check only.

## What it is
A small digital infrared (IR) object sensor. An IR LED sends modulated IR light; an IR receiver with a built-in 38kHz bandpass filter picks up the light reflected from an object. The output goes LOW when an object is within the set range [DS]. The range is set with a trimmer through a small opening at the front of the sensor [DS]. It gives a detected / not-detected signal only, not a distance value (two output states in the spec table) [DS].
Positioning (marketing, not spec): datasheet subtitle "Simplifying Object Sensor for Beginner" [DS].

## Specifications
Every row of the datasheet "2. SPECIFICATIONS" table, exact numbers and units, plus board functions from "1. BOARD LAYOUT & FUNCTION".

| Item | Value | Src |
|---|---|---|
| VCC voltage | 4.5 V min, 5.5 V max | [DS] |
| Output voltage (NPN output with internal pull-up), object detected | 0 V min, 0.8 V max | [DS] |
| Output voltage (NPN output with internal pull-up), no object detected | VCC - 0.5 V min, VCC max | [DS] |
| Sensing distance (adjustable), white surface (A4 size) | 40 cm min, 140 cm max | [DS] |
| Sensing distance (adjustable), black surface (A4 size) | 15 cm min, 60 cm max | [DS] |
| Response time ("Based on IR sensor's datasheet") | 180 µs min, 350 µs max | [DS] |
| IR transmitter | Infrared LED that transmits modulated infrared light | [DS] |
| IR receiver | Receives the IR light reflected from the object; built-in bandpass filter of 38kHz | [DS] |
| Sensing range trimmer | Adjusts the object detection range | [DS] |
| Power LED | On when the sensor is powered up | [DS] |
| Output LED | On when an object is detected | [DS] |
| Output type | NPN output with internal pull-up; LOW when object detected (active low) | [DS] |
| Reverse polarity protection | Yes, on the power input | [DS] |
| Connector | 3 pins: 5V, GND, OUT; 90-degree pin header | [DS][PP] |
| Dimensions | Datasheet section "3. DIMENSION" is a drawing only; no values in the text. See Needs verification | [DS] |
| IR LED / IR receiver part numbers | Not stated | [DS] |
| Supply current | Not stated | [DS] |
| Internal pull-up resistor value | Not stated | [DS] |
| Operating temperature | Not stated | [DS] |
| Weight | Not stated | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** tiny digital IR proximity sensor; IR modulated at 38 kHz "makes it immuned to the ambient light"; NPN output with internal pull-up, LOW when an object is detected; range adjusted through a small opening at the front; **90-degree pin header** for PCB or breadboard; maximum sensing 60 cm (black) – 140 cm (white) [PP].
- **Features:** 4.5–5.5 V; **reverse polarity protection**; breadboard friendly; active-low NPN output with internal pull-up; adjustable range 15–60 cm (black), 40–140 cm (white); applications: sumo robot, obstacle avoidance, auto-gate safety, parking occupancy, entrance sensor [PP].
- **Packing list:** 1x MAKER-OBJECT [PP].
- **Resources:** datasheet (Google Doc), 3D CAD [PP]. Layout and dimension images on the page — not read.

## Interfaces, terminals and pin mapping
- **Connector (3 pins)** [DS]:
  - **5V** — power input for the Maker Object.
  - **GND** — ground.
  - **OUT** — NPN output with internal pull-up. Output LOW when an object is detected (active low).
- Physical pin order on the connector: shown only in the board-layout figure, not in the text — see Needs verification.
- Not a Grove or Maker Port (I²C) connector: no such connector is named in the datasheet [DS]. Do not describe it as Grove or Maker Port.
- Maker Mini Sumo Controller: its datasheet says the opponent-sensor ports are digital, internally pulled up to +5V, active low, with a status LED per port, and "MAKER-OBJECT ports on the bottom layer are wired in parallel" with the screw-terminal ports [DS of MAKER-MSUMO]. Library pin names: `OPP_FC` D6, `OPP_FL` D5, `OPP_FR` D7, `OPP_L` D12, `OPP_R` D13 [GH].

## Rules and gotchas (for code, wiring and tutorials)
- **Active low.** `digitalRead(pin) == LOW` means an object is detected; HIGH means nothing in range [DS]. Cytron's AutoSumo example treats all five opponent inputs HIGH as "no opponent" and acts on `LOW` [GH].
- **Digital only.** The output has two states; there is no analog or distance reading. Use `digitalRead()`, not `analogRead()`, for detection logic [DS].
- **5V sensor.** VCC must be 4.5–5.5 V [DS]. Do not power it from 3.3 V.
- **Output HIGH is close to VCC.** With no object, OUT sits between VCC - 0.5 V and VCC [DS]; at a 5 V supply that is 4.5–5.0 V (derived). Do not wire OUT straight into a 3.3V-only GPIO (for example on RP2040 or ESP32 boards) without checking — see Needs verification.
- **Range depends on the target.** 40–140 cm is for a white A4-size surface; a black A4-size surface gives only 15–60 cm [DS]. Always state the surface colour when quoting range. A sumo opponent's colour and size change the real range.
- **Range is set by hand, not in code.** Use a small Phillips head screwdriver through the small opening at the front of the sensor [DS].
  - Maximum distance: power on, turn the trimmer **clockwise** until the output LED turns off, then turn back **counter-clockwise** slowly until the LED just turns on [DS].
  - Minimum distance: power on, turn the trimmer **counter-clockwise** until the output LED turns off, then turn back **clockwise** slowly until the LED just turns on [DS].
- **38kHz modulation.** The receiver has a built-in 38kHz bandpass filter [DS]. (Reseller copy says this makes it immune to ambient light [3P] — not stated in the datasheet; avoid "immune" as a spec claim.)
- Response time 180–350 µs is taken from the IR sensor's own datasheet, not measured on the module [DS].
- Reverse polarity protection is on the power input [DS] — but still wire 5V/GND correctly.

## Power and electrical limits
- VCC 4.5 V min, 5.5 V max [DS].
- Output LOW (object): 0–0.8 V. Output HIGH (no object): VCC - 0.5 V to VCC [DS].
- Supply current: **not stated** [DS] — do not quote a figure.
- Output sink current: **not stated** [DS] — treat OUT as a logic signal only; do not drive LEDs, relays or buzzers from it.
- Reverse polarity protection on the power input: yes [DS].

## Software support
- No library is needed; read OUT as a plain digital input from any language [DS].
- Arduino with the **Cytron Maker Sumo Library** (for Maker Mini Sumo): opponent inputs `OPP_FC, OPP_FL, OPP_FR, OPP_L, OPP_R`; the AutoSumo example reads them with `digitalRead()` and treats `LOW` as opponent detected [GH].
- MicroPython / CircuitPython / MakeCode examples for Maker Object: **not stated** by any Cytron source read.

## Compatibility and accessories
- Datasheet names no compatible boards [DS]. It needs a 5 V supply and a digital input [DS].
- **Maker Mini Sumo Controller** (`MAKER-MSUMO`): 5 opponent-sensor ports (pulled up to +5V, active low, status LEDs), with MAKER-OBJECT ports on the bottom layer wired in parallel [DS of MAKER-MSUMO].
- 3D CAD file: linked by Switch Science as https://drive.google.com/file/d/1RcpZzOPwZLUYpVj9i1CqrAfx6d8SqpDe/view [3P link; file not opened].

## Common mistakes / troubleshooting
- **Robot "sees" an opponent all the time / never:** the trimmer is set wrong. Re-set it with the datasheet procedure while watching the output LED [DS].
- **Code reacts backwards:** the output is active low — LOW = detected [DS][GH].
- **Short range on a dark opponent:** expected — black surface range is 15–60 cm vs 40–140 cm for white [DS].
- **Sensor dead at 3.3 V:** VCC min is 4.5 V [DS].
- **Output LED on but code sees nothing:** check OUT is wired to the input pin you read, and that the pin is a digital input [DS][GH].
- Don't quote "up to 140 cm" without saying "white A4-size surface" [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| White-surface range | [DS] 40–140 cm | [3P] Botland spec section: 4 cm to 140 cm (its own description says 40–140 cm) | [DS] wins: 40–140 cm. Botland figure is a typo |
| Range in Ikedo V2 kit | [DS] 15–60 cm (black) / 40–140 cm (white), adjustable | [3P] MakerPH kit page: "Range: 50cm adjustable" | [DS] wins; 50 cm is a reseller simplification |
| Dimensions | [DS] drawing only, no values in text | [3P] Switch Science / Botland: 18.6 x 13.7 x 12.6 mm; Botland table also lists 6 cm × 10 cm × 1.5 cm | Unresolved — see Needs verification. Do not quote dimensions as spec |
| Ambient light | [DS] 38kHz bandpass filter (no immunity claim) | [PP] (read 2026-10-19): "modulated at 38kHz makes it immuned to the ambient light"; [3P] The Pi Hut / RobotShop: "immune" | Cytron page claims immunity; in specs keep the [DS] wording (38 kHz bandpass filter) |

## Needs verification
- **Dimensions.** [3P] Switch Science and Botland give 18.6 x 13.7 x 12.6 mm; the datasheet drawing is not readable as text. Confirm from the datasheet drawing or 3D CAD.
- **Connector pin order** (5V / GND / OUT left-to-right) — only in the datasheet figure.
- **Supply current**, output sink current and internal pull-up value — not stated.
- **3.3V-logic boards.** Is OUT safe on a 3.3V-only GPIO (pull-up value and whether a divider/level shifter is needed)? Ask the design team before writing a Pico/ESP32 tutorial.
- **IR LED and IR receiver part numbers** — not stated (response time quotes "IR sensor's datasheet").
- **Trimmer procedure context.** The datasheet does not say whether a target object should be placed in front while setting maximum/minimum distance.
- **Weight** — [3P] Botland 0.004 kg only.
- Whether The Pi Hut's mirrored PDF (https://cdn.shopify.com/s/files/1/0176/3274/files/MAKER-OBJECT_Datasheet.pdf?v=1610043705) is the same Rev 1.0 — could not be downloaded (proxy 403).

## Sources
- [DS] MAKER-OBJECT Datasheet, Rev 1.0, December 2019 (public Google Doc) — https://docs.google.com/document/d/1SppJcAoTFGFDSaeBXrI4Ocq24quq-5ybFpr2bNsGMOI/edit
- [DS mirror, not opened] https://cdn.shopify.com/s/files/1/0176/3274/files/MAKER-OBJECT_Datasheet.pdf?v=1610043705 · 3D CAD https://cdn.shopify.com/s/files/1/0176/3274/files/MAKER-OBJECT_CAD.zip?v=1610043737
- [PP, not read] https://my.cytron.io/p-maker-object-simplifying-object-sensor-for-beginner · https://www.cytron.io/p-maker-object-simplifying-object-sensor-for-beginner
- [DS of MAKER-MSUMO] via KB entry maker-mini-sumo.md — https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit
- [GH] https://github.com/CytronTechnologies/CytronMakerSumo (README.md, CytronMakerSumo.h, examples/AutoSumo/AutoSumo.ino)
- [3P] https://www.switch-science.com/products/6241 · https://thepihut.com/products/maker-object-simple-object-sensor-for-beginners · https://www.robotshop.com/products/cytron-maker-object-sensor · https://botland.store/digital-distance-sensors/16039-cytron-maker-object-digital-distance-sensor-ir-38khz-5904422349134.html · https://st.robu.in/product/maker-object-simplifying-object-sensor-for-beginner · https://www.makerph.com/product/ikedo-mini-sumo-robot-v2-starter-kit/
