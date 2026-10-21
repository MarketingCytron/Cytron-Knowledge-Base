# 12V 37mm DC Geared Motor (SPG30 / SPG30E) — Verified Reference

| | |
|---|---|
| Product code | `V-SPG30` (series code on the page); variant codes `SPG30-GR30`, `SPG30-GR56`, `SPG30-GR131`, `SPG30-GR270`, `SPG30-GR506` (no encoder) and `SPG30E-GR30` … `SPG30E-GR506` (with encoder) [PP] |
| Family | Motors (Cytron OEM) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: product page read in full in the browser (all 10 variant combinations clicked for code, price and stock), page images (wire identification chart, two dimension images, option/bracket/key-hub images), and the Cytron "Motor Specification" PDFs from the linked Drive folder "V-SPG30": SPG30-GR30 (all 3 pages), SPG30-GR56/131/270/506 and SPG30E-GR30/GR506 (electrical page; SPG30E-GR30 drawing page). Linked tutorials read for relevant facts |
| Primary source | **Cytron "Motor Specification" PDFs** (Drive folder "V-SPG30", one 3-page PDF per variant: specification, performance curve, dimension; created 6–7 Mar 2025) [DS], and the **Cytron product page "12V 37MM DC Geared Motor"** (https://my.cytron.io/cytron-oem/p-12v-37mm-dc-geared-motor), read 2026-10-21 [PP]. The datasheets and the page **disagree on load and stall figures** (see *Conflicts*) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [DS] = Cytron-branded "Motor Specification" PDFs (MODEL: SPG30-GRxx / SPG30E-GRxx) from the page's "Datesheets: SPG30 & SPG30E series" Drive folder; the text layer is empty, so pages were rendered and read as images. [PP] = product page text and spec tables; [PP: img] = the page's description images (wire chart, dimension tables). [PP: tutorial] = Cytron tutorials linked from the page. The original motor manufacturer is not named on the page or in the PDFs. Not to be confused with the separate **SPG30HP** high-power motors (`high-power-dc-geared-motor-12v.md`).

## What it is
- A 12 V brushed DC motor with a Ø37 mm spur gearbox, sold in five gear ratios (1:30, 1:56, 1:131, 1:270, 1:506), each **with or without** a Hall-sensor quadrature encoder [PP].
- Without encoder = `SPG30-GRxx` (RM49.00); with encoder = `SPG30E-GRxx` (RM76.00) [PP]. The encoder wires are **not detachable** [PP].
- Output: **6 mm D-shaft** ("6mm diameter D-shaped shaft with 15mm length") for Cytron's 6 mm metal key hub [PP].
- Mounts with Cytron's "DC Geared Motor Bracket (SPG30/SPG50)" (`motor-bracket-spg30-spg50.md`) [PP].
- Brand on the page: Cytron OEM; the motor body is labelled "cytron" with model, RPM and kg·cm [PP: img].

## Specifications
### Per-ratio figures — Cytron datasheet [DS] (12 V, after 30 s run-in)
| Model | Gear ratio | No-load speed | Rated load | Rated speed | Max torque (stall prohibited) | Rated power |
|---|---|---|---|---|---|---|
| SPG30(E)-GR30 | 1:30 | 333 rpm ±10% | 2.8 kg·cm | 266 rpm ±10% | 14 kgf·cm | 7.852 W (SPG30E: 7.851 W) |
| SPG30(E)-GR56 | 1:56 | 178 rpm ±10% | 4 kg·cm | 140 rpm ±10% | 20 kgf·cm | 5.928 W |
| SPG30(E)-GR131 | 1:131 | 76 rpm ±10% | 8.6 kg·cm | 60 rpm ±10% | 43 kgf·cm | 5.504 W |
| SPG30(E)-GR270 | 1:270 | 37 rpm ±10% | 11 kg·cm | 29 rpm ±10% | 56 kgf·cm | 0.349 W (as printed) |
| SPG30(E)-GR506 | 1:506 | 20 rpm ±10% | 14 kg·cm | 16 rpm ±10% | 56 kgf·cm | 0.490 W (as printed) |

Common to every ratio [DS]: no-load current ≤ 160 mA ("160≤160mA" as printed); starting voltage 2.0 V; starting current 75 mA; **rated load current 1288 mA**; **stall current 5800 mA**; shaft end play 0.05–0.5 mm; rated voltage 12 V DC; rotation CW viewed from the output shaft; operating −10 to +50 °C, 30–80 % RH; measured horizontally on a regulated DC supply.

GR30 performance curve [DS p2]: no load 333 rpm / 160 mA; max efficiency 50.6 % at 1994 g·cm, 286 rpm, 963 mA; max output 11.96 W at 7000 g·cm, 167 rpm, 2980 mA; stall 14000 g·cm, 5800 mA; torque constant 2482 g·cm/A; speed constant 33 rpm/V.

### Per-ratio figures — product page table [PP] (same for SPG30 and SPG30E)
| Model | Rated current | Rated torque | Rated speed | No-load current | No-load speed | Stall torque | Stall current |
|---|---|---|---|---|---|---|---|
| GR30 | 400 mA | 1.14 kg·cm | 266 rpm | 120 mA | 333 rpm | 4.5 kg·cm | 1.2 A |
| GR56 | 400 mA | 2.1 kg·cm | 112 rpm | 120 mA | 178 rpm | 8.4 kg·cm | 1.2 A |
| GR131 | 400 mA | 5 kg·cm | 60 rpm | 120 mA | 76 rpm | 20 kg·cm | 1.2 A |
| GR270 | 400 mA | 10 kg·cm | 29 rpm | 120 mA | 37 rpm | 40 kg·cm | 1.2 A |
| GR506 | 400 mA | 19 kg·cm | 16 rpm | 120 mA | 20 rpm | N/A* | 1.2 A |
*"SPG30-GR506 is not allowed to apply stalled load." [PP]

### Mechanical and encoder
| Item | Value | Src |
|---|---|---|
| Rated voltage | 12 V DC | [DS][PP] |
| Gearbox | Spur gear, Ø37 mm; length L = 22 mm (GR30), 24 (GR56), 26.5 (GR131), 26.5 (GR270), 29 (GR506) | [DS drawing][PP: img] |
| Motor can (no encoder) | Ø34.5 mm × 30.3 ± 0.3 mm long, two solder tabs at the rear | [DS drawing] |
| Motor + encoder (SPG30E) | 47 mm long behind the gearbox, Ø34.5 mm ([PP: img] shows Ø35) | [DS drawing] |
| Output shaft | Ø6 mm (−0.01/−0.03), D-flat to 5.5 mm; 21 mm from the gearbox face to the shaft end, with 15 mm and 12 mm sub-dimensions (the 12 mm is the D-flat length — inferred); page text: "6mm … D-shaped shaft with 15mm length" | [DS drawing][PP] |
| Shaft position | Offset **7 mm** from the gearbox centre (SPG30E drawing in the PDF shows 7.5 mm; page image shows 7.0) | [DS drawing][PP: img] |
| Gearbox mounting holes | **6 × M3** threaded on a **Ø31 mm** circle on the gearbox face; Ø12 mm shaft boss | [DS drawing] |
| Encoder type | Incremental Hall-sensor encoder, 2 channels (A, B) | [PP][PP: img] |
| Encoder resolution | **16 PPR** at the motor; output resolution = 16 × gear ratio (e.g. 480 per output turn for GR30 — arithmetic, inferred) | [PP][PP: img] |
| Encoder supply | 3.3 V – 5 V | [PP] |
| Encoder lead | 6 wires ending in a 2.54 mm female pin-header housing, not detachable | [PP] |
| Weight | Not stated | — |
| Warranty | Not shown (warranty field hidden) | [PP] |

### Packing list [PP]
| Option | Contents |
|---|---|
| Without encoder | 1 × 12V 37mm DC geared motor without encoder (ratio as selected) |
| With encoder | 1 × 12V 37mm DC geared motor with encoder (ratio as selected) |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Options: "With or Without Encoder" × "SPG30 Motor Gear Ratio" (GR 1:30 / 1:56 / 1:131 / 1:270 / 1:506); price range RM49.00 – RM76.00 [PP].
- Accessories offered on the page: DC Geared Motor Bracket (SPG30/SPG50) RM14.00; Metal Key Hub – 6mm RM10.50 (was RM21.00) [PP].
- "You May Also Need" lists the 10Amp 5V-30V DC Motor Driver (2 Channels) (MDD10A) [PP].
- Resources: Datasheets "SPG30 & SPG30E series" (Drive folder); tutorials "How to choose a DC motor", "5 Easiest Ways to Control A DC Motor", "Control a DC Motor Using Arduino" (3A Motor Driver Shield getting-started); related tutorial "Product Counting in Continuous Feed Systems" (Hadrie Hakimi, 06 May 2026) [PP].

## Interfaces, terminals and pin mapping
Wire identification — motors with encoder [PP: img "Wire Identification Chart"]:

| Wire colour | Function |
|---|---|
| Red | DC motor power supply (+) |
| Black | DC motor power supply (−) |
| Green | Encoder power supply (−) = GND |
| Blue | Encoder power supply (+) = 3.3–5 V |
| Yellow | Encoder signal A |
| White | Encoder signal B |

- Motors **without** encoder: two solder tabs on the motor's rear cap; no leads are listed [DS drawing]. Polarity marking: the rear-view drawing marks one tab "+" (symbol only) [DS drawing].
- Reversing the motor leads reverses rotation [PP: tutorial "Choosing a DC Motor"].
- **Do not use the IG42E colour scheme** from the Cytron encoder tutorial (brown = Hall VCC, green = GND, blue = A, purple = B) for SPG30E — on SPG30E green is GND and **blue is VCC** [PP: tutorial vs PP: img].

## Rules and gotchas (for code, wiring and tutorials)
- **Size the driver for 5.8 A stall**, not the page's 1.2 A: the datasheet gives rated current 1288 mA and stall current 5800 mA for every ratio [DS]. Cytron's own rule: the driver must cope with the motor's peak current [PP: tutorial "5 Easiest Ways"].
- **Never stall GR506** (page) — and the datasheet marks max torque on every ratio as "stall prohibited" (禁止堵转) [DS][PP].
- Encoder supply is 3.3–5 V only; never put it on the 12 V motor supply [PP].
- Count both edges of A and B for 4× decoding only if the library supports it; the page states 16 PPR and "16 × GR = resolution" without saying which edge count that is (see *Needs verification*).
- Encoder wires cannot be unplugged from the motor; plan cable length and strain relief [PP].
- The shaft is a **D-shaft**, not round; the 6 mm metal key hub's two M3 set screws should bear on the flat (general practice, inferred).

## Power and electrical limits
- 12 V DC rated [DS][PP]. Starting voltage 2.0 V [DS].
- Rated current 1288 mA; stall current 5800 mA; no-load ≤ 160 mA [DS]. (Page: 400 mA / 1.2 A / 120 mA — superseded, see *Conflicts*.)
- **Driver choice (inferred from the [DS] currents and the driver KB files):**
  - **MDD10A** (`mdd10a.md`, 2 ch, 10 A continuous / 30 A peak, 5–30 V) — the page's suggested driver; covers stall current with margin.
  - **MD10C** (`md10c.md`, 1 ch, 13 A / 30 A) or **MD10-POT** (`md10-pot.md`) — single motor.
  - **MDD3A** (`mdd3a.md`, 3 A continuous / 5 A peak, 4–16 V) — runs the motor at rated load but **below the 5.8 A stall current**; acceptable only if stalls are avoided.
  - **3A Motor Driver Shield** (`shield-3amotor.md`, 1.2 A continuous / 3 A peak) — below the datasheet rated current; not recommended for loaded use. **Maker Drive** (`maker-drive.md`, 2.5–9.5 V) cannot run a 12 V motor at rated voltage.

## Software support
- No motor-specific library. Drive with Cytron motor-driver libraries (see driver files). Encoder reading: Cytron tutorial "Measuring DC Motor RPM Through Built-in Hall Sensor Encoder" (Idris Zainal Abidin, 04 Jul 2018) lists "SPG30 With Encoder (Spur Gear)" among supported motors but its wiring table is for IG42E [PP: tutorial].
- Related tutorial on the page: "Product Counting in Continuous Feed Systems" (Node-RED, encoder feedback) [PP].

## Compatibility and accessories
- Bracket: DC Geared Motor Bracket (SPG30/SPG50) `HD-BK-SPG` — fits SPG30, SPG30E, SPG50 (`motor-bracket-spg30-spg50.md`) [PP].
- Shaft hubs: Metal Key Hub – 6mm `CO-SPG` (`metal-key-hub.md`); 6mm Key Hub for 60mm Mecanum Wheel `CO-MEC-06` (`mecanum-key-hub-6mm.md`) [PP].
- Drivers: see *Power and electrical limits* (`mdd10a.md`, `md10c.md`, `md10-pot.md`, `mdd3a.md`, `mdds10.md`, `mdds30.md`). `mdds30.md` lists SPG30/SPG30E among its suitable motors [PP of MDDS30].
- Higher-speed sibling: SPG30HP 380/1100 RPM (`high-power-dc-geared-motor-12v.md`).

## Common mistakes / troubleshooting
- **Driver or fuse trips at start or when blocked** → inrush/stall reaches ~5.8 A [DS]; use a ≥ 10 A-class driver or avoid stalls.
- **Encoder reads nothing** → Blue is VCC and Green is GND on this motor [PP: img]; check 3.3–5 V supply.
- **Wrong RPM from encoder count** → multiply 16 PPR by the gear ratio [PP: img]; check single vs quad decoding.
- **Key hub slips** → tighten the set screws on the D-flat (inferred).
- **GR506 gearbox damaged** → it must not be stalled [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Rated current | [DS] 1288 mA (all ratios) | [PP] 400 mA | [DS] wins; driver sizing uses 1288 mA |
| Stall current | [DS] 5800 mA | [PP] 1.2 A | [DS] wins (GR30 curve also shows 5800 mA) |
| No-load current | [DS] ≤ 160 mA | [PP] 120 mA | [DS] wins |
| Rated torque / load | [DS] 2.8 / 4 / 8.6 / 11 / 14 kg·cm | [PP] 1.14 / 2.1 / 5 / 10 / 19 kg·cm | [DS] wins; [PP] values are lower except GR506 |
| Max / stall torque | [DS] 14 / 20 / 43 / 56 / 56 kgf·cm (stall prohibited) | [PP] 4.5 / 8.4 / 20 / 40 / N/A kg·cm | [DS] wins |
| GR56 rated speed | [DS] 140 rpm | [PP] 112 rpm | [DS] wins |
| Rated power GR270 / GR506 | [DS] 0.349 W / 0.490 W | — | Implausible vs 11 kg·cm × 29 rpm (≈ 3.3 W, arithmetic) — likely a datasheet typo; not used |
| Encoder can diameter / shaft offset | [DS] Ø34.5 mm / 7.5 mm | [PP: img] Ø35 mm / 7.0 mm | [DS] wins; ±0.5 mm, confirm on a sample |
| Shaft length | [DS] 21 mm from gearbox face (15 / 12 sub-dims) | [PP] "15mm length" | Not a true conflict: 15 mm is likely the length beyond the Ø12 boss (inferred) |

## Needs verification
- Why the page table differs from the datasheets (different test, older motor batch, or error) — ask the product team.
- Whether "16 PPR" is per channel rising edges (so 4× decoding = 64 counts per motor turn).
- Weight; warranty period (field hidden on the page).
- Original motor manufacturer (not named).
- Datasheets SPG30E-GR56 / GR131 / GR270 were listed in the folder but not opened (the SPG30E-GR30 and GR506 PDFs match the non-encoder ones).
- Encoder connector pin order inside the 2.54 mm housing (only colours are given).

## Sources
- [DS] Drive folder "V-SPG30" (Cytron document — link not public) — SPG30-GR30.pdf (3 pages: Motor Specification, Motor Performance Curve, Dimension; created 6 Mar 2025), SPG30-GR56/GR131/GR270/GR506.pdf (p1 read), SPG30E-GR30.pdf (p1, p3 read; created 7 Mar 2025), SPG30E-GR506.pdf (p1 read); read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-12v-37mm-dc-geared-motor — read 2026-10-21 (text, spec tables, 10 variant codes/prices/stock, images `v-spg30-wire-identification-chart-v2.png`, `v-spg30-dimension-spg30.png`, `v-spg30-dimension-spg30e-v2.png`, options, bracket and key-hub images)
- [PP: tutorial] https://my.cytron.io/tutorial/choosing-dc-motor ; https://my.cytron.io/tutorial/5-easiest-ways-control-dc-motor ; https://my.cytron.io/tutorial/getting-started-3a-motor-driver-shield/ ; https://my.cytron.io/tutorial/measuring-dc-motor-rpm-built-hall-sensor-encoder — read 2026-10-21 for relevant facts
- KB cross-references: `mdd10a.md`, `md10c.md`, `md10-pot.md`, `mdd3a.md`, `shield-3amotor.md`, `maker-drive.md`, `mdds30.md`, `motor-bracket-spg30-spg50.md`, `metal-key-hub.md`, `mecanum-key-hub-6mm.md`, `high-power-dc-geared-motor-12v.md`
