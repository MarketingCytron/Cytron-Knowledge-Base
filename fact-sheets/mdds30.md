# Product fact sheets

## Product name
SmartDriveDuo-30 (MDDS30)

## Aliases
MDDS30, SmartDriveDuo-30, SmartDriveDuo 30, Smart Drive Duo 30

## What it is
A dual-channel brushed DC motor driver that runs two motors from one 7–35 V supply. It takes RC receiver, analog, PWM or UART serial input, selected by DIP switch.

## Specs and functions
- Product code: MDDS30
- Motor channels: 2 (bi-directional, brushed DC)
- Input voltage (motor supply): 7 V to 35 V
- Maximum continuous motor current (IMAX): 30 A each channel, depends on room temperature
- Peak motor current (IPEAK): 80 A each channel, must not exceed 1 second
- Logic input high (VIOH): 1.3–5 V; logic input low (VIOL): 0–0.7 V
- Input dead-band (RC, Analog and PWM mode only): ±10%
- Switching frequency: 18 KHz
- Input modes: RC, Analog, PWM, Serial Simplified, Serial Packetized, selected by DIP switch SW1–SW3 (SW1:SW2 00 RC; 01 Analog; 10 PWM; 11 with SW3=0 Serial Simplified; 11 with SW3=1 Serial Packetized)
- RC and Analog/PWM options: SW3:SW4 Mixed (00), Independent Right (01), Independent Left (10), Independent Both (11); SW5 exponential response on/off
- RC SW6: MCU mode on Rev1.00 boards; Full Range mode on Rev1.10 boards (released Jan 2019, firmware update, revision sticker on board)
- Analog/PWM SW6: Locked Anti-Phase (stop at 2.5 V / 50% duty) or Signed Magnitude (stop at 0 V / 0% duty; IN1/IN2 set direction); PWM accepts TTL PWM 1.3–5 V HIGH and is low-pass filtered onboard
- Battery monitor SW7:SW8: 00 LiPo, 01 NiMH, 10 SLA, 11 Off
- Serial Simplified: 1 byte per command (bit 7 LEFT/RIGHT, bit 6 CW/CCW, bits 5–0 speed 0–63); baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Serial Packetized: 4-byte packet (header 0x55 / 85, channel and address, command 0–255, checksum = header + address + command); address 0–7 by SW4–SW6; up to 8 drivers on one UART Tx
- Serial Packetized auto-baud: send dummy byte 128 (0x80) once, one second after power-up; autobaud range 4800–115200 bps
- Control inputs: Grove connector AN1 (LEFT), AN2 (RIGHT); Grove connector IN1 (LEFT direction; UART receive in serial modes), IN2 (RIGHT direction); RC input RC1, RC2
- Terminals: Power Supply terminal block, Motor LEFT and Motor RIGHT terminal blocks (MLA/MLB, MRA/MRB); wires can also be soldered to the bottom pad
- Test buttons: 1 per motor, for fast test and manual operation
- Reset button: restarts the system to change mode without power cycling
- LEDs: RUN, ERR and OC per channel; motor direction LEDs; Power LED; Error LED blinks 2 input error, 3 under voltage, 4 over voltage, 5 over temperature
- Protections: thermal protection (max current 80 A below 50 °C, 50 A at 50–70 °C, 40 A at 70–100 °C, 30 A above 100 °C), current limit protection, over voltage (>35 V will not operate), battery low voltage warning
- Cooling fan connector (NC, +ve 5V, -ve): optional fan turns on automatically above 50 °C
- Packing list: 1 × SmartDriveDuo-30, 2 × Grove 4 Pin Buckled 20cm Cable, 2 × 2561 3 Ways Connector Extension Wire
- Optional fan kit (not included): DC5V Brushless Fan 40 x 40 x 20mm, 4 × PCB Stand 30mm, 4 × Bolt M3 x 25mm, 4 × M3 Nut
- Warranty: 12 months, manufacturing defects only
- 5V output current: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- User's Manual: Rev 1.2, September 2023
- Size 81.28 × 101.60 × 42 mm (product page)
- Latest board revision Rev 1.3 (RC-mode jerk fix); RC header vertical since Rev 1.2 (product page)
- Default configuration: RC, Mixed mode (product page)

## Interfaces and compatibility
- Signal sources: RC transmitter/receiver, analog joystick, microcontroller (Analog, PWM, UART)
- Logic input high range is 1.3–5 V; the manual does not explicitly state 3.3 V compatibility
- UART: receive only (IN1); no TX pin described
- Grove connectors; manual sample wiring uses CT UNO or Arduino Uno with Base Shield V2
- Cytron_SmartDriveDuo Arduino library (version 1.0.0, architectures=avr) for SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60, with PWM, Serial Simplified and Serial Packetized examples written for MDDS30

## Use cases
- Differential drive mobile robot controlled by an RC controller
- Motor control from an analog joystick
- Motor control from a microcontroller via PWM, Serial Simplified or Serial Packetized
- Up to 8 drivers sharing one microcontroller UART Tx pin (Serial Packetized)
- Cytron tutorial: [Control MDDS30 In Serial Simplified Mode Using Raspberry Pi](https://my.cytron.io/tutorial/control-mdds30-in-serial-simplified-mode-using-raspberry-pi)
- Cytron tutorial: [Getting Started with Cytron Motor Driver](https://my.cytron.io/tutorial/getting-started-with-cytron-motor-driver)
- Cytron tutorial: [Remote Raspberry Pi Using Maker pHAT](https://my.cytron.io/tutorial/control-mdds30-in-serial-simplified-mode-using-raspberry-pi-2)

## Known limitations
- No polarity protection on V motor / power input; double check connections before powering up
- Supply must stay within 7–35 V; above 35 V the driver will not operate
- A power supply that cannot sink current (bench-top or AC-to-DC switching supply) must have a battery of the same voltage connected in parallel to absorb regenerated current, or the driver may be destroyed permanently
- Pushing the robot with no battery connected might burn the driver; this is misuse and not covered by warranty
- 30 A continuous depends on room temperature; 80 A peak must not exceed 1 second
- Maximum current is reduced from 50 °C (down to 30 A above 100 °C)
- Under voltage is a warning only; motor power is maintained; LiPo below 3.0 V per cell must be replaced/recharged
- Input must be at stop at power-up (RC, Analog, PWM) or the driver shows Input Error
- The RC transmitter must be ON before powering up the driver
- Do not use an external BEC/regulator for the RC receiver; if required, disconnect the middle (red) wire
- Input mode is read only at power-up; press RESET or power cycle after changing the DIP switch
- RC SW6 function differs between Rev1.00 (MCU mode) and Rev1.10 (Full Range mode) boards
- Serial Packetized auto-baud byte is 0x80, not the 0x55 used by MDDS10 and MDDS60
- Maximum PWM input frequency: [NOT STATED]
- Wire size: "use wire with proper thickness to support the expected current"; gauge and fuse rating [NOT STATED]

## Positioning (kept apart from specs)
- Manual: "MOSFETs are switched at 18 KHz to ensure quiet operation and no annoying whining sound"
- Manual: "SmartDriveDuo-30's feature makes driving a robot with differential drive a truly plug and play experience"
- Manual: one of the latest smart series motor drivers, designed to drive medium power brushed DC motors

## Price band
RM364.98 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-30amp-7v-35v-smartdrive-dc-motor-driver-2-channels

## Datasheet
https://docs.google.com/document/d/1OstW8T0kRIopWSuMEOyG2h9KNhQ3O4yowwjnp40Z23o/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1OstW8T0kRIopWSuMEOyG2h9KNhQ3O4yowwjnp40Z23o/view
