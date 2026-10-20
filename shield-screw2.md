# Cytron Screw Terminal Shield — Verified Reference

| Field | Value |
|---|---|
| Product code | SHIELD-SCREW2 [UM][PP] |
| Family | Arduino shields and breakout boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: Cytron product photos (top, angle, bottom) read — terminal count and full terminal order confirmed; product page text re-read (no new specs) |
| Primary source | "Shield-Screw2 Getting Started Guide" (Cytron Screw Terminal Shield, SHIELD-SCREW2), V1.0, JAN 2015, Cytron Technologies Sdn. Bhd. — a Getting Started Guide / user manual [UM]. No separate Cytron datasheet was found. |

Tag notes: [PP: photo] = Cytron's own product photos on my.cytron.io (shield-screw2-a/b/c, top, angled and bottom views), read visually 2026-10-19 — silkscreen labels only, not electrical specs.

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
| Terminal count | 32 screw terminals (16 per side, in 2-way blocks) | [PP: photo] |
| Board silkscreen | "SHIELD-SCREW" (top), "SCREW PROTO SHIELD" + cytron.com.my (bottom) | [PP: photo] |
| Terminal current/voltage rating, wire gauge, weight, operating temperature | Not stated | [UM][PP] |
| ISP/ICSP pads | None visible in the product photos; not mentioned in the guide | [PP: photo][UM] |

## Interfaces, terminals and pin mapping
- **Screw terminals:** 3.5 mm pitch, extending "all pins of the Arduino" [UM]. The guide gives no list; the terminal labels below are read from Cytron's product photos [PP: photo].
- **Power / analog side (16 terminals, from the end nearest the board edge with IOREF):** IOREF, RST, VIN, GND, 5V, GND, 5V, GND, 3V3, GND, A0, A1, A2, A3, A4, A5 [PP: photo]. Read from A0 upward this is GND, 3V3, GND, 5V, GND, 5V, GND, VIN, RST, IOREF — the same order a RobotShop forum post reported [3P], now confirmed by Cytron's photo.
- **Digital side (16 terminals):** AREF, GND, D13, D12, D11, D10, D9, D8, D7, D6, D5, D4, D3, D2, D1, D0 [PP: photo].
- **Uno R3 footprint only:** terminals exist only for the Uno R3 header pins; the Mega/Due extra pins (D22–D53, A6–A15) have no terminals [PP: photo]. The R3 SCL and SDA pins (beside AREF) are broken out as solder holes next to the header, not to screw terminals [PP: photo].
- **Header breakout holes:** every header pin has a labelled solder hole beside the stacking header (IOREF, RST, 3V3, 5V, GND, GND, VIN, A0–A5; SCL, SDA, AREF, GND, D13–D8; D7–D0) [PP: photo].
- **Stackable headers:** the shield is stackable, so another shield can go on top and the Arduino headers remain available [UM].
- **Prototyping area:** 0.1" (2.54 mm) grid through-holes, some connected in strips ("connected") and some isolated ("unconnected"), placed in the middle of the board [UM][PP]. Which holes are strip-connected is not stated in text.
- **Busses:** more than one 5V bus and more than one GND bus ("a couple") [UM]; the photos show a 5V row and a GND row along the top and along the bottom edge of the prototyping area [PP: photo].
- **Reset button:** on the shield, because a stacked shield covers the Arduino's own reset button [UM]. Its wiring (to RESET) is implied by the name, not stated.
- **LED:** one LED [UM], a small SMD part beside the reset button near the 5V bus label, with no silkscreen name [PP: photo]. Whether it is a power LED or a user LED, and which pin it is on, is not stated.
- **ISP / ICSP pads:** not mentioned anywhere in the guide [UM]. Do not claim them.

## Rules and gotchas (for code, wiring and tutorials)
- No code is needed for the shield itself: it only re-routes Arduino pins to screw terminals [UM]. Pin numbers in a sketch are the Arduino's own pin numbers.
- Always **read the silkscreen label at each terminal**, not the position: the power-side terminal order (IOREF, RST, VIN, GND, 5V, GND, 5V, GND, 3V3, GND) differs from the Arduino Uno header order [PP: photo], although each terminal is labelled. Tutorials should show wires going to a labelled terminal (e.g. "the terminal marked 5V"), never "the third terminal from the left".
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
- "The GND terminal is where my Uno has VIN" → the shield re-orders the power-side terminals; wire by the label printed on the shield, not by Uno header position [PP: photo].
- On a Mega or Due, pins above D13 and A5 have no screw terminals — use the board's own headers for them [PP: photo].
- Arduino does not reset → press the shield's reset button, which is wired for exactly this use [UM].
- Terminal does not grip wire → terminal screw not opened enough before inserting the wire; 3.5 mm pitch terminals take thin wire only (gauge not stated).
- Expecting an ISP header → none is documented [UM].
- Board overhangs the Arduino → expected; the shield is 74.93 mm x 81.28 mm [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Terminal order vs Arduino Uno header | [UM] silent (only a photo) | [3P] RobotShop forum (2019) power-side order | **Resolved** — Cytron product photo shows the same order [PP: photo] |
| Compatible boards | [UM] Uno, Mega 2560, Mega ADK, Leonardo, Due, CT-UNO, CIKU | [3P] RobotShop: "Mega 2560 Rev3, Genuino and similar" | [UM] wins; no contradiction |

No disagreement between the Getting Started Guide [UM] and the product page [PP] was found.

## Needs verification
- Screw-terminal current and voltage rating, and accepted wire gauge — not stated.
- Which through-holes in the prototyping area are strip-connected and which are isolated — not stated in text.
- LED function (power indicator vs user LED) and the pin it is on — not stated.
- Weight, operating temperature — not stated.
- The guide is V1.0 from JAN 2015; whether the board has been revised since (the product page says the proto area was moved "to the middle") — confirm the current revision matches the guide [DT].

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Arduino + 2A Motor Shield + Encoder Motor](https://my.cytron.io/tutorial/arduino-2a-motor-shield-encoder-motor) — Tutorial, Beginner, 2016 [PP: tutorial]

## Sources
- [UM] "Shield-Screw2 Getting Started Guide", V1.0, JAN 2015, Cytron Technologies Sdn. Bhd. (Google Doc; the product page links it without a label) — https://docs.google.com/document/d/1Z65lZsEQ4x1nS4j9RSolcZ5cMYRg-nfXlnVgrgTl15o/edit
- [PP: photo] Cytron product photos — https://static.cytron.io/image/catalog/products/SHIELD-SCREW2/shield-screw2-a.png , -b.png (top), -c.png (bottom)
- [PP] Cytron product page (re-read 2026-10-19: 127 in stock, RM31.50, no new specs; earlier read 2026-10-16: product code, price RM31.50, stock 128, warranty 12 months, "upgraded the screw shield with the prototyping area at the middle") — https://my.cytron.io/p-cytron-screw-terminal-shield
- [3P] (cross-check only) RobotShop product page, SKU RB-Cyt-243, Manufacturer # SHIELD-SCREW2 — https://www.robotshop.com/products/cytron-screw-terminal-shield-arduino
- [3P] (cross-check only) RobotShop Community thread "Cytron screw shield", Jan 2019 — https://community.robotshop.com/forum/t/cytron-screw-shield/37525
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
