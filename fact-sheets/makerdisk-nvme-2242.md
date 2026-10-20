# Product fact sheets

## Product name
NVMe 2242 M-Key MakerDisk SSD (Preloaded with RPi OS)

## Aliases
V-MMR-NV2242, MMR-NV2242, MakerDisk NVMe 2242, MakerDisk M.2 2242 NVMe SSD, MakerDisk 2242, NVMe 2242 MakerDisk SSD

## What it is
A Cytron-branded M.2 2242 NVMe (PCIe) solid-state drive that ships with Raspberry Pi OS already written to it, so a Raspberry Pi can boot from it without imaging. Three capacities: 128GB (B+M-Key, PCIe Gen3 x2), 256GB and 512GB (M-Key, PCIe Gen3 x4).

## Specs and functions
- Model: MMR-NV2242-XXX (datasheet); store code V-MMR-NV2242 with capacity option (product page)
- Interface: M.2 M-Key (B+M Key on 128GB SSD)
- Dimensions: M.2 2242, L42.00mm x W22.0mm x H2.7mm, error ±0.5mm
- Capacity: 128GB / 256GB / 512GB
- Protocol: 128GB = PCIe Gen3 x 2 Lane, NVMe 1.3; 256GB and 512GB = PCIe Gen3 x 4 Lane, NVMe 1.3
- NAND Flash: 3D TLC
- Sequential Read (MB/s): 128GB 1700; 256GB 2250; 512GB 2300
- Sequential Write (MB/s): 128GB 600; 256GB 1300; 512GB 1850
- 4K Random Read (IOPS): 128GB 70K (Max); 256GB 85K (Max); 512GB 145K (Max)
- 4K Random Write (IOPS): 128GB 130K (Max); 256GB 280K (Max); 512GB 400K (Max)
- Test conditions for the speed figures: [NOT STATED]
- Input Voltage: DC 3.3V ±5%
- Power Consumption (Idle): 0.60W (Max)
- Power Consumption (Active): 3.65W (Max)
- MTBF: 1.5 million hours
- ECC: LDPC Error Correction of Hardware / Bad Block Management
- Features: Power management / TRIM / S.M.A.R.T. / NCQ / Wear-leveling
- Operating Temperature: 0℃ – 70℃
- Storage Temperature: −40℃ – 85℃
- Operating Humidity: 5 – 90%
- Certificates: FCC, CE, RoHS, REACH
- Made in: Taiwan
- Preloaded OS: Raspberry Pi OS 64-bit Bookworm on units shipped from January 2024 (product page)
- Controller, TBW, weight, warranty, packing list: [NOT STATED]

## Interfaces and compatibility
- Bus: NVMe over PCIe Gen3 — it is NOT a SATA drive
- Boots on Raspberry Pi 5 with the latest bootloader and a PCIe-to-M.2 HAT+ (product page)
- Boots on Raspberry Pi 4 Model B with the latest bootloader via a USB-NVMe adapter (product page)
- Boots on Raspberry Pi 400 (product page)
- Boots on Compute Module 4 on an NVMe carrier, e.g. CM4 Maker Board (product page)
- HAT+, USB-NVMe adapter and CM4 carrier are requirements, not included
- Needs an M.2 slot with a 2242 mounting position; the M-Key (256GB/512GB) units do not fit B-Key sockets
- Cytron tutorials linked: Raspberry Pi Imager updating bootloader; Clone Raspberry Pi OS into SSD; CM4 Maker Board getting started

## Use cases
- Boot drive for Raspberry Pi 5 (via PCIe-to-M.2 HAT+)
- Boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400 (via USB-NVMe adapter)
- Boot drive for Compute Module 4 on an NVMe carrier such as the CM4 Maker Board

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded Raspberry Pi OS
- NVMe (PCIe) only; not usable in M.2 SATA slots or SATA adapters
- 128GB is B+M-Key and PCIe Gen3 x2; 256GB/512GB are M-Key and PCIe Gen3 x4 — speeds and keys differ by capacity
- Raspberry Pi 5 needs the latest bootloader and a PCIe-to-M.2 HAT+; Raspberry Pi 4 B needs the latest bootloader and a USB-NVMe adapter
- Datasheet speed figures have no stated test conditions and are not Raspberry Pi measurements
- OS image on units shipped before January 2024: [NOT STATED]

## Positioning (kept apart from specs)
- Product page: Jeff Geerling verified the drive on Raspberry Pi 5
- Ready-to-boot storage for Raspberry Pi — plug in and boot, no imaging needed (product page framing)

## Price band
RM739.00 shown for the default option (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-nvme-2242-b-plus-m-key-makerdisk-ssd-preloaded-rpi-os

## Datasheet
https://docs.google.com/document/d/14tFhPy47Aa8ugKsBqsc8-0nyJH_La1EbLZbW4Ooeg_w/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/14tFhPy47Aa8ugKsBqsc8-0nyJH_La1EbLZbW4Ooeg_w/edit
