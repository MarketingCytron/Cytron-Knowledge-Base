# Cooling Fan for RPi with Screws (30mm x 30mm) — Verified Reference

| Field | Value |
|---|---|
| Product code | FAN-0305-3008 [PP] |
| Family | Power and accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | No datasheet, manual or tutorial exists ("No documents" on the product page). Primary source = Cytron product page "Cooling Fan for RPi with Screws (30mm x 30mm)", read by the coordinator 2026-10-19 [PP] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*. Every fact below is [PP]; nothing else was readable.

## What it is
A small black 30 mm x 30 mm x 8 mm DC cooling fan for Raspberry Pi boards, supplied with four mounting screws and nuts [PP]. It has a two-wire connector that plugs onto the Raspberry Pi 40-pin GPIO header and runs at two speeds depending on whether it is fed 3.3 V or 5 V DC; Cytron recommends 5 V [PP]. The product URL and title give the rating as 3V–5V, 0.2 A [PP]. The page notes it has a "longer cable" and fits the RetroFlag SuperPi 4 case, and references a Jeff Geerling video showing it in the official Raspberry Pi 4 B case [PP].

## Specifications
| Item | Value | Src |
|---|---|---|
| Operating voltage | 3 V to 5 V DC | [PP] |
| Rated current | 0.2 A (from the product title / URL "3v-5v-0.2a-cooling-fan-for-rpi-with-screws") | [PP] |
| Speed control | Two speeds: 3.3 V (slower) or 5 V (faster), selected by which GPIO-header supply pin the connector is placed on; 5 V recommended | [PP] |
| Connector | Two-wire connector for the Raspberry Pi 40-pin GPIO header | [PP] |
| Cable | "Longer cable" (length not stated) | [PP] |
| Colour | Black | [PP] |
| Dimensions | 30 mm x 30 mm x 8 mm | [PP] |
| Case fit | RetroFlag SuperPi 4 case; shown in the official Raspberry Pi 4 B case (Jeff Geerling video) | [PP] |
| Packing list | 1 x fan; 4 x screws and nuts | [PP] |
| Airflow, noise, RPM, bearing type, wire gauge, connector pitch, PWM/tach wire, weight, operating temperature | Not stated | [PP] |
| Warranty | 12 months | [PP] |
| Price | RM8.00 (10+ RM7.36; 30+ RM6.40) | [PP] |

## Interfaces, terminals and pin mapping
- Two wires only: positive and ground (no PWM control wire, no tachometer wire stated) [PP].
- Power is taken from the Raspberry Pi 40-pin GPIO header: a 3.3 V pin for low speed or a 5 V pin for high speed [PP]. The product page does not state the exact header pin numbers or wire colours — do not publish a pin number without checking the physical connector (see Needs verification). As general Raspberry Pi header knowledge (not a Cytron statement): 5 V is on pins 2 and 4, 3.3 V on pins 1 and 17, GND on pins 6, 9, 14, 20, 25, 30, 34, 39.
- Mounting: four screws and nuts included; hole pattern not stated (30 mm fan class) [PP].

## Rules and gotchas (for code, wiring and tutorials)
- **It is not software-controllable as sold.** Two wires, constant voltage — no PWM, no tachometer [PP]. A tutorial that wants temperature-controlled fan speed needs an extra transistor/MOSFET or a fan HAT; do not say the fan "supports PWM".
- **Not a Raspberry Pi 5 / Active Cooler fan.** Nothing on the page mentions the Pi 5 4-pin fan header; the page targets the 40-pin GPIO header and names the Pi 4 B case and the RetroFlag SuperPi 4 case [PP]. Do not claim Pi 5 fan-header compatibility.
- **Speed is chosen by the supply pin**: 3.3 V = slower/quieter, 5 V = faster; Cytron recommends 5 V [PP].
- **Current**: 0.2 A at the title rating [PP]. The Pi's 3.3 V rail is shared with the SoC and HATs; the page does not state the draw at 3.3 V — treat 0.2 A as the figure to budget.
- **Polarity**: a two-wire DC fan will not run (or can be damaged) if reversed; wire colours are not stated on the page — verify on the connector.
- **No datasheet exists.** Any spec not in the table above (CFM, dBA, RPM, bearing) must not be invented.

## Power and electrical limits
- Supply 3 V to 5 V DC [PP]; recommended 5 V [PP].
- Current 0.2 A [PP, title]. Power at 5 V = 1 W (arithmetic from the stated figures; not separately stated).
- Powered from the Raspberry Pi GPIO header 3.3 V or 5 V pins [PP]. Maximum voltage, inrush, start-up voltage, and polarity protection are not stated.

## Software support
- None required and none provided; the fan runs whenever the header pin it is connected to is powered [PP]. No Cytron library, script or GitHub repository is stated [PP].

## Compatibility and accessories
- Raspberry Pi boards with the 40-pin GPIO header (power source) [PP].
- Cases stated: RetroFlag SuperPi 4 case (fits); official Raspberry Pi 4 Model B case (shown in Jeff Geerling's video) [PP].
- Included: 1 x fan, 4 x screws and nuts [PP].
- Not included / not stated: PWM controller, fan HAT, heatsinks, case, extension cable [PP].
- Related: a Pi 5 is not named on the page; do not pair it with the Pi 5's dedicated fan connector.

## Common mistakes / troubleshooting
- Fan does not spin → connector on the wrong pins or reversed; it needs a 3.3 V or 5 V pin plus GND on the 40-pin header [PP].
- Fan too loud → move the positive wire from 5 V to 3.3 V for the slower speed [PP].
- Fan too weak → use 5 V, which Cytron recommends [PP].
- Expecting speed control from `raspi-config` / `dtoverlay=gpio-fan` → that overlay switches a transistor on a GPIO, which this two-wire fan does not have on its own; extra circuitry is required (general knowledge; not stated by Cytron).
- Quoting airflow or noise figures → none exist on the product page [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Operating voltage wording | [PP] body text: "dual speed (3.3V and 5V DC)" | [PP] specs: "operating voltage 3V to 5V" | Same page; the header supplies 3.3 V or 5 V, and the fan is rated for the 3–5 V range. No real conflict |
| None other | Only one source exists | — | — |

## Needs verification
- Rated current at 3.3 V and at 5 V separately — only "0.2A" in the title [PP].
- Cable length ("longer cable" only) and wire colours / connector type (2-pin Dupont female on 2.54 mm pitch is typical but not stated) [PP].
- Exact 40-pin header pins the connector is meant to occupy — not stated [PP].
- Airflow (CFM), noise (dBA), speed (RPM), bearing type, weight, operating temperature, start-up voltage — not stated anywhere [PP].
- Mounting hole spacing and screw size (M2.5 is typical for 30 mm fans but not stated) [PP].
- Whether the fan can be used with the Raspberry Pi 5 (via GPIO header power) — not stated [PP].
- Product page text was read by the coordinator; this agent could not fetch my.cytron.io.

## Sources
- [PP] Product page https://my.cytron.io/p-3v-5v-0.2a-cooling-fan-for-rpi-with-screws (read by coordinator 2026-10-19: RM8.00, 10+ RM7.36, 30+ RM6.40, in stock 567, warranty 12 months, "No documents")
