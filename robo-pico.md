# Robo Pico — Verified Reference

| | |
|---|---|
| Product code | `ROBO-PICO`. The my.cytron.io page "Robo Pico: Simplifying Robotics with Raspberry Pi Pico / Pico W" is listed in the tutorial shop links with model code `V-ROBO-PICO` (the page's variant code) [PP: tutorial] |
| Family | Robo series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read (features, packing lists, resources) plus Cytron pinout and dimension images. Pico 2 support, package contents, dimensions, mounting holes and the WS2812 LED part are now Cytron-stated |
| Primary source | Robo Pico Board Datasheet, "ROBO PICO – Simplifying Robotics with Raspberry Pi Pico / Pico W", Rev 1.0, April 2023 (Google Doc last modified 2025-03-11, still labelled Rev 1.0) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: no user manual [UM] was found. [PP] here means the Cytron tutorial page only; the product page could not be fetched.

## What it is
- A robot controller carrier board for the Raspberry Pi Pico / Pico W. The Pico plugs into an onboard "Pi Pico Socket: Socket for Raspberry Pi Pico and Pico W" [DS]. **There is no microcontroller on the Robo Pico itself**, and the Pico is not part of the board [DS socket; GH README lists Pico/Pico W firmware separately].
- Onboard: 2-channel DC motor driver, 4 RC servo ports, 7 Grove ports, 1 Maker Port, NeoPixel RGB LEDs, 2 programmable buttons, piezo buzzer with mute switch, GPIO status LEDs, motor test buttons and motor status LEDs, reset button, on/off switch, and USB / LiPo / VIN power [DS].
- Datasheet tagline: "Simplifying Robotics with Raspberry Pi Pico / Pico W" [DS].

## Specifications
Datasheet Table 2 is titled "ROBO-PICO **Absolute Maximum Ratings**" — every row below comes from it [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB, LiPo or VIN) | Min 3.6 V, Max 6 V | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 3.6 V | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.6 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Vmotor & Vservo, only USB connected | VUSB - 0.4 V | [DS] |
| Vmotor & Vservo, only LiPo or only VIN connected | VLiPo or VIN | [DS] |
| Vmotor & Vservo, USB and LiPo connected | VUSB - 0.4 V | [DS] |
| Vmotor & Vservo, USB and VIN, VIN < VUSB | VUSB - 0.4 V | [DS] |
| Vmotor & Vservo, USB and VIN, VIN > VUSB and VIN - VUSB < 0.6 V | VIN - 0.4 V | [DS] |
| Vmotor & Vservo, USB and VIN, VIN - VUSB > 0.6 V | VIN | [DS] |
| Max DC motor current per channel, continuous | 1 A | [DS] |
| Max DC motor current per channel, peak (< 5 seconds) | 1.5 A | [DS] |
| DC motor driver PWM frequency | max 20 kHz | [DS] |
| Total +3V3 output current (Grove ports) | max 300 mA | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |

Table footnotes [DS]: "Voltage for the DC motor and servo is equal to power input voltage." "It's not recommended to connect both LiPo and VIN at the same time. Although it's perfectly safe to do so."
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Host boards:** "Works with Raspberry Pi Pico 2, Pico and Pico W" [PP]. Purchase options: Robo Pico ONLY; + Raspberry Pi Pico 2 SH (pre-soldered headers, by Cytron); + Raspberry Pi Pico H; + Raspberry Pi Pico 2 WH [PP].
- **Packing (Robo Pico ONLY):** 1x Robo Pico, 4x Grove to female header cable, 1x transparent Phillips screwdriver, 1x silicone rubber feet (pack of 4). Bundles add the Pico board with pre-soldered headers and a 1 m USB micro B cable [PP].
- **Power:** automatic selection USB 5 V / 1-cell LiPo / Vin 3.6–6 V; built-in 1-cell LiPo/Li-ion charger with over-charge and over-discharge protection; power switch with status LED [PP].
- **On board:** reset button; 7 Grove ports (digital, analog, I2C, SPI, UART); 1 Maker Port (JST-SH 4-way, Qwiic/STEMMA QT compatible [PP: img]); GPIO breakout (female headers); 13 GPIO status LEDs; 2 RGB LEDs, Neopixel-compatible — the pinout image names them **WS2812** [PP: img]; 2 programmable buttons (GP20, GP21); piezo buzzer (GP22) with mute switch; 2 DC motor terminals with 2 status LEDs and 2 test buttons each; 4 servo ports (GP12–GP15) [PP][PP: img].
- **Size:** 88 × 72 mm; 4x Ø4.8 mm holes (82 mm apart) and 4x Ø3 mm (M3) holes (80 × 48 mm pattern) [PP: img dimension].
- Pinout image confirms Grove 7 = GP7 + GP28 (labels GP28, GP7, 3V3, GND) [PP: img].
- Resources: datasheet (Google Doc), Getting Started Guide using CircuitPython (tutorial + GitHub), 3D CAD, BocoBot 5-in-1 robot set [PP].

## Interfaces, terminals and pin mapping
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| DC motor 1 (M1A / M1B) | GP8 / GP9 | Two-input control, see truth table | [DS] |
| DC motor 2 (M2A / M2B) | GP10 / GP11 | | [DS] |
| Servo ports (4) | GP12, GP13, GP14, GP15 | V+ = power source voltage | [DS] |
| NeoPixel RGB LEDs | GP18 | 2 LEDs on one data pin (`neopixel.NeoPixel(board.GP18, 2)`) | [DS] pin; count [GH] |
| Programmable buttons | GP20, GP21 | Examples enable the internal pull-up and read a press as LOW | [DS] pins; [GH] usage |
| Piezo buzzer | GP22 | Buzzer mute switch silences it | [DS] |
| VBAT sense | GP28 (ADC2) | Only after soldering the jumper on the back. VADC2 = VBAT / 2, VBAT = VIN or VUSB or VLiPo, whichever is higher | [DS] |
| Grove 1 | GP0, GP1 | GP0: PWM0-A, SPI0 SDI0, I2C0 SDA0, UART0 TX0. GP1: PWM0-B, CSn0, SCL0, RX0 | [DS] |
| Grove 2 | GP2, GP3 | GP2: PWM1-A, SCK0, I2C1 SDA1. GP3: PWM1-B, SDO0, SCL1. **Shared with the Maker Port** | [DS] |
| Grove 3 | GP4, GP5 | GP4: PWM2-A, SDI0, SDA0, UART1 TX1. GP5: PWM2-B, CSn0, SCL0, RX1 | [DS] |
| Grove 4 | GP16, GP17 | GP16: PWM0-A, SDI0, SDA0, TX0. GP17: PWM0-B, CSn0, SCL0, RX0 | [DS] |
| Grove 5 | GP6, GP26 | GP6: PWM3-A, SCK0, SDA1. GP26: PWM5-A, SDA1, ADC0 | [DS] |
| Grove 6 | GP26, GP27 | GP26: PWM5-A, SDA1, ADC0. GP27: PWM5-B, SCL1, ADC1 | [DS] |
| Grove 7 | GP7, GP28 | GP7: PWM3-B, SDO0, SCL1. GP28: PWM6-A, ADC2 | [DS] |
| Maker Port | GP2, GP3 | QWIIC / STEMMA QT / Grove (with conversion cable) | [DS] |
| GPIO status LEDs | GP0–7, GP16, GP17, GP26, GP27, GP28 (13 pins) | Light when the GPIO is HIGH | [DS] function; [GH] demo drives these 13 pins |
| GPIO breakout | All Pico GPIO | Female pin headers | [DS] |
| Motor test buttons, motor status LEDs | Hardware only | Test button runs the motor at full speed: MxA forward, MxB backward | [DS] |
| Reset button, on/off switch, power LED | Hardware | Reset resets the Pico; switch turns off all power including the Pico | [DS] |

Motor driver truth table [DS] (Input A = GP8/GP10, Input B = GP9/GP11):
- A Low, B Low → outputs Low/Low → **Brake**
- A High, B Low → High/Low → Forward
- A Low, B High → Low/High → Backward
- A High, B High → Hi-Z (open) → **Coast**
- Actual direction depends on motor wiring; swapping MxA and MxB reverses it [DS].

The datasheet Grove table was mangled when read as text. The mapping above was rebuilt row by row and matches the order of the 13 status-LED pins in Cytron's demo code (GP0, 1, 2, 3, 4, 5, 16, 17, 6, 26, 27, 7, 28) [GH]. See *Needs verification*.

## Rules and gotchas (for code, wiring and tutorials)
- **Pins the board uses:** GP8–GP11 (motors), GP12–GP15 (servos), GP18 (NeoPixel), GP20, GP21 (buttons), GP22 (buzzer) [DS]. GP28 too, if the VBAT sense jumper is soldered [DS]. Don't wire external devices to these.
- **Grove user pins:** GP0–GP7, GP16, GP17, GP26, GP27, GP28 [DS]. GP19 is not on any Grove port or onboard function in the datasheet; it is reachable only on the GPIO breakout header [DS, by omission].
- **GP26 is on both Grove 5 and Grove 6** [DS]. Never use both ports for different devices at once.
- **Grove 2 and the Maker Port are the same pins (GP2/GP3)** [DS]. A Qwiic sensor on the Maker Port and a Grove device on Grove 2 cannot be used independently (unless both are I2C devices on one bus with different addresses — derived).
- **Grove 7 GP28 doubles as VBAT sense** once the back jumper is soldered [DS]. Don't put a sensor on Grove 7's GP28 with the jumper closed.
- **I2C-capable Grove ports** (SDA + SCL pair, derived from the [DS] table): Grove 1, 3, 4 (I2C0) and Grove 2, 6 (I2C1). Grove 5 has two SDA-only pins and Grove 7 has only one SCL pin, so neither can carry I2C.
- **UART-capable Grove ports** [DS]: Grove 1 and Grove 4 (UART0), Grove 3 (UART1).
- **Analog inputs** [DS]: GP26 (ADC0, Grove 5/6), GP27 (ADC1, Grove 6), GP28 (ADC2, Grove 7). Analog input range 0–3.3 V.
- **Brake vs coast:** LOW/LOW = brake, HIGH/HIGH = coast [DS]. This is the reverse of the comments in Cytron's CircuitPython demo (see *Conflicts*). With Adafruit `adafruit_motor`, `throttle = 0` sets both pins to 0xFFFF (HIGH/HIGH) [VEN library source], which on this board is **coast**; `throttle = None` sets both to 0 = **brake** (derived from [DS] + library source).
- **Motor PWM:** max 20 kHz [DS]. Official examples use 10 kHz (CircuitPython) and 50 Hz (MicroPython) [GH].
- **Motor current:** 1 A continuous, 1.5 A peak for under 5 s, per channel [DS].
- **Test buttons run motors at full speed with no code** [DS]. Lift the robot before testing.
- **Status LEDs follow the Grove pins** [DS], so I2C/UART traffic on a Grove port makes its LEDs flicker (expected behaviour, derived).
- **Spec table = absolute maximum ratings** [DS]. 6 V input and 1.5 A peak are limits, not operating targets.
- **Pico internal pins [VEN]:** on Pico, GP23–GP25 and GP29 are used on-module (SMPS mode, VBUS sense, LED, VSYS sense); on Pico W they connect to the wireless chip. Don't use them in Robo Pico examples.

## Power and electrical limits
- Three sources [DS]: USB (through the Pico's own USB port), a single-cell LiPo / Li-ion battery connector, or the VIN terminal (3.6–6 V).
- The battery is recharged through the Pico / Pico W USB port [DS]. Charge current is not stated.
- Battery is protected against over-charge and over-discharge. If the board won't turn on with the battery connected, charge the battery to activate the protection circuit [DS].
- LiPo + VIN together: "not recommended … Although it's perfectly safe" [DS].
- Motor and servo supply follow the power source; see the Vmotor/Vservo rows in *Specifications* [DS]. On USB only, motors and servos get VUSB - 0.4 V [DS].
- Grove 3V3 total: 300 mA max [DS].
- On/off switch cuts all power including the Pico [DS].
- Battery voltage can be read on GP28 (ADC2) as VBAT / 2 after soldering the jumper [DS].

## Software support
- Official repo: CircuitPython, MicroPython and Arduino code [GH README].
- **MicroPython:** standard rp2-pico / rp2-pico-w firmware from micropython.org [GH]. Examples: Blink, Button, Buzzer, DC_Motor, Servo_Motor, Analog_Read, NTP_Clock using `machine.Pin` / `PWM` / `ADC` [GH].
- **Arduino:** Earle Philhower `arduino-pico` core via Boards Manager [GH]. Examples: Blink, Button, Buzzer, DC_Motor (CytronMotorDriver, `CytronMD motor1(PWM_PWM, 8, 9)`, `motor2(PWM_PWM, 10, 11)`), Servo_Motor (`Servo.h`, pins 12–15), Analog_Read (pin 27, 12-bit) [GH].
- **Demo code** (`Demo_Code/circuitpython/code.py`): factory-test style program — melody, running status LEDs, NeoPixel animation; GP20 runs motors at ±50 % and servos to 0°, GP21 brakes and moves servos to 180° [GH].
- Cytron tutorial: "Getting Started Guide with Robo Pico using CircuitPython" (Blink, NeoPixel, buttons, music, DC motor, micro servo, analog sensor, SSD1315 OLED, NTP clock, HTTP server, ThingSpeak, Blynk) [PP tutorial page].
- Servo calibration in examples: CircuitPython `min_pulse=580, max_pulse=2700`; MicroPython duty_u16 2200–8300 at 50 Hz [GH].

## Compatibility and accessories
- **Host boards:** Raspberry Pi Pico 2, Pico and Pico W [PP] (datasheet and GitHub mention Pico / Pico W only [DS, GH]). Bundles ship with Pico 2 SH, Pico H or Pico 2 WH [PP].
- **Grove modules** on 7 Grove ports, 3.3 V supply [DS]. **QWIIC / STEMMA QT** on the Maker Port; Grove via conversion cable [DS].
- **4 RC servos**, **2 brushed DC motors** [DS].
- Related Cytron projects: "Build BocoBot Car with Robo Pico", "Build an RC robot car using Pi Pico W and Robo Pico" [PP tutorial page]. Example sensors in [GH]: Maker Line / Maker Soil (analog on Grove 6, GP27).

## Common mistakes / troubleshooting
- **Brake/coast mislabel:** Cytron's demo code says `motor1.throttle = 0` brakes and `None` lets the motor spin freely [GH]. On Robo Pico it is the other way round (see *Rules*). Tutorials should not copy the comment.
- **MicroPython DC_Motor labels:** the "Forwards" step drives M1B/M2B with M1A/M2A low [GH]. By the datasheet truth table that is "Backward" [DS]. Real direction depends on wiring, but keep naming consistent with the datasheet (A = forward).
- **Analog_Read header:** CircuitPython file says "read analog value on the Maker Soil" while its connection block says "Maker Line" on Grove 6 / GP27 [GH]. The pin (GP27) is correct per [DS].
- **Demo code comment** "LEDs placement on Maker Pi RP2040" is a copy-over from another board; the pins listed are Robo Pico's [GH].
- **Arduino Button comment** labels both buttons "button 1" (GP20 and GP21) [GH].
- **Board won't power on with battery:** charge the battery to reset the protection circuit [DS].
- **Maker Port device not responding:** check nothing else is driving Grove 2 (same GP2/GP3) [DS].
- **Wrong Grove reading on Grove 5/6:** both include GP26 [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| What `throttle = 0` / `None` does | [GH] demo code: 0 = "Brake motors", None = "spin freely" | [DS] truth table: HIGH/HIGH = coast, LOW/LOW = brake; `adafruit_motor` source: 0 → both HIGH, None → both LOW | [DS] wins: on Robo Pico, `throttle = 0` coasts and `None` brakes |
| MicroPython "Forwards" direction | [GH] MicroPython DC_Motor: "Forwards" = A low, B PWM | [DS]: A Low / B High = Backward | [DS] naming wins |
| VIN range | [3P] Tom's Hardware: "VIN terminals 3-6V" | [DS]: 3.6–6 V | [DS] wins: 3.6–6 V |
| Supported Pico boards | [PP] and [3P] Core Electronics: "Works with Raspberry Pi Pico 2, Pico and Pico W" | [DS] and [GH]: Pico / Pico W only | Cytron product page adds Pico 2 (newer than the datasheet); state Pico 2 support from [PP] |
| Datasheet revision | Google Doc modified 2025-03-11 | Cover still says Rev 1.0, April 2023 | Treat as Rev 1.0; ask whether a 2025 edit changed content |

## Needs verification
- **Grove pin table** — the datasheet table was mangled in text extraction. The rebuilt mapping matches [GH] demo pin order, but confirm against the datasheet figure (especially Grove 5 = GP6 + GP26 and Grove 7 = GP7 + GP28).
- Which GPIO is on Grove wire 1 (yellow) and wire 2 (white) for each port; the datasheet lists pins in order but doesn't name wire colours.
- Whether the Pico must have soldered male headers (implied by the socket [DS]; Tom's Hardware [3P] says headers must be soldered). Pico H fit not confirmed.
- Motor driver IC: MX1515H per Tom's Hardware [3P] only.
- Battery connector type ("JST" per Core Electronics [3P]) and VIN terminal type ("terminal block" per CNX [3P]).
- Stepper motor support (one bipolar/unipolar stepper per RobotShop / Core Electronics [3P]).
- Where the Grove 3V3 comes from (Pico 3V3 regulator or onboard), and the LiPo charge current — power-tree figure not readable.
- Whether muting the buzzer frees GP22 for other use.
- Whether the buttons have on-board pull-ups (examples rely on the RP2040 internal pull-up).
- Pico 2 software: which CircuitPython/MicroPython build and examples Cytron tests on Pico 2 (page says it works; no Pico 2 example code read).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Getting Started Guide with Robo Pico using CircuitPython](https://my.cytron.io/tutorial/getting-started-with-robo-pico-using-circuitpython) — Tutorial, Beginner, 2023 (series, 15 parts) [PP: tutorial]
- [Learn Robotics with Bocobot Car Kit and Robo Pico](https://my.cytron.io/tutorial/build-bocobot-car-with-robo-pico) — Tutorial, Beginner, 2023 (series, 6 parts) [PP: tutorial]
- [Setting up the MOTION 2350 Pro](https://my.cytron.io/tutorial/get-started-motion-2350-pro-circuitpython-setting-up-robo-pico) — Tutorial, Beginner, 2024 (part of "Getting Started with MOTION 2350 Pro using CircuitPython") [PP: tutorial]
- [How to Create Temperature Gauge Using Pi Pico](https://my.cytron.io/tutorial/how-to-create-temperature-gauge-using-pi-pico) — Tutorial, Beginner, 2023 [PP: tutorial]
- [Build an RC robot car using Pi Pico W and Robo Pico](https://my.cytron.io/tutorial/build-an-rc-robot-car-using-pi-pico-w-and-robo-pico) — Tutorial, Beginner, 2023 [PP: tutorial]
- [Colour Detection Robot using Colour Sensor with Robo Pico](https://my.cytron.io/tutorial/colour-detection-robot-using-TCS3200) — Tutorial, Intermediate, 2026 [PP: tutorial]

## Sources
- [GH] https://github.com/CytronTechnologies/Cytron-ROBO-PICO — README, `Demo_Code/circuitpython/code.py`, `Getting_Started_Guide/CircuitPython/*/code.py`, `Getting_Started_Guide/MicroPython/*/main.py`, `Getting_Started_Guide/Arduino/*/*.ino` (read via raw.githubusercontent.com)
- [PP] Cytron tutorial page: https://my.cytron.io/tutorial/getting-started-with-robo-pico-using-circuitpython
- [PP] Product page (linked from [GH], not read): https://my.cytron.io/p-robo-pico-simplifying-robotics-with-raspberry-pi-pico
- [VEN] Adafruit CircuitPython Motor library source: https://raw.githubusercontent.com/adafruit/Adafruit_CircuitPython_Motor/main/adafruit_motor/motor.py
- [3P] https://core-electronics.com.au/robo-pico-simplifying-robotics-with-raspberry-pi-pico-pico-w.html · https://www.tomshardware.com/reviews/cytron-robo-pico · https://uk.robotshop.com/products/robo-pico-simplifying-robotics-raspberry-pi-pico-pico-robo-pico-only · https://www.cnx-software.com/2023/07/30/robo-pico-review-raspberry-pi-pico-w-motor-sensor-control-board-bocobot-robotic-kit/
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
