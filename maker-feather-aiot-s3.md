# Maker Feather AIoT S3 — Verified Reference

| | |
|---|---|
| Product code | `MAKER-FEATHER-AIOT-S3` (basic, no headers); `MAKER-FEATHER-AIOT-S3-H` (pre-soldered female headers); parent listing `V-MAKER-FEATHER-AIOT-S3` [PP] |
| Family | Maker ESP32 family (ESP32 ecosystem) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Page matches the KB (ESP32-S3 WROOM-1 N8R8, 11 GPIO LEDs, buzzer GPIO12, button GPIO3, 3 Maker Ports, packing per variant) |
| Primary source | MAKER-FEATHER-AIOT-S3 Datasheet, Rev 1.1, January 2023 (Google Doc), plus schematic REV 1.0.0 dated 10/18/2022 — links under *Sources* |

**Authority rule:** Datasheet [DS] > Cytron design team [DT] > Cytron product page [PP] > Cytron GitHub [GH] > chip vendor docs [VEN] > third-party [3P].
Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
An ESP32-S3 development board in the Adafruit Feather form factor [DS][PP]. It adds onboard extras for teaching and IoT work:
- 11 buffered GPIO status LEDs, a WS2812B RGB LED, a piezo buzzer with a mute switch, and a user button [DS][PP]
- three JST-SH "Maker Ports" (Qwiic / STEMMA QT, and Grove through a conversion cable) [DS][PP]
- a switchable 3.3 V peripheral rail ("VPeripheral", VP) for saving power [DS][PP]
- a single-cell LiPo charger with protection [DS][PP]

It ships with the UF2 bootloader and CircuitPython preinstalled [DS][GH].

## Board facts
| Item | Value | Src |
|---|---|---|
| Module | Espressif ESP32-S3-WROOM-1-N8R8 | [DS] |
| Flash / PSRAM | 8 MB flash, 8 MB PSRAM | [DS] |
| PSRAM type | Octal (OPI), 80 MHz in the CircuitPython build; Arduino default is "OPI PSRAM" | [GH] |
| CPU | Dual-core Xtensa LX7, up to 240 MHz (Arduino default 240 MHz) | [GH][VEN] |
| Radio | Wi-Fi 2.4 GHz 802.11 b/g/n and Bluetooth 5 LE, from the module | [VEN] |
| USB | USB-C wired straight to ESP32-S3 native USB (D-/D+ = GPIO19/GPIO20). The schematic shows no USB-UART bridge chip | [DS] |
| USB VID / PID | VID 0x303A. PID 0x80F8 = Arduino core, 0x80F9 = CircuitPython, 0x80FA = UF2 bootloader | [DS][GH] |
| UF2 drive name | `MFAS3BOOT` | [DS][GH] |
| Buttons | RESET, BOOT (GPIO0), USER (GPIO3) | [DS] |
| Indicator LEDs | 3V3 power LED, VP power LED, charge LED (CHG), status LED (GPIO2), 11 GPIO LEDs, 1 RGB LED | [DS] |
| Header variants | Basic (no headers) or with pre-soldered female headers | [PP] |
| Package contents | 1 board + 3 Grove to JST-SH (Qwiic/STEMMA QT) cables (both variants) | [PP] |
| Warranty | 12 months | [PP] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- Page re-read: ESP32-S3-WROOM-1 **N8R8**; Feather form factor; 1-cell LiPo connector with overcharge/over-discharge protection; 11 GPIO status LEDs; piezo buzzer GPIO12; reset button; user button GPIO3; 1 RGB LED; 3 Maker Ports (Qwiic / STEMMA QT / Grove via cable); Arduino, CircuitPython, MicroPython, ESP-IDF; 2 Maker Ports on a switchable Vperipheral rail for sleep [PP].
- **Packing:** basic — board (no headers) + 3x Grove-to-JST-SH cable; with headers — board (female headers pre-soldered) + 3x Grove-to-JST-SH cable [PP]. Also sold in the Cytron IoT Kit (10 example projects) [PP].
- **Resources:** datasheet, schematic, pinout diagram, CAD, ESP32-S3-WROOM-1 datasheet, Getting Started with Arduino IDE and with CircuitPython (Cytron tutorials), circuitpython.org board page [PP].

## Onboard peripherals and pins
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| Status LED (user) | GPIO2 | Active high. Also the CircuitPython / UF2 status LED. Arduino `LED_BUILTIN` | [DS][GH] |
| RGB LED WS2812B | GPIO46 | Powered from VP. Arduino `RGB_BUILTIN`; CircuitPython `board.NEOPIXEL` | [DS][GH] |
| Piezo buzzer (passive) | GPIO12 | Driven through a MOSFET (Q15) from VP, via the mute switch S4 | [DS][GH] |
| User button | GPIO3 | 10 kΩ pull-up to 3V3; pressed = LOW | [DS] |
| BOOT button | GPIO0 | Hold during reset to enter the ROM bootloader | [DS] |
| VP enable (VPeripheral) | GPIO11 | HIGH = VP on. Arduino `VP_EN`; CircuitPython `board.VP_EN` | [DS][GH] |
| VIN sense | GPIO13 (A12) | V_ADC = 0.6 × VIN, where VIN = the higher of VUSB and VBATT (100 k / 150 k divider). Arduino `VBATT`/`VOLTAGE_MONITOR` | [DS][GH] |
| GPIO LEDs (11) | GPIO14, 15 (TX), 16 (RX), 21, 38, 39, 40, 41 (SCL), 42 (SDA), 47, 48 | LED is lit when the pin is HIGH. Each is buffered by a BSS138 MOSFET (3.3 MΩ gate pull-down), and the LED anodes are on VP | [DS] |
| Maker Port H #1 (JP4) | GND, VP, SDA=GPIO42, SCL=GPIO41 | Horizontal port, powered by VP. Default I2C bus | [DS] |
| Maker Port H #2 (JP6) | GND, VP, pin3=GPIO4 (A4), pin4=GPIO7 (A5) | Horizontal port, powered by VP | [DS] |
| Maker Port V (JP5) | GND, 3V3, pin3=GPIO6 (A2), pin4=GPIO5 (A3) | Vertical port, always-on 3V3 | [DS] |
| Double-reset detect | GPIO1 | RC network (1 µF / 1 MΩ) used by TinyUF2/CircuitPython. Not broken out | [DS][GH] |
| Debug UART TX | GPIO43 (U0TXD) | On the header as "DBG / DEBUG_TX0" | [DS] |
| Default I2C | SDA 42, SCL 41 | `board.I2C()` / `STEMMA_I2C()` | [GH][DS] |
| Default SPI | SCK 17, MOSI 8, MISO 18, SS 7 | | [GH][DS] |
| Default UART | TX 15, RX 16 | | [GH][DS] |

**Feather header pinout** [DS pinout diagram + schematic]
- Left side (16 pins, top to bottom): RST · 3V3 · **VP** (VPeripheral 3V3, in the Feather "AREF" position) · GND · A0/D10 · A1/D9 · A2/D6 · A3/D5 · A4/D4 · A5/D7 · SCK/D17 (A6) · MOSI/D8 (A7) · MISO/D18 (A8) · RX/D16 (A9) · TX/D15 (A10) · DBG (GPIO43).
- Right side (12 pins): BAT · EN · USB (VBUS) · D14 (A11) · D21 · D47 · D48 · D38 · D39 · D40 · SCL/D41 · SDA/D42.
- The `Dn` number always equals the GPIO number. The `An` number does **not** (A0 = GPIO10, A1 = GPIO9, A2 = GPIO6, A3 = GPIO5, A4 = GPIO4, A5 = GPIO7) [DS][GH].
- Touch pins: T4–T10 and T14, on GPIO4–10 and GPIO14 [GH][DS].

## Pin rules and gotchas (for code and tutorials)
- **Turn VP on first.** The GPIO LEDs, RGB LED, buzzer and both horizontal Maker Ports run from VP. Set GPIO11 HIGH before using them [DS].
  - CircuitPython and the Arduino core turn VP on automatically (`reset_board()` / `initVariant()`) [DS][GH].
  - **ESP-IDF and generic MicroPython do not**, so drive GPIO11 HIGH yourself [DS].
- **ESP32-S3 strapping pins are GPIO0, GPIO3, GPIO45 and GPIO46** [VEN].
  - GPIO0 = BOOT button.
  - GPIO3 = user button (it selects the JTAG signal source at reset; it only matters if eFuses are set).
  - GPIO45 = VDD_SPI voltage select. It is not connected on this board [DS].
  - GPIO46 = RGB LED (it controls ROM message printing at reset).
  - Do not add external pull-ups or pull-downs to these pins.
- **GPIO19/20 are native USB D-/D+.** They are not broken out. Do not reassign them, or USB serial and upload stop working [DS][VEN].
- **GPIO35, 36 and 37 are used by the octal PSRAM** (schematic note "Be careful"). They are not broken out [DS][VEN]. GPIO26–32 (flash/PSRAM bus) are also internal [VEN].
- **ADC2 and Wi-Fi:** ESP32-S3 ADC1 = GPIO1–10 and ADC2 = GPIO11–20. ADC2 is shared with Wi-Fi, and reads may fail or time out while Wi-Fi is active [VEN].
  - Safe with Wi-Fi: A0–A5 and A7 (GPIO4–10).
  - **ADC2:** A6 (17), A8 (18), A9 (16), A10 (15), A11 (14) and **A12 / VIN sense (GPIO13)**. Read battery voltage before starting Wi-Fi, or expect failures. This is derived from the vendor rule; see *Needs verification*.
- GPIO43 (DBG) carries the ROM and bootloader log at boot [DS][VEN]. Avoid it for inputs that need to be quiet at boot.
- The CircuitPython build pulls most broken-out pins down at reset. GPIO13 is left floating because it is the voltage monitor [GH].
- Digital limits per pin [DS]:
  - VIH 2.5–3.6 V, VIL −0.3–0.8 V. **Inputs are not 5 V tolerant** (3.6 V max).
  - Source up to 40 mA, sink up to 28 mA.
  - Internal pull-up/pull-down ≈45 kΩ.
- Remapping: PWM, UART, SPI and I2C can be routed to any GPIO through the GPIO matrix [DS pinout note].

## Power and electrical limits
| Parameter | Value | Src |
|---|---|---|
| USB input (VUSB) | 4.5–5.5 VDC | [DS] |
| LiPo input (VBAT) | 3.3–4.2 VDC, single-cell LiPo / Li-ion only | [DS] |
| 3V3 max current (including onboard use) | 1000 mA | [DS] |
| 3V3 regulator | SY8088AAC synchronous buck (U2) | [DS] schematic |
| Power path | VBUS through a Schottky diode (15MQ040N) and VBAT through a P-MOSFET (IRLML6402). The regulator runs from whichever is higher | [DS] schematic |
| Charger | MCP73831T-2ACI/OT, charges from USB. CHG LED is on while charging | [DS] |
| Charge current | ≈500 mA, **derived**: R_PROG = 2 kΩ and the MCP73831 formula I = 1000 V / R_PROG. Not stated as a spec | [DS] schematic + [VEN] |
| Battery protection | CT2105 protection IC: overcharge and over-discharge. If the board will not power on from a battery, charge it over USB to reset the protection | [DS] |
| VP rail | 3V3 switched by a P-MOSFET (Q2) driven from GPIO11 through Q3. VP current is a share of the 1000 mA 3V3 budget | [DS] |
| EN pin | Wired to the regulator EN pin. Pulling it LOW shuts off 3V3 (Feather convention) | [DS] schematic |
| 3V3 power LED | Goes through solder jumper JP2, which can be cut to save power | [DS] schematic |
| Operating temperature | −20 to 65 °C | [DS] |
| Analog input range | −0.3 to 3.6 V absolute | [DS] |

## Software support
- **Arduino (Espressif arduino-esp32 core)** [GH]:
  - Board name "Cytron Maker Feather AIoT S3", FQBN `esp32:esp32:cytron_maker_feather_aiot_s3`.
  - Defaults: USB Mode = USB-OTG (TinyUSB), USB CDC On Boot = Enabled, Upload Mode = USB-OTG CDC (TinyUSB) with 1200-bps touch reset, PSRAM = OPI, Partition = "TinyUF2 8MB (2MB APP/3.7MB FFAT)", Flash 8 MB.
  - Variant macros: `LED_BUILTIN` 2, `RGB_BUILTIN`, `BUZZER` 12, `VP_EN` 11, `BUTTON` 3, `BOOT` 0, `VBATT` / `VOLTAGE_MONITOR` / `BAT_VOLT_PIN` 13.
- **CircuitPython** [GH]:
  - Board id `cytron_maker_feather_aiot_s3`; preinstalled at the factory [DS].
  - `board` names: LED, BUTTON, BUZZER, VP_EN, VOLTAGE_MONITOR/VBATT/VIN, NEOPIXEL/RGB, BOOT, A0–A12, T4–T14, D0–D48 (exposed ones), I2C/STEMMA_I2C, SPI, UART.
  - The `neopixel` library is frozen into the firmware.
- **MicroPython:** Cytron lists it as supported [PP][DS]. There is **no board-specific build** on micropython.org (checked 2026-10-16); see *Needs verification* for which generic build to use.
- **ESP-IDF:** supported [PP]. VP must be enabled manually [DS].
- **Bootloaders** [DS]:
  - **UF2 (TinyUF2):** double-press RESET. The RGB LED turns green, the status LED blinks slowly, and the `MFAS3BOOT` drive appears. Drag a `.uf2` file onto it.
  - **ROM bootloader:** hold BOOT, press and release RESET, then release BOOT. A new COM port appears; flash with esptool or WebSerial esptool. **Flashing through the ROM bootloader overwrites the UF2 bootloader.**
  - **Restoring TinyUF2:** use `tinyuf2-cytron_maker_feather_aiot_s3-*.zip` and flash bootloader.bin @0x0, partition-table.bin @0x8000, ota_data_initial.bin @0xE000 and tinyuf2.bin @0x410000 (erasing first is recommended) [DS].
  - Installing TinyUF2 erases the board, including CIRCUITPY files [GH circuitpython.org].

## Compatibility and accessories
- Adafruit Feather footprint and FeatherWing add-ons [DS][PP]. The third left-header pin is VP, not AREF, so check any Wing that uses AREF [DS].
- Maker Ports are JST-SH 4-pin: Qwiic / STEMMA QT direct, Grove through a conversion cable (3 included) [DS][PP].
- Sold within the Cytron IoT Kit and the "Maker Feather S3 IoT Bundles" listing [PP].
- This is a different product from the 2026 classic-ESP32 "Maker ESP32" (`MAKER-ESP32`). Do not mix their pin maps.

## Common mistakes in older tutorials / migration notes
- **Using `An` labels as GPIO numbers.** A0 is GPIO10, not GPIO0. In Arduino, use the `A0` constant or the `Dn`/GPIO number [DS][GH].
- **ESP-IDF or generic MicroPython code with nothing working on the LEDs, buzzer, RGB LED or horizontal Maker Ports.** VP (GPIO11) was never set HIGH [DS].
- **Uploading an Arduino sketch with the wrong board selected** (e.g. "ESP32S3 Dev Module") can corrupt or overwrite the UF2 bootloader. Recover through the ROM bootloader [DS].
- **Reading battery voltage on A12 while Wi-Fi is running.** GPIO13 is ADC2 [VEN].
- **Assuming a USB-UART chip** (CP210x/CH340 drivers, auto-reset over DTR/RTS). The USB is native, and the COM port changes between app, ROM bootloader and UF2 mode (different PIDs) [DS].
- With USB CDC On Boot disabled, `Serial` prints nothing over USB [GH, inferred from the menu defaults].
- The Cytron CircuitPython tutorial URL slug misspells "circuitpyhton". Copy that link exactly; do not correct it [GH circuitpython.org].
- `RGB_BRIGHTNESS` is defined twice in the Arduino variant (64 and 65), which may cause a redefinition warning. It is harmless [GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Cables in box | [PP]: 3× Grove-to-JST-SH | [3P] The Pi Hut package list: 2 | [PP] wins: 3 |
| Strapping pins | [VEN]: GPIO0, 3, 45, 46 | [3P] espboards.dev also flags GPIO9, 10, 11, 12, 14, 41, 42 as "strapping" | [VEN] wins; the espboards list is wrong |
| GPIO46 direction | [DS]/[GH]: drives the WS2812B (output) | [3P] espboards.dev: "input-only" | [DS] wins; on the S3 it is not input-only |
| Exposed pins / DAC | [DS]: GPIO1 not broken out; ESP32-S3 has no DAC [VEN] | [3P] cirkitdesigner: GPIO1 on header, "DAC1, DAC2" | [DS]/[VEN] win; ignore cirkitdesigner |
| Arduino flash mode | [GH] boards.txt: build.flash_mode=dio, boot=qio, menu default QIO 80 MHz | [3P] espboards: "DIO" | Use the [GH] menu default; not material for tutorials |

## Needs verification
- Charge current: ≈500 mA is derived from the schematic resistor value, not a published spec. Confirm with [DT].
- Board dimensions 58.4 × 22.9 mm (Pi Hut: 58.42 × 22.86 mm) [3P]. The datasheet gives a dimension drawing only (image), which was not read.
- Battery connector type: "JST-PH 2.0" appears only on [3P] espboards.dev.
- Whether I2C pull-up resistors are fitted on SDA/SCL (GPIO41/42) or on the JP6 port pins. Not seen in the schematic sections read.
- MicroPython: which generic image Cytron recommends (likely `ESP32_GENERIC_S3`, SPIRAM_OCT variant, given octal PSRAM). Not confirmed by any Cytron source.
- Whether the first Arduino upload onto a factory board (running CircuitPython) works through 1200-bps touch, or needs BOOT+RESET. The Cytron Arduino tutorial could not be fetched.
- GPIO44 (U0RXD) connection and current draw in each mode (deep sleep, VP off) are not documented.
- The ADC2 / Wi-Fi impact on GPIO13 battery reads on this board is inferred from the [VEN] rule, not tested.
- Pin maps were transcribed by eye from the pinout image and schematic (my.cytron.io blocked to scripts) — spot-check Maker Port pin order and GPIO LED list on a real board.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Getting Started with Maker Feather AIoT S3 (Arduino IDE)](https://my.cytron.io/tutorial/getting-started-with-Maker-Feather-AIoT-S3-(ArduinoIDE)) — Tutorial, Beginner, 2022 [PP: tutorial]
- [Getting Started with Maker Feather AIoT S3 using CircuitPython](https://my.cytron.io/tutorial/get-started-with-maker-feather-aIot-s3-using-circuitpyhton) — Tutorial, Beginner, 2022 [PP: tutorial]
- [Maker Feather AIOT S3 Data Logging To Firebase](https://my.cytron.io/tutorial/maker-feather-aiot-s3-data-logging-to-firebase) — Tutorial, Beginner, 2023 [PP: tutorial]
- [How To Control LED with Blynk Using Maker Feather AIOT S3](https://my.cytron.io/tutorial/how-to-control-led-with-blynk-using-maker-feather-aiot-s3) — Tutorial, Beginner, 2023 [PP: tutorial]
- [Arducam Mega 3MP with Maker Feather AIOT S3](https://my.cytron.io/tutorial/arducam-mega-3mp-with-maker-feather-aiot-s3) — Tutorial, Beginner, 2023 [PP: tutorial]
- [Temperature And Humidity Data From SHT40 To Thingspeak With Maker Feather AIOT S3](https://my.cytron.io/tutorial/temperature-and-humidity-data-from-sht40-to-thingspeak-with-maker-feather-aiot-s3) — Tutorial, Beginner, 2023 [PP: tutorial]
- [Environment Data Monitoring With Maker Feather AIOT S3 and Adafruit IO](https://my.cytron.io/tutorial/environment-data-monitoring-with-maker-feather-aiot-S3-and-adafruit-io) — Tutorial, Beginner, 2023 [PP: tutorial]

## Sources
- [DS] Maker Feather AIoT S3 Datasheet Rev 1.1, Jan 2023 — https://docs.google.com/document/d/1vVYSdn84I8Hvi9SWHU54lhH_vWlhD3mwJ6pcSyLNGcE/edit
- [DS] MAKER-FEATHER-AIOT-S3 Schematic.pdf (REV 1.0.0, 10/18/2022) — https://drive.google.com/file/d/1s7VMlzyGdPTzRH8j-vfVWBLO983qKnwl/view
- [DS] Pinout diagram — https://static.cytron.io/image/catalog/products/V-MAKER-FEATHER-AIOT-S3/MAKER-FEATHER-AIOT-S3%20Pinout.png (also https://docs.google.com/drawings/d/e/2PACX-1vSd5MxXd2huv0QwrVJ2ijKLdzdCjQ__A8QhtFlWPrrWygAon_1teaNJq9zFrGCh_PumrNcDhEta-k8c/pub?w=3162&h=2502)
- [PP] https://my.cytron.io/p-v-maker-feather-aiot-s3-simplifying-aiot-with-esp32 ; https://my.cytron.io/p-maker-feather-aiot-s3 ; https://my.cytron.io/p-maker-feather-aiot-s3-presoldered-headers
- [GH] https://github.com/adafruit/circuitpython/tree/main/ports/espressif/boards/cytron_maker_feather_aiot_s3 (pins.c, mpconfigboard.h/.mk, board.c)
- [GH] https://github.com/espressif/arduino-esp32/tree/master/variants/cytron_maker_feather_aiot_s3 (pins_arduino.h, variant.cpp) and https://github.com/espressif/arduino-esp32/blob/master/boards.txt
- [GH] https://github.com/adafruit/tinyuf2/tree/master/ports/espressif/boards/cytron_maker_feather_aiot_s3
- [GH] https://circuitpython.org/board/cytron_maker_feather_aiot_s3/ (source: https://github.com/adafruit/circuitpython-org/blob/main/_board/cytron_maker_feather_aiot_s3.md)
- [VEN] https://docs.espressif.com/projects/esp-idf/en/stable/esp32s3/api-reference/peripherals/adc/adc_oneshot.html ; ESP32-S3-WROOM-1 datasheet (linked from [PP])
- [3P] https://thepihut.com/products/maker-feather-aiot-s3 ; https://www.cnx-software.com/2023/01/10/maker-feather-aiot-s3-esp32-s3-board-circuitpython-arduino/ ; https://www.espboards.dev/esp32/cytron-maker-feather-aiot-s3/ ; https://docs.cirkitdesigner.com/component/03c3256e-c76c-bf89-ec38-ef23a162afe1/cytron-maker-feather-aiot-s3 ; https://www.micropython.org/download
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
