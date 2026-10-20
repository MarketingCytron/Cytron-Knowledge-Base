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
- 3.3 V regulator for the module: 500 mA max (product page)
- Shipped with Cytron_ESP_AT V2.2.0 since mid-October 2021; Rev2.0 since April 2016; Rev1.0 used an ESP8266-12 module (product page)
- UART jumper options: USB (flash the ESP8266 through the Arduino), D0/D1, or software serial on D2, D3, D8–D13 (product page)

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
- Cytron tutorial: [Arduino Blynk Lesson 4 : Timer](https://my.cytron.io/tutorial/arduino-blynk-lesson-4-timer)
- Cytron tutorial: [Arduino Blynk Lesson 2 : Notification](https://my.cytron.io/tutorial/arduino-blynk-lesson-2-notification)
- Cytron tutorial: [Arduino Blynk Lesson 1: LED](https://my.cytron.io/tutorial/arduino-blynk-lesson-1-led)
- Cytron tutorial: [Arduino Blynk Lesson 3 : Servo](https://my.cytron.io/tutorial/arduino-blynk-lesson-3-servo)

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
RM52.40 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-cytron-esp8266-wifi-shield

## Datasheet
https://docs.google.com/document/d/1LFCe6MTNQh_0EBHRgc0f6n_hDLNUG8sFuM53oBJG8eE/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1LFCe6MTNQh_0EBHRgc0f6n_hDLNUG8sFuM53oBJG8eE/view
