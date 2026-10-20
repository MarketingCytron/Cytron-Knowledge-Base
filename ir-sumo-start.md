# IR Sumo Start — Verified Reference

| Field | Value |
|---|---|
| Product code | IR-SUMO-START [DS] |
| Family | Cytron sumo robot controllers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read for the first time. Price, packing list (no remote), size/weight and the setup steps are now Cytron-stated |
| Primary source | IR-SUMO-START Datasheet, Rev 1.0, April 2025 (Cytron Technologies Sdn Bhd) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A small infrared receiver module that gives a sumo robot a START/STOP signal from an IR remote. It receives IR commands from a remote/transmitter and turns them into one digital output (S): LOW in READY and STOP, HIGH in RUN [DS]. The user binds any three buttons of an IR remote to READY, RUN and STOP using the onboard bind button [DS]. Cytron's PIRC 2025 briefing describes it as a module that gives START/STOP to an autonomous sumo robot through a TV remote (IR signal) .

It is an accessory, not a robot controller: it does not drive motors itself. The robot's own controller must read S and start/stop the motors in code [DS].

## Specifications
Datasheet Table 2 is titled "Absolute Maximum Ratings" — every row below is from it unless marked.

| Item | Value | Src |
|---|---|---|
| Power input voltage (+) | Min 3.0 V, Max 5.5 V | [DS] |
| Output signal voltage (S), power input (+) = 5V | Min 0 V, Max 5 V | [DS] |
| Output signal voltage (S), power input (+) = 3.3V | Min 0 V, Max 3.3 V | [DS] |
| Output signal current, power input (+) = 5V | Max 2.27 mA (no Min given, "-") | [DS] |
| Output signal current, power input (+) = 3.3V | Max 1.50 mA (no Min given, "-") | [DS] |
| Note on output voltage | "The output signal voltage (S) is equal to the power input voltage supplied. Do not exceed the maximum power input voltage limit." | [DS] |
| Power input (connector text) | "Power input, compatible with 3V3 and 5V"; Figure 1 label: "POWER INPUT 3.3V OR 5V" | [DS] |
| Output type | "Output signal (0 or 1 Logic). The output voltage for HIGH logic is equal to power input voltage. (Vs = Vin)" | [DS] |
| IR receiver | Infrared receiver with built-in 38kHz bandpass filter | [DS] |
| Indicator | 1 × RGB LED (state/mode indicator) | [DS] |
| Button | 1 × bind button (push button; press and hold to enter bind mode) | [DS] |
| Mounting | 1 × breakout mounting hole, Ø3.0 mm, "for optional mounting" | [DS] |
| Dimensions (Figure 2, top view, mm) | Width 14.0; board body height 21.0; mounting-hole tab 5.4 above body; 23.3 from mounting-hole centre to bottom board edge; header pins extend ~6.0 beyond board edge | [DS] |
| 3D CAD | Google Drive folder linked from datasheet | [DS] |
| Supply current, operating temperature, IR range/angle, weight, pin pitch | Not stated | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** compact IR start module for sumo competitions; wireless start/stop from an IR remote for fair synchronised starts; pin assignment **S = signal, + = Vin, 0 = ground**; place it away from other IR sensors, easily accessible and at a good angle to receive the signal [PP].
- **Features:** works at 5 V and 3.3 V (SUMO:BIT, URC10, Arduino, Atmel-based systems); **32.4 × 14 × 10 mm, 2 g**; RGB LEDs; learns codes from most IR remotes [PP].
- **Setup (page text):** connect S to any digital pin; hold the white button 1 s to enter recording mode (RGB LEDs blink slowly 3 times); "press three different buttons on your IR remote to assign 'Release', 'Ready', 'Start', and 'Stop' functions respectively" with LED confirmation; then it is ready [PP]. The page names four functions but three buttons — see *Conflicts*.
- **Packing list:** 1x IR Sumo Start Module, 1x GVS female-to-female extension 10 cm, 1x 3D-printed case [PP]. **No IR remote is included.**
- **Resources:** datasheet (Google Doc), PIRC 2025 briefing slides (Bahasa Melayu), 3D CAD [PP]. Binding/receiving-mode, layout and dimension images on the page — not read.

## Interfaces, terminals and pin mapping
3-pin male header on the bottom edge. Silkscreen and Figure 1 order, left to right (top view, mounting hole up) [DS]:

| Pin (silkscreen) | Figure 1 label | Function | Src |
|---|---|---|---|
| − | GND | Ground (GND) | [DS] |
| + | POWER INPUT 3.3V OR 5V | Power input, 3.0–5.5 V | [DS] |
| S | OUT | Output signal: LOW = READY / STOP / power-up; HIGH = RUN; HIGH level = Vin | [DS] |

Note the **power pin is the middle pin**, GND is on one side and S on the other [DS]. The PIRC deck photos show the module connected with a 3-wire (black/red/white) female-female jumper cable .

### States and LED meanings
| State | How entered | LED | S output | Src |
|---|---|---|---|---|
| Power-up (on start) | Power applied | GREEN for 1 second, then off; module is then in Receive Mode | LOW | [DS] |
| READY | Bound READY button (button 1 in the datasheet example) | Blinks PINK fast (figure: 3×), then solid BLUE | LOW (stays LOW) | [DS] |
| RUN | Bound RUN button (button 2) | Solid GREEN | HIGH — "This should trigger the sumo robot to start." | [DS] |
| STOP | Bound STOP button (button 3) | Blinks RED slowly, indefinitely | LOW — "This should stop the robot immediately." | [DS] |
| Bind mode entered | Hold bind button > 1 second | Blinks BLUE, GREEN, RED (100ms each colour) three times, then off | Not stated | [DS] |
| Bind success | Remote button pressed in bind mode | Blinks BLUE / GREEN / RED three times (for READY / RUN / STOP), then off | Not stated | [DS] |

### Bind procedure [DS]
1. Press and hold the bind button for more than 1 second.
2. LED blinks BLUE → GREEN → RED (100ms each) three times, then turns off: module is in Bind Mode.
3. Press button 1 of the IR remote → set as READY (LED blinks BLUE 3×, then off).
4. Press button 2 → set as RUN (LED blinks GREEN 3×, then off).
5. Press button 3 → set as STOP (LED blinks RED 3×, then off). The module then returns automatically to Receive Mode.

## Rules and gotchas (for code, wiring and tutorials)
- **S is active HIGH for RUN.** HIGH = RUN, LOW = READY, STOP and power-up [DS]. Do not describe it as "active low" (a [3P] page does — wrong, see Conflicts).
- **READY does not start the robot.** READY keeps S LOW; only RUN drives S HIGH [DS].
- **STOP latches.** After STOP the LED blinks red indefinitely and "The module needs to be manually reset to be used again for the next round" [DS]. How to reset is not stated (no reset button is shown on the board) — see Needs verification.
- **HIGH level equals the supply voltage** (Vs = Vin) [DS]. Power the module from the same logic voltage as the controller's input pin (3.3V board → 3.3V; 5V board → 5V) so S never exceeds the input's limit. Never feed it above 5.5 V [DS].
- **It works with "any IR remote"** — the module learns three buttons; there is no fixed remote [DS]. Bind the remote before a match; the datasheet does not state whether bindings survive power-off.

## Power and electrical limits
- Supply: 3.0–5.5 V on "+" [DS]. Absolute maximum — "Do not exceed the maximum power input voltage limit" [DS].
- S output HIGH = Vin: 0–5 V at 5V supply, 0–3.3 V at 3.3V supply [DS].
- S output current: max 2.27 mA at 5V, max 1.50 mA at 3.3V [DS]. S is a logic signal only — do not drive LEDs, relays, buzzers or motors from it.
- Supply current: not stated [DS]. Reverse-polarity protection: not stated [DS] — do not claim it.

## Software support
- No library or firmware update path is stated [DS]. The module is read as a plain digital input from any language.
- MicroPython / CircuitPython / MakeCode examples: not stated.

## Compatibility and accessories
- Datasheet names no specific controller; it says S "should trigger the sumo robot to start" [DS].
- Remote: any IR remote (e.g. TV remote) [DS]. Whether a remote is included: not stated.
- Mounting: Ø3.0 mm hole; competition robots in the PIRC deck use 3D-printed holders [DS].

## Common mistakes / troubleshooting
- Robot starts on READY → code treats any IR activity as start; only HIGH (RUN) should start it [DS].
- Robot never starts → remote not bound (do the bind procedure), wrong button pressed, S not wired, or code expects LOW for start [DS].
- Robot won't run again after STOP → expected; STOP latches until the module is manually reset [DS].
- Bind mode not entered → button must be held more than 1 second until the LED flashes BLUE/GREEN/RED [DS].
- Powered at 5V into a 3.3V-only input → S HIGH = 5 V; power the module at 3.3V instead [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supply voltage | [DS] 3.0–5.5 V; "compatible with 3V3 and 5V" |  URC10 integration notes: "Do not use 3.3V — module requires 5V" | [DS] wins: 3.3V and 5V both valid. The notes may be a URC10 wiring preference, not a module limit |
| Output when IR signal is lost | [DS] states S LOW only at power-up, READY and STOP; RUN is a held state.  PIRC: noise → "no change" |  URC10 notes: "When there is no signal (or signal is lost), the output goes LOW" (fail-safe) | [DS] wins; no source above  says loss of signal returns S to LOW. Do not claim a signal-loss fail-safe |
| Output logic | [DS] HIGH = RUN; LOW = READY/STOP | [3P] Cirkit Designer: "Digital Output (Active Low)… goes LOW when an IR signal is detected" | [DS] wins; [3P] rejected |
| Supply voltage | [DS] 3.0–5.5 V | [3P] Cirkit Designer: "5V DC", "requires a 5V power supply" | [DS] wins |
| Dimensions | [DS] 14.0 mm wide, body 21.0 mm + 5.4 mm tab | [3P] Cirkit Designer: "30mm x 20mm x 10mm" | [DS] wins; [3P] rejected |
| Pin order | [DS] −, +, S (power in middle) | [3P] Cirkit Designer: Pin 1 VCC, Pin 2 GND, Pin 3 OUT | [DS] wins |
| Size | [DS] Figure 2: 14.0 mm wide, body 21.0 mm + 5.4 mm tab | [PP]: 32.4 × 14 × 10 mm, 2 g | Probably with the header/case; quote [DS] board size and [PP] overall size, labelled |

## Needs verification
- How to "manually reset" after STOP (power cycle? re-press READY?) — not stated [DS].
- Whether bound IR commands are kept after power-off — not stated.
- Whether RUN works directly from power-up without READY first — not stated.
- IR protocols supported (NEC, Sony, RC5, …) — datasheet says only "any IR remote" with a 38kHz filter.
- Supply current, operating temperature, header pin pitch, weight, reverse-polarity protection — not stated.
- Output stage: max current scales with Vin (2.27 mA at 5V, 1.50 mA at 3.3V, both ≈ Vin / 2.2 kΩ) — suggests a series resistor; not stated as such. Affects use with an input that has its own pull-up (e.g. Maker Mini Sumo D2) — confirm with design team [DT].
- PIRC sample uses pin 9 with `MakerSumo.begin()`; the Maker Mini Sumo KB lists D9 as the RC servo port and says `begin()` attaches the Servo library to D9. Confirm the intended port and that the Servo attach does not disturb reading S on D9 [DT].
- Factory-default bindings out of the box (the page shows a recording procedure; no remote is included).
- Recording step: the page says three remote buttons for four functions (Release, Ready, Start, Stop) — confirm against the datasheet bind procedure.

## Sources
- [DS] IR-SUMO-START Datasheet, Rev 1.0, April 2025 — (Cytron document — link not public) (same content as local file `IR-SUMO-START Datasheet.pdf`, AI Coding Pack URC10 `source-docs/`; 11 pages, read with figures)
- [DS] 3D CAD files (linked from datasheet) — https://drive.google.com/drive/u/0/folders/1xJxgIxndtl9YiDp0-MGCC9LyuWsXz6Or (not opened)
- [DS of related product] Maker Mini Sumo KB (`kb/maker-mini-sumo.md`) for D2/D9 port facts
- [PP] https://my.cytron.io/p-ir-sumo-start-module — product page not read (blocked)
- [3P] (cross-check only, rejected) https://docs.cirkitdesigner.com/component/289bfe0d-bed6-4199-bd50-dad44f3dc685/cytron-ir-start-module
