# Product fact sheets

## Product name
SmartDriveDuo-10 (MDDS10)

## Aliases
MDDS10, SmartDriveDuo-10, SmartDriveDuo 10, Smart Drive Duo 10

## What it is
A dual-channel brushed DC motor driver that runs two motors from one 7–35 V supply. It takes RC receiver, analog, PWM or UART serial input, selected by DIP switch.

## Specs and functions
- Product code: MDDS10
- Motor channels: 2 (bi-directional, brushed DC)
- Input voltage (motor supply): 7 V to 35 V
- Maximum continuous motor current (IMAX): 10 A, depends on room temperature
- Peak motor current (IPEAK): 30 A, must not exceed 1 second
- Logic input high (VIOH): 1.3–5 V; logic input low (VIOL): 0–0.7 V
- 5V output current: 500 mA max ("Do not connect to another 5V source")
- Switching frequency: 16 KHz
- Input modes: RC, Analog, PWM, Simplified Serial, Packetized Serial, selected by DIP switch SW1–SW3 (SW1=0/SW2=0 RC; 0/1 Analog; 1/0 PWM; 1/1 with SW3=0 Simplified Serial; 1/1 with SW3=1 Packetized Serial)
- RC and Analog/PWM options: SW3:SW4 Mixed (00), Independent Right (01), Independent Left (10), Independent Both (11); SW5 exponential response on/off
- RC MCU mode (SW6=1): centre fixed at 1.5 ms, signal-loss timeout disabled; SW6=0: centre calibrated at power-up, motor stops after 100 ms without signal
- Analog/PWM (0–5 V): Locked Anti-Phase (SW6=0, stop at 2.5 V) or Signed Magnitude (SW6=1, 0 V stop, 5 V full speed, DIG1/DIG2 set direction); PWM input is low-pass filtered onboard
- Simplified Serial: 1 byte per command (bit 7 = LEFT/RIGHT); baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Packetized Serial: 4-byte packet (header 85 decimal / hex 55, address, command 0–255, checksum = header + address + command); address 0–7 by SW4–SW6, up to 8 drivers on one UART; auto-baud from the header byte, sent about 1 second after power-up
- Input header: DIG1 (LEFT direction; UART Rx in serial modes), DIG2 (RIGHT direction), AN1 (LEFT), AN2 (RIGHT), +5V, GND; RC header: RC1, RC2
- Terminals: Power Supply terminal block, Motor LEFT and Motor RIGHT terminal blocks (MLA/MLB, MRA/MRB); motor wires can also be soldered to the bottom pad
- Test buttons: 1 per motor, for fast test and manual operation
- LEDs: Run LED and direction LEDs per motor; Error LED (2 blinks input error, 3 under voltage, 4 over voltage, 5 over temperature, 6 shutdown)
- Thermal protection: duty cycle reduced in steps from 100% below 50 °C to 5% at 100–105 °C; shutdown above 105 °C; channel restarts below 70 °C
- Battery low voltage indicator and battery over voltage indicator
- Packing list: 1 × SmartDriveDuo-10, 6 × Terminal pin for 2510, 1 × 6-way Connector Housing
- Warranty: 12 months, manufacturing defects only
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Over-current protection: [NOT STATED]
- User's Manual: V1.0, June 2015
- 10 A continuous per channel at 25 °C, 30 A peak for 10 s (product page)
- Dimension 66.8 × 101.09 mm (product page)
- Error LED codes: 2 input error, 3 under-voltage, 4 over-voltage, 5 over-temperature, 6 shutdown (product page)
- Packing: board, 6-way connector housing, 6 terminal pins (product page)

## Interfaces and compatibility
- Signal sources: RC receiver, potentiometer, joystick, foot pedal, PWM, microcontroller UART
- Logic input high range is 1.3–5 V; the manual does not explicitly state 3.3 V compatibility
- UART: receive only (DIG1 Rx); no TX pin described
- Cytron_SmartDriveDuo Arduino library (version 1.0.0, architectures=avr) for SmartDriveDuo-10, SmartDriveDuo-30 and SmartDriveDuo-60
- Cytron tutorial: "Raspberry Pi: Control DC Motor using MDDS10"

## Use cases
- Differential drive mobile robot controlled by an RC receiver
- Motor control from a potentiometer, joystick or foot pedal
- Motor control from a microcontroller via PWM, Simplified Serial or Packetized Serial
- Up to 8 drivers sharing one microcontroller UART (Packetized Serial)
- Cytron tutorial: [Peak Current vs Continuous/Rated Current](https://my.cytron.io/tutorial/peak-current-vs-continuousrated-current)
- Cytron tutorial: [Raspberry Pi: Control DC Motor using MDDS10](https://my.cytron.io/tutorial/raspberry-pi-control-dc-motor-using-mdds10)
- Cytron tutorial: [CT Uno + PS2 shield + MDDS10 for mobile robot control](https://my.cytron.io/tutorial/ctuno-ps2-shield-mdds10-mobile-robot-control)
- Cytron tutorial: [Let’s Arduino Control SmartDriveDuo-10 (MDDS10)](https://my.cytron.io/tutorial/lets-arduino-control-smartdriveduo-10)
- Cytron tutorial: [Improve MDDS10 Performance With External Fan](https://my.cytron.io/tutorial/improve-mdds10-performance-external-fan)

## Known limitations
- No polarity protection on the power input / V motor; double check connections before powering up
- Supply must stay within 7–35 V; above 35 V the driver will not operate
- A power supply that cannot sink current (bench-top or AC-DC switching supply) must have a battery of the same voltage connected in parallel to absorb regenerative current, or the driver may be permanently destroyed
- 10 A continuous depends on room temperature; 30 A peak must not exceed 1 second
- Output is derated from 50 °C and shuts down above 105 °C
- Under voltage is a warning only; LiPo below 3.0 V per cell must be replaced/recharged
- Input must be at stop at power-up (RC, Analog, PWM) or the driver shows Input Error
- The RC transmitter must be ON before powering up the driver
- Packetized Serial: wait about 1 second after power-up before sending the header; baud rate cannot change without power cycle or reset
- In Mixed mode the left and right motors must be wired to the matching terminal blocks
- +5V output must not be connected to another 5V source; 500 mA max
- Maximum PWM input frequency: [NOT STATED]
- Heatsink, wire size and fuse requirements: [NOT STATED]

## Positioning (kept apart from specs)
- Manual: "16 KHz switching frequency for quiet operation"
- Manual: designed mainly for differential drive robots controlled by an RC receiver

## Price band
RM254.10 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-7v-35v-smartdrive-dc-motor-driver-2-channels

## Datasheet
https://cdn.robotshop.com/media/c/cyt/rb-cyt-165/pdf/mdds10_users_manual.pdf

## Source type
Datasheet

## Source link
https://cdn.robotshop.com/media/c/cyt/rb-cyt-165/pdf/mdds10_users_manual.pdf
