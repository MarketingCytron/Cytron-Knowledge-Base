# Product fact sheets

## Product name
IRIV IOC MQTT Gateway

## Aliases
IRIV-IOC-MQTT, IRIV IOC MQTT Gateway, IOC MQTT Gateway, IRIV IOC MQTT, IOC MQTT, IRIV IO Controller MQTT Gateway

## What it is
An IRIV IO Controller (Raspberry Pi RP2350A industrial I/O controller) that ships preloaded from the factory with Cytron's MQTT Gateway Firmware. It sends its I/O and Modbus RTU data to an MQTT broker over Ethernet, and it is configured from a web page without coding.

## Specs and functions
- Datasheet: Rev 1.0, June 2026
- Status: on sale on my.cytron.io, RM334.95 (read 2026-10-19)
- Firmware: MQTT Ready Gateway, preloaded from the factory; uses standard MQTT (Port 1883)
- Factory reset: hold the user button for 10 seconds during boot until the buzzer beeps; configuration is wiped, licence is preserved
- USR LED network status: Slow Blink = Ethernet down; Solid On = Ethernet up, MQTT disabled; Single Pulse every 1.5s = Ethernet up, MQTT enabled but not reachable; Two Pulses every 3s = Ethernet up, MQTT connected
- Microcontroller: Raspberry Pi RP2350A, Dual Cortex-M33 @ 150MHz
- RAM: 520KB on-chip SRAM
- Storage: 2MB flash memory
- Power input, Terminal 1: 10 – 30 VDC (Surge Protected up to 60V 20ms), protected by a 500 mA PTC
- Power input, USB-C: 4.9 – 5.2 VDC
- Power consumption: max 0.7 W
- 11x isolated digital input (up to 50V), active high, in two groups: Group 1 DI0–DI4 (common S/S0..4), Group 2 DI5–DI10 (common S/S5..10)
- Digital input levels: VIL max ±0.8 V; VIH ±3 to ±50 V; maximum pulse frequency 5000 Hz (50% duty cycle); isolation 3750 Vrms
- 4x isolated digital output: dry contact, solid state relay, DC or AC load, max 50 V, max 500 mA, isolation 1500 Vrms
- 2x 12-bit analog input, non-isolated: voltage mode 0 – 10.56 V (input impedance 32K Ω), current mode 0 – 42.58 mA (input impedance 248 Ω)
- 1x isolated RS485: maximum baud rate 500 kbps, isolation 5000 Vrms, automatic direction control, switchable 120 Ω termination resistor
- 1x RJ45 Ethernet via Wiznet W5500: 10BaseT/100BaseTX, auto negotiation, hardwired TCP/IP (TCP, UDP, ICMP, IPv4, ARP, IGMP, PPPoE), 8 independent sockets, 32Kbytes Tx/Rx buffer memory
- PCF85063A Real Time Clock (I2C 0x51), not used by the MQTT Gateway firmware
- 1x reset button, 1x boot button (both pinhole), 1x user button
- 1x user LED (USR); status LEDs for PWR, RS485, DOUT 0-3 and DIN 0-10
- 1x passive buzzer
- Pin mapping: DI0–DI10 = GP0–GP10; AN0/AN1 = GP26/GP27; DO0–DO3 = GP12–GP15; RS485 UART1 TX GP24 / RX GP25; W5500 SPI0 MOSI GP19, MISO GP20, SCK GP22, CSn GP21, INT GP18, RESET GP23; RTC I2C0 SDA GP16 / SCL GP17; user button GP28; user LED GP29; buzzer GP11
- Operating temperature: -20 to 70 ℃
- Relative humidity: 10 – 80 % (non-condensing)
- Enclosure: metal, fanless design, DIN rail mountable
- Dimension: (L)140mm x (W)60mm x (H)36mm (metal enclosure only, excluding DIN socket & connectors); DIN bracket adds 8mm, terminals add 15.5mm
- Setup: USB-C PROG → USB network → web UI 10.0.0.1; change the default password before enabling Ethernet config (Cytron tutorial)
- Topics: Base Topic + di/, do/…/state, do/…/cmd (1/ON, 0/OFF), ai/, mbpoll/, mbwrite/ and …/confirm; QoS 0–2 and Retain per channel (Cytron tutorial)
- Modbus RTU master: up to 32 poll jobs, write jobs FC5/FC6/FC16, scaling and byte order (Cytron tutorial)
- Firmware update via web UI or BOOTSEL (.uf2 to the RP2350 drive); factory reset by holding User button at power-on until beep (Cytron tutorial)
- RTC is not used by the MQTT firmware (product page)

## Interfaces and compatibility
- Differences from the IRIV IO Controller: factory MQTT Gateway firmware that must not be overwritten; the user button does a factory reset; the USR LED shows network/MQTT status; the buzzer beeps on factory reset; the RTC is not used; USB-C is used for configuration
- Terminal 1 (pluggable): V-, V+ (10-30V), DGND, S/S0..4, DI0–DI4, RS485 A / B / G, AGND ×2, AN0, AN1
- Terminal 2 (pluggable): DGND, S/S5..10, DI5–DI10, DO0–DO3 (two contacts each)
- Bottom DIP switches: RS485 R-Term (120 Ω termination), AN-IN MODE (voltage/current)
- USB-C for configuration and power
- MQTT broker: standard MQTT on port 1883
- RS485 for Modbus RTU field devices
- Digital inputs accept dry contact, PNP and NPN sensors; PNP and NPN can be used at the same time on different groups
- No earth connection required
- 3D CAD: same as IRIV IOC

## Use cases
- Remote Asset & Utility Monitoring: tracking flow meters, pumps and environmental sensors across geographically distributed water or energy grids over cellular networks
- Factory Floor Digitalization: aggregating machine health parameters, production cycle counts and downtime alerts to feed predictive maintenance dashboards
- Smart Facilities & Building Automation: centralizing HVAC performance, energy sub-metering and safety alarms across a corporate or university campus into a unified cloud interface
- Sending field data to a server for processing and visualization out of the box, for software/IT users not familiar with hardware or firmware

## Known limitations
- Uses standard MQTT (Port 1883) with no TLS/SSL on the device; for cloud encryption, route the data through a local secure broker or edge gateway
- Preloaded MQTT Gateway firmware must not be erased or overwritten with other firmware; it is licence-locked to the CPU ID
- The RTC is not used by the MQTT Gateway firmware
- Analog inputs are not isolated (AGND is shared with system GND)
- Analog full scale is 10.56 V (voltage mode) or 42.58 mA (current mode)
- Digital output max 50 V, 500 mA per channel; a flyback diode is recommended for inductive loads
- Digital input max pulse frequency 5000 Hz (50% duty cycle)
- RS485 max 500 kbps; termination is only for the first and last device on the bus
- Terminal 1 power input is protected by a 500 mA PTC that may open on surge or overcurrent; the unit must cool down before it powers up again
- Power input 10 – 30 VDC on Terminal 1, or 4.9 – 5.2 VDC on USB-C
- Operating temperature -20 to 70 ℃; humidity 10 – 80 % non-condensing
- 2MB flash, 520KB SRAM
- RTC backup needs a CR2032 coin cell inserted by the user
- Web UI first reached over USB (10.0.0.1); password change forced before Ethernet configuration; MQTT port 1883, no TLS (Cytron tutorials)

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 Industrial I/O Controller"

## Price band
RM334.95 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-iriv-io-controller-mqtt-ir4.0-industrial-i-o-controller-with-mqtt-ready

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

