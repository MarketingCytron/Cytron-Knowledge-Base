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
- Speed test host board and random read figure: [NOT STATED]
- PCIe generation, lane count, NVMe version, NAND type, controller: [NOT STATED]
- Power consumption, operating temperature, MTBF, TBW, weight: [NOT STATED]
- Warranty, packing list: [NOT STATED]
- Datasheet: none published

## Interfaces and compatibility
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400
- Boots on Compute Module 4 with an NVMe carrier — carriers named: Piunora, Mini Base (A)
- Host needs an M.2 M-Key slot with a 2280 mounting position
- Does not fit the CM4 Maker Board M.2 slot (that slot takes NVMe 2230/2242 only)
- Not usable in M.2 SATA slots or SATA adapters
- Cytron tutorial linked: home NAS with Raspberry Pi 5

## Use cases
- Boot drive for Raspberry Pi 5
- Boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400
- Boot drive for Compute Module 4 on an NVMe carrier (Piunora, Mini Base (A))
- Storage for a home NAS built on Raspberry Pi 5 (linked tutorial)

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded OS
- NVMe only; it is NOT SATA
- 2280 length; will not fit 2230/2242-only M.2 slots
- The only Cytron speed figures are Raspberry Pi Diagnostics results on the 128GB unit; they do not describe the other capacities
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
