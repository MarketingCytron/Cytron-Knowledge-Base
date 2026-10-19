# DIY RC Boat Using micro:bit — Verified Reference

| | |
|---|---|
| Product code | `PR-DIY-BOAT-MBIT` [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | No datasheet, booklet or user manual exists: this is a **project kit** whose product page is itself the build guide [PP]. Companion Cytron tutorial: **"Build an RC Boat Using micro:bit"** (my.cytron.io; author and date not in the text read) [PP: tutorial Build an RC Boat]. Also linked from the page: "Getting Started with MOTION:BIT & Projects Guide" (not readable here). Electrical limits of the controller board come from the MOTION:BIT datasheet — see `motion-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Notes on tags: [PP] = my.cytron.io product page (coordinator read, 2026-10-19); [PP: tutorial] = "Build an RC Boat Using micro:bit" at https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit, read through a summarising fetch — its "Hardware Components" product cards, code-block images, parts images and the STL/MakeCode link targets did **not** come through as text; [GH] = CytronTechnologies/pxt-motionbit README. KIT RULE: MOTION:BIT (`motion-bit.md`) is **not** re-documented here. Documented as a project kit: parts, ports, radio scheme, hull options and what is not included.

## What it is
- A DIY remote-controlled boat project for the BBC micro:bit: **two micro:bits**, one as the hand-held remote (micro:bit radio) and one on the boat plugged into a **MOTION:BIT**, which drives two DC motors with propellers and a 9 g servo that moves a rudder fin [PP], [PP: tutorial].
- The hull is **3D-printed from STL files that Cytron provides**, or made from foam/plastic; a waterproof enclosure is optional [PP]. Cytron printed its hull on an Artillery Hornet [PP: tutorial].
- Programmed in MakeCode blocks with the MOTIONBIT extension; the remote uses shake/gesture, buttons A/B and the touch logo [PP], [PP: tutorial].
- Sold as one package at RM297.55 [PP]. Which of the listed components are physically in the package is **not stated in the text read** — see *Needs verification*.

## Specifications
No spec table exists. The product page's component list and build outline are reproduced; kit-level facts follow.

| Item | Value | Src |
|---|---|---|
| Controller on the boat | BBC micro:bit + MOTION:BIT (see `motion-bit.md`) | [PP] |
| Remote | second BBC micro:bit, micro:bit radio | [PP] |
| Components listed on the page | BBC micro:bit x2; MOTION:BIT; 2x DC motors with propellers; 9g servo (fin); 3.7V LiPo battery pack; boat hull 3D-printed (STL provided) or foam/plastic; waterproof enclosure optional | [PP] |
| Propulsion | 2x DC motors with propellers | [PP] |
| Steering | 9 g servo moving a fin (rudder); positions used: 130°, 50°, 90° (centre) | [PP], [PP: tutorial] |
| Power | 3.7 V LiPo battery pack | [PP] |
| Software | MakeCode blocks, MOTIONBIT extension | [PP], [PP: tutorial] |
| Build outline | 6 build steps on the page (gather components, assemble hull, …); tutorial: Code #1 (boat), Code #2 (remote), STL files, video tutorial | [PP], [PP: tutorial] |
| Hull | 3D-printed (STL provided) or foam/plastic; Cytron's print: Artillery Hornet | [PP], [PP: tutorial] |
| Waterproofing | "waterproof enclosure optional" | [PP] |
| Price | RM297.55 (read 2026-10-19) | [PP] |
| Warranty | not stated on the page text read | — |

## Interfaces, terminals and pin mapping
| Function | MOTION:BIT port | Notes | Src |
|---|---|---|---|
| Propeller motor (left) | MOTION:BIT motor terminal — channel **not stated** | M1–M4 exist on MOTION:BIT [GH]; the page/tutorial text does not name the channel | [PP] |
| Propeller motor (right) | MOTION:BIT motor terminal — channel **not stated** | | [PP] |
| Fin servo (9 g) | MOTION:BIT servo port — number **not stated** | S1–S8 exist [GH]; set with `set servo position` 0–180 | [PP], [GH] |
| Battery | 3.7 V LiPo battery pack | MOTION:BIT accepts an 18650 in its holder or an external 3.6–6 V input (see `motion-bit.md`); which input the LiPo pack uses is not stated | [PP] |
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
- Whether the "3.7V LiPo battery pack" is a pouch LiPo on the external input terminal or an 18650 cell in the holder is **not stated**.
- No run time or motor current is stated.

## Software support
- MakeCode blocks; "MOTIONBIT" extension (https://github.com/CytronTechnologies/pxt-motionbit) [PP], [PP: tutorial], [GH].
- Project resources linked from the page [PP]: Getting Started with MOTION:BIT & Projects Guide (https://my.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide); MOTION:BIT datasheet; pxt-motionbit; MOTION:BIT 3D CAD.
- Tutorial with video: https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit [PP: tutorial].

## Compatibility and accessories
- micro:bit (two); MOTION:BIT; 9 g servo (SG90-class, "9g servo (fin)"); 2x DC motors with propellers; 3.7 V LiPo pack [PP].
- Hull options: 3D-printed from Cytron's STL (printed by Cytron on an Artillery Hornet) or foam/plastic [PP], [PP: tutorial].
- Optional: waterproof enclosure [PP].

## Common mistakes / troubleshooting
- **Boat does not respond:** both micro:bits must run their own program (Code #1 boat, Code #2 remote) and be on the same radio group [PP: tutorial].
- **Fin moves the wrong way:** swap the 130°/50° values or re-seat the servo horn at 90° (A+B) first [PP: tutorial].
- **Only one propeller turns:** check the motor is on the channel the boat code drives; the MOTION:BIT motor test buttons run each channel at full speed without code (`motion-bit.md`).
- **Motors stop on the water:** low LiPo voltage — MOTION:BIT's input range starts at 3.6 V (`motion-bit.md`).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Hull | [PP] "boat hull 3D-printed (STL provided) or foam/plastic" | [PP: tutorial] hull printed on an Artillery Hornet, STL files provided | No conflict: the STL hull is Cytron's reference build; foam/plastic is an alternative. State both |
| Build steps | [PP] "6 build steps on the page" | [PP: tutorial] two code steps + hull + video (step list not in text) | Use the product page's 6-step outline; the tutorial adds the control table |

## Needs verification
- **What is in the box** for RM297.55: the page lists components, but no "packing list" was captured. In particular confirm whether the **hull (printed or not)**, the **3.7 V LiPo pack**, the **two micro:bits** and the propellers are included. The tutorial text does not say; the "STL provided" wording suggests the hull is printed by the user. Reported as unconfirmed, not as "not included".
- MOTION:BIT **motor channels** (M1–M4) and **servo port** (S1–S8) used by Code #1 — shown only in the code-block images.
- **Radio group** and the message format (numbers/strings) sent by the remote.
- STL file link target, MakeCode share links for Code #1 and #2, video URL — anchors only ("click here", "Here") in the text read.
- Full "Hardware Components" list with quantities and product links on the tutorial page (rendered as product cards, not text).
- micro:bit version required (touch logo implies V2 for the remote).
- Motor model, propeller size, servo model (only "9g servo"), LiPo capacity and connector, warranty, author and publish date of the tutorial.
- The 6 build-step titles beyond "gather components" and "assemble hull".

## Sources
- [PP] Product page (read by the coordinator 2026-10-19): https://my.cytron.io/p-diy-boat-mbit
- [PP: tutorial Build an RC Boat] https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit (partial text; also at https://www.cytron.io/tutorial/build-an-rc-boat-using-micro-bit — fetch failed)
- [PP] Getting Started with MOTION:BIT & Projects Guide: https://my.cytron.io/tutorial/getting-started-with-motion-bit-and-projects-guide (blocked here, not read)
- [GH] https://github.com/CytronTechnologies/pxt-motionbit — README.md via raw.githubusercontent.com
- [DS] MOTION:BIT datasheet (via `motion-bit.md`): https://docs.google.com/document/d/15iJY2DswdKegSMR-l9DNCwXlKnizPk3_2rCNBSDg5PY/edit
- Related KB files: `motion-bit.md`
