# Product fact sheets

## Product name
Maker Nano RP2040 Getting Started Bundles

## Aliases
V-MN2040, Maker Nano RP2040 Getting Started Bundles, Maker Nano RP2040 Getting Started Kit, Maker Nano RP2040 Getting Started With Blynk IoT, Maker Nano RP2040 Blynk IoT Bundle

## What it is
Two beginner bundles around the Cytron Maker Nano RP2040 board: a Getting Started Kit of breadboard electronics for the Arduino-IDE lessons, and a Getting Started With Blynk IoT variant that adds a Grove WiFi 8266 for Blynk IoT lessons. Each is paired with a Cytron Getting Started Google Doc.

## Specs and functions
- Product code: V-MN2040
- Variants: Getting Started Kit; Getting Started With Blynk IoT
- Controller board: Maker Nano RP2040 (MAKER-NANO-RP2040) — board specs are in the Maker Nano RP2040 fact sheet
- Wi-Fi module (Blynk variant): Grove WiFi 8266, Ai-Thinker ESP-12F module preloaded with Espressif ESP-AT firmware (doc wording "v2.20")
- Components used in "Getting Started With Maker Nano RP2040": 1x Maker Nano RP2040 (MAKER-NANO-RP2040), 1x Breadboard 8.5x5.5cm 400 holes (BD-BB-0508), 1x 40-Way 10cm Dupont Jumper Wire (WR-JW-4010MM), 1x Finger Adjust Preset 10K (RS-MP3386-10K), 2x LED 5mm Green (DS-LED-5NG), 2x LED 5mm Yellow (DS-LED-5NY), 2x LED 5mm Red (DS-LED-5NR), 1x DIY 4 Blades 56mm Motor Propeller Blue (HD-PROP-4B), 1x 3V Miniature Brush Motor with wire leads (MO-300CA-11440), 1x Transistor 2N2222 (TR-2N-2222), 10x Resistor 0.25W 5% 220R (RS-025W-220R), 1x LDR Small (SN-LDR-S), 1x Diode 1N4007 (DI-1N4007), 1x USB Micro B Cable (WR-USB-UB), 1x Resistor 0.25W 5% 10K (RS-025W-10K)
- Components used in "Getting Started With Maker Nano RP2040 And Blynk IoT": same list without the 10K resistor; the Grove WiFi 8266 used in every lesson is not in that table
- Packing (Getting Started): Maker Nano RP2040 with 2 Grove-to-JST-SH cables, 400-hole breadboard, 40-way jumper wires, 10K finger preset, 2 each green/yellow/red LEDs, propeller, 2–6 V motor, 2N2222, 10 × 220R, LDR, USB micro-B cable, 1N4007 (product page)
- Packing (Blynk IoT): the same plus a Grove WiFi 8266 module and a Grove cable (product page)
- Getting Started doc lessons: 1 LED Blink, 2 Siren, 3 Digital Input, 4 Analog Input, 5 Light Dependent Resistor, 6 Temperature Sensor, 7 DC Motor, 8 Neopixel; projects: 1 Knight Rider, 2 Interactive Traffic Light, 3 Temperature Alarm, 4 Light Theremin
- Blynk IoT doc lessons: 1 Getting Connected, 2 Simple LED Control, 3 Push Button As Input, 4 Analog Input, 5 Temperature Sensor, 6 Neopixel Color, 7 Motor Speed Controller, 8 Going Mobile; Chapter 3 Projects has no content
- Blynk setup in the doc: create a Blynk account, new template "Maker Nano RP2040 IoT" (hardware Arduino, connection WiFi), add a device from the template, copy its Template ID / Device Name / Auth Token into the sketch
- Pins used by the lesson code: LED D2; buzzer pin 22; push button pin 20; potentiometer A0 (Getting Started) or A3 (Blynk); LDR A0; NeoPixels pin 11; DC motor PWM pin 2 through a 2N2222; Blynk-controlled LED 7; Knight Rider pins 16, 19, 17, 9, 8, 7, 6, 5, 4, 3
- Grove WiFi connection: Maker Port (code comment "Maker port [0, 1]"), Serial1 at 115200 baud
- Warranty: [NOT STATED] (blank on the product page)
- Dimensions, weight: [NOT STATED]

## Interfaces and compatibility
- Software: Arduino IDE with the arduino-pico board package (board "Cytron Maker Nano RP2040"); hold BOOT while plugging in for the first upload
- Libraries: Blynk by Volodymyr Shymanskyy 1.1.0, BlynkESP8266 (ESP8266_Lib.h, BlynkSimpleShieldEsp8266.h), Adafruit_NeoPixel, WS2812FX, pitches.h
- IoT platform: Blynk web dashboard and Blynk mobile app
- Grove WiFi 8266 plugs into a Maker Port through the JST-SH to Grove conversion cable
- Power: USB Micro B cable; no battery in the component lists
- Product page links: Maker Nano RP2040 datasheet, GitHub MAKER-NANO-RP2040, 3D CAD, tutorials (Blynk IoT, Grove gas sensor MQ9B, Maker Line)

## Use cases
- Getting started with Maker Nano RP2040 in the Arduino IDE (LED, buzzer, button, analog input, LDR, temperature, DC motor, NeoPixel)
- Getting started with Maker Nano RP2040 and Blynk IoT (LED control, push button, analog input, temperature chart, NeoPixel colour, motor speed, mobile dashboard)
- Classic projects: Knight Rider, Interactive Traffic Light, Temperature Alarm, Light Theremin

## Known limitations
- If communication with the Grove WiFi fails, the 3.3V supply is not enough to power the ESP8266; the doc says to connect its power to 5V instead
- Blynk code comment: do not send more than 10 values per second
- The Blynk doc's Chapter 3 Projects is empty
- The Getting Started doc's project objectives cite wrong lesson numbers, and its Light Theremin code calls noTone(8) while the buzzer is on pin 22
- The Blynk doc's NeoPixel lesson declares 30 pixels although the board has 2
- Wi-Fi credentials and the Blynk Template ID / Auth Token in the sketches must be replaced with your own
- Exact packing list per variant is not stated in the page text read

## Positioning (kept apart from specs)
- "Maker Nano RP2040 is created to simplify digital making and troubleshooting" (Getting Started doc)

## Price band
RM58.00–RM88.52 across 2 variants (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-nano-rp2040-getting-started-kits

## Datasheet
https://docs.google.com/document/d/1yqR88btul39hZ77OgUMRrg-d0Z-e3xlgVlNHLoHSLzY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1T3FAROtD-uECHmBquAbhmKK9bxdzDWIQn_PhV93oKSo/edit
