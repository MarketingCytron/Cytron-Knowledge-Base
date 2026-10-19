# RCSwitch10 - RC controlled Relay Switch — Verified Reference

| Field | Value |
|---|---|
| Product code | RCS10A [PP] |
| Family | Servo and RC controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


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
| RC signal → relay | Switch ON when the RC signal is below 1.2 ms; switch OFF when it is above 1.8 ms | [VEN] |
| No signal | "Switch is OFF when no RC signal is received" | [VEN] |
| Indicators | Power LED (RCSwitch10 is powered up); Switch LED (the switch is ON) | [VEN] |
| Supply | Diagram text shows "4V-6V" and "GND" next to the RC side; which pin it labels is not readable from the text (see Needs verification) | [VEN] |
| Board supply current, weight, operating temperature | Not stated | [PP][VEN] |
| Cable / connector supplied | Not stated | [PP] |

## Interfaces, terminals and pin mapping
- **RC input:** the relay "can be turned on and off by using an RC controller" [PP]. The connection diagram connects it to a receiver channel — "Please connect to the preferred channel accordingly" — and the text carries "4V-6V" and "GND" labels on that side [VEN]. The connector type and pin order are not readable from the text; do not describe a 3-pin servo lead or a pin order as Cytron fact (see Needs verification).
- **Switching:** ON below 1.2 ms, OFF above 1.8 ms; OFF when no RC signal is received [VEN]. Behaviour between 1.2 ms and 1.8 ms is not stated.
- **LEDs:** Power LED = powered up; Switch LED = switch ON [VEN].
- **Relay output:** one SPDT contact set (common, normally open, normally closed is what "single pole, double throw" means) [PP]. Terminal type and terminal labels are not stated in text.

## Rules and gotchas (for code, wiring and tutorials)
- No code runs on the user side: the switch is driven by an RC transmitter/receiver, not by a microcontroller sketch [PP]. Cytron does not state whether a microcontroller servo-style pulse can drive it — do not claim Arduino control as a documented use.
- **Switching threshold and signal loss:** quote them as the connection diagram gives them — ON below 1.2 ms, OFF above 1.8 ms, OFF when no RC signal is received [VEN] — and say they come from the connection diagram. Do not give a value for 1.2–1.8 ms (not stated), and do not claim a receiver's own failsafe output turns it off: a receiver that keeps sending pulses on signal loss is still a "signal". For RC combat weapons tell readers to bench-test with the load disconnected and to check behaviour with the transmitter switched off.
- A standard RC pulse is roughly 1.0–2.0 ms, so on a stick channel the relay switches near the two ends of travel; a 2-position switch channel is the simpler choice (general RC practice, not a Cytron statement).
- Quote the contact ratings exactly as "250VAC, 30VDC" and "10A" [PP]. The page does not split the 10A by AC/DC or by resistive/inductive load; do not add derating figures.
- For mains-voltage loads ("domestic appliances and home automation" is a listed example application [PP]), tutorials must carry a mains-safety warning and an enclosure; the board's isolation/creepage is not stated.
- Size is 43.4mm x 38.3mm x 17.4mm [PP] — use this, not reseller figures.

## Power and electrical limits
- Relay contacts: max 250VAC or 30VDC, max 10A [PP].
- RC-side supply: the diagram text shows "4V-6V" beside "GND" [VEN] — consistent with a normal receiver supply, but the text does not say which pin or whether the board takes power from the receiver lead. Current draw: not stated. A reseller states "Trigger Voltage: 5VDC" and 20 mA trigger current [3P] — Needs verification.
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
- Relay never switches → check the Power LED first (no LED = no supply on the RC side) [VEN]; then check the channel: the pulse must go below 1.2 ms to switch ON and above 1.8 ms to switch OFF [VEN], so a channel trimmed or end-point-limited inside that band never switches. Reverse the channel in the transmitter if ON/OFF is the wrong way round (general RC practice).
- Switch LED on but load dead → check the load is on COM + NO, not NC [VEN][PP].
- Load not switching off when expected → check whether the load is wired to the normally-open or normally-closed contact (SPDT) [PP].
- Overloaded contacts → stay within 10A and 250VAC / 30VDC [PP]; high-inrush loads (glow plugs, lamps, motors) are not rated separately by Cytron.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Dimensions | [PP] 43.4mm x 38.3mm x 17.4mm | [3P] robu.in: length 44 mm, width 39 mm, height 19 mm, weight 20 g | [PP] wins; [3P] figures not used |
| Max voltage/current wording | [PP] "250VAC, 30VDC", "10A" | [3P] robu.in: "250VAC@10A; 30VDC@10A" | Consistent; quote the [PP] wording |
| Price | [PP] RM40.95, in stock | [VEN] Synacorp RM52.20, out of stock | Different seller; quote Cytron's page |

## Needs verification
- Behaviour between 1.2 ms and 1.8 ms (hold last state? hysteresis?) — not stated.
- What "4V-6V" labels in the diagram (receiver supply into the board, or a range for the RC lead) and the board's current draw; [3P] robu.in states "Trigger Voltage: 5VDC", "Trigger Current (mA)" 20 [DT].
- Input connector type and pin order (3-pin servo-style lead implied only by [3P] "Connecting 3 point cable with Connector (30 cm)").
- Package contents (cable included?) — [3P] only.
- Relay terminal type (screw terminal or solder pads) and labels — not stated in text.
- Whether a microcontroller servo signal (e.g. Arduino Servo library) can trigger it — not stated.
- Weight (20 g per [3P]) and operating temperature — not stated by Cytron.

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM40.95, availability 159, warranty 12 months, description, example applications, 4-row specification list) — https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch
- [VEN] Synacorp RCS10A page and its "Connection Diagram" attachment (text extraction, 2026-10-19): https://synacorp.my/v3/en/drivers/1492-rcs10a-rc-switch10.html
- [3P] (cross-check only) robu.in "Battle Switch (RCSwitch10)" — https://st.robu.in/?p=4706
- [3P] (cross-check only) RobotShop "Cytron 10A Radio Controlled Relay Switch", Manufacturer # RCS10A, SKU RB-Cyt-167 — https://www.robotshop.com/products/cytron-10a-radio-controlled-relay-switch
- [3P] (cross-check only) The Pi Hut "RCSwitch10 - RC Controlled Relay Switch" — https://thepihut.com/products/rcswitch10-rc-controlled-relay-switch
