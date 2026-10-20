# Product fact sheets

## Product name
IRIV IO Controller

## Aliases
IRIV-IOC, IRIV IOC, IRIV IO Controller, IRIV I/O Controller, IR4.0 Industrial I/O Controller

## What it is
An industrial I/O controller in a fanless metal DIN-rail enclosure, built on the Raspberry Pi RP2350A microcontroller. It is a standalone microcontroller device, not a Raspberry Pi computer or Compute Module, and it runs no Linux OS.

## Specs and functions
- Product code: IRIV-IOC
- Datasheet: Rev 1.0, July 2024
- Microcontroller: Raspberry Pi RP2350A, Dual Cortex-M33 @ 150MHz
- RAM: 520KB on chip SRAM
- Storage: 2MB flash memory
- Power input, Terminal 1: 10 – 30 VDC (surge protected up to 60V 20ms), protected by a 500mA PTC
- Power input, USB-C: 4.9 – 5.2 VDC
- Power consumption: max 0.7 W
- 11x isolated digital input (up to 50V), active high, in two groups: Group 1 DI0–DI4 (common S/S0..4), Group 2 DI5–DI10 (common S/S5..10)
- Digital input levels: VIL max ±0.8 V; VIH ±3 to ±50 V; max pulse frequency 5000 Hz (50% duty cycle); isolation 3750 Vrms
- Built-in isolated power source for dry contact inputs (no external supply needed)
- 4x isolated digital output: dry contact, solid state relay, DC or AC load, max 50 V, max 500 mA, isolation 1500 Vrms, active high, isolated from the system and from each other
- 2x 12-bit analog input, non-isolated (AGND shared with system GND): voltage mode 0 – 10.56 V (input impedance 32K Ω), current mode 0 – 42.58 mA (input impedance 248 Ω)
- Analog voltage scaling to MCU: MCU = AN × 5/16
- 1x isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, switchable 120 Ω termination resistor
- 1x RJ45 Ethernet via Wiznet W5500: 10BaseT/100BaseTX, auto negotiation (full/half duplex), hardwired TCP/IP (TCP, UDP, ICMP, IPv4, ARP, IGMP, PPPoE), 8 independent sockets, 32Kbytes Tx/Rx buffer memory, power down mode, Wake on LAN over UDP, SPI up to 80MHz
- PCF85063A Real Time Clock, I2C address 0x51, CR2032 coin cell keeps it running when powered off
- 1x reset button, 1x boot button (both pinhole), 1x programmable button
- 1x programmable LED; status LEDs for PWR, RS485, DOUT 0-3 and DIN 0-10
- 1x passive buzzer (variable frequency tone or melody)
- Pin mapping: DI0–DI10 = GP0–GP10; AN0/AN1 = GP26/GP27; DO0–DO3 = GP12–GP15; RS485 UART1 TX GP24 / RX GP25; W5500 SPI0 MOSI GP19, MISO GP20, SCK GP22, CSn GP21, INT GP18, RESET GP23; RTC I2C0 SDA GP16 / SCL GP17; user button GP28 (active low); user LED GP29; buzzer GP11 (GPIO/PWM)
- Operating temperature: -20 to 70 ℃
- Relative humidity: 10 – 80 % (non-condensing)
- Enclosure: metal, fanless design, DIN rail mountable
- Dimension: (L)140mm x (W)60mm x (H)36mm (metal enclosure only, excluding DIN socket & connectors); DIN bracket adds 8mm, terminals add 15.5mm
- Packing: controller + mini flat screwdriver (product page)
- Example code: github.com/CytronTechnologies/Cytron-IRIV-IO-Controller; CircuitPython getting-started tutorial (product page)

## Interfaces and compatibility
- Terminal 1 (pluggable): V-, V+ (10-30V), DGND, S/S0..4, DI0–DI4, RS485 A / B / G, AGND ×2, AN0, AN1
- Terminal 2 (pluggable): DGND, S/S5..10, DI5–DI10, DO0–DO3 (two contacts each)
- Bottom DIP switches: RS485 R-Term (120 Ω termination), AN-IN MODE (voltage/current, drawn with separate AN0 and AN1 switches)
- USB-C for programming, configuration and power
- Digital inputs accept dry contact, PNP and NPN sensors; PNP and NPN can be used at the same time on different groups
- Ethernet communication: OT (MODBUS TCP) and IT (MQTT/HTTP)
- RS485 for MODBUS RTU
- CircuitPython: official board build "IRIV IO Controller (RP2350)" on circuitpython.org, installed as a UF2 file
- Programming: hold BOOT while resetting to enter the bootloader, then drag and drop the UF2 file
- Cytron tutorial: Getting Started with IRIV IO Controller with CircuitPython
- No Compute Module, Raspberry Pi board or HAT is used; the RP2350A is on board
- No earth connection required

## Use cases
- Lightweight automation
- Industrial I/O expansion
- MODBUS RTU/TCP gateways
- Data acquisition and sensor monitoring
- Edge control systems
- Pulse counting from flow meters, energy meters and rotary encoders, with running totals in Modbus registers polled by a PLC, SCADA or dashboard
- IoT gateway to Blynk, ThingSpeak and MQTT
- Agricultural automation

## Known limitations
- Analog inputs are not isolated (AGND is shared with system GND)
- Analog full scale is 10.56 V (voltage mode) or 42.58 mA (current mode)
- Digital output max 50 V, 500 mA per channel; a flyback diode is recommended for inductive loads to reduce EMI
- Digital input max pulse frequency 5000 Hz (50% duty cycle)
- RS485 max 500 kbps; termination is only for the first and last device on the bus
- Terminal 1 power input is protected by a 500mA PTC that may open on surge or overcurrent; the unit must cool down before it powers up again
- Power input 10 – 30 VDC on Terminal 1, or 4.9 – 5.2 VDC on USB-C
- Operating temperature -20 to 70 ℃; humidity 10 – 80 % non-condensing
- Microcontroller device: does not run Linux, Raspberry Pi OS or Node-RED on the unit
- 2MB flash, 520KB SRAM
- RTC backup needs a CR2032 coin cell inserted by the user

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 Industrial I/O Controller"
- Cytron tagline on the datasheet: "Simplifying Digital Making"
- Staff wiki: "designed for lightweight automation solutions in Industry 4.0 applications"
- Cytron video framing: counts pulses reliably, with debouncing, and runs continuously without needing a PLC. Running totals sit in Modbus registers. You do not need a full PLC just to count pulses, and setup time and cost are lower

## Price band
RM303.45 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-iriv-io-controller

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

