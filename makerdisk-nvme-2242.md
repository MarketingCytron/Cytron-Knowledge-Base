# NVMe 2242 M-Key MakerDisk SSD (Preloaded with RPi OS) — Verified Reference

| Field | Value |
|---|---|
| Product code | V-MMR-NV2242 (product page, all capacities) [PP]; datasheet model number MMR-NV2242-XXX, "XXX" = capacity [DS] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "MakerDisk M.2 2242 NVMe SSD Datasheet", Rev 1.0, April 2024 (Cytron Technologies Sdn Bhd, Google Doc) [DS] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A Cytron-branded M.2 2242 NVMe (PCIe) solid-state drive sold with Raspberry Pi OS already written to it, so a Raspberry Pi can boot from it without imaging [DS][PP]. It is an NVMe PCIe drive, NOT a SATA drive [PP]. The three capacities differ in key, PCIe lane count and speed: the 128GB unit is a B+M-Key, PCIe Gen3 x2 drive; the 256GB and 512GB units are M-Key, PCIe Gen3 x4 drives [DS]. The datasheet covers the bare drive; everything about the preloaded OS and which Raspberry Pi boards boot from it comes from the product page [PP].

## Specifications
Every row of the datasheet table (Rev 1.0, April 2024). The datasheet numbers its rows 1–22 but has no row 9 (it jumps from 8 to 10) [DS].

| Item | Value | Src |
|---|---|---|
| Model | MMR-NV2242-XXX (MakerDisk M.2 NVMe 2242 SSD) | [DS] |
| Product code on store | V-MMR-NV2242; options 512GB / 256GB / 128GB | [PP] |
| Interface | M.2 M-Key (B+M Key on 128GB SSD) | [DS] |
| Form factor / dimensions | M.2 2242, L42.00mm × W22.0mm × H2.7mm, error ±0.5mm | [DS] |
| Capacity | 128GB / 256GB / 512GB | [DS][PP] |
| Protocol — 128GB | PCIe Gen3 x 2 Lane, NVMe 1.3 | [DS] |
| Protocol — 256GB | PCIe Gen3 x 4 Lane, NVMe 1.3 | [DS] |
| Protocol — 512GB | PCIe Gen3 x 4 Lane, NVMe 1.3 | [DS] |
| NAND Flash | 3D TLC (all capacities) | [DS] |
| Sequential Read (MB/s) | 128GB: 1700 / 256GB: 2250 / 512GB: 2300 | [DS] |
| Sequential Write (MB/s) | 128GB: 600 / 256GB: 1300 / 512GB: 1850 | [DS] |
| 4K Random Read (IOPS) | 128GB: 70K (Max) / 256GB: 85K (Max) / 512GB: 145K (Max) | [DS] |
| 4K Random Write (IOPS) | 128GB: 130K (Max) / 256GB: 280K (Max) / 512GB: 400K (Max) | [DS] |
| Test conditions for the speed rows | None stated (no host, queue depth or tool given) | [DS] |
| Input Voltage | DC 3.3V ±5% | [DS] |
| Power Consumption (Idle) | 0.60W (Max) | [DS] |
| Power Consumption (Active) | 3.65W (Max) | [DS] |
| MTBF | 1.5 million hours | [DS] |
| ECC | LDPC Error Correction of Hardware / Bad Block Management | [DS] |
| Features | Power management / TRIM / S.M.A.R.T. / NCQ / Wear-leveling | [DS] |
| Operating Temperature | 0℃ – 70℃ | [DS] |
| Storage Temperature | −40℃ – 85℃ | [DS] |
| Operating Humidity | 5 – 90% | [DS] |
| Certificates | FCC, CE, RoHS, REACH | [DS] |
| Made in | Made in Taiwan | [DS] |
| Preloaded OS | Raspberry Pi OS 64-bit Bookworm, on units shipped from January 2024 | [PP] |
| Price | RM369.00 – RM739.00 across the three capacities (Cytron product page, read 2026-10-19) | [PP] |
| Stock | Availability 164 (2026-10-19) | [PP] |
| Controller, TBW / endurance, weight, warranty, packing list | Not stated in the datasheet or in the product-page text read | — |

## Interfaces, terminals and pin mapping
- Connector: M.2 edge connector, M-Key on 256GB and 512GB; B+M-Key on 128GB [DS]. The two mechanical drawings in the datasheet are titled "MakerDisk M.2 2242 NVMe SSD - B+M Key - 128GB" and "MakerDisk M.2 2242 NVMe SSD - M Key - 256GB & 512GB" (top, bottom and side views) [DS]; the drawings are images and their dimension call-outs could not be read as text.
- Bus: PCIe Gen3, NVMe 1.3; two lanes (128GB) or four lanes (256GB, 512GB) [DS].
- Mounting length: 2242 (42 mm) — it needs a 2242 standoff position on the host board [DS].
- Supply: single 3.3 V rail from the M.2 slot, ±5% [DS].

## Rules and gotchas (for code, wiring and tutorials)
- **DO NOT format the drive** if it is meant to boot a Raspberry Pi — the product page says "DO NOT format it" [PP]. Formatting erases the preloaded Raspberry Pi OS.
- **It is NVMe, not SATA.** It will not work in an M.2 SATA (B-Key) slot or a SATA adapter [PP].
- **Key mismatch between capacities:** the 128GB is B+M-Key, the 256GB/512GB are M-Key only [DS]. State the key for the capacity you are writing about.
- **Raspberry Pi 5** boots from it with the latest bootloader and a PCIe-to-M.2 HAT+ [PP]. Keep the HAT+ as a separate purchase in any tutorial — the page lists it as a requirement, not as included.
- **Raspberry Pi 4 Model B** boots from it with the latest bootloader via a USB-to-NVMe adapter (the Pi 4 has no PCIe slot) [PP]. **Raspberry Pi 400** is also listed [PP]; the page text read does not say which adapter the Pi 400 uses — treat it as the same USB path as the Pi 4.
- **Compute Module 4** boots from it on an NVMe carrier, e.g. the CM4 Maker Board [PP]; the CM4 Maker Board's own datasheet limits its M.2 slot to NVMe 2230/2242 and excludes M.2 SATA (see cm4-maker-board.md).
- The datasheet speed rows are the drive's own maximum figures with no stated host [DS]. No Cytron source read gives a Raspberry Pi-measured speed for this product; do not present the datasheet MB/s figures as what a Pi will achieve.
- The product page says Jeff Geerling verified the drive on Raspberry Pi 5 [PP]; the page text read gives no figures from that verification.

## Power and electrical limits
| Item | Value | Src |
|---|---|---|
| Input voltage | DC 3.3V ±5% | [DS] |
| Idle power | 0.60W (Max) | [DS] |
| Active power | 3.65W (Max) | [DS] |
| Operating temperature | 0℃ – 70℃ | [DS] |
| Storage temperature | −40℃ – 85℃ | [DS] |
| Operating humidity | 5 – 90% | [DS] |
| MTBF | 1.5 million hours | [DS] |
| Peak / inrush current, 3.3 V current draw | Not stated | — |

## Software support
- Preloaded Raspberry Pi OS 64-bit Bookworm on units shipped from January 2024 [PP]. Units shipped earlier may carry an older image — the page text read does not say which.
- Drive features: TRIM, S.M.A.R.T., NCQ, power management, wear-levelling, LDPC ECC and bad-block management [DS].
- Cytron tutorials linked from the product page [PP]: "updating Pi 5 bootloader" (https://my.cytron.io/tutorial/raspberry-pi-imager-updating-bootloader), "clone RPi OS into SSD" (https://my.cytron.io/tutorial/clone-raspberry-pi-os-into-ssd) and "CM4 Maker Board getting started". None of these tutorials could be fetched in this session (my.cytron.io and www.cytron.io blocked), so their steps are not recorded here.

## Compatibility and accessories
- Boots on: Raspberry Pi 5 (latest bootloader + PCIe-to-M.2 HAT+), Raspberry Pi 4 Model B (latest bootloader, via USB-NVMe adapter), Raspberry Pi 400, Compute Module 4 on an NVMe carrier such as the CM4 Maker Board [PP].
- Not included (page lists them as requirements): PCIe-to-M.2 HAT+ for Pi 5, USB-to-NVMe adapter for Pi 4 B, NVMe carrier for CM4 [PP].
- Needs an M.2 slot with a 2242 mounting position; the 128GB B+M-Key unit also fits M-Key sockets, the M-Key units do not fit B-Key sockets [DS] (key fact; socket statement follows from the key definition).
- Related Cytron products: CM4 Maker Board (cm4-maker-board.md) — M.2 Key-M NVMe 2230/2242, bootable, M.2 SATA not supported [DS of that board].

## Common mistakes / troubleshooting
- **Drive formatted / OS gone:** the preloaded OS is the whole point of the product; the page warns not to format it [PP]. Re-imaging with Raspberry Pi Imager is possible but is not described by any source read.
- **Pi 5 does not boot from it:** the page requires the latest bootloader and a PCIe-to-M.2 HAT+ [PP]; check both before blaming the drive.
- **Pi 4 B does not boot from it:** the page requires the latest bootloader and a USB-NVMe adapter [PP].
- **Writing "SATA" in copy:** the page explicitly says NVMe (PCIe), NOT SATA [PP].
- **Quoting one speed for "the MakerDisk 2242":** the three capacities have different speeds, lane counts and keys [DS] — always name the capacity.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Product / model code | Datasheet: model "MMR-NV2242-XXX" [DS] | Store code "V-MMR-NV2242" with a capacity option [PP] | Not a true conflict: the store code is the variant-group code, the datasheet pattern is the per-capacity model. Use V-MMR-NV2242 for the store listing and MMR-NV2242-XXX when naming a specific drive. |
| Key | "M.2 M-Key (B+M Key on 128GB SSD)" [DS] | Title says "M-Key"; body says "M-Key (128GB is B+M-Key)" [PP] | Agree; datasheet wording used. |

## Needs verification
- Datasheet mechanical drawings (top/bottom/side views for both key variants): images only; dimension call-outs beyond 42.00 × 22.0 × 2.7 mm ±0.5 mm not readable — confirm with the design team if a drawing is needed.
- Controller chip, DRAM/HMB, TBW endurance, weight, warranty period and packing list: not stated in either source.
- Whether the Raspberry Pi 400 path is the same USB-NVMe adapter as the Pi 4 B: implied by the page's grouping, not stated.
- OS image on units shipped before January 2024: not stated.
- Raspberry Pi-measured throughput (any board): no Cytron figure for this product.
- Cytron tutorials "Raspberry Pi Imager: updating bootloader", "Clone Raspberry Pi OS into SSD" and "CM4 Maker Board getting started": not readable in this session — their titles, authors, dates and steps are unverified.
- Third-party reviews (cnx-software, April 2024) tested MakerDisk NVMe drives on Pi 5 with Geekworm/Waveshare HATs [3P]; not used for any spec.

## Sources
- [DS] "MakerDisk M.2 2242 NVMe SSD Datasheet", Rev 1.0, April 2024, Cytron Technologies Sdn Bhd — https://docs.google.com/document/d/14tFhPy47Aa8ugKsBqsc8-0nyJH_La1EbLZbW4Ooeg_w/edit
- [PP] Product page "NVMe 2242 M-Key MakerDisk SSD (Preloaded with RPi OS)" — https://my.cytron.io/p-nvme-2242-b-plus-m-key-makerdisk-ssd-preloaded-rpi-os (read by the coordinator 2026-10-19; text in the coordinator's product-page extract)
- [PP] Tutorial links on the page (not fetched): https://my.cytron.io/tutorial/raspberry-pi-imager-updating-bootloader ; https://my.cytron.io/tutorial/clone-raspberry-pi-os-into-ssd
- KB cross-reference: /home/claude/kb/cm4-maker-board.md (M.2 slot facts)
