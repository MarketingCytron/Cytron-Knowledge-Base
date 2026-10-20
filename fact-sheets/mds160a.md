# Product fact sheets

## Product name
160Amp 8V-28V SmartDrive DC Motor Driver (MDS160A, SmartDrive160)

## Aliases
MDS160A, SmartDrive160, SmartDrive 160, Cytron MDS160A, 160Amp 8V-28V SmartDrive DC Motor Driver

## What it is
A single-channel, bi-directional smart driver for one high-power brushed DC motor, 8–28 V input and 160 A continuous. An onboard microcontroller provides RC, Analog, PWM, Simplified Serial and Packetized Serial input modes, temperature-based current limiting and thermal protection.

## Specs and functions
- Product code: MDS160A (SmartDrive160)
- Channels: 1 (bi-directional, brushed DC motor)
- Input voltage (motor supply): 8 V min, 28 V max
- Maximum continuous motor current: 160 A (depends on the room temperature)
- Peak motor current: 190 A (1 minute); 175 A (2 minutes); 160 A continuously (depends on the room temperature)
- Logic input high level: 3 V min, 5.5 V max; low level: 0 V min, 0 V typical, 0.5 V max (not applicable for PWM signal, which is low-pass filtered to analog)
- Analog input range: 0 – 5V
- 5V output current: 1 A max
- Switching frequency: 16 KHz
- Input modes, selected by 8-way DIP switch and read at power-up: RC, Analog, PWM, Simplified Serial, Packetized Serial
- RC mode: single or left/right mix; exponential option; MCU mode (centre fixed at 1.5 ms, timeout disabled); otherwise 100 ms signal-loss timeout stops the motor
- Analog/PWM mode: 2.5V = stop (centre mode) or sign-magnitude (Input 1 speed 0V stop to 5V full, Input 2 direction); single or left/right mix; exponential option
- Simplified Serial baud rates: 1200, 2400, 4800, 9600, 19200, 38400, 57600, 115200; one byte (127 stop, 0 full reverse, 255 full forward); Slave Select on Input 2
- Packetized Serial: auto-baud from header byte 85; 4-byte packet (header, address 0–15, command, checksum = header + address + command); up to 16 units on one UART
- Current limit by board temperature: below 60°C 194A; 60–70°C 175A; 70–80°C 163A; 80–90°C 144A; 90–100°C 125A; 100–110°C 100A; above 110°C 50A
- LiPo under voltage warning (below 3.3V per cell; warning only)
- Overvoltage protection, overcurrent protection (current limited each PWM cycle), over temperature protection
- Cooling fan; height 75mm including the cooling fan
- 2 test buttons (A, B)
- LEDs: A, B, OC (overcurrent), ERR (error blink codes), STAT (motor running), PWR
- On/Off switch terminal (shorted by solder bridge by default)
- Warranty: 12 months, manufacturing defects only
- Reverse polarity protection: [NOT STATED]
- Length and width: [NOT STATED]
- Operating temperature: [NOT STATED]
- No reverse polarity protection for Vmotor (product page)
- Size 122 × 178 × 75 mm; wire 2–3 × 8 AWG per terminal (product page)

## Interfaces and compatibility
- Positive and negative supply terminals; Motor Terminal A and B
- Input header (4 pins): pin 1 IN2, pin 2 IN1, pin 3 +5V output, pin 4 Gnd
- Error LED blinks: 2 = Input Error, 3 = Lipo Undervoltage, 4 = Over Voltage, 5 = Over Temperature
- Works with hobby RC transmitter and receiver, potentiometer, joystick or foot pedal with potentiometer, or a microcontroller (PWM, RC-style pulse or UART)
- Two units can operate in mixed mode for a differential drive robot
- Arduino: Cytron Motor Drivers Library (version 1.0.1), PWM_DIR example; driver must be configured as Sign-Magnitude PWM Input mode (DIP 10010001)
- Recommended power sources: 7 – 18 cells NiMH or NiCd; 3 – 6 cells LiPo or Li-Ion; 12V – 24V sealed lead acid; 8V – 28V power supply in parallel with a battery of the same voltage
- 3D CAD files linked on the product page
- Wire size: [NOT STATED]
- Max PWM input frequency: [NOT STATED]

## Use cases
- Drive high power brushed DC motor with current capacity up to 160A continuously
- Drive a robot with differential drive using two units in mixed mode
- Control the motor with a standard hobby radio control transmitter and receiver
- Control the motor with a joystick or foot pedal with potentiometer
- Connect multiple units to a single microcontroller UART port
- Fast test and manual operation with the on board push buttons

## Known limitations
- A power supply that cannot sink current (bench top or AC to DC switching power supply) must be in parallel with a same-voltage battery; otherwise the input voltage might rise to a level where the driver will be destroyed permanently
- Input mode is read only at power-up; change the DIP switch then power cycle
- RC transmitter must be turned on before powering up the driver
- In Analog/PWM mode the stop signal must be present at power-on, else Input Error
- Packetized Serial: allow a one-second delay between applying power and sending the header byte
- +5V pin is an output up to 1A only; do not connect to another 5V source
- LiPo under voltage is a warning only; motor power is not cut
- Current limit drops with board temperature (50A above 110°C)
- Peak and continuous ratings depend on the room temperature
- If the board is off when power is supplied, the SWITCH terminal must be shorted
- Reverse polarity protection: [NOT STATED]

## Positioning (kept apart from specs)
- "one of the latest smart series motor drivers" (user's manual, Aug 2014)
- "MOSFETs are switched at 16 KHz to ensure quiet operation and no annoying whining sound"
- "This make driving a robot with differential drive a truly plug and play experience."

## Price band
RM1,062.60 (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-160amp-8v-28v-smartdrive-dc-motor-driver

## Datasheet
https://docs.google.com/document/d/1nkdj8CrZKoc4PHemBqlvpEJkQ2KjUHGqCTI8S5-mba4/view

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1nkdj8CrZKoc4PHemBqlvpEJkQ2KjUHGqCTI8S5-mba4/view
