# SUMO:BIT Robot Kits - 1kg Sumo Robot for micro:bit — Verified Reference

| Field | Value |
|---|---|
| Product code | V-KIT-SUMOBIT [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. All four kit options are now itemised (Complete / Basic, with or without micro:bit); one LiPo per kit; the kit motor is the 12 V 580 rpm 3.5 kgf·cm part per the packing-list link |
| Primary source | Guide book: "SUMO:BIT Robot Kit \| Assembly (V1)" (Google Slides), Last Updated 2 Dec 2024 [UM], with the companion decks "SUMO:BIT Robot Kit \| Checking" (2 Dec 2024), "\| Maintenance" (2 Dec 2024), "\| Autonomous" (9 Dec 2024) and "\| RC (Remote Control)" (10 Dec 2024) [UM]. No kit datasheet exists; the board datasheet is "SUMO:BIT Datasheet, Rev 1.0, December 2024" (Cytron Google Doc) — board facts live in `sumo-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A complete 1 kg-class sumo robot kit for the BBC micro:bit, built around the SUMO:BIT expansion board (with two MD13S motor drivers attached), five Maker Object opponent sensors, two Maker Reflect edge sensors, two 12 V DC motors, a 3S LiPo battery and a 3D-printed body with a steel blade [PP][UM]. The robot can run autonomously (micro:bit code written in MakeCode) or under remote control (wireless USB joystick, hobby RC receiver, or a second micro:bit as joystick) [UM]. Cytron launch artwork positions it as "Start your sumo journey with the SUMO:BIT Robot Kit" .

Board references — do not re-document here: SUMO:BIT board → see `sumo-bit.md`; MD13S → see `md13s.md`; Maker Object → see `maker-object.md`; Maker Reflect → see `maker-reflect.md`.

## Specifications
No kit-level spec table exists in any source; the rows below are the kit-level facts the guides and product page state. Board ratings (7–25 V input, 13 A / 30 A per channel with MD13S, 5 V 600 mA USB host, etc.) are the SUMO:BIT datasheet's — see `sumo-bit.md`.

| Item | Value | Src |
|---|---|---|
| Competition class | 1 kg sumo robot (product title) | [PP] |
| Purchase options | Complete Kit (with body) / Basic Kit (without body) / 3D Printed Body only, each with or without micro:bit | [PP] |
| Controller | SUMO:BIT board with 2× MD13S attached (see `sumo-bit.md`, `md13s.md`) | [PP] |
| Drive motors | 2× 12 V 580 rpm DC motor with wires | [UM] (Assembly item list; Checking guide: "This test uses a 12V 580RPM DC motor") |
| Drive motors (product page wording) | 2× 12 V brushed DC motor with wires — no rpm or torque stated | [PP] |
| Motor torque | Not stated in any kit source | — |
| Wheels | 2× aluminium rim + silicone tyre wheel set ("Aluminium silicone wheel set"); each rim held by two screws on the motor shaft flat | [UM] |
| Battery | LiPo 11.1 V 1300 mAh (3-cell) — quantity: 1× [PP] vs 2× [UM] (see Conflicts) | [PP][UM] |
| Battery charger | Not included; "2-3 cell LiPo balance charger" offered as an accessory on the page; guide says use a LiPo balance charger or USB LiPo charger | [PP][UM] |
| Full-charge / low-voltage figures | 3-cell LiPo full charge up to 12.6 V; do not let the battery drop below 11 V | [UM] (Maintenance) |
| Opponent sensors | 5× Maker Object (see `maker-object.md`) | [PP][UM] |
| Edge sensors | 2× Maker Reflect (see `maker-reflect.md`); "For best result, use with the latest (11 Dec 2024 onwards) Maker Reflect" | [PP][UM] |
| Robot weight | "robot weight without extra weight is around ±860g" (Complete kit as built) | [UM] (Assembly, optional step 4a) |
| Robot dimensions | Not stated in any source | — |
| Body | 1× 3D-printed main body, 1× right motor bracket, 1× left motor bracket; 2× copper base (bottom weights); 1× steel blade (6" stainless steel per page); 1× PCB plate (training blade substitute); [New] robot back cover (step 13) | [UM][PP] |
| STL files | Free STL body files on the Cytron-SUMOBIT GitHub repository | [PP][GH] |
| Extra weight | Not included; add balancing weights beside the battery compartment, maximum 4 pieces in a row, stacked if needed and covered to prevent short circuits | [UM] |
| Dohyo used in the guide | 1 m diameter | [UM] (Checking) |
| Match duration guidance | "A typical round of sumo robot match lasts around 10 seconds or less"; running continuously for more than 1 minute is "too long and may cause overheating" | [UM] (Maintenance) |
| Programming | Microsoft MakeCode with the "sumobit" extension (https://github.com/CytronTechnologies/pxt-sumobit) | [UM][GH] |
| micro:bit in the "with micro:bit" option | 1× BBC micro:bit V2 + 1× micro:bit Junior Kit + USB Micro B cable | [PP] |
| Warranty | Not stated on the product page (field blank) | [PP] |
| Price | RM80.00–RM1,047.70 across options (Cytron product page, read 2026-10-19) | [PP] |

### Exact packing list
**Complete Kit, with micro:bit (product page):** 1× SUMO:BIT with 2× MD13S attached, small flat screwdriver, Phillips screwdriver, Dean T male connector 18 AWG 15 cm, 5× Maker Object, 2× Maker Reflect, 7× GVS F-F extension cable 10 cm, 2× 12 V brushed DC motor with wires, 2× wheel set, M2 Allen key, 1× LiPo 11.1 V 1300 mAh, 3S LiPo charger cable extension 10 cm, 2× copper base for mini sumo robot, 4× M3 nylon lock nut, 4× M3 bolt 20 mm, 10× M3×6 self-tapping screw, 1× PCB Plate for Blade (training), 1× 6" stainless steel blade, 1× 3D-printed chassis with motor brackets, 1× micro:bit Junior Kit, 1× BBC micro:bit V2, USB Micro B cable, sticker set [PP].

**Assembly guide "List of items for SUMO:BIT Robot Kit" (2 Dec 2024):** Main items — 1× SUMO:BIT board, 1× micro:bit Junior Kit, 5× Maker Object (opponent sensor), 2× Maker Reflect (edge sensor), 2× 12 V 580 rpm DC motor with wires, 2× aluminium silicone wheel set, 2× LiPo battery 11.1 V 1300 mAh. Robot body — 1× 3D-printed main body, 1× right motor bracket, 1× left motor bracket, 2× copper base, 1× steel blade, 1× PCB plate. Accessories — 7× 10 cm GVS female-to-female cables, 1× Dean T male connector with cable, 1× 10 cm 3S LiPo charger cable extension, 1× small flat screwdriver, 1× Phillips screwdriver, 10× M3 tapping screws (6 mm), 4× M3 bolt and nut (20 mm) [UM].

**Basic Kit (without body) and 3D Printed Body only:** the page offers these options but does not itemise them; by the option names the Basic Kit omits the 3D-printed body and the Body-only option is the chassis alone — exact contents not stated (Needs verification). "Without micro:bit" options omit the micro:bit [PP].
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Complete kit (with micro:bit):** SUMO:BIT with 2x MD13S attached, small flat and Phillips screwdrivers, Dean T male connector 18 AWG 15 cm, 5x Maker Object, 2x Maker Reflect, 7x GVS F-F extension 10 cm, 2x 12 V brushed DC motor with wires, 2x wheel set, M2 Allen key, **1x LiPo 11.1 V 1300 mAh**, 3S LiPo charger cable extension 10 cm, 2x copper base, 4x M3 nylon lock nut, 4x M3 bolt 20 mm, 10x M3×6 self-tapping screw, PCB plate for blade (training), 6" stainless steel blade, **3D printed chassis with motor brackets**, micro:bit Junior Kit (BBC micro:bit V2 + USB micro B cable), free sticker set (early adopters) [PP].
- **Complete kit (without micro:bit):** the same without the micro:bit Junior Kit [PP].
- **Basic kit (with / without micro:bit):** the same parts **without the 3D printed chassis**, with a "6\" Blade" (not marked stainless) [PP].
- **Motor:** packing-list link is the Cytron "12V 580RPM 3.5kgfcm High Power Brushed DC Geared Motor" [PP: link].
- **Board spec block (page):** LiPo 7–25 V; 20 kHz with MD13S; 13 A continuous, 30 A peak (≤ 10 s) per channel; USB host 5 V 600 mA; servo 5 V; +5 V total 600 mA; MD13S 61 × 33 mm [PP].
- Prices subject to SST from April 2026 [PP]. Resources: datasheet, MakeCode extension, sample code, CAD, GitHub (UF2, STL), Assemble / Checking / Maintenance / Autonomous / RC slides, body STL [PP].

## Interfaces, terminals and pin mapping
Kit wiring as the Assembly guide states it (board port labels; micro:bit pin numbers behind each label are in `sumo-bit.md`) [UM]:

| Component | SUMO:BIT port | Cable | Src |
|---|---|---|---|
| Left Maker Reflect (edge) | EDGE-L | 10 cm GVS F-F; sensor pins OUT, VCC, GND | [UM] |
| Right Maker Reflect (edge) | EDGE-R | 10 cm GVS F-F | [UM] |
| Left Maker Object | OPP-L | 10 cm GVS F-F; sensor pins GND, VCC, OUT | [UM] |
| Front-left Maker Object | OPP-FL | 10 cm GVS F-F | [UM] |
| Front-centre Maker Object | OPP-FC | 10 cm GVS F-F | [UM] |
| Front-right Maker Object | OPP-FR | 10 cm GVS F-F | [UM] |
| Right Maker Object | OPP-R | 10 cm GVS F-F | [UM] |
| Left / right motors | LEFT MOTOR / RIGHT MOTOR terminals (bottom) | motor wires | [UM] |
| Battery | Battery terminal via Dean T male connector cable — "CHECK POLARITY!" | Dean T + 3S charger extension | [UM] |
| RC receiver (RC mode) | SERVO/RC port 1 = speed (forward/reverse), port 2 = steering (left/right) | — | [UM] |
| Wireless USB joystick receiver | USB-A joystick port | — | [UM] |

Assembly sequence (Assembly (V1) deck) [UM]: (1) fit the two Maker Reflect edge sensors with M3 tapping screws, cable through the hole; (2) fit the two copper bases under the robot, two M3 tapping screws each; (3) lock nuts into the motor brackets, motors into brackets, brackets onto the body (tighten only after cables are routed); the guide shows a 2–3 mm gap at the motor; (4) cable the Maker Object sensors and slot them in from inside the body; (4a, optional) add extra weights; (5) connect motors and power to the board, attach the LiPo charging extension, connect the battery; (6) power on and press the Motor Alignment button — both motors must rotate forward; if one runs backward, swap its two wires on the motor terminal; (7) connect the sensor cables per the table above; (8) mount the board with four M3 tapping screws, tidy cables inside the body; (9) fit aluminium rims (align with the shaft flat, two screws each) and silicone tyres; (10) insert the micro:bit with buttons and LED matrix facing up — "Only required for autonomous sumo robots"; (11) stick on the PCB plate (practice) or blade (tournaments) with thin, strong double-sided tape; (12, optional, not included) robot holder from ~30 cm of fibre tape through the body holes; (13, new) back cover fixed with double-sided tape and the mounting screws.

## Rules and gotchas (for code, wiring and tutorials)
- Remove the micro:bit for USB-joystick and RC-receiver modes; the micro:bit is only needed for autonomous (and micro:bit-as-joystick) operation [UM].
- Turn the robot off before plugging the USB cable into the micro:bit; program via MakeCode direct flashing or by copying the .hex, or wirelessly from an iPad/iPhone/Android app after pressing the micro:bit reset button three times to enter Bluetooth mode [UM].
- Programming flow (computer): turn off robot → build code → connect USB to micro:bit → flash → unplug USB → power up robot → test. Tablet: build code → turn on robot → micro:bit into Bluetooth mode → flash wirelessly → test [UM].
- Edge-sensor readings the guide records as examples: Left (black) 772, Right (black) 856, Left (white) 60, Right (white) 72; battery voltage example 12.05 V [UM]. These are examples, not thresholds.
- Autonomous sample programs (MakeCode 1–8): read edge sensors and battery voltage; robot navigation (A = turn right a bit, B = turn left a bit); move around the dohyo; detect the obstacle; basic sumo robot with a 5 s countdown on button A; [Community] sumo robot with DIP strategies started by button; [Community] DIP strategies started by IR Sumo Start; more sample code "in progress" [UM]. The decks embed the code as MakeCode links; the DIP strategy logic itself is not explained in text.
- USB joystick mode: turn off robot, remove micro:bit, plug in the USB receiver, turn on and wait until the RGB LEDs stay **yellow**, then turn on the joystick. "Currently, this mode only support for this model - USB Joystick" (the Cytron USB Joystick accessory). Two control schemes: gamepad direction at half speed with R2 held for full speed, or left/right analog sticks at half speed with R2 for full speed [UM].
- RC-receiver mode: turn off robot, remove micro:bit, receiver into SERVO/RC port 1 (speed) and port 2 (steering), **turn on the RC transmitter first**, then the robot; wait until the RGB LEDs stay **orange** [UM]. Example receiver mappings: FlySky FS-iA6B CH2 → RC PORT 1, CH4 → RC PORT 2; Hot RC F-06A CH2 → RC PORT 1, CH1 → RC PORT 2; Dumborc X6F CH2 → RC PORT 1, CH1 → RC PORT 2 [UM].
- micro:bit-as-joystick mode (Joystick:bit V2 used as the remote): code is needed on both transmitter and receiver, which also allows semi-auto behaviour; before running, press button B on the joystick to set the edge-sensor threshold. Guide button map: A = display robot battery voltage, B = set edge threshold, C = attack left, D = attack right, E = lower speed, F = full speed; direction at half speed [UM]. A second micro:bit and a Joystick:bit are not in the kit.
- Motor alignment: with the robot at the edge of a 1 m dohyo facing the centre, press the alignment button; after 1 s it drives forward and stops. If it veers left, turn the trimmer slightly right (and vice versa); repeat [UM].
- Opponent-sensor range (optional): with a tiny flat screwdriver in the Maker Object sensing-range trimmer, turn clockwise until the indicator LED turns off, then slowly back until it just turns on = maximum range; black surfaces are harder to detect [UM].
- Firmware update (only when a new version is released): download the .uf2 from the SUMO:BIT GitHub page, robot off, hold the SUMO:BIT boot button while connecting USB-C, release, copy the .uf2 to the RPI-RP2 drive [UM].
- The blade is sharp — "Please exercise extra CAUTION!" [UM]. Use the PCB plate for practice and the blade for tournaments [UM].

## Power and electrical limits
- Battery: 3-cell LiPo 11.1 V 1300 mAh via a Dean T connector; full charge up to 12.6 V; do not discharge below 11 V ("may damage the battery permanently"); use a LiPo balance charger or USB LiPo charger and a battery checker [UM]. The charger is not in the kit [PP].
- Check battery polarity at the board terminal before connecting [UM].
- Motors are high-current and heat quickly: check motor-bracket temperature during practice and rest the robot if warm; >1 minute continuous running is too long [UM].
- Board limits (7–25 V, 13 A continuous / 30 A ≤10 s per channel with MD13S, 5 V 600 mA total): see `sumo-bit.md` [DS].

## Software support
- Microsoft MakeCode with the "sumobit" extension (search "sumobit" or paste https://github.com/CytronTechnologies/pxt-sumobit under Extensions); a SUMO:BIT category drawer appears [UM][GH].
- Sample programs are linked from the Autonomous and RC decks as MakeCode share links (not reproduced as text) [UM].
- Firmware (.uf2) and STL body files: https://github.com/CytronTechnologies/Cytron-SUMOBIT [PP][GH]. Repository file list not readable here (GitHub API restricted).
- Beginners are pointed to the micro:bit "Transfer code" guide and Cytron's EDU:BIT / ZOOM:BIT Chapter 1 "Hello World" [UM].
- Support: Telegram "SUMO:BIT Support Group" https://t.me/sumobit_support [DS][GH].

## Compatibility and accessories
- Accessories offered on the page: USB Joystick (the only joystick model the USB mode supports), 2–3 cell LiPo balance charger [PP][UM].
- RC receivers shown as examples: FlySky FS-iA6B, Hot RC F-06A, Dumborc X6F [UM].
- Joystick:bit V2 (with its own micro:bit) for micro:bit-as-joystick mode [UM] — not included.
- IR Sumo Start module for competition start (community sample code) — see `ir-sumo-start.md` [UM].
- PCB Plate for Sumo Robot (15 cm plate recommended for 1 kg robots) is the training blade substitute [PP].
- Run only on a dohyo (or a clean flat surface for RC testing); avoid tiles, uneven, dusty floors and carpet [UM].

## Common mistakes / troubleshooting
- Robot does not move straight → adjust the alignment trimmer and re-test with the alignment button [UM].
- A motor runs backward at the alignment test → swap that motor's two wires at the motor terminal [UM].
- Opponent LED on the board stays on / never lights → re-check the Maker Object range trimmer; test by moving a hand in front of each sensor in an open area [UM].
- Silicone tyres lose grip → clean with a dust roller, or remove from the rim and wash with water/IPA; replace if heavily soiled [UM].
- Screws loosen after impacts → inspect and tighten regularly, especially near the motors [UM].
- Power LED on but Motor Alignment LEDs not lit after 1 s → power-up check fails (CHECK 1) [UM].
- Battery will not recover → it was discharged below 11 V [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Number of LiPo batteries | [PP] packing lists (all four options, read 2026-10-20): 1× LiPo 11.1 V 1300 mAh | [UM] Assembly item list: "2x LiPo battery 11.1V 1300mAH" | **One** per kit [PP]; the guide's "2x" is a typo |
| Motor speed | [PP] "12V brushed DC motor" (no rpm) | [UM] "12V 580rpm DC motor" | 580 rpm [UM] |
| Number of Maker Object sensors | [PP][UM] item list: 5× | [UM] Assembly step 4: "Repeat for all four Maker Object sensors" | 5 sensors wired to OPP-L, OPP-FL, OPP-FC, OPP-FR, OPP-R (step 7 lists all five); "four" is a slide typo |
| OPP-FC label | [UM] Assembly step 7: OPP-FC = front-centre | [UM] Assembly layout slide labels OPP-FC "Front-right opponent sensor" | Front-centre (layout caption is a copy error) |
| Accessories in the kit | [PP]: M2 Allen key, USB Micro B cable, sticker set, 4× M3 nylon lock nut + 4× M3 bolt | [UM] list: "4x M3 bolt and nut (20mm)"; no Allen key, USB cable or stickers listed | Page list is the fuller, later list; the guide's list predates the sticker set / Allen key — not a true contradiction |
| Datasheet source | KB `sumo-bit.md` cites a RobotShop mirror, "No Cytron Google Doc found" | Product page links the Cytron Google Doc "SUMO:BIT Datasheet", Rev 1.0, December 2024 | Same revision and date; feature list and Table 4 values match the mirror. The Doc adds the Telegram link https://t.me/sumobit_support |

## Needs verification
- Robot dimensions (footprint, height) — not stated; "1kg" is the class, the built weight is "around ±860g" before extra weight.
- Contents and version names of the firmware .uf2 and STL files in the Cytron-SUMOBIT repository (listing blocked; only the README was read).
- Which DIP-switch strategies the community sample programs implement (code is behind MakeCode links, not in text).
- Warranty terms (page field blank; other Cytron sumo kits state "no warranty").
- Tutorial "Build a 1kg Sumo Robot with SUMO:BIT" (https://my.cytron.io/tutorial/build-sumo-robot-with-sumobit, linked from the GitHub README) — not readable here.
- Motor gear ratio and stall current — torque 3.5 kgf·cm comes only from the packing-list product link.
- Whether a "3D printed body only" option is still sold (the page now lists four kit options only).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Joystick Pairing with SUMO:BIT and Motion 2350 Pro](https://my.cytron.io/tutorial/joystick-pairing-with-sumobit-and-motion-2350-pro) — Tutorial, 2026 [PP: tutorial]

## Sources
- [PP] https://my.cytron.io/p-sumobit-robot-kits-1kg-sumo-robot-for-microbit — product page facts as read by the coordinator on 2026-10-19 (page not fetched directly).
- [UM] SUMO:BIT Robot Kit | Assembly (V1), Last Updated 2 Dec 2024 — https://docs.google.com/presentation/d/15mmPIKEZlVMuslrhgAz_jTQuCI3Ud2Z0r1F7EQjnnpk/edit
- [UM] SUMO:BIT Robot Kit | Checking, Last Updated 2 Dec 2024 — https://docs.google.com/presentation/d/1IIAHdn9vYMl6ZR5Ub8dk4i2zn8G9e9ShdCyVT6yuVlY/edit
- [UM] SUMO:BIT Robot Kit | Maintenance, Last Updated 2 Dec 2024 — https://docs.google.com/presentation/d/1zcng7FHubdTSolIi3hU9j0wFy4-cY3OerctyFiYaqQo/edit
- [UM] SUMO:BIT Robot Kit | Autonomous, Last Updated 9 Dec 2024 — https://docs.google.com/presentation/d/1sWe9CB2GGSZ_7k4SaaBzzJjmZi5ORKxCjjZvQOVthN4/edit
- [UM] SUMO:BIT Robot Kit | RC (Remote Control), Last Updated 10 Dec 2024 — https://docs.google.com/presentation/d/1kkcqsfMDE5pzGX8FfeEHsAbjzOgs4QZmaKBYXHFHvfE/edit
- [DS] SUMO:BIT Datasheet, Rev 1.0, December 2024 (Cytron Google Doc) — https://docs.google.com/document/d/1xHrA7EkQ8gn0syVS93uhbWAVt8z3viTB763gGpLsC8k/edit (board facts: see `sumo-bit.md`)
- [GH] https://github.com/CytronTechnologies/Cytron-SUMOBIT — README read via raw.githubusercontent.com; file listing not accessible
- [GH] https://github.com/CytronTechnologies/pxt-sumobit — README and pxt.json (v1.3.6)
- KB cross-references: `sumo-bit.md`, `md13s.md`, `maker-object.md`, `maker-reflect.md`, `ir-sumo-start.md`
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
