# RCSwitch10 - RC controlled Relay Switch — Verified Reference

| Field | Value |
|---|---|
| Product code | RCS10A [PP] |
| Family | Servo and RC controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Primary source | No datasheet exists. **"RCSwitch10 Connection Diagram"** (Cytron; one-page drawing of the board, terminals, a Futaba receiver/transmitter and a motor), supplied by the Cytron marketing team on 2026-10-20 [UM] — the same document the product page links, whose Drive link returns "not found". Plus the Cytron product page https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch [PP] |

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
| RC signal → relay | "Switch is ON (RC Signal < 1.2ms)": COM connects to NO. "Switch is OFF (RC Signal > 1.8ms)": COM connects to NC | [UM] |
| 1.2–1.8 ms | "Switch state is undetermined when the RC signal is between 1.2ms - 1.8ms. Thus, do not connect the RCSwitch10 to the gimbal stick channel." | [UM] |
| No signal | "Switch is OFF when no RC signal is received" | [UM] |
| Indicators | Power LED DS1 — "Indicate the RCSwitch10 is powered up"; Switch LED DS2 — "Indicate the switch is ON" | [UM] |
| Supply | **4V–6V** from the RC receiver into the +5V and GND terminals of RC IN (the board is powered from the receiver lead) | [UM] |
| Relay | SONGLE SRD-05VDC-SL-C (5 V coil); contact ratings printed on the relay: 10A 250VAC, 10A 125VAC, 10A 30VDC, 10A 28VDC | [UM: photo] |
| Terminals | Two 3-way screw terminals: **OUT** (JP2) = NO, COM, NC; **RC IN** (JP3) = signal, +5V, GND | [UM] |
| Board marking | "RCSwitch10", "RCS10A", Cytron, www.cytron.com.my | [UM: photo] |
| Board supply current, weight, operating temperature | Not stated | [PP][UM] |
| Cable / connector supplied | Not stated | [PP] |

## Interfaces, terminals and pin mapping
| Terminal | Pin (top → bottom as drawn) | Connect to | Src |
|---|---|---|---|
| RC IN (JP3, 3-way screw terminal) | signal (pulse symbol) | receiver channel signal pin | [UM] |
| | +5V | receiver + (the receiver supply, 4V–6V) | [UM] |
| | GND | receiver − / GND | [UM] |
| OUT (JP2, 3-way screw terminal) | NO | in the example, Motor Battery − | [UM] |
| | COM | in the example, one motor lead (the other motor lead goes to Motor Battery +) | [UM] |
| | NC | not used in the example | [UM] |

- **Receiver channel:** "This is for reference only. Please connect to the preferred channel accordingly." The example uses a Futaba R2006GS 6-channel 2.4 GHz receiver with a Futaba transmitter [UM].
- **Switching:** ON (COM–NO) below 1.2 ms; OFF (COM–NC) above 1.8 ms; OFF when no RC signal; **undetermined between 1.2 and 1.8 ms** [UM].
- **LEDs:** DS1 Power = powered up; DS2 Switch = switch ON [UM].
- **Relay output:** one SPDT contact set [PP] on a SONGLE SRD-05VDC-SL-C relay [UM: photo].

## Rules and gotchas (for code, wiring and tutorials)
- **Use a 2-position switch channel, never a gimbal (stick) channel** — Cytron's diagram says the state is undetermined between 1.2 and 1.8 ms "Thus, do not connect the RCSwitch10 to the gimbal stick channel" [UM].
- **Load goes on COM + NO** for "ON when switched" (the diagram's motor example), or on COM + NC for "ON when the switch is OFF" [UM].
- **The board is powered from the receiver:** connect signal, +5V and GND of RC IN to the receiver channel; supply 4V–6V [UM]. The Power LED lights when it is powered [UM].
- **Signal loss:** "Switch is OFF when no RC signal is received" [UM]. A receiver whose failsafe keeps sending pulses is still a signal — set the receiver failsafe to the OFF position for that channel, and bench-test with the transmitter switched off (general RC practice).
- No code runs on the user side; it is driven by an RC receiver [PP]. Cytron does not state that a microcontroller servo pulse can drive it — do not claim Arduino control as a documented use.
- Quote contact ratings as "250VAC, 30VDC" and "10A" [PP]; the relay body also prints 10A at 125VAC and 28VDC [UM: photo]. No derating for inductive or high-inrush loads is given.
- For mains-voltage loads ("domestic appliances and home automation" [PP]), tutorials must carry a mains-safety warning and an enclosure; the board's isolation/creepage is not stated.
- Size is 43.4mm x 38.3mm x 17.4mm [PP] — use this, not reseller figures.

## Power and electrical limits
- Relay contacts: max 250VAC or 30VDC, max 10A [PP]; relay SONGLE SRD-05VDC-SL-C [UM: photo].
- Board supply: 4V–6V from the receiver into RC IN +5V/GND [UM]. Current draw: not stated (a reseller gives 20 mA trigger current [3P] — not used).
- No fuse, flyback/snubber or reverse-polarity protection is mentioned [PP][UM] — do not claim them.

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
- **Relay never switches** → check the Power LED (no LED = no 4V–6V on RC IN) [UM]; then check the channel: the pulse must go below 1.2 ms for ON and above 1.8 ms for OFF [UM]. A channel with reduced end points never reaches them — use a 2-position switch channel at full travel. Reverse the channel in the transmitter if ON/OFF is the wrong way round (general RC practice).
- **Relay chatters or behaves randomly** → it is on a stick channel or a pulse inside 1.2–1.8 ms, where the state is undetermined [UM].
- **Switch LED on but load dead** → the load must be on COM + NO [UM].
- **Wires in the wrong RC IN slot** → order is signal, +5V, GND [UM].
- **Overloaded contacts** → stay within 10A and 250VAC / 30VDC [PP]; high-inrush loads (glow plugs, lamps, motors) are not rated separately by Cytron.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Dimensions | [PP] 43.4mm x 38.3mm x 17.4mm | [3P] robu.in: length 44 mm, width 39 mm, height 19 mm, weight 20 g | [PP] wins; [3P] figures not used |
| Max voltage/current wording | [PP] "250VAC, 30VDC", "10A" | [UM: photo] relay body: 10A 250VAC, 10A 125VAC, 10A 30VDC, 10A 28VDC | Consistent; quote the [PP] wording |
| Price | [PP] RM40.95, in stock | [VEN] Synacorp RM52.20, out of stock | Different seller; quote Cytron's page |

## Needs verification
- Board supply current (receiver load) — not stated by Cytron.
- Package contents (is a cable included?) — [3P] robu.in lists "1 x Connecting 3 point cable with Connector (30 cm)"; Cytron does not say. With screw terminals on RC IN, a servo-style connector is not needed on the board side.
- Whether a microcontroller servo signal (e.g. Arduino Servo library at 5 V) can drive RC IN — not stated.
- Weight (20 g per [3P]) and operating temperature — not stated by Cytron.

## Sources
- [PP] Cytron product page, read by the coordinator 2026-10-19 (price RM40.95, availability 159, warranty 12 months, description, example applications, 4-row specification list) — https://my.cytron.io/p-rcswitch10-rc-controlled-relay-switch
- [UM] "RCSwitch10 Connection Diagram" (Cytron), supplied by the Cytron marketing team 2026-10-20; copy in the team folder reference/RCSwitch10-Connection-Diagram.png. The product page's Drive link to it returns "not found".
- [VEN] Synacorp RCS10A page and its "Connection Diagram" attachment (text extraction, 2026-10-19): https://synacorp.my/v3/en/drivers/1492-rcs10a-rc-switch10.html
- [3P] (cross-check only) robu.in "Battle Switch (RCSwitch10)" — https://st.robu.in/?p=4706
- [3P] (cross-check only) RobotShop "Cytron 10A Radio Controlled Relay Switch", Manufacturer # RCS10A, SKU RB-Cyt-167 — https://www.robotshop.com/products/cytron-10a-radio-controlled-relay-switch
- [3P] (cross-check only) The Pi Hut "RCSwitch10 - RC Controlled Relay Switch" — https://thepihut.com/products/rcswitch10-rc-controlled-relay-switch
