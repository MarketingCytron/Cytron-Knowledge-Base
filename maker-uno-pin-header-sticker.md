# Pin Header Sticker for Maker Uno — Verified Reference

| Field | Value |
|---|---|
| Product code | `MAKER-UNO-STICKER` [PP] |
| Family | Cables and small accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron OEM product page (Description only — no Features or Packing List tab) and its layout drawing "Pin Header Sticker Layout.jpg" (35 × 65 mm sheet, four strips with sizes and labels) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-pin-header-sticker-for-maker-uno (read 2026-10-21) [PP] and its layout drawing [PP: drawing] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: drawing] = the layout image on the page (labels and strip sizes, mm). Maker UNO already ships with one set ("1x GPIO labeling sticker" — `maker-uno.md`); this listing sells it separately.

## What it is
- A peel-off sticker sheet of colour-coded pin labels that stick onto the female pin headers of a **Maker UNO** (and other UNO-layout boards), so each header pin is labelled [PP].
- "We customized the pin header sticker for our Maker UNO and we are now selling separately for anyone of you that owning different versions of Uno boards" [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Sheet size | 35 mm × 65 mm, with cutting line | [PP: drawing] |
| Strip 1 (power header) | 8.3 mm × 21 mm: blank, IOREF, RESET, 3.3V, 5V, GND, GND, blank | [PP: drawing] |
| Strip 2 (analog header) | 8.3 mm × 15.6 mm: A0, A1, A2, A3, A4, A5 | [PP: drawing] |
| Strip 3 (upper digital header) | 8.3 mm × 26 mm: SCL, SDA, AREF, GND, 13, 12, 11~, 10~, 9~, 8 | [PP: drawing] |
| Strip 4 (lower digital header) | 8.3 mm × 21 mm: 7, 6~, 5~, 4, 3~, 2, 1 TX, 0 RX | [PP: drawing] |
| Colour code | Yellow = SCL/SDA/AREF, IOREF/RESET; red = 3.3V/5V; black = GND; blue = digital pins; green = A0–A5; pink = 0 RX / 1 TX; "~" marks PWM pins 3, 5, 6, 9, 10, 11 | [PP: drawing] |
| Header text | "PIN LABEL STICKER — Peel off & stick at your MAKER UNO board"; "Peel Here" tab | [PP: drawing] |
| Material | Not stated (a customer review says it is paper with ink printing [3P]) | — |
| Warranty | 12 months | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `MAKER-UNO-STICKER`, RM1.80, 10 or more RM1.62, availability 5718, 53 ratings [PP].
- No packing list or features tab; quantity per pack not stated (one sheet shown in the layout) [PP].
- Images: `PinLabel.JPG` (stickers on a board — not opened) and `Pin Header Sticker Layout.jpg` (read) [PP].

## Interfaces, terminals and pin mapping
- No electrical function. Label order matches the Arduino UNO R3 header layout as used on Maker UNO (`maker-uno.md` — "Arduino UNO R3-standard female headers", SDA/SCL/IOREF broken out) [PP: drawing].
- The power strip has **no VIN label** (two blanks) — Maker UNO has no Vin pin (`maker-uno.md`) [PP: drawing].

## Rules and gotchas (for code, wiring and tutorials)
- **Made for Maker UNO's header layout** [PP]. On an Arduino UNO R3 the power header includes VIN, which this sticker leaves blank — label it by hand if needed (inferred).
- PWM pins are marked "~" on 3, 5, 6, 9, 10, 11 [PP: drawing] — matches the ATmega328P UNO PWM set (`maker-uno.md`).
- Stick each strip on the plastic header body beside the matching pins; align GND on the upper digital strip with the GND next to AREF [PP: drawing].

## Power and electrical limits
- None.

## Software support
- None.

## Compatibility and accessories
- Maker UNO (`maker-uno.md`) — one set already in each Maker UNO box [PP of maker-uno].
- Other UNO-layout boards ("different versions of Uno boards") [PP]: e.g. `cytron-uno.md`, `maker-uno-plus.md` — fit not confirmed per board.

## Common mistakes / troubleshooting
- **Labels fade:** a reviewer reports ink-printed paper that can fade [3P]; reorder rather than rely on worn labels.
- **Strip one pin off:** start from the header end shown in the layout (SCL at the top of the upper digital strip, 0 RX at the end of the lower strip) [PP: drawing].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| — | [PP] text | [PP: drawing] | No conflict found |

## Needs verification
- Material (paper vs vinyl) and number of sheets per pack.
- Fit on Maker UNO X / Maker UNO RP2040 headers (not stated).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-pin-header-sticker-for-maker-uno — read 2026-10-21
- [PP: drawing] `MAKER-UNO-STICKER/Pin Header Sticker Layout.jpg` — read 2026-10-21
- [3P] Customer review (28 Dec 2024) on the product page
- KB cross-references: `maker-uno.md`, `maker-uno-plus.md`, `cytron-uno.md`
