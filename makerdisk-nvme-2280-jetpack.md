# NVMe 2280 MakerDisk SSD - JetPack for Jetson Orin Nano Super — Verified Reference

| Field | Value |
|---|---|
| Product code | V-MMR-NV2280-JP (product page, both capacities) [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
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
| PCIe generation / lane count, NVMe version, NAND, controller, speed, power, temperature, MTBF, TBW, weight, warranty, packing list | Not stated in any Cytron source read | — |
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
- Preloaded: NVIDIA JetPack 6.2 with SDK components (CUDA, TensorRT, cuDNN, DeepStream etc. are JetPack 6.x components per the Cytron upgrade-service page; the exact list preloaded on the drive is not stated) [PP].
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
| None found — only one Cytron source (the product page) was readable. | — | — | — |

## Needs verification
- Hardware specs of the drive (PCIe gen/lanes, NVMe version, NAND, controller, read/write speed, power, temperature, MTBF, TBW, weight): no Cytron source; whether the hardware is identical to V-MMR-NV2280 is not stated.
- Exact list of preloaded SDK components and the JetPack build on units shipped before 6 February 2025.
- Mapping "JetPack 6.2 = Jetson Linux r36.4.3": [VEN] NVIDIA numbering; confirm against the linked release notes before quoting.
- Whether the drive boots on the original (non-Super) Jetson Orin Nano Developer Kit after its firmware is upgraded to 36.x: the page says Super Dev Kit (8GB) ONLY; the upgrade service implies the upgraded original kit becomes "Super" — ask the product team before stating either.
- Tutorial "Upgrade Jetson Orin Nano to Super using NVIDIA SDK Manager": title, author, date and steps not verified (my.cytron.io, www.cytron.io and web.archive.org fetches blocked in this session).
- Warranty and packing list: not stated.

## Sources
- [PP] Product page "NVMe 2280 MakerDisk SSD - JetPack for Jetson Orin Nano Super" — https://my.cytron.io/p-nvme-2280-m-key-makerdisk-ssd-preloaded-with-jetpack (read by the coordinator 2026-10-19; text in the coordinator's product-page extract)
- [PP] Tutorial linked on the page (not fetched): https://my.cytron.io/tutorial/upgrade-jetson-orin-nano-to-super-using-nvidia-sdk-manager
- [PP] Related Cytron pages in the same extract: Flash JetPack Service SEV-JN-ORNN — https://my.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x ; Jetson Orin Nano workshop — https://my.cytron.io/p-jetson-orin-nano-ai-fundamentals-hands-on-workshop-with-nvidia-certification-v
- KB cross-reference: /home/claude/kb/makerdisk-nvme-2280.md
