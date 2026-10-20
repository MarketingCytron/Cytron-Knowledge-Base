# Maker Pi Pico — Verified Reference

| | |
|---|---|
| Product code | `MAKER-PI-PICO` |
| Family | RP2040 / RP2350 boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Pico 2 compatibility is now Cytron-stated (base + Pico 2 SH / Pico 2 WH bundles); five variants with packing lists; Rev1.2.0 schematic linked |
| Primary source | Maker Pi Pico Datasheet, "MAKER PI PICO – Simplifying Raspberry Pi Pico for Beginner" (covers MAKER-PI-PICO and MAKER-PI-PICO-NB), Rev 1.2, March 2021 (public Google Doc linked from Cytron GitHub) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: no user manual [UM] was found. The datasheet board-function table has **no Grove pin table and no ESP-01 pin list**; those pins come from the product page [PP] and Cytron's pinout image "Maker Pi Pico Pin Reference, PCB Rev1.2.0 & above" [GH].

## What it is
- A beginner breakout / project board for the **Raspberry Pi Pico**. On MAKER-PI-PICO the Pico comes **soldered onboard** [PP packing list: "Raspberry Pi Pico soldered onboard, with CircuitPython loaded"]. The datasheet pinout is the Raspberry Pi Pico (RP2040) [DS Figure 3].
- Onboard: GPIO LEDs, WS2812B RGB LED, 3 programmable buttons, reset button, piezo buzzer with mute switch, 3.5 mm stereo audio out, ESP-01 (ESP8266) socket, microSD socket, 6 Grove ports, debugging-port breakout, GPIO breakout on male pin headers, 3V3 power LED [DS; Grove count PP].
- No motor driver, no servo ports, no battery or VIN input [DS — not listed].
- Datasheet tagline: "Simplifying Raspberry Pi Pico for Beginner" [DS]; product page title "Maker Pi Pico: Simplifying Raspberry Pi Pico for Beginners" [PP]. Product page: "It is a compact yet feature-packed board designed to sit at the heart of your STEM & robotics projects." and "Work out-of-the-box. No soldering!" [PP].

## Specifications
Datasheet Table 2 is titled "MAKER-PI-PICO **Absolute Maximum Ratings**" — every row below comes from it [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB) | Min 4.5, Max 5.5 VDC | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 3.6 V | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.62 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |

Dimensions: datasheet Figures 4–5 could not be read as text. No dimension figure in [PP] text.
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Page note:** "Maker Pi Pico Base is compatible with the latest Raspberry Pi Pico 2, of course, please choose the version with pre-soldered headers" [PP].
- **Variants:** Maker Pi Pico (Pico pre-soldered, CircuitPython loaded, + pinout card); Base + Raspberry Pi Pico 2 SH (headers by Cytron) + USB micro-B cable; Base + Pico 2 WH + cable; Base + Pico SH + cable; Base only + pinout card [PP].
- **Features list:** no soldering; all Pico / Pico W pins on two 20-way headers; **LED indicators on all GPIO pins**; 3 buttons GP20–22; RGB LED GP28; piezo GP18; 3.5 mm stereo jack GP18–19; microSD GP10–15; ESP-01 socket GP16–17; 6 Grove ports; reset button; pinout printed on the bottom layer [PP].
- **Resources:** datasheet, **Rev1.2.0 schematic** (Google Drive), demo and example code (GitHub), 3D CAD, Pico / Pico 2 / Pico W documents [PP].

## Interfaces, terminals and pin mapping
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| Micro USB port | Pico USB | "Used to power up the Maker Pi Pico and upload programs from PC." (MAKER-PI-PICO only) | [DS] |
| WS2812B RGB LED | GP28 | "User programmable WS2812B RGB LED"; 1 LED | [DS] pin; [PP] "1x RGB LED - NeoPixel (GP28)" |
| Programmable buttons | GP20, GP21, GP22 | Rev1.0.0–1.1.0: enable internal pull-up in software. Rev1.2.0: "Pulled-up permanently on hardware with debouncing capacitor." Active LOW | [DS]; "Active LOW" [GH pinout] |
| Piezo buzzer | GP18 | Buzzer mute switch mutes it | [DS] |
| Audio out (3.5 mm stereo jack) | Left GP18, Right GP19 | "Non amplified audio output. Can be connected to an earphone or amplified speaker." | [DS]; jack type [PP] |
| microSD card socket | GP10–GP15 | See table below | [DS] |
| ESP-01 socket | GP16, GP17 | GP16 = TX0, GP17 = RX0 (UART0). "Socket for ESP-01 ESP8266 WiFi module. Can be used to IoT-enable your project." | [DS] socket; [PP] "1x ESP-01 socket (GP16-17)"; TX/RX [GH pinout] |
| GPIO LEDs | Pico GPIO | "LED indicator for Raspberry Pi Pico GPIO. Turn on when the GPIO state is high." Product page: "LED indicators on all GPIO pins" | [DS]; [PP] |
| GPIO breakout | All Pico pins | MAKER-PI-PICO = male pin headers; "two 20 ways pin headers" | [DS]; [PP] |
| Debugging port breakout | SWCLK, GND, SWDIO | Breakout of the Pico debugging port | [DS]; labels [GH pinout] |
| Reset button | RUN | Resets the Raspberry Pi Pico | [DS]; RUN label [GH pinout] |
| 3V3 power LED | — | On when powered up | [DS] |

**microSD pins** [DS] (RP2040 SPI1 names from [GH pinout]):

| Pico GPIO | SD mode | SPI mode |
|---|---|---|
| GP10 | CLK | SCK (SPI1 SCK) |
| GP11 | CMD | SDI — card input, Pico SPI1 TX/MOSI |
| GP12 | DAT0 | SDO — card output, Pico SPI1 RX/MISO |
| GP13 | DAT1 | X (unused) |
| GP14 | DAT2 | X (unused) |
| GP15 | CD/DAT3 | CSn |

Datasheet note: "Unused pins must be configured as internal pull-ups." [DS] Cytron demo code: `busio.SPI(board.GP10, MOSI=board.GP11, MISO=board.GP12)`, CS = GP15 [GH].

**Grove ports (6)** — count [PP]; pins from the pinout image and PCB silkscreen [GH]:

| Grove | Pins | Functions shown on pinout |
|---|---|---|
| Grove 1 | GP0, GP1 | GP0: TX0, SDA0, SDI0. GP1: RX0, SCL0, CSn0 |
| Grove 2 | GP2, GP3 | GP2: SDA1, SCK0. GP3: SCL1, SDO0 |
| Grove 3 | GP4, GP5 | GP4: TX1, SDA0, SDI0. GP5: RX1, SCL0, CSn0 |
| Grove 4 | GP6, GP7 | GP6: SCK0, SDA1. GP7: SDO0, SCL1 |
| Grove 5 | GP8, GP9 | GP8: SDI1, SDA0, TX1. GP9: CSn1, SCL0, RX1 |
| Grove 6 | GP26, GP27 | GP26: ADC0, SDA1. GP27: ADC1, SCL1 |

Each Grove port: GPIO, GPIO, 3V3, GND [GH silkscreen].

## Rules and gotchas (for code, wiring and tutorials)
- **GP18 is shared by the buzzer and the left audio channel** [DS]. Slide the buzzer mute switch when using the audio jack, or the buzzer plays the audio (derived).
- **Audio out is not amplified** [DS]. Use earphones or an amplified speaker. The product page's "dual channel speakers" wording should not be read as passive speakers (see *Conflicts*).
- **Pins the board's peripherals use:** GP10–GP15 (microSD), GP16–GP17 (ESP-01), GP18 (buzzer / audio L), GP19 (audio R), GP20–GP22 (buttons), GP28 (RGB) [DS, PP]. None of these are on Grove ports; don't reuse the microSD or ESP-01 pins while a card or module is fitted (derived).
- **microSD in SPI mode:** set GP13 and GP14 as internal pull-ups [DS "Unused pins must be configured as internal pull-ups"].
- **I2C-capable Grove ports** (derived from [GH] pinout): Grove 1, 3, 5 (I2C0) and Grove 2, 4, 6 (I2C1). Cytron's demo puts an SSD1306/SSD1315 OLED on Grove 4 (SCL = GP7, SDA = GP6) [GH].
- **UART-capable Grove ports** [GH]: Grove 1 (UART0), Grove 3 and Grove 5 (UART1). UART0 on GP16/GP17 goes to the ESP-01.
- **Analog inputs:** only Grove 6 (GP26 = ADC0, GP27 = ADC1) [GH]. GP28 (ADC2) drives the RGB LED [DS].
- **Buttons are active LOW** [GH]. On PCB Rev1.0.0–1.1.0, code must enable the internal pull-up; Rev1.2.0 has a hardware pull-up and debounce capacitor [DS]. Enabling the internal pull-up in code works on all revisions (derived; Cytron demo does this [GH]).
- **RGB LED needs a NeoPixel driver.** Product page Q&A: "We need to utilize the Programmable IO (PIO) feature on Pi Pico to drive this RGB LED on pin GP28." [PP] CircuitPython demo uses `neopixel_write`; MicroPython demo uses `neopixel.NeoPixel` [GH]. Colour order is GRB in Cytron's demo (red = `[0, 10, 0]`) [GH].
- **GPIO LEDs light whenever a pin is HIGH** [DS], so SPI/I2C/UART/audio traffic makes them flicker (expected, derived).
- **Grove cables:** "we recommend you to use official or compatible grove 4 pin" — ordinary jumper wires may not seat securely [PP Q&A].
- **Pin header type:** MAKER-PI-PICO has male headers [DS].

## Power and electrical limits
- Power input: USB only, 4.5–5.5 VDC [DS]. No LiPo connector, no VIN terminal and no on/off switch are listed in the datasheet [DS, by omission].
- 3V3 current budget for Grove ports, ESP-01 and microSD: not stated in any Cytron source read.

## Software support
- Product page: "Maker Pi Pico can be programmed with CircuitPython, MicroPython & C/C++." Programs upload by USB drag and drop [PP].
- Out-of-the-box demo [GH] (CircuitPython `code.py` and MicroPython `main.py` versions): Mario melody with running GPIO LEDs at startup; GP20 = all LEDs on/off; GP21 = left/right audio test (L-R.wav) then RGB test; GP22 = microSD write/read test then RGB/melody demo; optional SSD1306 OLED on Grove 4 shows status.
- MicroPython demo uses `sdcard`, `ssd1306`, `wav_player` modules and `SoftI2C` [GH]. CircuitPython demo uses `adafruit_ssd1306`, `sdcardio`, `audiopwmio` [GH].
- Cytron tutorials listed in the [GH] README: pyRTOS multitasking, line-following robot (with Maker Drive and Maker Line), play MP3 with CircuitPython, environment sensor display, metronome, COVID-19 data display, HC-SR04P ultrasonic.

## Compatibility and accessories
- **Host board:** Raspberry Pi Pico (RP2040) [DS pinout; PP]. Pico W, Pico 2 and Pico 2 W are not mentioned in the datasheet (see *Needs verification*).
- Product page Q&A on Pico W: asked whether Maker Pi Pico + ESP-01 can replicate the Pico W — "Yes, Can achieve the same purpose, but code and library will not be the same." [PP] The ESP-01 module is not in the packing list [PP].
- **Variant in the same datasheet:** MAKER-PI-PICO-NB ("Maker Pi Pico Base" in [GH]) — no Micro USB port of its own, female pin headers, and a "Pi Pico Socket" for "Raspberry Pi Pico with Pre-soldered Headers" [DS]. Not documented as a separate product here.
- Grove modules on 6 Grove ports (3V3) [PP; GH]. ESP-01 (ESP8266) module in the socket [DS]. microSD card [DS]. Earphones / amplified speakers [DS].
- Accessories named in [GH] README: SSD1306 OLED, 3V3 I2C/SPI 1602 LCD, Maker Line, Maker Drive, ultrasonic ranging module.
- Packing list [PP]: 1x Maker Pi Pico (Raspberry Pi Pico soldered onboard, with CircuitPython loaded), 1x pinout reference card. Optional USB Micro B cable sold separately [PP].

## Common mistakes / troubleshooting
- **Buzzer sounds during audio playback:** GP18 is shared; mute the buzzer [DS].
- **Buttons read random values on older boards:** Rev1.0.0–1.1.0 need the internal pull-up enabled in code [DS].
- **RGB LED not working with plain GPIO writes:** it needs a NeoPixel (PIO) driver on GP28 [PP Q&A].
- **SD card fails in SPI mode:** check GP13/GP14 pull-ups and that GP10–GP15 aren't used elsewhere [DS].
- **Demo code lost after overwriting:** demo code is on Cytron's GitHub [PP Q&A; GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Firmware preloaded | [PP] description and packing list (read 2026-10-20): "Raspberry Pi Pico soldered onboard, with CircuitPython loaded" | [PP] Q&A (2021): "It comes not preloaded" | Current packing list wins: CircuitPython loaded on the pre-soldered version |
| What the audio jack drives | [PP]: "dual channel speakers" | [DS]: "Non amplified audio output … earphone or amplified speaker" | [DS] wins: earphones or amplified speakers |
| Tagline wording | [DS]: "for Beginner" | [PP]: "for Beginners" | Use [PP] wording for marketing titles; both refer to the same product |
| Button pull-ups | [DS] Rev1.0.0–1.1.0: software pull-up | [DS] Rev1.2.0: hardware pull-up + debounce capacitor | Both true by PCB revision; enable the internal pull-up in code for all boards |
| GPIO LED coverage | [DS]: "LED indicator for Raspberry Pi Pico GPIO" | [PP]: "LED indicators on all GPIO pins" | Not contradictory; exact count unverified |

## Needs verification
- **Grove pin mapping** and **ESP-01 TX/RX** come from the [GH] pinout image ("PCB Rev1.2.0 & above") and [PP], not the datasheet. Confirm for PCB Rev1.0.0–1.1.0.
- Exact number of GPIO LEDs and which pins have them (Cytron demo drives GP0–17, GP19–22, GP26–28 plus GP25 [GH]).
- Board dimensions and mounting holes — datasheet figures not readable as text.
- 3V3 current available to Grove, ESP-01 and microSD.
- Whether the ESP-01 socket is 3.3 V-only (implied by ESP-01, not stated).
- Whether GP19 (right audio) has any other onboard load.
- Pico 2 W pin differences on the Base (GP23–GP25, GP29) — the page sells a Base + Pico 2 WH bundle but does not discuss them.
- Rev1.0.0–1.1.0 schematic — only the Rev1.2.0 schematic is linked.

## Sources
- [DS] Maker Pi Pico Datasheet, Rev 1.2, March 2021 (public Google Doc, linked from the Cytron GitHub README): https://docs.google.com/document/d/1JoHsZk5IipQPCLXWbZYpDKjGlnkyACOJ1taUrKVsRg8/edit
- [DS mirror] Same datasheet as public PDF (Electrokit), Rev 1.2, March 2021: https://www.electrokit.com/upload/product/41019/41019030/Maker%20Pi%20Pico%20Datasheet.pdf
- [PP] https://my.cytron.io/p-maker-pi-pico (read 2026-10-16)
- [GH] https://github.com/CytronTechnologies/MAKER-PI-PICO — README.md, MakerPiPico-Pinout.png, Out-of-the-box Demo Code/CircuitPython/code.py, Out-of-the-box Demo Code/MicroPython/main.py (via raw.githubusercontent.com)
- [3P] https://core-electronics.com.au/maker-pi-pico.html (cross-check only)
