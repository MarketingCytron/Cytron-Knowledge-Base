# Cytron Screw Terminal Shield — Verified Reference

| Field | Value |
|---|---|
| Product code | SHIELD-SCREW2 [UM][PP] |
| Family | Arduino shields and breakout boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "Shield-Screw2 Getting Started Guide" (Cytron Screw Terminal Shield, SHIELD-SCREW2), V1.0, JAN 2015, Cytron Technologies Sdn. Bhd. — a Getting Started Guide / user manual [UM]. No separate Cytron datasheet was found. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
An Arduino-format shield that "extends all pins of the Arduino out to 3.5mm pitch screw terminals" so wires can be fixed with a screwdriver instead of jumper wires [UM]. It also carries "a lot of the utility provided by Arduino Protoshield": a large prototyping space of both connected and unconnected 0.1" (2.54 mm) spaced through-holes, a couple of 5V and GND busses, a reset button and a LED [UM]. The shield's function is listed as "Adapter Prototype" and it is stackable [UM].

The product page describes this revision (SHIELD-SCREW2) as the screw shield "upgraded ... with the prototyping area at the middle" [PP].

It is a passive adapter/prototyping board: the guide names no active components, no voltage regulator and no logic on the shield [UM].

## Specifications
Every row below is from Section 2.0 "Specification" of the Getting Started Guide unless marked otherwise.

| Item | Value | Src |
|---|---|---|
| Compatible mainboard | Arduino Uno, Arduino Mega 2560, Arduino Mega ADK, Arduino Leonardo, Arduino Due, CT-UNO, CIKU | [UM] |
| Shield function | Adapter Prototype | [UM] |
| Board size | 74.93 mm x 81.28 mm | [UM] |
| Stackable | Yes | [UM] |
| Screw terminal pitch | 3.5 mm | [UM] §1.0 |
| Pins extended | "all pins of the Arduino" | [UM] §1.0 |
| Prototyping area | "a large prototyping space of both connected and unconnected 0.1" spaced through-holes"; located "at the middle" | [UM] §1.0; [PP] |
| Power busses | "a couple 5V and GND busses" | [UM] §1.0 |
| Reset button | Yes (1) | [UM] §1.0 |
| LED | Yes ("a LED") | [UM] §1.0 |
| Packing list | Screw Terminal Shield (board only) | [UM] §3.0 |
| Warranty | 12 months, manufacturing defects only; misuse not covered; freight both ways not covered | [UM] §6.0; [PP] 12 months |
| Terminal count, terminal current/voltage rating, ISP/ICSP pads, weight, operating temperature | Not stated | [UM] |

## Interfaces, terminals and pin mapping
- **Screw terminals:** 3.5 mm pitch, extending "all pins of the Arduino" [UM]. The guide does not list the terminals individually, give a count, or state the terminal order — its hardware section is a photo of the shield stacked on an Arduino Uno, which the Google Doc text export does not reproduce [UM]. See Needs verification for the terminal order reported by a reseller forum.
- **Stackable headers:** the shield is stackable, so another shield can go on top and the Arduino headers remain available [UM].
- **Prototyping area:** 0.1" (2.54 mm) grid through-holes, some connected in strips ("connected") and some isolated ("unconnected"), placed in the middle of the board [UM][PP]. Which holes are strip-connected is not stated in text.
- **Busses:** more than one 5V bus and more than one GND bus ("a couple") run beside the prototyping area [UM].
- **Reset button:** on the shield, because a stacked shield covers the Arduino's own reset button [UM]. Its wiring (to RESET) is implied by the name, not stated.
- **LED:** one LED [UM]. Whether it is a power LED or a user LED, and which pin it is on, is not stated.
- **ISP / ICSP pads:** not mentioned anywhere in the guide [UM]. Do not claim them.

## Rules and gotchas (for code, wiring and tutorials)
- No code is needed for the shield itself: it only re-routes Arduino pins to screw terminals [UM]. Pin numbers in a sketch are the Arduino's own pin numbers.
- Always **read the silkscreen label at each terminal**, not the position: a reseller forum reports that the terminal order on the power side differs from the Arduino Uno header order, although each terminal is correctly labelled ([3P] — see Needs verification). Tutorials should show wires going to a labelled terminal (e.g. "the terminal marked 5V"), never "the third terminal from the left".
- Use a small flat screwdriver to open the 3.5 mm terminals before inserting bare wire; the guide gives no wire-gauge range, so do not state one.
- The shield's reset button is the one to press when a stacked shield hides the Arduino's own button [UM].
- Board size 74.93 mm x 81.28 mm is larger than an Arduino Uno outline, so the shield overhangs the Uno — allow room in an enclosure [UM].
- "All pins" is stated for "the Arduino" generically; the guide does not say that the extra Mega 2560 / Due pins (D22–D53, A6–A15) are brought out. Do not claim full Mega pin coverage — see Needs verification.

## Power and electrical limits
- The shield has no regulator or power input of its own: the 5V and GND busses are the Arduino's 5V and GND, extended through the stackable headers [UM]. Anything powered from the shield's 5V bus draws from the Arduino's regulator/USB supply.
- Screw-terminal voltage and current ratings: not stated [UM]. Do not quote a terminal current limit.
- No fuse, no reverse-polarity protection and no level shifting are mentioned [UM] — do not claim them.

## Software support
- None required and none provided; the guide has no software section [UM]. Works with whatever software the host board uses (Arduino IDE for Uno/Mega/Leonardo/Due/CT-UNO; CIKU uses its own PIC toolchain — guide names CIKU as compatible but gives no software notes) [UM].

## Compatibility and accessories
- Compatible mainboards per the guide: Arduino Uno, Arduino Mega 2560, Arduino Mega ADK, Arduino Leonardo, Arduino Due, CT-UNO and CIKU [UM]. The guide's Requirements/Setup text says it "can be stack on any arduino main board" and shows it on an Arduino Uno [UM].
- Product page [PP] text read by the coordinator only mentions the prototyping-area upgrade; it does not add or remove any board from this list.
- A reseller lists it as compatible with "Arduino Mega 2560 Rev3, Genuino, and similar boards" [3P] — consistent with the guide but not a source.
- Package: the shield only [UM]. No headers, screwdriver or wires are listed.
- Related Cytron boards: the guide calls it a superset of a Protoshield; Cytron's separate SHIELD-PROTO2 prototyping shield is a different product (no KB file — no Cytron datasheet/manual found).

## Common mistakes / troubleshooting
- "The GND terminal is where my Uno has VIN" → the shield re-orders the power-side terminals; wire by the label printed on the shield, not by Uno header position ([3P] report, logic consistent with [UM] "extends all pins").
- Arduino does not reset → press the shield's reset button, which is wired for exactly this use [UM].
- Terminal does not grip wire → terminal screw not opened enough before inserting the wire; 3.5 mm pitch terminals take thin wire only (gauge not stated).
- Expecting an ISP header → none is documented [UM].
- Board overhangs the Arduino → expected; the shield is 74.93 mm x 81.28 mm [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Terminal order vs Arduino Uno header | [UM] silent (only a photo) | [3P] RobotShop forum (2019): power-side order GND, 3V3, GND, 5V, GND, 5V, GND, VIN, RST, IOREF, differs from Uno order but labels are correct | No conflict in text; [3P] fact kept in Needs verification only |
| Compatible boards | [UM] Uno, Mega 2560, Mega ADK, Leonardo, Due, CT-UNO, CIKU | [3P] RobotShop: "Mega 2560 Rev3, Genuino and similar" | [UM] wins; no contradiction |

No disagreement between the Getting Started Guide [UM] and the product page [PP] was found.

## Needs verification
- Total number of screw terminals and the exact terminal-by-terminal order (guide only has a photo) — confirm from the board or design team [DT].
- Whether the Mega 2560 / Mega ADK / Due extra pins (D22–D53, A6–A15) are brought to terminals, or only the Uno-footprint pins — the 74.93 mm x 81.28 mm board size suggests the latter, but it is not stated.
- Screw-terminal current and voltage rating, and accepted wire gauge — not stated.
- Which through-holes in the prototyping area are strip-connected and which are isolated — not stated in text.
- LED function (power indicator vs user LED) and the pin it is on — not stated.
- Whether ISP/ICSP pass-through pads exist — not mentioned.
- Power-side terminal order GND, 3V3, GND, 5V, GND, 5V, GND, VIN, RST, IOREF — [3P] forum report only.
- Whether an IOREF terminal exists (implied by the [3P] report only).
- Weight, operating temperature — not stated.
- The guide is V1.0 from JAN 2015; whether the board has been revised since (the product page says the proto area was moved "to the middle") — confirm the current revision matches the guide [DT].

## Sources
- [UM] "Shield-Screw2 Getting Started Guide", V1.0, JAN 2015, Cytron Technologies Sdn. Bhd. (Google Doc; the product page links it without a label) — https://docs.google.com/document/d/1Z65lZsEQ4x1nS4j9RSolcZ5cMYRg-nfXlnVgrgTl15o/edit
- [PP] Cytron product page (read by coordinator 2026-10-16: product code, price RM31.50, stock 128, warranty 12 months, "upgraded the screw shield with the prototyping area at the middle") — https://my.cytron.io/p-cytron-screw-terminal-shield
- [3P] (cross-check only) RobotShop product page, SKU RB-Cyt-243, Manufacturer # SHIELD-SCREW2 — https://www.robotshop.com/products/cytron-screw-terminal-shield-arduino
- [3P] (cross-check only) RobotShop Community thread "Cytron screw shield", Jan 2019 — https://community.robotshop.com/forum/t/cytron-screw-shield/37525
