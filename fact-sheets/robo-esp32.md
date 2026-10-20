# Product fact sheets

## Product name
Robo ESP32

## Aliases
ROBO-ESP32, RoboESP32

## What it is
A carrier board that turns a plug-in 30-pin NodeMCU ESP32 into a robot controller. There is no ESP32 on the Robo ESP32 itself; the ESP32 board is sold separately.

## Specs and functions
- Product code: ROBO-ESP32
- Revisions: Rev 1.0 (May 2025) and Rev 1.1 (Feb 2026); spec text is identical in both datasheets
- ESP32 socket: for NodeMCU ESP32, 30-pin straight header only
- Power input (USB, LiPo or VIN): 3.6 – 6 V
- Battery: single-cell LiPo / Li-ion on a JST PH2.0 connector, with over-charge and over-discharge protection; charged through the USB port of the plugged-in ESP32 board
- VIN: screw terminal, 3.6 – 6 V
- On/Off switch: switches all power, including the NodeMCU ESP32
- DC motor driver: 2 channels, 1 A continuous and 1.5 A peak (< 5 s) per channel, PWM up to 20 kHz
- Motor pins: Motor 1 M1A/M1B = GPIO12/13; Motor 2 M2A/M2B = GPIO14/27
- Motor truth table: A=L, B=L → Brake; A=H, B=L → Forward; A=L, B=H → Backward; A=H, B=H → Coast (Hi-Z)
- Motor status LEDs and motor test buttons (hardware only; test button runs the motor at full speed: MxA forward, MxB backward)
- Servo ports: 4, signal pins D4, D5, D18, D19; servo V+ equals the power source voltage
- Motor and servo voltage: USB only → VUSB − 0.4 V; LiPo or VIN only → VLiPo or VIN; USB + LiPo → VUSB − 0.4 V; USB + VIN: VIN < VUSB → VUSB − 0.4 V, VIN > VUSB by less than 0.6 V → VIN − 0.4 V, VIN − VUSB > 0.6 V → VIN
- NeoPixel RGB LEDs: 2 × WS2812 on GPIO15
- User buttons: GPIO34 and GPIO35 (examples read a press as LOW)
- Piezo buzzer: GPIO23, with mute switch (muting frees D23)
- Grove ports: 7, 3.3 V supply, 300 mA max total
- Grove 1: 17 (TX2), 16 (RX2) — UART2
- Grove 2: 21 (SDA), 22 (SCL) — I²C, shared with the Maker Port
- Grove 3: 26 (DAC2, ADC2_9), 25 (DAC1, ADC2_8)
- Grove 4: 25 (DAC1, ADC2_8), 33 (Touch8, ADC1_5)
- Grove 5: 33 (ADC1_5), 32 (Touch9, ADC1_4)
- Grove 6: 32 (ADC1_4), 39 (ADC1_3, input-only)
- Grove 7: 39 (ADC1_3), 36 (ADC1_0)
- Grove status LEDs light when the GPIO is HIGH; the official Blink example drives 16, 17, 21, 22, 25, 26, 32, 33
- Logic levels: VIL -0.3–0.8 V, VIH 2.5–3.6 V, VOL 0–0.3 V, VOH 2.6–3.3 V, analog in 0–3.3 V
- Operating temperature: -20 to 85 °C (Robo ESP32 board only)
- USB-UART: none on the Robo ESP32; it is on the plug-in board
- Reset button: product page states a "built-in reset button"; the datasheet function table lists none (it may be the plug-in board's EN button)
- Only one power source is needed for the board and the motors (product page)
- Package contents: 1× Robo ESP32, 1× transparent Phillips screwdriver, 1× silicone rubber feet (pack of 4), 4× Grove-to-female-header cables (product page); no ESP32 board included
- GPIO status LEDs: 10 (product page)
- Each motor channel up to 1 A continuous (product page)

## Interfaces and compatibility
- Socket for a 30-pin, straight-header NodeMCU ESP32
- Maker Port: Qwiic / STEMMA QT / Grove (with conversion cable), sharing D21/D22 with Grove 2
- 7 Grove ports, 4 servo ports, 2 motor outputs, JST PH2.0 battery connector, VIN screw terminal
- Arduino IDE: esp32 package by Espressif, board "ESP32 Dev Module"; official examples use Adafruit NeoPixel, ESP32Servo, CytronMotorDriver, U8g2
- Official Arduino examples: Blink, RGB, UserButton, Buzzer, DCMotor, Servo, AnalogRead, DigitalRead, OLED (SSD1315 on 21/22)
- MicroBlocks: flash via Settings → "update firmware on board" → ESP32
- FreeRTOS examples (dual-core, task control) in the Cytron Getting Started guide
- Software support: product page states Arduino IDE, MicroPython, C++ and MicroBlocks; official examples exist only for Arduino IDE and MicroBlocks
- Maker ESP32: the Maker ESP32 product page says it is "fully compatible with expansion boards like the Robo ESP32" and sells a Maker ESP32 + Robo ESP32 bundle; the Robo ESP32 page names only the NodeMCU ESP32

## Use cases
- Robotics with ESP32 (basic movement, obstacle avoidance, line following, servo gripper)
- Wi-Fi car
- PS4 controller (Bluepad32) and Bluetooth app control
- IoT projects: ThingSpeak, Blynk, Telegram
- Controller for the OjanBot ESP32 kit
- Cytron tutorial: [Smart Farming with ESP32](https://my.cytron.io/tutorial/farm-automation-system-using-roboesp32)
- Cytron tutorial: [Smart Dustbin with ESP32](https://my.cytron.io/tutorial/smart-dustbin-with-robo-esp32)
- Cytron tutorial: [Getting Started with Robo ESP32](https://my.cytron.io/tutorial/getting-started-guide-with-robo-esp32)
- Cytron tutorial: [Control LED & Servo from Raspberry Pi via I2C with RoboESP32](https://my.cytron.io/tutorial/robo-esp32-raspberry-pi-i2c)
- Cytron tutorial: [Top ESP32 Projects to Kickstart Your IoT Journey part 3](https://my.cytron.io/tutorial/top-esp32-projects-to-kickstart-your-iot-journey-part-3)

## Known limitations
- No ESP32 on the board; a NodeMCU ESP32 must be bought separately
- Only 30-pin straight-header NodeMCU ESP32 boards fit; 38-pin or angled-header boards are not supported
- Pins used by the board: 12, 13, 14, 27 (motors), 4, 5, 18, 19 (servos), 15 (NeoPixel), 23 (buzzer), 34, 35 (buttons)
- Grove ports overlap: 25 on Grove 3 and 4, 33 on Grove 4 and 5, 32 on Grove 5 and 6, 39 on Grove 6 and 7
- Grove 3 is ADC2 only and fails for analog reads while Wi-Fi is on; use Grove 4–7 for analog with Wi-Fi
- HIGH/HIGH on a motor channel is coast, not brake; stop with LOW/LOW
- Motor current: 1 A continuous, 1.5 A peak for under 5 s per channel
- GPIO34–39 have no internal pull-up or pull-down; INPUT_PULLUP in the examples has no effect there
- Strapping pins: GPIO12 (M1A) must not be HIGH at reset; GPIO5 (servo) and GPIO15 (NeoPixel) are also strapping pins
- Avoid GPIO1/3 (USB serial) and GPIO6–11 (flash)
- Grove 2 and the Maker Port are the same I²C bus
- Grove 3V3 total: 300 mA
- LiPo and VIN at the same time is "not recommended … although it's perfectly safe"
- Battery charge current is not specified
- If the board won't turn on with a battery connected, charge the battery to reset the protection circuit
- Power switch must be ON while uploading and running code
- Official example errors: DigitalRead says "Grove 2" but uses Grove 3 pins (26/25); Blynk guide puts the DHT on "D32 (Grove 3)" while the code uses GPIO16; line-following/PS4 code uses the core 2.x LEDC API; PS4 code comments don't match the motor pins
- Maker ESP32 on Robo ESP32 (derived from both datasheets): GPIO4 = Maker user button and servo D4; GPIO26 = Maker buzzer and Grove 3; GPIO23 = Robo buzzer and a Maker LED; Maker ESP32 VIN is rated 4.6–5.5 V

## Positioning (kept apart from specs)
- Datasheet Rev 1.0 tagline: "Simplifying Robotics with ESP32"
- Datasheet Rev 1.1 tagline: "Simplifying Smart Projects with ESP32" (the product page title matches Rev 1.1)

## Price band
RM62.58 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-robo-esp32

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

