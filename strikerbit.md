# STRIKER:BIT Soccer Competition Kit — Verified Reference

| | |
|---|---|
| Product code | `V-STRIKERBIT` [PP]. The scoring sheet carries the internal game code "PM-GAME-STRIKER" [UM] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: live product page re-read — Complete-with-batteries list confirmed (4 × PKCELL AAA sets for the Joystick:bits, 4 × 18650 2200 mAh, 5 Velcro sets); "without batteries" omits both the AAA sets and the 18650 cells; Basic photo = one robot set + one game handle. The STRIKER:BIT booklet (guide book, main source under KB rule 7) is still unread — 237 MB image-only PDF; confidence stays Medium-low until it is read |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Notes on tags: [UM] = STRIKER:BIT Scoring Sheet (read in full) and the Booklet (metadata only — Cytron confirms the booklet is the **only** guide, 19 Oct 2026; Google Drive says it is too large to preview); [PP] = my.cytron.io product page (coordinator read, 2026-10-19). The "Chapter codes" Drive folder is titled "STRIKERRBIT CODE (MAIN)" (created 2026-06-09) but its files could not be listed or read. KIT RULE: MOTION:BIT (`motion-bit.md`) is **not** re-documented here; only kit-level facts are stated. Joystick:bit V2 is a non-Cytron controller and has no KB file.

## What it is
- "STRIKER:BIT Soccer Competition Kit" — a classroom-scale robot-soccer competition kit: "4 Robots in One Package" with a 4-step workflow, a 7-chapter learning guidebook, a game field, barrier, goal posts, props and scoring sheets [PP].
- Each robot is a 2-wheel-drive micro:bit car on a Robobase Mini PCB chassis, driven by a MOTION:BIT, with a servo "shooter" mechanism (Robo Grip Mini PCB + 3D-printed part) that strikes a ping pong ball, and is remote-controlled with a micro:bit Joystick:bit [PP].
- Purchase options [PP]: **Complete Kit** (4 robots + field) or **Basic Kit** (1 robot set), each **with battery** or **without battery**. Price range RM370.00–RM1,675.65 across the options [PP].
- Controller board: MOTION:BIT — see `motion-bit.md`.

## Specifications
No kit datasheet or spec table exists. The product-page "Specifications" block is reproduced in full; kit-level facts follow.

| Item | Value | Src |
|---|---|---|
| Microcontroller | BBC micro:bit (micro:bit Junior Kit V2 in the packing list) | [PP] |
| Motors | 2x DC gear motors with wheels (per robot) | [PP] |
| Shooter mechanism | Non-copper PCB + 3D printed part with servo (Robo Grip Mini PCB; "8x 3D printed grippers" in the Complete Kit = 2 per robot) | [PP] |
| Power (robot) | 1x 3.7V 2200mAh 18650 Li-Ion with button top (per robot; fits the MOTION:BIT 18650 holder — see `motion-bit.md`) | [PP] |
| Control | micro:bit Joystick:bit (Joystick:bit V2 Kit in the packing list) | [PP] |
| Chassis | Non-copper PCB (Robobase Mini kit for 2WD Robot); no soldering | [PP] |
| Programming | MakeCode | [PP] |
| Learning guide | 7-chapter learning guidebook ("STRIKER:BIT booklet", one per robot) | [PP] |
| Workflow | "4-step workflow" (steps not named in the page text) | [PP] |
| Field | gamefield map, barrier (12x 3/4" PVC conduit pipe 34 cm, 4x elbow joints, 8x sockets), 2 goal posts (2x pizza box packing 315x220x70mm + 2x goal post stickers), whistle, yellow card, red card, gameplay instruction & scoring sheet | [PP] |
| Warranty | 12 months | [PP] |
| Packing list — Complete Kit, with batteries | 4x Robo Grip Mini Basic Bundle, 4x Robobase Mini kit for 2WD Robot, 4x micro:bit Junior Kit (V2), 4x micro servos, 4x motion:bit, 4x USB Micro B cables, 8x 3D printed grippers, 4x ping pong balls, 4x STRIKER:BIT booklet, 4x Joystick:bit V2 Kit, Velcro sets, whistle, 12x 3/4" PVC conduit pipe (34 cm), 4x elbow joints, 8x sockets, 2x goal post stickers, yellow card, red card, gameplay instruction & scoring sheet, 2x pizza box packing 315x220x70mm (goal post), gamefield map, 4x AAA battery sets, 4x 18650 battery | [PP] |
| Packing list — Basic Kit | 1 robot set: 1x Robo Grip Mini Basic Bundle, 1x Robobase Mini 2WD, 2x micro:bit Junior Kit V2, 1x micro servo, … (page text truncated after this) | [PP] |
| Booklet PDF | "20260606 STRIKERBIT Booklet (MAIN).pdf", 236,933,916 bytes, PDF, uploaded 2026-06-09 | [UM] metadata |
| Scoring sheet PDF | "20260611 STRIKERBIT Scoring Sheet.pdf" — two "STRIKER:BIT SOCCER MATCH SCORE SHEET" forms per page | [UM] |

## Interfaces, terminals and pin mapping
The booklet's wiring pages could not be read, and the chapter code folder could not be opened, so **no MOTION:BIT port assignment (M1–M4, S1–S8) or radio scheme is confirmed** for this kit — see *Needs verification*. What the sources do establish:

| Function | Part | Notes | Src |
|---|---|---|---|
| Drive | 2x DC gear motors with wheels on MOTION:BIT motor terminals | channel numbers not stated | [PP] |
| Shooter | 1x micro servo on a MOTION:BIT servo port | port number not stated | [PP] |
| Robot power | 1x 18650 3.7 V 2200 mAh button-top Li-Ion in the MOTION:BIT holder | MOTION:BIT input range and charging: see `motion-bit.md` | [PP] |
| Remote control | Joystick:bit V2 Kit with its own micro:bit, over micro:bit radio | the Basic Kit lists 2x micro:bit Junior Kit V2 per robot set (one for the robot, one for the joystick) | [PP] |
| Joystick power | 4 × PKCELL AAA battery sets in the Complete Kit with batteries — one set per Joystick:bit V2 | the 18650 powers the robot, so the AAA sets are for the joysticks | [PP] |

## Rules and gotchas (for code, wiring and tutorials)
- **Two micro:bits per robot:** the robot (on MOTION:BIT) and the Joystick:bit remote each need a micro:bit [PP]. See *Conflicts* for the micro:bit count in the Complete Kit.
- **Scoring rules printed on the official score sheet** [UM]: goals are ticked one per goal; **yellow cards: max 2 per robot**; **red cards: max 2 per team**; **final score = total number of goals**; the sheet is signed by the Team A captain and Team B captain ("Verify scores are accurate") and by the Head of Referee ("Final official match validation"). It has fields for Competition / Event / Round, Date and both team names.
- **Shooter, not gripper:** the kit reuses the Robo Grip Mini PCB with a 3D-printed striker part driven by a servo; the product page calls it a "shooter mechanism" [PP]. Don't describe it as a ball-carrying gripper.
- **Battery option:** "without battery" kits ship without **both** the 18650 cells and the AAA sets [PP]; the robot needs a 3.7 V button-top 18650 and each Joystick:bit needs AAA cells. The 18650 KB note applies: unprotected cells need a proper Li-ion charger (see the 18650 battery entry when added).
- **Programming is MakeCode** with the MOTION:BIT extension (pxt-motionbit) for the robot [PP]; the extension and radio-group handling for the Joystick:bit side are not stated by any Cytron source read — do not invent block names.
- **Field build:** barrier from 12 pieces of 34 cm 3/4" PVC conduit with 4 elbows and 8 sockets; goals are the two 315 x 220 x 70 mm pizza boxes with goal-post stickers; a printed gamefield map is included [PP]. Field dimensions are not stated.

## Power and electrical limits
- Robot: 1x 3.7 V 2200 mAh 18650 Li-Ion with button top per robot [PP]; charged/used through MOTION:BIT (limits in `motion-bit.md`: 3.6–6 V input, 1 A / 1.5 A motor, 5 V 300 mA, 3V3 200 mA).
- Controllers: 4 × PKCELL AAA battery sets in the Complete Kit with batteries, for the four Joystick:bit V2 [PP]; cells per set not stated.
- No run time, current draw or charging instruction is stated by any source read.

## Software support
- MakeCode [PP]. The robot's MOTION:BIT uses the pxt-motionbit extension (see `motion-bit.md`).
- Chapter example code: Drive folder "STRIKERRBIT CODE (MAIN)" https://drive.google.com/drive/folders/1MLOCy1TIm4yeIoTY4XvfEIb9uPKeGwJ4 — **contents could not be listed here** [UM].
- Booklet: 7 chapters [PP]; chapter titles not readable.

## Compatibility and accessories
- micro:bit V2 (micro:bit Junior Kit V2) [PP].
- Mechanical: Robobase Mini kit for 2WD Robot (PCB chassis), Robo Grip Mini Basic Bundle, 3D printed grippers (2 per robot), Velcro sets, USB Micro B cables [PP].
- Game props: ping pong balls (1 per robot), whistle, yellow/red cards, gamefield map, goal posts, PVC barrier, scoring sheets [PP].
- Related Cytron kits: SOCCER:BIT (4-wheel SUMO:BIT soccer bundle) is a different, larger product and must not be confused with STRIKER:BIT.

## Common mistakes / troubleshooting
- **Counting micro:bits:** a 4-robot class needs 8 micro:bits (4 robots + 4 joysticks); check the option's packing list before quoting [PP] — see *Conflicts*.
- **Wrong battery:** the robot takes a **button-top** 18650 (flat-top cells may not make contact in a holder) [PP].
- **Score disputes:** use the official sheet — both captains and the head referee sign; card limits are 2 yellow per robot, 2 red per team [UM].
- **Radio cross-talk** between four robots and four joysticks on one field: assign a different radio group per pair (general micro:bit practice; the booklet's scheme not read).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| micro:bit count | [PP] Complete Kit: "4x micro:bit Junior Kit (V2)" for 4 robots + 4 Joystick:bit V2 Kits | [PP] Basic Kit (1 robot): "2x micro:bit Junior Kit V2" | Internally inconsistent on the page: 4 robots with joysticks need 8 micro:bits. Unresolved — ask the EDU team; do not state a total micro:bit count in content |
| Shooter part naming | [PP] "Shooter mechanism: non-copper PCB + 3D printed part with servo" | [PP] packing list "Robo Grip Mini Basic Bundle" + "8x 3D printed grippers" | Same part; call it "the servo shooter built on the Robo Grip Mini PCB" |
| Document date | [UM] booklet file "20260606" (6 Jun 2026) | [UM] scoring sheet file "20260611" (11 Jun 2026) | Scoring sheet is the newer document; both post-date the booklet's main text. No conflict in content read |

## Needs verification
- **Booklet contents**: chapter titles, the 4-step workflow, assembly steps, which MOTION:BIT motor channels and servo port the drive motors and shooter use, the Joystick:bit radio scheme and extension, servo angles — the 237 MB image-only PDF could not be downloaded or OCR'd.
- **Chapter codes**: the Drive folder exists but its files were not visible to this account.
- **Game rules** beyond the score sheet (match length, field size, fouls that earn cards, what a red card does): "gameplay instruction" is a separate printed sheet not read.
- Exact Basic Kit packing list (page text truncated after "1x micro servo, ..."; the Basic photo shows one robot set and one game handle).
- Joystick:bit V2 Kit details (maker, power, extension) — no Cytron source read states them; treat as a third-party controller.
- Dimensions/weight of a robot, field size, age range, assembly time — not stated anywhere read.
- Availability on 2026-10-19 was 15 units [PP]; options may sell out separately.

## Sources
- [PP] Product page (read by the coordinator 2026-10-19): https://my.cytron.io/p-strikerbit-soccer-competition-kit
- [UM] STRIKER:BIT Book PDF — "20260606 STRIKERBIT Booklet (MAIN).pdf", Drive, uploaded 2026-06-09, **not readable as text**: https://drive.google.com/file/d/12FMdIQBJSj9FZLkH8i9N7iAjfZcL4TMG/view
- [UM] STRIKER:BIT Scoring Sheet PDF — "20260611 STRIKERBIT Scoring Sheet.pdf" (read in full): https://drive.google.com/file/d/107pdA24KHg3J_EgFw6I5Heqa9F0xisST/view
- [UM] Chapter codes folder "STRIKERRBIT CODE (MAIN)" (not listable): https://drive.google.com/drive/folders/1MLOCy1TIm4yeIoTY4XvfEIb9uPKeGwJ4
- [GH] https://github.com/CytronTechnologies/pxt-motionbit — README.md (MOTION:BIT MakeCode extension)
- Related KB files: `motion-bit.md`
