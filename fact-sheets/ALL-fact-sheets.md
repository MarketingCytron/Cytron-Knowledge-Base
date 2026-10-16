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
