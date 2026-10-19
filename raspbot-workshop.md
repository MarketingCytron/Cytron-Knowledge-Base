# Cytron Raspbot Workshop (Introduction to AI) — Verified Reference

| | |
|---|---|
| Product code | `V-TRAINING-AI` [PP] |
| Family | Workshops and services |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 (product page facts read 2026-10-19) |
| Primary source | **No datasheet exists (this is a service).** Highest source is the Cytron workshop schedule: "Raspbot Workshop Tentative.pdf" (Google Drive, no version or date printed) [UM]; product page https://my.cytron.io/p-ai-training-kit [PP]|

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A one-day Edge AI workshop built around the Raspbot, a Raspberry Pi mobile robot with a camera, run at Cytron HQ in Bukit Mertajam, Penang, from 9.00 am to 5.00 pm with food included and a maximum of 5 participants per workshop [PP]. The price includes the Raspbot kit (Raspberry Pi 5 8GB, pre-imaged 32GB microSD, chassis, mecanum wheels, camera, sensors, battery and accessories) and a certificate [PP]. The day runs from Python and OpenCV basics through an introduction to AI and ROS2 to assembling, testing and programming the Raspbot [UM]. Cytron states the workshop can also be conducted at the customer's location on request [PP].

## Specifications
Service / logistics table (kit contents as listed on the product page).

| Item | Value | Src |
|---|---|---|
| Product name | Cytron Raspbot Workshop (Introduction to AI) | [PP] |
| Product code | V-TRAINING-AI | [PP] |
| Duration | One day, 9.00 am – 5.00 pm | [PP][UM] |
| Venue | Cytron HQ, Bukit Mertajam, Penang; can be conducted at customer location (contact Cytron) | [PP] |
| Dates offered (as of 2026-10-19) | 15 Oct 2026; 12 Nov 2026; 10 Dec 2026 | [PP] |
| Participant limit | Maximum 5 participants per workshop | [PP] |
| Food | Included | [PP] |
| Certificate | Provided | [PP] |
| Price | RM1,800.00 (offer; was RM2,100.00) | [PP] |
| Availability | 15 | [PP] |
| Warranty shown | 12 months | [PP] |
| Kit: computer | Raspberry Pi 5 (8GB) | [PP] |
| Kit: storage | 32GB microSD with Raspbot OS | [PP] |
| Kit: robot parts | Car expansion board; camera platform PCB; PTZ component; 4x mecanum wheels; 4x motor fixing frames; 4-channel tracking module; 4x motor; battery + velcro; 40-pin cable; camera; ultrasonic sensor; remote control; screw pack | [PP] |
| Kit: accessories | Screwdriver; micro HDMI cable; 12.6V charger (EU) + UK adapter; manual | [PP] |
| Prerequisites | Not stated in any source read | — |
| Refund / cancellation terms | Not stated in any source read | — |

**Timetable ("Raspbot Workshop Tentative", Day 1)** [UM]:
| Time | Activity |
|---|---|
| 9:00 AM – 9:15 AM | Ice Breaking Session |
| 9:15 AM – 10:00 AM | Introduction to Python |
| 10:00 AM – 10:30 AM | Breakfast |
| 10:30 AM – 11:00 AM | Factory Tour |
| 11:00 AM – 11:30 AM | Introduction to OpenCV |
| 11:30 AM – 12:30 PM | Introduction to AI |
| 12:30 PM – 1:00 PM | Introduction to ROS2 |
| 1:00 PM – 2:00 PM | Lunch Break |
| 2:00 PM – 2:30 PM | Assembling Raspbot |
| 2:30 PM – 3:00 PM | Testing Raspbot App |
| 3:00 PM – 4:30 PM | Raspbot Programming |
| 4:30 PM – 4:45 PM | Tea Break |
| 4:45 PM – 5:00 PM | Q&A / Summary |


## Interfaces, terminals and pin mapping

## Rules and gotchas (for code, wiring and tutorials)
- Name: the store name is "Cytron Raspbot Workshop (Introduction to AI)" and the product URL slug is `p-ai-training-kit` [PP]. Do not call the workshop "AI Training Kit" as if it were a hardware product.
- One day, max 5 participants, food included, certificate provided, at Cytron HQ Bukit Mertajam [PP]. These are the facts most often needed; only this workshop (of the three in this batch) states a participant cap and a certificate.
- The kit lists a 12.6V charger with an EU plug plus a UK adapter [PP]; 12.6 V is a 3-cell lithium charger voltage, but the battery itself is only listed as "battery + velcro" with no chemistry or capacity stated. Do not state battery specs.
- The Pi is an 8GB Raspberry Pi 5 and the OS is on a 32GB microSD ("Raspbot OS") [PP]; do not describe NVMe or other storage.
- The timetable is "Tentative"; it includes a Factory Tour slot, which is specific to running at Cytron HQ [UM].

## Power and electrical limits
Not applicable (service). Kit power items stated: battery + velcro; 12.6V charger (EU) with UK adapter [PP]. No voltages, capacities or currents for the robot are stated.

## Software support
- Raspbot OS on the supplied 32GB microSD [PP].
- A "Raspbot App" is tested in the 2:30 PM slot [UM]; the app is not described further in the sources read.

## Compatibility and accessories
- Full kit per product page (see Specifications). Remote control, camera, ultrasonic sensor, 4-channel tracking module, PTZ component and camera platform PCB are included [PP].

## Common mistakes / troubleshooting
- Treating the product as a hardware kit sold alone: it is a workshop seat whose price includes the kit [PP].
- Quoting the old RM2,100.00 price without noting the RM1,800.00 offer, or vice versa [PP].
- Over-stating the group size: max 5 participants per workshop [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Robot name | Page: "Raspbot" [PP] | Deck: "RaspBot V2" / "Raspbot V2"  | Same rank; use "Raspbot" (store name) and note the deck's V2 designation. |
| Day structure | Timetable: assembling, app test and programming after lunch [UM] | Deck: five chapters, ROS2-OpenCV Docker course included  | Compatible; [UM] is the schedule,  is the content. |

## Needs verification
- Prerequisites and minimum age for the current product (the 2024 internal listing said 15+, but that is historical).
- Whether participants must bring a laptop.
- Refund, transfer and cancellation terms; on-site (customer location) pricing.
- Battery chemistry, voltage and capacity of the kit battery; manufacturer of the Raspbot platform.
- What the "Raspbot App" is (mobile app vs desktop) and which Raspbot OS version is on the microSD.
- Whether the 12 Nov 2026 and 10 Dec 2026 dates are still open after 2026-10-19.
- Version/date of the tentative timetable (none printed).

## Sources
- [UM] Raspbot Workshop Tentative.pdf — Cytron timetable (Google Drive): https://drive.google.com/file/d/1UqgaUC4sCqkGij_CYugQJBWlGZO8z-C6/view
- [PP] Product page (facts supplied by coordinator, read 2026-10-19): https://my.cytron.io/p-ai-training-kit
- Blocked (not read): https://www.cytron.io/p-ai-training-kit
