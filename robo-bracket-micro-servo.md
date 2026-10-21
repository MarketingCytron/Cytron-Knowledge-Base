# Robo Bracket for Micro Servo Motor — Verified Reference

| | |
|---|---|
| Product code | `ROBO-BK-SG90` [PP] |
| Family | Robot parts and project bundles |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron dimension drawing `robo-bk-sg90-dimensions.png` (the product page image, supplied by the team) read: overall size, slot and hole positions, hole sizes and which holes are threaded. Raised Medium → Medium-high; still open: weight, warranty, recommended orientation. Earlier: 2026-10-19 master-table review of the live product page |
| Primary source | No datasheet, user manual or guide exists. Primary sources = **Cytron product page "Robo Bracket for Micro Servo Motor"** (https://my.cytron.io/p-robo-bracket-for-microservo-motor), read by the coordinator on 2026-10-19 [PP], and its **dimension drawing** `robo-bk-sg90-dimensions.png` (three views, mm), read 2026-10-21 [PP: drawing]. The Cytron project "ZOOM:BIT with Robo Grip Mini" (Ng Zhi Tian, 18 Mar 2026) is linked from the page but was not read |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page facts saved by the coordinator (jkl-pp.md, 2026-10-19).  = Cytron Marketing tutorial index (metadata only: titles, authors, dates). [PP: drawing] = the product page's dimension drawing (front, side and top views, mm), read 2026-10-21. Page text and drawing do not conflict. Robo Base, Robo Base Mini and Robo Grip Mini are separate Cytron products and are **not** aliases for this bracket.

## What it is
- A black powder-coated aluminium-alloy bracket that holds a 9 g-class micro servo and bolts to Cytron's Robo Base / Robo Base Mini chassis plates [PP].
- Fits micro servos SG90, MG90S, TS90A, EF90D, FS90R "and same-dimension servos (23.0 x 12.2 x 29.0 mm)" [PP].
- "Designed to fit Robo Base and Robo Base Mini" [PP].
- Price RM9.90 (Cytron product page, read 2026-10-19) [PP]. Stock 82 on 2026-10-19 [PP]. Warranty field blank [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | Aluminium alloy | [PP] |
| Sheet thickness | 1.5 mm | [PP] |
| Finish | Powder coating | [PP] |
| Colour | Black | [PP] |
| Servo pocket | For servos of 23.0 x 12.2 x 29.0 mm (SG90 / MG90S / TS90A / EF90D / FS90R and same-dimension servos) | [PP] |
| Chassis fit | Robo Base and Robo Base Mini | [PP] |
| Overall dimensions | **37.50 mm wide × 28.00 mm high × 14.50 mm deep** | [PP: drawing] |
| Weight | Not stated | — |
| Front face | 3 × 3.0 mm slots: two vertical slots **25.00 mm** apart (centres) and one horizontal slot whose centre is **6.50 mm** above the bottom edge; four small round holes beside the vertical slots (size not dimensioned); one rectangular cut-out | [PP: drawing] |
| Side face | **4 × M3 threaded** holes in a diamond: **8.00 mm** apart vertically, **6.00 mm** apart horizontally | [PP: drawing] |
| Top / servo-tab view | **2 × M2 threaded** holes for the servo mounting tabs; **2 × M3** holes **10.50 mm** apart (not marked threaded); hole row **11.00 mm** from the reference edge | [PP: drawing] |
| Warranty | Not stated (field blank) | [PP] |
| Price | RM9.90 | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | Robo Bracket for Micro Servo Motor |
| 4 | M2 x 6 screw |
| 4 | M3 x 6 screw |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read: fits SG90, MG90S, TS90A, EF90D, FS90R and servos of the same size (23.0 × 12.2 × 29.0 mm); aluminium alloy, 1.5 mm, black powder coating; fits Robo Base and Robo Base Mini; packing 1x bracket, 4x M2×6 screw, 4x M3×6 screw [PP]. No new facts beyond the KB.
- Dimension image `robo-bk-sg90-dimensions.png` — read 2026-10-21 (see *Specifications*).

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface [PP].
- **Servo tabs → the 2 × M2 threaded holes** with the M2 × 6 screws: the holes are threaded, so no nuts are needed [PP: drawing]; that the M2 screws go here is inferred from the matching thread size.
- **Bracket → chassis:** M3 × 6 screws into the **4 × M3 threaded** side holes (8.00 × 6.00 mm diamond), or through the **2 × M3** top holes (10.50 mm apart) and the 3.0 mm slots on the front face [PP: drawing]. Which face Cytron intends for Robo Base / Robo Base Mini is not stated (see *Needs verification*).
- The threaded holes explain why the packing list has **no nuts** [PP][PP: drawing].

## Rules and gotchas (for code, wiring and tutorials)
- **Servo size is the only fit rule:** the bracket is for 23.0 x 12.2 x 29.0 mm micro servos [PP]. Standard-size servos (e.g. MG996R) and "sub-micro" servos of other dimensions are not covered — don't claim they fit.
- **FS90R is a continuous-rotation servo** in the compatibility list [PP]; the bracket fits it mechanically, but continuous rotation changes the code (speed, not angle) — say so in tutorials.
- **Bracket only:** no servo, servo horn, horn screw or nuts are included [PP packing list].
- **Chassis:** stated for Robo Base and Robo Base Mini [PP]; fit on the plastic STEM Robot Building Base (`stem-robot-building-base.md`) or other chassis is not stated.
- **Screws:** 4x M2 x 6 and 4x M3 x 6 [PP]; do not quote longer screws or nuts as included. The M2 and side M3 holes are threaded, so screws go straight in [PP: drawing]. A 1.5 mm sheet gives only a few threads — do not over-tighten (general practice, not stated by Cytron).
- The bracket is 1.5 mm aluminium [PP] — rigid, not a flexible/printed part; no load rating is stated.

## Power and electrical limits
- None (mechanical part) [PP]. Servo electrical limits belong to the servo and the controller board's KB file (e.g. REKA:BIT servo ports in `reka-bit.md`, MOTION:BIT in `motion-bit.md`).

## Software support
- None. Linked Cytron content: project "ZOOM:BIT with Robo Grip Mini" (Ng Zhi Tian, 18 Mar 2026, Beginner, about 425 words; excerpt "A tutorial on how to combine gripper with zoombot robot") [PP]. Related Cytron tutorials in the index: "Robo Grip Mini Installation Guide" (Norasyiqin Munirah, 23 Feb 2026, 4-part series; "how to install the Robo Grip Mini using one, two, or three servo motors") and "3D Printed ZOOM:BIT with 3D Robo Grip" (Ng Zhi Tian, 07 Apr 2026) . None of these bodies was read; whether they use this bracket is not confirmed.

## Compatibility and accessories
- Servos: SG90, MG90S, TS90A, EF90D, FS90R and same-dimension (23.0 x 12.2 x 29.0 mm) servos [PP].
- Chassis: Robo Base, Robo Base Mini [PP] (separate Cytron products; Robo Base PCB plates ship in BEETLE:BIT, Robo Base Mini kits in STRIKER:BIT — see those kits' KB files).
- Cytron micro servos sold in kits that match the list: TS90A (BEETLE:BIT) [PP in jkl-pp.md].
- Related gripper: Robo Grip Mini (separate product) — the linked project combines a gripper with ZOOM:BIT [PP].

## Common mistakes / troubleshooting
- **Servo doesn't sit in the bracket** → check the servo body is 23.0 x 12.2 x 29.0 mm; larger "standard" servos won't fit [PP].
- **Not enough screws** → only 4x M2 x 6 and 4x M3 x 6 are supplied; nuts are not needed for the threaded holes [PP][PP: drawing].
- **Bracket holes don't match the chassis** → it is designed for Robo Base / Robo Base Mini [PP]; other chassis are not stated to fit.
- **Scratched finish** → black powder coating on aluminium [PP]; cosmetic only.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | [PP] page text | [PP: drawing] dimension drawing | No conflict found; the drawing adds the sizes and hole details the text omits |

## Needs verification
- **Which face mounts to Robo Base / Robo Base Mini** (side M3 threaded diamond, top 2 × M3, or the front slots) — the drawing shows the holes but not the intended use.
- Size of the four small round holes on the front face (not dimensioned).
- **Weight** — not stated.
- **Whether it fits the STEM Robot Building Base or ZOOM:BIT's chassis** — the page only states Robo Base / Robo Base Mini.
- **Servo orientation(s) supported** (vertical / horizontal, horn up or down) — not stated.
- **Warranty** — field blank on the page.
- Contents of the linked "ZOOM:BIT with Robo Grip Mini" project — not read (the Robo Grip Mini guide notes the bracket may need filing to fit — see `robo-grip-mini.md`).

## Sources
- [PP: drawing] Dimension drawing `robo-bk-sg90-dimensions.png` from the product page (copy in the team reference folder), read 2026-10-21
- [PP] https://my.cytron.io/p-robo-bracket-for-microservo-motor — read by the coordinator 2026-10-19 (RM9.90; stock 82; warranty blank; servo list; Robo Base / Robo Base Mini; aluminium alloy, 1.5 mm, powder coating, black; packing list; dimension image)
- [PP: tutorial] https://my.cytron.io/tutorial/zoombit-with-robo-grip-mini — not readable here (blocked); metadata from  index https://raw.githubusercontent.com/MarketingCytron/Restructure-Cytron-Tutorial-Page/main/data/tutorials.json (ids 114, 126, 107)
- KB cross-references: `zoom-bit.md`, `reka-bit.md`, `motion-bit.md`, `stem-robot-building-base.md`
