# Maker pHAT: Simplifying Raspberry Pi for Education — Verified Reference

| | |
|---|---|
| Product code | `HAT-MAKER` (user's manual cover and packing list "Maker pHAT (Code: HAT-MAKER)" [UM]; product-page image paths [PP]) |
| Family | Raspberry Pi boards and HATs |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | *Maker pHAT (HAT-MAKER) User's Manual*, **Rev 1.10, Feb 2019** (Google Doc, last modified 2024-01-23), Cytron Technologies Sdn Bhd. No separate datasheet exists; the user's manual is the main source |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

No [DS] document exists for this product: the product page links only a User's Manual and two schematics [PP]. The schematics (Rev1.00 and Rev1.10) are image-only PDFs and could not be read here, so no fact below comes from them. No [DT] source was used.

## What it is
A Raspberry Pi Zero-size pHAT ("partially Hardware Attached on Top") that stacks on the 40-pin GPIO header [UM]. It adds a USB Micro-B socket that powers the Raspberry Pi and gives a USB-to-UART serial console (for headless setup without monitor, keyboard or mouse), 8 GPIO indicator LEDs, 3 programmable push buttons, an active buzzer and labelled breakout pins for all GPIOs, SPI, UART, I2C, 5V, 3.3V and GND [UM]. It is aimed at beginners and education [UM].
It is a pHAT, not a computer: it needs a Raspberry Pi (not included) [UM]. The PCB is purple [UM].

## Specifications
User's manual section 1 (features) and section 3 (Absolute Maximum Rating), every row:

| Item | Value | Src |
|---|---|---|
| Form factor | Raspberry Pi Zero size, stacks on the Pi Zero series of SBC | [UM] |
| Compatibility (manual) | Standard Raspberry Pi 3B / 3B+ and Raspberry Pi Zero / W / WH | [UM] |
| GPIO footprint | Standard Raspberry Pi GPIO footprint (40-pin) | [UM] |
| LED array | 8 LEDs on GPIO 17, 18, 27, 22, 25, 12, 13, 19 | [UM] |
| Push buttons | 3x programmable, need input pull-up: SW1 GPIO 21, SW2 GPIO 16, SW3 GPIO 20 (features list says "21, 19 and 20" — see *Conflicts*) | [UM] |
| Buzzer | Onboard active buzzer, GPIO 26, HIGH = on, LOW = off | [UM] |
| Labels | Proper label for all GPIOs, including SPI, UART, I2C, 5V, 3.3V and GND | [UM] |
| USB connector | USB Micro-B socket, for 5V input and USB-to-UART communication | [UM] |
| USB-serial IC | Board layout (Rev1.10 manual): FT231X. Features list: CH340 — see *Conflicts* | [UM] |
| Input voltage (features) | USB 5V, from computer, power bank or standard USB adapter | [UM] |
| Input voltage via USB connector (abs. max) | min 4.8, max 5.2 V | [UM] |
| DC current for 5V pin (max continuous) | Max "USB" mA (i.e. limited by the USB source; no number given) | [UM] |
| USB-serial indicator LED | Indicates USB-serial activity | [UM] |
| PCB colour | Purple | [UM] |
| Packing list | 1x Maker pHAT (HAT-MAKER); 1x 2x20 Stacking Header (CN-PH-PC104) | [UM] |
| Warranty | 1 year, manufacturing defects only [UM]; 12 months [PP] | [UM][PP] |
| Dimensions | Dimension drawing is an image only — not readable | — |

## Interfaces, terminals and pin mapping
Board layout (manual section 4) [UM]. All GPIO numbers are BCM GPIO numbers, not header pin numbers.

| Label | Function | Pins / notes |
|---|---|---|
| A | Raspberry Pi standard 40 header pin | Stacks the pHAT on the Pi |
| B | Breakout power pins | 5V, 3.3V, GND |
| C | Breakout I2C | SDA = GPIO 2, SCL = GPIO 3 |
| D | Breakout UART | TX = GPIO 14, RX = GPIO 15 |
| E | Breakout GPIO | GPIO 17, 18, 27, 22, 25, 12, 13, 19 |
| F | Breakout SPI | MOSI = GPIO 10, MISO = GPIO 9, SCK = GPIO 11, CE0 = GPIO 8, CE1 = GPIO 7 |
| G | GPIO indicator LEDs | On the selected GPIOs; can be driven as outputs or act as input indicators |
| H | USB Micro-B connector | Alternative supply to the Raspberry Pi and serial remote access |
| I | USB-serial indicator LED | USB-serial activity |
| J | USB-serial IC converter (FT231X) | Converts USB to serial; connected to the Pi UART RX/TX |
| K | Active buzzer | GPIO 26; HIGH = on, LOW = off |
| L | Programmable push buttons | GPIO 21, 16, 20; configure as input pull-up |

Onboard function map (manual sections 7 and 8, and demo code) [UM]:

| Function | GPIO |
|---|---|
| LED1 … LED8 (left to right) | GPIO 17, 18, 27, 22, 25, 12, 13, 19 |
| SW1 / SW2 / SW3 | GPIO 21 / GPIO 16 / GPIO 20 |
| Active buzzer | GPIO 26 |
| USB-serial (to Pi) | UART TX GPIO 14 / RX GPIO 15 |

- The 8 LED GPIOs "can be configured as output, input and input pull up"; the LED then shows the pin state [UM].
- Rev1.10 comes with pre-soldered SMD header pins on the breakout pads, so there is "no worry about short circuit" when stacked on a Raspberry Pi Zero WH [UM].
- No Grove ports, no ADC, no motor driver, and no HAT ID EEPROM are described in the manual [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **SW2 is GPIO 16, not GPIO 19.** The manual's feature list says "GPIO 21, 19 and 20", but the board layout table, section 7.2 and the demo code all use 21, 16, 20, and GPIO 19 is already LED8 [UM]. Use SW1 = 21, SW2 = 16, SW3 = 20.
- **Buttons need input pull-up** [UM]. With gpiozero, `Button(21)` (default pull-up) works as in the demo code [UM].
- **Buzzer is active**: set GPIO 26 HIGH to sound, LOW to mute [UM]. Drive it on/off; the manual gives no tone or PWM control.
- **Serial console needs `enable_uart=1`** added at the bottom of `config.txt` on the SD card boot partition before first boot [UM]. Terminal speed **115200** [UM].
- The USB-serial link uses the Pi's UART on GPIO 14/15 [UM]. The UART breakout (D) is the same GPIO 14/15, so do not wire another serial device there while using the USB serial console.
- The 8 LED GPIOs are shared with the breakout GPIO pins (E): anything wired there also lights the LED [UM].
- **Pi Zero WH stacks directly**; Pi 3 Model B / B+ need the 2x20 PC104 stacking header (included in the box) [UM].
- **Do not unplug the USB cable without a proper shutdown** — it might corrupt the microSD card [UM]. The demo code shows a hardware shutdown by holding SW2 + SW3 (`sudo shutdown -h now`) [UM].
- **The printed demo code in the manual has a bug**: the shutdown branch uses `for loop in range(times)` where `times` is undefined. The linked gist uses `range(3)` [GH]. Copy code from the gist, not the manual.
- The manual's driver links are for the CH340 (CH341SER for Windows 10 and macOS) [UM], while the Rev1.10 layout names an FT231X [UM] — check which chip is on the board before telling readers which driver to install (see *Conflicts*).

## Power and electrical limits
- Power input: USB 5V through the Micro-B socket, from a computer, power bank or standard USB adapter [UM].
- Absolute maximum input voltage via USB: 4.8 – 5.2 V [UM].
- When stacked, the USB connection powers up the Raspberry Pi through the Maker pHAT ("Supply (alternative) to Raspberry Pi") [UM].
- 5V pin max continuous current: limited by the USB source ("USB" in the table; no figure) [UM].
- 3.3V breakout current, logic levels and pHAT power consumption: not stated.

## Software support
- OS in the manual: Raspbian Stretch with Desktop (or NOOBS V2.9.0), written with Etcher [UM].
- Serial remote: PuTTY (Windows), Serial, COM port from Device Manager, speed 115200 [UM]. The board should appear as "USB Serial Port" under Ports (COM & LPT); if not, install the driver [UM].
- Drivers linked in the manual: Windows 10 and macOS (CH341SER) [UM].
- After serial login, the manual walks through Wi-Fi setup and enabling VNC in `sudo raspi-config`, finding the IP with `ifconfig`, `sudo apt-get update`, then VNC Viewer [UM].
- Python: Python 3 (IDLE) with the **gpiozero** library (`LED`, `Button`, `Buzzer`) [UM]. Demo `MakerpHATDemo.py`: SW1 runs LEDs right to left (GPIO 19 → 17) with a double beep, SW2 runs left to right with a double beep, SW3 stops with a single beep, hold SW2 + SW3 to shut down [UM]. Demo gist: IdrisCytron [GH].
- No Cytron library is needed; all functions are plain GPIO [UM].

## Compatibility and accessories
- Manual: Raspberry Pi 3B / 3B+ and Raspberry Pi Zero / W / WH [UM]. Intro also mentions the HAT-size Raspberry Pi B+/2/3/3B+ generally [UM].
- Pi Zero WH: stacks directly, no extra parts [UM].
- Pi 3 Model B / B+: needs the PC104 2x20 header (CN-PH-PC104), which is in the box [UM].
- Recommended starter set: Maker pHAT, Raspberry Pi Zero WH, 16GB microSD card, USB Micro-B cable [UM].
- Other models (Pi 4, Pi 5, Zero 2, A+) are not listed in the manual — see *Needs verification*.
- Price: RM45.78 (Cytron product page, read 2026-10-16) [PP].

## Common mistakes / troubleshooting
- No COM port on the PC → install the USB-serial driver; test the pHAT on the PC alone before stacking [UM].
- Serial terminal blank → `enable_uart=1` missing from `config.txt`, or speed not 115200; press Enter after opening the port [UM].
- Button never reads pressed / reads random → GPIO not set as input pull-up [UM]; or code uses GPIO 19 for SW2 (wrong, use 16).
- Corrupted SD card → USB cable was unplugged without shutdown [UM].
- Demo code crashes on SW2 + SW3 → use the gist version (`range(3)`) [GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| SW2 GPIO | "GPIO 21, 19 and 20" — manual features list [UM]; same on Core Electronics / The Pi Hut [3P] | GPIO 21, **16**, 20 — manual board layout L, section 7.2 and demo code [UM]; gist [GH] | Use GPIO 16 (stated three times in the manual and in working code; GPIO 19 is LED8). Confirm on schematic |
| USB-serial chip | "USB serial facilitated by the CH340" — manual features list [UM]; CH341SER driver links [UM] | "USB-SERIAL IC CONVERTER (FT231X)" — manual board layout J [UM]; "Rev1.10 uses FT231X" [3P] | Same document, both [UM]. Likely CH340 on Rev1.00 and FT231X on Rev1.10, but only [3P] says so — verify against the two schematics before naming a chip or driver |
| Warranty | 1 year [UM] | 12 months [PP] | Same |
| Compatible Pi models | 3B/3B+ and Zero/W/WH [UM] | Also Pi 1 A+, 3 A+, 4 B; "Compatible with" 3B, 4B, 5, Zero 2 [3P] | Manual list used in text; others to *Needs verification* |

## Needs verification
- **USB-serial chip per PCB revision** (CH340 vs FT231X) and the matching driver — schematics Rev1.00 and Rev1.10 are image-only and were not read.
- Any other Rev1.00 vs Rev1.10 difference besides the pre-soldered SMD headers on the breakout pads.
- Board dimensions and mounting holes (dimension drawing is an image only).
- Pi 4 B, Pi 1 A+, Pi 3 A+, Pi 5 and Pi Zero 2 W compatibility [3P only]. Pi Zero / Zero W (no header) need a 2x20 header soldered first [3P only].
- Whether it is safe to power the Pi from its own USB/PSU and the pHAT USB at the same time — not stated.
- 3.3V breakout current limit; total current available on the 5V pin.
- Steps for current Raspberry Pi OS (no Raspbian Stretch; raspi-config menu numbering; device names such as /dev/serial0) — the manual's 2019 steps were not re-tested.
- LED drive polarity (LED on = GPIO high is implied by the demo code `LED()` default, not stated).

## Sources
- [UM] Maker pHAT (HAT-MAKER) User's Manual, Rev 1.10, Feb 2019 (Google Doc, modified 2024-01-23): https://docs.google.com/document/d/1iDYLyoQKOPJRD5m5ivu8Ivv6zyeLIc3IxUtRKOx7n8k/view
- [UM] Mirror of the same manual (Electrokit PDF, read via fetch, matches the Google Doc): https://www.electrokit.com/upload/product/41018/41018274/Maker%20pHAT%20User's%20Manual.pdf
- [PP] Schematic Rev1.00, "Maker pHAT Rev1.00 Sch.pdf" (image only, not read): https://drive.google.com/file/d/1hoqUaCFq166SRasI6bxHrkCjJ1LZ3nnM/view
- [PP] Schematic Rev1.10, "HAT-MAKER Rev1.10 Sch.pdf" (image only, not read): https://drive.google.com/file/d/1ibTC7uP8Sy7kzTiq8G41mmgSTVJkIkUt/view
- [PP] Cytron product page (read by coordinator 2026-10-16: price, stock, warranty, linked documents): https://my.cytron.io/p-maker-phat-simplifying-raspberry-pi-for-education
- [GH] Maker pHAT demo code gist (IdrisCytron): https://gist.github.com/IdrisCytron/9b3e2994eb2142d4ac10cb4d151016e3
- [3P] Core Electronics, Maker pHAT: https://core-electronics.com.au/maker-phat.html
- [3P] The Pi Hut, Maker pHAT: https://thepihut.com/collections/cytron/products/maker-phat-simplifying-raspberry-pi-for-education
