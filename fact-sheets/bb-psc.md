# Product fact sheets

## Product name
Breakout Board PS2 Connector (BB-PSC)

## Aliases
BB-PSC, Breakout Board PS2 Connector, Cytron Breakout Board PS2 Connector, PS2 Connector Breakout Board, PS2 Breakout Board

## What it is
A breakout board with a PS2 connector (female) pre-soldered on the PCB and its pins broken out to 0.1" for use on a breadboard or donut board. It lets a PS2 controller be wired directly to a microcontroller's pins.

## Specs and functions
- Connector: PS2 Connector (Female), pre-soldered on the PCB (product page)
- Pins broken out to 0.1" (product page)
- Mounting: breadboard or donut board (product page)
- Signals wired in Cytron's tutorial: DATA, CMD, ATT, CLK, +5V, GND (Cytron tutorial "Maker Mini Sumo with PS2 Controller")
- Number of pins and pin order: [NOT STATED]
- Dimensions: [NOT STATED]
- Warranty: [NOT STATED]

## Interfaces and compatibility
- Maker Mini Sumo wiring (Cytron tutorial): DATA → D2 (START), CMD → D7 (OPP_FR), ATT → D6 (OPP_FC), CLK → D5 (OPP_FL), +5V → any + terminal, GND → any − terminal
- Library: Arduino PS2X library (Cytron GitHub, https://github.com/CytronTechnologies/PS2X_lib); tutorial uses ps2x.config_gamepad(5,7,6,2,true,true), argument order clk, cmd, att, dat, pressures, rumble
- Tutorial controller: Wireless PS2 Controller (Compatible), 2.4GHz, about 10 m range, 2 AAA batteries
- Different from SHIELD-PS2, which converts the PS2 controller to UART and uses a different library

## Use cases
- Connecting a PS2 controller connector to a breadboard or donut board
- Controlling a Maker Mini Sumo robot with a wireless PS2 controller (Cytron tutorial)

## Known limitations
- No Cytron datasheet or user manual; product page and one Cytron tutorial are the sources
- Pin count, pin order and dimensions are not stated
- Supply-voltage rating for the connected PS2 receiver is not stated (the tutorial uses +5V)
- On Maker Mini Sumo all Object Sensors must be removed when connecting the PS2 breakout (Cytron tutorial)
- On Maker Mini Sumo the PS2X example pins (13, 11, 10, 12) must be changed to (5, 7, 6, 2) (Cytron tutorial)
- Press reset after connecting (Cytron tutorial)

## Positioning (kept apart from specs)
- Product page frames it as a pre-soldered PS2 connector broken out for breadboard or donut board use

## Price band
RM9.45 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-breakout-board-ps2-connector

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/tutorial/maker-mini-sumo-with-ps2-controller
