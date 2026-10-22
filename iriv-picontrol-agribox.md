# IRIV PiControl Industry 4.0 Agribox (MyAgritech Software included) — Verified Reference

| | |
|---|---|
| Product code | `KIT-IRIV-AGRBX2` [PP] (page URL slug `p-iriv-picontrol-industry-4.0-agribox-v2-myagritech-software-included`, i.e. a "v2" Agribox). Controllers inside: **IRIV PiControl CM4** (`IRIV-PICL`), Raspberry Pi CM4 **4GB RAM / 32GB eMMC** (wireless or not is not stated) + **IRIV IO Controller** (`IRIV-IOC`, RP2350) [PP] |
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-22 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [PP] = live product page https://my.cytron.io/cytron-industry/p-iriv-picontrol-industry-4.0-agribox-v2-myagritech-software-included read in full in the browser on 2026-10-21 (the page has no Resources tab and no downloadable files). [PP: tutorial] = Cytron tutorial "IRIV PiControl - Setting-Up Dashboard of IRIV Agribox Agriculture Kit" (Raden Fatih, 21 Jul 2025, Project, Intermediate) linked from the page as a related tutorial; it builds an Agribox with the IRIV PiControl alone (3 relays, Node-RED, GPIO) and **does not include the IRIV IO Controller or MyAgritech**, so it describes an earlier/DIY build, not necessarily this kit's wiring. On 2026-10-22 the team pointed to this tutorial as the Agribox tutorial .  = Cytron team answer to the KB, 2026-10-22. [GH] = https://github.com/RadenFatih/IRIV-PiControl-Node-RED-Code (linked from the tutorial; last pushed 2025-10-21; folders: IRIV Agribox Agriculture Kit, 24V DC Pump with Industrial Relay, 3 in 1 Soil Sensor, SHT40 Sensor, Waterproof Ambient Light Sensor, Industrial 8xDI + 8xDO Modbus RTU IO Extender; no licence file) — a personal repo of the tutorial author, not the CytronTechnologies org. Wiring figures in the tutorial are images and were not read.

**Kit rule:** the controllers are not re-documented here — see `iriv-picontrol-cm4.md` (IRIV PiControl **CM4**, `IRIV-PICL`; not the CM5 `IRIV-PICL5` in `iriv-picontrol-cm5.md`) and `iriv-io-controller.md` (RP2350A, no Linux). Only kit-level facts are stated.

**Scope note:** the KB excludes customer / white-label builds (IRIV GreenBox, Systec, Vitrox, MACHHUB, OEI). The team confirmed on 21 Oct 2026 that this Agribox is added as a Cytron product. Do not merge GreenBox facts into this file.

## What it is
A packaged smart-agriculture control box from Cytron: an IRIV PiControl CM4 (4GB RAM / 32GB eMMC) and an IRIV IO Controller with 5 industrial 24 VDC relays — 3 switching DC pump/valve outputs on Hangton HE21 2-pin connectors and 2 switching 3-pin 16A AC sockets for AC pumps — plus an RS485 3-in-1 soil sensor (moisture, temperature, EC), an RS485 temperature and humidity sensor, an illuminated push button and a Meanwell 24V power supply [PP]. It is sold with the **MyAgritech** software package (web dashboard, cloud database, remote monitoring and control, automation scheduling, data analysis and email alerts) [PP]. Cytron calls it both "a Complete Industrial Solution for Smart Agriculture Application" and "this industrial-grade training kit" [PP].

## Specifications
Kit-level rows. Controller specs: `iriv-picontrol-cm4.md`, `iriv-io-controller.md`.

| Item | Value | Src |
|---|---|---|
| Product name | IRIV PiControl Industry 4.0 Agribox (MyAgritech Software included) | [PP] |
| Product code | KIT-IRIV-AGRBX2 | [PP] |
| Price / availability | RM3,673.95; availability "Enquiry" (2026-10-21) | [PP] |
| Warranty | 12 months | [PP] |
| Main controller | IRIV PiControl, Raspberry Pi Compute Module 4, 4GB RAM 32GB eMMC ("IRIV PiControl 4GB 32eMMC") | [PP] |
| I/O controller | IRIV IO Controller, "industrial-grade IO Controller based on Raspberry Pi RP2350" | [PP] |
| Input voltage | 240 VAC | [PP] |
| Power supply | Technical spec: "24 VDC, 1 A"; packing list: "Meanwell 24V 100W DC Power Supply" — see *Conflicts* | [PP] |
| Relays | 5x industrial relay, 24 VDC | [PP] |
| DC outputs | 3 relays to Hangton HE21 2-pin connectors; for DC pumps, lights and valves (e.g. A/B/C or N/P/K fertiliser mixing, low-power watering valves or sprinklers); pumps can also be wired directly to the relays | [PP] |
| AC outputs | 2 relays to 3-pin 16A AC sockets, for high-power AC pumps ("Just plug it in") | [PP] |
| Relay contact rating / DC output voltage | Not stated | — |
| Soil sensor | RS485 3-in-1 (moisture, temperature, EC); 24 V; temperature −40 to +60 ℃ (0.1 ℃ resolution); moisture 0–100% (1%); EC 0–20000 µS/cm (1 µS/cm) | [PP] |
| Temperature / humidity sensor | RS485 industrial; 24 V; −40 to 120 ℃; 0–99.9 %RH; accuracy ±0.3 ℃ and ±2 %RH at 25 ℃; sampling period 3 s | [PP] |
| Push button | Industrial illuminated push button, 24 V, push button + LED, NC or NO configuration | [PP] |
| Software | MyAgritech: real-time dashboard, cloud storage and database, automation scheduling, data analysis and reporting, email alerts and notifications | [PP] |
| MyAgritech entitlement | **1 User Account, a Getting Started Guide and a Dedicated Support Channel** on purchase — confirmed by the team; the page also mentions tutorials and a dedicated support team | [PP] |
| Setup tutorial | "IRIV PiControl - Setting-Up Dashboard of IRIV Agribox Agriculture Kit" (21 Jul 2025): Node-RED dashboard with System, AC Socket, Controls and Sensors groups; flows on GitHub | [PP: tutorial][GH] |
| MyAgritech provider | **Not stated** — the page does not say who develops or hosts MyAgritech | — |
| MyAgritech licence / subscription | **Not stated** — no subscription, renewal, term or hosting fee is mentioned on the page | — |
| Enclosure, IP rating, dimensions, weight, operating temperature of the box | Not stated | — |

### Product page facts (my.cytron.io, read 21 Oct 2026)
- **Packing list:** 1x IRIV PiControl Industry 4.0 Agribox; 1x IRIV PiControl 4GB 32eMMC; 1x IRIV IO Controller; 5x industrial relay; 3x Hangton HE21 2-pin male connectors; 2x AC sockets; 1x industrial illuminated push button; 1x RS485 industrial temperature and humidity sensor; 1x RS485 3-in-1 soil sensor; 1x Meanwell 24V 100W DC power supply [PP]. Sensors are listed but cable lengths are not.
- **Features listed:** real-time monitoring of temperature, humidity, soil moisture and EC, dashboard reachable remotely through a web browser or mobile; user-friendly interface "for farmers, students, and researchers"; alerts and notifications on abnormal readings; graphs and crop performance reports; integration with fertigation, aquaponics, greenhouse or open-field systems; automatic control of irrigation, fertilisation, lighting and pumps by schedule or sensor readings [PP].
- **Connector note (verbatim sense):** connect pumps or valves to "the provided Hangton HE21 2-Pin Female Connector"; "You need to use the Hangton HE21 2-Pin Male Connector to connect to the existing DC Port. Make sure your pumps and valves have the proper connector" [PP] — see *Conflicts*.
- **Use cases named:** smart agriculture, plant monitoring, automatic plant watering, agriculture data gathering, soil monitoring [PP].
- **No Resources tab**, no datasheet, no manual and no MyAgritech link on the page [PP].
- **Reviews:** 1 rating, 5/5 (May 2026) [PP].
- Page tags include "io controller", "ioc", "fertigation", "irrigation", "rs485" [PP].

## Interfaces, terminals and pin mapping
The kit's internal wiring (which controller drives which relay, which RS485 port the sensors use, how the IO Controller links to the PiControl) is **not documented** on the product page.

The related tutorial's earlier build (IRIV PiControl only, Node-RED, no IO Controller) [PP: tutorial]:

| Function | Tutorial assignment | Matches KB controller mapping |
|---|---|---|
| Push button (activation) | GPIO13 (rpi-gpio in) | DI0 = GPIO13 on IRIV PiControl CM4 (`iriv-picontrol-cm4.md`) |
| AC socket relay | GPIO25 (rpi-gpio out) | DO2 = GPIO25 |
| Pump 1 / Pump 2 relays | GPIO23 / GPIO24 | DO0 / DO1 = GPIO23 / GPIO24 |
| RS485 sensors | Modbus serial RTU, 9600 baud, port written "/dev/tty/ACM0" | KB: RS485 = `/dev/ttyACM0` (the tutorial's path has a typo) |
| Soil sensor | Unit ID 1, FC3 read holding registers, address 0, quantity 3 (moisture, temperature, conductivity); default 4800 baud, changed to 9600 | — |
| Temp/humidity sensor | Default ID 1 at 9600 baud; set to Unit ID 2 with the DIP switch inside the sensor; FC3, address 0, quantity 2 | — |
| Push-button LED | 2 of the button's 4 pins drive the LED that shows the AC socket is on | — |

Do not present this table as the v2 kit's wiring: the v2 packing list adds an IRIV IO Controller and 5 relays (the tutorial uses 3), and the kit ships with MyAgritech rather than a hand-built Node-RED flow [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **Name both controllers and the variant:** IRIV PiControl **CM4 4GB/32GB** + IRIV IO Controller (RP2350) [PP]. Never write bare "IRIV PiControl" as if it could be the CM5, and never call the IO Controller a Linux device.
- **RS485 sensors share one bus** and need different Modbus IDs and the same baud rate — the tutorial sets the temperature/humidity sensor to ID 2 and the soil sensor to 9600 baud [PP: tutorial]. On the PiControl the RS485 port is `/dev/ttyACM0` (USB serial), not a GPIO UART (`iriv-picontrol-cm4.md`).
- **AC sockets switch mains** via 24 VDC relays; the relay contact current rating is not stated, so do not promise 16 A loads from the "16A" socket rating [PP] (inferred caution).
- **Power supply figure:** quote the packing list's Meanwell 24V 100W unit; the "24 VDC, 1 A" line in the technical specification conflicts [PP].
- **MyAgritech:** say only what the page says — 1 user account, Getting Started Guide, dedicated support channel, cloud dashboard/database/alerts [PP]. Do not state who provides it, whether it needs a subscription, or whether it works offline.
- **Do not mix with IRIV GreenBox** or other customer builds (out of KB scope).
- Never copy MyAgritech or controller logins.

## Power and electrical limits
- Mains input 240 VAC to a Meanwell 24 V DC supply (100 W per packing list; "24 VDC, 1 A" per spec line) [PP].
- Relays, soil sensor, temperature/humidity sensor and push button are all 24 V parts [PP].
- Controller VIN 10–30 VDC on both IRIV PiControl CM4 and IRIV IO Controller (`iriv-picontrol-cm4.md`, `iriv-io-controller.md`) — the 24 V rail is inside that range (inferred).
- DC output voltage at the HE21 connectors, AC socket fusing and relay ratings are not stated.

## Software support
- **MyAgritech** (included): user-friendly web dashboard, cloud server connectivity, remote monitoring and control, data logging and analysis, automation scheduling, email alerts; accessible from PC, laptop or smartphone [PP].
- The IRIV PiControl also supports Node-RED (as used in the tutorial build) [PP: tutorial]; the page does not say whether Node-RED is pre-installed on the Agribox.
- **Node-RED flows:** the tutorial's flows (Agribox dashboard, 24 V pump relay, 3-in-1 soil sensor, SHT40, ambient light sensor, 8DI/8DO Modbus IO extender) are in https://github.com/RadenFatih/IRIV-PiControl-Node-RED-Code [GH]. It needs the `node-red-contrib-modbus` palette for the RS485 sensors [PP: tutorial]. The repo has no licence file — link to it rather than copying flows into Cytron material (inferred caution).
- OS image, MyAgritech version, hosting location and data retention are not stated.

## Compatibility and accessories
- DC pumps and valves need Hangton HE21 2-pin connectors to plug in, or can be wired directly to the relays [PP].
- Any AC pump with a 3-pin plug can use the AC sockets [PP] (subject to the unstated relay rating).
- Integration targets named: fertigation, aquaponics, greenhouse, open-field farming [PP].
- Pumps, valves and sprinklers are not included [PP].

## Common mistakes / troubleshooting
- Using the tutorial's Node-RED GPIO wiring as if it were the v2 kit's (the v2 adds an IO Controller and 2 more relays).
- Both RS485 sensors left at factory ID 1 or at different baud rates → Modbus read failures [PP: tutorial].
- Typing the RS485 port as `/dev/tty/ACM0` (tutorial typo) instead of `/dev/ttyACM0`.
- Assuming the 16A sockets can switch 16 A without checking the relay rating.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Power supply | Technical specification: "Power Supply: 24 VDC, 1 A" [PP] | Packing list: "Meanwell 24V 100W DC Power Supply" (~4.2 A, inferred) [PP] | Same source, unresolved; quote the packing list and ask engineering |
| HE21 connector gender | Description: pumps connect to "the provided Hangton HE21 2-Pin Female Connector"; note: you need the HE21 male connector for "the existing DC Port" [PP] | Packing list: "3 x Hangton HE21 2-Pin Male Connectors"; spec: relays "connected to Hangton HE21 2-Pin Male Connectors" [PP] | Unresolved; say "Hangton HE21 2-pin connectors" and ask which half is fitted on the box and which is supplied |
| Relay count | Kit page: 5 relays (3 DC + 2 AC) [PP] | Tutorial build: 3x 24 V relays, 2 DC pumps, 1 AC socket [PP: tutorial] | Different builds; the product page is the kit |
| Controllers | Kit page: IRIV PiControl + IRIV IO Controller [PP] | Tutorial: IRIV PiControl only [PP: tutorial] | Product page for the kit |
| Product type wording | "A Complete Industrial Solution for Smart Agriculture Application" [PP] | "This industrial-grade training kit" [PP] | Both on the page; call it a smart-agriculture control kit |

## Needs verification
- Which controller drives the relays (PiControl DO vs IO Controller DO), how the IO Controller connects to the PiControl (RS485 / Ethernet), and which RS485 port each sensor uses.
- Whether the PiControl CM4 4GB/32GB is the wireless variant (the CM4 page sells "Wireless 4GB / 32GB" — `iriv-picontrol-cm4.md`).
- PSU rating (24 V 1 A vs 100 W) and exact Meanwell model; relay contact ratings; DC output voltage at HE21 ports; AC socket protection.
- Enclosure type, IP rating, dimensions, weight and operating temperature of the assembled box.
- Whether "v2" in the URL implies a v1 product and what changed (the 2025 tutorial build may be v1).
- Sensor brand/model numbers and cable lengths.

## Sources
- [PP] Product page (read 2026-10-21): https://my.cytron.io/cytron-industry/p-iriv-picontrol-industry-4.0-agribox-v2-myagritech-software-included
- [GH] https://github.com/RadenFatih/IRIV-PiControl-Node-RED-Code — listed 2026-10-22
- [PP: tutorial] IRIV PiControl - Setting-Up Dashboard of IRIV Agribox Agriculture Kit (Raden Fatih, 21 Jul 2025): https://my.cytron.io/tutorial/IRIV-node-red-Agriculture-Box-tutorial
- Controllers: `iriv-picontrol-cm4.md`, `iriv-io-controller.md`
