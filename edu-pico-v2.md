# EDU PICO V2 — Verified Reference

| | |
|---|---|
| Product code | `EDU-PICO2` (board name used throughout the datasheet); variant `EDU-PICO2-NB` ships without the Raspberry Pi Pico 2 W [DS]. my.cytron.io sells it as "EDU PICO 2" with two options (with / without Raspberry Pi Pico 2 W) [PP] |
| Family | Raspberry Pi Pico education kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (features list, both packing lists, resources). Status, packing lists, GPIO status-LED count and the resource set are now Cytron-stated. Education kit — the EDU PICO V2 booklet is the main source (KB rule 7) |
| Primary source | EDU PICO V2 Datasheet, "EDU PICO V2 – EDU Project & Innovation Kit for Pico 2 W", Rev 1.1, June 2026 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
- A project and innovation board for the Raspberry Pi Pico 2 W: "EDU PICO V2 is designed to work seamlessly with the Raspberry Pi Pico 2 W microcontroller" [DS]. The Pico plugs into a socket; the socket text says it takes "the Pico 2 / Pico 2 W" [DS].
- Built-in modules: OLED display, temperature and humidity sensor, gesture and proximity sensor, colour and light sensor, RGB LEDs, push buttons, potentiometer, buzzer and stereo audio jack, PDM microphone, dual channel motor driver, servo ports, USB relay, Micro SD card socket [DS].
- Power: USB, 1-cell LiPo/Li-ion battery (built-in charger), or external power source within 3.6 – 6 V [DS].
- The standard kit includes a Raspberry Pi Pico 2 W; the EDU-PICO2-NB variant does not [DS].
- Hub: "EDU PICO V2 came with new and improved RP2350 that can handle more complex code and component" [PP].

## Specifications
Datasheet Table 3 is titled "EDU-PICO2 **Absolute Maximum Ratings**" — every row below comes from it [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB, LiPo or VIN) | Min 3.6 V, Max 6 V | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 5.5 V* (*"Only Pico 2 / Pico 2 W boards with RP2340-A4 stepping support 5 V-tolerant digital GPIO pins.") | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.6 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Vmotor & Vservo, only USB connected | VUSB - 0.4 V | [DS] |
| Vmotor & Vservo, only either one of LiPo or VIN connected | VLiPo or VIN | [DS] |
| Vmotor & Vservo, USB and LiPo connected | VUSB - 0.4 V | [DS] |
| Vmotor & Vservo, USB and VIN, VIN < VUSB | VUSB - 0.4 V | [DS] |
| Vmotor & Vservo, USB and VIN, VIN > VUSB and VIN - VUSB < 0.6 | VIN - 0.4 V | [DS] |
| Vmotor & Vservo, USB and VIN, VIN - VUSB > 0.6 | VIN | [DS] |
| Max DC motor current per channel, continuous | 1 A | [DS] |
| Max DC motor current per channel, peak (< 5 seconds) | 1.5 A | [DS] |
| DC motor driver PWM frequency | max 20 kHz | [DS] |
| USB relay output voltage | max 5 V | [DS] |
| USB relay output current | max 500 mA | [DS] |
| Total +3V3 output current (Grove ports) | max 300 mA | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |
| Dimensions | Figure 6 "EDU-PICO2 Dimension (mm)" — drawing only, no numbers in the text | [DS] |

Packing list (Table 1) [DS]: EDU PICO V2 Board ×1; Step-by-step Guidebook (English) ×1; Raspberry Pi Pico 2 W ×1 (not in EDU-PICO2-NB); USB Micro B Cable ×1; Grove 4 Pin Buckled 20cm Cable ×8; Micro Servo with Servo Horns ×1; DC2-6V Miniature Motor with 20cm Wire ×1; Mini Phillips Head Screwdriver ×1; DIY 4 Blades 56mm Motor Propeller (Blue) ×1; USB LED Light Stick (Blue) ×1; Cable Tie 100mm ×5; Self adhesive Round Velcro 10mm (Hook and loop pairs) ×27.
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Features list:** Pi Pico socket with GPIO breakout; power LED; on/off switch; LiPo battery connector; charge LED; VIN terminal; USB relay; 2 DC motor terminals; 4 motor test buttons; 4 motor status LEDs; 4 servo ports; micro SD socket; "Log data to Pico's flash" switch; 9 Grove ports; **12 GPIO status LEDs**; reset button; piezo buzzer; stereo audio jack; audio/buzzer switch; potentiometer; PDM microphone; protoboard; SSD1315 OLED; AHT20; OPT4048; PAJ7620; 5 RGB LEDs; 2 push buttons [PP].
- **Packing (with Raspberry Pi Pico 2 W):** 1x EDU PICO 2 board; 1x step-by-step guidebook (English); 1x Raspberry Pi Pico 2 W; 1x USB micro B cable; 1x micro servo with horns; 8x Grove 4-pin buckled 20 cm cable; 1x DC 2–6 V miniature motor with 20 cm wire; 1x 85 × 3 mm Phillips screwdriver; 1x DIY 4-blade 56 mm propeller (blue); 1x set Velcro 10 mm round adhesives; 2x 100 mm cable ties; 1x USB LED light stick (blue). The "without Pico 2 W" option is the same list minus the Pico 2 W [PP].
- A product-page image shows the breakable modules ("edu-pico2-breaking-modules") [PP: img].
- **Resources:** EDU PICO V2 booklet (PDF), out-of-the-box demo code, GitHub Cytron-EDU-PICO2, board datasheet, 3D CAD, EDU PICO resource hub [PP].

## Interfaces, terminals and pin mapping
All from datasheet Table 2 "EDU-PICO2 Board Functions" unless tagged otherwise.

| Function | GPIO / detail | Src |
|---|---|---|
| Button A / Button B | GP0 / GP1; pulled HIGH by default, LOW when pressed | [DS] |
| RGB LEDs | 5× addressable SK6812-based, WS2812B compatible, in series, on GP14 | [DS] |
| I2C bus for onboard sensors and OLED | SDA = GP4, SCL = GP5 (given under the gesture sensor; Grove 3/4/5 table lists GP4 SDA0 / GP5 SCL0) | [DS] |
| Temperature & humidity | AHT20, I2C 0x38 | [DS] |
| Colour & light sensor | OPT4048, I2C 0x44 | [DS] |
| OLED display | 0.96 inch 128x64 white, SSD1315, I2C 0x3C | [DS] |
| Gesture & proximity sensor | PAJ7620, I2C 0x73 | [DS] |
| PDM microphone | MP34DT01, DOUT = GP2, CLK = GP3 | [DS] |
| Potentiometer | GP28 (ADC2) | [DS] |
| Stereo audio jack | Right = GP20, Left = GP21; non-amplified | [DS] |
| Audio/Buzzer switch | switches between left-channel audio out and the piezo buzzer | [DS] |
| Piezo buzzer | datasheet says "Internally connected to GP8" — conflicts with the rest of the datasheet and with code; see *Conflicts*. Cytron's V2 code drives it on GP21 (`PIEZO_AUDIO_L_PIN = board.GP21`) | [DS] / [GH] |
| Servo ports | 4× RC servo, signal GP6, GP7, GP8, GP9; V+ = power source voltage | [DS] |
| DC motor terminals | M1A = GP10, M1B = GP11, M2A = GP12, M2B = GP13; locked-antiphase (dual-PWM) control; fits wires up to 18 AWG | [DS] |
| USB relay (USB-A) | 5 V USB output switched by a relay on GP22; overcurrent protection above 500 mA; D+ = GP26, D- = GP27 | [DS] |
| Micro SD card socket (SPI) | GP16 = SDO, GP17 = CSn, GP18 = SCK, GP19 = SDI (datasheet labels). Cytron code: MISO = GP16, CS = GP17, SCK = GP18, MOSI = GP19 | [DS] / [GH] |
| Log Data to Pico's Flash switch | slide switch on GP15: Enable = pulled LOW, Disable = pulled HIGH; can be repurposed | [DS] |
| Vin terminal | 3.6 V – 6 V, fits wires up to 18 AWG | [DS] |
| LiPo connector | JST-PH 2-pin, single-cell LiPo or Li-ion | [DS] |
| Other | Charging LED, On/Off switch (also powers the Pico), Power LED, Reset button, Status LEDs (on when Grove-port GPIO is high), GPIO breakout (outer rows of the 2×20 female headers; Pico sits in the inner rows), protoboard with Grove port (only the pins near the Grove port pins are connected) | [DS] |

Grove ports (4-pin, 2.0 mm pitch; "already connected to the adjacent Grove Modules") [DS]. The datasheet table is a merged-cell table that reads cleanly as:

| Grove | GPIOs (functions listed) | Connected module |
|---|---|---|
| 1 | GP0 (PWM0-A, SDI0, SDA0, TX0), GP1 (PWM0-B, CSn0, SCL0, RX0) | Buttons |
| 2 | x (not connected), GP14 (PWM7-A, SCK1, SDA1) | RGB LEDs |
| 3, 4, 5 | GP4 (PWM2-A, SDI0, SDA0, TX1), GP5 (PWM2-B, CSn0, SCL0, RX1) | AHT20, PAJ7620, OPT4048, SSD1315 |
| 6 | GP2 (PWM1-A, SCK0, SDA1), GP3 (PWM1-B, SDO0, SCL1) | PDM Microphone |
| 7 | x (not connected), GP28 (PWM6-A, ADC2) | Potentiometer |
| 8 | GP20 (PWM2-A, SCL0), GP21 (PWM2-B, SDA0) | Audio & Buzzer |
| 9 | GP26 (PWM5-A, SDA1, ADC0), GP27 (PWM5-B, SCL1, ADC1) | USB-A Port |

Motor driver truth table (Table 4) [DS]: A Low / B Low → Brake; A High / B Low → Forward*; A Low / B High → Backward*; A High / B High → Hi-Z (Open), Coast. *Direction depends on wiring; swapping MxA and MxB reverses it. (Table header says inputs "GP8 / GP10" and "GP9 / GP11" — see *Conflicts*.)

## Rules and gotchas (for code, wiring and tutorials)
- Name the board **EDU PICO V2** and the Pico **Raspberry Pi Pico 2 W** (RP2350 [PP]); do not reuse "Pico W" wording from V1 material [DS].
- All four I2C devices (AHT20 0x38, OPT4048 0x44, SSD1315 0x3C, PAJ7620 0x73) share one bus on GP4 (SDA) / GP5 (SCL) [DS]. Cytron code opens it as `busio.I2C(board.GP5, board.GP4)` (SCL, SDA) [GH].
- V2 has **no APDS9960**. Gesture/proximity is PAJ7620 (0x73) and colour/light is OPT4048 (0x44) [DS]. V1 code for APDS9960 (0x39) will not find a sensor [DS V1 vs DS V2].
- GP8 is a servo signal pin [DS]; the buzzer is on GP21 in Cytron's code [GH] and on GP21 in the V1 datasheet. Do not drive the buzzer on GP8 based on the V2 datasheet line.
- The Audio/Buzzer switch decides whether GP21 drives the left audio channel or the piezo buzzer [DS].
- Motors are on GP10–GP13 [DS terminals; GH code], not GP8/GP9 as the truth-table header suggests.
- GP26/GP27 are on Grove 9 **and** wired to the USB-A port D+ / D- [DS]. Grove 9 is shown connected to "USB-A Port" [DS].
- Grove 2 and Grove 7 carry only one GPIO each (GP14 and GP28); the other signal is "x" [DS].
- The Grove port 8 table lists GP20 = SCL0 and GP21 = SDA0 [DS]; check this before using port 8 for I2C (see *Needs verification*).
- Buttons read HIGH when released and LOW when pressed [DS].
- Log-data switch: with Cytron's `boot.py`, enabling it at startup makes the Pico 2 filesystem read-only to the computer and writable by CircuitPython. It "is needed when the board is powered via USB only" [DS]. The linked `boot.py` is in the V1 repo (Cytron-EDU-PICO) [DS].
- AHT20: "it is recommended to measure data every 2 seconds to reduce temperature rises due to high measurement frequency" [DS].
- The protoboard has only the pins near its Grove port connected [DS].
- Motor test buttons run the motor at full speed (MxA forward, MxB backward) [DS].

## Power and electrical limits
- Input 3.6 – 6 V from USB, LiPo or VIN (absolute max) [DS].
- Battery: single-cell LiPo / Li-ion on JST-PH 2-pin; built-in charger; "rechargeable via the USB port of the Raspberry Pi Pico 2 / Pico 2 W"; protected from over-charge and over-discharge. "If the board cannot be turned on when the battery is connected, please charge the battery to activate the battery protection circuit." [DS]
- Charging LED: on while charging, off when full; may flicker with no battery (normal). Frequent flicker, or on with no battery, means the board is not getting enough power from the USB port [DS].
- USB and VIN together: "USB and VIN can be connected at the same time. While this is electrically safe, it is not recommended for normal operation." [DS]
- Motor and servo voltage: see the Vmotor & Vservo rows above; on USB only it is VUSB - 0.4 V [DS]. Motor voltage at full speed equals power source voltage; servo V+ equals power source voltage [DS].
- Motor current per channel: 1 A continuous, 1.5 A peak (< 5 s); PWM max 20 kHz [DS].
- USB relay: 5 V, 500 mA max; overcurrent protection above 500 mA [DS].
- Grove +3V3 total: 300 mA max [DS].
- Digital inputs above 3.3 V: only with the stepping named in the footnote (see *Needs verification*) [DS].
- Battery charge current and capacity: not stated.

## Software support
- **CircuitPython** is the language of the official course: "Explore CircuitPython ... with EDU PICO V2", "8 chapters, 7 projects, & over 10 activities" [PP].
- Editor: Thonny IDE, interpreter "CircuitPython (generic)" [PP chapter 1].
- Firmware install (hub chapter 1): Thonny → Install CircuitPython, target volume RP2350, variant "Cytron EDU PICO 2" for Pico 2 W; or manual UF2 copy after holding BOOTSEL [PP]. Bootloader: hold RST and BOOTSEL, release RST, keep BOOTSEL until the RP2350 drive appears [PP].
- CircuitPython board ID for V2 is `cytron_edu_v2_pico_2w` ("EDU PICO 2 for Pico 2 W"), latest stable 10.3.1 on 2026-10-16 [3P circuitpython.org]. The hub's manual-download link points to `cytron_edu_pico_w` (the V1 / Pico W board) — see *Conflicts*.
- GitHub repo Cytron-EDU-PICO2: "firmware UF2 file, demo code, example projects, guidebook code, and supporting materials"; folders `demo_code/circuitpython`, `firmware`, `guide_book` [GH]. Out-of-box demo (`demo_code/circuitpython/code.py` + `edu_pico_lib`) cycles 15 modules with Buttons A/B [GH].
- Course chapters (V2 downloads page) [PP]: 1 Introduction to CircuitPython; 2 Water Drinking Reminder; 3 Gesture Reaction Game; 4 Colour Detection Game; 5 Automated Waste Bin; 6 Noise Pollution Monitoring; 7 Smart Classroom; 8 Climate Control Greenhouse. Guidebook: English; Malay and Chinese "Coming soon" [PP].
- V2 project videos [PP]: Flappy Bird Game, Wireless Communication System, DIY SpaceShip Game, Gesture Snake game, Color Based Water pH System, Smart Microphone Alert System.
- MicroPython, Arduino, MicroBlocks, Piper Make: **not stated for V2** by any source read. The hub lists MicroBlocks only under "EDU PICO V1 + MicroBlocks" [PP].

## Compatibility and accessories
- Hosts: Raspberry Pi Pico 2 W (included except NB); socket text also names Pico 2 [DS].
- 9 Grove ports (4-pin, 2.0 mm); 8 Grove 4-pin 20 cm cables in the box [DS].
- Kit accessories: micro servo, DC2-6V miniature motor, 56 mm propeller, USB LED light stick, screwdriver, cable ties, velcro pairs [DS].
- Supporting files: 3D CAD, out-of-box demo code, master library folder (Drive links on the hub Downloads page) [PP].

### V1 → V2: what the two datasheets state
| Item | EDU PICO (V1) DS Rev 1.0, Dec 2023 | EDU PICO V2 DS Rev 1.1, Jun 2026 |
|---|---|---|
| Pico board | Pico W (socket: Pico / Pico W) | Pico 2 W (socket: Pico 2 / Pico 2 W) |
| Gesture / proximity / light / colour | APDS9960, 0x39 (one chip) | PAJ7620 gesture & proximity 0x73 + OPT4048 colour & light 0x44 |
| Grove 3,4,5 modules | AHT20, APDS9960, SSD1315 | AHT20, PAJ7620, OPT4048, SSD1315 |
| USB relay | GP22, "5V USB output only" | GP22, plus D+ = GP26, D- = GP27 |
| Grove 9 module | "-" | USB-A Port |
| Digital input high max | 3.6 V | 5.5 V (with stepping footnote) |
| Buzzer pin text | GP21 | GP8 (conflict; code uses GP21) |
| Packing list | 10 items | adds Cable Tie 100mm ×5 and Velcro 10mm ×27 pairs |
| No-Pico variant | EDU-PICO-NB | EDU-PICO2-NB |
| Unchanged in both datasheets | Buttons GP0/GP1; RGB 5× SK6812 GP14; I2C GP4/GP5; AHT20 0x38; SSD1315 0x3C; mic MP34DT01 GP2/GP3; pot GP28; audio R GP20 / L GP21; servos GP6–GP9; motors GP10–GP13; SD GP16–GP19; log switch GP15; relay GP22; 3.6–6 V input; motor 1 A / 1.5 A, 20 kHz; relay 5 V / 500 mA; Grove 3V3 300 mA; -20 to 85 ℃ | same |

## Common mistakes / troubleshooting
- Board will not power on with a battery: charge the battery to activate its protection circuit [DS].
- Charging LED flickers often or stays on with no battery: USB port is not supplying enough power [DS].
- Sensor not found when reusing V1 code: V1 used APDS9960 (0x39); V2 uses PAJ7620 (0x73) and OPT4048 (0x44) [DS].
- Buzzer silent: check the Audio/Buzzer switch position [DS].
- Motor runs the wrong way: swap MxA and MxB [DS].
- Wrong firmware: use the V2 board build (Thonny variant "Cytron EDU PICO 2", target RP2350) [PP]; the V1 `cytron_edu_pico_w` build targets the Pico W [3P].
- Computer cannot write files after enabling the log-data switch with `boot.py`: the filesystem is read-only to the computer by design [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Piezo buzzer pin | [DS] V2 Table 2: "Internally connected to GP8" | [DS] V2 same table: Audio/Buzzer switch shares left channel (GP21), Grove 8 "Audio & Buzzer" = GP20/GP21; GP8 is a servo pin. [GH] V2 code `PIEZO_AUDIO_L_PIN = board.GP21`. V1 DS: GP21 | Datasheet is internally inconsistent; the GP8 line is most likely an error. Use GP21 in content; ask Cytron to fix the datasheet |
| Motor driver input pins | [DS] truth table header: Input A "GP8 / GP10", Input B "GP9 / GP11" | [DS] motor terminals: M1A GP10, M1B GP11, M2A GP12, M2B GP13; [GH] code GP10–GP13 | Use GP10–GP13; truth table header is wrong (same text in the V1 datasheet) |
| PDM microphone part | [DS] MP34DT01 | [3P] circuitpython.org: MP34DT05-A | Datasheet wins: MP34DT01 |
| Colour sensor part | [DS] OPT4048 |  "EDU PICO V2 REVAMPED POSTER.png": "OPT4084" | Datasheet wins: OPT4048 (poster typo) |
| CircuitPython firmware for V2 | [PP] hub chapter 1 manual link: circuitpython.org/board/cytron_edu_pico_w/ | [3P] circuitpython.org lists `cytron_edu_pico_w` as "EDU PICO for Pico W" and `cytron_edu_v2_pico_2w` as "EDU PICO 2 for Pico 2 W"; [PP] same chapter says Thonny variant "Cytron EDU PICO 2" for Pico 2 W | Use the V2 build; the hub's manual link appears to point to the V1 build |
| Required kit for V2 projects | [PP] hub V2 video page: each project lists "EDU PICO: Project & Innovation Kit for Pico W" | [PP] hub home: "EDU PICO 2: Project & Innovation Kit for Pico 2W" | Use the V2 name; hub project pages carry the V1 kit name |
| Detachable modules |  product-page images: "Breakable Modules", "9 Detachable Modules" | [DS] says Grove ports "are already connected to the adjacent Grove Modules"; no breaking-off instructions | Not a conflict in values; claim is  only, not described in the datasheet |

## Needs verification
- **5 V-tolerant GPIO footnote**: datasheet says "RP2340-A4 stepping". The Pico 2 / Pico 2 W chip is RP2350 [PP hub]; "RP2340" is probably a typo for RP2350 A4. Which Pico 2 W units shipped in kits have the A4 stepping is not stated. Do not tell readers inputs are 5 V-tolerant.
- **Grove 8 I2C labels**: datasheet lists GP20 = SCL0, GP21 = SDA0 (same in V1). Raspberry Pi's RP2350 GPIO function table should be checked [VEN]; not verified here.
- **Which Grove port (3, 4 or 5) each I2C module sits on**: the datasheet groups ports 3, 4, 5 with four modules.
- Microphone part MP34DT01 vs MP34DT05-A (see *Conflicts*).
- Dimensions: drawing only (Figure 6); numbers not in the text.
- Battery charge current and recommended battery capacity: not stated.
- MicroPython / Arduino / MicroBlocks support for V2: not stated by any source read.
- Whether the V1 `boot.py` (Cytron-EDU-PICO repo) linked from the V2 datasheet is the intended file for V2.
- Shop SKU for the two options (page shows names, not codes).

## Sources
- [DS] EDU PICO V2 Datasheet, Rev 1.1, June 2026 — (Cytron document — link not public) (same Rev 1.1 also hosted by Farnell: https://www.farnell.com/datasheets/4795796.pdf)
- [DS, V1 comparison only] EDU PICO Board Datasheet, Rev 1.0, December 2023 — (Cytron document — link not public)
- [PP] EDU PICO hub — https://edupico-hub.cytron.io/ ; chapter 1 https://edupico-hub.cytron.io/chapters/edu-pico-v2/chapter-1 ; downloads https://edupico-hub.cytron.io/downloads ; V2 videos https://edupico-hub.cytron.io/video-tutorial/edu-pico-v2
- [PP, not read] Product page — https://my.cytron.io/p-edu-pico-2-project-innovation-kit-for-pico-2-w
- [GH] https://github.com/CytronTechnologies/Cytron-EDU-PICO2 (README; https://raw.githubusercontent.com/CytronTechnologies/Cytron-EDU-PICO2/main/demo_code/circuitpython/code.py and `edu_pico_lib/*.py`)
- [3P] https://circuitpython.org/board/cytron_edu_v2_pico_2w/ and https://circuitpython.org/board/cytron_edu_pico_w/
