# PikaBot - Maker UNO Smart Car Kit — Verified Reference

| | |
|---|---|
| Product code | `V-KIT-PIKABOT` (my.cytron.io product page [PP]). Opencircuit lists `KIT-PIKABOT` as the model [3P] — see *Conflicts* |
| Family | Arduino kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 3): live my.cytron.io product page read (description, features, packing list, resources). Full packing list, the push button's role (start button), box size and warranty are now Cytron-stated; the booklet is image-only, so it stays Medium |
| Primary source | No datasheet exists. **Guide book: "PikaBot Booklet" (Arduino IDE edition, English, PDF on Google Drive, Feb 2020 upload; image-only PDF — OCR fragments only, body text NOT readable)** [UM]. Readable Cytron companion: **"PikaBot Resources" Google Doc** (Cytron Team, Jan–Feb 2020) with the code of every project and challenge in the booklet [PP: sample code]. The mBlock edition "Buku Panduan Pengaturcaraan PikaBot menggunakan Aplikasi mBlock v1.1" (Malay, static.cytron.io) could not be fetched. Boards in the kit: **Maker UNO → `maker-uno.md`**, **Maker Drive → `maker-drive.md`** |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs [PP: sample code] > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
- "PikaBot - Maker UNO Smart Car Kit": a DIY mobile robot kit built on the **Maker UNO** (Arduino UNO-compatible) with a **Maker Drive** dual-channel motor driver, two TT gear motors, two IR line-tracking modules and an HC-SR04 ultrasonic sensor, assembled with jumper wires — "no soldering" [PP].
- Powered by 4× AA batteries, which power the controller and the motors [PP].
- The kit's paper box doubles as the robot base and cover; schematics and mounting locations are printed inside the box [PP: tutorial mBlock][3P quoting Cytron copy].
- Two booklet options [PP]: **Arduino IDE (English)** or **mBlock (Bahasa Melayu)**. The Arduino booklet has 4 projects with challenges (list below) [PP: sample code]; the mBlock booklet is v1.1 (file name) and the mBlock lesson series is "1 Move Around", "2 Detect Object", "3 Line Follow" [PP: tutorial mBlock].
- After the lessons, Cytron suggests dismantling PikaBot and reusing the parts with cardboard, milk cartons, bottles or old toys [PP: sample code].

## Specifications
No spec table exists. Kit-level facts:

| Item | Value | Src |
|---|---|---|
| Controller | Maker UNO (see `maker-uno.md`) | [PP] |
| Motor driver | Maker Drive (see `maker-drive.md`) | [PP] |
| Motors | 2× 3–6 VDC dual-axis TT gear motor with pre-soldered wires | [PP] |
| Wheels | 2× rubber wheel 63 mm × 15 mm | [PP] |
| Line sensors | 2× IR line tracking module (digital output read on A0/A1) | [PP][PP: sample code] |
| Distance sensor | 1× HC-SR04 ultrasonic | [PP] |
| Battery | 4× AA batteries + 4×AA battery holder; "4x AA battery powers controller and motors" | [PP] |
| Breadboard | 1× mini breadboard 35 × 42 mm | [PP] |
| Wiring | 40-way M-F jumper, 40-way M-M jumper; panel-mount rocker switch | [PP] |
| Packing list (page) | 1× Maker UNO, 1× Maker Drive, 2× TT motor, 2× wheels, 2× IR line tracking module, 1× HC-SR04, 4× AA batteries, 1× 4×AA battery holder, 1× mini breadboard, 40-way M-F jumper, 40-way M-M jumper … (page list truncated in the capture; fuller reseller list under *Needs verification*) | [PP] |
| Example code | Open-source Arduino sample code (Drive folder "PikaBot Coding") and Resources doc; mBlock extension "PikaBot" | [PP][PP: sample code][PP: tutorial mBlock] |
| Arduino IDE / library shown in the booklet | Arduino 1.8.10 download page; CH341SER driver; "Cytron Motor Drivers Library" 1.0.1 in Library Manager | [UM, OCR fragments] |
| Price | RM128.00 (either booklet option) | [PP] |
| Warranty | 12 months | [PP] |

### Booklet projects (Arduino IDE edition) [PP: sample code]
| Project | Steps | What it teaches / code |
|---|---|---|
| 1 Let's Move It | 1-1 both motors `setSpeed(200)`; 1-2 forward 1 s, stop, backward 2 s; 1-3 `robotStop()` / `robotMove(speedLeft, speedRight)` helpers, spin left (-200, 200) and right (200, -200) | CytronMotorDriver library, `PWM_PWM` mode, functions |
| 1 Challenges | Rectangle (forward 1.5 s / 1 s, turn right 600 ms), Circle (`robotMove(100, 250)`), Triangle (turn right 1300 ms) | Timed moves |
| 2 Oh No! Stop! | 2-1 ultrasonic distance to Serial (`pulseIn`, distance = duration × 0.017 cm); 2-2 press button → forward while distance > 15 cm, else stop | Ultrasonic, `while(true)` after button |
| 2 Challenge | Distance > 20 cm forward, else turn left for 600 ms | Obstacle avoidance |
| 3 Black or White Line? | 3-1 print `digitalRead` of left/right IR to Serial; 3-2 button → both LOW (white) forward; left HIGH turn left; right HIGH turn right | Line following with 2 digital IR sensors |
| 3 Challenge | Both HIGH (black or nothing) stop; both LOW forward; one HIGH turn toward it | Stop at a full black line |
| 4 Music On | 4-1 IDE example toneMelody (booklet pp. 96–100 explain notes and durations); 4-2 play a 9-note melody on pin 8 in `setup()`, then spin left in `loop()` | `tone()`, `pitches.h` (how to add it as a new tab) |
| 4 Challenges | Super Mario, Baby Shark, Birthday Song melodies (toneMelody template) | Arrays, `for` loop |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Options:** PikaBot with Arduino IDE booklet (English) / PikaBot with mBlock booklet (Bahasa Melayu); the lists are the same except the booklet [PP].
- **Full packing list:** 1x Maker UNO, 1x Maker Drive, 2x 3–6 VDC dual-axis TT gear motor (pre-soldered wires), 2x rubber wheel 63 × 15 mm, 2x IR line tracking module, 1x HC-SR04, 4x AA batteries, 1x 4xAA battery holder, 1x mini breadboard (35 × 42 mm), 1x 40-way male-to-female jumper, 1x 40-way male-to-male jumper, 1x USB Micro-B cable, 1x mBot N20 vacuum steel ball castor, 1x tiny Phillips screwdriver (transparent), 4x bolt M3×25 mm, 4x M3 nut, 1x CH2 quick-wiring terminal (press type), 1x rocker switch with wires, 1x push button with wires, 14x plastic rivet (M3), 2x plastic rivet (M4), 1x PikaBot track, 1x PikaBot booklet, 1x PikaBot paper box [PP].
- **Features list:** no soldering; Maker UNO + Maker Drive; 4x AA powers controller and motors; IR line sensors; open-source example code; **panel-mount rocker switch = power switch; panel-mount push button = start button**; paper box is the robot body; **box dimension 127 mm × 55 mm × 190 mm (not including motor shafts and wheels)** [PP].
- **Description:** schematic and part positions are printed inside the box; booklet hardcopy in the kit, softcopies online (Arduino IDE PDF on Drive; mBlock v1.1 PDF on static.cytron.io); assembly video [PP].
- **FAQ (page):** Arduino IDE (C/C++); line following, obstacle avoidance, light tracking (marketing FAQ) [PP].

## Interfaces, terminals and pin mapping
All pins from the Cytron sample code [PP: sample code] (the booklet's wiring pages are images that could not be read):

| Function | Maker UNO pin | Maker Drive / module pin | Src |
|---|---|---|---|
| Left motor | D11 (A), D10 (B) | `CytronMD motorLeft(PWM_PWM, 11, 10)` → M1A/M1B (channel not named in code; see Needs verification) | [PP: sample code] |
| Right motor | D9 (A), D3 (B) | `CytronMD motorRight(PWM_PWM, 9, 3)` | [PP: sample code] |
| Ultrasonic TRIG | D5 | HC-SR04 Trig | [PP: sample code] |
| Ultrasonic ECHO | D4 | HC-SR04 Echo | [PP: sample code] |
| Left IR line sensor | A0 (`digitalRead`) | IR module digital output | [PP: sample code][PP: tutorial mBlock] |
| Right IR line sensor | A1 (`digitalRead`) | IR module digital output | [PP: sample code][PP: tutorial mBlock] |
| Start button | D2, `INPUT_PULLUP` (on-board Maker UNO button) | — | [PP: sample code] |
| Buzzer | D8 (on-board Maker UNO piezo, slide switch on) | — | [PP: sample code] |
| Battery | 4×AA holder → Maker Drive VB+/VB- (power terminal per `maker-drive.md`); rocker switch in the battery line (switch wiring not readable) | — | [PP][UM fragments] |

All four motor pins (11, 10, 9, 3) are PWM pins on the Maker UNO, as `PWM_PWM` mode needs [PP: sample code]; see `maker-drive.md` for the truth table and `maker-uno.md` for the PWM list.

## Rules and gotchas (for code, wiring and tutorials)
- **Library:** `#include "CytronMotorDriver.h"`, `CytronMD motorLeft(PWM_PWM, 11, 10); CytronMD motorRight(PWM_PWM, 9, 3);` `setSpeed(-255…255)`; `setSpeed(0)` on both = stop [PP: sample code]. Install "Cytron Motor Drivers Library" from the Arduino Library Manager (booklet shows version 1.0.1) [UM fragments].
- **Turn convention in Cytron's code:** `robotMove(-200, 200)` = turn left, `robotMove(200, -200)` = turn right (spin on the spot) [PP: sample code]. If the robot turns the other way, the motor wires are swapped — check Maker Drive M1/M2 wiring (`maker-drive.md`).
- **Programs wait for the on-board button (D2) before moving** so the robot does not drive off while plugged into USB [PP: sample code]. Keep this pattern in tutorials.
- **IR logic:** LOW = white surface, HIGH = black line (or no reflection) [PP: sample code]. The mBlock extension block is "left IR detects dark" [PP: tutorial mBlock]. Thresholds are set by the module's on-board trimmer, not in code.
- **Ultrasonic:** distance (cm) = `pulseIn(ECHO, HIGH) × 0.017`; the booklet uses 15 cm (stop) and 20 cm (avoid) [PP: sample code]; the mBlock lesson also stops below 15 cm [PP: tutorial mBlock].
- **Buzzer on D8** needs the Maker UNO slide switch on; `pitches.h` must exist as a second tab (the Resources doc gives the full file) [PP: sample code].
- **Pin-label stickers:** the booklet starts with "PIN LABEL STICKER — Peel off and stick at your MAKER UNO board" [UM fragment].
- **mBlock:** add the "PikaBot" extension from the device panel in mBlock 5 (online ide.mblock.cc or offline); set the line-sensor pins in the init block if not using the defaults A0/A1; put the board in upload mode and connect via the COM port [PP: tutorial mBlock].
- **Arduino IDE version:** the booklet screenshots show Arduino 1.8.10 and the CH341SER driver [UM fragments]; use the current IDE and the CH340 driver notes in `maker-uno.md`.

## Power and electrical limits
- 4× AA batteries in a holder power the Maker Drive, the motors and the controller [PP]. Maker Drive accepts 2.5–9.5 VDC and supplies 5 V at up to 200 mA for the host board (`maker-drive.md`); how the 5 V reaches the Maker UNO in PikaBot is not stated in readable text (see *Needs verification*).
- TT motors are rated 3–6 VDC [PP]; Maker Drive limits are 1 A continuous / 1.5 A peak per channel (`maker-drive.md`).
- The Maker UNO has no DC jack or Vin pin (`maker-uno.md`) — never tell readers to plug the battery into the Maker UNO directly.
- Rocker switch: listed in the kit as a panel-mount rocker switch [PP]; its position in the circuit is not readable.

## Software support
- **Arduino IDE** with the Cytron Motor Drivers Library (`CytronMotorDriver.h`) [PP: sample code][UM fragments]; sample code: Drive folder "PikaBot Coding" (Project_1-1 … Project_4-2 and challenges) [PP][PP: sample code].
- **mBlock 5** with the "PikaBot" extension (device panel → add) [PP: tutorial mBlock]; Malay mBlock booklet v1.1 [PP].
- Drivers: CH34x for the Maker UNO (`maker-uno.md`).

## Compatibility and accessories
- Boards: Maker UNO (`maker-uno.md`), Maker Drive (`maker-drive.md`).
- Sensors in the kit are generic modules (IR line tracking modules, HC-SR04); they are not Cytron Maker Line / Maker Object products.
- Cytron's EDU line-up lists PikaBot beside ZOOM:BIT, Ikedo and EDU PICO as a kit "for Primary / Jr Makers" [PP: exhibition flyer] and BEETLE:BIT's page names PikaBot as a prior step [PP, BEETLE:BIT].
- Parts can be reused for new robots after the course [PP: sample code].

## Common mistakes / troubleshooting
- Robot drives the wrong way or spins when it should go straight → swap one motor's wires or the M1/M2 pairs; check the `PWM_PWM` pin order (11,10 / 9,3) [PP: sample code].
- Nothing moves → button on D2 not pressed; battery switch off; Maker Drive VB+/VB- polarity or voltage (`maker-drive.md`).
- Line follower wanders → IR module trimmer; remember LOW = white in the code [PP: sample code].
- `pitches.h` not found → create the tab and paste the file [PP: sample code].
- Buzzer silent → D8 slide switch off (`maker-uno.md`).
- Uploading while the battery drives the robot → programs wait for the button, but keep wheels off the table.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Product code | [PP] `V-KIT-PIKABOT` | [3P] Opencircuit model `KIT-PIKABOT` | Use `V-KIT-PIKABOT`; keep `KIT-PIKABOT` as alias |
| Obstacle threshold | [PP: sample code] Project 2-2: 15 cm; Challenge: 20 cm | [PP: tutorial mBlock] 15 cm | Both are lesson values, not specs; quote the project |
| mBlock lesson names | [PP: tutorial mBlock] "1 Move Around / 2 Detect Object / 3 Line Follow" | [PP: sample code] Arduino booklet "Let's Move It / Oh No! Stop! / Black or White Line? / Music On" | Different editions; name the edition |

## Needs verification
- **Booklet body text** (version, date, page count ≥ 100, assembly steps, wiring diagrams, which Maker Drive channel is left/right) — the PDF is image-only; read a printed copy or re-OCR it.
- How the Maker UNO is powered from the battery (Maker Drive 5 V output to the Maker UNO 5V pin is the usual method but is not stated in readable text).
- mBlock booklet v1.1 contents and the PikaBot mBlock extension's pin defaults for motors and ultrasonic.
- Weight, assembly time, age range.
- Which pin the external start push button connects to (the sample code uses the on-board D2 button).
- Box height: the page says 127 × 55 × 190 mm; Opencircuit [3P] printed 19 mm — confirm.

## Sources
- [UM] PikaBot Booklet (Arduino IDE, English), PDF on Google Drive: https://drive.google.com/file/d/1G9rhCY_9ogJN4ufXdAwFmrgbaEHKP3Cp/view (image-only; OCR fragments read 2026-10-19)
- [UM, not read] Buku Panduan Pengaturcaraan PikaBot menggunakan Aplikasi mBlock v1.1: https://static.cytron.io/download/PIKABOT/Buku-Panduan-Pengaturcaraan-PikaBot-menggunakan-Aplikasi-mBlock-v1.1.pdf (host blocked)
- [PP: sample code] PikaBot Resources Google Doc (Cytron Team; same code as the public "Arduino sample code" Drive folder linked from the product page): (Cytron document — link not public)
- [PP] Sample code folder "PikaBot Coding": https://drive.google.com/drive/folders/1PQaOMgd1JKaJ6fqU8BYbhii-l76xVCdV
- [PP] https://my.cytron.io/p-pikabot-maker-uno-smart-car-kit (coordinator capture, 2026-10-19)
- [PP: tutorial mBlock] https://www.hackster.io/cytron-technologies/program-arduino-mobile-robot-using-mblock-3-line-follow-24119e (Cytron Technologies, 27 Apr 2020)
- [PP: sample code] 20240904 Exhibition Flyer (Cytron EDU line-up): (Cytron document — link not public)
- [3P] https://opencircuit.shop/product/pikabot-maker-uno-smart-car-kit (read 2026-10-19)
