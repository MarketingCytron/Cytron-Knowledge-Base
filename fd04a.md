# 1.5Amp 7V-15V DC Motor Driver (4 Channels) — Verified Reference

| | |
|---|---|
| Product code | `FD04A` (manual title "FD04A Rev2.0" [UM]; product-page image paths [PP]) |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — Cytron User's Manual (Google Doc "FD04A-R2 User's Manual"; cover "FD04A Rev2.0 4 Channel Motor Driver User's Manual", V1.2, Jun 2025; 16 pages) re-read in full via Google Drive, this time including the figures of its PDF export: dimension photo, board-layout photo, 7 x 2 IDE socket / extra-pad pin orientation, bottom-side silkscreen, POWER terminal +/− marking and wiring photos. This settles the physical IDE socket pin order (figure-only before) and gives the board size (106.68 × 52.07 mm) from the manual itself. Raised Medium → Medium-high; still open: product-page logic range 1.8–12 V vs manual 5.5 V max (manual wins), IPEAK duration, protections, mounting-hole spacing, M1/M2 terminal A/B order. Earlier: 2026-10-19 master-table review of the live product page (board size, packing list and reverse-polarity protection Cytron-stated; logic-range conflict; IDE pin order figure-only), so it stayed Medium |
| Primary source | "FD04A Rev2.0 4 Channel Motor Driver User's Manual" — **V1.2, Jun 2025** [UM] — public Google Doc (Drive title "FD04A-R2 User's Manual"; page header "Product User's Manual – FD04A Rev2.0"), 16 pages, read in full including figures on 2026-10-21: https://docs.google.com/document/d/1SWq9YtW6gsr8n9eIz2X8ek8Na8KoJ30whM5HsOdCnSc/edit |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: No document titled "datasheet" exists for FD04A; the Cytron **User's Manual** (linked, unlabelled, from the product page) calls itself a user's manual and is the top source [UM]. It was read in full as text via Google Drive (2026-10-19) and again on 2026-10-21 as a PDF export with every page viewed as an image, so the figures (dimension photo, board-layout photo, IDE socket pin orientation, bottom silkscreen, wiring photos) are now read. Facts taken from a figure say "(figure)". [PP] = facts from the coordinator's read of the my.cytron.io page on 2026-10-16 (title, URL, stock). No [DT] confirmation exists yet.

## What it is
A four-channel, bi-directional driver for four brushed DC motors, built on the **L298P** motor driver IC, powered from 7–15 VDC, rated 1.5 A continuous per channel [UM]. Each channel has a direction pin and an enable/speed-control pin, fed through a 7 x 2 (14-way) IDE socket or solder pads; an onboard 5 V regulator powers the board and can supply 5 V to another circuit [UM].
- Manual introduction: "FD04A Rev2.0 is an enhanced version of FD04A Rev1.0. It is a motor driver board to control unit of DC motor up to 2A for each channel." [UM] (see *Conflicts* — the spec table gives 1.5 A continuous, 2.5 A peak).
- Feature list [UM]: "Bi-directional control for 4 brushed DC motors (4 Channels)."; "Support motor voltage ranges: 7 - 15VDC."; "Maximum current up to 1.5A continuous per channel."; "3.3V and 5V logic level input."; "Test switches (Start and Direction) for every channel."; "Motor voltage polarity protection."; "Solid state switch for power."
- Backward compatible with FD04A Rev1.0 at the IDE connector, and used with the PR19 robot [UM].

## Specifications
Manual section 3 "Product Specification and Limitations", table **"Absolute Maximum Rating"** [UM], plus other manual facts.

| Item | Value | Src |
|---|---|---|
| Power input voltage (motor supply voltage) | Min **7 V**, Max **15 V** | [UM] |
| IMAX — maximum continuous motor current, each channel | Max **1.5 A** | [UM] |
| IPEAK — peak motor current | Max **2.5 A** (duration not stated; table does not say "each channel") | [UM] |
| VIOH — logic input high level | Min 3.3 V, Max **5.5 V** | [UM] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V | [UM] |
| Maximum PWM frequency | **10 kHz** | [UM] |
| Number of channels | 4 (M1, M2, M3, M4) | [UM] |
| Motor type | Brushed DC motors | [UM] |
| Driver IC | L298P | [UM] |
| Logic supply | No external logic supply needed: onboard 5 V regulator "Generates 5V to supply all the transistors and L298P motor driver, include V pin" | [UM] |
| 5 V output | V pin outputs 5 V; "User is prohibited to supply another 5V at V pin." | [UM] |
| Logic level input | "3.3V and 5V logic level input." | [UM] |
| Control inputs per channel | 2: direction pin and enable/Speed Control pin | [UM] |
| Control modes | Enable + direction (enable pin used for speed control). Locked-antiphase: not stated. RC, analog, serial: not stated | [UM] |
| Reverse polarity protection | **Yes** — "Motor voltage polarity protection"; board item E "Reverse polarity protection … this circuit will protect the board from broken" | [UM] |
| Clamping diodes | Schottky diodes "used as clamping diode" | [UM] |
| Over-current / thermal / under-voltage protection | Not stated | — |
| Power switch | Power toggle switch (ON/OFF); feature list also says "Solid state switch for power" | [UM] |
| Test buttons | Test switches for every channel: two push buttons per channel, silkscreen "M1 A B" … "M4 A B" along the bottom edge (figure); A drives output A→B, B drives B→A | [UM] |
| LEDs | Power indicator LED (PWR); motor status indicator LEDs ("Indicates voltage at corresponding terminal"), two per motor channel, silkscreen A and B (figure) | [UM] |
| Mounting | Four 3 mm holes (label M at the four corners in the board-layout photo) — "can fit standard PCB stand"; hole spacing not dimensioned | [UM] |
| Dimensions | **106.68 mm × 52.07 mm** (manual section 4 dimension photo); product page: 10.67 cm × 5.21 cm (same, rounded). Height and hole spacing not given | [UM] (figure), [PP] |
| Operating temperature | Not stated | — |
| Warranty | 12 months; manufacturing defects only; misuse and two-way freight not covered | [UM] |
| Packing list | 1 x FD04A Rev2.0 board; 1 x 14 way IDE cable connector | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** 4-channel driver for omnidirectional robots; bidirectional control of 4 brushed DC motors, 7–15 V; test buttons and motor LEDs; PWM and DIR inputs; "input logic voltage range from 1.8V to 12V" (Arduino, Raspberry Pi, PLC); "Starting from 10th April 2015, FD04A is Rev2.0" [PP].
- **Features list:** 7–15 V; 1.5 A continuous, 2.5 A peak; buttons for quick testing; motor output LEDs; PWM and DIR inputs; "Inputs compatible with 3.3V and 5V logic"; **reverse polarity protection**; **board size 10.67 cm × 5.21 cm**; applications: omnidirectional mobile robot, automation machine [PP].
- **Packing list:** 1x FD04A, 1x 14-way IDE cable [PP].
- **Resources:** User's Manual Rev2.0 (Google Doc), CytronMotorDriver library, 3D CAD, tutorials (getting started with Arduino, FD04A + SKPS, Flexibot with SKXBee); Rev1.0 manual, Fritzing files [PP].

## Interfaces, terminals and pin mapping
Board layout labels [UM]: A power toggle switch; B 5V voltage regulator; C 7 x 2 IDE socket; D extra pad; E reverse polarity protection; F power indicator LED; G power supply terminal block; H motor status indicator LED; I motor terminal block; J Schottky diode; K L298P motor driver; L motor test switch; M 3 mm hole.

**Control pins — 7 x 2 IDE socket and extra pad (Table 1)** [UM]:

| Pin | Description |
|---|---|
| 1 | Motor 1 direction |
| 2 | Motor 1 enable/Speed Control |
| 3 | Motor 2 direction |
| 4 | Motor 2 enable/Speed Control |
| 5 | Motor 3 direction |
| 6 | Motor 3 enable/Speed Control |
| 7 | Motor 4 direction |
| 8 | Motor 4 enable/Speed Control |
| V | Output voltage 5V |
| G | Ground |
| x | Not connected |

**Physical pin order** (manual section 5.1 figure, board viewed from the component side with the extra pads at the board edge) [UM] (figure):

| Position (left → right) | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| IDE socket, row next to the extra pads | 2 | 3 | x | 6 | 7 | x | G |
| IDE socket, inner row | 1 | x | 4 | 5 | x | 8 | V |

- Extra pads: one row of 10 pads along the board edge, silkscreen **1 2 3 4 5 6 7 8 V G** left to right [UM] (figure).
- The 14-way socket carries only 10 signals; 4 positions are "x" (not connected). The labels do not run 1–14 in IDC order, so wire by the figure or the silkscreen, not by IDC pin number (inference from the figure).
- The bottom side of the board repeats the pin table and the EN/DIR truth table in silkscreen (photo shows the mirrored socket labels and www.cytron.com.my) — "User may refers to pin description at the bottom of FD04A Rev2.0 board." [UM]

Truth table, every channel [UM]:

| Enable pin | Direction pin | OUT A | OUT B |
|---|---|---|---|
| 0 | X | LOW | LOW |
| 1 | 0 | HIGH | LOW |
| 1 | 1 | LOW | HIGH |

Terminals [UM]:
- POWER terminal (power supply terminal block, 2-way, top-right corner, silkscreen "7-15V" and "POWER"): motor power supply, 7–15 V, check polarity. Silkscreen beside it: **+** on the position nearer the board's top edge, **−** on the position nearer the M3 terminal (figure, section 6.1 photo).
- MOTOR terminals: four, labelled M1, M2, M3, M4 (M1 and M2 on the left edge, M3 and M4 on the right edge, as two 4-way blocks); each connects to the two terminals of a DC motor. Outputs are labelled A and B: on the right edge the order is A, B (M3) then A, B (M4) from top to bottom (figure). The A/B order on the left edge (M1/M2) is not legible in the figures.
- Power toggle switch: top-left corner, silkscreen ON / OFF; board silkscreen "FD04A-R2" and "4 CHANNEL MOTOR DRIVER Rev2.0" (figure).
- Wire size / terminal current rating: not stated.

Test switches [UM]: button A → current flows from output A to B, motor turns CW (or CCW depending on the connection); button B → current B to A, motor turns CCW (or CW).

Two ways to reach the control pins [UM]: the IDE connector (with the supplied 14-way IDE cable) or the extra pads ("User can solder any suitable header pin on extra pad"). The manual photos show the IDE ribbon cable to the PR19 main board, and an Arduino Uno wired to a header soldered on the extra pads with jumper wires (no Arduino pin list is given) [UM] (figure).

## Rules and gotchas (for code, wiring and tutorials)
- Motor supply is **7–15 V** [UM] — not 25 V, despite the product-page URL slug "7v-25v" [PP].
- **1.5 A continuous per channel** is the spec-table figure [UM]; the "up to 2A" in the introduction and the 2.5 A IPEAK are not continuous ratings. Peak duration is not stated.
- Logic inputs 3.3 V or 5 V; VIOH max 5.5 V [UM].
- Max PWM frequency 10 kHz [UM] (lower than the 20 kHz of Cytron's MOSFET drivers such as MDD10A).
- Enable LOW = both outputs LOW regardless of direction [UM].
- Never feed 5 V into the V pin — it is an output from the onboard regulator [UM]. The V pin can power the PR19 main board [UM].
- Direction labels depend on motor wiring; swap the motor leads to reverse [UM].
- Connect controller GND to the G pin.
- **IDE socket pin order is not IDC 1–14 order**: use the layout table above (row next to the pads 2, 3, x, 6, 7, x, G; inner row 1, x, 4, 5, x, 8, V) [UM] (figure).

## Power and electrical limits
- Supply 7–15 V on the POWER terminal; "Make sure the polarity is correct." [UM] (reverse polarity protection is fitted [UM]).
- 1.5 A continuous per channel; 2.5 A peak (duration and per-channel wording not stated) [UM].
- Battery vs switching power supply / regenerative current: not stated in the manual.
- Over-current, thermal, under-voltage behaviour: not stated. Heatsink or fan: not stated.

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, Library Manager name "Cytron Motor Drivers Library", v1.0.1) — FD04A is listed under the **PWM_DIR_DUAL** example [GH]. Use one `CytronMD motorN(PWM_DIR, enablePin, dirPin);` object per channel (four objects for four motors); the example sketch's pins 3/4/9/10 are only example wiring [GH].
- PIC sample code: GitHub repo "DIY-PR19-PIC16F777" (linked from the product page) — "Sample source code for DIY PR19" (Flexibot using Transwheel), for MPLAB/MPLABX with HI-TECH C and XC8 [GH].
- MicroPython / CircuitPython / MicroBlocks: not stated.

## Compatibility and accessories
- IDE connector compatible with FD04A Rev1.0: "for those already bought the PR19, or build any project that uses FD04A Rev1.0, you still can replace it with FD04A R2." [UM]
- 3.3 V and 5 V microcontrollers [UM].
- Included: 14-way IDE cable [UM].
- Not an Arduino shield (stand-alone board with 3 mm mounting holes) [UM].

## Common mistakes / troubleshooting
- Supplying 24 V because the URL says "7v-25v" → over the 15 V maximum [UM][PP].
- Motor does not move → enable pin LOW; check enable pin and the power toggle switch [UM].
- Quick check without code → press test switch A/B on the channel [UM].
- Wrong channel responds → check the socket pin order (layout table above, from the manual figure) or the pin description printed on the bottom of the board [UM].
- Back-feeding 5 V into V pin → prohibited [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Motor voltage | [UM] spec table and features: 7–15 V | [PP] URL slug "p-1.5amp-7v-25v-dc-motor-driver-4-channels" (page title says 7V-15V) | [UM] wins: 7–15 V. Slug appears to be a URL error |
| Current per channel | [UM] introduction: "up to 2A for each channel" | [UM] spec table: 1.5 A continuous, 2.5 A peak; [PP] title "1.5Amp" | Spec table wins: 1.5 A continuous; 2.5 A peak |
| Power switching | [UM] features: "Solid state switch for power" | [UM] board layout: "Power toggle switch" | Both stated; relationship not explained |
| Section numbering | [UM] hardware section numbered 6.1, 6.2, 7.1, 6.4 | — | Cosmetic error in manual |
| Test switch naming | [UM] feature list: "Test switches (Start and Direction) for every channel" | [UM] board-layout text and photos: two buttons per channel, A (output A→B) and B (output B→A), silkscreen "A" / "B" | Layout text and photos are specific: describe them as A and B direction buttons, not Start/Direction |
| Logic input voltage | [UM]: VIOH max 5.5 V; "3.3V and 5V logic level input"; [PP] features: "Inputs compatible with 3.3V and 5V logic" | [PP] description: "input logic voltage range from 1.8V to 12V" | [UM] wins: keep logic inputs at 3.3–5 V (max 5.5 V); ask [DT] about the 1.8–12 V sentence |

## Needs verification
1. IPEAK 2.5 A: per channel or total, and maximum duration.
2. Over-current / thermal / under-voltage protection — not stated.
3. Battery vs SMPS guidance (regenerative current) — not stated for FD04A (the manual photos show a battery lead, but the text does not say battery only).
4. Whether locked-antiphase PWM (PWM on direction pin, enable held high) is supported — not stated.
5. What "Solid state switch for power" refers to, given the mechanical toggle switch.
6. Rev1.0 vs Rev2.0 differences beyond IDE compatibility — the manual says "several important improvements" but lists only features.
7. Mounting-hole spacing (four 3 mm corner holes, not dimensioned), board height, operating temperature, terminal wire size.
8. Logic input maximum: product page "1.8V to 12V" vs manual VIOH max 5.5 V — ask the design team (see Conflicts).
9. A/B output order of the M1 and M2 terminals on the left edge (not legible in the manual figures; the right edge reads A, B per motor).
10. Purpose of the pairs of solder pads along the bottom edge under the test buttons (visible in the photos, not described).

## Sources
- [UM] FD04A Rev2.0 4 Channel Motor Driver User's Manual, V1.2, Jun 2025 (Google Doc "FD04A-R2 User's Manual", 16 pages; text read 2026-10-19, read again in full with all figures 2026-10-21): https://docs.google.com/document/d/1SWq9YtW6gsr8n9eIz2X8ek8Na8KoJ30whM5HsOdCnSc/edit
- [PP] Product page (read by coordinator 2026-10-16): https://my.cytron.io/p-1.5amp-7v-25v-dc-motor-driver-4-channels
- [GH] DIY-PR19-PIC16F777 (README read): https://github.com/CytronTechnologies/DIY-PR19-PIC16F777
- [GH] Cytron Motor Drivers Library (README, library.properties, PWM_DIR_DUAL example read): https://github.com/CytronTechnologies/CytronMotorDriver
