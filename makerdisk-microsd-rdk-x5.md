# MakerDisk microSD Card 64GB with RDK X5 OS — Verified Reference

| Field | Value |
|---|---|
| Product code | `MMR-USD-64-RDK` [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-22 |
| Reviewed | 2026-10-22 — Medium-low follow-up: Cytron internal "RDK X5 Testing" sheet (Jun 2025) and "RDK X5 Quick Start Guide" (Jul 2025) read from Drive; D-Robotics "Burn SD card" docs page read. Board maker, OS family and flashing notes added. Earlier: 2026-10-21 new product added from the full Cytron OEM product page and its three images |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-makerdisk-microsd-card-64gb-with-rdk-x5-os (read 2026-10-21) [PP]. No datasheet or linked document. Supporting: Cytron internal RDK X5 Testing sheet + Quick Start Guide ; D-Robotics developer docs [VEN] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
- A 64GB Cytron-brand MakerDisk microSD card preloaded with the **official RDK X5 OS image**, for the **RDK X5 AI Development Board only** ("This microSD card is ONLY compatible with the RDK X5 AI Development Board") [PP].
- "Just insert the card, power up your board, and begin developing with pre-configured tools and drivers" [PP].
- Sibling MakerDisk cards: `makerdisk-microsd-rpi-os.md` (same 64GB A2 figures), `makerdisk-microsd-visionfive2.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Capacity | 64GB; "Actual Capacity: 56.9GB" | [PP] |
| Preloaded OS | RDK X5 OS ("performance-tuned, Linux-based", "official RDK X5 OS image"); version not stated | [PP] |
| OS family | D-Robotics RDK OS — Ubuntu 22.04 based, desktop and server images; RDK X5 images published under archive.d-robotics.cc/downloads/os_images/rdk_x5/ | [VEN] |
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
- Default login, first-boot steps and OS version are not stated on the page; use the D-Robotics documentation (the default login is in the D-Robotics docs — never copied into the KB).
- **Re-flashing:** download the RDK X5 image from D-Robotics and flash with RDK Studio, Rufus or Raspberry Pi Imager [VEN]. Cytron's testing saw balenaEtcher fail on 3.2.3 . D-Robotics asks for a card of at least 16 GB [VEN].

## Power and electrical limits
- Not stated.

## Software support
- RDK X5 OS (version not stated) [PP] — D-Robotics RDK OS, Ubuntu 22.04 based [VEN]. ROS 2 Humble installs on it (Cytron Quick Start Guide) . No Cytron tutorials linked on the page.

## Compatibility and accessories
- RDK X5 AI Development Board (D-Robotics) only [PP][VEN]. Whether Cytron sells the board is not shown on this page.
- A USB reader (`cytron-microsd-card-reader.md`) is needed for re-flashing; not offered on this page.

## Common mistakes / troubleshooting
- **Card in another board does not boot:** expected — RDK X5 only [PP].
- **56.9GB shown instead of 64GB:** expected [PP].
- **Re-flash fails with balenaEtcher:** use Raspberry Pi Imager, RDK Studio or Rufus [VEN].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Measured 64GB A2 random read | This page: > 4000 IOPS [PP] | Pi 5 Diagnostics of the 64GB A2 MakerDisk: 3973 IOPS [PP: img on `makerdisk-microsd-rpi-os.md`] | Quote "about 4000 IOPS"; figures were measured on a Raspberry Pi 5, not on RDK X5 |

## Needs verification
- RDK X5 OS version/date written to current stock (Cytron tested 3.1.1 and 3.2.3 in Jun 2025; D-Robotics has since published newer 3.x images) — ask the product team which version is on the card.
- Whether this is exactly the `MMR-USD-MD-64` A2 card (inferred from image name and identical figures).
- Basis for "shockproof, waterproof, X-ray proof".

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-makerdisk-microsd-card-64gb-with-rdk-x5-os — read 2026-10-21
- [PP: img] `mmr-usd-md-64-18sep24-800x800-1.png`, `716c4f26-ee06-4c7c-a38d-ec628c087963-0.png` (board), `screenshot-2025-06-06-115632.png` (demo collage)
- [VEN] https://developer.d-robotics.cc/rdk_x_doc/en/Quick_start/system-burn/burn-sd-card — read 2026-10-22
- KB cross-references: `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-visionfive2.md`, `cytron-microsd-card-reader.md`
