# Jetson Orin Nano AI Fundamentals: Hands-On Workshop with NVIDIA Certification — Verified Reference

| | |
|---|---|
| Product code | `V-TW-JNORNN-NVIDIA` [PP] |
| Family | Workshops and services |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: live product page re-read in full (browser). Full kit list, certificate wording and loan-unit terms added; kit list no longer truncated. Service — product page + Cytron timetable are the main source (KB rule 7, workshops and services) |
| Primary source | **No datasheet exists (this is a service).** Highest source is the Cytron workshop schedule: "Jetson Orin Nano Workshop Tentative (Day 1).pdf" (Google Drive, no version or date printed) [UM]; product page https://my.cytron.io/p-jetson-orin-nano-ai-fundamentals-hands-on-workshop-with-nvidia-certification-v [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A one-day, hands-on AI fundamentals workshop on the NVIDIA Jetson Orin Nano, held at the Cytron Technologies office in Penang, that ends with an official NVIDIA AI certification on completion [PP]. It covers setup, architecture, real-time object detection, image classification, image regression and edge inference [PP]. Sold in two ways: "Kit + 1 Day Training at HQ" (a Jetson Orin Nano training kit plus the seat, date chosen as the variant) and "Workshop ONLY" for people who already own the Jetson Orin Nano Training Kit V2, with loan units available on request [PP].

## Specifications
Service / logistics table. There is no hardware spec table; the kit list below is as far as the page extract went.

| Item | Value | Src |
|---|---|---|
| Product name | Jetson Orin Nano AI Fundamentals: Hands-On Workshop with NVIDIA Certification | [PP] |
| Product code | V-TW-JNORNN-NVIDIA | [PP] |
| Duration | 1 day; timetable runs 9:00 AM to 5:00 PM | [PP][UM] |
| Venue | Cytron Technologies office, Penang ("Training at HQ") | [PP] |
| Dates offered (as of 2026-10-19) | 30 Sep 2026; 21 Oct 2026; 18 Nov 2026 | [PP] |
| Options | Kit + 1 Day Training at HQ (date as variant); Workshop ONLY (for owners of the Jetson Orin Nano Training Kit V2; loan training-kit units can be requested, subject to availability) | [PP] |
| Price | RM1,200.00–RM5,073.36 offer (struck-through list RM1,550.00–RM5,323.36) | [PP] |
| Availability | 10 | [PP] |
| Warranty shown | 12 months | [PP] |
| Certification | Official NVIDIA AI certification on completion; participants receive a **Certificate of Completion from NVIDIA and Cytron** | [PP] |
| Topics | Setup, architecture, real-time object detection, image classification, image regression, edge inference | [PP] |
| Kit (Kit + 1 Day option) | NVIDIA Jetson Orin Nano Super Developer Kit (8GB) preassembled in an aluminium alloy case with external antennas; 19V 45W power supply; NVMe 2280 MakerDisk SSD 512GB preloaded with JetPack; case with camera holder; USB camera with housing; extendable camera stand; DP-to-HDMI adapter; HDMI cable | [PP] |
| Participant limit | Not stated in any source read | — |
| Prerequisites | Not stated in any source read | — |
| Refund / cancellation terms | Not stated in any source read | — |
| Food | Breakfast, lunch and tea break appear as timetable slots; whether food is provided is not stated | [UM] |

**Timetable ("Jetson Orin Nano Workshop Tentative", Day 1)** [UM], times as printed:
| Time | Activity |
|---|---|
| 9:00 AM – 9:15 AM | Ice Breaking Session |
| 9:15 AM – 9:45 AM | Theory about AI/ML/DL |
| 9:45 AM – 10:15 AM | Breakfast |
| 10:15 AM – 10:45 AM | Theory about Jetson Orin Nano |
| 10:45 AM – 11:15 PM (sic; printed "11:15PM") | Theory about CUDA |
| 11:15 PM – 12:15 PM (sic; printed "11:15PM") | Hands On with Jetson Orin Nano |
| 12:15 PM – 1:00 PM | Create NVIDIA Account |
| 1:00 PM – 2:00 PM | Lunch |
| 2:00 PM – 3:00 PM | Image Classification/Test |
| 3:00 PM – 4:00 PM | Image Regression/Test |
| 4:00 PM – 4:30 PM | Tea Break |
| 4:30 PM – 5:00 PM | Q&A / Summary |

## Interfaces, terminals and pin mapping
Not applicable (service). Relevant software facts: the timetable includes a "Create NVIDIA Account" slot before the certification exercises [UM]; the kit's SSD is a MakerDisk NVMe 2280 512GB preloaded with JetPack [PP].

## Rules and gotchas (for code, wiring and tutorials)
- It is a 1-day workshop [PP][UM]; the AI Agent (AgentBox) workshop is the 2-day one. Do not swap them.
- The certification is described as an "official NVIDIA AI certification on completion", and participants receive a Certificate of Completion from NVIDIA and Cytron [PP]. Do not name a specific NVIDIA DLI course; none is stated in the sources read.
- The hardware in the kit is the Jetson Orin Nano **Super** Developer Kit (8GB) with a 19V 45W supply and a 512GB MakerDisk NVMe 2280 preloaded with JetPack [PP]. Use "Super Developer Kit", not the original Orin Nano Developer Kit.
- "Workshop ONLY" is restricted to owners of the Jetson Orin Nano Training Kit V2; loan training-kit units can be requested, subject to availability [PP]. Do not describe Workshop ONLY as open to anyone with any Jetson.
- The timetable file is titled "Tentative"; present it as a tentative schedule, not a fixed agenda. The "11:15PM" entries are typographical errors in the PDF (the slot sits between 10:45 AM and 12:15 PM).
- The page lists "real-time object detection" as a topic, but the tentative timetable has only Image Classification and Image Regression hands-on slots; see Conflicts.
- Dates are the purchase variants; quote them with "as of 2026-10-19" and check the page because the 30 Sep 2026 date has passed.

## Power and electrical limits
Not applicable (service). Kit power supply stated on the page: 19V 45W [PP]. No other electrical facts are stated in the sources read.

## Software support
- JetPack preloaded on the kit's MakerDisk NVMe 2280 512GB SSD [PP]; the JetPack version is not stated on this product's page extract (see Needs verification).
- Course content: CUDA theory, image classification and image regression hands-on tests [UM]; edge inference and real-time object detection [PP].
- An NVIDIA account is created during the workshop [UM].

## Compatibility and accessories
- Kit option: Jetson Orin Nano Super Developer Kit (8GB) in aluminium alloy case with external antennas and camera holder, 19V 45W power supply, NVMe 2280 MakerDisk SSD 512GB (JetPack) — see `makerdisk-nvme-2280-jetpack.md`, USB camera with housing, extendable camera stand, DP-to-HDMI adapter, HDMI cable [PP].
- Workshop ONLY option: participant brings their own Jetson Orin Nano Training Kit V2, or requests a loan training-kit unit (subject to availability) [PP].

## Common mistakes / troubleshooting
- Saying the workshop lasts 2 days, or is held in Kuala Lumpur: it is 1 day at the Cytron Technologies office in Penang [PP].
- Promising a named NVIDIA certificate (e.g. a specific DLI course): only "official NVIDIA AI certification" is stated [PP].
- Leaving out the camera items: the kit includes a USB camera with housing, an extendable camera stand and a case camera holder [PP].
- Copying the "11:15PM" times from the tentative PDF literally into content.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Hands-on topics | Timetable: Image Classification/Test and Image Regression/Test only [UM] | Page: real-time object detection, image classification, image regression, edge inference [PP] | Timetable is "Tentative"; state the page topics as the course scope and the timetable as the planned Day 1 order. Flagged under Needs verification. |
| Timetable times | PDF prints "10:45AM - 11:15PM" and "11:15PM - 12:15PM" [UM] | Surrounding slots make these 11:15 AM [UM] | Typographical error in the PDF; write 11:15 AM. |

## Needs verification
- Which JetPack version is preloaded on the kit SSD at the time of the workshop (the MakerDisk JetPack page says JetPack 6.2 on units shipped from 6 Feb 2025 — confirm for workshop kits).
- Whether the certificate maps to a named NVIDIA DLI course (page says only "official NVIDIA AI certification" and "Certificate of Completion from NVIDIA and Cytron").
- Maximum participants per session, prerequisites, and whether a laptop is required.
- Whether meals are provided (timetable only shows break slots).
- Refund, transfer and cancellation terms.
- Which price corresponds to which option (RM1,200.00 vs RM5,073.36).
- Whether the 21 Oct 2026 and 18 Nov 2026 dates are still open.
- Whether real-time object detection is actually taught on the day (not on the tentative timetable).

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [My Experience Attending the NVIDIA Jetson Workshop by Cytron](https://my.cytron.io/tutorial/jetson-orin-nano-workshop-experience) — Success Stories, 2024 [PP: tutorial]

## Sources
- [UM] Jetson Orin Nano Workshop Tentative (Day 1).pdf — Cytron timetable (Google Drive): https://drive.google.com/file/d/1W4ZJX9gzJETGO6qNpKIIxZXKXTTGLwMZ/view
- [PP] Product page (facts supplied by coordinator, read 2026-10-19): https://my.cytron.io/p-jetson-orin-nano-ai-fundamentals-hands-on-workshop-with-nvidia-certification-v
- Blocked (not read): https://www.cytron.io/p-jetson-orin-nano-ai-fundamentals-hands-on-workshop-with-nvidia-certification-v
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
