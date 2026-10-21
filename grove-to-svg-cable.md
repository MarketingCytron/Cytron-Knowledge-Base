# Grove to SVG Cable - 200mm length — Verified Reference

| Field | Value |
|---|---|
| Product code | `WR-GRVSVG-210` [PP] |
| Family | Cables and small accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (Description, Features incl. pin definition, Packing List) and its six photos (cable ends, Octopus button module, REKA:BIT with three modules) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-grove-to-svg-cable-200mm-length (read 2026-10-21) [PP]. No datasheet or drawing |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = page photos. The Octopus modules are made by ElecFreaks (the page writes "Elecfreak's Octopus modules"). Code suffix "-210" is Cytron's; the page states ~200 mm.

## What it is
- A ~200 mm 3-wire "chimera" cable with an **SVG (Signal-Voltage-Ground) 3-pin socket** on one end and a **Grove 4-pin plug** on the other [PP][PP: img].
- Lets ElecFreaks **Octopus** modules (SVG 3-pin) plug into the **Grove ports** of Cytron micro:bit boards such as **EDU:BIT** and **REKA:BIT** [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Length | ~200 mm | [PP] |
| End A | SVG 3-pin socket (black housing in photos) | [PP][PP: img] |
| End B | Grove 4-pin plug (white housing); only 3 wires fitted | [PP][PP: img] |
| Pin definition | S (Yellow) = Signal; V (Red) = VCC; G (Black) = GND | [PP] |
| Power wiring | Red and black go to the Grove connector's power and ground | [PP] |
| Signal wiring | S goes to the Grove port's **"side GPIO"** — e.g. on REKA:BIT's left-most Grove port the Octopus signal lands on **P0**, so the program uses P0, not P1 | [PP] |
| Price | RM4.00; 20 or more RM3.60 | [PP] |
| Warranty | Not shown in the page header | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `WR-GRVSVG-210`, availability 49, 1 rating [PP].
- Packing list: 1 × Grove to SVG Cable - 200mm length [PP]. "Octopus Digital Push Button Brick is NOT included" [PP].
- Photos: three Octopus modules on REKA:BIT Grove ports; close-up of the 3-wire Grove end; Octopus push-button brick [PP: img].

## Interfaces, terminals and pin mapping
| SVG pin | Wire | Grove side | Src |
|---|---|---|---|
| S | Yellow | Grove signal pin on the port's first GPIO (e.g. P0 of a P0/P1 port) | [PP] |
| V | Red | Grove VCC | [PP] |
| G | Black | Grove GND | [PP] |
| — | none | Grove second signal pin (e.g. P1) not connected | [PP: img] (3 wires only) |
- Matches the Grove yellow-wire position on REKA:BIT (Grove P0:P1 = P0 yellow + P1 white — `reka-bit.md`).

## Rules and gotchas (for code, wiring and tutorials)
- **Program the yellow-wire pin.** On a REKA:BIT P0:P1 port the module is on **P0, not P1** [PP]. Same rule on other ports: use the first pin of the pair (inferred from "side GPIO").
- **Grove power on REKA:BIT / EDU:BIT is 3.3 V** (`reka-bit.md`, `edu-bit.md`) — Octopus modules then run at 3.3 V; check each module's voltage range (not stated by Cytron).
- **Digital/analog modules only:** one signal wire means I2C (2-wire) modules cannot use this cable (inferred).

## Power and electrical limits
- Not stated. The host Grove port's rail applies (REKA:BIT: max 300 mA total +3V3 on Grove ports — `reka-bit.md`).

## Software support
- None. Program the pin in MakeCode with the board's extension (REKA:BIT / EDU:BIT KB files).

## Compatibility and accessories
- Hosts: EDU:BIT (`edu-bit.md`), REKA:BIT (`reka-bit.md`) and other Grove-port boards [PP].
- Modules: ElecFreaks Octopus (SVG 3-pin) modules, e.g. Octopus Digital Push Button Brick (not included) [PP].

## Common mistakes / troubleshooting
- **Module does nothing in code:** reading P1 instead of P0 — the signal is on the port's first GPIO [PP].
- **Grove end feels loose / one slot empty:** normal — the Grove housing has 3 of 4 positions fitted [PP: img].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Length | Title and features: 200 mm [PP] | Code suffix "-210" [PP] | Use ~200 mm (page text); the suffix is not a stated length |

## Needs verification
- SVG-end pitch (2.54 mm by convention) and housing part.
- Octopus module voltage range at 3.3 V Grove supply.
- Warranty (not shown in the page header).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-grove-to-svg-cable-200mm-length — read 2026-10-21
- [PP: img] `WR-GRVSVG-210 (5).jpg`, `(8).JPG`, `(12).jpg`, `(13).jpg`, `_f.jpg`, `_g.jpg`
- KB cross-references: `reka-bit.md`, `edu-bit.md`
