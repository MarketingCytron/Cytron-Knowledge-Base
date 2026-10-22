# DC Geared Motor Bracket (SPG30/SPG50) — Verified Reference

| | |
|---|---|
| Product code | `HD-BK-SPG` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: product page read in full in the browser; Cytron SolidWorks drawing "HD-BK-SPG" (title "HD-BK-SPG v2", rev 1.0, 10/4/2023) read via the Drive connector; page images read: assembly instruction (screw use) and the bracket selection table |
| Primary source | No datasheet. Primary sources = the **Cytron mechanical drawing "HD-BK-SPG"** ((Cytron document — link not public) linked as "Mechanical Drawing" / "Technical Drawing") [PP: drawing] and the **Cytron product page** https://my.cytron.io/cytron-oem/p-dc-geared-motor-bracket-spg30-spg50, read 2026-10-21 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP: drawing] = Cytron drawing HD-BK-SPG (A4, 1:1, mm; material alloy steel, powder coating). [PP: img] = page images `SPG-Motor-Bracket-Instruction-2.jpg` (exploded assembly with screw sizes) and `DC Motor Brackets Selection.png` (bracket-to-motor table shared by all three Cytron motor brackets). Page and drawing agree. Sister brackets: `motor-bracket-ig42e-ig45.md`.

## What it is
- A light-grey powder-coated **1.5 mm alloy-steel L-bracket** that holds a Ø37 mm SPG-series DC geared motor and bolts to a chassis [PP].
- "Fitted Motor: SPG30, SPG30E, SPG50" [PP]; the selection table gives **bore size 16 mm** for HD-BK-SPG [PP: img].
- "Strong enough to hold your DC motor at its position regardless of the strong vibration" [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | Alloy steel | [PP][PP: drawing] |
| Thickness | 1.5 mm (drawing: 1.50) | [PP][PP: drawing] |
| Finish / colour | Powder coating, light grey | [PP] |
| Fitted motors | SPG30, SPG30E, SPG50 | [PP][PP: img] |
| Overall size | **40 mm wide**; motor face 42.069 mm high; base 41.069 mm deep | [PP: drawing] |
| Motor face | Slot **16 mm wide**, 14 mm between its end-radius centres (R8 ends), running up the face, for the Ø12 mm gearbox boss; top edge R20; **2 × Ø3.30 mm holes** either side of the slot at the slot's mid-height, **31 mm apart** (they line up with the base-hole rows, 4.5 mm in from each side — spacing read from that alignment, not dimensioned on the face view) | [PP: drawing] |
| Base (chassis) holes | **8 × Ø3.30 mm** in two rows of four: rows **31 mm** apart (4.50 mm from each side edge), **10 mm** pitch (30 mm span), first hole 6.069 mm from the bend face, last 5 mm from the free edge | [PP: drawing] |
| Motor-axis height | Face-hole line / slot centre **22.069 mm** from the bend; the gearbox centre therefore sits ~22 mm above the base and the offset shaft at ~15 or ~29 mm (slot ends ±7 mm — inferred) | [PP: drawing] |
| Weight | Not stated | — |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | DC Geared Motor Bracket (SPG30/SPG50) |
| 2 | M3 × 4 mm screw |
| 4 | M3 × 10 mm screw |
| 4 | M3 nut |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Bracket selection table: HD-BK-SPG — bore 16 mm — SPG30, SPG30E, SPG50; HD-BK-IG3X — 21 mm — IG32E; HD-BK-IG4X — 26.5 mm — IG42E, IG45 [PP: img].
- Resources: Mechanical Drawing; Attachments: Technical Drawing (same Drive PDF) [PP].
- Related tutorial: "Getting Started With MDD3A/MAKER DRIVE Using Arduino" (Idris Zainal Abidin, 07 Oct 2025) — uses this bracket with 2 × SPG30HP-30K [PP][PP: tutorial].
- "You May Also Need": Metal Key Hub – 6mm, SPG30E motors, 12V 37MM DC Geared Motor, Small Robot Rubber Wheel (68x27mm), 10Amp 5V-30V DC Motor Driver, Hex Brass Mini Wheel Coupling, 12V 380RPM high power motor [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface.
- **Motor → bracket:** 2 × **M3 × 4 mm** screws through the two face holes into the gearbox's M3 holes (exploded image) [PP: img]. The face holes are 31 mm apart side by side, matching the two holes on the horizontal centreline of the SPG30 / SPG30HP **6 × M3 on Ø31 mm** pattern; the slot's ±7 mm end centres match the motors' **7 mm shaft offset**, so the shaft can sit above or below the gearbox centre (`dc-geared-motor-37mm-12v.md`, `high-power-dc-geared-motor-12v.md`) — inferred from the drawings.
- **Bracket → chassis:** 4 × **M3 × 10 mm** screws with M3 nuts through the base holes [PP: img]; 8 holes are available, 4 screws are supplied [PP][PP: drawing].

## Rules and gotchas (for code, wiring and tutorials)
- **Use the 4 mm screws on the motor face.** SPG30HP gearbox holes are ≤ 3.5 mm deep [DS of `high-power-dc-geared-motor-12v.md`]; a 10 mm screw there would hit the gears (inferred).
- Only **2 of the 6** gearbox holes are used [PP: img] — fine for normal loads; no extra face holes exist [PP: drawing].
- The 16 mm slot clears the Ø12 mm shaft boss [PP: drawing][DS of motor files]; mount the motor shaft-up or shaft-down — the axle height changes by 14 mm between the two (inferred).
- Not for IG32E or IG42E/IG45 planetary motors — use HD-BK-IG3X / HD-BK-IG4X [PP: img].

## Power and electrical limits
- None (mechanical part).

## Software support
- None.

## Compatibility and accessories
- Motors: SPG30 / SPG30E (`dc-geared-motor-37mm-12v.md`), SPG30HP-30K / -10K (`high-power-dc-geared-motor-12v.md`, page offers this bracket), SPG50 (no KB file) [PP].
- Shaft hubs for these motors: `metal-key-hub.md` (6 mm), `mecanum-key-hub-6mm.md`.
- Sister brackets: `motor-bracket-ig42e-ig45.md`; HD-BK-IG3X (IG32E bracket, being discontinued — not in the KB).

## Common mistakes / troubleshooting
- **Motor face screws too long** → use the M3 × 4 mm screws [PP][PP: img].
- **Bracket holes don't line up with the gearbox** → rotate the motor so the shaft is straight above or below the gearbox centre; the two horizontal M3 holes (31 mm apart) then meet the face holes (inferred).
- **Wrong bracket bought** → check the selection table: 16 mm bore for SPG, 21 mm for IG32E, 26.5 mm for IG42E/IG45 [PP: img].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | [PP] page text | [PP: drawing] drawing | No conflict; the drawing adds sizes and hole positions |

## Needs verification
- Exact shaft-axis height above the base (22.069 mm is measured to the bend; whether to the inner or outer face is not marked). The face-hole spacing (31 mm) is read from alignment, not a dimension.
- Weight.
- SPG50 hole pattern (no SPG50 product file in the KB).

## Sources
- [PP: drawing] "HD-BK-SPG Drawing.pdf" (title HD-BK-SPG v2, rev 1.0, 10/4/2023) (Cytron document — link not public) — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-dc-geared-motor-bracket-spg30-spg50 — read 2026-10-21
- [PP: img] `SPG-Motor-Bracket-Instruction-2.jpg`, `DC Motor Brackets Selection.png` — viewed 2026-10-21
- [PP: tutorial] https://my.cytron.io/tutorial/getting-started-mdd3a-makerdrive-motor-driver-using-arduino — read 2026-10-21 (component list)
- KB cross-references: `dc-geared-motor-37mm-12v.md`, `high-power-dc-geared-motor-12v.md`, `metal-key-hub.md`, `mecanum-key-hub-6mm.md`, `motor-bracket-ig42e-ig45.md`, `mdd3a.md`
