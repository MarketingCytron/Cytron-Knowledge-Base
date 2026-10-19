# Breakoutboard for SPG10 — Verified Reference

| Field | Value |
|---|---|
| Product code | BB-SPG10 [PP] |
| Family | Interface boards and breakouts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | Cytron product page "Breakoutboard for SPG10" (https://my.cytron.io/p-breakoutboard-for-spg10), read by the coordinator 2026-10-19 [PP]. The page states: "*There is no User's Manual as it is quite self explanatory." No Cytron datasheet exists. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A small breakout board for the SPG10 DC brush motor that gives the motor a secure power cable [PP]. It mounts to the back (rear) of the SPG10 motor, needs about 1 minute and two points of soldering, and comes with a 2-way cable with the proper jack (JST socket and cable/wire) so the motor terminals are extended with a ready cable [PP].

## Specifications
Every row of the product page Features list, plus the description facts.

| Item | Value | Src |
|---|---|---|
| Fits | SPG10 DC brushed motor ("designed to fit") | [PP] |
| Size | "tiny, compact" (no dimensions given) | [PP] |
| Assembly | Requires two-point soldering; about 1 minute | [PP] |
| Mounting | Back/rear of the SPG10 motor | [PP] |
| Centre hole | Allows rear shaft access | [PP] |
| Connector | Ready with JST socket and cable/wire | [PP] |
| Cable | 2-way cable included with the proper jack | [PP] |
| Alternative connection | Additional terminal pads for soldering if a cable is not preferred | [PP] |
| User manual | None ("quite self explanatory") | [PP] |
| Warranty | Not stated (blank on product page) | [PP] |
| Dimensions, JST series/pitch, cable length, current rating | Not stated | [PP] |

## Interfaces, terminals and pin mapping
- **Motor side:** two solder points to the SPG10 motor terminals [PP].
- **Output:** JST socket with a 2-way cable [PP]; or solder wires to the additional terminal pads [PP].
- Polarity marking on the board and which cable wire goes to which motor terminal: not stated. Motor direction is set by the driver anyway; swap wires (or the motor-driver outputs) if the motor turns the wrong way.

## Rules and gotchas (for code, wiring and tutorials)
- Soldering is required (two points) — it is not a press-fit or clip-on part [PP]. Tutorials must list a soldering iron in the tools.
- Fit it to the **rear** of the motor; the centre hole leaves the rear shaft accessible [PP]. What the rear shaft is used for is not stated.
- Purpose is a **secure power cable**: it takes strain off the motor's own small terminals [PP]. Do not describe it as a motor driver, encoder board or noise-suppression board — no components other than the socket and pads are stated.
- Do not state the JST series (PH, XH, SH, etc.), pitch or cable length — not stated.
- The SPG10 motor itself is a separate product; do not quote motor voltage, speed or current from this page.

## Power and electrical limits
- Current and voltage rating of the board, socket and cable: not stated [PP]. Size the motor driver to the SPG10 motor's own rating, not to this board.
- No capacitors, diodes or other components are stated [PP].

## Software support
- None. Passive wiring board [PP].

## Compatibility and accessories
- Designed for the SPG10 DC brushed motor [PP]. Compatibility with other motors is not stated.
- Included: 2-way cable with the proper jack [PP]. The page describes a breakout for the motor; it does not list the motor as included — do not imply it is.

## Common mistakes / troubleshooting
- Cold solder joint at the motor tabs → motor runs intermittently; reflow both points (two-point soldering) [PP].
- Shaft blocked at the rear → board not centred; the centre hole is there for rear shaft access [PP].
- Prefer no connector → use the additional terminal pads instead of the JST socket [PP].

## Conflicts between sources
None found. Only the Cytron product page was used; no datasheet, manual or reseller text was needed for any stated fact.

## Needs verification
- Board dimensions and mounting method beyond soldering (any screw/adhesive).
- JST connector series and pitch, and cable length.
- Which SPG10 variants (gear ratios, with/without rear shaft) it fits — page says only "SPG10 DC brushed motor".
- Polarity marking on the pads/socket.
- Warranty (blank on the product page).

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM3.15 special offer, was RM6.30; availability 33; warranty blank; description; Features list; "There is no User's Manual as it is quite self explanatory") — https://my.cytron.io/p-breakoutboard-for-spg10
