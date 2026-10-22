# IRIV EdgeAI Industry 4.0 Training: Getting Started with EdgeAI Vision — Verified Reference

| | |
|---|---|
| Product code | `V-KIT-IRIV-EAI` (training page) [PP]. Its only option, "Kit + 2 Days Training", opens the page "IRIV EdgeAI Industry 4.0 Complete Training Kit", code `KIT-IRIV-EAI-SP` [PP]. Controller inside: **IRIV EdgeAI CM5** (`IRIV-EDGEAI-CM5`), Raspberry Pi CM5 **8GB RAM / 32GB eMMC with a 13 TOPS Hailo AI accelerator** [PP] (wireless or not is not stated) |
| Family | Workshops and services |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-22 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


**Kit rule:** the controller is not re-documented here — see `iriv-edgeai-cm5.md`. The training kit uses the **8GB RAM / 32GB eMMC + 13 TOPS** configuration (one of the three configurations listed there), not the 26 TOPS Safety Box controller (`iriv-edgeai-safety-box-kit.md`). Only workshop- and kit-level facts are stated.

## What it is
A Cytron two-day Edge AI vision workshop sold with an IRIV EdgeAI Industry 4.0 training kit that participants take home [PP]. The kit is an industrial training box with DIN rails and cable management holding an IRIV EdgeAI CM5 controller (Raspberry Pi CM5, 8GB RAM, 32GB eMMC, 13 TOPS Hailo AI accelerator), a 24V power supply, an AC socket, a 24V industrial relay, an Acrel ADL200 RS485 power meter, an RS485 temperature and humidity sensor, an illuminated push button and an 8 MP USB camera [PP]. The course covers Node-RED, Modbus RS485, Blynk IoT, Linux and Python basics, then Hailo AI detection pipelines, custom dataset preparation, inference with a custom-trained model and linking AI results to outputs and Blynk [PP]. Meals and a professional certificate are included [PP]. Target users: engineers, system integrators, lecturers and trainers [PP].

## Specifications
Service / logistics table.

| Item | Value | Src |
|---|---|---|
| Product name | IRIV EdgeAI Industry 4.0 Training: Getting Started with EdgeAI Vision | [PP] |
| Product code | V-KIT-IRIV-EAI (training page); option page KIT-IRIV-EAI-SP "IRIV EdgeAI Industry 4.0 Complete Training Kit" | [PP] |
| Price | RM5,000.00 (training page); RM5,250.00 on the option page — 5% higher, reason not stated | [PP] |
| Availability | Out Of Stock (training page and its option); option page shows "Enquiry" | [PP] |
| Warranty shown | 12 months (option page only) | [PP] |
| Duration | 2 days | [PP][PP: tutorial] |
| Dates / slots | None listed | [PP] |
| Venue | **Not stated** on the page | — |
| Times / participant limit | Not stated | — |
| Meals | Included | [PP] |
| Certificate | "Professional certificate upon completion" | [PP] |
| HRDC | **Claimable** (team confirmation); the page itself does not say so, but links "How to Claim HRDC for our HRDC Claimable Training" | [PP] |
| Scheduling | No public dates or venue yet; **customers can request a session** (team). Example run: DRB-HICOM Port Klang, 2 days, 11–12 Jun 2026, 3 participants | [PP: tutorial] |
| Laptop | Required, with **Windows**; recommended Intel Core i5 10th Gen / AMD Ryzen 5 5th Gen or better and 16GB RAM for custom model training. A pre-trained custom model/dataset is provided if training does not finish in time | [PP] |
| Kit taken home | Yes — "participants can bring home the full kit" | [PP] |
| Kit controller | IRIV EdgeAI, Raspberry Pi CM5, 8GB RAM, 32GB eMMC, Hailo AI accelerator 13 TOPS | [PP] |
| Kit hardware (Features list) | 1x IRIV EdgeAI; 1x 24V DC power supply; 1x AC socket; 1x RS485 power meter; 1x 24V industrial relay; 1x illuminated push button; 1x USB camera; 1x industrial training box with DIN rails and cable management | [PP] |
| Packing list | 1x IRIV EdgeAI Training Kit: 1x IRIV EdgeAI 8GB 32eMMC with Hailo AI Accelerator 13 TOPs; 1x industrial relay; 1x AC socket; 1x industrial illuminated push button; 1x RS485 industrial temperature and humidity sensor; 1x Acrel ADL 200 RS485 power meter; 1x Meanwell 24V 100W DC power supply (no USB camera listed — see *Conflicts*) | [PP] |
| Input voltage | 240 VAC | [PP] |
| Power supply | Spec line "24 VDC, 1 A"; packing list "Meanwell 24V 100W" — see *Conflicts* | [PP] |
| Industrial relay | Input 24 VDC; operating 24 VDC / 240 VAC | [PP] |
| Power meter | Acrel ADL200, RS485; operating voltage 240 VAC; measures voltage, current, power and more | [PP] |
| Temperature / humidity sensor | RS485, 24 V; −40 to 120 ℃; 0–99.9 %RH; ±0.3 ℃ / ±2 %RH at 25 ℃; sampling period 3 s | [PP] |
| Push button | Illuminated, 24 V, button + LED, NC or NO | [PP] |
| USB camera | IMX219 sensor; 8 MP stills; rolling shutter; 1/4"; MJPG/YUY2; 1.12 µm pixels; active area 3280 × 2464; MJPG 15 fps at 3264 × 2448 / 2592 × 1944 and 30 fps at 1920 × 1080 down to 640 × 480; YUV 10 fps at 1280 × 720 down to 320 × 240; IR-cut filter (visible only); autofocus; FOV 60° H × 72° D × 47° V; F2.0; EFL 2.96 mm; focus 10 cm–∞; 5 V ±5%, max 200 mA; 0–70 ℃; board 38 × 38 mm (28 × 28 mm with case — as printed); dual microphone; UVC controls | [PP] |
| Software supplied | Raspberry Pi Bookworm OS; pre-built Node-RED dashboard; Node-RED and Python libraries for the AI vision application "(Only with training session)" | [PP] |
| Prerequisites | Not stated beyond the laptop | — |
| Refund / cancellation (this product) | Not stated on the page. Generic landing-page FAQ: full refund 14+ days before; 7–14 days 50% refund or full credit | [PP: landing] |

**Workshop outline** [PP] ("This 2-Days Workshop will cover the topics below. Participants will also learn how to train their own AI Dataset / Model"): Getting started with Node-RED · Basic Node-RED coding for input and output · MODBUS RS485 coding · Getting started with Blynk IoT platform · Linux command line interface · Basic Python coding · Getting started with Hailo AI, basic pipeline detection · Custom AI dataset preparation · Hailo AI inference using image and video input · Hailo AI inference using buzzer and LED output · Hailo AI inference using a custom-trained model · Integrate AI inference with the Blynk IoT platform.

**Landing-page syllabus card** [PP: landing]: Module 1 Getting Started with EdgeAI Vision (Edge AI in industrial settings; IRIV EdgeAI hardware overview; development environment) · Module 2 Computer Vision Fundamentals (image processing basics; object detection and recognition; quality inspection use cases) · Module 3 AI Model Deployment (deploying on industrial controllers; real-time inference optimisation; integration with production systems) · Module 4 Practical Applications (defect detection; automated visual inspection; production-ready AI solutions).

### Product page facts (my.cytron.io, read 21 Oct 2026)
- **Out of stock**, RM5,000.00, single option "Kit + 2 Days Training" (out of stock) [PP].
- **Option page:** "IRIV EdgeAI Industry 4.0 Complete Training Kit", KIT-IRIV-EAI-SP, RM5,250.00, Enquiry ("INQUIRE NOW"), warranty 12 months; same description and packing list [PP].
- **SST note:** from April 2026 prices are subject to applicable SST, calculated at checkout [PP].
- **Camera capacity claim:** "two USB 3.0 ports and two MIPI ports for CSI cameras, giving you the capability to connect up to four cameras simultaneously" [PP].
- **Applications named:** defect detection, product recognition, object identification, quality inspection, object tracking, automation monitoring [PP].
- **No Resources tab**, no brochure, no course outline file, no dates [PP].
- **Related story:** DRB-HICOM Port Klang, 3 participants, 11–12 Jun 2026; main exercise was training a custom model to detect a logo on a shirt and testing it live with a camera; topics listed: getting started with IRIV EdgeAI, Node-RED, camera setup, dataset preparation, model training, Hailo inference on images/video, running a custom model, connecting AI results to physical outputs [PP: tutorial]. Venue of that run not stated.
- **Reviews:** none [PP].

## Interfaces, terminals and pin mapping
Not applicable as a service; kit wiring is not documented. Controller facts that matter for the exercises (from `iriv-edgeai-cm5.md`): 2 isolated DI and 2 isolated dry-contact DO (SSR, max 50 V, 500 mA), isolated RS485 on `/dev/ttyACM0`, 2x USB 3.0 (one shared hub), 2x MIPI CSI, M.2 Key-M = NVMe only, mPCIe = USB 2.0 only, VIN 10–30 VDC. The relay, push button and RS485 meter/sensor in the kit connect to these (inferred; not mapped on the page). The "buzzer and LED output" exercises use the controller's on-board buzzer/LEDs or the push-button LED (inferred; not stated).

## Rules and gotchas (for code, wiring and tutorials)
- **Name the controller configuration:** IRIV EdgeAI CM5 **8GB / 32GB / 13 TOPS** [PP]. Do not write 26 TOPS (that is the Safety Box Kit and the other CM5 configurations), and do not name the Hailo chip — the KB has Hailo-8L for 13 TOPS only as [VEN] (`iriv-edgeai-cm5.md`).
- **Windows laptop required** [PP] — unlike the IRIV PiControl workshop, which accepts Windows or macOS.
- **USB camera:** the description and Features list include it; the packing list omits it [PP]. Say "USB camera included (description)" and flag the packing list.
- **Temperature/humidity sensor:** in the description and packing list, but missing from the Features hardware list [PP].
- **"Up to four cameras"** is 2 USB + 2 CSI ports [PP]; the two USB 3.0 ports share one hub (`iriv-edgeai-cm5.md`), so do not promise four full-rate streams.
- **Example run to cite:** "IRIV EdgeAI Workshop with DRB-HICOM" (11–12 Jun 2026, 3 participants, custom logo-detection model, aimed at product defect detection) [PP: tutorial].

## Power and electrical limits
- Kit mains input 240 VAC; Meanwell 24 V supply (100 W per packing list; "24 VDC, 1 A" per spec line) [PP].
- Relay: 24 VDC coil; switches 24 VDC / 240 VAC loads (current rating not stated) [PP]. AC socket switched through it (inferred).
- ADL200 power meter operates from 240 VAC [PP] — mains wiring inside the training box.
- USB camera 5 V ±5%, max 200 mA [PP].
- Controller limits: `iriv-edgeai-cm5.md`.

## Software support
- Raspberry Pi Bookworm OS; pre-built Node-RED dashboard; Node-RED and Python AI-vision libraries supplied only with the training session [PP].
- Hailo AI pipelines (basic detection, image/video inference, custom-trained model) and Blynk IoT [PP].
- Model training runs on the participant's laptop (hence the i5/Ryzen 5, 16GB RAM recommendation) [PP]; training framework and model type (e.g. YOLO version) not stated.

## Compatibility and accessories
- Participant Windows laptop (recommended i5 10th Gen / Ryzen 5 5th Gen, 16GB RAM) [PP].
- Extra cameras: USB 3.0 or Raspberry Pi CSI cameras on the controller's 2x MIPI ports [PP]; none beyond the USB camera are included.
- The IRIV EdgeAI CM5 product page sells a "Complete Kit" option (`iriv-edgeai-cm5.md`); whether it is the same as KIT-IRIV-EAI-SP is not confirmed.

## Common mistakes / troubleshooting
- Quoting 26 TOPS for this kit.
- Bringing a macOS laptop (Windows is required) [PP].
- Assuming the AI-vision libraries are on the kit without the training session [PP].
- Custom model training too slow on a low-spec laptop — a pre-trained model is provided as fallback [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| USB camera in the kit | Description and Features: included [PP] | Packing list: not listed [PP] | Same source; treat as included (stated twice) and ask marketing to fix the packing list |
| Temp/humidity sensor | Description and packing list: included [PP] | Features hardware list: not listed [PP] | Treat as included |
| Power supply | Spec: "24 VDC, 1 A" [PP] | Packing list: "Meanwell 24V 100W" [PP] | Unresolved; quote the packing list and ask engineering |
| Price | Training page: RM5,000.00 [PP] | Option page KIT-IRIV-EAI-SP: RM5,250.00 [PP] | Quote RM5,000.00 (the listed product) with date; ask why the option is 5% higher |
| Availability | Training page and its option: Out Of Stock [PP] | Option page: Enquiry [PP] | Status row = Out of stock (team instruction) |
| Course content | Page outline: Node-RED, Modbus, Blynk, Linux, Python, Hailo pipelines, custom dataset/model, Blynk integration [PP] | Landing syllabus: computer vision fundamentals, model deployment, inference optimisation, defect detection, production-ready solutions [PP: landing] | Page outline is product-specific; landing card is a marketing summary |
| Camera board size | "38×38 mm/28x28 mm with Case" [PP] | — | As printed; the "with case" size smaller than the board is probably reversed — do not quote |

## Needs verification
- Venue options for requested sessions (Cytron HQ or customer site), daily times and participant limit.
- Refund/cancellation terms.
- Whether the IRIV EdgeAI in the kit is the wireless variant; which Hailo chip the 13 TOPS AI HAT+ uses.
- Exact Meanwell PSU model and rating; relay current rating; USB camera brand (the page gives an IMX219 UVC camera spec but no brand).
- Model-training toolchain (framework, model family) and the Blynk plan used.
- Whether KIT-IRIV-EAI-SP is the same as the "Complete Kit" option on the IRIV EdgeAI CM5 page, and whether the kit is sold without training.
- Content of the "IRIV Edge AI Defect Detection Workshop" slides (Dec 2025; image-only) and whether they are this course's deck.
- The "Reason to join our Workshop" image block (not read).

## Sources
- [PP] Training page (read 2026-10-21): https://my.cytron.io/cytron-industry/iriv-edge-ai-training-page
- [PP] Option page KIT-IRIV-EAI-SP (read 2026-10-21): https://my.cytron.io/cytron-industry/p-iriv-edgeai-industry-4.0-complete-training-kit
- [PP: landing] Cytron Workshop Landing Page (read 2026-10-21): https://my.cytron.io/cytron-workshop
- [PP: tutorial] IRIV EdgeAI Workshop with DRB-HICOM (13 Aug 2026): https://my.cytron.io/tutorial/iriv-edgeai-workshop-drb-hicom
- Controller: `iriv-edgeai-cm5.md`
