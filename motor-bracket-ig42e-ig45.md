# Planetary Motor Bracket (IG42E/IG45) — Verified Reference

| | |
|---|---|
| Product code | `HD-BK-IG4X` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: product page read in full in the browser; Cytron SolidWorks drawing "IG4X Bracket" (rev 1.0, 22-Mar-16, A4 1:1, mm) read in the Drive viewer at full resolution; bracket selection table image read; related encoder tutorial read |
| Primary source | No datasheet. Primary sources = the **Cytron drawing "IG4X Bracket"** ((Cytron document — link not public) linked as "Mechanical Drawing") [PP: drawing] and the **Cytron product page** https://my.cytron.io/cytron-oem/p-planetary-motor-bracket-ig42e-ig45, read 2026-10-21 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP: drawing] = Cytron drawing "IG4X Bracket" (2016). [PP: img] = the shared bracket selection table image `DC Motor Brackets Selection.png`. [PP: tutorial] = "Measuring DC Motor RPM Through Built-in Hall Sensor Encoder" (Idris Zainal Abidin, 04 Jul 2018), shown as related on the page. The IG42E / IG45 motors themselves have no KB file. Sister brackets: `motor-bracket-spg30-spg50.md`.

## What it is
- A light-grey powder-coated alloy-steel L-bracket for Cytron's **IG42E** and **IG45** planetary DC geared motors [PP].
- Selection table: HD-BK-IG4X — **bore size 26.5 mm** — IG42E, IG45 [PP: img].
- Same description as the other Cytron motor brackets ("strong enough to hold your DC motor … regardless of the strong vibration") [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | Alloy steel | [PP] |
| Thickness | Page: 1.5 mm; drawing: **1.60 mm** | [PP][PP: drawing] |
| Finish / colour | Powder coating, light grey | [PP] |
| Fitted motors | IG42E, IG45 | [PP][PP: img] |
| Motor face | 52 mm wide × 49.60 mm high, top R24; **Ø26.50 mm bore**, centre **25.60 mm** above the base; **4 × Ø4.20 mm** holes in a diamond around the bore, top and bottom holes **34.70 mm** apart (so on a ~Ø34.7 mm circle — inferred) | [PP: drawing] |
| Base | **81.60 mm** long × 52 mm wide; **4 × Ø4.20 mm** holes on a **42 × 60 mm** rectangle (5 mm from each side, 10 mm from the free end); **2 slots** 3.50 mm wide × 14.50 mm long, 18.50 mm apart (centres), between the hole pairs; corner R3 | [PP: drawing] |
| Bend | Inside radius R3 | [PP: drawing] |
| Weight | Not stated | — |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | Planetary Geared Motor Bracket (IG42E/IG45) |
| 4 | M4 × 6 mm screw |
| 4 | M4 × 10 mm screw |
| 4 | M4 nut |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Resources: Mechanical Drawing (Drive PDF) [PP].
- Related tutorial: "Measuring DC Motor RPM Through Built-in Hall Sensor Encoder" — uses Maker UNO, MD10C ("Cytron 10Amp DC Motor Driver"), IG42E-24K motor, this bracket and an 11.1 V LiPo [PP: tutorial].
- "You May Also Need": 12V 248RPM 10kgfcm, 12V 1400RPM 2kgfcm and 12V 405RPM 6.5kgfcm planetary geared motors, 10Amp 5V-30V DC Motor Driver (2 ch), 5 Inches Robot Wheel Without Key Hub, Metal Key Hub – 8mm [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface.
- **Motor → bracket:** 4 × M4 × 6 mm screws through the four Ø4.2 face holes into the motor's gearbox (inferred from screw lengths; the page has no assembly image for this bracket).
- **Bracket → chassis:** 4 × M4 × 10 mm screws with M4 nuts through the base holes (inferred); the two slots allow fore-aft adjustment (inferred).

## Rules and gotchas (for code, wiring and tutorials)
- This bracket uses **M4** hardware, unlike the M3 SPG/IG32E brackets [PP].
- Bore is 26.5 mm — it will not fit SPG30 (16 mm) or IG32E (21 mm) motors [PP: img].
- IG42E encoder wire colours (from the tutorial: brown = Hall VCC, green = GND, blue = A, purple = B) belong to the motor, not this bracket; do not reuse them for SPG30E [PP: tutorial].

## Power and electrical limits
- None (mechanical part).

## Software support
- None.

## Compatibility and accessories
- Motors: IG42E, IG45 (no KB files) [PP].
- Wheel/hub for these motors: `robot-wheel-5in.md` with `metal-key-hub.md` (8 mm hub for IG42; 10 mm hub for IG45) [PP of those listings].
- Driver used in the related tutorial: MD10C (`md10c.md`) [PP: tutorial].
- Sister brackets: `motor-bracket-spg30-spg50.md`; HD-BK-IG3X (IG32E bracket, being discontinued — not in the KB).

## Common mistakes / troubleshooting
- **Screws don't fit** → M4 hardware, not M3 [PP].
- **Gearbox doesn't pass the bore** → check the motor is IG42E/IG45 (26.5 mm bore) [PP: img].
- **Face screws bottom out** → use the 6 mm screws on the motor face, 10 mm with nuts on the base (inferred).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Sheet thickness | [PP: drawing] 1.60 mm | [PP] 1.5 mm | Drawing is the more specific source; ±0.1 mm, confirm with calipers |

## Needs verification
- Side-hole spacing on the motor face (only the top–bottom 34.70 mm is dimensioned).
- Which screws go where (no assembly image on this page).
- Position of the base slots from the bend (8.15 mm dimension reference not clear).
- Weight.

## Sources
- [PP: drawing] "IG4X Bracket.PDF" (rev 1.0, 22-Mar-16) (Cytron document — link not public) — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-planetary-motor-bracket-ig42e-ig45 — read 2026-10-21
- [PP: img] `DC Motor Brackets Selection.png` — viewed 2026-10-21
- [PP: tutorial] https://my.cytron.io/tutorial/measuring-dc-motor-rpm-built-hall-sensor-encoder — read 2026-10-21
- KB cross-references: `motor-bracket-spg30-spg50.md`, `robot-wheel-5in.md`, `metal-key-hub.md`, `md10c.md`
