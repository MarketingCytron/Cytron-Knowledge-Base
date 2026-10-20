# Maker Nano RP2040 Getting Started Bundles — Verified Reference

| | |
|---|---|
| Product code | `V-MN2040` [PP] |
| Family | Robot parts and project bundles |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). The packing list for both variants is now read: the Blynk bundle includes the Grove WiFi 8266 and a Grove cable, and neither bundle lists a 10K resistor |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [UM-GS] = "Getting Started With Maker Nano RP2040"; [UM-BL] = "Getting Started With Maker Nano RP2040 And Blynk IoT". Both were read as Google Docs text; all figures (pinout, wiring diagrams, Blynk screenshots) are images and were not read. [PP] = live product page, read 2026-10-19 (packing lists for both variants read). The Cytron tutorial "Getting Started With Maker Nano RP2040 & Blynk IoT" (Hussien Jawhar Sathik, 07 Feb 2023, 9-part series)  could not be fetched. **Kit rule:** the board is documented in `maker-nano-rp2040.md`; the Grove WiFi 8266 in `grove-wifi-8266.md`. This file holds bundle-level facts only.

## What it is
- Two beginner bundles built around the Cytron Maker Nano RP2040 board (see `maker-nano-rp2040.md`), each paired with a Getting Started document [PP]:
  - **Getting Started Kit** — breadboard electronics for the Arduino-IDE lessons in [UM-GS].
  - **Getting Started With Blynk IoT** — the same electronics plus a Grove WiFi 8266 (see `grove-wifi-8266.md`) for the Blynk IoT lessons in [UM-BL].
- Price RM58.00–RM88.52 (Cytron product page, read 2026-10-19) [PP]; which price belongs to which variant is not stated in the saved page text.
- Stock 42 on 2026-10-19 [PP]. Warranty not stated in the saved page text.
- Links on the page: both Getting Started docs, the Maker Nano RP2040 datasheet, GitHub MAKER-NANO-RP2040, 3D CAD, and tutorials (Blynk IoT, Grove gas sensor MQ9B, Maker Line) [PP].

## Specifications
No bundle spec table exists. Board specs: see `maker-nano-rp2040.md`. The component lists below are the documents' "List of Components Used" — the product page packing list was not readable, so these are the best available statement of bundle contents (see *Needs verification*).

| Item | Value | Src |
|---|---|---|
| Variants | Getting Started Kit; Getting Started With Blynk IoT | [PP] |
| Price | RM58.00–RM88.52 | [PP] |
| Controller board | Maker Nano RP2040 (MAKER-NANO-RP2040), 1 | [UM-GS][UM-BL] |
| Wi-Fi module (Blynk variant) | Grove WiFi 8266 — "based on the Ai-Thinker's ESP-12F module and comes preloaded with the new Espressif ESP-AT firmware v2.20" (wording as printed) | [UM-BL] |
| Software | Arduino IDE with the arduino-pico board package (earlephilhower) | [UM-GS][UM-BL] |
| IoT platform (Blynk variant) | Blynk (blynk.io), web dashboard and mobile app | [UM-BL] |

### "List of Components Used" — Getting Started With Maker Nano RP2040 [UM-GS]
| No | Item | Cytron code | Qty |
|---|---|---|---|
| 1 | Maker Nano RP2040 | MAKER-NANO-RP2040 | 1 |
| 2 | Breadboard 8.5x5.5cm (400 Holes) | BD-BB-0508 | 1 |
| 3 | 40-Way 10cm Dupont Jumper Wire | WR-JW-4010MM | 1 |
| 4 | Finger Adjust Preset 10K | RS-MP3386-10K | 1 |
| 5 | LED 5mm Green | DS-LED-5NG | 2 |
| 6 | LED 5mm Yellow | DS-LED-5NY | 2 |
| 7 | LED 5mm Red | DS-LED-5NR | 2 |
| 8 | DIY 4 Blades 56mm Motor Propeller (Blue) | HD-PROP-4B | 1 |
| 9 | 3V Miniature Brush Motor with wire leads | MO-300CA-11440 | 1 |
| 10 | Transistor 2N2222 | TR-2N-2222 | 1 |
| 11 | Resistor 0.25W 5% (220R) | RS-025W-220R | 10 |
| 12 | LDR (Small) | SN-LDR-S | 1 |
| 13 | Diodes 1N4007 | DI-1N4007 | 1 |
| 14 | USB Micro B Cable | WR-USB-UB | 1 |
| 15 | Resistor 0.25W 5% (10K) | RS-025W-10K | 1 |

### "List of Components Used" — Getting Started With Maker Nano RP2040 And Blynk IoT [UM-BL]
Same items 1–7 and the propeller, motor, 2N2222, 10x 220R, LDR, 1N4007 and USB Micro B cable (the table is numbered 1–7 then 10–16, i.e. 14 rows). Differences from [UM-GS]: **no 10K resistor row**, and **the Grove WiFi 8266 is not in the table** even though every lesson uses it (see *Conflicts*).
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Packing — Getting Started Bundle:** 1x Maker Nano RP2040 (with 2 Grove to JST-SH cables), 1x breadboard 8.5 × 5.5 cm (400 holes), 1x 40-way 10 cm Dupont jumper wire, 1x finger-adjust preset 10K, 2x each 5 mm LED green / yellow / red, 1x DIY 4-blade 56 mm propeller (blue), 1x DC 2–6 V miniature motor with 20 cm wire, 1x 2N2222 transistor, 10x resistor 0.25 W 5% 220R, 1x LDR (small), 1x USB micro-B cable, 1x 1N4007 diode [PP].
- **Packing — Getting Started With Blynk IoT:** the same list plus **1x Grove WiFi 8266 module** and **1x Grove cable** [PP].
- **No 10K resistor** is listed in either variant; the only 10K part is the finger-adjust preset [PP].
- **Lesson lists on the page:** Getting Started — Lessons 1–8 (LED Blink, Siren, Digital Input, Analog Input, LDR, Temperature Sensor, DC Motor, RGB LED) and Projects 1–4 (Knight Rider, Interactive Traffic Light, Temperature Alarm, Light Theremin); Blynk IoT — Lessons 1–8; the page's list differs from the doc (page: Lessons 5 and 6 both temperature sensor, 8 = RGB LED; doc: 6 = Neopixel Color, 8 = Going Mobile) — follow the doc [PP][UM-BL].
- **Page note:** from April 2026 prices are subject to SST at checkout [PP].

## Interfaces, terminals and pin mapping
Board pins used by the lesson code (board pin facts: `maker-nano-rp2040.md`).

| Function in the lessons | Pin in code | Lesson | Src |
|---|---|---|---|
| Onboard LED blink | `D2` (digitalWrite HIGH = on) | GS L1, GS P3 | [UM-GS] |
| Piezo buzzer | `TONEPIN 22` (tone()) | GS L2, GS P3, GS P4 | [UM-GS] |
| Onboard push button | `20` (INPUT; L7 and P2 read it active-LOW with INPUT_PULLUP / `== LOW`) | GS L3, L7, P2; BL L3 | [UM-GS][UM-BL] |
| Potentiometer | `A0` (GS) / `A3` ("POTENTIMETER A3", BL) | GS L4; BL L4 | [UM-GS][UM-BL] |
| LDR | `A0` (threshold 900) | GS L5, GS P4 | [UM-GS] |
| RP2040 core temperature | `analogReadTemp()` (arduino-pico) | GS L6, P3; BL L5 | [UM-GS][UM-BL] |
| DC motor via 2N2222 (PWM) | `analogWrite(2, …)` | GS L7; BL L7 | [UM-GS][UM-BL] |
| Onboard NeoPixels | `11`, count 2 (GS, WS2812FX) / `PIN 11`, declared as 30 pixels (BL, Adafruit_NeoPixel) | GS L8; BL L6 | [UM-GS][UM-BL] |
| Knight Rider LEDs (10 status LEDs) | 16, 19, 17, 9, 8, 7, 6, 5, 4, 3 | GS P1 | [UM-GS] |
| Traffic light LEDs | vehicle G/Y/R = 4/3/2; pedestrian G/R = 5/6; button 20 | GS P2 | [UM-GS] |
| LED controlled from Blynk | `LED 7` via virtual pin V0 | BL L2 | [UM-BL] |
| Grove WiFi 8266 | Maker Port — code comment "Grove WiFi to Maker port [0, 1]"; `EspSerial Serial1`, 115200 baud, `AT+RST` then 5 s delay | BL all lessons | [UM-BL] |
| Blynk virtual pins | V0 switch→LED; V1 potentiometer / temperature; V2 WidgetLED (button); V3 slider→NeoPixel colour; V4 slider→motor PWM | BL L2–L7 | [UM-BL] |

- **Grove WiFi power note** [UM-BL]: "If the communication between the Maker Nano RP2040 and the Grove Wifi failed. Try to connect the Grove Wifi to the Maker Nano RP2040 as shown below [figure]. The reason is, the power from the 3.3V is not enough to power the ESP8266. Hence we need to connect the power to the 5V." The alternative wiring is a figure only (not read).

## Rules and gotchas (for code, wiring and tutorials)
- **Board package:** add `https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json` in Arduino IDE Preferences, install "pico" from Board Manager, select **Tools → Board → Cytron Maker Nano RP2040** [UM-GS][UM-BL].
- **First upload:** "Hold on the BOOT button when plugging it in to enter the bootloader", then pick the port [UM-GS].
- **Blynk libraries:** "Blynk by Volodymyr Shymanskyy 1.1.0 (Library Manager)" and "BlynkESP8266 (https://github.com/vshymanskyy/BlynkESP8266)"; sketches include `<ESP8266_Lib.h>` and `<BlynkSimpleShieldEsp8266.h>`; NeoPixel lesson adds `<Adafruit_NeoPixel.h>` [UM-BL]. GS Lesson 8 uses `<WS2812FX.h>`; GS Project 4 uses `"pitches.h"` [UM-GS].
- **Grove WiFi on 3.3 V may brown out** → move its power to 5 V per [UM-BL] (see pin table). Keep the ESP8266 UART at 3.3 V logic (`grove-wifi-8266.md`).
- **Blynk send rate:** code comment "Please don't send more that 10 values per second"; the lessons use a `BlynkTimer` at 1000 ms [UM-BL].
- **Button logic differs between lessons:** GS L3 and P2 treat `HIGH` / `LOW` differently (L3 lights the LED when `HIGH`; P2 and L7 act on `LOW`) [UM-GS]. Check the board's button polarity in `maker-nano-rp2040.md` before copying.
- **BL L6 declares 30 NeoPixels** but the board has 2 [UM-BL] — harmless, but set the count to 2 in new code.
- **GS P4 code quirk:** plays `tone(22, …)` but calls `noTone(8)` [UM-GS] — a copy error; use `noTone(22)`.
- **Cross-references inside [UM-GS] use wrong lesson numbers** (see *Conflicts*): quote lessons by title, not number.

## Power and electrical limits
- Bundle adds no power source: the board is powered by the USB Micro B cable [UM-GS component list]. Board limits: `maker-nano-rp2040.md`.
- Grove WiFi 8266 supply 3–6 V [DS in `grove-wifi-8266.md`]; the Blynk doc says 3.3 V from the board can be insufficient and recommends 5 V [UM-BL].
- The DC motor lesson drives a 3 V miniature brush motor through a 2N2222 and a 1N4007 flyback diode with a 220R base resistor [UM-GS component list] — do not drive the motor directly from a GPIO.

## Software support
- Arduino IDE (arduino-pico core) for all lessons [UM-GS][UM-BL]. CircuitPython / MicroPython are not used in either doc (board support: `maker-nano-rp2040.md`).
- **[UM-GS] contents:** Introduction; List of Components; Chapter 1 Getting Started (Installing the Arduino IDE; Installing Additional Board); Chapter 2 Lessons — 1 LED Blink, 2 Siren, 3 Digital Input, 4 Analog Input, 5 Light Dependent Resistor, 6 Temperature Sensor, 7 DC Motor, 8 Neopixel; Chapter 3 Projects — 1 Knight Rider, 2 Interactive Traffic Light, 3 Temperature Alarm (siren + LED above 41 °C), 4 Light Theremin (5 s LDR calibration, 49-note melody table); Appendixes.
- **[UM-BL] contents:** Introduction (board, Grove WiFi 8266, connection note); List of Components; Chapter 1 Getting Started (Arduino IDE; board package; Blynk library; Setting Up Blynk); Chapter 2 Lessons — 1 Getting Connected, 2 Simple LED Control, 3 Push Button As Input, 4 Analog Input, 5 Temperature Sensor (Blynk chart "RP2040 Temperature"), 6 Neopixel Color (slider), 7 Motor Speed Controller (slider), 8 Going Mobile (Blynk app); Chapter 3 Projects — **heading only, no projects written**; Appendix.

## Compatibility and accessories
- Board: Maker Nano RP2040 — see `maker-nano-rp2040.md`. Wi-Fi: Grove WiFi 8266 — see `grove-wifi-8266.md`.
- The Grove WiFi connects "through the Grove 4 pin connector and Maker Port" using the included JST-SH-to-Grove conversion cable [UM-BL].
- Other tutorials linked from the page: Grove gas sensor MQ9B; Maker Line [PP].

## Common mistakes / troubleshooting
- **Board not in Tools → Board** → the arduino-pico package is missing; add the JSON URL and install "pico" [UM-GS].
- **No port shown** → re-plug while holding BOOT (first upload), then select Tools → Port [UM-GS].
- **Blynk never connects / serial shows no "ready"** → try the 5 V power wiring for the Grove WiFi [UM-BL]; check `auth`/`ssid`/`pass` were replaced [UM-BL]; baud is 115200 [UM-BL].
- **Dashboard widget does nothing** → datastream must be a Virtual Pin (V0 Integer for the switch, etc.) and saved before uploading [UM-BL].
- **Theremin silent** → the 5 s calibration needs hand movement over the LDR first [UM-GS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Grove WiFi 8266 in the Blynk bundle | [UM-BL] lessons all require it; [PP] packing list (read 2026-10-19) includes 1x Grove WiFi 8266 module and 1x Grove cable | [UM-BL] "List of Components Used" omits it | Included in the Blynk bundle [PP]; the doc table is incomplete |
| 10K resistor | [UM-GS] row 15: 1x RS-025W-10K | [UM-BL] table has no 10K row; [PP] packing lists (both variants) have no 10K resistor, only a 10K finger preset | Not in either bundle per [PP]; the [UM-GS] row is a components-used entry, not a packing item |
| Lesson numbering in project objectives | [UM-GS] P2 cites "Lesson 4: Digital Input"; P3 cites "Lesson 3: Siren" and "Lesson 7: Temperature Sensor"; P4 cites "Lesson 6: Light Dependant Resistor" | [UM-GS] actual numbering: L2 Siren, L3 Digital Input, L5 LDR, L6 Temperature | Doc error; refer to lessons by title |
| Lesson 3 theory text | [UM-GS] "we would like to see how to control the onboard piezo buzzer" | [UM-GS] L3 code/result: push button controls LED on pin 2 | Copy-paste error in the doc; lesson is Digital Input |
| ESP-AT firmware version wording | [UM-BL] "ESP-AT firmware v2.20" | [GH] in `grove-wifi-8266.md`: V2.2.0 | Same release; use "V2.2.0" |
| Potentiometer pin | [UM-GS] L4: `A0` | [UM-BL] L4: `A3` | Both valid analog pins (A0–A3); follow the lesson being written |
| noTone pin | [UM-GS] P4: `noTone(8)` | [UM-GS] P4: `tone(22, …)` | Code error; buzzer is GP22 [DS] |

## Needs verification
- **Document versions/dates** — neither Google Doc prints a version or date; only Drive created/modified dates are known.
- **5 V wiring for the Grove WiFi** — shown only in a figure; which Maker Port pin or header pin carries 5 V in that wiring is not in text.
- **Maker Port numbering used for the Grove WiFi** — code comment "Maker port [0, 1]" and `Serial1`; the board datasheet gives Maker Port 0 = UART (see `maker-nano-rp2040.md` *Needs verification* on port pins).
- **Button polarity** (active-high vs active-low) as used by the two docs — inconsistent in code.
- **Chapter 3 Projects of [UM-BL]** — empty in the doc read; check whether a newer revision adds projects.
- **Tutorial series body** (9 parts, Feb 2023) — not read.
- Which variant is RM58.00 and which RM88.52 — the page shows the range only; the warranty line on the page is blank.

## Sources
- [PP] https://my.cytron.io/p-maker-nano-rp2040-getting-started-kits — read by the coordinator 2026-10-19 (RM58.00–RM88.52; variants; stock 42; links)
- [UM-GS] Getting Started With Maker Nano RP2040 — https://docs.google.com/document/d/1yqR88btul39hZ77OgUMRrg-d0Z-e3xlgVlNHLoHSLzY/edit (Drive: created 2022-09-23, modified 2023-05-23)
- [UM-BL] Getting Started With Maker Nano RP2040 And Blynk IoT — https://docs.google.com/document/d/1T3FAROtD-uECHmBquAbhmKK9bxdzDWIQn_PhV93oKSo/edit (Drive: created 2022-11-07, modified 2023-10-27)
- [PP: tutorial] https://my.cytron.io/tutorial/getting-started-with-maker-nano-rp2040-and-blynk-iot — not readable here (blocked); metadata from  index https://raw.githubusercontent.com/MarketingCytron/Restructure-Cytron-Tutorial-Page/main/data/tutorials.json (id 566)
- 3D CAD (linked, not opened): https://drive.google.com/file/d/1zVWueJJBDjhU4dvUAFX9pYVlNI8qdmqH/view
- Board package: https://github.com/earlephilhower/arduino-pico ; Blynk shield library: https://github.com/vshymanskyy/BlynkESP8266
- KB cross-references: `maker-nano-rp2040.md`, `grove-wifi-8266.md`
