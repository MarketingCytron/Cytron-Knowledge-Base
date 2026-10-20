# STRIKER:BIT Soccer Competition Kit — Verified Reference

| | |
|---|---|
| Product code | `V-STRIKERBIT` [PP]. The scoring sheet carries the internal game code "PM-GAME-STRIKER" [UM] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — STRIKER:BIT Booklet read in full (100 pages; it has a text layer, so "image-only" was wrong) plus the wiring, servo and code pages viewed as images. Wiring, port use, servo angles, radio scheme, chapter list and game rules are now Cytron-stated [UM]. Raised Medium-low → Medium: the standoff lengths in the assembly steps do not match the booklet's box list, and the product page's Complete Kit micro:bit count conflicts with the booklet (see *Conflicts*). Earlier: 2026-10-19 master-table review of the live product page |
| Primary source | No datasheet exists for the kit (KB rule 7: the guide book is the main source). Guide book: **"STRIKER:BIT — Build. Code. Move. SHOOT"** booklet, Cytron Education Team, June 2026, © Cytron Technologies, 100 pages, "Works with micro:bit V1 & V2" — file "20260606 STRIKERBIT Booklet (MAIN).pdf" (Canva export, created 9 Jun 2026), read in full 2026-10-20 [UM]. Also the **STRIKER:BIT Soccer Match Score Sheet** (11 Jun 2026) [UM] and the Cytron product page [PP]. Controller-board limits: see `motion-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Notes on tags: [UM] = the STRIKER:BIT Booklet (read in full 2026-10-20 from the copy in the team folder; text layer plus page images for wiring and code blocks; Cytron confirms it is the **only** guide) and the Scoring Sheet (read in full); [PP] = my.cytron.io product page (coordinator read, 2026-10-19). The "Chapter codes" Drive folder "STRIKERRBIT CODE (MAIN)" could not be opened; the booklet prints every code block, so the code facts below come from the booklet pages. KIT RULE: MOTION:BIT (`motion-bit.md`) is **not** re-documented here; only kit-level facts are stated. Joystick:bit V2 is a non-Cytron controller and has no KB file.

## What it is
- "STRIKER:BIT Soccer Competition Kit" — a classroom-scale robot-soccer competition kit: "4 Robots in One Package" with a 4-step workflow, a 7-chapter learning guidebook, a game field, barrier, goal posts, props and scoring sheets [PP].
- Each robot is a 2-wheel-drive micro:bit car on a Robobase Mini PCB chassis, driven by a MOTION:BIT, with a servo "shooter" mechanism (Robo Grip Mini PCB + 3D-printed part) that strikes a ping pong ball, and is remote-controlled with a micro:bit Joystick:bit [PP].
- Purchase options [PP]: **Complete Kit** (4 robots + field) or **Basic Kit** (1 robot set), each **with battery** or **without battery**. Price range RM370.00–RM1,675.65 across the options [PP].
- Controller board: MOTION:BIT — see `motion-bit.md`.

## Specifications
No kit datasheet or spec table exists. The product-page "Specifications" block is reproduced in full; kit-level facts follow.

| Item | Value | Src |
|---|---|---|
| Microcontroller | BBC micro:bit — booklet cover: "Works with micro:bit V1 & V2"; the kit ships micro:bit Junior Kit V2 [PP]; 2 micro:bits per robot set (robot + Joystick:bit) [UM] | [UM][PP] |
| Motors | 2x DC gear motors with wheels (per robot) | [PP] |
| Shooter mechanism | Non-copper PCB + 3D printed part with servo (Robo Grip Mini PCB; "8x 3D printed grippers" in the Complete Kit = 2 per robot) | [PP] |
| Power (robot) | 1x 3.7V 2200mAh 18650 Li-Ion with button top (per robot; fits the MOTION:BIT 18650 holder — see `motion-bit.md`) | [PP] |
| Control | micro:bit Joystick:bit (Joystick:bit V2 Kit in the packing list) | [PP] |
| Chassis | Non-copper PCB (Robobase Mini kit for 2WD Robot); no soldering | [PP] |
| Programming | MakeCode | [PP] |
| Learning guide | Booklet, 100 pages: Setup Guide (p.11), Ch1 micro:bit Basics (p.36), Ch2 Team Colour Selection – RGB LED (p.49), Ch3 Basic Movement – DC Motor (p.55), Ch4 Ball Shooter – Servo Motor (p.61), Ch5 Remote Control – Joystick:bit (p.67), Ch6 Combination of Servo, Motor & Joystick (p.77), Ch7 STRIKER:BIT Game Play Guide (p.89); one booklet per robot set | [UM] |
| Workflow | "4-step workflow" (steps not named in the page text) | [PP] |
| Field | gamefield map, barrier (12x 3/4" PVC conduit pipe 34 cm, 4x elbow joints, 8x sockets), 2 goal posts (2x pizza box packing 315x220x70mm + 2x goal post stickers), whistle, yellow card, red card, gameplay instruction & scoring sheet | [PP] |
| Warranty | 12 months | [PP] |
| Packing list — Complete Kit, with batteries | 4x Robo Grip Mini Basic Bundle, 4x Robobase Mini kit for 2WD Robot, 4x micro:bit Junior Kit (V2), 4x micro servos, 4x motion:bit, 4x USB Micro B cables, 8x 3D printed grippers, 4x ping pong balls, 4x STRIKER:BIT booklet, 4x Joystick:bit V2 Kit, Velcro sets, whistle, 12x 3/4" PVC conduit pipe (34 cm), 4x elbow joints, 8x sockets, 2x goal post stickers, yellow card, red card, gameplay instruction & scoring sheet, 2x pizza box packing 315x220x70mm (goal post), gamefield map, 4x AAA battery sets, 4x 18650 battery | [PP] |
| Packing list — Basic Kit | 1 robot set: 1x Robo Grip Mini Basic Bundle, 1x Robobase Mini 2WD, 2x micro:bit Junior Kit V2, 1x micro servo, … (page text truncated after this) | [PP] |
| Box contents — one robot set (booklet "What's in the STRIKER:BIT box?") | Robo Base Mini x1, Joystick:bit V2 Kit for micro:bit x1, micro:bit x2, LiPo battery x1, Robo Grip Mini x1, 4xAAA battery x1, servo motor x1, USB Micro B cable x1, 3D printed shooter x1, MOTION:BIT x1, TT DC gear motor bracket x2, M3x6mm screw x16 + M3 nut x16, TT motor with 15 cm wires and wheel kit x2, W420 steel ball universal wheel (castor) x1, M3 PCB stand (screw & nut) 10 mm x4, PCB stand (screw & nut) 25 mm x4, ping pong ball x1, printed booklet x1 | [UM] |
| Complete Kit field accessories (booklet) | Velcro (hooks & loops), red card x1, yellow card x1, whistle x1, goal post box x2, PVC elbow x4, PVC socket x8, PVC pipe 22 mm (34 cm) x12, STRIKER:BIT game field map x1, net sticker x2 | [UM] |
| Booklet PDF | "20260606 STRIKERBIT Booklet (MAIN).pdf", 236,933,916 bytes, 100 pages, 473.5 × 363.3 pt pages, Canva export 9 Jun 2026 | [UM] |
| Scoring sheet PDF | "20260611 STRIKERBIT Scoring Sheet.pdf" — two "STRIKER:BIT SOCCER MATCH SCORE SHEET" forms per page | [UM] |

## Interfaces, terminals and pin mapping
Wiring is stated in the booklet Setup Guide (pp.22–24) and repeated in Chapters 3–4 [UM].

| Function | Connection | Notes | Src |
|---|---|---|---|
| Right drive motor | MOTION:BIT **M1**: red (+) → **M1A**, black (−) → **M1B** | test with the M1A / M1B buttons | [UM] |
| Left drive motor | MOTION:BIT **M3**: black (−) → **M3A**, red (+) → **M3B** | test with the M3A / M3B buttons; the left motor is wired the opposite way round to the right | [UM] |
| Shooter servo | MOTION:BIT servo port **S1**: orange = S (signal), red = + (power), brown = − (ground) | 180° servo | [UM] |
| Team-colour LEDs | MOTION:BIT's two rear RGB LEDs (LED 0, LED 1) | set in the on start block: red team / green team (Ch2) | [UM] |
| Robot battery | one cell in the MOTION:BIT battery holder (booklet box list: "LiPo Battery x1"; product page: 3.7 V 2200 mAh 18650 button top) | see *Conflicts* for the naming | [UM][PP] |
| Joystick:bit V2 — stick | X → micro:bit **P1**, Y → **P2**; each axis reads 0–1023 | third-party controller; booklet description only | [UM] |
| Joystick:bit V2 — buttons | C → **P12**, D → **P13**, E → **P14**, F → **P15**; on-board buzzer and vibration motor | | [UM] |
| Joystick:bit power | 2 × AAA cells at the back; slide switch at top right, slide **left** for ON; insert the micro:bit (booklet says "micro:bit V2") at the front | | [UM] |
| Radio | Ch5 demo: radio group **1** on both micro:bits. Ch6 match code: robot fixed at group **0**; the Joystick:bit stores its channel ("id2") in flash — A = −1 (wraps to 255), B = +1, A+B = save | | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **Two micro:bits per robot set:** one on the MOTION:BIT (robot), one in the Joystick:bit (remote) [UM].
- **Motor channels are M1 (right) and M3 (left)** — not M1/M2 [UM]. In Ch6 code the left-wheel speed drives M3 and the right-wheel speed drives M1.
- **Servo on S1.** Ch4 test angles: button A → **60°** (close), button B → **150°** (open), each followed by pause 100 ms and "disable servo S1"; the booklet says to experiment with angles for the best shot [UM].
- **Servo calibration (Ch4):** remove the Robo Grip Mini, unscrew the horn, press A to drive the servo to 0°, refit the horn and gripper arm in the shown position. Do not turn the servo gears by hand [UM].
- **Match code (Ch6, robot):** start position 100°; Joystick C (b = 1) snaps the shooter open to **160°**; D (b = 2) closes it gradually to 0°; E (b = 4) opens it gradually to 160°; F (b = 8) snaps it to **0°** (shoot). Gradual moves step 2° every 20 ms in the forever loop [UM].
- **Drive mixing (Ch6):** left speed = y + x, right speed = y − x, each constrained to −255…255; negative values run the motor backward at the absolute speed [UM].
- **Joystick side (Ch6):** X mapped from 1023…0 and Y from 0…1023 to −255…255, dead band ±15 → 0; sends "x", "y" and "b" (buttons 0/1/2/4/8) by radio every 20 ms [UM].
- **Ch3 movement test:** button A runs M1 and M3 forward at speed **128 (50 %)**; turns use a pause before braking — tune the pause for a 90° turn. Motors that look identical can run at different speeds, low battery slows the robot, and carpet is slower and less accurate than a hard smooth floor [UM].
- **Wheels spin the wrong way?** Swap the red and black wires in that motor terminal (Ch3) [UM].
- **Several robots on one field:** give each robot its own radio group and set its Joystick:bit to the same group (A/B to change, A+B to save) — the booklet says each pair needs a unique group number [UM].
- **Shooter build:** uses Robo Grip Mini Parts 1, 3, 4 and 5 only; servo on Part 1 with M2 bolts and nuts; Part 5 pivots on M3 bolts with thick spacers and **M3 lock nuts — do not replace them with plain nuts** and do not over-tighten (the arm must swing freely); Part 3 to the second hole from the end of the servo horn; 3D-printed shooter under Part 5 with four spacers [UM].
- **Scoring rules printed on the official score sheet** [UM]: goals ticked one per goal; **yellow cards: max 2 per robot**; **red cards: max 2 per team**; **final score = total number of goals**; signed by both captains and the Head of Referee.
- **Shooter, not gripper:** it pinches and shoots a ping pong ball; call it "the servo shooter built on the Robo Grip Mini PCB" [UM][PP].

## Power and electrical limits
- Robot: one cell in the MOTION:BIT holder — product page: 1x 3.7 V 2200 mAh 18650 Li-Ion with button top [PP]; booklet box list calls it "LiPo Battery x1" and the wiring diagram labels it "LIPO-Battery" [UM]. Limits of the board: `motion-bit.md` (3.6–6 V input, 1 A / 1.5 A motor, 5 V 300 mA, 3V3 200 mA).
- Power switch on the MOTION:BIT: slide to ON to run (Ch1, Ch3) [UM].
- Joystick:bit: 2 × AAA cells; the box list has one 4 × AAA pack [UM]. "Without battery" kit options ship without the cells [PP].
- Battery level matters: a low battery makes the robot move more slowly (Ch3) [UM].
- No run time, current draw or charging instruction is stated in the booklet.

## Software support
- MakeCode (makecode.microbit.org) [UM].
- Robot extension: **motionbit** (search "MOTIONBIT" in Extensions) [UM]; GitHub pxt-motionbit (see `motion-bit.md`).
- Joystick extension: **joystickbit** (search "JOYSTICK:BIT" in Extensions) [UM].
- Chapter code is printed as MakeCode blocks in the booklet (Ch1–Ch6); the separate Drive code folder could not be opened.
- Download: pair over WebUSB from the Download button, or drag the .hex file into the MICROBIT drive (Ch1) [UM].

## Compatibility and accessories
- micro:bit V1 & V2 (booklet cover) [UM]; the kit ships micro:bit Junior Kit V2 [PP]; the Joystick:bit step says to insert a "micro:bit V2" [UM].
- Mechanical (per robot set): Robo Base Mini ×2 plates (wheel base + MOTION:BIT deck), TT motors with brackets and wheels, W420 steel-ball castor, Robo Grip Mini, 3D-printed shooter, M3 stands and screws [UM].
- Field (Complete Kit): game field map, 12 × 22 mm PVC pipes (34 cm) with 8 sockets and 4 elbows as the barrier (each long side 4 pipes + 3 sockets; each short side 2 pipes + 1 socket with elbows at the ends), Velcro to hold the barrier and goal posts, two goal posts cut from Cytron blue cardboard boxes (Part A stand + Part B net with net sticker), whistle, yellow and red cards [UM].
- Related Cytron kits: SOCCER:BIT (4-wheel SUMO:BIT soccer bundle) is a different product and must not be confused with STRIKER:BIT.

## Common mistakes / troubleshooting
- **Robot drives in circles or backward:** check M1 = right, M3 = left and the wire colours per terminal; swap red/black on the wrong-way motor [UM].
- **Robot drifts when going straight:** normal — motor tolerance, battery level and floor surface all affect it (Ch3) [UM].
- **Shooter jams or misses:** recalibrate the servo horn at 0° and re-tune the open/close angles (Ch4); check the M3 lock nuts are not over-tightened [UM].
- **Robot ignores its remote:** the robot and its Joystick:bit must be on the same radio group (Ch6 robot code is fixed at group 0; Joystick channel set with A/B and saved with A+B) [UM].
- **Robots react to the wrong remote:** two pairs share a group — give each pair a unique group [UM].
- **Score disputes:** use the official sheet — both captains and the head referee sign; card limits are 2 yellow per robot, 2 red per team [UM].

## Game rules (booklet Chapter 7)
- Designed for four (4) players [UM].
- **Match:** two halves of **2 minutes**, **1-minute** halftime; teams switch sides at halftime. Time pauses for ball out of bounds, goals, match reset, timeout and halftime; the referee restarts play [UM].
- **Kickoff:** coin toss — the winner kicks off. Ball on the centre point; only one robot of the kicking team near the ball; all other robots wait in front of their own penalty box until the kick. Play the ball immediately on the whistle. A match starts on time even if a team is missing robots [UM].
- **Goals:** the whole ball must cross the goal line between the posts; the referee whistles and play stops; the team that conceded kicks off from the centre. **A goal straight from a kickoff does not count** — another robot must touch the ball first; otherwise the opponents get the ball at the centre [UM].
- **Out of play:** an official puts the ball back near where it left; restart on the whistle. Ball over the outer goal line last touched by an opponent → kick-in from the edge of the goal area [UM].
- **Fouls:** contact inside the ball-contention area is normal play, as are minor collisions outside it. **Yellow card:** intentional, unsporting collision outside the ball-contention area without serious damage. **Red card (robot removed):** intentional collision that seriously damages an opponent's robot, intentional field damage, or a second yellow card [UM].
- **Timeout:** one per team per match, max 1 minute, requested only by players in the Team Zone and granted at the referee's discretion; used to change operators and/or repair robots. All repairs happen outside the court. The other team may also repair; the team that did **not** call the timeout kicks off afterwards [UM].
- **Referee whistle** signals match start, second half, kickoff, goal, ball out of play, timeout end, restart and match end [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| micro:bit count | [UM] booklet box list: **micro:bit x2** per robot set (robot + Joystick:bit) | [PP] Complete Kit (4 robots): "4x micro:bit Junior Kit (V2)"; Basic Kit: "2x micro:bit Junior Kit V2" | [UM] outranks [PP]: 2 per robot set, so a 4-robot class needs 8 micro:bits. The Complete Kit packing list on the product page looks wrong — ask the EDU team to correct the page |
| Robot battery name | [UM] "LiPo Battery x1" / "LIPO-Battery" | [PP] "3.7V 2200mAh 18650 Li-Ion with button top" | Same cell; name it as the product page does (18650 Li-ion, button top). The booklet's "LiPo" is a loose label |
| Standoff lengths | [UM] box list: M3 PCB stand 10 mm x4 and 25 mm x4 | [UM] assembly steps: 2 × 40 mm at the front, 2 × 20 mm under the shooter, 4 × 10 mm under the MOTION:BIT, 4 × 40 mm at the rear | Unresolved — the 40 mm and 20 mm stands are not in the box list (the Robo Grip Mini bundle has one 40 mm and four 20 mm). Ask the EDU team which stands ship and which lengths to use |
| Radio group | [UM] Ch5: group 1 on both micro:bits | [UM] Ch6: robot fixed at group 0; Joystick channel stored in flash | Both are correct for their chapter (Ch5 is a demo, Ch6 is match code). For matches, follow Ch6 and give each pair its own group |
| Shooter part naming | [PP] "Shooter mechanism: non-copper PCB + 3D printed part with servo" | [PP] "Robo Grip Mini Basic Bundle" + "8x 3D printed grippers"; [UM] "3D Printed Shooter x1" per set | Same part; call it "the servo shooter built on the Robo Grip Mini PCB" |

## Needs verification
- **Standoffs:** which stand lengths ship in each robot set and which the build needs (see *Conflicts*).
- **Product page Complete Kit micro:bit count** ("4x") — confirm 8 with the EDU team and correct the page.
- **"4-step workflow"** named on the product page — the booklet does not label four steps.
- Joystick:bit V2 Kit maker and extension details — third-party controller; only the booklet description is used.
- Dimensions/weight of a robot, field size in cm, age range, assembly time — not stated in the booklet or page.
- Game: "designed for four (4) players" [UM] — the booklet does not say how many robots per team; confirm "2 vs 2" before stating it.
- Availability on 2026-10-19 was 15 units [PP]; options may sell out separately.

## Sources
- [PP] Product page (read by the coordinator 2026-10-19): https://my.cytron.io/p-strikerbit-soccer-competition-kit
- [UM] STRIKER:BIT Booklet — "20260606 STRIKERBIT Booklet (MAIN).pdf" (Cytron Education Team, June 2026, 100 pages), read in full 2026-10-20 from the team folder copy (reference/); Drive: https://drive.google.com/file/d/12FMdIQBJSj9FZLkH8i9N7iAjfZcL4TMG/view
- [UM] STRIKER:BIT Scoring Sheet PDF — "20260611 STRIKERBIT Scoring Sheet.pdf" (read in full): https://drive.google.com/file/d/107pdA24KHg3J_EgFw6I5Heqa9F0xisST/view
- [UM] Chapter codes folder "STRIKERRBIT CODE (MAIN)" (not listable): https://drive.google.com/drive/folders/1MLOCy1TIm4yeIoTY4XvfEIb9uPKeGwJ4
- [GH] https://github.com/CytronTechnologies/pxt-motionbit — README.md (MOTION:BIT MakeCode extension)
- Related KB files: `motion-bit.md`
