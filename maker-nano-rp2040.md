# Maker Nano RP2040 — Verified Reference

| | |
|---|---|
| Product code | `MAKER-NANO-RP2040` (the name used throughout the datasheet) |
| Family | RP2040 / RP2350 boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Datasheet "MAKER-NANO-RP2040 – Simplifying Projects with Raspberry Pi RP2040", **Rev 1.1, July 2024** (public Google Doc, last modified 2024-08-13) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: [DS] = Rev 1.1 (July 2024). [DS-R10] = Rev 1.0 (December 2021, DigiKey mirror), used for comparison only. No user manual was found, and the product page was not read. The datasheet pinout diagram is a figure that could not be read. The header map below comes from the silkscreen in Cytron's own product photo [GH], cross-checked against Zephyr [3P]. [VEN] here also covers firmware/core board definitions (CircuitPython, arduino-pico).

## What it is
- An Arduino Nano form-factor board with the Raspberry Pi **RP2040** MCU soldered on [DS title, GH README].
- On board: GPIO status LEDs, 2 WS2812B RGB LEDs, a piezo buzzer with mute switch, a user button, BOOT and RESET buttons, 2 Maker Ports (JST-SH), Micro USB, and 5V / 3.3V power LEDs [DS].
- Datasheet tagline: "Simplifying Projects with Raspberry Pi RP2040" [DS].
- [GH] README: "a small but powerful MCU for your project. It has the same Arduino Nano form factor."

## Specifications
Datasheet Table 3 is titled "MAKER-NANO-RP2040 **Absolute Maximum Ratings**" (under "3. SPECIFICATIONS"). Every row is below [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (Vin) | Min 7.0, Max 30.0 VDC | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 3.6 V | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.6 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| DC +5V max current (including onboard usage), power from Vin | 110 mA | [DS] |
| DC +5V max current (including onboard usage), power from USB | 500 mA | [DS] |
| DC +3V3 max current (including onboard usage), power from Vin | 110 mA | [DS] |
| DC +3V3 max current (including onboard usage), power from USB | 500 mA | [DS] |
| Digital IO each LED current draw | max 85 µA | [DS] |
| USB VID & PID (CircuitPython & Arduino Core) | VID 0x2E8A, PID 0x100F | [DS] |

## Interfaces, terminals and pin mapping
Onboard functions [DS]:

| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| RGB LED 0 and RGB LED 1 | GP11 | User-programmable WS2812B (2 LEDs, one data pin) | [DS] |
| User programmable button | GP20 | Examples and Zephyr use active-low with pull-up | [DS] pin; [3P] polarity |
| Piezo buzzer | GP22 | "Able to play tone or melody" | [DS] |
| Mute switch | Hardware | "Used to mute the piezo buzzer if pin D8 is used for other purposes" (wording as printed; see *Conflicts*) | [DS] |
| Digital IO LEDs | GP0–GP9, GP16–GP18 (as printed) | "Turn on when the IO state is high" | [DS] |
| Digital IO LEDs enable jumper (bottom) | Hardware | Cut the trace to disable the LEDs (saves "~1.19 mA (85 µA x 14 LEDs)"). Solder it to re-enable | [DS] |
| Boot button | Hardware | Hold while resetting to enter the bootloader. Used for Arduino IDE upload or loading MicroPython/CircuitPython firmware | [DS] |
| Reset button | Hardware | Resets the RP2040 | [DS] |
| Micro USB port | — | Program upload and power | [DS] |
| 5V and 3.3V power LEDs | Hardware | 5V LED "Turn on when powered up" | [DS] |
| Maker Port 0 (JST-SH 4-way) | Pins not stated in text | "GPIO, I2C, UART". Qwiic, STEMMA QT, Grove (via conversion cable) | [DS] |
| Maker Port 1 (JST-SH 4-way) | Pins not stated in text | "GPIO, I2C, Analog In" | [DS] |
| Pin header | — | "Compatible with original Arduino Nano" | [DS] |

**Header map** (GP numbers are printed on the silkscreen, read from Cytron's product photo [GH]; Arduino Nano positions given for comparison):
- Left row, from the Vin end: GP0 (Nano TX/D1 position), GP1 (Nano RX/D0 position), RS, G, then D2–D9 = GP2–GP9, D10 = GP17, D11 = GP19, D12 = GP16.
- Right row, from the USB end: D13 = GP18, 3V3, **NC (AREF position)**, A0 = GP26, A1 = GP27, A2 = GP28, A3 = GP29, A4 = GP12, A5 = GP13, A6 = GP14, A7 = GP15, 5V, RS, G, VIN.
- Zephyr's Arduino-Nano header map [3P] agrees for D2–D13 and A0–A7. It maps D0 = GP0 and D1 = GP1 (see *Needs verification*).

RP2040 pin functions on the Nano positions [VEN]:
- ADC exists only on GP26–GP29 (A0–A3).
- GP16/GP17/GP18/GP19 = SPI0 RX/CSn/SCK/TX (D12/D10/D13/D11), so Nano SPI positions are kept.
- GP12/GP13 (A4/A5) can be I2C0 SDA/SCL.
- GP0/GP1 = UART0 TX/RX.

## Rules and gotchas (for code, wiring and tutorials)
- **3.3 V logic.** Digital input high-level max is 3.6 V [DS]. **5 V Nano shields and sensors can't drive the pins directly** (derived from [DS]). Cytron's board text says "The I/O voltage is only 3.3V and it's not 5V compatible" [3P copies].
- **Only A0–A3 (GP26–GP29) are analog.** A4–A7 sit on GP12–GP15, which have no ADC (RP2040 [VEN]). The AREF position is NC [GH silkscreen].
- **Use GP numbers in code, not D numbers.** CircuitPython names pins `board.GP0`…`board.GP29` and `A0`–`A3`. There are no `D` names [VEN]. Arduino-pico also uses GPIO numbers [VEN].
- **Default buses differ from an Arduino Nano.** CircuitPython `board.I2C()` and `board.UART()` use GP0 (SDA/TX) and GP1 (SCL/RX). Arduino-pico `Wire` is on GP0/GP1 and `Wire1` on GP26/GP27 [VEN]. A Nano shield that expects I2C on A4/A5 needs I2C set to GP12/GP13 in code (derived from [VEN]).
- **Default SPI** = SCK GP18, MOSI GP19, MISO GP16 (CS GP17 in arduino-pico) [VEN]. This matches the Nano D13/D11/D12/D10 positions [GH silkscreen].
- **"LED" is GP2.** CircuitPython `board.LED` and arduino-pico `PIN_LED` map to GP2, a header pin with a status LED. There is no separate user LED [VEN].
- **Board-used pins:** GP11 (RGB), GP20 (button), GP22 (buzzer) [DS]. Mute the buzzer with the switch if its pin is reused [DS].
- **Status LEDs** draw 85 µA each. Cut the enable jumper to save power [DS].
- Spec table values are **absolute maximum ratings** [DS].

## Power and electrical limits
- Power comes from **Micro USB** or the **Vin pin, 7.0–30.0 VDC** [DS].
- Total current for the +5V and +3V3 rails, including onboard use: **110 mA each when powered from Vin, 500 mA each from USB** [DS Rev 1.1]. Rev 1.0 gave different figures (see *Conflicts*).
- No protection features (reverse polarity, fuse) are stated in the datasheet [DS].
- Status LEDs: 85 µA each, about 1.19 mA for 14 LEDs [DS].

## Software support
- **CircuitPython:** Cytron-built firmware at circuitpython.org board `cytron_maker_nano_rp2040`, with NeoPixel and simpleio built in [GH README]. The `code.py` on a new board is the factory demo [GH]. Pin names: `LED` (GP2), `RGB`/`NEOPIXEL` (GP11), `BUTTON` (GP20), `BUZZER` (GP22), `A0`–`A3` / `GP26_A0`…`GP29_A3` [VEN]. Editor suggested: Mu [GH].
- **MicroPython:** load it using the Raspberry Pi guide (no Cytron-specific firmware) [GH README]. There is no dedicated board in the MicroPython repo [VEN]. Use the RP2040 Pico firmware (derived).
- **Arduino:** the datasheet refers to "Arduino IDE" upload and an "Arduino Core" VID/PID [DS]. The Earle Philhower `arduino-pico` core has the board **"Cytron Maker Nano RP2040"** (variant `cytron_maker_nano_rp2040`) [VEN].
- **C/C++ SDK:** not in Cytron sources read. [3P] (CNX, circuitpython.org) mention C/C++.
- [GH] examples folder: CircuitPython and MicroPython examples (file list not readable).

## Compatibility and accessories
- **Arduino Nano:** the pin header is "Compatible with original Arduino Nano" [DS]. Limits: 3.3 V logic, only 4 ADC inputs, AREF = NC (see *Rules*). Cytron's text says it is compatible with "most" Nano daughter boards [3P copies].
- **Maker Ports:** Qwiic, STEMMA QT, Grove (via conversion cable) [DS].
- **Breadboard-friendly** [3P circuitpython.org].

## Common mistakes / troubleshooting
- **Wrong firmware from the GitHub setup guide:** `setup-circuitpython.md` in the Maker Nano repo is copied from Maker Pi RP2040. It links the Maker Pi RP2040 firmware and mentions a power switch [GH]. Use the `cytron_maker_nano_rp2040` firmware.
- **Analog read on A4–A7 fails:** those pins have no ADC [VEN].
- **I2C shield on A4/A5 not found:** default I2C is GP0/GP1 (see *Rules*).
- **Buzzer clicks when a pin is reused:** use the mute switch [DS].
- **Bootloader:** hold BOOT while pressing RESET [DS]. The drive appears as RPI-RP2 [GH guide, generic RP2040].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| +5V / +3V3 max current | [DS] Rev 1.1 (Jul 2024): +5V and +3V3 each 110 mA from Vin, 500 mA from USB | [DS-R10] Rev 1.0 (Dec 2021): +5V 100 mA, +3V3 500 mA | Rev 1.1 is newer and wins |
| Digital IO LED pins / count | [DS] Table 1: "GP0 - GP9, GP16 - GP18" (13 pins) | [DS] jumper section: "85 µA x 14 LEDs". [GH] README: "14 status indicator LEDs". [GH] photo shows an LED by GP19 | Count = 14. The pin list in Table 1 probably omits GP19; see *Needs verification* |
| Mute switch wording | [DS]: mute "if pin D8 is used for other purposes" | [DS]: buzzer on GP22. [GH] silkscreen: the D8 position is GP8 | Buzzer pin = GP22. The "D8" wording is unexplained |
| D0/D1 positions | [GH] silkscreen: GP0 at the Nano TX/D1 position, GP1 at RX/D0 | [3P] Zephyr: D0 = GP0, D1 = GP1 | Use GP numbers. Position-to-D mapping to confirm |
| Product status | [3P] Pimoroni: no longer stocked there | Product page not read | Unknown |

## Needs verification
- **Maker Port pin assignments:** not in the datasheet text. Firmware defaults suggest Port 0 = GP0/GP1 and Port 1 = GP26/GP27 [VEN, 3P], but this is unconfirmed.
- **Flash size:** 2 MB per [3P] (Pimoroni, Core Electronics, CNX, circuitpython.org page) and firmware definitions (W25Q16JV, arduino-pico 2 MB menu) [VEN]. Not in a Cytron datasheet.
- RAM 264 KB and dual-core Cortex-M0+ (RP2040 facts, [3P]-quoted).
- The full GP-to-header map (the datasheet pinout figure was not readable). The map above was read from a product photo, and the left-row order needs confirming against the datasheet figure.
- Whether GP19 has a status LED (see *Conflicts*), and whether GP10 and GP21 reach the header.
- Package contents: [3P] Pimoroni lists 1x Maker Nano RP2040 and 2x Grove to JST-SH (Qwiic/STEMMA QT) cables.
- Price (only [3P] CNX "$7.12" at launch), dimensions (figure not readable), regulator type and protections.
- Current product page content and lifecycle status.

## Sources
- [DS-R10] MAKER-NANO-RP2040 Datasheet, Rev 1.0, December 2021 (DigiKey mirror): https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6147/MAKER-NANO-RP2040.pdf
- [GH] https://github.com/CytronTechnologies/MAKER-NANO-RP2040 — README, `setup-circuitpython.md`, `MAKER-NANO-RP2040-Image.PNG` (via raw.githubusercontent.com)
- [PP] Product page (not read): https://www.cytron.io/p-maker-nano-rp2040
- Pinout diagram (Google Drawing, not readable here): https://docs.google.com/drawings/d/e/2PACX-1vSGwfh_1ac_UFXT4F72D0yJHaYHjDC-lfeBMLp0dc8ry57sAYtdobIFBZqrfXE6AuDTYEY9Cicto2b8/pub?w=3373&h=2867
- [VEN] CircuitPython: https://raw.githubusercontent.com/adafruit/circuitpython/main/ports/raspberrypi/boards/cytron_maker_nano_rp2040/pins.c (and `mpconfigboard.h`, `mpconfigboard.mk`); https://raw.githubusercontent.com/adafruit/circuitpython-org/main/_board/cytron_maker_nano_rp2040.md
- [VEN] arduino-pico: https://raw.githubusercontent.com/earlephilhower/arduino-pico/master/variants/cytron_maker_nano_rp2040/pins_arduino.h · https://raw.githubusercontent.com/earlephilhower/arduino-pico/master/boards.txt
- [3P] Zephyr: https://raw.githubusercontent.com/zephyrproject-rtos/zephyr/main/boards/cytron/maker_nano_rp2040/arduino_nano_connector.dtsi · https://shop.pimoroni.com/products/maker-nano-rp2040 · https://core-electronics.com.au/maker-nano-rp2040.html · https://www.cnx-software.com/2022/01/31/maker-nano-rp2040-arduino-nano-board-grove-qwiic-modules/
