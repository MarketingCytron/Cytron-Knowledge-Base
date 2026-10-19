# Breakout Board PS2 Connector — Verified Reference

| Field | Value |
|---|---|
| Product code | BB-PSC [PP] |
| Family | Interface boards and breakouts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = product page; [PP: tutorial Maker Mini Sumo PS2] = the Cytron tutorial above, both as read by the coordinator 2026-10-19. [GH] = CytronTechnologies/PS2X_lib (master), PS2X_lib.cpp read 2026-10-19.  = cross-reference to maker-mini-sumo.md and shield-ps2.md.

## What it is
A small breakout board carrying a PS2 connector (female), pre-soldered on the PCB, with its pins broken out to 0.1" pitch so a PS2 controller (or its wireless receiver) can be wired to a breadboard or donut board [PP]. It is a passive connector board: no chip, no protocol conversion [PP describes only the connector and pin breakout].

## Specifications
The product page has no numeric spec table; every stated fact is listed.

| Item | Value | Src |
|---|---|---|
| Connector | PS2 Connector (Female), pre-soldered on the PCB | [PP] |
| Pin breakout pitch | 0.1" | [PP] |
| Intended mounting | Breadboard or donut board | [PP] |
| Signals used in Cytron's tutorial | DATA, CMD, ATT, CLK, +5V, GND | [PP: tutorial Maker Mini Sumo PS2] |
| Warranty | Not stated (blank on product page) | [PP] |
| Number of pins broken out, pin order, dimensions, header supplied | Not stated | [PP] |

## Interfaces, terminals and pin mapping
The breakout's own pin order is not stated in text. The Cytron tutorial wires these signals from the breakout to the Maker Mini Sumo controller [PP: tutorial Maker Mini Sumo PS2]:

| Breakout signal | Maker Mini Sumo pin | Mini Sumo port name [KB maker-mini-sumo.md] |
|---|---|---|
| DATA | D2 | START |
| CMD | D7 | OPP_FR |
| ATT | D6 | OPP_FC |
| CLK | D5 | OPP_FL |
| +5V | any + terminal | +5V |
| GND | any − terminal | GND |

Library call used in the tutorial: `ps2x.config_gamepad(5,7,6,2,true,true)`, changed from the example's `ps2x.config_gamepad(13,11,10,12,true,true)` [PP: tutorial Maker Mini Sumo PS2]. The PS2X_lib argument order is `config_gamepad(clk, cmd, att, dat, pressures, rumble)` [GH], so 5 = CLK, 7 = CMD, 6 = ATT, 2 = DATA — consistent with the wiring table.

## Rules and gotchas (for code, wiring and tutorials)
- **Bit-banged protocol, not UART.** With BB-PSC the microcontroller talks the PS2 protocol directly through the PS2X library (four GPIO pins: CLK, CMD, ATT, DATA) [PP: tutorial][GH]. This is different from the SHIELD-PS2, which converts the controller to a UART protocol and uses the Cytron_PS2Shield library [KB shield-ps2.md]. Do not mix the two libraries or wiring.
- **Argument order matters:** `config_gamepad(clk, cmd, att, dat, ...)` [GH]. Swapping CLK/DATA is the classic error.
- **Maker Mini Sumo:** "Please remove all of your Object Sensors from the Maker Mini Sumo when connecting to the PS2 Breakout Board." [PP: tutorial] — the PS2 lines reuse the opponent-sensor and START ports (D5, D6, D7, D2) [KB maker-mini-sumo.md].
- **PS2X default pins 13, 11, 10, 12 clash on Maker Mini Sumo** with its motor and sensor pins; use (5, 7, 6, 2) as the tutorial does [KB maker-mini-sumo.md][PP: tutorial].
- **Press reset after connecting** [PP: tutorial].
- Pin labels: identify DATA, CMD, ATT, CLK, +5V and GND on the actual board before wiring; neither the pin order nor the silkscreen labels are stated in text, so do not describe pins by position.
- The tutorial powers the receiver from the controller's +5V [PP: tutorial]. Cytron does not state a supply-voltage rating for the breakout or for PS2 receivers — do not quote one.

## Power and electrical limits
- Passive board; no regulator, protection or level shifting stated [PP].
- In the Cytron tutorial the PS2 receiver is powered from +5V and GND of the Maker Mini Sumo [PP: tutorial]. No current figure is stated.

## Software support
- Arduino PS2X library (Cytron GitHub): https://github.com/CytronTechnologies/PS2X_lib [PP: tutorial][GH]. Install by downloading the zip and using Sketch > Include Library > Add .ZIP Library [GH README].
- Key call: `ps2x.config_gamepad(clk, cmd, att, dat, pressures, rumble)` [GH].

## Compatibility and accessories
- Cytron tutorial component list [PP: tutorial]: Maker Mini Sumo Controller, Wireless PS2 Controller (Compatible), Breakout Board PS2 Connector or PS Connector (Female), male-to-female jumper wires, straight pin header 1x40, AAA batteries.
- The tutorial describes the wireless controller as 2.4GHz, about 10 m range, powered by 2 AAA batteries [PP: tutorial] — these are controller facts, not BB-PSC facts.
- A straight pin header 1x40 appears in the tutorial's component list [PP: tutorial]; the product page does not say a header is supplied with BB-PSC.
- Alternative Cytron product: SHIELD-PS2 (Cytron PS2 Shield) — Arduino shield with onboard PS2 connector and UART output [KB shield-ps2.md].

## Common mistakes / troubleshooting
- Controller not detected → CLK/CMD/ATT/DATA arguments in `config_gamepad` do not match the wiring [GH]; or the board was not reset after connecting [PP: tutorial].
- Erratic robot behaviour on Maker Mini Sumo → object sensors still plugged into the ports now used for PS2 [PP: tutorial].
- Using PS2X example code unchanged on Maker Mini Sumo → default pins (13, 11, 10, 12) clash with motor/sensor pins [KB maker-mini-sumo.md].
- Wireless controller not responding → batteries (2 AAA) or controller not paired; range about 10 m [PP: tutorial].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Description | [PP] PS2 Connector (Female), pre-soldered, pins broken out to 0.1", breadboard or donut board | [3P] RobotShop (Manufacturer # BB-PSC): same | No conflict |
| Wiring on Maker Mini Sumo | [PP: tutorial] DATA D2, CMD D7, ATT D6, CLK D5 | [KB maker-mini-sumo.md] same, from the same tutorial | No conflict |

## Needs verification
- Number of pins broken out (all PS2 pins, or only the six used in the tutorial) and their order on the 0.1" row.
- Whether a pin header is supplied or must be bought separately.
- Board dimensions and mounting holes.
- Supply-voltage rating for the PS2 receiver when used through this breakout (tutorial uses +5V; no rating stated).
- Whether the breakout exposes the ACK and vibration-motor supply pins of the PS2 connector.
- Warranty (blank on the product page).

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM9.45, availability 98, warranty blank, description) — https://my.cytron.io/p-breakout-board-ps2-connector
- [GH] CytronTechnologies PS2X_lib (README.md, PS2X_lib.cpp, PS2X_lib.h) — https://github.com/CytronTechnologies/PS2X_lib
- [3P] (cross-check only) RobotShop "Cytron Breakout Board PS2 Connector", Manufacturer # BB-PSC, SKU RB-Cyt-240 — https://www.robotshop.com/products/cytron-breakout-board-ps2-connector
