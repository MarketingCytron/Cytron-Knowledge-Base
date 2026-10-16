# Maker Pi Pico Mini — Verified Reference

| | |
|---|---|
| Product code | `MAKER-PI-PICO-MINI` (Pico / Pico W pre-mounted) and `MAKER-PI-PICO-MINI-NB` (no Pico, with Pi Pico socket) [DS cover]. Product page image paths also show a with-Pico-W variant [PP]; its separate order code is not stated. |
| Family | RP2040 / RP2350 boards and Raspberry Pi boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "MAKER-PI-PICO-MINI — Simplifying Projects with Raspberry Pi Pico / Pico W" Datasheet (covers MAKER-PI-PICO-MINI and MAKER-PI-PICO-MINI-NB), Rev 1.0, June 2022 (public Google Doc linked from the product page; Drive last modified 2022-10-20) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: no user manual [UM] was found. [DS] includes the pinout diagram (Figure 3, same drawing as the product-page "Pinout" link) and the dimension drawing (Figure 4); facts read from those figures are tagged [DS]. [DS-schematic] = Cytron schematic "MAKER-PI-PICO-MINI", REV 1.0.0, dated 6/13/2022 (public, linked from the product page); it supports but never overrides the datasheet text. "(derived)" = a conclusion drawn from the cited sources, not a stated spec.

## What it is
- A small carrier board for the **Raspberry Pi Pico / Pico W** [DS title]. MAKER-PI-PICO-MINI comes with a Raspberry Pi Pico / Pico W pre-mounted; MAKER-PI-PICO-MINI-NB has a "Pi Pico Socket" instead [DS Table 1, Figure 1: "Pre-soldered Pico/Pico-W" or "Pi Pico Socket"].
- Onboard [DS Table 1]: status LEDs for GP0–GP5, GPIO LED enable jumper, 1 programmable button (GP20), reset button, single-cell LiPo / Li-Ion battery connector with USB charging, charging LED, 3.3V power LED, passive piezo buzzer (GP18), WS2812B RGB LED (GP28), Maker Ports (JST-SH 4-way), GPIO breakout.
- Not on this board (none listed in [DS]): no audio jack, no microSD socket, no ESP-01 socket, no buzzer mute switch, no native Grove connectors, no motor driver, no servo header, no USB connector of its own (USB is the Pico's).
- Product page title: "Maker Pi Pico Mini: Simplifying Projects with Raspberry Pi Pico" [PP]; datasheet tagline "Simplifying Projects with Raspberry Pi Pico / Pico W" [DS].

## Specifications
Datasheet Table 3 is titled "MAKER-PI-PICO-MINI **Absolute Maximum Ratings**" — rows 1–5 below come from it [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage — USB | Min 4.5, Max 5.5 VDC | [DS] |
| Power input voltage — LiPo battery | Min 3.3, Max 4.2 VDC | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 3.6 V | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.6 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |
| Board dimensions | 53.85 mm × 23.12 mm | [DS Figure 4] |
| Battery type | Single Cell LiPo / Li-Ion, rechargeable via USB | [DS] |
| Battery charger IC / protection IC | MCP73831T-2ACI/OT / CT2105 | [DS-schematic] |

Not stated in any source read: charge current, 3V3 current budget for the Maker Ports, mounting holes, weight, battery connector part/pitch.

## Interfaces, terminals and pin mapping
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| Status LEDs for GPIO | GP0, GP1, GP2, GP3, GP4, GP5 (6 LEDs) | "LED indicator for digital IO GP0 - GP5. Turn on when the IO state is high." Each LED is switched by a BSS138 MOSFET whose gate is the GPIO | [DS]; MOSFET [DS-schematic] |
| GPIO LED Enable Jumper | JP2 ("LED" on silkscreen) | "Cut the trace to disable the GPIO LEDs. This is done to save power or to reduce distraction from GPIO LEDs." | [DS]; [DS-schematic] |
| Programmable button | GP20 | "Accessible from the user program." Hardware 10K pull-up to 3V3, 1K series and 0.1 µF capacitor; button pulls GP20 to GND (active LOW, derived) | [DS]; circuit [DS-schematic] |
| Reset button | RUN | "Press to reset the Raspberry Pi Pico / Pico W." | [DS]; RUN net [DS-schematic] |
| Piezo buzzer | GP18 (PWM1A) | "Programmable passive piezo buzzer." Driven through a MOSFET (Q2) | [DS]; PWM1A [DS Figure 3]; Q2 [DS-schematic] |
| RGB LED (WS2812B) | GP28 | "User programmable WS2812B RGB LED." 1 LED, powered from 3V3 | [DS]; count/3V3 [DS-schematic] |
| LiPo battery connector | 2-pin (JP1 "LIPO"), + and − marked | "Connect to Single Cell LiPo / Li-Ion Battery. Rechargeable via USB." | [DS]; [DS-schematic] |
| Charging LED | "CHG." | "Turn on when the LiPo battery is charging." | [DS] |
| 3.3V power LED | "3V3" | "Turn on when powered up." | [DS] |
| Maker Ports (3) | see table below | "JST-SH 4-Ways Connector for external modules. Compatible with Qwiic, STEMMA QT and Grove (Via Conversion Cable)." | [DS]; count [DS Figure 3, SCH] |
| GPIO breakout | All 40 Pico pins | "Pin Headers for external connection. It's not pre-soldered for Maker Pi Pico Mini which comes with Raspberry Pi Pico / Pico W pre-mounted." | [DS] |
| Pi Pico socket | — | "Socket for Raspberry Pi Pico / Pico W. Available on MAKER-PI-PICO-MINI-NB only." | [DS] |

**Maker Ports** — connector pin order GND, 3V3, then the two GPIOs [DS-schematic JP3/JP4/JP5; DS Figure 3]:

| Maker Port | Pins | Functions shown on the [DS] pinout |
|---|---|---|
| Port GP0/GP1 (JP3) | GP0, GP1 | GP0: SDA0, TX0, SDI0, PWM0A. GP1: SCL0, RX0, CSn0, PWM0B |
| Port GP4/GP5 (JP4) | GP4, GP5 | GP4: SDA0, TX1, SDI0, PWM2A. GP5: SCL0, RX1, CSn0, PWM2B |
| Port GP26/GP27 (JP5) | GP26, GP27 | GP26: SDA1, A0, PWM5A. GP27: SCL1, A1, PWM5B |

Pinout figure note: "Compatible with Qwiic, STEMMA QT and Grove (With conversion cable)" [DS Figure 3].

**GPIO breakout labels** (silkscreen, [DS Figure 4]): top row 0, 1, GND, 2, 3, 4, 5, GND, 6, 7, 8, 9, GND, 10–13, GND, 14, 15; bottom row USB (VBUS), SYS (VSYS), GND, EN (3V3_EN), 3V3, REF (ADC_VREF), 28, GND, 27, 26, RUN, 22, GND, 21, 20, 19, 18, GND, 17, 16.

## Rules and gotchas (for code, wiring and tutorials)
- **Pins the board's own parts use:** GP0–GP5 (status LEDs), GP18 (buzzer), GP20 (button), GP28 (RGB LED) [DS]. GP0/1, GP4/5 and GP26/27 are also on the Maker Ports [DS Figure 3].
- **Maker Ports GP0/GP1 and GP4/GP5 both map to I2C0** [DS Figure 3]. One I2C0 peripheral can be routed to only one pin pair at a time in most frameworks, so two I2C modules on those two ports either share one port (daisy-chain) or use different addresses on the same pins — or use the GP26/GP27 port (I2C1) for the second bus (derived).
- **Analog inputs on a Maker Port:** only GP26 (A0) and GP27 (A1) [DS Figure 3]. GP28 (A2) drives the RGB LED [DS].
- **UART on a Maker Port:** GP0/GP1 = UART0 (TX0/RX0); GP4/GP5 = UART1 (TX1/RX1) [DS Figure 3].
- **Status LEDs light on GP0–GP5 whenever the pin is HIGH** [DS], so I2C/UART traffic on the first two Maker Ports makes them flicker (expected, derived). Cut the LED jumper to disable them [DS].
- **GP0–GP5 and GP18 each have a 3M3 resistor to GND** (MOSFET gate pull-down) [DS-schematic]; a very weak pull-down, normally harmless (derived).
- **Button GP20 has a hardware pull-up and debounce capacitor** [DS-schematic]; reads 0 when pressed (derived). Enabling the internal pull-up in code is harmless (derived).
- **Buzzer is passive** [DS]: drive it with PWM tones; a steady HIGH gives no tone (derived).
- **RGB LED needs a WS2812B / NeoPixel driver** on GP28 [DS: WS2812B]; plain digital writes do not set colours (derived).
- **Headers on the pre-mounted version are not pre-soldered** [DS]: solder the breakout headers before using jumper wires.
- **Maker Ports are JST-SH, not Grove**: Grove modules need a conversion cable [DS].
- **Maker Port power is 3V3** [SCH, DS Figure 3] — use 3.3 V-tolerant modules (derived).

## Power and electrical limits
- Power in: USB 4.5–5.5 VDC (through the Pico's USB) or single-cell LiPo / Li-Ion 3.3–4.2 VDC [DS].
- Battery "Rechargeable via USB" [DS]. Charger MCP73831T-2ACI/OT fed from VBUS; a P-MOSFET (Q1) connects VBAT to VSYS [DS-schematic].
- Battery protection [DS]: "The battery is protected from overcharged and over discharged. If the board cannot be turned on when the battery is connected, please charge the battery to activate the battery protection circuit."
- Datasheet Table 3 values are labelled "Absolute Maximum Ratings" [DS]; no separate recommended operating table.
- Not stated: charge current, battery connector type/pitch, 3V3 current available to Maker Ports, on/off switch (none listed in [DS]).

## Software support
- No Cytron source read states supported languages or example code for this board. The board adds only passive peripherals to a Raspberry Pi Pico / Pico W, so it is programmed as a Pico / Pico W (derived).
- Code needs: PWM on GP18 (buzzer), WS2812B driver on GP28, digital input on GP20, I2C/UART/ADC on the Maker Port pins as listed above [DS].

## Compatibility and accessories
- **Host:** Raspberry Pi Pico / Pico W [DS title, Table 1]. Schematic symbol is "RPI Pico W" [DS-schematic]. Pico 2 / Pico 2 W are not mentioned in any Cytron source read (see *Needs verification*).
- **Variants:** MAKER-PI-PICO-MINI (Pico / Pico W pre-mounted, headers not pre-soldered) and MAKER-PI-PICO-MINI-NB (Pi Pico socket, no Pico) [DS]. Product page image paths show -NB and a with-Pico-W variant [PP].
- **Modules:** Qwiic / STEMMA QT modules directly; Grove modules via conversion cable [DS].
- **Battery:** single-cell LiPo / Li-Ion [DS].
- Packing list and cable bundles: not read.

## Common mistakes / troubleshooting
- **Board won't turn on from battery:** charge the battery over USB to activate the protection circuit [DS].
- **Status LEDs distracting or wasting power:** cut the GPIO LED enable jumper [DS].
- **Grove module won't plug in:** the Maker Ports are JST-SH; use a Grove conversion cable [DS].
- **No sound from buzzer with digitalWrite:** it is a passive buzzer — use PWM tones on GP18 [DS] (derived).
- **Two I2C modules on Maker Ports GP0/1 and GP4/5 conflict:** both are I2C0 [DS Figure 3]; use the GP26/27 port (I2C1) or chain on one port (derived).
- **Jumper wires loose on the breakout:** headers are not pre-soldered on the pre-mounted version [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supported host in the name | [DS] title: "Raspberry Pi Pico / Pico W" | [PP] title: "Simplifying Projects with Raspberry Pi Pico" | Not contradictory; [DS] wording lists Pico W too |

No conflicting numeric values were found between [DS], [DS-schematic] and [PP] for this board.

## Needs verification
- **Pico 2 / Pico 2 W (RP2350) compatibility** — not stated by Cytron; needs [DT].
- **Order code of the with-Pico-W variant** — product-page image paths show it but no code was given.
- **Charge current**: schematic R_PROG = 2K on MCP73831 → 500 mA by the [VEN] formula (1000/R_PROG); not stated by Cytron.
- **Battery connector type and pitch** — not stated in any Cytron source; only "+" / "−" silkscreen marks are visible [DS Figure 4].
- Digital output high level is 2.6 V min on this board [DS] (the Maker Pi Pico datasheet says 2.62 V — different product; do not copy across).
- 3V3 current budget for Maker Ports.
- Whether the -NB socket accepts both header-soldered Pico and Pico W only, or also castellated mounting.
- Supported languages / Cytron example code (product page text beyond title/stock was not provided).
- [3P] Pimoroni, The Pi Hut, RobotShop and CNX Software list this board; not used for any spec.

## Sources
- [DS] Maker Pi Pico Mini Datasheet, Rev 1.0, June 2022 (public Google Doc; read as text and exported to PDF for Figures 1, 3, 4): https://docs.google.com/document/d/14Yzc7C-3NXtMi0Cuqn2ZFWilJjBVvCIbsKoMZJ8b24Q/edit
- [DS mirror, not reachable from this session] https://core-electronics.com.au/attachments/uploads/Maker-Pi-Pico-Mini-Datasheet.pdf
- [DS Figure 3] Pinout drawing (same as product-page link): https://docs.google.com/drawings/d/e/2PACX-1vRdvCpIyX8rwWoiEK8QHufZtZLXF7Q-17HVSCCqKj5cgb1OvGnr0kA_7rC5dBFD8D_cPyaNWJxE825w/pub?w=3720&h=3462
- [DS-schematic] MAKER-PI-PICO-MINI Schematic.pdf, REV 1.0.0, 6/13/2022: https://drive.google.com/file/d/1JEdXa1Cx8yJ6E99TVwUOwOmhia3p0efa/view
- [PP] https://my.cytron.io/p-maker-pi-pico-mini-simplifying-projects-with-raspberry-pi-pico (read by coordinator 2026-10-16)
- 3D CAD (not read): https://drive.google.com/drive/folders/1JCpLU5N7C1ZYViPlxLu_2fu0D6EWRW3Q
- [3P, cross-check only] https://www.cnx-software.com/2022/10/11/maker-pi-pico-mini-battery-buzzer-gpio-leds-raspberry-pi-pico-w/
