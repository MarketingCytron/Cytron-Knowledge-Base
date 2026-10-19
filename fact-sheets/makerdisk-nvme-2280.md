# Product fact sheets

## Product name
NVMe 2280 M-Key MakerDisk SSD (Raspberry Pi OS Ready)

## Aliases
V-MMR-NV2280, MakerDisk NVMe 2280, MakerDisk 2280 RPi OS, NVMe 2280 MakerDisk SSD Raspberry Pi OS Ready, MakerDisk M.2 2280 NVMe SSD

## What it is
A Cytron-branded M.2 2280 M-Key NVMe (PCIe) solid-state drive that ships with Raspberry Pi OS 64-bit Bookworm already written to it, so a Raspberry Pi 5, Pi 4 Model B, Pi 400 or Compute Module 4 (on an NVMe carrier) can boot from it. Offered in 1TB, 512GB, 256GB and 128GB.

## Specs and functions
- Product code: V-MMR-NV2280
- Form factor: M.2 2280
- Key: M-Key
- Interface: NVMe (PCIe) — NOT SATA
- Capacities: 1TB / 512GB / 256GB / 128GB
- Preloaded OS: Raspberry Pi OS 64-bit Bookworm, on units shipped from 22 November 2023
- Speed test (128GB unit, Raspberry Pi Diagnostics): sequential write 385505 KB/s; random write 25680 IOPS
- Speed test random read (128GB unit): 22351 IOPS (product page image)
- Drive label 128GB: PCIe Gen 3 x4, NVMe 1.3, read up to 1800 MB/s, write up to 560 MB/s (product page image)
- Drive label 256GB: PCIe Gen 3 x4, NVMe 1.3, read up to 2050 MB/s, write up to 1000 MB/s (product page image)
- Drive label 512GB: PCIe Gen 3 x4, NVMe 1.3, read up to 2050 MB/s, write up to 1700 MB/s (product page image)
- Drive label 1TB: PCIe Gen 4 x4, NVMe 1.4, read 5100 MB/s, write 4800 MB/s (product page image)
- All labels: SMART & TRIM supported, Advanced Flash Management, Made in Taiwan, RoHS/FC/CE (product page image)
- Size: 22 × 80 mm (M.2 2280) (product page image)
- Warranty: 1 year limited, printed on the label; void if label removed (product page image)
- NAND type, controller, power, operating temperature, MTBF, TBW, weight, packing list: [NOT STATED]
- Datasheet: none published

## Interfaces and compatibility
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400
- Boots on Compute Module 4 with an NVMe carrier — carriers named: Piunora, Mini Base (A)
- Host needs an M.2 M-Key slot with a 2280 mounting position
- Does not fit the CM4 Maker Board M.2 slot (that slot takes NVMe 2230/2242 only)
- Not usable in M.2 SATA slots or SATA adapters
- Cytron tutorial linked: How to build a home NAS with Raspberry Pi 5

## Use cases
- Boot drive for Raspberry Pi 5
- Boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400
- Boot drive for Compute Module 4 on an NVMe carrier (Piunora, Mini Base (A))
- Storage for a home NAS built on Raspberry Pi 5 (linked tutorial)

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded OS
- NVMe only; it is NOT SATA
- 2280 length; will not fit 2230/2242-only M.2 slots
- Rated speeds differ by capacity (labels); the Raspberry Pi Diagnostics results are for the 128GB unit only
- Label ratings are drive maximums; Raspberry Pi Diagnostics results on a Pi are much lower
- HAT/adapter/carrier for the host board is not included
- OS image on units shipped before 22 November 2023: [NOT STATED]

## Positioning (kept apart from specs)
- "Raspberry Pi OS Ready" — plug in and boot (product page framing)

## Price band
RM1,099.00 shown for the 1TB option; other capacities not captured (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-nvme-2280-m-key-makerdisk-preloaded-with-rpi-os

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-nvme-2280-m-key-makerdisk-preloaded-with-rpi-os
