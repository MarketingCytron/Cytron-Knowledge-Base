# Cytron PS2 Shield — Verified Reference

| | |
|---|---|
| Product code | `SHIELD-PS2` [PP]; user manual header "Shield-PS2" / "Cytron PS2 Shield" [UM] |
| Family | Arduino shields |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 3): live my.cytron.io product page read (description, features, packing list, resources). Page agrees with the manual and library (A1 reset, UART, wired/wireless controllers) and adds the board size |
| Primary source | **No datasheet exists.** Primary = "Shield-PS2 — Cytron PS2 Shield — User's Manual", **V1.0, September 2013** (public Google Doc linked from the product page) [UM] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
An Arduino-form-factor shield that converts a SONY PS2 (DualShock) controller, wired or wireless, into a simple UART protocol: the Arduino sends a one-byte command and the shield answers with the button or joystick state [UM]. It is powered from the Arduino main board (5 V), has stackable headers, jumper-selectable UART pins and baud rate, and can drive the controller's vibration motors [UM]. The PS2 controller is not included [UM].

## Specifications
Section 3.0 "Product Specification and Limitations" [UM]:

| Item | Value | Src |
|---|---|---|
| Input voltage (logic operation voltage) | Min 4.5 V, Max 5.5 V | [UM] |
| Current consumption | Min 100 mA, Typ 150 mA, Max 500 mA | [UM] |
| VIOH (logic input, high level) | Min 3.5 V, Typ 5.0 V, Max 5.5 V | [UM] |
| VIOL (logic input, low level) | Min 0 V, Typ 0 V, Max 1.0 V | [UM] |
| Power source | "powered from Arduino main board"; "5V powered, low current consumption" | [UM] |
| Logic level | 5 V (VIOH 3.5–5.5 V) | [UM] |
| UART baud rates (jumper) | 4800, 9600, 57600, 115200 | [UM] |
| UART RX pin options (jumper) | D0, D2, D8, D10 (default D2) | [UM] |
| UART TX pin options (jumper) | D1, D3, D9, D11 (default D3) | [UM] |
| Shield reset line | Arduino A1 — pull low to reset the shield | [UM] |
| Controllers supported | SONY PS2 controller, wired or wireless; "automatically operate in analog mode" | [UM] |
| Vibration motors | Controllable (motor 1 on/off, motor 2 speed 0–255) | [UM] |
| LEDs | Status LED (orange), Power LED (green) | [UM] |
| Buttons | Main board reset button; PS2 RST button (resets the shield only) | [UM] |
| Headers | Stackable analog, power and digital I/O headers (JP4, JP7) | [UM] |
| Packing list | 1 x Shield-PS2, 3 x mini jumper | [UM] |
| Warranty | 12 months | [UM][PP] |
| Dimensions | 68 mm × 53 mm | [PP] |
| Onboard MCU / PS2 interface chip | **Not stated** | [UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Description:** works with Arduino UNO, Duemilanove, Mega, Leonardo and pin-compatible boards; powered from the Arduino; wired or wireless PS2 controller; stackable headers; hardware or software UART; shield reset on **A1** (pull low to reset); PS2 controller not included [PP].
- **Features list:** 5 V powered, low current; simple UART protocol; controllable vibration motor; controller automatically in analog mode; status LED; baud-rate jumper **9600 / 57600 / 115200**; jumpers to choose the TX and RX pins; **dimension 68 mm × 53 mm** [PP].
- No packing-list tab on the page [PP].
- **Resources:** User's Manual V1.0 Sept 2013 (Google Doc), Arduino library and wiki branch (GitHub), Fritzing files; tutorials: PS2 shield + G15 wheel, Arduino + PS2 shield + MDDS10 robot, Arduino Edubot, "SoftwareSerial Conflicting with Servo Interrupt" [PP].

## Interfaces, terminals and pin mapping
| Function | Arduino pin(s) / terminal | Src |
|---|---|---|
| UART RX (shield → selected Arduino pin) | Jumper: D0, D2, D8 or D10. D0 is hardware serial; "recommended to move the RX pin selector to D2, D8 or D10 as D0 is used for bootloader" on UNO/Mega | [UM] |
| UART TX (Arduino → shield) | Jumper: D1, D3, D9 or D11. D1 is hardware serial; recommended D3, D9 or D11 on UNO/Mega | [UM] |
| Default jumper position | TX = D3, RX = D2 (software serial) | [UM] |
| Baud rate selector | Jumper: 4800 / 9600 / 57600 / 115200; the shield must be **reset** after moving the jumper for the new baud rate to take effect | [UM] |
| Shield reset | A1 — "User can pull down this analog pin to reset the shield"; library drives A1 HIGH in `begin()` and LOW in `reset(1)` | [UM][GH] |
| PS2 connector socket | Standard SONY PS2 controller plug, wired or wireless receiver; no modification needed | [UM] |
| Status LED (orange) | Blinking with varying brightness = no controller detected; steady low brightness = controller detected and communicating; steady high brightness = a digital button is pressed | [UM] |
| Power LED (green) | On when the shield is powered | [UM] |
| Main board reset button | Resets the Arduino; "Arduino main board will require around 30ms to ready after reset" | [UM] |
| PS2 RST button | Resets only the shield, not the Arduino | [UM] |
| Stackable headers | Analog, power and digital I/O (JP4, JP7) pass through for shields stacked on top | [UM] |

**UART protocol** [UM Section 6] — the shield is passive and answers one command byte (decimal):

| Command | Meaning | Reply |
|---|---|---|
| 0–15 | Select, L-joystick centre, R-joystick centre, Start, Up, Right, Down, Left, L2, R2, L1, R1, Triangle, Circle, Cross, Square | 1 byte: 0 = pressed, 1 = not pressed |
| 16–19 | Left X, Left Y, Right X, Right Y (format 1) | 1 byte 0–255, 128 = neutral; up/left → 0, down/right → 255 |
| 20–27 | Left up/down/left/right, Right up/down/left/right (format 2) | 1 byte 0–100 |
| 28 | Connection status | 1 = controller detected |
| 29, value | Motor 1 (smaller vibrator, right) | value 1 = on, 0 = off |
| 30, value | Motor 2 (bigger vibrator, left) | value 0–255 = speed |
| 31 | All buttons and joysticks | 6 bytes: digital group 1, digital group 2, RX, RY, LX, LY |

Byte 1 (group 1) bits 7→0: Left, Down, Right, Up, Start, R-joystick centre, L-joystick centre, Select. Byte 2 (group 2) bits 7→0: Square, Cross, Circle, Triangle, R1, L1, R2, L2. Bit = 0 means pressed [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Baud rate in code must match the jumper**: `ps2.begin(9600); // This baudrate must same with the jumper setting at PS2 shield` [GH]. After moving the baud jumper, press PS2 RST (or power-cycle) [UM].
- **Default pins are D2 (RX) and D3 (TX)** → `Cytron_PS2Shield ps2(2, 3); // SoftwareSerial: Rx and Tx pin` [GH][UM]. Hardware serial: `Cytron_PS2Shield ps2;` (uses RX 0 / TX 1) [GH].
- **Hardware serial (D0/D1) blocks uploading**: "user needs to unplug the PS2 Connector from the Shield-PS2 before start to program the main board. Programming of main board may fail if the Shield-PS2 is stacked on mainboard and PS2 controller connector is connected." [UM]
- **Mega / Leonardo RX pin limits** (SoftwareSerial needs pin-change interrupts): Mega RX only on 10, 11, 12, 13, 50–53, 62–69; Leonardo RX only on 8, 9, 10, 11, 14 (MISO), 15 (SCK), 16 (MOSI) [UM]. Of the shield's RX jumper options, that leaves **D10 on Mega** and **D8 or D10 on Leonardo** (derived from the UM table and the jumper list).
- On Leonardo the library redefines `Serial` as `Serial1` for the hardware-serial constructor (`#if defined (__AVR_ATmega32U4__) #define Serial Serial1`) [GH].
- **Pressed = 0.** `readButton(PS2_SELECT) == 0` means pressed; 1 = released [GH][UM]. Writers often invert this.
- **Joystick values are not linear** and have "a big dead zone near the middle position" — the UM tells users to experiment [UM]. Neutral is 128 in format 1 [UM].
- **A1 is taken** by the shield reset line; the library sets A1 as OUTPUT HIGH in `begin()` [GH][UM]. Do not use A1 for a sensor.
- **Timeouts return 0xFF (255)** and set `SERIAL_ERR = true` when the shield does not answer (busy-wait count > 50000) [GH]. `readAllButton()` returns false if 6 bytes do not arrive [GH].
- **Current draw up to 500 mA max** from the Arduino's 5 V rail [UM] — budget it when the Arduino is USB-powered with other loads.
- The library `keywords.txt` still lists an older API (`getValue`, `getAll`, `p_select`, …) that does **not** exist in `Cytron_PS2Shield.h`; use `readButton`, `readAllButton`, `vibrate`, `reset` and the `PS2_*` enum [GH].
- A SoftwareSerial + Servo interrupt conflict tutorial is linked from the product page [PP]; its content was not read here — do not describe a fix without reading it.

## Power and electrical limits
- Logic/operating voltage 4.5–5.5 V, supplied by the Arduino main board [UM]. No separate power input on the shield is stated [UM].
- Current consumption 100 mA min / 150 mA typ / 500 mA max [UM] (includes the controller's vibration motors; not broken down in the UM).
- Logic input high 3.5–5.5 V; logic input low 0–1.0 V [UM]. 3.3 V-logic host boards: **not stated** by Cytron.
- Reverse-polarity, over-current or ESD protection: **not stated** [UM].

## Software support
- **Arduino library `Cytron_PS2Shield`** — https://github.com/CytronTechnologies/Cytron_PS2Shield (install: download ZIP → Arduino libraries folder; no `library.properties`, so it is not in the Library Manager) [GH]. Tested with CT UNO, Arduino IDE 1.6.5 [GH].
- Include: `#include <SoftwareSerial.h>` then `#include <Cytron_PS2Shield.h>` [GH].
- API [GH `Cytron_PS2Shield.h`]:
  - `Cytron_PS2Shield(uint8_t rxpin, uint8_t txpin)` — software serial; `Cytron_PS2Shield()` — hardware serial (RX 0, TX 1)
  - `void begin(uint32_t baudrate)` — opens the port and drives A1 HIGH
  - `uint8_t readButton(uint8_t key)` — digital keys return 0 = pressed / 1 = released; analog keys return the value
  - `boolean readAllButton()` — sends 31, fills `uint8_t ps_data[6]`, returns true on 6 bytes
  - `void vibrate(uint8_t motor, uint8_t value)` — motor 1 → command 29, else command 30
  - `void reset(uint8_t reset)` — 1 = A1 LOW (reset the shield), else A1 HIGH
  - `boolean SERIAL_ERR` — set true on read timeout
- Enum constants (0–31, same order as the protocol): `PS2_SELECT, PS2_JOYSTICK_LEFT, PS2_JOYSTICK_RIGHT, PS2_START, PS2_UP, PS2_RIGHT, PS2_DOWN, PS2_LEFT, PS2_LEFT_2, PS2_RIGHT_2, PS2_LEFT_1, PS2_RIGHT_1, PS2_TRIANGLE, PS2_CIRCLE, PS2_CROSS, PS2_SQUARE, PS2_JOYSTICK_LEFT_X_AXIS, PS2_JOYSTICK_LEFT_Y_AXIS, PS2_JOYSTICK_RIGHT_X_AXIS, PS2_JOYSTICK_RIGHT_Y_AXIS, PS2_JOYSTICK_LEFT_UP, PS2_JOYSTICK_LEFT_DOWN, PS2_JOYSTICK_LEFT_LEFT, PS2_JOYSTICK_LEFT_RIGHT, PS2_JOYSTICK_RIGHT_UP, PS2_JOYSTICK_RIGHT_DOWN, PS2_JOYSTICK_RIGHT_LEFT, PS2_JOYSTICK_RIGHT_RIGHT, PS2_CONNECTION_STATUS, PS2_MOTOR_1, PS2_MOTOR_2, PS2_BUTTON_JOYSTICK` [GH].
- Examples: `ReadButton` (LED on D13 while Select is pressed), `ReadJoystick` (prints left-X to Serial Monitor at 9600) [GH].
- The shield's protocol is plain UART bytes, so any board with a UART can use it without the library [UM Section 6].
- Fritzing part: SHIELD-PS2.fzpz on Google Drive [PP].

## Compatibility and accessories
- Arduino UNO, Arduino Duemilanove, Arduino Mega, Arduino Leonardo "and possibly other pin compatible main boards" [UM]; library README recommends CT UNO [GH].
- Stackable side headers allow more shields on top [UM]. "Please ensure that the pins alignment is correct." [UM]
- Controller: wired (Cytron PS-GP-1) or wireless (PS-GP-2) SONY-type PS2 controller, sold separately; "We do not guarantee the compatibility for all PS2 controllers from other sources" [UM].
- Arduino main board power during use: "from DC adaptor plug" in the UM example [UM].
- Price: RM65.10 (Cytron product page, read 2026-10-16) [PP].

## Common mistakes / troubleshooting
- **Garbage or 255 from every read** → baud jumper and `begin()` differ, or the jumper was moved without resetting the shield [UM][GH]; or the TX/RX jumpers do not match the pins in the constructor [UM].
- **Upload fails** → jumpers on D0/D1 with the controller plugged in; unplug the controller or move to D2/D3 [UM].
- **No response on Mega/Leonardo** → the chosen RX pin cannot do SoftwareSerial on that board; use D10 (Mega) or D8/D10 (Leonardo) [UM].
- **Button reads inverted** → 0 = pressed, 1 = released [UM][GH].
- **Status LED keeps blinking** → no controller detected (wireless receiver not paired, or controller off) [UM].
- **Joystick does not reach 0/255 or sits off-centre** → controller tolerance and dead zone; calibrate in software [UM].
- **A1 sensor misbehaves** → A1 is the shield reset line [UM][GH].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Library API names | [GH] header: `readButton`, `readAllButton`, `vibrate`, `reset` | [GH] keywords.txt: `getValue`, `getAll`, `p_select`… | Header/code wins; keywords.txt is stale |
| Warranty | [UM] 12 months | [PP] 12 months | Agree |
| A different "SmartElex PS2 Shield" manual (robu.in) lists RX D0/D9/D11, TX D1/D8/D10 and a 74880 default baud | [3P] | [UM] D0/D2/D8/D10, D1/D3/D9/D11, 4800–115200 | Different (derivative) product — never use its pin/baud table for SHIELD-PS2 |
| Baud-rate options | [UM]: jumper 4800 / 9600 / 57600 / 115200 | [PP] features (read 2026-10-19): 9600, 57600, 115200 | [UM] wins (4 options); the page omits 4800. Use 9600 in examples (library default) |

## Needs verification
- The onboard microcontroller / PS2-interface IC and whether the shield's own firmware can be updated.
- Whether the shield works with 3.3 V-logic hosts (VIOH min 3.5 V suggests not; not stated).
- Content of the Cytron tutorial "SoftwareSerial Conflicting with Servo Interrupt" (linked on the product page [PP]; not read) — what the conflict is and the recommended workaround.
- What the `wiki` branch of the GitHub repo contains (not fetchable here).
- [3P] RobotShop reviewer: joystick reads 255 with no controller attached — consistent with the library's 0xFF timeout value [GH], but not confirmed by Cytron.
- Whether the 500 mA max consumption includes both vibration motors running.

## Sources
- [UM] Shield-PS2 — Cytron PS2 Shield — User's Manual, V1.0, September 2013 — https://docs.google.com/document/d/1cifT1XqOquLffnu5J961wpKakSO8_LpV35v4sKSaIQU/edit
- [PP] Product page (read by coordinator 2026-10-16) — https://my.cytron.io/p-cytron-ps2-shield
- [GH] Arduino library — https://github.com/CytronTechnologies/Cytron_PS2Shield (README.md, Cytron_PS2Shield.h, Cytron_PS2Shield.cpp, keywords.txt, examples/ReadButton, examples/ReadJoystick; wiki branch https://github.com/CytronTechnologies/Cytron_PS2Shield/tree/wiki not readable here)
- [PP] Fritzing part — https://drive.google.com/file/d/188TaxyHvO1C1Kst8E6sXgypYA1Sc8eEk/view (SHIELD-PS2.fzpz; not opened)
- [PP] Tutorial (not read) — https://my.cytron.io/tutorial/softwareserial-conflicting-servo-interrupt
- [3P] (cross-check only) https://eu.robotshop.com/products/cytron-ps2-shield-arduino · https://test.robu.in/wp-content/uploads/2019/01/UserManual.pdf (SmartElex variant — not this product)
