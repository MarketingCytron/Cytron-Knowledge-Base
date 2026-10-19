# Robot Battle (500g) - SUMO:BIT — Verified Reference

| Field | Value |
|---|---|
| Product code | V-BATTLE-SMB [PP] |
| Family | micro:bit kits |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Cytron product page "Robot Battle (500g) - SUMO:BIT" (my.cytron.io, read by the coordinator 2026-10-19) [PP]. No kit datasheet, manual or booklet exists. The two Cytron tutorials the page links ("2 Wheel Robot Battle with SUMO:BIT"; "SUMO:BIT RC Mode with HOT RC") could not be read (my.cytron.io and www.cytron.io blocked). Board datasheet: "SUMO:BIT Datasheet, Rev 1.0, December 2024" — see `sumo-bit.md` |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A 500 g-class, two-wheel battle robot kit "Suitable for the Robot Battle Challenge", using the SUMO:BIT board (with two MD13S) as the controller, 12 V 980 rpm GM25 geared motors, a 3S 2000 mAh LiPo and a 3D-printed chassis [PP]. The page lists no opponent or edge sensors, so the kit as sold is a remote-controlled battle robot; the robot is driven in one of the SUMO:BIT RC modes (hobby RC receiver — the "HOT RC" tutorial — wireless USB joystick, or a second micro:bit) [PP][UM: SUMO:BIT Robot Kit RC guide]. "This Battle Robot Kit does not come with a controller" (no transmitter/joystick) and "There is NO warranty for Battle Robot" [PP].

Board references — do not re-document here: SUMO:BIT → `sumo-bit.md`; MD13S → `md13s.md`.

## Specifications
Kit-level facts only; board ratings are in `sumo-bit.md`.

| Item | Value | Src |
|---|---|---|
| Competition class | Robot Battle (500 g) — "Suitable for the Robot Battle Challenge" | [PP] |
| Purchase options | Complete / Basic / 3D Printed Body only, each with or without micro:bit | [PP] |
| Controller board | SUMO:BIT with 2× MD13S (see `sumo-bit.md`, `md13s.md`) | [PP] |
| Drive motors | 12 V 980 rpm 2.3 kgf·cm GM25 brushed DC geared motor — quantity printed as "1 x" on the packing list (see Needs verification; a two-wheel robot with a 1-pair wheel set implies two) | [PP] |
| Wheels | 1× G25T1 silicone wheel set (1 pair) | [PP] |
| Battery | 1× Mini LiPo 3S 11.1 V 2000 mAh | [PP] |
| Charger | 1× 3S LiPo USB balance charger (included) + 3S charger cable extension | [PP] |
| Battery lead | Dean T connector 18 AWG 15 cm; 10 cm JST SM 2-pin male connector | [PP] |
| Chassis | "robust 3D printed chassis"; chassis set = body + left/right motor brackets | [PP] |
| Dimensions | 15 cm × 15 cm × 4 cm | [PP] |
| Actual weight | 495 g | [PP] |
| Hardware | 4× M3×20 screw, 4× M3 nut, 4× M3×6 self-tapping screw; screwdrivers | [PP] |
| micro:bit (with-micro:bit options) | micro:bit Junior Kit, micro:bit V2, USB Micro B cable | [PP] |
| Remote controller | Not included ("does not come with a controller") | [PP] |
| Opponent / edge sensors | None listed in the packing list | [PP] |
| Programming | SUMO:BIT runs on MakeCode (sumobit extension) — see `sumo-bit.md` | [GH] |
| STL files | Google Drive folder "KIT-BATTLE-SMB" (created 7 May 2025) linked from the page; contents not listable here | [PP] |
| Warranty | "There is NO warranty for Battle Robot." | [PP] |
| Price | RM69.00–RM716.40 across options (Cytron product page, read 2026-10-19) | [PP] |

### Exact packing list (Complete, with micro:bit) [PP]
1× SUMO:BIT with 2× MD13S, screwdrivers, Dean T connector 18 AWG 15 cm, 1× 12 V 980 rpm 2.3 kgf·cm GM25 brushed DC geared motor (as printed), 1× G25T1 silicone wheel set (1 pair), 1× Mini LiPo 3S 11.1 V 2000 mAh, 1× 3S LiPo USB balance charger, 3S charger cable extension, 10 cm JST SM 2-pin male connector, 4× M3×20 screw, 4× M3 nut, 4× M3×6 self-tapping screw, 3D-printed chassis set (body + L/R motor brackets), micro:bit Junior Kit, micro:bit V2, USB Micro B cable.

Basic and 3D Printed Body only: offered but not itemised on the page (Needs verification). "Without micro:bit" options omit the micro:bit items.

## Interfaces, terminals and pin mapping
The page gives no wiring diagram. The SUMO:BIT board connections that apply (from the SUMO:BIT Robot Kit RC guide, 10 Dec 2024, which describes the board's RC modes) [UM]:
- Motors → LEFT MOTOR / RIGHT MOTOR terminals on the bottom of the SUMO:BIT (one MD13S per channel); verify direction with the Motor Alignment button and swap the motor's two wires if it runs backward.
- Battery → battery terminal via the Dean T cable; check polarity.
- Hobby RC receiver → SERVO/RC port 1 = speed (forward/reverse), port 2 = steering (left/right). Example for the Hot RC F-06A receiver (the model named in the page's "HOT RC" tutorial): CH2 → RC PORT 1, CH1 → RC PORT 2. Turn on the transmitter first, then the robot; RGB LEDs stay orange when ready; the micro:bit must be removed.
- Wireless USB joystick → USB-A port; RGB LEDs stay yellow when ready; only the Cytron USB Joystick model is supported; micro:bit removed.
- Second micro:bit as joystick (e.g. Joystick:bit V2) → micro:bit in the SUMO:BIT socket, code on both ends.
micro:bit pin mapping of the board: see `sumo-bit.md`.

## Rules and gotchas (for code, wiring and tutorials)
- The kit has no transmitter or joystick: a hobby RC set (e.g. Hot RC), the Cytron USB Joystick, or a Joystick:bit with a second micro:bit must be bought separately [PP][UM].
- For RC-receiver and USB-joystick modes the micro:bit is taken out; it is only inserted for micro:bit-coded (autonomous or micro:bit-joystick) control [UM].
- Do not state a 2-motor quantity as fact until Cytron confirms the "1 x" on the page is a typo (Needs verification).
- Keep the built robot within the 500 g class: the actual weight is 495 g, so there is only ~5 g headroom for extras such as a blade or stickers [PP].
- No warranty on this kit [PP].
- Which micro:bit versions the board supports is not stated by any source (see `sumo-bit.md`).

## Power and electrical limits
- Battery: Mini LiPo 3S 11.1 V 2000 mAh, charged with the included 3S LiPo USB balance charger [PP]. The SUMO:BIT guides for the sumo kit say a 3-cell LiPo is full at 12.6 V and must not be discharged below 11 V [UM, SUMO:BIT Robot Kit Maintenance] — general 3S LiPo guidance, not specific to this kit.
- Board limits (7–25 V input; 13 A continuous / 30 A ≤10 s per channel with MD13S; 5 V 600 mA total) — see `sumo-bit.md` [DS].
- Motor stall/rated current of the GM25 980 rpm motor: not stated.

## Software support
- MakeCode "sumobit" extension (https://github.com/CytronTechnologies/pxt-sumobit) for any micro:bit-coded control; RC-receiver and USB-joystick modes need no code (handled by the SUMO:BIT firmware) [UM][GH].
- Tutorials linked from the page (not read here): https://my.cytron.io/tutorial/2-wheel-robot-battle-with-sumobit ; https://my.cytron.io/tutorial/SUMO:BIT_RC_Mode_with_HOT_RC [PP].
- SUMO:BIT firmware and support: https://github.com/CytronTechnologies/Cytron-SUMOBIT ; Telegram https://t.me/sumobit_support [GH].

## Compatibility and accessories
- RC transmitter/receiver sets shown for the SUMO:BIT: Hot RC F-06A, FlySky FS-iA6B, Dumborc X6F [UM].
- Cytron USB Joystick (only supported USB joystick model) [UM].
- PCB Plate for Sumo Robot 10 cm (page for that plate: "10cm for 500g") as a training blade substitute [PP, PCB plate page].
- Related 500 g kit without micro:bit: "Build a Robot Sumo 500g R/C with MDDRC5" tutorial (different controller) — see `mddrc5.md`.

## Common mistakes / troubleshooting
- Robot does not respond to the RC transmitter → transmitter must be on before the robot; receiver channels must be on SERVO/RC port 1 (speed) and port 2 (steering); micro:bit removed; wait for orange RGB LEDs [UM].
- One wheel spins the wrong way → swap that motor's wires at the terminal and re-test with the alignment button [UM].
- Robot over 500 g after modifications → the base build is already 495 g [PP].
- Expecting a controller in the box → none is included [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Motor quantity | [PP] packing list: "1 x" 12 V 980 rpm 2.3 kgf·cm GM25 motor | [PP] same page: two-wheel robot, "1x G25T1 silicone wheel set (1 pair)", chassis with left and right motor brackets | Internally inconsistent; likely two motors. Not resolved — Needs verification |
| Battery capacity vs sibling kits | [PP] this kit: 3S 2000 mAh | [PP] SUMO:BIT Robot Kit and SOCCER:BIT: 3S 1300 mAh | Not a conflict — different kits; quote 2000 mAh for this kit only |

## Needs verification
- Number of motors supplied (1 or 2) — page prints "1 x".
- Exact contents of the Basic and 3D Printed Body only options.
- Assembly steps, motor-to-channel wiring and the exact RC channel mapping used in the two linked tutorials (both unreadable here).
- Whether the kit includes any blade, PCB plate or weapon, and what "Robot Battle Challenge" rules the 15 × 15 × 4 cm / 495 g build targets.
- GM25 motor gear ratio, rated and stall current.
- STL file names in the "KIT-BATTLE-SMB" Drive folder (folder found, contents not listable).
- What the "micro:bit Junior Kit" contains.
- Whether an autonomous (sensor-equipped) build is supported or intended for this kit.

## Sources
- [PP] https://my.cytron.io/p-robot-battle-500g-sumo-bit — product page facts as read by the coordinator on 2026-10-19 (page not fetched directly).
- [PP] Tutorials linked from the page — not readable (403 / blocked): https://my.cytron.io/tutorial/2-wheel-robot-battle-with-sumobit ; https://my.cytron.io/tutorial/SUMO:BIT_RC_Mode_with_HOT_RC
- [PP] STL folder "KIT-BATTLE-SMB": https://drive.google.com/drive/folders/1GJcer1Lz6KkvGiQscifHguNeW4PKkG8b (metadata only; created 7 May 2025)
- [UM] SUMO:BIT Robot Kit | RC (Remote Control), Last Updated 10 Dec 2024 — https://docs.google.com/presentation/d/1kkcqsfMDE5pzGX8FfeEHsAbjzOgs4QZmaKBYXHFHvfE/edit (board RC modes; written for the sumo kit)
- [UM] SUMO:BIT Robot Kit | Maintenance, 2 Dec 2024 — https://docs.google.com/presentation/d/1zcng7FHubdTSolIi3hU9j0wFy4-cY3OerctyFiYaqQo/edit (3S LiPo care)
- [DS] SUMO:BIT Datasheet, Rev 1.0, December 2024 — https://docs.google.com/document/d/1xHrA7EkQ8gn0syVS93uhbWAVt8z3viTB763gGpLsC8k/edit (see `sumo-bit.md`)
- [GH] https://github.com/CytronTechnologies/Cytron-SUMOBIT (README) ; https://github.com/CytronTechnologies/pxt-sumobit
- KB cross-references: `sumo-bit.md`, `md13s.md`, `mddrc5.md`
