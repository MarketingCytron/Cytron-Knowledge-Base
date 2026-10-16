# Robo ESP32 — Verified Reference

| | |
|---|---|
| Product code | `ROBO-ESP32` |
| Family | Maker ESP32 family (ESP32 ecosystem) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Robo ESP32 Rev1.1 Board Datasheet, Rev 1.1, February 2026 (Cytron Google Doc): (Cytron document — link not public) |

**Authority rule:** Datasheet [DS] > Cytron design team [DT] > Cytron product page [PP] > Cytron GitHub [GH] > chip vendor docs [VEN] > third-party [3P].
Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec. It goes to *Needs verification*.

## What it is
- A carrier board that turns a plug-in NodeMCU-format ESP32 into a robot controller. **There is no ESP32 on the Robo ESP32 itself.** It has an "ESP32 Socket: Socket for NodeMCU ESP32" [DS].
- Onboard: a 2-channel DC motor driver, 4 servo ports, 7 Grove ports plus a Maker Port, 2 NeoPixels, 2 user buttons, a piezo buzzer, GPIO status LEDs, motor test buttons, and LiPo/VIN/USB power with an on/off switch [DS].
- Datasheet tagline: Rev 1.0 says "Simplifying Robotics with ESP32", Rev 1.1 says "Simplifying Smart Projects with ESP32" [DS]. The product page title matches Rev 1.1 [PP search listing].

## Board facts
| Item | Value | Src |
|---|---|---|
| Product code | ROBO-ESP32 |  (element14 / RobotShop MPN agree [3P]) |
| Host board | Plug-in NodeMCU ESP32, 30-pin, straight header only | [DS] |
| Revisions | Rev 1.0 (May 2025) and Rev 1.1 (Feb 2026). The spec text in both datasheets is identical. | [DS] |
| Power input (USB, LiPo or VIN) | 3.6 – 6 V | [DS] |
| Battery | Single-cell LiPo / Li-ion on a JST PH2.0 connector. Protected against over-charge and over-discharge. Charged through the USB port of the plugged-in ESP32 board. | [DS] (JST PH2.0: ) |
| VIN terminal | Screw terminal, 3.6 – 6 V (the guide uses an AA battery holder) | [DS],  |
| On/Off switch | Switches all power, including the NodeMCU ESP32 | [DS] |
| DC motor driver | 2 channels. 1 A continuous and 1.5 A peak (< 5 s) per channel. PWM up to 20 kHz. | [DS] |
| Servo ports | 4. Signal pins D4, D5, D18, D19. V+ equals the power source voltage. | [DS] |
| Grove ports | 7 (Grove 1 – 7), 3.3 V supply | [DS] |
| Grove 3V3 total current | 300 mA max | [DS] |
| Maker Port | Qwiic / STEMMA QT / Grove (with conversion cable). Shares D21/D22 with Grove 2. | [DS] |
| Logic levels | VIL -0.3–0.8 V, VIH 2.5–3.6 V, VOL 0–0.3 V, VOH 2.6–3.3 V, analog in 0–3.3 V | [DS] |
| Operating temperature | -20 to 85 °C (Robo ESP32 board only) | [DS] |

## Onboard peripherals and pins
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| Motor 1 (M1A / M1B) | 12 / 13 | Two-input control, see truth table below | [DS] |
| Motor 2 (M2A / M2B) | 14 / 27 | | [DS] |
| Servo ports | 4, 5, 18, 19 | V+ equals the supply voltage | [DS] |
| NeoPixel RGB LEDs | 15 | 2 × WS2812 on one data pin (`numPixels = 2`, NEO_GRB) | [DS], , [GH RGB.ino] |
| User buttons | 34, 35 | Input-only pins. Examples read a press as LOW. | [DS], [GH UserButton.ino] |
| Piezo buzzer | 23 | Has a mute switch. Muting frees D23 for other uses. | [DS],  |
| Grove 1 | 17 (TX2), 16 (RX2) | UART2 | [DS] |
| Grove 2 | 21 (SDA), 22 (SCL) | I2C. Shared with the Maker Port. | [DS] |
| Grove 3 | 26 (DAC2, ADC2_9), 25 (DAC1, ADC2_8) | ADC2: no analog reads while Wi-Fi is on | [DS] |
| Grove 4 | 25 (DAC1, ADC2_8), 33 (Touch8, ADC1_5) | Overlaps Grove 3 (25) and Grove 5 (33) | [DS] |
| Grove 5 | 33 (ADC1_5), 32 (Touch9, ADC1_4) | Overlaps Grove 4 and 6 | [DS] |
| Grove 6 | 32 (ADC1_4), 39 (ADC1_3, input-only) | Overlaps Grove 5 and 7 | [DS] |
| Grove 7 | 39 (ADC1_3), 36 (ADC1_0) | Both pins are input-only | [DS] |
| Grove status LEDs | 16, 17, 21, 22, 25, 26, 32, 33 (the 8 in the Blink example) | Light when the GPIO is HIGH | [DS] (function), [GH Blink.ino] (pins) |
| Motor status LEDs, motor test buttons | Hardware only, no GPIO | A test button runs the motor at full speed: MxA forward, MxB backward | [DS] |

Motor truth table [DS]: A=L, B=L → **Brake**. A=H, B=L → Forward. A=L, B=H → Backward. A=H, B=H → **Coast (Hi-Z)**. Swapping the motor wires reverses the direction.

## Pin rules and gotchas (for code and tutorials)
- **Pins the board itself uses:** 12, 13, 14, 27 (motors), 4, 5, 18, 19 (servos), 15 (NeoPixel), 23 (buzzer) and 34, 35 (buttons) [DS]. Don't use these for external devices.
- **Grove ports overlap:** 25 is on Grove 3 and 4, 33 on Grove 4 and 5, 32 on Grove 5 and 6, and 39 on Grove 6 and 7 [DS]. Never assign two devices to adjacent overlapping ports.
- **Free for user I/O:** 16, 17, 21, 22, 25, 26, 32, 33, 36 and 39 (the Grove ports) [DS]. 36 and 39 are input-only [DS].
- **Analog with Wi-Fi:** use Grove 4–7 (ADC1 pins 33, 32, 39, 36). Grove 3 is ADC2 only and fails while Wi-Fi is on [DS], .
- **HIGH/HIGH means coast, not brake.** Stop with LOW/LOW (brake) [DS]. With `CytronMotorDriver` in `PWM_PWM` mode, the official example uses `CytronMD motor1(PWM_PWM, 12, 13)` and `motor2(PWM_PWM, 14, 27)` [GH DCMotor.ino].
- **Motor current limit:** 1 A continuous and 1.5 A peak for under 5 s per channel [DS].
- **Buttons on 34/35:** ESP32 GPIO34–39 have no internal pull-up or pull-down resistors [VEN], so the `INPUT_PULLUP` in the examples has no effect there. If a button reads correctly, the pull-up must be on the board itself (see *Needs verification*).
- **Strapping pins [VEN]:** 12 (M1A) must not be held HIGH at reset on 3.3 V-flash modules. 5 (servo) and 15 (NeoPixel) are also strapping pins. Don't drive Motor 1 or attach pull-ups on these pins during boot.
- **Avoid:** GPIO1 and GPIO3 (USB serial) and GPIO6–11 (flash) [VEN].
- **I2C:** Grove 2 and the Maker Port are the same bus (21/22) [DS]. I2C traffic will flicker the D21/D22 status LEDs.
- **Power switch:** keep it ON while uploading and running code . Servos and motors take power through the Robo ESP32 rail [DS].

## Power and electrical limits
- Inputs: USB (through the plug-in board), a 1-cell LiPo/Li-ion, or VIN 3.6–6 V [DS]. Connecting LiPo and VIN at the same time is "not recommended … although it's perfectly safe" [DS].
- Motor and servo voltage (Vmotor = Vservo) [DS]:
  - USB only: VUSB − 0.4 V
  - LiPo only or VIN only: VLiPo or VIN
  - USB + LiPo: VUSB − 0.4 V
  - USB + VIN: VIN < VUSB → VUSB − 0.4 V. VIN > VUSB by less than 0.6 V → VIN − 0.4 V. VIN − VUSB > 0.6 V → VIN.
- Grove 3V3 total: 300 mA [DS].
- The battery charges through the USB port of the plug-in ESP32 board [DS]. Charge current is not specified.
- If the board won't turn on with a battery connected, charge the battery to reset the protection circuit [DS].

## Software support
- **Libraries used by the official examples [GH]:** Adafruit NeoPixel, ESP32Servo, CytronMotorDriver, U8g2.
- **MicroBlocks:** web or PC IDE. Flash it with Settings → "update firmware on board" → ESP32 . The examples are block programs; [GH] has a `Getting Started Guide/MicroBlocks` folder, but its contents were not listed.
- **Official Arduino examples** (`Getting Started Guide/Arduino/`) [GH]: Blink, RGB, UserButton, Buzzer, DCMotor, Servo, AnalogRead (Maker Soil on Grove 7, OUT = D36), DigitalRead (HC-SR04, TRIG 26 / ECHO 25), OLED (SSD1315 on 21/22 using U8g2).

## Compatibility and accessories
- **NodeMCU ESP32 (30-pin, straight header):** the officially stated host [DS]. Boards with 38 pins or angled headers are not supported [DS].
- **Maker ESP32:** Cytron describes it as compatible (per the brief and the Cytron Maker ESP32 bundle with a Robo ESP32 option in project notes). The Maker ESP32 datasheet does not mention Robo ESP32. Pin compatibility is supported by the Maker ESP32 datasheet:
  - Its 30-pin header is "Compatible with NodeMCU ESP32 form factor" [DS Maker ESP32 Rev 1.1].
  - Its header order matches the DevKit V1 30-pin layout that the Robo ESP32 datasheet uses for its pinout [DS].
- **Pin clashes when a Maker ESP32 is stacked on the Robo ESP32** (derived from both datasheets):
  - GPIO4: Maker ESP32 user button = Robo servo port D4. Don't use servo D4 while you need the button.
  - GPIO26: Maker ESP32 buzzer = one pin of Robo Grove 3 (and Grove 3's status LED).
  - GPIO23: Robo buzzer = a Maker ESP32 GPIO LED. The two buzzers (D23 and D26) have separate mute switches.
  - Maker ESP32 GPIO LEDs sit on 12, 13 and 27 (motor) and 18 and 19 (servo). They will flicker with motor PWM or servo pulses. This is harmless.
  - USB on a Maker ESP32 is USB-C with a CH9102F bridge (WCH CH343SER driver), **not** CP210x [DS Maker ESP32 / project reference, DT-confirmed 2026-09-28].
  - Maker ESP32 VIN is rated 4.6–5.5 V, which is narrower than the Robo ESP32's 3.6–6 V input. How the Robo feeds the ESP32 board is only shown in the power-tree figure (see *Needs verification*).
- **Grove / Qwiic / STEMMA QT modules** through the Grove ports and Maker Port [DS]. Grove supplies 3.3 V [DS].

## Common mistakes in older tutorials / migration notes
- **LEDC API:** Cytron's line-following and PS4 project code uses `ledcAttachPin()` / channel setup . That is the ESP32 Arduino core 2.x API, removed in core 3.x [VEN]. Migrate to `ledcAttach(pin, freq, res)` or use CytronMotorDriver.
- **DigitalRead:** both the Arduino guide and the sketch header say "Grove 2", but the code uses 26/25, which is Grove 3 [GH],  vs [DS].
- **Blynk tutorial:** the Drive guide says DHT DATA is on "D32 (Grove 3)", but D32 is on Grove 5/6 [DS], and the repo code uses GPIO16 (Grove 1) [GH].
- **Code comment bugs in official examples [GH]:**
  - DCMotor says `255` is "50% speed".
  - AnalogRead says "2^8 resolution" but divides by 4096 (12-bit).
  - Servo's return sweep starts at `pos = 200`.
  - Servo comments say 15 ms where the code uses 10 ms.
  - The OLED sketch drives an SSD1315 with an SSD1306 software-I2C constructor, and the README lists "SSD1306".

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Grove port for the HC-SR04 example (pins 26/25) | [GH] DigitalRead.ino and  Arduino section: "Grove 2" | [DS]: 26/25 = Grove 3.  MicroBlocks section: Grove 3. | [DS] wins: Grove 3 |
| Blynk DHT11 pin |  Blynk section: D32 (Grove 3) | [GH] Blynk.ino: GPIO16. [DS]: Grove 3 = 26/25. | Use the [DS] mapping. The tutorial must name one port and pin that agree with [DS]. |
| Number of Grove status LEDs | [3P] RobotShop: "10 status LEDs" | [GH] Blink.ino drives 8 (16, 17, 21, 22, 25, 26, 32, 33). [DS] gives no count. | Unresolved. Listed under *Needs verification*. |

## Needs verification
- How the ESP32 board is powered from LiPo or VIN (boost to 5 V on its VIN pin, or feeding 3V3?), and whether the Grove 3V3 comes from the plug-in board's 3V3 pin. Only the datasheet power-tree figure shows this, and it could not be read. This matters for Maker ESP32, whose VIN is rated 4.6–5.5 V.
- Charging the LiPo from a Maker ESP32's USB-C. Charge current is not stated.
- Whether the user buttons on 34/35 have pull-ups on the board, and that they are active-LOW. This is inferred from the example code only.
- Grove status LED count and which pins have them: 8 per [GH], 10 per [3P]. Do 36 and 39 have LEDs?
- Which GPIO lands on Grove signal wire 1 (yellow) and which on wire 2 (white) for each port. [GH] AnalogRead implies Grove 7: D39 = DIS, D36 = OUT.
- Motor driver IC part number. Board dimensions and mounting holes (figure only).
- Hardware differences between Rev 1.0 and Rev 1.1. The text is identical, but the figures were not compared.
- MicroPython support: is there any official firmware, library or example?
- An official Cytron statement that Maker ESP32 is compatible with Robo ESP32 (the Maker ESP32 datasheet doesn't say so). Also check whether GPIO12 (M1A) has any pull-up on the Robo ESP32 that could affect boot.
- Current product-page status and SKU wording (my.cytron.io could not be fetched).

## Sources
- [DS] Robo ESP32 Rev1.1 Board Datasheet (Rev 1.1, Feb 2026): (Cytron document — link not public)
- [DS] Robo ESP32 Board Datasheet (Rev 1.0, May 2025): (Cytron document — link not public)
- [DS] Maker ESP32 Datasheet Rev 1.1 (Sept 2026): (Cytron document — link not public)
- [PP] https://my.cytron.io/p-robo-esp32 (title from search listing only, page not fetched). Tutorial: https://www.cytron.io/tutorial/getting-started-guide-with-robo-esp32
- [GH] https://github.com/CytronTechnologies/Cytron-ROBO-ESP32 (README, `Getting Started Guide/Arduino/*/*.ino`, `Internet of Things/Blynk/Blynk.ino`)
- [VEN] https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-reference/peripherals/gpio.html
- [3P] https://www.robotshop.com/products/cytron-robo-esp32-simplifying-robotics-w-esp32 · https://my.element14.com/cytron/robo-esp32/robo-kit-esp32-wi-fi-bluetooth/dp/4871671
