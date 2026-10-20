# Maker Hat Base - HAT & GPIO Extension for Raspberry Pi 400 — Verified Reference

| | |
|---|---|
| Product code | `MAKER-HAT-BASE` (datasheet title "MAKER-HAT-BASE" [DS]; product-page image paths [PP]) |
| Family | Raspberry Pi boards and HATs |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Still out of stock. The packing list, the onboard 3.3 V regulator and "status LEDs for each GPIO" are now Cytron-stated (earlier [3P] only) |
| Primary source | *MAKER-HAT-BASE — HAT & GPIO Extension for Raspberry Pi 400, Datasheet*, **Rev 1.0, September 2021** (Google Doc, last modified 2024-01-23), Cytron Technologies Sdn Bhd |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

No user manual exists; the product page links only the datasheet and a CAD zip [PP]. The datasheet is short (board layout table, 3-row spec table, dimension drawing). No [UM] or [DT] source was used.

## What it is
A base board that extends the Raspberry Pi 400 GPIO through a 40-way ribbon cable to a pin header for stacking a Raspberry Pi HAT, a labelled breakout of the Raspberry Pi pins, GPIO status LEDs, 3 Grove ports (I2C, UART, GPIO), 4 programmable buttons and a buzzer with mute switch [DS].
It is not a computer and adds no microcontroller: every function is a plain Raspberry Pi GPIO [DS]. The datasheet subtitle is "HAT & GPIO Extension for Raspberry Pi 400" [DS]; product-page images also mention Raspberry Pi 3 and 4 [PP].

## Specifications
Datasheet section 1 (board layout and function) and section 2 (specifications), every row:

| Item | Value | Src |
|---|---|---|
| Target host | Raspberry Pi 400 (datasheet subtitle); page images also mention Raspberry Pi 3/4 | [DS][PP] |
| Pin header for HAT | Stack the Raspberry Pi HAT here | [DS] |
| Grove ports | I2C, UART, GPIO (3 ports) | [DS] |
| IDC socket for Raspberry Pi | Connect to Raspberry Pi via 40-way ribbon cable | [DS] |
| Buzzer | Programmable fixed tone buzzer, resonant frequency 2700±300Hz, connected to GPIO26 internally | [DS] |
| Mute switch | Mutes the buzzer if GPIO26 is used for other purposes | [DS] |
| Programmable buttons | 4, active low, connected to GPIO17, 22, 23 and 27 internally; enable the internal pull-up to use them | [DS] |
| GPIO status LEDs | LED indicator for Raspberry Pi GPIO; turns on when the GPIO state is high | [DS] |
| Raspberry Pi pins breakout | Breakout of the Raspberry Pi pins, for jumper cables to other components | [DS] |
| 3.3V power LED | On when powered up | [DS] |
| 5V power LED | On when powered up | [DS] |
| 5V supply | Supplied by Raspberry Pi | [DS] |
| 3.3V supply voltage | min 3.235, max 3.365 V | [DS] |
| 3.3V supply current | max 800 mA | [DS] |
| GPIO specification | Refer to Raspberry Pi | [DS] |
| Dimensions | Section 3 is a drawing only — not readable | — |

Note: the spec table is slightly mangled in the text export (the 3.3V current row is split from its parent row), but each value maps to one row without ambiguity.
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Features list:** designed for Raspberry Pi 400; compatible with Pi 3 and Pi 4 (via the ribbon cable); extension pins for a HAT; labelled GPIO breakout; **status LEDs for each GPIO**; 1 programmable buzzer; 4 programmable push buttons; 3 Grove ports (GPIO, UART, I2C); **onboard 3.3 V regulator, up to 800 mA extra current** [PP].
- **Packing list:** 1x Maker Hat Base, 1x mini breadboard (random colour), 1x 40-way female-to-female IDE cable 10 cm, 1x flat cable clamper with adhesive 60 mm, 4x silicone bumpers, 1x PC104 2x20 header pin (shipped after 25 Nov 2021) [PP].
- **Resources:** datasheet, CAD file, MagPi review link [PP]. Layout and dimension images — not read.

## Interfaces, terminals and pin mapping
Pin mapping (datasheet section 1; BCM GPIO numbers) [DS]:

| Function | Signal | GPIO |
|---|---|---|
| I2C Grove port | SCL / SDA | GPIO3 / GPIO2 |
| UART Grove port | RXD / TXD | GPIO15 / GPIO14 |
| GPIO Grove port | 2 signals | GPIO12 / GPIO13 |
| Buzzer | — | GPIO26 (via mute switch) |
| Buttons (active low) | 4 buttons | GPIO17, GPIO22, GPIO23, GPIO27 |

- Connection to the Raspberry Pi: IDC socket + 40-way ribbon cable [DS].
- HAT header: a pin header to stack a Raspberry Pi HAT [DS]. Its pins are the same Raspberry Pi GPIOs as the breakout, so a HAT and the onboard buttons/buzzer/Grove ports share pins [DS].
- Order of the Grove pins on the connector (which GPIO is on which Grove wire) and the breakout header pin order are shown only as images — see *Needs verification*.
- Which GPIOs have status LEDs: the datasheet says "LED indicator for Raspberry Pi GPIO" without listing them — see *Needs verification*.

## Rules and gotchas (for code, wiring and tutorials)
- **Buttons are active low**: pressed = 0 / LOW. Enable the internal pull-up [DS]. Buttons: GPIO17, 22, 23, 27 [DS].
- **Buzzer is on GPIO26 behind a mute switch** [DS]. If the buzzer is silent, check the mute switch. If a HAT or project uses GPIO26 for something else, mute it [DS].
- The datasheet calls it a **"programmable fixed tone buzzer"**, resonant 2700±300Hz [DS]. Do not promise melodies; it is not stated as active or passive.
- **GPIO status LEDs turn on when the GPIO is high** [DS] — they show the pin state; they are not separate programmable LEDs.
- **Pin sharing**: a stacked HAT uses the same GPIOs as the buttons (17, 22, 23, 27), buzzer (26), I2C Grove (2/3), UART Grove (14/15) and GPIO Grove (12/13) [DS]. Check the HAT's pin use before running button or buzzer code.
- UART Grove = GPIO14 (TXD) / GPIO15 (RXD) = the Pi's primary UART [DS]. On Raspberry Pi OS the serial port must be enabled to use it (standard Pi setup, not stated in the datasheet).
- I2C Grove = GPIO2 (SDA) / GPIO3 (SCL) [DS]; enable I2C on the Pi.
- 5V is supplied by the Raspberry Pi [DS]: the board has no power input of its own, so a HAT's 5V load comes from the Pi.
- The 3.3V supply is rated 3.235–3.365 V, max 800 mA [DS]. Do not state "3.3V from the Pi" — the datasheet gives the board its own 3.3V rating.
- GPIO electrical limits: "Refer to Raspberry Pi" [DS] — 3.3V logic, not 5V tolerant [VEN].
- The datasheet does not describe any HAT ID EEPROM, Python library or example code.

## Power and electrical limits
- 5V: supplied by the Raspberry Pi through the ribbon cable [DS]. 5V current limit not stated.
- 3.3V supply: 3.235 – 3.365 V, max 800 mA [DS].
- 3.3V and 5V power LEDs show both rails are up [DS].
- GPIO specification: refer to Raspberry Pi [DS].
- Board power consumption: not stated.

## Software support
- No Cytron library is needed; buttons, buzzer and Grove ports are plain Raspberry Pi GPIO / I2C / UART [DS].
- Python / libraries: not described in the datasheet — see *Needs verification*.
- No Cytron GitHub repo or example code was found in the sources.
- CAD file: "MAKER-HAT-BASE CAD.zip" (Sep 2021) linked from the product page [PP].

## Compatibility and accessories
- Datasheet: designed for the **Raspberry Pi 400** [DS].
- Product-page images also mention **Raspberry Pi 3 and 4** [PP].
- Raspberry Pi 500, Pi 5 and Zero 2 are listed only by resellers [3P] — see *Needs verification*.
- Packing list: not stated in the datasheet — see *Needs verification*.
- Price: RM45.78 (Cytron product page, read 2026-10-16) [PP].

## Common mistakes / troubleshooting
- Button always reads pressed or floats → internal pull-up not enabled; remember pressed = LOW [DS].
- No sound → mute switch is on, or GPIO26 not driven [DS].
- Buzzer sounds when a HAT runs → the HAT uses GPIO26; set the mute switch [DS].
- LEDs light when nothing is "on" → status LEDs follow GPIO state (high = on) [DS].
- Power LEDs off → check the ribbon cable connection; the board takes 5V from the Pi [DS].
- Grove UART device not responding → Pi serial port not enabled, or TX/RX roles mixed (Grove TXD = GPIO14, RXD = GPIO15) [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supported Pi models | Raspberry Pi 400 (datasheet subtitle) [DS]; page images also mention Pi 3/4 [PP] | Pi 500/400 and "Compatible with" 3B, 4B, 5, Zero 2 [3P]; "works with any Raspberry Pi model" [3P] | Text states Pi 400 [DS] and Pi 3/4 [PP]; others go to *Needs verification* |
| Buzzer type | "Programmable fixed tone buzzer" [DS] | "Controllable by digital output or PWM for tones" (review) [3P] | Datasheet wins: fixed tone |
| 3.3V 800 mA | 3.3V supply, max 800 mA [DS] | "Onboard 3.3V regulator providing up to 800mA of extra current" [3P] | Datasheet value used; "onboard regulator" / "extra" not in [DS] |

## Needs verification
- Grove connector wire order and breakout header pin order (images only).
- Board dimensions and HAT mounting holes (datasheet section 3 is a drawing). A review gives 4.8 x 2.8 inches and M2.5 screw points [3P only].
- Buzzer drive: active (on/off) or needs PWM; behaviour with gpiozero `Buzzer` vs `TonalBuzzer`.
- Compatibility with Raspberry Pi 500, Pi 5, Zero 2 W and earlier 40-pin Pis [3P only].
- 5V current available to a stacked HAT through the ribbon cable.
- Python library use: a review tested the buttons and buzzer with GPIO Zero (Python 3) [3P only].
- Whether the product is discontinued (Pimoroni says it no longer stocks it [3P]); Cytron page shows out of stock only [PP].
- Whether the four button GPIOs also show on GPIO status LEDs (page: "Status LEDs for each GPIOs").

## Sources
- [DS] MAKER-HAT-BASE Datasheet, Rev 1.0, September 2021 (Google Doc, modified 2024-01-23): https://docs.google.com/document/d/12l4vzu-r3VRBCLkCsuM00KOYnMPnQw5HxdfxjA3p5E0/edit
- [DS] Mirror of the same datasheet (Electrokit PDF, read via fetch, matches the Google Doc): https://www.electrokit.com/upload/product/41018/41018865/MAKER-HAT-BASE%20Datasheet.pdf
- [PP] MAKER-HAT-BASE CAD.zip (Sep 2021, not opened): https://drive.google.com/file/d/1-QgPYwi-PCm4-nDJv4DANBdvUG8V7lQ8/view
- [PP] Cytron product page (read by coordinator 2026-10-16: price, stock, page images): https://my.cytron.io/p-maker-hat-base-hat-and-gpio-extension-for-raspberry-pi-400
- [VEN] Raspberry Pi GPIO documentation (3.3V logic): https://www.raspberrypi.com/documentation/computers/raspberry-pi.html
- [3P] Pimoroni, Maker Hat Base: https://shop.pimoroni.com/products/maker-hat-base-hat-gpio-extension-for-raspberry-pi-400
- [3P] The Pi Hut, Maker HAT Base for Raspberry Pi 500/400: https://thepihut.com/products/maker-hat-base-for-raspberry-pi-400
- [3P] Tom's Hardware review: https://www.tomshardware.com/reviews/cytron-maker-hat-base
- [3P] Raspberry Pi Official Magazine review: https://magazine.raspberrypi.com/articles/review-maker-hat-base-for-raspberry-pi-400
