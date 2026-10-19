# NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready) — Verified Reference

| Field | Value |
|---|---|
| Product code | V-MMR-NV2280 (product page, all capacities) [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Cytron product page "NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready)", read 2026-10-19 [PP] — no datasheet is linked from the page and none was found in Cytron's Google Drive (searches for "MakerDisk", "NVMe", "2280", "MMR-NV2280" returned no datasheet) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A Cytron-branded M.2 2280 M-Key NVMe (PCIe) solid-state drive sold with Raspberry Pi OS 64-bit Bookworm already written to it, so a Raspberry Pi 5, Pi 4 Model B, Pi 400 or Compute Module 4 (on an NVMe carrier) can boot from it without imaging [PP]. It is an NVMe PCIe drive, NOT a SATA drive [PP]. Capacities offered: 1TB, 512GB, 256GB and 128GB [PP]. The 2280 length (80 mm) is the longer standard M.2 size; the 2242 MakerDisk (makerdisk-nvme-2242.md) is the 42 mm version with its own datasheet.

## Specifications
No Cytron datasheet exists for this product; every row below comes from the product page text read on 2026-10-19 [PP].

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
| Speed test — random read | Figure present on the page but cut off in the text read | [PP] |
| Speed test host board | Not stated in the text read (Raspberry Pi Diagnostics tool named only) | [PP] |
| PCIe generation / lane count, NVMe version, NAND type, controller, power, temperature, MTBF, TBW, weight, warranty, packing list | Not stated in any Cytron source read | — |
| Price | RM1,099.00 shown for the 1TB option; prices of the other capacities not captured (Cytron product page, read 2026-10-19) | [PP] |
| Stock | Availability 24 (2026-10-19) | [PP] |

## Interfaces, terminals and pin mapping
- Connector: M.2 M-Key edge connector; mounting length 2280 (80 mm) [PP]. The host board must have a 2280 standoff position.
- Bus: NVMe over PCIe [PP]. Generation and lane count are not stated by Cytron.
- No other terminals; the drive is powered from the M.2 slot.

## Rules and gotchas (for code, wiring and tutorials)
- **DO NOT format the drive** if it is meant to boot a Raspberry Pi — the page says "DO NOT format" [PP]. Formatting erases the preloaded OS.
- **It is NVMe, not SATA.** It will not work in an M.2 SATA (B-Key) slot or in a SATA-to-USB adapter [PP].
- **2280 length:** it will not fit a 2230/2242-only slot such as the CM4 Maker Board M.2 slot (that board's datasheet limits it to NVMe 2230/2242 — see cm4-maker-board.md). For CM4 the page names carriers with a 2280 slot: Piunora and Mini Base (A) [PP].
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400 and Compute Module 4 with an NVMe carrier [PP]. The page text read for this product does not spell out the bootloader or HAT requirement per board; the sibling 2242 page does (latest bootloader; PCIe-to-M.2 HAT+ on Pi 5; USB-NVMe adapter on Pi 4 B) — apply the same hardware logic, but attribute it to the 2242 page if quoted.
- The only speed figures Cytron gives are Raspberry Pi Diagnostics results for the 128GB unit [PP]; do not generalise them to the 256GB, 512GB or 1TB units, and do not quote a reseller's "up to X MB/s" figure as a Cytron spec (see Needs verification).
- The 1TB price shown on the page (RM1,099.00) is the default option price; quote per-capacity prices only after reading the live page.

## Power and electrical limits
- Not stated in any Cytron source read. The drive is powered by the M.2 slot's 3.3 V rail by M.2 convention; no current or wattage figure exists for this product in Cytron documents.

## Software support
- Preloaded Raspberry Pi OS 64-bit Bookworm on units shipped from 22 November 2023 [PP]. Units shipped earlier may carry an older image — not stated which.
- Cytron tutorial linked from the page: "home NAS with Pi 5" [PP] (URL not captured; not fetched in this session).
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
- **Quoting 128GB Diagnostics numbers for the 1TB unit:** the test was on the 128GB unit only [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Datasheet | Product page: no datasheet linked [PP] | Reseller page (RobotShop) lists specs as if from a datasheet [3P] | No Cytron datasheet exists; reseller figures go to Needs verification, never stated as spec. |
| Preloaded OS wording | Product page: Raspberry Pi OS 64-bit Bookworm from 22 Nov 2023 [PP] | RobotShop: "latest Raspberry Pi OS", no version [3P] | Product page wins. |

## Needs verification
- Per-capacity model codes: RobotShop lists the 256GB unit as manufacturer number "MMR-NV2280-256" [3P], matching the MMR-NV2242-XXX pattern of the 2242 datasheet; Cytron has not published the per-capacity codes for the 2280 — confirm with the product team.
- RobotShop (256GB listing) states: PCIe Gen 3 x 4, NVMe 1.3, PCI Express Base 3.1, read up to 1800 MB/s, write up to 560 MB/s, shock 1500G/0.5ms, operating temperature 0°C to 70°C, SMART and TRIM, package = one SSD [3P]. None of these appear in a Cytron source; do not publish them as specs.
- Random read IOPS from the Cytron 128GB Raspberry Pi Diagnostics test and the host board used: cut off in the page text read.
- Which capacities share the same controller/NAND and whether the 128GB unit is a x2-lane part (as on the 2242): not stated.
- Bootloader/HAT requirement text on this page (as opposed to the 2242 page): not captured.
- "Home NAS with Pi 5" tutorial: title, author, date, URL and steps not verified (my.cytron.io unreachable in this session).
- Prices of the 128GB, 256GB and 512GB options: not captured.

## Sources
- [PP] Product page "NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready)" — https://my.cytron.io/p-nvme-2280-m-key-makerdisk-preloaded-with-rpi-os (read by the coordinator 2026-10-19; text in the coordinator's product-page extract)
- [3P] RobotShop UK listing "Cytron MakerDisk 256GB NVMe 2280m-Key SSD (Raspberry Pi OS Ready)" — https://uk.robotshop.com/products/cytron-makerdisk-256gb-nvme-2280m-key-ssd-raspberry-pi-os-ready (cross-check only)
- KB cross-references: /home/claude/kb/makerdisk-nvme-2242.md ; /home/claude/kb/cm4-maker-board.md
