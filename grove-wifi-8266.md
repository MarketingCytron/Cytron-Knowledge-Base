# Grove WiFi 8266 - IoT for micro:bit and beyond — Verified Reference

| | |
|---|---|
| Product code | `GRV-WIFI-8266` (datasheet figure/table captions [DS]; product page [PP]) |
| Family | Sensors and modules |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **GROVE WIFI 8266 Datasheet, Rev 1.0, August 2021** (public Google Doc linked from the product page): https://docs.google.com/document/d/1ub3WuRrp1F8QijoHCDjOez6SC1mtG5pQglhiPdeB12k/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: no user manual and no [DT] confirmation exist for this product. The datasheet is a public Google Doc linked from the public product page, so it may go in the public KB edition. [PP] facts (code, price, stock, warranty, linked documents) come from the coordinator's read of the product page on 2026-10-16; the page itself was not fetched here. [GH] = three Cytron repositories (pxt-esp8266, esp-at-binaries, MAKER-PI-PICO IoT examples). [3P] = RobotShop and The Pi Hut, cross-check only. Espressif and Ai-Thinker documents [VEN] were not read. The datasheet is short: it gives board functions, electrical limits and a dimension drawing; firmware, baud rate, flash size and supported boards come from [GH] and [3P], and are tagged as such.

## What it is
A Wi-Fi module on a Grove-connector board. It carries an Ai-Thinker ESP-12F module (ESP8266) and talks to a host controller over a 4-pin Grove port (GND, VCC, RX, TX), i.e. a UART serial link [DS]. It has a reset button, a boot button for firmware update, a power LED, and all ESP-12F pins broken out (pinout printed on the bottom of the PCB) [DS]. It ships with Cytron's build of the Espressif ESP-AT (AT-command) firmware, so the host sends AT commands over serial instead of running Wi-Fi code itself [GH]. Cytron provides a MakeCode extension for micro:bit and CircuitPython examples for Raspberry Pi Pico / Maker Pi RP2040 [GH].
Positioning (marketing, not spec): product name "IoT for micro:bit and beyond" [PP].

## Specifications
Every row of the datasheet "2. SPECIFICATIONS" table (Table 2), exact numbers and units, plus the board-function table (Table 1).

| Item | Value | Src |
|---|---|---|
| Power Input Voltage (VCC) | 3.0 min, 6.0 max V | [DS] |
| Digital Input Voltage (Rx & GPIOs), Low Level | −0.3 min, 0.8 max V | [DS] |
| Digital Input Voltage (Rx & GPIOs), High Level | 2.5 min, 3.6 max V | [DS] |
| Digital Output Voltage (Tx & GPIOs), Low Level | 0 min, 0.4 max V | [DS] |
| Digital Output Voltage (Tx & GPIOs), High Level | 2.6 min, 3.3 max V | [DS] |
| Operating Temperature | −20 min, 85 max °C | [DS] |
| Wi-Fi module | Ai-Thinker ESP-12F WiFi module, "Powered by the ESP8266" | [DS] |
| Grove Port | Connect to the host controller: GND, VCC (Positive Supply, 3V–6V), RX (Serial Rx pin for ESP8266, connect to host's Tx), TX (Serial Tx pin for ESP8266, connect to host's Rx) | [DS] |
| Reset Button | Press to reset the ESP8266 | [DS] |
| Boot Button | Press and hold while resetting the ESP8266 to enter bootloader mode; used to update the firmware or program the ESP8266 | [DS] |
| Power LED | On when powered up | [DS] |
| ESP-12F Pins Breakout | Breakout of the pins for the ESP-12F module; refer to the bottom of the PCB for pinout | [DS] |
| Firmware (preloaded) | Cytron_ESP-12F_WROOM-02_AT_Firmware, file version **V2.2.0**, compiled from Espressif ESP-AT source; "preloaded in … Cytron ESP8266 WiFi Grove Module" | [GH esp-at-binaries] |
| AT UART pins (Cytron firmware) | AT command/response on UART0 GPIO3 (RX) / GPIO1 (TX) — same pins as firmware update; log output on UART1 GPIO2 (TX) | [GH esp-at-binaries] |
| UART baud used by Cytron software | 115200 (MakeCode example `BaudRate115200`; CircuitPython `ESP_ATcontrol(uart, 115200)`) | [GH] |
| Dimensions | Datasheet section "3. DIMENSION" is a drawing only (Figure 2); no values in the text | [DS] |
| Flash size, RF (802.11 b/g/n, 2.4 GHz), antenna, weight, current draw | Not stated by the datasheet; see Needs verification for [3P] figures | [DS] |

## Interfaces, terminals and pin mapping
- **Grove port (4 pins)** [DS]: GND · VCC (3–6 V) · RX (ESP8266 serial in — to host TX) · TX (ESP8266 serial out — to host RX). Physical pin order on the connector is in the datasheet figure only — see Needs verification.
- **ESP-12F pin breakout**: all module pins broken out; the pinout is printed on the bottom of the PCB [DS]. Pin names/positions are not listed in the datasheet text.
- **Reset button** and **Boot button** (hold Boot while resetting → bootloader mode for flashing) [DS].
- **Host pins used by Cytron software** [GH]:
  - micro:bit (MakeCode): default `esp8266.init(SerialPin.P16, SerialPin.P15, BaudRate.BaudRate115200)` — Tx = P16, Rx = P15.
  - Raspberry Pi Pico / Maker Pi RP2040 (CircuitPython): `TX = board.GP16`, `RX = board.GP17`, `busio.UART(TX, RX, receiver_buffer_size=2048)`, 115200.

## Rules and gotchas (for code, wiring and tutorials)
- **Cross the serial lines.** Module RX goes to the host's TX and module TX to the host's RX [DS]. "No response" is most often RX/TX straight-through.
- **3.3 V logic on a 3–6 V supply.** VCC may be 3–6 V, but the RX/GPIO input high level is 2.5–3.6 V max and the TX output high is 2.6–3.3 V [DS]. Do not drive RX from a 5 V TX pin without level shifting (derived from the 3.6 V input limit). The datasheet does not say the Grove RX pin is 5 V-tolerant.
- **It is an AT-command modem, not a programmable board (as shipped).** The host sends Espressif ESP-AT commands over UART [GH]. ESP-AT v2.x commands "are not fully compatible with the legacy [NONOS-AT v1.7.x] AT firmware" [GH esp-at-binaries] — old ESP8266 AT tutorials and libraries written for v1.x may not work.
- **Cytron's firmware keeps the AT UART on GPIO1/GPIO3.** Stock Espressif ESP-AT ≥ v2.0.0 moved AT to GPIO13/GPIO15; Cytron recompiled it so AT runs on GPIO3 (RX) / GPIO1 (TX), "the rest of the features are exactly the same with Espressif's firmware" [GH]. If you reflash with stock Espressif binaries the Grove RX/TX will stop carrying AT traffic.
- **Baud 115200.** Both Cytron code paths use 115200 [GH]; the Pico IoT README says to use 115200 "instead of 9600 (Old firmware)" [GH]. micro:bit MakeCode init also calls `AT+RESTORE` then `ATE0` and waits for "ready" (5 s timeout) [GH].
- **Use the Cytron ESP-AT binary for reflashing** (Cytron_ESP-12F_WROOM-02_AT_Firmware, for ESP8266 with 2 MB flash or above; target address 0x0; Flash Download Tool in "Developer" mode; baud 115200 or below) [GH]. The README's step-by-step procedures cover the ESP-01S and the ESP8266 WiFi Shield; there is no Grove-module-specific procedure — use the Boot button [DS] with a USB-UART adapter (adapter/wiring not stated by Cytron; see Needs verification).
- **ThingSpeak rate limit:** the MakeCode block says data "can only be uploaded every 15 seconds"; the CircuitPython example sends every 20 s [GH].
- **Telegram uses SSL on port 443** (`AT+CIPSTART="SSL","api.telegram.org",443`), ThingSpeak uses TCP port 80 [GH] — so the module must have a firmware with SSL support (it does with ESP-AT v2.2.0 [GH]).
- Operating temperature −20 to 85 °C [DS].

## Power and electrical limits
- VCC 3.0–6.0 V [DS].
- Digital input (Rx & GPIOs): low −0.3 to 0.8 V; high 2.5 to 3.6 V [DS].
- Digital output (Tx & GPIOs): low 0 to 0.4 V; high 2.6 to 3.3 V [DS].
- Operating temperature −20 to 85 °C [DS].
- Supply current / peak transmit current: **not stated** [DS] — do not quote a figure; do not assume a micro:bit's own 3 V pin can supply it without checking (see Needs verification).

## Software support
- **MakeCode extension for micro:bit** [GH] https://github.com/CytronTechnologies/pxt-esp8266 — package name `pxt-esp8266`, version 2.0.1, block category "ESP8266 WiFi", `supportedTargets: microbit`. README: "ESP8266 AT Mode Extension for Microsoft MakeCode … provides the driver for ESP8266 WiFi Grove Module. This extension is tested with Espressif ESP-AT Firmware v2.2.0." Blocks: initialize (Tx/Rx/baud), ESP8266 initialized, connect to WiFi, WiFi connected, Upload data to ThingSpeak (8 fields), Blynk read/write, Internet time (SNTP, timezone, year/month/day/hour/minute/second), and a Telegram "send message" block (`telegram.ts` is in the package even though the README does not list it).
- **CircuitPython (Raspberry Pi Pico / Maker Pi RP2040)** [GH] https://github.com/CytronTechnologies/MAKER-PI-PICO/tree/main/Example%20Code/CircuitPython/IoT — uses Adafruit libraries `adafruit_espatcontrol`, `adafruit_requests`, `adafruit_minimqtt`, `adafruit_io` (included in the repo's lib folder). Requires "ESP-AT Firmware v2.2.0 and above". Examples: Adafruit IO, Blynk, Simple Test (scan, connect, ping 8.8.8.8), Telegram, Thingspeak.
- **ESP-AT firmware binaries** [GH] https://github.com/CytronTechnologies/esp-at-binaries — `Cytron_ESP-12F_WROOM-02_AT_Firmware_V2.2.0.bin` (for this module) and `Cytron_ESP-01S_AT_Firmware_V2.2.0.bin` (1 MB flash, not for this module). AT command reference: Espressif ESP-AT User Guide release v2.2.0.0 for ESP8266 [GH link].
- Arduino / MicroPython libraries from Cytron: **not stated** by any Cytron source read.

## Compatibility and accessories
- Datasheet names no host boards; any host with a 3.3 V-level UART and a Grove cable can use it [DS].
- Cytron software targets: **micro:bit** (MakeCode, PXT target microbit) [GH]; **Maker Pi Pico** and **Maker Pi RP2040** (CircuitPython IoT examples: "Cytron Maker Pi Pico or Cytron Maker Pi RP2040") [GH]. The Maker Pi RP2040 product page Q&A suggests this module for Wi-Fi via a Grove port [PP, from KB entry maker-pi-rp2040.md].
- CAD files: Google Drive folder linked from the product page [PP] https://drive.google.com/drive/folders/1kfOuKsVLOXPVkPTSarWBtlN2XdDNWKZJ (not opened).

## Common mistakes / troubleshooting
- **Init block shows a sad face / `isESP8266Initialized()` false:** RX/TX swapped, wrong micro:bit pins in the init block (default Tx P16 / Rx P15), or baud not 115200 [DS][GH].
- **Works on a 3.3 V board, fails on a 5 V board:** input high max is 3.6 V [DS]; level-shift the host TX line.
- **Old AT-command sketches fail:** firmware is ESP-AT v2.2.0; legacy NONOS-AT v1.x commands are not fully compatible [GH].
- **No AT response after reflashing with Espressif's own binary:** stock ESP-AT v2 uses GPIO13/15 for AT; use Cytron's binary to keep AT on GPIO1/3 [GH].
- **ThingSpeak update rejected:** sending faster than every 15 s [GH].
- **Module resets or drops Wi-Fi under load:** supply current is not stated [DS]; check the host's 3V3/5V rail capacity (see Needs verification).
- **Boot mode by accident:** holding Boot while resetting enters the bootloader [DS]; release Boot and reset again.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Product name | [DS] "GROVE WIFI 8266" | [PP] "Grove WiFi 8266 - IoT for micro:bit and beyond"; [3P] RobotShop/The Pi Hut "Grove WiFi 8266 IoT for micro:bit & Beyond" / "… micro:bit, Pico & More" | Use the [DS]/[PP] Cytron names; reseller variants are aliases only |
| Firmware version | [DS] not stated | [GH] file name V2.2.0, "tested with ESP-AT v2.2.0"; [3P] "preloaded with ESP-AT v2.2.0" | No conflict; [GH] is the highest source that states it — quote as "ships with Cytron's ESP-AT v2.2.0 build [GH]" |
| Supported boards | [DS] none named | [GH] micro:bit, Maker Pi Pico, Maker Pi RP2040; [3P] The Pi Hut adds micro:bit V1 & V2, Pico W, Pico 2 | State only [GH] boards as supported; Pico W / Pico 2 / micro:bit version split go to Needs verification |
| MakeCode Telegram support | [GH] README does not list Telegram | [GH] pxt.json includes `telegram.ts` with a "send message to Telegram" block | Both are Cytron GitHub; the code exists — say the extension has a Telegram block, README omits it |

No numeric disagreement was found: supply 3–6 V matches between [DS] and [3P]; 115200 baud matches between both [GH] code bases and [3P].

## Needs verification
- **Dimensions and weight.** Datasheet Figure 2 is a drawing only. Confirm from the drawing or the CAD folder.
- **Grove pin order** (GND/VCC/RX/TX left-to-right) and **which Grove signal pins map to which micro:bit / Pico pins through EDU:BIT or Maker Pi Pico Grove ports** — the datasheet only gives the four signal names.
- **Supply / peak current** — not stated by any Cytron source; the ESP8266 transmit peak is a [VEN] figure not read here. Needed before saying "powered from micro:bit 3V pin".
- **Flash size.** [3P] The Pi Hut: 32 Mbit SPI flash; [GH] says the firmware is for "flash size 2MB or above" and the Flash Download Tool setting for the WiFi Shield is 32 Mbit — not stated for the Grove module.
- **RF spec.** [3P] 802.11 b/g/n, 2.4 GHz — not stated by Cytron; antenna type not stated.
- **micro:bit V1 vs V2 support.** [GH] only says PXT target "microbit"; [3P] The Pi Hut says V1 and V2.
- **Raspberry Pi Pico W / Pico 2 / Pico 2 W** — [3P] The Pi Hut lists Pico W and Pico 2; no Cytron source read says so.
- **Firmware-update procedure for this module** (USB-UART adapter wiring, Flash Download Tool "FLASH SIZE" setting) — [GH] README only documents ESP-01S and the WiFi Shield.
- **Whether the Grove RX input is 5 V tolerant** — the datasheet limit (3.6 V) says no; confirm with the design team before any 5 V-host tutorial.
- **Prices elsewhere.** [3P] RobotShop USD 6.60; The Pi Hut £7.10 incl. VAT (sale). Cytron RM27.72 [PP].
- Product page text beyond the facts the coordinator supplied (page not read here).
- The RobotShop PDF mirror of the datasheet (https://cdn.robotshop.com/media/c/cyt/rb-cyt-321/pdf/grove-wifi-8266-iot-microbit--beyond-datasheet.pdf) could not be downloaded (proxy refused), so its revision was not compared.

## Sources
- [DS] GROVE WIFI 8266 Datasheet, Rev 1.0, August 2021 (public Google Doc) — https://docs.google.com/document/d/1ub3WuRrp1F8QijoHCDjOez6SC1mtG5pQglhiPdeB12k/edit
- [PP] https://my.cytron.io/p-grove-wifi-8266-iot-for-microbit-and-beyond (read by the coordinator 2026-10-16: RM27.72, in stock 173, warranty 12 months; linked documents: datasheet, MakeCode extension, CircuitPython examples, ESP-AT firmware, CAD)
- [GH] MakeCode extension — https://github.com/CytronTechnologies/pxt-esp8266 (README.md, pxt.json, main.ts, thingspeak.ts, sntp.ts, telegram.ts)
- [GH] ESP-AT firmware binaries — https://github.com/CytronTechnologies/esp-at-binaries (README.md; files Cytron_ESP-12F_WROOM-02_AT_Firmware_V2.2.0.bin, Cytron_ESP-01S_AT_Firmware_V2.2.0.bin)
- [GH] CircuitPython IoT examples — https://github.com/CytronTechnologies/MAKER-PI-PICO/tree/main/Example%20Code/CircuitPython/IoT (README.md, thingspeak.py, telegram.py)
- [PP link, not opened] CAD — https://drive.google.com/drive/folders/1kfOuKsVLOXPVkPTSarWBtlN2XdDNWKZJ
- [PP] /home/claude/kb/maker-pi-rp2040.md (product page Q&A suggests Grove WiFi 8266)
- [3P] https://www.robotshop.com/products/grove-wifi-8266-iot-microbit-beyond · https://thepihut.com/collections/pico/products/grove-wifi-8266-iot-for-micro-bit-pico-more
