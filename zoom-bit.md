# ZOOM:BIT — Verified Reference

| | |
|---|---|
| Product code | `ZOOMBIT` — model code of the my.cytron.io page "ZOOM:BIT Robot Car Kit for micro:bit (V2 included)" (p-zoombit-robot-car-kit-for-microbit), from the Cytron tutorial shop links [PP: tutorial]. A second shop listing, "ZOOM:BIT Robot Car Kits for micro:bit" (p-zoombit-robot-car-kits-for-microbit), has code `V-ZOOMBIT` and is the one linked from the Smart AI Lens tutorials [PP: tutorial]. `ZOOMBIT-NB` (without micro:bit) appears only as RobotShop's "Manufacturer #" [3P] |
| Family | micro:bit accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). Packing lists for all five options, the ultrasonic module, the battery pack and the HuskyLens AI option are now Cytron-stated; guidebook wiring figures still not read, so it stays Medium |
| Primary source | No ZOOM:BIT datasheet exists in any source found. The kit's user manual is the **ZOOM:BIT Quick Start Guidebook** (Cytron / rero EDUteam), English PDF `ZOOMBIT-Quick-Start-Guide-Book-EN-v1.1-2022.pdf`. No revision or date is printed inside it; "v1.1, 2022" comes from the file name only. The controller board in the kit is REKA:BIT. Its electrical limits come from the **REKA:BIT Datasheet, "Simplifying Robotics with micro:bit", Rev 1.0, April 2021** (Cytron) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: [UM] = ZOOM:BIT Quick Start Guidebook v1.1 (file name). [DS] = REKA:BIT Datasheet Rev 1.0. It covers only the REKA:BIT controller board in the kit, not the kit as a whole. REKA:BIT is a separate Cytron product with its own KB entry and is **not** an alias for ZOOM:BIT. Both PDFs and the product page were read through a summarising fetch, not as raw text. Wiring diagrams in the guidebook could not be read.

## What it is
- A robot car kit for the BBC micro:bit: "ZOOM:BIT Robot Car Kit for micro:bit" [PP].
- The controller board is a **REKA:BIT** listed as "REKA:BIT (with or without micro:bit)" in the box contents [UM]. The car is built on the REKA:BIT with a Maker Line sensor, an ultrasonic sensor, 2 LED modules (headlights), 2 DC motors with wheels, a castor and a servo-driven "head" [UM].
- Comes with a step-by-step building guide and a guide book: 9 chapters + 1 bonus chapter [UM]. The product page says "10-lesson guide book" [PP]; the GitHub README says "9+1 hands-on building and coding lessons" [GH].
- Three purchase options [PP]: "ZOOM:BIT with micro:bit V2 included", "ZOOM:BIT without micro:bit", and "ZOOM:BIT Classroom Pack (10x with micro:bit V2 included)".
- Every kit "comes with all the materials needed to complete ZOOM:BIT Robot Car, as well as a printed guide book with detailed instructions and a line following track" [PP].

## Specifications
There is no ZOOM:BIT spec table. The table below is every row of the REKA:BIT datasheet's specification table, which the datasheet labels as absolute maximum ratings [DS]. Kit-level items follow.

| Item | Value | Src |
|---|---|---|
| Power input voltage (REKA:BIT) | Min 3.6 V, Max 6 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Total +3V3 output current (Grove ports) | max 300 mA | [DS] |
| Maximum DC motor current, continuous | 1 A | [DS] |
| Maximum DC motor current, peak (< 5 seconds) | 1.5 A | [DS] |
| Battery | AA Battery x4 + Battery Holder | [UM] |
| Head servo | "a 180 degree servo motor" | [UM] |
| Maker Line sensor | 5 IR sensors (S1–S5), each with an LED indicator; calibration button; line-colour switch ("DARK" for a black line) | [UM] |
| Supported micro:bit | V1 and V2 (V1 needs a Grove buzzer for sound) | [UM], [PP] |
| Warranty | 12 months | [PP] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Options and packing (with micro:bit V2):** 1x micro:bit V2, 1x REKA:BIT expansion board, 1x USB power and data cable, 1x "9+1 lessons" quick start guide book, 1x Zoom track, 1x Maker Line sensor, 1x ultrasonic sensor, 2x 10 mm LED module, 2x DC motor with wheel, 1x micro servo motor, 4x Grove to female header cable, 1x 4xAA battery holder with DC plug, 4x AA battery, 1x castor, 1x mini screwdriver, rivets, double-sided tapes [PP]. "Without micro:bit" is the same list minus the micro:bit; Classroom Pack = 10x the V2 kit [PP].
- **AI version (HuskyLens):** adds 1x set of HuskyLens and 1x Grove to Gravity cable to the same list (with or without micro:bit V2) [PP]. Page note: HuskyLens draws a lot of current, so rechargeable AA batteries are advised [PP]. Cytron tutorials: introduction/hardware set-up, face recognition, object tracking, colour recognition, tag recognition (YouTube) [PP].
- **Parts linked from the packing list:** ultrasonic sensor = Cytron "3V-5.5V SR04P Ultrasonic Ranging Module" (HC-SR04P; 3.0–5.5 V supply, about 2–450 cm at 5 V / 400 cm at 3 V, best 10–250 cm per that page) [PP: linked page]; micro servo = "Analog Micro Servo 9g 3V-6V"; AA batteries = PKCELL Heavy Duty AA (4 pcs); USB cable = Dual Output Cable USB A to 2.1 mm DC barrel and micro USB; castor = W420 steel ball castor [PP: packing-list links].
- **Guide books:** English v1.2 (2022), Malay, Chinese, Thai and Vietnamese PDFs on static.cytron.io; MakeCode extension pxt-rekabit; Resource Hub; Telegram support group [PP].
- **FAQ (page):** MakeCode for beginners and MicroPython for advanced users (marketing FAQ; no ZOOM:BIT MicroPython library named) [PP].

## Interfaces, terminals and pin mapping
| Function | micro:bit pin / channel | Notes | Src |
|---|---|---|---|
| Left drive motor | REKA:BIT motor channel M1 | `LEFT_MOTOR = MotorChannel.M1` | [GH] |
| Right drive motor | REKA:BIT motor channel M2 | `RIGHT_MOTOR = MotorChannel.M2` | [GH] |
| Motors and servos (all) | Driven by the REKA:BIT co-processor over I2C, address 0x08 | Extension comment names the co-processor "PIC16F1827". Not micro:bit GPIO | [GH] |
| Maker Line sensor | P1 (analog) | One analog value encodes the line position | [GH] |
| Ultrasonic sensor trigger | P2 | | [GH] |
| Ultrasonic sensor echo | P12 | | [GH] |
| Left headlight (LED module) | P13 | | [GH] |
| Right headlight (LED module) | P15 | | [GH] |
| RGB LEDs (on REKA:BIT) | P8 | WS2812B, user programmable [DS]. 2 LEDs, labelled "0" and "1" [UM]; `RGB_LED_LENGTH = 2` [GH] | [DS], [UM], [GH] |
| Head servo | One of the 4 REKA:BIT servo ports | Which port is not stated in any text read | [DS] ports; port used unverified |
| Grove buzzer (micro:bit V1 only) | "Port P0:P1" | "plug in a Grove buzzer to Port P0:P1 to play sounds" | [UM] |
| I2C Grove port | REKA:BIT I2C port | Suggested for a Grove OLED Display | [UM]; port listed in [DS] |

REKA:BIT board features used by the kit [DS]: power input (3.6–6 V), on/off switch, power LED, low-voltage LED (blinks below 3.6 V), over-voltage LED (on above 7 V), WS2812B RGB LEDs on P8, Grove ports (3x analog input/digital I/O, 2x digital I/O, 1x I2C), GPIO status LEDs on the Grove-port pins, motor status LEDs, DC motor terminals, 4 motor test buttons (M1A, M1B, M2A, M2B), 4 RC servo ports. The datasheet doesn't map the Grove ports to micro:bit pins.

## Rules and gotchas (for code, wiring and tutorials)
- **Pins taken by the kit** [GH]: P1 (Maker Line), P2 and P12 (ultrasonic), P13 and P15 (headlights), P8 (RGB LEDs). I2C (micro:bit I2C pins) carries motor and servo commands to the co-processor at 0x08. Don't reuse these pins for add-ons.
- **micro:bit V1 has no speaker:** sound needs a Grove buzzer on Port P0:P1 [UM, PP]. Leave out sound-expression and built-in-speaker blocks on V1 [UM].
- **Motor naming:** left = M1, right = M2 [GH]. `turn left` runs the left motor backward and the right motor forward (spin on the spot); `turn right` does the reverse [GH].
- **Speed ranges** [GH]: `move` / `turn` speed 0–255. `set motors speed` takes -255 to 255 per side (negative = reverse). `brake` brakes both motors.
- **Motor direction depends on wiring** [DS]. If the wheels don't spin in the direction the red arrows show, check and correct the DC motor connections [UM].
- **Motor test buttons** on REKA:BIT run a motor at full speed with no code (MxA forward, MxB backward) [DS]. Lift the car before pressing them.
- **Maker Line must be calibrated** before line following. It needs re-calibration only if the sensor height, the line, or the background colour changes [UM]. Set the line-colour switch to "DARK" for a black line [UM].
- **Maker Line reading** [GH]: `line detected on` far left / left / center / right / far right / all / none, from analog bands on P1. `line position` returns -100 to 100 (negative = left, 0 = center, positive = right). It returns center (0) when all sensors or no sensor see the line.
- **micro:bit orientation:** the README says to "take note of the position of the micro:bit on ZOOM:BIT robot" when mapping line position to the LED matrix. Its example draws "far left" in the right-hand column [GH].
- **Ultrasonic** [GH]: `ultrasonic distance (cm)` returns 1–255 cm. It returns 255 if the distance is over 255 cm or there is no echo. The first call starts a background reader and pauses 300 ms. Readings refresh every 200 ms (code comment cites the RCWL-9610 module). The extension applies a different timing constant on micro:bit V1 than on V2.
- **Head servo** is 180° [UM]. To fix head alignment, unscrew the head, reposition it and reattach it to the servo horn [UM].
- **Power cycle = reset:** slide the power switch to OFF and back ON to reset [UM]. The REKA:BIT extension watches the power state and calls `control.reset()` when power returns [GH].
- **Flashing:** WebUSB download needs the new Edge or Chrome browser and the latest micro:bit firmware [UM].

## Power and electrical limits
- Battery: 4 x AA in the supplied battery holder [UM]. The guidebook doesn't state a voltage or battery chemistry.
- REKA:BIT power input: 3.6–6 V [DS]. The low-voltage LED blinks below 3.6 V ("can serve as a low-battery indicator"). The over-voltage LED lights above 7 V, and **power to the servos and DC motors is cut off** [DS].
- DC motor voltage at full speed = power source voltage. Servo V+ = power source voltage [DS].
- DC motor current: 1 A continuous, 1.5 A peak (< 5 s) per channel [DS].
- Grove +3V3 total: 300 mA max [DS]. Analog input range 0–3.3 V [DS].

## Software support
- **MakeCode extension:** `zoombit`, https://github.com/cytrontechnologies/pxt-zoombit. In MakeCode, go to Extensions under the gear menu and search "zoombit" or paste the URL [GH]. Product page: "Just add ZOOM:BIT Extension and you're good to go" [PP].
- The extension depends on `pxt-rekabit` (github:cytrontechnologies/pxt-rekabit), so the REKA:BIT blocks (motors, servos, RGB LED) load with it [GH]. The guidebook refers to the "REKA:BIT" category drawer [UM].
- ZOOM:BIT block groups [GH]: Headlights (set / toggle left, right, all), DC Motors (move, turn, set motors speed, brake), Maker Line (line detected on, line position), Ultrasonic (distance in cm).
- **Text coding:** "you can easily switch into JavaScript or Python mode on MakeCode Editor" [PP]. The guidebook doesn't mention Python [UM]. No standalone MicroPython (python.microbit.org) library for ZOOM:BIT was found.
- MakeCode editor: makecode.microbit.org; MakeCode Offline App available [UM, resource hub].
- Support channel named in the guidebook: t.me/zoombit_support [UM].

## Compatibility and accessories
- micro:bit V1 and V2 [UM, PP]. V2 has a built-in speaker. V1 needs a Grove Buzzer module [UM, PP].
- Add-on suggested in the guidebook: Grove OLED Display on the I2C port [UM].
- Kit contents [UM]: Zoom Track, REKA:BIT (with or without micro:bit), Maker Line Sensor, Grove Cable x4, Ultrasonic Sensor, LED Module x2, DC Motor & Wheel x2, Screwdriver, Screw & Nut x4, Castor, Double-sided Tape x5, Power & Data Cable, Servo Motor, White Rivet x4, Black Rivet x8, AA Battery x4, Battery Holder. Items listed without a quantity are not given a count in the guidebook.
- Quick Start Guide in 5 languages [PP]; resource hub lists English, Malay, Chinese, Thai, Vietnamese.

## Common mistakes / troubleshooting
- **No sound on V1:** expected; add a Grove buzzer on Port P0:P1 [UM].
- **Wheels turn the wrong way:** swap the DC motor connections [UM, DS].
- **Line following erratic:** re-calibrate the Maker Line; check the "DARK" line-colour switch [UM].
- **Motors and servos dead but micro:bit runs:** input over 7 V triggers the over-voltage cut-off [DS]. Below 3.6 V the low-voltage LED blinks [DS].
- **Assembly:** "The wires should be facing inwards and the notch facing outwards." "Clamp the exposed wire lead, and not the insulator." [UM]
- **Head points off-centre:** re-seat the head on the servo horn [UM].
- **Program won't flash over WebUSB:** use new Edge or Chrome and update the micro:bit firmware [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| micro:bit included? | [PP] product title "ZOOM:BIT Robot Car Kit for micro:bit (V2 included)" | [PP] note "This kit does NOT come with the micro:bit board" | Depends on option: "with micro:bit V2 included", "without micro:bit", or Classroom Pack (10x with V2) [PP]. Always name the option |
| Number of lessons | [UM] 9 chapters + bonus; [GH] "9+1" | [PP] "10-lesson guide book" | Same count (9 + 1 bonus). Say "9 chapters plus a bonus chapter" |
| Vietnamese guide link | Resource hub labels a Vietnamese PDF | Its redirect points to the Chinese translation PDF | Link problem on the hub; report to the EDU team |
| Kit list wording | [UM] lists "Castor" and "DC Motor & Wheel x2" | ManualsLib copy reads "Castor DC Motor & Wheel x2" | Text-extraction merge on the mirror. Use the [UM] list |

## Needs verification
- **Product codes:** `ZOOMBIT` and `V-ZOOMBIT` are now Cytron-sourced [PP: tutorial]. Still open: per-option codes (without micro:bit — `ZOOMBIT-NB` only from RobotShop [3P]; Classroom Pack), and how the `V-ZOOMBIT` listing differs from the main page.
- **Grove port each sensor plugs into** (Maker Line, ultrasonic, both LED modules) — only shown in guidebook wiring diagrams, which could not be read. The pins above come from [GH] code.
- Whether the Grove buzzer port "P0:P1" [UM] and the Maker Line on P1 [GH] can be used together. The buzzer on V1 (MakeCode music default pin P0) has not been confirmed.
- **Which REKA:BIT servo port** (S1–S4) the head servo uses.
- Whether the kit runs from USB power alone (motors and servos), or needs the AA pack.
- Guidebook v1.2 (`ZOOMBIT-Quick-Start-Guide-Book-EN-v1.2-2022.pdf`) exists on static.cytron.io but could not be read. Check whether its contents differ from v1.1.
- How headlights "automatically turn ON when the surrounding is dark" [UM] senses light (presumably the micro:bit light-level block — not stated).
- Which ultrasonic module ships: the packing list links the SR04P (HC-SR04P) page, while a pxt-zoombit code comment names RCWL-9610 timing [GH]; confirm the part with the EDU team.
- AA battery type: the packing list links PKCELL Heavy Duty AA cells; voltage under motor load and run time are not stated.
- Per-option prices (the page shows "from RM262.50" for the default option).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Differences Between Newer and Earlier Versions of Ultrasonic Sensor HC-SR04P](https://my.cytron.io/tutorial/differences-between-newer-and-earlier-versions-of-ultrasonic-sensor-hc-sr04p) — Protip, Beginner, 2022 [PP: tutorial]
- [Remote Control ZOOM:BIT using Grove 8266 WiFi and Blynk](https://my.cytron.io/tutorial/remote-control-zoombit-using-grove-8266-wifi-and-blynk) — Tutorial, Beginner, 2021 [PP: tutorial]
- [AI with ZOOM:BIT: Introduction & Hardware Setup](https://my.cytron.io/tutorial/ai-with-zoombit-introduction--hardware-setup) — Tutorial, Beginner, 2024 (series, 6 parts) [PP: tutorial]
- [Chapter 1: Setting Up Smart AI Lens & Battery with ZOOM:BIT](https://my.cytron.io/tutorial/setting-up-smart-ai-lens-and-battery-with-zoombit) — Tutorial, Intermediate, 2025 (series, 6 parts) [PP: tutorial]
- [ZOOM:BIT with Robo Grip Mini](https://my.cytron.io/tutorial/zoombit-with-robo-grip-mini) — Project, Beginner, 2026 [PP: tutorial]
- [Getting Started with 3D Printed ZOOM:BIT](https://my.cytron.io/tutorial/getting-started-with-3d-printed-zoombit) — Tutorial, Beginner, 2025 [PP: tutorial]
- [3D Printed ZOOM:BIT with 3D Robo Grip](https://my.cytron.io/tutorial/3d-zoombit-with-robo-grip-mini) — Tutorial, Beginner, 2026 [PP: tutorial]

## Sources
- [UM] ZOOM:BIT Quick Start Guidebook, English, v1.1 (file name), public: https://static.cytron.io/download/ZOOMBIT/ZOOMBIT-Quick-Start-Guide-Book-EN-v1.1-2022.pdf
- [UM] Newer English edition, not read: https://static.cytron.io/download/ZOOMBIT/ZOOMBIT-Quick-Start-Guide-Book-EN-v1.2-2022.pdf
- [UM mirror] ManualsLib "Cytron Technologies ZOOM:BIT Assembly Instructions Manual": https://www.manualslib.com/manual/2928244/Cytron-Technologies-Zoom-Bit.html
- [DS] REKA:BIT Datasheet Rev 1.0, April 2021 (Cytron), public mirrors: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-434/pdf/cytron-rekabit-simplifying-robotics-w-microbit-datasheet.pdf · https://www.farnell.com/datasheets/3685793.pdf
- [PP] Product page (read 2026-10-16): https://www.cytron.io/p-zoombit-robot-car-kit-for-microbit · also linked: https://my.cytron.io/p-zoombit-robot-car-kit-for-microbit
- [PP] ZOOM:BIT Resource Hub: https://sites.google.com/cytron.io/zoombit-resource-hub/ (Download page: https://sites.google.com/cytron.io/zoombit-resource-hub/download)
- [GH] https://github.com/CytronTechnologies/pxt-zoombit — `README.md`, `pxt.json` (v0.1.1), `main.ts` (read via raw.githubusercontent.com)
- [GH] https://github.com/CytronTechnologies/pxt-rekabit — `README.md`, `pxt.json` (v1.2.3), `main.ts`, `power.ts`, `motor.ts`, `rgb.ts`
- [3P] RobotShop: https://www.robotshop.com/products/zoombit-robot-car-kit-for-microbit-w-o-microbit
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
