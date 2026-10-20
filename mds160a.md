# 160Amp 8V-28V SmartDrive DC Motor Driver (MDS160A) — Verified Reference

| | |
|---|---|
| Product code | `MDS160A` (manual title [UM]; product-page image paths [PP]). Manual product name: **SmartDrive160** [UM] |
| Family | Cytron motor drivers |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. Board size, no reverse-polarity protection and the wiring advice (2–3 × 8 AWG per terminal) are now Cytron-stated |
| Primary source | "MDS160A SmartDrive160 User's Manual" — **V1.0, Aug 2014** — public Google Doc: https://docs.google.com/document/d/1nkdj8CrZKoc4PHemBqlvpEJkQ2KjUHGqCTI8S5-mba4/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
A single-channel, bi-directional smart driver for one high-power brushed DC motor: 8–28 V input, 160 A continuous, with a microcontroller providing multiple input modes (RC, Analog, PWM, Simplified Serial, Packetized Serial), temperature-based current limiting and thermal protection [UM]. MOSFETs switch at 16 KHz; it has a cooling fan [UM]. Two units can be paired in mixed mode for a differential-drive robot [UM].
- Manual introduction: "designed to drive high power brushed DC motor with current capacity up to 160A continuously. MOSFETs are switched at 16 KHz to ensure quiet operation and no annoying whining sound." [UM]

## Specifications
Manual section 3.0 "Product Specifications" table, plus feature list [UM].

| Item | Value | Src |
|---|---|---|
| Input voltage (motor supply voltage) | Min 8 V, Max 28 V | [UM] |
| IMAX — maximum continuous motor current | Max 160 A — footnote: "Depends on the room temperature." | [UM] |
| IPEAK — peak motor current | Max 190 A — footnote: "Depends on the room temperature." Feature list: "190A peak (1 minute), 175A (2 minutes) or 160A (continuously)." | [UM] |
| VIOH — logic input high level | Min 3 V, Max 5.5 V — "Not applicable for PWM signal as PWM signal will be converted to analog voltage via low pass filter before processed by the processor." | [UM] |
| VIOL — logic input low level | Min 0 V, Typical 0 V, Max 0.5 V (same footnote) | [UM] |
| 5V output current | Max 1 A | [UM] |
| Switching frequency | 16 KHz ("for quiet operation") | [UM] |
| Number of channels | 1 — "Bi-directional control for a single brushed DC motor." | [UM] |
| Logic supply | No separate logic supply input; board provides a +5V **output** (≤ 1 A) | [UM] |
| Input modes | RC, Analog, PWM, Simplified Serial, Packetized Serial — selected by 8-way DIP switch, read at power-up | [UM] |
| Serial baud rates | Simplified Serial: 1200, 2400, 4800, 9600, 19200, 38400, 57600, 115200 (SW6–SW8). Packetized Serial: auto-baud from header byte 85 | [UM] |
| Analog input range | 0 – 5 V | [UM] |
| Max PWM input frequency (PWM mode) | Not stated (PWM is low-pass filtered to analog) | — |
| Current limiting by temperature | < 60 °C: 194 A; 60–70 °C: 175 A; 70–80 °C: 163 A; 80–90 °C: 144 A; 90–100 °C: 125 A; 100–110 °C: 100 A; > 110 °C: 50 A | [UM] |
| Protections | LiPo under-voltage **warning** (no cut-out); overvoltage protection; overcurrent protection (current limited each PWM cycle); over-temperature protection | [UM] |
| Reverse polarity protection | Not stated | — |
| Cooling | Cooling fan fitted — "The height is 75mm including the cooling fan." | [UM] |
| Dimensions | 122 × 178 × 75 mm (height includes the fan) | [PP][UM] |
| Test buttons | 2 (Test Button A, Test Button B) | [UM] |
| LEDs | LED A, LED B, LED OC, LED ERR, LED STAT, LED PWR | [UM] |
| On/Off switch | Terminal for external on/off switch, shorted by default with a solder bridge on the bottom layer | [UM] |
| Operating temperature | Not stated (only the current-limit vs board temperature table) | — |
| Warranty | "Product warranty is valid for 12 months." Manufacturing defects only; misuse and two-way freight not covered | [UM] |
| Packing list | 1 x MDS160A SmartDrive160; user's manual downloadable from cytron.com.my | [UM] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Description:** SmartDrive160, 160 A continuous; MOSFETs switched at 16 kHz; MCU for multiple input modes, current limiting and thermal protection; can pair with a second unit for differential drive; "Normal wire cannot survive 160A or even 100A" — Cytron uses 2 to 3 **8 AWG** cables per terminal [PP].
- **Features:** single brushed DC motor; 8–28 V; 190 A peak (1 min), 175 A (2 min), 160 A continuous; LiPo low-voltage warning; full solid-state, no flyback diodes needed; regenerative braking; **NO reverse polarity protection for Vmotor**; thermal protection; current limit by temperature (below 60 °C 194 A; 60–70 °C 175 A; 70–80 °C 163 A; 80–90 °C 144 A; 90–100 °C 125 A; 100–110 °C 100 A; above 110 °C 50 A); input modes RC, analog, PWM/DIR (3.3/5 V), UART simplified and packetized; push buttons; **122 × 178 × 75 mm** [PP].
- **Packing list:** 1x MDS160A [PP]. **Resources:** user's manual, CytronMotorDriver library, 3D CAD [PP].

## Interfaces, terminals and pin mapping
Board layout components (manual numbering is lost in the Google Doc text; order as listed, and the manual refers to the SWITCH terminal as "No. 15") [UM]:
1. Positive Supply Terminal — power source (+).
2. Negative Supply Terminal — power source (−).
3. Motor Terminal A / 4. Motor Terminal B — swap A and B if direction is wrong.
5. LED A — on when A high, B low (current A to B). 6. LED B — on when A low, B high (current B to A).
7. LED OC — overcurrent detected and current is being limited.
8. LED ERR — blink count = error (table below).
9. LED STAT — on when the motor is running.
10. Test Button B — current B to A, motor CCW (or CW). 11. Test Button A — current A to B, motor CW (or CCW).
12. Input header (4 pins): pin 1 IN2 (Input channel 2); pin 2 IN1 (Input channel 1); pin 3 +5V ("+5V output. Do not connect to another 5V source."); pin 4 Gnd.
13. Mode Selection DIP Switch. 14. LED PWR — power LED.
15. On/Off Switch terminal — turn off motor power without disconnecting the power cable.

Error LED blinks [UM]: Off = No Error; 2 = Input Error (invalid or no input); 3 = Lipo Undervoltage; 4 = Over Voltage ("The power source cannot absorb the current generated by the motor."); 5 = Over Temperature.

DIP switch input-mode summary (0 = OFF/down, 1 = ON/up, X = don't care) [UM]:

| Mode | SW1–SW4 | SW5–SW8 | Input 1 | Input 2 |
|---|---|---|---|---|
| RC | 0000 | SW5:6 single (0X) / mix-left (10) / mix-right (11); SW7 exponential; SW8 MCU mode | Speed | Steering (mix mode) |
| Analog / PWM | XX01 (SW1/SW2: 0 = analog, 1 = PWM, for Input 1/Input 2) | SW5:6 single/mix; SW7 exponential; SW8 sign-magnitude | Speed | Steering (mix) / Direction (sign-magnitude) |
| Simplified Serial | 0010 | SW5 N/A; SW6–SW8 baud rate | UART Rx | Slave Select |
| Packetized Serial | 0011 | SW5–SW8 address 0–15 | UART Rx | N/A |

Common settings [UM]: 00000000 = RC single, exp off, MCU off; 00000010 = RC single, exponential on; 00001000 = RC left mix; 00001100 = RC right mix; 00010000 = Analog single; **10010001 = PWM, single, sign-magnitude on**; 11011000 = PWM left mix; 11011100 = PWM right mix.

Mode details [UM]:
- **RC:** standard hobby RC transmitter/receiver or an MCU generating the same signal. SW8 off: centre calibrated at power-up, 100 ms signal-loss timeout stops the motor. SW8 on (MCU mode): centre fixed at 1.5 ms, timeout disabled, motor keeps last speed.
- **Analog/PWM:** SW8 off: 2.5 V = stop, < 2.5 V one direction, > 2.5 V the other. SW8 on (sign-magnitude, single mode only, SW5 = 0, SW2 = 0): Input 1 speed, 0 V stop to 5 V full; Input 2 digital direction. Mix modes need SW8 = 0. Footnote: "For Watanabe revision, the center value is 3V and motor stops if < 0.8V. Input 2 must be low to enable the driver."
- **Simplified Serial:** one byte: 127 stop, 0 full reverse, 255 full forward. Slave Select must be HIGH to accept data; internally pulled high, may be left unconnected.
- **Packetized Serial:** 4-byte packet: Header 85, Address 0–15 (must match DIP), Command 0–255 (127 stop, 0 full reverse, 255 full forward), Checksum = Header + Address + Command. Up to 16 units on one UART.

## Rules and gotchas (for code, wiring and tutorials)
- **Power supply must be able to sink current.** Recommended sources: 7–18 cell NiMH/NiCd; 3–6 cell LiPo/Li-Ion; 12–24 V sealed lead acid; 8–28 V power supply "(**Must be in parallel with a battery with same voltage**)" [UM].
- "If a power supply that cannot sink current is being used (bench top and AC to DC switching power supply), the input voltage will rise when the driver is regenerating … Else, the input voltage might rise to a level where SmartDrive160 will be destroyed permanently." [UM]
- **Mode is read only at power-up** — change the DIP switch, then power-cycle [UM].
- RC mode: "The RC transmitter must be turn on before power up the SmartDrive160." [UM]
- Analog/PWM mode: the stop signal (2.5 V, or 0 V in sign-magnitude) must be present at power-on, else Input Error [UM].
- Packetized Serial: start-up takes up to 500 ms — "allow a one-second delay between applying power and sending the header byte" (85) [UM]. Baud rate fixed until power-cycled [UM].
- +5V pin is an **output** (≤ 1 A, for RC receiver, mini servo, other circuits) — "Do not connect to another 5V source." [UM]
- Logic inputs 3–5.5 V high, ≤ 0.5 V low (not applicable to PWM, which is filtered) [UM]. Analog input range 0–5 V [UM].
- LiPo under-voltage (< 3.3 V per cell) is a **warning only**; motor power is not cut — user must stop and replace the battery [UM]. With other battery types the warning may still show and can be ignored [UM].
- Board off at power-up → SWITCH terminal (No. 15) must be shorted (solder bridge) [UM].
- Smart drivers used with the Cytron Arduino library must be set to **Sign-Magnitude PWM input** mode [GH].

## Power and electrical limits
- Input 8–28 V [UM].
- 160 A continuous; 190 A peak (1 minute); 175 A (2 minutes) — all "depends on the room temperature" [UM].
- Overcurrent threshold falls with board temperature, 194 A (< 60 °C) down to 50 A (> 110 °C) [UM].
- Overvoltage protection: slows deceleration when voltage rises; at a dangerous level brakes immediately by shorting the motor terminals [UM].
- Over-temperature: temperature sensor gradually lowers the current-limit threshold; ERR LED blinks 5 times [UM].
- Reverse polarity protection: not stated. Under-voltage cut-off: none (LiPo warning only) [UM].
- 5 V output: 1 A max [UM].

## Software support
- Arduino: **Cytron Motor Drivers Library** (`CytronMotorDriver`, version 1.0.1); MDS160A listed under the **PWM_DIR** example with the note "Smart series motor driver needs to be configured as Sign-Magnitude PWM Input mode" [GH] — https://github.com/CytronTechnologies/CytronMotorDriver
  - In that mode IN1 = speed (PWM), IN2 = direction [UM]; `CytronMD motor(PWM_DIR, pwmPin, dirPin)` [GH].
- Serial protocols (Simplified and Packetized) fully described in the manual [UM]; no Cytron serial library stated for MDS160A.
- MicroPython / CircuitPython / ROS: not stated.

## Compatibility and accessories
- Hobby RC transmitter/receiver; potentiometer, joystick or foot pedal with potentiometer; microcontroller via PWM, RC-style pulses or UART [UM].
- Two units can run in mixed mode (left/right) for differential drive [UM]; up to 16 units on one UART in Packetized Serial [UM].
- External on/off switch via the SWITCH terminal (desolder the bridge first) [UM].
- 3D CAD folder linked on the product page [PP].

## Common mistakes / troubleshooting
- ERR LED blinks 2 times → no/invalid input; check transmitter on before power-up, stop signal present at power-on, or header byte not yet sent in Packetized Serial [UM].
- ERR LED blinks 4 times / driver brakes during deceleration → supply cannot absorb regenerative current; add a same-voltage battery in parallel [UM].
- ERR LED blinks 5 times / reduced torque when hot → over-temperature current limiting [UM].
- OC LED on → overcurrent; current limited each PWM cycle (e.g. starting/stall current above the threshold) [UM].
- DIP change has no effect → power-cycle the driver [UM].
- Board does not turn on → SWITCH terminal open; short it or fit a switch [UM].
- Motor runs wrong direction → swap Motor Terminal A and B [UM].

## Conflicts between sources

| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Peak current vs current-limit threshold | [UM] spec table / features: 190 A peak (1 minute) | [UM] current-limit table: 194 A below 60 °C | Same document; state 190 A as peak rating; 194 A is the overcurrent threshold, not a rating |
| Voltage in name | [PP] "160Amp 8V-28V" | [UM] 8–28 V, 160 A | Agree |

## Needs verification
1. Max PWM input frequency in PWM mode — not stated.
2. Packetized Serial checksum overflow — whether only the lower 8 bits of Header + Address + Command are used is not stated (value range 0–255 implies it).
3. "Watanabe revision" footnote — which units this applies to is not explained.
4. Operating temperature range, terminal wire size — not stated.
5. Board-layout item numbers are lost in the Google Doc text; order above follows the list as read and the "No. 15" SWITCH reference.
6. Mounting-hole positions (size 122 × 178 × 75 mm on the product page).

## Sources
- [UM] MDS160A User's Manual (Google Doc, "MDS160A SmartDrive160 User's Manual, V1.0, Aug 2014"): https://docs.google.com/document/d/1nkdj8CrZKoc4PHemBqlvpEJkQ2KjUHGqCTI8S5-mba4/view
- PDF mirror of the same manual (cross-check only): https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-174/pdf/smartdriveduo-smart-single-channel-160a-motor-driver-user-manual.pdf
- [PP] Product page "160Amp 8V-28V SmartDrive DC Motor Driver": https://my.cytron.io/p-160amp-8v-28v-smartdrive-dc-motor-driver (read by coordinator 2026-10-16)
- [PP] 3D CAD folder (linked from product page, not opened): https://drive.google.com/drive/folders/1HkRfARPpSH6DYcaj8fBsAaTx2djJAeCl
- [GH] Cytron Motor Drivers Library: https://github.com/CytronTechnologies/CytronMotorDriver
