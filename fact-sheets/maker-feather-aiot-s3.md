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
- Cytron tutorial: [Getting Started with Maker Feather AIoT S3 (Arduino IDE)](https://my.cytron.io/tutorial/getting-started-with-Maker-Feather-AIoT-S3-(ArduinoIDE))
- Cytron tutorial: [Getting Started with Maker Feather AIoT S3 using CircuitPython](https://my.cytron.io/tutorial/get-started-with-maker-feather-aIot-s3-using-circuitpyhton)
- Cytron tutorial: [Maker Feather AIOT S3 Data Logging To Firebase](https://my.cytron.io/tutorial/maker-feather-aiot-s3-data-logging-to-firebase)
- Cytron tutorial: [How To Control LED with Blynk Using Maker Feather AIOT S3](https://my.cytron.io/tutorial/how-to-control-led-with-blynk-using-maker-feather-aiot-s3)
- Cytron tutorial: [Arducam Mega 3MP with Maker Feather AIOT S3](https://my.cytron.io/tutorial/arducam-mega-3mp-with-maker-feather-aiot-s3)

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
RM79.80–RM87.80 across 2 variants (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-v-maker-feather-aiot-s3-simplifying-aiot-with-esp32

## Datasheet
https://docs.google.com/document/d/1vVYSdn84I8Hvi9SWHU54lhH_vWlhD3mwJ6pcSyLNGcE/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1vVYSdn84I8Hvi9SWHU54lhH_vWlhD3mwJ6pcSyLNGcE/edit
