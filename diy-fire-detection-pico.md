# DIY Fire Detection and Suppression with Raspberry Pi Pico — Verified Reference

| | |
|---|---|
| Product code | `PR-DIY-FIRE-PICO` [PP] |
| Family | Robot parts and project bundles |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | No datasheet or user manual exists. Primary source = **Cytron tutorial "DIY Fire Detection and Suppression with Raspberry Pi Pico"** (Abdulrahman Alhamed, 08 Nov 2023, level Beginner, about 194 words plus a video) [PP: tutorial DIY Fire Detection], read at https://www.cytron.io/tutorial/diy-fire-detection-and-suppression-with-raspberry-pi-pico through a summarising fetch on 2026-10-19 (the article's product cards, links and video URL did not render as text). The product page (https://my.cytron.io/p-diy-fire-detection-suppression-raspberry-pi-pico), which carries the same guide, was read by the coordinator on 2026-10-19 [PP]; its component list was truncated in that extract |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP-T] = the Cytron tutorial (same text as the product-page guide). [PP] = product page facts saved by the coordinator (jkl-pp.md).  = Cytron Marketing tutorial index (title, author, date, tags, word count). **The tutorial is a video project**: the text gives only two wiring facts, the software and the behaviour; the parts list and code are in the video / product cards, which could not be read. Nothing below the two stated connections should be presented as a confirmed build. Raspberry Pi Pico is a third-party board and has no KB file; a Cytron motor board, if one is in the kit, is not identified in the text read.

## What it is
- A beginner project kit: "Learn how to build a fire detection and suppression system using a Raspberry Pi Pico, a flame sensor, and a water pump in this quick and easy video tutorial" [PP-T excerpt, INT].
- The code "runs in an endless loop, reading the flame sensor. When it detects fire, it runs the water pump for five seconds, then switches it off" [PP-T]. The product page says the same: "when flame detected, pump runs 5 seconds" [PP].
- Programmed in **CircuitPython** using the **Thonny** editor [PP-T][PP]; the tutorial links a separate video on getting started with Thonny [PP-T].
- Price RM103.08 (Cytron product page, read 2026-10-19) [PP]. **Out of stock** on 2026-10-19 [PP].
- Links on the product page: the tutorial, and the Raspberry Pi Pico datasheet [PP].

## Specifications
No spec table exists. Every stated fact:

| Item | Value | Src |
|---|---|---|
| Controller | Raspberry Pi Pico | [PP][PP-T] |
| Sensor | Flame sensor (type / model not stated) | [PP][PP-T] |
| Actuator | Water pump (voltage / model not stated) | [PP][PP-T] |
| Firmware language | CircuitPython | [PP][PP-T] |
| Editor | Thonny | [PP][PP-T] |
| Behaviour | Endless loop reading the flame sensor; on fire detected → pump ON for 5 seconds → pump OFF | [PP-T][PP] |
| Flame sensor connection | GP3 | [PP-T] |
| Water pump connection | "motor terminal 1" | [PP-T] |
| Full component list | **Not readable** — product cards/images only (page extract truncated) | [PP][PP-T] |
| CircuitPython libraries | Not stated | [PP-T] |
| Code listing | Not in the text (video) | [PP-T] |
| Price | RM103.08 | [PP] |
| Warranty | Not stated | — |

## Interfaces, terminals and pin mapping
| Signal | Pico pin / terminal | Src |
|---|---|---|
| Flame sensor output | GP3 | [PP-T] |
| Water pump | "motor terminal 1" | [PP-T] |

- "Motor terminal 1" means the pump is driven from a motor-driver terminal, not directly from a Pico GPIO [PP-T]. A bare Raspberry Pi Pico has no motor terminals, so a motor-driver board must be part of the build — the text does not say which (see *Needs verification*; Cytron Pico boards with motor terminals and KB files include Robo Pico `robo-pico.md` and Maker Pi RP2040 `maker-pi-rp2040.md`).
- Power and ground wiring of the flame sensor, pump supply voltage and the digital/analog nature of the sensor signal are **not stated** [PP-T].

## Rules and gotchas (for code, wiring and tutorials)
- **Only two wiring facts are confirmed:** flame sensor → GP3; pump → motor terminal 1 [PP-T]. Do not add pin numbers for power, the second motor channel or other sensors.
- **Pump timing is fixed at 5 seconds** per detection, then off [PP-T]. Code written for this kit should keep that behaviour unless the tutorial is explicitly extended.
- **Never drive a water pump from a GPIO pin** — the guide uses a motor terminal [PP-T]; keep the pump on a motor driver output.
- **Flame-sensor polarity is not stated:** whether GP3 reads LOW or HIGH on flame is not in the text; check the sensor module's own datasheet before writing the `if` condition.
- **Safety wording (Cytron tutorial rules):** this is an educational prototype, not a certified fire-safety device — do not describe it as protecting people or property. Water near electronics: keep the pump, tubing and reservoir away from the Pico and driver board.
- **CircuitPython + Thonny:** the Pico must be running CircuitPython (not MicroPython) for the project code [PP-T]. Libraries used are not stated.

## Power and electrical limits
- None stated. Pump voltage/current, sensor supply (3.3 V or 5 V) and the motor driver's limits are not in the text read [PP-T][PP]. Use the driver board's KB file once the board is confirmed.

## Software support
- CircuitPython, written and uploaded with Thonny [PP-T][PP]; a linked video covers Thonny setup [PP-T].
- Code: shown in the video only; no listing, Gist or GitHub link rendered in the text [PP-T].
- Libraries: not stated [PP-T].

## Compatibility and accessories
- Raspberry Pi Pico (the product page links the Pico datasheet) [PP]. Whether a Pico W or Pico 2 also works is not stated.
- Flame sensor module and water pump — models not stated [PP-T].
- Motor-driver board with "motor terminal 1" — not identified [PP-T].
- Nothing is stated about what is **not** included (power supply, tubing, reservoir, USB cable) [PP][PP-T].

## Common mistakes / troubleshooting
- **Pump never runs** → check the pump is on motor terminal 1 of the driver board and that the board, not the Pico, powers it [PP-T].
- **Pump runs continuously** → the loop must switch the pump off after 5 seconds [PP-T]; a missing OFF command keeps it on.
- **Sensor never triggers** → sensor output must go to GP3 [PP-T]; the trigger level (HIGH/LOW) is not stated — verify with the sensor datasheet.
- **Code does not run** → Thonny must be talking to a Pico running CircuitPython [PP-T].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Pump run time | [PP-T] five seconds | [PP] 5 seconds | Same — no conflict |

## Needs verification
- **Full component list and quantities** (flame sensor model, pump model/voltage, motor driver board, cables, tubing) — product cards did not render; the product page extract is truncated.
- **Which board provides "motor terminal 1"** (Robo Pico? Maker Pi RP2040? another driver?) — not stated in text.
- **Flame sensor wiring** (VCC voltage, GND, digital vs analog output) and **trigger polarity** on GP3.
- **CircuitPython libraries** used (e.g. `digitalio`, `pwmio`, a motor helper) and the code listing — video only.
- **What is not included** (USB cable, power supply, water reservoir, tubing) — not stated.
- **Pico variant** (Pico / Pico W / Pico H) shipped in the kit — not stated.
- **Warranty** — not stated.
- **Video URL** and the Thonny getting-started video URL — not rendered in the fetched text.
- Whether the product-page guide is identical to the tutorial text (coordinator says "same guide"; not compared line by line).

## Sources
- [PP-T] https://www.cytron.io/tutorial/diy-fire-detection-and-suppression-with-raspberry-pi-pico — read 2026-10-19 via summarising fetch (title; flame sensor → GP3; pump → motor terminal 1; Thonny + CircuitPython; 5-second pump behaviour). Canonical URL: https://my.cytron.io/tutorial/diy-fire-detection-and-suppression-with-raspberry-pi-pico (blocked for this agent)
- [PP] https://my.cytron.io/p-diy-fire-detection-suppression-raspberry-pi-pico — read by the coordinator 2026-10-19 (RM103.08; out of stock; Pico + flame sensor + water pump; CircuitPython; pump 5 s; Thonny; Pico datasheet link; component list truncated)
- KB cross-references (candidate driver boards only, unconfirmed): `robo-pico.md`, `maker-pi-rp2040.md`
