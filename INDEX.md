# Cytron Product Knowledge Base

Verified product facts for **Cytron-brand products**, written for AI agents (tutorial, article and script writers) and for the people who check their output. Every fact is tagged with its source; anything a source doesn't state is marked as not stated rather than guessed.

**Start here:** read this index, then load only the product files a task needs.

**Scope: Cytron-brand products only.** Third-party boards and modules that Cytron resells are not covered here.

This is the public edition. Internal working notes (internal document links, pricing sources, unreleased products and the open-issues log) are kept privately by the Cytron marketing team.

## Rules for any agent using this KB

1. **Only state a spec that is in a product file.** If it isn't there, say it's unconfirmed — never fill the gap from memory or a reseller page.
3. **Read the *Conflicts* and *Needs verification* sections** before writing about a product. Anything listed under *Needs verification* must not appear as fact in published content.
4. **Pin rules are hard rules.** Code and wiring must follow each file's "Pin rules and gotchas".
6. **Dated facts** (price, stock, store list) must be re-checked on the live page before going public.
7. **Source rule by product type (decided 19 Oct 2026):**
   - **Boards, shields, sensors, motor drivers, controllers:** the Cytron datasheet is the main source (rule 2).
   - **Education kits** (e.g. EDU:BIT, Maker UNO Learning Box): the Cytron **guide book** is the main source. Students and teachers follow the book, so a datasheet is **not required** and its absence does not lower confidence. Electrical limits the book does not give stay "not stated"; for power, say "use the supplied cable / power source".
   - **Robot and project kits** (e.g. SUMO:BIT Robot Kit, Robot Battle, SOCCER:BIT, Ikedo kits): the **board inside follows its own datasheet** — link to the board's KB file, never re-document it. The **kit accessories, assembly and lessons** use the Cytron **guide book or guide tutorial** as the main source; no accessory datasheet is required.

## How the KB is arranged (two layers)

| Layer | Folder | Format | Use it for |
|---|---|---|---|
| **1. Product fact sheets** | `fact-sheets/` | Cytron Content Hub "Product fact sheets" form: 13 fixed headings, source-only facts, `[NOT STATED]` where the source is silent | Pasting into the Content Hub; marketing, scripts and articles; the first thing any agent reads |
| **2. Detailed references** | this folder (`<product>.md`) | Source-tagged reference with pin maps, conflicts and *Needs verification* | Writing code, wiring and tutorials; checking where a fact came from |

`fact-sheets/ALL-fact-sheets.md` holds every sheet in one file, ready to paste. A fact sheet must never say more than its detailed reference. When a reference changes, update the matching fact sheet in the same edit.

Fact sheet rules (from the Content Hub form): use only what the source states; keep numbers, units and names exactly; `[NOT STATED]` for anything missing; keep every heading in order; keep every stated limitation; marketing language only under *Positioning*; when product page and datasheet disagree give both with their source; price only if a source states one; each alias belongs to one product only.

## Products

### Maker ESP32 family (ESP32 ecosystem)

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker ESP32 | [`maker-esp32.md`](maker-esp32.md) | `MAKER-ESP32` | ESP32 (WROOM-32E-N8) | Active, launched Sep 2026 | **High** |
| Robo ESP32 | [`robo-esp32.md`](robo-esp32.md) | `ROBO-ESP32` | None onboard — hosts a 30-pin NodeMCU ESP32 / Maker ESP32 | Active (Datasheet Rev 1.1, Feb 2026) | **Medium** |
| Maker Feather AIoT S3 | [`maker-feather-aiot-s3.md`](maker-feather-aiot-s3.md) | `MAKER-FEATHER-AIOT-S3` (+`-H`) | ESP32-S3 (WROOM-1-N8R8) | Active | **Medium-high** |

### Arduino-compatible boards

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker UNO | [`maker-uno.md`](maker-uno.md) | `MAKER-UNO` | ATmega328P + CH340G | User's Manual Rev 1.0, Dec 2017 (no datasheet) | **Medium** |
| Maker UNO Plus | [`maker-uno-plus.md`](maker-uno-plus.md) | `MAKER-UNO-PLUS` | ATmega328P + **FT231X** (not CH340) | User's Manual Rev 1.0, Oct 2018 (no datasheet) | **Medium** |
| Maker UNO X | [`maker-uno-x.md`](maker-uno-x.md) | `MAKER-UNO-X` | ATmega328P + CH340-family USB chip (page: "CH9340") | Guide book v1.5, Feb 2023 + product page (no datasheet) | **Medium** |
| Maker Nano | [`maker-nano.md`](maker-nano.md) | `MAKER-NANO` | ATmega328P + **CH340C** | Datasheet Rev 1.0, Jun 2020 + product-page comparison table, pinout and dimension images | **Medium-high** |
| Cytron UNO | [`cytron-uno.md`](cytron-uno.md) | `CT-UNO` | ATmega328P + **FT231X** | User's Manual V1.0, Nov 2014 (no datasheet) | **Medium-high** |
| Cytron UNO Special Edition | [`cytron-uno-se.md`](cytron-uno-se.md) | `CT-UNO-SE` | ATmega328P + **FT231X** (same as CT-UNO) | Product page (CT-UNO + side connectors) + CT-UNO manual | **Medium-high** |
| Maker Uno RP2040 | [`maker-uno-rp2040.md`](maker-uno-rp2040.md) | `MAKER-UNO-RP2040` | RP2040, 2 MB flash | Datasheet Rev 1.0, Feb 2024 | **Medium-high** |
| Maker Nano RP2040 | [`maker-nano-rp2040.md`](maker-nano-rp2040.md) | `MAKER-NANO-RP2040` | RP2040 | Datasheet Rev 1.1, Jul 2024 | **Medium** |
| Robo Uno Shield | [`robo-uno-shield.md`](robo-uno-shield.md) | `SHIELD-ROBO-UNO` | None — shield for UNO-form-factor boards | Datasheet Rev 1.0, Feb 2025 | **Medium** |

Arduino-board notes for every agent:
- **Maker UNO has no DC jack and no VIN** — USB Micro-B 4.8–5.2 V only. Select "Arduino Uno" in the IDE; CH340 driver needed.
- **Maker Uno RP2040 is 3.3 V logic** — only 3.3 V-compatible UNO shields; power from USB-C or 1-cell LiPo (3.6–6 V); code uses GP numbers, not UNO D-numbers.
- **Robo Uno Shield:** 3.6–6 V single-cell input only; cannot be powered from the Arduino VIN pin; its micro-USB charges/powers the shield only (no code upload). Follow Cytron's code for motor pins (`CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);`) until the design team resolves the datasheet conflict. Grove 4 and the Maker Port share A4/A5; buttons D2/D3 are the Grove 6 pins.
- **USB-serial chips differ:** Maker UNO = CH340; **Maker UNO Plus and Cytron UNO = FTDI FT231X** (use the FTDI driver, not Maker UNO's CH340 steps). **Maker Nano = CH340C** (CH34X driver; Cytron comparison table).
- **Maker UNO Plus is USB-only** (4.8–5.2 V; no DC jack, no Vin, no 5 V regulator); button D2 needs `INPUT_PULLUP`; buzzer D8 with mute switch; LEDs on pins 2–13.
- **Maker UNO X:** USB Micro-B only (no DC jack or Vin named); the built-in LEDs and buzzer (D8) work only with the **Debug** switch on — switch Debug off to use D8 for something else; button D2 needs `INPUT_PULLUP`; USB driver does not support Windows 7.
- **Maker Nano power:** Vin 7.0–30.0 V, but the 5V pin gives only **100 mA** and 3V3 only **50 mA** (including the board's own use) — never copy Maker UNO's 500 mA. D2–D13 LEDs light whenever the pin is high (cut a trace to disable). A6/A7 are analog-only. IDE board: "Arduino Nano".
- **Cytron UNO:** DC jack 7–15 V recommended (6–20 V absolute); 5 V regulator 1 A max only stated "with Vin at 12V"; 3.3 V 500 mA; select "Arduino Uno"; one user LED (D13), no button or buzzer. **Cytron UNO Special Edition (CT-UNO-SE)** is the same board with special side connectors for stacking on top of or under a shield (product page, 19 Oct 2026).

### Arduino shields (non-motor)

| Product | File | Code | Function | Primary source | Confidence |
|---|---|---|---|---|---|
| Cytron PS2 Shield | [`shield-ps2.md`](shield-ps2.md) | `SHIELD-PS2` | PS2 controller interface over UART | User's Manual V1.0, Sep 2013 (no datasheet) | **Medium** |
| Cytron ESP8266 WiFi Shield | [`shield-esp-wifi.md`](shield-esp-wifi.md) | `SHIELD-ESP-WIFI` (Rev 2.0) | ESP-WROOM-02 Wi-Fi over UART + microSD | User's Manual Rev2.0 V2.1, Aug 2021 (no datasheet) | **Medium** |
| LiPo Power Shield | [`shield-lipo.md`](shield-lipo.md) | `SHIELD-LIPO` | 1-cell LiPo power + charger shield | User's Manual V1.0, Jan 2016 (no datasheet) | **Medium** |
| 8 Channels RC Servo Controller Shield | [`shield-servo.md`](shield-servo.md) | `SHIELD-SERVO` | 8-ch servo controller shield, 7–25 V in, 5 V 4 A/5 A peak out | User's Manual V1.1, Apr 2018 (no datasheet) | **Medium** |
| Cytron Screw Terminal Shield | [`shield-screw2.md`](shield-screw2.md) | `SHIELD-SCREW2` | Screw-terminal + proto-area shield, 3.5 mm pitch | Getting Started Guide V1.0, Jan 2015 | **Medium-low** |
| Cytron Prototyping Shield | [`shield-proto2.md`](shield-proto2.md) | `SHIELD-PROTO2` | Proto shield, UNO R3 / Leonardo, stackable headers, reset button, 1 LED | Product page only | **Medium-low** |

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
| Maker UNO Edu Kit | [`maker-uno-edu-kit.md`](maker-uno-edu-kit.md) | `V-KIT-MUNO-EDU` | Maker UNO + components kit for classes (School Package 10+1) | Getting Started Module PDF + Teacher Guidebook (no version/date) | **Medium-low** |
| Maker UNO Learning Box | [`maker-uno-learning-box.md`](maker-uno-learning-box.md) | `KIT-MAKER-UNO-START` | Maker UNO + parts for 17 projects / 7 lessons | Product page (Beginner Guide PDF host blocked) | **Medium** |
| PikaBot | [`pikabot.md`](pikabot.md) | `V-KIT-PIKABOT` | Maker UNO + Maker Drive smart-car kit, Arduino IDE or mBlock booklet | PikaBot booklet (image-only) + Cytron PikaBot Resources doc with code | **Medium** |
| Maker Uno X Learning Guide (book) | [`maker-uno-x-learning-guide.md`](maker-uno-x-learning-guide.md) | `BOK-MUNOX` | Printed 17-project guide for the Maker UNO X Learning Box | Guide v1.5, Feb 2023 (read to Lesson 6) | **Medium** |

Arduino-kit notes for every agent:
- **PikaBot pins (Cytron code):** left motor D11/D10, right D9/D3 (`PWM_PWM`), ultrasonic TRIG D5 / ECHO D4, IR left A0 / right A1 (LOW = white, HIGH = black), start button D2, buzzer D8. Sensors are generic IR modules and HC-SR04, not Maker Line / Maker Object. Maker UNO has no DC jack/Vin — the battery feeds Maker Drive.
- **Edu Kit vs Learning Box contents differ** (Learning Box: IR sensor, SR04, 1N4007, 2× 2N2222, 10/10/10 resistors). The Edu Kit packing list is not in any Cytron text — don't publish a list.
- **Maker UNO X guide wiring is for the X board** (it has a Debug switch the plain Maker UNO lacks); don't apply its pin notes to the Maker UNO Learning Box without checking.

### Raspberry Pi Pico, RP2040 and RP2350 boards (Robo, Maker Pi, MOTION, EDU PICO)

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Robo Pico | [`robo-pico.md`](robo-pico.md) | `ROBO-PICO` | None onboard — hosts a Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Apr 2023 | **Medium** |
| EDU PICO V2 | [`edu-pico-v2.md`](edu-pico-v2.md) | `EDU-PICO2` (`EDU-PICO2-NB` = no Pico) | Raspberry Pi Pico 2 W | Datasheet Rev 1.1, Jun 2026 | **Medium** |
| Maker Pi RP2040 | [`maker-pi-rp2040.md`](maker-pi-rp2040.md) | `MAKER-PI-RP2040` | RP2040 soldered on (no Pico socket) | Datasheet Rev 1.2, Jan 2022 | **Medium-high** |
| Maker Pi Pico | [`maker-pi-pico.md`](maker-pi-pico.md) | `MAKER-PI-PICO` (`MAKER-PI-PICO-NB` = Maker Pi Pico Base, no Pico) | Raspberry Pi Pico soldered on | Datasheet Rev 1.2, Mar 2021 | **Medium-high** |
| Maker Pi Pico Mini | [`maker-pi-pico-mini.md`](maker-pi-pico-mini.md) | `MAKER-PI-PICO-MINI` (`-NB` = socket, no Pico) | Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Jun 2022 | **Medium-high** |
| MOTION 2350 Pro | [`motion-2350-pro.md`](motion-2350-pro.md) | Not stated (mirrors use `MOTION-2350-PRO`) | RP2350 | Datasheet **Rev 2.0, Sep 2025** | **Medium** |

Pico / RP2040 / RP2350 notes for every agent:
- **MOTION 2350 Pro Rev 2.0 motors are 5 A continuous / 10 A peak per channel**, with over-current, 150 ℃ thermal and >18 V input shutdown. 3 A (and "no over-current protection") is the Rev 1.0 board — don't use 3 A for the current board. Motors GP8–GP15, servos GP0–GP7, buttons GP20/GP21, buzzer GP22, 2 RGB LEDs GP23; Arduino `LED_BUILTIN` = GP2 (a servo pin). Never publish the datasheet's "VIN = VADC / 6.1" until the design team confirms it.
- **Maker Pi RP2040 brake/coast:** High/High = coast, Low/Low = brake (datasheet). In CircuitPython `throttle = 0` coasts and `throttle = None` brakes — the opposite of Cytron's demo comments. Power 3.6–6 V (USB, LiPo or VIN); motor/servo voltage = input voltage.
- **Maker Pi Pico is USB-powered only** (4.5–5.5 V; no battery or VIN). GP18 drives both the buzzer and the left audio channel (mute the buzzer when using the jack); audio is not amplified. RGB: Maker Pi RP2040 = 2× WS2812B on GP18; Maker Pi Pico = 1× WS2812B on GP28.
- **Maker Pi Pico Mini Maker Ports are JST-SH (Qwiic/STEMMA QT)**, not Grove (Grove needs a conversion cable); the GP0/GP1 and GP4/GP5 ports both sit on I2C0. No audio jack, microSD, ESP-01 socket or mute switch (unlike Maker Pi Pico).

### Pico / RP2040 project bundles

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Nano RP2040 Getting Started Bundles | [`maker-nano-rp2040-bundles.md`](maker-nano-rp2040-bundles.md) | `V-MN2040` | Board + parts bundle; Getting Started / Blynk IoT variants | Getting Started docs (2022–2023, no version) | **Medium** |
| DIY Fire Detection and Suppression (Pico) | [`diy-fire-detection-pico.md`](diy-fire-detection-pico.md) | `PR-DIY-FIRE-PICO` | Project kit: Pico + flame sensor + pump, CircuitPython | Cytron tutorial (Nov 2023) + product page | **Medium-low** |

- **Maker Nano RP2040 + Grove WiFi 8266:** power the Grove WiFi from 5 V, not 3.3 V (the Blynk doc says 3.3 V is not enough). The Blynk doc's sample code carries a template ID — never copy it. Board facts live in `maker-nano-rp2040.md`.

### micro:bit accessories

| Product | File | Code | Role | Primary source | Confidence |
|---|---|---|---|---|---|
| MOTION:BIT | [`motion-bit.md`](motion-bit.md) | `MOTION-BIT` | Motor + servo expansion board, 3.6–6 V | Datasheet Rev 1.0, Feb 2023 | **Medium** |
| MOTION:BIT Pro | [`motion-bit-pro.md`](motion-bit-pro.md) | `MOTION-BIT-PRO` | Motor + servo expansion board, 7–12 V | Datasheet Rev 1.0, Apr 2024 | **Medium** |
| SUMO:BIT | [`sumo-bit.md`](sumo-bit.md) | Not stated | Sumo robot controller; needs 2× MD13S | Datasheet Rev 1.0, Dec 2024 (RobotShop mirror) | **Medium** |
| REKA:BIT | [`reka-bit.md`](reka-bit.md) | Not stated (resellers: `REKABIT-NB`) | Robotics expansion board, 3.6–6 V | Datasheet Rev 1.0, Apr 2021 | **Medium** |
| ZOOM:BIT | [`zoom-bit.md`](zoom-bit.md) | Not stated | Robot car kit built on REKA:BIT | Quick Start Guidebook v1.1, 2022 (no datasheet) + REKA:BIT datasheet | **Medium** |
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
| REKA:BIT RBT Project Kit | [`rekabit-rbt-project-kit.md`](rekabit-rbt-project-kit.md) | `V-KIT-REKABIT-RBT` | RBT Y5/Y6 kit: REKA:BIT + 7 components, 5 projects | Quick Start Guide (Malay, v1.0) + resource hub + pxt-rekabit-rbt-project-kit | **Medium** |
| Auto Plant Watering Kit | [`auto-plant-watering-kit.md`](auto-plant-watering-kit.md) | `V-KIT-RBT-APW` | REKA:BIT + soil sensor + pump + servo; IoT option adds Grove WiFi 8266 | Lesson Guide (English, Apr 2022) | **Medium-high** |
| BEETLE:BIT | [`beetlebit.md`](beetlebit.md) | `V-BEETLEBIT` | REKA:BIT gripper robot car, 7 chapters | Resource hub + MakeCode chapter programs (booklet PDF is image-only) | **Medium** |
| STRIKER:BIT | [`strikerbit.md`](strikerbit.md) | `V-STRIKERBIT` | 4-robot classroom soccer kit on MOTION:BIT + Robo Base Mini | Scoring sheet + product page (booklet PDF image-only) | **Medium-low** |
| SUMO:BIT Robot Kit (1 kg) | [`sumobit-robot-kit.md`](sumobit-robot-kit.md) | `V-KIT-SUMOBIT` | 1 kg sumo robot on SUMO:BIT + 2× MD13S | Google Slides guides (Assembly/Checking/Maintenance/Autonomous/RC, Dec 2024) | **Medium-high** |
| Robot Battle (500g) SUMO:BIT | [`robot-battle-500g-sumobit.md`](robot-battle-500g-sumobit.md) | `V-BATTLE-SMB` | 500 g battle robot on SUMO:BIT, no controller, no warranty | Product page only | **Medium-low** |
| SOCCER:BIT (4 wheel) | [`soccerbit-robot-kit.md`](soccerbit-robot-kit.md) | `V-SCRBIT-4WD` | 4-motor soccer robot on SUMO:BIT | Product page only (its "user manual" link is the MD13S manual) | **Medium-low** |
| DIY RC Boat Using micro:bit | [`diy-rc-boat-microbit.md`](diy-rc-boat-microbit.md) | `PR-DIY-BOAT-MBIT` | Project kit: 2 micro:bits + MOTION:BIT boat | Product page + tutorial (partial) | **Medium-low** |

micro:bit kit notes for every agent:
- **Soil moisture reading rises as soil dries** — the APW trigger is `reading > threshold`; there is no fixed threshold in the booklet. APW wiring: sensor P2:P12 (read P2), pump MOTOR 2, servo S1; servo sweeps 30–150°.
- **RBT kit extension is `pxt-rekabit-rbt-project-kit`** (search "rekabit rbt project"); ultrasonic returns 300 cm when nothing is detected (ZOOM:BIT's returns 255). RGB Stick and Ultrasonic blocks need an init block.
- **BEETLE:BIT uses `pxt-zoombit`** (there is no beetlebit extension); gripper servo S1, motors M1 left / M2 right, Maker Line P1, ultrasonic P2 trig / P12 echo; RC mode needs a second micro:bit (not included).
- **SUMO:BIT kit motors are 12 V 580 rpm** (torque not stated — don't borrow 3.5 kgf·cm from the RC bundle); built weight ≈860 g before weights. For USB-joystick or hobby-RC mode the micro:bit must be removed; only Cytron's USB Joystick is supported. Battle kit: 495 g, 15×15×4 cm, charger included; sumo kit: charger NOT included.
- **STRIKER:BIT:** the servo part is a shooter, not a gripper; each robot needs two micro:bits (robot + Joystick:bit); battery is a button-top 18650. Score rules: max 2 yellow cards per robot, 2 red per team.

### Cytron sumo robot controllers

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker Mini Sumo Controller | [`maker-mini-sumo.md`](maker-mini-sumo.md) | `MAKER-MSUMO` | ATmega328P | Active (Datasheet Rev 1.0, Nov 2019) | **Medium-high** |
| URC10 ("Sumo Robot Controller R1.1" on my.cytron.io) | [`urc10.md`](urc10.md) | `URC10` | Not stated by Cytron | Datasheet Rev 1.0, Mar 2019 + User's Manual V1.2, Apr 2019 | **Medium** |
| IR Sumo Start | [`ir-sumo-start.md`](ir-sumo-start.md) | `IR-SUMO-START` | — (IR start module) | Datasheet Rev 1.0, Apr 2025 | **Medium-high** |

### Servo, RC, interface and breakout boards

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| SC08A Servo Controller | [`sc08a.md`](sc08a.md) | `SC08A` | 8-ch (16 with two boards) UART servo controller, 9600 baud | User's Manual V1.0, Jun 2011 (no datasheet; read from a mirror) | **Medium** |
| RCSwitch10 | [`rcswitch10.md`](rcswitch10.md) | `RCS10A` | RC-controlled SPDT relay, 250 VAC / 30 VDC, 10 A | Product page + distributor copy of the connection diagram (Cytron link returns "not found") | **Medium-low** |
| UC00C | [`uc00c.md`](uc00c.md) | `UC00C` | CH340 USB-to-UART converter, 3.3/5 V switch | User's Manual V1.0, Jul 2016 (no datasheet) | **Medium** |
| UC00A | [`uc00a.md`](uc00a.md) | `UC00A` (Rev 3.0) | FTDI FT232RL USB-to-UART converter, 3.3/5 V switch | User's Manual Rev3.0 V1.1, Dec 2018 (no datasheet) | **Medium-high** |
| URS232A TTL-to-RS232 | [`urs232a.md`](urs232a.md) | `URS232A` | MAX232 level shifter, DB9 male (PC side), Tx/Rx/CTS/RTS | Product page + TI MAX232 [VEN] | **Medium-low** |
| Breakout Board PS2 Connector | [`bb-psc.md`](bb-psc.md) | `BB-PSC` | Female PS2 connector broken out to 0.1" | Product page + Maker Mini Sumo PS2 tutorial | **Medium** |
| Breakoutboard for SPG10 | [`bb-spg10.md`](bb-spg10.md) | `BB-SPG10` | Rear-mount cable breakout for SPG10 motor, JST socket + cable | Product page ("no user's manual") | **Medium-low** |

### Sumo robot kits and parts

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| Ikedo Mini Sumo Robot V2 | [`ikedo-mini-sumo-v2.md`](ikedo-mini-sumo-v2.md) | `KIT-IKEDO-MSV2-S` | Maker Mini Sumo + 5 Maker Object + 2 edge sensors, 600 rpm, ~200 g | Ikedo Bot V2 Getting Started Instruction | **Medium** |
| Ikedo Mini Sumo Robot Pro Bundle | [`ikedo-mini-sumo-pro.md`](ikedo-mini-sumo-pro.md) | `KIT-IKEDO-MSUMO-P` | Pro: 800 rpm 3.1 kg·cm, steel shield, razor blade, 350 g | Product page | **Medium-low** |
| 1KG Sumo Robot Bundles (RC) | [`sumo-1kg-rc-bundle.md`](sumo-1kg-rc-bundle.md) | `V-SUMO-1KG-RC` | MDDRC10 RC sumo, no code, 580 rpm 3.5 kgf·cm, 856 g | Product page (user-guide tutorials blocked) | **Medium-low** |
| PCB Plate for Sumo Robot | [`pcb-sumo-plate.md`](pcb-sumo-plate.md) | `V-PCB-SUMO-PLATE` | Training blade substitute, 15 cm (1 kg) / 10 cm (500 g) | Product page | **Medium-high** |

- **1KG RC bundle has no microcontroller** — the page's "Microcontroller: MDDRC10" is a motor driver; no sensors, no autonomous mode. **No warranty** on all three robot bundles. Kit pages say opponent range "50cm adjustable" — the Maker Object datasheet says 40–140 cm (white) / 15–60 cm (black).

### Sensors

| Product | File | Code | Output | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Line | [`maker-line.md`](maker-line.md) | `MAKER-LINE` | 5 digital (high = line) + 1 analog; 3.0–5.5 V | Datasheet Rev 1.0, Jul 2019 | **Medium-high** |
| Maker Object | [`maker-object.md`](maker-object.md) | `MAKER-OBJECT` | IR object sensor, digital **active LOW**; 4.5–5.5 V | Datasheet Rev 1.0, Dec 2019 | **Medium-high** |
| Maker Reflect | [`maker-reflect.md`](maker-reflect.md) | `MAKER-REFLECT` (page variant `V-MAKER-REFLECT`) | Analog IR reflectance, 3.0–5.5 V, 1–40 mm | Datasheet Rev 1.0, Nov 2019 | **Medium-high** |
| Maker Reflect S | [`maker-reflect-s.md`](maker-reflect-s.md) | `MAKER-REFLECT-S` | IR reflectance, **5 V only**, 25 mA, optimal 3 mm | Datasheet Rev 1.0, Feb 2026 | **Medium** |
| Maker Soil Moisture Sensor | [`maker-soil-moisture.md`](maker-soil-moisture.md) | `MAKER-SOIL-MOISTURE` | Capacitive soil moisture, analog OUT 1.0–5.2 V + DIS pin | Datasheet Rev 1.0, Jan 2022 | **Medium-high** |
| MCP9700 Temperature Sensor | [`mcp9700-temperature-sensor.md`](mcp9700-temperature-sensor.md) | `BCY-TEMP-MCP9700` | Analog temperature, 10 mV/°C with 500 mV offset at 0 °C | Datasheet Rev 1.0, Aug 2023 | **Medium-high** |
| LSA08 Line Sensor | [`lsa08.md`](lsa08.md) | `LSA08` | 8-sensor auto-calibrating line sensor bar; analog / digital / UART | User's Manual V1.1, Jun 2012 + Library Manual V1.1, Jan 2013 (no datasheet) | **Medium-high** |
| RE08A Rotary Encoder Kit | [`re08a.md`](re08a.md) | `RE08A` | 8-slot opto rotary encoder, 16 pulses/rev, single channel | User's Manual V1.2, Sep 2008 (mirror; no datasheet) | **Medium** |
| 50A Current Sensor | [`bb-acs756.md`](bb-acs756.md) | `BB-ACS756` | Allegro ACS756 ±50 A breakout, 40 mV/A, 5 V | Product page + Cytron schematic + Allegro [VEN] | **Medium** |
| RGB LED Stick | [`rgb-led-stick.md`](rgb-led-stick.md) | `BCY-NEO-STICK-8` | 8× SK6812 (WS2812B-compatible) chainable stick | Product page + tutorial | **Medium** |
| 3-Axis Accelerometer | [`sn-adxl335-cy.md`](sn-adxl335-cy.md) | `SN-ADXL335-CY` | ADXL335 ±3 g breakout, 2.5–6 V (on-board 3.3 V reg), 50 Hz | Product page + ADI [VEN] | **Medium-low** |

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
| STEM Robot Building Base Bundles | [`stem-robot-building-base.md`](stem-robot-building-base.md) | `V-HD-STEM` | Plastic 2WD base + TT motors, wheels, castor (Blue/Green) | Product page (installation tutorial blocked) | **Medium-low** |
| Reconfigurable Line Following Track | [`line-following-track.md`](line-following-track.md) | `V-RE-TRACKS` | EVA foam tiles 315×315×10 mm, 18 mm line; Combo 8/16 + add-ons | Product page | **Medium-high** |
| Robo Bracket for Micro Servo | [`robo-bracket-micro-servo.md`](robo-bracket-micro-servo.md) | `ROBO-BK-SG90` | 1.5 mm aluminium bracket for SG90-size servos, fits Robo Base / Mini | Product page | **Medium** |
| Robo Base | [`robo-base.md`](robo-base.md) | Series page `V-ROBO-BASE-MINI` | PCB robot chassis; 2WD / 4WD mecanum / accessories / single-base options; 30 mm standoffs | Product page + Getting Started tutorial (section list) | **Medium-low** |
| Robo Base Mini | [`robo-base-mini.md`](robo-base-mini.md) | Series page `V-ROBO-BASE-MINI` | Smaller PCB chassis, same options; 25 mm standoffs | Product page + Getting Started tutorial (section list) | **Medium-low** |
| Robo Grip Mini Kits | [`robo-grip-mini.md`](robo-grip-mini.md) | `V-ROBO-GRIP-MINI` | PCB gripper for SG90-size servos; gripper only / 2-servo / 3-servo | Product page + Installation Guide tutorial | **Medium** |

- **STEM base includes no electronics, battery or cable ties**; motor brackets are blue on both colour options. **Line track:** Combo 8/16 contain only Cross/Curve/Straight — Station, Blank and T-Junction are add-on packs only; hardness "40 degree (±5)" has no scale stated.
- **Robo Base series:** no kit includes a controller, battery, sensors or servo; 2WD option is named "Rubber Wheels" but lists "plastic wheels". **Robo Grip Mini:** max 3 servos ("1-axis" = 2 servos, "2-axis" = 3); "Gripper only" has no servo or Robo Bracket; snap and file the parts before assembly. In STRIKER:BIT it is a shooter.

### Cytron motor drivers

| Product | File | Code | Rating (per datasheet) | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Drive | [`maker-drive.md`](maker-drive.md) | `MAKER-DRIVE` | 2 ch, 2.5–9.5 V, 1 A cont / 1.5 A peak (<5 s) | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD3A | [`mdd3a.md`](mdd3a.md) | `MDD3A` | 2 ch, 4–16 V, 3 A cont / 5 A peak (<5 s) | Datasheet Rev 1.0, Mar 2019 | **Medium** |
| MD10C | [`md10c.md`](md10c.md) | `MD10C` (Rev 3.0) | 1 ch, 5–30 V, 13 A cont / 30 A peak (≤10 s) | User's Manual Rev3.0 V1.0, Aug 2018 (no datasheet) | **Medium** |
| MD13S | [`md13s.md`](md13s.md) | `MD13S` | 1 ch, 13 A, current limit 30 A; logic ≤5.5 V | User's Manual V1.1, Jun 2018 (no datasheet) | **Medium** |
| MD20A | [`md20a.md`](md20a.md) | `MD20A` | 1 ch, 6–30 V, 20 A cont / 60 A peak (current-limited, no duration); logic 1.5–15 V | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD10A | [`mdd10a.md`](mdd10a.md) | `MDD10A` (Rev 2.0) | 2 ch, 5–30 V, 10 A cont / 30 A peak (≤10 s) per ch | User's Manual V2.0, Jun 2017 (no datasheet) | **Medium-high** |
| MDD20A | [`mdd20a.md`](mdd20a.md) | `MDD20A` | 2 ch, 6–30 V, 20 A cont / 60 A peak (current-limited) per ch | Datasheet Rev 1.0, Jul 2020 | **Medium-high** |
| MD25HV | [`md25hv.md`](md25hv.md) | `MD25HV` | 1 ch, 7–58 V, 25 A cont / 60 A peak (current-limited); no locked-antiphase | Datasheet Rev 1.0, Jan 2019 | **Medium-high** |
| MDDS10 SmartDriveDuo-10 | [`mdds10.md`](mdds10.md) | `MDDS10` | 2 ch, 10 A cont / 30 A peak (≤1 s) | User's Manual V1.0, Jun 2015 (no datasheet) | **Medium** |
| MDDS30 SmartDriveDuo-30 | [`mdds30.md`](mdds30.md) | `MDDS30` | 2 ch, 7–35 V, 30 A cont / 80 A peak (≤1 s) per ch | User's Manual Rev 1.2, Sep 2023 (no datasheet) | **Medium-high** |
| MDDS60 SmartDriveDuo-60 | [`mdds60.md`](mdds60.md) | `MDDS60` | 2 ch, 10–45 V, 60 A cont / 100 A peak (≤1 s) per ch | User's Manual Rev 1.1, Jul 2019 (no datasheet) | **Medium** |
| Enhanced SmartDrive40 | [`smartdrive40.md`](smartdrive40.md) | `MDS40B` | **1 ch**, 40 A cont / 80 A peak (≤1 s) | User's Manual Rev 1.1, Jul 2023 (no datasheet) | **Medium-high** |
| MDDRC5 | [`mddrc5.md`](mddrc5.md) | `MDDRC5` | 2 ch R/C, 7–30 V, 5 A cont / 20 A peak (<1 s) per ch | Datasheet Rev 1.0, Mar 2026 | **Medium-high** |
| MDDRC10 | [`mddrc10.md`](mddrc10.md) | `MDDRC10` | 2 ch R/C, 7–30 V, 10 A cont / 30 A peak (current-limited) per ch | Datasheet Rev 1.0, Aug 2020 | **Medium-high** |
| iMD16 | [`imd16.md`](imd16.md) | `IMD16` | 1 ch, 16 A cont / 30 A peak (<10 s), no current limit | Datasheet Rev 1.0, Apr 2026 | **Medium-high** |
| SHIELD-2AMOTOR | [`shield-2amotor.md`](shield-2amotor.md) | `SHIELD-2AMOTOR` | 2 ch Arduino shield, 5–26 V, **0.8 A cont** / 2 A peak | User's Manual V1.1, Feb 2015 | **Medium** |
| SHIELD-3AMOTOR | [`shield-3amotor.md`](shield-3amotor.md) | `SHIELD-3AMOTOR` | 2 ch Arduino shield, 7–30 V, **1.2 A cont** / 3 A peak (≤1 s) | User's Manual Rev 1.0, Apr 2017 | **Medium** |
| FD04A | [`fd04a.md`](fd04a.md) | `FD04A` (Rev 2.0) | **4 ch**, 7–15 V, 1.5 A cont / 2.5 A peak, L298P | User's Manual V1.2, Jun 2025 | **Medium** |
| MD10-POT | [`md10-pot.md`](md10-pot.md) | `MD10-POT` | 1 ch, 7–30 V, 10 A / 30 A peak (<10 s); pot + switch or PWM/DIR | Datasheet Rev 1.0, Oct 2018 | **Medium** |
| SHIELD-MD10 | [`shield-md10.md`](shield-md10.md) | `SHIELD-MD10` (Rev 2.0, "R2") | 1 ch Arduino shield, 7–30 V (abs-max table says 25 V), 15 A peak (10 s) | User's Manual (Rev 2.0 board) V1.0, Jun 2015 | **Medium** |
| SHIELD-MDD10 | [`shield-mdd10.md`](shield-mdd10.md) | `SHIELD-MDD10` | 2 ch Arduino shield, 7–30 V, 10 A / 30 A over-current limit (temperature-dependent) | Datasheet Rev 1.0, May 2019 | **Medium** |
| HAT-MDD10 | [`hat-mdd10.md`](hat-mdd10.md) | `HAT-MDD10` | 2 ch Raspberry Pi HAT, 6–24 V, 10 A / 30 A (10 s) | User's Manual V1.0, Mar 2017 | **Medium** |
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
| Maker pHAT | [`maker-phat.md`](maker-phat.md) | `HAT-MAKER` | Raspberry Pi 3B/3B+, Zero/W/WH (manual) | User's Manual Rev 1.10, Feb 2019 (no datasheet) | **Medium** |
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
| 18650 Li-Ion 2200 mAh | [`li-ion-18650-2200.md`](li-ion-18650-2200.md) | `LI-18650-3.7-2200` | Button-top cell, no protection circuit, 1-week warranty | Product page + PKCELL vendor sheet (2019) | **Medium** |
| Cooling Fan for RPi 30 mm | [`rpi-cooling-fan-30mm.md`](rpi-cooling-fan-30mm.md) | `FAN-0305-3008` | 3–5 V 0.2 A two-wire fan, 30×30×8 mm | Product page | **Medium** |

- **PSU notes:** the 27W unit's 5 V profile is 5 A (5.1 V typ.); the 17.5W unit has no PD and was designed for Pi 4 B (Pi 5 appears only on the page list). **18650:** max discharge 1C ≈ 2.2 A per Cytron (vendor says 1.5C); cannot ship to Sabah/Sarawak/overseas; never treat it as an AA.

### Storage (MakerDisk)

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| MakerDisk NVMe 2242 | [`makerdisk-nvme-2242.md`](makerdisk-nvme-2242.md) | `V-MMR-NV2242` | M.2 2242 NVMe 128/256/512 GB, RPi OS Bookworm preloaded | Datasheet Rev 1.0, Apr 2024 | **Medium-high** |
| MakerDisk NVMe 2280 (RPi OS) | [`makerdisk-nvme-2280.md`](makerdisk-nvme-2280.md) | `V-MMR-NV2280` | M.2 2280 NVMe 128 GB–1 TB, RPi OS preloaded | Product page | **Medium-low** |
| MakerDisk NVMe 2280 (JetPack) | [`makerdisk-nvme-2280-jetpack.md`](makerdisk-nvme-2280-jetpack.md) | `V-MMR-NV2280-JP` | 256/512 GB, JetPack 6.2 for Jetson Orin Nano Super 8GB only | Product page | **Medium-low** |
| MakerDisk 2.5" SATA 120 GB | [`makerdisk-sata-120gb.md`](makerdisk-sata-120gb.md) | `MMR-2P5-MD-120` | SATA III SSD, RPi OS preloaded, USB-SATA boot | Product page | **Medium-low** |

### IRIV industrial series

| Product | File | Code | Processor | Primary source | Confidence |
|---|---|---|---|---|---|
| IRIV PiControl CM4 | [`iriv-picontrol-cm4.md`](iriv-picontrol-cm4.md) | `IRIV-PICL` | Raspberry Pi CM4 (BCM2711) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.3, Nov 2025 | **Medium-high** |
| IRIV PiControl CM5 | [`iriv-picontrol-cm5.md`](iriv-picontrol-cm5.md) | `IRIV-PICL5` | Raspberry Pi CM5 (BCM2712) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.5, Jan 2026 | **Medium** |
| IRIV IO Controller | [`iriv-io-controller.md`](iriv-io-controller.md) | `IRIV-IOC` | Raspberry Pi RP2350A (microcontroller, no Linux) | Datasheet Rev 1.0, Jul 2024 | **Medium** |
| IRIV IOC MQTT Gateway | [`iriv-ioc-mqtt-gateway.md`](iriv-ioc-mqtt-gateway.md) | `IRIV-IOC-MQTT` | Same hardware as IO Controller + factory MQTT firmware | Datasheet Rev 1.0, Jun 2026 | **Medium** |
| IRIV SmartHub CM5 | [`iriv-smarthub-cm5.md`](iriv-smarthub-cm5.md) | `IRIV-SH5` | Raspberry Pi CM5 (BCM2712) | User Manual Rev 1.3, Dec 2025 | **Medium-high** |
| IRIV EdgeAI CM5 | [`iriv-edgeai-cm5.md`](iriv-edgeai-cm5.md) | `IRIV-EDGEAI-CM5` | Raspberry Pi CM5 (BCM2712) + AI HAT+ | Datasheet Rev 1.0, Jul 2025 | **Medium-high** |
| IRIV EdgeAI Safety Box Kit | [`iriv-edgeai-safety-box-kit.md`](iriv-edgeai-safety-box-kit.md) | `KIT-IRIV-EAI-PPE` | IRIV EdgeAI CM5 (8GB/32GB) + Hailo-8 26 TOPS | **No kit datasheet exists.** Live product page + Quick Start Guide (Aug 2026) + EdgeAI CM5 Datasheet Rev 1.0 | **Medium-low** |

**Source rule for IRIV (16 Oct 2026): the datasheet is the main source.** User manuals rank second ([UM]); where a newer manual disagrees, the datasheet still wins in the text and the conflict is listed for engineering.

IRIV notes for every agent:
- **IO Controller is not a Raspberry Pi computer.** No Raspberry Pi OS or Node-RED on the device.
- **IOC MQTT Gateway firmware must not be overwritten** — no CircuitPython/UF2 steps; setup is via USB-C web page at 10.0.0.1. Plain MQTT on port 1883, no TLS on the device.
- **PiControl CM4, PiControl CM5 and EdgeAI CM5 RS485 is a USB serial device (`/dev/ttyACM*`)**, not a GPIO UART.
- **mini PCIe sockets on PiControl CM4, PiControl CM5, SmartHub CM5 and EdgeAI CM5 carry USB 2.0 only** (no PCIe). M.2 = NVMe only, no SATA.
- **Bare "IRIV PiControl" is ambiguous** between CM4 (`IRIV-PICL`) and CM5 (`IRIV-PICL5`); the shared datasheet code `IRIV-PICONTROL` covers both.
- **Safety Box Kit is not a certified safety system**, detects helmets and vests only, needs RTSP IP cameras (not included), and its "up to 6 cameras" holds only for 640x360 sub-streams at 15–25 FPS. No accuracy figure exists — "96% compliant" in marketing is an example dashboard reading.
- **Bare "IRIV SmartHub" is ambiguous** with the SmartHub dashboard feature of EdgeAI. Always use the full name.

### Workshops and services

| Product | File | Code | What it is | Primary source | Confidence |
|---|---|---|---|---|---|
| AI Agent Workshop for RPI 5 | [`ai-agent-workshop-rpi5.md`](ai-agent-workshop-rpi5.md) | `V-AI-AGT-RPI` | 2-day AgentBox (Pi 5 local AI agent hub) workshop + kit | Course outline (no date) + product page | **Medium-low** |
| Jetson Orin Nano AI Fundamentals Workshop | [`jetson-orin-nano-workshop.md`](jetson-orin-nano-workshop.md) | `V-TW-JNORNN-NVIDIA` | 1-day workshop, NVIDIA certification; kit = Orin Nano Super 8GB + 512 GB JetPack SSD | Tentative timetable + product page | **Medium-low** |
| Cytron Raspbot Workshop | [`raspbot-workshop.md`](raspbot-workshop.md) | `V-TRAINING-AI` | 1-day Edge AI workshop with Raspbot (Pi 5), max 5 pax, HQ Penang | Workshop tentative + product page | **Medium** |
| Flash JetPack / Orin Nano Upgrade Service | [`jetpack-flash-service.md`](jetpack-flash-service.md) | `SEV-JN-ORNN` | Software-only JetPack 5.x → 6.x flash, RM150 by enquiry | Product page | **Medium-low** |

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

1. Check it is a Cytron-brand product. Then copy `_TEMPLATE.md` to `<product-slug>.md`.
2. Start from the main source for the product type (rule 7: datasheet for boards; guide book for education kits; board datasheet + guide book/tutorial for robot kits). Tag every fact with its source. Put conflicts and unconfirmed items in their sections — don't drop them.
3. Fill `fact-sheets/<product-slug>.md` in the Content Hub template from that reference (only what it states), and add it to `fact-sheets/ALL-fact-sheets.md`. Check the aliases don't clash with another product.
4. Add the row to *Products* above with an honest confidence level.
5. Commit to this repository with a message like `kb: add <product>`.
6. When the design team confirms something, mark it [DT] with the date and remove it from *Needs verification*.

