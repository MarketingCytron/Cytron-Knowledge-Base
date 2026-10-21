# LiPo Power Shield — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-LIPO` [PP][UM]; manual name "Cytron LiPo Power Shield" [UM] |
| Family | Arduino shields |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Primary source | **No datasheet exists.** Primary = "SHIELD-LIPO — Cytron LiPo Power Shield — User's Manual", **V1.0, January 2016** (public Google Doc, 13 pages; read in full incl. figures 2026-10-21) [UM] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = the January 2016 User's Manual V1.0 (Cytron Google Doc, exported to PDF and read in full on 2026-10-21 including the dimension drawing, the front and back board-layout photos, the stacking/charging/VBATT photos and the example sketch, which are images in the doc; the Electrokit PDF mirror has the same text). The doc was supplied by the marketing team as "Schematic & Technical Specs", but it calls itself a User's Manual and contains no schematic. [PP] = coordinator's read of https://my.cytron.io/p-lipo-power-shield on 2026-10-16. No GitHub library exists for this product. [3P] = Cytron's own Tindie listing (reseller channel, not my.cytron.io) — cross-check only. No Drive hit for a separate datasheet. No [DT] confirmation.

## What it is
An Arduino shield that powers a stacked Arduino from a single-cell 3.7 V LiPo battery through an onboard 5 V boost converter, with an integrated 500 mA charger fed from the shield's own micro-USB port or from the Arduino's USB port [UM]. It has a power switch, charge/full/low-battery/power LEDs, under-voltage protection and a solder jumper for reading the battery voltage from the Arduino [UM]. The battery is a separate line item [PP].

## Specifications
The manual has no numbered spec table; the rows are every quantitative statement in Section 1 "Features" and the board layout [UM].

| Item | Value | Src |
|---|---|---|
| Output voltage | 5 V | [UM] |
| Output current | "Output current: 1A" (Features); body text: "can provide at least 500mA current, and peak at 1A" | [UM] |
| Battery | 3.7 V 1300 mAh LiPo (single cell); the cell in the manual photos is marked "SDL723562P 1300mAh 3.7V 4.81Wh" | [UM] |
| Integrated charger current | 500 mA | [UM] |
| Charge input | Onboard micro-USB port (USB Micro B cable) **or** the Arduino's USB port | [UM] |
| Low-battery indicator threshold | 3.3 V | [UM] |
| Under-voltage protection cut-out | 2.4 V | [UM] |
| LEDs | Low power (battery < 3.3 V); Power (green); Full (fully charged); Charge (charging) | [UM] |
| Switch | Power switch — "Switch to On/Off the battery" | [UM] |
| Buttons | Main board reset button ("Arduino main board will require around 30ms to ready after reset") | [UM] |
| Battery-voltage monitor | VBATT solder jumper on the back of the shield — a row of **six pads, one per analog pin A0–A5** (silkscreen under the pads, back-of-board photos); solder one pad to send the battery voltage to that analog pin. The manual's photo shows the **A3** pad bridged | [UM] |
| Headers | Stackable side headers (digital I/O, analog, power) | [UM] |
| ICSP | **Not passed through** ("the battery is in the way") | [UM] |
| Packing list | 1 x SHIELD-LIPO | [UM] |
| Warranty | 12 months | [UM][PP] |
| Dimensions | ~79.5 mm × ~53 mm (manual dimension drawing, board outline without the toggle switch) | [UM] |
| Dimensions | 80 mm × 54 mm (excluding the toggle switch) | [PP] |
| Boost converter / charger IC | **Not stated** | [UM] |
| Arduino pins used | 5V and GND only; battery-voltage monitoring optional via pads to A0–A6 | [PP] |
| Battery connector type | 2-pin plug-in connector labelled **"BATT"** (white housing, red and black leads) in the photos; connector family/pitch **not stated** | [UM] |
| LED colours (photos) | Power = green (stated); Charge LED shows red/orange while charging in the charging photos | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** stacks on Arduino UNO R3 or similar (UNO R3, Maker UNO, CT-UNO, CT-UNO-SE, Mega, Leonardo, Due); **uses only the 5V and GND pins**; battery voltage monitor is optional; digital and analog pins stay free; 5 V boost converter from a standard LiPo (**3.0–4.2 V**); charges through its own micro-USB or from the Arduino's USB when the Arduino is plugged in for programming; any 3.7/4.2 V Li-ion or LiPo cell, 1300 mAh suggested (fits the shield) [PP].
- **Output:** "at least 1000mA current, and output peak current at 1100mA"; boost has over-current protection; battery under-voltage protection [PP].
- **Spec list:** start-up maximum continuous current 700 mA; maximum continuous current 1000 mA; over-current cut-off about 1100 mA; on-board LiPo charger max 500 mA; under-voltage cut-off 2.40 V; Charge, Full Charged, battery LOW and power LEDs; power toggle switch; micro-USB charging port; optional battery voltage monitoring to A0–A6 (connection pads on the bottom of the PCB); **dimension 80 mm × 54 mm (excluding the toggle switch)** [PP].
- **Battery:** sold separately ("the Lipo battery is not included, yet the Lipo battery is under the default added item") [PP].
- **Resources:** User's Manual (Google Doc); line-following robot tutorials with CT-ARM [PP]. No packing-list tab on the page.

## Interfaces, terminals and pin mapping
| Function | Arduino pin(s) / terminal | Src |
|---|---|---|
| 5 V output to the Arduino | Through the stacked power header (back silkscreen: IOREF, RESET, 3V3, 5V, GND, GND, VIN); the Arduino runs from the shield when the power switch is on. Exact pin **not stated** in the manual; the product page says only 5V and GND are used [PP] | [UM] |
| Battery voltage sense | VBATT solder jumper (back of the PCB): six pads labelled **A0, A1, A2, A3, A4, A5**; bridge the pad for the analog pin you want. Manual example: A3 bridged, sketch reads `A3` (comment: "select the input pin, A0 to A5") | [UM] |
| Micro-USB port | Charging only ("This USB port is for charging") | [UM] |
| Arduino USB port | Also charges the battery — **only with the shield's power switch OFF** ("If it is ON, the battery will not charge") | [UM] |
| LiPo battery | Mounted on the shield (3.7 V 1300 mAh) | [UM] |
| Stackable digital I/O / analog / power headers | Pass-through for shields above or below | [UM] |
| ICSP header | Not passed through | [UM] |
| Main board reset button | Resets the Arduino (silkscreen "RST") | [UM] |

## Rules and gotchas (for code, wiring and tutorials)
- **Charging through the Arduino's USB needs the shield switched OFF**; charging through the shield's own micro-USB works with the switch ON or OFF [UM]. Tutorials that leave the switch on while charging from the Arduino will show "Charge" LED never lighting.
- **Charge LED = charging, Full LED = fully charged** [UM] — do not describe a blinking pattern; none is stated.
- **Low-battery LED comes on below 3.3 V**; the boost output cuts out at **2.4 V** to protect the cell [UM]. Nothing is stated about what the Arduino sees between 3.3 V and 2.4 V other than the LED.
- **Stacking order matters**: the shield does not pass the ICSP header, so any shield that uses ICSP for data (the UM example: Ethernet Shield) must sit **below** the LiPo shield — "you'll need to stack the Shield LiPo above it" [UM].
- **Battery monitoring needs a solder bridge**: bridge **one** of the six VBATT pads (A0–A5) on the back before the Arduino can read the battery voltage; the manual uses **A3** [UM]. Its sketch converts with `VBatt = analogRead(A3) * (5.0 / 1023.0)` — no scaling factor, so the battery appears to go to the pin without a divider (inferred from the formula; a full cell is 4.2 V, inside a 5 V ADC range). The result is only as accurate as the Arduino's 5 V reference (inferred).
- **Pick a free analog pin for VBATT**: once bridged, that analog pin carries the battery voltage, so do not use it for a sensor or another shield (inferred from the pad design). The product page says "A0–A6"; the board silkscreen has A0–A5 only [UM].
- **Current budget**: plan on ≥ 500 mA continuous and 1 A peak from the 5 V output [UM Section 1 text]; the Features line says "1A" — quote both with the source if a number matters.
- Single-cell 3.7 V LiPo only [UM]; no other battery chemistry or cell count is mentioned.
- Power switch turns the **battery** on/off [UM]; it does not stop USB charging via the shield's own port.
- No library is needed — the manual's example only reads an analog input and prints to Serial Monitor [UM].

## Power and electrical limits
- Battery input: 3.7 V 1300 mAh LiPo [UM]; input voltage window other than the 2.4 V cut-out: **not stated** [UM].
- Output: 5 V; "at least 500mA … peak at 1A" / "Output current: 1A" [UM].
- Charger: 500 mA charge current from micro-USB or Arduino USB [UM]; charger input voltage: **not stated** (USB implied).
- Protection stated: under-voltage (2.4 V cut-out) [UM]. Over-current, short-circuit, reverse polarity, over-charge: **not stated** [UM].
- What it powers: the stacked Arduino ("take your Arduino anywhere") [UM]; the UM does not say how much of the 1 A is left for other shields.

## Software support
- Arduino IDE: the manual's Section 6 example sketch "shield-lipo" (an image in the doc, read 2026-10-21): `int Pin = A3;` → `Serial.begin(9600)` → in `loop()` `VRead = analogRead(Pin); VBatt = VRead * (5.0 / 1023.0);` → prints "Battery voltage = " and the value → `delay(200)` [UM]. Needs the A3 VBATT pad bridged; change `Pin` to match the pad you bridged.
- No Cytron library, GitHub repo, MicroPython or CircuitPython support is stated [UM][PP].

## Compatibility and accessories
- Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo "and possibly other pin compatible main boards" [UM]; hardware example uses Arduino UNO / CT-UNO [UM].
- "You can stack shields on top, or stack the Shield LiPo on top" (except ICSP-dependent shields, which go below) [UM].
- Battery: 3.7 V 1300 mAh LiPo — sold as an option (Lip-3.7-1300) with the shield on my.cytron.io [PP]; the UM packing list shows the shield only [UM].
- Charging cable: USB Micro B [UM].
- Price: RM57.75 (Cytron product page, read 2026-10-16) [PP].

## Common mistakes / troubleshooting
- **Battery not charging from the Arduino's USB** → switch the shield OFF while charging that way [UM].
- **Ethernet (or other ICSP) shield stops working when stacked above the LiPo shield** → ICSP is not passed through; put the LiPo shield on top [UM].
- **Arduino cannot read battery voltage** → VBATT solder jumper on the back not bridged, or the sketch reads a different analog pin from the pad you bridged (manual example: A3) [UM].
- **Low LED on / Arduino browns out** → battery below 3.3 V; below 2.4 V the output cuts out — charge it [UM].
- **Not enough current for motors/servos** → output is at least 500 mA continuous, 1 A peak [UM]; use a separate motor supply.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Output current | [UM] Section 1 text: "at least 500mA current, and peak at 1A"; [UM] Features: "Output current: 1A" | [PP] (read 2026-10-19): "at least 1000mA", "peak current at 1100mA", "Start up maximum continuous current at 700mA", "Over current cutoff: ~1100mA" (the same text appears on Tindie [3P]) | Unresolved between two Cytron sources. Safe claim: "about 1 A"; ask [DT] (*Needs verification*) |
| Battery included? | [UM] packing list text: 1 x SHIELD-LIPO only (the packing-list photo shows the shield with the 1300 mAh cell fitted) | [PP] sold with a 1300 mAh LiPo option (Lip-3.7-1300); [3P] Tindie: "battery is not included" / "under the default added item" | Battery is a separate (optional) item; say so |
| Warranty | [UM] 12 months | [PP] 12 months | Agree |
| Dimensions | [UM] drawing: ~79.5 mm × ~53 mm | [PP] 80 mm × 54 mm (excluding the toggle switch) | Same board, rounding; quote "about 80 × 54 mm" |
| VBATT analog pins | [UM] back-of-board silkscreen: six pads A0–A5 | [PP] "A0 - A6 (connection pads at the bottom of PCB)" | [UM] wins: A0–A5 (an UNO has no A6 on the header) |

## Needs verification
- Battery connector family/pitch (photos show a 2-pin "BATT" plug-in connector; JST-PH or other not stated) and whether the shield works with other capacities (Tindie: "any Li-ion or LiPo cell of the 3.7/4.2V type"; UM names only 1300 mAh).
- Whether USB charging also powers the Arduino (pass-through) while the switch is on.
- Output current: manual (≥ 500 mA continuous, 1 A peak) vs product page (1000 mA continuous, 700 mA at start-up, ~1100 mA cut-off) — ask the design team which applies to the current board.
- That the VBATT pads connect the battery straight to the analog pin with no divider — inferred from the manual's `5.0/1023.0` formula, not stated; confirm with [DT].
- Boost converter and charger IC part numbers.

## Sources
- [PP] Product page (read by coordinator 2026-10-16) — https://my.cytron.io/p-lipo-power-shield
- [3P] (cross-check only) Cytron Tindie listing — https://tindie.com/products/cytron/lipo-power-shield
