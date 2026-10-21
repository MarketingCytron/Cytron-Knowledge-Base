# USB2.0 Cytron microSD Card Reader/Writer Adapter — Verified Reference

| Field | Value |
|---|---|
| Product code | `CA-USB-USD-CT` [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (Description, Features, Packing List) and its four product photos (purple "MAKERDISK" body, clear cap, shown in a Raspberry Pi 4 USB port) |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-usb2p0-cytron-microsd-card-reader-writer (read 2026-10-21) [PP]. No datasheet or linked document; reader chipset not named |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = page photos. "Note: Stock from April 2023 onwards is in Purple color with "MAKERDISK"" [PP] — older stock looked different (not described).

## What it is
- A small USB 2.0 Type-A stick that reads and writes microSD cards; the card slides into the edge and the stick plugs into a computer's USB port [PP].
- No driver needed — it appears as a standard USB mass-storage device "under any OS" [PP].
- Cytron sells it as the accessory for MakerDisk microSD cards (`makerdisk-microsd-rpi-os.md` and siblings) — e.g. for re-flashing an OS with Raspberry Pi Imager [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Host interface | USB 2.0, Type-A plug | [PP][PP: img] |
| Card type | microSD (no card included) | [PP] |
| Maximum card capacity | "Support up to 128GB microSD card"; description says "up to 128 GB SDHC cards" | [PP] |
| Max read / write speed | 16 MB/s read, 6 MB/s write | [PP] |
| OS support | Win7, 8, 10, macOS, Linux; no driver needed | [PP] |
| Functions | Read and write | [PP] |
| Body | Purple, printed "MAKERDISK" (stock from April 2023); clear plastic cap over the USB-A plug; loop at the rear end for a cord | [PP][PP: img] |
| Cord / cover | "Comes with a handy little cord" for attaching it to a datalogger project; plastic cover over the USB-A plug "so it won't short against nearby electronics" | [PP] |
| Dimensions, weight, chipset | Not stated | — |
| Price | RM4.00; 5 or more RM3.80 | [PP] |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `CA-USB-USD-CT`, RM4.00, availability 29, 135 ratings [PP].
- Packing list: 1 × USB MicroSD Card Reader/Writer [PP]. "It does not come with a microSD card! The MakerDisk microSD cards from Cytron work great with this card reader/writer" [PP].
- Related tutorials listed on the page are general Raspberry Pi tutorials (e.g. "Getting Started With Raspberry Pi 5 For Beginners", "Raspberry Pi 5 - Updating Bootloader and Boot from NVMe SSD", "With Raspberry Pi Imager, you can write Raspberry Pi OS and remote SSH easier") [PP].

## Interfaces, terminals and pin mapping
- USB 2.0 Type-A plug (host side) and a microSD slot at the far edge [PP][PP: img].

## Rules and gotchas (for code, wiring and tutorials)
- **USB 2.0 only:** 16 MB/s read / 6 MB/s write maximum [PP]. Flashing a full 32–128GB image is slow; that is the reader, not the card. Do not use its speed to judge a MakerDisk card.
- **Capacity:** "up to 128GB" [PP] — do not promise 256GB cards.
- **Booting a Raspberry Pi from it** is not stated by Cytron; treat it as a PC card reader for imaging (inferred).
- No card included [PP].

## Power and electrical limits
- Bus-powered from USB; current not stated.

## Software support
- No driver; standard mass storage [PP]. Use Raspberry Pi Imager (or the board maker's tool) to write OS images.

## Compatibility and accessories
- Hosts: Windows 7/8/10, macOS, Linux [PP]; shown plugged into a Raspberry Pi 4 USB port [PP: img].
- Cards: MakerDisk microSD — `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-makecode-offline.md`, `makerdisk-microsd-visionfive2.md`, `makerdisk-microsd-rdk-x5.md` [PP].

## Common mistakes / troubleshooting
- **Imaging takes a long time:** expected at USB 2.0 / 6 MB/s write [PP].
- **Card not detected:** confirm the card is fully inserted at the edge slot and ≤128GB [PP]. A customer review notes trouble writing images with a different cheap reader and A2 cards [3P, on the MakerDisk card page].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Card standard | Description: "up to 128 GB SDHC cards" [PP] | SD standard: cards above 32GB are SDXC (general knowledge); Features: "up to 128GB microSD card" [PP] | Read as "microSD/SDHC/SDXC up to 128GB" (inferred); SDXC support is not stated in words |
| Cord | "Comes with a handy little cord" [PP] | Photos show only a loop, no cord [PP: img] | Unresolved; packing list names only the reader |

## Needs verification
- Whether a lanyard/cord is still included.
- SDXC (64/128GB) and exFAT support stated explicitly; reader chipset; dimensions.
- Warranty (not shown in the page header).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-usb2p0-cytron-microsd-card-reader-writer — read 2026-10-21
- [PP: img] `CA-USB-USD-CT_b.jpg`, `_c.jpg`, `_da.jpg`, `_f.jpg`
- KB cross-references: `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-makecode-offline.md`, `makerdisk-microsd-visionfive2.md`, `makerdisk-microsd-rdk-x5.md`
