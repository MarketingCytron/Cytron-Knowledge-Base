# BEETLE:BIT Gripper Robot Car Kit for micro:bit — Verified Reference

| | |
|---|---|
| Product code | `V-BEETLEBIT` [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — BEETLE:BIT Quick Start Guide booklet read in full (96 pages; it has a text layer, so "image-only" was wrong). Wiring, Grove ports, box contents, chapter rules and the Bonus activities are now Cytron-stated [UM]. Raised Medium → Medium-high; still open: the booklet box list and the product page Accessories Kit list give different hardware counts (see *Conflicts*). Earlier: 2026-10-19 master-table review of the live product page |
| Primary source | No datasheet exists for the kit (KB rule 7: the guide book is the main source). Guide book: **"BEETLE:BIT — Build. Code. Move. Grab."** Quick Start Guide, Cytron Education Team, © 2026 Cytron Technologies, 96 pages, "Works with micro:bit V1 & V2" — file "202602 BEETLEBIT Quick Start Guide.pdf" (February 2026), read in full 2026-10-21 [UM]. Also the **BEETLE:BIT Resource Hub** (beetlebit-hub.cytron.io) with the published MakeCode chapter programs, and the Cytron product page. Electrical limits of the controller board come from the REKA:BIT datasheet — see `reka-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Notes on tags used here: [UM] = BEETLE:BIT Quick Start Guide booklet (read in full 2026-10-21 from the copy in the team folder); [PP] = my.cytron.io product page (coordinator read, 2026-10-19); [PP: hub] = BEETLE:BIT Resource Hub pages; [PP: hub code] = the MakeCode projects linked from the hub chapter pages (project names and code read through the MakeCode share API); [GH] = CytronTechnologies/pxt-zoombit and pxt-rekabit source. KIT RULE: the REKA:BIT board (`reka-bit.md`) and Maker Line sensor (`maker-line.md`) are **not** re-documented here; only kit-level facts are stated. BEETLE:BIT Track PDF ("BEETLEBIT Track.pdf") was read: it contains only the title and the numbers 50–170, i.e. a printable line track with a ruler scale; the line layout itself is an image.

## What it is
- "BEETLE:BIT Gripper Robot Car Kit for micro:bit" — a hands-on educational robotics kit built around the BBC micro:bit V2 and the REKA:BIT expansion board [PP]. Cytron calls it a "mobile manipulator": a configurable chassis, dual TT motors, a front-mounted servo gripper, an ultrasonic distance sensor and a line-following sensor, with a 7-chapter learning guide [PP].
- Positioned as a "stepping stone... for those who have mastered ZOOM:BIT, Pikabot, BocoBot, or OjanBot" [PP]. The Resource Hub describes it as a learning site for beginners in basic robotics covering building, coding and experimenting with a mobile manipulation robot [PP: hub].
- Purchase options [PP]: **with micro:bit** / **without micro:bit** / **Accessories Kit only**, each **with battery** or **without battery** (price range RM99.80–RM326.45 across the options).
- Controller board: REKA:BIT — see `reka-bit.md`. Line sensor: Maker Line — see `maker-line.md`.

## Specifications
No kit datasheet or spec table exists. The product-page "Specifications" block is reproduced in full; kit-level facts follow.

| Item | Value | Src |
|---|---|---|
| Microcontroller | BBC micro:bit — booklet cover: "Works with micro:bit V1 & V2"; V2 ships in the "with micro:bit" option [PP] | [UM][PP] |
| Motors | 2x DC gear motors with wheels (packing list: "2x TT motor with 15cm wires and wheel kit") | [PP] |
| Gripper | Non-copper PCB with servo motor (packing list: "1x TS90A micro servo"; "1x Robo Grip PCB with accessories") | [PP] |
| Sensors | Infrared line tracking (Maker Line), ultrasonic obstacle avoidance ("Ultrasonic 3V3") | [PP] |
| Power | 4x AA batteries (holder with DC jack) | [PP] |
| Control | Autonomous Mode or micro:bit RC Mode ("additional micro:bit not included") | [PP] |
| Chassis | Non-copper PCB ("2x Robo Base (PCB only)"); no soldering | [PP] |
| Programming | MakeCode | [PP] |
| Learning guide | Booklet, 96 pages: Setup Guide (p.8), Ch1 The Beetle's Brain – micro:bit Basics (p.24), Ch2 How the Beetle Moves – TT Motors (p.37), Ch3 The Beetle's Claw – Servo Gripper (p.46), Ch4 The Beetle's Eyes – Ultrasonic Sensor (p.52), Ch5 The Beetle Senses – Line Following (p.60), Ch6 Teaching the Beetle to Decide (p.72), Ch7 Coordinated Actions – Line + Grab (p.80), Bonus Activities (p.88) | [UM] |
| Box contents (booklet "What's in the box?") | battery holder & USB cable, Robo Base x2, REKA:BIT (with or without micro:bit), Grove cables x3, ultrasonic bracket, servo motor, ultrasonic sensor, Maker Line sensor, DC motor bracket x2, DC motor & wheels x2, M2 & M3 Phillips screwdriver, Velcro (hooks & loops), Robo Grip Mini, AA batteries x4, cross wrench, castor wheel, M3 PCB stand 40 mm x5 / 20 mm x8 / 10 mm x4 / 5 mm x4, M3 bolt 6 mm x26 / 10 mm x4 / 12 mm x4, M3 nut x18, M3 lock nut x5, M3 plastic washer 3 mm x5 / 1 mm x6, M2 bolt x6, M2 nut x6 | [UM] |
| Warranty | 12 months [PP]; hub Helpdesk: "1 year for manufacturing defects"; wear and tear, misuse, abuse or improper maintenance not covered; troubleshooting/repair/testing takes 7 working days from receipt | [PP], [PP: hub] |
| Packing list — "with micro:bit, with battery" option | 1x BBC micro:bit V2, 1x REKA:BIT, 1x Dual Output Cable USB-A to 2.1mm DC barrel & Micro USB, 1x 4xAA battery holder with DC jack, 1x Ultrasonic 3V3, 1x Maker Line, 4x AA battery, 2x TT motor with 15cm wires and wheel kit, 1x TS90A micro servo, 1x BEETLE:BIT Booklet, 1x BEETLE:BIT Track, 1x Accessories Kit | [PP] |
| Accessories Kit contents | bracket for ultrasonic HC-SR04, W420 steel ball castor, 2x TT motor bracket, 2x Robo Base (PCB only), 3x Grove 4-pin buckled to female cable, M3 PCB stands 40/20/10/5mm, 14x M3 nut, 14x M3x6 screw, Velcro set, 4x M3x10 bolt, 1x Robo Grip PCB with accessories, 1x ping pong ball | [PP] |
| Without-micro:bit option | Same minus the micro:bit (the page lists only the full option explicitly) | [PP] |
| Without-battery option | Same minus the 4x AA batteries (inferred from the option name; the page lists only the with-battery packing list) | [PP] |
| Guide book PDF | "202602 BEETLEBIT Quick Start Guide.pdf", 223,581,856 bytes, 96 pages, text layer present | [UM] |
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
Wiring is stated in the booklet Setup Guide (steps 31–36) [UM]; the pin numbers behind each port match the **pxt-zoombit** extension, which every chapter program uses (`github:cytrontechnologies/pxt-zoombit#v0.1.1`) [GH], [PP: hub code].

| Function | Connection | Notes | Src |
|---|---|---|---|
| Motor 1 | REKA:BIT **MOTOR 1**: black (−) → **M1A**, red (+) → **M1B** | pxt-zoombit treats M1 as the **left** motor | [UM], [GH] |
| Motor 2 | REKA:BIT **MOTOR 2**: red (+) → **M2A**, black (−) → **M2B** | pxt-zoombit treats M2 as the **right** motor; the two motors are wired the opposite way round | [UM], [GH] |
| Motor test | slide power ON, press the **M1A, M1B, M2A, M2B** buttons on the REKA:BIT one by one and check each wheel turns the way the booklet arrows show; if not, check the motor wiring | | [UM] |
| Gripper servo | servo port **S1**: orange = S (signal), red = + (power), brown = − (ground) | all chapter programs drive S1 | [UM], [PP: hub code] |
| Ultrasonic sensor | Grove-to-4-pin-female cable into port **P2:P12**: red = Vcc, yellow = Trigger (P2), white = Echo (P12), black = GND | | [UM], [GH] |
| Maker Line sensor | Grove-to-4-pin-female cable into port **P1:P9**: red = Vcc, yellow = AN (analog, P1), white = CAL (calibrate, P9), black = GND | **micro:bit V1: do NOT connect the white (CAL) wire** — leave it disconnected | [UM], [GH] |
| Battery | 4 × AA holder cable into the REKA:BIT DC jack | | [UM] |
| RGB LEDs | P8 (on REKA:BIT) | Bonus 2 lists "RGB LED on REKA:BIT" as an output | [GH], [UM] |
| Headlight pins P13 / P15 | defined by pxt-zoombit | BEETLE:BIT has no LED modules; these blocks are unused | [GH], [PP] |
| Motors and servo | I2C to the REKA:BIT co-processor (address 0x08) | see `reka-bit.md` | [GH] |

## Rules and gotchas (for code, wiring and tutorials)
- **Extension:** add `pxt-zoombit` (search "zoombit" or paste https://github.com/cytrontechnologies/pxt-zoombit). It pulls in `pxt-rekabit` automatically; the chapter projects list only pxt-zoombit as a dependency yet call `rekabit.*` servo blocks [PP: hub code]. Do not tell readers to add a "beetlebit" extension — none exists on GitHub (CytronTechnologies/pxt-beetlebit returns 404) [GH].
- **Gripper angles used by Cytron's code** [PP: hub code]: Chapter 3 activity toggles S1 between **0** (button A) and **180** (button B); Chapters 6 and 7 use **120 = open** and **0 = closed**. After every move the code pauses (100 ms in Ch. 3; 2000 ms in Ch. 6/7) and then calls `disableServo(S1)` so the servo is not held under load. Keep this pattern — a held micro servo on a 4xAA pack is the main power drain.
- **Gripper calibration:** Chapter 3 has a section "Gripper Not Working? Let's Calibrate!" (video); the Chapter 3 Challenge sweeps S1 0 ↔ 180 four times on a loud sound or a shake [PP: hub], [PP: hub code].
- **Drive blocks** (pxt-zoombit) [GH]: `move forward/backward at speed 0–255`, `turn left/right at speed` (spin on the spot: left = M1 backward + M2 forward), `set motors speed: left / right` (-255 to 255), `brake`. Cytron's chapter code uses speed **128** for driving and turning, 50 or 120 near obstacles, and 500 ms turn pulses [PP: hub code].
- **Ultrasonic** [GH]: `ultrasonic distance (cm)` returns 1–255; 255 means no echo or > 255 cm. Cytron's code treats **< 10** as "obstacle" and **< 20** as "slow down" (unit: cm, from the block name) [PP: hub code].
- **Line following** [GH], [PP: hub code]: `line detected on` center / left / right / far left / far right / all / none. Chapter 5 uses asymmetric motor speeds (50/100, then 0/100) to steer back and remembers the last side to recover when the line is lost. Chapter 7 counts T-junctions with `LinePosition.All` (stops after 2) and chains: wait for object < 10 cm → close gripper → follow line → stop at the 2nd junction → open gripper when an object is again < 10 cm.
- **Chapter 2 "Why Doesn't It Go Straight?"** — the hub has a dedicated section and challenge for drift between the two TT motors; fix in code with `set motors speed` rather than blaming the kit [PP: hub].
- **RC mode (Bonus 1)** uses micro:bit **radio group 1** and sends numbers 0–5 (A = forward, B = backward, tilt left/right = turn, shake = toggle gripper, nothing = brake). The same program runs on both micro:bits; the remote is a **second micro:bit, which is not included** [PP: hub code], [PP].
- **micro:bit V1:** the booklet says the kit works with V1 and V2, but leave the Maker Line white (CAL) wire disconnected on V1 [UM]; Chapter 3 Challenge uses the microphone (`onSound(Loud)`, V2 only) [PP: hub code]; Bonus 1 needs an **extra micro:bit V2** and the booklet recommends V2 for both controller and robot to avoid latency [UM].
- **Booklet rules** [UM]: Ch2 — two motors can turn at different speeds at the same voltage, and battery level and floor surface also change the speed, so BEETLE:BIT may drift left or right; Ch3 — disabling the servo after a move switches it off (a servo left enabled grips more strongly but draws power), and **do not force the servo gears by hand**; build step 27 — attach Robo Grip Mini **Part 3 to the first hole** for better grip; Ch4 — slow down when an obstacle is under **20 cm**, stop under **10 cm**; Ch4 challenge — keep a **15 cm** distance (back up if too close); Ch7 — a state machine with states 0, 1, 2; robo-base labels may differ from the booklet — follow the booklet.
- **Flashing:** MakeCode web editor or the MakeCode Offline App; adding an extension may need internet to compile [PP: hub Helpdesk].

## Power and electrical limits
- Kit power: **4x AA batteries** in a holder with a DC jack into the REKA:BIT [PP], [UM]. The holder is fixed to the base with Velcro (booklet build steps) [UM]. A low battery makes the robot move more slowly (Ch2) [UM]. The kit also includes a "Dual Output Cable USB-A to 2.1mm DC barrel & Micro USB" (USB power + data in one cable) [PP].
- Board limits (REKA:BIT datasheet, see `reka-bit.md`): input 3.6–6 V; motors 1 A continuous / 1.5 A peak per channel; servo V+ = input voltage; Grove +3V3 total 300 mA; over 7 V cuts power to motors and servos.
- No battery chemistry (alkaline vs NiMH), run time or current draw is stated by any source read.

## Software support
- **MakeCode** (blocks; JavaScript/Python text modes available in the editor) [PP], [PP: hub].
- Extension: **pxt-zoombit v0.1.1** → depends on pxt-rekabit [PP: hub code], [GH]. Product page wording: MakeCode extension = pxt-rekabit ("BEETLE:BIT (ZOOM:BIT) Extension") [PP] — see *Conflicts*.
- Published chapter programs (MakeCode share links, project names as published) [PP: hub]:
  - Setup Guide — "build BEETLE:BIT, together!" (video + construction-flow diagram on the hub; the booklet prints the steps in full) — https://beetlebit-hub.cytron.io/chapter-resources/beetlebit-setup-guide
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
- **Two kits interfere in RC mode:** every Bonus 1 program uses radio group 1 — change the group per pair [PP: hub code]. Booklet controls: hold A = forward, hold B = backward, tilt left/right = turn, shake = open/close the gripper, upright with no button = stop [UM].
- **Line sensor does nothing on micro:bit V1:** the white CAL wire must be left disconnected [UM].
- **Wheel turns the wrong way:** check the MOTOR 1 / MOTOR 2 wire colours against the table above using the M1A–M2B test buttons [UM].
- **Booklet:** download from https://beetlebit-hub.cytron.io/download (English only is listed) [PP: hub].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| MakeCode extension | [PP] "MakeCode extension = pxt-rekabit ('BEETLE:BIT (ZOOM:BIT) Extension')" | [UM] "add ZOOMBIT extension"; [PP: hub code] every chapter project depends on `pxt-zoombit#v0.1.1` | [UM] wins: tell readers to add **zoombit**; rekabit loads with it. No separate BEETLE:BIT extension exists |
| Hardware counts | [UM] box list: M3 PCB stand 40 mm x5, 20 mm x8, 10 mm x4, 5 mm x4; M3 bolt 6 mm x26; M3 nut x18; plus M3 lock nuts, washers, M2 bolts/nuts | [PP] Accessories Kit: 4x 40 mm, 2x 20 mm, 4x 10 mm, 4x 5 mm stands; 14x M3 nut; 14x M3x6 screw; 4x M3x10 bolt | [UM] outranks [PP]; the product page list looks out of date — ask the EDU team to correct the page |
| Gripper name | [PP] "Robo Grip PCB with accessories"; "Gripper: non-copper PCB with servo motor" | [UM], [PP: hub] "Robo Grip Mini" | Same part; use "Robo Grip Mini (PCB gripper)" and name the servo TS90A |
| Gripper open angle | [PP: hub code] Ch. 3: 0 ↔ 180 | [PP: hub code] Ch. 6/7: open = 120, closed = 0 | Both are Cytron code; 120/0 is the working range used in the task chapters. State both |
| Guide length | [PP] "7-chapter learning guide" | [UM] Setup Guide + Chapters 1–7 + Bonus (2 activities) | Say "7 chapters plus a setup guide and bonus activities" |
| Warranty wording | [PP] "12 months" | [PP: hub] "1 year for manufacturing defects", exclusions listed | Same period; quote the exclusions from the hub |

## Needs verification
- **Hardware counts:** booklet box list vs product page Accessories Kit (see *Conflicts*); the booklet's Maker Line step also uses "M3 bolts (4mm)", which are not in its box list.
- **Product code** `V-BEETLEBIT` is from the product page; codes for the individual options (without micro:bit, Accessories Kit) are not stated.
- Ultrasonic module model: packing list says "Ultrasonic 3V3"; the bracket is "for ultrasonic HC-SR04"; pxt-zoombit's code comment names RCWL-9610. Confirm which module ships.
- Dimensions, weight, assembly time and age range — not stated in the booklet or page.
- Track PDF: line width/length and layout (image only; scale numbers 50–170 visible).
- HuskyLens tutorial series: Grove port and HuskyLens mode — tutorial pages not readable here.
- Run time on 4x AA and whether USB power alone drives motors and servo.
- The booklet's Bonus link points to the old hub address (sites.google.com/cytron.io/beetlebit/...); the current hub is beetlebit-hub.cytron.io.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Chapter 1: Setting Up Beetle:Bit with Huskylens 2](https://my.cytron.io/tutorial/chapter-1-setting-up-beetlebit-with-huskylens-2) — Tutorial, Intermediate, 2025 (series, 5 parts) [PP: tutorial]

## Sources
- [PP] Product page (read by the coordinator 2026-10-19): https://my.cytron.io/p-beetlebit-gripper-robot-car-kit-for-microbit (short link https://my.cytron.io/p-beetlebit)
- [UM] BEETLE:BIT Quick Start Guide booklet (English) — "202602 BEETLEBIT Quick Start Guide.pdf", 96 pages, read in full 2026-10-21: https://drive.google.com/file/d/18ZOwcWVUn0xsEVdcUNOMDvZKf5haVmz5/view
- [UM] BEETLE:BIT Track PDF — "BEETLEBIT Track.pdf": https://drive.google.com/file/d/1uf-ScEUm3Y6hs8ExShzrGi_iHn8ZhFf-/view
- [PP: hub] BEETLE:BIT Resource Hub: https://beetlebit-hub.cytron.io/ — Setup Guide https://beetlebit-hub.cytron.io/chapter-resources/beetlebit-setup-guide ; Chapters https://beetlebit-hub.cytron.io/chapter-resources/chapter-1 … /chapter-7 ; Bonus https://beetlebit-hub.cytron.io/chapter-resources/bonus ; Download https://beetlebit-hub.cytron.io/download ; Helpdesk https://beetlebit-hub.cytron.io/helpdesk
- [PP: hub code] MakeCode projects linked above (read via https://makecode.com/api/<id>/text)
- [GH] https://github.com/CytronTechnologies/pxt-zoombit — main.ts, pxt.json (v0.1.1) via raw.githubusercontent.com
- [GH] https://github.com/CytronTechnologies/pxt-rekabit — README.md, pxt.json (v1.2.3)
- Related KB files: `reka-bit.md`, `maker-line.md`, `zoom-bit.md`
- Not readable here (403 / blocked): https://my.cytron.io/tutorial/chapter-1-setting-up-beetlebit-with-huskylens-2
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
