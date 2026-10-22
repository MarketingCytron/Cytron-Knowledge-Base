# Cytron Product Knowledge Base

Verified product facts for **Cytron-brand products**, written for AI agents (tutorial, article and script writers) and for the people who check their output. Every fact is tagged with its source; anything a source doesn't state is marked as not stated rather than guessed.

**Start here:** read this index, then load only the product files a task needs.

**Scope: Cytron-brand products, plus Teltonika industrial networking and Milesight LoRaWAN/IoT products distributed by Cytron (added 21 Oct 2026).** Other third-party boards and modules that Cytron resells are not covered here.

This is the public edition. Internal working notes (internal document links, pricing sources, unreleased products and the open-issues log) are kept privately by the Cytron marketing team.

## Rules for any agent using this KB

1. **Only state a spec that is in a product file.** If it isn't there, say it's unconfirmed — never fill the gap from memory or a reseller page.
3. **Read the *Conflicts* and *Needs verification* sections** before writing about a product. Anything listed under *Needs verification* must not appear as fact in published content.
4. **Pin rules are hard rules.** Code and wiring must follow each file's "Pin rules and gotchas".
6. **Dated facts** (price, stock, store list) must be re-checked on the live page before going public.
7. **Source rule by product type (decided 19 Oct 2026):**
   - **Boards, shields, sensors, motor drivers, controllers:** the Cytron datasheet is the main source (rule 2).
   - **Education kits** (e.g. EDU:BIT, Maker UNO Learning Box): the Cytron **guide book** is the main source. Students and teachers follow the book, so a datasheet is **not required** and its absence does not lower confidence. Electrical limits the book does not give stay "not stated"; for power, say "use the supplied cable / power source".
   - **Mechanical hardware with no electronics** (e.g. Robo Base, Robo Base Mini, brackets, chassis plates, wheels): the Cytron **guide tutorial** and the product page (including its spec images) are the main source. A datasheet is not required.
   - **Robot and project kits** (e.g. SUMO:BIT Robot Kit, Robot Battle, SOCCER:BIT, Ikedo kits): the **board inside follows its own datasheet** — link to the board's KB file, never re-document it. The **kit accessories, assembly and lessons** use the Cytron **guide book or guide tutorial** as the main source; no accessory datasheet is required.
   - **Workshops and services** (e.g. Jetson Orin Nano workshop, AI Agent workshop, JetPack flash service): the **product page plus the Cytron course outline or timetable** is the main source. No datasheet is required.
   - **What ships in the box** (items, quantities, screw sizes): the **product page packing list comes first**, the guide tutorial second (decided 19 Oct 2026). Where a tutorial names a different part, quote the packing list and note the tutorial difference under *Conflicts*.

## How the KB is arranged (two layers)

| Layer | Folder | Format | Use it for |
|---|---|---|---|
| **1. Product fact sheets** | `fact-sheets/` | Cytron Content Hub "Product fact sheets" form: 13 fixed headings, source-only facts, `[NOT STATED]` where the source is silent | Pasting into the Content Hub; marketing, scripts and articles; the first thing any agent reads |
| **2. Detailed references** | this folder (`<product>.md`) | Source-tagged reference with pin maps, conflicts and *Needs verification* | Writing code, wiring and tutorials; checking where a fact came from |

Cytron tutorials are an add-on to the product facts: 64 product files have a *Cytron tutorials* section listing only the my.cytron.io tutorials that use that product (series shown once with their part count), and each of those fact sheets lists up to 5 under *Use cases*. Products with no matching tutorial have no section. Tutorials never override [DS] or [UM] specs.

`fact-sheets/ALL-fact-sheets.md` holds every sheet in one file, ready to paste. A fact sheet must never say more than its detailed reference. When a reference changes, update the matching fact sheet in the same edit.

Fact sheet rules (from the Content Hub form): use only what the source states; keep numbers, units and names exactly; `[NOT STATED]` for anything missing; keep every heading in order; keep every stated limitation; marketing language only under *Positioning*; when product page and datasheet disagree give both with their source; price only if a source states one; each alias belongs to one product only.

## Products

### Maker ESP32 family (ESP32 ecosystem)

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker ESP32 | [`maker-esp32.md`](maker-esp32.md) | `MAKER-ESP32` | ESP32 (WROOM-32E-N8) | Active, launched Sep 2026 | **High** |
| Robo ESP32 | [`robo-esp32.md`](robo-esp32.md) | `ROBO-ESP32` | None onboard — hosts a 30-pin NodeMCU ESP32 / Maker ESP32 | Active (Datasheet Rev 1.1, Feb 2026) | **Medium-high** |
| Maker Feather AIoT S3 | [`maker-feather-aiot-s3.md`](maker-feather-aiot-s3.md) | `MAKER-FEATHER-AIOT-S3` (+`-H`) | ESP32-S3 (WROOM-1-N8R8) | Active | **Medium-high** |

### Arduino-compatible boards

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker UNO | [`maker-uno.md`](maker-uno.md) | `MAKER-UNO` | ATmega328P + CH340G | User's Manual Rev 1.0, Dec 2017 (no datasheet) | **Medium-high** |
| Maker UNO Plus | [`maker-uno-plus.md`](maker-uno-plus.md) | `MAKER-UNO-PLUS` | ATmega328P + **FT231X** (not CH340) | User's Manual Rev 1.0, Oct 2018 (no datasheet) | **Medium-high** |
| Maker UNO X | [`maker-uno-x.md`](maker-uno-x.md) | `MAKER-UNO-X` | ATmega328P + CH340-family USB chip (page: "CH9340") | Guide book v1.5, Feb 2023 + schematic REV 1.0.0 & board files (GitHub) + product page (no datasheet) | **Medium-high** |
| Maker Nano | [`maker-nano.md`](maker-nano.md) | `MAKER-NANO` | ATmega328P + **CH340C** | Datasheet Rev 1.0, Jun 2020 + product-page comparison table, pinout and dimension images | **Medium-high** |
| Cytron UNO | [`cytron-uno.md`](cytron-uno.md) | `CT-UNO` | ATmega328P + **FT231X** | User's Manual V1.0, Nov 2014 (no datasheet) | **Medium-high** |
| Cytron UNO Special Edition | [`cytron-uno-se.md`](cytron-uno-se.md) | `CT-UNO-SE` | ATmega328P + **FT231X** (same as CT-UNO) | Product page (CT-UNO + side connectors) + CT-UNO manual | **Medium-high** |
| Maker Uno RP2040 | [`maker-uno-rp2040.md`](maker-uno-rp2040.md) | `MAKER-UNO-RP2040` | RP2040, 2 MB flash | Datasheet Rev 1.0, Feb 2024 | **Medium-high** |
| Maker Nano RP2040 | [`maker-nano-rp2040.md`](maker-nano-rp2040.md) | `MAKER-NANO-RP2040` | RP2040 | Datasheet Rev 1.1, Jul 2024 | **Medium-high** |
| Robo Uno Shield | [`robo-uno-shield.md`](robo-uno-shield.md) | `SHIELD-ROBO-UNO` | None — shield for UNO-form-factor boards | Datasheet Rev 1.0, Feb 2025 + Cytron GitHub sketches (Getting Started + Demo_Code; no schematic in repo) | **Medium** |

Arduino-board notes for every agent:
- **Maker UNO has no DC jack and no VIN** — USB Micro-B 4.8–5.2 V only. Select "Arduino Uno" in the IDE; CH340 driver needed.
- **Maker Uno RP2040 is 3.3 V logic** — only 3.3 V-compatible UNO shields; power from USB-C or 1-cell LiPo (3.6–6 V); code uses GP numbers, not UNO D-numbers.
- **Robo Uno Shield:** 3.6–6 V single-cell input only; cannot be powered from the Arduino VIN pin; its micro-USB charges/powers the shield only (no code upload). Follow Cytron's code for motor pins (`CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);`) until the design team resolves the datasheet conflict. Grove 4 and the Maker Port share A4/A5; buttons D2/D3 are the Grove 6 pins.
- **USB-serial chips differ:** Maker UNO = CH340; **Maker UNO Plus and Cytron UNO = FTDI FT231X** (use the FTDI driver, not Maker UNO's CH340 steps). **Maker Nano = CH340C** (CH34X driver; Cytron comparison table).
- **Maker UNO Plus is USB-only** (4.8–5.2 V; no DC jack, no Vin, no 5 V regulator); button D2 needs `INPUT_PULLUP`; buzzer D8 with mute switch; LEDs on pins 2–13.
- **Maker UNO X:** USB Micro-B only (no DC jack; the VIN pin is an output only, fed from 5 V through a Schottky diode — schematic REV 1.0.0); USB chip CH340C, 3.3 V from an RT9013 (500 mA part); the built-in LEDs and buzzer (D8) work only with the **Debug** switch on — switch Debug off to use D8 for something else; button D2 needs `INPUT_PULLUP`; USB driver does not support Windows 7.
- **Maker Nano power:** Vin 7.0–30.0 V, but the 5V pin gives only **100 mA** and 3V3 only **50 mA** (including the board's own use) — never copy Maker UNO's 500 mA. D2–D13 LEDs light whenever the pin is high (cut a trace to disable). A6/A7 are analog-only. IDE board: "Arduino Nano".
- **Cytron UNO:** DC jack 7–15 V recommended (6–20 V absolute); 5 V regulator 1 A max only stated "with Vin at 12V"; 3.3 V 500 mA; select "Arduino Uno"; one user LED (D13), no button or buzzer. **Cytron UNO Special Edition (CT-UNO-SE)** is the same board with special side connectors for stacking on top of or under a shield (product page, 19 Oct 2026).

### Arduino shields (non-motor)

| Product | File | Code | Function | Primary source | Confidence |
|---|---|---|---|---|---|
| Cytron PS2 Shield | [`shield-ps2.md`](shield-ps2.md) | `SHIELD-PS2` | PS2 controller interface over UART | User's Manual V1.0, Sep 2013 (no datasheet) | **Medium-high** |
| Cytron ESP8266 WiFi Shield | [`shield-esp-wifi.md`](shield-esp-wifi.md) | `SHIELD-ESP-WIFI` (Rev 2.0) | ESP-WROOM-02 Wi-Fi over UART + microSD | User's Manual Rev2.0 V2.1, Aug 2021 (no datasheet) | **Medium-high** |
| LiPo Power Shield | [`shield-lipo.md`](shield-lipo.md) | `SHIELD-LIPO` | 1-cell LiPo power + charger shield | User's Manual V1.0, Jan 2016 (Cytron Google Doc, read in full incl. figures 21 Oct 2026; no datasheet) + product page | **Medium** |
| 8 Channels RC Servo Controller Shield | [`shield-servo.md`](shield-servo.md) | `SHIELD-SERVO` | 8-ch servo controller shield, 7–25 V in, 5 V 4 A/5 A peak out | User's Manual V1.1, Apr 2018 (no datasheet) | **Medium-high** |
| Cytron Screw Terminal Shield | [`shield-screw2.md`](shield-screw2.md) | `SHIELD-SCREW2` | Screw-terminal + proto-area shield, 3.5 mm pitch | Getting Started Guide V1.0, Jan 2015 + product photos | **Medium** |
| Cytron Prototyping Shield | [`shield-proto2.md`](shield-proto2.md) | `SHIELD-PROTO2` | Proto shield, UNO R3 / Leonardo, stackable headers, reset button, 1 LED | Schematic + artwork prints Rev 1.0.1 (read 20 Oct 2026) + product page | **Medium-high** |

Shield notes for every agent:
- **PS2 Shield:** button reads are 0 = pressed, 1 = released; `begin()` baud must match the jumper and the shield must be reset after moving it; A1 is the shield reset line; default D2 RX / D3 TX; on Mega only D10 can be SoftwareSerial RX.
- **ESP8266 WiFi Shield:** ships at 9600 8N1 (the manual's "9600 kbps" is a typo); after reflashing it runs 115200 — set it back with `AT+UART_DEF=9600,8,1,0,0`. Firmware ESP-AT V2.2.0, library "Cytron ESPWiFi Shield" v3.0.2. D4 is reserved for microSD CS; UART on D10–D13 kills SPI/microSD; ESP GPIO breakout is 3.3 V only.
- **LiPo Power Shield:** charging via the Arduino's USB only works with the shield switch OFF; ICSP is not passed through; bridge the VBATT solder jumper to read battery voltage.
- **Servo Shield / SC08A:** servos are deactivated at power-up — send the activate command first. Speed byte 0 = fastest. Resolution 0.25 µs, position 0–8000 = 0.5–2.5 ms; the shield library's `angle()` maps 0–180° to 156–7260. Servo shield: jumper K (servos from Arduino 5 V) and VM input are mutually exclusive. SC08A has **no regulator** — servo supply goes straight to the servos.
- **Screw Terminal Shield:** 3.5 mm pitch; wire by the silkscreen label, not terminal position; no ISP pads, terminal count or ratings are stated — don't quote any.
- **Prototyping Shield:** the page says the ISP **pads** are prepared — don't claim an ISP header is fitted. Compatibility stated for UNO R3 and Leonardo only.

### Arduino kits and books

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker UNO Edu Kit | [`maker-uno-edu-kit.md`](maker-uno-edu-kit.md) | `V-KIT-MUNO-EDU` | Maker UNO + components kit for classes (School Package 10+1) | Getting Started Module PDF + Teacher Guidebook (no version/date) | **Medium-high** |
| Maker UNO Learning Box | [`maker-uno-learning-box.md`](maker-uno-learning-box.md) | `KIT-MAKER-UNO-START` | Maker UNO + parts for 17 projects / 7 lessons | Arduino Learning Guide for Beginner Using Maker UNO, Ver 1.3, Dec 2018 (read 21 Oct 2026) + product page | **Medium-high** |
| PikaBot | [`pikabot.md`](pikabot.md) | `V-KIT-PIKABOT` | Maker UNO + Maker Drive smart-car kit, Arduino IDE or mBlock booklet | PikaBot Booklet, Arduino IDE edition (108 pages, read 21 Oct 2026 by OCR + page images) + Cytron PikaBot Resources doc with code | **Medium-high** |
| Maker Uno X Learning Guide (book) | [`maker-uno-x-learning-guide.md`](maker-uno-x-learning-guide.md) | `BOK-MUNOX` | Printed 17-project guide for the Maker UNO X Learning Box | Arduino Learning Guide for Beginners Using Maker UNO X, v1.5 Feb 2023 (104 pages, read in full 21 Oct 2026) | **Medium-high** |

Arduino-kit notes for every agent:
- **PikaBot pins (booklet + code):** left motor D11/D10, right D9/D3 (`PWM_PWM`), ultrasonic TRIG D5 / ECHO D4, IR left A0 / right A1 (LOW = white, HIGH = black), start push button D2 to GND, buzzer D8. Sensors are generic IR modules and HC-SR04, not Maker Line / Maker Object. Maker UNO has no DC jack/Vin — the battery feeds Maker Drive through the rocker switch, and Maker Drive 5VO powers the Maker UNO via the breadboard 5V rail. Switch off before uploading.
- **Edu Kit vs Learning Box contents differ** (Learning Box: IR sensor, SR04, 1N4007, 2× 2N2222, 10/10/10 resistors). The Edu Kit packing list is not in any Cytron text — don't publish a list.
- **Maker UNO X guide wiring is for the X board** (it has a Debug switch the plain Maker UNO lacks); don't apply its pin notes to the Maker UNO Learning Box without checking.

### Raspberry Pi Pico, RP2040 and RP2350 boards (Robo, Maker Pi, MOTION, EDU PICO, Maker Nano RP2040 bundles)

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Robo Pico | [`robo-pico.md`](robo-pico.md) | `ROBO-PICO` | None onboard — hosts a Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Apr 2023 | **Medium-high** |
| EDU PICO V2 | [`edu-pico-v2.md`](edu-pico-v2.md) | `EDU-PICO2` (`EDU-PICO2-NB` = no Pico) | Raspberry Pi Pico 2 W | Datasheet Rev 1.1, Jun 2026 | **Medium** |
| Maker Pi RP2040 | [`maker-pi-rp2040.md`](maker-pi-rp2040.md) | `MAKER-PI-RP2040` | RP2040 soldered on (no Pico socket) | Datasheet Rev 1.2, Jan 2022 | **Medium-high** |
| Maker Pi Pico | [`maker-pi-pico.md`](maker-pi-pico.md) | `MAKER-PI-PICO` (`MAKER-PI-PICO-NB` = Maker Pi Pico Base, no Pico) | Raspberry Pi Pico soldered on | Datasheet Rev 1.2, Mar 2021 | **Medium-high** |
| Maker Pi Pico Mini | [`maker-pi-pico-mini.md`](maker-pi-pico-mini.md) | `MAKER-PI-PICO-MINI` (`-NB` = socket, no Pico) | Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Jun 2022 | **Medium-high** |
| MOTION 2350 Pro | [`motion-2350-pro.md`](motion-2350-pro.md) | Not stated (mirrors use `MOTION-2350-PRO`) | RP2350 | Datasheet **Rev 2.0, Sep 2025** | **Medium-high** |
| Maker Nano RP2040 Getting Started Bundles | [`maker-nano-rp2040-bundles.md`](maker-nano-rp2040-bundles.md) | `V-MN2040` | RP2040 — Maker Nano RP2040 board (Arduino Nano layout) in a starter bundle; Getting Started / Blynk IoT variants | Getting Started docs (2022–2023, no version) | **Medium-high** |

Pico / RP2040 / RP2350 notes for every agent:
- **MOTION 2350 Pro Rev 2.0 motors are 5 A continuous / 10 A peak per channel**, with over-current, 150 ℃ thermal and >18 V input shutdown. 3 A (and "no over-current protection") is the Rev 1.0 board — don't use 3 A for the current board. Motors GP8–GP15, servos GP0–GP7, buttons GP20/GP21, buzzer GP22, 2 RGB LEDs GP23; Arduino `LED_BUILTIN` = GP2 (a servo pin). Never publish the datasheet's "VIN = VADC / 6.1" until the design team confirms it.
- **Maker Pi RP2040 brake/coast:** High/High = coast, Low/Low = brake (datasheet). In CircuitPython `throttle = 0` coasts and `throttle = None` brakes — the opposite of Cytron's demo comments. Power 3.6–6 V (USB, LiPo or VIN); motor/servo voltage = input voltage.
- **Maker Pi Pico is USB-powered only** (4.5–5.5 V; no battery or VIN). GP18 drives both the buzzer and the left audio channel (mute the buzzer when using the jack); audio is not amplified. RGB: Maker Pi RP2040 = 2× WS2812B on GP18; Maker Pi Pico = 1× WS2812B on GP28.
- **Maker Pi Pico Mini Maker Ports are JST-SH (Qwiic/STEMMA QT)**, not Grove (Grove needs a conversion cable); the GP0/GP1 and GP4/GP5 ports both sit on I2C0. No audio jack, microSD, ESP-01 socket or mute switch (unlike Maker Pi Pico).
- **Maker Nano RP2040 + Grove WiFi 8266:** power the Grove WiFi from 5 V, not 3.3 V (the Blynk doc says 3.3 V is not enough). The Blynk doc's sample code carries a template ID — never copy it. Board facts live in `maker-nano-rp2040.md`.

### micro:bit accessories

| Product | File | Code | Role | Primary source | Confidence |
|---|---|---|---|---|---|
| MOTION:BIT | [`motion-bit.md`](motion-bit.md) | `MOTION-BIT` | Motor + servo expansion board, 3.6–6 V | Datasheet Rev 1.0, Feb 2023 | **Medium-high** |
| MOTION:BIT Pro | [`motion-bit-pro.md`](motion-bit-pro.md) | `MOTION-BIT-PRO` | Motor + servo expansion board, 7–12 V | Datasheet Rev 1.0, Apr 2024 | **Medium-high** |
| SUMO:BIT | [`sumo-bit.md`](sumo-bit.md) | Not stated | Sumo robot controller; needs 2× MD13S | Datasheet Rev 1.0, Dec 2024 (RobotShop mirror) | **Medium-high** |
| REKA:BIT | [`reka-bit.md`](reka-bit.md) | Not stated (resellers: `REKABIT-NB`) | Robotics expansion board, 3.6–6 V | Datasheet Rev 1.0, Apr 2021 | **Medium-high** |
| ZOOM:BIT | [`zoom-bit.md`](zoom-bit.md) | Not stated | Robot car kit built on REKA:BIT | Quick Start Guidebook v1.1, 2022 (wiring pages read 21 Oct 2026; no datasheet) + REKA:BIT datasheet | **Medium-high** |
| Grove WiFi 8266 | [`grove-wifi-8266.md`](grove-wifi-8266.md) | `GRV-WIFI-8266` | ESP8266 Wi-Fi Grove module (ESP-AT), 3.3 V logic | Datasheet Rev 1.0, Aug 2021 | **Medium-high** |
| EDU:BIT | [`edu-bit.md`](edu-bit.md) | `V-EDUBIT` (board `EDUBIT`) | micro:bit training board with break-off modules, 3 servo + 2 DC motor ports, 10+1 game lessons | Product page + course overview + guide book (4th printing May 2021, read as images) + pxt-edubit v1.15.0 (no electrical datasheet) | **Medium** |

micro:bit notes for every agent:
- **Motors and servos on MOTION:BIT, MOTION:BIT Pro, REKA:BIT and SUMO:BIT are driven over I2C (P19/P20) by an on-board chip**, not by micro:bit GPIO: MOTION:BIT PCA9685 at 0x40; REKA:BIT PIC16F1827 at 0x08 (an I2C Grove device must not use 0x08); SUMO:BIT RP2040 co-processor at 0x09.
- **REKA:BIT servo/motor voltage is the raw battery voltage** (not regulated 5 V); above 7 V it cuts servo and motor power; below 3.6 V it only blinks an LED. MOTION:BIT Pro servo power is jumper-selected 5 V or VIN (VIN can damage servos).
- **SUMO:BIT USB-C is for its own firmware only**, not for programming. Opponent sensors P12–P16 read LOW on detection; edge sensors P0/P1 are analog.
- **ZOOM:BIT uses a REKA:BIT.** micro:bit V1 has no speaker (sound needs a Grove buzzer; sound-expression blocks are V2 only). The micro:bit is only included in some purchase options.
- **MakeCode extensions:** `motionbit` (also serves MOTION:BIT Pro), `rekabit`, `sumobit`, `zoombit`. "Python" means MakeCode's Python mode unless a file says otherwise.
- **Grove WiFi 8266 logic is 3.3 V** (RX high max 3.6 V) even though VCC accepts 3–6 V — level-shift from 5 V hosts. Ships with Cytron's ESP-AT v2.2.0 build (AT on GPIO1/GPIO3), 115200 baud; MakeCode default Tx P16 / Rx P15; Pico examples TX GP16 / RX GP17; legacy NONOS-AT v1.x commands are not fully compatible.
- **EDU:BIT pins (from pxt-edubit):** sound P1, potentiometer P2, IR P8, 4 RGB LEDs P13, traffic light P14/P15/P16; buttons parallel micro:bit A/B. Motors and servos only via the PIC16F1937 co-processor at I2C 0x08 (3 servo ports, not 4). The default extension does not work with Bluetooth (NeoPixel dependency) — use the modified one from the Teachable Machine tutorial.

### micro:bit kits

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| REKA:BIT RBT Project Kit | [`rekabit-rbt-project-kit.md`](rekabit-rbt-project-kit.md) | `V-KIT-REKABIT-RBT` | RBT Y5/Y6 kit: REKA:BIT + 7 components, 5 projects | Quick Start Guide, English v2.0 (Feb 2023, read 21 Oct 2026) + resource hub + pxt-rekabit-rbt-project-kit | **Medium-high** |
| Auto Plant Watering Kit | [`auto-plant-watering-kit.md`](auto-plant-watering-kit.md) | `V-KIT-RBT-APW` | REKA:BIT + soil sensor + pump + servo; IoT option adds Grove WiFi 8266 | Lesson Guide (English, Apr 2022) | **Medium-high** |
| BEETLE:BIT | [`beetlebit.md`](beetlebit.md) | `V-BEETLEBIT` | REKA:BIT gripper robot car, 7 chapters | BEETLE:BIT Quick Start Guide booklet (read 21 Oct 2026) + resource hub + MakeCode chapter programs | **Medium-high** |
| STRIKER:BIT | [`strikerbit.md`](strikerbit.md) | `V-STRIKERBIT` | 4-robot classroom soccer kit on MOTION:BIT + Robo Base Mini | STRIKER:BIT Booklet (read 20 Oct 2026) + scoring sheet + product page | **Medium** |
| SUMO:BIT Robot Kit (1 kg) | [`sumobit-robot-kit.md`](sumobit-robot-kit.md) | `V-KIT-SUMOBIT` | 1 kg sumo robot on SUMO:BIT + 2× MD13S | Google Slides guides (Assembly/Checking/Maintenance/Autonomous/RC, Dec 2024) | **Medium-high** |
| Robot Battle (500g) SUMO:BIT | [`robot-battle-500g-sumobit.md`](robot-battle-500g-sumobit.md) | `V-BATTLE-SMB` | 500 g battle robot on SUMO:BIT, no controller, no warranty | Product page only | **Medium** |
| SOCCER:BIT (4 wheel) | [`soccerbit-robot-kit.md`](soccerbit-robot-kit.md) | `V-SCRBIT-4WD` | 4-motor soccer robot on SUMO:BIT | Product page only (its "user manual" link is the MD13S manual) | **Medium** |

micro:bit kit notes for every agent:
- **Soil moisture reading rises as soil dries** — the APW trigger is `reading > threshold`; there is no fixed threshold in the booklet. APW wiring: sensor P2:P12 (read P2), pump MOTOR 2, servo S1; servo sweeps 30–150°.
- **RBT kit extension is `pxt-rekabit-rbt-project-kit`** (search "rekabit rbt project"); ultrasonic returns 300 cm when nothing is detected (ZOOM:BIT's returns 255). RGB Stick and Ultrasonic blocks need an init block.
- **BEETLE:BIT uses `pxt-zoombit`** (there is no beetlebit extension); gripper servo S1, motors M1 left / M2 right, Maker Line in Grove port P1:P9 (leave the white CAL wire off on micro:bit V1), ultrasonic in P2:P12; RC mode needs a second micro:bit V2 (not included).
- **SUMO:BIT kit motors are 12 V 580 rpm** (torque not stated — don't borrow 3.5 kgf·cm from the RC bundle); built weight ≈860 g before weights. For USB-joystick or hobby-RC mode the micro:bit must be removed; only Cytron's USB Joystick is supported. Battle kit: 495 g, 15×15×4 cm, charger included; sumo kit: charger NOT included.
- **STRIKER:BIT:** the servo part is a shooter, not a gripper; each robot needs two micro:bits (robot + Joystick:bit); battery is a button-top 18650. Score rules: max 2 yellow cards per robot, 2 red per team.

### Cytron sumo robot controllers

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker Mini Sumo Controller | [`maker-mini-sumo.md`](maker-mini-sumo.md) | `MAKER-MSUMO` | ATmega328P | Active (Datasheet Rev 1.0, Nov 2019) | **Medium-high** |
| URC10 ("Sumo Robot Controller R1.1" on my.cytron.io) | [`urc10.md`](urc10.md) | `URC10` | Not stated by Cytron | Datasheet Rev 1.0, Mar 2019 + User's Manual V1.2, Apr 2019 | **Medium-high** |
| IR Sumo Start | [`ir-sumo-start.md`](ir-sumo-start.md) | `IR-SUMO-START` | — (IR start module) | Datasheet Rev 1.0, Apr 2025 | **Medium-high** |

### Servo, RC, interface and breakout boards

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| SC08A Servo Controller | [`sc08a.md`](sc08a.md) | `SC08A` | 8-ch (16 with two boards) UART servo controller, 9600 baud | User's Manual V1.0, Jun 2011 (Cytron copy, read in full 21 Oct 2026; no datasheet) + Cytron GitHub sample code (PIC, GUI, Arduino) | **Medium-high** |
| RCSwitch10 | [`rcswitch10.md`](rcswitch10.md) | `RCS10A` | RC-controlled SPDT relay, 250 VAC / 30 VDC, 10 A | Cytron Connection Diagram (read 20 Oct 2026) + product page | **Medium-high** |
| UC00C | [`uc00c.md`](uc00c.md) | `UC00C` | CH340 USB-to-UART converter, 3.3/5 V switch | User's Manual V1.0, Jul 2016 (Cytron Google Doc, read in full incl. figures) + product page incl. pinout images (21 Oct 2026) + CH34x driver links | **Medium-high** |
| UC00A | [`uc00a.md`](uc00a.md) | `UC00A` (Rev 3.0) | FTDI FT232RL USB-to-UART converter, 3.3/5 V switch | User's Manual Rev3.0 V1.1, Dec 2018 (no datasheet) | **Medium-high** |
| URS232A TTL-to-RS232 | [`urs232a.md`](urs232a.md) | `URS232A` | MAX232 level shifter, DB9 male (PC side), Tx/Rx/CTS/RTS | Product page + Cytron schematic URS232A.sch (1/2/2016) [DT]; TI MAX232 [VEN] for chip context | **Medium-high** |
| Breakout Board PS2 Connector | [`bb-psc.md`](bb-psc.md) | `BB-PSC` | Female PS2 connector broken out to 0.1" | Maker Mini Sumo PS2 tutorial (20 May 2024, read in full incl. wiring figure) + product page | **Medium-high** |

### Sumo robot kits and parts

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Ikedo Mini Sumo Robot V2 | [`ikedo-mini-sumo-v2.md`](ikedo-mini-sumo-v2.md) | `KIT-IKEDO-MSV2-S` | Maker Mini Sumo + 5 Maker Object + 2 edge sensors, 600 rpm, ~200 g | Ikedo Bot V2 Getting Started Instruction | **Medium-high** |
| Ikedo Mini Sumo Robot Pro Bundle | [`ikedo-mini-sumo-pro.md`](ikedo-mini-sumo-pro.md) | `KIT-IKEDO-MSUMO-P` | Pro: 800 rpm 3.1 kg·cm, steel shield, razor blade, 350 g | Product page | **Medium** |
| 1KG Sumo Robot Bundles (RC) | [`sumo-1kg-rc-bundle.md`](sumo-1kg-rc-bundle.md) | `V-SUMO-1KG-RC` | MDDRC10 RC sumo, no code, 580 rpm 3.5 kgf·cm, 856 g | Product page (user-guide tutorials blocked) | **Medium** |
| PCB Plate for Sumo Robot | [`pcb-sumo-plate.md`](pcb-sumo-plate.md) | `V-PCB-SUMO-PLATE` | Training blade substitute, 15 cm (1 kg) / 10 cm (500 g) | Product page | **Medium-high** |
| High Grade Silicon Wheels for Sumo Robot (42×30 / 32×22 mm) | [`sumo-silicone-wheels.md`](sumo-silicone-wheels.md) | `V-WL-SL-4230` / `V-WL-SL-3222` | Silicone tyre on aluminium rim for 1 kg / 500 g sumo robots | Cytron product pages + rim drawing + STL | **Medium** |
| 500g Sumo Robot Map | [`sumo-robot-map-500g.md`](sumo-robot-map-500g.md) | `PM-MAP-SUMO` | UV-vinyl 500 g sumo practice ring, 77 cm | Cytron product page + team confirmation | **Medium** |
| Metal Base for Sumo Robot | [`sumo-metal-base.md`](sumo-metal-base.md) | `HD-BSC-MSUMO-MB` | 96 g metal ballast plate with M3 holes for sumo/soccer robots | Cytron product page + team confirmation + Copper Base STL (same-size part) | **Medium** |

- **1KG RC bundle has no microcontroller** — the page's "Microcontroller: MDDRC10" is a motor driver; no sensors, no autonomous mode. **No warranty** on all three robot bundles. Kit pages say opponent range "50cm adjustable" — the Maker Object datasheet says 40–140 cm (white) / 15–60 cm (black).
- **Sumo parts (added 21 Oct 2026 from the Cytron OEM page):** silicone wheels are sold **one per unit**; 42×30 mm (4 mm bore, 2× M4 set screws, 1 kg class, fits the GM25 motors) vs 32×22 mm (3 mm shaft, 500 g class, fits SPG10 micro gearmotors); M2 Allen key sold separately. The 500g Sumo Robot Map is a **practice** mat (77 cm white / 72 cm black, UV vinyl) — not for competition. The Metal Base (96 g, 83×50×3 mm, M3) is the "2x metal base" in the 1KG RC bundle; no screws included.

### Sensors

| Product | File | Code | Output | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Line | [`maker-line.md`](maker-line.md) | `MAKER-LINE` | 5 digital (high = line) + 1 analog; 3.0–5.5 V | Datasheet Rev 1.0, Jul 2019 | **Medium-high** |
| Maker Object | [`maker-object.md`](maker-object.md) | `MAKER-OBJECT` | IR object sensor, digital **active LOW**; 4.5–5.5 V | Datasheet Rev 1.0, Dec 2019 | **Medium-high** |
| Maker Reflect | [`maker-reflect.md`](maker-reflect.md) | `MAKER-REFLECT` (page variant `V-MAKER-REFLECT`) | Analog IR reflectance, 3.0–5.5 V, 1–40 mm | Datasheet Rev 1.0, Nov 2019 | **Medium-high** |
| Maker Reflect S | [`maker-reflect-s.md`](maker-reflect-s.md) | `MAKER-REFLECT-S` | IR reflectance, **5 V only**, 25 mA, optimal 3 mm | Datasheet Rev 1.0, Feb 2026 | **Medium-high** |
| Maker Soil Moisture Sensor | [`maker-soil-moisture.md`](maker-soil-moisture.md) | `MAKER-SOIL-MOISTURE` | Capacitive soil moisture, analog OUT 1.0–5.2 V + DIS pin | Datasheet Rev 1.0, Jan 2022 | **Medium-high** |
| MCP9700 Temperature Sensor | [`mcp9700-temperature-sensor.md`](mcp9700-temperature-sensor.md) | `BCY-TEMP-MCP9700` | Analog temperature, 10 mV/°C with 500 mV offset at 0 °C | Datasheet Rev 1.0, Aug 2023 | **Medium-high** |
| LSA08 Line Sensor | [`lsa08.md`](lsa08.md) | `LSA08` | 8-sensor auto-calibrating line sensor bar; analog / digital / UART | User's Manual V1.1, Jun 2012 + Library Manual V1.1, Jan 2013 (no datasheet) | **Medium-high** |
| RE08A Rotary Encoder Kit | [`re08a.md`](re08a.md) | `RE08A` | 8-slot opto rotary encoder, 16 pulses/rev, single channel | User's Manual V1.2, Sep 2008 (mirror; no datasheet) | **Medium-high** |
| 50A Current Sensor | [`bb-acs756.md`](bb-acs756.md) | `BB-ACS756` | Allegro ACS756 ±50 A breakout, 40 mV/A, 5 V | Product page + Cytron schematic + Allegro [VEN] + Cytron GitHub PIC sample code (SK28A) | **Medium** |
| RGB LED Stick | [`rgb-led-stick.md`](rgb-led-stick.md) | `BCY-NEO-STICK-8` | 8× SK6812 (WS2812B-compatible) chainable stick | Product page + tutorial | **Medium** |
| 3-Axis Accelerometer | [`sn-adxl335-cy.md`](sn-adxl335-cy.md) | `SN-ADXL335-CY` | ADXL335 ±3 g breakout, 2.5–6 V (on-board 3.3 V reg), 50 Hz | Product page + ADI [VEN] | **Medium** |

Sensor notes for every agent:
- **Maker Line:** digital outputs go HIGH when the line is detected; which colour counts as the line is set by the Light/Dark switch. Analog below 0.1×Vcc = line not found, above 0.9×Vcc = cross detected (not "far left / far right"). 4–40 mm sensing height is stated only at VCC = 5 V, black line on white. Calibrate: hold button >2 s, sweep across the line, press again.
- **Maker Object:** range is 40–140 cm on white A4 but only 15–60 cm on black A4 — never write "up to 140 cm" alone. Digital detect/no-detect only (no distance value); 5 V supply; output high is VCC − 0.5 V to VCC, so don't wire it straight into a 3.3 V-only GPIO without checking. Not a Grove/Maker Port connector.
- **Maker Reflect:** output voltage is HIGHER on darker surfaces (white = lower); sumo edge logic looks for a low reading. **Maker Reflect and Maker Reflect S specs are not interchangeable** — Reflect 3.0–5.5 V analog 1–40 mm; Reflect S 5 V only, 25 mA, optimal 3 mm, no min/max range stated. Neither has reverse-polarity protection, an LED, a trimmer or calibration.
- **Maker Soil Moisture:** higher voltage = drier; OUT spans 1.0–5.2 V, so at 5 V the DRY band (3.1–3.6 V) exceeds a 3.3 V ADC; DIS threshold is VCC − 0.8 V (unreachable from a 3.3 V GPIO at 5 V supply). The reading is qualitative, not a percentage.
- **MCP9700:** T(°C) = (VOUT − 500 mV) / 10 mV. "LM35 compatible" means the same slope, not the same zero — LM35-style code reads ~50 °C high. Output current 100 µA max; never quote ±2/±4 °C accuracy (not stated).
- **LSA08:** powered from 7.5–20 V (12 V typical), outputs are 5 V logic; UART streams only while UEN is held low and the default UART mode is 0 = no output; "no line" = 255 (UART), 5 V (analog), 127 (C library). Refresh 100 Hz (Tindie's 200 Hz is wrong).
- **RE08A:** 16 pulses per revolution, single channel (no direction), Sig LOW when a slot is in front of the sensor, output limited to 1 kHz.

### Robot parts and accessories

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| STEM Robot Building Base Bundles | [`stem-robot-building-base.md`](stem-robot-building-base.md) | `V-HD-STEM` | Plastic 2WD base + TT motors, wheels, castor (Blue/Green) | Installation guide tutorial (25 Jul 2023, read in full incl. images) + product page | **Medium-high** |
| Reconfigurable Line Following Track | [`line-following-track.md`](line-following-track.md) | `V-RE-TRACKS` | EVA foam tiles 315×315×10 mm, 18 mm line; Combo 8/16 + add-ons | Product page | **Medium-high** |
| Robo Bracket for Micro Servo | [`robo-bracket-micro-servo.md`](robo-bracket-micro-servo.md) | `ROBO-BK-SG90` | 1.5 mm aluminium bracket for SG90-size servos, fits Robo Base / Mini | Product page + its dimension drawing (read 21 Oct 2026) | **Medium-high** |
| Robo Base | [`robo-base.md`](robo-base.md) | Series page `V-ROBO-BASE-MINI` | PCB robot chassis; 2WD / 4WD mecanum / accessories / single-base options; 30 mm standoffs | Getting Started with Robo Base tutorial series (16 parts, Jun 2025) + product page spec images | **Medium-high** |
| Robo Base Mini | [`robo-base-mini.md`](robo-base-mini.md) | Series page `V-ROBO-BASE-MINI` | Smaller PCB chassis, same options; 25 mm standoffs | Product page + Getting Started tutorial (section list) | **Medium-high** |
| Robo Grip Mini Kits | [`robo-grip-mini.md`](robo-grip-mini.md) | `V-ROBO-GRIP-MINI` | PCB gripper for SG90-size servos; gripper only / 2-servo / 3-servo | Installation Guide series (overview + 1/2/3-servo parts, Feb 2026, read in full) + product page | **Medium-high** |
| DC Geared Motor Bracket (SPG30/SPG50) | [`motor-bracket-spg30-spg50.md`](motor-bracket-spg30-spg50.md) | `HD-BK-SPG` | 1.5 mm steel L-bracket for SPG30/SPG30E/SPG50 | Cytron drawing + product page | **Medium-high** |
| Planetary Motor Bracket (IG42E/IG45) | [`motor-bracket-ig42e-ig45.md`](motor-bracket-ig42e-ig45.md) | `HD-BK-IG4X` | Steel L-bracket for IG42E/IG45 motors, 26.5 mm bore | Cytron drawing + product page | **Medium-high** |
| 5 Inches Robot Wheel (no hub / 8 mm / 10 mm hub) | [`robot-wheel-5in.md`](robot-wheel-5in.md) | `WL-RBT-5` / `WL-RBT-508` / `WL-RBT-510` | 127 mm robot wheel, alone or with 8/10 mm key hub | Cytron drawing + product pages | **Medium-high** |
| Metal Key Hub (6/8/10 mm) | [`metal-key-hub.md`](metal-key-hub.md) | `CO-SPG` / `CO-MTL-08` / `CO-MTL-10` | Shaft-to-flange hub for 6/8/10 mm motor shafts | Cytron drawings + product pages | **Medium-high** |
| 6mm Key Hub for 60mm Mecanum Wheel | [`mecanum-key-hub-6mm.md`](mecanum-key-hub-6mm.md) | `CO-MEC-06` | Aluminium 6 mm hub for the 60 mm mecanum wheel | Cytron drawing + product page | **Medium** |
| Motor Mount & 5 Inches Wheel Bundle | [`motor-mount-5in-wheel-bundle.md`](motor-mount-5in-wheel-bundle.md) | `KIT-PW-5WL` | Left + Right power-window motors with 5-inch wheels mounted | Product page + motor/wheel drawings | **Medium-high** |
| Line Following Mobile Robot Bundle | [`line-following-mobile-robot-bundle.md`](line-following-mobile-robot-bundle.md) | `KIT-RBT-LF` | Maker UNO line-following robot kit on Robo Base Mini | Cytron tutorial (2025) + product page | **Medium** |
| Obstacle Avoidance Mobile Robot Bundle | [`obstacle-avoidance-mobile-robot-bundle.md`](obstacle-avoidance-mobile-robot-bundle.md) | `KIT-RBT-OA` | Maker UNO ultrasonic obstacle-avoiding robot kit on Robo Base Mini | Cytron tutorial (2025) + product page | **Medium** |

- **STEM base includes no electronics, battery or cable ties**; fit the brackets to the motors first, then screw motor + bracket to the lower plate; all fixings use M2.2 × 6 mm screws (installation guide, read 21 Oct 2026); motor brackets are blue on both colour options. **Line track:** Combo 8/16 contain only Cross/Curve/Straight — Station, Blank and T-Junction are add-on packs only; hardness "40 degree (±5)" has no scale stated.
- **Robo Base series:** no kit includes a controller, battery, sensors or servo; 2WD option is named "Rubber Wheels" but lists "plastic wheels". **Robo Grip Mini:** max 3 servos ("1-axis" = 2 servos, "2-axis" = 3); "Gripper only" has no servo or Robo Bracket; snap and file the parts before assembly. In STRIKER:BIT it is a shooter.
- **Motor brackets, hubs and wheels (added 21 Oct 2026 from the Cytron OEM page):** the 5-inch wheel, the 8/10 mm Metal Key Hubs and the power-window motor coupling share **3× M5 on a Ø31 mm circle**; the 6 mm Metal Key Hub is different (4× M3 on Ø20 mm, Ø25 mm flange). SPG bracket = M3, IG42E/IG45 bracket = M4 (26.5 mm bore); the IG32E bracket (HD-BK-IG3X, 21 mm bore) is being discontinued and is not in the KB. The 10 mm hub page's packing list says "8mm" (typo); the mecanum hub drawing shows an M4 set screw but the pack lists M3. Motor Mount & 5 Inches Wheel Bundle needs a 30 A-class driver (MD30C / MDDS30) — not the page's "10A shield".
- **Line Following / Obstacle Avoidance bundles:** follow the 2025 tutorials (Maker Drive on pins 11/10 and 6/5). The line-following sample sketch reads a third sensor on A3 that the kit doesn't include; the obstacle page's 2019 "Sample code" uses different pins and an L298 driver. Standoff lengths on the pages differ from the tutorials; the obstacle kit is Robo Base Mini PCB, not acrylic.

### Motors (Cytron OEM)

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| 12V 37mm DC Geared Motor (SPG30/SPG30E) | [`dc-geared-motor-37mm-12v.md`](dc-geared-motor-37mm-12v.md) | `V-SPG30` | 12 V 37 mm spur gearmotor, 5 ratios, optional 16 PPR encoder | Cytron Motor Specification PDFs + product page | **Medium** |
| 12V High Power DC Geared Motors (SPG30HP) | [`high-power-dc-geared-motor-12v.md`](high-power-dc-geared-motor-12v.md) | `SPG30HP-30K` / `SPG30HP-10K` | 12 V 37 mm high-power gearmotor, 30:1 or 10:1 | Outline drawings + product pages | **Medium-high** |
| Power Window Motor with Coupling (Left/Right) | [`power-window-motor.md`](power-window-motor.md) | `MO-PW-CL` / `MO-PW-CR` | 12 V worm-gear power-window motor with Cytron 3×M5 coupling | Product pages + motor and coupling drawings | **Medium-high** |

These products are listed on Cytron's OEM page (https://my.cytron.io/cytron-oem, read 21 Oct 2026; 32 listings filed as 25 KB files — variants share one file). No page names the original motor maker.

- **SPG30 / SPG30E:** the product page's current and torque table is far below Cytron's Motor Specification PDFs (e.g. 400 mA / 1.2 A vs 1288 mA / 5.8 A) — size drivers from the datasheet: MDD10A or MD10C; MDD3A only if the motor is never stalled. Encoder 16 PPR Hall, 3.3–5 V; wires Red/Black motor, Green GND, Blue VCC, Yellow A, White B.
- **SPG30HP:** ≤1 A rated, ≤3.7 A permitted max (drawing) vs page "may exceed 5 A"; gearbox M3 holes are only ≤3.5 mm deep — long screws hit the gears.
- **Power window motor:** 12 V 60 RPM, rated <15 A, stall <28 A, **intermittent duty only** — use a 30 A-class driver (MD30C / MDDS30); the page's 10 A suggestion (MDD10A) is below the rated current.

### Cytron motor drivers

| Product | File | Code | Rating (per datasheet) | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Drive | [`maker-drive.md`](maker-drive.md) | `MAKER-DRIVE` | 2 ch, 2.5–9.5 V, 1 A cont / 1.5 A peak (<5 s) | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD3A | [`mdd3a.md`](mdd3a.md) | `MDD3A` | 2 ch, 4–16 V, 3 A cont / 5 A peak (<5 s) | Datasheet Rev 1.0, Mar 2019 | **Medium-high** |
| MD10C | [`md10c.md`](md10c.md) | `MD10C` (Rev 3.0) | 1 ch, 5–30 V, 13 A cont / 30 A peak (≤10 s) | User's Manual Rev3.0 V1.0, Aug 2018 (no datasheet) | **Medium** |
| MD13S | [`md13s.md`](md13s.md) | `MD13S` | 1 ch, 13 A, current limit 30 A; logic ≤5.5 V | User's Manual V1.1, Jun 2018 (no datasheet) | **Medium-high** |
| MD20A | [`md20a.md`](md20a.md) | `MD20A` | 1 ch, 6–30 V, 20 A cont / 60 A peak (current-limited, no duration); logic 1.5–15 V | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD10A | [`mdd10a.md`](mdd10a.md) | `MDD10A` (Rev 2.0) | 2 ch, 5–30 V, 10 A cont / 30 A peak (≤10 s) per ch | User's Manual V2.0, Jun 2017 (no datasheet) | **Medium-high** |
| MDD20A | [`mdd20a.md`](mdd20a.md) | `MDD20A` | 2 ch, 6–30 V, 20 A cont / 60 A peak (current-limited) per ch | Datasheet Rev 1.0, Jul 2020 | **Medium-high** |
| MD25HV | [`md25hv.md`](md25hv.md) | `MD25HV` | 1 ch, 7–58 V, 25 A cont / 60 A peak (current-limited); no locked-antiphase | Datasheet Rev 1.0, Jan 2019 | **Medium-high** |
| MDDS10 SmartDriveDuo-10 | [`mdds10.md`](mdds10.md) | `MDDS10` | 2 ch, 10 A cont / 30 A peak (≤1 s) | User's Manual V1.0, Jun 2015 (no datasheet) | **Medium-high** |
| MDDS30 SmartDriveDuo-30 | [`mdds30.md`](mdds30.md) | `MDDS30` | 2 ch, 7–35 V, 30 A cont / 80 A peak (≤1 s) per ch | User's Manual Rev 1.2, Sep 2023 (no datasheet) | **Medium-high** |
| MDDS60 SmartDriveDuo-60 | [`mdds60.md`](mdds60.md) | `MDDS60` | 2 ch, 10–45 V, 60 A cont / 100 A peak (≤1 s) per ch | User's Manual Rev 1.1, Jul 2019 (no datasheet) | **Medium-high** |
| Enhanced SmartDrive40 | [`smartdrive40.md`](smartdrive40.md) | `MDS40B` | **1 ch**, 40 A cont / 80 A peak (≤1 s) | User's Manual Rev 1.1, Jul 2023 (no datasheet) | **Medium-high** |
| MDDRC5 | [`mddrc5.md`](mddrc5.md) | `MDDRC5` | 2 ch R/C, 7–30 V, 5 A cont / 20 A peak (<1 s) per ch | Datasheet Rev 1.0, Mar 2026 | **Medium-high** |
| MDDRC10 | [`mddrc10.md`](mddrc10.md) | `MDDRC10` | 2 ch R/C, 7–30 V, 10 A cont / 30 A peak (current-limited) per ch | Datasheet Rev 1.0, Aug 2020 | **Medium-high** |
| iMD16 | [`imd16.md`](imd16.md) | `IMD16` | 1 ch, 16 A cont / 30 A peak (<10 s), no current limit | Datasheet Rev 1.0, Apr 2026 | **Medium-high** |
| SHIELD-2AMOTOR | [`shield-2amotor.md`](shield-2amotor.md) | `SHIELD-2AMOTOR` | 2 ch Arduino shield, 5–26 V, **0.8 A cont** / 2 A peak | User's Manual V1.1, Feb 2015 | **Medium-high** |
| SHIELD-3AMOTOR | [`shield-3amotor.md`](shield-3amotor.md) | `SHIELD-3AMOTOR` | 2 ch Arduino shield, 7–30 V, **1.2 A cont** / 3 A peak (≤1 s) | User's Manual Rev 1.0, Apr 2017 | **Medium-high** |
| FD04A | [`fd04a.md`](fd04a.md) | `FD04A` (Rev 2.0) | **4 ch**, 7–15 V, 1.5 A cont / 2.5 A peak, L298P | User's Manual V1.2, Jun 2025 (read in full incl. figures 21 Oct 2026) | **Medium-high** |
| MD10-POT | [`md10-pot.md`](md10-pot.md) | `MD10-POT` | 1 ch, 7–30 V, 10 A / 30 A peak (<10 s); pot + switch or PWM/DIR | Datasheet Rev 1.0, Oct 2018 | **Medium-high** |
| SHIELD-MD10 | [`shield-md10.md`](shield-md10.md) | `SHIELD-MD10` (Rev 2.0, "R2") | 1 ch Arduino shield, 7–30 V (abs-max table says 25 V), 15 A peak (10 s) | User's Manual (Rev 2.0 board) V1.0, Jun 2015 + Cytron 3D model SHIELD-MD10 R2 (GitHub, Jan 2019) [DT] | **Medium** |
| SHIELD-MDD10 | [`shield-mdd10.md`](shield-mdd10.md) | `SHIELD-MDD10` | 2 ch Arduino shield, 7–30 V, 10 A / 30 A over-current limit (temperature-dependent) | Datasheet Rev 1.0, May 2019 | **Medium** |
| HAT-MDD10 | [`hat-mdd10.md`](hat-mdd10.md) | `HAT-MDD10` | 2 ch Raspberry Pi HAT, 6–24 V, 10 A / 30 A (10 s) | User's Manual V1.0, Mar 2017 | **Medium-high** |
| MD30C | [`md30c.md`](md30c.md) | `MD30C` (Rev 2.0) | 1 ch, 5–30 V, 30 A cont / 80 A peak (≤1 s) | User's Manual V1.4, Dec 2017 (no datasheet) | **Medium-high** |
| MDS160A SmartDrive160 | [`mds160a.md`](mds160a.md) | `MDS160A` | 1 ch, 8–28 V, 160 A cont / 175 A (2 min) / 190 A (1 min) | User's Manual V1.0, Aug 2014 (no datasheet) | **Medium-high** |

Motor-driver notes for every agent:
- **No reverse-polarity protection** on MD10C, MD13S, MD20A, MDD10A, MDD20A, MD25HV, MDDS10, MDDS30, MDDS60, MDS40B, MDDRC10 (Maker Drive, MDD3A and MDDRC5 do have it).
- **Over-current:** only MD13S ("current limiting at 30A"), MD20A, MDD20A, MD25HV, MDDRC10, MDDRC5 and MDDS30 state current limiting; never claim it for the others. Where a peak is current-limited (MD20A, MDD20A, MD25HV, MDDRC10) no peak duration is stated — don't invent one.
- **SmartDriveDuo serial:** MDDS30's packetized start-up byte is 0x80 (128); MDDS10/MDDS60 use 0x55. Cytron's Arduino library header byte (0x85) contradicts all three manuals.
- **MDS40B (Enhanced SmartDrive40) drives one motor** — a two-motor robot needs two boards (Mixed Left + Mixed Right).
- **Switching power supplies:** MDD10A, MDDS10 and iMD16 documents warn about regenerated current / back-EMF — use a battery, or a battery of the same voltage in parallel (MDDS10, MDD10A), or bulk capacitors / TVS (iMD16).
- **Brake vs coast differs by board.** Both inputs LOW = brake on Maker Drive, MDD3A and Robo Pico; both HIGH = coast on Maker Drive but brake on MDD3A. PWM LOW = brake on MD10C, MDD10A, iMD16. Check each file.
- **Control mode:** Maker Drive and MDD3A are two-PWM (CytronMotorDriver `PWM_PWM`), not PWM+DIR.
- **MDDRC5:** peak is 20 A for <1 s (product page says <5 s); its 5 V RC-header pin is for the receiver only (500 mA) — never power a servo from it; USB-C does not power the motors.
- **Shield/HAT drivers (2026-10-16 batch):** the "3A"/"2A" in SHIELD-3AMOTOR / SHIELD-2AMOTOR are **peak** ratings — continuous is 1.2 A / 0.8 A. Both use D4–D7 for motors: `CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);` (the library example's 3/4/9/10 pins don't match). SHIELD-3AMOTOR above 12 V needs the PWRIN–Vin link cut (voids warranty).
- **SHIELD-MDD10 powers the Arduino by default** (5 V buck, 500 mA; cut a jumper to disable); **SHIELD-MD10 does not** (power the Arduino first). HAT-MDD10 uses fixed BCM pins PWM1 GPIO12, DIR1 GPIO26, PWM2 GPIO13, DIR2 GPIO24.
- **Peak-duration differs:** MD30C 80 A ≤1 s; MD10-POT 30 A <10 s; SHIELD-MDD10 30 A is a temperature-dependent over-current limit with no duration; MDS160A 190 A for 1 min / 175 A for 2 min. MD10-POT logic high is 3–30 V; MD30C and MDS160A ≤5.5 V.
- **MDS160A** reads its DIP-switch mode only at power-up (power-cycle after changing); its +5V pin is a 1 A output — never connect another 5 V source; a supply that can't absorb regenerated current needs a same-voltage battery in parallel or the driver "will be destroyed permanently". MD30C: battery on the motor port burns the MOSFETs (not covered by warranty). Reverse-polarity protection is stated for MD30C and FD04A only in this batch; SHIELD-3AMOTOR has none.

### Raspberry Pi boards, HATs and accessories

| Product | File | Code | For | Primary source | Confidence |
|---|---|---|---|---|---|
| Industrial IO HAT+ | [`industrial-io-hat-plus.md`](industrial-io-hat-plus.md) | `HAT-IND-AG` | Raspberry Pi 5 only | Datasheet Rev 1.0, Sep 2025 | **Medium-high** |
| Maker pHAT | [`maker-phat.md`](maker-phat.md) | `HAT-MAKER` | Raspberry Pi 3B/3B+, Zero/W/WH (manual) | User's Manual Rev 1.10, Feb 2019 (no datasheet) | **Medium-high** |
| Maker Hat Base | [`maker-hat-base.md`](maker-hat-base.md) | `MAKER-HAT-BASE` | Raspberry Pi 400 (page also shows Pi 3/4) | Datasheet Rev 1.0, Sep 2021 | **Medium-high** |
| CM4 Maker Board | [`cm4-maker-board.md`](cm4-maker-board.md) | `MAKER-CM4` | Raspberry Pi CM4 (product page title now says CM4/CM5) | Datasheet Rev 1.2, Oct 2023 | **Medium** |

Raspberry Pi board notes for every agent:
- **CM4 Maker Board:** the 4 USB ports need `dtoverlay=dwc2,dr_mode=host` (USB host is off by default on CM4). M.2 is NVMe 2230/2242 only — no SATA. microSD works only with CM4 Lite. Both power buttons must be pressed together. Left audio GPIO19 (shared with the buzzer — use the mute switch), right GPIO18. **Do not claim CM5 support** until the design team confirms it.
- **Maker pHAT:** SW2 is **GPIO16** (the manual's feature list says 19 — wrong; 19 is an LED). Don't name its USB-serial chip or driver until the schematic is checked. Serial console needs `enable_uart=1`, 115200 baud.
- **Maker Hat Base:** buttons GPIO17/22/23/27 active low (enable pull-up); fixed-tone buzzer on GPIO26 behind a mute switch; takes 5 V from the Pi (no own input); 3.3 V rail 800 mA max.

### Power and accessories

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| 27W PD USB-C PSU | [`usbc-psu-27w-pd.md`](usbc-psu-27w-pd.md) | `V-AD-27W-PD` | PD adapter 5.1 V 5 A / 9 V 3 A / 12 V 2.25 A / 15 V 1.8 A; UK/EU/US plug | Datasheet Rev 1.0, Feb 2024 | **Medium-high** |
| 17.5W USB-C PSU | [`usbc-psu-17w5.md`](usbc-psu-17w5.md) | `V-AD-5V3P5A` | 5 V 3.5 A fixed, no PD; 20 AWG 1.5 m cable | Datasheet Rev 2.0, Oct 2024 | **Medium-high** |
| 18650 Li-Ion 2200 mAh | [`li-ion-18650-2200.md`](li-ion-18650-2200.md) | `LI-18650-3.7-2200` | Button-top cell, no protection circuit, 1-week warranty | Product page + PKCELL vendor sheet (2019) | **Medium-high** |
| Cooling Fan for RPi 30 mm | [`rpi-cooling-fan-30mm.md`](rpi-cooling-fan-30mm.md) | `FAN-0305-3008` | 3–5 V 0.2 A two-wire fan, 30×30×8 mm | Product page | **Medium** |

- **PSU notes:** the 27W unit's 5 V profile is 5 A (5.1 V typ.); the 17.5W unit has no PD and was designed for Pi 4 B (Pi 5 appears only on the page list). **18650:** max discharge 1C ≈ 2.2 A per Cytron (vendor says 1.5C); cannot ship to Sabah/Sarawak/overseas; never treat it as an AA.

### Cables and small accessories

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Dual Output Cable - USB A to 2.1mm DC Barrel & Micro USB | [`dual-output-cable-usb-dc.md`](dual-output-cable-usb-dc.md) | `WR-USB-UB-DC` | 1 m Y-cable: micro USB data+power and 2.1mm barrel power, for EDU:BIT | Cytron page + photos | **Medium** |
| Grove to JST-SH (Qwiic) Cable - 20cm | [`grove-to-jst-sh-cable.md`](grove-to-jst-sh-cable.md) | `WR-GRV-JST-SH` | Maker Port (JST-SH/Qwiic) to Grove I2C cable | Cytron page + JST SH datasheet | **Medium-high** |
| STEMMA QT / Qwiic JST SH 4-pin Cable with Premium Female Sockets - 150mm | [`stemma-qt-jst-sh-female-cable.md`](stemma-qt-jst-sh-female-cable.md) | `WR-SQ-150F` | Qwiic/Maker Port to female header sockets | Cytron page + photo | **Medium** |
| Grove to SVG Cable - 200mm length | [`grove-to-svg-cable.md`](grove-to-svg-cable.md) | `WR-GRVSVG-210` | Grove to SVG 3-wire cable for Octopus modules on REKA:BIT/EDU:BIT | Cytron page + photos | **Medium** |
| Pin Header Sticker for Maker Uno | [`maker-uno-pin-header-sticker.md`](maker-uno-pin-header-sticker.md) | `MAKER-UNO-STICKER` | Colour-coded header label sticker sheet for Maker UNO | Cytron page + layout drawing | **Medium-high** |

These products are listed on Cytron's OEM page (https://my.cytron.io/cytron-oem, read 21 Oct 2026; 32 listings filed as 25 KB files — variants share one file).

- **Grove to JST-SH:** I2C only (black GND, red V+, blue SDA, yellow SCL). **STEMMA QT female cable:** JST-SH to 4 female Dupont sockets (red 3.3V, black GND, blue SDA, yellow SCL) — the page's "male headers" sentence is wrong; backorder only on 21 Oct 2026. **Grove to SVG:** 3 wires S/V/G; signal goes to the port's first GPIO (P0 on REKA:BIT P0/P1). **Dual Output Cable:** barrel polarity, size and current not stated — don't quote them. **Maker UNO sticker:** no VIN label.

### Storage (MakerDisk)

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| MakerDisk NVMe 2242 | [`makerdisk-nvme-2242.md`](makerdisk-nvme-2242.md) | `V-MMR-NV2242` | M.2 2242 NVMe 128/256/512 GB, RPi OS Bookworm preloaded | Datasheet Rev 1.0, Apr 2024 | **Medium-high** |
| MakerDisk NVMe 2280 (RPi OS) | [`makerdisk-nvme-2280.md`](makerdisk-nvme-2280.md) | `V-MMR-NV2280` | M.2 2280 NVMe 128 GB–1 TB, RPi OS preloaded | Product page | **Medium** |
| MakerDisk NVMe 2280 (JetPack) | [`makerdisk-nvme-2280-jetpack.md`](makerdisk-nvme-2280-jetpack.md) | `V-MMR-NV2280-JP` | 256/512 GB, JetPack 6.2 for Jetson Orin Nano Super 8GB only | Product page | **Medium** |
| MakerDisk 2.5" SATA 120 GB | [`makerdisk-sata-120gb.md`](makerdisk-sata-120gb.md) | `MMR-2P5-MD-120` | SATA III SSD, RPi OS preloaded, USB-SATA boot | Product page | **Medium** |
| Raspberry Pi Approved MakerDisk microSD Card with RPi OS | [`makerdisk-microsd-rpi-os.md`](makerdisk-microsd-rpi-os.md) | `V-MMR-USD-MD` | MakerDisk microSD preloaded with Raspberry Pi OS (32/64/128GB, A1/A2) | Cytron page + RPi approval certificates 2022/2023 | **Medium** |
| MakerDisk 32GB Preloaded Offline MakeCode & Raspberry Pi OS | [`makerdisk-microsd-makecode-offline.md`](makerdisk-microsd-makecode-offline.md) | `MMR-USD-32-MC` | 32GB card, RPi OS + offline micro:bit MakeCode | Cytron page + TomatoCube user instruction | **Medium** |
| MakerDisk 32GB microSD with Debian 12 OS for VisionFive 2 | [`makerdisk-microsd-visionfive2.md`](makerdisk-microsd-visionfive2.md) | `MMR-USD-32-VF2` | 32GB card preloaded with Debian 12 for StarFive VisionFive 2 | Cytron page + images | **Medium** |
| MakerDisk microSD Card 64GB with RDK X5 OS | [`makerdisk-microsd-rdk-x5.md`](makerdisk-microsd-rdk-x5.md) | `MMR-USD-64-RDK` | 64GB A2 card preloaded with RDK X5 OS | Cytron page + Cytron RDK X5 test sheet/quick start [INT] + D-Robotics docs [VEN] | **Medium** |
| USB2.0 Cytron microSD Card Reader/Writer Adapter | [`cytron-microsd-card-reader.md`](cytron-microsd-card-reader.md) | `CA-USB-USD-CT` | USB-A microSD reader/writer (MakerDisk-branded) | Cytron page + photos | **Medium** |

- **MakerDisk microSD cards (added 21 Oct 2026 from the Cytron OEM page):** the latest Raspberry Pi approval certificate read (30 Jun 2023) is valid only to 1 Jul 2024. The "Read 1.1 GB/s" on the MakeCode and VisionFive 2 pages is a cached `dd` read, not a card speed — never quote it. 32GB cards are U1/V10 (sibling pages say U3/V30). Pi Zero/Zero W/WH need a 32-bit re-flash. The VisionFive 2 page prints a default login (not copied). The card reader is USB 2.0 (16/6 MB/s), "128 GB SDHC" on the page should be SDXC.

### IRIV industrial series

| Product | File | Code | Processor | Primary source | Confidence |
|---|---|---|---|---|---|
| IRIV PiControl CM4 | [`iriv-picontrol-cm4.md`](iriv-picontrol-cm4.md) | `IRIV-PICL` | Raspberry Pi CM4 (BCM2711) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.3, Nov 2025 | **Medium-high** |
| IRIV PiControl CM5 | [`iriv-picontrol-cm5.md`](iriv-picontrol-cm5.md) | `IRIV-PICL5` | Raspberry Pi CM5 (BCM2712) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.5, Jan 2026 (read in full incl. figures 21 Oct 2026) | **Medium-high** |
| IRIV IO Controller | [`iriv-io-controller.md`](iriv-io-controller.md) | `IRIV-IOC` | Raspberry Pi RP2350A (microcontroller, no Linux) | Datasheet Rev 1.0, Jul 2024 | **Medium-high** |
| IRIV IOC MQTT Gateway | [`iriv-ioc-mqtt-gateway.md`](iriv-ioc-mqtt-gateway.md) | `IRIV-IOC-MQTT` | Same hardware as IO Controller + factory MQTT firmware | Datasheet Rev 1.0, Jun 2026 | **Medium-high** |
| IRIV SmartHub CM5 | [`iriv-smarthub-cm5.md`](iriv-smarthub-cm5.md) | `IRIV-SH5` | Raspberry Pi CM5 (BCM2712) | User Manual Rev 1.3, Dec 2025 | **Medium-high** |
| IRIV EdgeAI CM5 | [`iriv-edgeai-cm5.md`](iriv-edgeai-cm5.md) | `IRIV-EDGEAI-CM5` | Raspberry Pi CM5 (BCM2712) + AI HAT+ | Datasheet Rev 1.0, Jul 2025 | **Medium-high** |
| IRIV EdgeAI Safety Box Kit | [`iriv-edgeai-safety-box-kit.md`](iriv-edgeai-safety-box-kit.md) | `KIT-IRIV-EAI-PPE` | IRIV EdgeAI CM5 (8GB/32GB) + Hailo-8 26 TOPS | **No kit datasheet exists.** Live product page + Quick Start Guide (Aug 2026) + EdgeAI CM5 Datasheet Rev 1.0 | **Medium** |
| IRIV PiControl Industry 4.0 Agribox | [`iriv-picontrol-agribox.md`](iriv-picontrol-agribox.md) | `KIT-IRIV-AGRBX2` | IRIV PiControl CM4 (4GB/32GB) + IRIV IO Controller (RP2350) | Product page + team-named Agribox tutorial + Node-RED flows on GitHub | **Medium** |

**Source rule for IRIV (16 Oct 2026): the datasheet is the main source.** User manuals rank second ([UM]); where a newer manual disagrees, the datasheet still wins in the text and the conflict is listed for engineering.

IRIV notes for every agent:
- **IO Controller is not a Raspberry Pi computer.** No Raspberry Pi OS or Node-RED on the device.
- **IOC MQTT Gateway firmware must not be overwritten** — no CircuitPython/UF2 steps; setup is via USB-C web page at 10.0.0.1. Plain MQTT on port 1883, no TLS on the device.
- **PiControl CM4, PiControl CM5 and EdgeAI CM5 RS485 is a USB serial device (`/dev/ttyACM*`)**, not a GPIO UART.
- **mini PCIe sockets on PiControl CM4, PiControl CM5, SmartHub CM5 and EdgeAI CM5 carry USB 2.0 only** (no PCIe). M.2 = NVMe only, no SATA.
- **Bare "IRIV PiControl" is ambiguous** between CM4 (`IRIV-PICL`) and CM5 (`IRIV-PICL5`); the shared datasheet code `IRIV-PICONTROL` covers both.
- **Safety Box Kit is not a certified safety system**, detects helmets and vests only, needs RTSP IP cameras (not included), and its "up to 6 cameras" holds only for 640x360 sub-streams at 15–25 FPS. No accuracy figure exists — "96% compliant" in marketing is an example dashboard reading.
- **Bare "IRIV SmartHub" is ambiguous** with the SmartHub dashboard feature of EdgeAI. Always use the full name.

### Industrial networking (Teltonika)

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Teltonika RUT200 | [`teltonika-rut200.md`](teltonika-rut200.md) | `RUT200` | Compact single-SIM 4G LTE Cat 4 router, 2 Ethernet, Wi-Fi 4, DI/DO on the power plug | Teltonika product page technical spec (datasheet 2026-09-24) + Cytron page | **Medium** |
| Teltonika RUT140 | [`teltonika-rut140.md`](teltonika-rut140.md) | `RUT140` | Industrial Ethernet/Wi-Fi router (no cellular), 3-pin 9–30 VDC terminal, DIN bracket | Teltonika product page technical spec (datasheet 2026-09-29) + Cytron page | **Medium** |
| Teltonika RUT901 | [`teltonika-rut901.md`](teltonika-rut901.md) | `RUT901` | Dual-SIM 4G LTE Cat 4 router, 4 Ethernet, Wi-Fi 4; no GNSS/serial/USB (vs RUT906) | Teltonika product page technical spec (datasheet 2026-09-24) + Cytron page | **Medium** |
| Teltonika RUT906 | [`teltonika-rut906.md`](teltonika-rut906.md) | `RUT906` | Dual-SIM 4G LTE Cat 4 router with GNSS, RS232, RS485, USB, 10-pin I/O, 4 Ethernet, Wi-Fi 4 | Teltonika product page technical spec (datasheet 2026-09-24) + Cytron page | **Medium** |
| Teltonika RUT956 | [`teltonika-rut956.md`](teltonika-rut956.md) | `RUT956` | Dual-SIM 4G router with Wi-Fi, GNSS, RS232/RS485 and 10-pin I/O | Teltonika product page technical spec (datasheet 2026-09-24) + Cytron page | **Medium** |
| Teltonika RUTX50 | [`teltonika-rutx50.md`](teltonika-rutx50.md) | `RUTX50` | 5G dual-SIM router, 5× Gigabit Ethernet, Wi-Fi 5, GNSS; no serial port | Teltonika product page technical spec (datasheet 2026-09-25) + Cytron page | **Medium** |
| Teltonika OTD140 | [`teltonika-otd140.md`](teltonika-otd140.md) | `OTD140` | IP55 outdoor 4G router, 802.3af/at PoE-in + 15 W PoE-out, internal antennas | Teltonika product page technical spec (datasheet 2026-09-24) + Cytron page | **Medium** |
| Teltonika TRB140 | [`teltonika-trb140.md`](teltonika-trb140.md) | `TRB140` | Compact 4G-to-Gigabit-Ethernet gateway with 1 DI / 1 DO on the power plug | Teltonika product page technical spec (datasheet 2026-09-30) + Cytron page | **Medium** |
| Teltonika TSW101 | [`teltonika-tsw101.md`](teltonika-tsw101.md) | `TSW101` | Unmanaged automotive 5-port Gigabit switch, 4× PoE+ (60 W total), 9–30 VDC | Teltonika product page technical spec (datasheet 2026-09-30) + Cytron page | **Medium** |
| Teltonika TSW202 | [`teltonika-tsw202.md`](teltonika-tsw202.md) | `TSW202` | Managed 8-port Gigabit PoE+ switch (240 W) with 2× SFP, TSWOS; PoE needs 44–57 VDC input | Teltonika product page technical spec (datasheet 2026-09-30) + Cytron page | **Medium** |
| Teltonika DIN Rail Kit | [`teltonika-din-rail-kit.md`](teltonika-din-rail-kit.md) | `PR5MEC00` | Steel 35 mm DIN-rail bracket for Teltonika routers and switches | Teltonika accessory page technical data + Cytron page | **Medium** |
| Teltonika 4G Magnetic SMA Antenna | [`teltonika-4g-magnetic-sma-antenna.md`](teltonika-4g-magnetic-sma-antenna.md) | `PR1KS210` | Magnetic-base mobile antenna, 699–868 / 1850–2690 MHz, 3 m RG174, SMA male | Teltonika accessory page technical data + Cytron page | **Medium-high** |

**Distributed brand (added 21 Oct 2026):** Teltonika Networks is the manufacturer; Cytron distributes these products in Malaysia (https://my.cytron.io/m-teltonika). Authority for these files: Teltonika datasheet / technical specification [DS] > Teltonika Wiki [UM] > Cytron product page [PP]. The Cytron page is used for price, stock, packing, options and warranty; where it disagrees with Teltonika the conflict is listed in the product file.

Teltonika notes for every agent:
- **Teltonika Wiki (wiki.teltonika-networks.com) was blocked by a Cloudflare check on 21 Oct 2026**, so power-socket pin order, I/O and RS485 pin numbers, LED meanings and default LAN IP are still to be read for every model — check the Wiki before giving wiring steps.
- **DIN Rail Kit (PR5MEC00)** is listed by Teltonika for RUT200, RUT901, RUT906, RUT956, RUTX50, TRB140, TSW101 — not RUT140 (built-in bracket), OTD140 or TSW202 (built-in bracket).
- **4G Magnetic SMA Antenna (PR1KS210)** is listed for RUT200, RUT901, RUT906, RUT956, TRB140 — not RUTX50, RUT140 or OTD140; it does not cover 900 MHz (B8).
- Several Cytron pages carry copy errors (3G 42 Mbps vs Teltonika 21 Mbps, eSIM "optional" on non-eSIM order codes, RUT956 packing list says "RUT906", dead datasheet links for RUT956 and TSW101, OTD140 weight 855 g vs 315 g) — see each file's *Conflicts*.

### LoRaWAN and IoT (Milesight)

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Milesight UG65 LoRaWAN Gateway | [`milesight-ug65.md`](milesight-ug65.md) | `UG65` | 8-channel IP65 LoRaWAN gateway with built-in network server, PoE, optional 4G | Milesight UG65 datasheet + user guide V2.14 + quick guide V2.5 | **Medium-high** |
| Milesight UG56 LoRaWAN Gateway | [`milesight-ug56.md`](milesight-ug56.md) | `UG56` | 8-channel IP30 metal LoRaWAN gateway, PoE or USB-C power, no cellular | Milesight UG56 datasheet + quick guide V1.5 | **Medium-high** |
| Milesight UG67 Outdoor LoRaWAN Gateway | [`milesight-ug67.md`](milesight-ug67.md) | `UG67` | 8-channel IP67 outdoor LoRaWAN gateway with 4G, GNSS, PoE or 6–12 V M12 power | Milesight UG67 datasheet + quick guide V1.7 | **Medium-high** |
| Milesight GA01 Fiber Glass S-N Antenna Kit | [`milesight-ga01.md`](milesight-ga01.md) | `FSN600` | 60 cm fiber-glass LoRa antenna with SMA–N cable for UG56 (not UG65/UG67) | Milesight accessories guide (web) | **Medium** |
| Milesight FT101 LoRaWAN Field Tester | [`milesight-ft101.md`](milesight-ft101.md) | `FT101` | Handheld Android LoRaWAN signal and coverage tester | Milesight FT101 datasheet + user guide V1.1 | **Medium-high** |
| Milesight UR32 Lite Series Router | [`milesight-ur32.md`](milesight-ur32.md) | `UR32L / UR32S` | Pocket 4G Cat 4 router (UR32 Lite), 2 Ethernet, UR32S adds Wi-Fi; no serial/I/O | Milesight UR32L/UR32S datasheets + UR32L quick guide | **Medium** |
| Milesight UR35 Industrial Router | [`milesight-ur35.md`](milesight-ur35.md) | `UR35` | Dual-SIM 4G router, 5 Ethernet, RS232+RS485, DI/DO, optional Wi-Fi/PoE | Milesight UR35 datasheet + quick guide V2.3 | **Medium-high** |
| Milesight UR41 Mini Industrial Router | [`milesight-ur41.md`](milesight-ur41.md) | `UR41` | Mini 4G Cat 4 router with GNSS, 1 LAN, RS232/RS485, DI/DO, low-power standby | Milesight UR41(L) datasheet + user guide V1.6 | **Medium** |
| Milesight UC100 IoT Controller | [`milesight-uc100.md`](milesight-uc100.md) | `UC100` | Modbus RS485 to LoRaWAN converter | UC100 datasheet + user guide V2.0 | **Medium** |
| Milesight UC300 IoT Controller | [`milesight-uc300.md`](milesight-uc300.md) | `UC300` | Multi-I/O industrial IoT controller (LoRaWAN/4G) | UC300 datasheet + LoRaWAN user guide | **Medium** |
| Milesight UC501 Multi-Interface Controller | [`milesight-uc501.md`](milesight-uc501.md) | `UC501` | Solar IP68 LoRaWAN multi-interface controller | UC50x datasheet + user guide | **Medium-high** |
| Milesight UC502 Multi-Interface Controller | [`milesight-uc502.md`](milesight-uc502.md) | `UC502` | Battery IP68 LoRaWAN multi-interface controller | UC50x datasheet + user guide | **Medium-high** |
| Milesight UC512 Solenoid Valve Controller | [`milesight-uc512.md`](milesight-uc512.md) | `UC512` | LoRaWAN controller for 2 DC 12 V latching valves | UC51x datasheet + user guide V4.3 | **Medium-high** |
| Milesight WS558-LN Smart Light Controller | [`milesight-ws558-ln.md`](milesight-ws558-ln.md) | `WS558-LN` | 8-output mains LoRaWAN light controller | WS558 datasheet + user guide | **Medium** |
| Milesight WS50x Smart Wall Switch | [`milesight-ws50x.md`](milesight-ws50x.md) | `WS501 / WS502` | 1/2-gang LoRaWAN smart wall switch (neutral required) | WS50x datasheet + user guide V1.3 | **Medium-high** |
| Milesight WT304 Smart Fan Coil Thermostat | [`milesight-wt304.md`](milesight-wt304.md) | `WT304` | LoRaWAN fan-coil thermostat with e-ink display | WT303/304 datasheet + WT30x user guide | **Medium** |
| Milesight CT Series Smart Current Transformer | [`milesight-ct10x.md`](milesight-ct10x.md) | `V-LR-CT10X` | Self-powered LoRaWAN split-core current sensor (CT101/103/303/310) | Milesight CT10x + CT3xx datasheets and user guides V2.0 | **Medium-high** |
| Milesight CTH01 Smart Power Monitor Hub | [`milesight-cth01.md`](milesight-cth01.md) | `LR-CTH01` | 12-channel DIN-rail LoRaWAN energy/power-quality hub (CTs separate) | Milesight CTH01 datasheet + user guide V1.0 | **Medium-high** |
| Milesight RCT-RJ11 Split-core CTs for CTH01 | [`milesight-cth01-ct-clamps.md`](milesight-cth01-ct-clamps.md) | `V-LR-RCT` | RJ11 split-core current transformers for the CTH01 hub | CTH01 datasheet CT table + Cytron page | **Medium** |
| Milesight EM300-DI LoRaWAN Pulse Counter | [`milesight-em300-di.md`](milesight-em300-di.md) | `LR-EM300-DI` | Battery LoRaWAN pulse counter for reed-switch meters, with T/RH | Milesight EM300-DI datasheet + user guide V1.1 | **Medium-high** |
| Milesight EM320-TH Temperature & Humidity Sensor | [`milesight-em320-th.md`](milesight-em320-th.md) | `V-LR-EM320-TH` | Compact battery LoRaWAN temperature/humidity sensor (Standard/Magnetic) | Milesight EM320-TH datasheet + user guide V1.2 | **Medium-high** |
| Milesight EM300-TH Temperature & Humidity Sensor | [`milesight-em300-th.md`](milesight-em300-th.md) | `LR-EM300-TH` | Battery LoRaWAN temperature/humidity sensor, IP67 | Milesight EM300-TH datasheet + user guide V2.3 | **Medium-high** |
| Milesight LoRaWAN IAQ Sensor (AM102/103/307/308/319) | [`milesight-iaq-sensor.md`](milesight-iaq-sensor.md) | `V-LR-AM` | AM102/AM102L/AM103/AM307/AM308/AM319 indoor air-quality sensors | Milesight AM30x/AM319/AM102/AM103 datasheets + user guides | **Medium** |
| Milesight WTS506 LoRaWAN IoT Weather Station | [`milesight-wts506.md`](milesight-wts506.md) | `LR-WTS506` | Solar-powered all-in-one LoRaWAN weather station | Milesight WTS506 datasheet + user guide V1.1 | **Medium-high** |
| Milesight EM400-MUD Ultrasonic Distance Sensor | [`milesight-em400-mud.md`](milesight-em400-mud.md) | `EM400-MUD` | Ultrasonic distance/fill-level sensor for bins and parking | Milesight datasheet + user guide V1.1 | **Medium-high** |
| Milesight EM400-TLD ToF Laser Distance Sensor | [`milesight-em400-tld.md`](milesight-em400-tld.md) | `EM400-TLD` | ToF laser fill-level sensor for small bins | Milesight datasheet + user guide V1.1 | **Medium-high** |
| Milesight EM410-RDL Radar Distance / Level Sensor | [`milesight-em410-rdl.md`](milesight-em410-rdl.md) | `EM410-RDL` | 60 GHz radar distance/liquid-level sensor, external antenna | Milesight EM410-RDL datasheet + user guide V1.2 | **Medium-high** |
| Milesight EM500-UDL (W050/W100) | [`milesight-em500-udl.md`](milesight-em500-udl.md) | `EM500-UDL` | Ultrasonic level sensor; two Cytron listings W050 (0.3–5 m) and W100 (0.5–10 m) | Milesight datasheet + user guide V2.2.1 | **Medium-high** |
| Milesight EM500-PP Pipe Pressure Sensor | [`milesight-em500-pp.md`](milesight-em500-pp.md) | `EM500-PP` | Pipe pressure sensor 0–1600 kPa with SS316L probe | Milesight datasheet + user guide V2.2.1 | **Medium-high** |
| Milesight EM500-PT100 Industrial Temperature Sensor (T200) | [`milesight-em500-pt100.md`](milesight-em500-pt100.md) | `EM500-PT100` | PT100 RTD temperature sensor, T200 range | Milesight datasheet + user guide V2.2.1 | **Medium-high** |
| Milesight EM500-SMTC Soil Moisture, Temperature and EC Sensor | [`milesight-em500-smtc.md`](milesight-em500-smtc.md) | `EM500-SMTC` | Buried soil moisture/temperature/EC probe with EM500 transceiver | Milesight datasheet + user guide V2.3 | **Medium** |
| Milesight EM500-CO2 Carbon Dioxide Sensor (4 in 1) | [`milesight-em500-co2.md`](milesight-em500-co2.md) | `EM500-CO2` | Outdoor CO2, temperature, humidity and pressure sensor | Milesight datasheet + user guide V2.2.1 | **Medium-high** |
| Milesight VS121 AI Workplace Occupancy Sensor | [`milesight-vs121.md`](milesight-vs121.md) | `VS121` | AI vision workplace occupancy sensor, LoRaWAN Class C, USB-C powered | VS121 datasheet + user guide V2.0 | **Medium** |
| Milesight VS125 PoE AI Stereo Vision People Counter | [`milesight-vs125.md`](milesight-vs125.md) | `VS125-LW-P` | 3D stereo-vision AI people counter, PoE/Ethernet (no LoRaWAN), low-and-wide | VS125-LW datasheet + user guide V1.2 | **Medium** |
| Milesight VS135 Ultra ToF People Counter | [`milesight-vs135.md`](milesight-vs135.md) | `VS135` | ToF AI people counter, PoE+ or LoRaWAN builds, Standard / High Ceiling optics | VS135 datasheet + VS135-P and VS135 user guides V1.4 | **Medium** |
| Milesight VS330 Bathroom Occupancy Sensor | [`milesight-vs330.md`](milesight-vs330.md) | `VS330` | Battery LoRaWAN cubicle/bathroom occupancy sensor (PIR + ToF) | VS330 datasheet + user guide V1.0 | **Medium-high** |
| Milesight VS370 Radar Human Presence Sensor | [`milesight-vs370.md`](milesight-vs370.md) | `VS370` | Battery LoRaWAN mmWave radar + PIR presence sensor, wall mount | VS370 datasheet + user guide V1.1 | **Medium-high** |
| Milesight WS202 PIR & Light Sensor | [`milesight-ws202.md`](milesight-ws202.md) | `WS202` | Battery LoRaWAN PIR motion + light sensor | WS202 datasheet + user guide V1.3 | **Medium-high** |
| Milesight WS301 Magnetic Contact Switch | [`milesight-ws301.md`](milesight-ws301.md) | `WS301` | Battery LoRaWAN door/window contact switch with tamper | WS301 datasheet + user guide V1.4 | **Medium-high** |
| Milesight EM300-MCS Magnetic Contact Switch | [`milesight-em300-mcs.md`](milesight-em300-mcs.md) | `EM300-MCS` | IP67 LoRaWAN magnetic contact switch with temperature/humidity | EM300-MCS datasheet + user guide V2.3 | **Medium-high** |
| Milesight WS101 Smart Button | [`milesight-ws101.md`](milesight-ws101.md) | `WS101` | Battery LoRaWAN smart button, 3 press modes, D2D | WS101 datasheet + user guide V1.2 | **Medium-high** |
| Milesight EM300-SLD Spot Leak Detection Sensor | [`milesight-em300-sld.md`](milesight-em300-sld.md) | `LR-EM300-SLD` | LoRaWAN spot leak + T/H sensor, IP67, battery | Milesight datasheet + user guide V2.3 | **Medium-high** |
| Milesight EM300-ZLD Zone Leak Detection Sensor | [`milesight-em300-zld.md`](milesight-em300-zld.md) | `LR-EM300-ZLD` | LoRaWAN rope leak + T/H sensor, 3 m cable | Milesight datasheet + ZLD user guide V2.3 | **Medium-high** |
| Milesight GS301 Bathroom Odor Detector | [`milesight-gs301.md`](milesight-gs301.md) | `LR-GS301` | LoRaWAN NH3/H2S/T/H restroom odour detector | Milesight datasheet + user guide V1.1 | **Medium-high** |
| Milesight GS601 Vape Detector | [`milesight-gs601.md`](milesight-gs601.md) | `LR-GS601` | Ceiling LoRaWAN vape/smoke detector, USB-powered | Milesight datasheet + user guide V1.0 | **Medium-high** |
| Milesight AT101 Outdoor Asset Tracker | [`milesight-at101.md`](milesight-at101.md) | `LR-AT101` | LoRaWAN GNSS + Wi-Fi-scan tracker, IP67/IK09 | Milesight datasheet + user guide V1.0 | **Medium-high** |
| Milesight LoRaWAN Smart CoWork Kit | [`milesight-smart-cowork-kit.md`](milesight-smart-cowork-kit.md) | `LR-KIT-SC-A` | Smart-office LoRaWAN kit (iBox Kit-A) + 6-month IoT Cloud | Cytron page + iBox CoWork Kit-A datasheet | **Medium** |
| Milesight LoRaWAN Smart Building Kit | [`milesight-smart-building-kit.md`](milesight-smart-building-kit.md) | `LR-KIT-SB` | Smart-building LoRaWAN kit, 7 devices + 6-month IoT Cloud | Cytron page + iBox Smart Building datasheet | **Medium** |
| Milesight LoRaWAN Smart Agriculture Kit | [`milesight-smart-agriculture-kit.md`](milesight-smart-agriculture-kit.md) | `LR-KIT-SA` | Smart-farming kit: soil sensor, UC511 valve controller, gateway + 6-month IoT Cloud | Cytron page + iBox Agriculture Kit datasheet | **Medium** |
| Milesight LoRaWAN Indoor Air Quality Kit | [`milesight-iaq-kit.md`](milesight-iaq-kit.md) | `LR-KIT-IAQ` | IAQ kit: AM102/AM103/AM307/AM319 + UG56 + 6-month IoT Cloud | Cytron page + iBox IAQ Kit datasheet | **Medium** |

**Distributed brand (added 21 Oct 2026):** Milesight (Xiamen Milesight IoT Co., Ltd.) is the manufacturer; Cytron distributes these products in Malaysia (https://my.cytron.io/Milesight, 51 listings → 50 files; the two EM500-UDL listings W050/W100 share one file). Authority: Milesight datasheet [DS] > Milesight user guide [UM] > Cytron product page [PP]. Status (team decision, 21 Oct 2026): products whose Cytron page says "Availability: Enquiry" count as **Active (sold on enquiry)** even when the brand-page card shows OUT OF STOCK; only the 8 whose product page itself says Out Of Stock are Out of stock (CT10x, WS50x, VS125, VS135, UR32, UR35, UC501, UC502).

Milesight notes for every agent:
- **Frequency plan:** Cytron sells `-915M` hardware and states "Malaysia AS923-2, Singapore AS923-1" on most pages (CTH01 says AS923-1 in one place) — check the factory plan before deployment.
- **Gateways:** UG56 (IP30, PoE/USB-C, SMA LoRa), UG65 (IP65, N-female, optional 4G), UG67 (IP67 outdoor, 4G, M12 6–12 V or PoE). The **GA01** antenna kit (SMA–N) fits the **UG56 only**.
- **Routers:** Cytron's "UR32 Series" is the **UR32 Lite** (UR32L/UR32S) — no serial, I/O or GNSS. UR35 has RS232+RS485+DI/DO on an 8-pin terminal; **UR41 power-pin location conflicts** between datasheet (2-pin block) and user guide (pins 4/8 of the 8-pin plug) — check the unit label.
- **Kits** list components without quantities or frequency plan; the Smart Agriculture Kit's **UC511 is not the UC512**; VS340, DS3604 and WS303 kit parts are not in the KB.
- **CT products:** follow the CTH01 guide (power off and lock out before installing); Cytron's "install on live circuits" wording is contradicted by the guide.
- Many Cytron pages carry spec errors (Tx power, battery capacity, IP rating, warranty 12 months vs Milesight 3 years) — see each file's *Conflicts*.

### Workshops and services

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| AI Agent Workshop for RPI 5 | [`ai-agent-workshop-rpi5.md`](ai-agent-workshop-rpi5.md) | `V-AI-AGT-RPI` | 2-day AgentBox (Pi 5 local AI agent hub) workshop + kit | Course outline (no date) + product page | **Medium** |
| Jetson Orin Nano AI Fundamentals Workshop | [`jetson-orin-nano-workshop.md`](jetson-orin-nano-workshop.md) | `V-TW-JNORNN-NVIDIA` | 1-day workshop, NVIDIA certification; kit = Orin Nano Super 8GB + 512 GB JetPack SSD | Tentative timetable + product page | **Medium** |
| Cytron Raspbot Workshop | [`raspbot-workshop.md`](raspbot-workshop.md) | `V-TRAINING-AI` | 1-day Edge AI workshop with Raspbot (Pi 5), max 5 pax, HQ Penang | Workshop tentative + product page | **Medium-high** |
| Flash JetPack / Orin Nano Upgrade Service | [`jetpack-flash-service.md`](jetpack-flash-service.md) | `SEV-JN-ORNN` | Software-only JetPack 5.x → 6.x flash, RM150 by enquiry | Product page | **Medium** |
| IRIV PiControl Industry 4.0 Workshop | [`iriv-picontrol-industry40-workshop.md`](iriv-picontrol-industry40-workshop.md) | `V-KIT-IRIV` | 2-day Node-RED/RS485/MQTT workshop + IRIV PiControl CM4 (2GB/16GB) training kit; HQ max 5 or on-site min 3 pax | Product page + workshop brochures (2025) | **Medium** |
| IRIV EdgeAI Industry 4.0 Training | [`iriv-edgeai-vision-training.md`](iriv-edgeai-vision-training.md) | `V-KIT-IRIV-EAI` | 2-day Edge AI vision workshop + kit: IRIV EdgeAI CM5 8GB/32GB 13 TOPS, USB camera, RS485 meter/sensor; Windows laptop | Product page + workshop landing page + team confirmation + DRB-HICOM example run | **Medium** |

- **IRIV training kits:** the PiControl Industry 4.0 Workshop kit is a PiControl **CM4** (2GB/16GB wireless); the EdgeAI Industry 4.0 Training kit is an EdgeAI CM5 8GB/32GB at **13 TOPS** (not 26). Both are 2-day courses; participants keep the kit. The Agribox (IRIV industrial series) is a PiControl CM4 4GB/32GB + IRIV IO Controller kit; who provides MyAgritech and its terms are not stated.
- **Workshop dates are purchase variants and expire** — re-check the page before quoting one; several listed dates had passed on 2026-10-19. Only the Raspbot workshop states a participant cap, meals and a certificate.
## Quick cross-product facts (ESP32 family)

| | Maker ESP32 | Robo ESP32 | Maker Feather AIoT S3 |
|---|---|---|---|
| USB | USB-C, CH9102F | none (uses host board) | USB-C, native USB (no bridge) |
| Arduino board | ESP32 Dev Module | ESP32 Dev Module (host) | Cytron Maker Feather AIoT S3 |
| Flash / PSRAM | 8 MB / — | — | 8 MB / 8 MB octal |
| Onboard LED pin | 14 LEDs (incl. GPIO2) | NeoPixel ×2 on GPIO15 | GPIO2 + RGB on GPIO46 |
| Buzzer | GPIO26 | GPIO23 | GPIO12 |
| User button | GPIO4 | GPIO34, 35 | GPIO3 |
| I2C port | Maker Port 21/22 | Grove 2 + Maker Port 21/22 | Maker Port 42/41 |
| Analog safe with Wi-Fi | ADC1: 32–39 | Grove 4–7 (33, 32, 39, 36) | GPIO4–10 (A0–A5, A7) |

## How to add or update a product

1. Check it is a Cytron-brand product (or a distributed brand the team has approved, e.g. Teltonika, Milesight). Then copy `_TEMPLATE.md` to `<product-slug>.md`.
2. Start from the main source for the product type (rule 7: datasheet for boards; guide book for education kits; board datasheet + guide book/tutorial for robot kits). Tag every fact with its source. Put conflicts and unconfirmed items in their sections — don't drop them.
3. Fill `fact-sheets/<product-slug>.md` in the Content Hub template from that reference (only what it states), and add it to `fact-sheets/ALL-fact-sheets.md`. Check the aliases don't clash with another product.
4. Add the row to *Products* above with an honest confidence level.
5. Commit to this repository with a message like `kb: add <product>`.
6. When the design team confirms something, mark it [DT] with the date and remove it from *Needs verification*.

