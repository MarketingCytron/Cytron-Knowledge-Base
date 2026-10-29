# Product fact sheets

## Product name
AI Defect Detection Bundle

## Aliases
KIT-AI-DEFECT, AI Defect Detection Bundle, AI Defect Detection Kit, Raspberry Pi AI Defect Detection Kit, Defect Detection Kit

## What it is
A ready-to-run AI visual defect-detection kit for proof-of-concept work, built on Raspberry Pi 5 (4GB), the Raspberry Pi AI HAT+ (13 TOPS) and Raspberry Pi Camera Module 3. A custom Raspberry Pi OS on the included 64GB microSD card holds a YOLOv8 defect model already converted to Hailo format, so detection runs without setup or training. Two defect material samples are included for testing.

## Specs and functions
- Product code: KIT-AI-DEFECT (product page)
- Computer: Raspberry Pi 5, 4GB RAM (product page)
- AI accelerator: Raspberry Pi AI HAT+, 13 TOPS (product page)
- Camera: Raspberry Pi Camera Module 3, 12MP, 75 degree, auto focus; CSI cable 50 cm (product page)
- Storage: 64GB microSD card preloaded with a custom Raspberry Pi OS, libraries and a precompiled trained model (product page)
- AI model: YOLOv8, converted PyTorch → ONNX → HEF for the AI HAT+; OpenCV-based real-time detection (product page)
- Power supply: Raspberry Pi 27W PD USB-C PSU, 5V / 5A, UK plug (product page)
- Packing list: 1x Raspberry Pi 5 with 4GB RAM board, 1x Raspberry Pi AI HAT+ (13 TOPS), 1x Raspberry Pi 27W PD USB-C PSU - UK Plug (white or black, random), 1x Heatsink & Active Cooler for Raspberry Pi 5, 1x Raspberry Pi Camera Module V3 (75° angle), 1x FPC 22-Way to 15-Way for Camera - 50cm, 1x Enclosure Case for Raspberry Pi Camera Module, 1x 64GB microSD card (preloaded with custom Raspberry Pi OS), 1x USB to microSD card adapter, 1x Set of Double Sided Tape, 2x Defect Material (product page)
- Defect classes detected: [NOT STATED]
- Detection accuracy / frame rate: [NOT STATED]
- OS base and version: [NOT STATED]
- Weight: [NOT STATED]
- Warranty: 12 months (product page)

## Interfaces and compatibility
- Run steps: fit cooler and AI HAT+, connect and mount the camera, insert the SD card, connect a monitor; enable the higher PCIe speed in raspi-config; check the HAT with `hailortcli fw-control identify`; run `basic_pipelines/detection.py` with `resources/cytron.hef` and `resources/cytron-labels.json` from `hailo-rpi5-examples` (tutorial)
- Own dataset: collect images, annotate in Roboflow, train YOLOv8 in Google Colab, convert to ONNX then HEF, deploy on the Pi (tutorial)
- Cytron tutorials: Getting Started with Raspberry Pi AI Defect Detection Kit (Dec 2024); Raspberry Pi AI Defect Detection Kit: Use Your Own Dataset (Dec 2024)
- Needs a monitor, keyboard, mouse and HDMI cable (not included) (tutorial)
- Optional: PCIe Metal Case for Raspberry Pi 5 (product page)

## Use cases
- Proof of Concept (POC) for AI visual inspection and quality control (product page)
- Final year projects (FYP) (product page)
- Real-time defect detection on sample products with the included defect materials (product page)
- Training a custom defect model on your own products (tutorial)

## Known limitations
- POC kit; no accuracy, frame rate or defect classes stated
- Monitor, keyboard, mouse and HDMI cable not included
- The tutorial mounts the camera inside a box that is not on the packing list
- The page's Raspberry Pi 5 link opens the 8GB product although the kit states 4GB
- Custom OS version and re-flash image not stated

## Positioning (kept apart from specs)
- "AI-powered defect detection solution is ready to use with no complicated setup, just plug it in and start detecting defects instantly" (product page)
- A complete kit with free defect materials and tutorials, so engineers can focus on deployment rather than configuration (product page)

## Price band
RM1,207.50 (Cytron product page, read 2026-10-29)

## Product page
https://my.cytron.io/p-ai-defect-detection-kit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-ai-defect-detection-kit
