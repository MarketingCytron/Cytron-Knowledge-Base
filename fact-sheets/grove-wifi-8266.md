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
- 32 Mbit SPI flash; 802.11 b/g/n 2.4 GHz; on-board Reset and Boot switches (product page)
- Packing: module and a Grove cable (product page)

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
RM27.72 (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-grove-wifi-8266-iot-for-microbit-and-beyond

## Datasheet
https://docs.google.com/document/d/1ub3WuRrp1F8QijoHCDjOez6SC1mtG5pQglhiPdeB12k/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1ub3WuRrp1F8QijoHCDjOez6SC1mtG5pQglhiPdeB12k/edit
