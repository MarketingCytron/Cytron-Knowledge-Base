# Flash Jetpack Service / Orin Nano Upgrade Service — Verified Reference

| | |
|---|---|
| Product code | `SEV-JN-ORNN` [PP] |
| Family | Workshops and services |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 (product page facts read 2026-10-19) |
| Primary source | **No datasheet exists (this is a service).** Highest source read is the Cytron Getting Started doc linked from the page: "Getting Started Guide - Computer Vision AI Training Kit with NVidia Jetson Orin Nano" (Google Doc, no version or date printed) [UM], which describes the training-kit software the service relates to but does not describe the flashing itself; the service terms come from the product page https://my.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A software-only service in which Cytron upgrades a customer's NVIDIA Jetson Orin Nano from JetPack 5.x to JetPack 6.x [PP]. The upgrade brings the latest CUDA, TensorRT, cuDNN and DeepStream, and enables the new 25W power mode ("Super" performance), which NVIDIA states gives up to 70% more generative AI performance [PP]. No hardware is included [PP]. The page lists it at RM150.00 and sells it by enquiry ("Inquire Now") [PP].

## Specifications
Service / logistics table.

| Item | Value | Src |
|---|---|---|
| Product name | Flash Jetpack Service / Orin Nano Upgrade Service | [PP] |
| Page title wording | Jetson Orin Nano Upgrade Service (JetPack 5.x to JetPack 6.x) — from the URL slug | [PP] |
| Product code | SEV-JN-ORNN | [PP] |
| Type | Software-only service; no hardware included | [PP] |
| Target device | NVIDIA Jetson Orin Nano | [PP] |
| From | JetPack 5.x | [PP] |
| To | JetPack 6.x | [PP] |
| What the upgrade delivers | Latest CUDA, TensorRT, cuDNN, DeepStream; new 25W power mode ("Super" performance); up to 70% more generative AI performance (NVIDIA figure quoted on page) | [PP] |
| Price | RM150.00 | [PP] |
| Availability | Enquiry ("Inquire Now") | [PP] |
| Exact JetPack 6.x point release flashed | Not stated on this page | — |
| Turnaround, shipping, data backup, warranty on the service | Not stated in any source read | — |
| Linked documents | NVIDIA Jetson Orin Nano Series datasheet (Drive) [VEN]; Jetson Orin Nano Training Kit Getting Started Guide (Google Doc) [UM] | [PP] |

## Interfaces, terminals and pin mapping
Not applicable (service). Relevant software facts: the service changes the JetPack release (BSP, CUDA, TensorRT, cuDNN, DeepStream) and enables the 25W "Super" power mode [PP]. Related Cytron context [PP-MD]: Cytron's MakerDisk NVMe 2280 SSD preloaded with JetPack 6.2 "cannot be used on Orin Nano with firmware < 36.0 (JetPack 5.x)", which is the situation this service resolves by moving the board to JetPack 6.x firmware.

## Rules and gotchas (for code, wiring and tutorials)
- It is a service, not a product: "software-only", "no hardware included" [PP]. Do not list a kit, a cable or an SSD as part of it.
- The upgrade path is JetPack 5.x → JetPack 6.x [PP]. Do not write a specific 6.x point release (6.0, 6.1, 6.2) as the service's target; none is stated on the page.
- The "Super" performance / 25W power mode and the "up to 70% more generative AI performance" claim are NVIDIA's figures as quoted on the page [PP]; attribute them to NVIDIA.
- A Jetson Orin Nano still on JetPack 5.x firmware (below 36.0) cannot boot Cytron's JetPack 6.2 MakerDisk SSD [PP-MD]; this service is the route for those boards.
- The linked Getting Started Guide [UM] describes the Cytron "Computer Vision AI Training Kit with NVidia Jetson Orin Nano": chapters on AI/DL concepts, the Orin Nano Developer Kit tour, connecting peripherals, login and updates, the jetson-inference Docker container, image classification, object detection and semantic segmentation. It does not state which JetPack it was written for, and it does not describe the flashing procedure. Do not cite it as the source of the service's JetPack version.
- Never copy the default login printed in the Getting Started Guide into any content.
- Price is RM150.00 but the item is enquiry-only [PP]; content should say "RM150, by enquiry" rather than "add to cart".

## Power and electrical limits
Not applicable (service). JetPack 6.x enables a 25W power mode on the Jetson Orin Nano [PP]. For the Developer Kit hardware, the Getting Started Guide's Appendix D lists module power as 7W to 15W and a 19V DC barrel jack input [UM]; that appendix predates the 25W "Super" mode and should not be quoted as the post-upgrade limit (see Conflicts).

## Software support
- JetPack 6.x with CUDA, TensorRT, cuDNN and DeepStream [PP].
- After the upgrade the board is on the firmware family (36.x) required by Cytron's JetPack 6.2 MakerDisk SSD [PP-MD].
- The Getting Started Guide uses the `dusty-nv/jetson-inference` Docker container (`docker/run.sh`), `imagenet.py`, `detectnet.py`, `segnet.py`, `nvgstcapture-1.0` camera test, and `sudo apt update` / `sudo apt full-upgrade -y` for updates [UM].
- A Cytron tutorial on upgrading the Orin Nano to the "super-powered" version exists on my.cytron.io (slug `upgrade-your-jetson-orin-nano-to-the-super-powered-version`, noted in an internal content schedule) but could not be read here.

## Compatibility and accessories
- Applies to the NVIDIA Jetson Orin Nano [PP]. Whether the Orin Nano 4GB module, Orin NX or third-party carrier boards are accepted is not stated.
- Related Cytron products: MakerDisk NVMe 2280 SSD preloaded with JetPack 6.2 (V-MMR-NV2280-JP) [PP-MD]; Jetson Orin Nano Training Kit (the Getting Started Guide's subject) [UM].

## Common mistakes / troubleshooting
- Describing the service as including a new SSD or new JetPack media: it is software-only, no hardware [PP].
- Stating the exact JetPack 6.x version, turnaround time or warranty: none is stated.
- Quoting the 70% figure as Cytron's own measurement: it is NVIDIA's figure [PP].
- Assuming a JetPack-6.2 SSD will fix a JetPack 5.x board without this (or an equivalent) firmware upgrade [PP-MD].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Orin Nano power envelope | Getting Started Guide Appendix D: module power 7W to 15W [UM] | Product page: JetPack 6.x adds a new 25W power mode [PP] | Not a true contradiction: the guide's appendix describes the original Developer Kit spec; the 25W mode is introduced with JetPack 6.x ("Super"). State both with their context. |
| Product naming | Store name "Flash Jetpack Service / Orin Nano Upgrade Service" [PP] | URL slug "jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x" [PP] | Same source; use the store name and give the slug as the URL. |

## Needs verification
- Exact JetPack 6.x release flashed at the time of service, and whether the customer can choose.
- How the service is delivered: send-in to Cytron, drop-off, or on-site; turnaround time; return shipping cost.
- Whether customer data on the board/SSD is preserved or wiped, and whether an NVMe SSD or microSD is flashed as well as the QSPI firmware.
- Whether the service covers the Orin Nano 4GB module, the Orin NX, or only the 8GB Developer Kit.
- Any warranty or support period on the service.
- Version/date of the Getting Started Guide (none printed), and which JetPack it targets.
- Content of the linked NVIDIA Jetson Orin Nano Series datasheet (not read).

## Sources
- [UM] Getting Started Guide - Computer Vision AI Training Kit with NVidia Jetson Orin Nano — Cytron Google Doc: https://docs.google.com/document/d/1Q5HOeChMO71il4RFB5OU7TqOwTYqv4niRN7_iJiAryM/edit
- [PP] Product page (facts supplied by coordinator, read 2026-10-19): https://my.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x
- [PP-MD] Related product page facts (coordinator, read 2026-10-19): https://my.cytron.io/p-nvme-2280-m-key-makerdisk-ssd-preloaded-with-jetpack
- [VEN] NVIDIA Jetson Orin Nano Series datasheet, DS-11105-001 v1.0 (Drive PDF linked from the page, not read): https://drive.google.com/file/d/1fNdS32r32GxRfeWPfMnnwjSJjS_IZoLI/view
- Blocked (not read): https://www.cytron.io/p-jetson-orin-nano-upgrade-service-jetpack-5.x-to-jetpack-6.x ; https://my.cytron.io/tutorial/upgrade-your-jetson-orin-nano-to-the-super-powered-version
