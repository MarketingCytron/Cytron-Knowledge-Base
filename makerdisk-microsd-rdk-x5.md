# MakerDisk microSD Card 64GB with RDK X5 OS — Verified Reference

| Field | Value |
|---|---|
| Product code | `MMR-USD-64-RDK` [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (Description, Features, Packing List; the page has no Resources tab) and its three images (card, RDK X5 board, AI-demo collage) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-makerdisk-microsd-card-64gb-with-rdk-x5-os (read 2026-10-21) [PP]. No datasheet or linked document |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = page images. The page names the board only as "RDK X5 AI Development Board" and does not name its maker. Its main image file name (`mmr-usd-md-64-18sep24`) is the same picture as the 64GB A2 card in `makerdisk-microsd-rpi-os.md`, and the speed figures are identical — so this is inferred to be the 64GB A2 MakerDisk card with a different image.

## What it is
- A 64GB Cytron-brand MakerDisk microSD card preloaded with the **official RDK X5 OS image**, for the **RDK X5 AI Development Board only** ("This microSD card is ONLY compatible with the RDK X5 AI Development Board") [PP].
- "Just insert the card, power up your board, and begin developing with pre-configured tools and drivers" [PP].
- Sibling MakerDisk cards: `makerdisk-microsd-rpi-os.md` (same 64GB A2 figures), `makerdisk-microsd-visionfive2.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Capacity | 64GB; "Actual Capacity: 56.9GB" | [PP] |
| Preloaded OS | RDK X5 OS ("performance-tuned, Linux-based", "official RDK X5 OS image"); version not stated | [PP] |
| Sequential write | > 44MB/s (A1 standard 10MB/s, Raspberry Pi standard 12MB/s) | [PP] |
| Random write | > 2000 IOPS (A1 standard 500, Raspberry Pi standard 500) | [PP] |
| Random read | > 4000 IOPS (A1 standard 1500, Raspberry Pi standard 2000) | [PP] |
| Class | Class 10, A2, U3, V30 | [PP] |
| Durability claims | "Shockproof, waterproof, and X-ray proof design"; "industrial-grade reliability" (no rating or test stated) | [PP] |
| Warranty | 12 months | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Packing list: 1 × MakerDisk microSD Card 64GB with RDK X5 OS [PP].
- No Resources tab, no linked documents or tutorials [PP].
- Images: card photo; RDK X5 board photo; collage of RDK demos (keypoint matching, optical flow, stereo depth, occupancy) [PP: img].

## Interfaces, terminals and pin mapping
- microSD card for the RDK X5's microSD slot [PP]. No other interface.

## Rules and gotchas (for code, wiring and tutorials)
- **RDK X5 only** — it will not boot a Raspberry Pi; use `makerdisk-microsd-rpi-os.md` for Pi [PP].
- "Fully formatted and tested. No image burning or OS installation needed" [PP] — do not re-format it.
- The "industrial-grade", shockproof/waterproof/X-ray-proof wording is marketing with no stated rating or temperature range [PP] — do not quote it as a spec.
- Default login, first-boot steps and OS version are not stated on the page; use the board maker's documentation.

## Power and electrical limits
- Not stated.

## Software support
- RDK X5 OS (version not stated) [PP]. No Cytron tutorials linked.

## Compatibility and accessories
- RDK X5 AI Development Board only [PP]. Whether Cytron sells the board is not shown on this page.
- A USB reader (`cytron-microsd-card-reader.md`) is needed for re-flashing; not offered on this page.

## Common mistakes / troubleshooting
- **Card in another board does not boot:** expected — RDK X5 only [PP].
- **56.9GB shown instead of 64GB:** expected [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Measured 64GB A2 random read | This page: > 4000 IOPS [PP] | Pi 5 Diagnostics of the 64GB A2 MakerDisk: 3973 IOPS [PP: img on `makerdisk-microsd-rpi-os.md`] | Quote "about 4000 IOPS"; figures were measured on a Raspberry Pi 5, not on RDK X5 |

## Needs verification
- RDK X5 OS version/date on current stock; default login (record only that it exists, never the value).
- Maker of the RDK X5 board (not named on the page).
- Whether this is exactly the `MMR-USD-MD-64` A2 card (inferred from image name and identical figures).
- Basis for "shockproof, waterproof, X-ray proof".

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-makerdisk-microsd-card-64gb-with-rdk-x5-os — read 2026-10-21
- [PP: img] `mmr-usd-md-64-18sep24-800x800-1.png`, `716c4f26-ee06-4c7c-a38d-ec628c087963-0.png` (board), `screenshot-2025-06-06-115632.png` (demo collage)
- KB cross-references: `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-visionfive2.md`, `cytron-microsd-card-reader.md`
