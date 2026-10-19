# 120GB 2.5-inch MakerDisk SATA III SSD with RPi OS — Verified Reference

| Field | Value |
|---|---|
| Product code | MMR-2P5-MD-120 [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: read the product-page images — the Cytron drive label (shock 1500G/0.5ms, 0–70 °C commercial, SMART & TRIM, 1-year warranty, Made in Taiwan), the Raspberry Pi Diagnostics screenshot, the test-setup photo (Raspberry Pi 4 Model B + USB3-SATA adapter) and the microSD vs MakerDisk table. Reseller-only facts now confirmed by the label |
| Primary source | Cytron product page "120GB 2.5-inch MakerDisk SATA III SSD with RPi OS", read 2026-10-19 [PP] — the page links no documents; no datasheet was found in Cytron's Google Drive (searches for "MakerDisk", "SATA", "SSD", "MMR-2P5") |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A Cytron-branded 120GB 2.5-inch SATA III (6.0 Gbps) solid-state drive sold with Raspberry Pi OS 64-bit Bookworm already written to it [PP]. Because no Raspberry Pi has a SATA port, it connects to the Pi over USB through a SATA-to-USB bridge (an SSD shield or a USB 3.0-to-SATA adapter) and boots a Raspberry Pi 5, Pi 4 Model B or Pi 400 that has the latest bootloader and USB boot enabled [PP]. It is the SATA member of the MakerDisk range; the NVMe members are M.2 drives (makerdisk-nvme-2242.md, makerdisk-nvme-2280.md).

## Specifications
No Cytron datasheet exists for this product; every row below comes from the product page text read on 2026-10-19 [PP].

| Item | Value | Src |
|---|---|---|
| Product code | MMR-2P5-MD-120 | [PP] |
| Form factor | 2.5-inch | [PP] |
| Interface | SATA III (6.0 Gbps) | [PP] |
| Capacity | 120GB (single option) | [PP] |
| Preloaded OS | Raspberry Pi OS 64-bit Bookworm, on units shipped from 1 November 2023 | [PP] |
| Max sequential read | up to 550MB/s | [PP] |
| Max sequential write | up to 460MB/s | [PP] |
| Test conditions for the max figures | Not stated (manufacturer maximum, host not named) | [PP] |
| Raspberry Pi Diagnostics — sequential write | 224438 KB/s (connected via USB3-SATA) | [PP] |
| Raspberry Pi Diagnostics — random write | 23744 IOPS (via USB3-SATA) | [PP] |
| Raspberry Pi Diagnostics — random read | 17102 IOPS (via USB3-SATA) | [PP] |
| Raspberry Pi Diagnostics run | Version 0.13, 23 Oct 2023, Test PASS (targets: 10000 KB/s seq. write, 500 IOPS random write, 1500 IOPS random read) | [PP: img] |
| Raspberry Pi Diagnostics host board | Raspberry Pi 4 Model B, drive on a USB 3.0-to-SATA adapter in a blue USB 3.0 port (test-setup photo) | [PP: photo] |
| Comparison table (Cytron) | Phidisk 128GB microSD ≈27 MB/s seq. write, ≈1000 / ≈2300 IOPS; MakerDisk 120GB 2.5" SSD ≈224 MB/s, ≈24000 / ≈17000 IOPS | [PP: img] |
| Label — headline | MakerDisk SSD 120GB; 2.5" SATA Solid State Drive; SATA III 6Gbps | [PP: img] |
| Label — specs | Read speed up to 550MB/s; write speed up to 460MB/s; host interface SATA III; SMART & TRIM support; shock 1500G/0.5ms; compatible with Windows, Linux, Raspberry Pi; operation temp 0 °C–70 °C (commercial) | [PP: img] |
| Label — marks | RoHS, FC, CE; Made in Taiwan; ESD warning; "1GB = 1,000,000,000 bytes. Actual usable capacity may be less" | [PP: img] |
| Warranty | 1 Year Limited Warranty; void if label removed or case opened (printed on the label) | [PP: img] |
| NAND type, controller, DRAM, power, MTBF, TBW, exact dimensions, weight, packing list | Not stated in any Cytron source read | — |
| Price | RM118.80 special offer, was RM158.40 (Cytron product page, read 2026-10-19) | [PP] |
| Stock | Availability 17 (2026-10-19) | [PP] |

## Interfaces, terminals and pin mapping
- Standard 2.5-inch SATA drive connector (SATA data + SATA power, 22-pin) [PP: "2.5-inch SATA III"].
- To a Raspberry Pi: via a SATA-to-USB bridge — the page names an SSD shield or a USB3-SATA adapter [PP]. The bridge is not included.
- Link rate: SATA III, 6.0 Gbps [PP]; the real throughput on a Pi is bounded by the USB bridge (see the Diagnostics figures above).

## Rules and gotchas (for code, wiring and tutorials)
- **DO NOT format the drive** if it is meant to boot a Raspberry Pi — the page says "DO NOT format" [PP].
- **It is SATA, not NVMe.** It does not fit any M.2 slot or PCIe HAT; it needs a USB-SATA bridge on every Raspberry Pi [PP]. Do not pair it with a Pi 5 PCIe-to-M.2 HAT in a tutorial.
- **Boot path is USB boot.** Raspberry Pi 5, Pi 4 Model B and Pi 400 need the latest bootloader (USB boot enabled) [PP]. The page text read does not mention Compute Module 4 or earlier Pi models.
- **Speed claims:** "up to 550MB/s / 460MB/s" are the drive's SATA maxima [PP]; the Pi-measured figures via USB3-SATA are 224438 KB/s sequential write, 23744 IOPS random write, 17102 IOPS random read [PP]. Quote the Pi figures for Pi content, and name the USB3-SATA path.
- **Price:** RM118.80 is a special-offer price (was RM158.40) [PP] — re-check before quoting.
- **Do not open the case or peel the label:** the label says the warranty is void if the label is removed or the case is opened [PP: img].
- Operating temperature is **commercial 0–70 °C** [PP: img] — not for outdoor or industrial enclosures without checking.
- An older reseller listing describes the preloaded OS as Bullseye and names only Pi 4 B / Pi 400 [3P]; the current Cytron page says Bookworm from 1 November 2023 and adds Pi 5 [PP]. Use the Cytron page.

## Power and electrical limits
- Not stated in any Cytron source read. A 2.5-inch SATA SSD is powered through its SATA power pins, which on a Pi come from the USB-SATA bridge; the bridge's and the Pi's USB current budget apply (figures not given by Cytron).

## Software support
- Preloaded Raspberry Pi OS 64-bit Bookworm on units shipped from 1 November 2023 [PP]. Units shipped earlier may carry an older image (a reseller's older copy of the page says Bullseye [3P]) — treat the pre-November-2023 image as unverified.
- No Cytron software, driver or firmware is associated with the drive; it appears as a USB mass-storage device through the bridge.
- No tutorial is linked from the page in the text read [PP].

## Compatibility and accessories
- Boots on: Raspberry Pi 5, Raspberry Pi 4 Model B, Raspberry Pi 400 — all with the latest bootloader, via USB boot through an SSD shield or USB3-SATA adapter [PP].
- Required but not included: SATA-to-USB bridge (SSD shield or USB 3.0-to-SATA adapter) [PP].
- Not usable in: M.2 slots, PCIe HATs, CM4 NVMe carriers (it is a 2.5-inch SATA drive) [PP].
- Sibling products: NVMe 2242 MakerDisk (makerdisk-nvme-2242.md), NVMe 2280 MakerDisk (makerdisk-nvme-2280.md).

## Common mistakes / troubleshooting
- **Pi does not boot from it:** confirm the bootloader is current and USB boot is enabled; confirm the drive is connected through a USB3-SATA bridge [PP].
- **Drive formatted / OS gone:** the preloaded OS is lost; re-imaging is possible but not described by any source read.
- **Calling it NVMe or M.2:** it is a 2.5-inch SATA III drive [PP].
- **Quoting 550MB/s as Pi performance:** the Pi-measured sequential write via USB3-SATA is 224438 KB/s [PP].
- **Quoting the old price:** RM158.40 was the pre-offer price; RM118.80 is the offer on 2026-10-19 [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Preloaded OS version | Cytron page: Raspberry Pi OS 64-bit Bookworm from 1 Nov 2023 [PP] | Opencircuit reseller copy: "latest Raspberry Pi OS - Bullseye" [3P] | Cytron page wins; the reseller text is an older copy. Pre-Nov-2023 units may be Bullseye (unverified). |
| Boards that boot from it | Cytron page: Pi 5, Pi 4 B, Pi 400 [PP] | Opencircuit: Pi 4 B (latest bootloader) or Pi 400 [3P] | Cytron page wins (newer, includes Pi 5). |
| Shock / temperature / SMART & TRIM | Previously reseller-only [3P] | Cytron drive label: 1500G/0.5ms, 0–70 °C commercial, SMART & TRIM [PP: img] | Now confirmed by Cytron's own label; stated as spec. |

## Needs verification
- NAND type, controller, DRAM, power draw, exact dimensions, weight, packing list: not stated.
- Compute Module 4 / Pi 3 / Pi Zero compatibility: not stated by Cytron (the label says only "Raspberry Pi").
- Which Cytron "SSD shield" the page refers to (product name/code): not captured in the text read.
- OS image on units shipped before 1 November 2023: unverified (reseller copy says Bullseye [3P]).

## Sources
- [PP] Product page "120GB 2.5-inch MakerDisk SATA III SSD with RPi OS" — https://my.cytron.io/p-120gb-2p5-inch-makerdisk-sata-3-ssd-with-raspberry-pi-os (read by the coordinator 2026-10-19; text in the coordinator's product-page extract)
- [3P] Opencircuit listing "Cytron 120GB 2.5-inch MakerDisk SATA III SSD with RPi OS" — https://opencircuit.shop/product/120gb-2.5-inch-makerdisk-sata-iii-ssd-rpi-os (cross-check only)
- KB cross-references: /home/claude/kb/makerdisk-nvme-2242.md ; /home/claude/kb/makerdisk-nvme-2280.md
