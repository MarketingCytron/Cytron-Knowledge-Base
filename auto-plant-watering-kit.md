# Auto Plant Watering Kit for micro:bit — Verified Reference

| | |
|---|---|
| Product code | `V-KIT-RBT-APW` (product page, variant parent) [PP]. The Cytron CDN path for the kit's files is `KIT-RBT-APW` [PP: CDN path]; `KIT-RBT-APW-NB` appears only in a CDN video file name — see Needs verification |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Page matches the KB; the IoT guide is still a separate Cytron tutorial (now also linked as a YouTube video) |
| Primary source | No datasheet exists for the kit. Lesson guide: **"Auto Plant Watering Kit for micro:bit"** booklet, English, **April 2022**, "Copyright @ 2022 Cytron Technologies", written by Goh Hao Zhen & Cheryl Ng, illustrated by Suhana Oazmi; file `RBT_APW_KIT_Booklet_English_v1.pdf` (static.cytron.io; "v1" from the file name only) [UM] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: [UM] = the April 2022 booklet, read through a summarising fetch (block images and wiring pictures not readable; all port assignments below are from the booklet's text). [PP] = my.cytron.io product page as read by the coordinator on 2026-10-19. The IoT tutorial "RBT Automatic Plant Watering IoT Project Using Blynk IoT" (my.cytron.io) **could not be fetched** here, so the IoT version is documented only from [PP]. [3P] = Pakronics reseller page (packing list cross-check only). The REKA:BIT board is in **reka-bit.md**, the Maker Soil Moisture Sensor in **maker-soil-moisture.md**, the Grove WiFi 8266 in **grove-wifi-8266.md** — not re-documented here.

## What it is
- A micro:bit lesson kit that builds an automatic plant-watering system: a Maker Soil Moisture Sensor reads the soil, a REKA:BIT drives a submersible pump when the soil is dry, and a micro servo aims the water pipe [UM][PP].
- Five lessons plus two additional activities in a printed Lesson Guide [UM][PP]: 1 Hello!; 2 What's the Soil Moisture Level?; 3 Dry? Moist? Or Wet?; 4 Water the Plant; 5 Servo Motor, Direct the Pipe!; Additional 1 visualise soil moisture on the LED matrix; Additional 2 melodies.
- Four purchase options: standard / IoT version × with micro:bit / without micro:bit [PP]. The IoT version adds 1× Grove WiFi 8266 and follows a separate Cytron Blynk IoT tutorial — "The step-by-step guide for IoT project is not included in the booklet" [PP].
- Lesson guide softcopies: English, Malay, Chinese, Thai (link.cytron.io/apw-book-english / -malay / -chinese / -thai) [PP].

## Specifications
No spec table exists for the kit. Kit-level items only.

| Item | Value | Src |
|---|---|---|
| Controller board | REKA:BIT (with or without micro:bit) | [UM][PP] |
| micro:bit | BBC micro:bit V2 in the "with micro:bit" options | [PP] |
| Kit contents (product page, with micro:bit) | 1× Lesson guide (English), 1× Maker Soil Moisture Sensor, 1× REKA:BIT (with micro:bit V2), 1× Micro Submersible Water Pump DC 3V-5V with Pipe, 1× Analog Micro Servo 9g (3V-6V) with horns and screws, 1× Grove 4 Pin Buckled 50cm Cable, 1× Servo Male-Female Extension Cable 30cm, 1× 4xAA battery holder with DC plug, 4× PKCELL Heavy Duty AA Battery, 1× Tiny Phillips Screwdriver, 2× Popsicle stick, 3× Cable Ties, 2× Double Sided Tapes | [PP] |
| IoT version | adds 1× Grove WiFi 8266 | [PP] |
| Kit contents (booklet "What's in the kit?", no quantities) | Lesson Guide, REKA:BIT (with or without micro:bit), Water Pump with Pipe, Maker Soil Moisture Sensor, Servo Motor, Power and Data Cable, Popsicle Stick, Cable Ties, 50cm Grove Cable, Double-sided Tapes, Servo Extension Cable, Battery Holder & AA Batteries | [UM] |
| Water pump | Micro submersible, DC 3V–5V, with pipe | [PP] |
| Servo | Analog micro servo 9g, 3V–6V, with horns and screws; lesson sweeps 30°–150° | [PP][UM] |
| Soil moisture reading | higher when the probe is dry, lower in water; threshold is calculated by the student (no fixed number) | [UM] |
| Pump run time (Lesson 4) | 5 seconds when the reading is higher than the threshold | [UM] |
| Battery | 4× AA (PKCELL Heavy Duty) in a holder with DC plug, into the REKA:BIT power jack | [PP][UM] |
| Booklet length | contents table ends at page 52; last printed page number 53 | [UM] |
| Warranty | 12 months | [PP] |
| Price | RM108.00–RM214.62 (Cytron product page, read 2026-10-19) | [PP] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- Page re-read: four options — standard with micro:bit V2, standard without micro:bit, IoT version with micro:bit V2, IoT version without micro:bit; IoT versions add a Grove WiFi 8266; "The step-by-step guide for IoT project is not included in the booklet" (Cytron tutorial page) [PP].
- Standard packing (with micro:bit): lesson guide (English), Maker Soil Moisture Sensor, REKA:BIT with micro:bit V2, micro submersible pump DC 3–5 V with pipe, analog micro servo 9 g (3–6 V) with horns and screws, Grove 4-pin 50 cm cable, servo extension 30 cm, 4xAA holder with DC plug, 4x PKCELL Heavy Duty AA, transparent Phillips screwdriver, 2 popsicle sticks, 3 cable ties, 2 double-sided tapes [PP].
- Lesson guides in English, Malay, Chinese and Thai (link.cytron.io); YouTube "RBT Automatic Plant Watering IoT Project Using Blynk IoT"; extra projects tag on the tutorial site; REKA:BIT extension and datasheet [PP]. Prices subject to SST from April 2026 [PP].

## Interfaces, terminals and pin mapping
All from the booklet's hardware-setup text [UM]:

| Component | REKA:BIT connection | Notes | Src |
|---|---|---|---|
| Maker Soil Moisture Sensor | Grove port **P2:P12** (50 cm Grove cable) | read as analog **P2** in Lesson 2; probe goes into the soil "up to the white line" | [UM] |
| Water pump | **MOTOR 2** terminal: black wire → **M2B**, red wire → **M2A** | "Clamp the exposed wire lead, and not the insulator" | [UM] |
| Micro servo | servo port **S1** via the 30 cm extension cable | port pins: White = S (signal), Red = +, Black = −; servo lead to extension: Orange–White, Red–Red, Brown–Black | [UM] |
| Battery holder | REKA:BIT power jack | then "Turn on your REKA:BIT" | [UM] |
| Grove buzzer (micro:bit V1 only) | port **P0:P1** | Additional Activity 2 | [UM] |
| RGB LEDs | on-board REKA:BIT RGB LEDs (green = moist, red = dry in Lesson 3) | pin not named in the booklet (P8 per REKA:BIT datasheet, see reka-bit.md) | [UM] |
| Grove WiFi 8266 (IoT version) | not stated in any source read | see Needs verification | — |

## Rules and gotchas (for code, wiring and tutorials)
- **Extension is `rekabit`** (MakeCode Settings → Extensions → search "rekabit"); it adds the REKA:BIT and Neopixel block drawers [UM]. The booklet does not use the separate `pxt-rekabit-rbt-project-kit` extension; the sensor is read with the plain micro:bit analog-read block on P2 [UM].
- **Moisture logic is inverted versus intuition:** a higher reading = drier soil (sensor output "higher voltage = less moisture" [DS, maker-soil-moisture.md]). Lesson 4 pumps when `reading > threshold` [UM].
- **No fixed dry/moist/wet numbers.** Lesson 2 records three readings (probe dry in mid-air, probe in a cup of water, and the plant's optimum level); Lesson 3 fills in the blanks "Optimum soil moisture level", "When sensor probe is dry", "Time to water the plant" and "calculate to determine the threshold value" [UM]. Do not publish a universal threshold.
- **Pump timing:** Lesson 4 runs the pump for 5 seconds per trigger; to test, pull the sensor out and dry it [UM].
- **Servo sweep:** Lesson 5 sweeps 30°–150° while the pump runs and stops at the optimum level; check that the pipe points at the pot [UM].
- **Keep electronics dry:** the booklet's only warning — do not wet the Maker Soil Moisture Sensor's exposed part or the REKA:BIT, "risk damaging electronic components on the board" [UM].
- **micro:bit V1 has no speaker:** Additional Activity 2 needs a Grove buzzer on P0:P1; V2 uses the built-in speaker [UM].
- **Flashing:** one-click WebUSB download needs the new Edge or Chrome and the latest micro:bit firmware; troubleshooting at makecode.microbit.org/device/usb/webusb/troubleshoot [UM].
- **Pins taken:** P2 (and P12 on the same port) by the sensor; M2 by the pump; S1 by the servo; P0:P1 if a buzzer is added [UM]. Leave M1, S2–S4 and the other Grove ports free.

## Power and electrical limits
- Power: 4× AA batteries in the holder → REKA:BIT power jack [UM][PP]. The booklet states no voltage figure.
- Pump: DC 3V–5V [PP]; servo: 3V–6V [PP]. On REKA:BIT the motor and servo rails equal the battery voltage (see reka-bit.md), so a fresh 4× AA pack (~6 V nominal for alkaline — not stated by any source) sits at the top of both ranges; see Needs verification.
- All board limits (3.6–6 V input, 1 A/1.5 A per motor, 300 mA Grove 3V3, 7 V cut-off) are the REKA:BIT's — see reka-bit.md.

## Software support
- MakeCode editor https://makecode.microbit.org with the `rekabit` extension [UM] (https://github.com/CytronTechnologies/pxt-rekabit [GH, via reka-bit.md]).
- Sample code: https://link.cytron.io/auto-plant-wateringproject-code ; more project ideas: https://link.cytron.io/apw-projects [UM] (not fetched).
- Blocks used per lesson [UM]: L1 show string/icon, on start vs forever; L2 analog read P2 on button A; L3 variable "Soil Moisture", comparison, REKA:BIT RGB LED colour, show icon; L4 REKA:BIT run motor M2 + pause 5 s; L5 REKA:BIT servo S1 angle; AA1 LED-matrix bar graph from optimum/threshold values; AA2 Music blocks.
- IoT version: Cytron tutorial "RBT Automatic Plant Watering IoT Project Using Blynk IoT" https://my.cytron.io/tutorial/rbt-automatic-plant-watering-iot-project-using-blynk-iot [PP] (not readable here). The Grove WiFi 8266 MakeCode extension (`pxt-esp8266`) has Blynk read/write blocks and a default init of Tx P16 / Rx P15 at 115200 baud [GH, via grove-wifi-8266.md] — whether the tutorial uses those pins is unverified.
- Related Cytron tutorials found by search (not read): "RBT Auto Plant Watering Kit Project - Not Enough Water!", "RBT Automatic Plant Watering Project - Automatic Pet Feeder", "Auto Plant Water IoT Project - AI Monitoring System" (my.cytron.io/tutorial/…).

## Compatibility and accessories
- micro:bit V1 and V2 (V1 needs a Grove buzzer for sound; the kit option ships V2) [UM][PP].
- Optional: Grove Buzzer (https://cytron.io/p-grove-buzzer) for V1 [UM]; Grove WiFi 8266 for IoT (included in the IoT option) [PP].
- Not included: plant, pot, water container and the IoT step-by-step guide [UM][PP]. Popsicle sticks, cable ties and tape are included for mounting the servo and pipe [UM][PP].
- The same sensor/pump/servo combination is Project 3 of the REKA:BIT RBT Project Kit (rekabit-rbt-project-kit.md).

## Common mistakes / troubleshooting
- **Pump never runs / runs constantly:** comparison direction wrong (reading rises when dry) or threshold not recalculated for the plant [UM].
- **Pump runs backwards / no flow:** check red → M2A, black → M2B and that the exposed lead, not the insulation, is clamped [UM].
- **Servo not moving:** extension cable colour order (Orange–White, Red–Red, Brown–Black) or port S1 [UM].
- **Readings jump:** probe not inserted to the white line; sensor or board got wet [UM].
- **No sound on V1:** add a Grove buzzer on P0:P1 [UM].
- **Download fails:** use the latest Edge/Chrome and micro:bit firmware [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Kit list quantities | [PP] gives counts (2× popsicle stick, 3× cable ties, 2× double-sided tape, 4× AA) | [UM] "What's in the kit?" gives no quantities | Use [PP] counts; no numeric disagreement |
| Lesson-guide naming | [PP] "Lesson Guide" | [UM] cover "Auto Plant Watering Kit for micro:bit", file name "Booklet" | Same document |
| Sensor-to-pin label | [UM] "port P2:P12" / "pin P2" | REKA:BIT datasheet text does not map Grove ports to pins (reka-bit.md, [GH]-derived P2/P12 pair) | Consistent; booklet is the authority for this kit |
| IoT guide | [PP] IoT version "follows a Cytron tutorial" | [UM] no IoT content | Booklet is the standard kit's guide only; say so in content |

No numeric disagreement was found between [PP] and [UM].

## Needs verification
- **IoT tutorial content** (wiring of the Grove WiFi 8266 to REKA:BIT — which Grove port / which Tx-Rx pins, which Blynk datastreams, whether the `pxt-esp8266` extension is used): the tutorial page could not be fetched; author and date unknown.
- **Kit code for the no-micro:bit option** — `KIT-RBT-APW-NB` appears only in a Cytron CDN video file name (`KIT-RBT-APW-NB-content.mp4`) linked from a reseller page [3P]; codes for the IoT variants not found.
- **Booklet version/date of the current print** — "v1" is from the file name; the PDF prints only "April 2022". Check whether a newer edition exists behind link.cytron.io/apw-book-english (short link not fetched here).
- **Malay / Chinese / Thai editions** not read.
- **Battery voltage**: booklet gives no figure; pump (3–5 V) and servo (3–6 V) ratings are from [PP] — confirm that 4× fresh alkaline AA on REKA:BIT's unregulated motor/servo rail is within the pump's 5 V rating.
- **Sample-code and project-ideas short links** (link.cytron.io/auto-plant-wateringproject-code, link.cytron.io/apw-projects) — targets not read.
- **RGB LED blocks** in Lesson 3 (which REKA:BIT block and pin) — booklet shows images only.
- Kit box dimensions/weight — not stated.

## Sources
- [UM] Auto Plant Watering Kit for micro:bit lesson guide, English, April 2022 (file v1): https://static.cytron.io/download/KIT-RBT-APW/RBT_APW_KIT_Booklet_English_v1.pdf
- [UM] Short links listed on the product page (not fetched): https://link.cytron.io/apw-book-english · https://link.cytron.io/apw-book-malay · https://link.cytron.io/apw-book-chinese · https://link.cytron.io/apw-book-thai
- [PP] Product page (coordinator read, 2026-10-19): https://my.cytron.io/p-auto-plant-watering-kit-for-microbit
- [PP] IoT tutorial (not fetched): https://my.cytron.io/tutorial/rbt-automatic-plant-watering-iot-project-using-blynk-iot
- [PP: CDN path] Kit media on Cytron CDN: https://static.cytron.io/image/catalog/products/KIT-RBT-APW/RBT-APW-Flipbook-2.mp4 · https://static.cytron.io/image/catalog/products/KIT-RBT-APW/KIT-RBT-APW-NB-content.mp4 (packing-list video)
- [GH] REKA:BIT extension: https://github.com/CytronTechnologies/pxt-rekabit (via reka-bit.md) · Grove WiFi 8266 extension: https://github.com/CytronTechnologies/pxt-esp8266 (via grove-wifi-8266.md)
- [3P] Pakronics (packing list cross-check, matches [PP]): https://www.pakronics.com.au/products/auto-plant-watering-kit-for-micro-bit-without-micro-bit-pakr-a0567
- Related KB files: reka-bit.md, maker-soil-moisture.md, grove-wifi-8266.md, rekabit-rbt-project-kit.md
