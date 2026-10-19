# DIY RC Boat Using micro:bit — Verified Reference

| | |
|---|---|
| Product code | `PR-DIY-BOAT-MBIT` [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: read the product page's packing-list image (propellers, SG90, two 3 V motors, MOTION:BIT bundle with micro:bit Junior Kit + 18650, micro:bit V2 Go Bundle; no hull) and the connection image (motors on M1 and M2; servo on a right-side servo header). Project kit — MOTION:BIT follows its datasheet; kit parts follow the product page / tutorial (KB rule 7) |
| Primary source | No datasheet, booklet or user manual exists: this is a **project kit** whose product page is itself the build guide [PP]. Companion Cytron tutorial: **"Build an RC Boat Using micro:bit"** (my.cytron.io; author and date not in the text read) [PP: tutorial Build an RC Boat]. Also linked from the page: "Getting Started with MOTION:BIT & Projects Guide" (not readable here). Electrical limits of the controller board come from the MOTION:BIT datasheet — see `motion-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Notes on tags: [PP] = my.cytron.io product page (coordinator read, 2026-10-19); [PP: tutorial] = "Build an RC Boat Using micro:bit" at https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit, read through a summarising fetch — its "Hardware Components" product cards, code-block images, parts images and the STL/MakeCode link targets did **not** come through as text; [GH] = CytronTechnologies/pxt-motionbit README. KIT RULE: MOTION:BIT (`motion-bit.md`) is **not** re-documented here. Documented as a project kit: parts, ports, radio scheme, hull options and what is not included.

## What it is
- A DIY remote-controlled boat project for the BBC micro:bit: **two micro:bits**, one as the hand-held remote (micro:bit radio) and one on the boat plugged into a **MOTION:BIT**, which drives two DC motors with propellers and a 9 g servo that moves a rudder fin [PP], [PP: tutorial].
- The hull is **3D-printed from STL files that Cytron provides**, or made from foam/plastic; a waterproof enclosure is optional [PP]. Cytron printed its hull on an Artillery Hornet [PP: tutorial].
- Programmed in MakeCode blocks with the MOTIONBIT extension; the remote uses shake/gesture, buttons A/B and the touch logo [PP], [PP: tutorial].
- Sold as one package at RM297.55 [PP]. In the box (packing-list image) [PP: img]: 2 × 56 mm 4-blade propellers (blue); 1 × SG90 micro servo; 2 × 3 V miniature brushed DC motors with leads; 1 × MOTION:BIT bundle with micro:bit Junior Kit and an 18650 battery; 1 × micro:bit V2 Go Bundle (the remote). **No hull** — print it from Cytron's STL files or make it from foam/plastic.

## Specifications
No spec table exists. The product page's component list and build outline are reproduced; kit-level facts follow.

| Item | Value | Src |
|---|---|---|
| Controller on the boat | BBC micro:bit + MOTION:BIT (see `motion-bit.md`) | [PP] |
| Remote | second BBC micro:bit, micro:bit radio | [PP] |
| Components listed on the page | BBC micro:bit x2; MOTION:BIT; 2x DC motors with propellers; 9g servo (fin); 3.7V LiPo battery pack; boat hull 3D-printed (STL provided) or foam/plastic; waterproof enclosure optional | [PP] |
| Propulsion | 2x DC motors with propellers | [PP] |
| Steering | 9 g servo moving a fin (rudder); positions used: 130°, 50°, 90° (centre) | [PP], [PP: tutorial] |
| Power | 3.7 V cell — the packing list supplies an **18650** with the MOTION:BIT bundle (the page text says "3.7V LiPo battery pack") | [PP][PP: img] |
| Packing list | 2 × 56 mm 4-blade propellers (blue); 1 × SG90 micro servo; 2 × 3 V miniature brushed DC motors with leads; 1 × MOTION:BIT bundle with micro:bit Junior Kit and an 18650 battery; 1 × micro:bit V2 Go Bundle (the remote). **No hull** — print it from Cytron's STL files or make it from foam/plastic | [PP: img] |
| Motors | 2 × 3 V miniature brushed DC motors with leads; 56 mm 4-blade propellers | [PP: img] |
| Servo | SG90 (9 g) | [PP: img] |
| Software | MakeCode blocks, MOTIONBIT extension | [PP], [PP: tutorial] |
| Build outline | 6 build steps on the page (gather components, assemble hull, …); tutorial: Code #1 (boat), Code #2 (remote), STL files, video tutorial | [PP], [PP: tutorial] |
| Hull | 3D-printed (STL provided) or foam/plastic; Cytron's print: Artillery Hornet | [PP], [PP: tutorial] |
| Waterproofing | "waterproof enclosure optional" | [PP] |
| Price | RM297.55 (read 2026-10-19) | [PP] |
| Warranty | not stated on the page text read | — |

## Interfaces, terminals and pin mapping
| Function | MOTION:BIT port | Notes | Src |
|---|---|---|---|
| Propeller motors | **M1 and M2** on the MOTION:BIT (one motor each) | from the page's connection image; which side is left/right not stated | [PP: img] |
| Fin servo (SG90) | MOTION:BIT servo header on the right-hand side of the board — port number **not readable** in the image | S1–S8 exist [GH]; set with `set servo position` 0–180 | [PP: img], [GH] |
| Battery | 18650 in the MOTION:BIT holder (supplied in the MOTION:BIT bundle) | MOTION:BIT input and charging: see `motion-bit.md` | [PP: img] |
| Remote → boat | micro:bit radio | radio group not stated | [PP] |

Remote-control scheme (remote micro:bit) [PP: tutorial]:

| Remote input | Boat action |
|---|---|
| Shake | start the motors |
| Button A | move the fin to 130° |
| Button B | move the fin to 50° |
| Buttons A + B | return the fin to 90° |
| Touch the micro:bit logo | stop the motors |

## Rules and gotchas (for code, wiring and tutorials)
- **Two programs**: Code #1 goes on the boat micro:bit (MakeCode, add the "MOTIONBIT" extension, download); Code #2 goes on the remote micro:bit [PP: tutorial]. The block code is shown only as images on the page — do not quote block names beyond the MOTION:BIT extension's documented blocks (`run motor`, `brake motor`, `set servo position`, `disable servo`) [GH].
- **Touch logo** is used to stop the motors [PP: tutorial]; the logo touch sensor exists only on micro:bit V2 [VEN: micro:bit hardware], so the remote must be a V2. The page does not name the micro:bit version.
- **Fin angles**: 130° / 50° / 90° are the values Cytron's remote sends [PP: tutorial]; adjust to the physical fin travel of the printed hull.
- **Motors on water**: the DC motors spin propellers, so the MOTION:BIT 1 A continuous / 1.5 A peak per-channel limit applies (`motion-bit.md`); stall a propeller on weed and the board's limit is reached quickly. No current figure for the supplied motors is stated.
- **Waterproofing**: the enclosure is optional per the page [PP]; the micro:bit, MOTION:BIT and LiPo are not waterproof. Nothing in the sources read describes sealing the motor shafts.
- **Hull**: print from the provided STL files or build one from foam/plastic [PP]. Link target for the STL files is on the tutorial page (anchor "Here") — URL not captured here.
- **Radio**: if several boats run together, set a different radio group per remote/boat pair (micro:bit radio practice; the page does not state the group used).

## Power and electrical limits
- 3.7 V LiPo battery pack [PP]. MOTION:BIT input limits, charging (micro USB charges an 18650 in the holder) and 5 V / 3V3 output limits: see `motion-bit.md`.
- The supplied cell is an **18650** in the MOTION:BIT holder [PP: img]; the page text's "3.7V LiPo battery pack" refers to it.
- No run time or motor current is stated.

## Software support
- MakeCode blocks; "MOTIONBIT" extension (https://github.com/CytronTechnologies/pxt-motionbit) [PP], [PP: tutorial], [GH].
- Project resources linked from the page [PP]: Getting Started with MOTION:BIT & Projects Guide (https://my.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide); MOTION:BIT datasheet; pxt-motionbit; MOTION:BIT 3D CAD.
- Tutorial with video: https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit [PP: tutorial].

## Compatibility and accessories
- micro:bit (two: one in the micro:bit Junior Kit for the boat, one in the micro:bit V2 Go Bundle for the remote); MOTION:BIT; SG90 servo; 2 × 3 V miniature motors with 56 mm propellers; 18650 cell [PP: img].
- Hull options: 3D-printed from Cytron's STL (printed by Cytron on an Artillery Hornet) or foam/plastic [PP], [PP: tutorial].
- Optional: waterproof enclosure [PP].

## Common mistakes / troubleshooting
- **Boat does not respond:** both micro:bits must run their own program (Code #1 boat, Code #2 remote) and be on the same radio group [PP: tutorial].
- **Fin moves the wrong way:** swap the 130°/50° values or re-seat the servo horn at 90° (A+B) first [PP: tutorial].
- **Only one propeller turns:** motors go on **M1 and M2** [PP: img]; the MOTION:BIT motor test buttons run each channel at full speed without code (`motion-bit.md`).
- **No hull in the box:** print it from the STL files or build one from foam/plastic [PP][PP: img].
- **Motors stop on the water:** low LiPo voltage — MOTION:BIT's input range starts at 3.6 V (`motion-bit.md`).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Hull | [PP] "boat hull 3D-printed (STL provided) or foam/plastic" | [PP: tutorial] hull printed on an Artillery Hornet, STL files provided | No conflict: the STL hull is Cytron's reference build; foam/plastic is an alternative. The hull is **not** in the packing list [PP: img] |
| Battery wording | [PP] text: "3.7V LiPo battery pack" | [PP: img] packing list: 18650 with the MOTION:BIT bundle | Packing list wins: an 18650 Li-ion cell |
| Build steps | [PP] "6 build steps on the page" | [PP: tutorial] two code steps + hull + video (step list not in text) | Use the product page's 6-step outline; the tutorial adds the control table |

## Needs verification
- Servo port number (S1–S8) — only "right-side servo header" is readable in the connection image.
- Which of M1/M2 is the left propeller.
- **Radio group** and the message format (numbers/strings) sent by the remote.
- STL file link target, MakeCode share links for Code #1 and #2, video URL — anchors only ("click here", "Here") in the text read.
- micro:bit version in the micro:bit Junior Kit (the remote's Go Bundle is V2; touch logo needs V2).
- Motor current rating, warranty, author and publish date of the tutorial.
- The 6 build-step titles beyond "gather components" and "assemble hull".

## Sources
- [PP] Product page (read by the coordinator 2026-10-19): https://my.cytron.io/p-diy-boat-mbit
- [PP: tutorial Build an RC Boat] https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit (partial text; also at https://www.cytron.io/tutorial/build-an-rc-boat-using-micro-bit — fetch failed)
- [PP] Getting Started with MOTION:BIT & Projects Guide: https://my.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide (blocked here, not read)
- [GH] https://github.com/CytronTechnologies/pxt-motionbit — README.md via raw.githubusercontent.com
- [DS] MOTION:BIT datasheet (via `motion-bit.md`): https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit
- Related KB files: `motion-bit.md`
