# Cytron Product Knowledge Base

Verified product facts for **Cytron-brand products**, written for AI agents (tutorial, article and script writers) and for the people who check their output. Every fact is tagged with its source; anything a source doesn't state is marked as not stated rather than guessed.

**Start here:** read this index, then load only the product files a task needs.

**Scope: Cytron-brand products only.** Third-party boards and modules that Cytron resells are not covered here.

This is the public edition. Internal working notes (internal document links, pricing sources, unreleased products and the open-issues log) are kept privately by the Cytron marketing team.

## Rules for any agent using this KB

1. **Only state a spec that is in a product file.** If it isn't there, say it's unconfirmed — never fill the gap from memory or a reseller page.
3. **Read the *Conflicts* and *Needs verification* sections** before writing about a product. Anything listed under *Needs verification* must not appear as fact in published content.
4. **Pin rules are hard rules.** Code and wiring must follow each file's "Pin rules and gotchas".
6. **Dated facts** (price, stock, store list) must be re-checked on the live page before going public.

## How the KB is arranged (two layers)

| Layer | Folder | Format | Use it for |
|---|---|---|---|
| **1. Product fact sheets** | `fact-sheets/` | Cytron Content Hub "Product fact sheets" form: 13 fixed headings, source-only facts, `[NOT STATED]` where the source is silent | Pasting into the Content Hub; marketing, scripts and articles; the first thing any agent reads |
| **2. Detailed references** | this folder (`<product>.md`) | Source-tagged reference with pin maps, conflicts and *Needs verification* | Writing code, wiring and tutorials; checking where a fact came from |

`fact-sheets/ALL-fact-sheets.md` holds every sheet in one file, ready to paste. A fact sheet must never say more than its detailed reference. When a reference changes, update the matching fact sheet in the same edit.

Fact sheet rules (from the Content Hub form): use only what the source states; keep numbers, units and names exactly; `[NOT STATED]` for anything missing; keep every heading in order; keep every stated limitation; marketing language only under *Positioning*; when product page and datasheet disagree give both with their source; price only if a source states one; each alias belongs to one product only.

## Products

### Maker ESP32 family (ESP32 ecosystem)

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker ESP32 | [`maker-esp32.md`](maker-esp32.md) | `MAKER-ESP32` | ESP32 (WROOM-32E-N8) | Active, launched Sep 2026 | **High** |
| Robo ESP32 | [`robo-esp32.md`](robo-esp32.md) | `ROBO-ESP32` | None onboard — hosts a 30-pin NodeMCU ESP32 / Maker ESP32 | Active (Datasheet Rev 1.1, Feb 2026) | **Medium** |
| Maker Feather AIoT S3 | [`maker-feather-aiot-s3.md`](maker-feather-aiot-s3.md) | `MAKER-FEATHER-AIOT-S3` (+`-H`) | ESP32-S3 (WROOM-1-N8R8) | Active | **Medium-high** |

### Arduino-compatible boards

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker UNO | [`maker-uno.md`](maker-uno.md) | `MAKER-UNO` | ATmega328P + CH340G | User's Manual Rev 1.0, Dec 2017 (no datasheet) | **Medium** |
| Maker UNO Plus | [`maker-uno-plus.md`](maker-uno-plus.md) | `MAKER-UNO-PLUS` | ATmega328P + **FT231X** (not CH340) | User's Manual Rev 1.0, Oct 2018 (no datasheet) | **Medium** |
| Maker Nano | [`maker-nano.md`](maker-nano.md) | `MAKER-NANO` | Not stated by Cytron (resellers: ATmega328P + CH340C) | Datasheet Rev 1.0, Jun 2020 | **Medium-low** |
| Cytron UNO | [`cytron-uno.md`](cytron-uno.md) | `CT-UNO` | ATmega328P + **FT231X** | User's Manual V1.0, Nov 2014 (no datasheet) | **Medium-high** |
| Cytron UNO Special Edition | [`cytron-uno-se.md`](cytron-uno-se.md) | `CT-UNO-SE` | Not stated for SE | Shares the CT-UNO manual, which never mentions SE | **Low** |
| Maker Uno RP2040 | [`maker-uno-rp2040.md`](maker-uno-rp2040.md) | `MAKER-UNO-RP2040` | RP2040, 2 MB flash | Datasheet Rev 1.0, Feb 2024 | **Medium-high** |
| Maker Nano RP2040 | [`maker-nano-rp2040.md`](maker-nano-rp2040.md) | `MAKER-NANO-RP2040` | RP2040 | Datasheet Rev 1.1, Jul 2024 | **Medium** |
| Robo Uno Shield | [`robo-uno-shield.md`](robo-uno-shield.md) | `SHIELD-ROBO-UNO` | None — shield for UNO-form-factor boards | Datasheet Rev 1.0, Feb 2025 | **Medium** |

Arduino-board notes for every agent:
- **Maker UNO has no DC jack and no VIN** — USB Micro-B 4.8–5.2 V only. Select "Arduino Uno" in the IDE; CH340 driver needed.
- **Maker Uno RP2040 is 3.3 V logic** — only 3.3 V-compatible UNO shields; power from USB-C or 1-cell LiPo (3.6–6 V); code uses GP numbers, not UNO D-numbers.
- **Robo Uno Shield:** 3.6–6 V single-cell input only; cannot be powered from the Arduino VIN pin; its micro-USB charges/powers the shield only (no code upload). Follow Cytron's code for motor pins (`CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);`) until the design team resolves the datasheet conflict. Grove 4 and the Maker Port share A4/A5; buttons D2/D3 are the Grove 6 pins.
- **USB-serial chips differ:** Maker UNO = CH340; **Maker UNO Plus and Cytron UNO = FTDI FT231X** (use the FTDI driver, not Maker UNO's CH340 steps). Maker Nano's chip is not stated by Cytron.
- **Maker UNO Plus is USB-only** (4.8–5.2 V; no DC jack, no Vin, no 5 V regulator); button D2 needs `INPUT_PULLUP`; buzzer D8 with mute switch; LEDs on pins 2–13.
- **Maker Nano power:** Vin 7.0–30.0 V, but the 5V pin gives only **100 mA** and 3V3 only **50 mA** (including the board's own use) — never copy Maker UNO's 500 mA. D2–D13 LEDs light whenever the pin is high (cut a trace to disable).
- **Cytron UNO:** DC jack 7–15 V recommended (6–20 V absolute); 5 V regulator 1 A max only stated "with Vin at 12V"; 3.3 V 500 mA; select "Arduino Uno"; one user LED (D13), no button or buzzer. **Never describe the Special Edition as identical** or invent what is special about it.

### Raspberry Pi Pico, RP2040 and RP2350 boards (Robo, Maker Pi, MOTION, EDU PICO)

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Robo Pico | [`robo-pico.md`](robo-pico.md) | `ROBO-PICO` | None onboard — hosts a Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Apr 2023 | **Medium** |
| EDU PICO V2 | [`edu-pico-v2.md`](edu-pico-v2.md) | `EDU-PICO2` (`EDU-PICO2-NB` = no Pico) | Raspberry Pi Pico 2 W | Datasheet Rev 1.1, Jun 2026 | **Medium** |
| Maker Pi RP2040 | [`maker-pi-rp2040.md`](maker-pi-rp2040.md) | `MAKER-PI-RP2040` | RP2040 soldered on (no Pico socket) | Datasheet Rev 1.2, Jan 2022 | **Medium-high** |
| Maker Pi Pico | [`maker-pi-pico.md`](maker-pi-pico.md) | `MAKER-PI-PICO` (`MAKER-PI-PICO-NB` = Maker Pi Pico Base, no Pico) | Raspberry Pi Pico soldered on | Datasheet Rev 1.2, Mar 2021 | **Medium-high** |
| Maker Pi Pico Mini | [`maker-pi-pico-mini.md`](maker-pi-pico-mini.md) | `MAKER-PI-PICO-MINI` (`-NB` = socket, no Pico) | Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Jun 2022 | **Medium-high** |
| MOTION 2350 Pro | [`motion-2350-pro.md`](motion-2350-pro.md) | Not stated (mirrors use `MOTION-2350-PRO`) | RP2350 | Datasheet **Rev 2.0, Sep 2025** | **Medium** |

Pico / RP2040 / RP2350 notes for every agent:
- **MOTION 2350 Pro Rev 2.0 motors are 5 A continuous / 10 A peak per channel**, with over-current, 150 ℃ thermal and >18 V input shutdown. 3 A (and "no over-current protection") is the Rev 1.0 board — don't use 3 A for the current board. Motors GP8–GP15, servos GP0–GP7, buttons GP20/GP21, buzzer GP22, 2 RGB LEDs GP23; Arduino `LED_BUILTIN` = GP2 (a servo pin). Never publish the datasheet's "VIN = VADC / 6.1" until the design team confirms it.
- **Maker Pi RP2040 brake/coast:** High/High = coast, Low/Low = brake (datasheet). In CircuitPython `throttle = 0` coasts and `throttle = None` brakes — the opposite of Cytron's demo comments. Power 3.6–6 V (USB, LiPo or VIN); motor/servo voltage = input voltage.
- **Maker Pi Pico is USB-powered only** (4.5–5.5 V; no battery or VIN). GP18 drives both the buzzer and the left audio channel (mute the buzzer when using the jack); audio is not amplified. RGB: Maker Pi RP2040 = 2× WS2812B on GP18; Maker Pi Pico = 1× WS2812B on GP28.
- **Maker Pi Pico Mini Maker Ports are JST-SH (Qwiic/STEMMA QT)**, not Grove (Grove needs a conversion cable); the GP0/GP1 and GP4/GP5 ports both sit on I2C0. No audio jack, microSD, ESP-01 socket or mute switch (unlike Maker Pi Pico).

### micro:bit accessories

| Product | File | Code | Role | Primary source | Confidence |
|---|---|---|---|---|---|
| MOTION:BIT | [`motion-bit.md`](motion-bit.md) | `MOTION-BIT` | Motor + servo expansion board, 3.6–6 V | Datasheet Rev 1.0, Feb 2023 | **Medium** |
| MOTION:BIT Pro | [`motion-bit-pro.md`](motion-bit-pro.md) | `MOTION-BIT-PRO` | Motor + servo expansion board, 7–12 V | Datasheet Rev 1.0, Apr 2024 | **Medium** |
| SUMO:BIT | [`sumo-bit.md`](sumo-bit.md) | Not stated | Sumo robot controller; needs 2× MD13S | Datasheet Rev 1.0, Dec 2024 (RobotShop mirror) | **Medium** |
| REKA:BIT | [`reka-bit.md`](reka-bit.md) | Not stated (resellers: `REKABIT-NB`) | Robotics expansion board, 3.6–6 V | Datasheet Rev 1.0, Apr 2021 | **Medium** |
| ZOOM:BIT | [`zoom-bit.md`](zoom-bit.md) | Not stated | Robot car kit built on REKA:BIT | Quick Start Guidebook v1.1, 2022 (no datasheet) + REKA:BIT datasheet | **Medium** |

micro:bit notes for every agent:
- **Motors and servos on MOTION:BIT, MOTION:BIT Pro, REKA:BIT and SUMO:BIT are driven over I2C (P19/P20) by an on-board chip**, not by micro:bit GPIO: MOTION:BIT PCA9685 at 0x40; REKA:BIT PIC16F1827 at 0x08 (an I2C Grove device must not use 0x08); SUMO:BIT RP2040 co-processor at 0x09.
- **REKA:BIT servo/motor voltage is the raw battery voltage** (not regulated 5 V); above 7 V it cuts servo and motor power; below 3.6 V it only blinks an LED. MOTION:BIT Pro servo power is jumper-selected 5 V or VIN (VIN can damage servos).
- **SUMO:BIT USB-C is for its own firmware only**, not for programming. Opponent sensors P12–P16 read LOW on detection; edge sensors P0/P1 are analog.
- **ZOOM:BIT uses a REKA:BIT.** micro:bit V1 has no speaker (sound needs a Grove buzzer; sound-expression blocks are V2 only). The micro:bit is only included in some purchase options.
- **MakeCode extensions:** `motionbit` (also serves MOTION:BIT Pro), `rekabit`, `sumobit`, `zoombit`. "Python" means MakeCode's Python mode unless a file says otherwise.

### Cytron sumo robot controllers

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker Mini Sumo Controller | [`maker-mini-sumo.md`](maker-mini-sumo.md) | `MAKER-MSUMO` | ATmega328P | Active (Datasheet Rev 1.0, Nov 2019) | **Medium-high** |
| URC10 | [`urc10.md`](urc10.md) | `URC10` | Not stated by Cytron | Datasheet Rev 1.0, Mar 2019 + User's Manual V1.2, Apr 2019 | **Medium** |
| IR Sumo Start | [`ir-sumo-start.md`](ir-sumo-start.md) | `IR-SUMO-START` | — (IR start module) | Datasheet Rev 1.0, Apr 2025 | **Medium-high** |

### Sensors

| Product | File | Code | Output | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Line | [`maker-line.md`](maker-line.md) | `MAKER-LINE` | 5 digital (high = line) + 1 analog; 3.0–5.5 V | Datasheet Rev 1.0, Jul 2019 | **Medium-high** |
| Maker Object | [`maker-object.md`](maker-object.md) | `MAKER-OBJECT` | IR object sensor, digital **active LOW**; 4.5–5.5 V | Datasheet Rev 1.0, Dec 2019 | **Medium-high** |

Sensor notes for every agent:
- **Maker Line:** digital outputs go HIGH when the line is detected; which colour counts as the line is set by the Light/Dark switch. Analog below 0.1×Vcc = line not found, above 0.9×Vcc = cross detected (not "far left / far right"). 4–40 mm sensing height is stated only at VCC = 5 V, black line on white. Calibrate: hold button >2 s, sweep across the line, press again.
- **Maker Object:** range is 40–140 cm on white A4 but only 15–60 cm on black A4 — never write "up to 140 cm" alone. Digital detect/no-detect only (no distance value); 5 V supply; output high is VCC − 0.5 V to VCC, so don't wire it straight into a 3.3 V-only GPIO without checking. Not a Grove/Maker Port connector.

### Cytron motor drivers

| Product | File | Code | Rating (per datasheet) | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Drive | [`maker-drive.md`](maker-drive.md) | `MAKER-DRIVE` | 2 ch, 2.5–9.5 V, 1 A cont / 1.5 A peak (<5 s) | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD3A | [`mdd3a.md`](mdd3a.md) | `MDD3A` | 2 ch, 4–16 V, 3 A cont / 5 A peak (<5 s) | Datasheet Rev 1.0, Mar 2019 | **Medium** |
| MD10C | [`md10c.md`](md10c.md) | `MD10C` (Rev 3.0) | 1 ch, 5–30 V, 13 A cont / 30 A peak (≤10 s) | User's Manual Rev3.0 V1.0, Aug 2018 (no datasheet) | **Medium** |
| MD13S | [`md13s.md`](md13s.md) | `MD13S` | 1 ch, 13 A, current limit 30 A; logic ≤5.5 V | User's Manual V1.1, Jun 2018 (no datasheet) | **Medium** |
| MD20A | [`md20a.md`](md20a.md) | `MD20A` | 1 ch, 6–30 V, 20 A cont / 60 A peak (current-limited, no duration); logic 1.5–15 V | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD10A | [`mdd10a.md`](mdd10a.md) | `MDD10A` (Rev 2.0) | 2 ch, 5–30 V, 10 A cont / 30 A peak (≤10 s) per ch | User's Manual V2.0, Jun 2017 (no datasheet) | **Medium-high** |
| MDD20A | [`mdd20a.md`](mdd20a.md) | `MDD20A` | 2 ch, 6–30 V, 20 A cont / 60 A peak (current-limited) per ch | Datasheet Rev 1.0, Jul 2020 | **Medium-high** |
| MD25HV | [`md25hv.md`](md25hv.md) | `MD25HV` | 1 ch, 7–58 V, 25 A cont / 60 A peak (current-limited); no locked-antiphase | Datasheet Rev 1.0, Jan 2019 | **Medium-high** |
| MDDS10 SmartDriveDuo-10 | [`mdds10.md`](mdds10.md) | `MDDS10` | 2 ch, 10 A cont / 30 A peak (≤1 s) | User's Manual V1.0, Jun 2015 (no datasheet) | **Medium** |
| MDDS30 SmartDriveDuo-30 | [`mdds30.md`](mdds30.md) | `MDDS30` | 2 ch, 7–35 V, 30 A cont / 80 A peak (≤1 s) per ch | User's Manual Rev 1.2, Sep 2023 (no datasheet) | **Medium-high** |
| MDDS60 SmartDriveDuo-60 | [`mdds60.md`](mdds60.md) | `MDDS60` | 2 ch, 10–45 V, 60 A cont / 100 A peak (≤1 s) per ch | User's Manual Rev 1.1, Jul 2019 (no datasheet) | **Medium** |
| Enhanced SmartDrive40 | [`smartdrive40.md`](smartdrive40.md) | `MDS40B` | **1 ch**, 40 A cont / 80 A peak (≤1 s) | User's Manual Rev 1.1, Jul 2023 (no datasheet) | **Medium-high** |
| MDDRC5 | [`mddrc5.md`](mddrc5.md) | `MDDRC5` | 2 ch R/C, 7–30 V, 5 A cont / 20 A peak (<1 s) per ch | Datasheet Rev 1.0, Mar 2026 | **Medium-high** |
| MDDRC10 | [`mddrc10.md`](mddrc10.md) | `MDDRC10` | 2 ch R/C, 7–30 V, 10 A cont / 30 A peak (current-limited) per ch | Datasheet Rev 1.0, Aug 2020 | **Medium-high** |
| iMD16 | [`imd16.md`](imd16.md) | `IMD16` | 1 ch, 16 A cont / 30 A peak (<10 s), no current limit | Datasheet Rev 1.0, Apr 2026 | **Medium-high** |
| SHIELD-2AMOTOR | [`shield-2amotor.md`](shield-2amotor.md) | `SHIELD-2AMOTOR` | 2 ch Arduino shield, 5–26 V, **0.8 A cont** / 2 A peak | User's Manual V1.1, Feb 2015 | **Medium** |
| SHIELD-3AMOTOR | [`shield-3amotor.md`](shield-3amotor.md) | `SHIELD-3AMOTOR` | 2 ch Arduino shield, 7–30 V, **1.2 A cont** / 3 A peak (≤1 s) | User's Manual Rev 1.0, Apr 2017 | **Medium** |
| FD04A | [`fd04a.md`](fd04a.md) | `FD04A` (Rev 2.0) | **4 ch**, 7–15 V, 1.5 A cont / 2.5 A peak, L298P | User's Manual V1.2, Jun 2025 | **Medium** |
| MD10-POT | [`md10-pot.md`](md10-pot.md) | `MD10-POT` | 1 ch, 7–30 V, 10 A / 30 A peak (<10 s); pot + switch or PWM/DIR | Datasheet Rev 1.0, Oct 2018 | **Medium** |
| SHIELD-MD10 | [`shield-md10.md`](shield-md10.md) | `SHIELD-MD10` (Rev 2.0, "R2") | 1 ch Arduino shield, 7–30 V (abs-max table says 25 V), 15 A peak (10 s) | User's Manual (Rev 2.0 board) V1.0, Jun 2015 | **Medium** |
| SHIELD-MDD10 | [`shield-mdd10.md`](shield-mdd10.md) | `SHIELD-MDD10` | 2 ch Arduino shield, 7–30 V, 10 A / 30 A over-current limit (temperature-dependent) | Datasheet Rev 1.0, May 2019 | **Medium** |
| HAT-MDD10 | [`hat-mdd10.md`](hat-mdd10.md) | `HAT-MDD10` | 2 ch Raspberry Pi HAT, 6–24 V, 10 A / 30 A (10 s) | User's Manual V1.0, Mar 2017 | **Medium** |
| MD30C | [`md30c.md`](md30c.md) | `MD30C` (Rev 2.0) | 1 ch, 5–30 V, 30 A cont / 80 A peak (≤1 s) | User's Manual V1.4, Dec 2017 (no datasheet) | **Medium-high** |
| MDS160A SmartDrive160 | [`mds160a.md`](mds160a.md) | `MDS160A` | 1 ch, 8–28 V, 160 A cont / 175 A (2 min) / 190 A (1 min) | User's Manual V1.0, Aug 2014 (no datasheet) | **Medium-high** |

Motor-driver notes for every agent:
- **No reverse-polarity protection** on MD10C, MD13S, MD20A, MDD10A, MDD20A, MD25HV, MDDS10, MDDS30, MDDS60, MDS40B, MDDRC10 (Maker Drive, MDD3A and MDDRC5 do have it).
- **Over-current:** only MD13S ("current limiting at 30A"), MD20A, MDD20A, MD25HV, MDDRC10, MDDRC5 and MDDS30 state current limiting; never claim it for the others. Where a peak is current-limited (MD20A, MDD20A, MD25HV, MDDRC10) no peak duration is stated — don't invent one.
- **SmartDriveDuo serial:** MDDS30's packetized start-up byte is 0x80 (128); MDDS10/MDDS60 use 0x55. Cytron's Arduino library header byte (0x85) contradicts all three manuals.
- **MDS40B (Enhanced SmartDrive40) drives one motor** — a two-motor robot needs two boards (Mixed Left + Mixed Right).
- **Switching power supplies:** MDD10A, MDDS10 and iMD16 documents warn about regenerated current / back-EMF — use a battery, or a battery of the same voltage in parallel (MDDS10, MDD10A), or bulk capacitors / TVS (iMD16).
- **Brake vs coast differs by board.** Both inputs LOW = brake on Maker Drive, MDD3A and Robo Pico; both HIGH = coast on Maker Drive but brake on MDD3A. PWM LOW = brake on MD10C, MDD10A, iMD16. Check each file.
- **Control mode:** Maker Drive and MDD3A are two-PWM (CytronMotorDriver `PWM_PWM`), not PWM+DIR.
- **MDDRC5:** peak is 20 A for <1 s (product page says <5 s); its 5 V RC-header pin is for the receiver only (500 mA) — never power a servo from it; USB-C does not power the motors.
- **Shield/HAT drivers (2026-10-16 batch):** the "3A"/"2A" in SHIELD-3AMOTOR / SHIELD-2AMOTOR are **peak** ratings — continuous is 1.2 A / 0.8 A. Both use D4–D7 for motors: `CytronMD motor1(PWM_DIR, 5, 4); motor2(PWM_DIR, 6, 7);` (the library example's 3/4/9/10 pins don't match). SHIELD-3AMOTOR above 12 V needs the PWRIN–Vin link cut (voids warranty).
- **SHIELD-MDD10 powers the Arduino by default** (5 V buck, 500 mA; cut a jumper to disable); **SHIELD-MD10 does not** (power the Arduino first). HAT-MDD10 uses fixed BCM pins PWM1 GPIO12, DIR1 GPIO26, PWM2 GPIO13, DIR2 GPIO24.
- **Peak-duration differs:** MD30C 80 A ≤1 s; MD10-POT 30 A <10 s; SHIELD-MDD10 30 A is a temperature-dependent over-current limit with no duration; MDS160A 190 A for 1 min / 175 A for 2 min. MD10-POT logic high is 3–30 V; MD30C and MDS160A ≤5.5 V.
- **MDS160A** reads its DIP-switch mode only at power-up (power-cycle after changing); its +5V pin is a 1 A output — never connect another 5 V source; a supply that can't absorb regenerated current needs a same-voltage battery in parallel or the driver "will be destroyed permanently". MD30C: battery on the motor port burns the MOSFETs (not covered by warranty). Reverse-polarity protection is stated for MD30C and FD04A only in this batch; SHIELD-3AMOTOR has none.

### Raspberry Pi boards, HATs and accessories

| Product | File | Code | For | Primary source | Confidence |
|---|---|---|---|---|---|
| Industrial IO HAT+ | [`industrial-io-hat-plus.md`](industrial-io-hat-plus.md) | `HAT-IND-AG` | Raspberry Pi 5 only | Datasheet Rev 1.0, Sep 2025 | **Medium-high** |
| Maker pHAT | [`maker-phat.md`](maker-phat.md) | `HAT-MAKER` | Raspberry Pi 3B/3B+, Zero/W/WH (manual) | User's Manual Rev 1.10, Feb 2019 (no datasheet) | **Medium** |
| Maker Hat Base | [`maker-hat-base.md`](maker-hat-base.md) | `MAKER-HAT-BASE` | Raspberry Pi 400 (page also shows Pi 3/4) | Datasheet Rev 1.0, Sep 2021 | **Medium-high** |
| CM4 Maker Board | [`cm4-maker-board.md`](cm4-maker-board.md) | `MAKER-CM4` | Raspberry Pi CM4 (product page title now says CM4/CM5) | Datasheet Rev 1.2, Oct 2023 | **Medium** |

Raspberry Pi board notes for every agent:
- **CM4 Maker Board:** the 4 USB ports need `dtoverlay=dwc2,dr_mode=host` (USB host is off by default on CM4). M.2 is NVMe 2230/2242 only — no SATA. microSD works only with CM4 Lite. Both power buttons must be pressed together. Left audio GPIO19 (shared with the buzzer — use the mute switch), right GPIO18. **Do not claim CM5 support** until the design team confirms it.
- **Maker pHAT:** SW2 is **GPIO16** (the manual's feature list says 19 — wrong; 19 is an LED). Don't name its USB-serial chip or driver until the schematic is checked. Serial console needs `enable_uart=1`, 115200 baud.
- **Maker Hat Base:** buttons GPIO17/22/23/27 active low (enable pull-up); fixed-tone buzzer on GPIO26 behind a mute switch; takes 5 V from the Pi (no own input); 3.3 V rail 800 mA max.

### IRIV industrial series

| Product | File | Code | Processor | Primary source | Confidence |
|---|---|---|---|---|---|
| IRIV PiControl CM4 | [`iriv-picontrol-cm4.md`](iriv-picontrol-cm4.md) | `IRIV-PICL` | Raspberry Pi CM4 (BCM2711) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.3, Nov 2025 | **Medium-high** |
| IRIV PiControl CM5 | [`iriv-picontrol-cm5.md`](iriv-picontrol-cm5.md) | `IRIV-PICL5` | Raspberry Pi CM5 (BCM2712) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.5, Jan 2026 | **Medium** |
| IRIV IO Controller | [`iriv-io-controller.md`](iriv-io-controller.md) | `IRIV-IOC` | Raspberry Pi RP2350A (microcontroller, no Linux) | Datasheet Rev 1.0, Jul 2024 | **Medium** |
| IRIV IOC MQTT Gateway | [`iriv-ioc-mqtt-gateway.md`](iriv-ioc-mqtt-gateway.md) | `IRIV-IOC-MQTT` | Same hardware as IO Controller + factory MQTT firmware | Datasheet Rev 1.0, Jun 2026 | **Medium** |
| IRIV SmartHub CM5 | [`iriv-smarthub-cm5.md`](iriv-smarthub-cm5.md) | `IRIV-SH5` | Raspberry Pi CM5 (BCM2712) | User Manual Rev 1.3, Dec 2025 | **Medium-high** |
| IRIV EdgeAI CM5 | [`iriv-edgeai-cm5.md`](iriv-edgeai-cm5.md) | `IRIV-EDGEAI-CM5` | Raspberry Pi CM5 (BCM2712) + AI HAT+ | Datasheet Rev 1.0, Jul 2025 | **Medium-high** |
| IRIV EdgeAI Safety Box Kit | [`iriv-edgeai-safety-box-kit.md`](iriv-edgeai-safety-box-kit.md) | `KIT-IRIV-EAI-PPE` | IRIV EdgeAI CM5 (8GB/32GB) + Hailo-8 26 TOPS | No kit datasheet. Controller: EdgeAI CM5 Datasheet Rev 1.0 | **Medium-low** |

**Source rule for IRIV (16 Oct 2026): the datasheet is the main source.** User manuals rank second ([UM]); where a newer manual disagrees, the datasheet still wins in the text and the conflict is listed for engineering.

IRIV notes for every agent:
- **IO Controller is not a Raspberry Pi computer.** No Raspberry Pi OS or Node-RED on the device.
- **IOC MQTT Gateway firmware must not be overwritten** — no CircuitPython/UF2 steps; setup is via USB-C web page at 10.0.0.1. Plain MQTT on port 1883, no TLS on the device.
- **PiControl CM4, PiControl CM5 and EdgeAI CM5 RS485 is a USB serial device (`/dev/ttyACM*`)**, not a GPIO UART.
- **mini PCIe sockets on PiControl CM4, PiControl CM5, SmartHub CM5 and EdgeAI CM5 carry USB 2.0 only** (no PCIe). M.2 = NVMe only, no SATA.
- **Bare "IRIV PiControl" is ambiguous** between CM4 (`IRIV-PICL`) and CM5 (`IRIV-PICL5`); the shared datasheet code `IRIV-PICONTROL` covers both.
- **Safety Box Kit is not a certified safety system**, detects helmets and vests only, needs RTSP IP cameras (not included), and its "up to 6 cameras" holds only for 640x360 sub-streams at 15–25 FPS. No accuracy figure exists — "96% compliant" in marketing is an example dashboard reading.
- **Bare "IRIV SmartHub" is ambiguous** with the SmartHub dashboard feature of EdgeAI. Always use the full name.
## Quick cross-product facts (ESP32 family)

| | Maker ESP32 | Robo ESP32 | Maker Feather AIoT S3 |
|---|---|---|---|
| USB | USB-C, CH9102F | none (uses host board) | USB-C, native USB (no bridge) |
| Arduino board | ESP32 Dev Module | ESP32 Dev Module (host) | Cytron Maker Feather AIoT S3 |
| Flash / PSRAM | 8 MB / — | — | 8 MB / 8 MB octal |
| Onboard LED pin | 14 LEDs (incl. GPIO2) | NeoPixel ×2 on GPIO15 | GPIO2 + RGB on GPIO46 |
| Buzzer | GPIO26 | GPIO23 | GPIO12 |
| User button | GPIO4 | GPIO34, 35 | GPIO3 |
| I2C port | Maker Port 21/22 | Grove 2 + Maker Port 21/22 | Maker Port 42/41 |
| Analog safe with Wi-Fi | ADC1: 32–39 | Grove 4–7 (33, 32, 39, 36) | GPIO4–10 (A0–A5, A7) |

## How to add or update a product

1. Check it is a Cytron-brand product. Then copy `_TEMPLATE.md` to `<product-slug>.md`.
2. Start from the Cytron datasheet. Tag every fact with its source. Put conflicts and unconfirmed items in their sections — don't drop them.
3. Fill `fact-sheets/<product-slug>.md` in the Content Hub template from that reference (only what it states), and add it to `fact-sheets/ALL-fact-sheets.md`. Check the aliases don't clash with another product.
4. Add the row to *Products* above with an honest confidence level.
5. Commit to this repository with a message like `kb: add <product>`.
6. When the design team confirms something, mark it [DT] with the date and remove it from *Needs verification*.

