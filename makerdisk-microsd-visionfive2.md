# MakerDisk 32GB microSD with Debian 12 OS for VisionFive 2 — Verified Reference

| Field | Value |
|---|---|
| Product code | `MMR-USD-32-VF2` [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page and its four description images (login screen, desktop app grid, `dd` speed test, card next to a VisionFive 2 board); resources list recorded (StarFive documentation links not opened) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-makerdisk-microsd-card-32gb-with-debian-12-os-for-visionfive-2 (read 2026-10-21) [PP]. No MakerDisk microSD datasheet exists |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = images on that page. The board is made by StarFive (named on the page: "StarFive VisionFive 2 Board"); its documentation on doc-en.rvspace.org is linked as [VEN] but was not read. Cytron sells the board separately (p-visionfive-2-single-board-computer); there is no VisionFive 2 file in this KB.

## What it is
- A 32GB Cytron-brand MakerDisk microSD card preloaded with **Debian 12** for the **StarFive VisionFive 2** single-board computer [PP].
- "You don't need to do any setup or configuration like Raspberry Pi OS or Jetson Jetpack OS … All of the startup configuration has been done" [PP].
- The image includes LibreOffice, Chromium, Firefox, FFMPEG, VLC, COGL, OpenCV and NodeJS "and much more" [PP].
- Sibling MakerDisk cards: `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-rdk-x5.md`, `makerdisk-microsd-makecode-offline.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Capacity | 32GB; ≈29GB usable in the Debian 12 file explorer (excl. boot) | [PP] |
| Preloaded OS | Debian 12 for StarFive VisionFive 2 (image build/date not stated) | [PP] |
| Speed class (Features) | "Class 10, A1, U3, V30 microSD card" | [PP] |
| `dd` write test | `sync; dd if=/dev/zero of=tempfile bs=1M count=1024; sync` → 1073741824 bytes in 49.2598 s, **21.8 MB/s** | [PP: img] |
| `dd` read test | `dd if=tempfile of=/dev/null bs=1M count=1024` → 0.941824 s, "1.1 GB/s" (file just written, served from RAM cache — not a card read speed) | [PP: img] |
| Default login | Stated on the product page and shown on the login screen image (not copied here) | [PP] |
| Desktop | GNOME-style desktop (Activities bar) with Settings, Terminal, Utilities, Chromium, Extensions, Firefox, Input Method, LibreOffice apps, VLC (screenshot) | [PP: img] |
| Warranty | Not shown in the page header (the sibling Raspberry Pi card shows 12 months) | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `MMR-USD-32-VF2`, RM54.00, availability 12, 3 ratings [PP].
- Packing list: 1 × 32GB MakerDisk MicroSD with Debian 12 for StarFive VisionFive 2 [PP].
- Accessory offered: USB2.0 Cytron microSD Card Reader/Writer Adapter (`cytron-microsd-card-reader.md`) [PP].
- Resources: Debian 12 download page; Documentation for VisionFive 2 (rvspace.org); Getting Started; Flashing Linux OS to the MicroSD card; Logging into Debian; VisionFive 2 Datasheet (PDF); VisionFive 2 Product Brief (PDF) [PP].

## Interfaces, terminals and pin mapping
- microSD card for the VisionFive 2's microSD slot [PP: img]. No other interface.

## Rules and gotchas (for code, wiring and tutorials)
- **Do not format the card** [PP].
- **Always shut down from the desktop.** "Please DO NOT power off without proper shutdown from the Desktop. It will corrupt the Debian 12 image in the microSD card" [PP].
- **For VisionFive 2 only:** the image is for StarFive VisionFive 2; it is not a Raspberry Pi image [PP].
- **Speed:** quote only the write figure (21.8 MB/s by `dd`); the "1.1 GB/s read" is a page-cache artefact [PP: img].
- To re-flash: use StarFive's "Flashing Linux OS to the MicroSD card" guide (linked) and a USB card reader [PP].

## Power and electrical limits
- Not stated. Powered from the board's microSD slot.

## Software support
- Debian 12 for VisionFive 2 with LibreOffice, Chromium, Firefox, FFMPEG, VLC, COGL, OpenCV, NodeJS [PP]. StarFive image version not stated.

## Compatibility and accessories
- StarFive VisionFive 2 (4GB or 8GB RAM; Cytron sells "VisionFive 2 8G or 4G RAM" and bundles) — "it can boot up on all StarFive VisionFive 2 computers right out of the box" [PP].
- Accessory: `cytron-microsd-card-reader.md` [PP].

## Common mistakes / troubleshooting
- **Image corrupted after pulling power:** re-flash the Debian image (StarFive guide) — the page warns that unclean power-off corrupts it [PP].
- **Card used in a Raspberry Pi:** it will not boot a Pi; use `makerdisk-microsd-rpi-os.md` [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Read speed | Features: "Read Speed: 1.1 GB/s" [PP] | The `dd` screenshot reads back a file it has just written; 1.1 GB is the file size and the read came from RAM cache [PP: img] (analysis, inferred) | Not a card speed; omit from content |
| 32GB speed class | This page: A1, U3, V30 [PP] | Raspberry Pi OS MakerDisk page: 32GB A1 is U1, V10 [PP] | Unresolved; quote only "Class 10, A1" |

## Needs verification
- StarFive Debian 12 image build/date on current stock.
- Warranty (not shown on this page's header).
- Card speed class (U1/V10 vs U3/V30) and SDHC marking for this 32GB card.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-makerdisk-microsd-card-32gb-with-debian-12-os-for-visionfive-2 — read 2026-10-21
- [PP: img] `mmr-usd-32-vf2-f.png` (login screen), `MMR-USD-32-VF2-c.png` (app grid), `MMR-USD-32-VF2-d.png` (`dd` test), `MMR-USD-32-VF2-e.jpg` (card beside VisionFive 2)
- [VEN] (linked, not read) https://doc-en.rvspace.org/Doc_Center/visionfive_2.html ; https://doc-en.rvspace.org/VisionFive2/Quick_Start_Guide/VisionFive2_QSG/flashing_with_mac_linux.html ; https://doc-en.rvspace.org/VisionFive2/PDF/VisionFive2_Datasheet.pdf
- KB cross-references: `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-rdk-x5.md`, `cytron-microsd-card-reader.md`
