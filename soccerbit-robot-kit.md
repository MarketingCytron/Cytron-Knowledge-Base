# 4 Wheel SOCCER:BIT Robot Bundles — Verified Reference

| Field | Value |
|---|---|
| Product code | V-SCRBIT-4WD [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review: live product page re-read in full (current Complete packing list now includes Joystick:bit V2, 4 × AAA, LiPo balance charger and LiPo indicator; with-micro:bit option = 2 × micro:bit Junior Kit V2) and the Cytron tutorial "Soccer Robot using SUMO:BIT" read (Azmir Che Azmi, 8 Aug 2025). Robot kit — SUMO:BIT follows its datasheet; kit accessories follow the guide tutorial (KB rule 7) |
| Primary source | Cytron product page "4 Wheel SOCCER:BIT Robot Bundles" (my.cytron.io, read by the coordinator 2026-10-19) [PP]. The page's "user manual" link resolves to the **MD13S User's Manual, V1.1, June 2018** (a motor-driver manual, not a SOCCER:BIT manual — see Conflicts). Guide tutorial (main source for the kit accessories, KB rule 7): "Soccer Robot using SUMO:BIT" (Azmir Che Azmi, 8 Aug 2025), read 2026-10-19 [PP: tutorial]. Board datasheet: "SUMO:BIT Datasheet, Rev 1.0, December 2024" — see `sumo-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A four-wheel-drive soccer robot bundle for the BBC micro:bit, using the SUMO:BIT board (with two MD13S motor drivers) as the controller, four 12 V 980 rpm GM25 geared motors on 42 × 30 mm silicone wheels, a 3S 1300 mAh LiPo and a 20 × 20 cm PLA 3D-printed body [PP]. It is programmed in MakeCode and driven by a Joystick:bit V2, which is included in the Complete option [PP]. "The Soccer Robot comes in loose parts. You will have to assemble them yourself." [PP]

Board references — do not re-document here: SUMO:BIT → `sumo-bit.md`; MD13S → `md13s.md`.

## Specifications
Kit-level facts only (product-page "Features" and packing list); board ratings are in `sumo-bit.md`.

| Item | Value | Src |
|---|---|---|
| Competition class | Soccer robot (4-wheel) | [PP] |
| Purchase options | Complete / Basic / 3D Printed Body only, each with or without micro:bit | [PP] |
| Microcontroller | SUMO:BIT (with 2× MD13S) — see `sumo-bit.md`, `md13s.md` | [PP] |
| Programming | MakeCode | [PP] |
| Motors | 4× 12 V 980 rpm 2.3 kgf·cm GM25 brushed DC geared motor | [PP] |
| Speed / torque (Features) | 980 rpm / 2.3 kgf·cm | [PP] |
| Wheels | 4× high-grade silicone wheels 42 mm × 30 mm | [PP] |
| Body | PLA 3D-printed body, 20 cm × 20 cm | [PP] |
| Weight | 1 kg | [PP] |
| Battery | 1× LiPo 11.1 V 1300 mAh | [PP] |
| Charger | 1× LiPo balance charger + 1× LiPo voltage indicator (Complete) | [PP] |
| Motor wiring parts | 2× Easy Clip wire splitter (2 in, 4 out); 18 AWG wires; Dean T connector | [PP] |
| Hardware / tools | 8× M3×20 with nylon lock nuts, 4× M3×20 with nuts, M2 Allen key | [PP] |
| Body parts | 3D-printed body, front weapon, 4 motor brackets | [PP] |
| Control | Joystick:bit V2 + 4× AAA batteries **included in the Complete option** (earlier page extract said "[optional]" — see Conflicts) | [PP] |
| micro:bit | With-micro:bit options: 2× micro:bit Junior Kit V2 (one for the robot, one for the Joystick:bit) | [PP] |
| Board electrical (page Specifications) | 7–25 V LiPo input; with MD13S 13 A per channel continuous, 30 A peak (<10 s), 20 kHz PWM; USB host 5 V 600 mA; servo 5 V; +5 V total 600 mA | [PP] (matches `sumo-bit.md` [DS]) |
| STL files | Google Drive folder "KIT-3DP-SCRBIT-4WD" (created 15 Dec 2025) linked from the page; contents not listable here | [PP] |
| Warranty | Not stated on the product page (field blank) | [PP] |
| Price | RM90.00–RM1,134.52 across options (Cytron product page, read 2026-10-19) | [PP] |

### Exact packing list (Complete) [PP]
1× SUMO:BIT with 2× MD13S; 4× 12 V 980 rpm 2.3 kgf·cm GM25 motors; 4× silicone wheel sets 42 × 30 mm; 1× LiPo 11.1 V 1300 mAh; 2× Easy Clip wire splitter (2 in, 4 out); wires; 8× M3×20 screws with nylon lock nuts; 4× M3×20 screws with nuts; M2 Allen key; 3D-printed body + front weapon + 4 motor brackets; 1× Joystick:bit V2; 4× AAA batteries (for the Joystick:bit); 1× LiPo balance charger; 1× LiPo voltage indicator; with-micro:bit options add 2× micro:bit Junior Kit V2.

**Basic** does **not** include the Joystick:bit V2 or the LiPo charger [DT, 19 Oct 2026]. 3D Printed Body only: not itemised on the page.

## Interfaces, terminals and pin mapping
Joystick setup from the guide tutorial [PP: tutorial]: the Joystick:bit's radio channel is chosen with the **A / B buttons** and confirmed with **A+B**; the robot and the joystick must be on the same channel. What the parts list implies and the SUMO:BIT guides state:
- The SUMO:BIT has two motor channels (one MD13S each) [DS]; the kit has four motors and two "2 in 4 out" Easy Clip splitters [PP], i.e. two motors per channel through a splitter (left pair / right pair). Exact pairing and polarity: Needs verification.
- Motors → LEFT MOTOR / RIGHT MOTOR terminals on the bottom of the SUMO:BIT; battery → battery terminal via the Dean T cable (check polarity) [DS][UM].
- RC control with Joystick:bit V2: the SUMO:BIT RC guide (10 Dec 2024) describes "micro:bit as Joystick" — code is needed on both the transmitter (micro:bit in the Joystick:bit) and the receiver (micro:bit in the SUMO:BIT), using the sumobit MakeCode extension [UM]. This means two micro:bits in total; how many the "with micro:bit" option includes is not stated.
- Board pin mapping (P0/P1 edge, P12–P16 opponent, I2C 0x09 to the RP2040 co-processor): see `sumo-bit.md` [GH].

## Rules and gotchas (for code, wiring and tutorials)
- The kit "comes in loose parts" — assembly is the customer's job [PP].
- The Complete option includes a Joystick:bit V2 and 4 AAA batteries [PP]; the robot and joystick are paired by radio channel — select with A/B, confirm with A+B [PP: tutorial]. Other SUMO:BIT RC modes (Cytron USB Joystick, hobby RC receiver) also work [UM].
- Four 980 rpm GM25 motors on a 2-channel board: each MD13S channel carries two motors in parallel; the per-channel limit is 13 A continuous / 30 A for ≤10 s [DS]. Motor stall current is not stated, so do not quote a safety margin.
- The 1300 mAh LiPo is smaller than the Robot Battle kit's 2000 mAh; run time is not stated [PP].
- A LiPo balance charger and a LiPo voltage indicator are in the Complete option [PP]. **Basic has no Joystick:bit and no charger** [DT] — Basic buyers need their own controller (or another SUMO:BIT RC mode) and a 3S charger.
- 3S LiPo care from the SUMO:BIT Maintenance guide: full at 12.6 V, do not discharge below 11 V [UM] — general guidance, not kit-specific.
- Weight is 1 kg and footprint 20 × 20 cm: check them against the target competition's soccer rules before promising eligibility [PP].

## Power and electrical limits
- Battery: LiPo 11.1 V 1300 mAh (3S) [PP].
- SUMO:BIT input 7–25 V; 13 A continuous / 30 A ≤10 s per channel with MD13S; 5 V 600 mA total — see `sumo-bit.md` [DS].
- MD13S (from the manual the page links): 6–30 V, 13 A continuous, 30 A peak ≤10 s, PWM up to 20 kHz, "not PWM from RC receiver" — see `md13s.md` [UM].
- GM25 motor rated/stall current: not stated.

## Software support
- MakeCode with the "sumobit" extension (https://github.com/CytronTechnologies/pxt-sumobit) [PP][GH].
- Joystick:bit V2 radio-control programs: the SUMO:BIT RC guide links transmitter and receiver MakeCode examples (half-speed drive, full speed, attack-left/right, battery display, edge-threshold set) written for the sumo robot — adaptation for soccer not read [UM].
- Tutorial linked from the page (read 2026-10-19): https://my.cytron.io/tutorial/soccer-robot-using-sumo-bit [PP: tutorial] — Joystick:bit channel select with A/B, confirm A+B.
- Firmware and support: https://github.com/CytronTechnologies/Cytron-SUMOBIT ; Telegram https://t.me/sumobit_support [GH].

## Compatibility and accessories
- Joystick:bit V2 (included in the Complete option, with 4 × AAA) [PP].
- Alternatives supported by the board: Cytron USB Joystick; hobby RC receivers (FlySky FS-iA6B, Hot RC F-06A, Dumborc X6F shown) [UM].
- LiPo balance charger and LiPo voltage indicator (included in the Complete option) [PP].
- Sibling kits on the same board: SUMO:BIT Robot Kit (1 kg sumo, 2 motors + sensors) — `sumobit-robot-kit.md`; Robot Battle (500g) — `robot-battle-500g-sumobit.md`.

## Common mistakes / troubleshooting
- Following the page's "user manual" link expecting a build guide → it opens the MD13S motor-driver manual; the build steps are in the tutorial [PP].
- Wheels on one side spin in opposite directions → the two motors on that channel are wired with opposite polarity through the splitter; match the polarity of both motors on a channel (board guidance: swap the motor wires and re-test with the alignment button) [UM].
- Robot does not respond to Joystick:bit → set the same radio channel on both: A/B to choose, A+B to confirm [PP: tutorial]; both micro:bits need their code.
- Weak push / resets under load → two motors per channel and a 1300 mAh pack; check battery voltage (≥11 V) [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| "User manual" document | [PP] labels the link "user manual" for the SOCCER:BIT | The linked Google Doc is the MD13S 13Amp DC Motor Driver User's Manual, V1.1, June 2018 | No SOCCER:BIT manual exists at that link; the MD13S manual is a board document (see `md13s.md`). Flag to Cytron to relabel or replace the link |
| Motor count vs board channels | [PP] 4 motors | [DS] SUMO:BIT has 2 motor channels | Reconciled by the 2× "2 in 4 out" splitters in the packing list; exact wiring unverified |
| Weight | [PP] Features: 1 kg | — | No second source; "Actual weight" not given as for the Battle kit |
| Joystick:bit V2 | Earlier coordinator extract: "RC Controller – Joystick:bit V2 Kit for micro:bit [optional]" | Live page re-read 2026-10-19: Complete packing list includes 1× Joystick:bit V2 + 4× AAA, charger and LiPo indicator | Current page wins for Complete; Basic does not include it [DT] |

## Needs verification
- Exact item list of the Basic and 3D Printed Body only options (Basic confirmed without Joystick:bit and charger [DT]).
- Motor pairing per channel and splitter polarity (no wiring drawing).
- GM25 motor gear ratio and rated/stall current; wheel hub type for the GM25 shaft.
- Whether 1 kg is the actual built weight or a class figure; robot height.
- STL file names in the "KIT-3DP-SCRBIT-4WD" Drive folder (folder found, contents not listable).
- Warranty terms (page field blank; the Robot Battle kit states "NO warranty").
- Supported micro:bit versions (V1/V2) — the kit ships micro:bit Junior Kit V2.

## Sources
- [PP] https://my.cytron.io/p-soccerbit-robot-kits — product page facts as read by the coordinator on 2026-10-19 (page not fetched directly).
- [PP → UM] "user manual" link on the page: https://docs.google.com/document/d/1icu1GVDxZhUn3ADSUc3JknNcmUMdPcsnJ4MhxOPRo-I/view — resolves to MD13S User's Manual V1.1, June 2018 (read)
- [PP: tutorial] "Soccer Robot using SUMO:BIT", Azmir Che Azmi, 8 Aug 2025 — https://my.cytron.io/tutorial/soccer-robot-using-sumo-bit (read 2026-10-19)
- [PP] STL folder "KIT-3DP-SCRBIT-4WD": https://drive.google.com/drive/folders/1e8w5kNDbIVv4FnHdhB-k01fpvbS1idUP (metadata only; created 15 Dec 2025)
- [DS] SUMO:BIT Datasheet, Rev 1.0, December 2024 — https://docs.google.com/document/d/1xHrA7EkQ8gn0syVS93uhbWAVt8z3viTB763gGpLsC8k/edit (see `sumo-bit.md`)
- [UM] SUMO:BIT Robot Kit | RC (Remote Control), 10 Dec 2024 — https://docs.google.com/presentation/d/1kkcqsfMDE5pzGX8FfeEHsAbjzOgs4QZmaKBYXHFHvfE/edit ; | Maintenance, 2 Dec 2024 — https://docs.google.com/presentation/d/1zcng7FHubdTSolIi3hU9j0wFy4-cY3OerctyFiYaqQo/edit
- [GH] https://github.com/CytronTechnologies/pxt-sumobit ; https://github.com/CytronTechnologies/Cytron-SUMOBIT (README)
- KB cross-references: `sumo-bit.md`, `md13s.md`, `sumobit-robot-kit.md`, `robot-battle-500g-sumobit.md`
