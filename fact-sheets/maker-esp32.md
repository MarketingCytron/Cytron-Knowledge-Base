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
- Cytron tutorial: [Getting Started with FreeRTOS on ESP32](https://my.cytron.io/tutorial/getting-started-freertos-esp32)
- Cytron tutorial: [Getting Started with ESP32 & PS4 Controller: Beginner](https://my.cytron.io/tutorial/esp32-ps4controller-beginner)
- Cytron tutorial: [Getting Started with ESP32 & Blynk](https://my.cytron.io/tutorial/getting-started-esp32-and-blynk)
- Cytron tutorial: [Getting Started with ESP32 & Node-RED](https://my.cytron.io/tutorial/getting-started-esp32-and-nodered)
- Cytron tutorial: [ESP32 Control Outputs with Telegram](https://my.cytron.io/tutorial/control-esp32-outputs-with-telegram)

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
RM40.95 (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-maker-esp32

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

