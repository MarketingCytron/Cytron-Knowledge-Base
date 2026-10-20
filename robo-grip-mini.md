# Robo Grip Mini Kits — Verified Reference

| | |
|---|---|
| Product code | `V-ROBO-GRIP-MINI` [PP] |
| Family | Robot platforms and parts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 3): live my.cytron.io product page read (description, features, packing list, resources). Packing lists re-read; the page now heads them "Robo Grip Mini with 3 Servos / with 2 Servos / with Accessories", and the rivet is printed "3x65mm". Stays Medium |
| Primary source | No Cytron datasheet or user manual could be found, and the printed "assembly guide" that ships in the box is not on Drive (searches "Robo Grip Mini", "Robo Grip", "ROBO-GRIP", "Gripper" returned only planning sheets). Primary sources = **Cytron product page "Robo Grip Mini Kits"** https://my.cytron.io/p-robo-grip-mini-kits [PP] and the Cytron tutorial **"Robo Grip Mini Installation Guide"** (Norasyiqin Munirah, 23 Feb 2026, Beginner, 4-part series) [PP: tutorial Installation Guide], both read by the coordinator 2026-10-19 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
- A PCB gripper kit for 9 g-class micro servos, with mounting holes compatible with the Robo Base Series (Robo Base, Robo Base Mini) [PP].
- The gripper parts come on one PCB panel ("Robo Grip Mini PCB (with 6 label parts)") that is snapped apart and filed before assembly [PP: tutorial IG].
- Builds as a gripper only (1 servo), a 1-axis gripper (2 micro servos) or a 2-axis gripper (3 micro servos) [PP][PP: tutorial IG].
- "Durable PCB" — described as a "cost-friendly alternative to metal grippers" [PP]. BEETLE:BIT's page describes its gripper as "non-copper PCB with servo motor" [PP: BEETLE:BIT page].
- Warranty field blank on the product page [PP].

## Specifications
No datasheet spec table exists. Facts stated in text:

| Item | Value | Src |
|---|---|---|
| Material | PCB ("durable PCB"); thickness **not stated in text** ("Material and thickness" is an image) | [PP] |
| Dimensions / weight | Not stated | [PP] |
| Options | Gripper only / 1-axis Gripper (2 micro servo) / 2-axis Gripper (3 micro servos) | [PP] |
| Servo fit | SG90, MG90S, TS90A, EF90D, FS90R and same-dimension servos | [PP] |
| Servo supplied in kits | TS90A micro servo (2x in 1-axis kit, 3x in 2-axis kit) | [PP] |
| Configurations | 1, 2 or 3 servo motors | [PP: tutorial IG] |
| Mounting | Holes compatible with the Robo Base Series | [PP] |
| Price | RM34.90–RM94.19 across the three options; per-option prices not stated | [PP] |
| Warranty | Blank on the page | [PP] |

### Packing lists [PP]
| Option | Contents |
|---|---|
| 2-axis Gripper (3 micro servos) | 1x Robo Grip Mini PCB, 6x M2 bolt 6mm, 6x M2 nut, 1x M3 SS PCB stand 40mm, 4x nylon M3 PCB stand 20mm + nut set, 4x nylon M3 PCB stand 10mm + nut set, 12x M3 bolt 6mm, 4x M3 bolt 12mm, 4x M3 nut, 5x M3 lock nut, 6x M3 plastic washer H1 W7, 5x M3 plastic washer H3 W7, 2x M3 black plastic rivet 3x6, M2 and M3 transparent Philips screwdrivers, mini cross wrench, **2x Robo Bracket for Micro Servo Motor**, 1x aluminium micro servo bracket, 4x M2 bolt 6mm, 4x M3 bolt 6mm, **3x TS90A micro servo**, 1x assembly guide |
| 1-axis Gripper (2 micro servo) | Same, but **1x Robo Bracket** and **2x TS90A** |
| Gripper only ("with Accessories") | PCB + hardware + tools + assembly guide; **no servos, no bracket** |

### Basic kit list per the Installation Guide [PP: tutorial IG]
Robo Grip Mini PCB (with 6 label parts) x1, M2 bolt 6mm x6, M2 nut x6, M3 **brass** PCB standoff 40mm x1, M3 nylon standoff 10mm + nut x4, 20mm x4, M3 bolt 6mm x12, M3 bolt 12mm x4, M3 nut x4, M3 lock nut x5, M3 plastic washer 1mm height x6, 3mm height x5, M3 black plastic rivet x2, M2 and M3 screwdrivers, mini cross wrench. Robo Bracket set: bracket, 4x M2 bolt 6mm, 4x M3 bolt 6mm. Micro servo set: servo, 3 horns, 2 self-tapping screws, 1 short horn screw.
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Packing-list headings (current page):** "Robo Grip Mini with 3 Servos", "Robo Grip Mini with 2 Servos", "Robo Grip Mini with Accessories" — same contents as the KB's 2-axis / 1-axis / Gripper-only lists [PP].
- **Rivet:** printed "2 x M3 black plastic rivet 3x65mm" in all three lists [PP] — most likely 3 × 6.5 mm (a 65 mm rivet would not fit this gripper); confirm.
- Description: PCB gripper for micro servos (SG90, MG90S, TS90A, EF90D, FS90R and same-size servos); fits Cytron Robo Base series; one-axis or two-axis builds; standard screws, nuts and standoffs; step-by-step installation guide (Cytron tutorial) [PP].
- Prices subject to SST from April 2026 [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface. Servo leads go to the user's controller board servo ports [PP].
- Which servo does what [PP: tutorial IG]: **1 servo** = main gripping motion; **2 servos** = adds arm movement; **3 servos** = better angle control / positioning.
- Hole positions and the Robo Base mounting pattern are not stated in text.

## Rules and gotchas (for code, wiring and tutorials)
- **Snap and file first:** "Before starting, snap and break every part. File the snapped parts." [PP: tutorial IG].
- **Servo count is 1, 2 or 3** on current Cytron sources — never 4 (see Conflicts) [PP][PP: tutorial IG].
- **Gripper only option has no servo and no Robo Bracket** — the reader must supply a micro servo [PP].
- **Option names vs servo count:** "1-axis" = 2 servos, "2-axis" = 3 servos [PP]; the gripping servo is not counted as an "axis".
- **Servo size:** only SG90 / MG90S / TS90A / EF90D / FS90R and same-dimension micro servos [PP]. FS90R is continuous-rotation — gripping code that sets angles won't work as written on it.
- **No controller, battery or chassis included** — mount on Robo Base / Robo Base Mini (bought separately) and drive from a controller with servo outputs.
- Servo power comes from the controller board. Cytron's BEETLE:BIT code releases the gripper servo after each move (`disableServo`, see `beetlebit.md`) — reuse that pattern.

## Power and electrical limits
- None for the gripper itself. Servo supply limits belong to the controller's KB file (e.g. `reka-bit.md` servo V+ = input voltage; `motion-bit.md`; `zoom-bit.md`).

## Software support
- None needed for the gripper. Cytron content [PP]: "Robo Grip Mini Installation Guide" (23 Feb 2026, 4 parts); project "ZOOM:BIT with Robo Grip Mini" (Ng Zhi Tian, 18 Mar 2026); "3D Printed ZOOM:BIT with 3D Robo Grip" (07 Apr 2026). BEETLE:BIT chapter code drives its gripper servo on REKA:BIT **S1** (open 120 / closed 0 in Ch. 6–7; 0/180 in Ch. 3) [see `beetlebit.md`].

## Compatibility and accessories
- **Chassis:** Robo Base and Robo Base Mini — "mounting holes compatible with the Robo Base Series" [PP]; see `robo-base.md`, `robo-base-mini.md`.
- **Servo bracket:** Robo Bracket for Micro Servo Motor (`ROBO-BK-SG90`, `robo-bracket-micro-servo.md`) — 1x in the 1-axis kit, 2x in the 2-axis kit [PP].
- **Servos:** SG90, MG90S, TS90A, EF90D, FS90R and same-dimension servos [PP].
- **Kits that use it:**
  - BEETLE:BIT — "1x Robo Grip PCB with accessories" + 1x TS90A; the resource hub calls it "Robo Grip Mini" [PP: BEETLE:BIT page, `beetlebit.md`].
  - STRIKER:BIT — "Robo Grip Mini Basic Bundle" per robot, used with a 3D-printed part as a **servo shooter, not a gripper** [PP: STRIKER:BIT page, `strikerbit.md`].
  - ZOOM:BIT — Cytron project "ZOOM:BIT with Robo Grip Mini" [PP].

## Common mistakes / troubleshooting
- **Parts don't fit / rough edges** → snap every part off the panel and file the edges first [PP: tutorial IG].
- **No servo in the box** → the Gripper only option has none [PP].
- **Servo won't fit** → only 9 g micro servos of SG90 dimensions fit [PP].
- **Gripper doesn't hold its angle / jitters** → check the servo isn't a continuous-rotation FS90R and the controller's servo supply is adequate (controller KB file).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Servo count in the full kit | [PP] options max "2-axis Gripper (3 micro servos)"; [PP: tutorial IG] 1, 2 or 3 servos | [3P] Switch Science 11032 sells "with 3 TS90A" but links a Cytron URL `p-robo-grip-mini-kit-with-4pcs-ts90a-micro-servo-motor` ("4pcs") | Cytron page + tutorial win: **max 3 servos**. The "4pcs" slug is a URL only, not a spec |
| 40 mm standoff material | [PP] "M3 SS PCB stand 40mm" | [PP: tutorial IG] "M3 brass PCB standoff 40mm" ([3P] Switch Science: steel spacer) | Both Cytron; say "M3 40 mm metal standoff"; material in Needs verification |
| Plastic rivet size | [PP] (read 2026-10-19): "M3 black plastic rivet 3x65mm" | [3P] Switch Science: "65 mm" rivets (same string) | Probably 3 × 6.5 mm; do not quote a length until confirmed (*Needs verification*) |
| Name in kits | [PP: BEETLE:BIT] "Robo Grip PCB with accessories" | [PP: STRIKER:BIT] "Robo Grip Mini Basic Bundle" | Same product family; which option each bundle equals is in Needs verification |

## Needs verification
- **PCB thickness, dimensions, weight, jaw opening and grip force** — not in text.
- **40 mm standoff material** (stainless steel vs brass).
- **Which option "Robo Grip Mini Basic Bundle" (STRIKER:BIT) and "Robo Grip PCB with accessories" (BEETLE:BIT) correspond to** — probably Gripper only, not confirmed.
- **Per-option prices** — only the RM34.90–RM94.19 range is in text.
- **Role of the aluminium micro servo bracket** vs the Robo Brackets in the 2- and 3-servo builds — step images not read.
- **What the printed assembly guide contains** and whether it matches the online Installation Guide.
- Warranty — blank on the page.
- Reseller code `CYTRON-CK-ROBO-GP-MINI-3TS90` [3P Switch Science].
- Rivet size printed "3x65mm" on the product page — confirm whether it means 3 × 6.5 mm.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Robo Grip Mini Installation Guide](https://my.cytron.io/tutorial/robo-grip-mini-installation-guide) — Tutorial, Beginner, 2026 (series, 4 parts) [PP: tutorial]
- [ZOOM:BIT with Robo Grip Mini](https://my.cytron.io/tutorial/zoombit-with-robo-grip-mini) — Project, Beginner, 2026 [PP: tutorial]
- [3D Printed ZOOM:BIT with 3D Robo Grip](https://my.cytron.io/tutorial/3d-zoombit-with-robo-grip-mini) — Tutorial, Beginner, 2026 [PP: tutorial]
- [RDK X5 Robot Kit with Robo Grip Mini](https://my.cytron.io/tutorial/rdk-x5-robot-kit-with-robo-grip-mini) — Tutorial, Intermediate, 2026 (part of "RDK X5 Mission Ready Robotic Series") [PP: tutorial]

## Sources
- [PP] https://my.cytron.io/p-robo-grip-mini-kits — Robo Grip Mini Kits, read by the coordinator 2026-10-19 (RM34.90–RM94.19, availability 177, warranty blank, options, packing lists, servo list)
- [PP: tutorial IG] https://my.cytron.io/tutorial/robo-grip-mini-installation-guide — Norasyiqin Munirah, 23 Feb 2026 (kit list, snap-and-file note, 1/2/3-servo roles)
- [PP] https://my.cytron.io/tutorial/zoombit-with-robo-grip-mini — Ng Zhi Tian, 18 Mar 2026 (title/metadata only)
- [3P] https://www.switch-science.com/products/11032 — Robo Grip Mini kit with 3 TS90A (links the Cytron "with-4pcs" URL)
- KB cross-references: `robo-base.md`, `robo-base-mini.md`, `robo-bracket-micro-servo.md`, `beetlebit.md`, `strikerbit.md`, `zoom-bit.md`
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
