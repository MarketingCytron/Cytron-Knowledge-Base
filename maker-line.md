# Maker Line — Verified Reference

| | |
|---|---|
| Product code | `MAKER-LINE` (datasheet title [DS]) |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. In stock on my.cytron.io; the page carries the same text the KB had from Cytron's Tindie listing, plus the Hackster tutorial and 3D files |
| Primary source | MAKER-LINE Datasheet — "Simplifying Line Sensor for Beginner" — **Rev 1.0, July 2019** (public Google Doc): https://docs.google.com/document/d/1wZwWl72CKkajTDIyiMxSQ3bwXbWbqW0eq7rdg2MUPeU/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: the datasheet link is **public** (linked from Cytron's Tindie listing; PDF mirror on RobotShop's CDN carries the same title page, Rev 1.0, July 2019). [PP: Tindie] = Cytron Technologies' own Tindie listing (seller "Cytron Technologies"); it stands in for the my.cytron.io product page, which was **not read**. No separate user manual, no Cytron GitHub library/example and no [DT] confirmation were found.

## What it is
A line sensor with an array of 5 infrared sensors (S1–S5) for line-following robots and AGVs [DS][PP: Tindie]. It gives 5 digital outputs (one per sensor, High when the line is detected) and 1 analog output whose voltage represents the line position [DS]. A slide switch selects a light or dark line, and a one-button calibration stores the result in EEPROM, so there are no per-sensor potentiometers [DS][PP: Tindie]. It runs from 3.0–5.5 V with reverse polarity protection on VCC/GND [DS].

## Specifications
Datasheet Table 2 is titled **"MAKER-LINE Absolute Maximum Ratings"** [DS].

| Item | Value | Src |
|---|---|---|
| VCC voltage | Min 3.0 V, Max 5.5 V | [DS] |
| Digital output voltage (D1–D5), low level | 0 – 0.5 V | [DS] |
| Digital output voltage (D1–D5), high level | 0.7×VCC – VCC | [DS] |
| Analog output voltage (AN) | 0 – VCC | [DS] |
| Sensing distance (VCC = 5V, black line on white surface) | 4 – 40 mm | [DS] |
| Sensor refresh rate | 200 Hz | [DS] |
| Recommended line width | 13 – 30 mm | [DS] |
| Number of sensors | 5 infrared line sensors (S1–S5) | [DS] |
| Outputs | 5 x digital (D1–D5), 1 x analog (AN) | [DS] |
| Line colour | Selectable Light / Dark (Line Color Switch) | [DS] |
| Reverse polarity protection | VCC and GND | [DS] |
| Calibration storage | EEPROM; retained after power-off | [DS] |
| Indicators | Power LED; 5 sensor LEDs (S1–S5) on when the line is detected | [DS] |
| Logic compatibility | "DC 3.3V and 5V compatible (With reverse polarity protection)" | [PP: Tindie] |
| Dimensions | **Not stated in text** (Figure 2 drawing only) | [DS] |
| Current consumption | **Not stated** | [DS] |
| Sensor spacing | **Not stated** | [DS] |
| Operating temperature | **Not stated** | [DS] |

Footnote [DS]: "Sensing distance may reduce if VCC is less than 5V or the line-background contrast is low."
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read on my.cytron.io: 5 IR sensors; line width 13–30 mm; light or dark line selectable; calibration by holding the button 2 s, sweeping across the line and pressing again (saved in EEPROM); 5 digital outputs + 1 analog line-position output; 3.3 V and 5 V compatible **with reverse polarity protection**; sensing height 4–40 mm (5 V, black line on white); refresh rate 200 Hz; applications: line-following robots, AGVs [PP].
- **Packing list:** 1x MAKER-LINE, 2x PCB stand 5 mm, 2x PCB stand 10 mm (screw and nut), 2x M3 screw 4 mm, 2x M3 nut [PP].
- **Resources:** datasheet (Google Doc), "Building A Low-Cost Line Following Robot" (Cytron Hackster tutorial), Maker Line 3D files (IGS and STEP) [PP]. Interface, dimension and sensor-pitch images on the page — not read.

## Interfaces, terminals and pin mapping
I/O connector [DS Table 1] (physical pin order is shown in Figure 1 only, not in text):

| Pin | Function | Src |
|---|---|---|
| VCC | Power input (reverse polarity protected) | [DS] |
| GND | Ground (reverse polarity protected) | [DS] |
| AN | Analog output; voltage represents line position | [DS] |
| CAL | "Short to GND to enter/exit sensor calibration mode" | [DS] |
| D1 – D5 | Sensor 1–5 digital output; High when the line is detected | [DS] |

On-board: Line Sensors S1–S5, Power LED, Sensor LEDs S1–S5, Line Color Switch (Light/Dark), Calibration Button [DS].

**Digital output truth table** [DS Table 3] (Sx = S1…S5, Dx = D1…D5):

| Line Color Switch | Sensor sees | LED (Sx) | Digital output (Dx) |
|---|---|---|---|
| Light | Light surface | On | High |
| Light | Dark surface | Off | Low |
| Dark | Light surface | Off | Low |
| Dark | Dark surface | On | High |

**Analog output vs line position** [DS Table 4]:

| Line position | Line not found | Left | Center | Right | Cross detected (all sensors on) |
|---|---|---|---|---|---|
| Analog output | Less than 0.1 × Vcc | 0.1 × Vcc | Vcc / 2 | 0.9 × Vcc | More than 0.9 × Vcc |
| Vcc = 3.3 V | 0 – 0.33 V | 0.33 V | 1.65 V | 2.97 V | 2.97 – 3.3 V |
| Vcc = 5 V | 0 – 0.5 V | 0.5 V | 2.5 V | 4.5 V | 4.5 – 5 V |

Values between Left–Center–Right vary continuously (arrows in the table) [DS].

**Calibration procedure** [DS section 6]:
1. Mount the MAKER-LINE on the robot exactly as it will be used and power it up.
2. Select the line colour with the slide switch.
3. Press and hold the calibrate button for more than 2 seconds; the LEDs show progress while waiting.
4. All 5 LEDs start blinking once calibration mode is entered; release the button.
5. Move the MAKER-LINE across the line so all sensors are exposed to the line (DS wording: "Swap the MAKER-LINE across the line").
6. Press the calibrate button again to exit. LEDs show the result: **Running Light = successful**; **Fast Blink = failed** ("Contrast between line and background is too low or the sensor is too high from the surface").
- Warning: the sensor-to-surface distance must not change during calibration [DS].
- Recalibrate only if the sensor height, line colour or background colour changes [DS].
- Calibration can also be entered/exited by shorting CAL to GND [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **Digital outputs are High when the line is detected** — "line detected" depends on the Light/Dark switch, not on black/white directly [DS].
- **Calibrate before first use**, with the sensor mounted at its final height, and set the line-colour switch before calibrating [DS].
- The digital high level is 0.7×VCC to VCC and AN spans 0 to VCC [DS]: power the sensor from the same voltage as the controller's logic (e.g. 3.3 V for a 3.3 V board) so outputs never exceed the controller's input limit (derived from [DS] levels).
- Analog thresholds are ratios of Vcc: "line not found" is below 0.1 × Vcc and "cross detected" is above 0.9 × Vcc [DS] — code must treat both ends as special cases, not as far-left/far-right.
- Sensing distance 4–40 mm is quoted **at VCC = 5 V with a black line on white**; it can shrink at lower VCC or low contrast [DS].
- Line width outside 13–30 mm is outside the recommended range [DS].
- Calibration hold: say "press and hold for more than 2 seconds" (section 6) [DS].
- Do not describe it as I2C/UART or as having a library — no Cytron source states either.

## Power and electrical limits
- VCC 3.0–5.5 V (absolute maximum table) [DS].
- Reverse polarity protection on VCC and GND [DS].
- Supply current, output drive current and over-voltage behaviour: **not stated** [DS].

## Software support
- No Cytron library or GitHub example found. The datasheet shows connection diagrams for digital output (Figure 3) and analog output (Figure 4) only [DS].
- Read with standard digital inputs (D1–D5) and one analog input (AN) on any controller; "Analog output also offers higher resolution compared to individual digital outputs" and suits PID control [PP: Tindie].
- Calibration video linked in the datasheet: https://drive.google.com/open?id=19okwq5Kp5xKjQq40woOOhy_JcsLVJZ87 [DS].

## Compatibility and accessories
- "Support wide range of controllers such as Arduino, Raspberry Pi, etc." [PP: Tindie].
- Packing list: 1 x Maker Line; 2 x 5mm PCB stand (screw and nut); 2 x 10mm PCB stand (screw and nut); 2 x M3 screw 4mm; 2 x M3 nut [PP: Tindie].

## Common mistakes / troubleshooting
- **Fast blink after calibration** → contrast too low or sensor too high; lower the sensor (4–40 mm at 5 V) or use a higher-contrast line, then recalibrate [DS].
- **Outputs inverted** → wrong Light/Dark switch setting; set it and recalibrate [DS].
- **Worked on the bench, fails on the robot** → calibrated at a different height; recalibrate mounted [DS].
- **Short sensing range on 3.3 V** → expected; sensing distance is specified at 5 V [DS].
- **Analog reading near 0 V** → line not found, not "far left" [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply voltage wording | [DS] VCC 3.0–5.5 V | [PP: Tindie] "DC 3.3V and 5V compatible" | Not a contradiction; state 3.0–5.5 V [DS] |
| Calibration hold time | [DS] Table 1 "Press and hold for 2 seconds" | [DS] section 6 "for more than 2 seconds"; [PP: Tindie] "press ... for 2 seconds" | Use "more than 2 seconds" |
| Calibration step wording | [DS] "Swap the MAKER-LINE across the line" | [PP: Tindie] "Sweep" the sensor across the line | Typo in DS; write "move/sweep across the line" |
| Line width | [DS] recommended 13–30 mm | [3P] element14 "30mm maximum" | [DS] wins |

## Needs verification
- Physical I/O connector pin order and connector type (Figure 1 not readable as text).
- Dimensions, mounting-hole spacing and sensor pitch (Figure 2 not readable as text).
- Supply current consumption.
- Whether CAL has an internal pull-up (DS only says short to GND).
- Weight — not stated by Cytron ([3P] element14 0.01 kg).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [ESP32 PD Line Following Robot with Maker Line](https://my.cytron.io/tutorial/esp32-pd-line-following-robot-with-maker-line) — Tutorial, Intermediate, 2019 [PP: tutorial]
- [Building Line Following Robot Using Maker Pi Pico, Maker Drive and Maker Line](https://my.cytron.io/tutorial/building-line-following-robot-using-maker-pi-pico-maker-drive-and-maker-line) — Project, Intermediate, 2021 [PP: tutorial]
- [Raspberry Pi Line Following Robot with Maker Line](https://my.cytron.io/tutorial/raspberry-pi-line-following-robot-with-maker-line) — Project, Advanced, 2019 [PP: tutorial]
- [Maker Nano RP2040 Interfacing With Maker Line Using Arduino IDE](https://my.cytron.io/tutorial/maker-nano-rp2040-interfacing-with-makerline) — Tutorial, Beginner, 2022 [PP: tutorial]
- [4.Line Following](https://my.cytron.io/tutorial/line-following) — Tutorial, Beginner, 2023 (part of "Learn Robotics with Bocobot Car Kit and Robo Pico") [PP: tutorial]
- [Line Following Robot using Scratch in Raspberry Pi 5](https://my.cytron.io/tutorial/line-rollowing-robot-using-raspberryPi5-and-scratch) — Tutorial, Beginner, 2024 [PP: tutorial]
- [Maker Line](https://my.cytron.io/tutorial/getting-started-with-rbm-maker-line) — Tutorial, Beginner, 2025 (part of "Getting Started with Robo Base Mini") [PP: tutorial]
- [Maker Line](https://my.cytron.io/tutorial/getting-started-with-rb-maker-line) — Tutorial, Beginner, 2025 (part of "Getting Started with Robo Base") [PP: tutorial]
- [Line Following with MOTION:BIT and Maker Line](https://my.cytron.io/tutorial/line_following_robot_car_using_motionbit) — Tutorial, Beginner, 2026 [PP: tutorial]
- [RDK X5 Robot Kit with Maker Line](https://my.cytron.io/tutorial/rdk-x5-robot-kit-with-maker-line) — Tutorial, Intermediate, 2026 (part of "RDK X5 Mission Ready Robotic Series") [PP: tutorial]

## Sources
- [DS] MAKER-LINE Datasheet Rev 1.0, July 2019 — https://docs.google.com/document/d/1wZwWl72CKkajTDIyiMxSQ3bwXbWbqW0eq7rdg2MUPeU/edit (public; PDF mirror, same revision: https://cdn.robotshop.com/media/c/cyt/rb-cyt-274/pdf/cytron-maker-line-line-sensor-datasheet.pdf; Farnell mirror listed by element14, not opened: https://www.farnell.com/datasheets/4725986.pdf)
- [PP] Product page https://my.cytron.io/p-maker-line-simplifying-line-sensor-for-beginner (URL as linked in a Cytron internal doc; **not read**)
- [PP: Tindie] Cytron Technologies Tindie listing — https://www.tindie.com/products/Cytron/maker-line-simplifying-line-sensor-for-beginner/
- [3P] (cross-check only) https://thepihut.com/products/maker-line-simplifying-line-sensor · https://my.element14.com/cytron/maker-line/simplifying-line-sensor-kit-200hz/dp/4871623 · https://robotshop.com/products/cytron-maker-line-line-sensor
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
