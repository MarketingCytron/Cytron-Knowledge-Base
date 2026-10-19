# RGB LED Stick (Neopixel-compatible) by Cytron — Verified Reference

| | |
|---|---|
| Product code | `BCY-NEO-STICK-8` [PP] |
| Family | Sensors and modules |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | **No Cytron datasheet or user manual exists.** Main source: Cytron product page https://my.cytron.io/p-neopixel-rgb-led-stick-by-cytron (read by the coordinator 2026-10-19) [PP]; Cytron tutorial "Controlling RGB LED Stick with Maker Pi Pico" (Abdulrahman Alhamed, 14 May 2023) [PP: tutorial RGB Stick with Maker Pi Pico]; REKA:BIT RBT Project Kit guide and MakeCode extension as recorded in rekabit-rbt-project-kit.md [UM][GH] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = coordinator's browser read, 2026-10-19 (my.cytron.io not fetched here). The page's power and controller wording follows Adafruit NeoPixel wording and links the Adafruit NeoPixel Überguide; it is recorded exactly, not corrected. No SK6812 vendor datasheet was read. [UM]/[GH] facts for the RBT kit are taken from rekabit-rbt-project-kit.md (not re-read at source here).

## What it is
- A PCB stick carrying **8× 5050 smart RGB LEDs** in series, with mounting holes; sticks can be chained, and one microcontroller pin controls the whole chain [PP].
- Each LED has its driver inside; ~18 mA constant-current drive per LED; no external resistors needed [PP].
- "NeoPixel compatible"; **SK6812-based, compatible with WS2812B** [PP].
- Shipped with **pre-soldered header pins on the input pins** [PP].
- Also the "RGB LED Stick" in the REKA:BIT RBT Project Kit [PP of that kit; rekabit-rbt-project-kit.md].

## Specifications
| Item | Value | Src |
|---|---|---|
| LEDs | 8 addressable RGB LEDs in series, 5050 package | [PP] |
| LED type | SK6812-based, compatible with WS2812B | [PP] |
| Drive | ~18 mA constant-current drive per LED; no external resistors | [PP] |
| Supply (description) | "Power the whole thing with 5VDC (4-7V works)" | [PP] |
| Supply (pinout text) | 5V pin: "regulated supply between 5V and about 7V. More than that could harm the LED, less than 5V will either reduce brightness, or it just won't turn on" | [PP] |
| Data | Single data line, timing-specific protocol | [PP] |
| Controller requirement (page wording) | Real-time microcontroller (AVR, Arduino, PIC, mbed); "8 MHz or faster processor required" | [PP] |
| Viewing angle | 120° | [PP] |
| Red | 620–630 nm, 550–700 mcd | [PP] |
| Green | 515–530 nm, 1100–1400 mcd | [PP] |
| Blue | 465–475 nm, 200–400 mcd | [PP] |
| Dimensions | 51.10 mm x 10.22 mm x 3.19 mm | [PP] |
| Weight | 2.57 g | [PP] |
| Packing list | 1x RGB LED Stick | [PP] |
| Price | RM9.35 (10+ RM8.88, 50+ RM8.41) (Cytron product page, read 2026-10-19) | [PP] |
| Warranty | 12 months | [PP] |

## Interfaces, terminals and pin mapping
| Pin | Function | Src |
|---|---|---|
| DI | Data in | [PP] |
| 5V | Supply (see wording above) | [PP] |
| GND | Ground | [PP] |
| DO | Data out to the next stick | [PP] |

- Header pins come pre-soldered on the input side [PP]; whether the DO side has pads only is not stated.
- Maker Pi Pico tutorial: stick connected to **Pin 7 (GP7)** "and leave the white wire unconnected" [PP: tutorial RGB Stick with Maker Pi Pico].
- REKA:BIT RBT kit: stick on any REKA:BIT Grove IO port with a Grove-to-female cable; pin chosen in the `set RGB Stick at pin` block (P0, P1, P2, P13, P15) [UM][GH via rekabit-rbt-project-kit.md].

## Rules and gotchas (for code, wiring and tutorials)
- **Quote the supply wording exactly** — the page gives both "5VDC (4-7V works)" and "between 5V and about 7V … less than 5V will either reduce brightness, or it just won't turn on" [PP]. Do not invent a single min/max.
- **Initialise the strip length as 8** (RBT kit extension constant `REKABIT_RGBSTICK_LENGTH = 8`; LEDs labelled 0–7) [GH][UM via rekabit-rbt-project-kit.md].
- **MakeCode (micro:bit / REKA:BIT):** the `set RGB Stick at pin` init block must run at the start of the program; brightness 0–255 [GH][UM via rekabit-rbt-project-kit.md].
- **Data direction matters:** feed DI; DO goes to the next stick's DI when chaining [PP].
- **Arduino:** works with the NeoPixel Arduino library [PP].
- The page says it cannot be used with a Linux-based microcomputer or an interpreted microcontroller (netduino, Basic Stamp) [PP] — see Conflicts for Cytron's own CircuitPython use.

## Power and electrical limits
- Supply: as worded above [PP]. ~18 mA constant-current per LED [PP]; total stick current is not stated.
- Grove 3V3 note: Cytron's own uses power the stick from Grove ports whose supply is 3V3 on Maker Pi Pico (maker-pi-pico.md) and REKA:BIT (reka-bit.md, 300 mA total) — this sits against the page's "less than 5V will either reduce brightness, or it just won't turn on" (see Conflicts).

## Software support
- Arduino: NeoPixel Arduino library [PP]; Adafruit NeoPixel Überguide linked [PP].
- CircuitPython on Maker Pi Pico (Thonny), patterns blue/red/green and random [PP: tutorial RGB Stick with Maker Pi Pico].
- MakeCode: `pxt-rekabit-rbt-project-kit` RGB Stick blocks — set at pin, turn off, set brightness (0–255), show rainbow, show color, set pixel color, shift pixels, rotate pixels [GH via rekabit-rbt-project-kit.md].
- 3D CAD: Google Drive folder linked from the product page [PP].

## Compatibility and accessories
- Real-time microcontrollers per page: AVR, Arduino, PIC, mbed [PP].
- Cytron boards shown with it: Maker Pi Pico [PP: tutorial]; REKA:BIT with micro:bit [UM][PP of RBT kit] — used in the RBT kit's Boom Barrier Gate and Mobile Robot Car projects [UM][PP: resource hub, via rekabit-rbt-project-kit.md]. Also listed among Maker ESP32 Halloween project tutorials (Oct 2026) [PP] — details not read.
- Chaining: multiple sticks in series, one data pin [PP].

## Common mistakes / troubleshooting
- Stick dark or dim: supply below 5 V per page wording [PP]; wrong pin in code vs the wire used [UM via rekabit-rbt-project-kit.md].
- Nothing lights on a chained stick: data wired to DO instead of DI [PP, derived from pin functions].
- MakeCode program does nothing: `set RGB Stick at pin` block missing [GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply range | [PP] description "5VDC (4-7V works)" | [PP] pinout "between 5V and about 7V … less than 5V will either reduce brightness, or it just won't turn on" | Same page, both Adafruit-style; quote both; recommend 5 V |
| Low-voltage use | [PP] less than 5 V reduces brightness or won't turn on | Cytron uses on 3V3 Grove ports: Maker Pi Pico tutorial [PP: tutorial]; REKA:BIT RBT kit (Grove 3V3 per reka-bit.md [DS]) | Works in Cytron's own 3V3 setups; do not state a minimum voltage — flag for [DT] |
| Interpreted controllers | [PP] cannot be used with an interpreted microcontroller | [PP: tutorial] CircuitPython on Maker Pi Pico; [GH] MakeCode on micro:bit | Cytron tutorials show both working; avoid repeating the blanket restriction |
| Name | [PP] "RGB LED Stick" | [UM] RBT guide "Papan RGB" (RGB board); [GH] "RGB Stick" | Same part |

## Needs verification
- Minimum working supply voltage at 3.3 V (Cytron [DT] to confirm; page wording is Adafruit-derived).
- Total current at full white (not stated).
- Maker Pi Pico tutorial wiring: why the white Grove wire is left unconnected and which Grove port is used.
- Whether the DO end has header pins or pads only.
- Maker ESP32 Halloween tutorial content (pin, power) — not read.
- PCB revision, mounting-hole size/spacing.

## Sources
- [PP] https://my.cytron.io/p-neopixel-rgb-led-stick-by-cytron (coordinator read, 2026-10-19; notes in local file m-pp.md)
- [PP: tutorial] "Controlling RGB LED Stick with Maker Pi Pico", my.cytron.io, 14 May 2023 (coordinator read; URL not recorded)
- [UM][GH] via KB file rekabit-rbt-project-kit.md — https://github.com/CytronTechnologies/pxt-rekabit-rbt-project-kit
- KB files maker-pi-pico.md, reka-bit.md (Grove 3V3 supply)
