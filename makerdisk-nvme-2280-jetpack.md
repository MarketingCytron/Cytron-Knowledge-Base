# NVMe 2280 MakerDisk SSD - JetPack for Jetson Orin Nano Super — Verified Reference

| Field | Value |
|---|---|
| Product code | V-MMR-NV2280-JP (product page, both capacities) [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: read the product-page images — 512GB and 256GB drive labels (same labels as the Raspberry Pi OS MakerDisk: PCIe Gen 3 x4, NVMe 1.3, 1-year warranty), the 128GB drive fitted in an Orin Nano carrier, the SDK Manager component list for JetPack 6.2, and the UEFI firmware screen. Login screenshots deliberately not transcribed |
| Primary source | Cytron product page "NVMe 2280 MakerDisk SSD - JetPack for Jetson Orin Nano Super", read 2026-10-19 [PP] — no Cytron datasheet is linked and none was found in Google Drive; the linked tutorial (upgrade Jetson Orin Nano to Super using NVIDIA SDK Manager) could not be fetched in this session |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A Cytron-branded M.2 2280 NVMe solid-state drive sold with NVIDIA JetPack 6.2 already installed, intended ONLY for the NVIDIA Jetson Orin Nano Super Developer Kit (8GB) [PP]. The user fits it into the NVMe slot on the back of the Orin Nano carrier board and boots; the SDK components are preloaded, so no SDK Manager flashing of the OS is needed [PP]. It ships with a pre-configured login (default login printed on the product page — never copy it into content) [PP]. Capacities: 512GB and 256GB [PP]. It is the JetPack sibling of the Raspberry Pi OS 2280 MakerDisk (makerdisk-nvme-2280.md); the two are not interchangeable because of the preloaded OS.

## Specifications
No Cytron datasheet exists for this product; every row below comes from the product page text read on 2026-10-19 [PP].

| Item | Value | Src |
|---|---|---|
| Product code | V-MMR-NV2280-JP | [PP] |
| Form factor | M.2 2280 | [PP] |
| Key | M-Key (product page URL "nvme-2280-m-key-makerdisk-ssd-preloaded-with-jetpack"); the Orin Nano carrier's NVMe slot is M-Key | [PP] |
| Interface | NVMe (PCIe) | [PP] |
| Capacities | 512GB / 256GB | [PP] |
| Preloaded software | NVIDIA JetPack 6.2 with SDK components preloaded, on units shipped from 6 February 2025 | [PP] |
| Target device | NVIDIA Jetson Orin Nano Super Developer Kit (8GB) ONLY | [PP] |
| Firmware requirement | Cannot be used on an Orin Nano whose firmware is below 36.0 (i.e. still on JetPack 5.x firmware) | [PP] |
| Installation | Insert into the NVMe slot on the back of the carrier board at 45°, then screw down | [PP] |
| Linked NVIDIA document | NVIDIA Jetson Linux r36.4.3 release notes | [PP] |
| Label — 512GB | NVMe 2280 M-Key M.2 MakerDisk SSD; PCIe Gen 3 x4, PCI Express Base 3.1, NVMe 1.3; read up to 2050 MB/s, write up to 1700 MB/s | [PP: img] |
| Label — 256GB | PCIe Gen 3 x4, PCI Express Base 3.1, NVMe 1.3; read up to 2050 MB/s, write up to 1000 MB/s | [PP: img] |
| Label — both | SMART & TRIM supported; Advanced Flash Management; RoHS, FC, CE; Made in Taiwan; warranty void if removed | [PP: img] |
| Warranty | 1 Year Limited Warranty (printed on the drive label) | [PP: img] |
| Size | M.2 2280 = 22 × 80 mm | [PP: img, size chart on sibling page] |
| SDK Manager screen shown | "JetPack 6.2 Linux for Jetson Orin Nano [8GB Developer Kit version]": Jetson Linux image; Runtime — CUDA Runtime, CUDA-X AI Runtime, Computer Vision Runtime, NVIDIA Container Runtime, Multimedia; SDK — CUDA, CUDA-X AI, Computer Vision, Developer Tools, DeepStream, GXF; Jetson Platform Services | [PP: img] |
| NAND, controller, power, temperature, MTBF, TBW, weight, packing list | Not stated in any Cytron source read | — |
| Price | RM469.00 – RM739.00 across the two capacities (Cytron product page, read 2026-10-19) | [PP] |
| Stock | Availability 4 (2026-10-19) | [PP] |

## Interfaces, terminals and pin mapping
- Connector: M.2 2280 NVMe edge connector; fits the NVMe slot on the underside of the Jetson Orin Nano Developer Kit carrier board [PP].
- Fitting: insert at 45° into the slot, press down, secure with the screw [PP].
- No other terminals.

## Rules and gotchas (for code, wiring and tutorials)
- **Only for the Jetson Orin Nano Super Developer Kit (8GB)** [PP]. Do not describe it as working on Jetson Nano, Orin NX, AGX Orin, Raspberry Pi or any PC — the page states "ONLY".
- **Firmware must be 36.0 or newer.** An Orin Nano still on JetPack 5.x firmware (below 36.0) cannot boot this drive [PP]. The board firmware (QSPI bootloader/UEFI) must first be upgraded to JetPack 6.x — Cytron links its "upgrade Jetson Orin Nano to Super using NVIDIA SDK Manager" tutorial and sells a flash/upgrade service (SEV-JN-ORNN, JetPack 5.x to 6.x) for this [PP].
- **DO NOT format the drive** — formatting erases the preloaded JetPack 6.2 [PP].
- **JetPack version is 6.2** on units shipped from 6 February 2025 [PP]; earlier units may carry a different JetPack — not stated. The page links the Jetson Linux r36.4.3 release notes [PP]; JetPack 6.2 corresponds to Jetson Linux r36.4.3 in NVIDIA's numbering [VEN].
- The page also links tutorials on JetPack 7.2 installation, F5-TTS and Jetson device skills [PP]; the drive as shipped carries JetPack 6.2, so a JetPack 7.x tutorial implies re-flashing — do not imply the drive ships with 7.x.

## Power and electrical limits
- Not stated in any Cytron source read. The drive draws power from the carrier board's M.2 slot.

## Software support
- Preloaded: NVIDIA JetPack 6.2 with SDK components [PP]. The page's SDK Manager screenshot shows the JetPack 6.2 selection for the Orin Nano 8GB Developer Kit: Jetson Linux image; runtime components (CUDA Runtime, CUDA-X AI Runtime, Computer Vision Runtime, NVIDIA Container Runtime, Multimedia); SDK components (CUDA, CUDA-X AI, Computer Vision, Developer Tools, DeepStream, GXF); Jetson Platform Services [PP: img].
- Pre-configured user account; default login printed on the product page [PP].
- Related Cytron tutorials linked from the page [PP]: "Upgrade Jetson Orin Nano to Super using NVIDIA SDK Manager" (https://my.cytron.io/tutorial/upgrade-jetson-orin-nano-to-super-using-nvidia-sdk-manager), JetPack 7.2 install, F5-TTS, Jetson device skills — none readable in this session.
- NVIDIA references linked: Jetson Linux r36.4.3 release notes [PP].

## Compatibility and accessories
- Compatible: NVIDIA Jetson Orin Nano Super Developer Kit (8GB) with firmware ≥ 36.0 [PP].
- Not compatible: Orin Nano with firmware < 36.0 (JetPack 5.x) until upgraded [PP]; any non-Jetson host for the preloaded OS (the page restricts it to the Orin Nano Super Dev Kit ONLY) [PP].
- Related Cytron items: Flash JetPack / Orin Nano Upgrade Service SEV-JN-ORNN (software-only JetPack 5.x to 6.x upgrade) [PP]; the Jetson Orin Nano AI Fundamentals workshop kit includes a "NVMe 2280 MakerDisk SSD 512GB (JetPack)" [PP, workshop page].
- Sibling: NVMe 2280 MakerDisk with Raspberry Pi OS, V-MMR-NV2280 (makerdisk-nvme-2280.md).

## Common mistakes / troubleshooting
- **Board does not boot from the drive:** check the firmware version first — below 36.0 is unsupported [PP]; upgrade with SDK Manager (Cytron tutorial) or Cytron's upgrade service.
- **Formatted the drive:** the preloaded JetPack is gone; a fresh JetPack install via SDK Manager is needed (procedure not in any source read).
- **Copying the login into a tutorial or post:** never — refer to the product page.
- **Ordering the wrong 2280:** V-MMR-NV2280 (Raspberry Pi OS) vs V-MMR-NV2280-JP (JetPack). Same form factor, different OS.
- **Claiming Jetson Nano / Orin NX support:** the page says Orin Nano Super Dev Kit (8GB) ONLY [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Hardware vs the Raspberry Pi OS MakerDisk | Not stated in page text [PP] | 512GB and 256GB labels are identical to the V-MMR-NV2280 labels [PP: img] | Treat the drive hardware as the same NVMe 2280 MakerDisk; only the preloaded OS differs. |

## Needs verification
- NAND, controller, power, temperature, MTBF, TBW and weight: no Cytron source.
- JetPack build on units shipped before 6 February 2025.
- Mapping "JetPack 6.2 = Jetson Linux r36.4.3": [VEN] NVIDIA numbering; confirm against the linked release notes before quoting.
- Whether the drive boots on the original (non-Super) Jetson Orin Nano Developer Kit after its firmware is upgraded to 36.x: the page says Super Dev Kit (8GB) ONLY; the upgrade service implies the upgraded original kit becomes "Super" — ask the product team before stating either.
- Tutorial "Upgrade Jetson Orin Nano to Super using NVIDIA SDK Manager": author, date and steps not read.
- What the page's UEFI firmware screenshot (Jetson UEFI firmware 3.0, built 2023-02-21) is meant to illustrate — most likely an old (JetPack 5.x) firmware that must be upgraded; confirm before quoting.
- Packing list: not stated (assume drive only).

## Sources
- [PP] Product page "NVMe 2280 MakerDisk SSD - JetPack for Jetson Orin Nano Super" — https://my.cytron.io/p-nvme-2280-m-key-makerdisk-ssd-preloaded-with-jetpack (read by the coordinator 2026-10-19; text in the coordinator's product-page extract)
- [PP] Tutorial linked on the page (not fetched): https://my.cytron.io/tutorial/upgrade-jetson-orin-nano-to-super-using-nvidia-sdk-manager
- [PP] Related Cytron pages in the same extract: Flash JetPack Service SEV-JN-ORNN — https://my.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x ; Jetson Orin Nano workshop — https://my.cytron.io/p-jetson-orin-nano-ai-fundamentals-hands-on-workshop-with-nvidia-certification-v
- KB cross-reference: /home/claude/kb/makerdisk-nvme-2280.md
