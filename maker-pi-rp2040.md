# Maker Pi RP2040 — Verified Reference

| | |
|---|---|
| Product code | `MAKER-PI-RP2040` |
| Family | RP2040 / RP2350 boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Packing list, size, mounting holes and a public schematic link are now read from the live page |
| Primary source | MAKER-PI-RP2040 Datasheet, "MAKER PI RP2040 – Simplifying Robotics with Raspberry Pi® RP2040", Rev 1.2, January 2022 (public Google Doc linked from Cytron GitHub) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: no user manual [UM] was found. An older datasheet, Rev 1.0 (April 2021), is mirrored on Electrokit and was checked for differences only [DS Rev 1.0].

## What it is
- A robot controller board with the Raspberry Pi RP2040 microcontroller **soldered on the board** (no Pico module, no socket) [DS, PP]. Product page: "Powered by Rapberry Pi RP2040", "Dual-core Arm Cortex-M0+ processor", "264KB internal RAM", "2MB of Flash memory", "the exact same specifications with Raspberry Pi Pico" [PP].
- Onboard: 2-channel DC motor driver with motor test buttons and motor status LEDs, 4 RC servo ports, 7 Grove ports, 2 WS2812B RGB LEDs, 2 programmable buttons, piezo buzzer with mute switch, GPIO status LEDs, Boot and Reset buttons, debug port, Micro USB, LiPo connector, VIN terminal, on/off switch, power LED [DS; LED count PP, GH].
- Datasheet tagline: "Simplifying Robotics with Raspberry Pi® RP2040" [DS].

## Specifications
Datasheet Table 2 is titled "MAKER-PI-RP2040 **Absolute Maximum Ratings**". Every row below comes from it (Rev 1.2) [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB, LiPo or VIN) | Min 3.6 V, Max 6 V | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 3.6 V | [DS] |
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
| Total +3V3 output current (Grove ports) | max 300 mA | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |
| USB VID & PID (CircuitPython & Arduino Core) | VID 0x2E8A, PID 0x1000 | [DS] |

Table footnotes [DS]: "Voltage for the DC motor and servo is equal to power input voltage." "It's not recommended to connect both LiPo and VIN at the same time. Although it's perfectly safe to do so."
Other product-page figures [PP]: dimensions "88mm(L) x 64mm(W) x 13mm(H)"; "4x 4.8mm mounting hole (LEGO® pin compatible)", "6x M3 screw hole". The datasheet dimension figure (Figure 2) could not be read as text.
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Features list:** RP2040, 264 KB RAM, 2 MB flash; 4 servo ports; 2 DC motors with quick-test buttons; automatic power selection USB 5 V / 1-cell LiPo / Vin 3.6–6 V; LiPo charger with over-charge/over-discharge protection; power switch; 13 GPIO status LEDs; piezo buzzer with mute switch; 2 push buttons; 2 RGB LEDs (Neopixel compatible); 7 Grove ports; CircuitPython preloaded; **4x 4.8 mm mounting holes (LEGO pin compatible), 6x M3 screw holes**; **88 (L) × 64 (W) × 13 (H) mm** [PP].
- **Description:** motor driver drives 2 brushed DC motors or 1 bipolar/unipolar stepper, 3.6–6 V, up to 1 A per channel continuous; Vmotor for DC and servo follows the input supply; one power source runs board and motors [PP].
- **Packing list:** 1x Maker Pi RP2040, 4x Grove-to-female header cable, 1x mini screwdriver, 1x silicone rubber feet (4) [PP].
- **Resources:** GitHub getting started and examples, datasheet, **schematic (Google Drive)**, Maker Pi RP2040 vs Maker Pi Pico table, circuitpython.org page, 3D CAD (cdn.cytron.io), RP2040 documents, Spanish book [PP].

## Interfaces, terminals and pin mapping
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| DC motor 1 (M1A / M1B) | GP8 / GP9 | Two-input control, see truth table | [DS] |
| DC motor 2 (M2A / M2B) | GP10 / GP11 | | [DS] |
| Servo ports (4) | GP12, GP13, GP14, GP15 | "V+ voltage is equal to power source voltage" | [DS] |
| RGB LEDs (WS2812B) | GP18 | "User programmable WS2812B RGB LED". 2 LEDs on the one data pin | [DS] pin; count [PP] "2x RGB LED (Neopixel)", [GH] `neopixel.NeoPixel(board.GP18, 2)` |
| Programmable buttons | GP20, GP21 | Demo code enables the internal pull-up and reads a press as LOW | [DS] pins; [GH] usage |
| Piezo buzzer | GP22 | Buzzer mute switch silences it | [DS] |
| Grove 1 | GP0, GP1 | GP0: PWM0-A, SDI0, SDA0, TX0. GP1: PWM0-B, CSn0, SCL0, RX0 | [DS] |
| Grove 2 | GP2, GP3 | GP2: PWM1-A, SCK0, SDA1. GP3: PWM1-B, SDO0, SCL1 | [DS] |
| Grove 3 | GP4, GP5 | GP4: PWM2-A, SDI0, SDA0, TX1. GP5: PWM2-B, CSn0, SCL0, RX1 | [DS] |
| Grove 4 | GP16, GP17 | GP16: PWM0-A, SDI0, SDA0, TX0. GP17: PWM0-B, CSn0, SCL0, RX0 | [DS] |
| Grove 5 | GP6, GP26 | GP6: PWM3-A, SCK0, SDA1. GP26: PWM5-A, SDA1, ADC0 | [DS] |
| Grove 6 | GP26, GP27 | GP26: PWM5-A, SDA1, ADC0. GP27: PWM5-B, SCL1, ADC1 | [DS] |
| Grove 7 | GP7, GP28 | GP7: PWM3-B, SDO0, SCL1. GP28: PWM6-A, ADC2 | [DS] |
| GPIO status LEDs | GP0–7, GP16, GP17, GP26, GP27, GP28 (13 pins) | "LED indicators for RP2040 GPIOs on Grove Ports. Turn on when the GPIO state is high." | [DS] function; [PP] "13x Status indicator LEDs for GPIO pins"; [GH] pin list |
| Motor test buttons | Hardware | "Motor will run at full speed." MxA: Forward, MxB: Backward | [DS] |
| Motor status LEDs | Hardware | "Turn on when the motor is running." MxA: Forward, MxB: Backward | [DS] |
| Boot button | Hardware | Hold while resetting to enter bootloader mode | [DS] |
| Reset button | Hardware | Resets the RP2040 | [DS] |
| Debug port | Hardware | "Debugging port of the RP2040" | [DS] |
| Micro USB port | — | Upload programs from PC; can also power the board | [DS] |
| On/off switch, power LED | Hardware | | [DS] |

Motor driver truth table [DS] (Input A = GP8/GP10, Input B = GP9/GP11):
- A Low, B Low → outputs Low/Low → **Brake**
- A High, B Low → High/Low → Forward
- A Low, B High → Low/High → Backward
- A High, B High → Hi-Z (Open) → **Coast**
- "Actual motor direction is depending on the motor connection. Swapping the connection (MA & MB) will reverse the direction." [DS]

The Grove table was flattened in the text export but rebuilt unambiguously; the Rev 1.0 mirror lists the same seven GPIO pairs [DS Rev 1.0], and the 13 status-LED pins in [GH] match them.

## Rules and gotchas (for code, wiring and tutorials)
- **The RP2040 is on the board.** Do not tell readers to insert a Pico; there is no socket [DS].
- **Pins the board uses:** GP8–GP11 (motors), GP12–GP15 (servos), GP18 (RGB), GP20, GP21 (buttons), GP22 (buzzer) [DS]. Don't wire external devices to these.
- **Grove user pins:** GP0–GP7, GP16, GP17, GP26, GP27, GP28 [DS].
- **GP26 is on both Grove 5 and Grove 6** [DS]. Never use both ports for different devices at once.
- **I2C-capable Grove ports** (SDA + SCL pair, derived from [DS] table): Grove 1, 3, 4 (I2C0) and Grove 2, 6 (I2C1). Grove 5 has two SDA-capable pins and Grove 7 has one SCL pin, so neither carries I2C.
- **UART-capable Grove ports** [DS]: Grove 1 and Grove 4 (UART0), Grove 3 (UART1).
- **Analog inputs** [DS]: GP26 (ADC0, Grove 5/6), GP27 (ADC1, Grove 6), GP28 (ADC2, Grove 7). Range 0–3.3 V.
- **Brake vs coast:** LOW/LOW = brake, HIGH/HIGH = coast [DS]. With Adafruit `adafruit_motor`, `throttle = 0` sets both pins HIGH (= coast on this board) and `throttle = None` sets both LOW (= brake) (derived from [DS] + library source [VEN]). Cytron's demo comments say the opposite (see *Conflicts*).
- **Motor PWM:** max 20 kHz [DS]. The CircuitPython demo uses 10 kHz [GH]. Product page Q&A: "We've tested it up to 20kHz." [PP]
- **Motor current:** 1 A continuous, 1.5 A peak for under 5 s, per channel [DS]. Spec table = absolute maximum ratings, not operating targets [DS].
- **Test buttons run motors at full speed with no code** [DS]. Lift the robot first.
- **Status LEDs follow the Grove pins** [DS], so I2C/UART/PWM traffic makes them flicker (expected, derived).
- **Motor and servo voltage = input voltage** [DS]. On USB only it is VUSB - 0.4 V [DS]; servos rated for 6 V max get the same supply.
- **Stepper:** product page says the driver can run "1x bipolar/unipolar stepper motor"; Q&A: "The two wires from first coil should be connected to Motor 1 terminals and wires from second coil to Motor 2 terminals." [PP]
- **No Wi-Fi/Bluetooth on board.** Product page Q&A suggests adding a Grove WiFi 8266 module via Grove [PP].

## Power and electrical limits
- Three sources [DS]: Micro USB, single-cell LiPo / Li-Ion connector, or VIN terminal ("any power source within 3.6 - 6V"). Product page: "Automatic power selection: USB 5V, LiPo (1-cell) or Vin (3.6-6V)" [PP].
- "The battery is rechargeable via USB." Battery "is protected from overcharged and over discharged. If the board cannot be turned on when the battery is connected, please charge the battery to activate the battery protection circuit." [DS] Product page: "Built-in 1-cell LiPo/Li-Ion charger" [PP]. Charge current not stated.
- LiPo + VIN together: "not recommended … Although it's perfectly safe to do so" [DS].
- "Only one power source is needed to power up both controller board and motors at a time." [PP]
- Grove 3V3 total: 300 mA max [DS].
- On/off switch turns the power on/off [DS].

## Software support
- **CircuitPython (preloaded):** "CircuitPython is preloaded on the Maker Pi RP2040 and it runs a simple demo program right out-of-the-box." [PP; GH]. Board-specific firmware: https://circuitpython.org/board/cytron_maker_pi_rp2040/ with `adafruit_motor`, `neopixel` and `simpleio` embedded, so they don't need to go in `lib` [GH]. The Raspberry Pi Pico CircuitPython firmware also works, but those libraries must be added manually [GH].
- **Out-of-the-box demo** [GH]: melody and running blue LEDs on startup, RGB colour fading; GP20 = all blue LEDs on, motor 1 forward / motor 2 backward at 50 %, servos to 0°; GP21 = LEDs off, stop motors, servos to 180°.
- **Bootloader:** hold BOOT, press and release RST → `RPI-RP2` drive; copy the .uf2 → `CIRCUITPY` drive [GH; DS Boot button].
- **MicroPython:** Raspberry Pi's drag-and-drop MicroPython guide (Pico firmware) [GH]. "you are free to use MicroPython and C/C++ for Pico/RP2040" [PP].
- **C/C++:** custom C/C++ firmware via bootloader mode [DS].
- **Arduino:** datasheet gives the USB VID/PID for "CircuitPython & Arduino Core" [DS]; product page points Arduino users to "this official news by Arduino" [PP]. No Cytron Arduino examples in the [GH] repo README.
- "Software, firmware, libraries and resources that are developed for Pico should work seamlessly" [PP].
- Recommended editor: Mu Editor [GH].

## Compatibility and accessories
- **Grove modules** on 7 Grove ports, 3.3 V supply [DS].
- **4 RC servos**, **2 brushed DC motors or 1 bipolar/unipolar stepper** [DS servos/motors; PP stepper].
- Compatible accessory listed: USB Micro B cable [PP].
- Same motor/servo/RGB/button/buzzer/Grove GPIO map as Cytron's later Robo Pico (see robo-pico.md) [DS of both]; Robo Pico differs in using a Pico socket.

## Common mistakes / troubleshooting
- **Brake/coast mislabel:** demo code comments `motor1.throttle = 0  # motor1.throttle = None to spin freely` under "Brake motors" [GH]. On this board `0` = coast and `None` = brake [DS + VEN].
- **Demo code header** links https://circuitpython.org/board/raspberry_pi_pico rather than the Maker Pi RP2040 build [GH]. Use the board-specific firmware.
- **Board won't power on with battery:** charge the battery to reset the protection circuit [DS].
- **Wrong reading on Grove 5/6:** both include GP26 [DS].
- **Wait for file save before reset/unplug** in CircuitPython [GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| What `throttle = 0` / `None` does | [GH] demo: 0 = "Brake motors", None = "spin freely" | [DS] truth table: HIGH/HIGH = coast, LOW/LOW = brake; `adafruit_motor` source: 0 → both HIGH, None → both LOW | [DS] wins: `throttle = 0` coasts, `None` brakes |
| GP21 action in out-of-box demo | [GH] README: "stop both DC Motor 1 & 2" | [GH] code comment: "Brake motors" | Code sets throttle 0 = coast per [DS]; describe as "stop" |
| Motor PWM frequency | [DS Rev 1.0, Apr 2021]: no PWM row (11 rows) | [DS Rev 1.2, Jan 2022]: max 20 kHz; [PP] Q&A "tested it up to 20kHz" | Rev 1.2 (newer datasheet) wins: max 20 kHz |
| USB VID/PID | [DS Rev 1.0]: not listed | [DS Rev 1.2]: VID 0x2E8A, PID 0x1000 | Rev 1.2 wins |
| RGB LED type label | [DS] heading "RGB LEDs (WS2812)" | [DS] body "WS2812B" | Use WS2812B |
| Product code in demo comment | [GH] link `cytron.io/p-maker-pi-rp2040` | [PP] live URL `my.cytron.io/p-maker-pi-rp2040-simplifying-robotics-with-raspberry-pi-rp2040` | Use the live [PP] URL |

## Needs verification
- Datasheet dimension figure (Figure 2) not readable as text; dimensions and mounting holes above are [PP] only.
- Whether GP19 is free / broken out anywhere (no header row in [DS]; not on any Grove port).
- Whether the buttons have hardware pull-ups (examples rely on the internal pull-up).
- Motor driver IC part number and LiPo charge current — not stated in any Cytron source read.
- Battery connector type and VIN terminal type — not stated in text.
- Arduino board-package details (which core, board name) — only the [DS] VID/PID row and a [PP] pointer to Arduino news; Zephyr also lists a `cytron/maker_pi_rp2040` board [3P].

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Build Otto DIY Robot Using Maker Pi RP2040](https://my.cytron.io/tutorial/build-otto-diy-robot-using-maker-pi-rp2040) — Uncategorized, 2021 [PP: tutorial]
- [Object Sense With Servo Using Maker Pi RP2040](https://my.cytron.io/tutorial/object-sense-with-servo-using-maker-pi-rp2040) — Tutorial, Beginner, 2021 [PP: tutorial]
- [Hungry Robot, powered by Maker Pi RP2040 and CircuitPython](https://my.cytron.io/tutorial/hungry-robot-powered-by-maker-pi-rp2040-and-circuitpython) — Tutorial, Beginner, 2022 [PP: tutorial]
- [Maker Pi RP2040](https://my.cytron.io/tutorial/getting-started-with-rbm-maker-pi-rp2040) — Tutorial, Beginner, 2025 (part of "Getting Started with Robo Base Mini") [PP: tutorial]
- [Maker Pi RP2040 Mobile Robot](https://my.cytron.io/tutorial/maker-pi-rp2040-mobile-robot) — Tutorial, Intermediate, 2021 [PP: tutorial]
- [Maker Pi RP2040](https://my.cytron.io/tutorial/getting-started-with-rb-maker-pi-rp2040) — Tutorial, Beginner, 2025 (part of "Getting Started with Robo Base") [PP: tutorial]

## Sources
- [DS] MAKER-PI-RP2040 Datasheet, Rev 1.2, January 2022 (public Google Doc, linked from the Cytron GitHub README): https://docs.google.com/document/d/1DJASwxgbattM37V4AIlJVR4pxukq0up25LppA8-z_AY/edit
- [DS Rev 1.0] MAKER-PI-RP2040 Datasheet, Rev 1.0, April 2021 (public PDF mirror, Electrokit): https://www.electrokit.com/upload/product/41018/41018440/MAKER-PI-RP2040%20Datasheet.pdf
- [PP] https://my.cytron.io/p-maker-pi-rp2040-simplifying-robotics-with-raspberry-pi-rp2040 (read 2026-10-16)
- [GH] https://github.com/CytronTechnologies/MAKER-PI-RP2040 — README.md, setup-circuitpython.md, Examples/CircuitPython/Out-of-the-box Demo Code/code.py, maker-pi-rp2040-tagline.png (via raw.githubusercontent.com)
- [VEN] Adafruit CircuitPython Motor library source: https://raw.githubusercontent.com/adafruit/Adafruit_CircuitPython_Motor/main/adafruit_motor/motor.py
- [3P] https://shop.pimoroni.com/products/maker-pi-rp2040 · https://docs.zephyrproject.org/latest/boards/cytron/maker_pi_rp2040/doc/index.html
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
