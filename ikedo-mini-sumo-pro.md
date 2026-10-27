# Ikedo Mini Sumo Robot Pro Bundle — Verified Reference

| | |
|---|---|
| Product code | `KIT-IKEDO-MSUMO-P` [PP] (RobotShop lists the same manufacturer number [3P]) |
| Family | Sumo robot kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-27 |
| Reviewed | 2026-10-27 — W3 Maker Mini Sumo tutorial research: 800 RPM motor specs (NovaMax 6V 800RPM Super Power DC Micro Metal Gearmotor) from Cytron's "Let's Upgrade your Mini Sumo to 1kg Sumo Robot" tutorial [PP: tutorial SumoRobot1KG] and the NovaMax product page [PP: NovaMax page]; Arduino board to select (Arduino Uno) from the Pro Hackster guide screenshot [PP: Hackster screenshot]; AutoSumo threshold behaviour from the raw example files [GH]. Earlier: 2026-10-19 — master-table review: live product page re-read in full — the two truncated passages are now complete: specs (on-board start button + port for an external start module, LEDs, DIP switch, potentiometer, buzzer, servo port) and packing list (2561 wire, 8 × M3×6, 4 × M3×18, 4 nuts, 2 screwdrivers, USB cable; no top cover, no charger). Robot kit — the controller follows its datasheet (`maker-mini-sumo.md`); kit parts follow the product page (no Pro guide book exists) |
| Primary source | **Cytron product page** (read by the coordinator 2026-10-19) [PP] — https://my.cytron.io/p-ikedo-mini-sumo-robot-pro-kit. No kit datasheet, manual or Getting Started doc covers the Pro: the "Ikedo Bot V2 Getting Started Instruction" states "Product Included: Ikedo Mini Sumo Robot Starter Kit V2" only [UM-V2]. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = product page, re-read in full 2026-10-19 (specs list and packing list complete). [UM-V2] = the V2 Getting Started Google Doc, used only for facts shared with the V2 kit (same controller, sensors, battery) and clearly labelled. [GH] = CytronMakerSumo library (read 2026-10-19). [PP: Hackster Pro] = Cytron's own "Ikedo Mini Sumo Robot Pro" Hackster guide (15 Jan 2020) — **not readable here** (fetch blocked); the facts quoted from it are those already recorded in `maker-mini-sumo.md`. The tutorial https://my.cytron.io/tutorial/SumoRobot1KG linked from the page could not be fetched on 19 Oct; its motor table was read on 27 Oct 2026 (W3 tutorial research) and is tagged [PP: tutorial SumoRobot1KG]. [PP: NovaMax page] = Cytron product page "6V 800RPM Super Power DC Micro Metal Gearmotor (NovaMax)", https://my.cytron.io/p-6v-800rpm-super-power-dc-micro-metal-gearmotor-novamax (read 27 Oct 2026). [PP: Hackster screenshot] = the Arduino IDE 1.8.6 Tools-menu screenshot inside the Pro Hackster guide (read 27 Oct 2026); the guide's text never names the board. The board datasheets linked from the page (Maker Mini Sumo, Maker Object, "Datasheet for Edge Sensor (MAKER-REFLECT-S)") are documented in their own KB files.

**Kit rule:** boards are not re-documented here — see `maker-mini-sumo.md`, `maker-object.md`, `maker-reflect-s.md`.

## What it is
The higher-specification Ikedo mini sumo kit: the same Maker Mini Sumo Controller, 5 Maker Object opponent sensors, 2 Maker Reflect S edge sensors, 7.4 V 450 mAh LiPo and 10 cm × 10 cm black PLA chassis as the V2 Starter, but with 800 RPM / 3.1 kg.cm 6 V micro metal gearmotors, a laser-cut stainless steel shield, a 4" stainless steel razor blade and a copper weight base, bringing the robot to 350 g [PP]. Supports auto and manual (RC) mode; the RC transmitter/receiver is sold separately [PP]. RobotShop's listing (cross-check only) calls it "one of the most powerful fighting machine" with "super powerful micro size metal geared DC motor (800 RPM)" [3P].
Positioning (marketing, not spec): "Pro" bundle for competition builders; the controller's page positions it from beginners up to "professional robot builder[s]" in international 500 g sumo competitions (`maker-mini-sumo.md` [PP]).

## Specifications
No datasheet spec table exists; rows are the product page "Specifications" block.

| Item | Value | Src |
|---|---|---|
| Size | 10 cm × 10 cm | [PP] |
| Weight | 350 g | [PP] |
| Chassis | Black PLA (3D printed); packing list: 1 × chassis (main), 1 × 3D printed motor bracket | [PP] |
| Controller | Maker Mini Sumo Controller — "ATmega328P", USB-serial "CH340C" | [PP] — see `maker-mini-sumo.md` |
| Battery | 7.4 V 450 mAh LiPo (1 ×) | [PP] |
| Opponent sensors | 5 × Maker Object; "range 50cm adjustable" | [PP] — see `maker-object.md` (conflict below) |
| Edge sensors | 2 × Maker Reflect S; page links "Datasheet for Edge Sensor (MAKER-REFLECT-S)" | [PP] — see `maker-reflect-s.md` |
| Motors | 2 × 800 RPM 6 V DC micro metal gearmotor; "6V DC motors (800rpm, 3.1kg.cm)". Same 800 rpm / 3.1 kg figures as Cytron's NovaMax 6V 800RPM Super Power gearmotor — full motor specs below | [PP][PP: tutorial SumoRobot1KG] |
| Wheels | 2 × silicon wheels 32 mm × 22 mm; blue from July 2025 | [PP] |
| Armour / blade | 1 × laser-cut stainless steel shield; 1 × 4" stainless steel razor blade; 1 × copper weight base | [PP] |
| Control modes | "auto and manual mode"; RC sold separately | [PP] |
| Start | On-board start button **and a port for an external start module** (start module not included) | [PP] |
| On-board user features (controller) | LEDs, DIP switch, potentiometer, buzzer, servo port — see `maker-mini-sumo.md` | [PP] |
| USB cable | Free, included from 25 Aug 2024 | [PP] |
| Warranty | "NO warranty for Sumo Robot." | [PP] |
| Price | RM693.00 (Cytron product page, read 2026-10-19) | [PP] |

### 800 RPM motor — NovaMax 6V 800RPM Super Power DC Micro Metal Gearmotor
The Pro page names the motor only as "800RPM 6V DC micro metal gearmotor"; the NovaMax figures below match its 800 rpm / 3.1 kg rating (match inferred from the figures; the Pro page does not print the NovaMax name).

| Item | Value | Src |
|---|---|---|
| Nominal voltage | 6 VDC; "can withstand up to 12VDC" | [PP: NovaMax page] |
| Operating voltage (tutorial table) | 6–16 VDC, normal 6 VDC, max 16 VDC — **conflicts with the product page's 12 VDC; product page wins** (see Conflicts) | [PP: tutorial SumoRobot1KG] |
| Speed | 800 rpm at 6 VDC | [PP: tutorial SumoRobot1KG] |
| No-load current | 190 mA | [PP: tutorial SumoRobot1KG] |
| Operating current | 260 mA | [PP: tutorial SumoRobot1KG] |
| Stopping (stall) current | **5.75 A** | [PP: tutorial SumoRobot1KG] |
| Rated load torque | 3.1 kg/cm | [PP: tutorial SumoRobot1KG] |
| Stall torque | 4.5 kg/cm | [PP: tutorial SumoRobot1KG] |
| Battery advice | "To using this motor in Sumo Robot, we highly recommend to use 2S Battery (7.4V) only" | [PP: tutorial SumoRobot1KG] |
| Installation | Bend both terminals inward, solder on the outside, and cover with cloth tape "to prevent accidental contact that could short-circuit and damage the motor driver" | [PP: NovaMax page] |

**Packing list [PP]:** 1 × Maker Mini Sumo Controller, 5 × Maker Object, 2 × Maker Reflect S, 2 × 800RPM 6V DC micro metal gearmotor, 1 × 3D printed motor bracket, 2 × silicon wheels 32x22mm, 1 × 7.4V 450mAh LiPo, 1 × chassis (main), 1 × laser-cut stainless steel shield, 1 × 4" stainless steel razor blade, 1 × copper weight base, JST LiPo wire extension, 1 × 2561 3-way connector extension wire, 8 × M3×6 screws, 4 × M3×18 screws, 4 × nuts, 2 × tiny screwdrivers, free USB cable.
**Not included:** RC transmitter/receiver; external start module; LiPo charger; no separate top cover is listed [PP].

### Differences from the V2 Starter (`ikedo-mini-sumo-v2.md`) [PP]
| Item | V2 Starter (`KIT-IKEDO-MSV2-S`) | Pro Bundle (`KIT-IKEDO-MSUMO-P`) |
|---|---|---|
| Motors | 600 RPM 6 V, "0.065kg.cm" (rated torque; `SPG10MP-30K`, stall 500 mA at 6 V) | 800 RPM 6 V, 3.1 kg.cm (NovaMax figures: stall 5.75 A) |
| Weight | ~200 g | 350 g |
| Armour | none listed | laser-cut stainless steel shield + 4" stainless steel razor blade + copper weight base |
| Chassis parts listed | chassis, top cover, motor bracket | chassis (main), 3D printed motor bracket (top cover not in the visible list) |
| Price (2026-10-19) | RM418.95 | RM693.00 |
| Shared | Maker Mini Sumo Controller, 5 × Maker Object, 2 × Maker Reflect S, 7.4 V 450 mAh LiPo, 32 × 22 mm silicon wheels, 10 × 10 cm, auto + manual mode, no warranty | |

## Interfaces, terminals and pin mapping
No Pro-specific assembly document was readable. Facts that carry over because the controller, sensors and battery are the same parts:
- **Battery:** JST LiPo wire extension to the controller's Battery Terminal, VB+ = red, VB− = black [UM-V2]; Cytron's Pro Hackster guide uses a 2-cell LiPo [PP: Hackster Pro, via `maker-mini-sumo.md`].
- **Edge sensors:** the 2561 3-way wire is cut in two to wire each Maker Reflect S to an edge terminal — S/OUT = white, +/VCC = red, −/GND = black [UM-V2]. Controller edge inputs are analog A0 (`EDGE_L`) / A1 (`EDGE_R`) (`maker-mini-sumo.md` [DS]).
- **Opponent sensors:** 5 × Maker Object plug onto the controller's five OPP ports (`OPP_FC` D6, `OPP_FL` D5, `OPP_FR` D7, `OPP_L` D12, `OPP_R` D13), active low (`maker-mini-sumo.md` [DS][GH]).
- **Motor terminals (NovaMax):** bend both motor terminals inward, solder the wires on the outside and cover with cloth tape so they cannot touch and short the motor driver [PP: NovaMax page].
- **Motors:** MLA/MLB and MRA/MRB screw terminals. The Pro Hackster guide wires red→MRA, black→MRB and then checks direction with the motor test buttons [PP: Hackster Pro, via `maker-mini-sumo.md`]; the V2 guide wires left MLA=red/MLB=black and right MRA=black/MRB=red [UM-V2]. Direction is wiring-dependent — test and swap.
- **Start:** "on-board start button" [PP] = controller START (D2, pulled high, active low; external start/IR start module port in parallel) (`maker-mini-sumo.md` [DS]).
- **RC receiver (manual mode):** `RcSumo` example — forward/reverse channel → GPIO1, left/right → GPIO2 (`INPUT_PULLUP`, neutral 1470 µs, range 1000 µs, 10 % dead band, stop on signal loss) [GH]. GPIO1 = A2, GPIO2 = A3 with S/+5V/GND pins (`maker-mini-sumo.md` [DS]). Using GPIO1/2 leaves all sensor ports free, so one robot can enter both RC and autonomous categories (`maker-mini-sumo.md` [PP]).
- **Programming:** Micro USB-B on the controller; Windows needs the WCH CH341SER driver (CH340 COM port) [PP: Hackster Pro, via `maker-mini-sumo.md`]; page says CH340C [PP].

## Rules and gotchas (for code, wiring and tutorials)
- The Pro's 800 RPM / 3.1 kg.cm motors are far stronger than the V2's; the controller is rated 3 A continuous / 6 A peak (< 5 s) per channel and the controller's page says motors over 3 A "will cause the motor driver chip to burn" and are not covered (`maker-mini-sumo.md` [DS][PP]). The NovaMax stall current is **5.75 A at 6 V** [PP: tutorial SumoRobot1KG] — close to the controller's 6 A peak (< 5 s); on a full 2S pack (above 6 V) the stall current is higher. Avoid long stalls (pushing matches); do not quote a derived stall figure as a spec.
- Cytron "highly recommend[s]" a 2S (7.4 V) battery only for this motor in a sumo robot [PP: tutorial SumoRobot1KG] — the kit's 7.4 V 450 mAh LiPo matches.
- "NO warranty for Sumo Robot" [PP] — do not promise the controller's usual 12-month warranty inside this bundle.
- The copper weight base and steel shield are what take the robot from ~200 g to 350 g; the 500 g class limit is a competition rule, not a kit spec — cite the competition rulebook, not Cytron.
- The 4" razor blade is a real blade; the PCB Plate for Sumo Robot (10 cm, for 500 g robots) exists as a training substitute (`pcb-sumo-plate.md` [PP]).
- Edge logic: `isEdgeDetected()` is true when the analog reading is **below** threshold (white edge reads lower); calibrate with `CalibrateEdgeSensors` (thresholds in EEPROM from address 0) [GH].
- Never use `tone()` on this controller (`maker-mini-sumo.md`).
- Opponent sensor "range 50cm adjustable" is a kit-page figure; the Maker Object datasheet gives 40–140 cm (white) / 15–60 cm (black) (`maker-object.md`).

## Power and electrical limits
- 1 × 7.4 V 450 mAh LiPo (2S) [PP]; controller Vin 7.0–18.0 V, reverse-polarity protected, +5 V output 500 mA total (`maker-mini-sumo.md` [DS]).
- Motor channel limit 3 A continuous / 6 A peak < 5 s (`maker-mini-sumo.md` [DS]).
- 800 RPM motor (NovaMax figures): no-load 190 mA, operating 260 mA, stall 5.75 A at 6 V [PP: tutorial SumoRobot1KG]; nominal 6 VDC, withstands up to 12 VDC [PP: NovaMax page].
- Charger: not in the visible packing list [PP]. Cytron's V1 guide: LiPo balance charger sold separately; charge regularly, do not over-drain; blinking charger LEDs = faulty battery (`ikedo-mini-sumo-v2.md` [PP: Hackster V1]).
- Warranty: none for the Sumo Robot [PP].

## Software support
- Arduino IDE + Cytron Maker Sumo Library v1.2.3 (`architectures=avr`, `depends=Servo`); examples `AutoSumo`, `RcSumo`, `CalibrateEdgeSensors`, `TestInputs`, `TestOutputs`; 115200 baud [GH]. The page links the library directly [PP].
- Library install per Cytron's Pro guide: Tools > Manage Libraries, search "maker sumo" [PP: Hackster Pro, via `maker-mini-sumo.md`].
- Pre-loaded code: not stated. **Arduino board: Arduino Uno** — "Arduino/Genuino Uno" (Port "COM5") in the Arduino IDE 1.8.6 screenshot of Cytron's Pro Hackster guide [PP: Hackster screenshot]; in IDE 2.x: Tools > Board > Arduino AVR Boards > Arduino Uno (not yet bench-tested on IDE 2.x).
- After `CalibrateEdgeSensors`, `AutoSumo` still uses its fixed 720 / 638 edge thresholds unless you edit the defines or use `isEdgeDetected()` [GH] (see `maker-mini-sumo.md`).
- Page tutorials: "SumoRobot1KG" and others [PP] — not readable here.

## Compatibility and accessories
- Controller `maker-mini-sumo.md`; opponent sensor `maker-object.md`; edge sensor `maker-reflect-s.md`.
- RC: any 2-channel transmitter/receiver on GPIO1/GPIO2 [GH]; Cytron tested Flysky and HotRC (`maker-mini-sumo.md` [PP tutorial]).
- PS2 controller: DATA→D2, CMD→D7, ATT→D6, CLK→D5, object sensors removed (`maker-mini-sumo.md` [PP tutorial]).
- IR Sumo Start module: fits the controller's start port in principle (`ir-sumo-start.md`), but no source links it to this kit.
- Sibling: Ikedo Mini Sumo Robot V2 (`KIT-IKEDO-MSV2-S`) — `ikedo-mini-sumo-v2.md`.
- Training plate: `pcb-sumo-plate.md` (10 cm variant for 500 g robots) [PP].

## Common mistakes / troubleshooting
- Calling it a 1 kg robot: it is a 350 g, 10 × 10 cm mini sumo build [PP]; the "SumoRobot1KG" tutorial link on the page is a cross-link, not a kit spec.
- Expecting a top cover, charger or RC set: only the items in the packing list are confirmed; the list is truncated [PP].
- Motor spins the wrong way: swap that motor's MxA/MxB wires after testing with the motor buttons [PP: Hackster Pro][UM-V2].
- Edge never/always detected: run `CalibrateEdgeSensors` on the actual ring [GH].
- Driver damage from stronger motors is not covered by warranty (`maker-mini-sumo.md` [PP]); the bundle itself has no warranty [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Opponent sensor range | [PP] kit page: "range 50cm adjustable" | Maker Object datasheet: 40–140 cm white / 15–60 cm black (`maker-object.md` [DS]) | Datasheet wins for the sensor |
| Motor wiring colours | [PP: Hackster Pro]: red→MRA, black→MRB (recorded in `maker-mini-sumo.md`) | [UM-V2]: right MRA=black, MRB=red | Wiring-dependent; verify with motor test buttons |
| Edge sensor in Ikedo kits | [PP] Pro page: Maker Reflect S (with MAKER-REFLECT-S datasheet link) | [UM-V2] V2 guide: "Maker Reflectance Sensor" → MAKER-REFLECT page | For the Pro, only the page speaks: Maker Reflect S. The V2 conflict stays open in `ikedo-mini-sumo-v2.md` |
| 800 RPM motor maximum voltage | [PP: tutorial SumoRobot1KG]: operating 6–16 VDC, "max 16 VDC" | [PP: NovaMax page]: nominal 6 VDC, "can withstand up to 12VDC" | Product page wins for the motor: **12 VDC max**. Tutorial table to be corrected (Marketing team) |
| Kit coverage of the Getting Started doc | Task brief: "same Getting Started doc if it covers the Pro" | [UM-V2]: "Product Included: Ikedo Mini Sumo Robot Starter Kit V2" | The doc does not cover the Pro; no Pro assembly document found |

## Needs verification
- Whether 350 g is with battery, shield, blade and copper base fitted.
- Dimensions/thickness of the stainless steel shield, razor blade and copper weight base.
- Which external start module the port is meant for (e.g. Cytron's IR sumo start module — `ir-sumo-start.md`) — not named on the page.
- Content of the Cytron Hackster "Ikedo Mini Sumo Robot Pro" guide (15 Jan 2020) beyond the IDE screenshot, and of the SumoRobot1KG tutorial beyond its motor table — not read.
- Pro page does not print the NovaMax name; the motor match rests on identical 800 rpm / 3.1 kg figures.
- Competition class (500 g) — stated for the controller, not on the kit page.
- Pre-loaded firmware.
- Arduino Uno selection on Arduino IDE 2.x — not yet bench-tested.
- [3P] RobotShop SKU RB-Cyt-276, USD 172.90 — cross-check only.

## Resolved verification items
- **Stall/rated current of the 800 RPM 6 V micro metal gearmotor** — resolved 27 Oct 2026: no-load 190 mA, operating 260 mA, stall 5.75 A at 6 V; rated load torque 3.1 kg/cm, stall torque 4.5 kg/cm [PP: tutorial SumoRobot1KG]. Was: "vs the controller's 3 A continuous limit — no source." Note for the controller: 5.75 A stall is close to its 6 A peak (< 5 s); higher on a full 2S pack.
- **Arduino board selection** — resolved 27 Oct 2026: Arduino Uno [PP: Hackster screenshot]. Pre-loaded firmware stays open.

## Sources
- [PP] Product page (read by coordinator 2026-10-19) — https://my.cytron.io/p-ikedo-mini-sumo-robot-pro-kit
- [PP] Tutorial linked from the page (not readable here on 19 Oct) — https://my.cytron.io/tutorial/SumoRobot1KG
- [PP: tutorial SumoRobot1KG] "Let's Upgrade your Mini Sumo to 1kg Sumo Robot" — motor table read 27 Oct 2026 — https://my.cytron.io/tutorial/SumoRobot1KG
- [PP: NovaMax page] 6V 800RPM Super Power DC Micro Metal Gearmotor (NovaMax) — read 27 Oct 2026 — https://my.cytron.io/p-6v-800rpm-super-power-dc-micro-metal-gearmotor-novamax
- [PP: Hackster screenshot] Arduino IDE 1.8.6 Tools menu in the Pro guide (Board "Arduino/Genuino Uno", Port "COM5") — read 27 Oct 2026
- [PP: Hackster Pro] Cytron Technologies, "Ikedo Mini Sumo Robot Pro", 15 Jan 2020 (not readable here; facts via `maker-mini-sumo.md`) — https://www.hackster.io/cytron-technologies/ikedo-mini-sumo-robot-pro-7da610
- [UM-V2] Ikedo Bot V2 Getting Started Instruction (Google Doc, modified 2026-01-20; covers the V2 Starter only) — https://docs.google.com/document/d/1K1BmYpMD1huE4dlEoHFVP3EIPX8xbpfYs_28KDh52f4/edit
- [GH] CytronMakerSumo library — https://github.com/CytronTechnologies/CytronMakerSumo
- [DS] Board datasheets linked from the page: Maker Mini Sumo (https://docs.google.com/document/d/1HrApn-5ldC58r9UOs4APiLVk_vUcJKDNX2-tJEHuHKk/edit), Maker Object and MAKER-REFLECT-S — see the board KB files; RobotShop mirror of the controller datasheet filed as "ikedo-mini-sumo-robot-pro-kit-datasheet.pdf" — https://cdn.robotshop.com/media/c/cyt/rb-cyt-276/pdf/ikedo-mini-sumo-robot-pro-kit-datasheet.pdf
- [3P] RobotShop listing (cross-check only) — https://www.robotshop.com/products/ikedo-mini-sumo-robot-pro-kit
- KB cross-references: /home/claude/kb/maker-mini-sumo.md · /home/claude/kb/maker-object.md · /home/claude/kb/maker-reflect-s.md · /home/claude/kb/ikedo-mini-sumo-v2.md · /home/claude/kb/pcb-sumo-plate.md
