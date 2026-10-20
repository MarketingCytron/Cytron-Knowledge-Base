# Product fact sheets

## Product name
RGB LED Stick (Neopixel-compatible) by Cytron — BCY-NEO-STICK-8

## Aliases
BCY-NEO-STICK-8, RGB LED Stick (Neopixel-compatible) by Cytron, RGB LED Stick, Cytron RGB LED Stick, NeoPixel RGB LED Stick by Cytron, Cytron NeoPixel Stick

## What it is
A small PCB stick with 8 addressable 5050 RGB LEDs (SK6812-based, WS2812B-compatible) controlled through one data pin. Sticks can be chained through the data-out pin.

## Specs and functions
- LEDs: 8 addressable RGB LEDs in series, 5050 package (product page)
- LED type: SK6812-based, compatible with WS2812B; NeoPixel compatible (product page)
- Drive: ~18 mA constant-current drive per LED; no external resistors (product page)
- Supply, as worded on the product page: "Power the whole thing with 5VDC (4-7V works)"; 5V pin: "regulated supply between 5V and about 7V. More than that could harm the LED, less than 5V will either reduce brightness, or it just won't turn on" (product page)
- Data: single data line with a timing-specific protocol (product page)
- Viewing angle: 120° (product page)
- Red: 620–630 nm, 550–700 mcd (product page)
- Green: 515–530 nm, 1100–1400 mcd (product page)
- Blue: 465–475 nm, 200–400 mcd (product page)
- Dimensions: 51.10 mm x 10.22 mm x 3.19 mm (product page)
- Weight: 2.57 g (product page)
- Header pins pre-soldered on the input pins (product page)
- Total current: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Pins: DI (data in), 5V, GND, DO (data out to next stick) (product page)
- Arduino: works with the NeoPixel Arduino library; 8 MHz or faster processor required (product page)
- Controllers named on the page: real-time microcontrollers (AVR, Arduino, PIC, mbed) (product page)
- Maker Pi Pico: connect to Pin 7 (GP7) and leave the white wire unconnected; CircuitPython in Thonny (Cytron tutorial)
- REKA:BIT RBT Project Kit: on a REKA:BIT Grove IO port; MakeCode extension pxt-rekabit-rbt-project-kit, `set RGB Stick at pin` block (P0, P1, P2, P13, P15), 8 LEDs numbered 0–7, brightness 0–255 (RBT kit guide and Cytron GitHub)

## Use cases
- Blue/red/green and random colour patterns with Maker Pi Pico and CircuitPython (Cytron tutorial)
- Boom Barrier Gate and Mobile Robot Car projects in the REKA:BIT RBT Project Kit (RBT kit guide)
- Cytron tutorial: [Controlling RGB LED Stick with Maker Pi Pico](https://my.cytron.io/tutorial/controlling-neopixel-rgb-led-stick-with-maker-pi-pico)

## Known limitations
- The page says it cannot be used with a Linux-based microcomputer or an interpreted microcontroller such as netduino or Basic Stamp (product page); Cytron's own tutorials run it from CircuitPython on Maker Pi Pico and MakeCode on micro:bit
- Supply wording on the page: less than 5V will either reduce brightness or it just won't turn on, and more than about 7V could harm the LED (product page)
- Needs a timing-specific single-wire protocol, so a library or extension is needed (product page)
- Only the input pins come with headers pre-soldered (product page)

## Positioning (kept apart from specs)
- "NeoPixel compatible" (product page)

## Price band
RM9.35 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-neopixel-rgb-led-stick-by-cytron

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-neopixel-rgb-led-stick-by-cytron
