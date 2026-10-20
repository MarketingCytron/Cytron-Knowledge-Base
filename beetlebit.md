# BEETLE:BIT Gripper Robot Car Kit for micro:bit — Verified Reference

| | |
|---|---|
| Product code | `V-BEETLEBIT` [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). Packing lists for all four kit options and the Accessories Kit are now read; the booklet (image-only PDF) is still unread, so it stays Medium |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Notes on tags used here: [UM] = BEETLE:BIT Booklet (file name and Drive metadata only — body not readable); [PP] = my.cytron.io product page (coordinator read, 2026-10-19); [PP: hub] = BEETLE:BIT Resource Hub pages; [PP: hub code] = the MakeCode projects linked from the hub chapter pages (project names and code read through the MakeCode share API); [GH] = CytronTechnologies/pxt-zoombit and pxt-rekabit source. KIT RULE: the REKA:BIT board (`reka-bit.md`) and Maker Line sensor (`maker-line.md`) are **not** re-documented here; only kit-level facts are stated. BEETLE:BIT Track PDF ("BEETLEBIT Track.pdf") was read: it contains only the title and the numbers 50–170, i.e. a printable line track with a ruler scale; the line layout itself is an image.

## What it is
- "BEETLE:BIT Gripper Robot Car Kit for micro:bit" — a hands-on educational robotics kit built around the BBC micro:bit V2 and the REKA:BIT expansion board [PP]. Cytron calls it a "mobile manipulator": a configurable chassis, dual TT motors, a front-mounted servo gripper, an ultrasonic distance sensor and a line-following sensor, with a 7-chapter learning guide [PP].
- Positioned as a "stepping stone... for those who have mastered ZOOM:BIT, Pikabot, BocoBot, or OjanBot" [PP]. The Resource Hub describes it as a learning site for beginners in basic robotics covering building, coding and experimenting with a mobile manipulation robot [PP: hub].
- Purchase options [PP]: **with micro:bit** / **without micro:bit** / **Accessories Kit only**, each **with battery** or **without battery** (price range RM99.80–RM326.45 across the options).
- Controller board: REKA:BIT — see `reka-bit.md`. Line sensor: Maker Line — see `maker-line.md`.

## Specifications
No kit datasheet or spec table exists. The product-page "Specifications" block is reproduced in full; kit-level facts follow.

| Item | Value | Src |
|---|---|---|
| Microcontroller | BBC micro:bit (V2 in the "with micro:bit" option) | [PP] |
| Motors | 2x DC gear motors with wheels (packing list: "2x TT motor with 15cm wires and wheel kit") | [PP] |
| Gripper | Non-copper PCB with servo motor (packing list: "1x TS90A micro servo"; "1x Robo Grip PCB with accessories") | [PP] |
| Sensors | Infrared line tracking (Maker Line), ultrasonic obstacle avoidance ("Ultrasonic 3V3") | [PP] |
| Power | 4x AA batteries (holder with DC jack) | [PP] |
| Control | Autonomous Mode or micro:bit RC Mode ("additional micro:bit not included") | [PP] |
| Chassis | Non-copper PCB ("2x Robo Base (PCB only)"); no soldering | [PP] |
| Programming | MakeCode | [PP] |
| Learning guide | 7 chapters + Setup Guide + Bonus activities | [PP], [PP: hub] |
| Warranty | 12 months [PP]; hub Helpdesk: "1 year for manufacturing defects"; wear and tear, misuse, abuse or improper maintenance not covered; troubleshooting/repair/testing takes 7 working days from receipt | [PP], [PP: hub] |
| Packing list — "with micro:bit, with battery" option | 1x BBC micro:bit V2, 1x REKA:BIT, 1x Dual Output Cable USB-A to 2.1mm DC barrel & Micro USB, 1x 4xAA battery holder with DC jack, 1x Ultrasonic 3V3, 1x Maker Line, 4x AA battery, 2x TT motor with 15cm wires and wheel kit, 1x TS90A micro servo, 1x BEETLE:BIT Booklet, 1x BEETLE:BIT Track, 1x Accessories Kit | [PP] |
| Accessories Kit contents | bracket for ultrasonic HC-SR04, W420 steel ball castor, 2x TT motor bracket, 2x Robo Base (PCB only), 3x Grove 4-pin buckled to female cable, M3 PCB stands 40/20/10/5mm, 14x M3 nut, 14x M3x6 screw, Velcro set, 4x M3x10 bolt, 1x Robo Grip PCB with accessories, 1x ping pong ball | [PP] |
| Without-micro:bit option | Same minus the micro:bit (the page lists only the full option explicitly) | [PP] |
| Without-battery option | Same minus the 4x AA batteries (inferred from the option name; the page lists only the with-battery packing list) | [PP] |
| Guide book PDF | "202602 BEETLEBIT Quick Start Guide.pdf", 223,581,856 bytes, PDF, uploaded 2026-02-13 | [UM] metadata |
| Track PDF | "BEETLEBIT Track.pdf" — printable line paper track with a 50–170 scale | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Options and packing:**
  - **With micro:bit, with battery:** 1x BBC micro:bit V2, 1x REKA:BIT, 1x Dual Output Cable (USB A to 2.1 mm DC barrel and micro USB), 1x 4xAA battery holder with DC jack, 1x Ultrasonic 3V3, 1x Maker Line, 4x AA battery, 2x TT motor with 15 cm wires and wheel kit, 1x TS90A micro servo, 1x BEETLE:BIT booklet, 1x BEETLE:BIT track, 1x BEETLE:BIT Accessories Kit [PP].
  - **With micro:bit, without battery:** same list without the 4 AA batteries [PP].
  - **Without micro:bit, with battery / without battery:** same lists without the micro:bit V2 [PP].
  - **Accessories Kit:** 1x bracket for ultrasonic HC-SR04, 1x W420 steel ball castor, 2x TT motor bracket, 2x Robo Base (PCB only), 3x Grove 4-pin buckled to female cable, 4x M3 PCB stand 40 mm, 2x 20 mm, 4x 10 mm, 4x 5 mm, 14x M3 nut, 14x screw M3×6 mm, 1x Velcro 10 mm round adhesive set (9 pairs), 4x bolt M3×10 mm, 1x Robo Grip PCB with accessories, 1x ping pong ball [PP].
- **Spec list:** BBC micro:bit; 2 DC gear motors with wheels; gripper = non-copper PCB with servo motor; sensors = infrared line tracking and ultrasonic obstacle avoidance; power 4x AA; control = autonomous mode or micro:bit RC mode (second micro:bit not included); chassis = non-copper PCB; screw-and-slot assembly, no soldering; programming = Microsoft MakeCode [PP].
- **Description:** stepping stone after ZOOM:BIT, PikaBot, BocoBot or OjanBot; 7-chapter learning guide [PP].
- **Resources:** Resource Hub, booklet PDF and track PDF (Google Drive), "BEETLE:BIT (ZOOM:BIT) Extension" link to pxt-rekabit [PP].

## Interfaces, terminals and pin mapping
Every chapter program depends on the **pxt-zoombit** MakeCode extension (`github:cytrontechnologies/pxt-zoombit#v0.1.1`), which hard-codes the pins below [PP: hub code], [GH]. The gripper servo channel comes from the chapter code itself.

| Function | REKA:BIT channel / micro:bit pin | Notes | Src |
|---|---|---|---|
| Left drive motor | REKA:BIT **M1** | `LEFT_MOTOR = MotorChannel.M1` | [GH] |
| Right drive motor | REKA:BIT **M2** | `RIGHT_MOTOR = MotorChannel.M2` | [GH] |
| Gripper servo (TS90A) | REKA:BIT servo port **S1** | All chapter and bonus programs call `rekabit.setServoPosition(ServoChannel.S1, …)` | [PP: hub code] |
| Maker Line sensor | **P1** (analog) | `MAKER_LINE_PIN = AnalogPin.P1`; one analog value encodes the line position | [GH] |
| Ultrasonic sensor trigger | **P2** | `US_TRIG_PIN = DigitalPin.P2` | [GH] |
| Ultrasonic sensor echo | **P12** | `US_ECHO_PIN = DigitalPin.P12` | [GH] |
| RGB LEDs | P8 (on REKA:BIT) | not used by any chapter program read | [GH] |
| Headlight pins P13 / P15 | defined by pxt-zoombit | BEETLE:BIT has no LED modules in its packing list; these blocks are unused | [GH], [PP] |
| Motors and servo | I2C to the REKA:BIT co-processor (address 0x08) | see `reka-bit.md` | [GH] |

Which physical Grove port label each sensor cable plugs into is only shown in the booklet / Setup Guide diagram and video, which could not be read — see *Needs verification*.

## Rules and gotchas (for code, wiring and tutorials)
- **Extension:** add `pxt-zoombit` (search "zoombit" or paste https://github.com/cytrontechnologies/pxt-zoombit). It pulls in `pxt-rekabit` automatically; the chapter projects list only pxt-zoombit as a dependency yet call `rekabit.*` servo blocks [PP: hub code]. Do not tell readers to add a "beetlebit" extension — none exists on GitHub (CytronTechnologies/pxt-beetlebit returns 404) [GH].
- **Gripper angles used by Cytron's code** [PP: hub code]: Chapter 3 activity toggles S1 between **0** (button A) and **180** (button B); Chapters 6 and 7 use **120 = open** and **0 = closed**. After every move the code pauses (100 ms in Ch. 3; 2000 ms in Ch. 6/7) and then calls `disableServo(S1)` so the servo is not held under load. Keep this pattern — a held micro servo on a 4xAA pack is the main power drain.
- **Gripper calibration:** Chapter 3 has a section "Gripper Not Working? Let's Calibrate!" (video); the Chapter 3 Challenge sweeps S1 0 ↔ 180 four times on a loud sound or a shake [PP: hub], [PP: hub code].
- **Drive blocks** (pxt-zoombit) [GH]: `move forward/backward at speed 0–255`, `turn left/right at speed` (spin on the spot: left = M1 backward + M2 forward), `set motors speed: left / right` (-255 to 255), `brake`. Cytron's chapter code uses speed **128** for driving and turning, 50 or 120 near obstacles, and 500 ms turn pulses [PP: hub code].
- **Ultrasonic** [GH]: `ultrasonic distance (cm)` returns 1–255; 255 means no echo or > 255 cm. Cytron's code treats **< 10** as "obstacle" and **< 20** as "slow down" (unit: cm, from the block name) [PP: hub code].
- **Line following** [GH], [PP: hub code]: `line detected on` center / left / right / far left / far right / all / none. Chapter 5 uses asymmetric motor speeds (50/100, then 0/100) to steer back and remembers the last side to recover when the line is lost. Chapter 7 counts T-junctions with `LinePosition.All` (stops after 2) and chains: wait for object < 10 cm → close gripper → follow line → stop at the 2nd junction → open gripper when an object is again < 10 cm.
- **Chapter 2 "Why Doesn't It Go Straight?"** — the hub has a dedicated section and challenge for drift between the two TT motors; fix in code with `set motors speed` rather than blaming the kit [PP: hub].
- **RC mode (Bonus 1)** uses micro:bit **radio group 1** and sends numbers 0–5 (A = forward, B = backward, tilt left/right = turn, shake = toggle gripper, nothing = brake). The same program runs on both micro:bits; the remote is a **second micro:bit, which is not included** [PP: hub code], [PP].
- **micro:bit V1:** the chapter projects use `microphone` (V2 only) in Chapter 3 Challenge (`onSound(Loud)`) and `input.onGesture`; the kit is sold with V2 [PP].
- **Flashing:** MakeCode web editor or the MakeCode Offline App; adding an extension may need internet to compile [PP: hub Helpdesk].

## Power and electrical limits
- Kit power: **4x AA batteries** in a holder with a DC jack into the REKA:BIT [PP]. The kit also includes a "Dual Output Cable USB-A to 2.1mm DC barrel & Micro USB" (USB power + data in one cable) [PP].
- Board limits (REKA:BIT datasheet, see `reka-bit.md`): input 3.6–6 V; motors 1 A continuous / 1.5 A peak per channel; servo V+ = input voltage; Grove +3V3 total 300 mA; over 7 V cuts power to motors and servos.
- No battery chemistry (alkaline vs NiMH), run time or current draw is stated by any source read.

## Software support
- **MakeCode** (blocks; JavaScript/Python text modes available in the editor) [PP], [PP: hub].
- Extension: **pxt-zoombit v0.1.1** → depends on pxt-rekabit [PP: hub code], [GH]. Product page wording: MakeCode extension = pxt-rekabit ("BEETLE:BIT (ZOOM:BIT) Extension") [PP] — see *Conflicts*.
- Published chapter programs (MakeCode share links, project names as published) [PP: hub]:
  - Setup Guide — "build BEETLE:BIT, together!" (video + construction-flow diagram; no text steps) — https://beetlebit-hub.cytron.io/chapter-resources/beetlebit-setup-guide
  - Ch. 1 "The Beetle's Brain (micro:bit Basics)" — LED matrix text/animation, downloading a program — https://makecode.microbit.org/_5ueMDfTd7ixT
  - Ch. 2 "How the Beetle Moves (TT Motors)" — activity https://makecode.microbit.org/_chVFH5MpMWL9 ; challenge https://makecode.microbit.org/_aV0Rpvc2J9s3
  - Ch. 3 "The Beetle's Claw (Servo Gripper)" — open/close the Robo Grip Mini with the servo — activity https://makecode.microbit.org/_LYf68Y6WADsj ; challenge https://makecode.microbit.org/_K7WHUyUb5Aeo
  - Ch. 4 "The Beetle's Eyes (Ultrasonic Sensor)" — obstacle detection — activity https://makecode.microbit.org/_MRcTvbDsg8mv ; challenge https://makecode.microbit.org/_PfuLdVcUX8wd
  - Ch. 5 "The Beetle Senses (Line Following)" — Maker Line — activity https://makecode.microbit.org/_2t0eTYhp0g2c ; challenge https://makecode.microbit.org/_EwPceP5VccxM
  - Ch. 6 "Teaching the Beetle to Decide" — decisions and a complete task — activity https://makecode.microbit.org/_YT9XW75Lg3PF ; challenge https://makecode.microbit.org/_bvi32yPaq6M2
  - Ch. 7 "Coordinated Actions (Line + Grab)" — https://makecode.microbit.org/_M3iLbqCkDRyx
  - Bonus 1 "Control BeetleBit Using a Controller" (radio) — https://makecode.microbit.org/_35PdFAiUb22w ; Bonus 2 "BEETLE:BIT Input–Output Challenge" (video only)
- Cytron tutorials listed on the product page [PP]: colour detection bot using HuskyLens; line following robot car using motionbit; colour detection robot using TCS3200; "Chapter 1: Setting Up Beetle:Bit with Huskylens 2" (https://my.cytron.io/tutorial/chapter-1-setting-up-beetlebit-with-huskylens-2 — **not readable here**).

## Compatibility and accessories
- micro:bit V2 included in the "with micro:bit" option; RC mode needs a second micro:bit (not included) [PP].
- Mechanical: Robo Base PCB chassis x2, TT motor brackets, W420 steel ball castor, M3 standoffs/hardware, Velcro, HC-SR04-style ultrasonic bracket, Robo Grip PCB gripper, ping pong ball (the object to grip) [PP].
- The hub calls the gripper "Robo Grip Mini" [PP: hub]; the packing list says "Robo Grip PCB with accessories" [PP].
- HuskyLens add-on is covered by a Cytron tutorial series [PP]; mounting/wiring not read.
- Related kits named by Cytron as prerequisites: ZOOM:BIT (`zoom-bit.md`), PikaBot, BocoBot, OjanBot [PP].

## Common mistakes / troubleshooting
- **Gripper does nothing:** servo must be on **S1**; code must end with `disableServo` only after the pause; run the Chapter 3 calibration [PP: hub code].
- **Robot curves instead of driving straight:** expected TT-motor mismatch; use `set motors speed` with different left/right values (Chapter 2 challenge) [PP: hub].
- **Ultrasonic always 255:** no echo — check the trigger/echo cable orientation on the Grove-to-female cable; the sensor is the 3.3 V version ("Ultrasonic 3V3") [PP], [GH].
- **Line following fails:** calibrate the Maker Line first (see `maker-line.md`); the hub's Chapter 5 has an "Introduction of Maker Line Sensor" section [PP: hub].
- **Two kits interfere in RC mode:** every Bonus 1 program uses radio group 1 — change the group per pair [PP: hub code].
- **Booklet:** download from https://beetlebit-hub.cytron.io/download (English only is listed) [PP: hub].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| MakeCode extension | [PP] "MakeCode extension = pxt-rekabit ('BEETLE:BIT (ZOOM:BIT) Extension')" | [PP: hub code] every chapter project depends on `pxt-zoombit#v0.1.1` (which itself depends on pxt-rekabit) | Tell readers to add **zoombit**; rekabit loads with it. No separate BEETLE:BIT extension exists |
| Gripper name | [PP] "Robo Grip PCB with accessories"; "Gripper: non-copper PCB with servo motor" | [PP: hub] "Robo Grip Mini" | Same part; use "Robo Grip Mini (PCB gripper)" and name the servo TS90A |
| Gripper open angle | [PP: hub code] Ch. 3: 0 ↔ 180 | [PP: hub code] Ch. 6/7: open = 120, closed = 0 | Both are Cytron code; 120/0 is the working range used in the task chapters. State both |
| Guide length | [PP] "7-chapter learning guide" | [PP: hub] Setup Guide + Chapters 1–7 + Bonus (2 activities) | Say "7 chapters plus a setup guide and bonus activities" |
| Warranty wording | [PP] "12 months" | [PP: hub] "1 year for manufacturing defects", exclusions listed | Same period; quote the exclusions from the hub |

## Needs verification
- **Booklet contents** (chapter text, wiring diagrams, parts diagram, any revision/date printed inside): the PDF is image-only and 223 MB; it could not be downloaded or OCR'd here. Everything above about chapters comes from the Resource Hub and the published MakeCode projects, which mirror the booklet.
- **Grove port labels** on REKA:BIT used for the ultrasonic (P2/P12) and Maker Line (P1) cables — shown only in the Setup Guide video/diagram.
- **Product code** `V-BEETLEBIT` is from the product page URL/SKU as read by the coordinator; codes for the individual options (without micro:bit, Accessories Kit) not stated.
- Ultrasonic module model: packing list says "Ultrasonic 3V3"; the bracket is "for ultrasonic HC-SR04"; pxt-zoombit's code comment names RCWL-9610. Confirm which module ships.
- Dimensions, weight, assembly time and age range — not stated anywhere read.
- Track PDF: line width/length and layout (image only; scale numbers 50–170 visible).
- Whether the HuskyLens tutorial series uses the I2C Grove port and which HuskyLens mode — tutorial pages returned 403 / blocked.
- Run time on 4x AA and whether USB power alone drives motors and servo.
- Codes for the individual options (with/without micro:bit, with/without battery, Accessories Kit) — the page shows names only.

## Sources
- [PP] Product page (read by the coordinator 2026-10-19): https://my.cytron.io/p-beetlebit-gripper-robot-car-kit-for-microbit (short link https://my.cytron.io/p-beetlebit)
- [UM] BEETLE:BIT Booklet / Guide Book PDF (English) — "202602 BEETLEBIT Quick Start Guide.pdf", Drive, uploaded 2026-02-13, **not readable as text**: https://drive.google.com/file/d/18ZOwcWVUn0xsEVdcUNOMDvZKf5haVmz5/view
- [UM] BEETLE:BIT Track PDF — "BEETLEBIT Track.pdf": https://drive.google.com/file/d/1uf-ScEUm3Y6hs8ExShzrGi_iHn8ZhFf-/view
- [PP: hub] BEETLE:BIT Resource Hub: https://beetlebit-hub.cytron.io/ — Setup Guide https://beetlebit-hub.cytron.io/chapter-resources/beetlebit-setup-guide ; Chapters https://beetlebit-hub.cytron.io/chapter-resources/chapter-1 … /chapter-7 ; Bonus https://beetlebit-hub.cytron.io/chapter-resources/bonus ; Download https://beetlebit-hub.cytron.io/download ; Helpdesk https://beetlebit-hub.cytron.io/helpdesk
- [PP: hub code] MakeCode projects linked above (read via https://makecode.com/api/<id>/text)
- [GH] https://github.com/CytronTechnologies/pxt-zoombit — main.ts, pxt.json (v0.1.1) via raw.githubusercontent.com
- [GH] https://github.com/CytronTechnologies/pxt-rekabit — README.md, pxt.json (v1.2.3)
- Related KB files: `reka-bit.md`, `maker-line.md`, `zoom-bit.md`
- Not readable here (403 / blocked): https://my.cytron.io/tutorial/chapter-1-setting-up-beetlebit-with-huskylens-2
