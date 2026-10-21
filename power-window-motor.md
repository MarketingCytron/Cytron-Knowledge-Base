# Power Window Motor with Coupling (Left / Right) — Verified Reference

| | |
|---|---|
| Product code | `MO-PW-CL` (Left) and `MO-PW-CR` (Right) — two listings [PP] |
| Family | Motors (Cytron OEM) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: both product pages read in full in the browser; "Motor's Dimension" (Google Doc "Power Window Dimension", Cytron drawing) and "Coupling's Dimension" (Cytron SolidWorks drawing "Bush - PW - User", rev 1.1, 27 Mar 2023) read via the Drive connector; page images (Left/Right pair photo, mounting example) viewed |
| Primary source | No motor datasheet is linked. Primary sources = **Cytron product pages** https://my.cytron.io/cytron-oem/p-power-window-motor-with-coupling-left and …-right, read 2026-10-21 [PP], the **"Power Window Motor Dimension"** drawing [PP: drawing] and the **coupling drawing "Bush - PW - User" v1.1** [PP: drawing] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = the two product pages (identical except the side and the extra duty-cycle note on the Right page). [PP: drawing] = the motor outline drawing (Cytron-headed, mm, "REF." dimensions) and the Cytron coupling drawing. [PP: img] = page photos. The automotive maker of the motor is not named. The bundle of two of these motors with 5-inch wheels is `motor-mount-5in-wheel-bundle.md`; the bare "Power Window Motor (Wira) – Left/Right" (RM42.00, without coupling) seen under "You May Also Need" is a different listing, not covered here.

## What it is
- A 12 V automotive power-window motor (brushed DC motor + worm gear) with Cytron's custom **coupling/hub** fitted in place of the original "odd output joint", so external parts attach with **3 screws** [PP].
- The housing is not symmetrical, so it is sold as a **Left** (`MO-PW-CL`) and a **Right** (`MO-PW-CR`) output version — "Make sure you get the correct model before you order" [PP].
- For a mobile robot Cytron points to the motor & wheel kit instead (`motor-mount-5in-wheel-bundle.md`) [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Voltage rating | 12 V DC | [PP] |
| Rated speed | 60 RPM | [PP] |
| Rated torque | 2.9 N·m (30 kgf·cm) | [PP] |
| Rated current | less than 15 A at 12 V | [PP] |
| Stall torque (locked) | 9.8 N·m (100 kg·cm) | [PP] |
| Stall current (locked) | less than 28 A at 12 V | [PP] |
| Duty | Tested driving a car window up and down for 8 s, survives 10,000 times; "Not meant for continuous driving without stopping" (stated on the Right page and on the bundle page) | [PP] |
| Weight | 680 g | [PP] |
| Overall length | 145.5 mm REF (motor 72.0 mm REF) | [PP: drawing] |
| Motor can | Ø39.0 mm REF; housing 62.0 mm REF high, 30.3 mm thick | [PP: drawing] |
| Gear housing | Ø66.0 mm REF; profile 16.7 / 13.5 / 8.7 mm REF | [PP: drawing] |
| Mounting holes (motor) | **4 × ISO M6 × 1.0 tapped**; horizontal pair 44.6 mm each side of the output axis; vertical positions 45.0 mm above and 43.5 mm below; one hole offset 11.3 mm / 6.0 mm (as drawn) | [PP: drawing] |
| Leads | Gray and Black | [PP: drawing] |
| Coupling ("Bush - PW - User") | Ø40 mm flange × 12 mm, Ø24 mm spigot, 37 mm overall; **3 × tapped M5** on a **Ø31 mm** circle at 120°; spigot end "is attached to motor"; C0.5 chamfers; material not stated | [PP: drawing] |
| Encoder | None | [PP] |
| Warranty | 3 months from purchase | [PP] |

### Packing list [PP]
| Listing | Contents |
|---|---|
| MO-PW-CL | Power Window Motor with Coupling (Left); 3 × M5 screw |
| MO-PW-CR | Power Window Motor with Coupling (Right); 3 × M5 screw |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Description images: mounting example (original output joint, a brake disc and sprocket as example parts), single-motor photo, a **Left/Right pair photo** and the motor & wheel kit photo [PP: img]. In the pair photo the Left motor's lead is black and the Right motor's is grey [PP: img — appearance only].
- Resources: "Motor's Dimension" (Google Doc) and "Coupling's Dimension" (Drive PDF) [PP].
- "You May Also Need": the other side's motor, Motor Mount & 5 Inches Wheel Bundle, Power Window Motor (Wira) Left/Right, DC 12V Worm Gear Motor, 30Amp 7V-35V SmartDrive (2 ch), 10Amp 5V-30V (2 ch), 40Amp 10V-45V SmartDrive, 30Amp 5V-30V driver, 5 Inches Robot Wheel with 8mm Key Hub / without hub [PP].

## Interfaces, terminals and pin mapping
- Two motor leads, **Gray** and **Black** [PP: drawing]; which polarity gives which rotation is not stated. Reversing them reverses the motor (general DC-motor behaviour; [PP: tutorial "Choosing a DC Motor"]).
- Output: the Cytron coupling's **3 × M5 tapped holes on Ø31 mm** take the 3 supplied M5 screws [PP][PP: drawing]. The 5-inch robot wheel has 3 × Ø5 holes on the same Ø31 mm circle (`robot-wheel-5in.md`) — this is how the bundle mounts its wheels (inferred from both drawings and the bundle photo).
- Frame mounting: 4 × M6 × 1.0 tapped holes in the gear housing [PP: drawing]; no bracket is sold for this motor on the page.

## Rules and gotchas (for code, wiring and tutorials)
- **Order the correct side.** Left and Right are mirror housings; for a two-wheel robot you need one of each [PP].
- **Intermittent duty:** rated for 8-second window strokes, "not meant for continuous driving without stopping" [PP]. Allow cooling in tutorials that run it long.
- **Worm drive holds position**: the output cannot be back-driven easily (bundle page, citing Wikipedia "Worm drive") [PP of `motor-mount-5in-wheel-bundle.md`] — good for pushing robots, but don't try to turn the wheel by hand.
- **High current:** rated < 15 A, stall < 28 A at 12 V [PP]; use thick wires, a fuse and a 30 A-class driver (inferred).
- Coupling screws are M5 (supplied: 3) [PP]; the motor's own frame holes are M6 (screws not supplied) [PP: drawing].

## Power and electrical limits
- 12 V DC; rated current < 15 A; stall current < 28 A [PP].
- **Driver choice (inferred from these currents and the driver KB files):**
  - **MD30C** (`md30c.md`, 1 ch, 30 A continuous / 80 A peak, 5–30 V) and **MDDS30** (`mdds30.md`, 2 ch, 30 A / 80 A, 7–35 V; its page lists power-window motors as suitable) — Cytron's own recommendations on the bundle page.
  - **SmartDrive40** (`smartdrive40.md`, 40 A, 10–45 V) and **MDDS60** (`mdds60.md`) — also adequate.
  - **MDD20A** (`mdd20a.md`, 20 A continuous / 60 A peak) — covers rated current and short stalls (inferred).
  - **10 A drivers** (MDD10A `mdd10a.md`, SHIELD-MD10 `shield-md10.md`, MD10C 13 A `md10c.md`) are **below the < 15 A rated current**; Cytron's pages still suggest them ("10A shield" on the bundle page; MDD10A under "You May Also Need") — acceptable only for light loads and short runs (see *Conflicts*).

## Software support
- None specific. Any PWM/DIR or RC-capable Cytron driver library applies (see driver files).

## Compatibility and accessories
- Wheel: 5 Inches Robot Wheel (`robot-wheel-5in.md`) bolts to the coupling (3 × M5 on Ø31 mm — inferred match); the ready-made pair is `motor-mount-5in-wheel-bundle.md`.
- Drivers: `md30c.md`, `mdds30.md`, `smartdrive40.md`, `mdds60.md`, `mdd20a.md`.

## Common mistakes / troubleshooting
- **Robot spins instead of driving straight** → two motors of the same side were bought, or one motor's leads need swapping (Left/Right housings turn opposite ways when mirrored — inferred).
- **Driver overheats / trips** → current < 15 A rated, < 28 A stall [PP]; use a 30 A driver.
- **Motor gets hot after long runs** → not designed for continuous duty [PP].
- **Screws strip in the coupling** → use the supplied M5 screws; the holes are tapped M5 [PP][PP: drawing].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Suitable driver current | [PP] rated current < 15 A at 12 V | [PP] "You May Also Need" MDD10A; bundle page "10A shield" | Rated current wins; 10 A drivers only for light loads (inferred) |
| Duty-cycle note | [PP Right page] 8 s up/down × 10,000, not continuous | [PP Left page] note absent | Same motor; note applies to both (inferred) |

## Needs verification
- Original automotive model / manufacturer of the motor.
- Coupling material and how it is fixed to the motor's output (not stated).
- Lead polarity vs rotation direction for Left and Right versions.
- No-load speed and no-load current (only rated and stall values are given).
- Lead length and connector (bundle photo shows a white 2-pin plug — not stated for these listings).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-power-window-motor-with-coupling-left — read 2026-10-21
- [PP] https://my.cytron.io/cytron-oem/p-power-window-motor-with-coupling-right — read 2026-10-21
- [PP: drawing] "Power Window Dimension" Google Doc (Cytron document — link not public) (exported as PDF, read 2026-10-21)
- [PP: drawing] "Bush - PW - User" v1.1 (27 Mar 2023) (Cytron document — link not public) — read 2026-10-21
- [PP: img] `MO-PW-Pair 2019.jpg`, `Power Window Motor Mounting.JPG` — viewed 2026-10-21
- KB cross-references: `motor-mount-5in-wheel-bundle.md`, `robot-wheel-5in.md`, `md30c.md`, `mdds30.md`, `smartdrive40.md`, `mdds60.md`, `mdd20a.md`, `mdd10a.md`, `shield-md10.md`, `md10c.md`
