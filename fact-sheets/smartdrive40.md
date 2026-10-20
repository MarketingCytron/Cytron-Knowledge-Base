# Product fact sheets

## Product name
Enhanced SmartDrive40 (MDS40B) — 40Amp 10V-45V SmartDrive DC Motor Driver

## Aliases
MDS40B, Enhanced SmartDrive40, SmartDrive40, 40Amp 10V-45V SmartDrive DC Motor Driver

## What it is
A single-channel brushed DC motor driver for medium to high power motors, running from a 10–45 V supply. An onboard microcontroller provides RC, Analog, PWM, Simplified Serial and Packetized Serial input modes, selected with a DIP switch.

## Specs and functions
- Product code: MDS40B
- User's Manual: Rev 1.1, July 2023 (spec table titled "Absolute Maximum Rating of Enhanced SmartDrive40")
- Motor channels: 1 (one brushed DC motor per board; two boards for a differential-drive robot)
- Input Voltage (Motor Supply Voltage): 10–45 V
- Maximum continuous motor current: 40 A (depends on the room temperature)
- Peak motor current: 80 A, must not exceed 1 second
- Logic input high level (VIOH): 1.3–5 V; logic input low level (VIOL): 0–0.7 V
- Product page: "3.3 and 5V compatible input"
- 5V output current: 500 mA max (do not connect to another 5V source)
- MOSFETs switched at 16 KHz for quiet operation
- Input modes: RC, Analog, PWM, Simplified Serial, Packetized Serial; selected with an 8-position DIP switch, read at power-up (press RST or power cycle after changing)
- RC mode (SW1:SW2 = 00): Independent (input 1 only), Mixed Right, Mixed Left; SW5 exponential response; SW6 MCU Mode (off: centre calibrated at power-up, motor stops after 100 ms signal loss; on: centre fixed at 1.5 ms, no timeout, motor keeps previous speed)
- RC transmitter must be ON before powering up the driver
- Analog mode (SW1:SW2 = 01) and PWM mode (SW1:SW2 = 10): 0–5 V input range; PWM input is low-pass filtered to analog
- SW6 in Analog/PWM: Locked Anti-Phase (stop at 2.5 V) or Signed Magnitude (Input 1 speed 0 V stop to 5 V full, Input 2 digital direction)
- Stop signal (2.5 V, or 0 V in Signed Magnitude) must be present at power-up, otherwise Input Error
- Simplified Serial (SW1–SW3 = 110): Input 1 = UART Rx, Input 2 = Slave Select; one byte: 127 stop, 0 full reverse, 255 full forward; baud 1200, 2400, 4800, 9600, 19200, 38400, 57600 or 115200 set by SW4–SW6
- Packetized Serial (SW1–SW3 = 111): 4-byte packet — header 85, address 0–7 (SW4–SW6), command (127 stop, 0 full reverse, 255 full forward), checksum = header + address + command; auto-baud from the first header byte; up to 8 units on one UART Tx pin; allow one-second delay after power-up before sending the header
- Error LED: 2 blinks Input Error; 3 blinks Under Voltage; 4 blinks Over Voltage (MDS40B will not operate); 5 blinks Over Temperature
- Over-temperature current limit: below 50 °C 80 A; 50–70 °C 50 A; 70–100 °C 45 A; 100–110 °C 40 A; above 110 °C 35 A
- Under voltage (LiPo, below 3.0 V per cell): warning only, motor power is not cut
- Over voltage: above 45 V the driver will not operate
- Run LED, Error LED, Motor LED indicators (LED A on = current from output A to B)
- Two motor test buttons (A: current flows from output A to B; B: vice versa)
- Reset button (RST)
- Power Switch Terminal Block: switches the microcontroller and logic circuit; ON by default
- Fan connector for an optional 5V cooling fan (always on, no speed control)
- Dimensions (product page): 105 mm (W) x 106 mm (D) x 38 mm (H) driver board; 125 mm (W) x 107 mm (D) x 47 mm (H) with the base
- Packing list: 1 x Enhanced SmartDrive40 with top and bottom cover; 2 x 2561 Servo Extension cable
- Warranty: 12 months, manufacturing defects only
- Reverse polarity protection: none
- Operating temperature: [NOT STATED]
- Weight: [NOT STATED]
- PWM input maximum frequency: [NOT STATED]

## Interfaces and compatibility
- Power Supply Terminal block (screw terminal or solder to bottom-layer pad)
- Motor Terminal Block (screw terminal or solder to bottom-layer pad)
- Analog/PWM/Serial Input Terminal Block: GND, 5V (output), IN1, IN2
- RC Input Pin: RC1 forward/reverse, RC2 steering
- Fan connector (5V)
- Power Switch Terminal Block
- Recommended power sources: 9–18 cells NiMH or NiCd (up to 30 cells; low voltage warning only up to 18 cells); 3–6 cells LiPo or Li-Ion (up to 10 cells; warning only up to 6 cells); 10–45 V sealed lead acid; 10–45 V power supply in parallel with a battery of the same voltage
- Wire: use wire thick enough for the expected current; product page recommends Multicore Wire AWG14
- Arduino: CytronMotorDriver library, PWM_DIR example (MDS40B set to Sign-Magnitude PWM Input mode)
- 3.3 V PWM input supported (product page); input pins are pulled up, so NPN optocouplers can be used (product page)
- Joystick breakout board recommended for Analog Locked Anti-Phase mode
- Onboard current sensor: not accessible (product page)

## Use cases
- Medium to high power brushed DC motor
- Robot with differential drive (two units, Mixed Left and Mixed Right)
- Control from a standard hobby radio control transmitter and receiver, or a microcontroller generating the similar signal
- Motor controlled by a joystick or foot pedal with potentiometer
- Microcontroller control via PWM or UART serial

## Known limitations
- Drives one motor only; two motors need two boards
- No reverse polarity protection; double check the connection before powering up
- Peak 80 A must not exceed 1 second; continuous 40 A depends on room temperature
- Current limit drops with board temperature (down to 35 A above 110 °C)
- With a power supply that cannot sink current (bench top or AC to DC switching power supply), a battery with the same voltage must be connected in parallel to absorb regenerative current; otherwise the input voltage might rise and destroy the driver permanently or trip the supply's protection
- Above 45 V the driver will not operate
- Under-voltage is a warning only; motor power is not cut, the user must stop and replace the battery
- Battery low voltage warning works only up to 18 NiMH/NiCd cells or 6 LiPo/Li-Ion cells
- Input must be at stop at power-up in RC, Analog and PWM modes, otherwise Input Error
- RC transmitter must be on before powering the driver
- With MCU Mode on there is no signal-loss timeout; the motor keeps its previous speed
- DIP switch changes need a reset or power cycle
- Packetized Serial needs a one-second delay after power-up before the header byte; baud rate fixed until power cycle or reset
- Do not connect the 5V output to another 5V source; 5V output limited to 500 mA
- Manual's features list says "dual brushed DC motor", but the board drives a single motor (product page: Motor Channel 1)

## Positioning (kept apart from specs)
- Product page: improved from MDS40A based on user feedback ("Enhanced SmartDrive40")
- Product page enhancements: increased Vin range up to 45 VDC; responsive current limiting sensor and algorithm; high ampere screw terminals; additional terminal to deactivate the driver without a high power switch; switching regulator for 5V; option to add a fan; ready header for RC receiver; over voltage protection
- Product page lists "Regenerative Braking."
- User's Manual: makes driving a robot with differential drive "a truly plug and play experience"

## Price band
RM346.50 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-40amp-10v-45v-smartdrive-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1WtfqfUlUlLCjGR_q33lZQt5xLPtft4zG0jJk5PX1A8Y/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1WtfqfUlUlLCjGR_q33lZQt5xLPtft4zG0jJk5PX1A8Y/edit
