# Motor Mount & 5 Inches Wheel Bundle — Verified Reference

| | |
|---|---|
| Product code | `KIT-PW-5WL` [PP] |
| Family | Robot parts and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: product page read in full in the browser; its "Detailed Drawing" (Google Doc "Power Window Dimension"), the in-page dimension image `Power Window Dimension.jpg` (same drawing) and "Wheel Dimension" (Cytron drawing "5 Inch Wheel") read; gallery photos viewed; linked tutorial "Choosing a DC Motor" read |
| Primary source | No datasheet. Primary sources = the **Cytron product page** https://my.cytron.io/cytron-oem/p-motor-mount-and-5-inches-wheel-kit, read 2026-10-21 [PP], and the two drawings it links [PP: drawing]. Component facts live in the component files (KIT RULE) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = bundle page. [PP: drawing] = motor drawing (also in `power-window-motor.md`) and "5 Inch Wheel" drawing (also in `robot-wheel-5in.md`). [PP: img] = gallery photos `motor-mount-and-5-inches-wheel-kit-40501` / `-a5862` (appearance only). KIT RULE: the motors and wheels are documented in their own files and are not re-documented here.

## What it is
- A **pair of power-window motors (one Left, one Right) with a 5-inch wheel already mounted on each** — a ready drive set for a two-wheeled robot, including combat robots [PP].
- The motors' worm gear "can prevent it from rotating from the external force … it is difficult for your opponent's robot to push your robot" (page quotes the Wikipedia "Worm drive" article on non-reversible transmission) [PP].
- Wheels are "made of thermoplastic rubber which provides absolute friction force on most of the surface" [PP].

| Component | Qty | KB file |
|---|---|---|
| Power window motor, Left | 1 | `power-window-motor.md` (MO-PW-CL; Cytron coupling, 3 × M5) |
| Power window motor, Right | 1 | `power-window-motor.md` (MO-PW-CR) |
| 5 Inches Robot Wheel, mounted | 2 | `robot-wheel-5in.md` (Ø127 mm, 3 × Ø5 holes on Ø31 mm) |

## Specifications
| Item | Value | Src |
|---|---|---|
| Voltage rating | 12 V DC | [PP] |
| Rated speed / torque | 60 RPM / 2.9 N·m (30 kgf·cm) | [PP] |
| Rated current | < 15 A at 12 V (per motor) | [PP] |
| Stall torque / current | 9.8 N·m (100 kg·cm) / < 28 A at 12 V | [PP] |
| Duty | Tested 8 s up and down, survives 10,000 times; not meant for continuous driving without stopping | [PP] |
| Motor dimension (w × l × h) | "~161.2 mm × 30.3 mm × 105.5 mm" | [PP] |
| Motor drawing | 145.5 mm REF long, 62 mm REF high, 30.3 mm thick; 4 × ISO M6 × 1.0 tapped mounting holes; leads Gray/Black | [PP: drawing] |
| Wheel | 5 in (Ø127 mm) × 25.4 mm, thermoplastic rubber tyre | [PP][PP: drawing] |
| Ground speed at rated speed | ≈ 0.40 m/s (60 RPM × 0.399 m circumference — arithmetic, inferred) | — |
| Warranty | 3 months (motor warranty from purchase date) | [PP] |

### Packing list [PP]
| Qty | Item |
|---|---|
| 1 pair | Power window motor (left and right) |
| — | "The wheels are mounted to power window motor." |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Note: "From April 2026 onwards, prices are subject to applicable SST … calculated during checkout where applicable" [PP].
- Driver advice on the page: "For Arduino lovers, you can utilize 10A shield to drive this motor. For normal control, try MD30C (single channel) or MDDS30 (dual channels). For RC (Radio Control) lovers, check out the MDDS30" [PP].
- Resources: Detailed Drawing (Google Doc), Wheel Dimension (Drive PDF), "How to choose a suitable Motor" (tutorial "Choosing a DC Motor") [PP].
- Gallery photos: blue tyres, each wheel held by 3 screws at the hub; motor leads end in a white 2-pin plug [PP: img — appearance only].

## Interfaces, terminals and pin mapping
- Per motor: two leads (Gray, Black on the drawing) [PP: drawing]; the photos show a white 2-pin plug on each lead [PP: img]. Plug type is not stated.
- Wheel-to-motor joint: Cytron coupling 3 × M5 on Ø31 mm ↔ wheel 3 × Ø5 on Ø31 mm (see `power-window-motor.md`, `robot-wheel-5in.md`; match inferred).
- Frame mounting: 4 × M6 × 1.0 tapped holes per motor housing [PP: drawing]; no bracket is included [PP].

## Rules and gotchas (for code, wiring and tutorials)
- Left and Right motors face opposite ways; for "forward" one motor's direction is inverted in code (or swap its leads) (inferred).
- Intermittent duty only; plan rest periods [PP].
- Use a **30 A-class driver** for full load: MD30C (`md30c.md`) ×2 or MDDS30 (`mdds30.md`) — the page's own picks [PP]. The page's "10A shield" (`shield-md10.md`, 10 A continuous) is below the < 15 A rated current; fine only for light loads (inferred, see *Conflicts*).
- Fuse and wire for up to ~28 A per motor at stall [PP].

## Power and electrical limits
- 12 V DC; per motor rated < 15 A, stall < 28 A [PP]; two motors can draw up to ~56 A combined at stall (arithmetic).
- Drivers: `mdds30.md` (dual, RC-capable), `md30c.md`, `smartdrive40.md`, `mdds60.md` (inferred), `shield-md10.md` only for light duty.

## Software support
- None specific; see the chosen driver's KB file.

## Compatibility and accessories
- Components: `power-window-motor.md`, `robot-wheel-5in.md`.
- Drivers: `mdds30.md`, `md30c.md`, `shield-md10.md`, `smartdrive40.md`, `mdds60.md`.
- Chassis, battery, castor and controller are not included [PP packing list].

## Common mistakes / troubleshooting
- **Robot turns in circles** → one side's direction needs inverting (mirror-image motors) (inferred).
- **Driver overheats** → < 15 A rated per motor [PP]; use 30 A drivers.
- **Robot can't be pushed by hand** → expected: worm drive is not back-drivable [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Motor overall size | [PP: drawing] 145.5 mm REF long × 62 mm REF × 30.3 mm | [PP] "~161.2 mm × 30.3 mm × 105.5 mm" (w × l × h) | Different envelopes (page figure probably includes the coupling/mount — inferred); 30.3 mm agrees |
| Suitable driver | [PP] rated < 15 A | [PP] "you can utilize 10A shield" | Rated current wins; 10 A shield for light loads only |

## Needs verification
- What the 161.2 × 105.5 mm envelope includes.
- Lead plug type and lead length.
- Whether the wheels are bolted with M5 screws into the Cytron coupling (photo shows 3 screws; assembly not described).
- Total bundle weight (motors 680 g each per `power-window-motor.md`; wheel weight not stated).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-motor-mount-and-5-inches-wheel-kit — read 2026-10-21
- [PP: drawing] (Cytron document — link not public) ("Power Window Dimension") and in-page `Power Window Dimension.jpg` — read 2026-10-21
- [PP: drawing] (Cytron document — link not public) ("5 Inch Wheel", rev 1.0, 3/3/2015) — read 2026-10-21
- [PP: tutorial] https://my.cytron.io/tutorial/choosing-dc-motor — read 2026-10-21
- KB cross-references: `power-window-motor.md`, `robot-wheel-5in.md`, `mdds30.md`, `md30c.md`, `shield-md10.md`, `smartdrive40.md`, `mdds60.md`
