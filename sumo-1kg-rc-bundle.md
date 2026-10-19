# 1KG Sumo Robot Bundles - Radio Controlled (RC) — Verified Reference

| | |
|---|---|
| Product code | `V-SUMO-1KG-RC` [PP] (the page offers three options — Complete (with body) / Basic (without body) / 3D Printed Body only — and the STL folder is named `KIT-SUMO-RC-3DP`; per-option codes not stated) |
| Family | Sumo robot kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | **Cytron product page** (read by the coordinator 2026-10-19) [PP] — https://my.cytron.io/p-radio-controlled-rc-1kg-sumo-robot-kits. The two Cytron user-guide tutorials linked from the page ("1KG RC Sumo Robot Starter Kit User Guide using MDDRC10", "1KG RC Sumo Robot using MDDRC10") could **not** be fetched here (my.cytron.io and www.cytron.io blocked). No kit datasheet exists. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = product page extract (the Complete packing list is truncated after the 6" blade). [DS: MDDRC10] = the MDDRC10 datasheet facts already recorded in `mddrc10.md` (Rev 1.0, Aug 2020) — used only for the wiring and limits that the kit inherits from its driver. STL folder: Google Drive folder "KIT-SUMO-RC-3DP" (created 12 Mar 2025, Cytron-owned); its file list could not be read here.

**Kit rule:** the driver is not re-documented — see `mddrc10.md`.

## What it is
A plug-and-play, no-coding 1 kg-class sumo robot bundle whose "microcontroller" is the MDDRC10 dual-channel R/C motor driver: two 12 V 580 RPM 3.5 kgf.cm brushed geared motors, 42 × 30 mm silicon wheels, an 11.1 V 1300 mAh LiPo, metal base plates, a 6" stainless steel blade and a 3D-printed PLA body, driven directly from an RC receiver [PP]. The assembled robot is 15 cm × 15 cm with an actual weight of 856 g [PP]. Sold as Complete (with body), Basic (without body) or 3D Printed Body only [PP]. "NO warranty"; "comes in loose parts" (self-assembly) [PP].
Positioning (marketing, not spec): "plug and play, no coding" [PP].

## Specifications
No datasheet spec table exists; rows are the product page "Features"/specification block.

| Item | Value | Src |
|---|---|---|
| Controller | "Microcontroller: MDDRC10" — in fact an R/C motor driver with no user-programmable MCU (`mddrc10.md` [DS]) | [PP] |
| Programming | "plug and play, no coding" | [PP] |
| Motor speed | 580 RPM | [PP] |
| Motor torque | 3.5 kgf.cm | [PP] |
| Motors | 2 × 12 V 580 RPM 3.5 kgf.cm high power brushed DC geared motor | [PP] |
| Body | PLA (3D printed), 15 cm × 15 cm; STL files in the Drive folder | [PP] |
| Actual weight | 856 g | [PP] |
| Battery | 11.1 V 1300 mAh LiPo (3S) | [PP] |
| Wheels | 2 × silicon wheels 42 mm × 30 mm | [PP] |
| Blade | 1 × 6" stainless steel blade | [PP] |
| Base | 2 × metal base for mini sumo robot | [PP] |
| Battery lead | Dean T LiPo wire extension | [PP] |
| Control | "RC controller" (transmitter/receiver inclusion not stated in the extract — see Needs verification) | [PP] |
| Options | Complete (with body) / Basic (without body) / 3D Printed Body only | [PP] |
| Warranty | "NO warranty" | [PP] |
| Price | RM99.90 – RM633.84 across the three options (Cytron product page, read 2026-10-19) | [PP] |

**Packing list, Complete [PP]** (truncated after the blade): 1 × MDDRC10, 2 × 12V 580RPM 3.5kgfcm high power brushed DC geared motor, 2 × silicon wheels 42x30mm, 1 × LiPo 11.1V 1300mAh, 2 × metal base for mini sumo robot, Dean T LiPo wire extension, 1 × 6" stainless steel blade, …
**Basic** = without body; **3D Printed Body only** = body alone (exact per-option lists not in the extract) [PP].
**Not included / not stated:** LiPo charger not in the visible list; RC transmitter/receiver inclusion not stated [PP].

## Interfaces, terminals and pin mapping
The kit's own guide could not be read; wiring below is what the MDDRC10 datasheet states for any build (`mddrc10.md` [DS: MDDRC10]) and the kit-level facts the page gives:
- **Battery → MDDRC10 Power Input Terminal:** VB+ positive, VB− negative, via the kit's Dean T LiPo wire extension [PP]. **No reverse-polarity protection** — "Connecting in reverse polarity will damage the motor driver instantaneously" [DS: MDDRC10].
- **Motors → MDDRC10 motor terminals:** two channels, bidirectional [DS: MDDRC10].
- **RC receiver → MDDRC10 RC Input:** RC1 and RC2 signal pins, +5 V (500 mA max, "do not use this to power the servo motor") and GND. Two 2561 3-way extension wires come with the MDDRC10 itself [DS: MDDRC10][PP].
- **Mode selection switch:** Mixed Mode — RC1 = forward/backward, RC2 = left/right (mixed to both motors), "preferred for differential-drive mobile robots"; Independent Mode — RC1 = left motor, RC2 = right motor [DS: MDDRC10]. Which mode the kit guide uses is not readable here.
- **Neutral calibration:** automatic at every power-up [DS: MDDRC10] — power the robot on with the transmitter sticks centred.
- **Test buttons and motor LEDs** on the MDDRC10 allow a motor check without a transmitter [DS: MDDRC10].
- **Start button / auto mode:** none — this is an RC-only bundle with no programmable controller [PP][DS: MDDRC10].

## Rules and gotchas (for code, wiring and tutorials)
- There is no code: do not write "upload the sketch" or "MakeCode" tutorials for this bundle [PP].
- "Microcontroller: MDDRC10" on the page is loose wording — MDDRC10 is a motor driver; say "RC motor driver" in content [PP][DS: MDDRC10].
- 856 g is the actual weight stated — under a 1 kg class limit, but the limit itself comes from the competition rulebook, not Cytron [PP].
- Reversed battery kills the driver instantly and there is no warranty on this bundle — double-check Dean T polarity before the first power-up [DS: MDDRC10][PP].
- The MDDRC10 +5 V pin feeds the receiver only (500 mA); do not hang a servo on it [DS: MDDRC10].
- Error blink codes on the MDDRC10 LED: 2 = no/invalid RC signal, 3 = under-voltage or MOSFET driver fault, 4 = over-voltage (regeneration) (`mddrc10.md` [DS]).
- Robot drives in circles / one wheel reversed: swap that motor's two wires at the driver terminal, or invert the channel on the transmitter (driver is wiring-direction dependent) [DS: MDDRC10].
- Loose parts: the page explicitly says the kit "comes in loose parts" — plan assembly time and tools in any tutorial [PP].
- Training blade substitute: PCB Plate for Sumo Robot, 15 cm variant recommended for 1 kg robots (`pcb-sumo-plate.md` [PP]).

## Power and electrical limits
- Battery 11.1 V 1300 mAh LiPo (3S) [PP], within the MDDRC10's 7–30 V input [DS: MDDRC10].
- MDDRC10: 10 A continuous / 30 A peak per channel (peak current-limited, temperature-dependent, no duration stated); no reverse-polarity protection; 5 V 500 mA receiver output [DS: MDDRC10].
- Motor current ratings for the 12 V 580 RPM 3.5 kgf.cm motors: not stated by any kit source.
- Charger: not in the visible packing list [PP] (the SUMO:BIT kit page offers a 2–3 cell LiPo balance charger as an accessory — not stated for this bundle).
- "NO warranty" [PP].

## Software support
- None required — "plug and play, no coding" [PP]; MDDRC10 needs no programming [DS: MDDRC10].
- 3D body: STL files in the Cytron Drive folder "KIT-SUMO-RC-3DP" (https://drive.google.com/drive/folders/1ah8zN67osF_GZj4KbN-Ox7QSPSIbz36X) [PP]; file names not readable here.

## Compatibility and accessories
- Driver: MDDRC10 — see `mddrc10.md`. (Not MDDRC5: different ratings and reverse-polarity protection — do not mix the two files' facts.)
- RC: any transmitter/receiver that gives standard RC pulses on two channels (MDDRC10 accepts 10–100 Hz RC pulses, `mddrc10.md` [DS]); specific sets tested in the kit guide not readable.
- Blade substitute: `pcb-sumo-plate.md` (15 cm) [PP].
- Related Cytron 1 kg kits: SUMO:BIT Robot Kit (programmable, micro:bit) — different product, documented separately.
- Related tutorials on the page: "1KG RC Sumo Robot Starter Kit User Guide using MDDRC10", "1KG RC Sumo Robot using MDDRC10" [PP]; MDDRC10 datasheet link [PP].

## Common mistakes / troubleshooting
- Driver dead after first connection: reversed battery (no protection, no warranty) [DS: MDDRC10][PP].
- No response to the transmitter: receiver not bound or RC1/RC2 not wired to the right channels — MDDRC10 LED blinks 2× [DS: MDDRC10].
- Robot turns when the stick is pushed forward: wrong mode (Independent vs Mixed) or one motor reversed [DS: MDDRC10].
- Receiver browns out: servo or other load on the driver's +5 V pin [DS: MDDRC10].
- Calling the kit "programmable" or "autonomous": it has no controller or sensors [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Nature of the MDDRC10 | [PP] "Microcontroller: MDDRC10" | [DS: MDDRC10] motor driver "controlled directly from an R/C receiver, no microcontroller or coding needed" | Datasheet wins: it is a motor driver |
| "Mini sumo" base plates in a 1 kg kit | [PP] packing list: "2x metal base for mini sumo robot" | [PP] title/specs: 1KG sumo robot, 15 cm × 15 cm, 856 g | Page-internal naming; the part is Cytron's "metal base for mini sumo robot" product used here as weight/base plates |
| Peak current wording | `mddrc10.md`: product page "30A peak" without conditions | [DS: MDDRC10] peak limited by over-current circuit and temperature | Quote the datasheet conditions |

## Needs verification
- Whether an RC transmitter/receiver is included in the Complete bundle — the page says "Control: RC controller" but the packing list extract is truncated.
- Full Complete packing list after the 6" blade (screws, wires, switch, charger?) and the exact Basic / Body-only contents.
- Which MDDRC10 mode (Mixed/Independent) and which receiver channels the Cytron user guide uses; tested transmitter models.
- Whether 856 g includes battery and blade.
- Motor current ratings and gearbox details for the 12 V 580 RPM 3.5 kgf.cm motors.
- STL file names and body part count in the Drive folder.
- Both Cytron tutorials (titles, authors, dates) — pages not readable here.

## Sources
- [PP] Product page (read by coordinator 2026-10-19) — https://my.cytron.io/p-radio-controlled-rc-1kg-sumo-robot-kits
- [PP] Cytron tutorials linked from the page (not readable here) — https://my.cytron.io/tutorial/1kg-rc-sumo-robot-starter-kit-user-guide-using-mddrc10 · https://my.cytron.io/tutorial/1kg-rc-sumo-robot-using-mddrc10
- [PP] STL folder "KIT-SUMO-RC-3DP" (Drive, created 2025-03-12; contents not listable here) — https://drive.google.com/drive/folders/1ah8zN67osF_GZj4KbN-Ox7QSPSIbz36X
- [DS: MDDRC10] MDDRC10 Datasheet Rev 1.0, Aug 2020, as recorded in /home/claude/kb/mddrc10.md — mirror https://cdn.robotshop.com/media/c/cyt/rb-cyt-288/pdf/cytron-10a-7v-30v-dual-dc-motor-driver-r-c-datasheet.pdf
- KB cross-references: /home/claude/kb/mddrc10.md · /home/claude/kb/pcb-sumo-plate.md
