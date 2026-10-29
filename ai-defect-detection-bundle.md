# AI Defect Detection Bundle — Verified Reference

| | |
|---|---|
| Product code | `KIT-AI-DEFECT` [PP] (MPN blank on the page) |
| Family | AI vision kits (Raspberry Pi) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-29 |
| Reviewed | 2026-10-29 — new product added: product page read in full (description, features/specifications, packing list, resources), packing image viewed, linked component pages checked for names and codes, both Cytron tutorials read in full |
| Primary source | No kit datasheet or manual exists. Kit rule (INDEX rule 7): **product page packing list first** — https://my.cytron.io/p-ai-defect-detection-kit, read 2026-10-29 [PP] — then the Cytron tutorials **"Getting Started with Raspberry Pi AI Defect Detection Kit"** (02 Dec 2024) [PP: tutorial 1] and **"Raspberry Pi AI Defect Detection Kit: Use Your Own Dataset"** (06 Dec 2024) [PP: tutorial 2] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = product page text, read in the browser 2026-10-29. [PP: img] = the page's packing image `npi-product-73.png`. [PP: links] = the component product pages the packing list links to (title, code and brand only, read 2026-10-29). [PP: tutorial 1] / [PP: tutorial 2] = the two Cytron tutorials above, read in full 2026-10-29. KIT RULE: the Raspberry Pi 5, AI HAT+, Camera Module 3, PSU, cooler, FPC cable and camera case are third-party products with no KB file and are not documented here beyond what the kit sources say. The USB microSD reader has its own KB file (`cytron-microsd-card-reader.md`).

## What it is
- A ready-to-run **AI visual defect-detection kit** built on **Raspberry Pi 5 (4GB)** and the **Raspberry Pi AI HAT+ (13 TOPS)** with a **Raspberry Pi Camera Module 3**, for engineers building a **Proof of Concept (POC)** [PP]; the page meta description also names **FYP** (final year) projects [PP].
- Ships with a **custom Raspberry Pi OS preinstalled on a 64GB microSD card** that holds "all necessary libraries, dependencies, and a precompiled set of trained datasets" — no manual setup [PP].
- The defect model is **YOLOv8**, trained by Cytron, converted **PyTorch → ONNX → HEF** (Hailo Executable Format) to run on the AI HAT+; detection runs in "an OpenCV-based real-time detection system" [PP].
- Includes **2 × Defect Material** samples to test the system [PP].
- Store category: Industry (my.cytron.io/c-industry, read 2026-10-29) [PP]. Warranty 12 months [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Computer | Raspberry Pi 5 – 4GB RAM | [PP] |
| AI accelerator | Raspberry Pi AI HAT+ – 13 TOPS | [PP] |
| Camera | Raspberry Pi Camera Module 3 – 12MP, 75 degree, auto focus | [PP] |
| Camera cable | CSI cable 50 cm (FPC 22-way to 15-way) | [PP] |
| Storage | microSD card 64GB, preloaded with the custom Raspberry Pi OS | [PP] |
| Power supply | UK plug, 5V / 5A, 27W, Power Delivery (Raspberry Pi 27W PD USB-C PSU) | [PP] |
| AI model | YOLOv8, pre-trained on Cytron's defect dataset; HEF format | [PP] |
| Model files (tutorial) | `resources/cytron.hef`, `resources/cytron-labels.json` | [PP: tutorial 1] |
| Defect classes detected | Not stated | — |
| Detection accuracy / frame rate | Not stated | — |
| OS base and version | Not stated ("custom Raspberry Pi OS") | — |
| Price | RM1,207.50; cashback RM34.50 | [PP] |
| Stock (2026-10-29) | 3 | [PP] |
| Warranty | 12 months | [PP] |

### Packing list (product page, as stated) [PP]
| Qty | Item | Linked page (code, brand) [PP: links] |
|---|---|---|
| 1 | Raspberry Pi 5 with 4GB RAM board | link opens "Raspberry Pi 5 Computer with 8GB RAM" (`RASPBERRY-PI-5-8G`, Raspberry Pi) — see *Conflicts* |
| 1 | Raspberry Pi AI HAT+ (13 TOPS AI Power) | `V-RPI-HATP-AI`, Raspberry Pi |
| 1 | Raspberry Pi 27W PD USB-C PSU - UK Plug (White or Black, random color) | "Raspberry Pi 5 USB-C PD (Power Delivery) 27W PSU" (`V-RPI-PD-27W`, Raspberry Pi) |
| 1 | Heatsink & Active Cooler for Raspberry Pi 5 | "Active Cooler for Raspberry Pi 5" (`V-BO-PI5-HAC`, brand China) |
| 1 | Raspberry Pi Camera Module V3 (75° Angle) | "Raspberry Pi Camera Module 3 - 12MP with Auto Focus" (`RPI-CAM3`, Raspberry Pi) |
| 1 | FPC 22-Way to 15-Way for Camera - 50cm | "22-way to 15-way CSI (Camera) FPC for Raspberry Pi 5" (`V-WR-CSI-2215`, WaveShare) |
| 1 | Enclosure Case for Raspberry Pi Camera Module | `BO-CAM-V2V3`, Arducam |
| 1 | 64GB microSD card (preloaded with custom Raspberry Pi OS) | — |
| 1 | USB to microSD card adapter | "USB2.0 Cytron microSD Card Reader/Writer Adapter" (`CA-USB-USD-CT`, Cytron OEM) → `cytron-microsd-card-reader.md` |
| 1 | Set of Double Sided Tape | — |
| 2 | Defect Material | — |

- The packing image shows the cooler with thermal pads and two screws, the AI HAT+, the 50 cm FPC, a red camera case, one "Defect Material" item, the PSU ("Random Color"), a "Custom OS Defect Detection" label, a Raspberry Pi 64GB microSD card and a MakerDisk-branded card reader marked **FREE** [PP: img]. It does not show the double-sided tape.

### Not included (needed to follow tutorial 1) [PP: tutorial 1]
- Monitor, keyboard and mouse ("Required Hardware").
- An HDMI cable (step 1.8 connects "the HDMI cable" to a monitor; no HDMI cable is on the packing list).
- "The box" the camera is taped inside (step 1.5); no box is on the packing list — see *Conflicts*.
- Optional on the page ("Accessories you may need"): PCIe Metal Case for Raspberry Pi 5, RM59.00 [PP].

## Setup and run steps (tutorial 1) [PP: tutorial 1]
1. Fit the thermal pads and the active cooler on the Raspberry Pi 5.
2. Fit the AI HAT+ on the Pi 5 PCIe connector and secure it with the screws "provided in the kit".
3. Connect the ribbon cable to the camera (metal contacts the correct way), put the camera in its case and screw it in.
4. Tape the camera case inside the box, lens aligned with the box opening; tape the cable to the back of the box.
5. Connect the ribbon cable to the Pi, insert the preloaded SD card, connect HDMI to a monitor, then power on.
6. Update: `sudo apt update && sudo apt full-upgrade`.
7. Check the camera: `ls /dev/vid*` should list `/dev/video0` or `/dev/video1`.
8. `sudo raspi-config` → Advanced Options → PCIe Speed → Yes; then `sudo reboot`.
9. Check the AI HAT+: `hailortcli fw-control identify`.
10. Open a terminal in `/home/pi/hailo-rpi5-examples` and run `source setup_env.sh`.
11. Run detection: `python3 basic_pipelines/detection.py --hef-path resources/cytron.hef --labels-json resources/cytron-labels.json`.

## Training your own model (tutorial 2) [PP: tutorial 2]
- Outline only — the tutorial gives no commands or notebook:
  1. Collect images of defective and good items (RPi Camera, smartphone or other camera) at different angles, distances and lighting.
  2. Upload, annotate and augment (flip, rotate, brightness) in **Roboflow**; export in YOLOv8 format.
  3. Train a **YOLOv8** model (the overview says YOLOv8s) in **Google Colab**; tune learning rate, batch size and epochs; test on new data.
  4. Convert PyTorch → ONNX → HEF with Hailo's tools.
  5. Deploy the HEF on the Pi 5 + AI HAT+ with the RPi Camera.

## Rules and gotchas (for tutorials, scripts and marketing)
- **It is a POC kit, not a finished inspection system.** Cytron positions it for proof of concept and FYP work [PP]. No accuracy, frame rate, defect classes or certification are stated — never quote any.
- **Name the model YOLOv8.** Do not repeat the page's sentence that YOLOv8 was "Developed by Alexey Bochkovskiy in 2020" — see *Needs verification*. Do not repeat the "69% of impactful digital initiatives" statistic; the page gives no source.
- **AI HAT+ in this kit is 13 TOPS** [PP]. Don't confuse it with the 26 TOPS option sold with IRIV EdgeAI CM5.
- **Use the tutorial paths and file names exactly** (`/home/pi/hailo-rpi5-examples`, `setup_env.sh`, `basic_pipelines/detection.py`, `resources/cytron.hef`, `resources/cytron-labels.json`) [PP: tutorial 1].
- **Enable the faster PCIe speed in raspi-config** before running detection (tutorial step 4) [PP: tutorial 1].
- **Power:** use the included 27W 5V/5A PD PSU [PP]. This is the Raspberry Pi-brand PSU (`V-RPI-PD-27W`), not Cytron's 27W PD adapter (`V-AD-27W-PD`, `usbc-psu-27w-pd.md`).
- **Monitor, keyboard, mouse and HDMI cable are not in the box** [PP][PP: tutorial 1].
- Never print a default login for the custom OS (none is stated in the sources).

## Power and electrical limits
- Supply: 5V / 5A, 27W USB-C PD, UK plug [PP]. No other electrical limits are stated for the kit.

## Software support
- Custom Raspberry Pi OS (preloaded) with the Hailo examples folder `hailo-rpi5-examples`, a Python virtual environment (`setup_env.sh`), the `hailortcli` tool and the detection pipeline [PP: tutorial 1].
- Model pipeline: YOLOv8 → ONNX → HEF; OpenCV-based real-time detection [PP].
- Custom training: Roboflow (dataset), Google Colab (training), Hailo conversion tools [PP: tutorial 2].

## Compatibility and accessories
- KB files: USB microSD card reader → `cytron-microsd-card-reader.md`.
- Industrial alternatives in the KB using the same AI HAT+ family: **IRIV EdgeAI CM5** → `iriv-edgeai-cm5.md`; **IRIV EdgeAI Safety Box Kit** → `iriv-edgeai-safety-box-kit.md`; **IRIV EdgeAI Industry 4.0 Training** → `iriv-edgeai-vision-training.md`.
- Not in the KB (third-party): Raspberry Pi 5, AI HAT+, Camera Module 3, Raspberry Pi 27W PSU, active cooler, FPC cable, Arducam camera case, PCIe Metal Case.
- Related Cytron tutorials listed under tutorial 1 (not read): "Real-Time Object Detection & Counting with Raspberry Pi AI Kit" (22 Jul 2024), "Custom Object Detection on Raspberry Pi AI HAT with Hailo8L" (10 Mar 2026), "Defect Detection and Counter on Raspberry Pi" (22 Nov 2024), "Exploring Lightweight AI Models for Raspberry Pi Applications" (23 Apr 2025).

## Common mistakes / troubleshooting
- **No `/dev/video0` or `/dev/video1`** → re-seat the ribbon cable at both ends with the metal contacts the correct way [PP: tutorial 1].
- **`hailortcli fw-control identify` does not find the HAT** → check the AI HAT+ is fully seated on the PCIe connector and screwed down [PP: tutorial 1].
- **Detection script can't find the model** → run it from `hailo-rpi5-examples` after `source setup_env.sh`, with `cytron.hef` and `cytron-labels.json` in `resources/` [PP: tutorial 1].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Raspberry Pi 5 RAM | [PP] specifications and packing list: "4GB RAM" | [PP: links] the packing-list link opens the 8GB product page (`RASPBERRY-PI-5-8G`) | 4GB (stated twice); the link is wrong — fix the page |
| Camera box | [PP: tutorial 1] steps 1.5 mount the camera "inside the box" with double-sided tape | [PP] packing list has the tape but no box | Unresolved; ask whether a box (or the kit's packaging) is meant |
| HDMI cable | [PP: tutorial 1] step 1.8 "Connect the HDMI Cable" | [PP] packing list: none | Not included; buyer supplies it |
| Product name | [PP] title "AI Defect Detection Bundle" | [PP] description and URL "Defect Detection Kit"; [PP: tutorial 1] "Raspberry Pi AI Defect Detection Kit"; [PP: tutorial 2] also "Raspberry Pi AI Kit" | Use the product title; list the others as aliases (not "Raspberry Pi AI Kit", which is a different Raspberry Pi product name) |
| Price | [PP] RM1,207.50 | [PP: tutorial 1/2] hardware widget shows RM1,207.50 struck through to RM1,150.00 | Dated; re-check the live page before quoting |
| microSD card | [PP] "64GB microSD card (preloaded with custom Raspberry Pi OS)" | [PP: img] shows a Raspberry Pi-branded 64GB card | Brand not stated in text; don't name one |
| Card reader | [PP] packing list item | [PP: img] marked "FREE" | Included either way |

## Needs verification
- **Defect classes** the pre-trained model detects, what the **2 × Defect Material** samples are, and any measured accuracy or frame rate.
- **Custom OS** base (Bookworm?), image version, Hailo software version, and whether a re-flash image is available to buyers.
- Whether running `sudo apt full-upgrade` (tutorial step 2) keeps the preinstalled pipeline working.
- Whether the **pre-collected annotated dataset** is given to buyers, and where.
- The **box** in tutorial step 1.5 (included or not).
- Which Raspberry Pi 5 RAM ships today (4GB per the page text).
- The page's YOLOv8 history sentence ("Developed by Alexey Bochkovskiy in 2020", "builds upon ... YOLOv5 and YOLOv7") — not supported by any Cytron or vendor source read here; do not publish it.
- Kit weight and box size.

## Cytron tutorials
Add-on: Cytron tutorials that use this product. They never override [DS] or [UM] specs, and tutorial code is not copied here beyond the commands needed to run the kit [PP: tutorial 1][PP: tutorial 2].
- [Getting Started with Raspberry Pi AI Defect Detection Kit](https://my.cytron.io/tutorial/getting-started-with-ai-defect-detection-kit) — Tutorial, Intermediate, 2024
- [Raspberry Pi AI Defect Detection Kit: Use Your Own Dataset](https://my.cytron.io/tutorial/ai-defect-detection-kit-use-your-own-dataset) — Tutorial, Intermediate, 2024

## Sources
- [PP] https://my.cytron.io/p-ai-defect-detection-kit — read 2026-10-29 (KIT-AI-DEFECT; brand "Kit by Cytron"; RM1,207.50; cashback RM34.50; availability 3; warranty 12 months; description; features and specifications; packing list; resources)
- [PP: img] https://static.cytron.io/image/catalog/products/KIT-AI-DEFECT/npi-product-73.png (packing image) — viewed 2026-10-29
- [PP: links] linked component pages on my.cytron.io (Raspberry Pi 5 8GB, AI HAT+, 27W PD PSU, Camera Module 3, Arducam camera case, WaveShare FPC, active cooler, Cytron microSD reader) — titles, codes and brands read 2026-10-29
- [PP: tutorial 1] "Getting Started with Raspberry Pi AI Defect Detection Kit", 02 Dec 2024 — https://my.cytron.io/tutorial/getting-started-with-ai-defect-detection-kit — read in full 2026-10-29
- [PP: tutorial 2] "Raspberry Pi AI Defect Detection Kit: Use Your Own Dataset", 06 Dec 2024 — https://my.cytron.io/tutorial/ai-defect-detection-kit-use-your-own-dataset — read in full 2026-10-29
- KB cross-references: `cytron-microsd-card-reader.md`, `usbc-psu-27w-pd.md`, `iriv-edgeai-cm5.md`, `iriv-edgeai-safety-box-kit.md`, `iriv-edgeai-vision-training.md`
