# Milesight RCT-RJ11 Split-core Current Transformers for CTH01 (100 A / 300 A / 1000 A) — Verified Reference

| | |
|---|---|
| Product code | Cytron parent code `V-LR-RCT`. Options: 100 A `LR-RCT100` (MPN `RCT-100`), 300 A `LR-RCT300` (MPN `RCT-300`), 1000 A `LR-RCT1000` (MPN `RCT-1000`) [PP]. Milesight series name "RCT-RJ11" [PP] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (3 options: code, MPN, price, stock, spec) read; CT options table in the CTH01 datasheet and the CT sections of the CTH01 user guide V1.0 read. No stand-alone Milesight datasheet for the CTs was found |
| Primary source | Milesight *CTH01 Datasheet*, "Current Transformer Options" table, https://resource.milesight.com/milesight/iot/document/cth01-datasheet-en.pdf (read 2026-10-21) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = "Current Transformer Options" table of the Milesight CTH01 datasheet (the CTs have no datasheet of their own on the Cytron page). [UM] = Milesight CTH01 User Guide V1.0, 20 Mar 2026 (CT installation steps). [PP] = Cytron product page. The DS table's 1000 A column is partly garbled in the PDF text layer (see *Needs verification*).

## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Range | 0 – 100 A / 0 – 300 A / 0 – 1000 A | [DS][PP] |
| Measuring accuracy | Class 0.5 (the DS table row reads "Class: 0.5 ±2 %") | [DS][PP] |
| Wire hole | Ø16 mm (100 A) / Ø24 mm (300 A) / Ø51 mm (1000 A; [PP] Ø50 mm) | [DS] |
| Dimensions | 35.5 × 30.8 × 45.6 mm (100 A) / 56.5 × 36.5 × 68.5 mm (300 A) / 1000 A: DS text garbled, [PP] 75.5 × 55.5 × 110.5 mm | [DS][PP] |
| Weight | 100 g / 195 g / 835 g ([PP] 800 g for 1000 A) | [DS] |
| Operating temperature | -40 ~ 55 °C (all) | [DS] |
| Insulation voltage | 3 kVac rms (1 mA / 1 min) (all) | [DS] |
| Flame retardant | UL94 V0 | [DS] |
| Connection | RJ11 plug | [PP][UM] |
| Installation | Suspended on the conductor | [DS] |
Milesight also lists a 0–500 A split-core CT (Ø36.6 mm, 287 g) and a 0–4000 A Rogowski coil (Ø150 mm, 115.1 g); Cytron does not sell these on this page [DS].
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Split-core Current Transformers for CTH01 (100A/300A/1000A)"; parent code `V-LR-RCT`; warranty 12 months; RM215.25 – RM861.00; availability 24; ADD TO CART [PP].
- Options: 100 A `LR-RCT100` / `RCT-100` RM215.25 (15 in stock); 300 A `LR-RCT300` / `RCT-300` RM258.30 (6); 1000 A `LR-RCT1000` / `RCT-1000` RM861.00 (3). Each option also has its own URL (…-range-0-100a, …-range-0-300a, …-range0-1000a) [PP].
- Description: "Milesight RCT-RJ11 Series", for the CTH01; non-invasive; plug-and-play RJ11 "click" into any of the 12 channels; UL94 V0; -40 to 55 °C [PP].
- Features claim "Snap-on installation allows for deployment on live circuits with zero downtime" (see *Conflicts*) [PP].
- Packing list: the CT of the selected range (one unit per option, inferred) [PP].
- No datasheet or user-guide link on this page [PP].

## Interfaces, terminals and pin mapping
- One RJ11 plug per CT, into a numbered CTH01 current channel (Ch1–Ch12) [UM][PP]. RJ11 pin assignment is not published [DS].
- Arrow on the clamp body: must point to the **load side** (direction of current flow) [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **CTH01 only.** These CTs are for the CTH01 hub's RJ11 channels [PP]. They are not the clamps of the self-powered CT10x/CT3xx sensors (`milesight-ct10x.md`).
- **Install per the CTH01 user guide:** open the clamp, centre the conductor, arrow to the load, close until it clicks, push the RJ11 plug fully into the numbered port, label the cable [UM].
- **One conductor per CT.** Put each CT around a single phase conductor (phase/neutral rules as for any CT; the CTH01 guide asks for the conductor to be centred) [UM].
- **Set the matching range in ToolBox** for that channel (100 A / 300 A / 1000 A); a wrong range gives wrong current (inferred from the per-channel range setting) [UM].
- **Phase position matters:** a CT on L1 must be in the 1st channel of a group, L2 the 2nd, L3 the 3rd [UM].
- **Mixing:** different CT ratings can be mixed in one group; Rogowski coils cannot be mixed with CTs in a group [UM].
- **Reversed CT** reads negative; fix with Current Direction in ToolBox [UM].
- **Safety:** CTH01 installation is for qualified electricians with the board de-energized and locked out [UM]. No Milesight statement about opening the CT circuit (unplugging RJ11) under load was found; do not unplug a CT while its clamp is on a loaded conductor (general CT practice, inferred — see *Needs verification*).

## Power and electrical limits
- Rated range 100 / 300 / 1000 A; insulation 3 kVac rms (1 mA / 1 min); -40 ~ 55 °C [DS].
- No working-voltage or measurement-category rating is stated for the CTs themselves (the CTH01 is CAT III) [DS].

## Software support
- None on the CT. Range, direction and circuit type are set per channel on the CTH01 (ToolBox app or downlink: range code 0001 = 100 A, 0002 = 300 A, 0003 = 500 A, 0004 = 1000 A, 0005 = 4000 A) [UM].

## Compatibility and accessories
- Hub: `milesight-cth01.md` (12 RJ11 channels; supports 100 / 300 / 500 / 1000 A CTs and 4000 A Rogowski coils) [DS].
- Cytron lists the 100 A and 300 A options as "Accessories you may need" on the CTH01 page [PP].

## Common mistakes / troubleshooting
- **Negative current:** arrow faces the source; reverse in ToolBox or re-fit [UM].
- **Wrong power figures:** CT in the wrong channel position for its voltage phase [UM].
- **Clamp not locked:** close until it clicks [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 1000 A wire hole | [PP] Ø50 mm | [DS] Ø51 mm | [DS] wins: Ø51 mm |
| 1000 A weight | [PP] 800 g | [DS] 835 g | [DS] wins: 835 g |
| 1000 A dimensions | [PP] 75.5 × 55.5 × 110.5 mm | [DS] garbled text ("9631 × 595 × 119 mm") | Unresolved: DS figure not legible in text; see *Needs verification* |
| Installation on live circuits | [PP] "deployment on live circuits with zero downtime" | [UM] CTH01 installation with breaker powered off, lock out all supplies | [UM] wins for the CTH01 installation. Safety-critical |

## Needs verification
- 1000 A CT dimensions (DS text layer garbled; Cytron gives 75.5 × 55.5 × 110.5 mm).
- Meaning of "±2 %" in the DS accuracy row (may belong to the Rogowski coil column).
- Whether a CT may be unplugged from the hub while clamped on a loaded conductor (no "do not open secondary" statement found); CT secondary type (current or voltage output) is not published.
- RJ11 pin assignment and cable length (not stated).

## Sources
- [DS] CTH01 Datasheet, Current Transformer Options: https://resource.milesight.com/milesight/iot/document/cth01-datasheet-en.pdf (read 2026-10-21).
- [UM] CTH01 User Guide V1.0 (20 Mar 2026): https://resource.milesight.com/milesight/iot/document/cth01-user-guide-en.pdf
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-split-core-current-transformers-for-cth01-100a300a1000a (read 2026-10-21).
