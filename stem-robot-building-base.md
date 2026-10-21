# STEM Robot Building Base Bundles — Verified Reference

| | |
|---|---|
| Product code | `V-HD-STEM` [PP] |
| Family | Robot parts and project bundles |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — the Cytron tutorial "STEM Robot Building Base Kit Step-by-Step Installation Guide" (Hao Zhen Goh, 25 Jul 2023) read in full in the browser: 8 text steps plus all 12 step/example images and their printed captions. Corrects the KB's earlier step summary (the brackets go on the motors first, then the motor-plus-bracket is screwed to the lower plate), and adds per-step fastener use (M2.2 × 6 mm screws for brackets, spacers, upper plate and castor), the corner-tab removal, castor position on the centreline, and which example boards are screwed vs cable-tied. Raised Medium → Medium-high; still open: TT motor rating, wheel size, hole pattern, weight, Maker Line position. Earlier: 2026-10-19 master-table review of the product page and its dimension image (plate 12 × 8.5 cm; assembled robot 13.5 cm long × 6.5 cm high) |
| Primary source | No datasheet or user manual exists for this product. Primary sources = the Cytron tutorial **"STEM Robot Building Base Kit Step-by-Step Installation Guide"** (Hao Zhen Goh, 25 Jul 2023, Tutorial, Beginner) https://my.cytron.io/tutorial/p-stem-rbb-kit-step-by-step-installation-guide — read in full incl. all images 2026-10-21 [PP: tutorial] — and the **Cytron product page "STEM Robot Building Base Bundles"** (https://my.cytron.io/p-stem-robot-building-base-kit), read by the coordinator 2026-10-19 [PP]. Cytron Marketing's tutorial index gave the same title, author and date  |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page facts as saved by the coordinator (jkl-pp.md, 2026-10-19). [PP: tutorial] = the installation guide above, read in full in the browser 2026-10-21 (text plus the captions printed inside its step images; image-only facts are marked "image").  = Cytron Marketing tutorial index (`MarketingCytron/Restructure-Cytron-Tutorial-Page`, data/tutorials.json, scraped Sep 2026) — metadata only, no article body. [3P] = CNX Software's Robo Pico / BocoBot review (July 2023), which uses the same chassis parts; cross-check only. No board in this bundle has its own KB file (the TT motors, wheels and castor are generic parts).

## What it is
- A plastic two-wheeled robot-car chassis bundle: "Plastic base + motor brackets, DC motors, rubber wheels, steel castor; build with a screwdriver" [PP].
- The microcontroller / motor driver board is "secured with screws or cable ties" to the base [PP]. The page shows it used with REKA:BIT, MOTION:BIT, Maker Pi RP2040 and Robo Pico (the Boco Bot kit) [PP] — none of these boards is included (see *Compatibility*).
- Two purchase options: **Blue base** or **Green base**; the motor brackets are always blue [PP].
- Features listed on the page: step-by-step guide; durable lightweight plastic chassis; 2-wheeled robot car [PP].
- Price: RM35.00 (Cytron product page, read 2026-10-19) [PP].
- Warranty field on the page is blank [PP].

## Specifications
There is no datasheet and no spec table. Every stated physical fact is below.

| Item | Value | Src |
|---|---|---|
| Base material | "Plastic" / "durable lightweight plastic chassis" (polymer type not stated) | [PP] |
| Base colour options | Blue or Green | [PP] |
| Motor bracket colour | Blue (both options) | [PP] |
| Drive | 2-wheeled robot car (2x TT motor, 2x wheel, 1x castor) | [PP] |
| TT motor leads | 15 cm wires | [PP] |
| Castor | Steel ball castor | [PP] |
| Wheels | "rubber wheels" (diameter not stated) | [PP] |
| Dimensions — base plate | 12 × 8.5 cm | [PP: img] |
| Dimensions — assembled robot | 13.5 cm long × 6.5 cm high (with wheels) | [PP: img] |
| Weight | Not stated | — |
| Price | RM35.00 | [PP] |
| Stock (2026-10-19) | 136 units | [PP] |
| Warranty | Not stated (field blank) | [PP] |

### Packing list (per bundle, either colour) [PP]
| Qty | Item |
|---|---|
| 2 | Robot Building Base (plastic plates) |
| 2 | Motor Bracket (blue) |
| 25 | M2.2 x 6 mm self-tapping screw |
| 3 | M2.3 x 8 mm self-tapping screw "for Maker Line" |
| 4 | Spacer |
| 2 | TT motor with 15 cm wires |
| 2 | Wheel |
| 1 | Steel ball castor |
| 1 | Tiny Phillips screwdriver |

## Interfaces, terminals and pin mapping
- Mechanical product only: no electrical interface, no pins [PP].
- The TT motors have 15 cm bare wire leads [PP]; how they terminate (bare, JST, etc.) is not stated.
- Mounting: the controller / motor driver board is "secured with screws or cable ties" [PP]. No hole pattern or hole diameter is stated (the dimension image gives only outer sizes) [PP: img].
- Maker Line sensor mounting: 3x M2.3 x 8 mm self-tapping screws are supplied "for Maker Line" [PP] — i.e. the base is designed to take a Maker Line sensor (see `maker-line.md`); the exact position/holes are not stated in text.

## Rules and gotchas (for code, wiring and tutorials)
- **Nothing electronic is included.** A tutorial must list a controller/motor driver board, battery, sensors and a Maker Line (if line following) separately [PP packing list].
- **Two screw sizes, two jobs:** 25x M2.2 x 6 mm (general: brackets/boards) and 3x M2.3 x 8 mm reserved for the Maker Line [PP]. Do not use up the M2.3 screws elsewhere.
- **Cable ties are an alternative fixing** named on the page [PP] but they are **not in the packing list** — tell readers to supply their own if the board's holes don't match.
- **TT motor polarity / direction** is not stated; the motor driver board's own KB file governs wiring direction.
- **Size:** base plate 12 × 8.5 cm; assembled robot 13.5 cm long × 6.5 cm high [PP: img].
- **Assembly order (Cytron installation guide, 8 steps)** [PP: tutorial]:
  1. Unpack all parts.
  2. Fit the blue motor brackets **onto the DC (TT) motors**.
  3. Screw each motor-and-bracket to the plastic base, which becomes the **lower layer** — "Place the DC Motor on the plastic base. Make sure all 4 holes are aligned", then "Tighten 4 screws (M2.2 x 6mm self tapping screw) on the motor bracket" (image captions). Repeat for the second motor on the other side. **Wires face inward.**
  4. Spacers: "Remove this small part for all 4 corners at the bottom of the plastic board"; drive an M2.2 × 6 mm screw up through each bottom corner and tighten a spacer onto it from the top; repeat on all 4 corners (image captions).
  5. Fit the upper-layer plate on the spacers: align its holes with the spacers and fix each corner with an M2.2 × 6 mm screw (all 4 corners) (image captions).
  6. Fix the steel ball castor under the lower layer with **2x M2.2 × 6 mm** screws, **on the centreline** of the plate (image captions).
  7. Push the rubber wheels onto the motor shafts.
  8. Done. The guide then shows example boards fixed on the upper plate (see *Compatibility*).
  Every fixing in the guide uses the M2.2 × 6 mm self-tapping screws and the supplied screwdriver; the M2.3 × 8 mm screws are not used.
- **Spacers join the two plates** (they are not for the castor or the board) [PP: tutorial].
- **Remove the small plastic part at each bottom corner** of the lower plate before fitting the spacers (image caption) [PP: tutorial].
- **Castor on the centreline:** place it on the centreline of the lower plate — "Make sure the holes are aligned" (image caption) [PP: tutorial].

## Power and electrical limits
- None stated — no electronics in the bundle [PP]. The TT motors' voltage and current ratings are **not stated** on the page; use the limits in the motor driver board's KB file when writing power advice.

## Software support
- None (mechanical kit) [PP]. Code depends on the controller board chosen (REKA:BIT → `reka-bit.md`; MOTION:BIT → `motion-bit.md`; Maker Pi RP2040 → `maker-pi-rp2040.md`; Robo Pico → `robo-pico.md`).
- Guide: Cytron tutorial "STEM Robot Building Base Kit Step-by-Step Installation Guide", Hao Zhen Goh, 25 Jul 2023, Beginner [PP: tutorial] — read in full in the browser 2026-10-21 (8 text steps, 12 images; summary under *Rules and gotchas*). No code in the guide.

## Compatibility and accessories
- Installation-guide examples ("Securing MCU on the Plastic Base", images) [PP: tutorial]: **REKA:BIT**, **Robo Pico (with Raspberry Pi Pico W)** and **Maker Pi RP2040** are shown fixed to the upper plate with self-tapping screws; **MOTION:BIT** is shown held with **cable ties**. The guide's hardware list links REKA:BIT, Maker Pi RP2040, MOTION:BIT, Robo Pico and the bundle (Blue / Green, RM35.00 each).
- Boards shown on the page: REKA:BIT, MOTION:BIT, Maker Pi RP2040, Robo Pico ("Boco Bot kit") [PP] — see `reka-bit.md`, `motion-bit.md`, `maker-pi-rp2040.md`, `robo-pico.md`. None is included.
- Maker Line sensor: screws provided "for Maker Line" [PP] — see `maker-line.md`. Not included.
- [3P] CNX Software's BocoBot review lists the same chassis family (robot chassis, 2x TT motors and 2x wheels, "a caster (small metal wheel mounted on a plastic frame)", screwdriver and screw set) in the Robo Pico kit — cross-check only; it does not name "STEM Robot Building Base".
- Related product in the catalogue (different product, not an alias): Robo Base / Robo Base Mini PCB chassis (BEETLE:BIT, STRIKER:BIT) — not this plastic base.

## Common mistakes / troubleshooting
- **Board won't line up with base holes** → the page allows cable ties as the fixing method [PP], and the guide shows MOTION:BIT held with cable ties [PP: tutorial]; bring cable ties (not supplied).
- **Spacer won't sit flat at a corner** → the small plastic part at that bottom corner was not removed (guide step 4) [PP: tutorial].
- **Motor bracket screws won't bite** → check all 4 bracket holes are aligned with the plate holes before tightening (guide step 3) [PP: tutorial].
- **Ran out of screws for the Maker Line** → the 3x M2.3 x 8 mm screws are the Maker Line screws; the 25x M2.2 x 6 mm are for everything else [PP].
- **Motor brackets are blue on a green base** → that is as sold ("motor brackets always blue") [PP], not a packing error.
- **Expecting a battery holder or battery** → not in the packing list [PP].
- **Motor wires snag on the wheels** → the guide routes the motor wires inward, toward the centre of the base [PP: tutorial].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Fixing method vs contents | [PP] text: board "secured with screws or cable ties" | [PP] packing list: screws and spacers only, no cable ties | Cable ties are optional and user-supplied; state this in tutorials |
| Date of the installation guide | [PP: tutorial] page header "Hao Zhen Goh, 25 Jul 2023" (read 2026-10-21) |  index: same author, "25 Jul 2023" | No conflict |
| Fixing method for boards | [PP] board "secured with screws or cable ties" | [PP: tutorial] examples: REKA:BIT, Robo Pico, Maker Pi RP2040 screwed; MOTION:BIT cable-tied | No conflict; the guide shows which method each example uses |

Correction (not a source conflict): the KB's 2026-10-19 summary said the brackets were fixed to the plate first and the motors fitted after; the guide fits the brackets onto the motors first (step 2), then screws the motor-and-bracket to the plate (step 3). Fixed 2026-10-21.

## Needs verification
- **Mounting-hole pattern** — not stated. The guide's images show REKA:BIT, Robo Pico and Maker Pi RP2040 screwed down and MOTION:BIT cable-tied, but give no hole positions.
- **TT motor rating** (voltage, gear ratio, no-load RPM), **wheel diameter/width**, **castor size** — not stated by Cytron.
- **Motor lead termination** (bare wire vs connector) — "15 cm wires" only.
- **Weight** — not stated.
- Where the Maker Line fixes with the 3 × M2.3 × 8 mm screws — the installation guide (read in full 2026-10-21) does not cover it.
- Whether "4 screws" per motor bracket in guide step 3 means 4 per motor or 2 per side — caption is ambiguous.
- Whether this bundle is identical to the chassis supplied inside the BocoBot (Robo Pico) kit — implied by the page's "Boco Bot kit" photo and the [3P] review, not stated.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [STEM Robot Building Base Kit Step-by-Step Installation Guide](https://my.cytron.io/tutorial/p-stem-rbb-kit-step-by-step-installation-guide) — Tutorial, Beginner, 2023 [PP: tutorial]

## Sources
- [PP] https://my.cytron.io/p-stem-robot-building-base-kit — read by the coordinator 2026-10-19 (RM35.00; Blue / Green; stock 136; warranty blank; packing list; features; dimension image)
- [PP: tutorial] "STEM Robot Building Base Kit Step-by-Step Installation Guide", Hao Zhen Goh, 25 Jul 2023, Tutorial, Beginner — https://my.cytron.io/tutorial/p-stem-rbb-kit-step-by-step-installation-guide — read in full in the browser 2026-10-21 (8 steps; 12 images: steps 2, 3a, 3b, 4a, 4b, 5a, 5b, 6, 7, done, two example-connection images)
- [3P] https://www.cnx-software.com/2023/07/30/robo-pico-review-raspberry-pi-pico-w-motor-sensor-control-board-bocobot-robotic-kit/ (cross-check only)
- KB cross-references: `reka-bit.md`, `motion-bit.md`, `maker-pi-rp2040.md`, `robo-pico.md`, `maker-line.md`
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
