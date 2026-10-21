# Raspberry Pi Approved MakerDisk microSD Card with RPi OS — Verified Reference

| Field | Value |
|---|---|
| Product code | `V-MMR-USD-MD` (parent listing) [PP]; variant codes `MMR-USD-MD-128-A1`, `MMR-USD-MD-64-A1`, `MMR-USD-MD-64` (64GB A2), `MMR-USD-MD-32-A1` [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page (description, features table, packing list, resources) with every variant selected for code/price/stock; the two Raspberry Pi Diagnostics screenshots (64GB A1 and A2 on Raspberry Pi 5); the card-face images; both Raspberry Pi microSD Approval Certificates (29 Apr 2022 and 30 Jun 2023, PDFs on Cytron's Google Drive) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = images on that page (Diagnostics screenshots, card faces); [VEN: cert] = Raspberry Pi Ltd approval certificates linked from the page (2022 PDF linked from the certificate image; 2023 PDF linked as "Raspberry Pi Approval Certificate (June 2023)"); [3P] = customer reviews on the Cytron page. MakerDisk is Cytron's own brand ("A microSD card from Makers to Makers!"). The 2023 certificate also lists a 256GB card that Cytron does not sell on this page.

## What it is
- A Cytron-brand (MakerDisk) microSD card sold with **Raspberry Pi OS (64-bit) already written to it**, so it boots a Raspberry Pi straight out of the box [PP]. "Please DO NOT format it if you intend to use it with the Raspberry Pi board" [PP].
- Cytron states it was "TESTED and APPROVED by the Raspberry Pi for use with Raspberry Pi Products" [PP]; the linked Raspberry Pi approval certificates list "Makerdisk 32GB / 64GB / 128GB" (2022) and "32GB / 64GB / 128GB / 256GB" (2023) [VEN: cert].
- Two performance tiers: **A1** "Standard Value" (32GB, 64GB, 128GB) and **A2** "High Performance" (64GB only) [PP].
- It is the microSD member of the MakerDisk range; the SSD members are `makerdisk-sata-120gb.md`, `makerdisk-nvme-2242.md`, `makerdisk-nvme-2280.md`. Board-specific siblings: `makerdisk-microsd-makecode-offline.md`, `makerdisk-microsd-visionfive2.md`, `makerdisk-microsd-rdk-x5.md`.

## Specifications
| Item | Value | Src |
|---|---|---|
| Brand | MakerDisk (Cytron OEM) | [PP] |
| Capacities | 128GB, 64GB, 32GB | [PP] |
| Usable capacity in Raspberry Pi OS file manager (excl. boot partition) | 128GB ≈ 114.8GB; 64GB ≈ 56.9GB; 32GB ≈ 28.2GB ("1GB = 1,000,000,000 bytes") | [PP] |
| Preloaded OS | Raspberry Pi OS 64-bit; "June 2024 onwards, the latest Raspberry Pi OS - Bookworm" | [PP] |
| Bus mode | Supports SDR104 ("all MakerDisk microSD cards support SDR104"), so faster on Raspberry Pi 5 | [PP] |
| Card-face marks | "micro SD XC", UHS-I (I), Class 10 (10 in circle), A1 or A2 printed on the card (product images) | [PP: img] |
| 128GB A1 (`MMR-USD-MD-128-A1`) | Seq. write > 50MB/s; random write > 700 IOPS; random read > 2000 IOPS; Class 10, A1, U3, V30 | [PP] |
| 64GB A1 (`MMR-USD-MD-64-A1`) | Seq. write > 41MB/s; random write > 600 IOPS; random read > 2300 IOPS; Class 10, A1, U3, V30 | [PP] |
| 64GB A2 (`MMR-USD-MD-64`) | Seq. write > 44MB/s; random write > 2000 IOPS; random read > 4000 IOPS; Class 10, A2, U3, V30 | [PP] |
| 32GB A1 (`MMR-USD-MD-32-A1`) | Seq. write > 32MB/s; random write > 800 IOPS; random read > 3000 IOPS; Class 10, A1, **U1, V10** | [PP] |
| Pi 5 Diagnostics — 64GB A2 | Raspberry Pi Diagnostics v0.20, 1 Jul 2026: sequential write 44879 KB/s, random write 2003 IOPS, random read 3973 IOPS — Test PASS | [PP: img] |
| Pi 5 Diagnostics — 64GB A1 | Raspberry Pi Diagnostics v0.20, 1 Jul 2026: sequential write 41524 KB/s, random write 661 IOPS, random read 2395 IOPS — Test PASS | [PP: img] |
| Raspberry Pi approval limits | A1 standard: seq. write > 10MB/s, random write > 500 IOPS, random read > 1500 IOPS; Raspberry Pi: > 12MB/s, > 500 IOPS, > 2000 IOPS | [VEN: cert] |
| Approval test 2023 (end-of-run averages) | 32GB 28,492 KB/s / 833 / 2,856 IOPS after 16,856 power interrupts; 64GB 33,144 / 904 / 3,009 after 16,880; 128GB 33,715 / 960 / 2,964 after 16,903; 256GB 40,273 / 1,589 / 4,791 after 7,761 (seq. write KB/s / random write / random read) | [VEN: cert] |
| Approval test rig | Raspberry Pi 4 Model B 4GB rig, custom Buster image, stress scripts, random power cuts | [VEN: cert] |
| Certificate dates | 2022: tested 29 Apr 2022, valid to 1 May 2023. 2023: tested 29 Jun 2023, approved 30 Jun 2023, **valid to 1 Jul 2024** | [VEN: cert] |
| Warranty | 12 months | [PP] |
| Dimensions, operating temperature, endurance (TBW), controller/NAND | Not stated | — |

### Variants, prices and stock (read 2026-10-21) [PP]
| Capacity / class | Code | Price | Availability |
|---|---|---|---|
| 128GB A1 | `MMR-USD-MD-128-A1` | RM145.00 | 172 |
| 64GB A1 | `MMR-USD-MD-64-A1` | RM89.00 | 66 |
| 32GB A1 | `MMR-USD-MD-32-A1` | RM54.00 | 250 |
128GB and 32GB are not offered in A2 (the A2 option is hidden/unavailable when either is selected) [PP].

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "Raspberry Pi Approved MakerDisk microSD Card with RPi OS"; Brand Cytron OEM; code `V-MMR-USD-MD`; warranty 12 months; 298 ratings [PP].
- Packing list: 1 × card of the chosen capacity/class ("Raspberry Pi Approved MakerDisk MicroSD with Raspberry Pi OS") [PP].
- "Accessories you may need": USB2.0 Cytron microSD Card Reader/Writer Adapter (RM4.00, `cytron-microsd-card-reader.md`) and Maker-Friendly Zipper Case (RM2.90) [PP].
- Resources: Using Raspberry Pi Imager (Raspberry Pi blog); Bookworm news post; Raspberry Pi Imager; Raspberry Pi OS download page; Raspberry Pi Approval Certificate (June 2023) [PP].
- Videos (not watched): first-boot setup of Bookworm on a 32GB card ("the method is the same for all memory sizes"); a reviewer video; Imager advanced-features video [PP].
- The page describes the Raspberry Pi lifespan test and says the cards were re-certified with "up to 15,000" power-interrupt cycles [PP].

## Interfaces, terminals and pin mapping
- Standard microSD card (UHS-I bus marks on the card) [PP: img]. Goes into the Raspberry Pi's microSD slot; to re-flash it on a PC it needs a USB microSD reader (not included) [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **Do not format it** if it will boot a Raspberry Pi — the OS is already on it [PP].
- **Pi Zero / Zero W / Zero WH need re-flashing with 32-bit Raspberry Pi OS** — the preloaded image is 64-bit [PP]. Zero 2 W works out of the box [PP].
- **Raspberry Pi 5 needs Bookworm or newer** — the page notes Pi 5 cannot run older Raspberry Pi OS versions [PP].
- **A1 vs A2:** only the 64GB comes in A2 [PP]. Quote IOPS per variant from the table, not one figure for all.
- **32GB is U1 / V10**, the 64GB and 128GB are U3 / V30 [PP] — do not call every MakerDisk card "U3".
- **"Approved" status:** the newest certificate linked (30 Jun 2023) says "Valid to: 1st July 2024" and that approval covers only cards of the same bill of materials [VEN: cert]. In tutorials say "tested and approved by Raspberry Pi (2022/2023 certificates)", not that a current certificate is in force.
- The Pi 5 Diagnostics screenshots are dated 1 Jul 2026 and show 64GB cards only [PP: img].
- To change OS, Cytron recommends Raspberry Pi Imager and a USB card reader [PP].
- First-boot setup (user account, Wi-Fi) is done in the Raspberry Pi OS first-boot wizard (video on the page); no default login is printed on the page [PP].

## Power and electrical limits
- Not stated by Cytron. The card is powered from the host's microSD slot.

## Software support
- Preloaded: Raspberry Pi OS 64-bit, Bookworm, on units "June 2024 onwards" [PP]. Earlier units may hold an older image (not stated).
- Re-imaging: Raspberry Pi Imager [PP].
- A customer review (Aug 2026) notes that a newer Raspberry Pi OS release (Trixie) exists and suggests flashing it instead of upgrading [3P] — see *Needs verification*.

## Compatibility and accessories
- Out of the box (Raspberry Pi OS 64-bit): Raspberry Pi 5, Raspberry Pi 500, Raspberry Pi 400 (US layout), Raspberry Pi 4 Model B 8GB/4GB/2GB/1GB, Raspberry Pi 3 Model B+, 3 Model B, 3 Model A+, Raspberry Pi Zero 2 W [PP].
- Needs re-flash with 32-bit Raspberry Pi OS: Raspberry Pi Zero WH, Zero W, Zero [PP].
- Compute Modules: not listed (CM4/CM5 with eMMC do not use a microSD; Lite carriers not mentioned) [PP].
- Accessories: `cytron-microsd-card-reader.md` (USB 2.0 reader, RM4.00); Maker-Friendly Zipper Case [PP].
- Related KB: `makerdisk-nvme-2242.md`, `makerdisk-nvme-2280.md`, `makerdisk-sata-120gb.md` (MakerDisk SSDs), `ai-agent-workshop-rpi5.md`, `raspbot-workshop.md` (Pi 5 workshops).

## Common mistakes / troubleshooting
- **Pi Zero W does not boot:** it needs a 32-bit image; re-flash with Imager [PP].
- **Card formatted by Windows "format disk" prompt:** the OS is gone; re-flash with Raspberry Pi Imager [PP].
- **Usable size smaller than label:** expected — about 114.8 / 56.9 / 28.2GB in the file manager [PP].
- **Lower IOPS than the table:** one reviewer measured ~1400 read / ~650 write IOPS on an older 32GB card [3P]; Cytron's own figures are host-dependent (Pi 5 for the 2026 screenshots, Pi 4 for the certificates).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 64GB A2 random read | Features table: "> 4000 IOPS" [PP] | Pi 5 Diagnostics screenshot: 3973 IOPS [PP: img] | Measured value is just under the table figure; quote "about 4000 IOPS (3973 measured on Pi 5)" |
| 32GB speed class | This page: Class 10, A1, **U1, V10** [PP] | MakeCode and VisionFive 2 MakerDisk pages: 32GB "Class 10, A1, U3, V30" [PP] | This page's per-capacity table is the more specific; treat 32GB as U1/V10 unless Cytron confirms otherwise |
| 32GB card standard | Usual SD rule: 32GB = SDHC (general knowledge) | 32GB card-face image on this page prints "micro SD XC" [PP: img]; the MakeCode page photo of a 32GB MakerDisk prints "micro SD HC" [PP: img] | Image likely a template; card standard for 32GB = SDHC is inferred, not stated |
| Power-interrupt cycles | Page: "up to 15,000" [PP] | 2023 certificate: averages of 16,856–16,903 for 32–128GB [VEN: cert] | Certificate wins; it shows more than 15,000 |
| Approval validity | Page: "TESTED and APPROVED by the Raspberry Pi" (no date limit) [PP] | Certificate: valid to 1 Jul 2024 [VEN: cert] | Report the certificate dates; whether a newer certificate exists is in *Needs verification* |

## Needs verification
- Whether a Raspberry Pi approval certificate newer than 30 Jun 2023 exists, and whether it covers the current A2 64GB (`MMR-USD-MD-64`) part.
- Exact Raspberry Pi OS build/date on current stock, and whether Cytron will move to Trixie (a customer review mentions Trixie [3P]).
- Card standard of the 32GB (SDHC vs SDXC) and its U/V class (see *Conflicts*).
- Operating temperature, endurance, dimensions, controller — not stated.

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-raspberry-pi-approved-makerdisk-microsd-with-rpi-os — read 2026-10-21 (all four variants selected)
- [PP: img] `64gb-a2-pi5.png`, `64gb-a1-pi5-1.png` (Diagnostics), `128gb-a1-1.png`, `64gb.png`, `32gb-a1-1.png` (card faces) on static.cytron.io, read 2026-10-21
- [VEN: cert] "RaspberryPiuSDApprovalCertificateMakerdisk32_64_128_256_230630.pdf" — (Cytron document — link not public) (rendered and read 2026-10-21)
- [VEN: cert] "RaspberryPiSDApprovalCertificate_MakerdiskMicroSD_220429.pdf" — (Cytron document — link not public) (text read 2026-10-21)
- [3P] Customer reviews on the product page (2024–2026)
- KB cross-references: `cytron-microsd-card-reader.md`, `makerdisk-nvme-2242.md`, `makerdisk-nvme-2280.md`, `makerdisk-sata-120gb.md`, `makerdisk-microsd-makecode-offline.md`, `makerdisk-microsd-visionfive2.md`, `makerdisk-microsd-rdk-x5.md`
