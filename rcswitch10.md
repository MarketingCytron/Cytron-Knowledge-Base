# RCSwitch10 - RC controlled Relay Switch — Verified Reference

| Field | Value |
|---|---|
| Product code | RCS10A [PP] |
| Family | Servo and RC controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Primary source | Cytron product page "RCSwitch10 - RC controlled Relay Switch" (https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch), read by the coordinator 2026-10-19 [PP]. No Cytron datasheet or user manual could be found or read: the page's "RCSwitch10 Connection Diagram" Drive link (file 0BzFWfMiqqjyqMkI4cURDZ3lUbGs) returns "not found"; Drive full-text/title searches for RCSwitch10, RCS10A and "RC Switch" found nothing; web searches found only reseller pages. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: every fact without another tag comes from the coordinator's read of the product page on 2026-10-19 [PP]. [3P] = reseller pages (robu.in, RobotShop, The Pi Hut), cross-check only.

## What it is
"RCSwitch10 is an RC controlled relay switch. It can be turned on and off by using an RC controller." [PP] It is a single relay (single pole, double throw) that a hobby RC transmitter/receiver switches on and off, so an RC model can switch a separate load [PP].

## Specifications
The product page specification list has four rows; all are reproduced here.

| Item | Value | Src |
|---|---|---|
| Relay type | Single pole, double throw | [PP] |
| Max voltage | 250VAC, 30VDC | [PP] |
| Max current | 10A | [PP] |
| Dimension | 43.4mm x 38.3mm x 17.4mm | [PP] |
| Product code | RCS10A | [PP] |
| Warranty | 12 months | [PP] |
| RC signal input (pulse widths, on/off threshold, failsafe) | Not stated | [PP] |
| Board supply voltage / current, trigger voltage, LED indicators, weight, operating temperature | Not stated | [PP] |
| Cable / connector supplied | Not stated | [PP] |

## Interfaces, terminals and pin mapping
- **RC input:** the relay "can be turned on and off by using an RC controller" [PP]. The page does not name the input connector, its pin order, which receiver channel type it expects, or how it is powered. Do not describe a 3-pin servo lead, a pin order or a channel requirement as Cytron fact (see Needs verification).
- **Relay output:** one SPDT contact set (common, normally open, normally closed is what "single pole, double throw" means) [PP]. Terminal type and terminal labels are not stated in text.
- **Connection diagram:** the product page lists an "RCSwitch10 Connection Diagram" resource, but its Drive link returns "not found", so no wiring fact could be taken from it. A reseller (The Pi Hut) shows a wiring-diagram image; it could not be downloaded or read here [3P].

## Rules and gotchas (for code, wiring and tutorials)
- No code runs on the user side: the switch is driven by an RC transmitter/receiver, not by a microcontroller sketch [PP]. Cytron does not state whether a microcontroller servo-style pulse can drive it — do not claim Arduino control as a documented use.
- **Do not state the switching threshold** (stick position, pulse width in µs) or **failsafe behaviour** (what the relay does when signal is lost). Neither is published by Cytron. For RC combat weapons this matters for safety — tell readers to bench-test with the load disconnected and to check behaviour with the transmitter switched off.
- Quote the contact ratings exactly as "250VAC, 30VDC" and "10A" [PP]. The page does not split the 10A by AC/DC or by resistive/inductive load; do not add derating figures.
- For mains-voltage loads ("domestic appliances and home automation" is a listed example application [PP]), tutorials must carry a mains-safety warning and an enclosure; the board's isolation/creepage is not stated.
- Size is 43.4mm x 38.3mm x 17.4mm [PP] — use this, not reseller figures.

## Power and electrical limits
- Relay contacts: max 250VAC or 30VDC, max 10A [PP].
- Logic/receiver-side supply voltage and current draw: not stated [PP]. A reseller states "Trigger Voltage: 5VDC" and 20 mA trigger current [3P] — Needs verification.
- No fuse, flyback/snubber, or reverse-polarity protection is mentioned [PP] — do not claim them.

## Software support
- None. Operated directly by an RC controller [PP]. No library, firmware update or configuration procedure is documented.
- The product page links a Fritzing folder (Fritzing part) [PP]; it was not opened.

## Compatibility and accessories
- Example applications listed by Cytron [PP]:
  - Powerful auxiliary weapons in RC combat tournament
  - Glow plugs on nitro RC vehicles
  - High powered lighting system on RC aircraft, boats and cars
  - Domestic appliances and home automation
  - Non-critical automotive electrics like glow wire
- Which RC receivers/transmitters are compatible (PWM channel, 2-position switch channel, voltage) is not stated [PP].
- Package contents are not stated on the page as read [PP]. A reseller lists "1 x Connecting 3 point cable with Connector (30 cm)" [3P] — Needs verification.
- Related Cytron RC products in the KB (different products, do not merge facts): MDDRC5 / MDDRC10 RC motor drivers, SC08A servo controller.

## Common mistakes / troubleshooting
- Relay never switches → no Cytron troubleshooting text exists; general RC practice is to check the receiver channel, the transmitter switch/stick assignment and that the receiver is powered (the RCSwitch10's own input and supply arrangement is not stated — see Needs verification).
- Load not switching off when expected → check whether the load is wired to the normally-open or normally-closed contact (SPDT) [PP].
- Overloaded contacts → stay within 10A and 250VAC / 30VDC [PP]; high-inrush loads (glow plugs, lamps, motors) are not rated separately by Cytron.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Dimensions | [PP] 43.4mm x 38.3mm x 17.4mm | [3P] robu.in: length 44 mm, width 39 mm, height 19 mm, weight 20 g | [PP] wins; [3P] figures not used |
| Max voltage/current wording | [PP] "250VAC, 30VDC", "10A" | [3P] robu.in: "250VAC@10A; 30VDC@10A" | Consistent; quote the [PP] wording |

## Needs verification
- RC input signal: pulse width range, switching threshold, hysteresis, and failsafe/no-signal behaviour — not stated by any Cytron source.
- Input connector type and pin order (3-pin servo-style lead implied only by [3P] "Connecting 3 point cable with Connector (30 cm)").
- Supply for the relay coil/logic: [3P] robu.in states "Trigger Voltage: 5VDC", "Trigger Current (mA)" 20, "No. of Channels" 1 — confirm with Cytron [DT].
- Package contents (cable included?) — [3P] only.
- Status LED presence and meaning — not stated.
- Relay terminal type (screw terminal or solder pads) and labels — not stated in text.
- Whether a microcontroller servo signal (e.g. Arduino Servo library) can trigger it — not stated.
- Weight (20 g per [3P]) and operating temperature — not stated by Cytron.
- The connection diagram: a working link to the Cytron "RCSwitch10 Connection Diagram" is needed.

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM40.95, availability 159, warranty 12 months, description, example applications, 4-row specification list) — https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch
- [3P] (cross-check only) robu.in "Battle Switch (RCSwitch10)" — https://st.robu.in/?p=4706
- [3P] (cross-check only) RobotShop "Cytron 10A Radio Controlled Relay Switch", Manufacturer # RCS10A, SKU RB-Cyt-167 — https://www.robotshop.com/products/cytron-10a-radio-controlled-relay-switch
- [3P] (cross-check only) The Pi Hut "RCSwitch10 - RC Controlled Relay Switch" — https://thepihut.com/products/rcswitch10-rc-controlled-relay-switch
