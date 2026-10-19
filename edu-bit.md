# EDU:BIT Training & Project Kit for micro:bit — Verified Reference

| Field | Value |
|---|---|
| Product code | V-EDUBIT (board code EDUBIT; reseller EDUBIT-NB) [PP]. Farnell/element14 list Manufacturer Part Number "EDUBIT-NB" [3P] |
| Family | micro:bit accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: the Farnell "datasheet" link turned out to be the full English guide book (132 pages, 4th printing May 2021) and was read as page images; power cable, power switch, INT/EXT audio switch and servo-port wiring added. Still no electrical datasheet |
| Primary source | No Cytron electrical datasheet found. Guide book **"Explore STEM & Coding with EDU:BIT"** (Cytron Technologies, © 2020, ISBN 978-967-19475-0-0, Fourth Printing May 2021; written by Cheryl Ng, SC Lim & Adrian Teo; 132 pages incl. covers) read as page images from the Farnell copy [UM-book]. Main source for specs: Cytron product page https://my.cytron.io/p-edubit-training-and-project-kits-for-microbit (read 2026-10-19) [PP]. Supporting: Lesson guide: "Learn Coding Bit by Bit with EDU:BIT Course Overview" (PDF, Cytron Drive, no revision/date) [UM]; EDU:BIT Resource Hub (Cytron Google Site) [PP: Resource Hub]; MakeCode extension pxt-edubit v1.15.0 [GH] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: [UM-book] = the English guide book PDF that Farnell hosts as its "datasheet" (https://www.farnell.com/datasheets/3685792.pdf, 102 MB, image-only; pages read visually 2026-10-19: contents, Ch.1 setup, Ch.3 Music, Ch.8 DC motor, Ch.9 servo, closing pages). It is a children's activity book with no electrical specification section. The link.cytron.io book link and GitLab gitlab.com/cytrontech/rh2t/edubit could not be fetched from here. No power-input voltage, current limit or protection threshold is stated in any Cytron source read — see *Needs verification*.

## What it is
- A micro:bit training and project kit for beginners: a board with built-in modules ("Bits"), a printed step-by-step guide book of "10+1 hands-on coding lessons", game maps and accessories, a servo motor and a DC motor [PP].
- Each guide-book chapter teaches one module through a classic childhood game (e.g. Rock Paper Scissors, Snakes and Ladders, Twister, Simon Says), with a challenge at the end of each chapter [PP][UM].
- Works out of the box: lights and a melody play on button press; no wiring needed as a training kit [PP].
- Modules can be broken off the board and reconnected with plug-and-play (Grove) cables [PP].
- Servos and DC motors are driven by a dedicated controller and power supply on the board, so servo control and music can run together [PP]. The controller is a PIC16F1937 co-processor at I2C address 0x08 (code comment in the extension) [GH].
- Three purchase options: EDU:BIT with micro:bit V2 included; without micro:bit; Classroom Pack (10x EDU:BIT, each with micro:bit V2) [PP].

## Specifications
Cytron product page "Specifications" — every row [PP]:

| Item | Value | Src |
|---|---|---|
| Piezo buzzer | 1x piezo buzzer with audio jack | [PP] |
| Sound sensor | 1x | [PP] |
| Potentiometer | 1x | [PP] |
| IR sensor | 1x | [PP] |
| RGB LEDs | 4x programmable RGB LEDs | [PP] |
| Big LEDs | 3x (traffic light: red, yellow, green) | [PP] |
| Push buttons | 2x | [PP] |
| Servo ports | 3x | [PP] |
| DC motor ports | 2x | [PP] |
| I2C port | 1x (3.3V) | [PP] |
| Dimension | 157.50 mm x 124.50 mm x 19.00 mm | [PP] |
| Co-processor | PIC16F1937, I2C slave address 0x08 | [GH] |
| Indicator LEDs | For digital and analog IO pins | [PP] |
| Warranty | 12 months | [PP] |
| Power input | The supplied USB cable splits into a micro USB plug (to the micro:bit) and a round barrel plug (to EDU:BIT); the computer's USB powers EDU:BIT through it. "Remember to power up EDU:BIT by sliding the switch to ON" | [UM-book] |
| Input voltage range, current, battery option | Not stated in any Cytron source read | — |
| Audio switch | Slide switch INT (onboard piezo buzzer) / EXT (external speakers or headphones on the audio jack) | [UM-book] |
| Motor / servo current, servo voltage | Not stated | — |
| Weight, operating temperature | Not stated | — |

## Interfaces, terminals and pin mapping
Each feature and its micro:bit IO pin is labelled on the board [PP]. Pin numbers below come from the MakeCode extension source [GH]; the board labels themselves were not read.

| Module ("Bit") | micro:bit pin / bus | How used | Src |
|---|---|---|---|
| Sound Bit (sound sensor) | P1 (analog) | `analogReadPin`, 0–1023 | [GH] |
| Potentio Bit (potentiometer) | P2 (analog) | `analogReadPin`, 0–1023 | [GH] |
| IR Bit (IR sensor) | P8 (digital) | `digitalReadPin`; event on edge | [GH] |
| RGB Bit | P13 | 4 pixels, `neopixel.create(P13, 4, NeoPixelMode.RGB)` | [GH] |
| Traffic Light Bit | P14 red, P15 yellow, P16 green | `digitalWritePin` | [GH] |
| Button Bit | In parallel with micro:bit buttons A and B | Default MakeCode Input blocks | [GH] |
| Music Bit (piezo + audio jack) | Default MakeCode Music blocks (pin not stated); INT/EXT switch selects buzzer or audio jack; volume block 0–255 | — | [GH][UM-book] |
| Servo ports S1–S3 | I2C co-processor 0x08 | registers 1–3 | [GH] |
| Servo port wiring | S = orange/yellow (signal), + = red, − = brown/black; Ch.9 plugs the servo into Servo Port 1 | — | [UM-book] |
| DC motor ports M1, M2 | I2C co-processor 0x08 | registers M1A 4, M1B 5, M2A 6, M2B 7 | [GH] |
| I2C port | 3.3V | Grove-type port | [PP] |

Co-processor register map (main.ts) [GH]: 0 revision; 1–3 servo 1–3; 4–7 M1A, M1B, M2A, M2B; 8 low-batt upper threshold; 9 low-batt lower threshold; 10 over-voltage threshold; 11 VIN; 12 power state; 13 low-batt state; 14 over-voltage state. Threshold values are not stated.

## Rules and gotchas (for code, wiring and tutorials)
- Add the EDU:BIT extension in MakeCode (search "edubit" or https://github.com/cytrontechnologies/pxt-edubit) before using Bit blocks; Music Bit and Button Bit use the built-in Music and Input blocks [GH].
- P1, P2, P8, P13, P14, P15, P16 are taken by the onboard Bits [GH] — do not reassign them in projects while those modules are attached.
- Do not put an I2C device at address 0x08 on the I2C port — the co-processor uses it [GH].
- Servos and DC motors are driven only through the co-processor via the extension's "Motors & Servos" blocks [GH]; this is how EDU:BIT lets servo control and music run together [PP].
- When the extension loads it brakes both motors and disables all servos [GH].
- The extension polls the power state every 200 ms and resets the micro:bit when the EDU:BIT power is switched from off to on [GH]. Programs restart on power-on — expected behaviour.
- Motor speed 0–255 (127 = 50% in the README example); "Brake motor" writes 0 to both A and B registers [GH]. Forward = MxA, backward = MxB [GH].
- Servo position 0–180°; the extension writes `position × 20 / 18 + 50` to the servo register. "Disable servo" stops the pulse so the servo can be turned by hand [GH].
- RGB Bit default brightness is 25 (range 0–255); set it with "set RGB pixels brightness" [GH]. Pixel index 0–3 [GH].
- On micro:bit V2 the extension sets `music.setSilenceLevel(0)` ("For V2 only") [GH].
- **Bluetooth:** "The default EDU:BIT extension in MakeCode is not compatible with Bluetooth because it includes NeoPixel/RGB dependencies, so a modified version is provided" (test code https://makecode.microbit.org/S17056-87020-85261-13593) [PP: tutorial Chapter 1: Setting Up EDU:BIT with Teachable Machine].
- Sound Bit is the board's own sound sensor on P1, not the micro:bit V2 built-in microphone [GH].

## Power and electrical limits
- "Dedicated controller and power supply"; supports up to 3 servo motors and 2 DC motors [PP].
- Kit includes "1x USB power and data cable" [PP]: a Y-cable whose micro USB end goes to the micro:bit and whose barrel plug powers EDU:BIT from the computer's USB [UM-book]. Switch EDU:BIT ON with its power switch before use [UM-book]. Input voltage range and battery option are not stated by Cytron.
- The co-processor reports power state, low-battery state, over-voltage state and input voltage (VIN register ÷ 10, in volts) through hidden extension blocks [GH]. Thresholds and protection behaviour are not stated.
- I2C port is 3.3V [PP].
- Motor/servo current limits, servo supply voltage and reverse-polarity protection: not stated.

## Software support
- Microsoft MakeCode for micro:bit + EDU:BIT extension **pxt-edubit** (https://github.com/CytronTechnologies/pxt-edubit), v1.15.0, MIT; dependencies core, neopixel (microsoft/pxt-neopixel v0.6.12), microphone; target microbit [GH]. Blocks, JavaScript or Python mode [PP].
- Extension block groups: Sound Bit, Potentio Bit, IR Bit, RGB Bit, Traffic Light Bit, Motors & Servos (DC Motors, Servos); Power blocks are hidden [GH].
- Locales in the extension: de, es, fr, it, ja, ko, pt-PT, zh-CN [GH].
- Out-of-the-box demo code: https://link.cytron.io/edubit-demo-code → MakeCode project "EDUBIT Demo Code (V1&2) with Motors Control" [PP].
- MakeCode offline app works after first load; adding extensions may need internet [PP: Resource Hub].
- Resource Hub http://link.cytron.io/edubit-resource-hub: chapter resources, sample code, downloads, free Coding Programme with Asia Pacific University (e-certificate), community roles [PP][PP: Resource Hub].
- Teachable Machine series (my.cytron.io tutorials, ch.1–6): setting up, smart object sorting, face recognition door, gesture-controlled fan, colour-controlled motor, object counter display; uses cardboard.lofirobot.com/teachable-microbit over Bluetooth with the modified extension [PP: tutorial Chapter 1: Setting Up EDU:BIT with Teachable Machine].

### Guide book chapters (10 + 1 bonus)
From the Cytron course overview [UM] (page ranges), matched with the Resource Hub chapter list [PP: Resource Hub]:

| Ch | Title (module) | Game / "Let's Play" | Application challenge | Pages |
|---|---|---|---|---|
| 1 | Hello, World! (LED matrix on micro:bit) | Fun animation | Digital announcement board | 1–11 |
| 2 | Let's Play Rock, Paper, Scissors! (buttons A/B, Button Bit) | Rock, Paper, Scissors | Attendance counter | 12–25 |
| 3 | Let's Have Some Music~ (Music Bit: piezo buzzer + audio jack) | Play Baby Shark | Game show buzzer | 26–38 |
| 4 | Win, Lose or Draw~ (Traffic Light Bit) | Win, Lose or Draw (Charade) timer and score counter | Score counter and timer | 39–47 |
| 5 | IR Digital Dice.. Let's Roll~ (IR Bit) | Snakes and Ladders with digital dice | Anti-slouch detector | 48–60 |
| 6 | Tag, You're It! (Potentio Bit) | Tag, You're It | Adjustable timer | 61–74 |
| 7 | Let's Hear the Applause! (Sound Bit) | Talent Time applause-o-meter | Classroom noise monitor | 75–87 |
| 8 | Let's Take a Spin! (DC Motor) | Finger Twister random spinner | Sound-activated fan with speed control | 88–95 |
| 9 | Penalty Shoot-Out... Goal!!! (Servo Motor) | Penalty shoot-out goalkeeper | Metronome | 96–104 |
| 10 | Mastermind, Can You Break the Secret Code? (RGB Bit) | Mastermind | Memory game training tool | 105–113 |
| Bonus | Simon Says with LEDs (radio communication) | Simon Says between players | Classroom feedback network (2+ EDU:BITs) | 114–124 |

The course-overview PDF text came out with columns interleaved; the pairing above follows the page ranges and the Resource Hub chapter order. Guide book PDFs: English, Malay, Chinese, Tamil, Thai, Japanese, Hungarian, Italian, French, German, Korean, Spanish (volunteer translations) [PP].

## Compatibility and accessories
- micro:bit V1 & V2 [GH]; the demo code is labelled "V1&2" [PP]. The with-micro:bit options ship micro:bit V2 [PP].
- Packing list (with micro:bit V2): 1x EDU:BIT board, 1x micro:bit V2, 1x step-by-step guide book, 1x USB power and data cable, 2x game maps, 2x game accessories, 7x Grove cables, 1x servo motor, 1x DC motor, 1x pulley wheel, 1x fan blade [PP]. Without micro:bit: same minus micro:bit ("This kit DOES NOT include micro:bit board") [PP]. Classroom Pack: 10 sets, each with micro:bit V2 [PP].
- Grove WiFi 8266 (separate product, own KB entry): the product page lists the tutorial "Get started with Grove WiFi 8266 on micro:bit" [PP].
- Board 3D CAD: https://drive.google.com/drive/folders/1DzkhwTZVYgaauBn16YPrb7fXiyUiZf5L [PP].
- Related Cytron micro:bit boards (separate products, not aliases): REKA:BIT, ZOOM:BIT, MOTION:BIT.

## Common mistakes / troubleshooting
- Bit blocks missing → add the pxt-edubit extension [GH].
- Teachable Machine / Bluetooth project will not pair or compile → use the modified Bluetooth-compatible extension from the Chapter 1 TM tutorial [PP: tutorial].
- Program restarts when the board is switched on → expected; the extension resets the micro:bit on power-on [GH].
- Servo can be turned by hand / does not hold → it was disabled ("Disable servo"); set a position again [GH].
- RGB LEDs look dim → default brightness is 25; raise it [GH].
- I2C sensor clashes with motors/servos → it uses address 0x08 [GH].
- Broken-off module stops working → reconnect it with the supplied Grove cables [PP].
- Warranty (1 year, manufacturing defects): report at https://my.cytron.io/support with the warranty form [PP: Resource Hub].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Product name | [PP] "Training & Project Kit" | [3P] The Pi Hut "Learning & Project Kit" | Use the Cytron name |
| Ch.3 song | Course overview / Resource Hub: "Play Baby Shark" | [UM-book] 4th printing: "I Will Follow You" | Printings differ; not a spec |
| Guide book translations | [PP] and Resource Hub Download page: 12 languages incl. French, German, Korean, Spanish | [PP: Resource Hub] Helpdesk FAQ: Malay, Tamil, Thai, Hungarian, Japanese, Simplified Chinese, Italian; "German and French are in progress" | Product page (read 2026-10-19) wins; the Helpdesk FAQ is undated and probably older |
| Board size | [PP] 157.50 x 124.50 x 19.00 mm | [3P] recantha "16 cm x 12 cm" PCB | [PP] wins |
| Teachable Machine ch.5 | Resource Hub title "Color Controlled Motor System" | its URL slug "...color-controlled-light-system" | Title used; not a spec |

## Needs verification
- **Electrical datasheet:** the Farnell "datasheet" is the guide book; no EDU:BIT electrical datasheet has been found. Ask [DT] for one (power input range, current limits, protection).
- Barrel-jack voltage range and whether a 5 V adapter or battery pack may be used instead of the USB Y-cable.
- Low-battery and over-voltage thresholds and what the board does at them (registers exist [GH]).
- DC motor and servo current limits, servo supply voltage, motor driver IC, reverse-polarity protection.
- Music Bit pin (the INT/EXT switch is now confirmed [UM-book]).
- RGB LED part number (extension uses NeoPixel mode RGB; part not stated). Co-processor PIC16F1937 is from a code comment only.
- Pin map of the I2C port and of each broken-off module's Grove connector.
- Board code "EDUBIT" and reseller code "EDUBIT-NB" ([3P] Farnell MPN). [3P] Farnell weight 0.85 kg; [3P] recantha 126-page book; [3P] recantha: servo plastic pieces and cardboard props in the box.
- Why the extension depends on the "microphone" package.
- Per-option prices (the page gives only the range).

## Sources
- [PP] Cytron product page (read by coordinator in a browser, 2026-10-19): https://my.cytron.io/p-edubit-training-and-project-kits-for-microbit — saved as /tmp/claude-0/-home-claude/89df22ce-d748-57bf-95c2-077265d94eeb/scratchpad/m-pp.md
- [UM] Lesson guide: "Learn Coding Bit by Bit with EDU:BIT Course Overview.pdf": (Cytron document — link not public)
- [PP: Resource Hub] https://sites.google.com/cytron.io/edubit-resource-hub (chapter resources, /download, /helpdesk)
- [PP: tutorial] Chapter 1: Setting Up EDU:BIT with Teachable Machine (TM): https://my.cytron.io/tutorial/chapter-1-setting-up-edubit-with-teachable-machine-tm
- [PP] Demo code: https://link.cytron.io/edubit-demo-code → https://makecode.microbit.org/51429-17321-87791-03541
- [GH] https://github.com/CytronTechnologies/pxt-edubit — README.md, pxt.json, main.ts, motors.ts, power.ts, rgb_bit.ts, sound_bit.ts, potentio_bit.ts, ir_bit.ts, traffic_light_bit.ts, test.ts via https://raw.githubusercontent.com/CytronTechnologies/pxt-edubit/master/
- [UM-book] Explore STEM & Coding with EDU:BIT (English guide book, 4th printing May 2021) — Farnell copy https://www.farnell.com/datasheets/3685792.pdf (image-only PDF, read visually 2026-10-19)
- Not readable: http://link.cytron.io/edubit-book-english ; https://gitlab.com/cytrontech/rh2t/edubit
- [3P] (cross-check only) https://uk.farnell.com/cytron/edubit-nb/programmable-board-education/dp/3942218 ; https://thepihut.com/collections/cytron/products/edu-bit-learning-project-kit-for-micro-bit ; https://www.recantha.co.uk/blog/?p=21134
