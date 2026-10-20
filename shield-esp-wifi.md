# Cytron ESP8266 WiFi Shield — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-ESP-WIFI` [PP][UM]; manual title "ESPWiFi Shield Rev2.0" [UM]; library name "Cytron ESPWiFi Shield" [GH] |
| Family | Arduino shields |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 4): live my.cytron.io product page read (description, features, packing list, resources). Revision history, Rev1.0 module (ESP8266-12), the 3.3 V regulator rating (500 mA) and the firmware shipped since Oct 2021 are now Cytron-stated |
| Primary source | **No datasheet exists.** Primary = "ESPWiFi Shield SHIELD-ESP-WIFI Rev2.0 User's Manual", **V2.1, August 2021** (public Google Doc) [UM]. Older: "ESPWiFi Shield SHIELD-ESP-WIFI User's Manual" V1.0, Nov 2015 (Rev1.0 hardware) [UM-R1] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = Rev2.0 manual V2.1 Aug 2021; [UM-R1] = Rev1.0 manual V1.0 Nov 2015 (both Google Docs; layout and dimension drawings are images, not readable as text). [PP] = coordinator's read of https://my.cytron.io/p-cytron-esp8266-wifi-shield on 2026-10-16. [GH] = CytronWiFiShield library (library.properties v3.0.2) and esp-at-binaries repo. [VEN] = Espressif ESP-WROOM-02 Datasheet v2.0, Nov 2016 (SparkFun mirror; the Drive copy linked from the product page returned "not found"). The two schematic PDFs on Drive (SHIELD-ESP-WIFI_schematic.pdf, sheet dated 1/6/2016; SHIELD-ESP-WIFI-R2-Sch.pdf, uploaded 14 Apr 2016) are vector drawings with no extractable text and the Drive download is blocked here — **not read**. No Drive hit for a separate datasheet. No [DT] confirmation.

## What it is
An Arduino shield carrying an Espressif ESP-WROOM-02 (ESP8266) Wi-Fi module preloaded with AT-command firmware, which the Arduino talks to over a jumper-selected hardware or software UART [UM]. It also has a USB jumper position for talking to the module straight from the PC through the Arduino's USB-serial, a microSD card slot on D4, a 3.3 V ESP GPIO breakout, a prototyping area, Flash/Run switch and separate Arduino and ESP reset buttons [UM]. Cytron provides the "Cytron ESPWiFi Shield" Arduino library (TCP client/server over AT commands) and the ESP-AT firmware binaries [UM][GH].

## Specifications
The manual has no numbered spec table; the rows below are every quantitative or definite statement in it [UM], plus module data [VEN] and firmware/library data [GH].

| Item | Value | Src |
|---|---|---|
| Wi-Fi module | ESP-WROOM-02 (Rev2.0); Rev1.0 manual says only "ESP8266 module" | [UM][UM-R1] |
| Module Wi-Fi standard / band | IEEE 802.11 b/g/n, 2.4–2.5 GHz | [VEN] |
| Module flash | 2 MB SPI flash | [VEN] |
| Module operating voltage / avg current | 3.0–3.6 V (3.3 V typ); average operating current 80 mA; max listed TX current 170 mA | [VEN] |
| Module operating temperature | −40 to 85 °C | [VEN] |
| Preloaded firmware | AT firmware; current Cytron binary **Cytron_ESP-12F_WROOM-02_AT_Firmware_V2.2.0.bin** (ESP-AT v2.2.0, UART0 on GPIO1/GPIO3) | [UM][GH] |
| Default UART (AT firmware, as shipped) | "9600 kbps baudrate, 8 bit data, 1 stop bit and no parity" (sic — 9600 baud) | [UM] |
| UART after a fresh firmware flash | 115200; manual sets 9600 with `AT+UART_DEF=9600,8,1,0,0` | [UM][GH] |
| Arduino RX pin (jumper) | D0, D2, D8, D10, D12 or USB | [UM] |
| Arduino TX pin (jumper) | D1, D3, D9, D11, D13 or USB | [UM] |
| microSD chip select | D4 — "Do not make any other connection to this pin" | [UM] |
| ESP 3V3 GPIO breakout | 9 digital I/O pins + 1 analog input pin; "All pins are 3.3V tolerant only" | [UM] |
| Prototyping area | Yes (size not stated) | [UM] |
| LEDs | Power LED (on when 5 V is supplied to the module), RX LED, TX LED | [UM] |
| Buttons / switches | Arduino Reset button; ESP Reset button; Flash/Run slide switch | [UM] |
| Headers | Stackable digital I/O and analog input headers | [UM] |
| Packing list | 1 x ESPWiFi Shield, 2 x mini jumper | [UM] |
| Warranty | 6 months [UM] / 12 months [PP] — see Conflicts | [UM][PP] |
| Dimensions | **Not stated in text** (drawing only) | [UM] |
| 3.3 V regulator output current | 500 mA max (regulator part not stated) | [PP] |
| Shield power input range | **Not stated** (powered from the Arduino's 5 V; Power LED "will turn on when 5V power is supplied") | [UM] |
| Library | Cytron ESPWiFi Shield v3.0.2 (`CytronWiFiShield.h`) | [GH] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Revision notes:** "This shield is Rev2.0 starting April 2016"; "From mid of October 2021 onwards, Cytron ESP8266 WiFi Shield is uploaded with Cytron_ESP_AT V2.2.0 ESP-AT Firmware" (binaries on GitHub `esp-at-binaries`); "Rev2.0 utilize WROOM-02 instead of ESP8266-12 as the WiFi module" [PP].
- **Features list:** Arduino R3 layout (Maker UNO, CT-UNO, CT-ARM, Arduino UNO R3, Leonardo and other compatibles); **on-board 3.3 V regulator for the WROOM-02, 500 mA max output**; every board preassembled and tested; UART pins by mini jumper — USB (direct to the Arduino's USB-serial for flashing the ESP8266), D0/D1 (hardware serial on UNO/CT-UNO), D2, D3, D8–D13 (software serial); 802.11 b/g/n; Wi-Fi Direct (P2P), soft-AP; integrated TCP/IP stack; +19.5 dBm in 802.11b mode [PP].
- **Description:** pre-flashed AT firmware controlled over UART; most ESP8266 I/O broken out, the module can be programmed directly; microSD slot for data logging [PP].
- No packing-list tab on the page [PP].
- **Resources:** Rev1.0 schematic and manual (ESP8266-12), Rev2.0 schematic and manual (ESP-WROOM-02), ESP-WROOM-02 datasheet, CytronWiFiShield library (GitHub), ESP-AT firmware (GitHub), tutorials (EasyMP3 with WiFly remote, light dancing, Maker UNO IoT with Blynk in Malay) [PP].

## Interfaces, terminals and pin mapping
| Function | Arduino pin(s) / terminal | Src |
|---|---|---|
| ESP UART RX ← Arduino TX | Jumper: D1, D3, D9, D11, D13, USB | [UM] |
| ESP UART TX → Arduino RX | Jumper: D0, D2, D8, D10, D12, USB | [UM] |
| microSD card CS | D4 (fixed) | [UM] |
| microSD data | SPI — "SPI pinouts uses D10-D13 in Arduino Uno" | [UM] |
| ESP 3V3 GPIO breakout | 9 digital + 1 analog (ESP pins; which GPIO numbers **not stated**) | [UM] |
| Power LED / RX LED / TX LED | Module power; RX/TX signal activity "from ESP8266" | [UM] |
| Flash/Run switch | Flash = module waits for firmware upload; Run = runs firmware | [UM] |
| Arduino Reset / ESP Reset | Separate push buttons | [UM] |

**Recommended RX/TX pairs per board** (UM Table 5.1) [UM]:

| RX | TX | Boards |
|---|---|---|
| USB | USB | Uno / Mega / Leonardo — PC ↔ ESP via Serial Monitor etc. (AT test and flashing only) |
| D0 | D1 | Uno / Mega / Leonardo (hardware serial) |
| D2 | D3 | **Arduino Uno only** (recommended default) |
| D8 | D9 | Uno / Leonardo |
| D10 | D11 | Uno** / Mega / Leonardo |
| D12 | D13 | Uno** / Mega |

** "Only applicable if no SPI communication is used because SPI pinouts uses D10-D13 in Arduino Uno. MicroSD card cannot be used as well in this case." [UM]

## Rules and gotchas (for code, wiring and tutorials)
- **Default to software serial D2 (RX) / D3 (TX)**: "We recommend user to use software serial (D3-TX, D2-RX) instead of hardware serial." → `wifi.begin(2, 3)` — "1st argument … refers to RX of Arduino and 2nd refers to TX" [UM][GH].
- **Jumpers and code must agree**: the jumpers physically route the ESP UART; the sketch must use the same pins [UM]. On Mega, D2/D3 is **not** listed — use D10/D11 or D12/D13 (software serial RX on Mega only works on pins with pin-change interrupts) [UM].
- **USB jumper position = PC talks to the ESP directly.** Hold the Arduino in reset (RST to GND with a jumper wire) or upload an empty sketch first, otherwise the Arduino's own serial traffic interferes [UM]. The GitHub flashing guide uploads "Blink" instead of an empty sketch [GH].
- **AT test settings**: Serial Monitor 9600 baud, "Both NL & CR"; `AT` → `OK` [UM].
- **D4 is reserved** for the microSD CS even if no card is used [UM].
- **microSD vs UART on D10–D13**: choosing D10/D11 or D12/D13 for UART kills SPI and the microSD slot [UM].
- **ESP GPIO breakout is 3.3 V only** — never drive it from 5 V Arduino pins without level shifting [UM].
- **Firmware flashing sequence**: jumpers USB, RST→GND, slide switch FLASH, press ESP Reset, Flash Download Tool at 115200, binary at 0x0, then after flashing: 115200 baud → wait for "ready" → `AT+UART_DEF=9600,8,1,0,0` → switch Serial Monitor to 9600 → move jumpers back to D2/D3 → RUN mode [UM][GH]. Flash tool settings per Cytron: CrystalFreq 26M, SPI SPEED 40MHz, SPI MODE DIO, FLASH SIZE 32Mbit, "DoNotChgBin" selected [GH].
- **Library auto-recovers from 115200**: `begin()` tries 9600, and if `AT` gets no reply it re-opens at 115200 and sends `AT+UART_DEF=9600,8,1,0,0`, then returns to 9600 [GH]. `setBaud()` constrains to 110–115200 [GH].
- **ESP-AT vs NONOS-AT**: Cytron's binaries are ESP-AT v2.2.0 (OS-based; AT set "not fully compatible with the legacy AT firmware"); legacy NONOS-AT ≤ v1.7.x is "no longer supported by Espressif" [GH]. The library keeps a NONOS fallback for `AT+CIPSTA?` and notes SSL buffer sizing is "incompatible with ESP-AT firmware" [GH].
- Library limits: `ESP8266_MAX_SOCK_NUM 5`, `ESP8266_RX_BUFFER_LEN 128`, Wi-Fi connect timeout 30 s, command timeout 5 s [GH].
- The Rev2.0 getting-started adds: "Make sure PC is connected to the same internet network with the ESPWiFi Shield" before browsing to the shield's IP [UM].
- Do not quote "9600 kbps" from the manual — it is a typo for 9600 baud (bps) [UM; the manual's own Serial Monitor setting is 9600 Baud].

## Power and electrical limits
- The shield is powered by the Arduino's 5 V rail (Power LED on "when 5V power is supplied to the module") [UM]. Input range, regulator type and output current: **not stated** [UM].
- Module needs 3.0–3.6 V, 80 mA average, up to 170 mA during 802.11b transmit [VEN] — budget this on USB-powered Arduinos.
- ESP GPIO breakout: 3.3 V tolerant only [UM].
- Protection (over-current, reverse polarity, ESD): **not stated** [UM].

## Software support
- **Arduino library "Cytron ESPWiFi Shield" v3.0.2** — https://github.com/CytronTechnologies/CytronWiFiShield ; install via Library Manager ("Cytron ESPWiFi Shield") or ZIP [GH]. Based on SparkFun's ESP8266 AT library; maintainer Ng Beng Chet [GH].
- Headers: `CytronWiFiShield.h`, `CytronWiFiClient.h`, `CytronWiFiServer.h` (+ `SoftwareSerial.h`) [GH]. Global object `wifi` (class `ESP8266Class`, a `Stream`) [GH].
- `ESP8266Class` API [GH]: `begin(rx_pin=2, tx_pin=3)` / `begin(HardwareSerial&)`; `test()`, `reset()`, `firmwareVersion()` (AT+GMR), `echo()`, `setAutoConn()`, `showInfo()`, `setBaud()`; `getMode()`, `setMode(WIFI_STA | WIFI_AP | WIFI_BOTH)`, `connectAP(ssid[, pwd])`, `disconnectAP()`, `softAP(ssid, pwd, channel=1, enc=4)`, `SSID()`, `RSSI()`, `localIP()`, `config(ip, gateway, subnet)`, `softAPIP()`, `status()`, `updateStatus()`; `tcpConnect()`, `sslConnect()`, `tcpSend()`, `close()`, `setMux()`, `configureTCPServer(create=1, port=80)`, `setServerTimeout()`.
- `ESP8266Client` (Arduino `Client`): `connect(host|ip, port[, keepAlive])`, `secure_connect(...)`, `available/read/peek/flush/stop/connected`, `write()`, `status()` [GH].
- `ESP8266Server(port=80)`: `begin()`, `end()`, `available()`, `hasClient()`, `closeClient()`, `setTimeout()`, `arg()/argName()/args()/hasArg()`, `uri()`, `method()` (HTTP_GET/POST/…) [GH].
- Status codes: 2 = got IP, 3 = connected to server/client, 4 = disconnected, 5 = no Wi-Fi [GH]. Encryption constants: OPEN 0, WPA_PSK 2, WPA2_PSK 3, WPA_WPA2_PSK 4 [GH].
- Example `CytronWiFiDemo`: joins an AP, prints firmware version/IP, does an HTTP GET client test, then serves `/`, `/analog` (A0–A5 values) and `/info` on port 80 [UM][GH].
- **Firmware repo** https://github.com/CytronTechnologies/esp-at-binaries — `Cytron_ESP-12F_WROOM-02_AT_Firmware_V2.2.0.bin` is the one for this shield (the ESP-01S 1 MB build is not) [GH]. Tool: Espressif Flash Download Tool (Windows) [UM][GH].
- Advanced: "customise and upload their own firmware on this ESP8266 module and use it as an additional microcontroller" [UM] (no Cytron guide for that in the sources).

## Compatibility and accessories
- Arduino Uno, Arduino Duemilanove, Arduino Mega2560, Arduino Leonardo "and possibly other pin compatible main boards"; hardware section also names CT-UNO and CIKU [UM].
- Pin-pair restrictions per board: see the RX/TX table (D2/D3 is Uno-only; Mega needs D10/D11 or D12/D13; Leonardo D8/D9 or D10/D11) [UM].
- Stackable side headers for shields on top [UM].
- Related Cytron tutorials in the library README: "ESPresso Lite v2 with AT Firmware", "EasyMP3 shield with WiFly Remote" [GH].
- Price: RM52.40 (Cytron product page, read 2026-10-16) [PP].

## Common mistakes / troubleshooting
- **`Error talking to shield`** → jumpers not on the pins used in `wifi.begin()`, slide switch in FLASH, or Mega with D2/D3 [UM][GH].
- **No `OK` to `AT` in Serial Monitor** → jumpers not on USB, Arduino not held in reset / no empty sketch, wrong baud (9600 as shipped, 115200 right after flashing), or NL & CR not enabled [UM].
- **Firmware flash fails** → switch not in FLASH or ESP Reset not pressed after selecting FLASH; baud above 115200 [UM][GH].
- **microSD stops working** → UART jumpers on D10–D13, or something else wired to D4 [UM].
- **ESP GPIO pin damaged** → 5 V applied to the 3.3 V-only breakout [UM].
- **AT commands behave differently from old tutorials** → ESP-AT v2.x command set differs from NONOS-AT [GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Warranty | [UM] Rev2.0 V2.1 (Aug 2021) and [UM-R1]: 6 months | [PP] 12 months (read 2026-10-16) | UM is the higher source but older; product page is newer. Quote "12 months per the current product page" and flag |
| Module naming | [UM] Rev2.0: ESP-WROOM-02 | [UM-R1]: "ESP8266 module" (type not named) | [PP]: Rev2.0 uses WROOM-02 "instead of ESP8266-12" — Rev1.0 = ESP8266-12 |
| Flash size setting | [GH] flash tool "FLASH SIZE: 32Mbit" for the shield | [VEN] ESP-WROOM-02 has 2 MB (16 Mbit) flash | Follow Cytron's tool settings; actual module flash size on the shield — Needs verification |
| Default baud | [UM] "9600 kbps" | [UM] Serial Monitor "9600 Baud"; [GH] `#define baudRate 9600` | 9600 baud; "kbps" is a typo |
| Layout numbering of LEDs | [UM] 12 = RX LED, 13 = TX LED | [UM-R1] 12 = TX LED, 13 = RX LED | Cosmetic; both LEDs exist |

**Rev1.0 → Rev2.0 differences stated by the sources:** Rev2.0 manual names the ESP-WROOM-02 module and adds Section 8 "Firmware Installation" (Flash/Run switch procedure, Flash Download Tool, ESP-AT binaries); Rev1.0 manual has no firmware chapter. Pin options, jumpers, microSD on D4, LEDs, buttons, packing list, default 9600 8N1 and board list are identical in both manuals. Electrical differences between the two PCB revisions are only in the schematics, which were not readable here.

## Needs verification
- Board dimensions (drawing only); which ESP8266 GPIOs are on the 3.3 V breakout (9 digital + 1 analog, numbers not stated); the 3.3 V regulator part and current rating; whether the shield has level shifting on the UART lines (not stated).
- Actual flash size of the module fitted (2 MB per [VEN] vs 32 Mbit tool setting per [GH]); whether OTA is supported with the 2 MB build (README says only the 1 MB build "doesn't support OTA").
- Hardware changes between Rev1.0 and Rev2.0 (schematics not read).
- Which Arduino pins, if any, besides the selected UART pair and D4 are connected (not stated).
- Library v3.0.2 release date and whether the Library Manager entry is current.
- Whether Rev1.0 boards (ESP8266-12) can be upgraded to ESP-AT v2.2.0 with the Rev2.0 procedure — boards shipped since mid-Oct 2021 already carry Cytron_ESP_AT V2.2.0 [PP].

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Arduino Blynk Lesson 4 : Timer](https://my.cytron.io/tutorial/arduino-blynk-lesson-4-timer) — Tutorial, Beginner, 2018 (part of "Getting Started with Arduino and Blynk") [PP: tutorial]
- [Arduino Blynk Lesson 2 : Notification](https://my.cytron.io/tutorial/arduino-blynk-lesson-2-notification) — Tutorial, Beginner, 2018 (part of "Getting Started with Arduino and Blynk") [PP: tutorial]
- [Arduino Blynk Lesson 1: LED](https://my.cytron.io/tutorial/arduino-blynk-lesson-1-led) — Tutorial, Beginner, 2018 (part of "Getting Started with Arduino and Blynk") [PP: tutorial]
- [Arduino Blynk Lesson 3 : Servo](https://my.cytron.io/tutorial/arduino-blynk-lesson-3-servo) — Tutorial, Beginner, 2018 (part of "Getting Started with Arduino and Blynk") [PP: tutorial]

## Sources
- [UM] ESPWiFi Shield SHIELD-ESP-WIFI Rev2.0 User's Manual, V2.1, August 2021 — https://docs.google.com/document/d/1LFCe6MTNQh_0EBHRgc0f6n_hDLNUG8sFuM53oBJG8eE/view
- [UM-R1] ESPWiFi Shield SHIELD-ESP-WIFI User's Manual, V1.0, Nov 2015 — https://docs.google.com/document/d/1LAc8jJ9u6FDcugRvzn4Bewz6karp-EPfDKOmeD8yw84/view
- [PP] Product page (read by coordinator 2026-10-16) — https://my.cytron.io/p-cytron-esp8266-wifi-shield
- [DS-schematic, not read] Schematic Rev1.0 "SHIELD-ESP-WIFI_schematic.pdf" — https://drive.google.com/file/d/0BzFWfMiqqjyqMDVFNk5IeXlOa2M/view · Schematic Rev2.0 "SHIELD-ESP-WIFI-R2-Sch.pdf" — https://drive.google.com/file/d/0BzFWfMiqqjyqdHZ4blE1VHhiZ1U/view
- [VEN] ESP-WROOM-02 Datasheet v2.0, Nov 2016 — Drive link https://drive.google.com/file/d/0BzFWfMiqqjyqR1A5d0NhVC15XzA/view (not found); mirror used: https://cdn.sparkfun.com/assets/9/3/8/d/d/0c-esp-wroom-02-datasheet-en.pdf
- [GH] Firmware — https://github.com/CytronTechnologies/esp-at-binaries (README.md; Cytron_ESP-12F_WROOM-02_AT_Firmware_V2.2.0.bin)
- [GH] Library — https://github.com/CytronTechnologies/CytronWiFiShield (README.md, library.properties v3.0.2, keywords.txt, src/CytronWiFiShield.h/.cpp, src/CytronWiFiClient.h, src/CytronWiFiServer.h, examples/CytronWiFiDemo/CytronWiFiDemo.ino)
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
