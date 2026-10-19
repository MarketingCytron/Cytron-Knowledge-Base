# REKA:BIT RBT Project Kit — Verified Reference

| | |
|---|---|
| Product code | `V-KIT-REKABIT-RBT` (product page, variant parent) [PP]. Kit codes `KIT-REKABIT-RBT` (with micro:bit V2) / `KIT-REKABIT-RBT-NB` (without micro:bit) ; the Cytron CDN image path also uses `KIT-REKABIT-RBT` [PP: resource hub] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | No datasheet exists for the kit. Guide book: **"Buku Panduan — Kit Projek RBT REKA:BIT" (REKA:BIT RBT Project Kit Quick Start Guide), Malay edition, file `REKABIT-RBT-Project-Kit-Quick-Start-Guide-BM-v1.0.pdf`** (static.cytron.io), credited "Adam & Anna", "Nota daripada rero EDUteam" [UM]. "v1.0" comes from the file name only; no date is printed in the readable text. The English edition (link.cytron.io/rekabit-project-book-english) could not be fetched here — see Needs verification |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: [UM] = the Malay guide book above, read through a summarising fetch; its wiring diagrams and the REKA:BIT board diagram (parts labelled A–L) are images and could not be read, so **no per-component Grove port label comes from the guide**. [PP] = my.cytron.io product page as read by the coordinator on 2026-10-19, plus the public **REKA:BIT RBT Project Kit Resource Hub** (rekabit-rbt-hub.cytron.io, Cytron Google Site) tagged [PP: resource hub]. [GH] = `pxt-rekabit-rbt-project-kit` v1.1.4. [3P] = Petrosains online shop (kit list cross-check only). The REKA:BIT board itself is documented in **reka-bit.md**; the Maker Soil Moisture Sensor in **maker-soil-moisture.md** — this file does not re-document them.

## What it is
- A micro:bit project kit for the Malaysian primary-school RBT syllabus: "For RBT Y5 and Y6 (Reka Bentuk dan Teknologi Tahun 5 & 6)"; page tags: Age 10+, Platform micro:bit, Syllabus RBT Y5&Y6 [PP].
- Built on the **REKA:BIT** expansion board (see reka-bit.md) plus 7 component types: micro servo, RGB stick, 2× Big LED (10 mm LED module), Maker Soil Moisture Sensor, submersible water pump, ultrasonic sensor, 2× DC motor with wheels [UM][PP].
- Comes with a hardcopy Quick Start Guide ("5 projects + 7 components quick start guide book (English Version)") and online resources with example code and a step-by-step building video per project [PP].
- Two purchase options: with micro:bit V2 included / without micro:bit [PP].
- Programmed in Microsoft MakeCode with the "REKA:BIT RBT Project Kit" extension; JavaScript/Python mode available [PP]. The extension README states its aim: "to lower the learning curve for beginners who wants to build STEAM (and RBT) projects with micro:bit" [GH].

## Specifications
No spec table exists for the kit. Kit-level items only; board limits are in reka-bit.md.

| Item | Value | Src |
|---|---|---|
| Controller board | REKA:BIT (with or without micro:bit) | [UM][PP] |
| micro:bit | BBC micro:bit V2 in the "with micro:bit" option; none in the "without" option | [PP] |
| Guide book | Quick Start Guide: 5 projects + 7 component guides; English, Malay, Chinese softcopies (link.cytron.io/rekabit-project-book-english / -malay / -chinese) | [PP]; Spanish also listed on the hub [PP: resource hub] |
| Kit contents (guide list) | REKA:BIT (with/without micro:bit), micro servo motor, RGB board, soil moisture sensor, Big LED module ×2, water pump, ultrasonic sensor, USB cable (power & data), Grove cable ×4, AA battery ×4, battery holder, ball caster, DC motor with wheels ×2, mini screwdriver, adhesive tape ×5 | [UM] |
| Kit contents (product page, with micro:bit) | 1× micro:bit v2, 1× REKA:BIT expansion board, 1× USB power and data cable, 1× quick start guide book, 1× Maker Soil Moisture Sensor, 1× RGB LED Stick, 1× Ultrasonic sensor, 2× 10mm LED module, 2× DC motor with wheel, 1× Micro servo motor, 1× Submersible Water Pump, 4× Grove to female header cable, 1× 4xAA battery holder with DC plug, 4× AA battery, 1× Castor, 1× Mini screwdriver, double-sided tapes. "Without micro:bit" = same minus the micro:bit | [PP] |
| RGB stick | 8 LEDs, labelled 0–7; brightness 0–255 | [UM][GH `REKABIT_RGBSTICK_LENGTH = 8`] |
| Servo | channels S1–S4; angle 0°–180°; a block disables an unused servo to stop jitter | [UM] |
| Water pump | on motor channel M1 or M2; speed 0–255 ("controls the pumping rate, i.e. flow rate"); "can work in either direction" | [UM] |
| DC motor | on channel M1 or M2; speed is a relative value 0–255 | [UM] |
| Ultrasonic block range | 1–300 cm; returns 300 when over range or no echo | [GH `REKABIT_MAX_DISTANCE = 300`] |
| Soil moisture block range | 0–1023 (micro:bit analog read) | [GH] |
| Battery | AA ×4 in a battery holder with DC plug | [UM][PP] |
| Warranty | 12 months (manufacturing defects; wear/tear and misuse excluded; repair/testing 7 working days after receipt) | [PP][PP: resource hub helpdesk] |
| Price | RM219.00–RM295.00 (Cytron product page, read 2026-10-19) | [PP] |

## Interfaces, terminals and pin mapping
The guide tells the reader to "set the pin number to match the port on REKA:BIT you connected the module to" for the RGB board, Big LED, soil moisture sensor and ultrasonic sensor [UM] — i.e. the port is a choice, not fixed. What the sources state in text:

| Component | Connection | Src |
|---|---|---|
| RGB stick | Any REKA:BIT IO (Grove) port, black Grove cable; pin set in the `set RGB Stick at pin` block (choices P0, P1, P2, P13, P15); README example uses **P0** | [UM][GH] |
| Big LED ×2 | Any IO port; pin choices P0, P1, P2, P13, P15; README example uses **P13** | [UM][GH] |
| Soil moisture sensor | Grove cable (black/red/white wires) to an IO port; analog pin choices P0, P1, P2; README example uses **P2**; hub Project 3 says **"P2:P12"** | [UM][GH][PP: resource hub] |
| Ultrasonic sensor | Any IO port; Trig/Echo pairs offered: P0/P1, P1/P9, **P2/P12** (README example), P13/P14, P15/P16 | [UM][GH] |
| Servo | REKA:BIT servo terminal S1–S4; wire labels s (Isyarat/signal), +, − ; servo lead colours listed as white and orange (guide does not say which is which) | [UM] |
| Water pump | MOTOR terminal M1 or M2; hub Project 3: "motor terminal 2" | [UM][PP: resource hub] |
| DC motors (Project 5 car) | left wheel → **MOTOR 1**, right wheel → **MOTOR 2** | [PP: resource hub] |
| Battery holder | REKA:BIT power jack ("battery jack") | [PP: resource hub] |

Grove signal pairs (yellow/white pin) on REKA:BIT — P0/P1, P1/P9, P2/P12, P13/P14, P15/P16 — are derived from this extension's enums [GH]; confirm against the REKA:BIT datasheet Figure 1 (see reka-bit.md).

## Rules and gotchas (for code, wiring and tutorials)
- **The extension is `pxt-rekabit-rbt-project-kit`** (search "rekabit rbt project" in MakeCode Extensions); it depends on `pxt-rekabit`, so the REKA:BIT motor/servo blocks load with it [GH]. Block categories added: RGB Stick, Big LED, Soil Moisture, Ultrasonic [GH].
- **RGB Stick and Ultrasonic need an init block at the start of every program**: `set RGB Stick at pin` and `set Ultrasonic pins to Trig:Px | Echo:Py` [GH].
- **Pin choice must match the physical port** — the guide repeats this for every Grove module [UM]. The big-LED/RGB pin list is P0, P1, P2, P13, P15 (the yellow pin of each Grove port); the soil-moisture pin list is P0, P1, P2 only (the analog-capable ports) [GH].
- **Soil moisture reading rises as soil dries** (sensor: higher voltage = less moisture [DS in maker-soil-moisture.md]). README example: `< 550` → moist, `> 550` → dry; 550 is an example, not a calibrated value [GH]. The guide uses a user-chosen "reference value" (threshold) [UM].
- **Ultrasonic distance block** returns 1–300 cm and 300 when nothing is detected; a background reader refreshes every 200 ms; a different timing constant is applied on micro:bit V1 vs V2 [GH].
- **Servo jitter:** disable a servo that is not in use ("this prevents the servo from jittering") [UM]. Servo range 0°–180° [UM].
- **Pump and motor blocks carry a ⚠ warning symbol** in the guide, but the warning text is not readable in the extracted text [UM]. Speed 0–255 [UM].
- **Reset:** "slide the power switch to OFF, then to ON to restart" [UM]. Flashing: use the latest Edge or Chrome; if no WebUSB pop-up appears, drag the downloaded `microbit-xxx.hex` to the MICROBIT drive; success = "Hello" scrolls then a heart icon [UM].
- **micro:bit V1:** the product page says "Get a Grove Buzzer module if you are going to use REKA:BIT with micro:bit V1 board (No built-in piezo buzzer)" [PP]; the extension states REKA:BIT works with V1 & V2 [GH]. The guide only mentions "micro:bit V2" [UM].
- **Project 3 has two code versions** on the hub (3a and 3b) [PP: resource hub].

## Power and electrical limits
- Power sources in the kit: USB cable (power & data) and 4× AA battery holder with DC plug [UM][PP]. The guide does not say when to use which [UM].
- All voltage/current limits are the REKA:BIT board's (3.6–6 V input, 1 A/1.5 A motor, 300 mA Grove 3V3, 7 V over-voltage cut-off) — see reka-bit.md. No kit-specific electrical figure is stated by any source.

## Software support
- MakeCode extension: https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit — `pxt.json` name `pxt-rekabit-rbt-project-kit`, version 1.1.4, MIT, target microbit; files `rgb_stick.ts`, `big_led.ts`, `soil_moisture.ts`, `ultrasonic.ts`; dependency `rekabit: github:cytrontechnologies/pxt-rekabit` [GH]. MakeCode approved-content listing: https://makecode.microbit.org/pkg/cytrontechnologies/pxt-rekabit-rbt-project-kit.
- Blocks [GH]: RGB Stick — set at pin, turn off, set brightness (0–255), show rainbow, show color, set pixel color, shift pixels, rotate pixels, colour/RGB helpers; Big LED — set Big LED at pin to on/off, toggle Big LED; Soil Moisture — soil moisture level at pin (0–1023), compare `>`/`<` threshold; Ultrasonic — set pins (Trig/Echo pair), distance (cm), compare distance.
- Sample code per project (MakeCode share links) [PP: resource hub]: P1 `_UbJL1EP2390C`; P2 `_9AW0A4HV7JjM`; P3a `_Jho590c1iczh`, P3b `_bW2bkfe9HFsh`; P4 `_PfiUCLMmR18Y`; P5 `_MVjd7e63EXJA` (prefix https://makecode.microbit.org/).
- MakeCode Offline App supported; "new extensions may need an internet connection to compile" [PP: resource hub helpdesk].
- Text coding: switch to JavaScript or Python inside MakeCode [PP].

## Compatibility and accessories
- Project list and components (guide + hub) [UM][PP: resource hub]:
  1. **Boom Barrier Gate** (Pagar Keselamatan) — servo, RGB stick, battery holder, cardboard + printed A4 template.
  2. **Interactive Robot** (Robot Interaktif) — 2× Big LED, servo, battery holder, cardboard template.
  3. **Auto Plant Watering Robot** (guide prints "Robot Penjaga Tanaman"; see Conflicts) — soil moisture sensor on P2:P12, water pump on motor terminal 2, battery holder.
  4. **Coin-Eating Robot** (Robot Pemakan Syiling) — servo, ultrasonic sensor, battery holder; steel hanger wire (20 cm) and popsicle sticks.
  5. **Mobile Robot Car** (Robot Mudah Alih) — 2× DC motor + wheels (left M1, right M2), castor, ultrasonic, 2× LED headlights, RGB stick; chassis = a plastic food container.
- Resource hub downloads: printable A4 project templates (Google Drive), project folders, REKA:BIT datasheet (Google Doc), MakeCode Offline App link [PP: resource hub].
- Support: Telegram group t.me/microbit_malaysia; warranty claims via my.cytron.io/support with the warranty form [PP: resource hub helpdesk].
- Not included: micro:bit (in the "without" option) [PP]; cardboard, hot glue, Blu Tack, plastic container, steel hanger used in the projects are household items [PP: resource hub].
- Related kit: Auto Plant Watering Kit for micro:bit (auto-plant-watering-kit.md) uses the same REKA:BIT + Maker Soil Moisture + pump + servo combination with its own lesson guide.

## Common mistakes / troubleshooting
- **Module does nothing:** the pin in the block does not match the Grove port used [UM]; RGB/ultrasonic init block missing [GH].
- **Ultrasonic always reads 300:** no echo / out of range, or Trig/Echo pair wrong [GH].
- **Soil reading "backwards":** value rises when dry, falls in water [UM of APW kit][GH].
- **Servo twitching when idle:** use the disable-servo block [UM].
- **No "Hello" + heart after download:** press reset on the back of the micro:bit or power-cycle; check browser (latest Edge/Chrome) and WebUSB troubleshooting page [UM].
- **No sound on micro:bit V1:** add a Grove buzzer [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Project 3 name | [PP: resource hub] "Auto Plant Watering Robot" (code 3a/3b) | [UM] heading reads "Robot Penjaga Tanaman" with overlapping text "Robot Penyiram Pokok Auto"; a line "Projek 3: Robot Pengesan Paras Air" (water-level detecting robot) also appears | Text-extraction overlap in the PDF; use "Auto Plant Watering Robot (Robot Penyiram Pokok Auto)" and verify against the printed book |
| Number of components | [PP] "5 projects + 7 components" | [PP: resource hub] lists 8 "Explore Components" (REKA:BIT + 7) | Same count: 7 component types plus the REKA:BIT board |
| Guide languages | [PP] English, Malay, Chinese | [PP: resource hub] adds Spanish | Hub is newer; say "English, Malay, Chinese (and Spanish on the hub)" |
| micro:bit V1 support | [GH] "REKA:BIT works with micro:bit V1 & V2"; [PP] V1 needs a Grove buzzer | [UM] mentions only micro:bit V2 | Works with V1 (no speaker); the kit ships with V2 |
| "RGB LED Stick" vs "RGB board" | [PP] "RGB LED Stick"; [GH] "RGB Stick" | [UM] "Papan RGB" (RGB board) | Same part (8-LED NeoPixel stick) |

## Needs verification
- **English guide book** (link.cytron.io/rekabit-project-book-english): fetch blocked here (permission not granted); the Malay v1.0 PDF was read instead. Confirm the English title, version/date, and whether a v1.1+ exists.
- **Per-component Grove port labels** in the guide's wiring diagrams (which port each module is shown on in each project) — images not readable. Only Project 3 (P2:P12, motor 2) and Project 5 (M1 left, M2 right) are stated in hub text.
- **Which servo port** (S1–S4) Projects 1, 2 and 4 use — not stated in text.
- **⚠ warning text** beside the pump and DC-motor blocks in the guide.
- **Ultrasonic module model** shipped (code comment names RCWL-9610 timing [GH]); **Big LED** module spec (10 mm LED module, voltage) ; **pump** voltage (the sibling APW kit lists "DC 3V-5V" [PP]); **servo** model (APW kit: analog 9g 3–6 V [PP]) — none stated for this kit.
- **Dimensions/weight** of the kit box: not stated anywhere.
- **MakeCode share links** could not be opened here; pin usage per project is taken from the README examples and hub text, not the actual project code.
- Whether the guide's "Hello" chapter requires USB power only or the battery pack.

## Sources
- [UM] REKA:BIT RBT Project Kit Quick Start Guide, Malay, v1.0 (file name): https://static.cytron.io/download/REKABIT-RBT-Project-Kit/REKABIT-RBT-Project-Kit-Quick-Start-Guide-BM-v1.0.pdf (read via summarising fetch; diagrams unreadable)
- [UM] English / Malay / Chinese / Spanish short links (not fetched): https://link.cytron.io/rekabit-project-book-english · https://link.cytron.io/rekabit-project-book-malay · https://link.cytron.io/rekabit-project-book-chinese · https://link.cytron.io/rekabit-project-book-spanish
- [PP] Product page (coordinator read, 2026-10-19): https://my.cytron.io/p-rekabit-rbt-project-kits
- [PP: resource hub] https://rekabit-rbt-hub.cytron.io/ — pages: /download, /helpdesk, /chapter-resources/rekabit-project-1 … -5, /explore-components (component pages are images only)
- [PP: resource hub] Printable A4 template (Project 1): https://drive.google.com/file/d/1lwTzCC9j0Wd9DKnT5X_91dygzJ2q7xXz/view · Project folders: https://drive.google.com/drive/folders/1jGbZVvKiiMLRpCJtgBJF-tlE6xInuxhu (Boom Barrier Gate) · (Cytron document — link not public) (Interactive Robot) · (Cytron document — link not public) (Auto Plant Watering / Coin-Eating)
- [GH] https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit — README.md, pxt.json (v1.1.4), rgb_stick.ts, big_led.ts, soil_moisture.ts, ultrasonic.ts (raw.githubusercontent.com)
- [GH] MakeCode listing: https://makecode.microbit.org/pkg/cytrontechnologies/pxt-rekabit-rbt-project-kit
- [3P] Petrosains shop (kit list cross-check, matches [PP]): https://shop.petrosains.com.my/products/reka-bit-rbt-project-kit
- Related KB files: reka-bit.md, maker-soil-moisture.md, auto-plant-watering-kit.md, zoom-bit.md
