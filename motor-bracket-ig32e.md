# Planetary Geared Motor Bracket (IG32E) — Verified Reference

| | |
|---|---|
| Product code | `HD-BK-IG3X` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: product page read in full in the browser (no drawing or resource is linked); gallery photos (bracket with screws; bracket on an IG32E motor) and the shared bracket selection table viewed |
| Primary source | No datasheet or drawing exists on the page. Primary source = **Cytron product page** https://my.cytron.io/cytron-oem/p-planetary-geared-motor-bracket-ig32e, read 2026-10-21 [PP], plus its selection-table image [PP: img] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text. [PP: img] = `DC Motor Brackets Selection.png` (shared by all three Cytron motor brackets) and the gallery photos `planetary-geared-motor-bracket-ig32e-27753` and `Planetary motor bracket HD-BK-IG3X` (appearance only, no dimensions). The IG32E motor has no KB file. Sister brackets: `motor-bracket-spg30-spg50.md`, `motor-bracket-ig42e-ig45.md`.

## What it is
- A light-grey powder-coated **1.5 mm alloy-steel** L-bracket for Cytron's **IG32E** 32 mm planetary DC geared motor [PP].
- Selection table: HD-BK-IG3X — **bore size 21 mm** — IG32E [PP: img].
- Same description text as the other Cytron motor brackets [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Material | Alloy steel | [PP] |
| Thickness | 1.5 mm | [PP] |
| Finish / colour | Powder coating, light grey | [PP] |
| Fitted motor | IG32E | [PP][PP: img] |
| Bore | 21 mm | [PP: img] |
| Motor-face holes | 4 holes around the bore (photo; size and spacing not stated) | [PP: img] |
| Base holes | Two rows of holes along the base (photo shows about 8; size and spacing not stated) | [PP: img] |
| Overall dimensions | Not stated | — |
| Weight | Not stated | — |
| Warranty | 12 months | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 | Planetary Geared Motor Bracket (IG32E) |
| 4 | M3 × 4 mm screw |
| 4 | M3 × 10 mm screw |
| 4 | M3 nut |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- No Resources section and no drawing [PP].
- "You May Also Need": Metal Key Hub – 6mm, 12V 60RPM 6.7kgfcm 32mm Planetary DC Geared Motor, Planetary Motor Bracket (IG42E/IG45) [PP].

## Interfaces, terminals and pin mapping
- Mechanical part; no electrical interface.
- **Motor → bracket:** 4 × M3 × 4 mm screws through the four face holes (inferred from the screw count and the photo of the bracket on an IG32E with four face screws) [PP: img].
- **Bracket → chassis:** 4 × M3 × 10 mm screws with M3 nuts (inferred, same pattern as `HD-BK-SPG`).

## Rules and gotchas (for code, wiring and tutorials)
- For IG32E only; SPG30 motors need HD-BK-SPG (16 mm bore), IG42E/IG45 need HD-BK-IG4X (26.5 mm) [PP: img].
- Uses M3 hardware [PP].
- No hole dimensions are published — measure the part before designing a chassis.

## Power and electrical limits
- None (mechanical part).

## Software support
- None.

## Compatibility and accessories
- Motor: IG32E (e.g. "12V 60RPM 6.7kgfcm 32mm Planetary DC Geared Motor", no KB file) [PP].
- Shaft hub: Metal Key Hub – 6mm `CO-SPG` (its page lists IG32 as a fit) (`metal-key-hub.md`); 6 mm mecanum hub (`mecanum-key-hub-6mm.md`, lists IG32).
- Sister brackets: `motor-bracket-spg30-spg50.md`, `motor-bracket-ig42e-ig45.md`.

## Common mistakes / troubleshooting
- **Bracket doesn't fit the motor** → check it is an IG32E (21 mm bore) [PP: img].
- **Long screws into the gearbox** → use the 4 mm screws on the motor face (inferred).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | [PP] text | [PP: img] selection table | No conflict found |

## Needs verification
- **All hole sizes and positions** (face and base), overall size and bore-centre height — no drawing is linked.
- Weight.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-planetary-geared-motor-bracket-ig32e — read 2026-10-21
- [PP: img] `DC Motor Brackets Selection.png`; gallery photos — viewed 2026-10-21
- KB cross-references: `motor-bracket-spg30-spg50.md`, `motor-bracket-ig42e-ig45.md`, `metal-key-hub.md`, `mecanum-key-hub-6mm.md`
