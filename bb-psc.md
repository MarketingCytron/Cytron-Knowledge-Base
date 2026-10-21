# Breakout Board PS2 Connector — Verified Reference

| Field | Value |
|---|---|
| Product code | BB-PSC [PP] |
| Family | Interface boards and breakouts |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = product page, read by the coordinator 2026-10-19; [PP: tutorial Maker Mini Sumo PS2] (short form [PP: tutorial]) = the Cytron tutorial above, read in full in the browser 2026-10-21 including its wiring drawing (figure facts are marked "wiring figure"). [GH] = CytronTechnologies/PS2X_lib (master), PS2X_lib.cpp read 2026-10-19.  = cross-reference to maker-mini-sumo.md and shield-ps2.md.

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
| Pins broken out | One row of **9 pads**, marked **JP1**, square pad at one end (wiring figure) | [PP: tutorial] |
| Board silkscreen | "BB-PSC", "www.cytron.com.my", "JP1" (wiring figure) | [PP: tutorial] |
| Pad labels on the header | None visible in the wiring figure (only "JP1") | [PP: tutorial] |
| Dimensions, header supplied | Not stated | [PP] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- Page re-read: breakout for a female PS2 connector, pre-soldered on the PCB; pins broken out to 0.1" for breadboard or donut board; links the PS2 Connector (Female) part [PP]. No features, packing-list or resources tab. Matches the KB.

## Interfaces, terminals and pin mapping
### BB-PSC header JP1 (from the tutorial's wiring figure)
The text never lists the pad order; it comes from the wiring drawing (board shown with the PS2 socket below and the 9-pad row along the top, square pad at the right-hand end, next to the "JP1" label) [PP: tutorial, wiring figure]. Pad numbers count from the square pad — numbering from the square pad is the usual pin-1 convention and is an inference, not printed.

| JP1 pad (from square pad) | Wire in figure | Signal | Maker Mini Sumo pin |
|---|---|---|---|
| 1 (square) | yellow | DATA | D2 (START) |
| 2 | green | CMD | D7 (OPP_FR) |
| 3 | — (not wired) | not stated | — |
| 4 | black, "−" | GND | any − terminal |
| 5 | red, "+" | +5V | any + terminal |
| 6 | blue | ATT | D6 (OPP_FC) |
| 7 | orange | CLK | D5 (OPP_FL) |
| 8 | — (not wired) | not stated | — |
| 9 | — (not wired) | not stated | — |

The order matches the widely published PS2 controller socket pinout (1 DATA, 2 CMD, 3 vibration-motor supply, 4 GND, 5 VCC, 6 ATT, 7 CLK, 8 not connected, 9 ACK) [3P, general reference — not a Cytron statement], so the breakout appears to bring all nine socket pins out in socket order. Treat the roles of pads 3, 8 and 9 as unconfirmed.

### Wiring to Maker Mini Sumo (tutorial text)
The Cytron tutorial wires these signals from the breakout to the Maker Mini Sumo controller [PP: tutorial Maker Mini Sumo PS2]:

| Breakout signal | Maker Mini Sumo pin | Mini Sumo port name [KB maker-mini-sumo.md] |
|---|---|---|
| DATA | D2 | START |
| CMD | D7 | OPP_FR |
| ATT | D6 | OPP_FC |
| CLK | D5 | OPP_FL |
| +5V | any + terminal | +5V |
| GND | any − terminal | GND |

On the Maker Mini Sumo the four signal wires land on the screw-terminal ports labelled CLK, ATT, CMD and DATA in the figure (the OPP_FL, OPP_FC, OPP_FR and START ports); the tutorial took the pin numbers from the "Arduino Pin Mapping" table of the Maker Mini Sumo datasheet, reproduced as a figure (START D2, OPP_FC D6, OPP_FL D5, OPP_FR D7) [PP: tutorial].

Library call used in the tutorial: `ps2x.config_gamepad(5,7,6,2,true,true)`, changed from the example's `ps2x.config_gamepad(13,11,10,12,true,true)` [PP: tutorial Maker Mini Sumo PS2]. The PS2X_lib argument order is `config_gamepad(clk, cmd, att, dat, pressures, rumble)` [GH], so 5 = CLK, 7 = CMD, 6 = ATT, 2 = DATA — consistent with the wiring table.

## Rules and gotchas (for code, wiring and tutorials)
- **Bit-banged protocol, not UART.** With BB-PSC the microcontroller talks the PS2 protocol directly through the PS2X library (four GPIO pins: CLK, CMD, ATT, DATA) [PP: tutorial][GH]. This is different from the SHIELD-PS2, which converts the controller to a UART protocol and uses the Cytron_PS2Shield library [KB shield-ps2.md]. Do not mix the two libraries or wiring.
- **Argument order matters:** `config_gamepad(clk, cmd, att, dat, ...)` [GH]. Swapping CLK/DATA is the classic error.
- **Maker Mini Sumo:** "Please remove all of your Object Sensors from the Maker Mini Sumo when connecting to the PS2 Breakout Board." [PP: tutorial] — the PS2 lines reuse the opponent-sensor and START ports (D5, D6, D7, D2) [KB maker-mini-sumo.md].
- **PS2X default pins 13, 11, 10, 12 clash on Maker Mini Sumo** with its motor and sensor pins; use (5, 7, 6, 2) as the tutorial does [KB maker-mini-sumo.md][PP: tutorial].
- **Press reset after connecting** [PP: tutorial].
- **Pad order (wiring figure):** counting from the square pad of JP1: 1 DATA, 2 CMD, 3 unused, 4 GND, 5 +5V, 6 ATT, 7 CLK, 8 and 9 unused [PP: tutorial, wiring figure]. The header pads carry no signal labels in the figure, so when describing pins by position always say "counted from the square pad", and include the drawing.
- **Start-up order:** upload the code, switch on the PS2 controller, power the Maker Mini Sumo, then press reset to start control [PP: tutorial].
- A "Wireless PS2 Controller (Compatible)" is recognised by the PS2X library as a DualShock controller; the tutorial puts its button handling in that branch [PP: tutorial].
- The tutorial powers the receiver from the controller's +5V [PP: tutorial]. Cytron does not state a supply-voltage rating for the breakout or for PS2 receivers — do not quote one.

## Power and electrical limits
- Passive board; no regulator, protection or level shifting stated [PP].
- In the Cytron tutorial the PS2 receiver is powered from +5V and GND of the Maker Mini Sumo [PP: tutorial]. No current figure is stated.

## Software support
- Arduino PS2X library (Cytron GitHub): https://github.com/CytronTechnologies/PS2X_lib [PP: tutorial][GH]. Install by downloading the zip and using Sketch > Include Library > Add .ZIP Library [GH README].
- Key call: `ps2x.config_gamepad(clk, cmd, att, dat, pressures, rumble)` [GH].
- Tutorial links: PS2X library at https://github.com/CytronTechnologies/PS2X_lib/tree/main ("CYTRON GITHUB"); the tutorial's manual-install method refers to an "Arduino-PS2X-master.zip" containing a "PS2X_lib" folder copied into Documents\Arduino\libraries [PP: tutorial]. Example code "PS2Controller_Basic" and the "FULL CODE" adjusted for Maker Mini Sumo are Google Drive links (not opened; not copied here).
- The full code also uses the **Cytron Maker Sumo Library** (Library Manager, by Cytron Technologies Sdn Bhd; version 1.2.3 shown installed in the tutorial screenshot) for `MakerSumo.begin()` and `setMotorSpeed(MOTOR_L/MOTOR_R, ±100)` [PP: tutorial].

## Compatibility and accessories
- Cytron tutorial component list [PP: tutorial]: Maker Mini Sumo Controller, Wireless PS2 Controller (Compatible), Breakout Board PS2 Connector or PS Connector (Female), male-to-female jumper wires, straight pin header 1x40, AAA batteries.
- In the tutorial's hardware list (read 2026-10-21) the Wireless PS2 Controller (Compatible) is marked **Discontinued**; BB-PSC RM9.45 and PS Connector (Female) RM3.00 are listed [PP: tutorial].
- The tutorial describes the wireless controller as 2.4GHz, about 10 m range, powered by 2 AAA batteries [PP: tutorial] — these are controller facts, not BB-PSC facts.
- A straight pin header 1x40 appears in the tutorial's component list [PP: tutorial]; the product page does not say a header is supplied with BB-PSC.
- Alternative Cytron product: SHIELD-PS2 (Cytron PS2 Shield) — Arduino shield with onboard PS2 connector and UART output [KB shield-ps2.md].

## Common mistakes / troubleshooting
- Controller not detected → wires counted from the wrong end of JP1 (count from the square pad: 1 DATA, 2 CMD, 4 GND, 5 +5V, 6 ATT, 7 CLK) [PP: tutorial, wiring figure]; or CLK/CMD/ATT/DATA arguments in `config_gamepad` do not match the wiring [GH]; or the board was not reset after connecting [PP: tutorial].
- Erratic robot behaviour on Maker Mini Sumo → object sensors still plugged into the ports now used for PS2 [PP: tutorial].
- Using PS2X example code unchanged on Maker Mini Sumo → default pins (13, 11, 10, 12) clash with motor/sensor pins [KB maker-mini-sumo.md].
- Wireless controller not responding → batteries (2 AAA) or controller not paired; range about 10 m [PP: tutorial].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Description | [PP] PS2 Connector (Female), pre-soldered, pins broken out to 0.1", breadboard or donut board | [3P] RobotShop (Manufacturer # BB-PSC): same | No conflict |
| Wiring on Maker Mini Sumo | [PP: tutorial] DATA D2, CMD D7, ATT D6, CLK D5 | [KB maker-mini-sumo.md] same, from the same tutorial | No conflict |
| JP1 pad order | [PP: tutorial, wiring figure] from the square pad: DATA, CMD, –, GND, +5V, ATT, CLK, –, – | [3P] general PS2 socket pinout: 1 DATA, 2 CMD, 3 motor supply, 4 GND, 5 VCC, 6 ATT, 7 CLK, 8 n/c, 9 ACK | Agree on all six used pins; Cytron figure wins; roles of pads 3, 8, 9 stay unconfirmed |
| PS2X library branch | [PP: tutorial] link `PS2X_lib/tree/main`; install step names "Arduino-PS2X-master.zip" | [GH] read 2026-10-19 as `master` | Same Cytron repository; use whatever the repository's default branch is when linking |

## Needs verification
- Function of JP1 pads 3, 8 and 9 (not wired in the tutorial; by the usual PS2 pinout they would be vibration-motor supply, not connected and ACK) and whether they connect straight to the socket.
- Whether the board has any pad labels on the back silkscreen (the figure shows only "JP1" on the front).
- Whether a pin header is supplied or must be bought separately.
- Board dimensions and mounting holes.
- Supply-voltage rating for the PS2 receiver when used through this breakout (tutorial uses +5V; no rating stated).
- Warranty (blank on the product page).

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM9.45, availability 98, warranty blank, description) — https://my.cytron.io/p-breakout-board-ps2-connector
- [GH] CytronTechnologies PS2X_lib (README.md, PS2X_lib.cpp, PS2X_lib.h) — https://github.com/CytronTechnologies/PS2X_lib
- [3P] (cross-check only) RobotShop "Cytron Breakout Board PS2 Connector", Manufacturer # BB-PSC, SKU RB-Cyt-240 — https://www.robotshop.com/products/cytron-breakout-board-ps2-connector
