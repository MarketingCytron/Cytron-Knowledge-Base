# Ikedo Mini Sumo Robot V2 — Verified Reference

| | |
|---|---|
| Product code | `KIT-IKEDO-MSV2-S` [PP] |
| Family | Sumo robot kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-27 |
| Reviewed | 2026-10-27 — W3 Maker Mini Sumo tutorial research: kit motor identified as the 6V 600RPM Medium Power DC Micro Metal Gearmotor `SPG10MP-30K` and its product page read [PP: motor page] (0.065 kg-cm = rated torque); Arduino board to select (Arduino Uno) from Cytron's Hackster screenshot [PP: Hackster screenshot]; AutoSumo / CalibrateEdgeSensors behaviour from the raw example files [GH]. Earlier: 2026-10-19 — master-table review (Medium batch 3): live my.cytron.io product page read (description, features, packing list, resources). The full page now reads: from March 2026 the kit ships with Maker Reflect S edge sensors; full packing list and 500 g class are Cytron-stated |
| Primary source | Getting Started doc: **"Ikedo Bot V2 Getting Started Instruction"** (Google Doc, heading "Ikedo Bot Starter Kit V2 Getting Started Instruction"; no revision number or date printed; Drive metadata: created 7 Dec 2023, last modified 20 Jan 2026) [UM] — https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit. No kit datasheet exists. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the Getting Started Google Doc above. [PP] = my.cytron.io product page as read by the coordinator on 2026-10-19 (two page passages are truncated in that extract). [GH] = CytronMakerSumo library (README, library.properties, examples) read 2026-10-19. The three Cytron tutorials linked from the page (RC sumo, PS2, Bluetooth) could **not** be fetched here (my.cytron.io and www.cytron.io blocked); PS2 wiring facts come from `maker-mini-sumo.md`, which read the PS2 tutorial earlier. The Cytron Hackster guide "Building A Mini Sumo Robot (500g)" (5 Dec 2019) describes the **original** Ikedo Starter Kit (3 opponent sensors), not V2 — only kit-independent facts are taken from it, tagged [PP: Hackster V1]. [PP: motor page] = the kit motor's own Cytron product page, "6V 600RPM Medium Power DC Micro Metal Gearmotor" (`SPG10MP-30K`), https://my.cytron.io/p-6v-600rpm-medium-power-dc-micro-metal-gearmotor, read 27 Oct 2026. [PP: Hackster screenshot] = the Arduino IDE screenshot in Cytron's "Ikedo Mini Sumo Robot Pro" Hackster guide (same controller), read 27 Oct 2026.

**Kit rule:** this file does not re-document the boards. For the controller see `maker-mini-sumo.md`; for the opponent sensor see `maker-object.md`; for the edge sensor see `maker-reflect-s.md` (product page name) and `maker-reflect.md` (Getting Started guide name) — the naming conflict is recorded below.

## What it is
A ready-to-assemble mini sumo robot kit built around the Maker Mini Sumo Controller, with 5 Maker Object opponent sensors, 2 edge sensors, two 6 V micro metal gearmotors, a 7.4 V 450 mAh LiPo and a black 3D-printed PLA chassis [PP][UM]. It is the "upgraded version of the Ikedo Mini Sumo Robot Starter Kit" with "an upgraded chassis design and increased sensor quantity", described as beginner-friendly and "suitable for primary and secondary school" [UM]. The robot is 10 cm × 10 cm and about 200 g [PP]. It supports autonomous ("auto") and manual (RC) control; the RC transmitter/receiver is sold separately [PP]. The controller it uses is positioned for the 500 g mini sumo category (`maker-mini-sumo.md` [PP]); the kit page extract itself does not name a weight class.
Positioning (marketing, not spec): "a reliable choice for your kids to get started in Sumo Robot Competitions"; inspired by the team manager of Ikedo Kogeki "who is also a father of 2 teenage sons" [UM].

## Specifications
No datasheet spec table exists; rows are the product page "Specifications" block and the Getting Started components list.

| Item | Value | Src |
|---|---|---|
| Size | 10 cm × 10 cm | [PP] |
| Weight | ~200 g | [PP] |
| Chassis | Black PLA, 3D printed; "upgraded chassis design"; parts: Main chassis, Top Cover, Motor Bracket | [PP][UM] |
| Controller | Maker Mini Sumo Controller — "Arduino Nano/Uno compatible (ATmega328P)"; USB-serial "CH340C" | [PP] — see `maker-mini-sumo.md` |
| Battery | 7.4 V 450 mAh LiPo (1 ×) | [PP][UM] |
| Opponent sensors | 5 × Maker Object Sensor; page: "range 50cm adjustable" | [PP][UM] — see `maker-object.md` (conflict below) |
| Edge sensors | 2 × Maker Reflect S, mounted underneath — "From March 2026 onwards, Ikedo Mini Sumo Robot V2 will include Maker Reflect S as the edge sensor"; the older guide calls them "Maker Reflectance Sensor" | [PP][UM] |
| Motors | 2 × 600 RPM 6 V DC micro metal gearmotor; page: "6V DC motors (600rpm, 0.065kg.cm)". Motor = "6V 600RPM Medium Power DC Micro Metal Gearmotor", code `SPG10MP-30K` — 0.065 kg-cm is its **rated** torque (stall 0.3 kg-cm); full specs below | [PP][UM][PP: motor page] |
| Wheels | 2 × high grade silicon wheel set 32 mm × 22 mm; blue from 17 Jul 2025 | [PP][UM] |
| Control modes | "auto and manual control mode"; RC transmitter/receiver sold separately | [PP] |
| Programming port | Micro USB-B on the right side of the assembled robot | [UM] |
| Warranty | "There is NO warranty for Sumo Robot." | [PP] |
| Price | RM418.95 (Cytron product page, read 2026-10-19) | [PP] |

### Kit motor — SPG10MP-30K (motor's own product page, read 27 Oct 2026) [PP: motor page]
| Item | Value |
|---|---|
| Name / code | 6V 600RPM Medium Power DC Micro Metal Gearmotor, `SPG10MP-30K` (176 in stock, 3-month warranty) |
| Rated voltage | 6 VDC; tested 3–9 V |
| Free run (6 V) | 600 rpm, 50 mA |
| At rated torque | 500 rpm, 150 mA |
| Rated torque | 0.065 kg-cm |
| Stall (6 V) | 500 mA, 0.3 kg-cm |
| Gear ratio | 30:1 |
| Wire / connector | 5 cm wire with JST PHR-2 (mating socket JST S2B-PH-K-S) |
| Shaft | D-shaft 3 mm × 9 mm |
| Motor size | 10 × 12 × 35.2 mm |
| Page note | "higher voltage will provide higher torque and higher speed, but it will shorten the life of the motor." |

**Kit contents — Getting Started components list [UM]:** 1 × Maker Mini Sumo Controller; 5 × Maker Object Sensor (opponent); 2 × Maker Reflectance Sensor (edge) [link → MAKER-REFLECT page]; 2 × 600RPM 6V DC Micro Metal Gearmotor; 2 × High Grade Silicon Wheels Set (32mm x 22mm); 1 × 7.4V 450mAh LiPo Battery; 1 × Mini Sumo Robot Chassis (Top Cover); 1 × Mini Sumo Robot Chassis (Main); 1 × Mini Sumo Robot Chassis (Motor Bracket); 1 × JST LiPo Battery Wire Extension; 1 × 2561 3Ways Connector Extension Wire; 4 × M3x6 Self-Tapping Screw (Black); 6 × M2.5x20 Bolt; 1 × Tiny Phillips Screwdriver (3mm); 1 × Tiny Flat Head Screwdriver (2mm); 1 × USB Cable (FREE).
**Product page packing list [PP]** (full list read 2026-10-19): see *Product page facts* below.
**Not included:** RC transmitter/receiver [PP]; a LiPo charger appears in neither list [UM][PP] (the V1 Hackster guide states "a LiPo balance charger is not included" [PP: Hackster V1]).
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Page notes:** prices subject to SST from April 2026; "There is NO warranty for Sumo Robot. Please avoid extensive use to prevent damaging the motor"; blue silicone wheels from 17 Jul 2025; **"From March 2026 onwards, Ikedo Mini Sumo Robot V2 will include Maker Reflect S as the edge sensor"** [PP].
- **Class:** "The 10cm x 10cm robot size is designed for 500g Mini Sumo Robot competitions"; compliant with international game standards [PP].
- **Assembly notes:** motor mounting is modular (normal micro metal gearmotor or the high-speed Novamax); leave a 1 mm gap when fitting the motor bracket so it can lever-lock the motor, otherwise the body may bend; keep the PLA chassis out of direct sun and hot cars [PP].
- **Spec list:** 10 × 10 cm; ~200 g; black PLA 3D-printed chassis; 7.4 V 450 mAh LiPo; 5 opponent sensors ("Range: 50cm adjustable"); 2 edge sensors underneath; 2 × 6 V DC motors (600 rpm, "0.065kg.cm"); ATmega328P, Arduino Nano/Uno compatible; CH340C USB-serial; auto and manual (RC, transmitter/receiver not included) modes; start button and external start-module port (module not included); status LEDs; programmable LED, 3-way DIP switch, potentiometer, piezo buzzer; RC servo port; Arduino IDE [PP].
- **Full packing list:** 1x Maker Mini Sumo Controller, 5x Maker Object Sensor (opponent), 2x Maker Reflect S (edge), 2x 600RPM 6V DC micro metal gearmotor, 2x high-grade silicone wheel set (32 × 22 mm), 1x 7.4V 450mAh LiPo, 3D printed parts (chassis, top cover, motor bracket), 1x JST LiPo battery wire extension, 1x 2561 3-way connector extension wire, 4x M3×6 self-tapping screw (black), 6x M2.5×20 bolt, 1x tiny Phillips screwdriver (3 mm), 1x tiny flat-head screwdriver (2 mm), 1x USB cable (free) [PP].
- **Resources:** Ikedo Bot V2 Getting Started Instruction (Google Doc), software set-up (Cytron Hackster guide), STL files (Thingiverse 6719505) [PP].

## Interfaces, terminals and pin mapping
Assembly/wiring facts stated by the Getting Started guide [UM] (controller pin numbers from `maker-mini-sumo.md` [DS] in brackets):
- **Edge sensors:** cut the 2561 3-way extension wire into two, strip the ends, and connect each to the controller's "Front Left and Front Right terminals" — S = white, + = red, − = black. At the sensor: OUT = white, VCC = red, GND = black. [Edge L = A0, Edge R = A1; ports S/+/−, +5 V supply.] Slot the sensors into the chassis holes and fix with 2 × M3x6 self-tapping screws.
- **Battery:** JST LiPo Battery Wire Extension to the Battery Terminal — VB+ = red, VB− = black. Battery sits centred in the chassis; keep "the wire with the white header" tucked outside the chassis for charging.
- **Opponent sensors:** "Attach 4x Maker Object sensors as shown in the figure" (the list says 5 — see Conflicts); the Maker Object must sit "after the slot" when the board slides into the chassis. [Maker Object headers plug straight onto the controller's OPP ports D5/D6/D7/D12/D13; active low.]
- **Board mounting:** slide the controller into the main chassis (the guide warns this "might be a little tricky") and screw its Front Left and Front Right corners with 2 × M3x6 self-tapping screws; a magnetised screwdriver may help.
- **Motors:** press each motor into the wheel hub, tighten the wheel fastener with an Allen key, fit the silicon tyre on the rim. Motor bracket to main chassis with "4x M3x20 Bolt", **not fully tightened — leave a 1 mm gap** so the bracket acts as a lever; "Without this gap, the body may bend." Insert the right motor and tighten the right side, then the left.
- **Motor wiring:** Left motor → MLA = red, MLB = black. Right motor → MRA = black, MRB = red (the guide's heading for this step mistakenly says "left motor wire" again). [MLA/MLB = D3 PWM / D4 DIR; MRA/MRB = D11 PWM / D10 DIR.]
- **Top cover:** 2 × M2.5x20 bolts.
- **Upload:** through the Micro USB-B port on the right side of the robot [UM].
- **RC receiver (manual mode):** no wiring in the kit guide. The library's `RcSumo` example: forward/reverse channel → GPIO1, left/right channel → GPIO2, pins set `INPUT_PULLUP`, neutral 1470 µs, range 1000 µs, 10 % dead band, robot stops when no pulse is received, LED on while moving; "Invert the channel in RC transmitter settings if the direction is reversed." [GH]. [GPIO1 = A2, GPIO2 = A3; ports S/+5V/GND.]
- **Start:** the controller's onboard START button (D2, active low); `AutoSumo` waits for press-and-release, then runs a start routine with a 1 s delay; pressing START again stops the motors [GH].

## Rules and gotchas (for code, wiring and tutorials)
- The guide names the edge-sensor terminals "Front Left and Front Right", which is also how the page describes opponent-sensor positions — in code they are `EDGE_L` / `EDGE_R` (A0/A1), not `OPP_FL` / `OPP_FR` [UM][GH].
- Motor wiring colours differ per side (left red→MLA, right black→MRA) [UM]; direction is wiring-dependent, so verify with the controller's motor test buttons and swap MxA/MxB if reversed (`maker-mini-sumo.md` [DS]).
- Leave the 1 mm bracket gap; over-tightening bends the body [UM].
- Edge thresholds: `AutoSumo` uses fixed 720 (L) / 638 (R) and treats a reading **below** threshold as the white edge; use `CalibrateEdgeSensors` (hold START at power-up, sweep sensors over white edge and black ring, press START) to store thresholds in EEPROM [GH].
- **After calibrating, `AutoSumo` still uses 720 / 638** — it reads `analogRead()` against its own `#define EDGE_L_THRESHOLD` / `EDGE_R_THRESHOLD`, not the EEPROM values. Edit those defines or change the sketch to `isEdgeDetected()` (see `maker-mini-sumo.md`) [GH].
- **Motors on 7.4 V:** the SPG10MP-30K is rated 6 V and tested 3–9 V; its page warns that higher voltage gives more torque and speed "but it will shorten the life of the motor" [PP: motor page]. The kit's 2S pack is above the rated 6 V — expect shorter motor life with hard use (matches the kit page's "avoid extensive use" note [PP]).
- Opponent sensors read LOW when an object is detected; `AutoSumo` searches when all five read HIGH [GH].
- Do not use `tone()` on this controller (it breaks motor PWM on D3/D11) — see `maker-mini-sumo.md`.
- Edge sensor: Maker Reflect S on kits from March 2026 [PP]. It runs at 5.0 V only (Maker Reflect S spec [PP]), which the controller's edge port supplies.
- The page's "range 50cm adjustable" for the opponent sensors is a kit-page figure; the Maker Object datasheet states 40–140 cm on white / 15–60 cm on black (`maker-object.md`). Quote with source.

## Power and electrical limits
- Battery: 1 × 7.4 V 450 mAh LiPo (2S) via JST wire extension to VB+/VB− [PP][UM]. The controller's Vin range is 7.0–18.0 V with reverse-polarity protection (`maker-mini-sumo.md` [DS]).
- Motors are 6 V gearmotors on a 7.4 V pack [PP][UM]. The kit sources state no motor current; the motor's own page gives, at 6 V: 50 mA free run, 150 mA at rated torque, **500 mA stall** [PP: motor page] — well inside the controller's 3 A continuous / 6 A peak (< 5 s) per channel (`maker-mini-sumo.md` [DS]). At 7.4 V the currents are higher than the 6 V figures (not stated — do not quote a derived number).
- Charger: not in the kit [UM][PP]. Cytron's V1 guide: use a LiPo balance charger on its 2-cell port; LEDs red while charging, green when full, blinking = faulty battery; "Charge the battery regularly. Letting it over-drain can damage it." [PP: Hackster V1]
- "There is NO warranty for Sumo Robot." [PP]

## Software support
- Arduino IDE + **Cytron Maker Sumo Library** v1.2.3 (`architectures=avr`, `depends=Servo`), installed from Library Manager; `#include "CytronMakerSumo.h"`; call `MakerSumo.begin()` first [GH].
- Examples: `AutoSumo` (autonomous: start → search → attack → back-off), `RcSumo` (2-channel RC on GPIO1/GPIO2), `CalibrateEdgeSensors`, `TestInputs`, `TestOutputs`; serial examples at 115200 baud [GH].
- Code shipped pre-loaded on the kit: **not stated** by any source.
- USB-serial driver: page says CH340C [PP]; Cytron's V1 guide installs the WCH CH341SER driver (Windows/Mac) and selects the CH340 COM port [PP: Hackster V1]. **Arduino board: Arduino Uno** — "Arduino/Genuino Uno" in the Arduino IDE 1.8.6 screenshot of Cytron's Ikedo Pro Hackster guide (same controller) [PP: Hackster screenshot]; in IDE 2.x: Tools > Board > Arduino AVR Boards > Arduino Uno (not yet bench-tested on IDE 2.x) — see `maker-mini-sumo.md`.
- Cytron tutorials linked from the page (not read here): "Maker Mini Sumo with Bluetooth controller", "Maker Mini Sumo with PS2 controller", "RC sumo using Maker Mini Sumo Controller" [PP].

## Compatibility and accessories
- Controller: Maker Mini Sumo Controller — see `maker-mini-sumo.md`.
- Opponent sensor: Maker Object — see `maker-object.md`. Edge sensor: see `maker-reflect-s.md` / `maker-reflect.md`.
- Manual mode: any 2-channel RC transmitter/receiver (sold separately) on GPIO1/GPIO2 [PP][GH]; `maker-mini-sumo.md` records Cytron's tutorial tested Flysky and HotRC.
- PS2 controller: Cytron tutorial wires DATA→D2, CMD→D7, ATT→D6, CLK→D5 and says to remove the object sensors first (recorded in `maker-mini-sumo.md`).
- Sibling: Ikedo Mini Sumo Robot Pro Bundle (`KIT-IKEDO-MSUMO-P`) — same controller/sensors/battery/chassis size, 800 RPM 3.1 kg.cm motors, steel shield, 4" razor blade, copper weight base, 350 g — see `ikedo-mini-sumo-pro.md` [PP].
- Predecessor: Ikedo Mini Sumo Robot Starter Kit (3 opponent sensors) [UM][PP: Hackster V1].
- Training blade substitute: PCB Plate for Sumo Robot, 10 cm for 500 g robots — see `pcb-sumo-plate.md` [PP].

## Common mistakes / troubleshooting
- No power/melody at switch-on: check VB+/VB− polarity at the terminal and the battery plug [PP: Hackster V1][UM].
- Robot turns instead of driving straight: a motor is wired reversed — swap that motor's two wires [PP: Hackster V1].
- Edge never detected / always detected: thresholds not calibrated for the ring; run `CalibrateEdgeSensors` [GH].
- Wrong terminal: edge wires go to the three-pin green edge terminals, not the opponent headers [UM][DS via `maker-mini-sumo.md`].
- Body bends: motor bracket bolts over-tightened (1 mm gap rule) [UM].
- Expecting a charger or RC set in the box — neither is included [UM][PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Edge sensor identity | [PP] packing list, specs and page note: "From March 2026 onwards … Maker Reflect S as the edge sensor" | [UM] components list: "2 x Maker Reflectance Sensor (edge)", linked to the MAKER-REFLECT page | **Resolved:** Maker Reflect S from March 2026 [PP]; the guide text predates the change |
| Number of Maker Object sensors fitted | [UM] components list: 5 ×; [PP]: 5 × | [UM] assembly step: "Attach **4x** Maker Object sensors as shown in the figure" | Treat as a guide typo; kit has 5 (controller has 5 OPP ports). Flag to doc owner |
| Bolt sizes | [UM] list: "6 x M2.5x20 Bolt" | [UM] steps: "4x M3x20 Bolt" (motor bracket) + "2x M2.5x20 Bolt" (top cover) | Count matches (6); thread size inconsistent in the guide. Don't quote a bolt size |
| Opponent sensor range | [PP] kit page: "range 50cm adjustable" | Maker Object datasheet: 40–140 cm (white), 15–60 cm (black) (`maker-object.md` [DS]) | Datasheet wins for the sensor; the kit page's 50 cm is a page figure |
| USB cable | [UM]: "1 x USB Cable (FREE)" | [PP] full packing list: "1 x USB Cable (FREE)" | Agree: free USB cable included |
| Motor wiring colours | [UM] V2: left MLA=red/MLB=black, right MRA=black/MRB=red | [PP: Hackster V1]: "Red typically goes to MRA… black to MRB", then test and swap | Kit-specific; rule = test with motor buttons |

## Needs verification
- Whether the kit ships with any firmware/example pre-loaded.
- Arduino Uno selection on Arduino IDE 2.x — not yet bench-tested (see `maker-mini-sumo.md`).
- Weight "~200 g": with or without battery not stated.
- Contents and wiring of the three linked Cytron tutorials (RC, PS2, Bluetooth) — pages not readable here.
- Age/syllabus tags on the page (none in the extract).
- Edge sensor on kits sold before March 2026: the Getting Started guide links Maker Reflect (MAKER-REFLECT); confirm whether older stock shipped Maker Reflect.

## Resolved verification items
- **Motor torque "0.065kg.cm"** — resolved 27 Oct 2026: it is the **rated** torque of the kit motor `SPG10MP-30K` (6V 600RPM Medium Power DC Micro Metal Gearmotor); stall torque is 0.3 kg-cm at 6 V [PP: motor page]. Was: "unusually low next to the Pro's 3.1 kg.cm; the motor's own product page was not readable." The Pro uses a different, much stronger motor (800 rpm, 3.1 kg/cm rated — see `ikedo-mini-sumo-pro.md`).
- **Which Arduino board to select** — resolved 27 Oct 2026: Arduino Uno [PP: Hackster screenshot] (see `maker-mini-sumo.md`). Pre-loaded firmware stays open.

## Sources
- [UM] Ikedo Bot V2 Getting Started Instruction (Google Doc; Drive: created 2023-12-07, modified 2026-01-20) — https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit
- [PP] Product page (read by coordinator 2026-10-19) — https://my.cytron.io/p-ikedo-mini-sumo-robot-v2-starter
- [PP] Tutorials linked from the page (not readable here) — https://my.cytron.io/tutorial/rc-sumo-using-maker-mini-sumo-controller · https://my.cytron.io/tutorial/maker-mini-sumo-with-ps2-controller · https://my.cytron.io/tutorial/maker-mini-sumo-with-bluetooth-controller
- [PP: Hackster V1] Cytron Technologies, "Building A Mini Sumo Robot (500g)", 5 Dec 2019 (original Starter Kit) — https://www.hackster.io/cytron-technologies/building-a-mini-sumo-robot-500g-a7a685
- [GH] CytronMakerSumo library (README, library.properties v1.2.3, examples RcSumo/AutoSumo/CalibrateEdgeSensors; raw example files re-read 27 Oct 2026) — https://github.com/CytronTechnologies/CytronMakerSumo
- [PP: motor page] 6V 600RPM Medium Power DC Micro Metal Gearmotor, `SPG10MP-30K` (read 27 Oct 2026; 176 in stock; 3-month warranty) — https://my.cytron.io/p-6v-600rpm-medium-power-dc-micro-metal-gearmotor
- [PP: Hackster screenshot] Arduino IDE 1.8.6 Tools menu (Board "Arduino/Genuino Uno", Port "COM5") in Cytron's "Ikedo Mini Sumo Robot Pro" guide — https://www.hackster.io/cytron-technologies/ikedo-mini-sumo-robot-pro-7da610
- KB cross-references: /home/claude/kb/maker-mini-sumo.md · /home/claude/kb/maker-object.md · /home/claude/kb/maker-reflect-s.md · /home/claude/kb/maker-reflect.md
