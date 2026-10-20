# Product fact sheets

## Product name
SmartDriveDuo-60 (MDDS60)

## Aliases
MDDS60, SmartDriveDuo-60, SmartDriveDuo 60, Smart Drive Duo 60

## What it is
A dual-channel brushed DC motor driver that runs two motors from one 10–45 V supply. It takes RC receiver, analog, PWM or UART serial input, selected by DIP switch.

## Specs and functions
- Product code: MDDS60
- Motor channels: 2 (bi-directional, brushed DC)
- Input voltage (motor supply): 10 V to 45 V
- Maximum continuous motor current (IMAX): 60 A each channel, depends on room temperature
- Peak motor current (IPEAK): 100 A each channel, must not exceed 1 second
- Logic input high (VIOH): 1.3–5 V; logic input low (VIOL): 0–0.7 V
- 5V output current: 500 mA max ("Do not connect to another 5V source")
- Switching frequency: 16 KHz
- Input modes: RC, Analog, PWM, Simplified Serial, Packetized Serial, selected by DIP switch SW1–SW3 (SW1:SW2 00 RC; 01 Analog; 10 PWM; 11 with SW3=0 Simplified Serial; 11 with SW3=1 Packetized Serial)
- RC and Analog/PWM options: SW3:SW4 Mixed (00), Independent Right (01), Independent Left (10), Independent Both (11); SW5 exponential response on/off
- RC MCU mode (SW6=1): centre fixed at 1.5 ms, signal-loss timeout disabled; SW6=0: centre calibrated at power-up, motor stops after 100 ms without signal
- Analog/PWM (0–5 V): Locked Anti-Phase (SW6=0, stop at 2.5 V) or Signed Magnitude (SW6=1, 0 V stop, 5 V full speed, DIG1/DIG2 set direction); PWM input is low-pass filtered onboard
- Simplified Serial: 1 byte per command (bit 7 = LEFT/RIGHT); baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Packetized Serial: 4-byte packet (header 85 decimal / hex 55, address, command 0–255, checksum = header + address + command); address 0–7 by SW4–SW6; up to 8 drivers on one UART Tx; auto-baud from the header byte, sent one second after power-up
- Input terminal block: DIG1 (LEFT direction; UART Rx in serial modes), DIG2 (RIGHT direction), AN1 (LEFT), AN2 (RIGHT), +5V, GND; RC input: RC1, RC2
- Terminals: Power Supply terminal block, Motor LEFT and Motor RIGHT terminal blocks; wires can also be soldered to the bottom pad
- Power Switch terminal block: switches the microcontroller and logic circuit; ON by default; cut/unsolder the bottom-layer link to use an external switch
- Test buttons: 1 per motor, for fast test and manual operation
- "RST" reset button to change input mode without power cycling
- LEDs: RUN_L, RUN_R, motor direction LEDs; Error LED (2 blinks input error, 3 under voltage, 4 over voltage, 5 over temperature, 6 shutdown)
- Cooling fan: runs once the driver is powered up
- Thermal protection: duty cycle reduced in steps from 100% below 50 °C to 5% at 100–105 °C; shutdown above 105 °C; channel restarts below 70 °C
- Battery low voltage indicator and battery over voltage indicator (above 45 V the driver will not operate)
- Packing list: 1 × SmartDriveDuo-60 with top and bottom cover, 2 × 2561 Servo Extension cable
- Hardware revision: Rev1.10 shipped since January 2019 (component change; performance and interface unchanged)
- Warranty: 12 months, manufacturing defects only
- Over-current protection: [NOT STATED]
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- User's Manual: Rev 1.1, July 2019
- Two DC brushless fans on the top cover (product page)
- Dimension ~190 × 121 × 45 mm (product page)
- Peak 100 A for 1 s; no polarity protection (product page)

## Interfaces and compatibility
- Signal sources: RC transmitter/receiver, joystick or foot pedal with potentiometer, Cytron Breakout board with Joystick soldered, microcontroller (PWM, UART)
- Logic input high range is 1.3–5 V; the manual does not explicitly state 3.3 V compatibility
- UART: receive only (DIG1 Rx); no TX pin described
- Cytron_SmartDriveDuo Arduino library (version 1.0.0, architectures=avr) for SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60

## Use cases
- Differential drive mobile robot controlled by an RC controller
- Motor control from a joystick or foot pedal with potentiometer
- Motor control from a microcontroller via PWM, Simplified Serial or Packetized Serial
- Up to 8 drivers sharing one microcontroller UART Tx pin (Packetized Serial)
- Cytron tutorial: [Let's Arduino Control Your SmartDriveDuo-60 (MDDS60)](https://my.cytron.io/tutorial/lets-arduino-control-smartdriveduo-60)

## Known limitations
- No polarity protection on V motor / power input; double check connections before powering up
- Supply must stay within 10–45 V; above 45 V the driver will not operate
- A power supply that cannot sink current (bench-top or AC-to-DC switching supply) must have a battery of the same voltage connected in parallel to absorb regenerated current, or the driver may be destroyed permanently
- 60 A continuous depends on room temperature; 100 A peak must not exceed 1 second
- Output is derated from 50 °C and shuts down above 105 °C
- Under voltage is a warning only; motor power is maintained; LiPo below 3.0 V per cell must be replaced/recharged
- Input must be at stop at power-up (RC, Analog, PWM) or the driver shows Input Error
- The RC transmitter must be ON before powering up the driver
- Input mode is read only at power-up; press "RST" or power cycle after changing the DIP switch
- Packetized Serial: wait one second after power-up before sending the header; baud rate cannot change without power cycle or reset
- In Mixed mode the left and right motors must be wired to the matching terminal blocks
- +5V output must not be connected to another 5V source; 500 mA max
- Maximum PWM input frequency: [NOT STATED]
- Wire size: "use wire with proper thickness to support the expected current"; gauge and fuse rating [NOT STATED]

## Positioning (kept apart from specs)
- Manual: "MOSFETs are switched at 16 KHz to ensure quiet operation and no annoying whining sound"
- Manual: "SmartDriveDuo-60's feature makes driving a robot with differential drive a truly plug and play experience"
- Manual: one of the latest smart series motor drivers, designed to drive medium power brushed DC motors

## Price band
RM831.60 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-mdds60

## Datasheet
https://docs.google.com/document/d/15ICHc5CqQL8oXdU-n3ZL0_o8Vm4wQCnWOHHEfrEDDaI/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/15ICHc5CqQL8oXdU-n3ZL0_o8Vm4wQCnWOHHEfrEDDaI/view
