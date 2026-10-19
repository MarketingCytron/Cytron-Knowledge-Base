# Product fact sheets

## Product name
120GB 2.5-inch MakerDisk SATA III SSD with RPi OS

## Aliases
MMR-2P5-MD-120, MakerDisk SATA 120GB, MakerDisk 2.5-inch SATA SSD, 120GB MakerDisk SATA III SSD, MakerDisk SATA SSD with RPi OS

## What it is
A Cytron-branded 120GB 2.5-inch SATA III solid-state drive that ships with Raspberry Pi OS 64-bit Bookworm already written to it. It connects to a Raspberry Pi 5, Pi 4 Model B or Pi 400 through a SATA-to-USB bridge and boots over USB.

## Specs and functions
- Product code: MMR-2P5-MD-120
- Form factor: 2.5-inch
- Interface: SATA III (6.0 Gbps)
- Capacity: 120GB
- Preloaded OS: Raspberry Pi OS 64-bit Bookworm, on units shipped from 1 November 2023
- Max sequential read: up to 550MB/s
- Max sequential write: up to 460MB/s
- Test conditions for the max figures: [NOT STATED]
- Raspberry Pi Diagnostics via USB3-SATA: sequential write 224438 KB/s; random write 23744 IOPS; random read 17102 IOPS
- Raspberry Pi Diagnostics host board: [NOT STATED]
- NAND type, controller, power consumption, operating temperature, MTBF, TBW: [NOT STATED]
- Dimensions, weight, warranty, packing list: [NOT STATED]
- Datasheet: none published

## Interfaces and compatibility
- Boots on Raspberry Pi 5, Raspberry Pi 4 Model B and Raspberry Pi 400 with the latest bootloader (USB boot)
- Connects through a SATA-to-USB bridge: SSD shield or USB 3.0-to-SATA adapter (not included)
- Not usable in M.2 slots, PCIe HATs or CM4 NVMe carriers — it is a 2.5-inch SATA drive
- Compute Module 4 and other Raspberry Pi models: [NOT STATED]

## Use cases
- USB boot drive for Raspberry Pi 5
- USB boot drive for Raspberry Pi 4 Model B / Raspberry Pi 400

## Known limitations
- DO NOT format it if it is meant to boot a Raspberry Pi — formatting removes the preloaded OS
- SATA, not NVMe; needs a USB-SATA bridge on every Raspberry Pi
- Requires the latest bootloader with USB boot on the Pi
- Pi-measured throughput via USB3-SATA (224438 KB/s sequential write) is far below the drive's 550MB/s / 460MB/s SATA maxima
- OS image on units shipped before 1 November 2023: [NOT STATED]

## Positioning (kept apart from specs)
- Ready-to-boot Raspberry Pi OS SSD for USB boot (product page framing)

## Price band
RM118.80 special offer, was RM158.40 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-120gb-2p5-inch-makerdisk-sata-3-ssd-with-raspberry-pi-os

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-120gb-2p5-inch-makerdisk-sata-3-ssd-with-raspberry-pi-os
