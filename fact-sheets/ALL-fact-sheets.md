# Product fact sheets

## Product name
Maker ESP32

## Aliases
MAKER-ESP32, MakerESP32

## What it is
An ESP32 development board built around the ESP32-WROOM-32E-N8 module, in the NodeMCU ESP32 pin layout. It adds 14 GPIO LEDs, RX/TX LEDs, a user button, a passive buzzer with mute switch, USB-C and an I²C Maker Port.

## Specs and functions
- Product code: MAKER-ESP32
- Module: ESP32-WROOM-32E-N8 (8 MB flash, no PSRAM)
- Processor: dual-core Xtensa® LX6, up to 240MHz (product page)
- SRAM: 520KB (product page)
- Wireless: Wi-Fi 802.11 b/g/n, 2.4GHz; Bluetooth 4.2 BLE (product page)
- USB-to-UART chip: WCH CH9102F (Cytron design team, 2026-09-28); Windows driver if needed: WCH CH343SER
- Firmware upload: automatic, without holding the BOOT button (launch page)
- Power input: USB-C 5 V, or VIN pin 4.6–5.5 V
- VIN pin outputs 5 V when the board is on USB power (from USB, not from the 3.3 V LDO) (Cytron design team)
- 3V3 rail: LDO, 700 mA max, shared by the module, LEDs, buzzer, Maker Port and USB-UART (Datasheet Rev 1.1). Datasheet Rev 1.0 stated 1.35 A; Rev 1.1 supersedes it.
- Digital input: low -0.3 to 0.8V, high 2.5 to 3.6V
- Digital output: low 0–0.4V, high 2.6–3.3V
- Analog input range: 0–3.3V
- GPIO output current: datasheet states 28mA low-level sink and 40mA high-level source (absolute max); product page states 40mA maximum output current per I/O pin
- Internal pull-up resistor 45kΩ; internal pull-down resistor 45kΩ
- Operating temperature: -10 to 70 °C (Datasheet Rev 1.1). Datasheet Rev 1.0 stated -40°C to 85°C; Rev 1.1 supersedes it.
- Dimensions: 58mm × 28.4mm (product page and datasheet); datasheet drawing shows 51.7 mm for the PCB
- 14 GPIO LEDs, lit when the pin is HIGH: GPIO2, 12, 13, 16, 17, 18, 19, 21, 22, 23, 25, 27, 32, 33
- LED bar order used by the official examples: 32, 33, 25, 27, 12, 13, 23, 22, 21, 19, 18, 17, 16, 2
- RX and TX LEDs (serial activity); 1 × 3.3V power LED
- Buttons: BOOT (GPIO0), EN (reset), user button on GPIO4
- Programmable passive piezo buzzer on GPIO26, with physical mute switch (Up = buzzer ON, Down = muted)
- Header top row: 23, 22, TX(1), RX(3), 21, 19, 18, 5, 17, 16, 4, 2, 15, GND, 3V3
- Header bottom row: EN, VP(36), VN(39), 34, 35, 32, 33, 25, 26, 27, 14, 12, 13, GND, VIN
- Wireless module ESP32-WROOM-32E is type-approved by SIRIM under Cytron Technologies (launch page)

## Interfaces and compatibility
- USB-C: power, firmware upload and serial monitoring
- Maker Port: 4-way JST-SH, I²C — GND, 3V3, SDA = GPIO21, SCL = GPIO22
- Maker Port is compatible with Qwiic and STEMMA QT; Grove modules through a conversion cable
- NodeMCU ESP32-compatible form factor and pin layout; existing NodeMCU ESP32 code and tutorials work without changes (launch page)
- Compatible with Robo ESP32 and the NodeMCU ESP32 Expansion Board (product page)
- Arduino IDE ("esp32 by Espressif Systems" package, board "ESP32 Dev Module") and ESP-IDF
- Official examples use the ESP32 Arduino core 3.x API (ledcAttach()): Out_of_the_box_Demo_Code, LEDs_Fade, LEDs_Fill_Button, Buzzer_Melody
- No manual driver installation needed before starting (launch page)

## Use cases
- First ESP32 / programming board
- Classroom / teaching
- Smart electronics projects
- IoT projects
- Connected-device prototyping
- Robotics
- Final-year projects
- Existing NodeMCU ESP32 projects
- I²C sensor/module prototyping through the Maker Port
- GPIO learning and debugging with the onboard LEDs

## Known limitations
- GPIO LEDs are on only the 14 listed pins, not on every GPIO
- Maker Port is I²C only; SPI or UART through it is not stated
- Grove modules need a conversion cable
- The 700 mA 3V3 limit includes onboard usage
- 3.3 V logic; analog input limited to 0–3.3 V. 5 V sensors must not drive GPIO directly
- Relays, motors and solenoids need a driver
- GPIO26 is shared with the buzzer: do not use it for SPI CS or data unless the buzzer is muted
- GPIO4 is shared with the user button
- GPIO0 is not on the header (Boot button only)
- GPIO34, 35, 36, 39 are input-only, with no internal pull resistors
- GPIO6–11 are used by internal flash and are not broken out
- Strapping pins 0, 2, 5, 12, 15: GPIO12 must not be pulled HIGH at boot
- GPIO1/3 are used by USB serial
- ADC2 pins (2, 4, 12–15, 25–27) do not work while Wi-Fi is on; Wi-Fi projects with analog sensors must use ADC1 (32, 33, 34, 35, 36, 39)
- I²C activity on GPIO21/22 makes those LEDs flicker
- Use one power source at a time: USB-C and VIN together is protected but not recommended; external VIN must stay within 4.6–5.5 V
- Only one module/flash variant is stated (ESP32-WROOM-32E-N8, 8MB); no PSRAM
- Core 2.x LEDC functions (ledcSetup(), ledcAttachPin()) do not compile on core 3.x
- On Robo ESP32 (derived from both datasheets): GPIO4 is both the user button and Robo servo D4; GPIO26 is both the buzzer and a Robo Grove 3 pin; GPIO23 is the Robo buzzer and a Maker ESP32 LED

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Digital Making."
- Launch-page headline: "The ESP32 you know. Easier to learn, better to build with."
- Three pillars: Start Faster (USB-C, upload without holding BOOT), Understand Better (14 GPIO LEDs and RX/TX indicators), Build Further (8MB flash, built-in Wi-Fi/Bluetooth, Maker Port)
- Launch-page comparison vs NodeMCU ESP32: 8MB vs 4MB flash, USB Type-C vs Micro USB, 14 GPIO LEDs vs 1, plus RX/TX LEDs, passive buzzer, user button and Maker Port

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-maker-esp32

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

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

## Interfaces and compatibility
- Socket for a 30-pin, straight-header NodeMCU ESP32
- Maker Port: Qwiic / STEMMA QT / Grove (with conversion cable), sharing D21/D22 with Grove 2
- 7 Grove ports, 4 servo ports, 2 motor outputs, JST PH2.0 battery connector, VIN screw terminal
- Arduino IDE: esp32 package by Espressif, board "ESP32 Dev Module"; official examples use Adafruit NeoPixel, ESP32Servo, CytronMotorDriver, U8g2
- Official Arduino examples: Blink, RGB, UserButton, Buzzer, DCMotor, Servo, AnalogRead, DigitalRead, OLED (SSD1315 on 21/22)
- MicroBlocks: flash via Settings → "update firmware on board" → ESP32
- FreeRTOS examples (dual-core, task control) in the Cytron Getting Started guide
- Maker ESP32: Cytron describes it as compatible (30-pin NodeMCU ESP32 form factor)

## Use cases
- Robotics with ESP32 (basic movement, obstacle avoidance, line following, servo gripper)
- Wi-Fi car
- PS4 controller (Bluepad32) and Bluetooth app control
- IoT projects: ThingSpeak, Blynk, Telegram
- Controller for the OjanBot ESP32 kit

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
[NOT STATED]

## Product page
https://my.cytron.io/p-robo-esp32

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
Maker Feather AIoT S3

## Aliases
MAKER-FEATHER-AIOT-S3, MAKER-FEATHER-AIOT-S3-H, V-MAKER-FEATHER-AIOT-S3, Feather AIoT S3, Maker Feather S3

## What it is
An ESP32-S3 development board in the Adafruit Feather form factor, with GPIO status LEDs, an RGB LED, a buzzer, a user button, three JST-SH Maker Ports, a switchable 3.3 V peripheral rail and a single-cell LiPo charger.

## Specs and functions
- Product codes: MAKER-FEATHER-AIOT-S3 (basic, no headers); MAKER-FEATHER-AIOT-S3-H (pre-soldered female headers); parent listing V-MAKER-FEATHER-AIOT-S3
- Module: Espressif ESP32-S3-WROOM-1-N8R8
- Flash / PSRAM: 8 MB flash, 8 MB PSRAM
- USB: USB-C wired straight to ESP32-S3 native USB (D-/D+ = GPIO19/GPIO20); no USB-UART bridge chip on the schematic
- USB VID 0x303A; PID 0x80F8 = Arduino core, 0x80F9 = CircuitPython, 0x80FA = UF2 bootloader
- UF2 drive name: MFAS3BOOT
- Ships with the UF2 bootloader and CircuitPython preinstalled
- Buttons: RESET, BOOT (GPIO0), USER (GPIO3, 10 kΩ pull-up, pressed = LOW)
- Status LED: GPIO2, active high
- RGB LED: WS2812B on GPIO46, powered from VP
- Piezo buzzer (passive): GPIO12, driven through a MOSFET from VP, via mute switch
- VP (VPeripheral) enable: GPIO11, HIGH = VP on
- VIN sense: GPIO13 (A12), V_ADC = 0.6 × VIN, where VIN = the higher of VUSB and VBATT
- 11 GPIO LEDs (lit when HIGH, buffered by MOSFETs, anodes on VP): GPIO14, 15, 16, 21, 38, 39, 40, 41, 42, 47, 48
- Indicator LEDs: 3V3 power, VP power, charge (CHG), status (GPIO2), 11 GPIO LEDs, 1 RGB LED
- USB input (VUSB): 4.5–5.5 VDC
- LiPo input (VBAT): 3.3–4.2 VDC, single-cell LiPo / Li-ion only
- 3V3 max current (including onboard use): 1000 mA; regulator SY8088AAC synchronous buck
- Charger: MCP73831T-2ACI/OT, charges from USB; CHG LED on while charging
- Battery protection: CT2105, overcharge and over-discharge
- EN pin: pulling it LOW shuts off 3V3
- Operating temperature: −20 to 65 °C
- Analog input range: −0.3 to 3.6 V absolute
- Digital: VIH 2.5–3.6 V, VIL −0.3–0.8 V; source up to 40 mA, sink up to 28 mA; internal pull-up/pull-down ≈45 kΩ
- Default I²C: SDA 42, SCL 41. Default SPI: SCK 17, MOSI 8, MISO 18, SS 7. Default UART: TX 15, RX 16
- Feather left header: RST, 3V3, VP, GND, A0/D10, A1/D9, A2/D6, A3/D5, A4/D4, A5/D7, SCK/D17 (A6), MOSI/D8 (A7), MISO/D18 (A8), RX/D16 (A9), TX/D15 (A10), DBG (GPIO43)
- Feather right header: BAT, EN, USB (VBUS), D14 (A11), D21, D47, D48, D38, D39, D40, SCL/D41, SDA/D42
- Package contents: 1 board + 3 Grove to JST-SH (Qwiic/STEMMA QT) cables (product page)
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Adafruit Feather footprint; FeatherWing add-ons
- Maker Port H #1: GND, VP, SDA = GPIO42, SCL = GPIO41
- Maker Port H #2: GND, VP, GPIO4 (A4), GPIO7 (A5)
- Maker Port V: GND, 3V3 (always on), GPIO6 (A2), GPIO5 (A3)
- Maker Ports are JST-SH 4-pin: Qwiic / STEMMA QT direct, Grove through a conversion cable
- Arduino (Espressif arduino-esp32 core): board "Cytron Maker Feather AIoT S3", FQBN esp32:esp32:cytron_maker_feather_aiot_s3
- CircuitPython: board id cytron_maker_feather_aiot_s3
- MicroPython and ESP-IDF listed as supported (product page)
- UF2 upload: double-press RESET, drag a .uf2 onto MFAS3BOOT. ROM bootloader: hold BOOT, press and release RESET
- Sold within the Cytron IoT Kit and the "Maker Feather S3 IoT Bundles" listing

## Use cases
- IoT work
- Teaching
- Cytron IoT Kit

## Known limitations
- The GPIO LEDs, RGB LED, buzzer and both horizontal Maker Ports run from VP: GPIO11 must be HIGH first. CircuitPython and the Arduino core turn VP on; ESP-IDF and generic MicroPython do not
- Strapping pins GPIO0, GPIO3, GPIO45, GPIO46: do not add external pull-ups or pull-downs
- GPIO19/20 are native USB D-/D+ and not broken out; reassigning them stops USB serial and upload
- GPIO35, 36, 37 are used by the octal PSRAM and not broken out
- ADC2 (GPIO11–20) is shared with Wi-Fi: A6, A8, A9, A10, A11 and A12 / VIN sense (GPIO13) may fail while Wi-Fi is active
- GPIO43 (DBG) carries the boot log
- Inputs are not 5 V tolerant (3.6 V max)
- Single-cell LiPo / Li-ion only
- If the board will not power on from a battery, charge it over USB to reset the protection
- Flashing through the ROM bootloader overwrites the UF2 bootloader; installing TinyUF2 erases the board, including CIRCUITPY files
- Uploading an Arduino sketch with the wrong board selected can corrupt or overwrite the UF2 bootloader
- An labels are not GPIO numbers (A0 = GPIO10, A1 = GPIO9, A2 = GPIO6, A3 = GPIO5, A4 = GPIO4, A5 = GPIO7)
- No board-specific MicroPython build on micropython.org
- The third left-header pin is VP, not AREF; check FeatherWings that use AREF
- GPIO1 is not broken out; ESP32-S3 has no DAC
- USB is native: the COM port changes between app, ROM bootloader and UF2 mode; with USB CDC On Boot disabled, Serial prints nothing over USB

## Positioning (kept apart from specs)
- Product listing name: "Simplifying AIoT with ESP32" (V-MAKER-FEATHER-AIOT-S3 product page)
- Onboard extras aimed at teaching and IoT work

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-v-maker-feather-aiot-s3-simplifying-aiot-with-esp32

## Datasheet
https://docs.google.com/document/d/1vVYSdn84I8Hvi9SWHU54lhH_vWlhD3mwJ6pcSyLNGcE/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1vVYSdn84I8Hvi9SWHU54lhH_vWlhD3mwJ6pcSyLNGcE/edit

# Product fact sheets

## Product name
Maker UNO

## Aliases
MAKER-UNO, Maker UNO, Maker UNO: Simplifying Arduino for Education

## What it is
An Arduino UNO-compatible board built on the ATmega328P, powered and programmed through a USB Micro-B socket via a CH340 USB-to-serial chip. It adds LEDs on the digital pins, a piezo buzzer on pin 8 and a programmable push button on pin 2.

## Specs and functions
- Product code: MAKER-UNO
- Microcontroller: SMD ATmega328P (the same microcontroller as the Arduino UNO) with Optiboot (UNO) bootloader
- Clock speed: 16MHz
- Flash memory: 32k
- Digital I/O pins: 14 (6 PWM outputs)
- Analog inputs: 6
- I/O levels: 0-5V outputs with 3.3V compatible inputs
- USB-to-serial: CH340 (board layout names the chip CH340G)
- USB connector: USB Micro-B socket (main power, program upload, debugging)
- Input voltage via USB connector: 4.8 V min, 5.2 V max
- Power: USB 5V from computer, power bank or standard USB adapter; Cytron LiPo Power Shield for portable use
- 3.3V voltage regulator: 500mA maximum; DC current for 3.3V pin 500 mA max continuous
- DC current per I/O pin: 20 mA max
- 5V output current: [NOT STATED]
- LEDs: LED array for 5V, 3.3V, TX, RX and all digital pins; standard LED on pin 13 (user manual: a programmable LED on every digital pin, D0 to D13; product page: "12x LEDs")
- Pin LEDs are driven through a series of MOSFETs, so an LED can be controlled or act as an indicator for an input, even a pull-up input
- USB-serial LED shows upload and Serial Monitor activity
- Programmable push button: pin 2 to GND, configure as INPUT_PULLUP
- Piezo buzzer: pin 8, through a slide switch (on = buzzer, off = pin 8 free for other uses)
- Reset button
- ISP 6-pin (2x3) header for AVR programmers; also usable for SPI
- PCB colour: purple
- Packing list: 1 × Maker Uno (Code: MAKER-UNO); product page: pin header label stickers included
- Warranty: 6 months, manufacturing defects only (user manual Rev 1.0); product page: 12 months
- Dimensions: [NOT STATED]
- User's Manual: Rev 1.0, Dec 2017; board package section updated 21 March 2018

## Interfaces and compatibility
- Arduino UNO R3-standard female headers; R3 shield compatible
- SDA, SCL and IOREF pins are broken out as on the UNO R3
- No Vin pin: Arduino shields that require Vin are not compatible
- No DC jack: power through USB only (product page)
- Differences from Arduino UNO: CH340 instead of ATmega16u2 (product page: "to bring down the cost"), USB Micro-B, no DC jack, no Vin pin, onboard LEDs, buzzer and button
- Arduino IDE: select board "Arduino/Genuino Uno" and the correct COM port (Cytron advises this board "for safety purpose")
- Optional Cytron board package "Maker Uno" (Boards Manager URL https://cytrontechnologies.github.io/package_cytron_makeruno_index.json); it sets all digital pins to OUTPUT by default; latest version in the index 1.1.0-rc2
- CH340 driver needed; port appears as "USB-SERIAL CH340 (COMx)" in Device Manager
- MicroPython / CircuitPython: [NOT STATED]

## Use cases
- Arduino learning in classrooms (boards "used in classes are powered using USB")
- Testing code without external parts using the onboard LEDs, buzzer and button
- Troubleshooting with pin LEDs that show input state
- Portable projects powered by a power bank or Cytron LiPo Power Shield

## Known limitations
- Power from USB only, 4.8–5.2 V; no DC jack and no Vin pin
- Shields that need Vin do not work
- 3.3V pin limited to 500 mA; each I/O pin to 20 mA
- Pin 8 is shared with the buzzer; switch the buzzer off to use pin 8 for other purposes
- Pin 2 is shared with the onboard button
- With board "Arduino/Genuino Uno", floating input pins can make the pin LEDs light up randomly
- The Maker Uno board package sets all digital pins to OUTPUT by default
- Use one power source at a time
- Needs the CH340 driver for USB programming
- 5V output current and protection features: [NOT STATED]

## Positioning (kept apart from specs)
- Product page: "an Arduino Compatible board specially designed to simplify building your projects"
- User manual: "PURPLE PCB !"; three extra features that make it "more suitable for beginner"

## Price band
[NOT STATED]

## Product page
https://www.cytron.com.my/p-maker-uno-simplifying-arduino-for-education

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-250/pdf/cytron-maker-uno-microcontroller-datasheet1.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-250/pdf/cytron-maker-uno-microcontroller-datasheet1.pdf

# Product fact sheets

## Product name
Maker UNO Plus for Education (Arduino Compatible)

## Aliases
MAKER-UNO-PLUS, Maker UNO Plus, Maker UNO+, Cytron Maker UNO Plus, Maker UNO Plus: Simplifying Arduino for Education, Maker UNO Plus for Education

## What it is
An Arduino UNO R3-compatible board built on the SMD ATmega328P, powered and programmed through a USB Micro-B socket via an FT231X USB-to-serial chip. It adds LEDs on the digital pins, a piezo buzzer on pin 8 with a slide switch and a programmable push button on pin 2.

## Specs and functions
- Product code: MAKER-UNO-PLUS
- User's Manual: Rev 1.0, Oct 2018 (no separate datasheet)
- Microcontroller: SMD ATmega328P (the same microcontroller as the Arduino UNO) with Optiboot (UNO) bootloader
- USB-to-serial: FT231X
- USB connector: USB Micro-B socket (main supply, program upload, Serial Monitor)
- Operating voltage: 5V
- Input voltage via USB connector: 4.8 V min, 5.2 V max; "5V (USB only)"
- 5V current: "USB source"
- 3.3V voltage regulator: 500mA maximum; DC current for 3.3V pin 500 mA max continuous
- DC current per I/O pin: 20 mA max
- I/O levels: 0-5V outputs with 3.3V compatible inputs
- Digital I/O pins: 14 (6 PWM outputs); analog inputs: 6
- UART, SPI, I2C: 1, 1, 1; external interrupts: 2
- Flash, SRAM, EEPROM: 32KB, 2KB, 1KB
- Clock speed: 16MHz
- ISP 6-pin (2x3) header, for AVR programmer; also usable for SPI
- LED array for 5V, 3.3V, TX, RX and the digital pins; programmable indicator LEDs at pins 2 – 13 (user manual introduction says D0 to D13); standard LED on pin 13
- Pin LEDs driven through a series of MOSFETs, so each LED can be controlled as an output or act as an input indicator, even for input pull-up
- USB-serial LED shows upload and Serial Monitor data
- Programmable push button: pin 2 to GND, configure as INPUT_PULLUP
- Piezo buzzer: pin 8, through a slide switch (on = buzzer; off = pin 8 free for other uses)
- Reset button
- FCC, CE, RoHS: Yes
- PCB colour: purple
- Packing list: 1 × Maker Uno Plus (Code: MAKER-UNO-PLUS), 1 × Micro USB cable, 1 × Pin Header Sticker
- Warranty: user manual 6 months, manufacturing defects only; product page 12 months
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Arduino UNO R3-standard female headers; R3 shield compatible; SDA, SCL and IOREF broken out as on UNO R3
- No Vin pin: Arduino shields that require Vin are not compatible, unless the shield can select an external power source instead of Vin
- Arduino IDE: select "Arduino/Genuino UNO" and the correct COM port; compatible with Arduino UNO example code and libraries
- Cytron learning guide: Windows installs the driver automatically; macOS 10.11 and later does not need the FTDI driver
- Portable power: power bank or Cytron LiPo Power Shield
- Differences from Arduino Uno: input 5V USB only (Uno: 7 - 12V recommended, 6 - 20V limit via adapter); 5V current "USB source" (Uno: 1A); 3.3V current 500mA (Uno: 50mA); USB-serial FT231X (Uno: ATmega16U2); SMD ATmega328P; USB Micro-B; no DC jack; no Vin; onboard LEDs, button and buzzer
- Differences from Maker UNO (user manual table): USB-serial FT231X (Maker UNO: CH340G); FCC, CE, RoHS Yes (Maker UNO: No)

## Use cases
- Students learning coding and microcontrollers
- Learning digital input, output and PWM (piezo buzzer and LED brightness) with just the board
- Playing tones with the onboard buzzer (Arduino example toneMelody)

## Known limitations
- Power through USB only: the DC jack (12V adapter input) and the 5V linear regulator were removed
- No Vin pin; shields that need Vin and cannot select another power source are not compatible (example: GPRS Shield V3.0)
- 5V current is limited by the USB source; 3.3V pin 500 mA max; 20 mA max per I/O pin
- Pin 8 is shared with the buzzer: slide the switch off to use pin 8 for other purposes
- Pin 2 is used by the onboard button
- Use only 1 power source at a time
- User manual (Oct 2018) and product page disagree on warranty: 6 months vs 12 months

## Positioning (kept apart from specs)
- "Simplifying Arduino for Education"
- Designed and developed specially for students to learn coding and microcontroller
- Named Maker UNO Plus "to encourage everyone to be a maker"
- Redesign of CT-UNO with ARUS and rero, "more affordable, and more beginner friendly"

## Price band
RM75.60 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-uno-plus-simplifying-arduino-for-education

## Datasheet
https://docs.google.com/document/d/1M2sYWbmmt-Auyq963b5VpsdONsfrjwCBTLAf0VuP6zk/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1M2sYWbmmt-Auyq963b5VpsdONsfrjwCBTLAf0VuP6zk/edit

# Product fact sheets

## Product name
Maker UNO X for Classrooms (Arduino Compatible)

## Aliases
MAKER-UNO-X, Maker UNO X, Maker UNO X for Classrooms, Maker UNO X for Classrooms (Arduino Compatible), Maker UNO X: Simplifying Arduino for Classrooms, Cytron Maker UNO X, Maker UNO X board, MakerUnoX

## What it is
An Arduino UNO-compatible board built on the ATmega328P, powered, programmed and connected through a USB Micro B socket. It has an LED on every digital pin, a piezo buzzer on D8, a programmable push button on D2, and an onboard perfboard and breadboard prototyping area.

## Specs and functions
- Product code: MAKER-UNO-X
- Microcontroller: ATmega328P
- Operating voltage: 5V
- Clock speed: 16MHz
- Flash memory: 32KB; SRAM: 2KB; EEPROM: 1KB
- Digital I/O pins: 20 (product page)
- PWM pins: 6 — pins 3, 5, 6, 9, 10 and 11 (marked ~); analogWrite range 0 to 255
- Analog input pins: 6 (10-bit), A0–A5 only; values 0 to 1023
- UART: 1; SPI: 1; I2C: 1
- USB to UART chip: guide driver is CH341SER and the port shows as CH340; product page links "CH34X" drivers; product page spec list writes "CH9340"; Cytron's Fritzing part artwork labels the chip "CH340C"
- USB connector: USB Micro B for power, program loading and USB communication
- Powerbank-friendly: "Enable continuous supply from most powerbanks"
- 1x programmable push button on D2 (use INPUT_PULLUP; reads LOW when pressed)
- 1x piezo buzzer on D8
- 12x LED as I/O indicators on D2 to D13
- 2x LED as UART TX/RX activity indicators on D0 & D1
- Debug mode slide switch: on = built-in LEDs and piezo buzzer enabled; off = D8 free for another I/O device
- With Debug on, LED 2 acts as an input indicator and turns off when the onboard button is pressed
- Reset button
- Onboard perfboard (donut board) prototyping area and breadboard; the breadboard is supplied loose with adhesive backing and stuck onto the board by the user (product page features say "half-size breadboard"; packing list says "mini breadboard")
- Header pins in Cytron's Fritzing part: D0/RX–D13/SCK, A0–A5 (A4/SDA, A5/SCL), separate SDA/SCL, AREF, IOREF, RESET, 3V3, 5V, GND, ICSP MISO/SCK/MOSI; no Vin connector
- Packing list: 1x Maker UNO X board, 1x mini breadboard, 1x Maker UNO pin sticker
- USB Micro B cable: optional accessory, not in the packing list
- Warranty: 12 months
- 5V and 3.3V pin output current: [NOT STATED]
- Per-I/O-pin current: [NOT STATED]
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Arduino UNO compatible; "fully compatible with Arduino UNO R3 sample code and libraries" (product page)
- Arduino IDE: select board "Arduino UNO" (product page)
- Guide v1.5 (Feb 2023) is updated to Arduino IDE 2.X; guide v1.4 is based on Arduino IDE 1.8.X
- Driver: CH34X/CH341 — Windows V3.5 (Mar 2019), Mac V1.5, Linux V1.5 on the product page; guide links CH341SER.EXE (Windows) and CH341SER_MAC.ZIP (Mac)
- Windows 7: not compatible with the USB to Serial driver; use a more recent version of Windows
- Fritzing part available from Cytron's GitHub (CytronTechnologies/MAKER-UNO-X)
- Companion book: Arduino Learning Guide for Beginners with Maker UNO X (BOK-MUNOX)
- Differences vs Maker UNO: adds the onboard perfboard and breadboard area; one Debug switch enables both the built-in LEDs and the buzzer (Maker UNO has a buzzer-only slide switch)
- Differences vs genuine Arduino UNO R3: no source lists them; sources state USB Micro B, a CH340-family USB-serial chip, no Vin connector in the Fritzing part, and onboard LEDs, buzzer, button and prototyping area
- UNO R3 shield compatibility: [NOT STATED]
- MicroPython / CircuitPython / block coding: [NOT STATED]

## Use cases
- Teaching Arduino in classrooms; students "code right away"
- The board lights up and plays a melody with a button press, no soldering
- Building circuits on the onboard breadboard and perfboard
- Portable projects powered from a powerbank
- Learning Arduino with the Arduino Learning Guide for Beginners with Maker UNO X

## Known limitations
- USB-serial driver not compatible with Windows 7
- Built-in LEDs and buzzer work only with Debug mode switched on
- D8 is shared with the buzzer; switch Debug off to use D8 for another I/O device
- D2 is used by the onboard button and cannot be connected to other external components while in use
- PWM only on pins 3, 5, 6, 9, 10, 11; analog input only on A0–A5
- Power input is USB Micro B; no other power input is named and the Fritzing part has no Vin connector
- 5V/3.3V pin current limits and protection features: [NOT STATED]
- USB cable not included

## Positioning (kept apart from specs)
- Designed for educators and classrooms
- "the culmination of years of teaching Arduino & STEM by our education partners - Chumbaka, ARUS, and rero EDUteam"
- Predecessor Maker UNO was 1825% funded on Kickstarter (17 Apr 2018)
- "Powerbank-friendly to enable the portability of the projects"

## Price band
RM50.40 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-x-simplifying-arduino-for-classrooms

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
Maker Uno RP2040

## Aliases
MAKER-UNO-RP2040, Cytron Maker Uno RP2040, MakerUnoRP2040, Uno RP2040

## What it is
A development board in the Arduino UNO form factor built around the Raspberry Pi RP2040 (dual-core ARM Cortex-M0+). It uses 3.3 V logic and has onboard Grove ports, servo ports, LEDs, a buzzer and a LiPo charger.

## Specs and functions
- Product code: MAKER-UNO-RP2040
- Datasheet: Rev 1.0, February 2024; its spec table is titled "Absolute Maximum Ratings"
- MCU: Raspberry Pi RP2040, dual-core ARM Cortex-M0+, up to 133 MHz, 264 KB SRAM
- Flash: 2 MB (Winbond W25Q16JVUXIQ per schematic; not stated in the datasheet)
- USB Type-C: for both powering and programming the board from a PC
- Power input voltage (USB or LiPo/Li-Ion): 3.6 – 6 V
- Nominal sources: LiPo / Li-Ion 3.7V (single cell only) or USB-C 5V
- Battery: 2-pin JST-PH connector for a single-cell LiPo / Li-Ion battery, rechargeable via USB, protected from overcharge and over-discharge; charging LED on while charging, off when full
- On/Off slide switch; power LEDs for 3.3V and 5V
- Total +3V3 output current: 500 mA max; total +5V output current: 600 mA max
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.62 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃
- USB VID & PID (CircuitPython & Arduino Core): VID 0x2E8A, PID 0x1071
- Reset button; Boot button (hold while resetting to enter bootloader mode)
- User programmable button: GP2
- Piezo buzzer: GP8, with buzzer mute switch on the bottom layer
- RGB LEDs: 2x WS2812B on GP25
- GPIO status LEDs: 16 (GP0–GP13, GP20, GP21), on when the GPIO is high; can be disabled by cutting a solder jumper (closed by default)
- Servo ports: 4 x RC servo, signal on GP14, GP15, GP16, GP17
- Vservo: USB only → VUSB - 0.4 V; LiPo/Li-Ion only → VBAT; USB and LiPo/Li-Ion → VUSB - 0.4 V
- Grove ports: 6 (4-pin, 2.0 mm pitch), 3.3V power pin
- Grove 1: GP0, GP1 (PWM0, SPI0, I2C0, UART0)
- Grove 2: GP4, GP5 (PWM2, SPI0, I2C0, UART1)
- Grove 3: GP6, GP26 (GP26 = ADC0)
- Grove 4: GP7, GP27 (GP27 = ADC1)
- Grove 5: GP28, GP29 (ADC2, ADC3; I2C0; UART0)
- Grove 6: GP20, GP21 (I2C0 SDA0/SCL0; UART1)
- Maker Port: JST-SH 4-pin, GP20 / GP21, shared with Grove 6
- SPI header (2x3 male): MISO GP12, SCK GP10, MOSI GP11, 5V, RESET, GND
- Analog inputs: A0–A3 = GP26–GP29 (ADC0–ADC3)
- Peripherals: 2x I2C, 2x SPI, 2x UART, 16 PWM (8 slices x 2 outputs)
- Onboard ICs (schematic): MCP73831T-2ACI/OT charger, MT3608 5 V boost, AP1117E33L 3.3 V regulator, 12 MHz crystal
- Packing list: 1x Maker Uno RP2040, 1x Silicone Rubber Feet (pack of 4), 4x Grove to female header cable

## Interfaces and compatibility
- Arduino UNO form factor; use 3.3 V-compatible UNO shields only
- Digital header order (from USB end): GP21 (SCL), GP20 (SDA), NC, GND, GP10, GP12, GP11, GP13, GP9, GP8 | GP7, GP6, GP5, GP4, GP3, GP2, GP0, GP1
- Power header order: NC, IOREF, RESET, 3.3V, 5V, GND, GND, "~5V out"
- Analog header: A0 GP26, A1 GP27, A2 GP28, A3 GP29, SDA GP20, SCL GP21
- Maker Port: compatible with QWIIC / Stemma QT / Grove (with conversion cable)
- Arduino IDE 2: Earle F. Philhower "Raspberry Pi Pico/RP2040" core, Boards Manager URL https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json, board "Cytron Maker Uno RP2040"
- CircuitPython: board id cytron_maker_uno_rp2040 (circuitpython.org); Thonny variant "Cytron Technologies • Maker Uno RP2040"
- MicroPython: no custom Cytron firmware yet; Cytron points to the Pico (rp2-pico) MicroPython firmware
- Cytron example code (Arduino, CircuitPython, MicroPython) in the CytronTechnologies/Cytron-MAKER-UNO-RP2040 GitHub repo
- Accessories used in Cytron examples: TS90A micro servo, Maker Soil Sensor, ultrasonic ranging module, SSD1306 0.96" I2C OLED

## Use cases
- Programming with Arduino IDE, CircuitPython or MicroPython in the Uno form factor
- Plug-and-play Grove and Maker Port sensors and modules
- Driving up to 4 servo motors from the onboard servo ports
- Portable projects powered by a single-cell LiPo / Li-Ion battery
- Offline Dino Game Cheat with Maker Uno RP2040
- DHT11 sensor data logging
- Playing a game using a joystick

## Known limitations
- 3.3 V logic: digital input high max 3.6 V, analog input 0 – 3.3 V; not for 5 V shields or 5 V signals
- Spec values are absolute maximum ratings
- Power inputs are only USB Type-C and the LiPo/Li-Ion connector (3.6 – 6 V); no DC jack or VIN input
- The UNO VIN position is labelled "~5V out"; the AREF position is NC
- Code pin numbers are GP numbers; the D10–D13 positions carry GP10, GP12, GP11, GP13 and the D1/D0 positions carry GP0/GP1
- Only 4 analog inputs (GP26–GP29)
- Servo voltage equals the power-source voltage (VUSB - 0.4 V on USB, VBAT on battery only); servo current limit not stated
- Total +3V3 output 500 mA max; total +5V output 600 mA max
- Shared PWM channels cannot run PWM at the same time: GP0/GP16 (Servo 3), GP1/GP17 (Servo 4), GP4/GP20, GP5/GP21, GP10/GP26, GP11/GP27, GP12/GP28, GP13/GP29, GP9/GP25
- Grove 6, the Maker Port and header SDA/SCL all use GP20/GP21
- Grove 3 and Grove 4 cannot carry I2C (two SDA or two SCL pins each)
- Mute the buzzer if GP8 is used for other purposes
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Battery charge current not stated
- Switch the board on before entering bootloader mode; the COM port may need reselecting after each upload
- The datasheet does not state the flash size or the RGB LED count

## Positioning (kept apart from specs)
- Brings the Raspberry Pi RP2040 into the familiar Uno form factor while keeping its user-friendly nature
- Large flash makes CircuitPython and MicroPython possible on an Uno-style board
- Maker series features: onboard LEDs for troubleshooting, programmable buzzer and button, Grove and Maker ports for plug-and-play connections
- Follows the move from 5V to 3.3V microcontrollers

## Price band
USD 14.90 (Cytron tutorial page hardware list)

## Product page
https://my.cytron.io/p-maker-uno-rp2040

## Datasheet
https://docs.google.com/document/d/16RTRPaV0Xaqg3xKwM89iMkXrDB8T_pBjCKYHOadv_Z4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/16RTRPaV0Xaqg3xKwM89iMkXrDB8T_pBjCKYHOadv_Z4/edit

# Product fact sheets

## Product name
Maker Nano for Projects (Arduino Compatible)

## Aliases
MAKER-NANO, Maker Nano, Cytron Maker Nano, Maker Nano: Simplifying Arduino for Projects, Maker Nano for Projects

## What it is
An Arduino Nano-form-factor board whose pin header is compatible with the original Arduino Nano. It adds LEDs on D2–D13, a piezo buzzer with a mute switch, a user button on D2 and a 7.0–30.0 VDC Vin input.

## Specs and functions
- Product code: MAKER-NANO
- Datasheet: Rev 1.0, June 2020; spec table titled "Absolute Maximum Ratings"
- Power input voltage (Vin): 7.0 – 30.0 VDC
- Digital input voltage: low level 0 – 0.5 V; high level 1.7 – 5.0 V
- Analog input voltage: 0 – 5.0 V
- DC +5V maximum current (including onboard usage): 100 mA
- DC +3V3 maximum current (including onboard usage): 50 mA
- Micro USB port: upload Arduino program from PC; debugging (Serial Monitor)
- Digital IO LEDs on D2 – D13: turn on when the IO state is high
- Digital IO LEDs enable jumper (bottom): cut the trace to disable the digital IO LEDs, to save power or reduce distraction
- Power LEDs for 3V3 and 5V: turn on when powered up
- Serial port LEDs: TX on when data is transmitted from Maker Nano; RX on when data is received by Maker Nano
- Programmable piezo buzzer (bottom): can play tone or melody
- Mute switch: mutes the piezo buzzer if pin D8 is used for other purposes
- User programmable button: connected to pin D2 internally, accessible from the user program
- Reset button
- Microcontroller: [NOT STATED]
- USB-serial chip and driver: [NOT STATED]
- Dimensions: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Pin header: "Compatible with original Arduino Nano"
- Arduino: program uploaded from PC through the Micro USB port
- Arduino IDE board to select: [NOT STATED]
- Differences from the genuine Arduino Nano: [NOT STATED] (the datasheet's comparison table is an image); stated additions are the D2 – D13 IO LEDs, buzzer with mute switch, user button on D2, power LEDs and IO-LED enable jumper
- Box contents: [NOT STATED]

## Use cases
- Building projects with an Arduino Nano-compatible board ("Simplifying Arduino for Projects")
- Playing a tone or melody on the onboard piezo buzzer
- Reading the onboard user button on D2 from the user program

## Known limitations
- DC +5V output is limited to 100 mA and DC +3V3 to 50 mA, both including onboard usage
- Vin minimum is 7.0 V; maximum 30.0 V
- Digital and analog inputs must not exceed 5.0 V
- D8 is shared with the piezo buzzer: use the mute switch when D8 is used for other purposes
- D2 is used by the onboard user button
- The digital IO LEDs on D2 – D13 light when a pin is high; they can only be disabled by cutting the enable-jumper trace

## Positioning (kept apart from specs)
- "Simplifying Arduino for Projects"

## Price band
RM37.38 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-nano-simplifying-arduino-for-projects

## Datasheet
https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lUUJSzbsvzH_Ss6vDcHpGfVY7p_txuW5BZ1QOmHgcBA/view

# Product fact sheets

## Product name
Maker Nano RP2040

## Aliases
MAKER-NANO-RP2040, Cytron Maker Nano RP2040, MakerNanoRP2040

## What it is
An Arduino Nano form-factor microcontroller board built on the Raspberry Pi RP2040. It has GPIO status LEDs, two RGB LEDs, a piezo buzzer, a user button and two Maker Ports.

## Specs and functions
- Product code: MAKER-NANO-RP2040
- MCU: Raspberry Pi RP2040
- Datasheet: Rev 1.1, July 2024; its spec table is titled "Absolute Maximum Ratings"
- Flash: [NOT STATED] in the Cytron datasheet
- USB: Micro USB port, for program upload and power
- Power input voltage (Vin): 7.0 – 30.0 VDC
- DC +5V max current (including onboard usage): 110 mA powered from Vin, 500 mA powered from USB
- DC +3V3 max current (including onboard usage): 110 mA powered from Vin, 500 mA powered from USB
- RGB LEDs: 2 x WS2812B, user programmable, on GP11
- User programmable button: GP20
- Boot button (hold while resetting to enter bootloader mode) and Reset button
- Piezo buzzer: GP22, able to play tone or melody, with mute switch
- Digital IO LEDs: on when the IO state is high (14 LEDs, 85 µA each); the datasheet table lists GP0 – GP9, GP16 – GP18
- Digital IO LEDs enable jumper: cut the trace to disable the LEDs (~1.19 mA saved); solder it to re-enable
- 5V and 3.3V power LEDs
- Maker Port 0: JST-SH 4-way, GPIO, I2C, UART
- Maker Port 1: JST-SH 4-way, GPIO, I2C, Analog In
- Analog inputs: A0 – A3 = GP26 – GP29
- Header (silkscreen GP numbers): D2 – D9 = GP2 – GP9, D10 = GP17, D11 = GP19, D12 = GP16, D13 = GP18, A4 – A7 = GP12 – GP15; AREF position is NC; GP0 and GP1 sit at the Nano TX/RX positions
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- USB VID 0x2E8A, PID 0x100F (CircuitPython & Arduino Core)

## Interfaces and compatibility
- Pin header: "Compatible with original Arduino Nano"
- Maker Ports: compatible with Qwiic, STEMMA QT and Grove (via conversion cable)
- CircuitPython: Cytron firmware at circuitpython.org board "cytron_maker_nano_rp2040", with NeoPixel and simpleio built in; pin names LED (GP2), RGB/NEOPIXEL (GP11), BUTTON (GP20), BUZZER (GP22), A0 – A3
- MicroPython: loaded using the Raspberry Pi guide (no Cytron-specific firmware)
- Arduino: Arduino IDE upload per the datasheet; the arduino-pico (Earle Philhower) core has the board "Cytron Maker Nano RP2040"
- Cytron GitHub: CircuitPython and MicroPython examples; a new board's code.py is the demo program

## Use cases
- Projects that need an Arduino Nano form factor with an RP2040 MCU
- Connecting Qwiic, STEMMA QT or Grove modules through the Maker Ports

## Known limitations
- 3.3 V logic: digital input high level max 3.6 V, so 5 V signals can't drive the pins directly
- Only A0 – A3 (GP26 – GP29) are analog inputs; A4 – A7 (GP12 – GP15) have no ADC; AREF position is NC
- Code uses GP numbers, not Arduino D numbers
- Default I2C/UART in CircuitPython is GP0/GP1 and arduino-pico Wire is on GP0/GP1, not A4/A5
- board.LED / PIN_LED is GP2, a header pin; there is no separate user LED
- +5V and +3V3 are limited to 110 mA each when powered from Vin
- Spec values are absolute maximum ratings
- The datasheet does not state the Maker Port pin assignments
- The datasheet's Digital IO LED list (GP0 – GP9, GP16 – GP18) does not match its own count of 14 LEDs
- The datasheet's mute-switch text refers to "pin D8", while the buzzer is on GP22
- The setup-circuitpython.md guide in Cytron's Maker Nano GitHub repo is copied from Maker Pi RP2040 and links that board's firmware
- No protection features are stated in the datasheet

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Projects with Raspberry Pi RP2040"
- GitHub README: "a small but powerful MCU for your project"

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-maker-nano-rp2040

## Datasheet
https://docs.google.com/document/d/15IMxlESQE43sP7brZpqlfHVTAdX1N_XenzpvfP8cT_8/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/15IMxlESQE43sP7brZpqlfHVTAdX1N_XenzpvfP8cT_8/edit

# Product fact sheets

## Product name
Cytron UNO - Arduino UNO Compatible

## Aliases
CT-UNO, CT UNO, Cytron UNO, CT UNO (Arduino Uno Compatible)

## What it is
A Cytron version of the Arduino UNO built on an SMD ATmega328 with the Optiboot (UNO) bootloader, programmed over USB Micro-B through an FTDI FT231X USB-serial chip. It can be powered from a 2.1 mm DC adapter socket or from USB.

## Specs and functions
- Product code: CT-UNO
- Microcontroller: SMD ATmega328 with Optiboot (UNO) bootloader (manual spec section names it ATmega328p)
- Clock speed: 16MHz
- Flash memory: 32k
- Digital I/O pins: 14 (6 PWM outputs)
- Analog inputs: 6 (can be digital I/O too)
- Peripherals: UART, SPI, external interrupts, I2C
- I/O levels: 0-5V digital outputs with 3.3V compatible inputs
- USB-to-serial: FTDI FT231X; needs the FTDI VCP driver
- USB connector: USB Micro-B socket (program upload and power)
- DC input: Adapter Socket (2.1mm)
- Input voltage via adapter (recommended): 7 V min, 15 V max
- Input voltage via adapter (limits): 6 V min, 20 V max
- If both adapter and USB are connected, the board automatically uses the adapter
- 5V regulator: 1 A max (with Vin at 12V)
- 3.3V regulator: 500 mA max
- Per-pin current: [NOT STATED] (manual: refer to the ATmega328P specification)
- LEDs: RX LED, TX LED, Power LED (green), programmable LED on pin 13 (active HIGH, orange); TX, RX, Power and pin 13 LEDs moved to the board edge
- Reset button
- ISP 6-pin header (SPI and power); for uploading the Arduino Uno bootloader with an AVR programmer (e.g. AVR USBasp)
- Extra pads for stacking on strip/donut board (0.1" pitch)
- PCB colour: white
- Packing list: 1 x CT-UNO board; USB Micro B cable and 12V 2A AC to DC Adapter are optional add-ons (cable sold separately)
- Warranty: 12 months, manufacturing defects only; misuse and freight both ways not covered
- Dimensions: [NOT STATED]
- User's Manual: V1.0, Nov 2014

## Interfaces and compatibility
- Arduino R3 standard headers; R3 shield compatible; SDA, SCL and IOREF broken out as on UNO R3
- Arduino IDE: Tools > Board > "Arduino Uno", then select the CT-UNO serial port
- Driver: FTDI VCP driver from http://www.ftdichip.com/Drivers/VCP.htm
- Manual examples: LCD Keypad shield; wireless remote omni robot with SHIELD-XBEE and FD04A-R2
- Differences from Arduino UNO R3: FTDI FT231X USB-serial, USB Micro-B socket, SMD ATmega328, 7–15 V recommended input, upgraded on-board regulator (5V 1A), LEDs moved to the edge, extra pads, white PCB
- MicroPython / CircuitPython: [NOT STATED]

## Use cases
- Stacking Arduino UNO shields (e.g. LCD Keypad shield)
- Mobile robots with shields (e.g. wireless remote omni robot with SHIELD-XBEE and FD04A-R2)
- Stacking onto strip/donut board for custom circuits

## Known limitations
- 5V regulator 1 A rating is given only with Vin at 12V
- 3.3V regulator limited to 500 mA
- Adapter input 7–15 V recommended; 6–20 V absolute limits
- Uses an FTDI FT231X: Windows driver install may fail until the FTDI VCP driver is installed
- USB cable not included
- Only one user LED (pin 13); no user button or buzzer
- Per-pin current, reverse-polarity and over-current protection: [NOT STATED]

## Positioning (kept apart from specs)
- User manual: combines "the simplicity of the UNO's Optiboot bootloader (which load program faster), the stability of the FTDI and the R3 shield compatibility of the latest Arduino UNO R3"
- User manual: "White PCB!"
- cytron.com.my product page recommends Maker UNO for beginners and students

## Price band
RM61.74 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-uno-arduino-uno-compatible

## Datasheet
https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view

# Product fact sheets

## Product name
Cytron UNO Special Edition - Arduino Compatible

## Aliases
CT-UNO-SE, Cytron UNO Special Edition, Cytron UNO SE, Cytron UNO Special Edition - Arduino Compatible

## What it is
An Arduino-compatible board sold by Cytron as the Cytron UNO Special Edition (CT-UNO-SE). Cytron documents it with the CT-UNO (Cytron UNO) User's Manual and schematic; how it differs from the standard Cytron UNO is not stated.

## Specs and functions
- Product code: CT-UNO-SE
- Warranty: 12 months (product page)
- Documentation: the product page links the CT-UNO User's Manual (V1.0, Nov 2014) and CT-UNO Schematic; the manual does not mention the Special Edition
- Per the linked CT-UNO manual (not confirmed to apply unchanged to CT-UNO-SE):
- Microcontroller: SMD ATmega328 (ATmega328p in spec section) with Optiboot (UNO) bootloader; 32k Flash; 16MHz
- USB-to-serial: FTDI FT231X; USB Micro-B socket
- DC input: Adapter Socket (2.1mm); 7–15 V recommended, 6–20 V limits
- 5V regulator: 1 A max (with Vin at 12V); 3.3V regulator: 500 mA max
- I/O: 14 digital I/O (6 PWM), 6 analog inputs; 0-5V digital outputs with 3.3V compatible inputs
- LEDs: RX, TX, Power (green), programmable LED on pin 13 (active HIGH); reset button; ISP 6-pin header; extra pads; white PCB
- Special Edition differences from Cytron UNO: [NOT STATED]
- Packing list: [NOT STATED]
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Per the linked CT-UNO manual: Arduino R3 standard headers, R3 shield compatible; Arduino IDE board "Arduino Uno"; FTDI VCP driver
- SE-specific interfaces: [NOT STATED]
- MicroPython / CircuitPython: [NOT STATED]

## Use cases
[NOT STATED]

## Known limitations
- No source states what makes the Special Edition different from the standard Cytron UNO
- Technical specs come only from the CT-UNO User's Manual, which does not name the Special Edition
- Per the linked CT-UNO manual: 5V regulator 1 A rating given only with Vin at 12V; 3.3V regulator limited to 500 mA; adapter input 7–15 V recommended, 6–20 V limits; FTDI VCP driver needed

## Positioning (kept apart from specs)
[NOT STATED]

## Price band
RM63.00 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-uno-special-arduino-compatible

## Datasheet
https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lAeGP_92g0VC_xuyL_ibK_EhHU-cxrf3AOS--tf-hvw/view

# Product fact sheets

## Product name
Robo Uno Shield

## Aliases
SHIELD-ROBO-UNO, Robo Uno Shield, Robo Uno Shield for Arduino, Robo Uno, Robo Uno Shield: The All-in-One Robotics Shield

## What it is
An Arduino Uno-form-factor robotics shield with a 2-channel DC motor driver, 4 servo ports, 6 Grove ports, a Maker Port and a built-in single-cell LiPo/Li-ion charger. It is powered from 3.6–6 V through its own VIN terminal, LiPo port or micro-USB.

## Specs and functions
- Product code: SHIELD-ROBO-UNO
- Datasheet: Rev 1.0, February 2025 (spec table titled "Absolute Maximum Ratings")
- Power input voltage (USB, LiPo or VIN): 3.6–6 V
- VIN terminal block: 3.6–6 V, reverse polarity protection
- LiPo connector: JST PH2.0, single-cell LiPo / Li-ion; rechargeable via the shield's micro-USB port; protected from overcharge and over-discharge
- Micro-USB port: powers the shield and charges the battery only; no data or code upload
- Digital input voltage: low 0–0.5 V, high 2.7–5 V
- Digital output voltage: low 0–0.5 V, high 4.2–5 V
- Analog input voltage: 0–5 V
- Motor and servo voltage: equal to the power input voltage (VUSB − 0.4 V when powered from USB; VLiPo or VIN when only one of those is connected)
- DC motor driver: dual-channel H-bridge, 2 DC motors
- Maximum DC motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds)
- DC motor driver PWM frequency: 20 kHz max
- Motor driver truth table: Low/Low = Brake; High/Low = Forward; Low/High = Backward; High/High = Coast (outputs Hi-Z)
- Motor test buttons (motor runs at full speed) and motor status LEDs: MxA forward, MxB backward
- Servo ports: 4 x RC servo, signal on D9, D10, D11, D12; V+ equal to the power source voltage
- Total 5V output current (Grove ports): 400 mA max
- Grove ports: 6; Maker Port: 1 (shared with Grove 4)
- RGB LEDs on D13 (user-programmable)
- Piezo buzzer on D8 (bottom side) with mute switch
- Programmable buttons on D2 and D3
- Status LEDs for the Grove-port pins (on when the pin is high); launch material: "2x RGB LEDs / 10x GPIO LEDs"
- On/Off switch, power LED, reset button (resets the shield and the microcontroller)
- Operating temperature: −20 to 85 ℃
- Motor driver IC: [NOT STATED]
- Dimensions: [NOT STATED]
- Charging current: [NOT STATED]

## Interfaces and compatibility
- DC motor pins: datasheet Table 1 lists M1A D4, M1B D5, M2A D6, M2B D7; Cytron's example code uses Motor 1 PWM = D5, DIR = D4 and Motor 2 PWM = D6, DIR = D7 (`CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);`)
- Grove 1: A0, A1; Grove 2: A2, A3; Grove 3: A1, A3 (as printed in the datasheet); Grove 4: A4 (SDA), A5 (SCL); Grove 5: D0 (RX), D1 (TX); Grove 6: D2, D3
- Maker Port: A4, A5; compatible with QWIIC / Stemma QT / Grove (with conversion cable)
- Datasheet and GitHub name Arduino Uno and Maker UNO
- Launch compatible-board list: Maker Uno / Maker Uno X / Maker Uno Plus; Maker Uno RP2040; Cytron Uno; Uno Compatible (CH340); Official Arduino Uno Rev3; Official Arduino Uno R4 Minima; Official Arduino Mega 2560 Rev3; Wifi Uno ESP8266; Official Arduino Zero, Leonardo and GIGA R1 listed as "Not tested"
- Libraries in Cytron examples: Cytron Motor Drivers Library (CytronMotorDriver.h), Servo, Adafruit_NeoPixel, U8g2
- Packing list: 1x Robo Uno Shield board, 1x Small Philips Screwdriver, 4x Grove to Female Header Cable

## Use cases
- Building robots using Arduino Uno, Arduino Mega, Maker Uno, or compatible boards
- Mobile robot projects for the RBT syllabus (light, sound and movement)
- Teaching robotics with simplified wiring and power options (educators and training centres)
- Adding sensors and modules through Grove ports and the Maker Port without messy wiring
- Troubleshooting wiring vs code with status LEDs and motor test buttons

## Known limitations
- Power input 3.6–6 V only (absolute maximum); only single-cell batteries are supported
- Cannot be powered through the VIN pin of the microcontroller (e.g. Arduino Uno, Maker UNO)
- The shield's micro-USB port cannot be used for data communication or uploading code
- Motor and servo voltage equals the power input voltage; no separate motor supply
- Motor current 1 A continuous per channel; 1.5 A peak only for < 5 seconds
- Total 5V output on the Grove ports limited to 400 mA
- Datasheet advises one power source at a time (LiPo and VIN together not recommended)
- If the board will not turn on with a battery connected, the battery must be charged to activate the protection circuit
- Grove 4 and the Maker Port share A4/A5; buttons D2/D3 share pins with Grove 6
- Motor test buttons run the motor at full speed; motor direction depends on wiring
- Protection stated in the datasheet is limited to VIN reverse polarity and battery overcharge / over-discharge

## Positioning (kept apart from specs)
- "The All-in-One Robotics Shield"
- Launch pitch: "Designed for Beginners and Intermediate Learners"
- "Simply add your preferred microcontroller, motor, robot base, and sensors"
- Part of Cytron's Robo series (alongside Robo Pico)

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1DWNFjaC8XuEBnRx13xmJkOJgdrZvjDGWSx3C6OJeUm4/edit

# Product fact sheets

## Product name
Cytron PS2 Shield

## Aliases
SHIELD-PS2, Shield-PS2, Cytron PS2 Shield, PS2 Shield, PS2 Shield for Arduino

## What it is
An Arduino-form-factor shield that converts a SONY PS2 (DualShock) controller, wired or wireless, into a simple UART protocol so the Arduino can read button and joystick states and drive the controller's vibration motors. It is powered from the Arduino main board (5 V) and has stackable headers with jumper-selectable UART pins and baud rate.

## Specs and functions
- Product code: SHIELD-PS2
- Primary source: Shield-PS2 User's Manual V1.0, September 2013 (no datasheet exists)
- Input voltage (logic operation voltage): 4.5 V min, 5.5 V max
- Current consumption: 100 mA min, 150 mA typical, 500 mA max
- VIOH (logic input high level): 3.5 V min, 5.0 V typical, 5.5 V max
- VIOL (logic input low level): 0 V min, 0 V typical, 1.0 V max
- Power source: powered from the Arduino main board; "5V powered, low current consumption"
- Logic level: 5 V
- UART baud rate (jumper-selectable): 4800, 9600, 57600, 115200; the shield must be reset after changing the jumper
- UART RX pin (jumper-selectable): D0, D2, D8 or D10; default D2
- UART TX pin (jumper-selectable): D1, D3, D9 or D11; default D3
- Shield reset line: Arduino A1 (pull low to reset the shield)
- Controllers: SONY PS2 controller, wired or wireless; the controller automatically operates in analog mode
- Vibration motors: controllable (motor 1 on/off; motor 2 speed 0–255)
- Status LED (orange): blinking = no controller detected; steady low brightness = controller detected; steady high brightness = digital button pressed
- Power LED (green)
- Buttons: Arduino main board reset button (Arduino needs around 30 ms to be ready after reset); PS2 RST button (resets the shield only)
- Headers: stackable analog, power and digital I/O headers (JP4, JP7)
- Protocol: Arduino sends one command byte (decimal); 0–15 = digital buttons (reply 0 = pressed, 1 = not pressed); 16–19 = joystick X/Y axes (0–255, 128 neutral); 20–27 = joystick up/down/left/right values (0–100); 28 = connection status (1 = detected); 29 + value = motor 1 on/off; 30 + value = motor 2 speed 0–255; 31 = all buttons and joysticks in 6 bytes
- Packing list: 1 x Shield-PS2, 3 x mini jumper
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Onboard interface IC: [NOT STATED]

## Interfaces and compatibility
- Compatible boards: Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo and possibly other pin-compatible main boards; library README uses CT UNO
- Hardware serial option: D0/D1 (unplug the PS2 controller before uploading code); software serial options: D2/D3 (default), D8/D9, D10/D11
- SoftwareSerial RX restriction from the manual: Mega RX only on 10, 11, 12, 13, 50–53, 62–69; Leonardo RX only on 8, 9, 10, 11, 14, 15, 16
- PS2 connector socket for a wired controller or wireless receiver; no modification needed
- Arduino library: Cytron_PS2Shield — https://github.com/CytronTechnologies/Cytron_PS2Shield (ZIP install; examples ReadButton and ReadJoystick)
- Library API: Cytron_PS2Shield(rxpin, txpin) or Cytron_PS2Shield() for hardware serial; begin(baudrate); readButton(key); readAllButton() with ps_data[6]; vibrate(motor, value); reset(1/0); SERIAL_ERR flag
- Library constants: PS2_SELECT … PS2_SQUARE (digital), PS2_JOYSTICK_LEFT_X_AXIS … PS2_JOYSTICK_RIGHT_RIGHT (analog), PS2_CONNECTION_STATUS, PS2_MOTOR_1, PS2_MOTOR_2, PS2_BUTTON_JOYSTICK
- On Leonardo the library maps Serial to Serial1 for the hardware-serial constructor
- Controller sold separately: Cytron wired (PS-GP-1) or wireless (PS-GP-2) PS2 controller

## Use cases
- Reading joystick and button states of a PS2 controller as easily as reading UART data
- Remote-controlling Arduino robots with a wired or wireless PS2 controller
- Controlling the PS2 controller's vibration motors from the Arduino

## Known limitations
- Powered only from the Arduino's 5 V (4.5–5.5 V); up to 500 mA consumption
- Baud rate must match the jumper and the shield must be reset after changing the baud jumper
- Using hardware serial (D0/D1): programming may fail unless the PS2 controller is unplugged first
- On Mega and Leonardo only certain pins support SoftwareSerial RX (see manual table)
- A1 is used as the shield reset line
- Joystick analog values are not linear and have a large dead zone near the centre
- Compatibility is not guaranteed for PS2 controllers from other sources; the controller is not included
- Logic input high level minimum 3.5 V (3.3 V hosts not stated)

## Positioning (kept apart from specs)
- "a compact yet reliable PS2 Controller Converter"
- "Reading Joy-stick and button's state of PS2 controller will be as easy as reading UART data"

## Price band
- RM65.10 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-ps2-shield

## Datasheet
https://docs.google.com/document/d/1cifT1XqOquLffnu5J961wpKakSO8_LpV35v4sKSaIQU/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1cifT1XqOquLffnu5J961wpKakSO8_LpV35v4sKSaIQU/edit

# Product fact sheets

## Product name
Cytron ESP8266 WiFi Shield

## Aliases
SHIELD-ESP-WIFI, Cytron ESP8266 WiFi Shield, ESP8266 WiFi Shield, ESPWiFi Shield, ESP WiFi Shield, ESPWiFi Shield Rev2.0

## What it is
An Arduino shield carrying an Espressif ESP-WROOM-02 (ESP8266) Wi-Fi module preloaded with AT-command firmware, which the Arduino talks to over a jumper-selected hardware or software UART. It also has a USB jumper position for PC-to-ESP communication, a microSD card slot on D4, a 3.3 V ESP GPIO breakout, a prototyping area, a Flash/Run switch and separate Arduino and ESP reset buttons.

## Specs and functions
- Product code: SHIELD-ESP-WIFI
- Current hardware revision: Rev2.0
- Primary source: ESPWiFi Shield Rev2.0 User's Manual V2.1, August 2021 (no datasheet exists); Rev1.0 User's Manual V1.0, Nov 2015
- Wi-Fi module: ESP-WROOM-02 (Rev2.0); Rev1.0 manual says only "ESP8266 module"
- Module (vendor datasheet v2.0, Nov 2016): IEEE 802.11 b/g/n, 2.4–2.5 GHz, 2 MB SPI flash, 3.0–3.6 V operating voltage, 80 mA average operating current, −40 to 85 °C
- Preloaded firmware: AT firmware; current Cytron binary Cytron_ESP-12F_WROOM-02_AT_Firmware_V2.2.0.bin (ESP-AT v2.2.0 with UART0 on GPIO1/GPIO3)
- Default UART as shipped: 9600 baud, 8 data bits, 1 stop bit, no parity (manual prints "9600 kbps")
- After a fresh firmware flash the module runs at 115200; the manual sets 9600 with AT+UART_DEF=9600,8,1,0,0
- Arduino RX pin (jumper): D0, D2, D8, D10, D12 or USB
- Arduino TX pin (jumper): D1, D3, D9, D11, D13 or USB
- microSD card chip select: D4 (no other connection allowed on this pin)
- ESP 3V3 GPIO breakout: 9 digital I/O pins and 1 analog input pin; all 3.3 V tolerant only
- Prototyping area
- LEDs: Power LED (on when 5 V is supplied to the module), RX LED, TX LED
- Buttons/switches: Arduino Reset button, ESP Reset button, Flash/Run slide switch (Flash = wait for firmware upload; Run = run installed firmware)
- Headers: stackable digital I/O and analog input headers
- Firmware flashing: Espressif Flash Download Tool, 115200 baud, binary at address 0x0; settings CrystalFreq 26M, SPI SPEED 40MHz, SPI MODE DIO, FLASH SIZE 32Mbit, DoNotChgBin selected
- Packing list: 1 x ESPWiFi Shield, 2 x mini jumper
- Warranty: 6 months (user manuals V1.0 and V2.1) / 12 months (product page, read 2026-10-16)
- Dimensions: [NOT STATED]
- 3.3 V regulator and output current: [NOT STATED]
- Shield power input range: [NOT STATED] (powered from the Arduino's 5 V)
- Rev1.0 vs Rev2.0 differences stated: Rev2.0 manual names the ESP-WROOM-02 module and adds a Firmware Installation chapter; pins, jumpers, LEDs, buttons and defaults are identical in both manuals

## Interfaces and compatibility
- Compatible boards: Arduino Uno, Arduino Duemilanove, Arduino Mega2560, Arduino Leonardo and possibly other pin-compatible main boards; CT-UNO and CIKU also named
- Recommended UART pairs (RX/TX): USB/USB (Uno/Mega/Leonardo, PC-to-ESP only); D0/D1 (Uno/Mega/Leonardo, hardware serial); D2/D3 (Arduino Uno only; recommended default); D8/D9 (Uno/Leonardo); D10/D11 (Uno/Mega/Leonardo); D12/D13 (Uno/Mega)
- D10/D11 and D12/D13 on Uno only if no SPI is used; the microSD card cannot be used in that case
- USB position: hold the Arduino in reset (RST to GND) or upload an empty sketch first
- Arduino library: Cytron ESPWiFi Shield v3.0.2 — https://github.com/CytronTechnologies/CytronWiFiShield (Library Manager "Cytron ESPWiFi Shield" or ZIP)
- Library headers: CytronWiFiShield.h, CytronWiFiClient.h, CytronWiFiServer.h, SoftwareSerial.h; global object `wifi`
- Library API: wifi.begin(rx=2, tx=3) or begin(HardwareSerial&); test(); reset(); firmwareVersion(); echo(); setBaud(); getMode(); setMode(WIFI_STA/WIFI_AP/WIFI_BOTH); connectAP(ssid, pwd); disconnectAP(); softAP(); SSID(); RSSI(); localIP(); config(ip, gateway, subnet); softAPIP(); status(); updateStatus(); tcpConnect(); sslConnect(); tcpSend(); close(); setMux(); configureTCPServer(); setServerTimeout()
- ESP8266Client: connect(host/ip, port), secure_connect(), available(), read(), write(), stop(), connected()
- ESP8266Server(port=80): begin(), available(), hasClient(), closeClient(), arg(), args(), uri(), method()
- Library begin() auto-detects a module at 115200 and switches it to 9600
- Firmware binaries: https://github.com/CytronTechnologies/esp-at-binaries (use the ESP-12F/WROOM-02 2 MB-or-above build, not the ESP-01S 1 MB build)
- Example sketch: CytronWiFiDemo (joins an AP, HTTP GET client test, serves /, /analog and /info on port 80)

## Use cases
- Adding a low-cost Wi-Fi solution to any Arduino project
- Creating a simple Wi-Fi web server with Arduino Uno + ESPWiFi Shield
- Performing AT tests and sending AT commands to the ESP8266 from the PC
- Using the ESP8266 as an additional microcontroller with custom firmware (advanced users)
- Extra file storage with the microSD slot; small circuits on the prototyping area

## Known limitations
- D4 is reserved for the microSD chip select
- UART on D10–D13 disables SPI and the microSD card on Arduino Uno
- D2/D3 UART pair is for Arduino Uno only
- ESP GPIO breakout is 3.3 V tolerant only
- PC-to-ESP (USB jumper) use and firmware flashing require the Arduino to be held in reset or loaded with an empty sketch
- Firmware must be flashed at 115200 or below; after flashing the module defaults to 115200 and must be set back to 9600
- ESP-AT v2.x command set is not fully compatible with legacy NONOS-AT firmware
- Warranty stated as 6 months in the user manuals, 12 months on the product page
- Shield power input range, regulator current and dimensions not stated

## Positioning (kept apart from specs)
- "provides low cost WiFi solution with any Arduino projects"
- "easy and stable UART interface for users to communicate with onboard WiFi module"

## Price band
- RM52.40 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-esp8266-wifi-shield

## Datasheet
https://docs.google.com/document/d/1LFCe6MTNQh_0EBHRgc0f6n_hDLNUG8sFuM53oBJG8eE/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1LFCe6MTNQh_0EBHRgc0f6n_hDLNUG8sFuM53oBJG8eE/view

# Product fact sheets

## Product name
LiPo Power Shield

## Aliases
SHIELD-LIPO, LiPo Power Shield, Cytron LiPo Power Shield, Shield LiPo, Shield-LiPo, LiPo Shield for Arduino

## What it is
An Arduino shield that powers a stacked Arduino from a single-cell 3.7 V LiPo battery through an onboard 5 V boost converter, with an integrated 500 mA charger fed from the shield's own micro-USB port or from the Arduino's USB port. It has a power switch, charge/full/low-battery/power LEDs, under-voltage protection and a solder jumper for reading the battery voltage from the Arduino.

## Specs and functions
- Product code: SHIELD-LIPO
- Primary source: Cytron LiPo Power Shield User's Manual V1.0, January 2016 (no datasheet exists)
- Output voltage: 5 V
- Output current: "Output current: 1A" (Features list); body text: "at least 500mA current, and peak at 1A"
- Battery: 3.7 V 1300 mAh LiPo (single cell)
- Integrated charger, charging current: 500 mA
- Charging input: onboard micro-USB port (USB Micro B cable) or the USB port on the Arduino
- Low battery indicator threshold: 3.3 V
- Under-voltage protection cut-out: 2.4 V
- LEDs: Low power (battery below 3.3 V), Power (green), Full (fully charged), Charge (charging)
- Power switch: switches the battery on/off
- Main board reset button (Arduino needs around 30 ms to be ready after reset)
- VBATT solder jumper on the back of the shield: solder the pads to monitor battery voltage from the Arduino
- Stackable side headers
- ICSP header: not passed through (the battery is in the way)
- Packing list: 1 x SHIELD-LIPO
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Boost converter / charger IC: [NOT STATED]
- Arduino pins used: [NOT STATED]
- Battery connector type: [NOT STATED]

## Interfaces and compatibility
- Compatible boards: Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo and possibly other pin-compatible main boards; hardware example uses Arduino UNO / CT-UNO
- Can be stacked with shields on top, or placed on top of other shields; shields that use ICSP for data (e.g. Ethernet Shield) must be below the LiPo shield
- Charging from the Arduino's USB port requires the shield's power switch to be OFF; charging from the onboard USB port works with the switch ON or OFF
- Battery voltage monitoring: bridge the VBATT solder jumper, then read it with the Arduino and view it in the Arduino IDE Serial Monitor (example sketch in the manual)
- Battery sold separately as an option (3.7 V 1300 mAh LiPo, Lip-3.7-1300) on the product page
- No Cytron library or GitHub repository for this product

## Use cases
- Taking an Arduino anywhere with portable LiPo power
- Charging the LiPo battery from the onboard USB port or the Arduino's USB port
- Monitoring the battery voltage from the Arduino via the VBATT solder jumper

## Known limitations
- Output current at least 500 mA continuous, 1 A peak (Features line states 1 A)
- Single-cell 3.7 V LiPo only; under-voltage cut-out at 2.4 V
- ICSP header is not passed through; ICSP-dependent shields must sit below it
- Battery does not charge from the Arduino's USB port while the shield is switched ON
- Battery voltage monitoring requires soldering the VBATT jumper
- Battery not in the manual's packing list (separate item)
- Arduino pins used, dimensions and the monitoring analog pin are not stated in the manual text

## Positioning (kept apart from specs)
- "You can take your Arduino anywhere you wish with this LiPo Power Shield."

## Price band
- RM57.75 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-lipo-power-shield

## Datasheet
https://docs.google.com/document/d/1SKOewuQDMKS-EQSgeAn7w-p6xtPRtCQVZl9MHfjzGYo/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1SKOewuQDMKS-EQSgeAn7w-p6xtPRtCQVZl9MHfjzGYo/view

# Product fact sheets

## Product name
Cytron 8 Channels RC Servo Controller Shield for Arduino (SHIELD-SERVO)

## Aliases
SHIELD-SERVO, SHIELD-Servo, Shield-Servo, Cytron Servo Shield, Servo Controller Shield, 8 Channels RC Servo Controller Shield for Arduino, Cytron 8 Channel Servo Shield

## What it is
An Arduino shield that controls up to 8 RC servo motors over a UART command protocol from an Arduino-compatible board, a PC (via UC00A/UC00C USB-to-serial) or another microcontroller. It has a built-in 5 V switching regulator (4 A continuous, 5 A peak) fed from a 7–25 V servo supply input.

## Specs and functions
- Servo channels: 8, controlled independently or simultaneously (User's Manual V1.1)
- Servo supply input VM: 7 V to 25 V; absolute maximum rating 7 V min / 25 V max, VM current 5 A max (User's Manual V1.1)
- On-board 5 V switching regulator for the servos: 4 A continuous, 5 A peak, total for all servos (User's Manual V1.1); product page states "5V at 5A (peak)"
- Servo pulse range: 0.5 ms to 2.5 ms (User's Manual V1.1)
- Position resolution: 0.25 µs; position value 0–8000 (13-bit); pulse width = (0.25 µs × position) + 0.5 ms (User's Manual V1.1)
- Speed per command: 0–100; 1 = slowest, 100 = fastest, 0 = full speed (faster than 100) (User's Manual V1.1)
- Host interface: UART, TTL/CMOS 5 V logic; factory default baud rate 9600; baud rate saved in non-volatile memory (User's Manual V1.1)
- Arduino UART pins selected by DIP switch: shield TX on D0, D2, D10 or D12; shield RX on D1, D3, D11 or D13 (User's Manual V1.1)
- Alternative 6-pin UART header for UC00A/UC00C: DTR (reset via 0.1 µF), TX, RX, VSEL (5 V in, powers the controller), CTS (not connected), GND (User's Manual V1.1)
- UART command set: activate/deactivate channel (mode 110, 2 bytes), position and speed (mode 111, 4 bytes), position reporting (mode 101, 1 byte, 2-byte reply), starting position at next start-up (mode 100, 3 bytes, reply 0x04); channel 0 = all channels (User's Manual V1.1)
- Servos are deactivated at power-up until the activate command is sent (User's Manual V1.1)
- Servo signal outputs S1–S8: TTL/CMOS 5 V logic; inputs 5 V logic-level compatible (User's Manual V1.1)
- LEDs: servo power indicator (MPWR) and small green logic power indicator (PWR) (User's Manual V1.1)
- Buttons: reset (shield controller only, not Arduino) and test (runs every connected servo in a predetermined movement) (User's Manual V1.1)
- Solder jumper K: share the Arduino 5 V for the servos or supply the Arduino from a single source (User's Manual V1.1)
- Wrong-polarity protection on the VM input (User's Manual V1.1)
- Dimension: 7.4 cm × 6.6 cm (User's Manual V1.1)
- Warranty: 6 months (User's Manual V1.1); 12 months (product page, read 2026-10-16)
- Arduino library "Cytron Servo Shield" version 2.0.0 (Arduino Library Manager / GitHub); functions init, setChannel, position, angle, getPosition, getAngle, setStartPosition, setStartAngle, registerErrorCallback (GitHub)
- Library angle() maps 0–180° to positions 156–7260; getPosition() timeout 100 ms; setStartPosition() waits up to 5 s for 0x04 (GitHub)
- PC GUI "Shield-Servo GUI" written in VB.net (Visual Studio Community 2015), source on the repository's visual-basic branch (User's Manual V1.1, GitHub)

## Interfaces and compatibility
- Arduino-compatible hosts named: Arduino/Genuino UNO, Mega, CT-UNO, CT-ARM (User's Manual V1.1)
- 10/8/6-way Arduino headers to the host (User's Manual V1.1)
- PC control through UC00A or UC00C USB-to-serial converter plugged into the 6-pin header; more than one UC00A/UC00C may be connected to control more than one shield (User's Manual V1.1)
- Any other microcontroller with 5 V TTL UART via the 6-pin header; direct connection to SKXBee mentioned (User's Manual V1.1)
- Logic power comes from the Arduino header or from UC00A/UC00C VSEL, not from VM (User's Manual V1.1)
- Servo power from VM/GND through the regulator, or from the Arduino 5 V by soldering jumper K (User's Manual V1.1)
- Software: Arduino library (hardware serial or SoftwareSerial), sample sketch "Shield Servo Example.ino" for CT-UNO, VB.net GUI for PC (User's Manual V1.1, GitHub)
- Packing list: 1 × SHIELD-Servo board; manual and sample code are downloads (User's Manual V1.1)

## Use cases
- Controlling 8 RC servo motors from an Arduino main board over UART
- Controlling servos from a computer through UC00A/UC00C and the Shield-Servo GUI
- Robotics using RC servos: humanoid robots, biologically inspired robots, robotic arms (User's Manual V1.1 framing)
- Offloading servo speed/position control from the host so the host can run other routines

## Known limitations
- Regulator output is 4 A continuous / 5 A peak total for all 8 servos (User's Manual V1.1)
- Powering servos from the Arduino 5 V (jumper K) is "strongly not recommended" for more than one small servo; Arduino 5 V is normally only 1 A max (User's Manual V1.1)
- If jumper K is used (Arduino 5 V powering servos), do NOT connect any power to VM and GND (User's Manual V1.1)
- VM absolute maximum 25 V, minimum 7 V (User's Manual V1.1)
- Servos are deactivated at start-up; the activate command must be sent first (User's Manual V1.1)
- Position reporting command with channel 0 is not executed (User's Manual V1.1)
- UART is 5 V logic; the 6-pin header TX/RX "should be interfaced to 5V logic UART" (User's Manual V1.1)
- Only UART control is described; no I2C, SPI, PWM-input or RC-receiver input (User's Manual V1.1)
- No command to change the baud rate is documented; default 9600 (User's Manual V1.1)
- Reset button resets the shield controller only, not the Arduino; do not press during operation (User's Manual V1.1)
- Manufacturing test point header must not be connected or shorted (User's Manual V1.1)
- Pulse-width-to-angle correspondence varies between servo manufacturers (User's Manual V1.1)
- GUI project needs Visual Studio Community 2015 or newer and may need the latest .NET Framework (User's Manual V1.1)

## Positioning (kept apart from specs)
- Product page: 8-channel RC servo controller shield for Arduino with built-in 5 V at 5 A (peak) switching regulator, supply 7 V to 25 V
- User's Manual: "reliable yet user friendly RC Servo motor controller to hobbyist and students"; "the enhanced version from SC08A" with on-board regulator and UC00A/UC00C interface; UART "present a flexible, fast and easy to use feature"

## Price band
RM79.80 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-8-channels-rc-servo-controller-shield-for-arduino

## Datasheet
https://docs.google.com/document/d/191P6FwTgJ_dWhAhB3eWfP0YMSbI4_7Kehgzw3pYy-AY/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/191P6FwTgJ_dWhAhB3eWfP0YMSbI4_7Kehgzw3pYy-AY/view

# Product fact sheets

## Product name
Cytron Screw Terminal Shield (SHIELD-SCREW2)

## Aliases
SHIELD-SCREW2, Shield-Screw2, Screw Terminal Shield, Cytron Screw Terminal Shield, Cytron Screw Shield, Screw Terminal Shield for Arduino

## What it is
An Arduino-format shield that extends all pins of the Arduino out to 3.5mm pitch screw terminals. It also carries a prototyping area of 0.1" spaced through-holes (connected and unconnected), a couple of 5V and GND busses, a reset button and a LED.

## Specs and functions
- Shield function: Adapter Prototype (Getting Started Guide)
- Screw terminal pitch: 3.5mm (Getting Started Guide)
- Pins extended: "all pins of the Arduino" to screw terminals (Getting Started Guide)
- Prototyping area: large prototyping space of both connected and unconnected 0.1" spaced through-holes (Getting Started Guide); located at the middle of the board (product page)
- Power busses: a couple of 5V and GND busses (Getting Started Guide)
- Reset button: yes (Getting Started Guide)
- LED: one LED (Getting Started Guide)
- Board size: 74.93mm x 81.28mm (Getting Started Guide)
- Stackable: Yes (Getting Started Guide)
- Terminal count: [NOT STATED]
- Terminal voltage/current rating: [NOT STATED]
- ISP/ICSP pads: [NOT STATED]
- Packing list: Screw Terminal Shield only (Getting Started Guide)
- Warranty: 12 months, manufacturing defects only; damage caused by misuse not covered; freight cost both ways not covered (Getting Started Guide; product page also states 12 months)

## Interfaces and compatibility
- Compatible mainboards: Arduino Uno, Arduino Mega 2560, Arduino Mega ADK, Arduino Leonardo, Arduino Due, CT-UNO, CIKU (Getting Started Guide)
- Mounts by stacking on the Arduino main board headers; stackable, so another shield can go on top (Getting Started Guide)
- Interface to the user: 3.5mm pitch screw terminals for the Arduino pins; 0.1" prototyping through-holes; 5V and GND busses (Getting Started Guide)
- No software or library required (Getting Started Guide has no software section)
- Exact terminal order and count: [NOT STATED]

## Use cases
- Screwing wires directly to the Arduino pins instead of using jumper wires
- Prototyping circuits on the 0.1" through-hole area while the Arduino pins remain available on screw terminals
- Stacking under another shield (stackable headers)

## Known limitations
- Terminal count, terminal order and terminal ratings are not stated in the Getting Started Guide
- No ISP/ICSP pads are documented
- No regulator, fuse or protection is documented; the 5V and GND busses are the Arduino's own supply
- Whether the extra Arduino Mega 2560 / Due pins are brought to terminals is not stated
- The Getting Started Guide is V1.0, JAN 2015

## Positioning (kept apart from specs)
- Product page: "upgraded the screw shield with the prototyping area at the middle"
- Getting Started Guide: has "a lot of the utility provided by Arduino Protoshield"

## Price band
RM31.50 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-cytron-screw-terminal-shield

## Datasheet
https://docs.google.com/document/d/1Z65lZsEQ4x1nS4j9RSolcZ5cMYRg-nfXlnVgrgTl15o/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1Z65lZsEQ4x1nS4j9RSolcZ5cMYRg-nfXlnVgrgTl15o/edit

# Product fact sheets

## Product name
Cytron Prototyping Shield (SHIELD-PROTO2)

## Aliases
SHIELD-PROTO2, Shield-Proto2, Cytron Prototyping Shield, Prototyping Shield for Arduino, Cytron Proto Shield, Cytron Arduino Proto Shield

## What it is
An Arduino prototyping shield with a standard 0.1" x 0.1" prototyping area, stackable headers, a reset button, one LED and GND and +5V rails, revised to be UNO R3 and Leonardo compatible. It is delivered assembled.

## Specs and functions
- Prototyping area: standard 0.1" x 0.1" (product page)
- Headers: stackable, 4 rows of stackable header (product page)
- Reset button: yes (product page)
- LED: one LED for power or output indicator (product page)
- Every pin extended out to two sides of the headers (product page)
- Rails: GND and +5V (product page)
- Mounting: 4 screw holes (product page)
- ISP: pads for ISP prepared (product page)
- SMD components: 4 SMD components (LED, push-button and resistor) soldered on the labelled PCB (product page)
- Dimension: 68.58mm x 58.42mm (product page)
- Delivered assembled (product page)
- Packing list: 1x shield (product page)
- Warranty: 12 months (product page)
- LED circuit details: [NOT STATED]
- Rail current rating: [NOT STATED]

## Interfaces and compatibility
- Compatible with Arduino UNO R3 and Leonardo (product page)
- Mounts on the Arduino with stackable headers (product page)
- ISP pads prepared; a fitted ISP header is [NOT STATED]
- Software: none required; Fritzing files provided (product page)

## Use cases
- Building circuits on a standard 0.1" protoboard grid on top of an Arduino, without the Arduino's 0.1-inch header offset
- Low-cost prototyping with maximum prototyping area within the Arduino dimensions

## Known limitations
- No Cytron datasheet or user manual; the product page is the only Cytron text source
- Only pads for ISP are stated, not a fitted ISP header
- How the LED is wired is not stated
- No regulator, fuse or protection is stated; the +5V rail comes from the Arduino
- Only UNO R3 and Leonardo compatibility is stated
- Schematic and PCB prints are provided "given as is"

## Positioning (kept apart from specs)
- Product page: low cost, maximum prototyping area within Arduino dimensions
- Product page: solves the 0.1-inch offset of the Arduino header versus standard protoboard

## Price band
RM14.70 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-cytron-prototyping-shield

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-cytron-prototyping-shield

# Product fact sheets

## Product name
Maker UNO Edu Kit (Arduino Compatible)

## Aliases
V-KIT-MUNO-EDU, KIT-MAKER-UNO-EDU, Maker UNO Edu Kit, Maker UNO Edu Kit (Arduino Compatible), Maker UNO EduKit, Maker UNO Edu Kit School Package 10+1

## What it is
A classroom kit built around the Maker UNO (an Arduino UNO-compatible board with on-board LEDs, a piezo buzzer and a programmable button), sold with a Getting Started Module of 10 lessons and 2 projects and a Teacher Guidebook for the Malaysian Form 2 RBT syllabus.

## Specs and functions
- Product code: V-KIT-MUNO-EDU (my.cytron.io); older Cytron page: KIT-MAKER-UNO-EDU
- Purchase options: Maker UNO Edu Kit (single set); School Package 10+1 ("10 sets + 1 free set (Get 11 sets for the price of 10)")
- Controller board: Maker UNO (ATmega328P, CH340 USB-serial, Micro USB, no DC jack) — board details in the Maker UNO fact sheet
- On-board I/O used in lessons: "12x LEDs, 1x piezo buzzer and 1x programmable button"
- Pin-label stickers included (user peels and applies them)
- Box has an opening for the USB cable so the board can stay in the box
- Getting Started Module lessons: 1 The LED (Digital Output); 2 LED Blinking; 3 LED Output (PWM); 4 Push Button as Digital Input; 5 Serial Write; 6 Serial Read; 7 Tone Melody; 8 Potentiometer as Analog Input; 9 LDR as Analog Input; 10 Controlling Motor
- Getting Started Module projects: Interactive Traffic Light; Light Theremin
- Lesson pins: LED pin 7 (L1, L2, L6); LED pin 3 PWM (L3); LED pin 4 + button pin 2 INPUT_PULLUP (L4); Serial 9600 baud (L5, L6); 10 kΩ potentiometer on A0 + LED 13 (L8); LDR with 10 kΩ on A0 + LED 13, threshold 600 (L9); motor from pin 6 through 220 Ω and a transistor, speeds 255/123/50/0 (L10)
- Interactive Traffic Light: vehicle green pin 5, yellow pin 6, red pin 7; pedestrian green pin 3, red pin 4; button pin 2; 5 x 220 Ω; yellow 2 s, red, pedestrian green 5 s
- Light Theremin: LDR + 10 kΩ on A0, piezo buzzer pin 8 via tone(), LED 13 shows calibration, calibration for the first 5 s after power-up
- Teacher Guidebook: 4 units, 10 hours total — Unit 1 Microcontroller Theory (2 h), Unit 2 Output (3 h), Unit 3 Input (2 h), Unit 4 Combination of Input and Output (3 h); learning standards 2.4.1–2.4.8; assessment Tier 1–6; Appendix 1 programming from Android (USB OTG Checker, ArduinoDroid)
- Software: Arduino IDE (module written for 1.8.x); CH340/CH341 USB driver for Windows and macOS
- Packing list: [NOT STATED] (product page list is an image; not in the module or Teacher Guidebook)
- Warranty: [NOT STATED] (blank on product page)
- Dimensions and weight: [NOT STATED]

## Interfaces and compatibility
- Power and programming over Micro USB only (Maker UNO has no DC jack and no Vin pin)
- Button: D2 with INPUT_PULLUP (pressed = LOW)
- Buzzer: D8 through the on-board slide switch (on to use the buzzer, off to free pin 8)
- PWM pins: ~3, ~5, ~6, ~9, ~10, ~11
- Analog inputs used: A0
- Arduino libraries and code compatible; Arduino UNO R3 shields except those needing Vin (see Maker UNO fact sheet)
- Documents linked: Maker UNO User's Manual, Getting Started Module PDF, schematic, Fritzing part, CH341 drivers, DSKP KSSM RBT Tingkatan 2, Teacher's Guide, Student's Class Module, Answer Scheme, Bahasa Malaysia versions
- Default sketch: github.com/CytronTechnologies/MakerUno_Examples (MakerUno_DefaultSketch)

## Use cases
- Teaching Arduino coding in class with the Maker UNO's on-board LEDs, buzzer and button before building circuits
- Form 2 RBT (DSKP KSSM) microcontroller unit: theory, output, input, combined input/output, project creation
- Digital output, PWM fading, push button input, serial write/read, tone melody, potentiometer and LDR analog input, DC motor speed control
- Interactive Traffic Light project
- Light Theremin project
- School Package 10+1 for a class set

## Known limitations
- Power is USB only; no DC jack and no Vin pin on the Maker UNO
- The on-board button occupies D2 and the buzzer occupies D8 (slide switch)
- analogWrite() works only on PWM pins ~3, ~5, ~6, ~9, ~10, ~11
- Pin-label stickers must be applied by the user
- Teacher Guidebook units 2.4, 3.4 and 4.3 need internet access; each student needs a Maker UNO; some topics need laptops or phones
- The Getting Started Module has no printed version or date
- Packing list and warranty are not stated in any Cytron text read

## Positioning (kept apart from specs)
- "Many students lack basic electronics knowledge and struggle with circuit diagrams, often spending much of a lesson wiring and troubleshooting."
- "The kit lets students skip building basic circuits at first and start coding quickly, with a project that lights the board and plays a melody on a button press."
- "The onboard LEDs act as both outputs and indicators, showing pin activity so students can tell whether a problem comes from wiring or code."
- School Package: "Get 11 sets for the price of 10"

## Price band
RM60.00 (single kit) to RM689.92 (School Package 10+1) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-edu-kits-arduino-compatible

## Datasheet
https://cdn.cytron.io/makeruno/Maker_Uno_Edu_Kit_Module.pdf

## Source type
Datasheet

## Source link
https://cdn.cytron.io/makeruno/Maker_Uno_Edu_Kit_Module.pdf

# Product fact sheets

## Product name
Maker UNO Learning Box - Everything You Need to Start Making

## Aliases
KIT-MAKER-UNO-START, Maker UNO Learning Box, Maker UNO Learning Box - Everything You Need to Start Making, Maker UNO Learning Kit

## What it is
A beginner kit that packs a Maker UNO board with the LEDs, switches, resistors, transistors, diode, potentiometer, IR line sensor, SR04 ultrasonic sensor, 3 V motor and breadboard needed for the 17 projects in Cytron's "Arduino Learning Guide for Beginner Using Maker UNO". The guide is a PDF linked from the product page.

## Specs and functions
- Product code: KIT-MAKER-UNO-START
- Controller board: 1x Maker UNO (board details in the Maker UNO fact sheet)
- Lessons: 7 lessons, 17 projects
- Lesson 1 Digital Output: P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence
- Lesson 2 Digital Input: P4 On-board Pushbutton Switch; P5 External Pushbutton Switch
- Lesson 3 Analog Output: P6 Construct An LED Circuit; P7 Fade An LED
- Lesson 4 Melody Tone: P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code
- Lesson 5 Analog Input: P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line
- Lesson 6 DC Motor: P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton
- Lesson 7 Ultrasonic Sensor: P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor
- Packing list: 1x Maker UNO; 1x 3V miniature brush motor; 1x DIY 4-blade propeller (blue); 1x SR04 ultrasonic sensor; 1x IR line sensor; 3x LED 5mm red; 3x LED 5mm yellow; 3x LED 5mm green; 3x pushbutton switch; 10x 220Ω; 10x 1kΩ; 10x 10kΩ; 1x 1N4007 diode; 2x 2N2222 transistor; 1x finger preset 10K; 1x 40-way M-M jumper; 1x 40-way M-F jumper; 1x Micro B USB cable; 1x breadboard 8.5cm x 5.5cm
- Software: Arduino IDE; CH341 (CH34x) USB driver; Maker UNO default sketch on GitHub
- Warranty: 12 months
- Dimensions and weight: [NOT STATED]
- Project wiring (pins per project): [NOT STATED] (guide PDF not read)

## Interfaces and compatibility
- Power and programming over Micro USB only (Maker UNO has no DC jack and no Vin pin)
- On-board button D2 (INPUT_PULLUP), on-board piezo buzzer D8 (slide switch), PWM on ~3, ~5, ~6, ~9, ~10, ~11, analog inputs A0–A5 (Maker UNO board facts)
- IR line sensor is read as an analog input in the lessons
- Ultrasonic sensor: SR04
- Motor projects use the 2N2222 transistors and the 1N4007 diode
- Arduino IDE (arduino.cc); CH34X driver for Windows (V3.5, Mar 2019), macOS (V1.5, Mar 2019), Linux (V1.5, Mar 2019, usually preinstalled); plug the Maker UNO in during driver installation
- Default program: github.com/CytronTechnologies/MakerUno_Examples (MakerUno_DefaultSketch)

## Use cases
- Learning Arduino from zero with no electronics or coding background (students and teachers)
- Digital output: turn on, blink and sequence LEDs
- Digital input: on-board and external pushbutton switches
- Analog output: build an LED circuit and fade an LED
- Melody tone: basic tones, "Happy Birthday" melody, code optimisation
- Analog input: serial monitor values, analog IR sensor reading, black line detection
- DC motor: control a motor and its speed with a pushbutton
- Ultrasonic sensor: set up the sensor and build a car's rear bumper sensor

## Known limitations
- Power is USB only; no battery or adapter in the kit
- The guide is a PDF download; a printed copy is not listed in the packing list
- Project wiring is in the guide PDF, which was not read for this fact sheet
- Not the Maker UNO X Learning Box: same 17-project structure but a different board and guide edition
- The 3 V motor must be driven through the supplied transistor, not directly from an I/O pin (Maker UNO I/O pin limit 20 mA)

## Positioning (kept apart from specs)
- "Everything You Need to Start Making"
- A beginner Arduino learning set created by a non-technical author, for students and teachers who lack electronics or coding experience; each lesson shows a visible result early, then gives a brief explanation of how it works
- "Arduino is the easiest platform to learn digital making."

## Price band
RM62.90 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-learning-box-everything-you-need-to-start-making

## Datasheet
https://s3-ap-southeast-1.amazonaws.com/cdn.cytron.io/makeruno/Arduino_Learning_Guide_for_Beginner_Using_Maker_UNO.pdf

## Source type
Website

## Source link
https://my.cytron.io/p-maker-uno-learning-box-everything-you-need-to-start-making

# Product fact sheets

## Product name
Learning Guide for Beginners with Maker Uno X compatible with Arduino

## Aliases
BOK-MUNOX, Maker UNO X Learning Guide, Maker Uno X Learning Guide book, Learning Guide for Beginners with Maker Uno X, Arduino Learning Guide for Beginners Using Maker UNO X, Maker UNO X guide book

## What it is
A printed beginner's guidebook (v1.5, February 2023, published by Cytron Technologies, written by ET Tan) that teaches Arduino on the Maker UNO X board through Lesson 0 Setting Up plus 7 lessons and 17 projects. It is designed for the Maker Uno X Learning Box and sold on its own as one book.

## Specs and functions
- Product code: BOK-MUNOX
- Format: printed book; packing: 1x book
- Edition read: v1.5, February 2023 ("Arduino Learning Guide For Beginners — MAKER UNO X"; "Explore STEM and Coding with Maker UNO Xperiment Kit"); earlier edition v1.4, February 2020
- Written by ET Tan (Tan Eng Tong, Co-founder and CEO, Cytron Technologies); edited by Cheryl Ng; illustrated by Suhana Azmi; revised by Hairil and 'Awatif (v1.5)
- Target board: Maker UNO X (with the Maker UNO X Learning Box)
- Lesson 0 Setting Up: pin-label stickers, breadboard stuck onto the board, micro USB cable; Arduino IDE download; CH341 driver for Windows (CH341SER.EXE) and Mac (CH341SER_MAC.ZIP)
- Lesson 1 Digital Output: P1 Turn On An LED; P2 Blink An LED; P3 Blink the LEDs In Sequence
- Lesson 2 Digital Input: P4 On-board Pushbutton Switch; P5 External Pushbutton Switch
- Lesson 3 Analog Output: P6 Construct An LED Circuit; P7 Fade An LED
- Lesson 4 Melody Tone: P8 Compose Basic Tone; P9 Compose "Happy Birthday" Melody; P10 Optimize Your Code
- Lesson 5 Analog Input: P11 Display Analog Value On Serial Monitor; P12 Read Analog IR Sensor; P13 IR Sensor To Detect Black Line
- Lesson 6 DC Motor: P14 Control A DC Motor; P15 Controlling A Motor Speed Using A Pushbutton
- Lesson 7 Ultrasonic Sensor: P16 Setting Up Ultrasonic Sensor; P17 Build A Car's Rear Bumper Sensor
- Project pins (as stated in the guide): P1–P3 LEDs on pins 7 and 2–7; P4 on-board switch pin 2 (INPUT_PULLUP) and LED 4; P5 external pushbutton on pin 3 with a 10 kΩ pull-up; P6–P7 external LED with 220 Ω on pin 5 (PWM); P8–P10 piezo buzzer on pin 8 via tone(); P11 potentiometer on A0; P12–P13 IR sensor VCC 5V, GND, A0 to A0; P14 DC motor on pin 5 through a 2N2222 transistor, 220 Ω resistor and a diode
- Tone values taught: Do 262, Re 294, Mi 330, Fa 349, So 392, La 440, Ti 494, high Do 523 Hz; delay 30 % longer than the note duration
- IR threshold rule: (reading on white + reading on black) / 2; author's example 500
- Motor speed demo: analogWrite(5, 255) for 3 s then analogWrite(5, 80) for 3 s; kit motor rated 3–6 V
- Each project links a demo video by QR code; each lesson ends with a Task and a summary
- Page count, size, ISBN: [NOT STATED]
- Warranty: 12 months

## Interfaces and compatibility
- For the Maker UNO X board: on-board LEDs on pins 2–13, piezo buzzer on pin 8, on-board switch on pin 2, "Debug" mode slide switch that enables the built-in LEDs and buzzer, PWM on pins 3, 5, 6, 9, 10, 11, analog input on A0–A5
- Software: Arduino IDE from arduino.cc (Windows 10+ 64-bit installer recommended; Mac package); CH341 driver; Mac port shown as /dev/cu.usbserial-220
- Not the guide for the Maker UNO Learning Box (that kit uses the Maker UNO edition of the guide)

## Use cases
- A student (or teacher) learning Arduino for the first time
- Turn on, blink and sequence LEDs
- Read the on-board and an external pushbutton; pull-up and pull-down circuits
- Build an LED circuit and fade it with PWM
- Play tones and the "Happy Birthday" melody; use the toneMelody example
- Read a potentiometer and an IR sensor; detect a black line
- Control a DC motor and its speed
- Set up an ultrasonic sensor and build a car's rear bumper sensor

## Known limitations
- Written for the Maker UNO X: Debug mode must be on for the built-in LEDs and buzzer; switch it off to use pin 8 for another device
- The on-board switch occupies pin 2 and cannot be shared with other components while in use
- P6 blinks forever once the switch is pressed until reset; P9 plays once because the code is in setup()
- The motor may lack torque if its blades rest on a surface; applying voltage beyond the motor's rating shortens its life
- Projects 15–17 and the total page count were not read for this sheet
- The product page does not state which edition ships

## Positioning (kept apart from specs)
- "I wrote this guide with you in mind - a student (or teacher), learning Arduino for the first time."
- "I just added explanation on some aspects that I initially struggled with and I also simplified the technical part for better understanding."
- "Simplifying Digital Making"

## Price band
RM39.00 (5+ RM37.10, 10+ RM35.10) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-arduino-learning-guide-for-beginners-with-maker-uno-x

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
PikaBot - Maker UNO Smart Car Kit

## Aliases
V-KIT-PIKABOT, KIT-PIKABOT, PikaBot, Pikabot, PIKABOT, PikaBot Smart Car Kit, Maker UNO Smart Car Kit, PikaBot - Maker UNO Smart Car Kit

## What it is
A DIY two-wheel robot car kit built on the Maker UNO board and the Maker Drive motor driver, with two TT gear motors, two IR line-tracking modules and an HC-SR04 ultrasonic sensor, assembled with jumper wires and powered by 4 AA batteries. It comes with a project booklet in an Arduino IDE (English) or mBlock (Bahasa Melayu) edition.

## Specs and functions
- Product code: V-KIT-PIKABOT (reseller model: KIT-PIKABOT)
- Booklet options: Arduino IDE (English); mBlock (Bahasa Melayu, v1.1)
- Controller: Maker UNO (see Maker UNO fact sheet)
- Motor driver: Maker Drive (see Maker Drive fact sheet)
- Motors: 2x 3-6VDC dual-axis TT gear motor with pre-soldered wires
- Wheels: 2x rubber wheel 63mm x 15mm
- Sensors: 2x IR line tracking module; 1x HC-SR04 ultrasonic
- Power: 4x AA batteries in a 4xAA battery holder; powers controller and motors; panel-mount rocker switch
- Breadboard: 1x mini breadboard 35x42mm; 40-way M-F jumper; 40-way M-M jumper
- Packing list (product page, truncated): 1x Maker UNO, 1x Maker Drive, 2x TT gear motor, 2x rubber wheel, 2x IR line tracking module, 1x HC-SR04 ultrasonic, 4x AA batteries, 1x 4xAA battery holder, 1x mini breadboard, 40-way M-F jumper, 40-way M-M jumper
- No soldering: assembled with jumper wires
- Arduino booklet projects: 1 Let's Move It (3 steps + Rectangle, Circle, Triangle challenges); 2 Oh No! Stop! (2 steps + challenge); 3 Black or White Line? (2 steps + challenge); 4 Music On (2 steps + Super Mario, Baby Shark, Birthday Song challenges)
- mBlock lesson series: 1 Move Around; 2 Detect Object; 3 Line Follow
- Arduino library: Cytron Motor Drivers Library (CytronMotorDriver.h), PWM_PWM mode
- Pin map (Cytron sample code): left motor D11/D10; right motor D9/D3; ultrasonic TRIG D5, ECHO D4; left IR A0, right IR A1 (digital read); start button D2 (on-board, INPUT_PULLUP); buzzer D8 (on-board)
- IR logic in code: LOW = white surface, HIGH = black line
- Ultrasonic distance in code: pulseIn(ECHO, HIGH) x 0.017 cm; lessons stop at 15 cm and avoid at 20 cm
- Warranty: [NOT STATED]
- Dimensions and weight: [NOT STATED]

## Interfaces and compatibility
- Maker UNO: USB Micro-B for programming; no DC jack or Vin pin
- Maker Drive: PWM_PWM control, 2.5–9.5 VDC input, 1 A continuous / 1.5 A peak per channel, 5 V 200 mA output (Maker Drive datasheet)
- Arduino IDE with the Cytron Motor Drivers Library (booklet shows Arduino 1.8.10 and library 1.0.1)
- mBlock 5 (online ide.mblock.cc or offline) with the "PikaBot" extension added from the device panel; upload mode over the COM port
- CH34x USB driver for the Maker UNO (CH341SER shown in the booklet)
- pitches.h must be present as a second tab for the music projects (full file in the Resources doc)

## Use cases
- Learning electronics, microcontrollers, sensors, motors and coding with a mobile robot
- Project 1: move forward, backward, turn; drive a rectangle, circle and triangle
- Project 2: measure distance with the ultrasonic sensor; stop or avoid obstacles
- Project 3: read the IR line sensors; follow a black line; stop at a full black line
- Project 4: play melodies on the Maker UNO buzzer (toneMelody, Super Mario, Baby Shark, Birthday Song)
- Reuse the parts to build new robots from cardboard, cartons, bottles or old toys

## Known limitations
- The booklet PDF is image-only; its wiring diagrams were not readable for this sheet
- The product page packing list is truncated in the capture; the full list is not confirmed from Cytron text
- Programs wait for the on-board D2 button before moving; the buzzer needs the D8 slide switch on
- Turn convention in Cytron code: robotMove(-200, 200) = turn left, robotMove(200, -200) = turn right; swapped motor wires reverse this
- The Maker UNO cannot take the battery directly (no DC jack, no Vin)
- The IR modules and HC-SR04 are generic modules, not Cytron Maker Line / Maker Object
- Warranty, weight and age range are not stated

## Positioning (kept apart from specs)
- DIY mobile robot kit; no soldering (jumper wires)
- "Schematics and mounting locations are printed inside the box"
- Programmable in the Arduino IDE or the block-based mBlock environment
- Cytron EDU line-up lists PikaBot beside ZOOM:BIT, Ikedo and EDU PICO; BEETLE:BIT is positioned as the next step after PikaBot

## Price band
RM128.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-pikabot-maker-uno-smart-car-kit

## Datasheet
https://drive.google.com/file/d/1G9rhCY_9ogJN4ufXdAwFmrgbaEHKP3Cp/view

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
Robo Pico

## Aliases
ROBO-PICO, RoboPico, Robo Pico Board

## What it is
A robot controller carrier board for the Raspberry Pi Pico / Pico W. The Pico plugs into a socket on the board; there is no microcontroller on the Robo Pico itself.

## Specs and functions
- Product code: ROBO-PICO
- Datasheet: Rev 1.0, April 2023; its spec table is titled "Absolute Maximum Ratings"
- Pi Pico Socket: socket for Raspberry Pi Pico and Pico W
- Power input voltage (USB, LiPo or VIN): 3.6 – 6 V
- Battery: single-cell LiPo / Li-ion, rechargeable via the USB port on the Raspberry Pi Pico / Pico W, protected from over-charge and over-discharge
- VIN terminal: any power source within 3.6 – 6 V
- On/Off switch: turns all power on/off, including the Raspberry Pi Pico; power LED; reset button (resets the Pico)
- DC motor driver: 2 channels, 1 A continuous and 1.5 A peak (< 5 seconds) per channel, PWM frequency max 20 kHz
- Motor pins: M1A = GP8, M1B = GP9, M2A = GP10, M2B = GP11
- Motor truth table: A Low, B Low → Brake; A High, B Low → Forward; A Low, B High → Backward; A High, B High → Hi-Z (Open), Coast
- Motor test buttons (run the motor at full speed: MxA forward, MxB backward) and motor status LEDs
- Servo ports: 4 x RC servo, signal on GP12, GP13, GP14, GP15; V+ equals the power source voltage
- Vmotor & Vservo: USB only → VUSB - 0.4 V; LiPo only or VIN only → VLiPo or VIN; USB + LiPo → VUSB - 0.4 V; USB + VIN: VIN < VUSB → VUSB - 0.4 V, VIN > VUSB and VIN - VUSB < 0.6 V → VIN - 0.4 V, VIN - VUSB > 0.6 V → VIN
- NeoPixel RGB LEDs: on GP18 (2 LEDs in Cytron's example code)
- Programmable buttons: GP20 and GP21
- Piezo buzzer: GP22, with buzzer mute switch
- VBAT sense: solder the jumper on the back to read VBAT on GP28 (ADC2); VADC2 = VBAT / 2 (VBAT = VIN or VUSB or VLiPo, whichever is higher)
- Grove ports: 7; total +3V3 output current 300 mA max
- Grove 1: GP0, GP1 (PWM0, SPI0, I2C0, UART0)
- Grove 2: GP2, GP3 (PWM1, SPI0, I2C1); shared with the Maker Port
- Grove 3: GP4, GP5 (PWM2, SPI0, I2C0, UART1)
- Grove 4: GP16, GP17 (PWM0, SPI0, I2C0, UART0)
- Grove 5: GP6, GP26 (GP26 = ADC0)
- Grove 6: GP26, GP27 (ADC0, ADC1; I2C1)
- Grove 7: GP7, GP28 (GP28 = ADC2)
- Status LEDs for the Grove-port GPIOs (13 pins in Cytron's demo code), on when the GPIO is high
- GPIO breakout: female pin headers for the Pico / Pico W GPIO pins
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃

## Interfaces and compatibility
- Hosts: Raspberry Pi Pico and Raspberry Pi Pico W
- Maker Port: compatible with QWIIC / STEMMA QT / Grove (with conversion cable); pins shared with Grove 2 (GP2, GP3)
- 7 Grove ports, 4 servo ports, 2 DC motor terminals, LiPo battery connector, VIN terminal
- CircuitPython: Pico / Pico W firmware from circuitpython.org; official examples Blink, Button, Buzzer, DC_Motor, Servo_Motor, Analog_Read, NTP_Clock, IoT_Blynk (libraries: neopixel, simpleio, adafruit_motor, adafruit_ntp, adafruit_requests)
- MicroPython: rp2-pico / rp2-pico-w firmware; official examples Blink, Button, Buzzer, DC_Motor, Servo_Motor, Analog_Read, NTP_Clock
- Arduino: arduino-pico core (Earle Philhower) via Boards Manager; official examples Blink, Button, Buzzer, DC_Motor (CytronMotorDriver, PWM_PWM on 8/9 and 10/11), Servo_Motor (Servo.h on 12–15), Analog_Read (pin 27)
- Cytron tutorial: Getting Started Guide with Robo Pico using CircuitPython

## Use cases
- Robotics with Raspberry Pi Pico / Pico W
- Build BocoBot Car with Robo Pico
- Build an RC robot car using Pi Pico W and Robo Pico
- Analog sensor reading (Maker Line / Maker Soil on Grove 6)
- SSD1315 OLED text display over I2C
- NTP clock
- IoT examples: simple HTTP server, ThingSpeak, Blynk

## Known limitations
- No microcontroller on the board; a Raspberry Pi Pico or Pico W is needed
- Datasheet names Pico and Pico W only
- Spec values are absolute maximum ratings
- Pins used by the board: GP8–GP11 (motors), GP12–GP15 (servos), GP18 (NeoPixel), GP20, GP21 (buttons), GP22 (buzzer); GP28 also, when the VBAT sense jumper is soldered
- GP26 is on both Grove 5 and Grove 6
- Grove 2 and the Maker Port share GP2 and GP3
- Grove 7's GP28 doubles as VBAT sense when the jumper is soldered
- Grove 5 (two SDA pins) and Grove 7 (one SCL pin) cannot carry I2C
- Motor current: 1 A continuous, 1.5 A peak for under 5 seconds per channel; PWM max 20 kHz
- A High / B High is coast, not brake; Low / Low is brake. With adafruit_motor, throttle = 0 drives both pins high (coast on this board) and throttle = None drives both low (brake) — the opposite of the comments in Cytron's demo code
- Cytron's MicroPython DC_Motor example labels A-low / B-high as "Forwards", which the datasheet truth table calls Backward
- Motor test buttons run the motor at full speed without any code
- Grove +3V3 total: 300 mA max
- Connecting LiPo and VIN at the same time is not recommended, "Although it's perfectly safe to do so"
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Battery charge current is not stated
- Motor and servo voltage on USB only is VUSB - 0.4 V

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Robotics with Raspberry Pi Pico / Pico W"
- Part of Cytron's Robo series

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-robo-pico-simplifying-robotics-with-raspberry-pi-pico

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
EDU PICO V2 – EDU Project & Innovation Kit for Pico 2 W

## Aliases
EDU PICO V2, EDU PICO 2, EDU-PICO2, EDU-PICO2-NB, EDUPICO2, EDU PICO 2: Project & Innovation Kit for Pico 2W, EDU Project & Innovation Kit for Pico 2 W

## What it is
A project and innovation board for the Raspberry Pi Pico 2 W with built-in sensors, display, audio, motor driver, servo ports and a USB relay. The Pico 2 W plugs into a socket on the board and is included in the kit, except in the EDU-PICO2-NB variant.

## Specs and functions
- Board name in datasheet: EDU-PICO2; variant EDU-PICO2-NB ships without the Raspberry Pi Pico 2 W
- Datasheet: Rev 1.1, June 2026; its spec table is titled "Absolute Maximum Ratings"
- Pi Pico socket: 2×20 female pin headers for the Pico 2 / Pico 2 W (inner rows); outer rows break out the GPIO pins
- Pico chip: RP2350 (EDU PICO hub)
- Power input voltage (USB, LiPo or VIN): 3.6 – 6 V
- Vin terminal: 3.6 V – 6 V, fits wires up to 18 AWG
- Battery: JST-PH 2-pin, single-cell LiPo or Li-ion; built-in charger, rechargeable via the USB port of the Raspberry Pi Pico 2 / Pico 2 W; protected from over-charge and over-discharge
- Charging LED, Power LED, On/Off switch (also powers the Pico), Reset button
- Digital input: low -0.3 – 0.8 V, high 2.0 – 5.5 V, with the datasheet footnote "Only Pico 2 / Pico 2 W boards with RP2340-A4 stepping support 5 V-tolerant digital GPIO pins."
- Digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Push buttons: Button A = GP0, Button B = GP1; pulled HIGH, LOW when pressed
- RGB LEDs: 5× addressable SK6812-based, WS2812B compatible, on GP14
- I2C bus: SDA = GP4, SCL = GP5
- Temperature & humidity sensor: AHT20, I2C 0x38
- Colour & light sensor: OPT4048, I2C 0x44
- OLED display: 0.96 inch 128x64 white, SSD1315, I2C 0x3C
- Gesture & proximity sensor: PAJ7620, I2C 0x73
- PDM microphone: MP34DT01, DOUT = GP2, CLK = GP3
- Potentiometer: GP28 (ADC2)
- Stereo audio jack: Right = GP20, Left = GP21; non-amplified, for earphone or amplified speaker
- Audio/Buzzer switch: selects left-channel audio out or the piezo buzzer
- Piezo buzzer: datasheet says GP8; Cytron's EDU PICO 2 code (GitHub) uses GP21
- Servo ports: 4× RC servo, signal GP6, GP7, GP8, GP9; V+ equals power source voltage
- DC motor driver: 2 channels, locked-antiphase (dual-PWM); M1A = GP10, M1B = GP11, M2A = GP12, M2B = GP13; terminals fit wires up to 18 AWG
- Motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds); PWM frequency max 20 kHz
- Motor truth table: A Low, B Low → Brake; A High, B Low → Forward; A Low, B High → Backward; A High, B High → Hi-Z (Open), Coast
- Motor test buttons (run the motor at full speed) and red motor status LEDs
- Vmotor & Vservo: USB only → VUSB - 0.4 V; LiPo only or VIN only → VLiPo or VIN; USB + LiPo → VUSB - 0.4 V; USB + VIN: VIN < VUSB → VUSB - 0.4 V, VIN > VUSB and VIN - VUSB < 0.6 → VIN - 0.4 V, VIN - VUSB > 0.6 → VIN
- USB relay: 5 V USB output switched by a relay on GP22; max 5 V, 500 mA; overcurrent protection above 500 mA; D+ = GP26, D- = GP27
- Micro SD card socket (SPI): GP16 = SDO, GP17 = CSn, GP18 = SCK, GP19 = SDI (datasheet labels)
- Log Data to Pico's Flash switch: GP15; Enable = pulled LOW, Disable = pulled HIGH; can be repurposed
- Grove ports: 9, 4-pin, 2.0 mm pitch, already connected to the adjacent Grove modules; total +3V3 output current 300 mA max
- Grove 1: GP0, GP1 – Buttons
- Grove 2: GP14 only – RGB LEDs
- Grove 3, 4, 5: GP4, GP5 – AHT20, PAJ7620, OPT4048, SSD1315
- Grove 6: GP2, GP3 – PDM Microphone
- Grove 7: GP28 only – Potentiometer
- Grove 8: GP20, GP21 – Audio & Buzzer
- Grove 9: GP26, GP27 – USB-A Port
- Status LEDs for the Grove-port GPIOs, on when the GPIO is high
- Protoboard with Grove port
- Operating temperature: -20 – 85 ℃
- In the box: EDU PICO V2 Board ×1; Step-by-step Guidebook (English) ×1; Raspberry Pi Pico 2 W ×1 (not in EDU-PICO2-NB); USB Micro B Cable ×1; Grove 4 Pin Buckled 20cm Cable ×8; Micro Servo with Servo Horns ×1; DC2-6V Miniature Motor with 20cm Wire ×1; Mini Phillips Head Screwdriver ×1; DIY 4 Blades 56mm Motor Propeller (Blue) ×1; USB LED Light Stick (Blue) ×1; Cable Tie 100mm ×5; Self adhesive Round Velcro 10mm (Hook and loop pairs) ×27

## Interfaces and compatibility
- Hosts: Raspberry Pi Pico 2 W (included except EDU-PICO2-NB); socket text also names Pico 2
- 9 Grove ports, 4 servo ports, 2 DC motor terminals, USB-A relay port, Micro SD socket, stereo audio jack, LiPo connector, VIN terminal
- CircuitPython: official course language; Thonny IDE with "CircuitPython (generic)" interpreter; Thonny firmware install with target volume RP2350 and variant "Cytron EDU PICO 2" for Pico 2 W
- GitHub repo Cytron-EDU-PICO2: firmware UF2, CircuitPython demo code, guidebook code
- Course: 8 chapters, 7 projects, over 10 activities; guidebook in English (Malay and Chinese "Coming soon")
- MicroPython, Arduino, MicroBlocks: [NOT STATED] for V2
- Changes from EDU PICO (V1) per the two datasheets: Pico W → Pico 2 W; APDS9960 (0x39) replaced by PAJ7620 (0x73) and OPT4048 (0x44); USB relay gains D+ GP26 / D- GP27; Grove 9 now connected to the USB-A port; digital input high max 3.6 V → 5.5 V (with stepping footnote); box adds cable ties and velcro
- Same in V1 and V2 datasheets: buttons GP0/GP1, RGB GP14, I2C GP4/GP5, AHT20 0x38, SSD1315 0x3C, microphone GP2/GP3, potentiometer GP28, audio GP20/GP21, servos GP6–GP9, motors GP10–GP13, SD GP16–GP19, log switch GP15, relay GP22, 3.6 – 6 V input, motor and relay ratings

## Use cases
- Introduction to CircuitPython
- Water Drinking Reminder
- Gesture Reaction Game
- Colour Detection Game
- Automated Waste Bin
- Noise Pollution Monitoring
- Smart Classroom
- Climate Control Greenhouse
- Flappy Bird Game
- Wireless Communication System
- DIY SpaceShip Game
- Gesture Snake game
- Color Based Water pH System
- Smart Microphone Alert System
- Data logging to the Pico's flash with CircuitPython

## Known limitations
- Spec values are absolute maximum ratings
- Power input 3.6 – 6 V only
- 5 V-tolerant digital inputs only on Pico 2 / Pico 2 W boards with the stepping named in the datasheet footnote ("RP2340-A4")
- Motor current: 1 A continuous, 1.5 A peak for under 5 seconds per channel; PWM max 20 kHz
- A High / B High is coast, not brake; Low / Low is brake
- Motor direction depends on wiring; swap MxA and MxB to reverse
- Motor test buttons run the motor at full speed
- Motor and servo voltage on USB only is VUSB - 0.4 V; servo V+ equals power source voltage
- USB relay: 5 V, 500 mA max; overcurrent protection above 500 mA
- Grove +3V3 total: 300 mA max
- Grove 2 and Grove 7 carry one GPIO each
- GP26/GP27 are shared by Grove 9 and the USB-A port D+ / D-
- GP8 is a servo signal pin
- The buzzer and the left audio channel share one output, selected by the Audio/Buzzer switch
- Audio jack output is not amplified
- Protoboard: only the pins near the Grove port pins are connected
- USB and VIN can be connected at the same time; "electrically safe" but "not recommended for normal operation"
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Charging LED flickering often, or on with no battery, means the board is not getting enough power from the USB port
- AHT20: measure every 2 seconds for accuracy
- Log-data switch with Cytron's boot.py makes the filesystem read-only to the computer; needed when powered via USB only
- Datasheet is internally inconsistent on the buzzer pin (GP8) and motor truth-table pins (GP8/GP9); the motor terminals are GP10–GP13
- Battery charge current: [NOT STATED]
- Dimensions: [NOT STATED] in text (drawing only)

## Positioning (kept apart from specs)
- "Explore CircuitPython, the fastest-growing programming language with EDU PICO V2" (EDU PICO hub)
- "EDU PICO V2 came with new and improved RP2350 that can handle more complex code and component" (EDU PICO hub)
- "Educational kit for learning Python"; "An all-in-one platform to learn electronics and Python programming through hands-on-projects" (product-page images)
- "13 Built-in Functions with 9 Detachable Modules"; "Breakable Modules – Total of 9 functional grove modules"; "No soldering & wiring required" (product-page images)
- "Beginner friendly"; "Perfect for students & educators" (product-page images)

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-edu-pico-2-project-innovation-kit-for-pico-2-w

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
Maker Pi RP2040

## Aliases
MAKER-PI-RP2040, Cytron Maker Pi RP2040, Maker Pi RP2040: Simplifying Robotics with Raspberry Pi RP2040

## What it is
A robot controller board with the Raspberry Pi RP2040 microcontroller soldered on the board. It has a 2-channel DC motor driver, 4 servo ports and 7 Grove ports.

## Specs and functions
- Product code: MAKER-PI-RP2040
- Datasheet: Rev 1.2, January 2022; its spec table is titled "Absolute Maximum Ratings"
- MCU (product page): Raspberry Pi RP2040, dual-core Arm Cortex-M0+, 264KB internal RAM, 2MB of Flash memory, "the exact same specifications with Raspberry Pi Pico"
- Power input voltage (USB, LiPo or VIN): 3.6 – 6 V
- Power sources: Micro USB, single-cell LiPo / Li-Ion connector, VIN terminal (any power source within 3.6 - 6V); product page: "Automatic power selection: USB 5V, LiPo (1-cell) or Vin (3.6-6V)"
- Battery: rechargeable via USB, protected from overcharge and over-discharge; product page: built-in 1-cell LiPo/Li-Ion charger
- On/Off switch, power LED, reset button (resets the RP2040), boot button (hold while resetting to enter bootloader mode), debug port
- DC motor driver: 2 channels, 1 A continuous and 1.5 A peak (< 5 seconds) per channel, PWM frequency max 20 kHz
- Product page: controls 2x brushed DC motors or 1x bipolar/unipolar stepper motor
- Motor pins: M1A = GP8, M1B = GP9, M2A = GP10, M2B = GP11
- Motor truth table: A Low, B Low → Brake; A High, B Low → Forward; A Low, B High → Backward; A High, B High → Hi-Z (Open), Coast
- Motor test buttons (motor runs at full speed: MxA forward, MxB backward) and motor status LEDs
- Servo ports: 4 x RC servo, signal on GP12, GP13, GP14, GP15; V+ equals the power source voltage
- Vmotor & Vservo: USB only → VUSB - 0.4 V; LiPo only or VIN only → VLiPo or VIN; USB + LiPo → VUSB - 0.4 V; USB + VIN: VIN < VUSB → VUSB - 0.4 V, VIN > VUSB and VIN - VUSB < 0.6 → VIN - 0.4 V, VIN - VUSB > 0.6 → VIN
- RGB LEDs: WS2812B on GP18 (product page: 2x RGB LED (Neopixel))
- Programmable buttons: GP20 and GP21
- Piezo buzzer: GP22, with buzzer mute switch
- Grove ports: 7; total +3V3 output current 300 mA max
- Grove 1: GP0, GP1 (PWM0, SPI0, I2C0, UART0)
- Grove 2: GP2, GP3 (PWM1, SPI0, I2C1)
- Grove 3: GP4, GP5 (PWM2, SPI0, I2C0, UART1)
- Grove 4: GP16, GP17 (PWM0, SPI0, I2C0, UART0)
- Grove 5: GP6, GP26 (GP26 = ADC0)
- Grove 6: GP26, GP27 (ADC0, ADC1; I2C1)
- Grove 7: GP7, GP28 (GP28 = ADC2)
- GPIO status LEDs: 13, for the Grove-port GPIOs (GP0–7, GP16, GP17, GP26–28), on when the GPIO is high
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃
- USB VID & PID (CircuitPython & Arduino Core): VID 0x2E8A, PID 0x1000
- Product page: dimensions 88mm(L) x 64mm(W) x 13mm(H); 4x 4.8mm mounting hole (LEGO® pin compatible); 6x M3 screw hole

## Interfaces and compatibility
- Micro USB (upload programs and power), LiPo battery connector, VIN terminal, 2 DC motor terminals, 4 servo ports, 7 Grove ports, debug port
- CircuitPython: preloaded with a demo program; board-specific firmware at circuitpython.org/board/cytron_maker_pi_rp2040 with adafruit_motor, neopixel and simpleio built in; the Raspberry Pi Pico CircuitPython firmware also works if those libraries are added manually
- Bootloader: hold BOOT and press RST to get the RPI-RP2 drive, then copy the .uf2 file
- MicroPython and C/C++ for Pico/RP2040
- Arduino: datasheet lists the USB VID/PID for the Arduino Core; product page points to Arduino's official news
- Product page: "Software, firmware, libraries and resources that are developed for Pico should work seamlessly"
- Wi-Fi: product page suggests adding a Grove WiFi 8266 module via a Grove port
- Compatible accessory (product page): USB Micro B cable

## Use cases
- Robotics with the Raspberry Pi RP2040
- DIY robot / motion control projects
- Driving 2 brushed DC motors or 1 bipolar/unipolar stepper motor
- Driving up to 4 RC servo motors
- Connecting Grove modules (digital, analog, I2C, SPI, UART)

## Known limitations
- Spec values are absolute maximum ratings
- Power input range is 3.6 – 6 V; motor and servo voltage equals the power input voltage (VUSB - 0.4 V on USB only)
- Motor current: 1 A continuous, 1.5 A peak for under 5 seconds per channel; PWM max 20 kHz
- Pins used by the board: GP8–GP11 (motors), GP12–GP15 (servos), GP18 (RGB), GP20, GP21 (buttons), GP22 (buzzer)
- GP26 is on both Grove 5 and Grove 6
- Grove 5 and Grove 7 cannot carry I2C
- Grove +3V3 total: 300 mA max
- A High / B High is coast, not brake; Low / Low is brake. With adafruit_motor, throttle = 0 drives both pins high (coast on this board) and throttle = None drives both low (brake) — the opposite of the comments in Cytron's demo code
- Motor test buttons run the motor at full speed without any code
- Connecting LiPo and VIN at the same time is not recommended, "Although it's perfectly safe to do so"
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Battery charge current is not stated
- No onboard Wi-Fi

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Robotics with Raspberry Pi® RP2040"
- Product page: "Cytron Maker Pi RP2040 is basically the Raspberry Pi Pico + Maker series' goodness"
- Cytron internal: "very well received among the users", launched in Jun 2021

## Price band
RM48.00 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-pi-rp2040-simplifying-robotics-with-raspberry-pi-rp2040

## Datasheet
https://docs.google.com/document/d/1DJASwxgbattM37V4AIlJVR4pxukq0up25LppA8-z_AY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1DJASwxgbattM37V4AIlJVR4pxukq0up25LppA8-z_AY/edit

# Product fact sheets

## Product name
Maker Pi Pico

## Aliases
MAKER-PI-PICO, Cytron Maker Pi Pico, Maker Pi Pico: Simplifying Raspberry Pi Pico for Beginners

## What it is
A beginner project board for the Raspberry Pi Pico, with the Pico soldered onboard. It breaks out all Pico pins and adds LEDs, buttons, a buzzer, audio out, a microSD socket, an ESP-01 socket and 6 Grove ports.

## Specs and functions
- Product code: MAKER-PI-PICO
- Datasheet: Rev 1.2, March 2021 (covers MAKER-PI-PICO and MAKER-PI-PICO-NB); its spec table is titled "Absolute Maximum Ratings"
- Host board: Raspberry Pi Pico, soldered onboard (product page packing list)
- Power input voltage (USB): 4.5 – 5.5 VDC
- Micro USB port: used to power up the Maker Pi Pico and upload programs from PC
- 3V3 power LED
- GPIO LEDs: LED indicator for Raspberry Pi Pico GPIO, on when the GPIO state is high (product page: "LED indicators on all GPIO pins")
- WS2812B RGB LED: 1, on GP28
- Programmable buttons: 3, on GP20, GP21 and GP22; Rev1.0.0 to 1.1.0 = enable internal pull-up in software; Rev1.2.0 = pulled-up permanently on hardware with debouncing capacitor
- Reset button: resets the Raspberry Pi Pico
- Piezo buzzer: GP18, with buzzer mute switch
- Audio out: non amplified, 3.5mm stereo audio jack; Left channel GP18, Right channel GP19
- Micro SD card socket: GP10 CLK / SCK, GP11 CMD / SDI, GP12 DAT0 / SDO, GP13 DAT1 / X, GP14 DAT2 / X, GP15 CD/DAT3 / CSn (SD mode / SPI mode); unused pins must be configured as internal pull-ups
- ESP-01 socket: for ESP-01 ESP8266 WiFi module, GP16-17 (product page)
- Grove ports: 6 (product page)
- GPIO breakout: two 20 ways pin headers, male pin headers on MAKER-PI-PICO
- Debugging port breakout
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.62 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃

## Interfaces and compatibility
- Micro USB (power and programming), 6 Grove ports, 3.5mm stereo audio jack, micro SD card socket, ESP-01 socket, debugging port breakout, two 20-way GPIO pin headers
- Programming: CircuitPython, MicroPython and C/C++; programs upload over USB by drag and drop
- Cytron out-of-the-box demo code in CircuitPython and MicroPython on GitHub (CytronTechnologies/MAKER-PI-PICO)
- RGB LED on GP28 is driven with the Pico's PIO feature (product page Q&A)
- Grove: official or compatible Grove 4-pin cables recommended (product page Q&A)
- Pico W: product page Q&A says Maker Pi Pico with an ESP-01 module "Can achieve the same purpose, but code and library will not be the same"
- Packing list: 1 x Maker Pi Pico (Raspberry Pi Pico soldered onboard, with CircuitPython loaded), 1x Pinout reference card

## Use cases
- Learning Raspberry Pi Pico for beginners
- STEM & robotics projects
- Real-Time Multitasking on Maker Pi Pico Using pyRTOS
- Building Line Following Robot Using Maker Pi Pico, Maker Drive and Maker Line
- Play MP3 File on Maker Pi Pico Using CircuitPython
- Read and Display Environment Sensor Data Using Raspberry Pi Pico and CircuitPython
- Metronome with Maker Pi Pico, programmed with CircuitPython
- Ultrasonic HC-SR04P Using Raspberry Pi Pico
- IoT-enabling a project with an ESP-01 module

## Known limitations
- Spec values are absolute maximum ratings
- Power input is USB only, 4.5 – 5.5 VDC
- Audio output is not amplified; connect an earphone or amplified speaker
- GP18 is shared by the piezo buzzer and the left audio channel
- Unused microSD pins must be configured as internal pull-ups
- On PCB Rev1.0.0 to 1.1.0 the button pull-ups must be enabled in software
- The RGB LED on GP28 needs the Pico's PIO feature to drive it
- The ESP-01 module is not included in the packing list
- The datasheet names the Raspberry Pi Pico only

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Raspberry Pi Pico for Beginner"
- Product page: "It is a compact yet feature-packed board designed to sit at the heart of your STEM & robotics projects."
- Product page: "Work out-of-the-box. No soldering!"

## Price band
RM48.00 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-pi-pico

## Datasheet
https://docs.google.com/document/d/1JoHsZk5IipQPCLXWbZYpDKjGlnkyACOJ1taUrKVsRg8/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1JoHsZk5IipQPCLXWbZYpDKjGlnkyACOJ1taUrKVsRg8/edit

# Product fact sheets

## Product name
Maker Pi Pico Mini: Simplifying Projects with Raspberry Pi Pico

## Aliases
MAKER-PI-PICO-MINI, MAKER-PI-PICO-MINI-NB, Maker Pi Pico Mini, Cytron Maker Pi Pico Mini

## What it is
A small carrier board for the Raspberry Pi Pico / Pico W with status LEDs, a button, a passive buzzer, an RGB LED, three JST-SH Maker Ports and a USB-rechargeable single-cell LiPo / Li-Ion battery input. MAKER-PI-PICO-MINI comes with a Pico / Pico W pre-mounted; MAKER-PI-PICO-MINI-NB has a Pi Pico socket instead.

## Specs and functions
- Power input voltage, USB: 4.5–5.5 VDC (Datasheet, Absolute Maximum Ratings)
- Power input voltage, LiPo battery: 3.3–4.2 VDC
- Digital input voltage: low -0.3 to 0.8 V; high 2.0 to 3.6 V
- Digital output voltage: low 0 to 0.5 V; high 2.6 to 3.3 V
- Analog input voltage: 0 to 3.3 V
- Operating temperature: -20 to 85 ℃
- Dimensions: 53.85 mm × 23.12 mm
- Status LEDs for GP0 - GP5 (6 LEDs), turn on when the IO state is high
- GPIO LED Enable Jumper: cut the trace to disable the GPIO LEDs
- Programmable button on GP20 (hardware pull-up and debounce capacitor per schematic)
- Reset button (RUN)
- Programmable passive piezo buzzer on GP18
- User programmable WS2812B RGB LED on GP28
- LiPo battery connector for single cell LiPo / Li-Ion, rechargeable via USB; charging LED
- Battery charger MCP73831T-2ACI/OT and protection IC CT2105 (schematic)
- 3.3V power LED
- GPIO breakout for all Pico pins (headers not pre-soldered on the pre-mounted version)
- Pi Pico socket on MAKER-PI-PICO-MINI-NB only

## Interfaces and compatibility
- Host: Raspberry Pi Pico / Pico W
- 3x Maker Ports, JST-SH 4-ways, pin order GND, 3V3, GPIO, GPIO: GP0/GP1 (I2C0 SDA0/SCL0, UART0 TX0/RX0), GP4/GP5 (I2C0 SDA0/SCL0, UART1 TX1/RX1), GP26/GP27 (I2C1 SDA1/SCL1, A0/A1)
- Maker Ports compatible with Qwiic, STEMMA QT and Grove (via conversion cable)
- Board uses GP0–GP5 (status LEDs), GP18 (buzzer), GP20 (button), GP28 (RGB LED)
- Battery: single cell LiPo / Li-Ion

## Use cases
- Projects with Raspberry Pi Pico / Pico W
- Battery-powered Pico / Pico W projects with USB recharging
- Connecting Qwiic, STEMMA QT and Grove (via conversion cable) modules to a Pico

## Known limitations
- No audio jack, no microSD socket, no ESP-01 socket, no buzzer mute switch, no on/off switch
- Maker Ports are JST-SH; Grove modules need a conversion cable
- Maker Ports GP0/GP1 and GP4/GP5 both use I2C0
- Only GP26 and GP27 offer analog input on a Maker Port; GP28 (A2) drives the RGB LED
- Status LEDs on GP0–GP5 light whenever the pin is HIGH; cut the jumper to disable them
- GPIO breakout headers are not pre-soldered on the version with Pico / Pico W pre-mounted
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Pico 2 / Pico 2 W compatibility: [NOT STATED]
- Charge current and 3V3 current budget for Maker Ports: [NOT STATED]

## Positioning (kept apart from specs)
- Product page title: "Maker Pi Pico Mini: Simplifying Projects with Raspberry Pi Pico"
- Datasheet tagline: "Simplifying Projects with Raspberry Pi Pico / Pico W"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-maker-pi-pico-mini-simplifying-projects-with-raspberry-pi-pico

## Datasheet
https://docs.google.com/document/d/14Yzc7C-3NXtMi0Cuqn2ZFWilJjBVvCIbsKoMZJ8b24Q/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/14Yzc7C-3NXtMi0Cuqn2ZFWilJjBVvCIbsKoMZJ8b24Q/edit

# Product fact sheets

## Product name
MOTION 2350 Pro

## Aliases
MOTION-2350-PRO, Cytron MOTION 2350 Pro, MOTION 2350 Pro Rev 2.0, MOTION2350 Pro

## What it is
A robot controller board built on the Raspberry Pi RP2350, with a 4-channel brushed DC motor driver, 8 servo ports and 3 Maker Ports. The current board is Rev 2.0.

## Specs and functions
- MCU: RP2350
- Datasheet: Rev 2.0, September 2025; its spec table is titled "Absolute Maximum Ratings"
- Revision ID: Rev 2.0 has a "REV 2.0" silkscreen label just below the "MOTION 2350 PRO" logo; its bottom side has fewer IC chips
- Power input voltage (USB or VIN): 3.6 – 16 V; absolute maximum VIN 18 V, recommended maximum 16 V
- VIN terminal: external 3.6V – 16V DC; can be powered by an external LiPo or 4x AA batteries
- USB-C: program upload and power
- On/Off switch, plus an Ext. On/Off switch header (onboard switch must be Off to use it)
- Overvoltage protection: above 18V the board shuts down, and resumes once the voltage is back in the safe range
- DC motor driver: 4 channels (M1–M4), 5 A continuous and 10 A peak (< 5 seconds) per channel, PWM frequency max 20 kHz
- Motor driver has overcurrent and overtemperature protection: shutdown threshold 150 ℃, thermal hysteresis (recovery) 60 ℃; the datasheet text says it resumes below a safe temperature (typically 100°C)
- Motor pins: M1A = GP8, M1B = GP9, M2A = GP10, M2B = GP11, M3A = GP12, M3B = GP13, M4A = GP14, M4B = GP15
- Vmotor: USB only → VUSB - 0.4 V to VUSB; VIN only → VIN; USB + VIN: VIN < VUSB → VUSB - 0.4 V to VUSB, VIN > VUSB and VIN - VUSB < 0.6 V → VIN - 0.4 V, VIN - VUSB > 0.6 V → VIN
- Motor test buttons (run the motor at full speed) and motor status LEDs
- Servo ports: 8 x RC servo, signal on GP0 – GP7, header marked GND / 5V / SIG
- 5V servo supply: VIN > 5.8 V → 5 V from a buck converter; VIN < 5.5 V → follows VIN (Schmitt-trigger switching)
- Total +5V output current (servo ports): 3 A when VIN < 5.8 V, 2.5 A when VIN > 5.8 V
- Total +3V3 output current (GPIO breakout & Maker Ports): 200 mA max
- Maker Ports: 3 x JST-SH 4-way, on GP16/GP17, GP26/GP27, GP28/GP29
- GPIO breakout: 8 pins (GP16 – GP19, GP26 – GP29) in colour-coded GVS format with 3.3V
- USB host (Type-A): D+ = GP24, D- = GP25; 5 V, 100 mA max
- RGB LEDs: 2 x WS2812B (NeoPixel compatible) on GP23
- User buttons: GP20 and GP21
- Piezo buzzer: GP22, with buzzer mute switch
- Measure VIN jumper: solder it to read VIN on GP29 (ADC3); formula as printed "VIN = VADC / 6.1"
- GPIO/servo status LEDs: on when the IO is high
- Debug header: SWDIO, GND, SWCLK; BOOT and RST buttons
- Digital input: low -0.3 – 0.8 V, high 2.0 – 5.5 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃

## Interfaces and compatibility
- Maker Ports: compatible with Qwiic, STEMMA QT and Grove (via conversion cable)
- USB host for a USB joystick/gamepad
- 4 brushed DC motor terminals, 8 servo ports, 8-pin GPIO breakout, VIN terminal, USB-C
- CircuitPython: preloaded with a demo program; firmware is board "cytron_motion_2350_pro" on circuitpython.org (board.M1A – board.M4B, NEOPIXEL, VOLTAGE_MONITOR; NeoPixel, Motor and SimpleIO libraries built in)
- MicroPython: official board CYTRON_MOTION_2350_PRO (pin names M1A – M4B, BTN1, BTN2, NEOPIXEL)
- C/C++: listed on the product page
- Arduino: product page says "Arduino IDE (coming soon)"; the arduino-pico (Earle Philhower) core includes the board "Cytron Motion 2350 Pro"
- Product page: compatible with the existing Raspberry Pi Pico ecosystem

## Use cases
- Building an advanced robot while minimizing effort on electronics and focusing on mechanics
- Robots with mecanum wheels using the 4-channel driver
- Robots controlled by a USB joystick/gamepad through the USB host port

## Known limitations
- Rev 2.0 ratings (5 A continuous / 10 A peak) apply to Rev 2.0 only; Rev 1.0 is rated 3 A continuous / 5 A peak and has no motor overcurrent protection
- Product page and Cytron's GitHub pinout image still state 3 A per channel (Rev 1 figures)
- Thermal shutdown may occur even if current is below the rated value; a heatsink or better airflow helps
- Spec values are absolute maximum ratings
- Connecting USB and VIN at the same time is not recommended (the datasheet says it is safe)
- Servo 5V rail follows VIN when VIN is below 5.5 V
- Maker Ports and the GPIO breakout share GP16, GP17, GP26, GP27, GP28, GP29; free user GPIO is GP16 – GP19 and GP26 – GP29 only
- With the VIN jumper soldered, GP29 is used and its GPIO LED stays on
- Motor test buttons run the motor at full speed without any code
- The ext. switch header works only with the onboard switch Off
- USB host output: 100 mA max
- The datasheet has no motor-driver truth table (brake/coast not stated)
- arduino-pico maps LED_BUILTIN to GP2 (a servo pin), Serial1 to GP0/GP1 and SPI to GP4 – GP7 (servo pins)
- Cytron's demo code comment says the NeoPixels are on GP18; the code and datasheet use GP23

## Positioning (kept apart from specs)
- Datasheet tagline: "An Advanced Robotics Controller for Beginners"
- Product page: "Built for beginner and intermediate users to experience the Pro version of the board"
- Product page: "Maker" features such as silkscreen GPIO references, colored headers, quick test buttons and motor output LEDs

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-motion-2350-pro

## Datasheet
https://www.farnell.com/datasheets/4726021.pdf

## Source type
Datasheet

## Source link
https://www.farnell.com/datasheets/4726021.pdf

# Product fact sheets

## Product name
Maker Nano RP2040 Getting Started Bundles

## Aliases
V-MN2040, Maker Nano RP2040 Getting Started Bundles, Maker Nano RP2040 Getting Started Kit, Maker Nano RP2040 Getting Started With Blynk IoT, Maker Nano RP2040 Blynk IoT Bundle

## What it is
Two beginner bundles around the Cytron Maker Nano RP2040 board: a Getting Started Kit of breadboard electronics for the Arduino-IDE lessons, and a Getting Started With Blynk IoT variant that adds a Grove WiFi 8266 for Blynk IoT lessons. Each is paired with a Cytron Getting Started Google Doc.

## Specs and functions
- Product code: V-MN2040
- Variants: Getting Started Kit; Getting Started With Blynk IoT
- Controller board: Maker Nano RP2040 (MAKER-NANO-RP2040) — board specs are in the Maker Nano RP2040 fact sheet
- Wi-Fi module (Blynk variant): Grove WiFi 8266, Ai-Thinker ESP-12F module preloaded with Espressif ESP-AT firmware (doc wording "v2.20")
- Components used in "Getting Started With Maker Nano RP2040": 1x Maker Nano RP2040 (MAKER-NANO-RP2040), 1x Breadboard 8.5x5.5cm 400 holes (BD-BB-0508), 1x 40-Way 10cm Dupont Jumper Wire (WR-JW-4010MM), 1x Finger Adjust Preset 10K (RS-MP3386-10K), 2x LED 5mm Green (DS-LED-5NG), 2x LED 5mm Yellow (DS-LED-5NY), 2x LED 5mm Red (DS-LED-5NR), 1x DIY 4 Blades 56mm Motor Propeller Blue (HD-PROP-4B), 1x 3V Miniature Brush Motor with wire leads (MO-300CA-11440), 1x Transistor 2N2222 (TR-2N-2222), 10x Resistor 0.25W 5% 220R (RS-025W-220R), 1x LDR Small (SN-LDR-S), 1x Diode 1N4007 (DI-1N4007), 1x USB Micro B Cable (WR-USB-UB), 1x Resistor 0.25W 5% 10K (RS-025W-10K)
- Components used in "Getting Started With Maker Nano RP2040 And Blynk IoT": same list without the 10K resistor; the Grove WiFi 8266 used in every lesson is not in that table
- Product page packing list per variant: [NOT STATED] (did not extract)
- Getting Started doc lessons: 1 LED Blink, 2 Siren, 3 Digital Input, 4 Analog Input, 5 Light Dependent Resistor, 6 Temperature Sensor, 7 DC Motor, 8 Neopixel; projects: 1 Knight Rider, 2 Interactive Traffic Light, 3 Temperature Alarm, 4 Light Theremin
- Blynk IoT doc lessons: 1 Getting Connected, 2 Simple LED Control, 3 Push Button As Input, 4 Analog Input, 5 Temperature Sensor, 6 Neopixel Color, 7 Motor Speed Controller, 8 Going Mobile; Chapter 3 Projects has no content
- Blynk setup in the doc: create a Blynk account, new template "Maker Nano RP2040 IoT" (hardware Arduino, connection WiFi), add a device from the template, copy its Template ID / Device Name / Auth Token into the sketch
- Pins used by the lesson code: LED D2; buzzer pin 22; push button pin 20; potentiometer A0 (Getting Started) or A3 (Blynk); LDR A0; NeoPixels pin 11; DC motor PWM pin 2 through a 2N2222; Blynk-controlled LED 7; Knight Rider pins 16, 19, 17, 9, 8, 7, 6, 5, 4, 3
- Grove WiFi connection: Maker Port (code comment "Maker port [0, 1]"), Serial1 at 115200 baud
- Warranty: [NOT STATED]
- Dimensions, weight: [NOT STATED]

## Interfaces and compatibility
- Software: Arduino IDE with the arduino-pico board package (board "Cytron Maker Nano RP2040"); hold BOOT while plugging in for the first upload
- Libraries: Blynk by Volodymyr Shymanskyy 1.1.0, BlynkESP8266 (ESP8266_Lib.h, BlynkSimpleShieldEsp8266.h), Adafruit_NeoPixel, WS2812FX, pitches.h
- IoT platform: Blynk web dashboard and Blynk mobile app
- Grove WiFi 8266 plugs into a Maker Port through the JST-SH to Grove conversion cable
- Power: USB Micro B cable; no battery in the component lists
- Product page links: Maker Nano RP2040 datasheet, GitHub MAKER-NANO-RP2040, 3D CAD, tutorials (Blynk IoT, Grove gas sensor MQ9B, Maker Line)

## Use cases
- Getting started with Maker Nano RP2040 in the Arduino IDE (LED, buzzer, button, analog input, LDR, temperature, DC motor, NeoPixel)
- Getting started with Maker Nano RP2040 and Blynk IoT (LED control, push button, analog input, temperature chart, NeoPixel colour, motor speed, mobile dashboard)
- Classic projects: Knight Rider, Interactive Traffic Light, Temperature Alarm, Light Theremin

## Known limitations
- If communication with the Grove WiFi fails, the 3.3V supply is not enough to power the ESP8266; the doc says to connect its power to 5V instead
- Blynk code comment: do not send more than 10 values per second
- The Blynk doc's Chapter 3 Projects is empty
- The Getting Started doc's project objectives cite wrong lesson numbers, and its Light Theremin code calls noTone(8) while the buzzer is on pin 22
- The Blynk doc's NeoPixel lesson declares 30 pixels although the board has 2
- Wi-Fi credentials and the Blynk Template ID / Auth Token in the sketches must be replaced with your own
- Exact packing list per variant is not stated in the page text read

## Positioning (kept apart from specs)
- "Maker Nano RP2040 is created to simplify digital making and troubleshooting" (Getting Started doc)

## Price band
RM58.00–RM88.52 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-nano-rp2040-getting-started-kits

## Datasheet
https://docs.google.com/document/d/1yqR88btul39hZ77OgUMRrg-d0Z-e3xlgVlNHLoHSLzY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1T3FAROtD-uECHmBquAbhmKK9bxdzDWIQn_PhV93oKSo/edit

# Product fact sheets

## Product name
DIY Fire Detection and Suppression with Raspberry Pi Pico

## Aliases
PR-DIY-FIRE-PICO, DIY Fire Detection and Suppression with Raspberry Pi Pico, DIY Fire Detection Pico, Fire Detection and Suppression Pico Kit, Pico Fire Detection Kit

## What it is
A beginner project kit for building a fire detection and suppression system with a Raspberry Pi Pico, a flame sensor and a water pump, programmed in CircuitPython with the Thonny editor. When the flame sensor detects fire, the code runs the water pump for 5 seconds and then switches it off.

## Specs and functions
- Product code: PR-DIY-FIRE-PICO
- Controller: Raspberry Pi Pico
- Sensor: flame sensor (model: [NOT STATED])
- Actuator: water pump (model and voltage: [NOT STATED])
- Firmware: CircuitPython, written and uploaded with Thonny
- Behaviour: endless loop reading the flame sensor; on fire detected the water pump runs for 5 seconds, then switches off
- Flame sensor connection: GP3
- Water pump connection: motor terminal 1
- Full component list and quantities: [NOT STATED] (product cards did not render in the text read)
- CircuitPython libraries: [NOT STATED]
- Code listing: [NOT STATED] (video tutorial)
- Warranty: [NOT STATED]
- Dimensions, weight: [NOT STATED]

## Interfaces and compatibility
- Raspberry Pi Pico (product page links the Pico datasheet)
- Flame sensor on GP3
- Water pump on motor terminal 1 (a motor-driver terminal, not a Pico GPIO; board not named in the text read)
- Software: Thonny editor with CircuitPython; a video on getting started with Thonny is linked
- Guide: Cytron tutorial "DIY Fire Detection and Suppression with Raspberry Pi Pico" (Abdulrahman Alhamed, 08 Nov 2023)

## Use cases
- Build a fire detection and suppression system using a Raspberry Pi Pico, a flame sensor, and a water pump (quick video tutorial)
- Keep your surroundings safe from fire hazards (tutorial framing)

## Known limitations
- The pump runs for a fixed 5 seconds per detection
- Only two wiring facts are stated: flame sensor to GP3 and water pump to motor terminal 1
- The parts list, code and libraries are in the video and product cards, not in the text read
- Out of stock on my.cytron.io on 2026-10-19

## Positioning (kept apart from specs)
- "Quick and easy video tutorial" for a DIY fire detection and suppression system (tutorial excerpt)

## Price band
RM103.08 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-diy-fire-detection-suppression-raspberry-pi-pico

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/tutorial/diy-fire-detection-and-suppression-with-raspberry-pi-pico

# Product fact sheets

## Product name
MOTION:BIT

## Aliases
MOTION:BIT, MOTION-BIT, Motion:Bit, MOTIONBIT, MOTION:BIT for micro:bit, MOTION:BIT - Simplifying Motion Control with micro:bit

## What it is
A robotics and motion-control expansion board for the BBC micro:bit that drives brushed DC motors and 8 RC servos. It runs from an onboard 18650 Li-Ion battery holder (charged over micro USB) or an external 3.6–6 V input.

## Specs and functions
- Product code: MOTION-BIT (datasheet document title)
- Datasheet: Rev 1.0, February 2023 (spec table titled "Absolute Maximum Ratings")
- Power input voltage: 3.6 V min, 6 V max
- Power sources: 18650 Li-Ion battery holder; micro USB (charges the battery or powers the board, no data transmission); power input terminal for external 3.6V - 6V (external LiPo or 4x AA batteries)
- Analog input voltage: 0–3.3 V
- Total +3V3 output current (GPIO Breakout & Grove Ports): 200 mA max
- Total +5V output current: 300 mA max
- Maximum DC motor current: 1 A continuous; 1.5 A peak (< 5 seconds)
- DC motor channels: 4 (M1, M2, M3, M4) (MakeCode extension)
- Motor voltage at full speed is equal to power source voltage
- Servos: connectors for 8x RC servo motors; V+ voltage is equal to power source voltage
- Servo control in MakeCode: 0–180 degrees (500–2500 µs pulse, 50 Hz); disable servo sends no pulse
- Motor and servo outputs driven by a PCA9685 at I2C address 0x40 (MakeCode extension code)
- RGB LEDs: 2 user-programmable WS2812B RGB LEDs, connected to P8
- Ext. RGB LED connector for external WS2812B RGB LEDs, daisy-chained to the onboard RGB LEDs (Dout of RGB LED 1)
- GPIO status LEDs: on when the IO state is high
- Motor test buttons: motor runs at full speed
- Motor status LEDs: on when the motor is running
- Power/Charge LED: power on when powered; charge on while charging, off when full
- On/Off switch and Ext. On/Off switch header
- Motor driver IC: [NOT STATED]
- Buzzer: [NOT STATED]
- Dimensions: [NOT STATED] (drawing only)
- Protections (reverse polarity, over-current, thermal, battery): [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- micro:bit V1 and V2 (MakeCode extension README)
- micro:bit socket: plug in with the micro:bit LEDs facing out
- GPIO breakout, colour-coded GVS, 3.3V power per GPIO: P0, P1, P2, Button A, Button B, P9, P12, P13, P14, P15, P16
- Maker Ports: JST-SH 4-way, compatible with Qwiic, STEMMA QT and Grove (via conversion cable); datasheet: "These pins are available on Maker Ports: P0-P9, P1-P2, P2-P12"
- Maker Port (I2C): JST-SH 4-way, for I2C modules only
- I2C breakout: micro:bit I2C pins (P19 SCL, P20 SDA)
- P8: onboard RGB LEDs
- 5V Supply output for external sensors/modules
- Motor terminals: direction depends on polarity
- MakeCode extension: pxt-motionbit (block category "MOTION:BIT"), search "motionbit" or https://github.com/cytrontechnologies/pxt-motionbit
- MakeCode blocks: run motor (speed 0–255), brake motor, set servo position, disable servo, RGB pixel colour and brightness, external RGB pixels
- Python: [NOT STATED]

## Use cases
- Robots and motion-control projects with micro:bit ("simplifying robots & motion control projects making with micro:bit")
- Projects with mechanical movements using DC motors and servos
- Adding sensors and modules through the GPIO breakout and Maker Ports

## Known limitations
- Power input 3.6–6 V absolute maximum
- DC motor current 1 A continuous; 1.5 A peak only for < 5 seconds (per channel or total not stated)
- +5V output total 300 mA; +3V3 total 200 mA shared by GPIO breakout and Grove ports
- Analog input 0–3.3 V
- Servo V+ and motor full-speed voltage equal the power source voltage (no servo voltage selection)
- Micro USB is for power and charging only; no data transmission
- Maker Port (I2C) is for I2C modules only
- P8 is used by the RGB LEDs
- I2C address 0x40 is used by the motor/servo controller
- External On/Off switch works only when the onboard switch is Off
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring polarity

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Motion Control with micro:bit"
- "MOTION:BIT aims at simplifying robots & motion control projects making with micro:bit." (MakeCode extension README)
- "students can build projects with mechanical movements right away" (MakeCode extension README)

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-motionbit

## Datasheet
https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit

# Product fact sheets

## Product name
MOTION:BIT Pro

## Aliases
MOTION:BIT Pro, MOTION-BIT-PRO, Motion:Bit Pro, MOTIONBIT PRO, MOTION:BIT Pro for micro:bit, MOTION:BIT Pro - 12V Robotics Expansion Board for micro:bit

## What it is
A higher-voltage robotics and motion-control expansion board for the BBC micro:bit, powered from an external 7–12 V input, that drives brushed DC motors and 8 RC servos. It is programmed with the same MOTION:BIT MakeCode extension as MOTION:BIT.

## Specs and functions
- Product code: MOTION-BIT-PRO (datasheet document title)
- Datasheet: Rev 1.0, April 2024 (spec table titled "Absolute Maximum Ratings")
- Power input terminal: external 7V - 12V (external LiPo or 4x AA batteries)
- Power input voltage absolute maximum: 6 V min, 16 V max
- Analog input voltage: 0–3.3 V
- Total +3V3 output current (GPIO Breakout & Grove Ports): 200 mA max
- Maximum DC motor current: 3 A continuous; 5 A peak (< 5 seconds)
- DC motors controlled with the MOTION:BIT MakeCode extension (channels M1–M4 in the extension)
- Motor voltage at full speed is equal to power source voltage
- Servos: connectors for 8x RC servo motors
- RGB LEDs: user-programmable WS2812B RGB LEDs, connected to P8
- Ext. RGB LED connector for external WS2812B RGB LEDs, daisy-chained (Dout of RGB LED 1)
- GPIO status LEDs: on when the IO state is high
- Motor test buttons: motor runs at full speed
- Motor status LEDs: on when the motor is running
- On/Off switch and Ext. On/Off switch header
- Battery holder: none listed in the datasheet
- Motor driver IC: [NOT STATED]
- Buzzer: [NOT STATED]
- Dimensions: [NOT STATED] (drawing only)
- Protections (reverse polarity, over-current, thermal): [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- micro:bit versions: [NOT STATED]
- micro:bit socket: plug in with the micro:bit LEDs facing out
- GPIO breakout, colour-coded GVS, 3.3V power per GPIO: P0, P1, P2, Button A, Button B, P9, P12, P13, P14, P15, P16
- Maker Ports: JST-SH 4-way, compatible with Qwiic, STEMMA QT and Grove (via conversion cable); datasheet: "These pins are available on Maker Ports: P0-P9, P1-P2, P2-P12"
- Maker Port (I2C): JST-SH 4-way, for I2C modules only
- I2C breakout: micro:bit I2C pins (P19 SCL, P20 SDA)
- P8: onboard RGB LEDs
- 5V Supply output for external sensors/modules
- Motor terminals MA and MB: swapping the connection reverses the direction
- MakeCode: "Add MOTION:BIT Extension in MakeCode Editor to control the DC Motors and Servo Motors"; https://makecode.microbit.org/pkg/CytronTechnologies/pxt-motionbit (search "motionbit" in Extensions)
- Python: [NOT STATED]

## Use cases
- Controlling DC motors and servo motors with micro:bit ("Simplifying Motion Control with micro:bit")
- Adding sensors and modules through the GPIO breakout and Maker Ports

## Known limitations
- External input 7–12 V; absolute maximum 6–16 V
- DC motor current 3 A continuous; 5 A peak only for < 5 seconds (per channel or total not stated)
- +5V output total 3 A; +3V3 total 200 mA shared by GPIO breakout and Grove ports
- Analog input 0–3.3 V
- If the servo jumper is set to VIN, the servo voltage rating must be compatible with VIN, else it might damage the servo
- Motor full-speed voltage equals the power source voltage
- No battery holder listed in the datasheet
- Maker Port (I2C) is for I2C modules only
- P8 is used by the RGB LEDs
- External On/Off switch works only when the onboard switch is Off
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Motion Control with micro:bit"
- Datasheet header: "Simplifying Digital Making"

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
https://drive.google.com/file/d/17kkl6oBU0n-gQtyQ84ylxg2KX3E9Ma0_/view

## Source type
Datasheet

## Source link
https://drive.google.com/file/d/17kkl6oBU0n-gQtyQ84ylxg2KX3E9Ma0_/view

# Product fact sheets

## Product name
SUMO:BIT

## Aliases
SUMO:BIT, SUMOBIT, SUMO-BIT, SUMO BIT

## What it is
A sumo robot expansion board for the BBC micro:bit. It takes a LiPo battery, plugs in two external MD13S motor drivers, and provides opponent-sensor, edge-sensor, servo/RC, RGB LED, mode-switch and joystick connections.

## Specs and functions
- Product code: [NOT STATED]
- Power input voltage (LiPo battery): 7 V min, 25 V max; reverse polarity protection
- Vibration-proof on/off slide switch with MOSFET latching circuit; green power LED
- Battery voltage can be monitored programmatically (battery + terminal feeds an analog input)
- 2 × sockets for external MD13S motor driver boards (one per motor channel); MD13S can be removed and replaced
- With MD13S: 13 A continuous per channel, 30 A peak per channel (peak must not last longer than 10 seconds), motor PWM frequency up to 20 kHz
- 2 × motor current sensors, one for each motor channel
- 4 × red motor status LEDs (MLA/MRA forward, MLB/MRB backward)
- 5 × opponent sensor input ports, pulled up to 5V, with active-low status LEDs; voltage divider protects the micro:bit pins
- 2 × edge sensor input ports (analog sensors); voltage divider adjusts the output voltage
- 1 × general purpose port P2 (analog/digital) with active-low status LED; voltage divider reduces 5V to about 3V
- 2 × servo ports that can also be used as RC pins; servo voltage 5 V max
- 2 × WS2812B RGB LEDs, user programmable
- 1 × 4-way DIP switch for mode/tactic selection, up to 16 configurations (mode 0–15 in the MakeCode extension)
- USB-A port for wireless joystick connection; USB host output 5 V, 600 mA max
- +5V output maximum current (total): 600 mA
- Motor Alignment Module: potentiometer to balance left/right motor speed, test button runs the motors forward for 1 second, potentiometer indicator LEDs
- Firmware Update Module: USB-C port for firmware upload (not for programming) and boot button
- RP2040 co-processor at I2C address 0x09 controls motors, servos, RGB LEDs, mode switch, motor current and battery voltage (Cytron GitHub)
- Datasheet: Rev 1.0, December 2024
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- micro:bit plugs into a vertical edge-connector socket with the LED matrix facing up
- Supported micro:bit versions (V1/V2): [NOT STATED]
- micro:bit pin use (MakeCode extension source): P0 right edge sensor (analog), P1 left edge sensor (analog), P2 general-purpose port, P12 opponent Right, P13 opponent Front Right, P14 opponent Front Center, P15 opponent Front Left, P16 opponent Left, I2C to the RP2040 co-processor (address 0x09)
- Servos, RGB LEDs, motors, mode switch and battery voltage are controlled through the RP2040, not micro:bit pins
- Opponent sensors: Maker Object or other digital sensors; detection is LOW
- Edge sensors: Maker Reflect or any other analog sensors; edge detected when the reading is below the calibrated threshold
- Motor drivers: MD13S × 2, inserted from the bottom of the PCB
- MakeCode extension: pxt-sumobit (search "sumobit"), https://github.com/cytrontechnologies/pxt-sumobit, v1.3.6, approved on makecode.microbit.org
- Extension blocks: DC Motors, Servos, Mode, Motor Current, Opponent Sensors, Edge Sensors, RGB LED, Battery, Robot Kit (countdown, backoff, attack, search)
- MicroPython / Arduino: [NOT STATED]
- USB joystick and RC-receiver input blocks: [NOT STATED]

## Use cases
- Sumo robot projects and competitions with the BBC micro:bit, for learners of all ages
- Selecting a tactic or mode with the DIP switch before a match
- Wireless joystick control through the USB-A port
- SUMO:BIT Robot Kit builds

## Known limitations
- Battery input must stay within 7–25 V (LiPo)
- Motor ratings apply only with the MD13S motor drivers; the board drives no motors on its own
- Peak motor current 30 A per channel must not last longer than 10 seconds
- +5V output is 600 mA total, shared by servos and other 5V loads; servo voltage 5 V max
- USB-C port is for firmware updates only, not for programming the micro:bit
- micro:bit must be inserted with the LED matrix facing up; MD13S must be inserted from the bottom of the PCB
- P2 port signal passes through a voltage divider (5V to about 3V)
- Supported micro:bit version: [NOT STATED]

## Positioning (kept apart from specs)
- Cytron launch artwork: "Beginner Friendly, Competition Ready."
- "Start your sumo journey with the SUMO:BIT Robot Kit!"

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-sumo-bit

## Datasheet
https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-429/pdf/sumobit-expansion-board-for-microbit-datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-429/pdf/sumobit-expansion-board-for-microbit-datasheet.pdf

# Product fact sheets

## Product name
REKA:BIT

## Aliases
REKA:BIT, REKABIT, REKA-BIT, REKA BIT, REKA:BIT Simplifying Robotics with micro:bit

## What it is
A robotics expansion board for the BBC micro:bit with a built-in 2-channel DC motor driver, 4 servo ports, RGB LEDs and 6 Grove ports. It works with micro:bit V1 and V2.

## Specs and functions
- Product code: [NOT STATED]
- Power input voltage: 3.6 V min, 6 V max (DC jack)
- On/Off switch and power LED
- Low Voltage LED: blinks when the power input is below 3.6V; can be used as the low battery indicator
- Over Voltage LED: on when the power input is over 7V; power to the servos and DC motors is cut off
- 2-channel DC motor driver: 1 A continuous, 1.5 A peak (< 5 seconds) per motor; motor voltage at full speed equals the power source voltage
- Motor status LEDs: MxA forward, MxB backward
- Motor test buttons (M1A, M1B, M2A, M2B): run the motor at full speed without code
- 4 × RC servo ports; servo V+ equals the power source voltage
- WS2812B RGB LEDs, user programmable, connected to P8 (2 pixels in the MakeCode extension)
- 6 × Grove ports: 3 × analog input/digital IO, 2 × digital IO, 1 × I2C interface
- GPIO status LEDs on the Grove-port GPIOs (on when HIGH)
- Analog input voltage: 0–3.3 V
- Total +3V3 output current (Grove ports): 300 mA max
- Co-processor PIC16F1827 at I2C address 0x08 drives the motors and servos (Cytron GitHub)
- Datasheet: Rev 1.0, April 2021
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Works with micro:bit V1 & V2
- micro:bit pin use: P8 RGB LEDs; I2C to the co-processor (address 0x08) for motors, servos, power state, low-battery state, over-voltage state and input voltage
- Grove port to micro:bit pin map: [NOT STATED]
- Grove ports are 3.3 V; analog inputs 0–3.3 V
- MakeCode extension: pxt-rekabit, https://github.com/CytronTechnologies/pxt-rekabit, v1.2.3, approved on makecode.microbit.org
- Extension blocks: DC Motors (run 0–255, brake), Servos (0–180°, disable), RGB LED (clear, brightness, pixel colour)
- MakeCode Python: test program viewable in MakeCode Python mode
- REKA:BIT RBT Project Kit extension: https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit (RGB Stick, Big LED, soil moisture, ultrasonic)
- MicroPython library: [NOT STATED]

## Use cases
- Simplifying robots and projects with micro:bit
- Student projects with mechanical movement using DC motors and servos
- Adding sensors and modules through Grove ports
- REKA:BIT RBT Project Kit (STEAM and RBT projects for beginners)

## Known limitations
- Power input 3.6–6 V; above 7V the servo and DC motor power is cut off
- Below 3.6V only the Low Voltage LED blinks; no under-voltage cut-off is stated
- DC motor current 1 A continuous, 1.5 A peak for less than 5 seconds
- Servo V+ and motor voltage equal the power source voltage (not regulated)
- Grove analog input max 3.3 V; Grove +3V3 output 300 mA total
- Do not use I2C address 0x08 on the Grove I2C port (used by the co-processor)
- On micro:bit V1, P9 is shared with the LED matrix, so the P9 status LED stays lit
- Motor direction depends on wiring; swapping MxA and MxB reverses it
- Reverse-polarity protection: [NOT STATED]

## Positioning (kept apart from specs)
- "Simplifying Robotics with micro:bit"
- "REKA" comes from the Malay word "reka bentuk", which means design
- With the built-in dual-channel DC motor driver, 4x servo control and dedicated power input, students can build projects with mechanical movements right away

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-rekabit-simplifying-robotics-with-microbit

## Datasheet
https://docs.google.com/document/d/1axLhH-zaFDheOyz6gbXfYEysigGxpmMnRBC93SW-zR8/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1axLhH-zaFDheOyz6gbXfYEysigGxpmMnRBC93SW-zR8/edit

# Product fact sheets

## Product name
ZOOM:BIT Robot Car Kit for micro:bit

## Aliases
ZOOM:BIT, ZOOMBIT, ZOOM BIT, ZOOM:BIT Robot Car Kit, ZOOM:BIT Robot Car

## What it is
A robot car kit for the BBC micro:bit, built on a REKA:BIT controller board with a line sensor, an ultrasonic sensor, two LED headlights, two DC motors and a servo-driven head. It comes with a printed building and coding guide book and a line following track.

## Specs and functions
- Product code: [NOT STATED]
- Purchase options: ZOOM:BIT with micro:bit V2 included; ZOOM:BIT without micro:bit; ZOOM:BIT Classroom Pack (10x with micro:bit V2 included)
- Controller board: REKA:BIT (with or without micro:bit)
- Kit contents: Zoom Track, REKA:BIT (with or without micro:bit), Maker Line Sensor, Grove Cable x4, Ultrasonic Sensor, LED Module x2, DC Motor & Wheel x2, Screwdriver, Screw & Nut x4, Castor, Double-sided Tape x5, Power & Data Cable, Servo Motor, White Rivet x4, Black Rivet x8, AA Battery x4, Battery Holder; printed guide book
- Guide book: 9 chapters plus a bonus chapter (product page: "10-lesson guide book")
- Battery: AA Battery x4 in a battery holder
- REKA:BIT power input voltage: 3.6 – 6 V (absolute maximum ratings)
- REKA:BIT analog input voltage: 0 – 3.3 V
- REKA:BIT total +3V3 output current (Grove ports): 300 mA max
- DC motor current: 1 A continuous, 1.5 A peak (< 5 seconds)
- DC motor voltage at full speed and servo V+: equal to the power source voltage
- Low voltage LED blinks below 3.6 V; over voltage LED lights above 7 V and power to the servos and DC motors is cut off
- Drive motors: left = M1, right = M2 (REKA:BIT motor channels)
- Motor test buttons on REKA:BIT run a motor at full speed (MxA forward, MxB backward)
- Maker Line sensor: 5 IR sensors (S1–S5) with LED indicators, calibration button, line-colour switch ("DARK" for a black line); read on P1 (analog)
- Ultrasonic sensor: trigger P2, echo P12; MakeCode block returns 1 – 255 cm, 255 if over 255 cm or no echo
- Headlights (LED modules): left P13, right P15
- RGB LEDs: 2 x WS2812B on REKA:BIT, on P8, labelled "0" and "1"
- Head: 180 degree servo motor on a REKA:BIT servo port
- Motors and servos are controlled by the REKA:BIT co-processor over I2C (address 0x08)
- Power switch: slide OFF then ON to reset
- Warranty: 12 months

## Interfaces and compatibility
- micro:bit V1 and V2; V1 has no built-in speaker, so sound needs a Grove buzzer on Port P0:P1
- Sound expression and built-in speaker blocks are for micro:bit V2 only
- I2C port: guide book suggests adding a Grove OLED Display
- MakeCode extension: zoombit — https://github.com/cytrontechnologies/pxt-zoombit (search "zoombit" under Extensions)
- The zoombit extension loads the REKA:BIT extension (pxt-rekabit), whose blocks appear in the REKA:BIT category
- MakeCode Block, JavaScript and Python modes
- ZOOM:BIT blocks: headlights (set / toggle), move, turn, set motors speed (-255 to 255), brake, line detected on (far left / left / center / right / far right / all / none), line position (-100 to 100), ultrasonic distance (cm)
- WebUSB download needs the new Edge or Chrome browser and the latest micro:bit firmware
- Quick Start Guide in 5 languages

## Use cases
- Display text and animation
- Play simple melodies
- When dark, turn on headlights
- Move & turn on command
- Signal using RGB LEDs
- Control head movement/angle
- Detect and avoid obstacles
- Follow the line & stay on track
- Change from one mode to another
- Remote control (bonus chapter)
- ZOOM:BIT with HuskyLens (Cytron video content and workshops)

## Known limitations
- The micro:bit is not included in the "ZOOM:BIT without micro:bit" option
- micro:bit V1 has no built-in speaker; a Grove buzzer is needed for sound
- Pins used by the kit: P1 (Maker Line), P2 and P12 (ultrasonic), P13 and P15 (headlights), P8 (RGB LEDs), plus the I2C bus to the REKA:BIT co-processor
- Power input values are absolute maximum ratings: 3.6 – 6 V; over 7 V cuts power to the servos and DC motors
- DC motor current: 1 A continuous, 1.5 A peak for under 5 seconds
- Grove +3V3 total: 300 mA max
- Motor direction depends on the motor connection; if the wheels don't spin in the direction of the red arrows, correct the DC motor connections
- Motor test buttons run the motor at full speed without any code
- The Maker Line sensor needs calibration before line following, and again if the sensor height, the line or the background colour changes
- Ultrasonic block returns 255 when nothing is detected or the distance is over 255 cm
- The guide book does not state the battery voltage or chemistry
- The guide book does not mention Python; Python is through MakeCode's Python mode
- Assembly: wires face inwards with the notch facing outwards; clamp the exposed wire lead, not the insulator

## Positioning (kept apart from specs)
- "Looking for a solution to introduce robotics and coding to your kids?"
- "This kit comes with a step-by-step building guide written in simple language and a generous dose of graphics to help young learners to follow along."
- "You can easily program ZOOM:BIT using open-sourced Microsoft MakeCode Editor."
- Classroom Pack: "Save more with this Classroom Pack!"

## Price band
Cytron product page (www.cytron.io, read 2026-10-16): $62.50 offer price (12% off); currency and variant not stated on the page

## Product page
https://www.cytron.io/p-zoombit-robot-car-kit-for-microbit

## Datasheet
https://static.cytron.io/download/ZOOMBIT/ZOOMBIT-Quick-Start-Guide-Book-EN-v1.1-2022.pdf

## Source type
Datasheet

## Source link
https://static.cytron.io/download/ZOOMBIT/ZOOMBIT-Quick-Start-Guide-Book-EN-v1.1-2022.pdf

# Product fact sheets

## Product name
EDU:BIT Training & Project Kit for micro:bit

## Aliases
V-EDUBIT, EDUBIT, EDUBIT-NB, EDU:BIT, EDU BIT, EDU-BIT, EDU:BIT Training & Project Kit, EDU:BIT Classroom Pack

## What it is
A micro:bit training and project kit: a board with built-in modules (buzzer, sensors, LEDs, buttons, servo and DC motor ports) plus a guide book of 10+1 coding lessons, game accessories, a servo motor and a DC motor. It works with micro:bit V1 and V2.

## Specs and functions
- Product code: V-EDUBIT (board code EDUBIT; reseller EDUBIT-NB)
- 1x piezo buzzer with audio jack
- 1x sound sensor (micro:bit P1, analog)
- 1x potentiometer (micro:bit P2, analog)
- 1x IR sensor (micro:bit P8, digital)
- 4x programmable RGB LEDs (micro:bit P13)
- 3x big LEDs, traffic light: red P14, yellow P15, green P16
- 2x push buttons (in parallel with micro:bit buttons A and B)
- 3x servo ports and 2x DC motor ports, driven by a dedicated controller and power supply (PIC16F1937 co-processor at I2C address 0x08, Cytron GitHub)
- 1x I2C port (3.3V)
- Indicator LEDs for digital and analog IO pins; each feature and its micro:bit IO pin labelled on the board
- Modules can be broken off the board and reconnected with plug-and-play (Grove) cables
- Works out of the box: lights and melody on button press, no wiring needed
- Dimension: 157.50 mm x 124.50 mm x 19.00 mm
- Power input voltage / connector: [NOT STATED]
- Motor and servo current limits: [NOT STATED]
- Weight: [NOT STATED]
- Warranty: 12 months
- Packing list (with micro:bit V2): 1x EDU:BIT board, 1x micro:bit V2, 1x step-by-step guide book, 1x USB power and data cable, 2x game maps, 2x game accessories, 7x Grove cables, 1x servo motor, 1x DC motor, 1x pulley wheel, 1x fan blade
- Without micro:bit option: same contents minus the micro:bit
- Classroom Pack: 10 sets, each with micro:bit V2
- Guide book: 10 chapters + 1 bonus — Hello, World!; Rock, Paper, Scissors (Button Bit); Music (Music Bit); Win, Lose or Draw (Traffic Light Bit); IR Digital Dice / Snakes and Ladders (IR Bit); Tag, You're It (Potentio Bit); Applause (Sound Bit); Let's Take a Spin / Finger Twister (DC motor); Penalty Shoot-Out (servo); Mastermind (RGB Bit); Bonus: Simon Says with LEDs (radio)
- Guide book PDFs: English, Malay, Chinese, Tamil, Thai, Japanese, Hungarian, Italian, French, German, Korean, Spanish

## Interfaces and compatibility
- Works with micro:bit V1 & V2
- micro:bit pins used: P1 sound, P2 potentiometer, P8 IR, P13 RGB LEDs, P14/P15/P16 traffic light, I2C (co-processor 0x08) for servos S1–S3 and motors M1/M2
- Programmed with Microsoft MakeCode (blocks, JavaScript or Python mode) and the EDU:BIT extension pxt-edubit, https://github.com/CytronTechnologies/pxt-edubit (v1.15.0)
- Extension blocks: Sound Bit, Potentio Bit, IR Bit, RGB Bit, Traffic Light Bit, Motors & Servos (motor speed 0–255, servo 0–180°); Music Bit and Button Bit use the built-in Music and Input blocks
- Resource Hub with chapter resources and sample code: http://link.cytron.io/edubit-resource-hub
- Out-of-the-box demo code: https://link.cytron.io/edubit-demo-code
- Grove WiFi 8266 tutorial listed on the product page
- MicroPython library: [NOT STATED]

## Use cases
- Beginner micro:bit kit for STEAM and coding
- 10+1 hands-on coding lessons, each built around a classic childhood game, with a challenge at the end of each chapter
- Training kit that works with no wiring
- Custom projects using the broken-off modules
- Projects with up to 3 servo motors and 2 DC motors while playing music
- AI projects with Teachable Machine (tutorial series ch.1–6: object sorting, face recognition door, gesture-controlled fan, colour-controlled motor, object counter)
- Classroom teaching (Classroom Pack of 10)

## Known limitations
- The default EDU:BIT MakeCode extension is not compatible with Bluetooth (NeoPixel/RGB dependencies); a modified version is provided in the Teachable Machine Chapter 1 tutorial
- P1, P2, P8, P13, P14, P15 and P16 are used by the onboard modules
- Do not use I2C address 0x08 on the I2C port (used by the co-processor)
- Servos and DC motors can only be driven through the co-processor (extension blocks), not directly from micro:bit pins
- The extension resets the micro:bit when the EDU:BIT power is switched on
- RGB LED default brightness in the extension is 25 (of 255)
- The kit without micro:bit does not include a micro:bit board
- Power input voltage range, battery option and protection thresholds: [NOT STATED]

## Positioning (kept apart from specs)
- EDU:BIT was 575% funded on Kickstarter on Oct 22, 2020
- Specially designed to encourage kids to explore STEAM and learn coding
- "Cannot control servo motor and play music at the same time on your micro:bit? Servo motor refuses to move correctly? ... EDU:BIT takes care of these issues with its dedicated controller and power supply."
- Name-writing space on the board
- Guide books translated by volunteers into many languages

## Price band
RM156.00–RM2,390.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-edubit-training-and-project-kits-for-microbit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-edubit-training-and-project-kits-for-microbit

# Product fact sheets

## Product name
Grove WiFi 8266 - IoT for micro:bit and beyond — GRV-WIFI-8266

## Aliases
GRV-WIFI-8266, Grove WiFi 8266, Grove WiFi 8266 - IoT for micro:bit and beyond, Grove WiFi 8266 IoT for micro:bit & Beyond, Cytron Grove WiFi 8266, ESP8266 WiFi Grove Module, Grove ESP8266

## What it is
A Wi-Fi module board carrying an Ai-Thinker ESP-12F (ESP8266) module, connected to a host controller through a 4-pin Grove port (GND, VCC, RX, TX) as a UART serial link. It ships with Cytron's build of the Espressif ESP-AT (AT-command) firmware and has a reset button, a boot button, a power LED and a breakout of all ESP-12F pins.

## Specs and functions
- Wi-Fi module: Ai-Thinker ESP-12F, powered by the ESP8266 (datasheet)
- Power input voltage (VCC): 3.0 V min, 6.0 V max (datasheet)
- Digital input voltage (Rx & GPIOs): low level −0.3 V min to 0.8 V max; high level 2.5 V min to 3.6 V max (datasheet)
- Digital output voltage (Tx & GPIOs): low level 0 V min to 0.4 V max; high level 2.6 V min to 3.3 V max (datasheet)
- Operating temperature: −20 °C min, 85 °C max (datasheet)
- Reset button: resets the ESP8266 (datasheet)
- Boot button: press and hold while resetting to enter bootloader mode, used to update firmware or program the ESP8266 (datasheet)
- Power LED: on when powered up (datasheet)
- ESP-12F pins breakout: all module pins broken out; pinout printed on the bottom of the PCB (datasheet)
- Preloaded firmware: Cytron_ESP-12F_WROOM-02_AT_Firmware V2.2.0, compiled by Cytron from Espressif ESP-AT source (Cytron GitHub esp-at-binaries)
- AT command UART in Cytron firmware: UART0 GPIO3 (RX) / GPIO1 (TX); log output UART1 GPIO2 (TX) (Cytron GitHub esp-at-binaries)
- UART baud used by Cytron software: 115200 (Cytron GitHub)
- Supply current: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Weight: [NOT STATED]
- Flash size, RF standard, antenna: [NOT STATED] by Cytron sources
- Datasheet: GROVE WIFI 8266 Datasheet, Rev 1.0, August 2021

## Interfaces and compatibility
- Grove port, 4 pins: GND (ground); VCC (positive supply, 3 V–6 V); RX (serial Rx of the ESP8266, connect to host's Tx); TX (serial Tx of the ESP8266, connect to host's Rx) (datasheet)
- Host boards used by Cytron software: micro:bit (MakeCode extension, PXT target microbit); Maker Pi Pico and Maker Pi RP2040 (CircuitPython IoT examples) (Cytron GitHub)
- MakeCode extension: pxt-esp8266, version 2.0.1, block category "ESP8266 WiFi", tested with Espressif ESP-AT firmware v2.2.0; default init Tx P16, Rx P15, baud 115200; blocks for WiFi connect, ThingSpeak upload, Blynk read/write, internet time (SNTP) and Telegram message; https://github.com/CytronTechnologies/pxt-esp8266 (Cytron GitHub)
- CircuitPython examples: Adafruit libraries adafruit_espatcontrol, adafruit_requests, adafruit_minimqtt, adafruit_io; UART TX GP16 / RX GP17 at 115200; examples for Adafruit IO, Blynk, simple test, Telegram, ThingSpeak; requires ESP-AT firmware v2.2.0 and above; https://github.com/CytronTechnologies/MAKER-PI-PICO/tree/main/Example%20Code/CircuitPython/IoT (Cytron GitHub)
- ESP-AT firmware binaries and update notes: https://github.com/CytronTechnologies/esp-at-binaries (Cytron GitHub)
- AT command reference named by Cytron: Espressif ESP-AT User Guide, release v2.2.0.0 for ESP8266 (Cytron GitHub)
- Warranty: 12 months (product page)

## Use cases
- Enable a micro:bit to send and receive data over Wi-Fi with MakeCode blocks (Cytron GitHub)
- Upload sensor data to ThingSpeak from micro:bit or Raspberry Pi Pico (Cytron GitHub)
- Read and write Blynk virtual pins from micro:bit or Raspberry Pi Pico (Cytron GitHub)
- Send Telegram bot messages from micro:bit or Raspberry Pi Pico (Cytron GitHub)
- Get internet time (SNTP) on micro:bit (Cytron GitHub)
- Send data to Adafruit IO from Maker Pi Pico / Maker Pi RP2040 with CircuitPython (Cytron GitHub)

## Known limitations
- Serial RX/GPIO input high level is 2.5–3.6 V max and TX output high is 2.6–3.3 V; the logic is 3.3 V level even though VCC accepts 3–6 V (datasheet)
- The module is used as an AT-command modem over UART; Espressif ESP-AT v2.x commands are not fully compatible with the legacy NONOS-AT v1.7.x firmware (Cytron GitHub esp-at-binaries)
- Cytron's firmware keeps AT on GPIO1/GPIO3; stock Espressif ESP-AT v2.0.0 and above uses GPIO13/GPIO15 for AT, so reflashing with stock Espressif binaries moves the AT UART off the Grove RX/TX pins (Cytron GitHub esp-at-binaries)
- ThingSpeak data can only be uploaded every 15 seconds (Cytron GitHub pxt-esp8266)
- The Cytron ESP-01S AT firmware (1 MB flash) does not support OTA update and is not the binary for this module; this module uses the ESP-12F/WROOM-02 binary for 2 MB flash or above (Cytron GitHub esp-at-binaries)
- Supply current, dimensions, weight, flash size and RF specification are not stated in the Cytron datasheet
- The GitHub firmware-update procedures cover the ESP-01S and the ESP8266 WiFi Shield; no Grove-module-specific procedure is given (Cytron GitHub esp-at-binaries)

## Positioning (kept apart from specs)
- Product page name: "Grove WiFi 8266 - IoT for micro:bit and beyond" (product page)

## Price band
RM27.72 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-grove-wifi-8266-iot-for-microbit-and-beyond

## Datasheet
https://docs.google.com/document/d/1ub3WuRrp1F8QijoHCDjOez6SC1mtG5pQglhiPdeB12k/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1ub3WuRrp1F8QijoHCDjOez6SC1mtG5pQglhiPdeB12k/edit

# Product fact sheets

## Product name
REKA:BIT RBT Project Kit

## Aliases
REKA:BIT RBT Project Kit, REKA:BIT RBT Project Kits, REKABIT RBT Project Kit, REKA:BIT RBT Project Bundle, RBT Project Kit, Kit Projek RBT REKA:BIT, V-KIT-REKABIT-RBT, KIT-REKABIT-RBT, KIT-REKABIT-RBT-NB

## What it is
A micro:bit project kit for the Malaysian RBT Year 5 and Year 6 syllabus, built on the REKA:BIT expansion board with a servo, RGB stick, two Big LED modules, a Maker Soil Moisture Sensor, a submersible water pump, an ultrasonic sensor and two DC motors with wheels. It comes with a printed Quick Start Guide covering 5 projects and 7 components, programmed in MakeCode with the REKA:BIT RBT Project Kit extension.

## Specs and functions
- Product code: V-KIT-REKABIT-RBT (product page); kit codes KIT-REKABIT-RBT (with micro:bit V2) and KIT-REKABIT-RBT-NB (without micro:bit)
- Purchase options: with micro:bit V2 included; without micro:bit
- Controller board: REKA:BIT (see the REKA:BIT entry for board specs)
- Kit contents (with micro:bit): 1x micro:bit v2, 1x REKA:BIT expansion board, 1x USB power and data cable, 1x quick start guide book, 1x Maker Soil Moisture Sensor, 1x RGB LED Stick, 1x Ultrasonic sensor, 2x 10mm LED module, 2x DC motor with wheel, 1x Micro servo motor, 1x Submersible Water Pump, 4x Grove to female header cable, 1x 4xAA battery holder with DC plug, 4x AA battery, 1x Castor, 1x Mini screwdriver, double-sided tapes
- Without-micro:bit option: same contents minus the micro:bit
- Guide book list: REKA:BIT (with or without micro:bit), micro servo motor, RGB board, soil moisture sensor, Big LED module x2, water pump, ultrasonic sensor, USB cable (power & data), Grove cable x4, AA battery x4, battery holder, ball caster, DC motor with wheels x2, mini screwdriver, adhesive tape x5
- Guide book: Quick Start Guide, 5 projects + 7 components; softcopies in English, Malay, Chinese (Spanish on the resource hub)
- Projects: 1 Boom Barrier Gate; 2 Interactive Robot; 3 Auto Plant Watering Robot (two code versions, 3a and 3b); 4 Coin-Eating Robot; 5 Mobile Robot Car
- RGB stick: 8 LEDs labelled 0 to 7; brightness 0 to 255
- Servo: channels S1 to S4; angle 0 to 180 degrees; disable-servo block stops jitter
- Water pump: motor channel M1 or M2; speed 0 to 255; works in either direction
- DC motor: channel M1 or M2; speed 0 to 255 (relative value)
- Ultrasonic block: 1 to 300 cm; returns 300 when out of range or no echo
- Soil moisture block: 0 to 1023; reading rises as the soil dries
- Battery: 4x AA in a battery holder with DC plug
- Power switch: slide OFF then ON to restart
- Age: 10+; Syllabus: RBT Y5&Y6; Platform: micro:bit
- Warranty: 12 months (manufacturing defects; wear and tear and misuse excluded)

## Interfaces and compatibility
- MakeCode extension: pxt-rekabit-rbt-project-kit (search "rekabit rbt project") — https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit ; it loads the REKA:BIT extension (pxt-rekabit) with it
- Block categories: RGB Stick, Big LED, Soil Moisture, Ultrasonic (plus REKA:BIT motor and servo blocks)
- RGB stick and Big LED pin choices: P0, P1, P2, P13, P15 (README examples: RGB stick P0, Big LED P13)
- Soil moisture pin choices: P0, P1, P2 (README example P2; Project 3 uses port P2:P12)
- Ultrasonic Trig/Echo pairs: P0/P1, P1/P9, P2/P12, P13/P14, P15/P16 (README example Trig P2, Echo P12)
- Water pump: MOTOR terminal (Project 3: motor terminal 2)
- Mobile Robot Car: left wheel MOTOR 1, right wheel MOTOR 2
- Servo: REKA:BIT servo terminal S1 to S4 (wire labels s = signal, +, -)
- micro:bit V1 and V2 (V1 has no built-in buzzer; add a Grove Buzzer module)
- MakeCode Blocks, JavaScript and Python modes; MakeCode Offline App supported
- WebUSB download needs the latest Edge or Chrome; otherwise drag the .hex file to the MICROBIT drive
- Resource hub: https://rekabit-rbt-hub.cytron.io/ (project videos, sample code, printable A4 templates)

## Use cases
- Boom Barrier Gate (servo + RGB stick)
- Interactive Robot (two Big LEDs + servo)
- Auto Plant Watering Robot (soil moisture sensor + water pump)
- Coin-Eating Robot (servo + ultrasonic sensor)
- Mobile Robot Car (two DC motors, ultrasonic sensor, LED headlights, RGB stick)
- RBT Year 5 and Year 6 classroom projects

## Known limitations
- The micro:bit is not included in the "without micro:bit" option
- micro:bit V1 has no built-in piezo buzzer; a Grove Buzzer module is needed for sound
- The pin set in a block must match the REKA:BIT port the module is plugged into
- RGB Stick and Ultrasonic blocks need their init block at the start of every program
- Ultrasonic block returns 300 when nothing is detected
- The soil moisture threshold (README example 550) is an example, not a calibrated value
- Disable an unused servo to prevent jitter
- The pump and DC motor pages in the guide carry a warning symbol
- All electrical limits are the REKA:BIT board's (3.6 to 6 V input; 1 A continuous / 1.5 A peak per motor; 300 mA Grove 3V3; over 7 V cuts motor and servo power)
- Cardboard, hot glue, Blu Tack, plastic container and steel hanger used in the projects are not included
- New MakeCode extensions may need an internet connection to compile even in the offline app
- The guide's per-project wiring is shown in diagrams; port labels for the RGB stick, Big LEDs, ultrasonic sensor and servo in each project are not stated in text

## Positioning (kept apart from specs)
- "with the aim to lower the learning curve for beginners who wants to build STEAM (and RBT) projects with micro:bit"
- Hardcopy Quick Start Guide plus online resources with example code and a step-by-step building video per project
- For RBT Y5 and Y6 (Reka Bentuk dan Teknologi Tahun 5 & 6)

## Price band
RM219.00 to RM295.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-rekabit-rbt-project-kits

## Datasheet
https://static.cytron.io/download/REKABIT-RBT-Project-Kit/REKABIT-RBT-Project-Kit-Quick-Start-Guide-BM-v1.0.pdf

## Source type
Datasheet

## Source link
https://static.cytron.io/download/REKABIT-RBT-Project-Kit/REKABIT-RBT-Project-Kit-Quick-Start-Guide-BM-v1.0.pdf

# Product fact sheets

## Product name
Auto Plant Watering Kit for micro:bit

## Aliases
Auto Plant Watering Kit for micro:bit, Auto Plant Watering Kit, RBT Auto Plant Watering Kit, RBT Automatic Plant Watering Kit, APW Kit, RBT APW, V-KIT-RBT-APW, KIT-RBT-APW

## What it is
A micro:bit lesson kit that builds an automatic plant-watering system: a Maker Soil Moisture Sensor reads the soil, a REKA:BIT runs a submersible pump when the soil is dry, and a micro servo aims the water pipe. It comes with a printed five-lesson guide; an IoT option adds a Grove WiFi 8266 and follows a separate Cytron Blynk IoT tutorial.

## Specs and functions
- Product code: V-KIT-RBT-APW
- Purchase options: standard / IoT version, each with micro:bit or without micro:bit
- Controller board: REKA:BIT (see the REKA:BIT entry for board specs)
- Kit contents (with micro:bit): 1x Lesson guide (English), 1x Maker Soil Moisture Sensor, 1x REKA:BIT (with micro:bit V2), 1x Micro Submersible Water Pump DC 3V-5V with Pipe, 1x Analog Micro Servo 9g (3V-6V) with horns and screws, 1x Grove 4 Pin Buckled 50cm Cable, 1x Servo Male-Female Extension Cable 30cm, 1x 4xAA battery holder with DC plug, 4x PKCELL Heavy Duty AA Battery, 1x Tiny Phillips Screwdriver, 2x Popsicle stick, 3x Cable Ties, 2x Double Sided Tapes
- IoT version: adds 1x Grove WiFi 8266
- Without-micro:bit options: REKA:BIT without micro:bit
- Lesson guide: "Auto Plant Watering Kit for micro:bit", April 2022, by Goh Hao Zhen & Cheryl Ng; softcopies in English, Malay, Chinese, Thai
- Lessons: 1 Hello! (micro:bit + MakeCode); 2 What's the Soil Moisture Level?; 3 Dry? Moist? Or Wet?; 4 Water the Plant (pump when dry); 5 Servo Motor, Direct the Pipe!; Additional Activity 1 visualise soil moisture on the LED matrix; Additional Activity 2 melodies
- Soil moisture reading: higher when the probe is dry, lower in water; the threshold is calculated by the student from three recorded readings (no fixed number)
- Lesson 4: pump runs for 5 seconds when the reading is higher than the threshold
- Lesson 5: servo sweeps 30 to 150 degrees while the pump runs
- Lesson 3 indication: REKA:BIT RGB LEDs green = moist, red = dry; micro:bit shows a smiley or sad face
- Water pump: DC 3V-5V, with pipe
- Servo: analog micro servo 9g, 3V-6V
- Battery: 4x AA in a holder with DC plug, into the REKA:BIT power jack
- Warranty: 12 months

## Interfaces and compatibility
- Maker Soil Moisture Sensor: REKA:BIT Grove port P2:P12 (50 cm Grove cable); read on analog pin P2; probe inserted up to the white line
- Water pump: MOTOR 2 terminal, black wire to M2B, red wire to M2A
- Servo: servo port S1 via the 30 cm extension cable (port pins White = S signal, Red = +, Black = -; servo lead to extension Orange-White, Red-Red, Brown-Black)
- Battery holder: REKA:BIT power jack
- Grove buzzer for micro:bit V1: port P0:P1
- MakeCode extension: rekabit (adds REKA:BIT and Neopixel drawers)
- MakeCode editor: https://makecode.microbit.org ; WebUSB one-click download needs the new Edge or Chrome and the latest micro:bit firmware
- micro:bit V1 and V2 (V2 has the built-in speaker used in Additional Activity 2)
- IoT version: Cytron tutorial "RBT Automatic Plant Watering IoT Project Using Blynk IoT" — https://my.cytron.io/tutorial/rbt-automatic-plant-watering-iot-project-using-blynk-iot
- Sample code: https://link.cytron.io/auto-plant-wateringproject-code ; project ideas: https://link.cytron.io/apw-projects

## Use cases
- Display soil moisture level on the micro:bit
- Classify soil as dry, moist or wet
- Water the plant automatically when the soil is dry
- Direct the water pipe with a servo motor
- Visualise soil moisture as a bar graph on the LED matrix
- Play melodies and sound notifications
- IoT monitoring with Blynk IoT (IoT version)

## Known limitations
- The micro:bit is not included in the "without micro:bit" options
- The step-by-step guide for the IoT project is not included in the booklet
- A higher sensor reading means drier soil; the pump trigger is reading higher than threshold
- No fixed dry/moist/wet values are given; each plant needs its own threshold
- Do not wet the Maker Soil Moisture Sensor's exposed part or the REKA:BIT; it risks damaging electronic components on the board
- micro:bit V1 has no built-in speaker; a Grove buzzer on P0:P1 is needed for sound
- Pins taken: P2 (P2:P12 port), MOTOR 2, S1, and P0:P1 if a buzzer is added
- When clamping the pump wires, clamp the exposed wire lead, not the insulator
- Electrical limits are the REKA:BIT board's (3.6 to 6 V input; motor and servo rails equal the battery voltage; over 7 V cuts motor and servo power)
- The booklet gives no battery voltage figure
- Plant, pot and water container are not included

## Positioning (kept apart from specs)
- Lesson Guide offered as a free PDF in English, Malay, Chinese and Thai
- Standard and IoT versions, each with or without the micro:bit
- Same sensor, pump and servo combination as Project 3 of the REKA:BIT RBT Project Kit

## Price band
RM108.00 to RM214.62 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-auto-plant-watering-kit-for-microbit

## Datasheet
https://static.cytron.io/download/KIT-RBT-APW/RBT_APW_KIT_Booklet_English_v1.pdf

## Source type
Datasheet

## Source link
https://static.cytron.io/download/KIT-RBT-APW/RBT_APW_KIT_Booklet_English_v1.pdf

# Product fact sheets

## Product name
BEETLE:BIT Gripper Robot Car Kit for micro:bit

## Aliases
BEETLE:BIT, BEETLEBIT, BEETLE BIT, V-BEETLEBIT, BeetleBit, BEETLE:BIT Gripper Robot Car Kit, BEETLE:BIT Gripper Robot

## What it is
An educational gripper robot car kit for the BBC micro:bit, built on the REKA:BIT expansion board with two TT motors, a front servo gripper, an ultrasonic sensor and a Maker Line sensor. It comes with a 7-chapter booklet, a printed line track and an online Resource Hub with chapter code.

## Specs and functions
- Product code: V-BEETLEBIT
- Purchase options: with micro:bit / without micro:bit / Accessories Kit only, each with battery or without battery
- Microcontroller: BBC micro:bit (V2 in the "with micro:bit" option)
- Controller board: REKA:BIT (see the REKA:BIT fact sheet; not re-documented here)
- Motors: 2x DC gear motors with wheels (2x TT motor with 15cm wires and wheel kit)
- Gripper: non-copper PCB gripper (Robo Grip PCB with accessories, called "Robo Grip Mini" on the Resource Hub) driven by 1x TS90A micro servo
- Sensors: infrared line tracking (Maker Line), ultrasonic obstacle avoidance (Ultrasonic 3V3)
- Power: 4x AA batteries in a 4xAA battery holder with DC jack
- Control: Autonomous Mode or micro:bit RC Mode (additional micro:bit not included)
- Chassis: non-copper PCB (2x Robo Base, PCB only); no soldering
- Programming: MakeCode
- Packing list (with micro:bit, with battery): 1x BBC micro:bit V2, 1x REKA:BIT, 1x Dual Output Cable USB-A to 2.1mm DC barrel & Micro USB, 1x 4xAA battery holder with DC jack, 1x Ultrasonic 3V3, 1x Maker Line, 4x AA battery, 2x TT motor with 15cm wires and wheel kit, 1x TS90A micro servo, 1x BEETLE:BIT Booklet, 1x BEETLE:BIT Track, 1x Accessories Kit
- Accessories Kit: bracket for ultrasonic HC-SR04, W420 steel ball castor, 2x TT motor bracket, 2x Robo Base (PCB only), 3x Grove 4-pin buckled to female cable, M3 PCB stands 40/20/10/5mm, 14x M3 nut, 14x M3x6 screw, Velcro set, 4x M3x10 bolt, 1x Robo Grip PCB with accessories, 1x ping pong ball
- Booklet: "202602 BEETLEBIT Quick Start Guide.pdf" (English), 7 chapters plus a Setup Guide and Bonus activities
- Chapters: Setup Guide (build BEETLE:BIT); 1 The Beetle's Brain (micro:bit Basics); 2 How the Beetle Moves (TT Motors); 3 The Beetle's Claw (Servo Gripper); 4 The Beetle's Eyes (Ultrasonic Sensor); 5 The Beetle Senses (Line Following); 6 Teaching the Beetle to Decide; 7 Coordinated Actions (Line + Grab); Bonus 1 Control BeetleBit Using a Controller; Bonus 2 BEETLE:BIT Input–Output Challenge
- Gripper angles in Cytron's chapter code: Chapter 3 toggles 0 and 180; Chapters 6 and 7 use 120 = open, 0 = closed, then disable the servo after a pause
- Drive speeds in Cytron's chapter code: 128 for move/turn; obstacle thresholds: ultrasonic < 10 = stop, < 20 = slow
- Bonus 1 RC mode: micro:bit radio group 1; numbers 0–5 = forward, backward, turn left, turn right, toggle gripper, brake; remote is a second micro:bit
- Warranty: 12 months (1 year for manufacturing defects; wear and tear, misuse, abuse or improper maintenance not covered; troubleshooting, repair and testing take 7 working days from receipt)
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Age range: [NOT STATED]

## Interfaces and compatibility
- Left drive motor: REKA:BIT M1; right drive motor: REKA:BIT M2
- Gripper servo: REKA:BIT servo port S1
- Maker Line sensor: micro:bit P1 (analog)
- Ultrasonic sensor: trigger P2, echo P12
- RGB LEDs on REKA:BIT: P8 (not used by the chapter code)
- Motors and servo are driven over I2C by the REKA:BIT co-processor (address 0x08)
- Grove port labels used for the sensor cables: [NOT STATED]
- MakeCode extension: pxt-zoombit v0.1.1 (https://github.com/cytrontechnologies/pxt-zoombit), which loads pxt-rekabit; the product page names the extension as pxt-rekabit "BEETLE:BIT (ZOOM:BIT) Extension"
- MakeCode blocks, JavaScript and Python modes; MakeCode Offline App available
- micro:bit V2 is included in the "with micro:bit" option; RC mode needs a second micro:bit
- Related Cytron tutorials: colour detection bot using HuskyLens; line following robot car using motionbit; colour detection robot using TCS3200; Chapter 1: Setting Up Beetle:Bit with Huskylens 2
- MicroPython library: [NOT STATED]

## Use cases
- Display text and animation on the LED matrix and download a program
- Control BEETLE:BIT to move around with the TT motors
- Open and close the gripper with the servo
- Detect obstacles using an ultrasonic sensor
- Follow a line using the Maker Line sensor
- Make decisions and perform a complete task on its own
- Perform several actions in sequence (line following plus grabbing)
- Control BeetleBit using a controller (second micro:bit over radio)
- Input–output challenge
- Stepping stone for learners who have mastered ZOOM:BIT, Pikabot, BocoBot or OjanBot

## Known limitations
- The micro:bit is not included in the "without micro:bit" and "Accessories Kit only" options
- RC mode needs an additional micro:bit, which is not included
- Batteries are not included in the "without battery" options
- No kit datasheet; the booklet PDF is image-only (223 MB) and its text could not be read; chapter facts come from the Resource Hub and published code
- Pins used by the kit: P1 (Maker Line), P2 and P12 (ultrasonic), P8 (RGB LEDs), I2C to the REKA:BIT co-processor; servo on S1; motors on M1/M2
- Controller limits apply from REKA:BIT: 3.6–6 V input, 1 A continuous / 1.5 A peak per motor, 300 mA total on Grove +3V3, motor and servo power cut above 7 V
- All Bonus 1 programs use radio group 1, so two kits in the same room interfere unless the group is changed
- Chapter 3 Challenge uses the microphone (micro:bit V2 only)
- Ultrasonic block returns 255 when nothing is detected or the distance is over 255 cm
- No Cytron GitHub extension named "beetlebit" exists; use zoombit
- Battery chemistry, run time, dimensions, weight and age range are not stated

## Positioning (kept apart from specs)
- "Hands-on educational robotics kit"
- "Stepping stone... for those who have mastered ZOOM:BIT, Pikabot, BocoBot, or OjanBot"
- "Mobile manipulator: configurable chassis, dual TT motors, front-mounted servo gripper, ultrasonic distance sensor, line-following sensor"
- Resource Hub: a learning site for beginners in basic robotics covering building, coding and experimenting with a mobile manipulation robot

## Price band
RM99.80–RM326.45 across the options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-beetlebit-gripper-robot-car-kit-for-microbit

## Datasheet
https://drive.google.com/file/d/18ZOwcWVUn0xsEVdcUNOMDvZKf5haVmz5/view

## Source type
Website

## Source link
https://beetlebit-hub.cytron.io/

# Product fact sheets

## Product name
STRIKER:BIT Soccer Competition Kit

## Aliases
STRIKER:BIT, STRIKERBIT, STRIKER BIT, V-STRIKERBIT, StrikerBit, STRIKER:BIT Soccer Kit, PM-GAME-STRIKER

## What it is
A classroom robot-soccer competition kit for the BBC micro:bit: four 2-wheel-drive robots built on Robobase Mini PCB chassis with a MOTION:BIT, a servo shooter and Joystick:bit remote control, plus a game field, barrier, goal posts, props and scoring sheets. A Basic Kit option contains one robot set.

## Specs and functions
- Product code: V-STRIKERBIT (scoring sheet game code: PM-GAME-STRIKER)
- Purchase options: Complete Kit / Basic Kit, each with battery or without battery
- Microcontroller: BBC micro:bit (micro:bit Junior Kit V2)
- Controller board: MOTION:BIT (see the MOTION:BIT fact sheet; not re-documented here)
- Motors: 2x DC gear motors with wheels per robot
- Shooter mechanism: non-copper PCB + 3D printed part with servo (Robo Grip Mini Basic Bundle; 8x 3D printed grippers in the Complete Kit)
- Power: 1x 3.7V 2200mAh 18650 Li-Ion with button top per robot
- Control: micro:bit Joystick:bit (Joystick:bit V2 Kit)
- Chassis: non-copper PCB (Robobase Mini kit for 2WD Robot); no soldering
- Programming: MakeCode
- Learning guide: 7-chapter learning guidebook (STRIKER:BIT booklet, "20260606 STRIKERBIT Booklet (MAIN).pdf"); 4-step workflow
- Packing list (Complete Kit, with batteries): 4x Robo Grip Mini Basic Bundle, 4x Robobase Mini kit for 2WD Robot, 4x micro:bit Junior Kit (V2), 4x micro servos, 4x motion:bit, 4x USB Micro B cables, 8x 3D printed grippers, 4x ping pong balls, 4x STRIKER:BIT booklet, 4x Joystick:bit V2 Kit, Velcro sets, whistle, 12x 3/4" PVC conduit pipe (34 cm), 4x elbow joints, 8x sockets, 2x goal post stickers, yellow card, red card, gameplay instruction & scoring sheet, 2x pizza box packing 315x220x70mm (goal post), gamefield map, 4x AAA battery sets, 4x 18650 battery
- Packing list (Basic Kit): 1 robot set: 1x Robo Grip Mini Basic Bundle, 1x Robobase Mini 2WD, 2x micro:bit Junior Kit V2, 1x micro servo (rest of the list not stated)
- Scoring sheet ("STRIKER:BIT SOCCER MATCH SCORE SHEET", 11 June 2026): fields for Competition / Event / Round, Date, Team A and Team B names; goals ticked per goal; yellow cards max 2 per robot; red cards max 2 per team; final score = total number of goals; signatures of Team A captain, Team B captain and Head of Referee
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Field size: [NOT STATED]
- Age range: [NOT STATED]

## Interfaces and compatibility
- Robot: micro:bit on MOTION:BIT; 2 DC motors on MOTION:BIT motor terminals; 1 micro servo on a MOTION:BIT servo port
- MOTION:BIT motor channel and servo port numbers used: [NOT STATED]
- Remote: Joystick:bit V2 Kit with its own micro:bit; the Basic Kit lists 2x micro:bit Junior Kit V2 per robot set
- Radio scheme / radio groups: [NOT STATED]
- Robot battery: 18650 3.7V 2200mAh button top in the MOTION:BIT holder
- Controller batteries: 4x AAA battery sets (Complete Kit)
- MakeCode; MOTION:BIT extension pxt-motionbit for the robot
- MicroPython library: [NOT STATED]

## Use cases
- Classroom-scale robot soccer competition ("4 Robots in One Package")
- Build and program a 2WD micro:bit soccer robot with a servo shooter
- Remote-control a robot with a micro:bit Joystick:bit
- Run and score matches with the game field, goal posts, cards, whistle and official score sheets

## Known limitations
- The booklet PDF is image-only (237 MB) and its chapter text, wiring and code could not be read; the chapter-code Drive folder could not be opened
- MOTION:BIT port assignments and the radio control scheme are not stated by any readable source
- "without battery" options ship without the 18650 cells; the robot needs a 3.7V button-top 18650
- The product page is inconsistent on micro:bit count: 4x micro:bit Junior Kit (V2) in the Complete Kit for 4 robots plus 4 Joystick:bit V2 Kits, but 2x per robot set in the Basic Kit
- Basic Kit packing list is truncated on the product page
- Card limits: max 2 yellow cards per robot, max 2 red cards per team (score sheet)
- Controller limits apply from MOTION:BIT: 3.6–6 V input, 1 A continuous / 1.5 A peak motor current, 5 V output 300 mA, 3V3 output 200 mA
- Joystick:bit V2 is not a Cytron product; its details are not stated by Cytron sources
- Field size, match rules beyond the score sheet, robot dimensions, weight and age range are not stated

## Positioning (kept apart from specs)
- "Classroom-scale soccer competition kit"
- "4 Robots in One Package"
- "4-step workflow"
- "7-chapter learning guidebook"

## Price band
RM370.00–RM1,675.65 across the options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-strikerbit-soccer-competition-kit

## Datasheet
https://drive.google.com/file/d/12FMdIQBJSj9FZLkH8i9N7iAjfZcL4TMG/view

## Source type
Website

## Source link
https://my.cytron.io/p-strikerbit-soccer-competition-kit

# Product fact sheets

## Product name
SUMO:BIT Robot Kits - 1kg Sumo Robot for micro:bit

## Aliases
V-KIT-SUMOBIT, SUMO:BIT Robot Kit, SUMO:BIT Robot Kits, SUMOBIT Robot Kit, SUMO:BIT 1kg Sumo Robot Kit, 1kg Sumo Robot for micro:bit

## What it is
A 1 kg-class sumo robot kit for the BBC micro:bit built around the SUMO:BIT board with two MD13S motor drivers, five Maker Object opponent sensors, two Maker Reflect edge sensors, two 12 V DC motors, a 3S LiPo battery and a 3D-printed body with a steel blade. It runs autonomously from MakeCode or under remote control.

## Specs and functions
- Product code: V-KIT-SUMOBIT
- Competition class: 1 kg sumo robot
- Purchase options: Complete Kit (with body) / Basic Kit (without body) / 3D Printed Body only, each with or without micro:bit
- Controller: SUMO:BIT board with 2x MD13S attached (board specs: see the SUMO:BIT fact sheet)
- Drive motors: 2x 12 V 580 rpm DC motor with wires (Assembly guide and Checking guide); product page says "12V brushed DC motor" without rpm
- Motor torque: [NOT STATED]
- Wheels: 2x aluminium rim + silicone tyre wheel set, each rim fixed with two screws on the motor shaft flat
- Battery: LiPo 11.1 V 1300 mAh (3-cell); product page packing list 1x, Assembly guide item list 2x
- Charger: not included; "2-3 cell LiPo balance charger" offered as an accessory; guide says use a LiPo balance charger or USB LiPo charger
- 3-cell LiPo full charge up to 12.6 V; do not let the battery drop below 11 V
- Opponent sensors: 5x Maker Object
- Edge sensors: 2x Maker Reflect; "For best result, use with the latest (11 Dec 2024 onwards) Maker Reflect"
- Robot weight without extra weight: "around ±860g"
- Robot dimensions: [NOT STATED]
- Body: 1x 3D-printed main body, 1x right motor bracket, 1x left motor bracket, 2x copper base, 1x 6" stainless steel blade, 1x PCB plate (training), back cover (new step 13); free STL files on the Cytron-SUMOBIT GitHub
- Extra weight: not included; maximum 4 pieces in a row beside the battery compartment, covered to prevent short circuits
- Complete Kit packing list (with micro:bit, product page): 1x SUMO:BIT with 2x MD13S attached, small flat screwdriver, Phillips screwdriver, Dean T male connector 18 AWG 15 cm, 5x Maker Object, 2x Maker Reflect, 7x GVS F-F extension cable 10 cm, 2x 12 V brushed DC motor with wires, 2x wheel set, M2 Allen key, 1x LiPo 11.1 V 1300 mAh, 3S LiPo charger cable extension 10 cm, 2x copper base for mini sumo robot, 4x M3 nylon lock nut, 4x M3 bolt 20 mm, 10x M3x6 self-tapping screw, 1x PCB Plate for Blade (training), 1x 6" stainless steel blade, 1x 3D-printed chassis with motor brackets, 1x micro:bit Junior Kit, 1x BBC micro:bit V2, USB Micro B cable, sticker set
- Assembly guide item list: 1x SUMO:BIT board, 1x micro:bit Junior Kit, 5x Maker Object, 2x Maker Reflect, 2x 12 V 580 rpm DC motor with wires, 2x aluminium silicone wheel set, 2x LiPo battery 11.1 V 1300 mAh, 1x 3D-printed main body, 1x right motor bracket, 1x left motor bracket, 2x copper base, 1x steel blade, 1x PCB plate, 7x 10 cm GVS female-to-female cables, 1x Dean T male connector with cable, 1x 10 cm 3S LiPo charger cable extension, 1x small flat screwdriver, 1x Phillips screwdriver, 10x M3 tapping screws (6 mm), 4x M3 bolt and nut (20 mm)
- Basic Kit and Body-only contents: [NOT STATED]
- Dohyo used in the guides: 1 m diameter
- A typical sumo round lasts around 10 seconds or less; more than 1 minute continuous running may overheat the motors
- Guides: Assembly (V1) 2 Dec 2024, Checking 2 Dec 2024, Maintenance 2 Dec 2024, Autonomous 9 Dec 2024, RC (Remote Control) 10 Dec 2024 (Google Slides)
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Wiring: EDGE-L = left Maker Reflect, EDGE-R = right Maker Reflect, OPP-L = left Maker Object, OPP-FL = front-left, OPP-FC = front-centre, OPP-FR = front-right, OPP-R = right Maker Object, all on 10 cm GVS F-F cables; motors on the LEFT MOTOR / RIGHT MOTOR terminals; battery on the battery terminal through the Dean T cable
- Maker Reflect cable pins OUT, VCC, GND; Maker Object cable pins GND, VCC, OUT (as the guide lists them)
- Assembly: 13 steps (edge sensors, copper bases, motors and brackets, opponent sensors, optional weights, motor and battery connection, motor direction check with the alignment button, sensor connections, board mounting, rims and tyres, micro:bit, PCB plate or blade, optional robot holder, back cover)
- micro:bit inserted with buttons and LED matrix facing up; only required for autonomous mode
- Programming: Microsoft MakeCode with the "sumobit" extension (https://github.com/CytronTechnologies/pxt-sumobit); flash by USB from a computer or wirelessly from an iPad/iPhone/Android app (press the micro:bit reset button three times for Bluetooth mode)
- Autonomous sample programs: edge sensor and battery readout, navigation, move around the dohyo, detect obstacle, basic sumo robot with 5 s countdown, community DIP-strategy programs started by button or by IR Sumo Start
- RC mode 1 — wireless USB joystick: remove the micro:bit, plug the receiver into the USB-A port, RGB LEDs stay yellow when ready; only the Cytron USB Joystick model is supported; half speed by default, hold R2 for full speed
- RC mode 2 — hobby RC receiver on the SERVO/RC port: port 1 = speed (forward/reverse), port 2 = steering; turn on the transmitter first; RGB LEDs stay orange when ready; example mappings FlySky FS-iA6B CH2/CH4, Hot RC F-06A CH2/CH1, Dumborc X6F CH2/CH1 to RC port 1/2
- RC mode 3 — a second micro:bit as joystick (Joystick:bit V2 used in the guide): code on both ends, semi-auto possible; press B on the joystick to set the edge threshold before a run
- Firmware update: .uf2 from the SUMO:BIT GitHub page, hold the boot button while connecting USB-C, copy to the RPI-RP2 drive
- Accessories offered: USB Joystick, 2-3 cell LiPo balance charger
- Support: Telegram SUMO:BIT Support Group (https://t.me/sumobit_support)

## Use cases
- Start your sumo journey: build and compete with a 1 kg sumo robot
- Autonomous sumo robot programmed in MakeCode (edge detection, opponent detection, attack and search)
- Remote-controlled sumo robot via wireless USB joystick, hobby RC transmitter, or a second micro:bit as joystick
- DIP-switch strategy selection for competitions, started by button or IR Sumo Start
- Practice with the PCB plate; tournaments with the steel blade

## Known limitations
- Charger not included; extra weights, robot holder tape, Joystick:bit and a second micro:bit are not included
- "Without micro:bit" options omit the micro:bit; the micro:bit is removed for USB-joystick and RC-receiver modes
- USB joystick mode only supports the Cytron USB Joystick model
- Do not discharge the 3S LiPo below 11 V; full charge is 12.6 V
- Motors are high-current and heat quickly; rest the robot if the motor bracket feels warm; more than 1 minute continuous running is too long
- Run only on a dohyo (or a clean flat surface for RC testing); avoid tiles, uneven or dusty floors and carpet
- Check battery polarity at the board before connecting
- The blade is sharp; use the PCB plate for practice
- Screws loosen after impacts and need regular tightening
- Best edge-sensor results need Maker Reflect units from 11 Dec 2024 onwards
- Robot dimensions, motor torque and the Basic Kit / Body-only contents are not stated
- Product page lists 1 battery while the Assembly guide lists 2

## Positioning (kept apart from specs)
- "Start your sumo journey with the SUMO:BIT Robot Kit!"
- "Whether you're a beginner or looking to sharpen your skills, this kit has everything you need to start your journey."
- "SUMO:BIT board, MD13S Motor Driver, Essential accessories, Free STL file for robot body"

## Price band
RM80.00–RM1,047.70 across options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-sumobit-robot-kits-1kg-sumo-robot-for-microbit

## Datasheet
https://docs.google.com/presentation/d/15mmPIKEZlVMuslrhgAz_jTQuCI3Ud2Z0r1F7EQjnnpk/edit

## Source type
Datasheet

## Source link
https://docs.google.com/presentation/d/15mmPIKEZlVMuslrhgAz_jTQuCI3Ud2Z0r1F7EQjnnpk/edit

# Product fact sheets

## Product name
Robot Battle (500g) - SUMO:BIT

## Aliases
V-BATTLE-SMB, Robot Battle (500g) - SUMO:BIT, Robot Battle 500g, SUMO:BIT Robot Battle Kit, 500g Battle Robot SUMO:BIT

## What it is
A 500 g-class two-wheel battle robot kit using the SUMO:BIT board with two MD13S as the controller, 12 V 980 rpm GM25 geared motors, a 3S 2000 mAh LiPo and a 3D-printed chassis. It ships without a remote controller and without sensors, so it is driven through the SUMO:BIT's RC modes.

## Specs and functions
- Product code: V-BATTLE-SMB
- Competition class: Robot Battle (500 g); "Suitable for the Robot Battle Challenge"
- Purchase options: Complete / Basic / 3D Printed Body only, each with or without micro:bit
- Controller: SUMO:BIT with 2x MD13S (board specs: see the SUMO:BIT fact sheet)
- Motors: 12 V 980 rpm 2.3 kgf·cm GM25 brushed DC geared motor; packing list prints "1 x" (quantity unconfirmed)
- Wheels: 1x G25T1 silicone wheel set (1 pair)
- Battery: 1x Mini LiPo 3S 11.1 V 2000 mAh
- Charger: 1x 3S LiPo USB balance charger included, plus 3S charger cable extension
- Battery lead: Dean T connector 18 AWG 15 cm; 10 cm JST SM 2-pin male connector
- Chassis: robust 3D-printed chassis set (body + left/right motor brackets)
- Dimension: 15 cm x 15 cm x 4 cm
- Actual weight: 495 g
- Hardware: 4x M3*20 screw, 4x M3 nut, 4x M3*6 self-tapping screw, screwdrivers
- With-micro:bit options add: micro:bit Junior Kit, micro:bit V2, USB Micro B cable
- Complete packing list (with micro:bit): 1x SUMO:BIT with 2x MD13S, screwdrivers, Dean T connector 18 AWG 15 cm, 1x 12 V 980 rpm 2.3 kgf·cm GM25 brushed DC geared motor (as printed), 1x G25T1 silicone wheel set (1 pair), 1x Mini LiPo 3S 11.1 V 2000 mAh, 1x 3S LiPo USB balance charger, 3S charger cable extension, 10 cm JST SM 2-pin male connector, 4x M3*20 screw, 4x M3 nut, 4x M3*6 self-tapping screw, 3D-printed chassis set, micro:bit Junior Kit, micro:bit V2, USB Micro B cable
- Basic and Body-only contents: [NOT STATED]
- Remote controller: not included ("This Battle Robot Kit does not come with a controller")
- Opponent / edge sensors: none listed
- Warranty: "There is NO warranty for Battle Robot."

## Interfaces and compatibility
- Motors on the SUMO:BIT LEFT MOTOR / RIGHT MOTOR terminals (one MD13S per channel); battery on the battery terminal via the Dean T cable
- RC mode with a hobby receiver on the SUMO:BIT SERVO/RC port: port 1 = speed (forward/reverse), port 2 = steering; Hot RC F-06A example mapping CH2 to RC port 1, CH1 to RC port 2; transmitter on first; RGB LEDs orange when ready; micro:bit removed (SUMO:BIT Robot Kit RC guide, 10 Dec 2024)
- RC mode with the Cytron USB Joystick on the USB-A port (only supported USB joystick model); RGB LEDs yellow when ready; micro:bit removed
- A second micro:bit (e.g. Joystick:bit V2) as joystick needs code on both ends
- Programming for micro:bit-coded control: MakeCode "sumobit" extension (https://github.com/CytronTechnologies/pxt-sumobit)
- Tutorials on the page: 2 Wheel Robot Battle with SUMO:BIT; SUMO:BIT RC Mode with HOT RC
- Support: Telegram SUMO:BIT Support Group

## Use cases
- Robot Battle Challenge (500 g class) competition robot
- 2-wheel robot battle with SUMO:BIT
- SUMO:BIT RC mode with a Hot RC transmitter

## Known limitations
- No warranty for the Battle Robot
- No remote controller in the box; a hobby RC set, Cytron USB Joystick, or Joystick:bit with a second micro:bit is bought separately
- No opponent or edge sensors in the kit
- Actual weight 495 g leaves about 5 g inside the 500 g class
- Packing list prints "1 x" motor; the true quantity is unconfirmed
- Basic and 3D Printed Body only contents not stated
- "Without micro:bit" options omit the micro:bit; the micro:bit is removed for RC-receiver and USB-joystick modes
- Supported micro:bit version not stated by any source

## Positioning (kept apart from specs)
- "Suitable for the Robot Battle Challenge"
- "Robust 3D printed chassis"

## Price band
RM69.00–RM716.40 across options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-robot-battle-500g-sumo-bit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-robot-battle-500g-sumo-bit

# Product fact sheets

## Product name
4 Wheel SOCCER:BIT Robot Bundles

## Aliases
V-SCRBIT-4WD, SOCCER:BIT, SOCCERBIT, SOCCER BIT, SOCCER:BIT Robot Kit, 4 Wheel SOCCER:BIT Robot Bundle, 4WD SOCCER:BIT

## What it is
A four-wheel-drive soccer robot bundle for the BBC micro:bit using the SUMO:BIT board with two MD13S as the controller, four 12 V 980 rpm GM25 geared motors, 42 x 30 mm silicone wheels, a 3S 1300 mAh LiPo and a 20 x 20 cm PLA 3D-printed body. It comes in loose parts for self-assembly and is programmed in MakeCode.

## Specs and functions
- Product code: V-SCRBIT-4WD
- Purchase options: Complete / Basic / 3D Printed Body only, each with or without micro:bit
- Microcontroller: SUMO:BIT with 2x MD13S (board specs: see the SUMO:BIT fact sheet)
- Programming: MakeCode
- Motors: 4x 12 V 980 rpm 2.3 kgf·cm GM25 brushed DC geared motor
- Speed: 980 rpm; Torque: 2.3 kgf·cm
- Wheels: 4x high-grade silicone wheels 42 mm x 30 mm
- Body: PLA 3D-printed, 20 cm x 20 cm
- Weight: 1 kg
- Battery: 1x LiPo 11.1 V 1300 mAh
- Charger: [NOT STATED]
- Motor wiring: 2x Easy Clip wire splitter (2 in, 4 out), 18 AWG wires, Dean T connector
- Hardware and tools: M3 hardware, M2 Allen key, screwdrivers
- Control: RC Controller – Joystick:bit V2 Kit for micro:bit [optional], not included
- Complete packing list: 1x SUMO:BIT with 2x MD13S, screwdrivers, Dean T connector, 4x 12 V 980 rpm 2.3 kgf·cm GM25 motors, 4x silicone wheels 42 x 30 mm, 1x LiPo 11.1 V 1300 mAh, 2x Easy Clip wire splitter (2 in 4 out), 18 AWG wires, M3 hardware, M2 Allen key, 3D-printed body, micro:bit items per option
- Basic and Body-only contents: [NOT STATED]
- "The Soccer Robot comes in loose parts. You will have to assemble them yourself."
- Warranty: [NOT STATED]

## Interfaces and compatibility
- SUMO:BIT has two motor channels (one MD13S each); the four motors connect through the two "2 in 4 out" splitters, two motors per channel
- Motors on the SUMO:BIT LEFT MOTOR / RIGHT MOTOR terminals; battery on the battery terminal via the Dean T cable
- RC control with Joystick:bit V2: a micro:bit in the Joystick:bit and a micro:bit in the SUMO:BIT, both programmed in MakeCode with the "sumobit" extension (SUMO:BIT Robot Kit RC guide, 10 Dec 2024)
- Other SUMO:BIT RC modes: Cytron USB Joystick on the USB-A port; hobby RC receiver on the SERVO/RC port (port 1 speed, port 2 steering)
- The page's "user manual" link opens the MD13S User's Manual V1.1 (June 2018), a motor-driver manual
- Tutorial on the page: Soccer Robot using SUMO:BIT
- Support: Telegram SUMO:BIT Support Group

## Use cases
- 4-wheel soccer robot using SUMO:BIT
- Remote-controlled soccer robot with Joystick:bit V2
- MakeCode-programmed micro:bit robotics

## Known limitations
- Comes in loose parts; self-assembly required
- Joystick:bit V2 controller is optional and not included; a second micro:bit is needed for Joystick:bit control
- Charger not listed in the packing list
- Four motors share two MD13S channels (13 A continuous / 30 A for 10 s max per channel)
- "Without micro:bit" options omit the micro:bit
- Basic and 3D Printed Body only contents not stated
- No SOCCER:BIT manual: the "user manual" link is the MD13S manual
- Supported micro:bit version not stated by any source
- Warranty not stated

## Positioning (kept apart from specs)
- "High grade silicon" wheels
- "4 Wheel SOCCER:BIT Robot Bundles"

## Price band
RM90.00–RM1,134.52 across options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-soccerbit-robot-kits

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-soccerbit-robot-kits

# Product fact sheets

## Product name
DIY RC Boat Using micro:bit

## Aliases
DIY RC Boat Using micro:bit, PR-DIY-BOAT-MBIT, DIY RC Boat, micro:bit RC Boat, RC Boat micro:bit, DIY Boat micro:bit

## What it is
A do-it-yourself remote-controlled boat project for the BBC micro:bit: one micro:bit on the boat plugged into a MOTION:BIT drives two DC motors with propellers and a 9 g servo rudder fin, and a second micro:bit is the radio remote. The product page is the build guide and the hull is 3D-printed from Cytron's STL files or made from foam or plastic.

## Specs and functions
- Product code: PR-DIY-BOAT-MBIT
- Project kit; the product page is itself the build guide (6 build steps: gather components, assemble hull, ...)
- Controller board: MOTION:BIT (see the MOTION:BIT fact sheet; not re-documented here)
- Components listed: BBC micro:bit x2; MOTION:BIT; 2x DC motors with propellers; 9g servo (fin); 3.7V LiPo battery pack; boat hull 3D-printed (STL provided) or foam/plastic; waterproof enclosure optional
- Propulsion: 2x DC motors with propellers
- Steering: 9 g servo moving a fin; fin positions used by Cytron's remote code: 130 degrees, 50 degrees, 90 degrees (centre)
- Power: 3.7V LiPo battery pack
- Software: MakeCode blocks with the MOTIONBIT extension; Code #1 on the boat micro:bit, Code #2 on the remote micro:bit
- Remote controls: Shake = start the motors; Button A = fin to 130 degrees; Button B = fin to 50 degrees; Buttons A+B = fin back to 90 degrees; touch the micro:bit logo = stop the motors
- Hull: 3D-printed (STL files provided; Cytron printed it on an Artillery Hornet) or foam/plastic
- Packing list / what is in the box: [NOT STATED]
- Warranty: [NOT STATED]
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]

## Interfaces and compatibility
- Boat: micro:bit on MOTION:BIT; 2 DC motors on MOTION:BIT motor terminals; 9 g servo on a MOTION:BIT servo port
- MOTION:BIT motor channels and servo port used: [NOT STATED]
- Remote: second micro:bit over micro:bit radio; radio group: [NOT STATED]
- Battery: 3.7V LiPo battery pack (which MOTION:BIT input it uses: [NOT STATED])
- MakeCode blocks; MOTIONBIT extension https://github.com/CytronTechnologies/pxt-motionbit
- Linked resources: Getting Started with MOTION:BIT & Projects Guide tutorial; MOTION:BIT datasheet; pxt-motionbit; MOTION:BIT 3D CAD
- Tutorial with video: Build an RC Boat Using micro:bit (https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit)
- micro:bit version required: [NOT STATED] (the remote uses the touch logo)

## Use cases
- Build a remote-control boat with a micro:bit
- Control the boat's motors and rudder fin from a second micro:bit using shake, buttons and the touch logo
- 3D-print a boat hull from the provided STL files

## Known limitations
- No datasheet, booklet or packing list; the product page and tutorial are the only guides
- Whether the hull, LiPo pack, propellers and the two micro:bits are included in the package is not stated in the text read
- MOTION:BIT motor channels, servo port and the radio group are not stated in text (shown only in code-block images)
- The hull must be 3D-printed from the STL files or made from foam or plastic
- Waterproof enclosure is optional and not described; the micro:bit, MOTION:BIT and LiPo are not waterproof
- MOTION:BIT limits apply: 3.6–6 V input, 1 A continuous / 1.5 A peak per motor channel
- The remote's touch-logo stop command needs a micro:bit with a touch logo
- Motor model, propeller size, servo model, LiPo capacity, run time and warranty are not stated

## Positioning (kept apart from specs)
- Remote-control boat built with a micro:bit, with a video tutorial available

## Price band
RM297.55 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-diy-boat-mbit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit

# Product fact sheets

## Product name
Maker Mini Sumo Controller

## Aliases
MAKER-MSUMO, Maker MSumo, Maker Mini Sumo, Maker Mini Sumo Controller

## What it is
A mini sumo robot controller based on the ATmega328P (Arduino Nano/Uno compatible), with a 2-channel motor driver and ports for opponent sensors, edge sensors, a start module, an RC servo and 2 GPIO. It is programmed from the Arduino IDE with the Cytron Maker Sumo Library.

## Specs and functions
- Product code: MAKER-MSUMO
- MCU: ATmega328P ("Arduino Nano/Uno Compatible (Powered by ATMEGA328P)")
- Programming and serial: USB Micro-B (upload Arduino program, Serial Monitor); Tx/Rx LEDs; reset button
- Cytron's Ikedo Mini Sumo Robot Pro setup guide installs the WCH CH341SER USB driver
- Power input (Vin): 7.0–18.0 VDC, through the Battery Terminal (VB+ positive, VB- negative/ground)
- Reverse polarity protection on Vin (product page: reconnect with the correct polarity and it will work again)
- On/off switch with MOSFET latching circuit: "Vibration proof" (datasheet) / "Shockproof" (product page); once on, a lost switch contact does not turn the board off
- Switching regulator for +5V; DC +5V output 500 mA max total
- Battery voltage readable in code (VB+ via voltage divider to A7, `readBatteryVoltage()`)
- Motor driver: 2 channels, 3.0 A continuous and 6.0 A peak (< 5 seconds) per channel; product page describes a "discrete MOSFETs H-Bridge design"
- Motor PWM frequency: DC to 20 kHz
- Motor truth table: PWM Low = brake; PWM High + DIR Low = forward; PWM High + DIR High = backward (actual direction depends on wiring; swapping MxA and MxB reverses it)
- Motor test buttons (run the motor at full speed without code) and motor status LEDs (MLA/MRA forward, MLB/MRB backward)
- Digital input: low 0–0.5 V, high 1.7–5.0 V; analog input 0–5.0 V
- Pins (Arduino): left motor PWM D3 / DIR D4; right motor PWM D11 / DIR D10
- 5 × opponent sensor inputs (digital, internally pulled up to +5V, active low, with status LEDs): Left D12, Right D13, Front-Center D6, Front-Left D5, Front-Right D7; MAKER-OBJECT ports on the bottom layer are wired in parallel
- 2 × edge sensor inputs (analog/digital): Left A0, Right A1
- 2 × GPIO ports (digital in/out or analog in): GPIO1 A2, GPIO2 A3
- 1 × start module input (digital) D2, in parallel with the onboard start button, pulled high to +5V, active low, with Start LED; for an external start button or IR start module
- 1 × RC servo output D9
- 1 × programmable user LED A4
- 1 × potentiometer A5
- 1 × 3-way mode selection DIP switch on A6 (up to 8 configurations; `readDipSwitch()` returns 0–7, SW1 = MSB)
- 1 × piezo buzzer D8 (bottom layer, plays tones/melody)
- Power LED
- Dimensions: 92 mm × 36 mm (product page)
- Packing list: 1 × Maker Mini Sumo Controller
- Warranty: generally 12 months (product page)
- Datasheet: Rev 1.0, November 2019

## Interfaces and compatibility
- Arduino IDE with the Cytron Maker Sumo Library (version 1.2.3, architectures=avr, depends on Servo); install via Library Manager by searching "Cytron Maker Sumo Library"; `#include "CytronMakerSumo.h"`; call `MakerSumo.begin()` first
- Official examples: AutoSumo, CalibrateEdgeSensors, RcSumo, TestInputs, TestOutputs (File > Examples > Cytron Maker Sumo Library)
- Library functions: begin, readDipSwitch, readBatteryVoltage, stop, moveForward, moveBackward, turnLeft, turnRight, setMotorSpeed, setServoPosition, playTone, playMelody, calibrateEdgeSensors, readEdgeSensorThreshold, isEdgeDetected
- Sensor, GPIO, start and servo ports: S (signal), + (+5V), - (GND); screw terminals for sensors and motors (solderless)
- Opponent sensors: Maker Object (used in the Ikedo V2 kit); edge sensors: Maker Reflect S (used in the Ikedo V2 kit)
- RC mode: RC receiver on GPIO1/GPIO2 (Cytron tutorial tested Flysky and HotRC; RcSumo example)
- PS2 controller: Cytron tutorial wires DATA→D2, CMD→D7, ATT→D6, CLK→D5 with `ps2x.config_gamepad(5, 7, 6, 2, true, true)`, with object sensors removed
- Included in the Ikedo Mini Sumo Robot V2 kit (KIT-IKEDO-MSV2-S), with 2 × 600RPM 6V DC Micro Metal Gearmotor and a 7.4V 450mAh LiPo battery
- Resources: datasheet, 3D CAD, Arduino library and examples on GitHub
- MicroBlocks / CircuitPython / MakeCode / MicroPython: [NOT STATED]

## Use cases
- Sumo robot competitions, for beginners through professional sumo robot builders
- International Sumo robot competition 500g category
- Autonomous sumo robot (AutoSumo example; Ikedo Mini Sumo Robot V2 kit)
- RC category of Sumo robot competitions, and both RC and autonomous categories with the same robot
- Mini sumo robot controlled by a PS2 controller
- Mini sumo robot controlled by a Bluetooth controller (HC-05 or HC-06)

## Known limitations
- Motor current limited to 3.0 A continuous per channel; 6.0 A peak only for < 5 seconds
- Product page: a motor of more than 3A "will cause the motor driver chip to burn" and is not covered by warranty
- Warranty does not cover board modifications (e.g. adding external components), use in competition ("intense usage"), or misuse
- Over-current, thermal or short-circuit protection is not stated; reverse polarity protection is on Vin only
- Vin must stay within 7.0–18.0 VDC
- +5V output limited to 500 mA total across all ports
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring; swap MxA/MxB to reverse
- Opponent sensor and start inputs are active low
- Almost all pins are used by onboard functions; GPIO1 (A2) and GPIO2 (A3) are the expansion ports
- `tone()` interferes with PWM on pins 3 and 11 (both motor PWM pins); use the library's melody functions
- The Servo library (always attached by `begin()`) disables `analogWrite()` on pins 9 and 10
- I²C pins A4/A5 are used by the user LED and potentiometer; SPI pins D11/D12/D13 are used by PWM_R, OPP_L and OPP_R
- A6 (DIP switch) and A7 (battery sense) are analog-only
- Edge calibration is stored in EEPROM from address 0; user EEPROM writes there overwrite it
- Library declares architectures=avr only
- README sample snippets call bare `println(...)`, which does not compile; use `Serial.println(...)`
- PS2X library default pins (13, 11, 10, 12) clash with the board's pins
- No USB cable in the packing list
- Operating temperature: [NOT STATED]
- Arduino IDE board selection: [NOT STATED]

## Positioning (kept apart from specs)
- Product page title: "Maker Mini Sumo Controller: Simplifying Sumo Robot for Beginner"
- "the ultimate board for you - Whether you are a beginner who just started learning about Sumo robots or a professional robot builder who participates in international Sumo robot competitions"
- Designed with Team Ikedo Kogeki, "the winner of multiple Sumo robot competitions locally and internationally"

## Price band
- RM114.45 on the product page (RM108.73 each for 10 or more), 16 Oct 2026

## Product page
https://my.cytron.io/p-maker-mini-sumo-controller-simplifying-sumo-robot-for-beginner

## Datasheet
https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit

# Product fact sheets

## Product name
URC10 Sumo Robot Controller

## Aliases
URC10, URC10 Sumo Robot Controller, 2x10A UNO Robot Controller, Cytron Uno Robot Controller

## What it is
An Arduino UNO-compatible controller board with an onboard 2-channel brushed DC motor driver, made for sumo robots. It is programmed from the Arduino IDE over USB Micro-B through a CH340 USB-to-UART converter.

## Specs and functions
- Product code: URC10
- Power Input Voltage (Vin): 8 – 25 VDC (datasheet spec table), on the Power Input Terminal: VM = positive, GND = negative
- Bottom-layer silkscreen reads "POWER (7-24V)"; the datasheet spec table value (8 – 25 VDC) applies
- No reverse polarity protection: connecting in reverse polarity "will damage the board instantaneously"
- Motor driver: 2 channels (Motor 1, Motor 2), PWM + DIR control; silkscreen "2x10A", "MOTOR1 (10A)", "MOTOR2 (10A)"
- Maximum Motor Current: 10 A continuous, 30 A peak (< 10 seconds), per channel
- Motor truth table: PWM Low = brake; PWM High + DIR Low = forward; PWM High + DIR High = backward (actual direction depends on wiring; swapping MA and MB reverses it)
- Motor Driver Port (connected internally): Motor 1 DIR D4, PWM D5; Motor 2 DIR D7, PWM D6
- Logic Input Voltage: Low 0 – 0.7 V, High 1.5 – 5.0 V
- DC +3V3 Output Maximum Current: 500 mA
- DC +5V Output Maximum Current: 1000 mA
- IO pin Maximum Current: 20 mA
- USB Micro B connector: upload Arduino program from PC; Serial Monitor debugging
- USB-to-UART: CH340
- Power LED; Motor Status LEDs (M1A/M2A forward, M1B/M2B backward); TX/RX LEDs
- Test Buttons M1A, M1B, M2A, M2B (run the motor at full speed); Reset Button
- Board size: 99.70 mm × 75.57 mm; 4 × ⌀3 mm mounting holes spaced 94.62 mm × 70.49 mm
- Datasheet: Rev 1.0, March 2019; User's Manual: V1.2, April 2019
- Microcontroller: [NOT STATED]
- Over-current / thermal protection: [NOT STATED]
- Motor PWM frequency: [NOT STATED]
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- Packing list: [NOT STATED]

## Interfaces and compatibility
- Arduino UNO Standard Female Header: takes compatible Arduino shields, except shields that use D4, D5, D6, D7 (connected to the motor driver internally)
- Power + motor screw terminal block order: M1A, M1B, VM, GND, M2A, M2B
- Digital Port × 6 (GND, +5V, Signal): D0 – D3 and D10 – D13; D0 and D1 are used for serial communication
- Analog/Digital Port × 6 (Signal, +5V, GND): A0 – A5
- HC-SR04 Ultrasonic Sensor Port × 2 (+5V, TRIG, ECHO, GND): Sensor 1 ECHO D8, TRIG D9; Sensor 2 ECHO D10, TRIG D11
- I2C Port (SCL, SDA, PWR, GND): PWR is +3V3 by default; +5V by cutting the trace and soldering the center pad to the 5V pad on the bottom layer
- Power Port: NC, IOREF, RESET, +3V3, +5V, GND, GND, VIN
- Arduino UNO Standard ISP Port: load program with an AVR programmer; also usable for SPI
- Arduino IDE; user manual screenshots show Board "Arduino/Genuino Uno"
- CH340 driver from Cytron: Windows CH341SER.EXE, macOS CH341SER_MAC.ZIP
- Cytron Motor Drivers Library (Library Manager: "cytron motor drivers library"); `#include <CytronMotorDriver.h>`; `CytronMD motorL(PWM_DIR, 5, 4)` and `CytronMD motorR(PWM_DIR, 6, 7)`; `setSpeed()` from -255 to 255
- Sample code: GitHub CytronTechnologies/URC10SumoRobot (edge sensors D12/D11, side opponent sensors D3/D10, front opponent sensors A0/A1/A2, external start button D13, LEDs on D0/D1 driven active low)
- IR Sumo Start module (pack's Auto Kit notes): S to D2, + to 5V, − to GND; read D2 with `INPUT` (HIGH = run, LOW = stop)
- Cytron's Hackster build guide uses an 11.1V 3-cell 1300mAh LiPo, 4 × 12V 380RPM DC geared motors (two per side on one channel), 5 × IR opponent sensors and 2 × IR line tracking modules
- MicroPython / CircuitPython / MakeCode: [NOT STATED]

## Use cases
- Sumo robot controller
- Autonomous sumo robot (Cytron URC10SumoRobot sample: search, attack and edge back-off)
- "Building a Sumo Robot" with URC10 (Cytron Hackster guide linked from the user manual)
- Auto sumo robot started and stopped by an IR Sumo Start module (pack's Auto Kit notes)

## Known limitations
- No reverse polarity protection; reverse connection damages the board instantly
- Vin must stay within 8 – 25 VDC
- Motor current: 10 A continuous; 30 A peak only for < 10 seconds
- D4, D5, D6, D7 are taken by the motor driver; avoid shields that use them
- D0 and D1 are the serial pins (upload and Serial Monitor)
- HC-SR04 Sensor 2 uses D10 and D11, the same pins as the Digital Port's D10/D11 (used by the right opponent and right edge sensors in the sample code)
- +5V output limited to 1000 mA, +3V3 to 500 mA, each IO pin to 20 mA
- Motor test buttons run the motor at full speed
- Motor direction depends on wiring; swap MA/MB to reverse
- No onboard start button; the sample code's start button on D13 is external
- Sample code start delay is 1 s; the pack notes say most sumo rules require 5 s
- I2C port PWR is 3.3 V by default; 5 V needs a solder-jumper change
- Needs the CH340 driver for USB programming
- Over-current and thermal protection: [NOT STATED]

## Positioning (kept apart from specs)
- Named "Sumo Robot Controller" on the datasheet and user manual; the board silkscreen calls it "2x10A UNO ROBOT CONTROLLER"

## Price band
RM156.24 (Cytron product page "Sumo Robot Controller R1.1", read 2026-10-19)

## Product page
https://my.cytron.io/p-sumo-robot-controller-r1.1

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IR Sumo Start

## Aliases
IR-SUMO-START, IR Sumo Start, IR Sumo Start Module

## What it is
An infrared receiver module that gives a sumo robot a START/STOP signal from an IR remote. It outputs one digital signal: LOW in READY and STOP, HIGH in RUN, which the robot's controller reads to start or stop the motors.

## Specs and functions
- Product code: IR-SUMO-START
- Power input voltage (+): 3.0 V min, 5.5 V max (absolute maximum ratings); "compatible with 3V3 and 5V"
- Output signal (S): digital, 0 or 1 logic; HIGH level equals the power input voltage (Vs = Vin)
- Output signal voltage: 0–5 V at 5V power input; 0–3.3 V at 3.3V power input
- Output signal current: max 2.27 mA at 5V power input; max 1.50 mA at 3.3V power input
- IR receiver with built-in 38kHz bandpass filter
- Responds to IR signals from any IR remote; three remote buttons are bound to READY, RUN and STOP
- Power-up: LED GREEN for 1 second, then off; S = LOW (Receive Mode)
- READY: LED blinks PINK fast, then solid BLUE; S stays LOW
- RUN: LED solid GREEN; S = HIGH ("should trigger the sumo robot to start")
- STOP: LED blinks RED slowly, indefinitely; S = LOW ("should stop the robot immediately"); module must be manually reset before the next round
- Bind mode: hold the bind button more than 1 second; LED blinks BLUE, GREEN, RED (100ms each) three times, then off
- Binding: press remote button 1 (READY, LED blinks BLUE 3×), button 2 (RUN, GREEN 3×), button 3 (STOP, RED 3×); the module then returns to Receive Mode automatically
- Internal competition deck: IR noise makes the LED flash bright BLUE with no change to the output
- 1 × RGB indicator LED, 1 × bind button, 1 × Ø3.0 mm mounting hole (optional mounting)
- Dimensions (datasheet Figure 2): 14.0 mm wide; board body 21.0 mm; mounting-hole tab 5.4 mm; 23.3 mm from mounting-hole centre to bottom edge; header pins extend ~6.0 mm
- Datasheet: Rev 1.0, April 2025
- Supply current: [NOT STATED]
- Operating temperature: [NOT STATED]
- IR receiving range and angle: [NOT STATED]

## Interfaces and compatibility
- 3-pin header, left to right: − (GND), + (power input, 3.3V or 5V), S (output signal); power is the middle pin
- Read S as a digital input: HIGH = RUN, LOW = READY / STOP / power-up
- Cytron PIRC 2025 sample code (Arduino, Cytron Maker Sumo library, "based on Ikedo Mini V2") uses `pinMode(IR_SUMO_START, INPUT)` with `#define IR_SUMO_START 9`
- PIRC 2025 deck photos show the module plugged into robots built on the Maker Mini Sumo controller with a 3-wire jumper cable
- URC10 1KG Autonomous Sumo Robot Starter Kit (Auto Kit Mode, internal integration notes): + to 5V, − to GND, S to D2, `pinMode(..., INPUT)`
- Works with any IR remote (e.g. a TV remote); remote included: [NOT STATED]
- Supported IR protocols: [NOT STATED]
- Libraries / MicroPython / CircuitPython / MakeCode: [NOT STATED]

## Use cases
- Giving START/STOP to an autonomous sumo robot through a TV remote (IR signal)
- Sumo robot competitions where both robots must start at the same time, with no early start
- Stopping a robot wirelessly for safety
- PIRC 2025 competition robots
- URC10 1KG Autonomous Sumo Robot Starter Kit (Auto Kit Mode)

## Known limitations
- Power input must stay within 3.0–5.5 V; the output HIGH level equals the supply voltage, so a 5V supply gives a 5 V signal
- Output signal current max 2.27 mA (5V) / 1.50 mA (3.3V) — logic signal only
- STOP latches: the module must be manually reset to be used again for the next round
- READY keeps the output LOW; only RUN gives HIGH
- Remote buttons must be bound before use; whether bindings are kept after power-off is [NOT STATED]
- Reverse-polarity protection: [NOT STATED]
- Must be mounted away from noise, easy to access, and at the best angle to receive the judge's signal
- The robot's code must keep checking S to stop when STOP is sent; the module does not stop motors itself

## Positioning (kept apart from specs)
- Internal PIRC 2025 deck: "2 robot yang berlawan bergerak serentak. Tiada isu robot bergerak lebih awal." (the two opposing robots move at the same time; no early-start issue)
- "Keselamatan lebih terjamin. Robot boleh dihentikan secara wireless." (safer; the robot can be stopped wirelessly)

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
Ikedo Mini Sumo Robot V2

## Aliases
KIT-IKEDO-MSV2-S, Ikedo Mini Sumo Robot V2, Ikedo Mini Sumo Robot V2 Starter, Ikedo Mini Sumo Robot Starter Kit V2, Ikedo Bot Starter Kit V2, Ikedo Bot V2, Ikedo V2

## What it is
A ready-to-assemble mini sumo robot kit built around the Maker Mini Sumo Controller, with 5 Maker Object opponent sensors, 2 edge sensors, two 6 V micro metal gearmotors, a 7.4 V 450 mAh LiPo and a black 3D-printed PLA chassis. It is the upgraded version of the Ikedo Mini Sumo Robot Starter Kit, with an upgraded chassis design and more sensors.

## Specs and functions
- Product code: KIT-IKEDO-MSV2-S
- Size: 10 cm x 10 cm (product page)
- Weight: ~200 g (product page)
- Chassis: black PLA, 3D printed; parts: Main chassis, Top Cover, Motor Bracket
- Controller: Maker Mini Sumo Controller ("Arduino Nano/Uno compatible (ATmega328P)", USB-serial CH340C per the product page)
- Battery: 1 x 7.4V 450mAh LiPo, connected with a JST LiPo battery wire extension (VB+ = red, VB- = black)
- Opponent sensors: 5 x Maker Object Sensor; product page: "range 50cm adjustable"
- Edge sensors: 2 x, mounted underneath; product page: "Maker Reflect S"; Getting Started guide: "Maker Reflectance Sensor" (linked to the MAKER-REFLECT page)
- Motors: 2 x 600RPM 6V DC Micro Metal Gearmotor; product page: "6V DC motors (600rpm, 0.065kg.cm)"
- Wheels: 2 x High Grade Silicon Wheels Set (32mm x 22mm); blue from 17 Jul 2025
- Control: auto and manual control mode; RC transmitter/receiver sold separately
- Programming: through the Micro USB-B port on the right side of the assembled robot
- Getting Started components list: 1 x Maker Mini Sumo Controller, 5 x Maker Object Sensor (opponent), 2 x Maker Reflectance Sensor (edge), 2 x 600RPM 6V DC Micro Metal Gearmotor, 2 x High Grade Silicon Wheels Set (32mm x 22mm), 1 x 7.4V 450mAh LiPo Battery, 1 x Mini Sumo Robot Chassis (Top Cover), 1 x Mini Sumo Robot Chassis (Main), 1 x Mini Sumo Robot Chassis (Motor Bracket), 1 x JST LiPo Battery Wire Extension, 1 x 2561 3Ways Connector Extension Wire, 4 x M3x6 Self-Tapping Screw (Black), 6 x M2.5x20 Bolt, 1 x Tiny Phillips Screwdriver (3mm), 1 x Tiny Flat Head Screwdriver (2mm), 1 x USB Cable (FREE)
- Product page packing list (truncated on the page): 1 x Maker Mini Sumo Controller, 5 x Maker Object Sensor (opponent), 2 x Maker Reflect S (edge), 2 x 600RPM 6V DC micro metal gearmotor, 2 x silicon wheels 32mm x 22mm, 1 x 7.4V 450mAh LiPo, 3D printed parts (chassis, top cover, motor bracket), JST LiPo battery wire extension, ...
- Not included: RC transmitter/receiver; no LiPo charger in either packing list
- Assembly (Getting Started guide): edge sensor wires S = white, + = red, - = black (sensor side OUT = white, VCC = red, GND = black) to the "Front Left and Front Right" edge terminals; edge sensors fixed with 2 x M3x6 self-tapping screws; controller fixed with 2 x M3x6 self-tapping screws; motor bracket with 4 x M3x20 bolts, leaving a 1 mm gap; left motor MLA = red, MLB = black; right motor MRA = black, MRB = red; top cover with 2 x M2.5x20 bolts
- Warranty: "There is NO warranty for Sumo Robot."
- Age/syllabus: Getting Started guide says "suitable for primary and secondary school"

## Interfaces and compatibility
- Controller: see the Maker Mini Sumo Controller fact sheet (MAKER-MSUMO)
- Opponent sensor: Maker Object (MAKER-OBJECT); edge sensor: Maker Reflect S (product page) / Maker Reflectance Sensor (Getting Started guide)
- Software: Arduino IDE with the Cytron Maker Sumo Library v1.2.3 (architectures=avr, depends=Servo); examples AutoSumo, RcSumo, CalibrateEdgeSensors, TestInputs, TestOutputs
- RC (manual) mode: 2-channel RC receiver, forward/reverse channel to GPIO1 and left/right channel to GPIO2 (RcSumo example); invert the channel in the transmitter settings if the direction is reversed
- Start: onboard START button on the controller (AutoSumo waits for press-and-release; pressing START again stops the motors)
- Cytron tutorials linked from the product page: Maker Mini Sumo with Bluetooth controller; with PS2 controller; RC sumo using Maker Mini Sumo Controller
- Sibling: Ikedo Mini Sumo Robot Pro Bundle (KIT-IKEDO-MSUMO-P); predecessor: Ikedo Mini Sumo Robot Starter Kit

## Use cases
- Getting started in Sumo Robot competitions (primary and secondary school students)
- Learning robotics programming and computational skills
- Autonomous sumo robot (auto mode, AutoSumo example)
- Radio-controlled sumo robot (manual mode with a separately bought RC transmitter/receiver)

## Known limitations
- No warranty for the Sumo Robot
- RC transmitter/receiver not included; LiPo charger not listed in the kit
- Kit must be assembled; the guide says sliding the controller into the chassis "might be a little tricky"
- Motor bracket bolts must leave a 1 mm gap or "the body may bend"
- Edge sensor name differs between the product page (Maker Reflect S) and the Getting Started guide (Maker Reflectance Sensor)
- Getting Started guide lists 5 Maker Object sensors but one assembly step says "4x"
- Getting Started guide bolt sizes are inconsistent (6 x M2.5x20 in the list; 4 x M3x20 + 2 x M2.5x20 in the steps)
- Controller limits apply: 3.0 A continuous / 6.0 A peak per motor channel, Vin 7.0-18.0 V (see MAKER-MSUMO)
- Pre-loaded code: [NOT STATED]
- Arduino board selection: [NOT STATED]
- Competition weight class on the kit page: [NOT STATED]

## Positioning (kept apart from specs)
- "very beginner-friendly, and suitable for primary and secondary school"
- "a reliable choice for your kids to get started in Sumo Robot Competitions"
- Developed with the team manager of Ikedo Kogeki to "bring down the barrier for students who want to learn how to build a Sumo Robot"

## Price band
- RM418.95 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ikedo-mini-sumo-robot-v2-starter

## Datasheet
https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit

# Product fact sheets

## Product name
Ikedo Mini Sumo Robot Pro Bundle

## Aliases
KIT-IKEDO-MSUMO-P, Ikedo Mini Sumo Robot Pro Bundle, Ikedo Mini Sumo Robot Pro Kit, Ikedo Mini Sumo Robot Pro, Ikedo Pro Bundle, Ikedo Pro

## What it is
The higher-specification Ikedo mini sumo robot kit: the Maker Mini Sumo Controller, 5 Maker Object opponent sensors, 2 Maker Reflect S edge sensors, a 7.4 V 450 mAh LiPo and a 10 cm x 10 cm black PLA chassis, with 800 RPM 3.1 kg.cm motors, a laser-cut stainless steel shield, a 4" stainless steel razor blade and a copper weight base. It supports auto and manual (RC) mode; the RC transmitter/receiver is sold separately.

## Specs and functions
- Product code: KIT-IKEDO-MSUMO-P
- Size: 10 cm x 10 cm
- Weight: 350 g
- Chassis: black PLA; packing list: 1 x chassis (main), 1 x 3D printed motor bracket
- Controller: Maker Mini Sumo Controller (ATmega328P; USB-serial CH340C per the product page)
- Battery: 1 x 7.4V 450mAh LiPo, JST LiPo wire extension
- Opponent sensors: 5 x Maker Object; product page: "range 50cm adjustable"
- Edge sensors: 2 x Maker Reflect S (product page links "Datasheet for Edge Sensor (MAKER-REFLECT-S)")
- Motors: 2 x 800RPM 6V DC micro metal gearmotor; "6V DC motors (800rpm, 3.1kg.cm)"
- Wheels: 2 x silicon wheels 32x22mm; blue from July 2025
- Armour: 1 x laser-cut stainless steel shield, 1 x 4" stainless steel razor blade, 1 x copper weight base
- Control: auto and manual mode; RC transmitter/receiver sold separately; on-board start button (controller START, active low)
- USB cable: free, included from 25 Aug 2024
- Packing list (truncated on the product page): 1 x Maker Mini Sumo Controller, 5 x Maker Object, 2 x Maker Reflect S, 2 x 800RPM 6V DC micro metal gearmotor, 1 x 3D printed motor bracket, 2 x silicon wheels 32x22mm, 1 x 7.4V 450mAh LiPo, 1 x chassis (main), 1 x laser-cut stainless steel shield, 1 x 4" stainless steel razor blade, 1 x copper weight base, JST LiPo wire extension, 2561 3-way connector extension wire, ...
- Not included: RC transmitter/receiver; no LiPo charger in the visible packing list
- Differences from the Ikedo Mini Sumo Robot V2 (KIT-IKEDO-MSV2-S): 800 RPM 3.1 kg.cm motors instead of 600 RPM "0.065kg.cm"; 350 g instead of ~200 g; adds steel shield, 4" razor blade and copper weight base; RM693.00 instead of RM418.95
- Warranty: "NO warranty for Sumo Robot."

## Interfaces and compatibility
- Controller: see the Maker Mini Sumo Controller fact sheet (MAKER-MSUMO); opponent sensor Maker Object (MAKER-OBJECT); edge sensor Maker Reflect S (MAKER-REFLECT-S)
- Software: Arduino IDE with the Cytron Maker Sumo Library v1.2.3 (architectures=avr, depends=Servo), linked from the product page; examples AutoSumo, RcSumo, CalibrateEdgeSensors, TestInputs, TestOutputs
- RC (manual) mode: 2-channel RC receiver, forward/reverse channel to GPIO1 and left/right channel to GPIO2 (RcSumo example); robot stops when no pulse is received
- Battery wiring: VB+ = red, VB- = black at the controller's Battery Terminal (shared with the V2 Getting Started guide); Cytron's Pro guide uses a 2-cell LiPo
- Edge sensor wiring: S/OUT = white, +/VCC = red, -/GND = black, using the 2561 3-way wire cut in two (shared with the V2 Getting Started guide)
- Motor wiring: Cytron's Pro guide wires red to MRA and black to MRB, then checks direction with the motor test buttons and swaps if reversed
- Programming: Micro USB-B on the controller; Windows uses the WCH CH341SER driver (CH340 COM port)
- Cytron tutorials linked from the product page include SumoRobot1KG

## Use cases
- Competition mini sumo robot builds ("Pro" bundle with shield, blade and weight base)
- Autonomous sumo robot (auto mode, AutoSumo example)
- Radio-controlled sumo robot (manual mode with a separately bought RC transmitter/receiver)
- One robot entering both RC and autonomous categories (RC receiver on GPIO1/GPIO2 leaves the sensor ports free)

## Known limitations
- No warranty for the Sumo Robot
- RC transmitter/receiver not included; LiPo charger not in the visible packing list
- Product page specifications and packing list are truncated; top cover, screws and screwdrivers are not confirmed
- No Pro-specific assembly document; the Ikedo Bot V2 Getting Started Instruction covers the V2 Starter only
- Controller limits apply: 3.0 A continuous / 6.0 A peak (< 5 s) per motor channel; motors over 3 A are not covered by the controller's warranty (see MAKER-MSUMO)
- 800 RPM motor current rating: [NOT STATED]
- Whether 350 g includes battery, shield, blade and copper base: [NOT STATED]
- Pre-loaded code and Arduino board selection: [NOT STATED]
- Competition weight class on the kit page: [NOT STATED]

## Positioning (kept apart from specs)
- "Pro" bundle of the Ikedo mini sumo line, with armour and weight base added over the V2 Starter
- Controller positioned by Cytron for beginners through professional builders in international Sumo robot competitions (Maker Mini Sumo product page)

## Price band
- RM693.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ikedo-mini-sumo-robot-pro-kit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-ikedo-mini-sumo-robot-pro-kit

# Product fact sheets

## Product name
1KG Sumo Robot Bundles - Radio Controlled (RC)

## Aliases
V-SUMO-1KG-RC, 1KG Sumo Robot Bundles - Radio Controlled (RC), 1KG RC Sumo Robot Bundle, 1KG RC Sumo Robot Kit, RC 1KG Sumo Robot Bundle, 1KG RC Sumo Robot Starter Kit, Radio Controlled 1KG Sumo Robot

## What it is
A plug-and-play, no-coding 1 kg-class sumo robot bundle built on the MDDRC10 R/C motor driver, with two 12 V 580 RPM 3.5 kgf.cm geared motors, 42 x 30 mm silicon wheels, an 11.1 V 1300 mAh LiPo, metal base plates, a 6" stainless steel blade and a 3D-printed PLA body, driven directly from an RC receiver. It is sold as Complete (with body), Basic (without body) or 3D Printed Body only.

## Specs and functions
- Product code: V-SUMO-1KG-RC
- Options: Complete (with body) / Basic (without body) / 3D Printed Body only
- Controller: product page says "Microcontroller: MDDRC10"; the MDDRC10 is an R/C motor driver with no programmable MCU (MDDRC10 datasheet)
- Programming: "plug and play, no coding"
- Motors: 2 x 12V 580RPM 3.5kgfcm high power brushed DC geared motor; Speed 580RPM; Torque 3.5kgfcm
- Body: PLA (3D printed), 15cm x 15cm; STL files in the Cytron Drive folder "KIT-SUMO-RC-3DP"
- Actual weight: 856 g
- Battery: 11.1V 1300mAh LiPo
- Wheels: 2 x silicon wheels 42mm x 30mm
- Blade: 1 x 6" stainless steel blade
- Base: 2 x metal base for mini sumo robot
- Battery lead: Dean T LiPo wire extension
- Control: RC controller
- Packing list, Complete (truncated on the product page): 1 x MDDRC10, 2 x 12V 580RPM 3.5kgfcm high power brushed DC geared motor, 2 x silicon wheels 42x30mm, 1 x LiPo 11.1V 1300mAh, 2 x metal base for mini sumo robot, Dean T LiPo wire extension, 1 x 6" stainless steel blade, ...
- Assembly: "comes in loose parts"
- Warranty: "NO warranty"

## Interfaces and compatibility
- Motor driver: MDDRC10 (see the MDDRC10 fact sheet) — battery to the Power Input Terminal VB+/VB- via the Dean T lead; two bidirectional motor channels; RC receiver on RC1/RC2 with +5V (500 mA max, not for servos) and GND
- MDDRC10 modes: Mixed Mode (RC1 = forward/backward, RC2 = left/right, preferred for differential-drive robots) or Independent Mode (RC1 = left motor, RC2 = right motor), selected by the onboard mode switch; neutral points auto-calibrated at every power-up
- MDDRC10 has no reverse-polarity protection: a reversed battery damages it instantaneously
- No start button, sensors or programmable controller: RC control only
- 3D body STL folder: https://drive.google.com/drive/folders/1ah8zN67osF_GZj4KbN-Ox7QSPSIbz36X
- Cytron tutorials linked from the product page: "1KG RC Sumo Robot Starter Kit User Guide using MDDRC10"; "1KG RC Sumo Robot using MDDRC10"
- Training blade substitute: PCB Plate for Sumo Robot, 15 cm (recommended for 1 kg sumo robots)

## Use cases
- Radio-controlled 1 kg sumo robot for competitions
- Plug-and-play sumo robot build with no coding

## Known limitations
- No warranty
- Comes in loose parts; self-assembly required
- RC only: no autonomous mode, no sensors, no code
- MDDRC10 has no reverse-polarity protection; its +5V output (500 mA) is for the receiver only
- Product page packing list is truncated after the blade; Basic and Body-only contents are not listed in the extract
- RC transmitter/receiver inclusion: [NOT STATED]
- LiPo charger: not in the visible packing list
- Whether 856 g includes battery and blade: [NOT STATED]
- Motor current ratings: [NOT STATED]
- MDDRC10 mode used by the Cytron user guide: [NOT STATED]

## Positioning (kept apart from specs)
- "plug and play, no coding"

## Price band
- RM99.90 - RM633.84 across the three options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-radio-controlled-rc-1kg-sumo-robot-kits

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-radio-controlled-rc-1kg-sumo-robot-kits

# Product fact sheets

## Product name
PCB Plate for Sumo Robot

## Aliases
V-PCB-SUMO-PLATE, PCB Plate for Sumo Robot, PCB Sumo Plate, Sumo PCB Plate, PCB Plate for Blade, Sumo Training Plate

## What it is
A flat plate made of PCB material that stands in for a steel blade on a sumo robot during training and education; it is not intended for official competitions. It comes in a 15 cm size for 1 kg sumo robots and a 10 cm size for 500 g robots.

## Specs and functions
- Product code: V-PCB-SUMO-PLATE
- Options: 15cm / 10cm
- 15CM: 15 cm x 2.3 cm x 0.2 cm; weight 10.6 g; recommended for 1 kg sumo robots
- 10CM: 10 cm x 1.8 cm x 0.1 cm; weight 3.5 g; recommended for 500 g sumo robots
- Material: lightweight PCB material
- Intended use: training/educational blade substitute; "not intended for official competitions"
- Packing list: 1 x plate
- Warranty: 12 months
- Mounting holes and fixing hardware: [NOT STATED]

## Interfaces and compatibility
- Passive mechanical part; no electrical interface
- 1 kg robots: 1KG Sumo Robot Bundles - RC (V-SUMO-1KG-RC); the SUMO:BIT Robot Kit Complete packing list includes "1x PCB Plate for Blade (training)"
- 500 g robots: Ikedo Mini Sumo Robot V2 (KIT-IKEDO-MSV2-S) and Ikedo Mini Sumo Robot Pro Bundle (KIT-IKEDO-MSUMO-P) by size recommendation; chassis mounting compatibility: [NOT STATED]

## Use cases
- Training and educational sumo robot practice in place of a steel blade
- 15 cm plate on 1 kg sumo robots
- 10 cm plate on 500 g sumo robots

## Known limitations
- Not intended for official competitions
- Packing list is the plate only; no screws or bracket
- Mounting hole pattern and compatible chassis: [NOT STATED]
- PCB material grade and copper layer: [NOT STATED]
- Which price applies to which size: [NOT STATED] (only the range is given)

## Positioning (kept apart from specs)
- Training/educational blade substitute

## Price band
- RM5.00 - RM8.00 across the two sizes (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-v-pcb-sumo-plate

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-v-pcb-sumo-plate

# Product fact sheets

## Product name
8 Channel Servo Controller (SC08A)

## Aliases
SC08A, SC08A Servo Controller, 8 Channel Servo Controller, Cytron SC08A, SC08A 8 Channel Servo Controller

## What it is
A stand-alone 8-channel RC servo controller board (PIC16F1827) commanded over 5 V TTL UART at 9600 baud from a PC via UC00A or from a microcontroller. Two boards can be linked to control 16 servos; servo power is a separate supply on a terminal block and there is no on-board regulator.

## Specs and functions
- Servo channels: 8, driven independently (User's Manual V1.0)
- Extendable to 16 channels: two controllers linked together to drive 16 servos (User's Manual V1.0)
- Servo pulse range: 0.5 ms to 2.5 ms (User's Manual V1.0)
- Resolution: 8000 steps = 0.25 µs; pulse width = (0.25 µs × position) + 0.5 ms, position 0–8000 (User's Manual V1.0)
- Optional servo ramping: one of 100 ramp rates per servo; speed byte 0–100, 1 = slowest, 100 = fastest, 0 = faster than 100 (User's Manual V1.0)
- Servo activation for each channel: any channel can be activated or deactivated; initial status is deactivated (User's Manual V1.0)
- Optional position reporting: request the position of an individual servo; 2-byte reply (User's Manual V1.0)
- Independent starting position command for each channel, applied at the next start-up, 0–8000; reply byte 0x04 (User's Manual V1.0)
- UART: 9600 baud rate, TTL level (User's Manual V1.0)
- UART command set: activate/deactivate (mode 110, 2 bytes), position and speed (mode 111, 4 bytes), position reporting (mode 101, 1 byte), starting position (mode 100, 3 bytes); channel 0 = all channels (User's Manual V1.0)
- Controller supply: 5 V, from UC00A (PC use) or shared from the host microcontroller board (User's Manual V1.0)
- Servo supply: independent source on the blue terminal block; 4.8 V to 9 V (standard 4.8 V to 6.0 V); some servos need 7.2 V (User's Manual V1.0)
- Microcontroller: PIC16F1827 (User's Manual V1.0)
- JP11 mini jumper: "1-8" for a single board or the first board, "9-16" for the second board (User's Manual V1.0)
- LEDs: orange servo power indicator; green 5 V for PIC indicator (User's Manual V1.0)
- Buttons: servo test (drives servos to the end position); reset (stops all pulse generation, servos free-run) (User's Manual V1.0)
- Connectors: two 4-way UART/expansion headers (U_1, U_2) (User's Manual V1.0)
- Packing list: 1 × SC08A main board, 1 × 2510H-04 connector with terminal pins, 1 × 2561-04 connector with terminal pins, 1 × mini jumper for JP11 (User's Manual V1.0)
- Warranty: 6 months (User's Manual V1.0); 12 months (product page, read 2026-10-16)

## Interfaces and compatibility
- PC: UC00A USB-to-UART converter plugged into the 4-way UART connector; driver creates a virtual COM port; SC08A takes its 5 V from the UC00A (User's Manual V1.0)
- Microcontroller: 5 V TTL UART and 5 V supply, minimum 3 wires; TX/RX cross-connected; SC08A TX only needed for position reporting (User's Manual V1.0)
- Only one host (computer or microcontroller) may be connected at a time (User's Manual V1.0)
- Expansion: second SC08A joined by a separate 4-way interlink cable via U_1 or U_2; board 2 jumper at "9-16"; board 2 channel S1 is addressed as S9 (User's Manual V1.0)
- Sample code: SK40C_16F877A_SC08A (PICC Lite, PIC16F877A on SK40C, also PIC16F876A) (User's Manual V1.0); GitHub SC08A_PIC16F877A (Feb 2011, Apr 2014) and SC08A_PIC18F4520 (May 2012) (GitHub)
- PC GUI "SC08A Servo Control Panel" for 8 or 16 servos; GitHub GUI_SC08A, VB 2010 Express project, July 2012 (User's Manual V1.0, GitHub)
- Wireless servo control tutorial with XBee series 1 and SKXBee (GitHub)
- Servo named in the manual's speed table: Cytron C36S (User's Manual V1.0)

## Use cases
- Driving 8 RC servos from a PC through UC00A and the SC08A Servo Control Panel
- Driving RC servos from a PIC microcontroller (SK40C) over UART
- Linking two boards for 16-servo projects
- Wireless servo control over XBee (Cytron tutorial)
- Robotics using RC servos: humanoid robots, biologically inspired robots, robotic arms (User's Manual framing)

## Known limitations
- No on-board regulator: the servo supply goes directly to the servos; over-supply voltage may spoil the servo motor (User's Manual V1.0)
- Servo power must be connected correctly before servos are plugged in, else all servo motors will be damaged (User's Manual V1.0)
- Servo headers are not polarised; a servo plugged in backwards may be destroyed (User's Manual V1.0)
- Controller needs its own 5 V from the UC00A or the host (User's Manual V1.0)
- Only one host may be connected at a time (User's Manual V1.0)
- The expansion cable must not be used to connect the SC08A to a microcontroller (User's Manual V1.0)
- Wrong UART connection can spoil the SC08A and the host (User's Manual V1.0)
- Position reporting is not executed for channel 0 (User's Manual V1.0)
- Reset stops all pulses; servos free-run until re-activated (User's Manual V1.0)
- Only UART at 9600 baud is described; no I2C, SPI, PWM-input or RC receiver input, and no baud-rate change command (User's Manual V1.0)
- Pulse-width-to-angle correspondence varies between servo manufacturers (User's Manual V1.0)
- Speed-vs-time figures are approximate and vary with the servo (User's Manual V1.0)

## Positioning (kept apart from specs)
- User's Manual: 8-channel servo controller, extendable to 16 channels, with position reporting, per-channel activation, start-up position and ramping, for RC servo robotics (humanoid, biologically inspired robots, robotic arms)

## Price band
RM65.10 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-8-channel-servo-controller

## Datasheet
https://drive.google.com/file/d/0BzFWfMiqqjyqem1oQnlXUk4yaXc/view

## Source type
Datasheet

## Source link
https://www.gotronic.fr/pj2-38783-nt-3349.pdf

# Product fact sheets

## Product name
RCSwitch10 - RC controlled Relay Switch (RCS10A)

## Aliases
RCS10A, RCSwitch10, RCSwitch10 - RC controlled Relay Switch, RC Controlled Relay Switch, Cytron RCSwitch10, Cytron RC Relay Switch

## What it is
An RC controlled relay switch that can be turned on and off by using an RC controller. It has one single pole, double throw relay.

## Specs and functions
- Relay type: Single pole, double throw (product page)
- Max voltage: 250VAC, 30VDC (product page)
- Max current: 10A (product page)
- Dimension: 43.4mm x 38.3mm x 17.4mm (product page)
- Control: turned on and off by using an RC controller (product page)
- Warranty: 12 months (product page)
- RC input pulse widths, switching threshold and failsafe behaviour: [NOT STATED]
- Supply voltage and current of the switch board: [NOT STATED]
- Package contents: [NOT STATED]

## Interfaces and compatibility
- Input: RC controller (product page); connector type and pin order [NOT STATED]
- Output: one SPDT relay contact set rated 250VAC, 30VDC, 10A (product page)
- Compatible RC receivers/transmitters: [NOT STATED]
- Software: none required; operated by an RC controller (product page)
- Fritzing part linked from the product page

## Use cases
- Powerful auxiliary weapons in RC combat tournament
- Glow plugs on nitro RC vehicles
- High powered lighting system on RC aircraft, boats and cars
- Domestic appliances and home automation
- Non-critical automotive electrics like glow wire

## Known limitations
- No Cytron datasheet or user manual is available; the product page's connection-diagram link returns "not found"
- RC signal thresholds and failsafe (signal-loss) behaviour are not published
- Board supply voltage, current draw, connector type and package contents are not stated
- Contact rating is given only as 250VAC, 30VDC, 10A; no load-type derating is stated

## Positioning (kept apart from specs)
- Product page frames it for RC hobby use (RC combat, nitro RC vehicles, RC aircraft, boats and cars) as well as domestic appliances and home automation

## Price band
RM40.95 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch

# Product fact sheets

## Product name
UC00C (CH340) USB to UART Converter

## Aliases
UC00C, UC00C CH340, CH340 USB to UART Converter, Cytron UC00C, Cytron USB to UART Converter UC00C

## What it is
A small USB-powered converter board that gives a computer a virtual COM port and connects it directly to a microcontroller's TTL UART at 3.3 V or 5 V logic. It plugs onto Arduino-style bootloader headers (Pro Mini, BBFuino, Fio) for program loading.

## Specs and functions
- USB-to-UART chip: "USB to UART chip", not named (user manual); CH340 (product page title)
- USB connector: USB Micro-B socket
- Power: USB powered, no external source required; "5V from USB port is available for user"
- UART logic level: 3.3 V or 5 V TTL, set by the VCC selectable slide switch (label F)
- VCC output pin: 3.3 V or 5 V, follows the switch
- 6-way header socket: DTR, RX, TX, VCC, CTS, GND
- DTR: used for auto-reset on Arduino-compatible boards
- CTS: hardware handshaking pin
- LEDs: Power LED (green), RX LED, TX LED (RX/TX LEDs work only when connected to a PC over USB)
- Driver: plug and play, driver needed for first-time use only; appears as a Virtual COM port
- Operating systems stated: Windows 7, 8 and 10
- Dimension: 3.9 cm x 2 cm
- Packing list: 1 x UC00C (USB Micro-B cable optional, not included)
- Warranty: 1 year (user manual); 12 months (product page)
- Baud rate range, VCC/5V output current, supply current, operating temperature: [NOT STATED]

## Interfaces and compatibility
- Host: PC USB port (Micro-B cable)
- Target: any 3.3 V or 5 V TTL UART device; "development between computer and microcontroller, 3.3V or 5V logic"
- Bootloader compatible: BBFuino, Boarduino, Arduino Mini Pro "etc."; header socket reserved for loading program to Arduino Mini Pro, BBFuino, Fio and others
- Driver links (product page): Windows CH341SER V3.5 Mar2019 https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view ; Mac CH341SER_MAC V1.5 Mar2019 https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view ; Linux CH341SER_LINUX V1.5 Mar2019 https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view ; Mac troubleshooting https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf
- User manual (2016) states "Linux normally pre-installed with the proper driver"

## Use cases
- Serial communication between a microcontroller and a PC through a virtual COM port
- Loading program into Arduino boards without an onboard USB chip (Arduino Mini Pro, BBFuino, Fio, Boarduino)
- Replacing the old PC serial port (DB9) plus RS232 level shifter path with a USB connection

## Known limitations
- "Vsel" and "5V" are supplied directly from the computer's USB port; it is advised not to use this power to power application circuits or devices; wrong polarity, wrong voltage or a short might permanently damage the computer
- Only CTS is broken out as a handshake pin; RTS, DSR, DCD and RI are not on the 6-way socket
- USB powered only; no external power input
- Does not provide RS232 levels (TTL UART only)
- The user manual names only Windows 7, 8 and 10; Windows 11 and current macOS support are not stated
- Driver installation is required once before the COM port appears

## Positioning (kept apart from specs)
- "Low cost, easy to use USB to UART converter" aimed at development between computer and microcontroller (user manual)
- "USB plug and play, direct interface with microcontroller" (user manual)

## Price band
RM15.75 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-uc00c-ch340-usb-to-uart-converter

## Datasheet
https://docs.google.com/document/d/1adRsDAq_2xHbCvTTBw_mdcA3iCzYsW2S5WuDaZOizjc/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1adRsDAq_2xHbCvTTBw_mdcA3iCzYsW2S5WuDaZOizjc/view

# Product fact sheets

## Product name
UC00A (FTDI) USB to UART Converter

## Aliases
UC00A, UC00A Rev3.0, UC00A R3, FTDI USB to UART Converter, Cytron UC00A, Cytron USB to UART Converter UC00A

## What it is
A USB-powered USB-to-UART converter built on an FTDI chip that gives a computer a virtual COM port and connects directly to a 3.3 V or 5 V TTL UART device. Rev3.0 (current) has a USB Micro-B socket, a 3.3V/5V slide switch and a standard 6-way header socket for Arduino-style bootloader headers.

## Specs and functions
- USB-to-UART chip: "FTDI chip" (user manual); FT232RL (Rev3.0 schematic linked from product page)
- USB connector: USB Micro-B socket
- Power: USB powered, no external source required
- UART logic level: 3.3 V or 5 V TTL, set by Vsel slide switch (label G); default Vsel is 5V
- Standard 6-way header socket: DTR, RXI, TXO, VCC, CTS, GND (DTR marked Green, GND marked Black)
- VCC pin: 3.3 V or 5 V output, follows Vsel
- Extra UART pins (JP4/JP6): 5V, GND, CTS, DCD, DSR, RI, RX, RTS, DTR, TX; logic level follows Vsel
- 5V pin: constant 5 V from USB, not affected by Vsel; maximum current "limited from USB port, normally is 900mA"
- DTR: used for auto-reset on Arduino-compatible boards
- CTS, DCD, DSR, RI, RTS: "unused under normal UART operation"
- LEDs: Power LED (green), FTDI TX indicator LED, FTDI RX indicator LED
- Driver: plug and play, FTDI driver needed for first-time use only; appears as a Virtual COM port
- Operating systems stated: Windows XP, Vista, 7, 8 and 10
- Dimension (Rev3.0): 4.4 cm x 2 cm
- Packing list: 1 x UC00A Rev3.0 (USB Micro-B cable optional, not included)
- Warranty: 6 months (Rev3.0 user manual, Dec 2018); 12 months (product page, 2026-10-16)
- Revision history: Rev1.0 (2008) USB-A plug, 5 V only, 4-way 2510 pin header, 5V max 200 mA; Rev2.0 (2012) Mini USB, Vsel solder jumper, 4-way 2510 connector plus 6-way socket, 5V max 250 mA, 3.3V max 50 mA, 3.9 cm x 2 cm; Rev3.0 (current) Micro-B, slide switch, 6-way socket plus JP4/JP6, no 2510 connector
- Baud rate range, VCC output current (Rev3.0), supply current, operating temperature: [NOT STATED]

## Interfaces and compatibility
- Host: PC USB port (Micro-B cable)
- Target: "any device which offer 3.3V/5V UART interface, this includes microcontroller, RFID reader, XBee, Bluetooth, WiFi, wireless module and more"
- Bootloader compatible: BBFuino, Boarduino, Arduino Mini Pro "etc."; 6-way socket used for loading program to Arduino Pro Mini, BBFuino, Fio and others
- Program loading stated for Arduino Pro Mini, Arduino FIO, ArduPilot, Rainbow LED Ring V3, BBFuino
- Arduino Pro Mini wiring: DTR (Green) to RESET, RX to TXD, TX to RXD, Vsel to 5V, CTS to GND, GND (Black) to GND
- PC-to-PC link: two UC00A cross-wired RXI to TXO, TXO to RXI, GND to GND, same baud on both PCs
- Drivers: FTDI VCP driver; manual links Driver Installation Guide for Win 7 https://drive.google.com/file/d/12HDo0o2ygGj9s0I90drnNp0FnFZG2jAx/view and FTDI driver page http://www.ftdichip.com/FTDrivers.htm
- Schematic Rev3.0: https://drive.google.com/file/d/15aQuzmaxM7FiHtMJkuptoebEAMuz-Wip/view

## Use cases
- Serial communication between a microcontroller or UART module and a PC through a virtual COM port
- Loading program into Arduino boards without an onboard USB chip (Arduino Pro Mini, FIO, BBFuino, ArduPilot, Rainbow LED Ring V3)
- Testing a UART device (example: SKPS PS2 controller converter) from a PC terminal
- Communication between two PCs using two UC00A boards

## Known limitations
- "Vsel" and "5V" are supplied directly from the computer's USB port; it is advised not to use this power to power application circuits or devices; wrong polarity, wrong voltage or a short might permanently damage the computer
- Handshake pins CTS, DCD, DSR, RI, RTS and DTR are "unused under normal UART operation"
- USB powered only; no external power input
- TTL UART only; does not provide RS232 levels
- Rev3.0 has no 4-way 2510 connector (Rev1.0/Rev2.0 cables do not apply)
- The user manual names only Windows XP to Windows 10; Windows 11 and current macOS support are not stated
- Driver installation is required once before the COM port appears
- Warranty differs between user manual (6 months) and product page (12 months)

## Positioning (kept apart from specs)
- "Low cost, easy to use USB to UART converter" aimed at development between computer and microcontroller (user manual)
- "USB plug and play, direct interface with microcontroller and it provides 5V power supply from USB port" (user manual)

## Price band
RM43.05 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-uc00a-ftdi-usb-to-uart-converter

## Datasheet
https://docs.google.com/document/d/1pFK7DSRuZB7SeP3aCmjYzWB0i7aT-C_W_D-x25WLops/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1pFK7DSRuZB7SeP3aCmjYzWB0i7aT-C_W_D-x25WLops/view

# Product fact sheets

## Product name
TTL UART to RS232 Converter (URS232A)

## Aliases
URS232A, TTL UART to RS232 Converter, Cytron TTL UART to RS232 Converter, UART to RS232 Converter, Cytron URS232A

## What it is
A level-shifter board between a microcontroller's TTL UART and RS232 (DB9) devices such as a GSM modem or RFID reader. It uses the MAX232 and comes pre-soldered with a male DB9 connector, the MAX232 and capacitors.

## Specs and functions
- Level-shifter IC: MAX232 (product page)
- RS232 connector: DB9-Male (PC side) (product page)
- Signals supported: Tx, Rx, CTS and RTS (product page)
- Assembly: pre-soldered male DB9 connector, MAX232 and capacitors (product page)
- Warranty: 12 months (product page)
- Supply voltage: [NOT STATED]
- TTL logic level (3.3V/5V): [NOT STATED]
- Baud rate range: [NOT STATED]
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Microcontroller side: TTL UART with Tx, Rx, CTS and RTS (product page); connector type and pin order [NOT STATED]
- Device side: DB9-Male (PC side) RS232 connector (product page)
- Works with Cytron UC00A or UC00C to make a USB-to-RS232 converter (product page)
- UC00C's 6-way socket has no RTS pin, so RTS handshake is not available from UC00C as documented (UC00C user manual, via KB)
- Software: none needed on the board

## Use cases
- Interfacing a microcontroller with RS232 devices such as a GSM modem or RFID reader
- Making a USB-to-RS232 converter together with UC00A or UC00C

## Known limitations
- No Cytron datasheet or user manual; the product page is the only Cytron text source
- Supply voltage, logic level and TTL-side pinout are not stated
- The schematic linked from the product page could not be read for this fact sheet
- The DB9 is male (PC side), the same gender as a PC serial port
- The product page's "Serial Loopback Test" tutorial link returns 404

## Positioning (kept apart from specs)
- Product page frames it as the way to connect microcontroller projects to RS232 devices and, with UC00A or UC00C, to build a USB-to-RS232 converter

## Price band
RM22.05 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ttl-uart-to-rs232-converter

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-ttl-uart-to-rs232-converter

# Product fact sheets

## Product name
Breakout Board PS2 Connector (BB-PSC)

## Aliases
BB-PSC, Breakout Board PS2 Connector, Cytron Breakout Board PS2 Connector, PS2 Connector Breakout Board, PS2 Breakout Board

## What it is
A breakout board with a PS2 connector (female) pre-soldered on the PCB and its pins broken out to 0.1" for use on a breadboard or donut board. It lets a PS2 controller be wired directly to a microcontroller's pins.

## Specs and functions
- Connector: PS2 Connector (Female), pre-soldered on the PCB (product page)
- Pins broken out to 0.1" (product page)
- Mounting: breadboard or donut board (product page)
- Signals wired in Cytron's tutorial: DATA, CMD, ATT, CLK, +5V, GND (Cytron tutorial "Maker Mini Sumo with PS2 Controller")
- Number of pins and pin order: [NOT STATED]
- Dimensions: [NOT STATED]
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Maker Mini Sumo wiring (Cytron tutorial): DATA → D2 (START), CMD → D7 (OPP_FR), ATT → D6 (OPP_FC), CLK → D5 (OPP_FL), +5V → any + terminal, GND → any − terminal
- Library: Arduino PS2X library (Cytron GitHub, https://github.com/CytronTechnologies/PS2X_lib); tutorial uses ps2x.config_gamepad(5,7,6,2,true,true), argument order clk, cmd, att, dat, pressures, rumble
- Tutorial controller: Wireless PS2 Controller (Compatible), 2.4GHz, about 10 m range, 2 AAA batteries
- Different from SHIELD-PS2, which converts the PS2 controller to UART and uses a different library

## Use cases
- Connecting a PS2 controller connector to a breadboard or donut board
- Controlling a Maker Mini Sumo robot with a wireless PS2 controller (Cytron tutorial)

## Known limitations
- No Cytron datasheet or user manual; product page and one Cytron tutorial are the sources
- Pin count, pin order and dimensions are not stated
- Supply-voltage rating for the connected PS2 receiver is not stated (the tutorial uses +5V)
- On Maker Mini Sumo all Object Sensors must be removed when connecting the PS2 breakout (Cytron tutorial)
- On Maker Mini Sumo the PS2X example pins (13, 11, 10, 12) must be changed to (5, 7, 6, 2) (Cytron tutorial)
- Press reset after connecting (Cytron tutorial)

## Positioning (kept apart from specs)
- Product page frames it as a pre-soldered PS2 connector broken out for breadboard or donut board use

## Price band
RM9.45 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-breakout-board-ps2-connector

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/tutorial/maker-mini-sumo-with-ps2-controller

# Product fact sheets

## Product name
Breakoutboard for SPG10 (BB-SPG10)

## Aliases
BB-SPG10, Breakoutboard for SPG10, Breakout Board for SPG10, SPG10 Breakout Board, Cytron BB-SPG10

## What it is
A small breakout board that mounts to the rear of the SPG10 DC brush motor to give it a secure power cable. It needs two-point soldering and comes with a 2-way cable with the proper jack.

## Specs and functions
- Designed to fit SPG10 DC brushed motor (product page)
- Tiny, compact (product page)
- Requires two-point soldering, about 1 minute (product page)
- Mounts to the back/rear of the SPG10 motor (product page)
- Centre hole allows rear shaft access (product page)
- Ready with JST socket and cable/wire; 2-way cable included with the proper jack (product page)
- Additional terminal pads for soldering if a cable is not preferred (product page)
- User manual: none ("quite self explanatory") (product page)
- Dimensions: [NOT STATED]
- JST series, pitch and cable length: [NOT STATED]
- Current and voltage rating: [NOT STATED]
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Motor side: two solder points to the SPG10 motor (product page)
- Output: JST socket with 2-way cable, or additional terminal pads (product page)
- Compatible motor: SPG10 DC brushed motor (product page); other motors [NOT STATED]
- Software: none

## Use cases
- Giving an SPG10 DC brush motor a secure power cable with a ready jack instead of wires soldered straight to the motor terminals

## Known limitations
- No user manual or datasheet exists (product page)
- Soldering is required
- Dimensions, connector series, cable length and electrical ratings are not stated
- Fit is stated only for the SPG10 DC brushed motor

## Positioning (kept apart from specs)
- Product page: tiny, compact; about 1 minute of soldering; "quite self explanatory"

## Price band
RM3.15 special offer, was RM6.30 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-breakoutboard-for-spg10

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-breakoutboard-for-spg10

# Product fact sheets

## Product name
Maker Line

## Aliases
MAKER-LINE, Maker Line, Maker Line: Simplifying Line Sensor for Beginner, Maker Line Sensor, Cytron Maker Line

## What it is
A line sensor with 5 infrared sensors that gives 5 digital outputs (one per sensor) and 1 analog output for line position. It runs from 3.0–5.5 V and is calibrated with one button.

## Specs and functions
- Product code: MAKER-LINE
- Datasheet: Rev 1.0, July 2019 (spec table titled "Absolute Maximum Ratings")
- VCC voltage: 3.0–5.5 V; reverse polarity protection on VCC and GND
- Sensors: 5 infrared line sensors (S1–S5)
- Digital outputs D1–D5: one per sensor, High when the line is detected; low level 0–0.5 V, high level 0.7×VCC to VCC
- Analog output AN: 0 to VCC; voltage represents line position
- Analog output vs position: line not found < 0.1 × Vcc; Left 0.1 × Vcc; Center Vcc / 2; Right 0.9 × Vcc; cross detected (all sensors on) > 0.9 × Vcc
- Analog output at Vcc = 5 V: 0–0.5 V not found, 0.5 V left, 2.5 V center, 4.5 V right, 4.5–5 V cross; at Vcc = 3.3 V: 0–0.33 V, 0.33 V, 1.65 V, 2.97 V, 2.97–3.3 V
- Sensing distance: 4–40 mm (VCC = 5V, black line on white surface); may reduce if VCC is less than 5V or contrast is low
- Sensor refresh rate: 200 Hz
- Recommended line width: 13–30 mm
- Line Color Switch: Light / Dark
- Digital truth table: Light switch + light surface = High; Light + dark = Low; Dark + light = Low; Dark + dark = High
- Calibration: mount the sensor as used and power up; set the line colour switch; press and hold the calibrate button for more than 2 seconds; all 5 LEDs blink in calibration mode; move the sensor across the line so all sensors see it; press the button again to exit
- Calibration result: running light = successful; fast blink = failed (contrast too low or sensor too high)
- Calibration can also be entered/exited by shorting CAL to GND
- Calibration data saved in EEPROM, kept after power-off; recalibrate only if sensor height, line or background colour changes
- Indicators: power LED; 5 sensor LEDs (on when the line is detected)
- Dimensions: [NOT STATED]
- Current consumption: [NOT STATED]
- Sensor spacing: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- I/O connector pins: VCC, GND, AN, CAL, D1, D2, D3, D4, D5
- Product listing: "DC 3.3V and 5V compatible (With reverse polarity protection)"
- Product listing: "Support wide range of controllers such as Arduino, Raspberry Pi, etc."
- Connection diagrams for digital output and analog output in the datasheet
- Software library / example code: [NOT STATED]
- Packing list: 1 x Maker Line; 2 x 5mm PCB stand (screw and nut); 2 x 10mm PCB stand (screw and nut); 2 x M3 screw 4mm; 2 x M3 nut

## Use cases
- Line following mobile robot for school project or competition
- Automated Guided Vehicle (AGV) for industrial use
- Precise line-following control such as PID using the analog output

## Known limitations
- VCC absolute maximum 5.5 V (minimum 3.0 V)
- Sensing distance 4–40 mm is specified at VCC = 5V with a black line on white; it may reduce at lower VCC or low contrast
- Recommended line width 13–30 mm
- Digital outputs swing to VCC (high level 0.7×VCC to VCC); analog output spans 0 to VCC
- Must be calibrated before use; sensor height must not change during calibration; recalibrate after changing height, line colour or background colour
- Calibration fails if contrast is too low or the sensor is too high from the surface
- Analog output below 0.1 × Vcc means line not found; above 0.9 × Vcc means cross detected

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Line Sensor for Beginner"
- Product listing: no need to adjust a potentiometer for each sensor; "easy calibration process"
- Product listing: "Analog output also offers higher resolution compared to individual digital outputs"

## Price band
- USD 9.90 on Cytron's Tindie store (sold out since Jan 28, 2024), checked 16 Oct 2026

## Product page
https://my.cytron.io/p-maker-line-simplifying-line-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1wZwWl72CKkajTDIyiMxSQ3bwXbWbqW0eq7rdg2MUPeU/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1wZwWl72CKkajTDIyiMxSQ3bwXbWbqW0eq7rdg2MUPeU/edit

# Product fact sheets

## Product name
Maker Object

## Aliases
MAKER-OBJECT, Maker Object, Maker Object Sensor, Cytron Maker Object, Maker Object: Simplifying Object Sensor for Beginner

## What it is
A small digital infrared object sensor. It sends modulated IR light and pulls its output LOW when it picks up IR light reflected from an object within the set range.

## Specs and functions
- Product code: MAKER-OBJECT
- VCC voltage: 4.5 V min, 5.5 V max
- Output: NPN output with internal pull-up; LOW when an object is detected (active low)
- Output voltage, object detected: 0 V min, 0.8 V max
- Output voltage, no object detected: VCC - 0.5 V min, VCC max
- Sensing distance (adjustable), white surface (A4 size): 40 cm min, 140 cm max
- Sensing distance (adjustable), black surface (A4 size): 15 cm min, 60 cm max
- Response time (based on IR sensor's datasheet): 180 µs min, 350 µs max
- IR transmitter: infrared LED that transmits modulated infrared light
- IR receiver with built-in 38kHz bandpass filter
- Sensing range trimmer, adjusted with a small Phillips head screwdriver through a small opening at the front of the sensor
- Maximum distance setting: power on, turn the trimmer clockwise until the output LED turns off, then counter-clockwise slowly until the LED just turns on
- Minimum distance setting: power on, turn the trimmer counter-clockwise until the output LED turns off, then clockwise slowly until the LED just turns on
- Power LED (on when powered); Output LED (on when an object is detected)
- Reverse polarity protection on the power input
- Gives a detected / not-detected signal only, not a distance value
- Datasheet: Rev 1.0, December 2019
- Dimensions: [NOT STATED]
- Supply current: [NOT STATED]
- IR LED / IR receiver part numbers: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- 3-pin connector: 5V (power input), GND (ground), OUT (NPN output with internal pull-up, active low)
- Not a Grove or Maker Port connector
- Read OUT as a plain digital input; no library needed
- Maker Mini Sumo Controller: 5 opponent-sensor ports, pulled up to +5V, active low, with status LEDs; MAKER-OBJECT ports on the bottom layer are wired in parallel
- Cytron Maker Sumo Library (Arduino): opponent inputs OPP_FC (D6), OPP_FL (D5), OPP_FR (D7), OPP_L (D12), OPP_R (D13); AutoSumo example treats LOW as opponent detected
- Ikedo Mini Sumo Robot V2 kit includes 5 x Maker Object Sensor (opponent)
- Compatible boards listed in the datasheet: [NOT STATED]
- MicroPython / CircuitPython / MakeCode examples: [NOT STATED]

## Use cases
- Object detection: reflected IR light from an object turns the output LOW
- Opponent sensor in sumo robots (Ikedo Mini Sumo Robot V2 kit, with the Maker Mini Sumo Controller)

## Known limitations
- VCC must be 4.5–5.5 V; not for a 3.3 V supply
- Output HIGH (no object) is VCC - 0.5 V to VCC, close to the 5 V supply
- Sensing range depends on the target: 40–140 cm on a white A4-size surface but only 15–60 cm on a black A4-size surface
- Range is set by hand with the trimmer, not in code
- Digital output only; no distance reading
- Response time figure is taken from the IR sensor's datasheet
- Supply current and output current: [NOT STATED]

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying Object Sensor for Beginner"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-maker-object-simplifying-object-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1SppJcAoTFGFDSaeBXrI4Ocq24quq-5ybFpr2bNsGMOI/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1SppJcAoTFGFDSaeBXrI4Ocq24quq-5ybFpr2bNsGMOI/edit

# Product fact sheets

## Product name
Maker Reflect: Simplifying IR Reflectance Sensor for Beginner (MAKER-REFLECT)

## Aliases
MAKER-REFLECT, V-MAKER-REFLECT, Maker Reflect, Cytron Maker Reflect, Maker Reflect: Simplifying IR Reflectance Sensor for Beginner, Maker Reflect IR Reflectance Sensor, Maker Reflectance Sensor, Analog Reflectance Sensor (Line Detector)

## What it is
A tiny analog infrared reflectance sensor (line detector) with a 3-pin VCC/GND/OUT connector; its analog output voltage rises on darker surfaces. It runs from 3.0 V to 5.5 V and senses 1 mm to 40 mm at VCC = 5 V with a black line on a white surface.

## Specs and functions
- Sensor type: IR Reflectance Sensor — infrared sensors for line detection (datasheet)
- VCC voltage: 3.0 V min, 5.5 V max (datasheet absolute maximum ratings)
- Analog output voltage: 0 V min, VCC max (datasheet)
- Output rule: higher voltage = darker surface (datasheet)
- Sensing distance: 1 mm min, 40 mm max, at VCC = 5 V with a black line on white surface (datasheet)
- Sensing distance may reduce if VCC is less than 5 V or the line-background contrast is low (datasheet)
- Reverse polarity protection: none — "Reversed Polarity will damage the sensor" (datasheet)
- On-board threshold, trimmer, calibration or switch: none listed (datasheet)
- Indicator LED: none listed (datasheet)
- Supply current: [NOT STATED]
- Sensor IC / IR part number: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Operating temperature: [NOT STATED]
- Datasheet: MAKER-REFLECT Datasheet, "Analog Reflectance Sensor (Line Detector)", Rev 1.0, November 2019
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Connector: 3 pins — VCC (power input), GND (ground), OUT (analog output)
- Read with any analog input (ADC) pin; no library needed
- Compatible boards named in the datasheet: [NOT STATED]
- SUMO:BIT edge-sensor ports accept "Maker Reflect or any other analog sensors" (SUMO:BIT datasheet)
- Maker Mini Sumo Controller edge ports (A0/A1, analog) are read with the Cytron Maker Sumo Library (Maker Mini Sumo datasheet and library)
- Sold on the same product page as the newer Maker Reflect S (option "Maker Reflect S", code MAKER-REFLECT-S); the product page says "The new Maker Reflect S comes with a smaller threshold sensing for more stable output"
- Documents linked from the product page: datasheet only

## Use cases
- Line detection (datasheet: "Infrared sensors for line detection")
- Edge sensor for sumo robots (SUMO:BIT and Maker Mini Sumo edge-sensor ports)

## Known limitations
- Analog output only; the threshold must be set in code
- Reversed polarity will damage the sensor (no reverse polarity protection)
- Sensing distance of 1 mm to 40 mm applies at VCC = 5 V with a black line on white; it reduces at lower VCC or low contrast
- Supply current, dimensions and sensor part number are not stated in the datasheet
- No Cytron library or code example

## Positioning (kept apart from specs)
- "Simplifying IR Reflectance Sensor for Beginner" (product page title)
- Cytron's beginner-series reflectance sensor; the newer Maker Reflect S is positioned as the more stable-output option on the same page

## Price band
RM8.00–RM9.00 depending on option (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-reflect-ir-reflectance-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1RdldHYXGyjtmrZmqSi-gXY-nAEqwA7t_kV5X4JFv7qE/edit

# Product fact sheets

## Product name
Maker Reflect S (MAKER-REFLECT-S)

## Aliases
MAKER-REFLECT-S, Maker Reflect S, Cytron Maker Reflect S, Maker Reflect-S, MakerReflectS

## What it is
The newer "S" variant of the Maker Reflect infrared reflectance sensor (line detector) with the same 3-pin VCC/GND/OUT connector; its output is higher on darker surfaces and its datasheet lists it as digital-IO compatible with no ADC required. It is a 5 VDC sensor with an optimal sensing distance of 3 mm.

## Specs and functions
- Sensor type: IR Reflectance Sensor — infrared sensors for line detection (datasheet)
- Operating voltage: 5VDC (datasheet)
- Supply current: 25mA (datasheet)
- Digital IO Compatible (datasheet)
- No ADC required (datasheet)
- Optimal sensing distance: 3mm (0.125") (datasheet)
- Output: "OUT : Analog output. Higher voltage = darker surface." (datasheet connector table)
- Threshold: "The new Maker Reflect S comes with a smaller threshold sensing for more stable output" (product page); no numeric threshold stated
- Reverse polarity protection: none — "Reversed Polarity will damage the sensor" (datasheet)
- On-board adjustment, trimmer or switch: none listed (datasheet)
- Indicator LED: none listed (datasheet)
- Supply voltage min/max: [NOT STATED]
- Sensing distance min/max: [NOT STATED]
- Output voltage levels: [NOT STATED]
- Sensor IC / IR part number: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Operating temperature: [NOT STATED]
- Datasheet: MAKER-REFLECT-S Datasheet, "Analog Reflectance Sensor (Line Detector)", Rev 1.0, February 2026
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Connector: 3 pins — VCC (power input), GND (ground), OUT (output)
- Readable on a digital input pin (datasheet: "Digital IO Compatible", "No ADC required") or an analog input (datasheet: "Analog output")
- Compatible boards named in the datasheet: [NOT STATED]
- Sold as the option "Maker Reflect S" on the Maker Reflect product page (code MAKER-REFLECT-S)
- The Ikedo Mini Sumo Robot V2 product page lists its edge sensors as "Maker Reflect S"; the Ikedo V2 Getting Started guide calls them "Maker Reflectance Sensor" and links the older Maker Reflect page; neither Reflect datasheet mentions the Ikedo kit
- Documents linked from the product page: datasheet only

## Use cases
- Line detection (datasheet: "Infrared sensors for line detection")
- Edge sensor on sumo robots (Ikedo Mini Sumo Robot V2 product page)

## Known limitations
- Only 5VDC is stated as the operating voltage; 3.3 V operation is not stated
- Reversed polarity will damage the sensor (no reverse polarity protection)
- Only the 3 mm optimal sensing distance is stated; no minimum/maximum range
- The datasheet calls OUT an analog output and also says "Digital IO Compatible / No ADC required"; output voltage levels are not stated
- Dimensions and sensor part number are not stated in the datasheet
- No Cytron library or code example

## Positioning (kept apart from specs)
- "The new Maker Reflect S comes with a smaller threshold sensing for more stable output" (product page)
- Sold under "Maker Reflect: Simplifying IR Reflectance Sensor for Beginner" as the newer option

## Price band
RM8.00–RM9.00 depending on option (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-reflect-ir-reflectance-sensor-for-beginner

## Datasheet
https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1lRTCSQkuwSsE6LYWHZ6CR2ripHQt-P-qIVuzjREYJ18/edit

# Product fact sheets

## Product name
Maker Soil Moisture Sensor (Capacitive) (MAKER-SOIL-MOISTURE)

## Aliases
MAKER-SOIL-MOISTURE, Maker Soil Moisture Sensor, Maker Soil Moisture Sensor (Capacitive), Maker Soil Moisture, Maker Soil Sensor, Maker Soil, Cytron Maker Soil Moisture Sensor, Cytron Soil Moisture Sensor

## What it is
A capacitive soil-moisture sensor on a probe-shaped board with a 4-pin Grove port (GND, VCC, DIS, OUT). It gives an analog output voltage that is higher when the soil has less moisture, has three LED indicators (Blue WET, Green MOIST, Red DRY), and a DIS pin that disables the sensor when HIGH.

## Specs and functions
- Sensing method: capacitive probe used to detect the presence of water in soil (datasheet)
- VCC voltage: 2.5 VDC min, 7.0 VDC max (datasheet absolute ratings)
- Analog output voltage (OUT): 1.0 V min, 5.2 V max (datasheet)
- Output rule: higher voltage = less moisture (datasheet)
- Disable pin threshold voltage (DIS): VCC − 0.8 V min; HIGH signal disables the sensor (datasheet)
- LED turn-on output voltage at VCC = 3.3 V: Blue (WET) 1.4–1.8 V; Green (MOIST) 1.8–2.1 V; Red (DRY) 2.1–2.3 V (datasheet)
- LED turn-on output voltage at VCC = 5.0 V: Blue (WET) 2.3–2.7 V; Green (MOIST) 2.7–3.1 V; Red (DRY) 3.1–3.6 V (datasheet)
- Current consumption: 5.4–5.6 mA at VCC = 3.3 V; 3.6–3.7 mA at VCC = 5.0 V (datasheet)
- Current consumption when disabled: 80–140 µA at VCC = 3.3 V; 140–180 µA at VCC = 5.0 V (datasheet)
- LED indicators turn on depending on the value of the output (datasheet)
- Calibration or threshold adjustment on board: none listed (datasheet)
- Sensor IC: [NOT STATED]
- Reverse polarity protection: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Operating temperature: [NOT STATED]
- Datasheet: MAKER SOIL MOISTURE SENSOR Datasheet, Rev 1.0, January 2022
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Grove port, 4 pins: GND (ground), VCC (power input), DIS (disable pin, HIGH disables), OUT (analog output)
- Read OUT with any analog input (ADC); drive DIS from a digital output if power saving is needed; no library needed
- Compatible boards named in the datasheet: [NOT STATED]
- Cytron board examples that read it on a Grove analog port: Robo Pico (Grove 6, GP27), Robo ESP32 (Grove 7, D36), Maker Uno RP2040 example repo (Cytron GitHub)
- Sold with Grove cable options (product page)
- Documents linked from the product page: datasheet and 3D CAD (https://drive.google.com/file/d/1stZDBLdZ1141wIdrRsNFRAVAT8iRiCNg/view)

## Use cases
- Detect the presence of water in soil (datasheet)
- Soil moisture reading on a Grove analog port of a Cytron board (Cytron GitHub examples)
- Cytron tutorial: 3D Printed Self-Watering Pot featuring Maker Soil Moisture Sensor (2022-03-25)

## Known limitations
- Output voltage can reach 5.2 V; at VCC = 5.0 V the DRY band (3.1–3.6 V) is above a 3.3 V ADC's full scale
- DIS threshold is VCC − 0.8 V, so at VCC = 5 V a 3.3 V GPIO may not reach it
- LED turn-on bands differ between VCC = 3.3 V and VCC = 5.0 V; the output is a relative reading, not a moisture percentage
- Current draw is higher at 3.3 V (5.4–5.6 mA) than at 5.0 V (3.6–3.7 mA)
- Maximum supply is 7.0 VDC
- Sensor IC, reverse polarity protection, dimensions and probe depth are not stated in the datasheet
- Out of stock on my.cytron.io (2026-10-16)

## Positioning (kept apart from specs)
- Cytron "Maker" series sensor: a capacitive (not resistive) soil moisture sensor with Grove connection and LED moisture indicators

## Price band
RM20.58 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-soil-moisture-sensor

## Datasheet
https://docs.google.com/document/d/1XErDF1j2W9LaeTdB7ySIbm4T83_ov0TZtVC47lmC7Pg/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1XErDF1j2W9LaeTdB7ySIbm4T83_ov0TZtVC47lmC7Pg/edit

# Product fact sheets

## Product name
MCP9700 Linear Temperature Sensor (LM35 Compatible) — BCY-TEMP-MCP9700

## Aliases
BCY-TEMP-MCP9700, MCP9700 Linear Temperature Sensor, MCP9700 Linear Temperature Sensor (LM35 Compatible), MCP9700 Temperature Sensor, Cytron MCP9700, MCP9700 Sensor by Cytron

## What it is
A small three-pin breakout board (GND, VCC, OUT) carrying a Microchip MCP9700 analog temperature sensor IC. The output voltage rises 10.0 mV per °C with 500 mV at 0 °C, and the board runs from 2.3 to 5.5 V.

## Specs and functions
- Sensor IC: MCP9700 (Cytron datasheet title and product name); MCP9700 vs MCP9700A grade [NOT STATED]
- VCC voltage: 2.3 V min, 5.5 V max (datasheet)
- Sensor output voltage (VOUT): 100 mV min, 2000 mV max (datasheet)
- Output voltage at TA = 0 °C: 500 mV typ (datasheet)
- Temperature coefficient (TC): 10 mV/°C typ (datasheet)
- Temperature range: −40 °C min, +150 °C max (datasheet)
- Current consumption: 6 µA typ, 12 µA max (datasheet)
- Output current: 100 µA max (datasheet)
- Output type: analog voltage on OUT (datasheet)
- Conversion equation: TA (°C) = (VOUT − 500 mV) / 10 mV/°C (datasheet Section 3)
- Accuracy: [NOT STATED]
- Dimensions: [NOT STATED] (datasheet gives a drawing only)
- Weight: [NOT STATED]
- Reverse-polarity protection: [NOT STATED]
- Datasheet: BCY-TEMP-MCP9700 Linear Temperature Sensor Datasheet, Rev 1.0, August 2023

## Interfaces and compatibility
- Pins: GND (ground), VCC (power input, 2.3–5.5 V), OUT (analog output, 10.0 mV/°C) (datasheet)
- Connector type: [NOT STATED] in datasheet text
- No I²C, SPI, Grove or Maker Port connector named; needs one ADC-capable pin on the host (datasheet)
- Compatible boards named by Cytron: Arduino UNO or Maker UNO, Raspberry Pi Pico (Cytron GitHub example README); "applicable to other microcontroller analog pin" (Cytron GitHub)
- Example code: Arduino (A0, 5 V / 10-bit ADC conversion), CircuitPython (board.GP28, 3.3 V / 65536), MicroPython (machine.ADC(28), 3.3 V / 65536) at https://github.com/CytronTechnologies/Cytron-BCY-TEMP-MCP9700 (Cytron GitHub)
- Warranty: 12 months (product page)

## Use cases
- Reading ambient temperature on an Arduino UNO / Maker UNO analog pin (Cytron GitHub example)
- Reading ambient temperature on a Raspberry Pi Pico with CircuitPython or MicroPython (Cytron GitHub example)

## Known limitations
- Analog output only; no digital interface, library or calibration register (datasheet)
- Output must be corrected for the 500 mV offset at 0 °C; the equation is TA = (VOUT − 500) / 10 (datasheet)
- Output current is limited to 100 µA max; the output is a signal for an ADC pin, not a load driver (datasheet)
- Accuracy is not stated in the Cytron datasheet
- Dimensions are not stated in the datasheet text
- Reverse-polarity protection is not stated

## Positioning (kept apart from specs)
- Product page name: "MCP9700 Linear Temperature Sensor (LM35 Compatible)" (product page); the datasheet does not mention the LM35

## Price band
RM7.77 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-mcp9700-linear-temperature-sensor-by-cytron

## Datasheet
https://docs.google.com/document/d/1Yg4krOVZN__Q0NPKvb4om0IJVZMJksBEIjuhJPlcBTM/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1Yg4krOVZN__Q0NPKvb4om0IJVZMJksBEIjuhJPlcBTM/edit

# Product fact sheets

## Product name
Advanced Auto-Calibrating Line Sensor (LSA08)

## Aliases
LSA08, Advance Line Following Sensor Bar, LSA08 Line Sensor, Cytron LSA08, Advanced Auto Calibrating Line Sensor, Auto-Calibrating Line Sensor Bar

## What it is
An 8-sensor line-following sensor bar with sensors spaced 16 mm apart, an on-board 2x8 LCD with SEL and MODE buttons, and auto-calibration. It outputs the line position over UART, as an analog voltage, or as 8 parallel digital lines, and provides a junction pulse and junction counter.

## Specs and functions
- Sensors: 8 sensor pairs (S0–S7) spaced at 16 mm (user manual)
- Operating voltage: 7.5 V min, 12 V typical, 20 V max (user manual); typical wiring 9–12 V (user manual)
- Current consumption at 12 V: 25.3 mA min, 25.5 mA typical, 130 mA max; "typically around 26mA" (user manual)
- Input signal VIH 2–5 V; VIL 0–0.8 V; output signal 5 V (user manual)
- Maximum current per I/O signal pin: 20 mA (user manual)
- Sensing distance from board: 1 cm min, 3 cm typical, 5 cm max (user manual)
- Minimum line width: 15 mm (user manual)
- Refresh rate: 100 Hz (user manual); Cytron Tindie listing says up to 200 Hz
- Line position: 0 (sensor 0) to 70 (sensor 7), 35 = between S3 and S4, linear (user manual)
- Analog output: 0 V to 4.5 V = position 0 to 70; 5 V = no line; Position = (AN voltage / 4.5 V) x 70 (user manual)
- UART: 1 start bit, 8 data bits, no parity, 1 stop bit; baud settings 0 = 9600, 1 = 19200, 2 = 38400, 3 = 57600, 4 = 115200, 5 = 230400 (user manual)
- UART output modes: 0 = no output; 1 = one byte of sensor digital values (LSB = sensor 0, MSB = sensor 7); 2 = one byte line position 0–70, 255 = no line; 3 = 9-byte raw packet, header 0x00 + 8 raw sensor bytes (user manual)
- UART data streams from TX only while UEN is pulled low (user manual)
- UART command packet: ADDRESS, COMMAND, DATA, CHECKSUM (lower byte of ADDRESS + COMMAND + DATA); max 20 ms between bytes; setting commands answered with "OK" (user manual)
- UART commands: C 0x43 calibrate (0); L 0x4C line mode (0 = Light-On, 1 = Dark-On); T 0x54 threshold (0–7); J 0x4A junction width (3–8); A 0x41 UART address (0–255); B 0x42 LCD backlight (0–10); S 0x53 LCD contrast (0–255); R 0x52 baud setting (0–5); D 0x44 UART output mode (0–3); 0x50 junction information (0 = clear counter, 1 = read counter); 0x4F line/sensor information (1 = sensor byte, 2 = line position) (user manual)
- Default settings: Line Mode Light On; Threshold 4; Junction width 5; UART address 1; Baudrate 0 (9600); UART mode 0; LCD backlight 2 (user manual)
- Calibration: MODE twice to CALB, SEL to start, swing the sensors across bright and dark surfaces; values saved to non-volatile memory; also started by UART command C (user manual)
- Junction pulse (JPULSE): pulse generated each time the bar crosses a junction at least Junction Width sensors wide; internal junction counter readable over UART (user manual)
- LCD: shows line position and bar chart; "****" = no line; backlight 0–10 (0 = off) (user manual)
- Power polarity protection (user manual)
- Dimensions: PCB 135 mm x 45.7 mm; mounting holes 127.3 mm x 38 mm apart; sensor pitch 16 mm (user manual drawing)
- Packing list: 1 x LSA08 PCB, 1 x LSA08 cable connector (user manual)

## Interfaces and compatibility
- Port A (10 pins, pin 1 = square pad): 1 TX, 2 RX, 3 UEN (active low), 4 AN, 5 JPULSE, 6–8 not used, 9 VIN (12 V), 10 GND (user manual)
- Port B (10 pins): 1–8 O0–O7 digital outputs (5 V = line detected), 9 VIN (12 V), 10 GND (user manual)
- Board can be powered from VIN/GND of either Port A or Port B; both ports may be used at once (user manual)
- TX is floating/high-impedance when not sending; RX is weakly pulled up (user manual)
- Multiple LSA08 on one UART by giving each a unique address; multiple on analog need one ADC channel each (user manual)
- Manual example controllers: SK40C with MD10C, MC40A, IFC system (IFC-MB00, IFC-PC00, IFC-AI08, IFC-DI08, IFC-BH02, IFC-BL02, IFC-CP04), MC40SE; DC Geared Mobile Robot Base Set HD-BSC-SPG-G (user manual)
- Software: Cytron LSA08 C library (LSA08.h) for PIC with C Library Manual V1.1 Jan 2013; example projects for SK40C+MD10C, MC40A (analog and UART PID), IFC in GitHub repo https://github.com/CytronTechnologies/Cytron_LSA08 (user manual, GitHub)
- Library position convention: -35 to 35 with centre 0; 127 = no line (library manual)

## Use cases
- Line following for embedded systems or robots (user manual)
- Cross-junction detection and counting using JPULSE or the UART junction counter (user manual)
- Line following on reflective or glossy surfaces and on red, green, blue, white, black or grey surfaces (user manual)
- PID line-following robots with SK40C, MC40A or IFC controllers (user manual)

## Known limitations
- Operating voltage 7.5–20 V; not a 5 V or 3.3 V-powered board (user manual)
- Outputs are 5 V signals; I/O pins limited to 20 mA (user manual)
- Minimum line width 15 mm; sensing distance 1–5 cm (user manual)
- Refresh rate 100 Hz (user manual)
- Default UART mode is 0 (no output); UART data only streams while UEN is low (user manual)
- Incomplete UART packets are discarded after 20 ms (user manual)
- Polling line position by command is slower than streaming with UEN (user manual)
- Only one Cytron library exists and it is for PIC C; no Arduino library (library manual, GitHub)
- Hidden debug mode exits only by power cycling (user manual)
- Manual (2012) states warranty 6 months; product page states 12 months

## Positioning (kept apart from specs)
- "Advance" line sensor bar with LCD and on-board buttons for instant configuration without a computer (user manual)
- Auto-calibration minimises setup effort for line-following robots (user manual)
- Low current consumption and polarity protection (user manual)

## Price band
RM204.75 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-advanced-auto-calibrating-line-sensor

## Datasheet
https://drive.google.com/file/d/0BzFWfMiqqjyqXzFaMTNHMy1pWUE/view

## Source type
Datasheet

## Source link
https://raw.githubusercontent.com/CytronTechnologies/Cytron_LSA08/master/LSA08_User_Manual.pdf

# Product fact sheets

## Product name
Rotary Encoder Kit (RE08A)

## Aliases
RE08A, Rotary Encoder Kit, RE08A Rotary Encoder Kit, Cytron Rotary Encoder Kit, Simple Rotary Encoder Kit, 8-slot Rotary Encoder Kit

## What it is
A single-channel optical rotary encoder kit made of a sensor board with a slotted opto interrupter and an 8-slot disc that gives 16 transitions per revolution. It has a 3-pin interface (+5, Gnd, Sig), a green indicator LED and a pulse output internally pulled up to 5 V.

## Specs and functions
- Disc: 8 slots giving 16 transitions per revolution (user manual)
- Disc size: 35 mm outer diameter x 3 mm inner diameter (user manual)
- Sensor board size: 12 mm (height) x 35 mm (length) x 15 mm (width) (user manual)
- Supply voltage (+5): 4.5 V min, 5 V typical, 5.5 V max (user manual)
- Output: 0 V to 5 V pulses; low 0–1.0 V (0.8 V typical), high 4.5–4.9 V (4.7 V typical) with +5 = 5 V (user manual)
- Output frequency: up to 1 kHz (1000 pulses/sec) (user manual)
- Current at low state: 25 mA min, 30 mA typical, 40 mA max (user manual)
- Current at high state: 5 uA min, 10 uA typical, 20 uA max (user manual)
- Operating temperature: 0 °C to 75 °C, 25 °C typical (user manual)
- Sig is internally pulled up to 5 V; no external component needed (user manual)
- Truth table: beam unblocked (slot) = LED ON, Sig 0 V; beam blocked = LED OFF, Sig 5 V (user manual)
- Packing list: 1 x RE08A sensor board, 1 x 8-slot disc (user manual)
- Ready to use without further soldering (user manual)

## Interfaces and compatibility
- 3-pin header: +5 (5 V supply), Gnd (supply negative), Sig (pulse output) (user manual)
- Board labels: A optical sensor, B +5, C Gnd, D Sig, E indicator LED (user manual)
- Connect Sig to a microcontroller counter, clock or encoder input; mount the disc on a motor shaft or gear output so it passes through the sensor gap (user manual)
- Software setup depends on the microcontroller and is not covered by the manual (user manual)
- No Cytron library or GitHub example found

## Use cases
- Counting pulses to measure shaft rotation, speed or distance on a motor shaft or gear output (user manual)

## Known limitations
- 5 V device: supply 4.5–5.5 V and 5 V output levels (user manual)
- Single signal output; no second channel listed (user manual)
- Output frequency limited to 1 kHz (user manual)
- Reversed supply polarity can damage the sensor (user manual)
- Disc slots must not be broken during installation (user manual)
- Manual (2008) states warranty 6 months; product page states 12 months

## Positioning (kept apart from specs)
- Simple 3-pin interface and on-board LED indicator; ready to use without soldering (user manual)

## Price band
RM38.85 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-rotary-encoder-kit

## Datasheet
https://drive.google.com/file/d/0BzFWfMiqqjyqdlpDUTc5ektndlE/view

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-39/pdf/cytron-simple-rotary-encoder-kit-users-manual.pdf

# Product fact sheets

## Product name
50A Current Sensor — BB-ACS756

## Aliases
BB-ACS756, 50A Current Sensor, Cytron 50A Current Sensor, Cytron BB-ACS756, ACS756 50A Current Sensor Breakout, 50A Current Sensor Breakout

## What it is
A breakout board for the Allegro ACS756 Hall-effect linear current sensor (50 A version) that measures AC or DC current and gives an analog output voltage. It is supplied with a Dean-T connector set and a 3-way right-angle pin header that are not soldered.

## Specs and functions
- Sensor IC: Allegro ACS756, X050 (50 Amp) version, model ACS756KCA-050B-PFF-T (product page)
- Current type: AC or DC; output voltage proportional to AC or DC current (product page)
- Primary sampled current: −50 A to +50 A (Allegro ACS756 chip datasheet, chip-level)
- Supply: 5.0 V single supply (product page); the chip itself is specified 3 V min, 5.0 V typ, 5.5 V max and factory-trimmed at 5 V (Allegro chip datasheet)
- Sensitivity: 40 mV/A (product page; Allegro typical at 25 °C); 37.2–42.8 mV/A over −40 °C to 125 °C (Allegro chip datasheet)
- Output at 0 A: VCC/2, i.e. 2.5 V at VCC = 5 V (Allegro chip datasheet)
- Total output error: 0.8% at TA = 25 °C (product page)
- Internal conductor resistance: 130 µΩ (product page)
- Isolation: 3 kV RMS minimum from pins 1-3 to 4-5 (product page)
- Output rise time: 3 µs (product page)
- Factory-trimmed; stable offset; nearly zero magnetic hysteresis (product page)
- On-board capacitors: 0.1 µF on VIOUT–GND and 0.1 µF on VCC–GND (Cytron schematic)
- Dimension: 1.43 x 1.435 inch (product page)
- Included: one set of Dean-T connector and a 3-way right-angle pin header, not soldered (product page)
- Weight: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Current path: 2-pin IN (+/−) and 2-pin OUT (+/−); the + line runs IN+ → ACS756 IP+ → IP− → OUT+, the − line passes straight through from IN to OUT (Cytron schematic)
- Signal header, 3 pins: 1 VCC, 2 GND, 3 VIOUT (analog output) (Cytron schematic)
- Output: single analog voltage; read with any ADC-capable pin
- Output is ratiometric: the 0 A level and sensitivity scale with VCC (Allegro chip datasheet)
- Fritzing part linked from the product page (product page)
- Library / sample code: [NOT STATED]

## Use cases
- Motor control (product page)
- Load detection (product page)
- Power supplies (product page)
- Over-current fault protection (product page)

## Known limitations
- The Dean-T connector and 3-way header are not soldered when purchased (product page)
- Output sits at VCC/2 at 0 A and is ratiometric to the supply, so supply variation changes offset and sensitivity (Allegro chip datasheet)
- Specified for a 5.0 V supply (product page); Allegro says 3.3 V operation needs confirmation of accuracy from Allegro (Allegro chip datasheet)
- Chip output drive: 3 mA source, 1 mA sink max; minimum load 4.7 kΩ (Allegro chip datasheet)
- No Cytron datasheet, user manual or sample code exists; board-level maximum continuous current is [NOT STATED]

## Positioning (kept apart from specs)
- [NOT STATED]

## Price band
RM52.50 (10+ RM47.25, 30+ RM42.00) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-50a-current-sensor

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-50a-current-sensor

# Product fact sheets

## Product name
RGB LED Stick (Neopixel-compatible) by Cytron — BCY-NEO-STICK-8

## Aliases
BCY-NEO-STICK-8, RGB LED Stick (Neopixel-compatible) by Cytron, RGB LED Stick, Cytron RGB LED Stick, NeoPixel RGB LED Stick by Cytron, Cytron NeoPixel Stick

## What it is
A small PCB stick with 8 addressable 5050 RGB LEDs (SK6812-based, WS2812B-compatible) controlled through one data pin. Sticks can be chained through the data-out pin.

## Specs and functions
- LEDs: 8 addressable RGB LEDs in series, 5050 package (product page)
- LED type: SK6812-based, compatible with WS2812B; NeoPixel compatible (product page)
- Drive: ~18 mA constant-current drive per LED; no external resistors (product page)
- Supply, as worded on the product page: "Power the whole thing with 5VDC (4-7V works)"; 5V pin: "regulated supply between 5V and about 7V. More than that could harm the LED, less than 5V will either reduce brightness, or it just won't turn on" (product page)
- Data: single data line with a timing-specific protocol (product page)
- Viewing angle: 120° (product page)
- Red: 620–630 nm, 550–700 mcd (product page)
- Green: 515–530 nm, 1100–1400 mcd (product page)
- Blue: 465–475 nm, 200–400 mcd (product page)
- Dimensions: 51.10 mm x 10.22 mm x 3.19 mm (product page)
- Weight: 2.57 g (product page)
- Header pins pre-soldered on the input pins (product page)
- Total current: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Pins: DI (data in), 5V, GND, DO (data out to next stick) (product page)
- Arduino: works with the NeoPixel Arduino library; 8 MHz or faster processor required (product page)
- Controllers named on the page: real-time microcontrollers (AVR, Arduino, PIC, mbed) (product page)
- Maker Pi Pico: connect to Pin 7 (GP7) and leave the white wire unconnected; CircuitPython in Thonny (Cytron tutorial)
- REKA:BIT RBT Project Kit: on a REKA:BIT Grove IO port; MakeCode extension pxt-rekabit-rbt-project-kit, `set RGB Stick at pin` block (P0, P1, P2, P13, P15), 8 LEDs numbered 0–7, brightness 0–255 (RBT kit guide and Cytron GitHub)

## Use cases
- Blue/red/green and random colour patterns with Maker Pi Pico and CircuitPython (Cytron tutorial)
- Boom Barrier Gate and Mobile Robot Car projects in the REKA:BIT RBT Project Kit (RBT kit guide)

## Known limitations
- The page says it cannot be used with a Linux-based microcomputer or an interpreted microcontroller such as netduino or Basic Stamp (product page); Cytron's own tutorials run it from CircuitPython on Maker Pi Pico and MakeCode on micro:bit
- Supply wording on the page: less than 5V will either reduce brightness or it just won't turn on, and more than about 7V could harm the LED (product page)
- Needs a timing-specific single-wire protocol, so a library or extension is needed (product page)
- Only the input pins come with headers pre-soldered (product page)

## Positioning (kept apart from specs)
- "NeoPixel compatible" (product page)

## Price band
RM9.35 (10+ RM8.88, 50+ RM8.41) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-neopixel-rgb-led-stick-by-cytron

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-neopixel-rgb-led-stick-by-cytron

# Product fact sheets

## Product name
3-Axis Accelerometer — SN-ADXL335-CY

## Aliases
SN-ADXL335-CY, 3-Axis Accelerometer, Cytron 3-Axis Accelerometer, Cytron ADXL335 Breakout, ADXL335 3-Axis Accelerometer Breakout

## What it is
A breakout board for the Analog Devices ADXL335 ±3 g 3-axis analog accelerometer, with an on-board 3.3 V regulator so it runs from 2.5 V to 6 V. It is out of stock on my.cytron.io (2026-10-19).

## Specs and functions
- Sensor IC: Analog Devices ADXL335 (product page)
- Axes: 3 (product page)
- Range: ±3g (product page)
- Regulator: on-board 3.3V regulator (product page)
- Operating voltage: 2.5V–6.0V (product page)
- Typical current: 300 µA (product page features); the page description says "only 320uA" (product page)
- Bandwidth: adjustable with one capacitor per axis; the included 0.1 µF capacitors set each axis to 50 Hz (product page)
- Fully assembled and tested (product page)
- Dimension: 19.5mm x 22mm (product page)
- Chip sensitivity: 300 mV/g typ at VS = 3 V, ratiometric to supply (ADXL335 vendor datasheet, chip-level)
- Chip 0 g output: nominally VS/2 (ADXL335 vendor datasheet, chip-level)
- Chip operating temperature: −40 °C to +85 °C (ADXL335 vendor datasheet, chip-level)
- Board pinout: [NOT STATED]
- Weight: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Outputs: analog voltage per axis (X, Y, Z) (ADXL335 vendor datasheet); needs three ADC inputs
- Board pin labels and order: [NOT STATED]
- Self-test pin on the board: [NOT STATED]
- Library / sample code: [NOT STATED]

## Use cases
- Tilt-angle measurement (Cytron tutorial title "Measuring Tilt Angle with Gyro and Accelerometer", product page)

## Known limitations
- Out of stock on my.cytron.io (2026-10-19)
- Bandwidth is set to 50 Hz per axis by the fitted 0.1 µF capacitors (product page)
- Analog outputs are ratiometric to the chip supply, so zero-g and sensitivity scale with it (ADXL335 vendor datasheet)
- The product page states two current figures (300 µA and 320 µA)
- The page's resource list mislabels the datasheet as "ADXL355 Datasheet" (product page)
- One linked tutorial ("Accelerometer ADXL335 Fast Test and Angle Test") returns 404

## Positioning (kept apart from specs)
- "only 320uA" current draw (product page)

## Price band
RM38.85 (10+ RM35.70, 30+ RM31.08) (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-3-axis-accelerometer

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-3-axis-accelerometer

# Product fact sheets

## Product name
STEM Robot Building Base Bundles

## Aliases
V-HD-STEM, STEM Robot Building Base, STEM Robot Building Base Bundles, STEM Robot Building Base Kit, STEM RBB Kit, Robot Building Base Bundle

## What it is
A plastic two-wheeled robot-car chassis bundle: plastic base plates, motor brackets, two TT DC motors with wheels, a steel ball castor, screws, spacers and a screwdriver. The controller or motor driver board is fixed to the base with screws or cable ties; no electronics are included.

## Specs and functions
- Product code: V-HD-STEM
- Options: Blue base or Green base; motor brackets are always blue
- Base material: plastic ("durable lightweight plastic chassis")
- Drive layout: 2-wheeled robot car (2 TT motors, 2 wheels, 1 castor)
- TT motors: 2, with 15 cm wires
- Wheels: 2, rubber
- Castor: 1, steel ball castor
- Screws: 25x M2.2 x 6 mm self-tapping; 3x M2.3 x 8 mm self-tapping (for Maker Line)
- Spacers: 4
- Tool: 1 tiny Phillips screwdriver
- Packing list: 2x Robot Building Base, 2x Motor Bracket (blue), 25x M2.2x6mm self-tapping screw, 3x M2.3x8mm self-tapping screw for Maker Line, 4x spacer, 2x TT motor with 15cm wires, 2x wheels, 1x steel ball castor, 1x tiny Phillips screwdriver
- Dimensions: [NOT STATED] (drawing image only on the product page)
- Weight: [NOT STATED]
- TT motor voltage, gear ratio, RPM: [NOT STATED]
- Wheel diameter: [NOT STATED]
- Warranty: [NOT STATED] (field blank on the product page)

## Interfaces and compatibility
- Mechanical product only; no electrical interface
- Controller / motor driver board is secured with screws or cable ties (cable ties not included)
- Boards shown on the product page: REKA:BIT, MOTION:BIT, Maker Pi RP2040, Robo Pico (Boco Bot kit) — none included
- Maker Line sensor mounting: 3x M2.3 x 8 mm screws supplied for Maker Line (sensor not included)
- Mounting-hole pattern: [NOT STATED]
- Guide: Cytron tutorial "STEM Robot Building Base Kit Step-by-Step Installation Guide" (Hao Zhen Goh, 25 Jul 2023)

## Use cases
- Build your robot car base by using the STEM Robot Building Base Kit (installation guide)
- 2-wheeled robot car chassis for a micro:bit or RP2040 controller board (REKA:BIT, MOTION:BIT, Maker Pi RP2040, Robo Pico)

## Known limitations
- No controller board, motor driver, battery, battery holder, sensors or cable ties are included
- Motor brackets are blue on both the Blue and the Green option
- Only 3 of the screws (M2.3 x 8 mm) are intended for the Maker Line
- Dimensions are given as an image only; no size is stated in text
- Warranty is not stated on the product page

## Positioning (kept apart from specs)
- "Durable lightweight plastic chassis" with a step-by-step guide for building a 2-wheeled robot car (product page)

## Price band
RM35.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-stem-robot-building-base-kit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-stem-robot-building-base-kit

# Product fact sheets

## Product name
Cytron Reconfigurable Line Following Track

## Aliases
V-RE-TRACKS, Cytron Reconfigurable Line Following Track, Reconfigurable Line Following Track, Line Following Track Tiles, Line Following Combo Tiles, Line Following Add On Tiles, EVA Line Following Track

## What it is
A set of square EVA-foam floor tiles printed with black line patterns on a white non-reflective surface, laid out in different arrangements to make a line-following course. Six tile types exist (Cross, Curve, Station, Straight, Blank, T-Junction), sold as Combo sets of 8 or 16 tiles or Add On packs of 4.

## Specs and functions
- Product code: V-RE-TRACKS
- Material: EVA foam, no lamination layer
- Surface: white, non-reflective, with black line patterns
- Hardness: 40 degree (±5)
- Tile size: 315mm x 315mm
- Thickness: 10mm
- Black line width: 18mm
- Tile types: 6 — Cross, Curve, Station, Straight, Blank, T-Junction
- Variants: Combo Tiles / Add On Tiles; patterns: 16 Combo, 8 Combo, 4 Cross, 4 Curve, 4 Station, 4 Straight, 4 Blank, 4 T-Junction
- Combo 8: 1 cross, 4 curve, 3 straight
- Combo 16: 2 cross, 8 curve, 6 straight
- Add On 1: 4 cross; Add On 2: 4 curve; Add On 3: 4 station; Add On 4: 4 straight; Add On 5: 4 blank; Add On 6: 4 T-junction
- Each set includes an info sheet of track designs
- Warranty: 12 months
- Weight: [NOT STATED]
- Hardness scale: [NOT STATED]
- Tile joining method: [NOT STATED]

## Interfaces and compatibility
- Passive floor track; no electronics
- For line-following robots with IR line sensors (no specific sensor named on the product page)
- Referenced by the Cytron tutorial "Learn Robotics with Bocobot Car Kit and Robo Pico"

## Use cases
- Build a reconfigurable line-following course for robot cars
- Line following in the Bocobot Car Kit with Robo Pico tutorial

## Known limitations
- Combo 8 and Combo 16 contain only Cross, Curve and Straight tiles; Station, Blank and T-Junction tiles come only in Add On packs
- The surface is non-reflective EVA foam with no lamination layer
- Price per individual option is not stated in the page text read (range only)

## Positioning (kept apart from specs)
- "Reconfigurable" line following track: tiles can be rearranged into different course designs (product page)

## Price band
RM44.00–RM176.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-cytron-reconfigurable-line-following-track

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-cytron-reconfigurable-line-following-track

# Product fact sheets

## Product name
Robo Bracket for Micro Servo Motor

## Aliases
ROBO-BK-SG90, Robo Bracket for Micro Servo Motor, Robo Bracket, Robo Bracket SG90, Robo Micro Servo Bracket, Micro Servo Bracket for Robo Base

## What it is
A black powder-coated aluminium-alloy bracket that holds a 9 g-class micro servo (SG90, MG90S, TS90A, EF90D, FS90R or any servo of 23.0 x 12.2 x 29.0 mm) and is designed to bolt to Cytron's Robo Base and Robo Base Mini chassis.

## Specs and functions
- Product code: ROBO-BK-SG90
- Material: aluminium alloy
- Thickness: 1.5mm
- Finish: powder coating
- Colour: black
- Fits micro servos: SG90, MG90S, TS90A, EF90D, FS90R and same-dimension servos (23.0x12.2x29.0mm)
- Designed to fit Robo Base and Robo Base Mini
- Packing list: 1x bracket, 4x M2*6 screw, 4x M3*6 screw
- Overall dimensions: [NOT STATED] (dimension drawing image only)
- Hole pattern and hole sizes: [NOT STATED]
- Weight: [NOT STATED]
- Warranty: [NOT STATED] (field blank on the product page)

## Interfaces and compatibility
- Mechanical part; no electrical interface
- Servos: SG90, MG90S, TS90A, EF90D, FS90R and same-dimension (23.0x12.2x29.0mm) servos
- Chassis: Robo Base, Robo Base Mini
- Which screws go to the servo and which to the base: [NOT STATED]
- Linked Cytron project: "ZOOM:BIT with Robo Grip Mini" (Ng Zhi Tian, 18 Mar 2026)

## Use cases
- Mount a micro servo on a Robo Base or Robo Base Mini robot chassis
- Combine a gripper with a ZOOM:BIT robot (linked project)

## Known limitations
- Only servos of 23.0 x 12.2 x 29.0 mm are stated to fit; larger servos are not covered
- No servo, servo horn or nuts are included; only 4x M2*6 and 4x M3*6 screws
- Fit is stated only for Robo Base and Robo Base Mini
- Dimensions are an image only; no size is stated in text
- Warranty is not stated on the product page

## Positioning (kept apart from specs)
- Aluminium-alloy, powder-coated bracket for Cytron's Robo Base family (product page)

## Price band
RM9.90 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-robo-bracket-for-microservo-motor

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-robo-bracket-for-microservo-motor

# Product fact sheets

## Product name
Robo Base

## Aliases
Robo Base, Cytron Robo Base, Robo Base PCB Chassis, Robo Base Kit, Robo Base Double Base 2WD, Robo Base Double Base 4WD, Robo Base Basic Bundle

## What it is
A PCB chassis plate for building small mobile robot cars, or for mounting a Cytron controller board on another chassis. It is sold as a single plate or as Double Base kits with M3 standoffs, and optionally TT motors and wheels.

## Specs and functions
- Product code: Robo Base (series page code V-ROBO-BASE-MINI); Robo Base and Robo Base Mini share one product page
- Material: durable PCB material; "non-copper PCB" (BEETLE:BIT product page)
- Thickness: [NOT STATED] (image only on the product page)
- Dimensions: [NOT STATED] (image only on the product page)
- Weight: [NOT STATED]
- Kit options: Double Base 4WD (Mecanum Wheels), Double Base 2WD (Rubber Wheels), Double Base with Accessories, Single Base Only
- Double Base 4WD: 2x Robo Base, 4x M3 PCB stand (screw+nut) 30mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 4x TT motor 15cm wire, 2x 48mm Mecanum left and right wheel set, 2x TT DC gear motor bracket
- Double Base 2WD: 2x Robo Base, 4x M3 PCB stand 30mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 2x TT motor 15cm wire, 2x plastic wheels, 2x TT motor bracket, 1x W420 ball castor
- Double Base with Accessories: 2x Robo Base, 4x M3 PCB stand 30mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench
- Single Base Only: 1x Robo Base
- Standoffs: 30mm and 10mm M3 (Robo Base Mini uses 25mm instead of 30mm)
- Warranty: 12 months

## Interfaces and compatibility
- Mechanical part; no electrical interface
- Controller boards with compatible mounting holes: REKA:BIT, MOTION:BIT, MOTION:BIT Pro, MOTION 2350 Pro, Robo Pico, Maker Pi RP2040, Maker UNO or Arduino UNO form factor, Maker UNO + Maker Drive, Raspberry Pi 4 or 5, Jetson series
- Attachments covered by the Getting Started with Robo Base tutorial: TT motor and castors, ultrasonic sensor, Maker Line, micro servo motor, ⌀37mm 12V DC motor
- Servo bracket: Robo Bracket for Micro Servo Motor (ROBO-BK-SG90), designed to fit Robo Base and Robo Base Mini
- Gripper: Robo Grip Mini, mounting holes compatible with the Robo Base Series
- Used in BEETLE:BIT (2x Robo Base PCB only, in the accessories kit)

## Use cases
- Build a small mobile robot car (2WD with castor, or 4WD with mecanum wheels)
- Use as an adapter plate to mount a Cytron controller board on another robot chassis
- Line following with Maker Line, obstacle sensing with an ultrasonic sensor, servo add-ons
- Fire Fighting Robot using MOTION 2350 Pro; Line Following with Robo Base using URC10 (Cytron tutorials)

## Known limitations
- No controller board, battery, sensors or servo are included in any kit option
- Single Base Only is the plate only, with no screws or standoffs
- Dimensions and thickness are not stated in text (image only)
- The 2WD option is named "Rubber Wheels" but its packing list says "2x plastic wheels" (both on the Cytron product page)
- Product page price is a range for the whole Robo Base series; per-option prices are not stated

## Positioning (kept apart from specs)
- "Inspired by Nature" (Fiddler beetle) design (product page)
- "Cost-friendly alternative to metal chassis and tougher than fragile acrylic plates" (product page)
- Flexible platform, reconfigurable with standard screws, nuts and standoffs (product page)

## Price band
RM9.00–RM112.00 for the whole Robo Base series page, covering Robo Base and Robo Base Mini in all kit options (Cytron product page, read 2026-10-19); "Robo Base Basic Bundle" RM41.80 (product card in the Getting Started with Robo Base tutorial, read 2026-10-19)

## Product page
https://my.cytron.io/p-robo-base-mini-and-kits

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-robo-base-mini-and-kits

# Product fact sheets

## Product name
Robo Base Mini

## Aliases
Robo Base Mini, Cytron Robo Base Mini, Robobase Mini, Robo Base Mini Kit, Robo Base Mini Basic Bundle, Robobase Mini kit for 2WD Robot, Robo Base Mini Double Base 2WD, Robo Base Mini Double Base 4WD

## What it is
The smaller PCB chassis plate in Cytron's Robo Base series, for building small mobile robot cars or for mounting a Cytron controller board on another chassis. It is sold as a single plate or as Double Base kits with M3 standoffs, and optionally TT motors and wheels.

## Specs and functions
- Product code: Robo Base Mini (series page code V-ROBO-BASE-MINI); Robo Base Mini and Robo Base share one product page
- Material: durable PCB material; "non-copper PCB" (STRIKER:BIT product page)
- Thickness: [NOT STATED] (image only on the product page)
- Dimensions: [NOT STATED] (image only on the product page)
- Weight: [NOT STATED]
- Kit options: Double Base 4WD (Mecanum Wheels), Double Base 2WD (Rubber Wheels), Double Base with Accessories, Single Base Only
- Double Base 4WD: 2x Robo Base Mini, 4x M3 PCB stand (screw+nut) 25mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 4x TT motor 15cm wire, 2x 48mm Mecanum left and right wheel set, 2x TT DC gear motor bracket
- Double Base 2WD: 2x Robo Base Mini, 4x M3 PCB stand 25mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench, 2x TT motor 15cm wire, 2x plastic wheels, 2x TT motor bracket, 1x W420 ball castor
- Double Base with Accessories: 2x Robo Base Mini, 4x M3 PCB stand 25mm, 4x M3 PCB stand 10mm, 12x M3 bolt 6mm, 12x M3 nut, 1x transparent Philips screwdriver, 1x mini cross wrench
- Single Base Only: 1x Robo Base Mini
- Standoffs: 25mm and 10mm M3 (Robo Base uses 30mm instead of 25mm)
- Warranty: 12 months

## Interfaces and compatibility
- Mechanical part; no electrical interface
- Controller boards with compatible mounting holes (Robo Base series list): REKA:BIT, MOTION:BIT, MOTION:BIT Pro, MOTION 2350 Pro, Robo Pico, Maker Pi RP2040, Maker UNO or Arduino UNO form factor, Maker UNO + Maker Drive, Raspberry Pi 4 or 5, Jetson series
- Attachments covered by the Getting Started with Robo Base Mini tutorial: DC motor and castors, Maker Line, ultrasonic sensor, micro servo, battery
- Servo bracket: Robo Bracket for Micro Servo Motor (ROBO-BK-SG90), designed to fit Robo Base and Robo Base Mini
- Gripper: Robo Grip Mini, mounting holes compatible with the Robo Base Series
- Used in STRIKER:BIT ("Robobase Mini kit for 2WD Robot")

## Use cases
- Build a small mobile robot car (2WD with castor, or 4WD with mecanum wheels)
- Use as an adapter plate to mount a Cytron controller board on another robot chassis
- Robo Base Mini Line Following Robot with Maker UNO and Maker Drive (Cytron tutorial)
- Robo Base Mini Obstacle Avoidance Robot with Maker UNO and Maker Drive (Cytron tutorial)
- Line Following Robo Base Mini with ESP32 (Cytron project)

## Known limitations
- No controller board, battery, sensors or servo are included in any kit option
- Single Base Only is the plate only, with no screws or standoffs
- Dimensions and thickness are not stated in text (image only)
- The 2WD option is named "Rubber Wheels" but its packing list says "2x plastic wheels" (both on the Cytron product page)
- The ⌀37mm 12V DC motor mounting is covered for Robo Base, not for Robo Base Mini
- Product page price is a range for the whole Robo Base series; per-option prices are not stated

## Positioning (kept apart from specs)
- "Inspired by Nature" (Fiddler beetle) design (product page)
- "Cost-friendly alternative to metal chassis and tougher than fragile acrylic plates" (product page)
- Flexible platform, reconfigurable with standard screws, nuts and standoffs (product page)

## Price band
RM9.00–RM112.00 for the whole Robo Base series page, covering Robo Base and Robo Base Mini in all kit options (Cytron product page, read 2026-10-19); "Robo Base Mini Basic Bundle" RM19.80 (product card in the Getting Started with Robo Base Mini tutorial, read 2026-10-19)

## Product page
https://my.cytron.io/p-robo-base-mini-and-kits

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-robo-base-mini-and-kits

# Product fact sheets

## Product name
Robo Grip Mini Kits

## Aliases
V-ROBO-GRIP-MINI, Robo Grip Mini, Robo Grip Mini Kits, Robo Grip Mini Kit, Cytron Robo Grip Mini, Robo Grip Mini PCB, Robo Grip PCB, Robo Grip Mini Basic Bundle, Robo Grip Mini Gripper

## What it is
A PCB gripper kit for micro servos that mounts on Cytron's Robo Base and Robo Base Mini chassis. It is sold as a gripper only, a 1-axis gripper with 2 micro servos, or a 2-axis gripper with 3 micro servos.

## Specs and functions
- Product code: V-ROBO-GRIP-MINI
- Material: PCB; thickness [NOT STATED] (image only on the product page)
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]
- Options: Gripper only / 1-axis Gripper (2 micro servo) / 2-axis Gripper (3 micro servos)
- Servo configurations: 1 servo = main gripping motion; 2 servos = adds arm movement; 3 servos = better angle control and positioning
- Servos supplied: TS90A micro servo (2x in the 1-axis kit, 3x in the 2-axis kit); none in Gripper only
- 2-axis kit (3 servos) contents: 1x Robo Grip Mini PCB, 6x M2 bolt 6mm, 6x M2 nut, 1x M3 PCB stand 40mm, 4x nylon M3 PCB stand 20mm + nut set, 4x nylon M3 PCB stand 10mm + nut set, 12x M3 bolt 6mm, 4x M3 bolt 12mm, 4x M3 nut, 5x M3 lock nut, 6x M3 plastic washer H1 W7, 5x M3 plastic washer H3 W7, 2x M3 black plastic rivet 3x6, M2 and M3 transparent Philips screwdrivers, mini cross wrench, 2x Robo Bracket for Micro Servo Motor, 1x aluminium micro servo bracket, 4x M2 bolt 6mm, 4x M3 bolt 6mm, 3x TS90A micro servo, 1x assembly guide
- 1-axis kit (2 servos): same, but 1x Robo Bracket and 2x TS90A
- Gripper only ("with Accessories"): PCB, hardware, tools and assembly guide; no servos, no bracket
- 40mm M3 standoff: "SS" (product page) vs "brass" (Installation Guide tutorial)
- Assembly: snap and break every part off the PCB, then file the snapped parts
- Warranty: [NOT STATED] (field blank on the product page)

## Interfaces and compatibility
- Mechanical part; no electrical interface
- Servos: SG90, MG90S, TS90A, EF90D, FS90R and same-dimension servos
- Chassis: mounting holes compatible with the Robo Base Series (Robo Base, Robo Base Mini)
- Servo bracket: Robo Bracket for Micro Servo Motor (ROBO-BK-SG90)
- Used in BEETLE:BIT ("Robo Grip PCB with accessories", gripper servo on REKA:BIT S1)
- Used in STRIKER:BIT ("Robo Grip Mini Basic Bundle", used with a 3D-printed part as a servo shooter)
- Cytron project: ZOOM:BIT with Robo Grip Mini

## Use cases
- Add a servo gripper to a Robo Base or Robo Base Mini robot car
- Build a one-axis or two-axis gripper arm with micro servos
- ZOOM:BIT with Robo Grip Mini (Cytron project)
- BEETLE:BIT gripper robot car; STRIKER:BIT servo shooter

## Known limitations
- Gripper only option includes no servo and no Robo Bracket
- Maximum 3 servos in Cytron's configurations (1, 2 or 3)
- Only SG90-size micro servos are stated to fit; FS90R is a continuous-rotation servo
- No controller board, battery or chassis included
- Parts must be snapped off the PCB and filed before assembly
- PCB thickness and dimensions are not stated in text
- Warranty is not stated on the product page

## Positioning (kept apart from specs)
- "Stag Beetle" inspired design (product page)
- "Cost-friendly alternative to metal grippers", durable PCB (product page)
- Easy snap-and-play assembly with standard screws, nuts and standoffs (product page)

## Price band
RM34.90–RM94.19 across the three options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-robo-grip-mini-kits

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-robo-grip-mini-kits

# Product fact sheets

## Product name
Maker Drive

## Aliases
MAKER-DRIVE, Maker Drive, Maker Drive: Simplifying H-Bridge Motor Driver for Beginner

## What it is
A 2-channel, bi-directional H-bridge motor driver for two brushed DC motors or one stepper motor, powered from 2.5–9.5 VDC. Each motor is controlled by two PWM inputs (A and B).

## Specs and functions
- Product code: MAKER-DRIVE
- Datasheet: Rev 1.0, Feb 2019 (spec table titled "Absolute Maximum Ratings")
- Power input voltage: 2.5–9.5 VDC (VB+ positive, VB- negative; datasheet: "Connect to battery")
- Maximum motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds)
- Channels: 2 (Motor 1, Motor 2), bi-directional
- Logic input voltage (M1A, M1B, M2A, M2B): low 0–0.5 V, high 1.7–6 V
- PWM frequency: DC to 20 kHz (output frequency is same as input frequency)
- DC +5V output (5VO): 200 mA max, can power the microcontroller; product listing: buck-boost regulator, 5V from input as low as 2.5V
- Input truth table per motor: Low/Low = Brake; High/Low = Forward; Low/High = Backward; High/High = Coast (outputs Hi-Z/open)
- Actual direction depends on motor wiring; swapping MA and MB reverses it
- Control: two PWM inputs per motor (no DIR pin); no RC, analog or serial mode stated
- 4 test buttons (2 per channel): M1A/M2A forward, M1B/M2B backward; motor runs at full speed
- 4 motor status LEDs (2 per channel): M1A/M2A forward, M1B/M2B backward
- Power LED
- Reverse polarity protection on the power input
- Temperature protection: H-bridge IC cuts output to the motor when its internal temperature is over 150 °C
- Dimensions: 43 mm (W) × 35 mm (L) × 14 mm (H) (product listing; datasheet gives a drawing only)
- Driver IC part number: [NOT STATED]
- Over-current / short-circuit protection: [NOT STATED]
- Under-voltage protection: [NOT STATED]
- Operating temperature: [NOT STATED]
- Terminal type and wire size: [NOT STATED]

## Interfaces and compatibility
- Pins: VB+, VB- (power input terminal); motor output terminals; M1A, M1B, M2A, M2B (PWM inputs); 5VO; GND
- Logic: "Inputs compatible with 1.8V, 3.3V and 5V logic (Arduino, Raspberry Pi, etc)." (product listing)
- Motors: brushed DC motors (2) or one stepper motor (datasheet connection diagrams)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), `#include "CytronMotorDriver.h"`, `CytronMD motor1(PWM_PWM, pinA, pinB);`, `setSpeed(-255..255)`; `setSpeed(0)` gives Brake
- Official example: PWM_PWM_DUAL (lists MAKER-DRIVE and MDD3A); wiring D3 → 1A, D9 → 1B, D10 → 2A, D11 → 2B, GND → GND
- Host GND must connect to the driver GND
- MicroPython / CircuitPython / MakeCode: [NOT STATED]
- Packing list: [NOT STATED]

## Use cases
- Beginner motor driver projects ("designed for simplicity and with the beginner in mind")
- Replacing an L298N motor driver
- Line following ("Most application perform better in Regen braking for example line following")
- Driving two brushed DC motors
- Driving a stepper motor ("additional bonus feature")
- Powering the project from a single power source (5V output powers the controller)

## Known limitations
- Power input absolute maximum 9.5 VDC (minimum 2.5 VDC)
- Motor current 1 A continuous per channel; 1.5 A peak only for < 5 seconds
- Logic input high level absolute maximum 6 V (not for 12 V/24 V logic)
- High/High on the inputs gives Coast, not Brake; use Low/Low for Brake
- No DIR pin: PWM+DIR (PWM_DIR) code does not suit this board; both A and B pins need PWM for speed in both directions
- 5VO limited to 200 mA
- Thermal cut-off at 150 °C IC temperature; over-current and short-circuit protection not stated
- Reverse polarity protection is on the power input only
- Test buttons run the motor at full speed
- Motor direction depends on wiring
- Datasheet says to connect a battery; SMPS/bench supply guidance not stated

## Positioning (kept apart from specs)
- Datasheet subtitle: "Simplifying H-Bridge Motor Driver for Beginner"
- Product listing: "ideal to replace the L298N"
- "Maker Drive is designed for simplicity and with the beginner in mind!"
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay"
- "Regenerative Braking"

## Price band
- USD 3.80 on Cytron's Tindie store ("Sold out since Nov 17, 2022"), checked 16 Oct 2026

## Product page
https://www.cytron.io/p-maker-drive

## Datasheet
https://docs.google.com/document/d/1XakJWz9DAtrMc_Jf75FnDXs4gwT_osCSj3Rbx1OU7bM/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1XakJWz9DAtrMc_Jf75FnDXs4gwT_osCSj3Rbx1OU7bM/edit

# Product fact sheets

## Product name
MDD3A 3Amp 4V-16V DC Motor Driver (2 Channels)

## Aliases
MDD3A, 3Amp 4V-16V DC Motor Driver, 3Amp 2 Channel 4V-16V DC Motor Driver

## What it is
A 2-channel, bi-directional motor driver for two brushed DC motors or one stepper motor, powered from 4–16 VDC. Each motor is controlled by two PWM inputs (A and B).

## Specs and functions
- Product code: MDD3A
- Datasheet: Rev 1.0, March 2019 (spec table titled "Absolute Maximum Ratings")
- Power input voltage (Vin): 4–16 VDC (VB+ positive, VB- negative; datasheet: "Connect to battery")
- Maximum motor current: 3 A continuous, 5 A peak (< 5 seconds) (datasheet); product listing: "3 Amp per channel continuously without any additional heatsink"
- Channels: 2 (Motor 1, Motor 2), bi-directional
- Output stage: "discrete MOSFETs H-Bridge design" (product listing)
- Logic input voltage (M1A, M1B, M2A, M2B): low 0–0.5 V, high 1.7–12 V
- PWM frequency: DC to 20 kHz (output frequency is same as input frequency)
- DC +5V output (5VO): 200 mA max, can power the microcontroller; product listing: buck-boost regulator, 5V from input as low as 4V
- Input truth table per motor: Low/Low = Brake; High/Low = Forward; Low/High = Backward; High/High = Brake
- Actual direction depends on motor wiring; swapping MA and MB reverses it
- Control: two PWM inputs per motor (no DIR pin); no RC, analog or serial mode stated
- Test buttons: M1A/M2A forward, M1B/M2B backward; motor runs at full speed
- Motor status LEDs: M1A/M2A forward, M1B/M2B backward
- Power LED
- Reverse polarity protection on the power input
- Thermal protection: [NOT STATED]
- Over-current / short-circuit protection: [NOT STATED]
- Under-voltage protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Terminal type and wire size: [NOT STATED]
- Packing list: 1 x 3Amp 4V-16V DC Motor Driver (2 Channels) (product listing)

## Interfaces and compatibility
- Pins: VB+, VB- (power input terminal); motor output terminals; M1A, M1B, M2A, M2B (PWM inputs); 5VO; GND
- Logic: "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." (product listing)
- Motors: two brushed DC motors, or one unipolar/bipolar stepper motor
- Arduino: Cytron Motor Drivers Library (version 1.0.1), `#include "CytronMotorDriver.h"`, `CytronMD motor1(PWM_PWM, pinA, pinB);`, `setSpeed(-255..255)`; `setSpeed(0)` gives Brake
- Official example: PWM_PWM_DUAL (lists MAKER-DRIVE and MDD3A); wiring D3 → 1A, D9 → 1B, D10 → 2A, D11 → 2B, GND → GND
- Host GND must connect to the driver GND
- MicroPython / CircuitPython / MakeCode / PLC examples: [NOT STATED]

## Use cases
- Small size mobile robot for competition or school projects
- Motor driver for a mobile robot
- Driving a stepper motor (one unipolar/bipolar stepper)
- Bidirectional control of two brushed DC motors
- Host controllers such as Arduino, Raspberry Pi or PLC

## Known limitations
- Power input absolute maximum 16 VDC (minimum 4 VDC)
- Motor current 3 A continuous; 5 A peak only for < 5 seconds
- Datasheet current table does not say "per channel"; the per-channel 3 A figure comes from the product listing
- Logic input high level absolute maximum 12 V
- No coast state: both Low/Low and High/High give Brake
- No DIR pin: PWM+DIR (PWM_DIR) code does not suit this board; both A and B pins need PWM for speed in both directions
- 5VO limited to 200 mA
- Only reverse polarity protection is stated (power input only); thermal and over-current protection not stated
- Test buttons run the motor at full speed
- Motor direction depends on wiring
- Datasheet says to connect a battery; SMPS/bench supply guidance not stated

## Positioning (kept apart from specs)
- Product listing: "Looking for a motor driver for your mobile robot?"
- "it's compatible with wide variety of host controller (e.g. Arduino, Raspberry Pi, PLC)"
- Reverse polarity protection pitched against "a very common mistake done by a lot of makers even for the very experienced one" (datasheet)

## Price band
- USD 7.00 on Cytron's Tindie store ("Sold out since Aug 02, 2026"), checked 16 Oct 2026

## Product page
https://www.cytron.io/p-mdd3a

## Datasheet
https://docs.google.com/document/d/1ax3gSo0srTzoSr2bo8ETLym0OqrYjlk_JCZK4kxtfXg/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1ax3gSo0srTzoSr2bo8ETLym0OqrYjlk_JCZK4kxtfXg/edit

# Product fact sheets

## Product name
0.8Amp 5V-26V DC Motor Driver Shield for Arduino (2 Channels)

## Aliases
SHIELD-2AMOTOR, Cytron 2A Motor Driver Shield, 2A Motor Driver Shield, 0.8Amp 5V-26V DC Motor Driver Shield for Arduino, 0.8Amp 5V-26V DC Motor Driver Shield

## What it is
An Arduino shield that drives two brushed DC motors in both directions using the L298P IC. Mini jumpers select sign-magnitude or locked-antiphase control and the motor power source.

## Specs and functions
- Channels: 2, brushed DC motors
- Motor supply voltage: 5 V to 26 V
- Continuous current: 0.8 A per channel
- Peak current: 2 A per channel; the spec table carries the footnote "*Must not exceed 10 seconds" without marking which row it applies to
- The "2A" in the product code and manual title is the peak rating; the product page title's "0.8Amp" is the continuous rating
- Logic input high: 3.3 V min, 5.5 V max; logic input low: 0 V to 0.5 V
- 3.3V and 5V logic level input
- Maximum PWM frequency: 10 kHz
- Driver IC: L298P
- Control modes: Signed Magnitude (default) and Locked Anti-Phase, selected by moving 4 mini jumpers
- Power source selection: external (PWRIN) or internal (VIN, from the Arduino power source)
- Reverse polarity protection on the external power (PWRIN) input
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Test switch for both channels; PWR LED (motor power indicator)
- Reset button for the Arduino main board
- Stackable I/O header pins
- LSS05 connector
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Warranty: 12 months, manufacturing defect only
- In the box: 1 x SHIELD-2AMOTOR, 5 x mini jumper

## Interfaces and compatibility
- Signed Magnitude: DIR 1 = D4, EN 1 = D5, EN 2 = D6, DIR 2 = D7
- Locked Anti-Phase: DIR 1 = D5, EN 1 = D4, EN 2 = D7, DIR 2 = D6
- LSS05 pins: 5V, GND, A1 = O1, A2 = O2, A3 = O3, A4 = O4, A5 = O5, D8 = Cal
- MOTOR1 and MOTOR2 terminal blocks; PWRIN terminal for external power
- Compatible with Arduino Uno, Leonardo, Mega, Due and possibly other pin compatible main boards
- Arduino: Cytron Motor Drivers Library (PWM_DIR_DUAL example); in Signed Magnitude mode use PWM pin 5 / DIR pin 4 for motor 1 and PWM pin 6 / DIR pin 7 for motor 2

## Use cases
- Controlling dual brushed DC motors with an Arduino Uno, Leonardo, Mega or Due
- Connecting the LSS05 line sensor directly to the Arduino through the shield

## Known limitations
- Continuous current is 0.8 A per channel; 2 A is peak only
- Motor supply maximum 26 V
- Reverse polarity protection covers the PWRIN input only
- Maximum PWM frequency 10 kHz; logic input maximum 5.5 V
- Uses Arduino pins D4 to D7 (and A1 to A5 and D8 when the LSS05 connector is used)

## Positioning (kept apart from specs)
[NOT STATED]

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-0.8amp-5v-26v-dc-motor-driver-shield-for-arduino-2-channels

## Datasheet
https://docs.google.com/document/d/1EiQAE_9VpDDm4rjZrySAoGjQldJnTk6rJIsUkqCT37w/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1EiQAE_9VpDDm4rjZrySAoGjQldJnTk6rJIsUkqCT37w/view

# Product fact sheets

## Product name
1.2Amp 7V-30V DC Motor Driver Shield for Arduino (2 Channels)

## Aliases
SHIELD-3AMOTOR, Cytron 3A Motor Driver Shield, 3A Motor Driver Shield, 1.2Amp 7V-30V DC Motor Driver Shield for Arduino, 1.2Amp 7V-30V DC Motor Driver Shield

## What it is
An Arduino shield that drives two brushed DC motors in both directions using the DRV8871 IC. A DIP switch selects sign-magnitude or locked-antiphase control.

## Specs and functions
- Channels: 2, brushed DC motors
- Motor supply voltage: 7 V to 30 V; above 12 V the PWRIN-Vin connection pad must be cut and the Arduino powered separately
- Continuous current: 1.2 A per channel (depends on room temperature)
- Peak current: 3 A per channel, must not exceed 1 second
- The "3A" in the product code and manual title is the peak rating; the product page title's "1.2Amp" is the continuous rating
- Logic input high: 1.5 V min, 5 V max; logic input low: 0 V to 0.5 V
- Supports 3.3V and 5V logic level input
- Maximum PWM frequency: [NOT STATED]
- Driver IC: DRV8871
- Control modes: Sign Magnitude and Locked Anti-Phase, selected by DIP switch (switches 5, 6, 7, 8 ON = Sign Magnitude; switches 1, 2, 3, 4 ON = Locked Anti-Phase)
- Current limit protection
- No polarity protection for V motor
- Thermal and under-voltage protection: [NOT STATED]
- Test buttons for both channels; Motor 1 and Motor 2 direction LEDs; power LED
- Reset button
- Stackable Arduino header pins
- LSS05 Auto-Calibrating Line Sensor connector
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Warranty: 12 months, manufacturing defect only; cutting any trace voids the warranty
- In the box: 1 x Cytron 3A Motor Driver (Code: SHIELD-3AMOTOR)

## Interfaces and compatibility
- Sign Magnitude: DIR1 = D4, EN1 = D5, EN2 = D6, DIR2 = D7
- Locked Anti-Phase: DIR1 = D5, EN1 = D4, EN2 = D7, DIR2 = D6
- Control pins can be changed only by cutting traces on the back and soldering jumpers (voids warranty)
- LSS05 pins: O1 = D13, O2 = D12, O3 = D11, O4 = D10, O5 = D9, Calibrate = D8
- Screw terminal blocks for Motor 1, Motor 2 and power supply
- PWRIN (shield power terminal) and Arduino Vin are joined by a connection pad by default
- Compatible with Arduino Uno, Leonardo, Mega, Due, Zero, 101 and possibly other pin compatible boards such as CIKU, CT UNO and CT ARM
- Arduino: Cytron Motor Drivers Library (PWM_DIR_DUAL example); in Sign Magnitude mode use PWM pin 5 / DIR pin 4 for motor 1 and PWM pin 6 / DIR pin 7 for motor 2

## Use cases
- Controlling dual DC motors from an Arduino
- Line following robot with the LSS05 line sensor connected directly to the shield

## Known limitations
- Continuous current is 1.2 A per channel; 3 A is peak only, for no more than 1 second
- No polarity protection on the motor supply; double check the connection before connecting power
- Supplying more than 12 V requires cutting the PWRIN-Vin trace, which voids the warranty
- Set only Sign Magnitude or Locked Anti-Phase on the DIP switch at a time; mixing the setting causes unexpected results
- The manual specifies a battery power source; SMPS use is not covered
- Uses Arduino pins D4 to D7 (and D8 to D13 when the LSS05 connector is used)

## Positioning (kept apart from specs)
- The manual describes it as "an improvement from our previous Cytron 2A Motor Driver Shield" that "can handle higher current up to 3A together with limit current protection"

## Price band
RM41.79 on offer (was RM92.40) (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-1.2amp-7v-30v-dc-motor-driver-shield-for-arduino-2-channels

## Datasheet
https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1gzOZmvPOlycLE2lz935gsNGHn9SZdbbSCnHCQyKssi8/view

# Product fact sheets

## Product name
1.5Amp 7V-15V DC Motor Driver (4 Channels)

## Aliases
FD04A, FD04A Rev2.0, FD04A R2, FD04A-R2, 1.5Amp 7V-15V DC Motor Driver, 4 Channel Motor Driver

## What it is
A four-channel bi-directional driver for four brushed DC motors, built on the L298P IC. Each channel is controlled by a direction pin and an enable/speed-control pin.

## Specs and functions
- Channels: 4 (M1, M2, M3, M4), brushed DC motors
- Motor supply voltage: 7 V to 15 V (user manual). Product page title says 7V-15V; product page URL slug says "7v-25v"
- Continuous current: 1.5 A per channel (user manual spec table)
- Peak current: 2.5 A (user manual spec table; duration not stated)
- Manual introduction also says "up to 2A for each channel"; the spec table gives 1.5 A continuous and 2.5 A peak
- Logic input high: 3.3 V min, 5.5 V max; logic input low: 0 V to 0.5 V
- 3.3V and 5V logic level input
- Maximum PWM frequency: 10 kHz
- Control per channel: direction pin and enable/Speed Control pin; Enable 0 = both outputs LOW; Enable 1 + Direction 0 = OUT A HIGH, OUT B LOW; Enable 1 + Direction 1 = OUT A LOW, OUT B HIGH
- Driver IC: L298P
- Onboard 5V voltage regulator supplies the transistors and L298P and the V pin (5 V output)
- Reverse polarity protection on the motor supply
- Schottky clamping diodes
- Power toggle switch; feature list also states "Solid state switch for power"
- Test switches (A and B) for every channel
- Power indicator LED and motor status indicator LEDs
- 3 mm mounting holes for standard PCB stands
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Warranty: 12 months, manufacturing defects only
- In the box: 1 x FD04A Rev2.0 board, 1 x 14 way IDE cable connector

## Interfaces and compatibility
- Control pins through a 7 x 2 (14-way) IDE socket or through extra solder pads
- Control pins 1-8: Motor 1 direction, Motor 1 enable/Speed Control, Motor 2 direction, Motor 2 enable/Speed Control, Motor 3 direction, Motor 3 enable/Speed Control, Motor 4 direction, Motor 4 enable/Speed Control; V = 5V output; G = ground; x = not connected
- POWER terminal block for motor supply; four MOTOR terminal blocks M1 to M4
- IDE connector compatible with FD04A Rev1.0; can replace FD04A Rev1.0 in the PR19
- 5V from the V pin can supply the PR19 main board; do not supply another 5V into the V pin
- Arduino: Cytron Motor Drivers Library (PWM_DIR_DUAL example)
- PIC sample code: DIY-PR19-PIC16F777 on GitHub

## Use cases
- Driving four brushed DC motors from one board
- Replacing FD04A Rev1.0 in the PR19 robot or other FD04A projects

## Known limitations
- Motor supply maximum is 15 V
- Continuous current is 1.5 A per channel; peak 2.5 A
- Maximum PWM frequency 10 kHz
- Logic input maximum 5.5 V
- Do not supply 5V into the V pin
- Over-current, thermal and under-voltage protection are not stated

## Positioning (kept apart from specs)
- The manual describes FD04A Rev2.0 as "an enhanced version of FD04A Rev1.0"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-1.5amp-7v-25v-dc-motor-driver-4-channels

## Datasheet
https://docs.google.com/document/d/1SWq9YtW6gsr8n9eIz2X8ek8Na8KoJ30whM5HsOdCnSc/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1SWq9YtW6gsr8n9eIz2X8ek8Na8KoJ30whM5HsOdCnSc/edit

# Product fact sheets

## Product name
MD10C 10Amp 5V-30V DC Motor Driver (Rev 3.0)

## Aliases
MD10C, MD10C R3.0, MD10C Rev3.0, Cytron MD10C, 10Amp 5V-30V DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from one 5–30 V supply and controlled with PWM and DIR signals from a microcontroller. It is rated 13 A continuous and 30 A peak for up to 10 seconds.

## Specs and functions
- Product code: MD10C; current revision Rev 3.0 (packing list "1 x MD10C Rev3.0")
- Channels: 1 (bi-directional, one DC brushed motor, two terminals)
- Power input voltage (Vmotor): 5 V to 30 V (Rev 3.0)
- Single power source: "powered from a single power source, the Vmotor only. No additional Vin is required."
- Maximum continuous motor current: 13 A, tested under 25℃ room temperature without airflow and heatsink
- Peak motor current: 30 A, must not exceed 10 seconds
- Logic input high level: 3 V min, 30 V max (user's manual, live Google Doc); 3 V min, 5.5 V max (PDF copy of the same manual version); product page: "3.3 and 5V"
- Logic input low level: 0 V min, 0 V typical, 0.5 V max
- Maximum PWM frequency: 20 kHz; output frequency is the same as input frequency
- Control modes: Sign-Magnitude PWM (PWM pin = speed, DIR pin = direction) and Locked-Antiphase PWM (PWM pin tied to logic high, PWM signal on DIR; 50% duty = stop); selected by wiring
- Truth table: PWM Low = Brake Low (both outputs low, DIR don't care); PWM High + DIR Low = Forward (A high, B low); PWM High + DIR High = reverse (A low, B high)
- Full NMOS H-Bridge; manual states no heat sink is required
- Solid-state components (replaces the relay-based MD10B, launched 2008)
- Regenerative Braking (product page)
- Test Button A and Test Button B to run the motor without a controller
- Red LED A / Red LED B show current direction; green power LED
- Dimensions: 75 mm x 43 mm
- Certifications (Cytron product page Q&A reply): CE, FCC and RoHS
- PCB: standard FR4 (Cytron product page Q&A reply)
- Packing list: 1 x MD10C R3.0; 1 x 2510 PCB connector 3-way female; 3 x 2510 terminal pin; 4 x plastic spacer (~7 mm)
- Warranty: 12 months, manufacturing defects only
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Green terminal block: pin 1 V motor Power + (5V to 30VDC), pin 2 V motor Power - (ground)
- Black terminal block: pin 3 Motor Output A, pin 4 Motor Output B
- Control header (2510, 3 pins): pin 1 GND, pin 2 PWM (up to 20 kHz), pin 3 DIR
- Compatible with Arduino and Raspberry Pi (3.3V logic PWM)
- Not an Arduino shield; connect with wires
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, 3, 4);`, `setSpeed(-255 to 255)`
- PIC: SK40C + PIC16F877A sample code (github.com/CytronTechnologies/SK40C-MD10C)
- Not isolated: controller and motor share a common GND
- RC servo signal: not supported
- Analog input / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive high current brushed DC motor up to 13A continuously
- Use MD10C even without any controller (test buttons)
- Control a DC motor from Arduino (sign-magnitude and locked-antiphase)
- Control a DC motor from SK40C with PIC16F877A
- Driving two DC geared motors with MD10C by using SKPS + SK40C
- Measuring DC motor RPM through built-in Hall sensor encoder

## Known limitations
- No reverse polarity protection: check polarity before power-up
- Peak 30 A only for 10 seconds or less; 13 A continuous tested only at 25℃ without airflow or heatsink
- Not for RC PWM (TTL PWM from a microcontroller only)
- Brushed DC motors only
- Not isolated; controller and motor share a common GND
- PWM pin Low brakes the motor (Brake Low) regardless of DIR
- Motor direction depends on wiring
- Logic-input maximum differs between copies of the user's manual (30 V vs 5.5 V); product page states 3.3 and 5V
- Product name says "10Amp" but the continuous rating is 13 A
- Over-current, thermal and under-voltage protection: [NOT STATED]
- Battery vs switching power supply guidance: [NOT STATED]

## Positioning (kept apart from specs)
- "another version of the MD10B … It offers several enhancements over the MD10B such as support for both locked-antiphase and sign-magnitude PWM signal as well as using full solid state components which result in faster response time and eliminate the wear and tear of the mechanical relay"
- Product page points to MD13S as an SMD version with similar specs at a lower price

## Price band
- $11.50 on www.cytron.io (10 or more: $10.63; 50 or more: $9.20), read 16 Oct 2026

## Product page
https://my.cytron.io/p-10amp-5v-30v-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1rgQzn-nWn-qcWNnHjDZvIYqUrdCeBQQxXA-TU3BF0AQ/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1rgQzn-nWn-qcWNnHjDZvIYqUrdCeBQQxXA-TU3BF0AQ/view

# Product fact sheets

## Product name
10 Amp 7V-30V Potentiometer & Switch Control DC Motor Driver (MD10-POT)

## Aliases
MD10-POT, MD10POT, Cytron MD10-POT, 10 Amp 7V-30V Potentiometer & Switch Control DC Motor Driver, Potentiometer and Switch Control 10Amp DC Motor Driver

## What it is
A single-channel brushed DC motor driver, 7–30 V input, 10 A continuous and 30 A peak for less than 10 seconds. Speed and direction are set with a 10KΩ potentiometer and an SPDT switch, or with PWM and DIR signals from a controller.

## Specs and functions
- Product code: MD10-POT
- Channels: 1
- Power input voltage: 7 V min, 30 V max
- Maximum motor current, continuous: 10 A
- Maximum motor current, peak: 30 A (less than 10 seconds)
- Logic input voltage, low level (PWM, DIR): 0 V min, 0.5 V max
- Logic input voltage, high level (PWM, DIR): 3 V min, 30 V max
- Internal PWM generator frequency: 9 KHz min, 11 KHz max (output frequency when potentiometer is used)
- External PWM input frequency: DC to 20 KHz (output frequency = input frequency)
- Speed control: 10KΩ potentiometer or PWM signal; direction control: SPDT switch or DIR pin
- Truth table: PWM Low = both outputs low (brake, DIR don't care); PWM High + DIR Low = MA high, MB low (forward); PWM High + DIR High = MA low, MB high (reverse)
- Test buttons to test the functionality of the motor / driver
- Power LED; Motor Status LEDs (turn on when the motor is running)
- 3D printable case STL file linked on the product page
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Protections (reverse polarity, over-current, thermal, under-voltage): [NOT STATED]
- Packing list: [NOT STATED]
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Power Input Terminal: connect to battery
- Motor Output Terminal: connect to motor (outputs MA and MB)
- Speed Control Potentiometer connector: 10KΩ potentiometer
- Direction Switch connector: SPDT switch
- PWM/DIR Input: PWM signal for speed, DIR pin for direction
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, pwmPin, dirPin)`
- Connector pin order: [NOT STATED]
- Locked-antiphase PWM: [NOT STATED]
- RC, analog voltage or serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Control a DC motor's speed with a 10KΩ potentiometer and its direction with an SPDT switch
- Control the motor with a PWM signal and a DIR pin
- Test the functionality of the motor / driver with the test buttons

## Known limitations
- Power input 7 V minimum, 30 V maximum
- Peak 30 A only for less than 10 seconds; 10 A continuous
- Logic low must be 0.5 V or below
- PWM Low brakes the motor regardless of DIR
- Single channel, brushed DC motor
- Forward/reverse depends on motor wiring
- Protections (reverse polarity, over-current, thermal, under-voltage): [NOT STATED]
- Switching power supply / regenerative current guidance: [NOT STATED]

## Positioning (kept apart from specs)
[NOT STATED]

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-10-amp-7v-30v-potentiometer-and-switch-control-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1U_dn6OCEw76pqJaIzZYuWqWoU1C9APwpNp8qztaJ1uA/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1U_dn6OCEw76pqJaIzZYuWqWoU1C9APwpNp8qztaJ1uA/view

# Product fact sheets

## Product name
10Amp 7V-30V DC Motor Driver Shield for Arduino

## Aliases
SHIELD-MD10, SHIELD-MD10 R2, Cytron SHIELD-MD10, Cytron 10A Motor Driver Shield, Shield MD10 Rev 2.0

## What it is
A single-channel Arduino shield that drives one brushed DC motor at up to 10 A continuous. Speed and direction come from a PWM pin and a DIR pin selected with mini jumpers.

## Specs and functions
- Motor supply voltage (Rev 2.0): feature list "7V to 30V"; the same manual's Absolute Maximum Rating table says 7 V min, 25 V max (both from the Rev2.0 user manual)
- Rev 1.0: 7 V to 25 V
- Maximum continuous motor current: 10 A
- Peak motor current: 15 A, must not exceed 10 seconds
- 1 channel, bi-directional
- Logic input high level (VIOH): 3 V min, 5.5 V max
- Logic input low level (VIOL): 0 V min, 0 V typical, 0.5 V max
- 3.3V and 5V logic level input
- Maximum PWM frequency: 10 kHz
- Fully NMOS H-Bridge; no heat sink is required
- Test Button A (current A to B) and Test Button B (current B to A)
- Red LED A, Red LED B, Green Power LED
- Reset button for the Arduino main board
- Rev 2.0 boards labelled "SHIELD-MD10 R2" on front and back
- Packing list: 1 x SHIELD-MD10 shield, 2 x mini jumper
- Warranty: 12 months, manufacturing defects only
- Over-current, thermal, under-voltage, reverse-polarity protection: [NOT STATED]
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- PWM pin selectable: D3, D5, D6, D9, D10 or D11 (default D3)
- DIR pin selectable: D2, D4, D7, D8, D12 or D13 (default D2)
- Terminal block: POWER +, POWER -, Motor Output A, Motor Output B
- Stackable digital, analog and power headers; only RST and GND of the power header connect to the shield
- Optional External Control header for microcontrollers other than Arduino
- Compatible with Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo "and possibly other pin compatible main boards"
- Arduino library: Cytron Motor Drivers Library, PWM_DIR example
- 3D files (STEP, IGS) for SHIELD-MD10 R2 on GitHub

## Use cases
- Controlling one high-current brushed DC motor from an Arduino UNO, Duemilanove, Mega or Leonardo
- Controlling the motor from other microcontrollers through the Optional External Control header

## Known limitations
- Single channel only
- Peak 15 A for no more than 10 seconds
- PWM frequency up to 10 kHz
- The shield does not power the Arduino; the Arduino needs its own power source
- Power up the Arduino and load the sketch before powering the shield
- Rev2.0 manual states two different maximum voltages (30 V feature list, 25 V table)
- Rev 1.0 boards: 25 V maximum
- No protection features stated

## Positioning (kept apart from specs)
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay."

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino

## Datasheet
https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1zITY9dHK26-iBkS9AnZ0ZUS3Z8K8NzLu3t709F7r7us/view

# Product fact sheets

## Product name
MDD10A 10Amp 5V-30V DC Motor Driver (2 Channels) (Rev 2.0)

## Aliases
MDD10A, MDD10A Rev2.0, Cytron MDD10A, 10Amp 5V-30V DC Motor Driver (2 Channels), Dual Channel 10A DC Motor Driver

## What it is
A dual-channel, bi-directional driver for two brushed DC motors, powered from 5–30 V and controlled with a PWM and a DIR signal per channel from a microcontroller. Each channel is rated 10 A continuous and 30 A peak for up to 10 seconds.

## Specs and functions
- Product code: MDD10A; current revision Rev 2.0 (boards shipped after Jan 2017)
- Channels: 2 (bi-directional, brushed DC motors)
- Power input voltage: 5 V to 30 V (Rev 2.0); earlier boards 25 V max
- Maximum continuous motor current: 10 A per channel, tested in room temperature at 25°C
- Peak motor current: 30 A per channel, must not exceed 10 seconds
- Logic input high level: 3 V min, 5.5 V max
- Logic input low level: 0 V min, 0 V typical, 0.5 V max
- Logic level input: 3.3V and 5V (for PWM and DIR) (product page)
- Maximum PWM frequency: 20 kHz; actual output frequency is the same as input frequency
- Control modes: Sign-Magnitude PWM (PWM = speed, DIR = direction) and Locked-Antiphase PWM (PWM pin tied to logic high, PWM signal on DIR; 50% duty = stop); selected by wiring
- Truth table (each channel): PWM Low = both outputs low (DIR don't care); PWM High + DIR Low = A high, B low; PWM High + DIR High = A low, B high
- Fully NMOS H-Bridge; manual states no heat sink is required
- Solid-state components (no mechanical relay)
- Regenerative Braking (product page)
- 4 test buttons (M1A, M1B, M2A, M2B), 2 per channel
- Red LEDs M1A, M1B, M2A, M2B show current direction; green power LED
- Dimensions: 84.5 mm x 62 mm
- Packing list: 1 x MDD10A; 1 x 2510 PCB connector 5-way female; 5 x 2510 terminal pin
- Warranty: 12 months, manufacturing defects only
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Input header (2510, 5 pins): pin 1 GND, pin 2 PWM2, pin 3 DIR2, pin 4 PWM1, pin 5 DIR1
- Terminal block (6 pins): 1 Motor 1 Output B, 2 Motor 1 Output A, 3 POWER +, 4 POWER -, 5 Motor 2 Output A, 6 Motor 2 Output B
- Compatible with Arduino and Raspberry Pi (3.3V and 5V logic)
- Not an Arduino shield; connect with wires
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR_DUAL example, one `CytronMD(PWM_DIR, pwmPin, dirPin)` object per channel
- Getting started with SK40C (PIC) in the user's manual
- RC servo signal: not supported
- Analog input / serial input: [NOT STATED]
- Isolation: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive 2 brushed DC motors with high current up to 10A continuously
- Control the motors manually with the onboard test buttons
- Control two DC motors from Arduino UNO
- Control two DC motors from SK40C

## Known limitations
- Use a battery when driving an inductive load such as a DC brush motor; most switching power supplies shut down when regenerative current from the motor is detected
- If a switching power supply is needed, a battery with the same rated voltage must be in parallel with it to absorb the regenerative current
- No reverse polarity protection at Vmotor (product page): check polarity before power-up
- Logic inputs 5.5 V max (not for 12 V or 24 V logic)
- Peak 30 A per channel only for 10 seconds or less; 10 A continuous tested at 25°C
- Not for RC PWM (TTL PWM from a microcontroller only)
- Brushed DC motors only
- PWM Low brakes the channel (both outputs low) regardless of DIR
- Motor direction depends on wiring
- Header order is PWM2/DIR2 (pins 2–3) before PWM1/DIR1 (pins 4–5)
- Boards shipped before Jan 2017 are limited to 25 V
- Over-current, thermal and under-voltage protection: [NOT STATED]

## Positioning (kept apart from specs)
- "the dual-channel version of MD10C" (user's manual)
- Solid-state components "result in faster response time and eliminate the wear and tear of the mechanical relay"

## Price band
- www.cytron.io volume prices: 5 or more $22.33; 20 or more $21.15; 50 or more $19.98 (read 16 Oct 2026); single-unit price [NOT STATED]

## Product page
https://www.cytron.io/p-10amp-5v-30v-dc-motor-driver-2-channels

## Datasheet
https://docs.google.com/document/d/1ol8nICCTTw5dAHHE_hju08cCVH2GN5_Y3cGC6B4Gbas/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1ol8nICCTTw5dAHHE_hju08cCVH2GN5_Y3cGC6B4Gbas/edit

# Product fact sheets

## Product name
10Amp 7V-30V DC Motor Driver Shield for Arduino (2 Channels)

## Aliases
SHIELD-MDD10, Cytron SHIELD-MDD10, Shield MDD10, 10A Dual Channel DC Motor Driver Shield for Arduino

## What it is
An Arduino-shield-format driver for two brushed DC motors, 10 A continuous per channel from a 7–30 V battery. Each motor is controlled by a PWM input and a DIR input on jumper-selected Arduino pins.

## Specs and functions
- Power input voltage: 7 V to 30 V (VB+ / VB-)
- Motor current per channel: 10 A continuous; 30 A peak
- Peak current is limited by the overcurrent protection circuit; actual limit depends on board temperature; 30 A value is at room temperature (25 - 30 degree Celsius); no peak duration stated
- 2 channels, PWM + DIR control per channel
- Logic input (PWM & DIR): low level 0 V to 0.8 V; high level 1.5 V to 5.5 V
- PWM frequency: standard DC to 20 kHz; extended 20 kHz to 40 kHz (continuous motor current reduced in the extended range); output frequency is same as input frequency
- Truth table: PWM low = brake (both outputs low); PWM high + DIR low = forward; PWM high + DIR high = backward (actual direction depends on motor connection)
- Built-in 5 V buck regulator powers the Arduino by default; DC +5V output 500 mA max
- Overcurrent protection with active current limiting (OC LED on when limiting)
- Temperature protection: higher board temperature gives a lower current-limit threshold
- Undervoltage shutdown (ERR LED on)
- Test buttons MA (forward) and MB (backward), run the motor at full speed
- LEDs: Power, motor status MA/MB, Error, OC
- Arduino reset button
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Arduino shield form factor: male header (bottom) to the Arduino, female header (top) for stacking other shields
- PWM/DIR Input Pin Selector to choose the Arduino pins for PWM and DIR; selectable pins: [NOT STATED]
- 5V Output solder jumper: cut the track to stop the shield powering the Arduino 5V pin
- Power Input Terminal VB+ / VB-; Motor Output Terminals MA / MB per motor
- Arduino library: Cytron Motor Drivers Library, PWM_DIR_DUAL example (CytronMD with PWM_DIR)
- Logic high threshold 1.5 V to 5.5 V
- 3D CAD file linked from the product page

## Use cases
- Driving two brushed DC motors from an Arduino
- Driving a motor that stalls or is oversized, with current limiting protecting the driver ("when the motor stalls or an oversized motor is hooked up")

## Known limitations
- No reverse polarity protection: "Connecting in reverse polarity will damage the motor driver instantaneously."
- 5 V output to the Arduino is 500 mA max
- Continuous current is reduced when PWM runs at 20–40 kHz
- Current-limit threshold falls as the board heats up
- Output shuts down if the power input drops below the lower limit (threshold [NOT STATED])
- Locked-antiphase operation: [NOT STATED]

## Positioning (kept apart from specs)
- [NOT STATED]

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino-2-channels

## Datasheet
https://docs.google.com/document/d/1QHlQbs6f5fY_BMBs3hJRg1QLFe4yqy4nyH3mBavZ2-0

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1QHlQbs6f5fY_BMBs3hJRg1QLFe4yqy4nyH3mBavZ2-0

# Product fact sheets

## Product name
10Amp 6V-24V DC Motor Driver HAT for Raspberry Pi (2 Channels)

## Aliases
HAT-MDD10, Cytron HAT-MDD10, 10Amp DC Motor Driver for Raspberry Pi, MDD10 HAT for Raspberry Pi

## What it is
A Raspberry Pi HAT that drives two brushed DC motors at up to 10 A continuous each from a 6–24 V supply. Each motor is controlled by a PWM and a DIR signal on fixed Raspberry Pi GPIOs.

## Specs and functions
- Power input voltage: 6 V to 24 V (absolute maximum)
- Maximum continuous motor current: 10 A (without heatsink at 25 ℃)
- Peak motor current: 30 A, must not exceed 10 seconds
- Current limiting at 30 A
- 2 channels, bi-directional
- Logic input high level (VIOH): 3 V min, 5.5 V max
- Logic input low level (VIOL): 0 V min, 0 V typical, 0.5 V max
- 3.3V and 5V logic level input
- Maximum PWM frequency: 20 kHz (actual output frequency is same as input frequency)
- Sign-magnitude PWM and locked-antiphase PWM
- Truth table: PWM low = both outputs low; PWM high + DIR low = A high, B low; PWM high + DIR high = A low, B high
- Fully NMOS H-Bridge; no heat sink is required
- Test switches M1A, M1B, M2A, M2B; LED indicators per output; power LED
- Dimension: 67.5 mm x 59 mm
- Packing list: 1 x Hat-MDD10, 1 x PC104 Header Pin (2x20) (CN-PH-PC104)
- Warranty: 12 months, manufacturing defects only
- Thermal, under-voltage, reverse-polarity protection: [NOT STATED]

## Interfaces and compatibility
- PWM1 = GPIO12, DIR1 = GPIO26, PWM2 = GPIO13, DIR2 = GPIO24 (BCM numbering)
- Terminal block: M1A, M1B, VM, GND, M2A, M2B
- Raspberry Pi compatible connector; Raspberry Pi 3 named in the manual and sample code
- Python sample code (RPi.GPIO) for sign-magnitude (HatMDD10SM.py) and locked-antiphase (HatMDD10LA.py) on GitHub; written in Python 2 syntax
- Whether it powers the Raspberry Pi: [NOT STATED]

## Use cases
- Driving two high-current brushed DC motors with a Raspberry Pi as the controller

## Known limitations
- Supports TTL PWM from a microcontroller, not PWM from an RC receiver
- 24 V is the absolute maximum supply
- Peak 30 A must not exceed 10 seconds
- 10 A continuous rating is without heatsink at 25 ℃
- GPIO pins are fixed (no pin selector described)
- Sample code uses Python 2 print statements

## Positioning (kept apart from specs)
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay."

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-10amp-6v-24v-dc-motor-driver-hat-for-rpi-2-channels

## Datasheet
https://docs.google.com/document/d/19JLDnzU0y-9FKH4ZXm0lk4xtMJKtaKTDBT5ulGgj8UI/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/19JLDnzU0y-9FKH4ZXm0lk4xtMJKtaKTDBT5ulGgj8UI/view

# Product fact sheets

## Product name
MD13S 13Amp 6V-30V DC Motor Driver

## Aliases
MD13S, Cytron MD13S, 13Amp 6V-30V DC Motor Driver, 13Amp DC Motor Driver, MD13S 13Amp DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 6 V to 30 V and controlled with a PWM and a DIR signal from a microcontroller. It is rated 13 A continuous and 30 A peak for up to 10 seconds.

## Specs and functions
- Product code: MD13S; user's manual V1.1, June 2018
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage: 6 V to 30 V
- Maximum continuous motor current: 13 A (without heatsink at 25℃)
- Peak motor current: 30 A, must not exceed 10 seconds
- Current limiting at 30A; OC LED lights when output current is over the 30A limit
- Logic input high level: 3 V min, 5.5 V max
- Logic input low level: 0 V min, 0 V typical, 0.5 V max
- 3.3V and 5V logic level input
- Maximum PWM frequency: 20 KHz; actual output frequency is same as input frequency
- Control modes: sign-magnitude PWM (PWM = speed, DIR = direction) and locked-antiphase PWM (PWM pin held high, PWM signal on DIR; 50% duty cycle = motor stops); selected by wiring
- Truth table: PWM Low = both outputs low (DIR don't care); PWM High + DIR Low = A high, B low; PWM High + DIR High = A low, B high
- Fully NMOS H-Bridge; manual states no heat sink is required
- Regenerative Braking (product page)
- 2 test switches (MA, MB)
- LEDs: MA, MB (current direction), Power, OC (Over Current), ERR (fault detected in on-board MOSFET driver)
- GROVE compatible connector
- SMD compatible
- RoHS, FCC and CE compliance (product page)
- Dimensions: 61 mm x 33 mm
- Packing list (user's manual): 1 x MD13S 13A DC Motor Driver; 2 x Terminal socket, Black for power and Green for Motor; Grove connector with cable
- Packing list (product page): 1 x MD13S motor driver board; 1 x Green + Black 2-way terminal blocks (Normally Black is for Motor, Green is for Power); 1 x Grove connector (Grove to Grove)
- Warranty: 12 months, manufacturing defects only
- Thermal protection: [NOT STATED]
- Under-voltage protection: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Terminal block: POWER + (6V to 30V), POWER -, Motor Output A, Motor Output B
- Input pins: GND (logic ground), PWM (speed control, not for RC PWM), DIR (direction control)
- Grove-compatible input connector; Grove pinout [NOT STATED]
- Works with TTL PWM from a microcontroller at 3.3 V or 5 V logic
- Not an Arduino shield; can be used with wire connection
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, 3, 4)`
- RC servo signal: not supported
- Analog input / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive a high current brushed DC motor up to 13A continuously
- Bi-directional control for one brushed DC motor with PWM and DIR signals from a microcontroller
- Test the motor manually with the onboard MA and MB test switches

## Known limitations
- No polarity protection (product page): check polarity before power-up
- Logic inputs 5.5 V max (not for 12 V or 24 V logic)
- Not for RC receiver PWM (TTL PWM from a microcontroller only)
- Peak 30 A only for 10 seconds or less; 13 A continuous stated without heatsink at 25℃
- Current limiting at 30A; behaviour beyond the limit [NOT STATED]
- One brushed DC motor only
- PWM Low sets both outputs low regardless of DIR
- Motor direction depends on wiring
- Battery vs switching power supply guidance: [NOT STATED] in the user's manual
- Terminal socket colours differ between user's manual (Black for power, Green for Motor) and product page (Normally Black is for Motor, Green is for Power)
- Listed as Out Of Stock on my.cytron.io (16 Oct 2026)

## Positioning (kept apart from specs)
- "Solid state components provide faster response time and eliminate the wear and tear of mechanical relay"
- "Fully NMOS H-Bridge for better efficiency and no heat sink is required"

## Price band
- my.cytron.io: 1 unit RM55.60; 5 or more RM52.80; 20 or more RM50.00; 50 or more RM47.20 (read 16 Oct 2026)

## Product page
https://my.cytron.io/p-13amp-6v-30v-dc-motor-driver

## Datasheet
https://www.electrokit.com/upload/product/41018/41018267/MD13S%20User's%20Manual.pdf

## Source type
Datasheet

## Source link
https://www.electrokit.com/upload/product/41018/41018267/MD13S%20User's%20Manual.pdf

# Product fact sheets

## Product name
MD20A 20Amp 6V-30V DC Motor Driver

## Aliases
MD20A, Cytron MD20A, 20Amp 6V-30V DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 6 V to 30 V and controlled with a PWM and a DIR signal. It is rated 20 A continuous and 60 A peak, with overcurrent current limiting, temperature-dependent current limit and undervoltage shutdown.

## Specs and functions
- Product code: MD20A; datasheet Rev 1.0, Feb 2019
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage: 6 V min, 30 V max
- Maximum motor current: 20 A continuous
- Peak motor current: 60 A, limited by the overcurrent protection circuit; actual current limit depends on board temperature; value shown is at room temperature (25 - 30 degree Celsius)
- Peak current duration: [NOT STATED]
- Logic input voltage (PWM & DIR) low level: 0 V min, 0.8 V max
- Logic input voltage (PWM & DIR) high level: 1.5 V min, 15 V max
- Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (product page)
- PWM frequency, standard: DC to 20 KHz; output frequency is same as input frequency
- PWM frequency, extended: 20 to 40 KHz; continuous motor current will be reduced in the extended range
- Product page states PWM frequency up to 20kHz
- Control: PWM & DIR inputs; compatible with sign-magnitude and locked-antiphase PWM operation (product page)
- Truth table: PWM Low = MA Low, MB Low (Brake), DIR don't care; PWM High + DIR Low = MA High, MB Low (Forward); PWM High + DIR High = MA Low, MB High (Backward)
- Overcurrent protection with active current limiting: PWM is chopped and motor current is held at the maximum current limit; OC LED on
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shut down when power input drops below the lower limit; ERR LED on
- Test buttons MA (Forward) and MB (Backward); motor runs at full speed
- LEDs: Power, Motor Status (MA, MB), Error (undervoltage shutdown or hardware fault), OC (Overcurrent)
- Packing list: 1 x 20Amp 6V-30V DC Motor Driver; 4 x PCB Spacer
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Power Input Terminal: VB+ (positive), VB- (negative); connect to battery
- Motor Output Terminal: MA, MB
- PWM/DIR Input: DIR (direction input), PWM (PWM input for motor speed control), GND (signal ground)
- Compatible with Arduino, Raspberry Pi, PLC, etc (product page)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, 3, 4)`
- RC, analog and serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Bidirectional control for one brushed DC motor
- Control the motor with PWM & DIR signal from Arduino, Raspberry Pi or PLC
- Test the functionality of the motor driver with the onboard test buttons

## Known limitations
- Power input does not have reverse-voltage protection; connecting in reverse polarity will damage the motor driver instantaneously
- Peak current is limited by the overcurrent protection circuit and the limit falls as board temperature rises
- Continuous motor current is reduced when PWM operates in the extended 20 to 40 KHz range
- Undervoltage threshold: [NOT STATED]
- Logic inputs 15 V max
- One brushed DC motor only
- PWM Low brakes the motor regardless of DIR
- Motor direction depends on motor connection; swapping MA and MB reverses it
- Battery vs switching power supply guidance: [NOT STATED] beyond "Connect to battery."

## Positioning (kept apart from specs)
- "Inputs compatible with 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)." (product page)
- Overcurrent protection "prevents the motor driver from damage when the motor stalls or an oversized motor is hooked up" (datasheet)

## Price band
- www.cytron.io: $17.25; 10 or more $15.87; 50 or more $14.66 (read 16 Oct 2026; currency shown only as "$")

## Product page
https://www.cytron.io/p-20amp-6v-30v-dc-motor-driver

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-254/pdf/md20a_datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-254/pdf/md20a_datasheet.pdf

# Product fact sheets

## Product name
MDD20A 20Amp 6V-30V DC Motor Driver (2 Channels)

## Aliases
MDD20A, Cytron MDD20A, 20Amp 6V-30V DC Motor Driver (2 Channels), 20A 6V-30V Dual DC Motor Driver, Dual Channel 20A DC Motor Driver

## What it is
A dual-channel, bi-directional driver for two brushed DC motors, powered from 6–30 V and controlled with a PWM and a DIR signal per channel. Each channel is rated 20 A continuous and 60 A peak.

## Specs and functions
- Product code: MDD20A; datasheet Rev 1.0, July 2020
- Channels: 2 (bi-directional, brushed DC motors)
- Power input voltage: 6 V min, 30 V max
- Maximum motor current per channel: 20 A continuous, 60 A peak
- Peak current is limited by the overcurrent protection circuit; actual current limit depends on board temperature; value shown is at room temperature (25 - 30 degree Celsius); peak duration [NOT STATED]
- Logic input voltage (PWM & DIR): low level 0 V to 0.8 V; high level 1.5 V to 15 V; maximum input voltage can be extended up to 30V by connecting a 10K ohm resistor in series
- Logic compatibility (product page): 1.8V, 3.3V, 5V and 12V logic (Arduino, Raspberry Pi, PLC, etc)
- PWM frequency: standard up to 20 kHz; extended 20 kHz to 40 kHz, where continuous motor current will be reduced; output frequency is same as input frequency
- Control: PWM & DIR per channel (PWMx = speed, DIRx = direction)
- Truth table (each channel): PWMx Low = MxA Low, MxB Low (Brake, DIRx don't care); PWMx High + DIRx Low = MxA High, MxB Low (Forward); PWMx High + DIRx High = MxA Low, MxB High (Backward); actual direction depends on motor connection
- Locked-antiphase PWM: "Compatible with sign-magnitude and locked-antiphase PWM operation" (product page; not mentioned in the datasheet)
- Overcurrent protection with active current limiting: PWM to the motor is chopped and motor current is held at the maximum current limit; OC LED turns on
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shuts down when power input voltage drops below the lower limit; Error LED turns on
- Test buttons: motor will run at full speed
- LEDs: Power LED, Motor Status LEDs (MxA forward, MxB backward), Error LED (undervoltage shutdown or hardware fault), OC (Overcurrent) LED
- Weight: 89g (product page)
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Packing list (product page): 1 x 20Amp 6V-30V DC Motor Driver (2 Channels), 4 x PCB Spacer
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Power input terminal: VB+ (positive), VB- (negative); connect to battery
- Motor output terminals: MxA / MxB per channel
- PWM/DIR input per channel: DIRx (direction input), PWMx (PWM input for motor speed control), GND (signal ground)
- No 5V output or separate logic supply listed
- Compatible with Arduino, Raspberry Pi, PLC, etc (product page)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR_DUAL example, one `CytronMD(PWM_DIR, pwmPin, dirPin)` object per channel
- RC / analog / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Bidirectional control for two brushed DC motors
- Automated Guided Vehicle (AGV)
- Solar Tracker
- Game Simulator
- Mobile Robot
- Automation Machine

## Known limitations
- No reverse polarity protection: connecting in reverse polarity will damage the motor driver instantaneously
- Logic input high level max 15 V; up to 30 V only with a 10K ohm resistor in series
- Continuous motor current is reduced when PWM operates in the extended 20–40 kHz range
- Peak current is limited by the overcurrent protection circuit and the limit drops as board temperature rises
- PWM Low brakes the channel regardless of DIR
- Motor direction depends on motor wiring
- Brushed DC motors only
- Switching power supply / regenerative current guidance: [NOT STATED]
- Heatsink / fan requirement: [NOT STATED]

## Positioning (kept apart from specs)
- Product page features: "Buttons for quick testing." "LEDs for motors output state."

## Price band
- www.cytron.io volume prices: 5 or more $33.25; 20 or more $31.50; 50 or more $29.75 (read 16 Oct 2026); single-unit price [NOT STATED]

## Product page
https://www.cytron.io/p-20amp-6v-30v-dc-motor-driver-2-channels

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-287/pdf/cytron-20a-6v-30v-dual-dc-motor-driver-datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-287/pdf/cytron-20a-6v-30v-dual-dc-motor-driver-datasheet.pdf

# Product fact sheets

## Product name
MD25HV 25Amp 7V-58V High Voltage DC Motor Driver

## Aliases
MD25HV, Cytron MD25HV, 25Amp 7V-58V High Voltage DC Motor Driver, MD25HV High Voltage 7V-58V 25Amp DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 7–58 V and rated 25 A continuous and 60 A peak. It is controlled either by PWM/DIR signals or by a potentiometer and direction switch.

## Specs and functions
- Product code: MD25HV; datasheet Rev 1.0, Jan 2019
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage: 7 V min, 58 V max
- Maximum motor current: 25 A continuous, 60 A peak; peak duration [NOT STATED]
- 5V output voltage: 4.9 V min, 5.1 V max; 5V output maximum current: 250 mA
- Potentiometer analog input voltage (POT 2): 0 V to 5 V
- Direction switch input voltage (MA, MB): low level 0 V to 0.8 V; high level 3 V to 5 V
- Logic input voltage (PWM, DIR): low level 0 V to 0.8 V; high level 3 V to 30 V
- Logic compatibility (product page): 1.8V, 3.3V, 5V, 12V and 24V logic (Arduino, Raspberry Pi, PLC, etc); datasheet: logic input high level min 3 V
- PWM input frequency: DC to 40 kHz
- Motor driver output PWM frequency: 16 kHz, independent of input frequency
- Lock-Antiphase PWM is not supported
- Input Mode 1: PWM/DIR input; Input Mode 2: Potentiometer/Switch input; mode selection method [NOT STATED]
- Truth table (PWM/DIR): PWM Low = MA Low, MB Low (Brake, DIR don't care); PWM High + DIR Low = MA High, MB Low (Forward); PWM High + DIR High = MA Low, MB High (Backward); actual direction depends on motor connection
- Overcurrent protection with active current limiting: PWM to the motor is chopped and motor current is held at the maximum current limit; OC LED turns on
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shuts down when power input voltage drops below the lower limit
- Error LED blink codes: 2 = MOSFET Driver Error (undervoltage error or hardware failure); 3 = Overvoltage Error (power input voltage has exceeded the maximum rating); 4 = Overheat Error (board temperature over 80℃ (176℉), warning only, driver can still be safely operated)
- Test buttons MA (forward) and MB (backward): motor will run at 78% of full speed
- LEDs: Power LED, Error LED, OC (Overcurrent) LED, Motor Status LEDs MA (forward) / MB (backward)
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Packing list (product page): 1 x MD25HV, 1 x Potentiometer with connector, 1 x Rocker switch with connector, 4 x Nylon PCB Standoffs/Spacers
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Power input terminal: VB+ (positive), VB- (negative); connect to battery
- Motor output terminal: MA / MB
- PWM/DIR input: PWM (speed), DIR (direction), 5VO (5V output, can be used to power Arduino and other MCU), GND (signal ground)
- Speed control potentiometer (10KΩ): POT 1 (GND, lowest speed), POT 2 (Analog In, middle pin), POT 3 (5V, highest speed)
- Direction switch (SPDT): MA (short to GND to run forward), COM (connected to GND internally), MB (short to GND to run backward); MA and MB internally pulled high
- Compatible with Arduino, Raspberry Pi, PLC, etc (product page)
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD(PWM_DIR, pwmPin, dirPin)`
- RC / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Bidirectional control for one brushed DC motor
- Control the motor with PWM/DIR signal from Arduino and other MCU
- Control the motor speed with a 10KΩ potentiometer and direction with an SPDT switch

## Known limitations
- No reverse polarity protection: connecting in reverse polarity will damage the motor driver instantaneously
- Lock-Antiphase PWM is not supported
- Output PWM is 16 kHz regardless of input PWM frequency
- Logic input high level min 3 V (datasheet), although the product page lists 1.8V logic
- Direction switch inputs (MA, MB) max 5 V
- 5V output max 250 mA
- With a switching power supply, connect a motor shunt regulator or rechargeable battery with the same voltage in parallel to absorb regenerative energy from the motor during deceleration (otherwise Overvoltage Error)
- Current limiting threshold drops as board temperature rises
- Test buttons run the motor at 78% of full speed only
- PWM Low brakes the motor regardless of DIR
- Brushed DC motors only
- Heatsink / fan requirement: [NOT STATED]

## Positioning (kept apart from specs)
- Product page features: "Buttons for quick testing." "LEDs for motor output state." "Dual Input Mode: PWM/DIR or Potentiometer/Switch Input."

## Price band
- www.cytron.io volume prices: 5 or more $56.05; 10 or more $53.10; 30 or more $50.15 (read 16 Oct 2026); single-unit price [NOT STATED]

## Product page
https://www.cytron.io/p-25amp-7v-58v-high-voltage-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1xJHVG2dc3aEtedCHf3L9NzUy5KqpxeWjeS9Lfh9XuqA/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1xJHVG2dc3aEtedCHf3L9NzUy5KqpxeWjeS9Lfh9XuqA/edit

# Product fact sheets

## Product name
30Amp 5V-30V DC Motor Driver (MD30C)

## Aliases
MD30C, MD30C Rev2.0, Cytron MD30C, 30Amp 5V-30V DC Motor Driver, MD30C 30A DC Motor Driver

## What it is
A single-channel, bi-directional driver for one brushed DC motor, powered from 5–30 V and rated 30 A continuous and 80 A peak for up to 1 second. It takes PWM and DIR signals from a microcontroller or runs standalone from its onboard PWM generator with switches and a speed potentiometer.

## Specs and functions
- Product code: MD30C; hardware Revision 2.0 since January 2016
- Channels: 1 (bi-directional, brushed DC motor)
- Power input voltage (motor supply): 5 V min, 30 V max
- Maximum continuous motor current: 30 A
- Peak motor current: 80 A, must not exceed 1 second
- Idle current: 100 mA max
- Logic input high level: 3 V min, 5.5 V max
- Logic input low level: 0 V min, 0.5 V max
- Logic level input: 3.3V and 5V
- Maximum PWM frequency: 20 KHz; actual output frequency is same as input frequency when external PWM is selected
- PWM source selected by jumpers: internal potentiometer = JP4 INT POT + JP6 INT PWM; external potentiometer = JP4 EXT POT + JP6 INT PWM; external PWM signal = JP4 don't care + JP6 EXT PWM
- Truth table: PWM Low = both outputs low (brake, DIR don't care); PWM High + DIR Low = A high, B low (CW); PWM High + DIR High = A low, B high (CCW)
- Fully NMOS H-Bridge; manual states no heatsink or fan is required
- Reverse polarity protection
- 2 test buttons (A and B); external switches can be connected
- Red LED A, Red LED B (current direction), Green Power LED
- Packing list: 1 x MD30C; 2 x Mini Jumper; 1 x 2510 PCB Connector 3 Ways (Female); 3 x 2510 Terminal Pin
- Warranty: 6 months, manufacturing defects only
- CE, FCC and RoHS certificates linked on the product page
- Internal PWM generator frequency: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Over-current, thermal and under-voltage protection: [NOT STATED]

## Interfaces and compatibility
- Input header (2510, 3 pins): pin 1 GND, pin 2 PWM (not RC PWM), pin 3 DIR
- Power terminal block and motor terminal block; for current above 20A, solder wires directly to the pads at the bottom layer
- JP4 and JP6: PWM source selector jumpers
- JP5: external 10K Ohm potentiometer port
- JP7 and JP8: external switches
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example, `CytronMD motor(PWM_DIR, pwmPin, dirPin)`
- Getting started with SK40C in the user's manual
- Works with 3.3V and 5V logic controllers
- RC (Radio Control) PWM: not supported
- Analog voltage input / serial input: [NOT STATED]
- Wire size: [NOT STATED]

## Use cases
- Drive medium to high power DC brushed motor with current capacity up to 80A peak and 30A continuously
- Operate without a host controller using the onboard switches and speed potentiometer
- Mount external switches and potentiometer at an easy to reach place
- Control the motor from a microcontroller (example with SK40C)

## Known limitations
- Battery recommended as the power source
- If a switching power supply is used, parallel it with a same-voltage battery to absorb the re-gen power from the motor
- Connecting the battery to the motor port will burn the MOSFETs and is not covered under warranty
- Set either DIR or PWM pin LOW first when power is on
- Logic inputs 5.5 V max (not for 12 V or 24 V logic)
- Peak 80 A only for 1 second or less
- Not for RC (Radio Control) PWM
- For current above 20A, solder wires to the bottom-layer pads instead of using the terminal block
- JP6 must be EXT PWM for microcontroller control; with JP4 on EXT POT the onboard potentiometer has no effect
- PWM Low brakes the motor regardless of DIR
- Brushed DC motor only, one channel
- Motor direction depends on wiring

## Positioning (kept apart from specs)
- "the successor of MD30B"
- "user friendly features such as reverse polarity protection and onboard PWM generator which allows it to operate without a host controller"
- "Fully NMOS design not only provides faster switching time, it is also more efficient and no heatsink or fan is required."

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-30amp-5v-30v-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/178uDa3dmoG0ZX859rWUOS2Xyafkd8hSsSET5-ZLXMYQ/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/178uDa3dmoG0ZX859rWUOS2Xyafkd8hSsSET5-ZLXMYQ/view

# Product fact sheets

## Product name
SmartDriveDuo-10 (MDDS10)

## Aliases
MDDS10, SmartDriveDuo-10, SmartDriveDuo 10, Smart Drive Duo 10

## What it is
A dual-channel brushed DC motor driver that runs two motors from one 7–35 V supply. It takes RC receiver, analog, PWM or UART serial input, selected by DIP switch.

## Specs and functions
- Product code: MDDS10
- Motor channels: 2 (bi-directional, brushed DC)
- Input voltage (motor supply): 7 V to 35 V
- Maximum continuous motor current (IMAX): 10 A, depends on room temperature
- Peak motor current (IPEAK): 30 A, must not exceed 1 second
- Logic input high (VIOH): 1.3–5 V; logic input low (VIOL): 0–0.7 V
- 5V output current: 500 mA max ("Do not connect to another 5V source")
- Switching frequency: 16 KHz
- Input modes: RC, Analog, PWM, Simplified Serial, Packetized Serial, selected by DIP switch SW1–SW3 (SW1=0/SW2=0 RC; 0/1 Analog; 1/0 PWM; 1/1 with SW3=0 Simplified Serial; 1/1 with SW3=1 Packetized Serial)
- RC and Analog/PWM options: SW3:SW4 Mixed (00), Independent Right (01), Independent Left (10), Independent Both (11); SW5 exponential response on/off
- RC MCU mode (SW6=1): centre fixed at 1.5 ms, signal-loss timeout disabled; SW6=0: centre calibrated at power-up, motor stops after 100 ms without signal
- Analog/PWM (0–5 V): Locked Anti-Phase (SW6=0, stop at 2.5 V) or Signed Magnitude (SW6=1, 0 V stop, 5 V full speed, DIG1/DIG2 set direction); PWM input is low-pass filtered onboard
- Simplified Serial: 1 byte per command (bit 7 = LEFT/RIGHT); baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Packetized Serial: 4-byte packet (header 85 decimal / hex 55, address, command 0–255, checksum = header + address + command); address 0–7 by SW4–SW6, up to 8 drivers on one UART; auto-baud from the header byte, sent about 1 second after power-up
- Input header: DIG1 (LEFT direction; UART Rx in serial modes), DIG2 (RIGHT direction), AN1 (LEFT), AN2 (RIGHT), +5V, GND; RC header: RC1, RC2
- Terminals: Power Supply terminal block, Motor LEFT and Motor RIGHT terminal blocks (MLA/MLB, MRA/MRB); motor wires can also be soldered to the bottom pad
- Test buttons: 1 per motor, for fast test and manual operation
- LEDs: Run LED and direction LEDs per motor; Error LED (2 blinks input error, 3 under voltage, 4 over voltage, 5 over temperature, 6 shutdown)
- Thermal protection: duty cycle reduced in steps from 100% below 50 °C to 5% at 100–105 °C; shutdown above 105 °C; channel restarts below 70 °C
- Battery low voltage indicator and battery over voltage indicator
- Packing list: 1 × SmartDriveDuo-10, 6 × Terminal pin for 2510, 1 × 6-way Connector Housing
- Warranty: 12 months, manufacturing defects only
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Over-current protection: [NOT STATED]
- User's Manual: V1.0, June 2015

## Interfaces and compatibility
- Signal sources: RC receiver, potentiometer, joystick, foot pedal, PWM, microcontroller UART
- Logic input high range is 1.3–5 V; the manual does not explicitly state 3.3 V compatibility
- UART: receive only (DIG1 Rx); no TX pin described
- Cytron_SmartDriveDuo Arduino library (version 1.0.0, architectures=avr) for SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60
- Cytron tutorial: "Raspberry Pi: Control DC Motor using MDDS10"

## Use cases
- Differential drive mobile robot controlled by an RC receiver
- Motor control from a potentiometer, joystick or foot pedal
- Motor control from a microcontroller via PWM, Simplified Serial or Packetized Serial
- Up to 8 drivers sharing one microcontroller UART (Packetized Serial)

## Known limitations
- No polarity protection on the power input / V motor; double check connections before powering up
- Supply must stay within 7–35 V; above 35 V the driver will not operate
- A power supply that cannot sink current (bench-top or AC-DC switching supply) must have a battery of the same voltage connected in parallel to absorb regenerative current, or the driver may be permanently destroyed
- 10 A continuous depends on room temperature; 30 A peak must not exceed 1 second
- Output is derated from 50 °C and shuts down above 105 °C
- Under voltage is a warning only; LiPo below 3.0 V per cell must be replaced/recharged
- Input must be at stop at power-up (RC, Analog, PWM) or the driver shows Input Error
- The RC transmitter must be ON before powering up the driver
- Packetized Serial: wait about 1 second after power-up before sending the header; baud rate cannot change without power cycle or reset
- In Mixed mode the left and right motors must be wired to the matching terminal blocks
- +5V output must not be connected to another 5V source; 500 mA max
- Maximum PWM input frequency: [NOT STATED]
- Heatsink, wire size and fuse requirements: [NOT STATED]

## Positioning (kept apart from specs)
- Manual: "16 KHz switching frequency for quiet operation"
- Manual: designed mainly for differential drive robots controlled by an RC receiver

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-165/pdf/mdds10_users_manual.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-165/pdf/mdds10_users_manual.pdf

# Product fact sheets

## Product name
SmartDriveDuo-30 (MDDS30)

## Aliases
MDDS30, SmartDriveDuo-30, SmartDriveDuo 30, Smart Drive Duo 30

## What it is
A dual-channel brushed DC motor driver that runs two motors from one 7–35 V supply. It takes RC receiver, analog, PWM or UART serial input, selected by DIP switch.

## Specs and functions
- Product code: MDDS30
- Motor channels: 2 (bi-directional, brushed DC)
- Input voltage (motor supply): 7 V to 35 V
- Maximum continuous motor current (IMAX): 30 A each channel, depends on room temperature
- Peak motor current (IPEAK): 80 A each channel, must not exceed 1 second
- Logic input high (VIOH): 1.3–5 V; logic input low (VIOL): 0–0.7 V
- Input dead-band (RC, Analog and PWM mode only): ±10%
- Switching frequency: 18 KHz
- Input modes: RC, Analog, PWM, Serial Simplified, Serial Packetized, selected by DIP switch SW1–SW3 (SW1:SW2 00 RC; 01 Analog; 10 PWM; 11 with SW3=0 Serial Simplified; 11 with SW3=1 Serial Packetized)
- RC and Analog/PWM options: SW3:SW4 Mixed (00), Independent Right (01), Independent Left (10), Independent Both (11); SW5 exponential response on/off
- RC SW6: MCU mode on Rev1.00 boards; Full Range mode on Rev1.10 boards (released Jan 2019, firmware update, revision sticker on board)
- Analog/PWM SW6: Locked Anti-Phase (stop at 2.5 V / 50% duty) or Signed Magnitude (stop at 0 V / 0% duty; IN1/IN2 set direction); PWM accepts TTL PWM 1.3–5 V HIGH and is low-pass filtered onboard
- Battery monitor SW7:SW8: 00 LiPo, 01 NiMH, 10 SLA, 11 Off
- Serial Simplified: 1 byte per command (bit 7 LEFT/RIGHT, bit 6 CW/CCW, bits 5–0 speed 0–63); baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Serial Packetized: 4-byte packet (header 0x55 / 85, channel and address, command 0–255, checksum = header + address + command); address 0–7 by SW4–SW6; up to 8 drivers on one UART Tx
- Serial Packetized auto-baud: send dummy byte 128 (0x80) once, one second after power-up; autobaud range 4800–115200 bps
- Control inputs: Grove connector AN1 (LEFT), AN2 (RIGHT); Grove connector IN1 (LEFT direction; UART receive in serial modes), IN2 (RIGHT direction); RC input RC1, RC2
- Terminals: Power Supply terminal block, Motor LEFT and Motor RIGHT terminal blocks (MLA/MLB, MRA/MRB); wires can also be soldered to the bottom pad
- Test buttons: 1 per motor, for fast test and manual operation
- Reset button: restarts the system to change mode without power cycling
- LEDs: RUN, ERR and OC per channel; motor direction LEDs; Power LED; Error LED blinks 2 input error, 3 under voltage, 4 over voltage, 5 over temperature
- Protections: thermal protection (max current 80 A below 50 °C, 50 A at 50–70 °C, 40 A at 70–100 °C, 30 A above 100 °C), current limit protection, over voltage (>35 V will not operate), battery low voltage warning
- Cooling fan connector (NC, +ve 5V, -ve): optional fan turns on automatically above 50 °C
- Packing list: 1 × SmartDriveDuo-30, 2 × Grove 4 Pin Buckled 20cm Cable, 2 × 2561 3 Ways Connector Extension Wire
- Optional fan kit (not included): DC5V Brushless Fan 40 x 40 x 20mm, 4 × PCB Stand 30mm, 4 × Bolt M3 x 25mm, 4 × M3 Nut
- Warranty: 12 months, manufacturing defects only
- 5V output current: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- User's Manual: Rev 1.2, September 2023

## Interfaces and compatibility
- Signal sources: RC transmitter/receiver, analog joystick, microcontroller (Analog, PWM, UART)
- Logic input high range is 1.3–5 V; the manual does not explicitly state 3.3 V compatibility
- UART: receive only (IN1); no TX pin described
- Grove connectors; manual sample wiring uses CT UNO or Arduino Uno with Base Shield V2
- Cytron_SmartDriveDuo Arduino library (version 1.0.0, architectures=avr) for SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60, with PWM, Serial Simplified and Serial Packetized examples written for MDDS30

## Use cases
- Differential drive mobile robot controlled by an RC controller
- Motor control from an analog joystick
- Motor control from a microcontroller via PWM, Serial Simplified or Serial Packetized
- Up to 8 drivers sharing one microcontroller UART Tx pin (Serial Packetized)

## Known limitations
- No polarity protection on V motor / power input; double check connections before powering up
- Supply must stay within 7–35 V; above 35 V the driver will not operate
- A power supply that cannot sink current (bench-top or AC-to-DC switching supply) must have a battery of the same voltage connected in parallel to absorb regenerated current, or the driver may be destroyed permanently
- Pushing the robot with no battery connected might burn the driver; this is misuse and not covered by warranty
- 30 A continuous depends on room temperature; 80 A peak must not exceed 1 second
- Maximum current is reduced from 50 °C (down to 30 A above 100 °C)
- Under voltage is a warning only; motor power is maintained; LiPo below 3.0 V per cell must be replaced/recharged
- Input must be at stop at power-up (RC, Analog, PWM) or the driver shows Input Error
- The RC transmitter must be ON before powering up the driver
- Do not use an external BEC/regulator for the RC receiver; if required, disconnect the middle (red) wire
- Input mode is read only at power-up; press RESET or power cycle after changing the DIP switch
- RC SW6 function differs between Rev1.00 (MCU mode) and Rev1.10 (Full Range mode) boards
- Serial Packetized auto-baud byte is 0x80, not the 0x55 used by MDDS10 and MDDS60
- Maximum PWM input frequency: [NOT STATED]
- Wire size: "use wire with proper thickness to support the expected current"; gauge and fuse rating [NOT STATED]

## Positioning (kept apart from specs)
- Manual: "MOSFETs are switched at 18 KHz to ensure quiet operation and no annoying whining sound"
- Manual: "SmartDriveDuo-30's feature makes driving a robot with differential drive a truly plug and play experience"
- Manual: one of the latest smart series motor drivers, designed to drive medium power brushed DC motors

## Price band
[NOT STATED]

## Product page
https://www.cytron.io/p-mdds30

## Datasheet
https://docs.google.com/document/d/1OstW8T0kRIopWSuMEOyG2h9KNhQ3O4yowwjnp40Z23o/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1OstW8T0kRIopWSuMEOyG2h9KNhQ3O4yowwjnp40Z23o/view

# Product fact sheets

## Product name
SmartDriveDuo-60 (MDDS60)

## Aliases
MDDS60, SmartDriveDuo-60, SmartDriveDuo 60, Smart Drive Duo 60

## What it is
A dual-channel brushed DC motor driver that runs two motors from one 10–45 V supply. It takes RC receiver, analog, PWM or UART serial input, selected by DIP switch.

## Specs and functions
- Product code: MDDS60
- Motor channels: 2 (bi-directional, brushed DC)
- Input voltage (motor supply): 10 V to 45 V
- Maximum continuous motor current (IMAX): 60 A each channel, depends on room temperature
- Peak motor current (IPEAK): 100 A each channel, must not exceed 1 second
- Logic input high (VIOH): 1.3–5 V; logic input low (VIOL): 0–0.7 V
- 5V output current: 500 mA max ("Do not connect to another 5V source")
- Switching frequency: 16 KHz
- Input modes: RC, Analog, PWM, Simplified Serial, Packetized Serial, selected by DIP switch SW1–SW3 (SW1:SW2 00 RC; 01 Analog; 10 PWM; 11 with SW3=0 Simplified Serial; 11 with SW3=1 Packetized Serial)
- RC and Analog/PWM options: SW3:SW4 Mixed (00), Independent Right (01), Independent Left (10), Independent Both (11); SW5 exponential response on/off
- RC MCU mode (SW6=1): centre fixed at 1.5 ms, signal-loss timeout disabled; SW6=0: centre calibrated at power-up, motor stops after 100 ms without signal
- Analog/PWM (0–5 V): Locked Anti-Phase (SW6=0, stop at 2.5 V) or Signed Magnitude (SW6=1, 0 V stop, 5 V full speed, DIG1/DIG2 set direction); PWM input is low-pass filtered onboard
- Simplified Serial: 1 byte per command (bit 7 = LEFT/RIGHT); baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Packetized Serial: 4-byte packet (header 85 decimal / hex 55, address, command 0–255, checksum = header + address + command); address 0–7 by SW4–SW6; up to 8 drivers on one UART Tx; auto-baud from the header byte, sent one second after power-up
- Input terminal block: DIG1 (LEFT direction; UART Rx in serial modes), DIG2 (RIGHT direction), AN1 (LEFT), AN2 (RIGHT), +5V, GND; RC input: RC1, RC2
- Terminals: Power Supply terminal block, Motor LEFT and Motor RIGHT terminal blocks; wires can also be soldered to the bottom pad
- Power Switch terminal block: switches the microcontroller and logic circuit; ON by default; cut/unsolder the bottom-layer link to use an external switch
- Test buttons: 1 per motor, for fast test and manual operation
- "RST" reset button to change input mode without power cycling
- LEDs: RUN_L, RUN_R, motor direction LEDs; Error LED (2 blinks input error, 3 under voltage, 4 over voltage, 5 over temperature, 6 shutdown)
- Cooling fan: runs once the driver is powered up
- Thermal protection: duty cycle reduced in steps from 100% below 50 °C to 5% at 100–105 °C; shutdown above 105 °C; channel restarts below 70 °C
- Battery low voltage indicator and battery over voltage indicator (above 45 V the driver will not operate)
- Packing list: 1 × SmartDriveDuo-60 with top and bottom cover, 2 × 2561 Servo Extension cable
- Hardware revision: Rev1.10 shipped since January 2019 (component change; performance and interface unchanged)
- Warranty: 12 months, manufacturing defects only
- Over-current protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- User's Manual: Rev 1.1, July 2019

## Interfaces and compatibility
- Signal sources: RC transmitter/receiver, joystick or foot pedal with potentiometer, Cytron Breakout board with Joystick soldered, microcontroller (PWM, UART)
- Logic input high range is 1.3–5 V; the manual does not explicitly state 3.3 V compatibility
- UART: receive only (DIG1 Rx); no TX pin described
- Cytron_SmartDriveDuo Arduino library (version 1.0.0, architectures=avr) for SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60

## Use cases
- Differential drive mobile robot controlled by an RC controller
- Motor control from a joystick or foot pedal with potentiometer
- Motor control from a microcontroller via PWM, Simplified Serial or Packetized Serial
- Up to 8 drivers sharing one microcontroller UART Tx pin (Packetized Serial)

## Known limitations
- No polarity protection on V motor / power input; double check connections before powering up
- Supply must stay within 10–45 V; above 45 V the driver will not operate
- A power supply that cannot sink current (bench-top or AC-to-DC switching supply) must have a battery of the same voltage connected in parallel to absorb regenerated current, or the driver may be destroyed permanently
- 60 A continuous depends on room temperature; 100 A peak must not exceed 1 second
- Output is derated from 50 °C and shuts down above 105 °C
- Under voltage is a warning only; motor power is maintained; LiPo below 3.0 V per cell must be replaced/recharged
- Input must be at stop at power-up (RC, Analog, PWM) or the driver shows Input Error
- The RC transmitter must be ON before powering up the driver
- Input mode is read only at power-up; press "RST" or power cycle after changing the DIP switch
- Packetized Serial: wait one second after power-up before sending the header; baud rate cannot change without power cycle or reset
- In Mixed mode the left and right motors must be wired to the matching terminal blocks
- +5V output must not be connected to another 5V source; 500 mA max
- Maximum PWM input frequency: [NOT STATED]
- Wire size: "use wire with proper thickness to support the expected current"; gauge and fuse rating [NOT STATED]

## Positioning (kept apart from specs)
- Manual: "MOSFETs are switched at 16 KHz to ensure quiet operation and no annoying whining sound"
- Manual: "SmartDriveDuo-60's feature makes driving a robot with differential drive a truly plug and play experience"
- Manual: one of the latest smart series motor drivers, designed to drive medium power brushed DC motors

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
https://docs.google.com/document/d/15ICHc5CqQL8oXdU-n3ZL0_o8Vm4wQCnWOHHEfrEDDaI/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/15ICHc5CqQL8oXdU-n3ZL0_o8Vm4wQCnWOHHEfrEDDaI/view

# Product fact sheets

## Product name
Enhanced SmartDrive40 (MDS40B) — 40Amp 10V-45V SmartDrive DC Motor Driver

## Aliases
MDS40B, Enhanced SmartDrive40, SmartDrive40, 40Amp 10V-45V SmartDrive DC Motor Driver

## What it is
A single-channel brushed DC motor driver for medium to high power motors, running from a 10–45 V supply. An onboard microcontroller provides RC, Analog, PWM, Simplified Serial and Packetized Serial input modes, selected with a DIP switch.

## Specs and functions
- Product code: MDS40B
- User's Manual: Rev 1.1, July 2023 (spec table titled "Absolute Maximum Rating of Enhanced SmartDrive40")
- Motor channels: 1 (one brushed DC motor per board; two boards for a differential-drive robot)
- Input Voltage (Motor Supply Voltage): 10–45 V
- Maximum continuous motor current: 40 A (depends on the room temperature)
- Peak motor current: 80 A, must not exceed 1 second
- Logic input high level (VIOH): 1.3–5 V; logic input low level (VIOL): 0–0.7 V
- Product page: "3.3 and 5V compatible input"
- 5V output current: 500 mA max (do not connect to another 5V source)
- MOSFETs switched at 16 KHz for quiet operation
- Input modes: RC, Analog, PWM, Simplified Serial, Packetized Serial; selected with an 8-position DIP switch, read at power-up (press RST or power cycle after changing)
- RC mode (SW1:SW2 = 00): Independent (input 1 only), Mixed Right, Mixed Left; SW5 exponential response; SW6 MCU Mode (off: centre calibrated at power-up, motor stops after 100 ms signal loss; on: centre fixed at 1.5 ms, no timeout, motor keeps previous speed)
- RC transmitter must be ON before powering up the driver
- Analog mode (SW1:SW2 = 01) and PWM mode (SW1:SW2 = 10): 0–5 V input range; PWM input is low-pass filtered to analog
- SW6 in Analog/PWM: Locked Anti-Phase (stop at 2.5 V) or Signed Magnitude (Input 1 speed 0 V stop to 5 V full, Input 2 digital direction)
- Stop signal (2.5 V, or 0 V in Signed Magnitude) must be present at power-up, otherwise Input Error
- Simplified Serial (SW1–SW3 = 110): Input 1 = UART Rx, Input 2 = Slave Select; one byte: 127 stop, 0 full reverse, 255 full forward; baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Packetized Serial (SW1–SW3 = 111): 4-byte packet — header 85, address 0–7 (SW4–SW6), command (127 stop, 0 full reverse, 255 full forward), checksum = header + address + command; auto-baud from the first header byte; up to 8 units on one UART Tx pin; allow one-second delay after power-up before sending the header
- Error LED: 2 blinks Input Error; 3 blinks Under Voltage; 4 blinks Over Voltage (MDS40B will not operate); 5 blinks Over Temperature
- Over-temperature current limit: below 50 °C 80 A; 50–70 °C 50 A; 70–100 °C 45 A; 100–110 °C 40 A; above 110 °C 35 A
- Under voltage (LiPo, below 3.0 V per cell): warning only, motor power is not cut
- Over voltage: above 45 V the driver will not operate
- Run LED, Error LED, Motor LED indicators (LED A on = current from output A to B)
- Two motor test buttons (A: current flows from output A to B; B: vice versa)
- Reset button (RST)
- Power Switch Terminal Block: switches the microcontroller and logic circuit; ON by default
- Fan connector for an optional 5V cooling fan (always on, no speed control)
- Dimensions (product page): 105 mm (W) x 106 mm (D) x 38 mm (H) driver board; 125 mm (W) x 107 mm (D) x 47 mm (H) with the base
- Packing list: 1 x Enhanced SmartDrive40 with top and bottom cover; 2 x 2561 Servo Extension cable
- Warranty: 12 months, manufacturing defects only
- Reverse polarity protection: none
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- PWM input maximum frequency: [NOT STATED]

## Interfaces and compatibility
- Power Supply Terminal block (screw terminal or solder to bottom-layer pad)
- Motor Terminal Block (screw terminal or solder to bottom-layer pad)
- Analog/PWM/Serial Input Terminal Block: GND, 5V (output), IN1, IN2
- RC Input Pin: RC1 forward/reverse, RC2 steering
- Fan connector (5V)
- Power Switch Terminal Block
- Recommended power sources: 9–18 cells NiMH or NiCd (up to 30 cells; low voltage warning only up to 18 cells); 3–6 cells LiPo or Li-Ion (up to 10 cells; warning only up to 6 cells); 10–45 V sealed lead acid; 10–45 V power supply in parallel with a battery of the same voltage
- Wire: use wire thick enough for the expected current; product page recommends Multicore Wire AWG14
- Arduino: CytronMotorDriver library, PWM_DIR example (MDS40B set to Sign-Magnitude PWM Input mode)
- 3.3 V PWM input supported (product page); input pins are pulled up, so NPN optocouplers can be used (product page)
- Joystick breakout board recommended for Analog Locked Anti-Phase mode
- Onboard current sensor: not accessible (product page)

## Use cases
- Medium to high power brushed DC motor
- Robot with differential drive (two units, Mixed Left and Mixed Right)
- Control from a standard hobby radio control transmitter and receiver, or a microcontroller generating the similar signal
- Motor controlled by a joystick or foot pedal with potentiometer
- Microcontroller control via PWM or UART serial

## Known limitations
- Drives one motor only; two motors need two boards
- No reverse polarity protection; double check the connection before powering up
- Peak 80 A must not exceed 1 second; continuous 40 A depends on room temperature
- Current limit drops with board temperature (down to 35 A above 110 °C)
- With a power supply that cannot sink current (bench top or AC to DC switching power supply), a battery with the same voltage must be connected in parallel to absorb regenerative current; otherwise the input voltage might rise and destroy the driver permanently or trip the supply's protection
- Above 45 V the driver will not operate
- Under-voltage is a warning only; motor power is not cut, the user must stop and replace the battery
- Battery low voltage warning works only up to 18 NiMH/NiCd cells or 6 LiPo/Li-Ion cells
- Input must be at stop at power-up in RC, Analog and PWM modes, otherwise Input Error
- RC transmitter must be on before powering the driver
- With MCU Mode on there is no signal-loss timeout; the motor keeps its previous speed
- DIP switch changes need a reset or power cycle
- Packetized Serial needs a one-second delay after power-up before the header byte; baud rate fixed until power cycle or reset
- Do not connect the 5V output to another 5V source; 5V output limited to 500 mA
- Manual's features list says "dual brushed DC motor", but the board drives a single motor (product page: Motor Channel 1)

## Positioning (kept apart from specs)
- Product page: improved from MDS40A based on user feedback ("Enhanced SmartDrive40")
- Product page enhancements: increased Vin range up to 45 VDC; responsive current limiting sensor and algorithm; high ampere screw terminals; additional terminal to deactivate the driver without a high power switch; switching regulator for 5V; option to add a fan; ready header for RC receiver; over voltage protection
- Product page lists "Regenerative Braking."
- User's Manual: makes driving a robot with differential drive "a truly plug and play experience"

## Price band
$62.50 ex tax (www.cytron.io, read 2026-10-16); 5 or more $57.50; 10 or more $50.00

## Product page
https://www.cytron.io/p-40amp-10v-45v-smartdrive-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1WtfqfUlUlLCjGR_q33lZQt5xLPtft4zG0jJk5PX1A8Y/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1WtfqfUlUlLCjGR_q33lZQt5xLPtft4zG0jJk5PX1A8Y/edit

# Product fact sheets

## Product name
160Amp 8V-28V SmartDrive DC Motor Driver (MDS160A, SmartDrive160)

## Aliases
MDS160A, SmartDrive160, SmartDrive 160, Cytron MDS160A, 160Amp 8V-28V SmartDrive DC Motor Driver

## What it is
A single-channel, bi-directional smart driver for one high-power brushed DC motor, 8–28 V input and 160 A continuous. An onboard microcontroller provides RC, Analog, PWM, Simplified Serial and Packetized Serial input modes, temperature-based current limiting and thermal protection.

## Specs and functions
- Product code: MDS160A (SmartDrive160)
- Channels: 1 (bi-directional, brushed DC motor)
- Input voltage (motor supply): 8 V min, 28 V max
- Maximum continuous motor current: 160 A (depends on the room temperature)
- Peak motor current: 190 A (1 minute); 175 A (2 minutes); 160 A continuously (depends on the room temperature)
- Logic input high level: 3 V min, 5.5 V max; low level: 0 V min, 0 V typical, 0.5 V max (not applicable for PWM signal, which is low-pass filtered to analog)
- Analog input range: 0 – 5V
- 5V output current: 1 A max
- Switching frequency: 16 KHz
- Input modes, selected by 8-way DIP switch and read at power-up: RC, Analog, PWM, Simplified Serial, Packetized Serial
- RC mode: single or left/right mix; exponential option; MCU mode (centre fixed at 1.5 ms, timeout disabled); otherwise 100 ms signal-loss timeout stops the motor
- Analog/PWM mode: 2.5V = stop (centre mode) or sign-magnitude (Input 1 speed 0V stop to 5V full, Input 2 direction); single or left/right mix; exponential option
- Simplified Serial baud rates: 1200, 2400, 4800, 9600, 19200, 38400, 57600, 115200; one byte (127 stop, 0 full reverse, 255 full forward); Slave Select on Input 2
- Packetized Serial: auto-baud from header byte 85; 4-byte packet (header, address 0–15, command, checksum = header + address + command); up to 16 units on one UART
- Current limit by board temperature: below 60°C 194A; 60–70°C 175A; 70–80°C 163A; 80–90°C 144A; 90–100°C 125A; 100–110°C 100A; above 110°C 50A
- LiPo under voltage warning (below 3.3V per cell; warning only)
- Overvoltage protection, overcurrent protection (current limited each PWM cycle), over temperature protection
- Cooling fan; height 75mm including the cooling fan
- 2 test buttons (A, B)
- LEDs: A, B, OC (overcurrent), ERR (error blink codes), STAT (motor running), PWR
- On/Off switch terminal (shorted by solder bridge by default)
- Warranty: 12 months, manufacturing defects only
- Reverse polarity protection: [NOT STATED]
- Length and width: [NOT STATED]
- Operating temperature: [NOT STATED]

## Interfaces and compatibility
- Positive and negative supply terminals; Motor Terminal A and B
- Input header (4 pins): pin 1 IN2, pin 2 IN1, pin 3 +5V output, pin 4 Gnd
- Error LED blinks: 2 = Input Error, 3 = Lipo Undervoltage, 4 = Over Voltage, 5 = Over Temperature
- Works with hobby RC transmitter and receiver, potentiometer, joystick or foot pedal with potentiometer, or a microcontroller (PWM, RC-style pulse or UART)
- Two units can operate in mixed mode for a differential drive robot
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example; driver must be configured as Sign-Magnitude PWM Input mode (DIP 10010001)
- Recommended power sources: 7 – 18 cells NiMH or NiCd; 3 – 6 cells LiPo or Li-Ion; 12V – 24V sealed lead acid; 8V – 28V power supply in parallel with a battery of the same voltage
- 3D CAD files linked on the product page
- Wire size: [NOT STATED]
- Max PWM input frequency: [NOT STATED]

## Use cases
- Drive high power brushed DC motor with current capacity up to 160A continuously
- Drive a robot with differential drive using two units in mixed mode
- Control the motor with a standard hobby radio control transmitter and receiver
- Control the motor with a joystick or foot pedal with potentiometer
- Connect multiple units to a single microcontroller UART port
- Fast test and manual operation with the on board push buttons

## Known limitations
- A power supply that cannot sink current (bench top or AC to DC switching power supply) must be in parallel with a same-voltage battery; otherwise the input voltage might rise to a level where the driver will be destroyed permanently
- Input mode is read only at power-up; change the DIP switch then power cycle
- RC transmitter must be turned on before powering up the driver
- In Analog/PWM mode the stop signal must be present at power-on, else Input Error
- Packetized Serial: allow a one-second delay between applying power and sending the header byte
- +5V pin is an output up to 1A only; do not connect to another 5V source
- LiPo under voltage is a warning only; motor power is not cut
- Current limit drops with board temperature (50A above 110°C)
- Peak and continuous ratings depend on the room temperature
- If the board is off when power is supplied, the SWITCH terminal must be shorted
- Reverse polarity protection: [NOT STATED]

## Positioning (kept apart from specs)
- "one of the latest smart series motor drivers" (user's manual, Aug 2014)
- "MOSFETs are switched at 16 KHz to ensure quiet operation and no annoying whining sound"
- "This make driving a robot with differential drive a truly plug and play experience."

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-160amp-8v-28v-smartdrive-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1nkdj8CrZKoc4PHemBqlvpEJkQ2KjUHGqCTI8S5-mba4/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1nkdj8CrZKoc4PHemBqlvpEJkQ2KjUHGqCTI8S5-mba4/view

# Product fact sheets

## Product name
MDDRC5 5 Amp 7V-30V DC Motor Driver for R/C (2 Channels)

## Aliases
MDDRC5, 5 Amp 7V-30V DC Motor Driver for R/C (2 Channels), 5 Amp 7V-30V DC Motor Driver for R/C, 5 Amp Dual Channel RC Motor Driver

## What it is
A dual-channel DC motor driver controlled directly from an R/C receiver, driving two DC motors from a 7–30 V supply. Its RC1/RC2 inputs work in Independent Mode or Mixed Mode, selected with an onboard switch.

## Specs and functions
- Product code: MDDRC5
- Datasheet: Rev 1.0, March 2026 (spec table titled "MDDRC5 Absolute Maximum Ratings")
- Power input voltage: 7–30 V (V+ positive, V- negative; datasheet: "Connect to the battery")
- Maximum motor current (per channel): 5 A continuous
- Peak motor current (per channel): 20 A, "supported for less than 1 seconds and is limited by the overcurrent protection circuit" (datasheet); product page: 20 A peak "less than 5 seconds" — datasheet value applies
- Motor channels: 2
- Motor output PWM frequency: 20 kHz
- Control input: R/C signal on RC1 and RC2
- RC input voltage (RC1 & RC2): low level 0–0.7 V, high level 1.5–15 V
- RC signal timing: frequency 10–100 Hz, deadband ±35 µs, fullscale ±435 µs
- 5V output for the RC receiver: 500 mA max; do not use it to power a servo motor
- Mixed Mode: RC1 = forward/backward speed, RC2 = turn left/right (mixed to both motors)
- Independent Mode: RC1 = left motor speed and direction, RC2 = right motor speed and direction
- Mode selection switch (IND/MIX) selects Independent or Mixed Mode
- Motor alignment potentiometers (FWD, REV) compensate for left/right motor differences so the robot drives straight
- Test button: motors run at half speed; single press and hold = both motors forward, double press and hold = both motors backward
- Onboard microcontroller: RP2040
- USB-C port: firmware updates (datasheet); product page also states it can upload custom code
- Boot and Reset buttons: hold BOOT, press and release RESET, release BOOT; board appears as RPI-RP2 USB mass storage device
- Firmware: .uf2 files on GitHub (mddrc5_v1.0.4.uf2, mddrc5_v1.0.5.uf2, mddrc5_v1.0.6.uf2 present); copy the .uf2 file to the RPI-RP2 drive
- Product page: update to the latest firmware before use
- LEDs: Power LED; Motor status LEDs (MxA = Forward, MxB = Backward, direction depends on wiring); Error LEDs (ERR1 left motor, ERR2 right motor); OC (Overcurrent) LEDs on while current limiting is active
- Error LED codes: 2 blinks = RC Input Error (no RC signal or pulse width out of range); 3 blinks = Undervoltage / MOSFET Driver Error; 4 blinks = Overvoltage Error
- Overcurrent protection with active current limiting: PWM chopped, current held at the maximum limit; current limit threshold 20 A
- Undervoltage shutdown: motor output shuts down when input drops below the lower limit
- Reverse polarity protection on the power input
- Overvoltage: detected and reported as an error (4 blinks)
- Thermal shutdown: listed on the product page; not stated in the datasheet
- Footprint: 69 × 35.5 mm (product page)
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- Terminal type and wire size: [NOT STATED]
- Undervoltage / overvoltage thresholds: [NOT STATED]
- Failsafe motor behaviour on RC signal loss: [NOT STATED]
- Calibration procedure for the transmitter: [NOT STATED]
- Packing list: [NOT STATED]

## Interfaces and compatibility
- Power input terminal: V+, V-
- Motor output terminals: MxA, MxB per motor; swapping MxA and MxB reverses rotation
- RC input header: RC1, RC2 (signal), +5V (receiver supply, 500 mA max), GND
- USB-C (firmware update); USB-C powers the control circuit only, not the motors
- RP2040 pin mapping: RC1 = GP1, RC2 = GP0, TEST = GP3, IND/MIX = GP24, ERR1 = GP7, ERR2 = GP9, battery voltage sensor = GP29, FWD pot = GP26, REV pot = GP27
- Left motor: PWM GP11, Direction GP10, Sleep GP12, Fault GP13; Right motor: PWM GP20, Direction GP21, Sleep GP18, Fault GP17
- Works with an R/C receiver; no Arduino coding needed for normal R/C use (product page)
- 3D files on GitHub: Robot Sumo 500g R/C body and motor bracket; Robot Battle Karnival STEM files
- Tutorials: Getting Started with MDDRC5; Build a Robot Sumo 500g R/C with MDDRC5
- Arduino / MicroPython libraries or code examples: [NOT STATED]

## Use cases
- Differential drive motors in mobile robots (Mixed Mode preferred)
- Non-wheeled motors, or controlling the motors independently (Independent Mode)
- 500g R/C sumo robots
- Compact competition robots
- Compact mobile platforms
- Space-limited robotics projects

## Known limitations
- Power input absolute maximum 30 V (minimum 7 V)
- Motor current 5 A continuous per channel; 20 A peak only for less than 1 second, limited by the overcurrent protection circuit
- 5V output limited to 500 mA; do not use it to power a servo motor
- RC signal must be 10–100 Hz; missing signal or out-of-range pulse width gives an RC Input Error
- Motor output shuts down on undervoltage
- Overvoltage gives an error; with a switching power supply, connect a motor shunt regulator or a rechargeable battery with the same voltage in parallel to absorb regenerative energy from the motor during deceleration
- Motor direction depends on terminal wiring; the Forward/Backward LED labels follow the terminals
- Test button runs motors at half speed only
- USB-C does not power the motors
- Thermal shutdown is not described in the datasheet (product page only)
- No R/C failsafe behaviour or calibration procedure stated
- GitHub READMEs disagree on the latest firmware version (root README: v1.0.5; firmware README: v1.0.6); no release notes published

## Positioning (kept apart from specs)
- Product page framing: "5 Amp Dual Channel RC Motor Driver (MDDRC5)"
- Positioned as a smaller alternative inspired by MDDRC10 for direct R/C motor control in compact robots
- Compact footprint for space-limited competition robots

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-5-amp-7v-30v-dc-motor-driver-for-r-c-2-channels

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
MDDRC10 10Amp 7V-30V DC Motor Driver for R/C (2 Channels)

## Aliases
MDDRC10, 10Amp 7V-30V DC Motor Driver for R/C (2 Channels), 10Amp 7V-30V DC Motor Driver for R/C

## What it is
A dual-channel brushed DC motor driver controlled directly from an R/C receiver, driving two DC motors from a 7–30 V supply. Its RC1/RC2 inputs work in Independent Mode or Mixed Mode, selected with an onboard switch.

## Specs and functions
- Product code: MDDRC10
- Datasheet: Rev 1.0, August 2020 (spec table titled "MDDRC10 Absolute Maximum Ratings")
- Power input voltage: 7–30 V (VB+ positive, VB- negative; datasheet: "Connect to battery.")
- Maximum motor current (per channel): 10 A continuous
- Peak motor current (per channel): 30 A, limited by the overcurrent protection circuit; actual current limit depends on board temperature; value shown is at room temperature (25–30 °C); peak duration [NOT STATED]
- Motor channels: 2 (bidirectional control for two brushed DC motors)
- Motor output PWM frequency: 20 KHz
- Control input: R/C signal on RC1 and RC2
- RC input voltage (RC1 & RC2): low level 0–0.7 V, high level 1.5–15 V
- RC signal timing: frequency 10–100 Hz, deadband ±35 µs, fullscale ±435 µs
- 5V output for the RC receiver: 500 mA max, from an onboard switching regulator; do not use it to power a servo motor
- RC input auto-calibration: neutral points and offsets calibrated automatically at every power-up (captures the first valid RC signal as neutral)
- Mixed Mode: RC1 = forward/backward speed, RC2 = turn left/right
- Independent Mode: RC1 = left motor speed and direction, RC2 = right motor speed and direction
- Mode selection switch selects Independent or Mixed Mode
- Test buttons: motor runs at full speed
- LEDs: Power LED; Motor status LEDs (MxA = Forward, MxB = Backward, actual direction depends on motor connection); Error LED; OC (Overcurrent) LED on while current limiting is active
- Error LED codes: 2 blinks = RC Input Error (no RC signal or pulse width out of range); 3 blinks = Undervoltage / MOSFET Driver Error; 4 blinks = Overvoltage Error
- Overcurrent protection with active current limiting: PWM chopped, current held at the maximum limit
- Temperature protection: the higher the board temperature, the lower the current limiting threshold
- Undervoltage shutdown: output shuts down when input drops below the lower limit
- Reverse polarity protection: none (reverse polarity damages the driver instantaneously)
- 10 A per channel continuously without any additional heatsink (product page)
- Packing list (product page): 1 x 10Amp 7V-30V DC Motor Driver for R/C (2 Channels), 2 x 2561 3-way connector extension wire, 4 x PCB Spacer
- Warranty: 12 months
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- Terminal type and wire size: [NOT STATED]
- Undervoltage / overvoltage thresholds: [NOT STATED]
- Failsafe motor behaviour on RC signal loss: [NOT STATED]

## Interfaces and compatibility
- Power input terminal: VB+, VB-
- Motor output terminals: MxA, MxB per motor; swapping MxA and MxB reverses rotation
- RC input header: RC1, RC2 (signal), +5V (receiver supply, 500 mA max), GND
- Works with an R/C receiver; no coding or programming needed
- Microcontroller, USB, firmware or software library: [NOT STATED]
- Differences from MDDRC5 (per each datasheet): MDDRC10 is 10 A continuous / 30 A peak per channel vs MDDRC5 5 A / 20 A; MDDRC10 has no reverse polarity protection (MDDRC5 has); MDDRC10 lists temperature protection and RC auto-calibration; MDDRC10 test buttons run at full speed (MDDRC5 half speed); MDDRC10 has no RP2040, USB-C or alignment potentiometers described

## Use cases
- Differential drive motors in mobile robots (Mixed Mode preferred)
- Non-wheeled motors, or controlling the motors independently (Independent Mode)
- RC vehicle or mobile robot without any microcontroller
- RC Lawn Mower
- Combat Robot
- Sumo Robot
- RC Toy

## Known limitations
- Power input 7–30 V absolute maximum
- No reverse polarity protection; connecting the battery in reverse polarity damages the motor driver instantaneously
- Motor current 10 A continuous per channel; 30 A peak is current-limited and falls as the board temperature rises (30 A at 25–30 °C)
- 5V output limited to 500 mA; do not use it to power a servo motor
- RC transmitter must be on with sticks at neutral before switching on the driver, because neutral is captured at power-up
- RC signal must be 10–100 Hz; missing signal or out-of-range pulse width gives an RC Input Error
- Motor output shuts down on undervoltage
- Overvoltage gives an error; with a switching power supply, connect a motor shunt regulator or a rechargeable battery with the same voltage in parallel to absorb regenerative energy from the motor during deceleration
- Test buttons run the motor at full speed
- Motor direction depends on terminal wiring; the Forward/Backward LED labels follow the terminals
- No failsafe behaviour or peak current duration stated

## Positioning (kept apart from specs)
- Product page: "Building a RC vehicle or mobile robot without any microcontroller? MDDRC10 is what you need."
- "Plug & play, controlled from RC directly."

## Price band
$39.00 ex tax (www.cytron.io, read 2026-10-16; shown Out of Stock); 5 or more $37.05; 20 or more $35.10; 50 or more $31.20

## Product page
https://www.cytron.io/p-10amp-7v-30v-dc-motor-driver-for-rc-2-channels

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf

# Product fact sheets

## Product name
iMD16 (16 Amp 7-30V Industrial DC motor Driver)

## Aliases
IMD16, 16Amp 7-30V Industrial DC Motor Driver, 16 Amp 7-30V Industrial DC Motor Driver, iMD16 Industrial Motor Driver

## What it is
A single-channel, bidirectional brushed DC motor driver in a metal enclosure, rated 7–30 V DC input, 16 A continuous and 30 A peak (less than 10 seconds). It is controlled either by an external PWM/DIR signal or standalone with the included potentiometer and 3-way rocker switch.

## Specs and functions
- Product code: IMD16; launched 25 June 2026
- Power Input Voltage: 7 V min, 30 V max (POWER + / − screw terminal)
- Maximum Motor Current – Continuous: 16 A
- Maximum Motor Current – Peak (Less than 10 seconds): 30 A
- Logic Input Voltage – Low Level (PWM, DIR): 0 V to 0.5 V
- Logic Input Voltage – High Level (PWM, DIR): 3 V to 30 V
- Internal PWM Generator Frequency (output frequency when the potentiometer is used): 9 kHz to 11 kHz
- External PWM Input Frequency (Output Frequency = Input Frequency): DC to 20 kHz
- 1 motor output (MA, MB), bidirectional
- PWM/DIR truth table: PWM Low, DIR don't care → MA Low, MB Low → Brake; PWM High, DIR Low → MA High, MB Low → Forward; PWM High, DIR High → MA Low, MB High → Reverse
- Two control modes: PWM/DIR input (external microcontroller) and POT/SWITCH input (standalone, potentiometer for speed, 3-way switch for stop/forward/reverse, no microcontroller needed)
- Power LED (lights when supply voltage is present) and Motor Status LEDs (MA, MB; indicate motor operating conditions)
- No current limiting function
- Metal enclosure that also works as a passive heatsink; fanless
- Dimensions (datasheet Figure 4, mm): 102.00 overall length, 52.20 width, 73.99 enclosure body length, 5.00 flange thickness, 16.60 height dimension above the flange
- Mounting: two M4 slotted holes, slot centres 93.00 mm apart
- Packing box 72 × 118 × 46 mm; 157 g fully packed
- Certifications: CE (EMC EN 55032, EN IEC 61000-3-2, EN 61000-3-3, EN 55035; safety EN IEC 62368-1), UKCA, FCC Part 15 Subpart B Supplier's Declaration of Conformity, RoHS (CE and UKCA)
- Thermal, reverse polarity, under-voltage protection: [NOT STATED]
- Isolation: [NOT STATED]
- IP rating: [NOT STATED]
- Operating temperature: [NOT STATED]
- Unit weight: [NOT STATED]

## Interfaces and compatibility
- Power Input Terminal: 2-way screw terminal, POWER + / −, 7–30 V DC
- Motor Output Terminal: 2-way screw terminal, MOTOR MA / MB
- Speed Control Potentiometer: 3-pin JST PH connector (SPEED POT(10K): P3, P2, P1) for a 10 kΩ potentiometer
- Direction Switch: 3-pin JST PH connector (DIR SWITCH: MB, COM, MA) for a 3-way rocker switch (Forward, Stop, Reverse)
- PWM/DIR Input: 3-pin JST PH connector (DIR, PWM, GND); the controller's GND connects to GND
- Works with PLCs, microcontrollers (Arduino or Raspberry Pi named) and industrial motion controllers; direct connection to 24V PLC outputs without additional level shifters
- In the box: 1 × iMD16; 1 × 10k Ohm Potentiometer with connector; 1 × 3-Way Rocker Switch with connector; 1 × JST PH2.0-3P with Wires – 20cm; 1 × Phillips Screwdriver; 1 × Quick Start Guide
- Resources: Getting Started Guide for iMD16, datasheet, 3D CAD
- No firmware or configuration needed
- Arduino library support: [NOT STATED] (iMD16 is not in the CytronMotorDriver library's compatible-driver list)

## Use cases
- Conveyor systems
- Automated feeders
- Small industrial machines
- AGV / robotics subsystems
- Pumps, rollers, fans, and lifters
- Test and measurement equipment
- Custom automation systems
- Agricultural equipment
- Conveyor and material handling systems
- Custom OEM machinery
- Standalone field-deployed equipment
- Doors, actuators, and reversible conveyors

## Known limitations
- No current limiting function: 16 A continuous and 30 A peak (< 10 seconds) are maximum supported operating currents, not an active current limit; operating above the rated current may cause the board to overheat and could damage it
- Peak 30 A only for less than 10 seconds
- Back-EMF during braking or direction changes can make a switching power supply (SMPS) rail overshoot, potentially damaging the driver or tripping the SMPS protection; use a battery where possible, or add large electrolytic bulk capacitors or external TVS/clamping diodes to the power rail if an SMPS must be used
- Power input limited to 7–30 V
- External PWM limited to DC–20 kHz
- Logic Low must be 0–0.5 V and High 3–30 V
- PWM Low brakes the motor (both outputs Low)
- Control signals use JST PH connectors; screw terminals are for power and motor only
- Single motor channel
- Thermal, reverse polarity and under-voltage protection are not stated

## Positioning (kept apart from specs)
- "Meet Cytron's first industrial motor driver, the iMD16"
- "Industrial Motor Driver. Ready to Install."
- "Deployment-Ready with Integrated Controls and Protective Enclosure"
- Created "to bridge the gap between development motor drivers and complex industrial motor controllers"
- Positioned for 12V and 24V systems ("covering both 12V and 24V systems")
- Target audience: system integrators, existing Cytron MD users, machine makers, industrial engineers / technicians

## Price band
[NOT STATED]

## Product page
https://cytron.io/p-16amp-7-30v-industrial-dc-motor-driver

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV PiControl CM4

## Aliases
IRIV PiControl CM4, IRIV-PICL, PiControl CM4, IRIV PiControl IR4.0 CM4 Industrial Controller

## What it is
An industrial controller built around the Raspberry Pi Compute Module 4 in a fanless, DIN-rail-mountable metal enclosure. It adds isolated digital inputs, digital outputs, analog inputs, RS485 and RS232, two Ethernet ports and M.2 NVMe / mini PCIe expansion, powered from 10–30 VDC. The datasheet also lists an optional 4G module setup (Micro SIM socket, 4G antenna mounting hole, 4G status LEDs).

## Specs and functions
- Primary source: IRIV PiControl Datasheet Rev 1.2, Nov 2025 (covers CM4 and CM5; CM4 values only here); secondary: User Manual Rev 1.3, Nov 2025
- Document code: IRIV-PICL (User Manual Rev 1.3, Nov 2025; not stated in the datasheet)
- Compute module: Raspberry Pi CM4
- CPU: Broadcom BCM2711 quad-core 64-bit Cortex-A72 (ARM v8) SoC @ 1.5GHz
- RAM: 1GB/2GB/4GB/8GB LPDDR4-3200
- Storage: 8GB/16GB/32GB eMMC, expandable via M.2 NVMe SSD
- Wireless (optional): 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- Power input: Terminal 1 10–30 VDC, surge protected up to 60V 20ms; or USB-C (3 Amp) 4.9–5.2 VDC
- Power-input fuse: 4 Amp, replaceable
- Power consumption: max 6.5 W (stress-ng --cpu 4 --cpu-method fft; USB load not included)
- 4x isolated digital input: VIL -50 to 0.8 V, VIH 3 to 50 V, turn-on minimum DC 3.0V 0.2mA, isolation 3750 Vrms, active high, wet contact only; DI0/DI1/DI2/DI3 = GPIO13/GPIO17/GPIO22/GPIO27
- 4x isolated digital output: solid state relay dry contact, DC or AC load, max 50 V 500 mA, isolation 1500 Vrms, active high; DO0/DO1/DO2/DO3 = GPIO23/GPIO24/GPIO25/GPIO26
- 4x isolated analog input: 0-5V / 0-10V / 0-20mA, common AGND; voltage mode 0–10 V, current mode 0–20 mA; input impedance 25 kΩ (voltage) / 250 Ω (current); isolation 3000 Vrms; ADS1115 ADC at I2C 0x48 (bus 1)
- Isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, /dev/ttyACM0, switchable 120Ω termination
- Isolated RS232: max 120 kbps, isolation 3000 Vrms, /dev/ttyACM1
- PCF85063A RTC (I2C 0x51, I2C0) with CR2032 coin-cell holder
- ATECC608B crypto authentication (I2C 0x60)
- SSD1306 0.96" OLED display (I2C 0x3C)
- User button on GPIO4 (can be programmed as safe-shutdown button); reset button (hard reset, also wakes the CM4 after shutdown)
- Active buzzer on GPIO19 (beeps when high); LED0 on GPIO20, LED1 on GPIO21
- Status LEDs: PWR, ACT, M.2 (NVMe activity), 4G PWR (4G module power), WWAN (4G WWAN activity) — the 4G PWR and WWAN LEDs are in the datasheet but not the user manual, whose drawing shows mPCIe PWR / STAT instead (to be confirmed by engineering)
- Optional 4G hardware (datasheet): Micro SIM socket for the 4G module, 4G antenna mounting hole — not shown in the user manual (to be confirmed by engineering)
- Operating temperature: -20 to 60 ℃
- Enclosure: metal, fanless, DIN rail mountable; 141.2mm x 83.5mm x 39.5mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- DIN bracket can be moved; four mounting options (no DIN socket, DIN positions 1 (default), 2 and 3)

## Interfaces and compatibility
- 1x full-size HDMI 2.0 (up to 4K@60Hz)
- 2x USB 2.0 host (480Mbps), 1000mA max for both ports together
- 1x USB-C: Boot mode (load OS image into eMMC) or Debug mode (CM4 UART console via USB-UART chip), set by an internal switch; can also power the unit
- 1x RJ45 Gigabit Ethernet (10/100/1000M) = eth0; 1x RJ45 10/100M Ethernet via USB Ethernet controller = eth1
- 1x M.2 Key-M socket: PCIe Gen 2 x1, NVMe SSD 2230 & 2242, bootable
- 1x mini PCIe socket for 4G/LoRa modules (optional): USB 2.0 and SPI only, no PCIe signal; power switched by GPIO6
- Terminal 1: VIN (10-30V), GND, RS485 A / B / 485G, RS232 TX / RX / 232G, DO0–DO3
- Terminal 2: DI0–DI3 (+/−), AN0–AN3 (AI0–AI3), AGND
- OS: Raspberry Pi OS; setup script `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash` (Raspberry Pi OS only), then reboot
- Setup script enables USB host (dtoverlay=dwc2,dr_mode=host), I2C0 + RTC, I2C1, external antenna (dtparam=ant2), and installs the OLED/status/shutdown background script
- ADC library: Adafruit_ADS1x15 (pip install Adafruit_ADS1x15)
- Raspberry Pi GPIO libraries and serial libraries (pySerial) work with the GPIO numbers and /dev/ttyACM0 / ttyACM1 (staff wiki)
- Node-RED: Cytron 13-part tutorial series "IRIV PiControl Hands-On Using Node-RED in Industry 4.0" (staff wiki)
- eMMC flashing with rpiboot (github.com/raspberrypi/usbboot) in USB-C Boot mode (staff wiki)

## Use cases
- Edge computing
- IoT gateways
- Industrial automation
- Robotics
- Data logging
- Energy management systems
- Machine monitoring
- Energy monitoring
- PLC / data integration (PLC / Modbus data into an app, dashboard or report)
- Remote monitoring / IIoT
- System integrator pathway
- Training (workshops, kits, Industry 4.0 capability building)
- Custom IRIV solution

## Known limitations
- Digital inputs accept wet contacts only (need an external source, min DC 3.0V 0.2mA, max DC 50V); a plain dry switch will not register
- Digital outputs are dry contacts, max 50V 500mA; they switch an external source and do not supply voltage
- AGND is isolated from system ground but common to all four analog input channels
- 0-20mA measurement needs the internal shunt DIP switch ON (enclosure must be opened)
- RS485 termination, analog mode and USB-C Boot/Debug selection are internal switches
- M.2 SATA SSDs are not supported (NVMe only, 2230/2242)
- Mini PCIe has no PCIe signal: only USB 2.0 and SPI
- USB host is disabled by default on CM4: USB 2.0 ports, eth1 and the RS485/RS232 chip need the setup script (or manual config) before they work
- Setup script is only available for Raspberry Pi OS
- RS485/RS232 appear as /dev/ttyACM0 and /dev/ttyACM1, not as CM4 GPIO UARTs
- USB 2.0 ports share 1000mA total
- Wireless is optional (depends on CM4 variant); WiFi or BT can be disabled only by solder-shorting a jumper
- GPIO4, 6, 13, 17, 19, 20, 21, 22, 23, 24, 25, 26, 27 are used by onboard functions
- Operating temperature -20 to 60 ℃
- The manual's 0-20mA code example stores a current in mA in a variable named `voltage`
- On Raspberry Pi OS Bookworm, a system-wide pip install is blocked; use a virtual environment

## Positioning (kept apart from specs)
- Manual tagline: "Simplifying Digital Making"
- Described as an "IR4.0 CM4 Industrial Controller" (user manual) / "IR4.0 CM4 / CM5 Industrial Controller" (datasheet) / Industry 4.0 controller
- Sibling product IRIV PiControl CM5 (IRIV-PICL5) exists; keep CM4 and CM5 specs apart

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-iriv-picontrol-cm4-industrial-controller

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV PiControl CM5

## Aliases
IRIV-PICL5, IRIV PiControl CM5, PiControl CM5, IRIV PiControl IR4.0 CM5 Industrial Controller, IR4.0 CM5 Industrial Controller

## What it is
An industrial controller built around the Raspberry Pi Compute Module 5 in a fanless, DIN-rail-mountable metal enclosure. It adds isolated digital inputs, digital outputs, analog inputs, RS485 and RS232, two Ethernet ports and M.2 NVMe / mini PCIe expansion, and runs from 10–30 VDC.

## Specs and functions
- Document code: IRIV-PICL5 (User Manual Rev 1.5, Jan 2026); datasheet: IRIV PiControl Datasheet Rev 1.2, Nov 2025 (covers CM4 and CM5)
- Compute module: Raspberry Pi CM5
- CPU: Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) SoC @ 2.4GHz
- RAM: 2GB/4GB/8GB/16GB LPDDR4-4267 (Datasheet Rev 1.2); 4GB/8GB/16GB (User Manual Rev 1.5)
- Storage: 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD (Datasheet Rev 1.2); 32GB/64GB eMMC (User Manual Rev 1.5)
- Variants listed in the User Manual: IRIV PiControl CM5 Wireless 4GB/32GB, Wireless 8GB/32GB, Wireless 8GB/64GB, Wireless 16GB/64GB
- Wireless (optional): 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- Power input: Terminal 1 10–30 VDC, surge protected up to 60V 20ms; or USB-C (3 Amp) 4.9–5.2 VDC
- Power-input fuse: 4 Amp, replaceable
- Power consumption: max 10.5 W (stress-ng --cpu 4 --cpu-method fft; USB load not included)
- 4x isolated digital input: VIL -50 to 0.8 V, VIH 3 to 50 V, turn-on minimum DC 3.0V 0.2mA, isolation 3750 Vrms, active high, wet contact only
- 4x isolated digital output: solid state relay dry contact, DC or AC load, max 50 V 500 mA, isolation 1500 Vrms, active high
- 4x isolated analog input: 0-5V / 0-10V / 0-20mA, common AGND; voltage mode 0–10 V, current mode 0–20 mA; input impedance 25 kΩ (voltage) / 250 Ω (current); isolation 3000 Vrms; ADS1115 ADC at I2C 0x48 (bus 1)
- Isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, /dev/ttyACM0, switchable 120Ω termination
- Isolated RS232: max 120 kbps, isolation 3000 Vrms, /dev/ttyACM1
- PCF85063A RTC (I2C 0x51, I2C0) with CR2032 coin-cell holder
- ATECC608B crypto authentication (I2C 0x60)
- SSD1306 0.96" OLED display (I2C 0x3C)
- User button on GPIO4 (can be programmed as safe-shutdown button); reset button (hard reset, also wakes the CM5 after shutting down)
- Active buzzer on GPIO19 (beeps when high); LED0 on GPIO20, LED1 on GPIO21
- Status LEDs: PWR, ACT, M.2 (NVMe SSD activity)
- Operating temperature: -20 to 60 ℃
- Enclosure: metal, fanless, DIN rail mountable; 141.2mm x 83.5mm x 39.5mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- DIN bracket can be moved; four mounting options (without DIN rail socket, DIN positions 1 (default), 2 and 3)
- DI and DO GPIO numbers: [NOT STATED]

## Interfaces and compatibility
- 1x full-size HDMI 2.0 (up to 4K@60Hz), Type-A
- 2x USB 2.0 host (480Mbps), 1000mA max for both ports together
- 1x USB-C: Boot mode (load OS image into eMMC) or Debug mode (CM5 UART console via USB-UART chip), set by an internal switch; can also power the unit
- 1x RJ45 Gigabit Ethernet (10/100/1000M) = eth0; 1x RJ45 10/100M Ethernet via USB ethernet controller = eth1
- 1x M.2 Key-M socket: PCIe Gen 2 x1, NVMe SSD 2230 & 2242, bootable; CM5 PCIe can be enabled as Gen 3 (not certified)
- 1x mini PCIe socket: USB 2.0 and SPI only, no PCIe; power switched by GPIO6. Datasheet says "for 4G/LoRa modules (optional)"; User Manual names no use
- Terminal 1: power supply input, isolated RS485 (A, B, GND), isolated RS232, isolated digital outputs
- Terminal 2: isolated digital inputs, isolated analog inputs (AGND)
- OS: Raspberry Pi OS; setup script `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash` (Raspberry Pi OS only), then reboot
- Setup script edits config.txt (USB host, I2C0 + RTC, I2C1, external antenna dtparam=ant2) and installs the OLED/status/safe-shutdown background script
- ADC library: Adafruit_ADS1x15 (pip install Adafruit_ADS1x15), ADS1115(address = 0x48, busnum = 1)
- Same I/O, terminals, enclosure, dimensions, power input and operating temperature as IRIV PiControl CM4; differs in compute module, CPU, RAM, eMMC, power consumption (10.5 W vs 6.5 W) and optional PCIe Gen 3 (not certified)

## Use cases
- Machine monitoring
- Energy monitoring
- PLC / data integration (PLC / Modbus data into an app, dashboard or report)
- Remote monitoring / IIoT
- System integrator pathway
- Training (workshops, kits, Industry 4.0 capability building)
- Custom IRIV solution

## Known limitations
- Digital inputs accept wet contacts only (need an external source, min DC 3.0V 0.2mA, max DC 50V)
- Digital outputs are dry contacts, max 50V 500mA; they switch an external source and do not supply voltage
- AGND is isolated from system ground but common to all four analog input channels
- 0-20mA measurement needs the internal shunt DIP switch ON
- RS485 termination, analog mode and USB-C Boot/Debug selection are internal switches
- M.2 SATA SSDs are not supported (NVMe only, 2230/2242); PCIe Gen 3 on CM5 is not certified
- Mini PCIe has no PCIe signal: only USB 2.0 and SPI
- Setup script is only available for Raspberry Pi OS
- RS485/RS232 appear as /dev/ttyACM0 and /dev/ttyACM1
- USB 2.0 ports share 1000mA total
- WiFi or BT can be disabled only by solder-shorting a jumper
- GPIO4, 6, 19, 20, 21 are used by onboard functions (DI/DO GPIOs also used; numbers not stated)
- Operating temperature -20 to 60 ℃
- The datasheet's 0-20mA code example stores a current in mA in a variable named `voltage`
- Datasheet layout pictures and layout text are of the CM4 version

## Positioning (kept apart from specs)
- Described as an "IR4.0 CM5 Industrial Controller"
- Sibling product IRIV PiControl CM4 (IRIV-PICL); keep CM4 and CM5 specs apart

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV IO Controller

## Aliases
IRIV-IOC, IRIV IOC, IRIV IO Controller, IRIV I/O Controller, IR4.0 Industrial I/O Controller

## What it is
An industrial I/O controller in a fanless metal DIN-rail enclosure, built on the Raspberry Pi RP2350A microcontroller. It is a standalone microcontroller device, not a Raspberry Pi computer or Compute Module, and it runs no Linux OS.

## Specs and functions
- Product code: IRIV-IOC
- Datasheet: Rev 1.0, July 2024
- Microcontroller: Raspberry Pi RP2350A, Dual Cortex-M33 @ 150MHz
- RAM: 520KB on chip SRAM
- Storage: 2MB flash memory
- Power input, Terminal 1: 10 – 30 VDC (surge protected up to 60V 20ms), protected by a 500mA PTC
- Power input, USB-C: 4.9 – 5.2 VDC
- Power consumption: max 0.7 W
- 11x isolated digital input (up to 50V), active high, in two groups: Group 1 DI0–DI4 (common S/S0..4), Group 2 DI5–DI10 (common S/S5..10)
- Digital input levels: VIL max ±0.8 V; VIH ±3 to ±50 V; max pulse frequency 5000 Hz (50% duty cycle); isolation 3750 Vrms
- Built-in isolated power source for dry contact inputs (no external supply needed)
- 4x isolated digital output: dry contact, solid state relay, DC or AC load, max 50 V, max 500 mA, isolation 1500 Vrms, active high, isolated from the system and from each other
- 2x 12-bit analog input, non-isolated (AGND shared with system GND): voltage mode 0 – 10.56 V (input impedance 32K Ω), current mode 0 – 42.58 mA (input impedance 248 Ω)
- Analog voltage scaling to MCU: MCU = AN × 5/16
- 1x isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, switchable 120 Ω termination resistor
- 1x RJ45 Ethernet via Wiznet W5500: 10BaseT/100BaseTX, auto negotiation (full/half duplex), hardwired TCP/IP (TCP, UDP, ICMP, IPv4, ARP, IGMP, PPPoE), 8 independent sockets, 32Kbytes Tx/Rx buffer memory, power down mode, Wake on LAN over UDP, SPI up to 80MHz
- PCF85063A Real Time Clock, I2C address 0x51, CR2032 coin cell keeps it running when powered off
- 1x reset button, 1x boot button (both pinhole), 1x programmable button
- 1x programmable LED; status LEDs for PWR, RS485, DOUT 0-3 and DIN 0-10
- 1x passive buzzer (variable frequency tone or melody)
- Pin mapping: DI0–DI10 = GP0–GP10; AN0/AN1 = GP26/GP27; DO0–DO3 = GP12–GP15; RS485 UART1 TX GP24 / RX GP25; W5500 SPI0 MOSI GP19, MISO GP20, SCK GP22, CSn GP21, INT GP18, RESET GP23; RTC I2C0 SDA GP16 / SCL GP17; user button GP28 (active low); user LED GP29; buzzer GP11 (GPIO/PWM)
- Operating temperature: -20 to 70 ℃
- Relative humidity: 10 – 80 % (non-condensing)
- Enclosure: metal, fanless design, DIN rail mountable
- Dimension: (L)140mm x (W)60mm x (H)36mm (metal enclosure only, excluding DIN socket & connectors); DIN bracket adds 8mm, terminals add 15.5mm

## Interfaces and compatibility
- Terminal 1 (pluggable): V-, V+ (10-30V), DGND, S/S0..4, DI0–DI4, RS485 A / B / G, AGND ×2, AN0, AN1
- Terminal 2 (pluggable): DGND, S/S5..10, DI5–DI10, DO0–DO3 (two contacts each)
- Bottom DIP switches: RS485 R-Term (120 Ω termination), AN-IN MODE (voltage/current, drawn with separate AN0 and AN1 switches)
- USB-C for programming, configuration and power
- Digital inputs accept dry contact, PNP and NPN sensors; PNP and NPN can be used at the same time on different groups
- Ethernet communication: OT (MODBUS TCP) and IT (MQTT/HTTP)
- RS485 for MODBUS RTU
- CircuitPython: official board build "IRIV IO Controller (RP2350)" on circuitpython.org, installed as a UF2 file
- Programming: hold BOOT while resetting to enter the bootloader, then drag and drop the UF2 file
- Cytron tutorial: Getting Started with IRIV IO Controller with CircuitPython
- No Compute Module, Raspberry Pi board or HAT is used; the RP2350A is on board
- No earth connection required

## Use cases
- Lightweight automation
- Industrial I/O expansion
- MODBUS RTU/TCP gateways
- Data acquisition and sensor monitoring
- Edge control systems
- Pulse counting from flow meters, energy meters and rotary encoders, with running totals in Modbus registers polled by a PLC, SCADA or dashboard
- IoT gateway to Blynk, ThingSpeak and MQTT
- Agricultural automation

## Known limitations
- Analog inputs are not isolated (AGND is shared with system GND)
- Analog full scale is 10.56 V (voltage mode) or 42.58 mA (current mode)
- Digital output max 50 V, 500 mA per channel; a flyback diode is recommended for inductive loads to reduce EMI
- Digital input max pulse frequency 5000 Hz (50% duty cycle)
- RS485 max 500 kbps; termination is only for the first and last device on the bus
- Terminal 1 power input is protected by a 500mA PTC that may open on surge or overcurrent; the unit must cool down before it powers up again
- Power input 10 – 30 VDC on Terminal 1, or 4.9 – 5.2 VDC on USB-C
- Operating temperature -20 to 70 ℃; humidity 10 – 80 % non-condensing
- Microcontroller device: does not run Linux, Raspberry Pi OS or Node-RED on the unit
- 2MB flash, 520KB SRAM
- RTC backup needs a CR2032 coin cell inserted by the user

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 Industrial I/O Controller"
- Cytron tagline on the datasheet: "Simplifying Digital Making"
- Staff wiki: "designed for lightweight automation solutions in Industry 4.0 applications"
- Cytron video framing: counts pulses reliably, with debouncing, and runs continuously without needing a PLC. Running totals sit in Modbus registers. You do not need a full PLC just to count pulses, and setup time and cost are lower

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/c-industrial-with-raspberry-pi/p-iriv-io-controller

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV IOC MQTT Gateway

## Aliases
IRIV-IOC-MQTT, IRIV IOC MQTT Gateway, IOC MQTT Gateway, IRIV IOC MQTT, IOC MQTT, IRIV IO Controller MQTT Gateway

## What it is
An IRIV IO Controller (Raspberry Pi RP2350A industrial I/O controller) that ships preloaded from the factory with Cytron's MQTT Gateway Firmware. It sends its I/O and Modbus RTU data to an MQTT broker over Ethernet, and it is configured from a web page without coding.

## Specs and functions
- Datasheet: Rev 1.0, June 2026
- Firmware: MQTT Ready Gateway, preloaded from the factory; uses standard MQTT (Port 1883)
- Factory reset: hold the user button for 10 seconds during boot until the buzzer beeps; configuration is wiped, licence is preserved
- USR LED network status: Slow Blink = Ethernet down; Solid On = Ethernet up, MQTT disabled; Single Pulse every 1.5s = Ethernet up, MQTT enabled but not reachable; Two Pulses every 3s = Ethernet up, MQTT connected
- Microcontroller: Raspberry Pi RP2350A, Dual Cortex-M33 @ 150MHz
- RAM: 520KB on-chip SRAM
- Storage: 2MB flash memory
- Power input, Terminal 1: 10 – 30 VDC (Surge Protected up to 60V 20ms), protected by a 500 mA PTC
- Power input, USB-C: 4.9 – 5.2 VDC
- Power consumption: max 0.7 W
- 11x isolated digital input (up to 50V), active high, in two groups: Group 1 DI0–DI4 (common S/S0..4), Group 2 DI5–DI10 (common S/S5..10)
- Digital input levels: VIL max ±0.8 V; VIH ±3 to ±50 V; maximum pulse frequency 5000 Hz (50% duty cycle); isolation 3750 Vrms
- 4x isolated digital output: dry contact, solid state relay, DC or AC load, max 50 V, max 500 mA, isolation 1500 Vrms
- 2x 12-bit analog input, non-isolated: voltage mode 0 – 10.56 V (input impedance 32K Ω), current mode 0 – 42.58 mA (input impedance 248 Ω)
- 1x isolated RS485: maximum baud rate 500 kbps, isolation 5000 Vrms, automatic direction control, switchable 120 Ω termination resistor
- 1x RJ45 Ethernet via Wiznet W5500: 10BaseT/100BaseTX, auto negotiation, hardwired TCP/IP (TCP, UDP, ICMP, IPv4, ARP, IGMP, PPPoE), 8 independent sockets, 32Kbytes Tx/Rx buffer memory
- PCF85063A Real Time Clock (I2C 0x51), not used by the MQTT Gateway firmware
- 1x reset button, 1x boot button (both pinhole), 1x user button
- 1x user LED (USR); status LEDs for PWR, RS485, DOUT 0-3 and DIN 0-10
- 1x passive buzzer
- Pin mapping: DI0–DI10 = GP0–GP10; AN0/AN1 = GP26/GP27; DO0–DO3 = GP12–GP15; RS485 UART1 TX GP24 / RX GP25; W5500 SPI0 MOSI GP19, MISO GP20, SCK GP22, CSn GP21, INT GP18, RESET GP23; RTC I2C0 SDA GP16 / SCL GP17; user button GP28; user LED GP29; buzzer GP11
- Operating temperature: -20 to 70 ℃
- Relative humidity: 10 – 80 % (non-condensing)
- Enclosure: metal, fanless design, DIN rail mountable
- Dimension: (L)140mm x (W)60mm x (H)36mm (metal enclosure only, excluding DIN socket & connectors); DIN bracket adds 8mm, terminals add 15.5mm

## Interfaces and compatibility
- Differences from the IRIV IO Controller: factory MQTT Gateway firmware that must not be overwritten; the user button does a factory reset; the USR LED shows network/MQTT status; the buzzer beeps on factory reset; the RTC is not used; USB-C is used for configuration
- Terminal 1 (pluggable): V-, V+ (10-30V), DGND, S/S0..4, DI0–DI4, RS485 A / B / G, AGND ×2, AN0, AN1
- Terminal 2 (pluggable): DGND, S/S5..10, DI5–DI10, DO0–DO3 (two contacts each)
- Bottom DIP switches: RS485 R-Term (120 Ω termination), AN-IN MODE (voltage/current)
- USB-C for configuration and power
- MQTT broker: standard MQTT on port 1883
- RS485 for Modbus RTU field devices
- Digital inputs accept dry contact, PNP and NPN sensors; PNP and NPN can be used at the same time on different groups
- No earth connection required
- 3D CAD: same as IRIV IOC

## Use cases
- Remote Asset & Utility Monitoring: tracking flow meters, pumps and environmental sensors across geographically distributed water or energy grids over cellular networks
- Factory Floor Digitalization: aggregating machine health parameters, production cycle counts and downtime alerts to feed predictive maintenance dashboards
- Smart Facilities & Building Automation: centralizing HVAC performance, energy sub-metering and safety alarms across a corporate or university campus into a unified cloud interface
- Sending field data to a server for processing and visualization out of the box, for software/IT users not familiar with hardware or firmware

## Known limitations
- Uses standard MQTT (Port 1883) with no TLS/SSL on the device; for cloud encryption, route the data through a local secure broker or edge gateway
- Preloaded MQTT Gateway firmware must not be erased or overwritten with other firmware; it is licence-locked to the CPU ID
- The RTC is not used by the MQTT Gateway firmware
- Analog inputs are not isolated (AGND is shared with system GND)
- Analog full scale is 10.56 V (voltage mode) or 42.58 mA (current mode)
- Digital output max 50 V, 500 mA per channel; a flyback diode is recommended for inductive loads
- Digital input max pulse frequency 5000 Hz (50% duty cycle)
- RS485 max 500 kbps; termination is only for the first and last device on the bus
- Terminal 1 power input is protected by a 500 mA PTC that may open on surge or overcurrent; the unit must cool down before it powers up again
- Power input 10 – 30 VDC on Terminal 1, or 4.9 – 5.2 VDC on USB-C
- Operating temperature -20 to 70 ℃; humidity 10 – 80 % non-condensing
- 2MB flash, 520KB SRAM
- RTC backup needs a CR2032 coin cell inserted by the user
- Not confirmed on sale; product page not confirmed

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 Industrial I/O Controller"

## Price band
[NOT STATED]

## Product page
[NOT STATED]

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV SmartHub CM5

## Aliases
IRIV-SH5, IRIV SmartHub CM5, SmartHub CM5

## What it is
An industrial controller in a fanless metal enclosure, built around the Raspberry Pi Compute Module 5. It adds HDMI, USB, Gigabit Ethernet, an M.2 NVMe socket and a USB-2.0-only mini PCIe socket, and runs from DC 10-30V.

## Specs and functions
- Product code: IRIV-SH5
- Datasheet subtitle: IR4.0 CM5 Industrial Controller
- CPU: Broadcom BCM2712, Quad-Core Cortex-A76 64-bit SoC @ 2.4GHz (Raspberry Pi Compute Module 5)
- RAM: 2GB/4GB/8GB/16GB
- Storage: 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD
- Wireless: 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE; one external antenna for WiFi and Bluetooth
- Power input: DC barrel jack 10-30 VDC (surge protected up to 60V 20ms), adapter rated more than 2A recommended; USB-C 4.9-5.2 VDC, 5V 5A adapter recommended
- Power input fuse: 4A, replaceable
- USB 3.0 total output current: max 2 A for both ports
- USB 2.0 total output current: max 1 A for both ports
- Operating temperature: -20 to 60 ℃
- RTC: CR2032 coin cell holder keeps the CM5 built-in RTC running when powered off
- User button: GPIO4, can be programmed as a safe shutdown button
- Power button: single press to turn on; double-press or long-press to turn off
- User LEDs: LED0 = GPIO20, LED1 = GPIO21
- Status LEDs: PWR (same as red LED on Pi 5), ACT (same as green LED on Pi 5), M.2 (NVMe SSD activity); panel also shows mPCIe PWR and mPCIe STAT
- Active piezo buzzer: GPIO19, beeps when output is high
- Mini PCIe power on/off: GPIO6; mini PCIe reset: pull GPIO5 low
- Boot/Run switch (inside enclosure): selects USB-C for OS flashing into eMMC (Boot) or normal use (Run)
- Wireless disable jumper (back of board, labels BT and WLAN): solder-short to disable WiFi or Bluetooth
- Enclosure: metal, fanless design
- Dimensions: 147mm x 94mm x 35.7mm (metal enclosure only, excluding antenna) per datasheet Features table; the datasheet dimension drawing shows 147.00 x 98.00 x 35.00
- Mounting: 4x M4 VESA mount 75x75mm; flange slots (M4 and M8) per datasheet drawing

## Interfaces and compatibility
- 2x full size HDMI 2.0 (HDMI0, HDMI1), Type-A, up to 4K@60Hz
- 2x USB 3.0 host, 5 Gbps, direct from CM5
- 2x USB 2.0 host, 480Mbps, through an onboard USB hub
- 1x USB-C (for boot and power)
- 1x RJ45 Gigabit Ethernet (10/100/1000M), eth0 in Raspberry Pi OS
- 1x M.2 Key-M socket: Gen 2 1-lane PCIe, NVMe SSD 2230 & 2242, bootable
- 1x mini PCIe socket: USB 2.0 only, no PCIe signal
- Compute module: Raspberry Pi CM5
- OS: Raspberry Pi OS; Cytron tutorial also lists Ubuntu as a Raspberry Pi Imager choice
- OS flashing: Boot switch + USB-C to a PC; Cytron tutorial uses rpiboot (if required) and Raspberry Pi Imager
- Optional 4G/LTE module in the mini PCIe socket (not included; regional compatibility varies) per Cytron tutorial
- Remote access per Cytron tutorials: SSH (iriv-smarthub.local or IP), VNC via raspi-config, SCP/SFTP/USB drive file transfer, UVC USB webcam

## Use cases
- IR4.0 industrial controller
- Edge computing
- Industrial automation and centralized control
- Remote monitoring
- Thin clients
- Digital systems
- Smart infrastructure
- Headless, field and rack-mounted deployments
- Moving scripts and software updates; retrieving logs
- Air-gapped or offline file transfer by USB drive
- Basic machine vision with a UVC USB webcam
- Inspection stations
- Offline video monitoring

## Known limitations
- Mini PCIe socket is USB 2.0 only; PCIe signal is not available, so PCIe-only cards will not work
- M.2 socket supports NVMe 2230 and 2242 only; M.2 SATA SSD is not supported
- USB-C input range is 4.9-5.2 VDC only
- DC input is 10-30 VDC
- USB current is shared: 2 A total across both USB 3.0 ports, 1 A total across both USB 2.0 ports
- The 6 W power figure excludes USB load and applies to the stated stress-ng CPU test only
- Operating temperature is -20 to 60 ℃
- Dimensions exclude the antenna; datasheet Features table and drawing disagree on width/height (94 vs 98 mm, 35.7 vs 35 mm)
- No field I/O (RS485, CAN, digital or analog I/O) and no 40-pin GPIO header are listed
- GPIO4, 5, 6, 19, 20, 21 are used by onboard functions
- Boot/Run switch and wireless disable jumper are inside the enclosure; disabling WiFi/BT needs soldering
- 4G/LTE module and CR2032 battery are not included (Cytron tutorial); a SIM card is needed only when an LTE module is installed
- DIN-rail mounting is not stated
- Datasheet text calls the PWR/ACT LEDs "CM4" LEDs; this is a typo, the module is CM5

## Positioning (kept apart from specs)
- Centralized point for data processing, device connectivity and intelligent control at the edge
- Alternative to traditional PCs for edge computing: compact, fanless metal enclosure with no moving parts, lower maintenance, lower power, simpler infrastructure
- Raspberry Pi CM5 compute with industrial power handling, cooling and a finished enclosure
- Datasheet tagline: "Simplifying Smart Technology"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-iriv-smarthub-cm5

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV EdgeAI CM5

## Aliases
IRIV-EDGEAI-CM5, IRIV EdgeAI CM5, IRIV Edge AI CM5, EdgeAI CM5

## What it is
An industrial controller built around the Raspberry Pi Compute Module 5 in a fanless, DIN-rail-mountable metal enclosure. It has a PCIe port for the Raspberry Pi AI HAT+, two MIPI CSI camera ports, NVMe and mPCIe expansion, dual Gigabit Ethernet, and a terminal with isolated RS485, isolated digital inputs/outputs and LED lighting drivers.

## Specs and functions
- Product code: IRIV-EDGEAI-CM5 (datasheet header)
- Compute module: Raspberry Pi CM5
- CPU: Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) SoC @ 2.4GHz
- RAM: 2GB/4GB/8GB/16GB LPDDR4-4267 (datasheet)
- Storage: 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD (datasheet)
- Configurations listed on the product page (via internal KB): 16GB RAM + 64GB eMMC + 26 TOPS; 8GB RAM + 32GB eMMC + 26 TOPS; 8GB RAM + 32GB eMMC + 13 TOPS
- AI acceleration: Raspberry Pi AI HAT+ on a dedicated PCIe port (similar to the PCIe port on Raspberry Pi 5)
- Wireless: 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- 1x full-size HDMI 2.0 (up to 4K@60Hz)
- 2x USB 3.0 host ports (sharing one USB 3.0 hub); 1x USB-C for boot and debug
- 2x 22-way MIPI ports for CSI camera (datasheet); product page describes "dual 4-lane MIPI CSI"
- 2x RJ45 Gigabit Ethernet (10/100/1000M): eth0 = CM5 native, eth1 = USB 3.0-to-Gigabit Ethernet controller
- 2x isolated bidirectional digital inputs: VIL 0–0.8 V, VIH 3–50 V, isolation 3750 Vrms, PNP or NPN sensors, common S/S pin
- 2x isolated bidirectional digital outputs: dry contact (solid state relay), DC or AC load up to 50 V 500 mA, isolation 1500 Vrms
- 2x LED lighting drivers: wet contact, output voltage = Vin, up to 2 A per channel, PWM capable, independent 2 A fuse per channel
- 1x isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, onboard 120 Ω termination, mapped to /dev/ttyACM0
- 1x M.2 Key-M socket: PCIe Gen 2 1-lane, NVMe SSD 2230 & 2242, bootable
- 1x mPCIe socket for 4G/LoRa modules (USB 2.0 only), Micro SIM socket
- Power input: terminal 10–30 VDC (surge protected up to 60 V 20 ms); USB-C 4.9–5.2 VDC (PD supply, up to 5V 5A)
- Power consumption: max 11 W running "stress-ng --cpu 4 --cpu-method fft", USB load not included
- ATECC608B secure authentication (I2C1, 0x60)
- SSD1315 0.96" OLED display (I2C1, 0x3C)
- 1x power button (single press on, double-press soft shutdown, long-press force shutdown); 1x programmable button on GPIO4
- 1x active buzzer on GPIO19 (active high); 2x programmable LEDs: LED0 GPIO20, LED1 GPIO21
- Status LEDs: PWR, ACT, M.2, 4G PWR, WWAN, LED0, LED1
- GPIO map: DI0 GPIO22, DI1 GPIO27, DO0 GPIO23, DO1 GPIO24, L0 GPIO12, L1 GPIO13, mPCIe reset GPIO5 (active low), mPCIe power GPIO6, USB-C debug UART0
- CR2032 holder keeps the CM5 RTC running when powered off
- 4 A replaceable system fuse (LED drivers excluded)
- Internal Boot/Run switch: Boot = load OS into eMMC via USB-C; Run = USB-C is the CM5 UART0 console
- Solder jumpers to disable WiFi (WL) or Bluetooth (BT)
- Operating temperature: -20 to 60 ℃
- Enclosure: metal, fanless, DIN rail mountable (bracket can move to the bottom)
- Dimension: 139mm x 88mm x 38mm (metal enclosure only, excl. antenna, DIN socket & connectors)

## Interfaces and compatibility
- Terminal (pluggable): VIN, GND, RS485 A/B/G, S/S, DI0, DI1, DO0, DO1, L0 +/−, L1 +/−
- Raspberry Pi AI HAT+ (PCIe port plus 40-pin header with only 5V, 3V3, GND, ID_SC, ID_SD connected)
- CSI cameras on MIPI0 / MIPI1
- NVMe M.2 SSD 2230/2242 (M.2 SATA not supported)
- 4G or LoRa mini-PCIe modules that use USB 2.0; Micro SIM for the 4G module; reserved 4G antenna mounting hole
- HDMI display, USB 3.0 devices, two Ethernet networks
- RS485 devices via /dev/ttyACM0; PNP or NPN sensors on the digital inputs
- DIN rail
- Raspberry Pi OS (staff wiki)
- Used as the controller in the IRIV EdgeAI Safety Box Kit (KIT-IRIV-EAI-PPE), a separate product

## Use cases
- Edge AI and vision applications
- Defect detection / quality control
- Sorting lines
- Machine-learning inference at the edge, without offloading to the cloud
- IIoT edge gateway connecting sensors, legacy machinery and cloud platforms
- Compact industrial server for Docker/containerized applications, OPC UA servers and local databases
- Industrial automation and digital control
- Smart surveillance
- Agriculture, energy and infrastructure monitoring
- Factory floor, mobile robotics and network-edge deployments

## Known limitations
- mPCIe socket has only USB 2.0 connected; no PCIe signal
- M.2 SATA SSD is not supported
- LED driver outputs (L0, L1) are not powered when running from USB-C (getting-started tutorial)
- LED driver output voltage equals Vin; it is not set separately
- Digital outputs are dry contacts: the load needs its own supply, max 50 V 500 mA
- The two digital inputs share one S/S common
- Inductive loads on the digital outputs: a flyback diode is recommended to reduce EMI
- RS485 max baud rate is 500 kbps; it appears as /dev/ttyACM0, not a GPIO UART
- The 4 A system fuse does not cover the LED drivers; the fuse can blow on surge or overcurrent
- The 11 W maximum excludes USB load
- Boot/Run switch and wireless-disable jumpers are inside the enclosure
- Only 5V, 3V3, GND, ID_SC and ID_SD of the AI HAT+ 40-pin header are connected
- 4G antenna position is a reserved mounting hole only
- Dimensions exclude antenna, DIN socket and connectors
- Operating temperature is -20 to 60 ℃

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 CM5 Edge AI Controller"
- Product-page name: "IRIV EdgeAI CM5 - IR4.0 Industrial AI Controller"
- Product-page framing: "IR4.0 Industrial-Grade, Low Power, High Performance AI Hub with CM5."
- For manufacturers, machine builders, developers and system integrators deploying Industry 4.0 systems
- Combines Raspberry Pi CM5 compute, AI acceleration, industrial I/O, modular connectivity, fanless metal enclosure and DIN-rail mounting
- Local edge processing to avoid depending on the cloud for AI inference and to reduce latency and bandwidth in IIoT deployments

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-iriv-edge-ai-cm5

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

# Product fact sheets

## Product name
IRIV EdgeAI Safety Box Kit

## Aliases
KIT-IRIV-EAI-PPE, IRIV EdgeAI Safety Box Kit, IRIV EdgeAI Safety Box, IRIV EdgeAI - Safety Box: PPE and Zone Monitoring, EdgeAI Safety Box, Safety Box Kit, IRIV SafeVision, IRIV SafeOps, IRIV EdgeAI Safety Vision, IRIV EdgeAI v2

## What it is
A packaged on-premise AI vision appliance: an IRIV EdgeAI CM5 controller with a Hailo-8 26 TOPS accelerator and 128GB NVMe SSD in an IP67 ABS enclosure with its own 24V power supply and fan. It connects to existing RTSP IP cameras to detect missing safety helmets / hi-vis vests and entry into restricted zones, logs events and triggers alarm outputs and digital alerts.

## Specs and functions
- Product code: KIT-IRIV-EAI-PPE
- Controller: 1x IRIV EdgeAI CM5 Wireless, 8GB RAM, 32GB eMMC, 26 TOPS AI
- Processor: Raspberry Pi Compute Module 5, Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) @ 2.4GHz
- Storage: 32GB eMMC + pre-installed 128GB NVMe 2242 B+M-Key MakerDisk SSD
- Camera stream capacity: up to 6 RTSP IP camera sub-streams, 640x360 @ 15–25 FPS, H.264/H.265
- PPE detection: safety helmet and hi-vis / safety vest, enabled per camera; only non-compliant PPE raises an alert
- Restricted zones: polygon or circle zones drawn on the live view; multiple zones per camera; detects people, vehicles and animals entering; zone entry tracked until clear
- Alerts: isolated digital outputs DO0/DO1 (stack lights, buzzers/sirens, door interlocks, relays), Telegram, Email, MQTT
- Event records: timestamp, camera, detection type, snapshot; optional event clips; filter by date range, camera, zone, detection type
- Dashboard: live camera streams with detection boxes, confidence scores and recent events; layouts Smart, Grid, Focus, Single; multi-user access control
- Analytics: compliance rates, PPE vs zone events, most active zone, top violation type, helmet-vs-vest split
- Reports: CSV and PDF export
- Software: pre-loaded web UI and pre-trained PPE and safety-zone models; on-board database; inference runs locally on the Hailo NPU, video is not uploaded to the cloud
- Digital inputs: 2x isolated (up to 50V)
- Wireless: 2.4/5.0 GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- Display: 1x full-size HDMI 2.0 (up to 4K@60Hz); SSD1315 0.96" OLED status display
- Kit power supply: industrial switching power supply 24V 36W, wide DC and AC input voltage
- Controller power input: DC 10–30V, surge-protected
- Cooling: 24V DC exhaust fan with 2x intake/exhaust dust filters
- Enclosure: IP67 ABS industrial enclosure, 250 × 350 × 160mm
- Controller dimensions: 139mm × 88mm × 38mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- Controller operating temperature: -20 to 60 ℃; kit operating temperature [NOT STATED]
- Setup steps: connect existing cameras; discover via ONVIF or add RTSP URL; draw restricted zones on the live frame; enable helmet and/or vest detection per camera; detection and event logging start
- Typical setup is stated as under 10 minutes per camera
- In the box: 1x IRIV EdgeAI CM5 Wireless 8GB RAM / 32GB eMMC / 26 TOPS AI; 1x NVMe 2242 B+M-Key MakerDisk SSD 128GB; 2x Gigabit Ethernet cables 0.5m; 1x industrial switching power supply 24V 36W; 1x UK plug power cord with 13A fuse, C13 (D-shape); 1x IEC fuse chassis male power plug with switch; 2x female-to-female RJ45 extension ports; 1x 24V DC fan; 2x intake/exhaust filters; 1x DIN-rail power-distribution terminal block 6P

## Interfaces and compatibility
- Cameras: IP cameras with RTSP streaming support (required); ONVIF for automatic discovery; manual add by RTSP URL
- Camera streams: H.264/H.265, 640x360 sub-stream
- Network: 2x RJ45 Gigabit Ethernet (10/100/1000M) on the controller; 2x female-to-female RJ45 extension ports on the enclosure for external network access
- Outputs: DO0 (GPIO23) and DO1 (GPIO24), dry contact; DO1 can be driven by zone presence
- Integrations: MQTT, Telegram, Email
- Controller ports: 2x USB 3.0, 1x USB-C (boot and debug), 2x MIPI CSI, 1x HDMI 2.0, 1x isolated RS485, 2x isolated DI
- Expansion: 1x M.2 Key-M (holds the 128GB NVMe SSD), 1x PCIe (Raspberry Pi AI HAT+), 1x mPCIe (USB 2.0 only)
- Mains: UK plug, 13A fuse, C13 cord into an IEC fused, switched inlet
- Not included: IP cameras, sirens / stack lights

## Use cases
- Manufacturing plants
- Warehouses
- Construction sites
- Production floors: PPE and restricted-zone monitoring
- Loading bays: forklift/loading-bay monitoring
- Forklift lanes: restricted-zone monitoring
- Oil & Gas: PPE and hazardous-zone monitoring
- Palm oil mills: machinery-area zone monitoring
- Utilities: restricted-area monitoring
- Water treatment: restricted-area monitoring
- EHS / safety operations for EHS officers and safety managers
- PPE compliance monitoring (helmet and vest detection)
- Restricted-zone monitoring (configurable zone-entry detection)
- Audit preparation: logs, snapshots, CSV/PDF reporting, analytics

## Known limitations
- Requires IP cameras with RTSP streaming support; ONVIF is for discovery only
- Up to 6 RTSP feeds, stated at 640x360 sub-streams, 15–25 FPS, H.264/H.265
- PPE detection is limited to safety helmets and safety vests
- Not a certified safety system; supports but does not replace certified safety controls, procedures or trained supervision
- Lighting and camera angle affect suitability
- IP cameras are not included in the packing list
- Digital outputs are dry contacts (max 50 V, 500 mA); the alarm device needs its own supply
- mPCIe expansion uses USB 2.0, not PCIe
- Kit operating temperature, detection distance and accuracy: [NOT STATED]

## Positioning (kept apart from specs)
- Product page name: "IRIV EdgeAI - Safety Box: PPE and Zone Monitoring"; landing-page headline: "AI Vision for Workplace Safety."
- Retrofit layer that turns existing CCTV into an AI safety-monitoring system without replacing cameras; framed around Detection, Response and Record
- Local/on-premise processing positioned as a privacy and latency advantage; video stays on-site
- Target users: EHS officers, safety managers, plant managers and site supervisors; runs alongside existing safety supervision
- Aligned with Malaysia's OSHMP30 framework

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-iriv-edgeai-safety-box-kit

## Datasheet
[NOT STATED]

## Source type
[NOT STATED]

## Source link
[NOT STATED]

# Product fact sheets

## Product name
Maker pHAT: Simplifying Raspberry Pi for Education

## Aliases
HAT-MAKER, Maker pHAT, Cytron Maker pHAT, Maker pHAT: Simplifying Raspberry Pi for Education

## What it is
A Raspberry Pi Zero-size pHAT that stacks on the Raspberry Pi 40-pin GPIO header and adds a USB Micro-B socket for 5V power and a USB-to-UART serial console, 8 GPIO indicator LEDs, 3 push buttons, an active buzzer and labelled breakout pins. It needs a Raspberry Pi (not included).

## Specs and functions
- Product code: HAT-MAKER
- User's manual: Rev 1.10, Feb 2019 (no separate datasheet)
- Form factor: Raspberry Pi Zero size, standard Raspberry Pi GPIO footprint
- 8 GPIO indicator LEDs on GPIO 17, 18, 27, 22, 25, 12, 13, 19; these GPIOs can be configured as output, input or input pull-up
- 3 programmable push buttons: SW1 GPIO 21, SW2 GPIO 16, SW3 GPIO 20; configure as input pull-up (the manual's feature list says "GPIO 21, 19 and 20"; its board layout, section 7.2 and demo code say 21, 16 and 20)
- Active buzzer on GPIO 26: HIGH = on, LOW = off
- USB Micro-B socket for 5V input and USB-to-UART communication, connected to the Raspberry Pi UART (TX GPIO 14, RX GPIO 15)
- USB-serial IC: FT231X (manual board layout); the manual's feature list says CH340
- USB-serial activity indicator LED
- Labelled breakouts: 5V, 3.3V, GND; I2C SDA GPIO 2, SCL GPIO 3; UART TX GPIO 14, RX GPIO 15; SPI MOSI GPIO 10, MISO GPIO 9, SCK GPIO 11, CE0 GPIO 8, CE1 GPIO 7; GPIO 17, 18, 27, 22, 25, 12, 13, 19
- Input voltage: USB 5V, from computer, power bank or standard USB adapter
- Absolute maximum input voltage via USB connector: 4.8 – 5.2 V
- DC current for 5V pin (max continuous): limited by USB (no figure given)
- Rev1.10 has pre-soldered SMD header pins on the breakout pads
- Purple PCB
- Warranty: 1 year (user's manual); 12 months (Cytron product page)
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Raspberry Pi 3B / 3B+ and Raspberry Pi Zero / W / WH
- Stacks directly on Raspberry Pi Zero WH
- Raspberry Pi 3 Model B / B+ need the 2x20 PC104 stacking header (included)
- Serial console: add enable_uart=1 to config.txt; terminal speed 115200 (PuTTY on Windows)
- USB-serial drivers linked in the manual for Windows 10 and macOS (CH341SER)
- Python 3 with the gpiozero library (LED, Button, Buzzer); demo code in the manual and on a Cytron gist
- In the box: 1x Maker pHAT (HAT-MAKER), 1x 2x20 Stacking Header (CN-PH-PC104)

## Use cases
- Getting started with Raspberry Pi without a monitor, keyboard or mouse (headless), using the serial console
- Remote access to the Raspberry Pi through serial, then setting up Wi-Fi and VNC
- Learning to interface with sensors and actuators and coding with the onboard LEDs, push buttons and buzzer
- Prototyping with labelled GPIO, SPI, UART and I2C breakouts
- Hardware shutdown with push buttons

## Known limitations
- Power input is USB 5V only (4.8 – 5.2 V absolute maximum)
- 5V pin current is limited by the USB source
- Push buttons need the GPIO set as input pull-up
- LEDs are only on GPIO 17, 18, 27, 22, 25, 12, 13, 19
- Do not unplug the USB cable without a proper shutdown; it might corrupt the microSD card
- The USB serial console uses the Pi UART on GPIO 14/15 and needs enable_uart=1
- Raspberry Pi 3 Model B / B+ need the stacking header to fit
- The printed demo code in the manual has an undefined variable (times) in the shutdown branch; the gist version uses range(3)
- The manual's setup steps are for Raspbian Stretch / NOOBS (2019)
- Raspberry Pi not included

## Positioning (kept apart from specs)
- "Maker pHAT is designed for anyone who want to get start with any Raspberry Pi projects"
- Designed to ease getting started with Raspberry Pi headless, and prototyping
- Addresses beginner pain points: no onboard USB-to-UART, no GPIO status indicator, unlabelled GPIO, no programmable push button for proper shutdown
- Product name tagline: "Simplifying Raspberry Pi for Education"
- "PURPLE PCB!"

## Price band
RM45.78 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-phat-simplifying-raspberry-pi-for-education

## Datasheet
https://docs.google.com/document/d/1iDYLyoQKOPJRD5m5ivu8Ivv6zyeLIc3IxUtRKOx7n8k/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1iDYLyoQKOPJRD5m5ivu8Ivv6zyeLIc3IxUtRKOx7n8k/view

# Product fact sheets

## Product name
Maker Hat Base - HAT & GPIO Extension for Raspberry Pi 400

## Aliases
MAKER-HAT-BASE, Maker Hat Base, Cytron Maker Hat Base, Maker Hat Base - HAT & GPIO Extension for Raspberry Pi 400, HAT & GPIO Extension for Raspberry Pi 400

## What it is
A base board that connects to the Raspberry Pi 400 GPIO by a 40-way ribbon cable and extends it to a pin header for stacking a Raspberry Pi HAT, a labelled pin breakout, GPIO status LEDs, 3 Grove ports, 4 buttons and a buzzer. It has no processor of its own; every function is a Raspberry Pi GPIO.

## Specs and functions
- Product code: MAKER-HAT-BASE
- Datasheet: Rev 1.0, September 2021
- Pin header for stacking a Raspberry Pi HAT
- IDC socket for connecting to the Raspberry Pi via 40-way ribbon cable
- Raspberry Pi pins breakout for jumper cables
- GPIO status LEDs: turn on when the GPIO state is high
- 3 Grove ports: I2C (SCL GPIO3, SDA GPIO2), UART (RXD GPIO15, TXD GPIO14), GPIO (GPIO12, GPIO13)
- 4 programmable push buttons, active low, on GPIO17, 22, 23 and 27; enable the internal pull-up to use them
- Programmable fixed tone buzzer, resonant frequency 2700±300Hz, on GPIO26
- Mute switch for the buzzer, for when GPIO26 is used for other purposes
- 3.3V power LED and 5V power LED (on when powered up)
- 5V supply: supplied by Raspberry Pi
- 3.3V supply: 3.235 – 3.365 V, max 800 mA
- GPIO specification: refer to Raspberry Pi
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Designed for the Raspberry Pi 400 (datasheet)
- Cytron product page images also mention Raspberry Pi 3 and 4
- Connects to the Raspberry Pi through a 40-way ribbon cable to the IDC socket
- Accepts a stacked Raspberry Pi HAT on the pin header
- Grove I2C, UART and GPIO modules
- CAD file available (MAKER-HAT-BASE CAD.zip)

## Use cases
- Stacking a Raspberry Pi HAT on the Raspberry Pi 400
- Connecting components to the Raspberry Pi pins with jumper cables
- Connecting Grove modules over I2C, UART or GPIO
- Using the onboard buttons and buzzer as programmable inputs and output

## Known limitations
- 5V is supplied by the Raspberry Pi; the board has no separate power input
- 3.3V supply max 800 mA
- GPIO limits follow the Raspberry Pi
- Buttons are active low and need the internal pull-up enabled
- Buzzer is fixed tone (2700±300Hz) on GPIO26; mute it with the switch if GPIO26 is used for other purposes
- A stacked HAT shares the same GPIOs as the buttons, buzzer and Grove ports
- Out of stock on my.cytron.io (2026-10-16)
- Raspberry Pi not included

## Positioning (kept apart from specs)
- Datasheet subtitle: "HAT & GPIO Extension for Raspberry Pi 400"

## Price band
RM45.78 (Cytron product page, read 2026-10-16)

## Product page
https://my.cytron.io/p-maker-hat-base-hat-and-gpio-extension-for-raspberry-pi-400

## Datasheet
https://docs.google.com/document/d/12l4vzu-r3VRBCLkCsuM00KOYnMPnQw5HxdfxjA3p5E0/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/12l4vzu-r3VRBCLkCsuM00KOYnMPnQw5HxdfxjA3p5E0/edit

# Product fact sheets

## Product name
CM4 Maker Board: Maker's Carrier Board for Raspberry Pi CM4/CM5

## Aliases
MAKER-CM4, V-MAKER-CM4, CM4 Maker Board, Cytron CM4 Maker Board

## What it is
A carrier board for the Raspberry Pi Compute Module 4 (CM4 Lite or eMMC) with Raspberry Pi 4-style ports, M.2 NVMe, camera and display connectors, an RTC and maker parts (Grove ports, buttons, buzzer, GPIO LEDs). The datasheet covers CM4; the product page title also names CM5.

## Specs and functions
- Power input: USB-C 5V or DC power jack 7V - 18V (only one is needed)
- HDMI: 1x full size, up to 4K resolution (HDMI 0 of CM4)
- USB: 4x USB 2.0 Host
- Ethernet: 1Gbps Gigabit Ethernet
- M.2 Key-M connector for PCIe modules: NVMe SSD 2230 & 2242 (bootable)
- microSD card slot for Raspberry Pi CM4 Lite
- CSI camera port: 15-pin 2-lane MIPI CSI, CAM 1 of CM4, compatible with Raspberry Pi Camera Module
- DSI display port: 15-pin 2-lane MIPI DSI, DSI 1 of CM4
- PCF85063A RTC with CR2032 coin cell holder
- 10 GPIO LEDs (GPIO 2, 3, 5, 6, 12, 13, 14, 15, 23, 24), turn on when the IO state is high
- Passive piezo buzzer on GPIO 19 with buzzer mute switch
- Analog audio out (line level): Left GPIO 19, Right GPIO 18
- User programmable buttons: GPIO 17, 22, 27
- 2 power buttons in series (GLOBAL_EN & GPIO 4), both pressed together to turn the CM4 ON/OFF; external power button header in parallel (not soldered by default)
- Boot switch: RUN or BOOT (BOOT loads the OS image to the CM4 eMMC via USB-C)
- Status LEDs: M.2, ACT, PWR, 5V
- Dimensions: 110 mm × 110 mm; 4 mounting holes Ø 3.2 mm at 104 mm × 104 mm

## Interfaces and compatibility
- Compute Module: Raspberry Pi CM4 (Lite or with eMMC) per datasheet Rev 1.2; product page title says "for Raspberry Pi CM4/CM5"
- 40-pin GPIO breakout, pinout exactly the same as Raspberry Pi 4
- Grove ports: 2x GPIO (GPIO 5, 6 and GPIO 23, 24), 1x PWM (GPIO 12, 13), 1x UART (GPIO 14, 15), 1x I2C (GPIO 2, 3); each GND, 3V3, pin, pin
- Maker Port: I2C on GPIO 2, 3 (shared with the Grove I2C port), compatible with QWIIC / Stemma QT / Grove (with conversion cable)
- Storage: microSD (CM4 Lite), CM4 eMMC, M.2 NVMe 2230 / 2242
- Official Raspberry Pi Camera Module and 7-Inch Display (need the matching dt-blob.bin)
- Setup script and pre-configured bootloader for Raspberry Pi OS (CytronTechnologies/MAKER-CM4_Script)

## Use cases
- Maker's carrier board for Raspberry Pi CM4
- Connecting Grove, QWIIC and Stemma QT modules to a Compute Module
- Booting a CM4 from NVMe SSD, eMMC or microSD

## Known limitations
- M.2 SATA SSD is not supported
- microSD slot is not accessible by Raspberry Pi CM4 with eMMC
- USB host on CM4 is disabled by default; the setup script (Raspberry Pi OS only) enables it
- Power buttons cannot wake the CM4 after shutdown unless Cytron's pre-configured bootloader is flashed
- Piezo buzzer shares GPIO 19 with the analog audio out; use the mute switch when using audio
- The audio remap line must be commented out to use hardware PWM for the buzzer
- Maker Port shares GPIO 2, 3 with the Grove I2C port
- dt-blob.bin method is only for the official Raspberry Pi Camera Module and 7-Inch Display
- Make sure the CM4 orientation is correct in the socket
- ESD may disturb normal function; power cycle to recover
- No fan header, USB 3.0 or PoE listed in the datasheet
- CM5 support: named in the product page title only; not described in the datasheet
- Operating temperature and supply current rating: [NOT STATED]

## Positioning (kept apart from specs)
- Datasheet title: "CM4 Maker Board — Maker's Carrier Board for Raspberry Pi CM4"
- Product page title: "CM4 Maker Board: Maker's Carrier Board for Raspberry Pi CM4/CM5"
- Product page bundles: "CM4 Maker board ONLY" and "CM4 Maker Board + CM4NW216 + Accessories"
- Out of stock on my.cytron.io (2026-10-16)

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-cm4-maker-board-and-kits

## Datasheet
https://docs.google.com/document/d/1XmZSR81IN70pndZ2odBmlZgAufiIBawVdKZ71C7101Y/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1XmZSR81IN70pndZ2odBmlZgAufiIBawVdKZ71C7101Y/edit

# Product fact sheets

## Product name
Industrial IO HAT+

## Aliases
HAT-IND-AG, IR4.0 Industrial I/O HAT+, Industrial I/O HAT+, Industrial IO HAT+ for Raspberry Pi 5, IO HAT+

## What it is
An industrial I/O HAT+ for the Raspberry Pi 5 that adds RS485, RS232, isolated digital inputs and isolated digital outputs, and powers the Pi from a 10–30 VDC supply. It is a HAT, not a computer, and needs a Raspberry Pi 5 (not included).

## Specs and functions
- Datasheet: Rev 1.0, Sep 2025
- Host: Raspberry Pi 5
- Raspberry Pi HAT+ compliant, with EEPROM that lets Raspberry Pi OS recognise the HAT+ and tells the Pi 5 the HAT+ can supply 5A (needs bootloader version 2025-06-29 or greater)
- Power input: 10 – 30 VDC, surge protected up to 60V 20ms
- Maximum current for Raspberry Pi (5V): 5 A
- 4A replaceable fuse for the system
- 1x RS485: max baud rate 1 Mbps, automatic direction control, onboard 120 ohm termination resistor, mapped to UART0 (TX GPIO14, RX GPIO15)
- 1x RS232: max baud rate 250 kbps, mapped to UART4 (TX GPIO12, RX GPIO13)
- 6x isolated bidirectional digital input (up to 50V), sharing one common pin (DIC), for PNP or NPN sensors
- Digital input levels: VIL max ±0.8 V; VIH ±3 to ±50 V; isolation 3750 Vrms
- 4x isolated digital output (up to 50V), sharing one common pin (DOC): dry contact, driven by solid state relays, DC or AC load up to 50V 500mA, isolation 1500 Vrms, built-in surge protection
- 2x programmable LED: LED0 GPIO17, LED1 GPIO18
- 1x programmable active buzzer: GPIO23, active high
- Status LEDs for RS485, RS232, DI 0-5 and DO 0-3
- 5V display power connector
- Header pins for the optional LetsTrust TPM module (TPM 2.0, from pi3g)
- Pin mapping: DI0–DI5 = GPIO4, GPIO5, GPIO6, GPIO16, GPIO22, GPIO27; DO0–DO3 = GPIO19, GPIO20, GPIO21, GPIO26; TPM RSTn GPIO24, IRQn GPIO25, CS0n GPIO8, CS1n GPIO7, SPI MISO GPIO9, MOSI GPIO10, SCK GPIO11
- Operating temperature: -20 to 60 ℃
- Relative humidity: 10 – 80 % (non-condensing)
- Dimensions: [NOT STATED]

## Interfaces and compatibility
- Connects to the Raspberry Pi 5 40-pin GPIO header
- Pluggable IO terminal (20-pin pluggable terminal block included) for power input, RS485, RS232, DI and DO
- Enable RS485 with dtoverlay=uart0 and RS232 with dtoverlay=uart4 in /boot/firmware/config.txt
- RS485 supports Modbus RTU
- Enclosures: Argon Industria HMI 10CS, HMI 8CS, HMI 7C, HMI 5C and Argon Industria Basic Industrial Enclosure, all for Raspberry Pi 5
- Optional LetsTrust TPM module, supported directly by the Linux kernel TPM subsystem
- In the box: 1x Industrial IO HAT+, 1x 20-pin pluggable terminal block, 3x M2.5*21mm PCB stand, 1x sticker for pinout
- Also sold in Argon40 Industria HMI complete kits with display, Industrial IO HAT+ and 16GB Raspberry Pi 5 (5", 7", 8", 10")
- No earth connection required

## Use cases
- Greenhouse environment monitoring (temperature, humidity, soil moisture and nutrients, luminescence)
- Factory monitoring system
- Production line monitoring system
- Defect detection dashboard

## Known limitations
- Supports Raspberry Pi 5 only
- Digital inputs and outputs are limited to 50V; outputs max 500mA
- Digital outputs are dry contact: the load needs its own supply; a flyback diode is recommended for inductive loads to reduce EMI
- All six inputs share one common (DIC); all four outputs share one common (DOC)
- RS485 max 1 Mbps; RS232 max 250 kbps
- UART0 and UART4 must be enabled with dtoverlay lines in config.txt
- RS485 works with A-B only, but connecting GND is recommended for better noise immunity
- The 4A fuse might break on surge or overcurrent; if the device does not power up, check and replace the fuse
- The HAT+ 5A recognition needs Pi 5 bootloader version 2025-06-29 or greater
- With the TPM module fitted, GPIO7–GPIO11, GPIO24 and GPIO25 are used by the TPM
- Operating temperature -20 to 60 ℃; humidity 10 – 80 % non-condensing
- Raspberry Pi and enclosure not included

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 Industrial I/O HAT+"
- Co-developed with Argon40 for the Argon Industria HMI enclosures for Raspberry Pi 5
- Target audience: industrial engineers, training providers (SHRDC), system integrators, industrial AI system integrators
- Cytron tagline: "Simplifying Digital Making"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-industry-hat-plus-for-raspberry-pi-5

## Datasheet
https://docs.google.com/document/d/1G8XOqDg5tSYu-hFeNG1x2qfTjAIdBlXN-yGC49WR2nQ/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1G8XOqDg5tSYu-hFeNG1x2qfTjAIdBlXN-yGC49WR2nQ/edit

# Product fact sheets

## Product name
27W PD 5V 5A USB-C Universal Power Adapter for Raspberry Pi

## Aliases
V-AD-27W-PD, AD-27W-PD-X, 27W PD USB-C Power Adapter, 27W 5V 5A USB-C Universal Power Adapter, Cytron 27W PD PSU, 27W USB-C PSU for Raspberry Pi 5, HD-PD27W

## What it is
A 27 W AC-to-DC power supply with a captive USB Type-C cable and USB Power Delivery (5.1V 5A up to 15V 1.8A), designed to power the Raspberry Pi 5 and other compatible development boards. It accepts 100–240 VAC 50–60 Hz and uses interchangeable AC plug heads.

## Specs and functions
- Rated power, continuous: 27 W (datasheet)
- Typical output voltage: 5.1 VDC (datasheet)
- Rated output voltage, no load: 5V / 9V / 12V / 15V (datasheet)
- Full-load PD profiles: 5V 5A; 9V 3A; 12V 2.25A; 15V 1.8A (datasheet); 5.1V 5.0A / 9.0V 3.0A / 12.0V 2.25A / 15.0V 1.8A (product page)
- Nominal load current: 5 A (datasheet)
- Ripple and noise at full load: < 200 mV (p-p) (datasheet)
- Protection: Overcurrent Protection; Short Circuit Protection (datasheet)
- Efficiency (average): 84.25 % (5V); 86.62 % (9V/12V/15V) (datasheet); ~82% (product page)
- Electrostatic discharge: direct ± 4 kV; air ± 8 kV (datasheet)
- Rated input voltage: 100 – 240 VAC (datasheet)
- Rated input frequency: 50 – 60 Hz (datasheet)
- Maximum AC current: < 0.6 A (datasheet)
- Maximum inrush current, cold start: < 80 A (datasheet)
- Standby power at 115 or 230 VAC: < 0.1 W (datasheet)
- Output cable length: 1200 ± 50 mm (datasheet); 1.5 m (product page)
- Output cable type: UL 2464, 18AWG (datasheet)
- After-binding length: 80 ± 20 mm (datasheet)
- Output connector: USB Type-C (datasheet)
- Cable colour: black; housing: black (datasheet)
- Operating temperature: 0 ~ 40 °C (datasheet)
- Storage temperature: -25 ~ 70 °C (datasheet)
- Compliance UKCA: EN 55032:2015/A1:2020; EN 55035:2017/A11:2020; EN IEC 61000-3-2:2019/A1:2021; EN 61000-3-3:2013/A2:2021; BS EN 55032:2015/A1:2020; BS EN 55035:2017/A11:2020; BS EN IEC 61000-3-2:2019/A1:2021; BS EN 61000-3-3:2013/A2:2021 (datasheet)
- Compliance CE: EN 55032:2015/A1:2020; EN 55035:2017/A11:2020; EN IEC 61000-3-2:2019/A1:2020; EN 61000-3-3:2013/A2:2021; EN IEC 62368-1:2020+A11:2020 (datasheet)
- Certifications based on MPN: HD-PD27W-wwz (datasheet)
- AC plug options: UK (Type G) / EU (Type C) / US (Type A); only one included (product page); datasheet says three interchangeable AC plugs are included
- Adapter dimensions and weight: [NOT STATED] (drawings only)
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Output: one captive cable with USB Type-C plug; no other output connector
- Input: interchangeable AC plug head (EU / UK / US drawings in datasheet)
- Designed for Raspberry Pi 5 and other compatible development boards (datasheet); Raspberry Pi 4 Model B and Raspberry Pi 5 (product page)
- USB Power Delivery: the device selects a 5V/9V/12V/15V profile; "can be used to charge many types of devices" (datasheet)
- PD version, PPS, E-marker: [NOT STATED]

## Use cases
- Powering the Raspberry Pi 5 (5.1V 5A profile)
- Powering the Raspberry Pi 4 Model B (product page)
- Powering other compatible development boards and charging USB-C PD devices within the stated profiles

## Known limitations
- Operating temperature range 0 ~ 40 °C
- Only overcurrent and short-circuit protection are stated; over-voltage and over-temperature protection are not stated
- Captive cable: cannot be replaced or extended by swapping the cable
- Only one AC plug head is included per the product page (UK, EU or US chosen at purchase); the datasheet Rev 1.0 says three — confirm with the shipment
- Cable length stated differently: 1200 ± 50 mm (datasheet) vs 1.5 m (product page)
- Efficiency stated differently: 84.25 % / 86.62 % (datasheet) vs ~82% (product page)
- "Appearance details are subject to the actual samples" (datasheet)

## Positioning (kept apart from specs)
- "Specifically designed to provide power to the latest Raspberry Pi 5 and other compatible development boards" (datasheet)
- "Suitable for use around the world" thanks to 100–240 VAC input and interchangeable plugs; "versatile" PD support; "sleek black color" (datasheet)

## Price band
RM50.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-27w-pd-5v-5a-usb-c-universal-power-adapter

## Datasheet
https://docs.google.com/document/d/1pLMnoGWQFCbzt7I2AX8-qhGa6N6ljDat5eaFH6eBu-4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1pLMnoGWQFCbzt7I2AX8-qhGa6N6ljDat5eaFH6eBu-4/edit

# Product fact sheets

## Product name
17.5W 5V 3.5A USB-C Power Adapter for Raspberry Pi

## Aliases
V-AD-5V3P5A, AD-5V3P5-3P, 17.5W 5V 3.5A USB-C Power Adapter, 17.5W USB-C PSU for Raspberry Pi, 5V 3.5A USB-C Power Adapter, Cytron 17.5W USB-C PSU, HT24A-0503500BS

## What it is
A 17.5 W fixed 5 V, 3.5 A AC-to-DC power supply with a captive USB Type-C cable, designed to power the Raspberry Pi 4 Model B and other compatible development boards. It accepts 100–240 VAC 50–60 Hz and ships with one interchangeable AC plug (UK by default).

## Specs and functions
- Rated power, continuous: 17.5 W (datasheet)
- Nominal load current: 3.5 A (datasheet)
- Typical output voltage: 5.1 VDC (datasheet)
- Rated output voltage, no load: 4.75 – 5.4 VDC (datasheet)
- Rated output voltage, full load Iout = 3.5 A: 4.75 – 5.4 VDC (datasheet)
- Ripple and noise at full load: < 200 mV (p-p) (datasheet)
- Protection: Overcurrent Protection; Short Circuit Protection (datasheet)
- Efficiency (average): 82.32 % (datasheet)
- Electrostatic discharge: direct ± 4 kV; air ± 8 kV (datasheet)
- Rated input voltage: 100 – 240 VAC (datasheet)
- Absolute min/max input voltage: 90 – 264 VAC (datasheet)
- Rated input frequency: 50 – 60 Hz (datasheet)
- Maximum AC current: < 0.6 A (datasheet)
- Maximum inrush current, cold start: < 60 A (datasheet)
- Standby power at 115 or 230 VAC: < 0.1 W (datasheet)
- Output cable length: 1500 ± 50 mm (datasheet)
- Output cable type: UL 2464, 20AWG (datasheet)
- Output connector: USB Type-C (datasheet)
- Cable colour: black; housing: black (datasheet)
- Operating temperature: 0 ~ 40 °C (datasheet)
- Storage temperature: -25 ~ 70 °C (datasheet)
- Mean Time Between Failures (MTBF): 30000 hours (datasheet)
- Compliance UKCA: BS EN 62368-1:2014+A11:2017; EN 62378-1:2014+A11:2017 (as printed) (datasheet)
- Compliance UL: IEC 62368-1:2014 (datasheet)
- Compliance CE: EN 55032:2015/A11:2020; EN 55035:2017; EN IEC 61000-3-2:2019; EN 61000-3-3:2013/A1:2019 (datasheet)
- Compliance RoHS: IEC 62321-1:2013; IEC 62321-2:2021; IEC 62321-3-1:2013; IEC 62321-4:2013+A1:2017; IEC 62321-5:2013; IEC 62321-6:2015; IEC 62321-7-1:2015; IEC 62321-7-2:2017; IEC 62321-8:2017 (datasheet)
- Certifications based on MPN: HT24A-0503500BS (datasheet)
- AC plug: ONE interchangeable AC plug included, default UK; PSU shipped from 23 October 2024 onwards comes with UK plug only (datasheet); plug options UK / EU (product page)
- Adapter dimensions and weight: [NOT STATED] (drawings only)
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Output: one captive cable with USB Type-C plug; single fixed 5 V output; no USB Power Delivery profiles
- Input: interchangeable AC plug head (UK default)
- Designed for Raspberry Pi 4 Model B and other compatible development boards (datasheet)
- Recommended for Raspberry Pi 4 Model B, Raspberry Pi 400 and CM4 carrier boards with USB-C; "suitable for 24-hour operation" (product page)
- Product page compatibility list also includes Raspberry Pi 5 (8/4/2GB), Pi 4 B (1–8GB), Pi 400, many CM4 carriers, Jetson Nano developer kit, VisionFive 2 (product page)
- Linked Cytron tutorial: "Can 3A/3.5A PSU power Raspberry Pi 5" https://my.cytron.io/tutorial/can-3a-3.5a-psu-power-raspberry-pi-5

## Use cases
- Powering the Raspberry Pi 4 Model B
- Powering the Raspberry Pi 400 and CM4 carrier boards with USB-C input (product page)
- Powering other compatible 5 V USB-C development boards within 3.5 A

## Known limitations
- 5 V 3.5 A / 17.5 W only; no USB Power Delivery and no 5 A profile
- Designed for Raspberry Pi 4 Model B (datasheet); Raspberry Pi 5 appears only on the product page compatibility list
- Operating temperature range 0 ~ 40 °C
- Only overcurrent and short-circuit protection are stated
- Captive cable (20AWG, 1.5 m) cannot be replaced
- Only one AC plug is included; units shipped from 23 October 2024 come with the UK plug only (datasheet), although the product page lists UK / EU options
- Output voltage window is 4.75 – 5.4 VDC, not a fixed 5.1 V

## Positioning (kept apart from specs)
- "Specifically designed to provide power to the latest Raspberry Pi 4 Model B and other compatible development boards" (datasheet)
- "Suitable for use around the world"; "sleek black color" (datasheet)
- "Suitable for 24-hour operation" (product page)

## Price band
RM32.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-5v-3p5a-usb-c-universal-power-adapter

## Datasheet
https://docs.google.com/document/d/1xhmvk4w7S_FsKjmb7wwx1S1RvuXo-jRydAW7l1R8mxY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1xhmvk4w7S_FsKjmb7wwx1S1RvuXo-jRydAW7l1R8mxY/edit

# Product fact sheets

## Product name
3.7V 2200mAh 18650 Li-Ion Battery with Button Top

## Aliases
LI-18650-3.7-2200, 18650 2200mAh Li-Ion Battery, 3.7V 2200mAh 18650 Li-Ion Battery with Button Top, 18650 Button Top Li-Ion Cell, ICR18650 2200mAh, PKCELL ICR18650 2200mAh 3.7V, Cytron 18650 Battery

## What it is
A single cylindrical 18650-size lithium-ion cell, nominal 3.7 V (4.2 V full), 2200 mAh, with a button-top positive terminal and flat negative terminal. It has no built-in protection circuit and must be charged with a proper Li-ion charger with balancer.

## Specs and functions
- Chemistry / size: Li-ion, cylindrical 18650 (product page; vendor spec)
- Vendor model: ICR18650 2200mAh 3.7V, Shenzhen PKCELL (vendor spec)
- Nominal voltage: 3.7 V; 4.2 V when fully charged (product page)
- Capacity: 2200 mAh (product page); typical 2200 mAh, minimum 2090 mAh (vendor spec)
- Minimum discharge voltage / discharge cut-off: 3.0 V (product page; vendor spec)
- Charging voltage: 4.2 V ± 0.05 V (product page); charging cut-off 4.2 V (vendor spec)
- Rapid charge: 0.5C, ~1.1 A (product page)
- Standard charge: 0.2C, ~440 mA (product page)
- Vendor standard charge: CC 0.5C, CV 4.2 V, 0.01C cut-off, approx 4.0 h (vendor spec)
- Maximum constant charging current: 2200 mA (1.0C) (vendor spec)
- Maximum discharge: 1C, ~2.2 A (product page); maximum continuous discharge 3300 mA (1.5C) (vendor spec)
- Standard discharge: 0.2C, ~440 mA (product page)
- Operating temperature: charge 0 ~ 45 °C; discharge -20 ~ 60 °C (vendor spec)
- Storage temperature: -20 ~ 45 °C for 1 month; -10 ~ 35 °C for 6 months (vendor spec)
- Storage voltage: 3.7 – 3.85 V (vendor spec)
- Cycle life at 25 °C: ≥ 300 cycles to 80 % of rated capacity (vendor spec)
- Capacity retention after 28 days at 20 °C: ≥ 1760 mAh (vendor spec)
- Cell open-circuit voltage before delivery: ≥ 3.75 V (vendor spec)
- Protection circuit: NO built-in protection circuit (product page)
- Terminals: button top (medium) positive; flat negative (product page)
- Size: 2 cm x 6.5 cm x 2 cm (product page)
- Weight: [NOT STATED]
- Environmental: RoHS (vendor spec)
- Battery warranty: 1 week (product page); vendor warranty 1 year from leaving the manufacturer (vendor spec)
- Shipping: cannot ship to Sabah, Sarawak, or overseas (product page)

## Interfaces and compatibility
- Two bare terminals (button-top positive, flat negative); no tabs, wires, connector or protection PCB
- Requires a proper Li-ion charger with balancer (product page); charger not included and not named
- Used as the robot power in the STRIKER:BIT Soccer Competition Kit ("1x 3.7V 2200mAh 18650 Li-Ion with button top", STRIKER:BIT product page)
- Compatible holders: [NOT STATED]

## Use cases
- Power source for small robots and projects that need a single 3.7 V Li-ion cell (STRIKER:BIT robot power)
- Rechargeable cell for devices designed for 18650 button-top cells

## Known limitations
- NO built-in protection circuit — over-charge, over-discharge and short-circuit protection must be provided externally
- NOT an A/AA/AAA battery; does not fit AA holders
- Maximum discharge 1C (~2.2 A) per the product page (vendor spec states 1.5C / 3300 mA; product page value applies)
- Rapid charge limited to 0.5C (~1.1 A) per the product page (vendor spec allows up to 1.0C / 2200 mA; product page value applies)
- Do not discharge below 3.0 V or charge above 4.2 V ± 0.05 V
- Charge only between 0 and 45 °C; discharge between -20 and 60 °C (vendor spec)
- Battery warranty is 1 week only
- Cannot be shipped to Sabah, Sarawak, or overseas
- Vendor warnings: use a specified charger; do not throw into fire or heat; do not short-circuit, disassemble, reverse polarity, connect to a mains outlet, solder directly to the cell, pierce, strike or immerse in water; keep away from metal objects; remove a cell that smells, heats, discolours or deforms; tape terminals before disposal
- Vendor dimension drawing and internal impedance value not available in the extracted document

## Positioning (kept apart from specs)
- [NOT STATED]

## Price band
RM10.80; 5+ RM9.72; 20+ RM8.64 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-3.7v-2200mah-18650-li-ion-battery

## Datasheet
https://drive.google.com/file/d/1p_FfaVllULPQLdflNAwP4zIYq6_gvUbb/view

## Source type
Website

## Source link
https://my.cytron.io/p-3.7v-2200mah-18650-li-ion-battery

# Product fact sheets

## Product name
Cooling Fan for RPi with Screws (30mm x 30mm)

## Aliases
FAN-0305-3008, Cooling Fan for RPi with Screws (30mm x 30mm), 3V-5V 0.2A Cooling Fan for RPi, 30mm Raspberry Pi Cooling Fan, RPi 30mm Fan, Raspberry Pi GPIO Cooling Fan 30mm, Cytron RPi Cooling Fan

## What it is
A black 30 mm x 30 mm x 8 mm DC cooling fan for Raspberry Pi boards, supplied with four screws and nuts. Its two-wire connector plugs onto the Raspberry Pi 40-pin GPIO header and runs at one of two speeds depending on whether it is fed 3.3 V or 5 V.

## Specs and functions
- Operating voltage: 3 V to 5 V DC (product page)
- Rated current: 0.2 A (product page title)
- Dual speed: 3.3 V or 5 V DC from the Raspberry Pi 40-pin GPIO header; 5 V recommended (product page)
- Connector: two-wire connector for the 40-pin GPIO header (product page)
- Cable: "longer cable"; length [NOT STATED]
- Colour: black (product page)
- Dimensions: 30 mm x 30 mm x 8 mm (product page)
- Packing list: 1 x fan, 4 x screws and nuts (product page)
- Airflow, noise, RPM, bearing type, weight, wire gauge, operating temperature: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Power: Raspberry Pi 40-pin GPIO header, 3.3 V pin (low speed) or 5 V pin (high speed)
- Two wires only: no PWM wire, no tachometer wire
- Fits the RetroFlag SuperPi 4 case (product page)
- Shown fitted in the official Raspberry Pi 4 Model B case in a Jeff Geerling video (product page)
- Exact GPIO header pin numbers: [NOT STATED]
- Raspberry Pi 5 fan-header compatibility: [NOT STATED]

## Use cases
- Cooling a Raspberry Pi board powered from the GPIO header
- Fan upgrade for the RetroFlag SuperPi 4 case or the official Raspberry Pi 4 B case

## Known limitations
- Two-wire fan: no PWM speed control and no tachometer; speed is set only by choosing the 3.3 V or 5 V header pin
- No datasheet; airflow, noise and RPM figures are not published
- Cable length, wire colours and connector type are not stated
- Not stated for the Raspberry Pi 5 dedicated fan connector
- Draws up to 0.2 A from the Raspberry Pi header rail it is connected to

## Positioning (kept apart from specs)
- Fan "with screws" and a "longer cable" for Raspberry Pi; dual speed from the GPIO header (product page)

## Price band
RM8.00; 10+ RM7.36; 30+ RM6.40 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-3v-5v-0.2a-cooling-fan-for-rpi-with-screws

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-3v-5v-0.2a-cooling-fan-for-rpi-with-screws

# Product fact sheets

## Product name
NVMe 2242 M-Key MakerDisk SSD (Preloaded with RPi OS)

## Aliases
V-MMR-NV2242, MMR-NV2242, MakerDisk NVMe 2242, MakerDisk M.2 2242 NVMe SSD, MakerDisk 2242, NVMe 2242 MakerDisk SSD

## What it is
A Cytron-branded M.2 2242 NVMe (PCIe) solid-state drive that ships with Raspberry Pi OS already written to it, so a Raspberry Pi can boot from it without imaging. Three capacities: 128GB (B+M-Key, PCIe Gen3 x2), 256GB and 512GB (M-Key, PCIe Gen3 x4).

## Specs and functions
- Model: MMR-NV2242-XXX (datasheet); store code V-MMR-NV2242 with capacity option (product page)
- Interface: M.2 M-Key (B+M Key on 128GB SSD)
- Dimensions: M.2 2242, L42.00mm x W22.0mm x H2.7mm, error ±0.5mm
- Capacity: 128GB / 256GB / 512GB
- Protocol: 128GB = PCIe Gen3 x 2 Lane, NVMe 1.3; 256GB and 512GB = PCIe Gen3 x 4 Lane, NVMe 1.3
- NAND Flash: 3D TLC
- Sequential Read (MB/s): 128GB 1700; 256GB 2250; 512GB 2300
- Sequential Write (MB/s): 128GB 600; 256GB 1300; 512GB 1850
- 4K Random Read (IOPS): 128GB 70K (Max); 256GB 85K (Max); 512GB 145K (Max)
- 4K Random Write (IOPS): 128GB 130K (Max); 256GB 280K (Max); 512GB 400K (Max)
- Test conditions for the speed figures: [NOT STATED]
- Input Voltage: DC 3.3V ±5%
- Power Consumption (Idle): 0.60W (Max)
- Power Consumption (Active): 3.65W (Max)
- MTBF: 1.5 million hours
- ECC: LDPC Error Correction of Hardware / Bad Block Management
- Features: Power management / TRIM / S.M.A.R.T. / NCQ / Wear-leveling
- Operating Temperature: 0℃ – 70℃
- Storage Temperature: −40℃ – 85℃
- Operating Humidity: 5 – 90%
- Certificates: FCC, CE, RoHS, REACH
- Made in: Taiwan
- Preloaded OS: Raspberry Pi OS 64-bit Bookworm on units shipped from January 2024 (product page)
- Controller, TBW, weight, warranty, packing list: [NOT STATED]

## Interfaces and compatibility
- Bus: NVMe over PCIe Gen3 — it is NOT a SATA drive
- Boots on Raspberry Pi 5 with the latest bootloader and a PCIe-to-M.2 HAT+ (product page)
- Boots on Raspberry Pi 4 Model B with the latest bootloader via a USB-NVMe adapter (product page)
- Boots on Raspberry Pi 400 (product page)
- Boots on Compute Module 4 on an NVMe carrier, e.g. CM4 Maker Board (product page)
- HAT+, USB-NVMe adapter and CM4 carrier are requirements, not included
- Needs an M.2 slot with a 2242 mounting position; the M-Key (256GB/512GB) units do not fit B-Key sockets
- Cytron tutorials linked: Raspberry Pi Imager updating bootloader; Clone Raspberry Pi OS into SSD; CM4 Maker Board getting started

## Use cases
- Boot drive for Raspberry Pi 5 (via PCIe-to-M.2 HAT+)
- Boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400 (via USB-NVMe adapter)
- Boot drive for Compute Module 4 on an NVMe carrier such as the CM4 Maker Board

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded Raspberry Pi OS
- NVMe (PCIe) only; not usable in M.2 SATA slots or SATA adapters
- 128GB is B+M-Key and PCIe Gen3 x2; 256GB/512GB are M-Key and PCIe Gen3 x4 — speeds and keys differ by capacity
- Raspberry Pi 5 needs the latest bootloader and a PCIe-to-M.2 HAT+; Raspberry Pi 4 B needs the latest bootloader and a USB-NVMe adapter
- Datasheet speed figures have no stated test conditions and are not Raspberry Pi measurements
- OS image on units shipped before January 2024: [NOT STATED]

## Positioning (kept apart from specs)
- Product page: Jeff Geerling verified the drive on Raspberry Pi 5
- Ready-to-boot storage for Raspberry Pi — plug in and boot, no imaging needed (product page framing)

## Price band
RM369.00 – RM739.00 depending on capacity (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-nvme-2242-b-plus-m-key-makerdisk-ssd-preloaded-rpi-os

## Datasheet
https://docs.google.com/document/d/14tFhPy47Aa8ugKsBqsc8-0nyJH_La1EbLZbW4Ooeg_w/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/14tFhPy47Aa8ugKsBqsc8-0nyJH_La1EbLZbW4Ooeg_w/edit

# Product fact sheets

## Product name
NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready)

## Aliases
V-MMR-NV2280, MakerDisk NVMe 2280, MakerDisk 2280 RPi OS, NVMe 2280 MakerDisk SSD Raspberry Pi OS Ready, MakerDisk M.2 2280 NVMe SSD

## What it is
A Cytron-branded M.2 2280 M-Key NVMe (PCIe) solid-state drive that ships with Raspberry Pi OS 64-bit Bookworm already written to it, so a Raspberry Pi 5, Pi 4 Model B, Pi 400 or Compute Module 4 (on an NVMe carrier) can boot from it. Offered in 1TB, 512GB, 256GB and 128GB.

## Specs and functions
- Product code: V-MMR-NV2280
- Form factor: M.2 2280
- Key: M-Key
- Interface: NVMe (PCIe) — NOT SATA
- Capacities: 1TB / 512GB / 256GB / 128GB
- Preloaded OS: Raspberry Pi OS 64-bit Bookworm, on units shipped from 22 November 2023
- Speed test (128GB unit, Raspberry Pi Diagnostics): sequential write 385505 KB/s; random write 25680 IOPS
- Speed test host board and random read figure: [NOT STATED]
- PCIe generation, lane count, NVMe version, NAND type, controller: [NOT STATED]
- Power consumption, operating temperature, MTBF, TBW, weight: [NOT STATED]
- Warranty, packing list: [NOT STATED]
- Datasheet: none published

## Interfaces and compatibility
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400
- Boots on Compute Module 4 with an NVMe carrier — carriers named: Piunora, Mini Base (A)
- Host needs an M.2 M-Key slot with a 2280 mounting position
- Does not fit the CM4 Maker Board M.2 slot (that slot takes NVMe 2230/2242 only)
- Not usable in M.2 SATA slots or SATA adapters
- Cytron tutorial linked: home NAS with Raspberry Pi 5

## Use cases
- Boot drive for Raspberry Pi 5
- Boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400
- Boot drive for Compute Module 4 on an NVMe carrier (Piunora, Mini Base (A))
- Storage for a home NAS built on Raspberry Pi 5 (linked tutorial)

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded OS
- NVMe only; it is NOT SATA
- 2280 length; will not fit 2230/2242-only M.2 slots
- The only Cytron speed figures are Raspberry Pi Diagnostics results on the 128GB unit; they do not describe the other capacities
- HAT/adapter/carrier for the host board is not included
- OS image on units shipped before 22 November 2023: [NOT STATED]

## Positioning (kept apart from specs)
- "Raspberry Pi OS Ready" — plug in and boot (product page framing)

## Price band
RM1,099.00 shown for the 1TB option; other capacities not captured (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-nvme-2280-m-key-makerdisk-preloaded-with-rpi-os

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-nvme-2280-m-key-makerdisk-preloaded-with-rpi-os

# Product fact sheets

## Product name
NVMe 2280 MakerDisk SSD - JetPack for Jetson Orin Nano Super

## Aliases
V-MMR-NV2280-JP, MakerDisk NVMe 2280 JetPack, MakerDisk JetPack SSD, NVMe 2280 MakerDisk SSD JetPack, MakerDisk 2280 JetPack, JetPack MakerDisk

## What it is
A Cytron-branded M.2 2280 NVMe solid-state drive that ships with NVIDIA JetPack 6.2 and its SDK components already installed, for the NVIDIA Jetson Orin Nano Super Developer Kit (8GB) only. It fits the NVMe slot on the back of the carrier board and boots the kit without SDK Manager flashing of the OS.

## Specs and functions
- Product code: V-MMR-NV2280-JP
- Form factor: M.2 2280
- Interface: NVMe (PCIe)
- Capacities: 512GB / 256GB
- Preloaded software: NVIDIA JetPack 6.2 with SDK components, on units shipped from 6 February 2025
- Target device: NVIDIA Jetson Orin Nano Super Developer Kit (8GB) ONLY
- Firmware requirement: the Orin Nano firmware must be 36.0 or newer; cannot be used on firmware below 36.0 (JetPack 5.x)
- Login: pre-configured username and password; default login printed on the product page
- Installation: insert into the NVMe slot on the back of the carrier board at 45°, then screw down
- Linked references: NVIDIA Jetson Linux r36.4.3 release notes; "Nvbuf_utils to NVUtils" migration file
- PCIe generation, lane count, NVMe version, NAND type, controller: [NOT STATED]
- Read/write speed, power consumption, operating temperature, MTBF, TBW, weight: [NOT STATED]
- Warranty, packing list: [NOT STATED]
- Datasheet: none published

## Interfaces and compatibility
- Compatible: NVIDIA Jetson Orin Nano Super Developer Kit (8GB) with firmware 36.0 or newer
- Not compatible: Jetson Orin Nano on firmware below 36.0 (JetPack 5.x) until the firmware is upgraded
- Related Cytron service: Flash JetPack / Orin Nano Upgrade Service SEV-JN-ORNN (JetPack 5.x to 6.x, software only)
- Cytron tutorials linked: Upgrade Jetson Orin Nano to Super using NVIDIA SDK Manager; JetPack 7.2 install; F5-TTS; Jetson device skills
- Sibling product: NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready), V-MMR-NV2280 — same form factor, different preloaded OS, not interchangeable

## Use cases
- Ready-to-boot JetPack 6.2 system drive for the Jetson Orin Nano Super Developer Kit (8GB)
- Storage for the Jetson Orin Nano AI Fundamentals workshop kit (the kit includes a 512GB JetPack MakerDisk)

## Known limitations
- Jetson Orin Nano Super Developer Kit (8GB) ONLY
- Cannot be used on an Orin Nano with firmware below 36.0 (JetPack 5.x); upgrade the firmware first
- DO NOT format it — formatting removes the preloaded JetPack 6.2
- Ships with a pre-configured login; the credentials are on the product page and must not be copied into content
- Drive hardware specs (speed, lanes, NAND, power, temperature) are not published
- JetPack build on units shipped before 6 February 2025: [NOT STATED]

## Positioning (kept apart from specs)
- Skip the SDK Manager OS flash: JetPack 6.2 and SDK components come preloaded, plug in and boot (product page framing)

## Price band
RM469.00 – RM739.00 depending on capacity (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-nvme-2280-m-key-makerdisk-ssd-preloaded-with-jetpack

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-nvme-2280-m-key-makerdisk-ssd-preloaded-with-jetpack

# Product fact sheets

## Product name
120GB 2.5-inch MakerDisk SATA III SSD with RPi OS

## Aliases
MMR-2P5-MD-120, MakerDisk SATA 120GB, MakerDisk 2.5-inch SATA SSD, 120GB MakerDisk SATA III SSD, MakerDisk SATA SSD with RPi OS

## What it is
A Cytron-branded 120GB 2.5-inch SATA III solid-state drive that ships with Raspberry Pi OS 64-bit Bookworm already written to it. It connects to a Raspberry Pi 5, Pi 4 Model B or Pi 400 through a SATA-to-USB bridge and boots over USB.

## Specs and functions
- Product code: MMR-2P5-MD-120
- Form factor: 2.5-inch
- Interface: SATA III (6.0 Gbps)
- Capacity: 120GB
- Preloaded OS: Raspberry Pi OS 64-bit Bookworm, on units shipped from 1 November 2023
- Max sequential read: up to 550MB/s
- Max sequential write: up to 460MB/s
- Test conditions for the max figures: [NOT STATED]
- Raspberry Pi Diagnostics via USB3-SATA: sequential write 224438 KB/s; random write 23744 IOPS; random read 17102 IOPS
- Raspberry Pi Diagnostics host board: [NOT STATED]
- NAND type, controller, power consumption, operating temperature, MTBF, TBW: [NOT STATED]
- Dimensions, weight, warranty, packing list: [NOT STATED]
- Datasheet: none published

## Interfaces and compatibility
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B and Raspberry Pi 400 with the latest bootloader (USB boot)
- Connects through a SATA-to-USB bridge: SSD shield or USB 3.0-to-SATA adapter (not included)
- Not usable in M.2 slots, PCIe HATs or CM4 NVMe carriers — it is a 2.5-inch SATA drive
- Compute Module 4 and other Raspberry Pi models: [NOT STATED]

## Use cases
- USB boot drive for Raspberry Pi 5
- USB boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded OS
- SATA, not NVMe; needs a USB-SATA bridge on every Raspberry Pi
- Requires the latest bootloader with USB boot on the Pi
- Pi-measured throughput via USB3-SATA (224438 KB/s sequential write) is far below the drive's 550MB/s / 460MB/s SATA maxima
- OS image on units shipped before 1 November 2023: [NOT STATED]

## Positioning (kept apart from specs)
- Ready-to-boot Raspberry Pi OS SSD for USB boot (product page framing)

## Price band
RM118.80 special offer, was RM158.40 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-120gb-2p5-inch-makerdisk-sata-3-ssd-with-raspberry-pi-os

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-120gb-2p5-inch-makerdisk-sata-3-ssd-with-raspberry-pi-os

# Product fact sheets

## Product name
AI Agent Workshop for RPI 5

## Aliases
V-AI-AGT-RPI, AI Agent Workshop for RPI 5, AgentBox AI Agent Workshop, AgentBox Workshop, AI Agent Workshop for Raspberry Pi 5

## What it is
A two-day hands-on training workshop at Cytron HQ, sold together with an AgentBox kit, that teaches participants to build AI agents on AgentBox, a Raspberry Pi 5-powered local AI agent hub. Participants connect to cloud LLMs through OpenRouter or local models through an Ollama server and build, test and deploy their own task-oriented AI agent.

## Specs and functions
- Programme title: AgentBox AI Agent Workshop (course outline)
- Duration: 2 days (course outline, product page)
- Venue: Cytron HQ ("Training at HQ") (product page)
- Dates offered as of 2026-10-19: 10 & 11 Sep 2026; 15 & 16 Oct 2026; 19 & 20 Nov 2026 (product page)
- Option: "Kit + 2 Day Training at HQ", date chosen as the variant (product page)
- Availability: 10 (product page, 2026-10-19)
- Warranty shown on page: 12 months (product page)
- Platform: AgentBox, a Raspberry Pi 5-powered local AI agent hub with a browser-based visual workflow builder connecting inputs, LLMs, knowledge bases, tools and outputs (product page)
- Model providers: cloud models via OpenRouter; local models via an Ollama server (course outline, product page)
- Training methodology: instructor-led presentations, live demonstrations, guided hands-on activities, individual practical activities, real-world use case demonstrations, project-based learning, interactive Q&A (course outline)
- Learning outcomes: understand AI agent and LLM fundamentals; navigate and operate AgentBox; design effective prompts and agent workflows; develop an AI agent for a specific real-world task (course outline)
- Module 1 – Introduction to AI Agents and AgentBox: Generative AI, LLMs, cloud vs local models, AI agent fundamentals and use cases; AgentBox hardware overview, system architecture, interface tour, connecting to model providers (course outline)
- Module 2 – Configuring AgentBox: initial system configuration, connecting to OpenRouter, connecting to a local Ollama server, managing models, model selection; creating a first agent, agent settings, prompt engineering, agent instructions, testing and troubleshooting (course outline)
- Module 3 – Building Practical AI Agents: task-specific agents, agent workflows, context and memory, improving response quality, practical exercises; managing multiple agents, testing different models, performance and cost considerations, best practices (course outline)
- Module 4 – Hands-on Project: plan, design, configure, build and test an agent for a real-world use case; final demonstration, peer review, troubleshooting and optimisation, future enhancements, wrap-up and Q&A (course outline)
- Prerequisites: no prior AI development experience required (course outline)
- Kit contents: [NOT STATED]
- Participant limit: [NOT STATED]
- Certification: [NOT STATED]
- Refund / cancellation terms: [NOT STATED]

## Interfaces and compatibility
- Host hardware: Raspberry Pi 5 (AgentBox is Raspberry Pi 5-powered) (course outline, product page)
- AgentBox is browser-based (product page)
- LLM connections: OpenRouter (cloud) and Ollama server (local) (course outline, product page)
- Laptop or other participant-supplied equipment: [NOT STATED]

## Use cases
- Automating tasks, interacting with information and improving productivity with AI agents (course outline)
- Building, testing and deploying a task-oriented AI agent that can be customised after the workshop (course outline)
- Training for IT professionals, software developers, AI/ML enthusiasts, makers and Raspberry Pi users, technical educators and trainers, and university students in Computer Science, Engineering or IT (course outline)

## Known limitations
- Two of the three listed dates (Sep and Oct 2026) had passed by 2026-10-19; only 19 & 20 Nov 2026 remained
- Kit contents, participant limit, certificate, meals and refund terms are not stated in the sources read
- Course outline carries no version or date

## Positioning (kept apart from specs)
- "No prior AI development experience is required, making this workshop suitable for beginners while still providing valuable insights for technical users" (course outline)
- For beginners, makers, developers and educators (product page)

## Price band
RM1,930.50–RM3,861.00, with a 50% offer shown (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ai-agent-workshop-for-rpi-5

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1e8Z1nlHWOvaEaraC6Fm3W8f-05Oz4c9S/edit

# Product fact sheets

## Product name
Jetson Orin Nano AI Fundamentals: Hands-On Workshop with NVIDIA Certification

## Aliases
V-TW-JNORNN-NVIDIA, Jetson Orin Nano AI Fundamentals Workshop, Jetson Orin Nano Workshop with NVIDIA Certification, Jetson Orin Nano Hands-On Workshop, Cytron Jetson Orin Nano Workshop

## What it is
A one-day hands-on AI fundamentals workshop on the NVIDIA Jetson Orin Nano at the Cytron Technologies office in Penang, with an official NVIDIA AI certification on completion. It is sold as a kit-plus-training bundle or as a workshop-only seat for owners of the Jetson Orin Nano Training Kit V2.

## Specs and functions
- Duration: 1 day, timetable 9:00 AM to 5:00 PM (product page, workshop tentative)
- Venue: Cytron Technologies office, Penang ("Training at HQ") (product page)
- Dates offered as of 2026-10-19: 30 Sep 2026; 21 Oct 2026; 18 Nov 2026 (product page)
- Options: Kit + 1 Day Training at HQ (date chosen as variant); Workshop ONLY for owners of the Jetson Orin Nano Training Kit V2, loan units on request (product page)
- Availability: 10 (product page, 2026-10-19)
- Warranty shown on page: 12 months (product page)
- Certification: official NVIDIA AI certification on completion (product page)
- Topics: setup, architecture, real-time object detection, image classification, image regression, edge inference (product page)
- Tentative Day 1 timetable: Ice Breaking 9:00–9:15 AM; Theory about AI/ML/DL 9:15–9:45 AM; Breakfast 9:45–10:15 AM; Theory about Jetson Orin Nano 10:15–10:45 AM; Theory about CUDA 10:45–11:15 AM; Hands On with Jetson Orin Nano 11:15 AM–12:15 PM; Create NVIDIA Account 12:15–1:00 PM; Lunch 1:00–2:00 PM; Image Classification/Test 2:00–3:00 PM; Image Regression/Test 3:00–4:00 PM; Tea Break 4:00–4:30 PM; Q&A / Summary 4:30–5:00 PM (workshop tentative)
- Kit option contents as far as stated: NVIDIA Jetson Orin Nano Super Developer Kit (8GB) preassembled in an aluminium alloy case with external antennas; 19V 45W power supply; NVMe 2280 MakerDisk SSD 512GB preloaded with JetPack; remaining items not stated (product page)
- Participant limit: [NOT STATED]
- Prerequisites: [NOT STATED]
- Refund / cancellation terms: [NOT STATED]
- Meals included: [NOT STATED]

## Interfaces and compatibility
- Hardware platform: NVIDIA Jetson Orin Nano Super Developer Kit (8GB) (product page)
- Storage: NVMe 2280 MakerDisk SSD 512GB with JetPack preloaded (product page)
- Power: 19V 45W power supply (product page)
- Workshop ONLY requires the participant's own Jetson Orin Nano Training Kit V2 or a loan unit requested in advance (product page)
- An NVIDIA account is created during the workshop (workshop tentative)

## Use cases
- Learning Jetson Orin Nano setup and architecture (product page)
- Hands-on real-time object detection, image classification and image regression (product page, workshop tentative)
- Edge inference on Jetson Orin Nano (product page)
- Earning an official NVIDIA AI certification (product page)

## Known limitations
- The 30 Sep 2026 date had passed by 2026-10-19
- Workshop ONLY option is for owners of the Jetson Orin Nano Training Kit V2; others need a loan unit on request
- The timetable is titled "Tentative"; the PDF prints two "11:15PM" times that are typographical errors for 11:15 AM
- The tentative timetable shows only image classification and image regression hands-on slots, while the page also lists real-time object detection
- Full kit list, JetPack version, participant limit, prerequisites, meals and refund terms are not stated in the sources read

## Positioning (kept apart from specs)
- Hands-on AI fundamentals workshop with NVIDIA certification (product page)

## Price band
RM1,200.00–RM5,073.36, offer shown (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-jetson-orin-nano-ai-fundamentals-hands-on-workshop-with-nvidia-certification-v

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
https://drive.google.com/file/d/1W4ZJX9gzJETGO6qNpKIIxZXKXTTGLwMZ/view

# Product fact sheets

## Product name
Cytron Raspbot Workshop (Introduction to AI)

## Aliases
V-TRAINING-AI, Cytron Raspbot Workshop, Raspbot Workshop (Introduction to AI), Raspbot Workshop, Raspbot Edge AI Workshop, Raspbot AI Training

## What it is
A one-day Edge AI workshop at Cytron HQ in Bukit Mertajam, Penang, built around the Raspbot, a Raspberry Pi 5 mobile robot with a camera. The price includes the Raspbot kit, food and a certificate, with a maximum of 5 participants per workshop.

## Specs and functions
- Duration: one day, 9.00 am to 5.00 pm (product page, workshop tentative)
- Venue: Cytron HQ, Bukit Mertajam, Penang; can be conducted at the customer's location on request (product page)
- Dates offered as of 2026-10-19: 15 Oct 2026; 12 Nov 2026; 10 Dec 2026 (product page)
- Maximum 5 participants per workshop (product page)
- Food included (product page)
- Certificate provided (product page)
- Availability: 15 (product page, 2026-10-19)
- Warranty shown on page: 12 months (product page)
- Kit: Raspberry Pi 5 (8GB); 32GB microSD with Raspbot OS; car expansion board; camera platform PCB; PTZ component; 4x mecanum wheels; 4x motor fixing frames; 4-channel tracking module; 4x motor; battery + velcro; 40-pin cable; camera; ultrasonic sensor; remote control; screwdriver; micro HDMI cable; 12.6V charger (EU) + UK adapter; screw pack; manual (product page)
- Tentative timetable: Ice Breaking 9:00–9:15 AM; Introduction to Python 9:15–10:00 AM; Breakfast 10:00–10:30 AM; Factory Tour 10:30–11:00 AM; Introduction to OpenCV 11:00–11:30 AM; Introduction to AI 11:30 AM–12:30 PM; Introduction to ROS2 12:30–1:00 PM; Lunch 1:00–2:00 PM; Assembling Raspbot 2:00–2:30 PM; Testing Raspbot App 2:30–3:00 PM; Raspbot Programming 3:00–4:30 PM; Tea Break 4:30–4:45 PM; Q&A / Summary 4:45–5:00 PM (workshop tentative)
- Prerequisites: [NOT STATED]
- Refund / cancellation terms: [NOT STATED]

## Interfaces and compatibility
- Robot computer: Raspberry Pi 5 (8GB) with Raspbot OS on 32GB microSD (product page)
- Laptop requirement for participants: [NOT STATED]

## Use cases
- Introduction to AI with a Raspberry Pi mobile robot and camera (product page)
- Python, OpenCV, AI and ROS2 fundamentals in one day (workshop tentative)
- Assembling, testing and programming the Raspbot (workshop tentative)

## Known limitations
- Maximum 5 participants per workshop (product page)
- The 15 Oct 2026 date had passed by 2026-10-19
- Battery chemistry and capacity are not stated; only "battery + velcro" and a 12.6V charger (EU) with UK adapter are listed
- Prerequisites, laptop requirement and refund terms are not stated in the sources read
- The timetable is titled "Tentative"

## Positioning (kept apart from specs)
- Introduction to AI workshop with a hands-on mobile robot, food and certificate included (product page)

## Price band
RM1,800.00 offer, was RM2,100.00 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-ai-training-kit

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
https://drive.google.com/file/d/1UqgaUC4sCqkGij_CYugQJBWlGZO8z-C6/view

# Product fact sheets

## Product name
Flash Jetpack Service / Orin Nano Upgrade Service

## Aliases
SEV-JN-ORNN, Flash Jetpack Service, Orin Nano Upgrade Service, Jetson Orin Nano Upgrade Service, JetPack 5.x to 6.x Upgrade Service, Jetson Orin Nano JetPack Flash Service

## What it is
A software-only service in which Cytron upgrades a customer's NVIDIA Jetson Orin Nano from JetPack 5.x to JetPack 6.x. No hardware is included; it is priced at RM150.00 and ordered by enquiry.

## Specs and functions
- Type: software-only service, no hardware included (product page)
- Target device: NVIDIA Jetson Orin Nano (product page)
- Upgrade path: JetPack 5.x to JetPack 6.x (product page)
- Delivers: latest CUDA, TensorRT, cuDNN and DeepStream (product page)
- Enables the new 25W power mode, the "Super" performance mode (product page)
- Up to 70% more generative AI performance, as stated by NVIDIA (product page)
- Availability: enquiry ("Inquire Now") (product page, 2026-10-19)
- Exact JetPack 6.x release flashed: [NOT STATED]
- Turnaround time: [NOT STATED]
- Delivery method (send-in / on-site): [NOT STATED]
- Data preservation: [NOT STATED]
- Warranty on the service: [NOT STATED]

## Interfaces and compatibility
- Applies to the NVIDIA Jetson Orin Nano (product page)
- A Jetson Orin Nano on firmware below 36.0 (JetPack 5.x) cannot use Cytron's MakerDisk NVMe 2280 SSD preloaded with JetPack 6.2; this service moves the board to JetPack 6.x (MakerDisk JetPack product page)
- Linked documents: NVIDIA Jetson Orin Nano Series datasheet; Jetson Orin Nano Training Kit Getting Started Guide (product page)
- The Getting Started Guide covers the Orin Nano Developer Kit tour, peripherals, login and software updates, the jetson-inference Docker container, image classification, object detection and semantic segmentation (Getting Started Guide)
- Coverage of Orin Nano 4GB, Orin NX or third-party carriers: [NOT STATED]

## Use cases
- Upgrading a Jetson Orin Nano from JetPack 5.x to JetPack 6.x for the latest CUDA, TensorRT, cuDNN and DeepStream (product page)
- Unlocking the 25W "Super" power mode for more generative AI performance (product page)
- Preparing a JetPack 5.x board to boot a JetPack 6.2 MakerDisk SSD (MakerDisk JetPack product page)

## Known limitations
- Software-only; no hardware included (product page)
- Ordered by enquiry, not stocked (product page)
- Exact JetPack 6.x release, turnaround, delivery method, data handling and warranty are not stated in the sources read
- The Getting Started Guide's Appendix D lists Developer Kit module power as 7W to 15W, which predates the 25W mode enabled by JetPack 6.x
- The Getting Started Guide carries no version or date and does not state which JetPack it targets

## Positioning (kept apart from specs)
- "Super" performance: new 25W power mode with up to 70% more generative AI performance per NVIDIA (product page)

## Price band
RM150.00, by enquiry (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x
