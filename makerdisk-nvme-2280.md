# NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready) — Verified Reference

| Field | Value |
|---|---|
| Product code | V-MMR-NV2280 (product page, all capacities) [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: read the product-page images — Cytron drive labels for all four capacities (PCIe gen/lanes, NVMe version, rated read/write, SMART & TRIM, 1-year warranty, Made in Taiwan), both Raspberry Pi Diagnostics screenshots, the MakerDisk vs CM4 eMMC comparison table, the M.2 size chart and the OS screenshot. No datasheet exists; labels are tagged [PP: img] |
| Primary source | Cytron product page "NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready)", read 2026-10-19 [PP] — no datasheet is linked from the page and none was found in Cytron's Google Drive (searches for "MakerDisk", "NVMe", "2280", "MMR-NV2280" returned no datasheet) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A Cytron-branded M.2 2280 M-Key NVMe (PCIe) solid-state drive sold with Raspberry Pi OS 64-bit Bookworm already written to it, so a Raspberry Pi 5, Pi 4 Model B, Pi 400 or Compute Module 4 (on an NVMe carrier) can boot from it without imaging [PP]. It is an NVMe PCIe drive, NOT a SATA drive [PP]. Capacities offered: 1TB, 512GB, 256GB and 128GB [PP]. The 2280 length (80 mm) is the longer standard M.2 size; the 2242 MakerDisk (makerdisk-nvme-2242.md) is the 42 mm version with its own datasheet.

## Specifications
No Cytron datasheet exists for this product. Rows come from the product page text [PP] and the Cytron images on that page — the printed drive labels, diagnostics screenshots and comparison table [PP: img] — all read 2026-10-19.

| Item | Value | Src |
|---|---|---|
| Product code | V-MMR-NV2280 | [PP] |
| Form factor | M.2 2280 | [PP] |
| Key | M-Key | [PP] |
| Interface | NVMe (PCIe); "NOT SATA" | [PP] |
| Capacities | 1TB / 512GB / 256GB / 128GB | [PP] |
| Preloaded OS | Raspberry Pi OS 64-bit Bookworm, on units shipped from 22 November 2023 | [PP] |
| Speed test — sequential write | 385505 KB/s (128GB unit, Raspberry Pi Diagnostics) | [PP] |
| Speed test — random write | 25680 IOPS (128GB unit, Raspberry Pi Diagnostics) | [PP] |
| Speed test — random read | 22351 IOPS (128GB unit; Raspberry Pi Diagnostics v0.13, 23 Oct 2023; Test PASS) | [PP: img] |
| Speed test host board | Not stated; the page photos show the drive fitted to a CM4-type carrier board | [PP: img] |
| Earlier comparison (Cytron table) | MakerDisk NVMe 2280 ≈372 MB/s seq. write, ≈18600 IOPS random write, ≈25300 IOPS random read; MakerDisk NVMe 2242 ≈387 / ≈17800 / ≈24400; CM4 eMMC ≈76 MB/s / ≈8700 / ≈7300 (Raspberry Pi Diagnostics v0.10 run of 17 Oct 2022: 312076 KB/s, 11586 / 18984 IOPS) | [PP: img] |
| Label — 128GB | PCIe Gen 3 x4, PCI Express Base 3.1, NVMe 1.3; read up to 1800 MB/s, write up to 560 MB/s | [PP: img] |
| Label — 256GB | PCIe Gen 3 x4, PCI Express Base 3.1, NVMe 1.3; read up to 2050 MB/s, write up to 1000 MB/s | [PP: img] |
| Label — 512GB | PCIe Gen 3 x4, PCI Express Base 3.1, NVMe 1.3; read up to 2050 MB/s, write up to 1700 MB/s | [PP: img] |
| Label — 1TB | **PCIe Gen 4 x4**, PCI Express Base 3.1 (as printed), **NVMe 1.4**; read 5100 MB/s, write 4800 MB/s | [PP: img] |
| Label — all capacities | SMART & TRIM supported; Advanced Flash Management; RoHS, FC, CE; Made in Taiwan; "WARRANTY VOID IF REMOVED" | [PP: img] |
| Size | M.2 2280 = 22 × 80 mm (page size chart: 0.87" × 3.15") | [PP: img] |
| Warranty | 1 Year Limited Warranty (printed on the drive label) | [PP: img] |
| NAND type, controller, DRAM, power, temperature, shock, MTBF, TBW, weight, packing list | Not stated in any Cytron source read | — |
| Price | RM1,099.00 shown for the 1TB option; prices of the other capacities not captured (Cytron product page, read 2026-10-19) | [PP] |
| Stock | Availability 24 (2026-10-19) | [PP] |

## Interfaces, terminals and pin mapping
- Connector: M.2 M-Key edge connector; mounting length 2280 (80 mm) [PP]. The host board must have a 2280 standoff position.
- Bus: NVMe over PCIe [PP]. Drive labels: PCIe Gen 3 x4 / NVMe 1.3 on 128GB, 256GB and 512GB; PCIe Gen 4 x4 / NVMe 1.4 on 1TB [PP: img]. Label ratings are drive maximums; on a Raspberry Pi the measured speed is much lower (see the Raspberry Pi Diagnostics rows).
- No other terminals; the drive is powered from the M.2 slot.

## Rules and gotchas (for code, wiring and tutorials)
- **DO NOT format the drive** if it is meant to boot a Raspberry Pi — the page says "DO NOT format" [PP]. Formatting erases the preloaded OS.
- **It is NVMe, not SATA.** It will not work in an M.2 SATA (B-Key) slot or in a SATA-to-USB adapter [PP].
- **2280 length:** it will not fit a 2230/2242-only slot such as the CM4 Maker Board M.2 slot (that board's datasheet limits it to NVMe 2230/2242 — see cm4-maker-board.md). For CM4 the page names carriers with a 2280 slot: Piunora and Mini Base (A) [PP].
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400 and Compute Module 4 with an NVMe carrier [PP]. The page text read for this product does not spell out the bootloader or HAT requirement per board; the sibling 2242 page does (latest bootloader; PCIe-to-M.2 HAT+ on Pi 5; USB-NVMe adapter on Pi 4 B) — apply the same hardware logic, but attribute it to the 2242 page if quoted.
- Rated speeds are **per capacity** (drive labels [PP: img]): 128GB 1800/560 MB/s, 256GB 2050/1000, 512GB 2050/1700, 1TB 5100/4800 (Gen 4). Quote them as "up to" label ratings, never as Raspberry Pi speeds. The Raspberry Pi Diagnostics figures were measured on the 128GB unit only [PP: img].
- The 1TB price shown on the page (RM1,099.00) is the default option price; quote per-capacity prices only after reading the live page.

## Power and electrical limits
- Not stated in any Cytron source read. The drive is powered by the M.2 slot's 3.3 V rail by M.2 convention; no current or wattage figure exists for this product in Cytron documents.

## Software support
- Preloaded Raspberry Pi OS 64-bit Bookworm on units shipped from 22 November 2023 [PP]. The page's Raspberry Pi Imager screenshot shows "Raspberry Pi OS with desktop", release 5 Dec 2023, 64-bit, kernel 6.1, Debian 12 (bookworm) [PP: img]. Units shipped earlier may carry an older image — not stated which.
- Cytron tutorial linked from the page: "How to build a home NAS with Raspberry Pi 5" — https://my.cytron.io/tutorial/how_to_build_a_home_nas_with_raspberry_pi5 [PP] (steps not read).
- No Cytron software, driver or firmware is associated with the drive; it is a standard NVMe device to the OS.

## Compatibility and accessories
- Boots on: Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400, Compute Module 4 on an NVMe carrier — carriers named: Piunora, Mini Base (A) [PP].
- Required but not included: a PCIe-to-M.2 HAT/HAT+ with a 2280 position for Pi 5; a USB-to-NVMe enclosure/adapter for Pi 4 B and Pi 400 (these boards have no PCIe slot); an NVMe carrier for CM4 [PP for the board list; adapter types follow from the 2242 page and the boards' own hardware].
- Not compatible: CM4 Maker Board M.2 slot (2230/2242 only, see cm4-maker-board.md); any M.2 SATA slot [PP].
- Sibling products: NVMe 2242 MakerDisk (makerdisk-nvme-2242.md, datasheet available); NVMe 2280 MakerDisk JetPack edition for Jetson Orin Nano Super (makerdisk-nvme-2280-jetpack.md) — same form factor, different preloaded OS, not interchangeable.

## Common mistakes / troubleshooting
- **Drive formatted / OS gone:** page warns "DO NOT format" [PP]; re-imaging is possible with Raspberry Pi Imager but is not described by any source read.
- **Does not fit:** the drive is 80 mm long; 2242-only slots (CM4 Maker Board) cannot take it [PP + cm4-maker-board.md].
- **Confusing it with the JetPack edition:** V-MMR-NV2280 carries Raspberry Pi OS; V-MMR-NV2280-JP carries JetPack 6.2 for Jetson Orin Nano Super. Check the code.
- **Writing "SATA":** the page says NVMe, NOT SATA [PP].
- **Quoting 128GB Diagnostics numbers for the 1TB unit:** the test was on the 128GB unit only [PP: img].
- **Quoting the 1TB as Gen 3:** the 1TB label says PCIe Gen 4 x4, NVMe 1.4; the smaller capacities are Gen 3 x4, NVMe 1.3 [PP: img].
- **Peeling the label:** it carries "warranty void if removed" [PP: img].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Datasheet | Product page: no datasheet linked [PP] | Reseller page (RobotShop) lists specs as if from a datasheet [3P] | No Cytron datasheet exists. Cytron's own drive labels [PP: img] now confirm PCIe Gen 3 x4, NVMe 1.3, PCIe Base 3.1, SMART & TRIM. |
| 256GB rated speed | Cytron 256GB label: read up to 2050 MB/s, write up to 1000 MB/s [PP: img] | RobotShop 256GB listing: read up to 1800, write up to 560 MB/s [3P] | Cytron label wins. RobotShop's figures match the 128GB label — likely copied from it. |
| Preloaded OS wording | Product page: Raspberry Pi OS 64-bit Bookworm from 22 Nov 2023 [PP] | RobotShop: "latest Raspberry Pi OS", no version [3P] | Product page wins. |

## Needs verification
- Per-capacity model codes: RobotShop lists the 256GB unit as manufacturer number "MMR-NV2280-256" [3P], and the page's image folders use MMR-NV2280-128 / MMR-NV2280-1T — confirm the full set with the product team.
- RobotShop (256GB listing) also states shock 1500G/0.5ms and operating temperature 0°C to 70°C [3P]. These are not on the NVMe labels (they are on the SATA MakerDisk label); do not publish for the NVMe drive.
- Host board used for the 2023 Raspberry Pi Diagnostics run (photos show a CM4-type carrier).
- Which capacities share the same controller/NAND; whether drives in the current batch still match the photographed labels.
- Bootloader/HAT requirement text on this page (as opposed to the 2242 page): not captured.
- Prices of the 128GB, 256GB and 512GB options: not captured.
- "PCI Express Base 3.1" printed on the Gen 4 1TB label: PCIe Base 3.1 is the standard version for Gen 3 links; Gen 4 belongs to PCIe Base 4.0. The 1TB label likely reuses the Gen 3 label text — quote "PCIe Gen 4 x4, NVMe 1.4" and leave out the Base version for the 1TB.

## Sources
- [PP] Product page "NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready)" — https://my.cytron.io/p-nvme-2280-m-key-makerdisk-preloaded-with-rpi-os (read by the coordinator 2026-10-19; text in the coordinator's product-page extract)
- [3P] RobotShop UK listing "Cytron MakerDisk 256GB NVMe 2280m-Key SSD (Raspberry Pi OS Ready)" — https://uk.robotshop.com/products/cytron-makerdisk-256gb-nvme-2280m-key-ssd-raspberry-pi-os-ready (cross-check only)
- KB cross-references: /home/claude/kb/makerdisk-nvme-2242.md ; /home/claude/kb/cm4-maker-board.md
