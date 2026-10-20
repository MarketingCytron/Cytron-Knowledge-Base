# Product fact sheets

## Product name
Industrial IO HAT+

## Aliases
HAT-IND-AG, IR4.0 Industrial I/O HAT+, Industrial I/O HAT+, Industrial IO HAT+ for Raspberry Pi 5, IO HAT+

## What it is
An industrial I/O HAT+ for the Raspberry Pi 5 that adds RS485, RS232, isolated digital inputs and isolated digital outputs, and powers the Pi from a 10–30 VDC supply. It is a HAT, not a computer, and needs a Raspberry Pi 5 (not included).

## Specs and functions
- Datasheet: Rev 1.0, Sep 2025
- Host: Raspberry Pi 5
- Raspberry Pi HAT+ compliant, with EEPROM that lets Raspberry Pi OS recognise the HAT+ and tells the Pi 5 the HAT+ can supply 5A (needs bootloader version 2025-06-29 or greater)
- Power input: 10 – 30 VDC, surge protected up to 60V 20ms
- Maximum current for Raspberry Pi (5V): 5 A
- 4A replaceable fuse for the system
- 1x RS485: max baud rate 1 Mbps, automatic direction control, onboard 120 ohm termination resistor, mapped to UART0 (TX GPIO14, RX GPIO15)
- 1x RS232: max baud rate 250 kbps, mapped to UART4 (TX GPIO12, RX GPIO13)
- 6x isolated bidirectional digital input (up to 50V), sharing one common pin (DIC), for PNP or NPN sensors
- Digital input levels: VIL max ±0.8 V; VIH ±3 to ±50 V; isolation 3750 Vrms
- 4x isolated digital output (up to 50V), sharing one common pin (DOC): dry contact, driven by solid state relays, DC or AC load up to 50V 500mA, isolation 1500 Vrms, built-in surge protection
- 2x programmable LED: LED0 GPIO17, LED1 GPIO18
- 1x programmable active buzzer: GPIO23, active high
- Status LEDs for RS485, RS232, DI 0-5 and DO 0-3
- 5V display power connector
- Header pins for the optional LetsTrust TPM module (TPM 2.0, from pi3g)
- Pin mapping: DI0–DI5 = GPIO4, GPIO5, GPIO6, GPIO16, GPIO22, GPIO27; DO0–DO3 = GPIO19, GPIO20, GPIO21, GPIO26; TPM RSTn GPIO24, IRQn GPIO25, CS0n GPIO8, CS1n GPIO7, SPI MISO GPIO9, MOSI GPIO10, SCK GPIO11
- Operating temperature: -20 to 60 ℃
- Relative humidity: 10 – 80 % (non-condensing)
- Dimensions: [NOT STATED]
- Packing: HAT, 20-pin pluggable terminal block, 3 M2.5 × 21 mm PCB stands, pinout sticker (product page)
- Designed for the Argon40 Industria Case; LetsTrust TPM supported (product page)

## Interfaces and compatibility
- Connects to the Raspberry Pi 5 40-pin GPIO header
- Pluggable IO terminal (20-pin pluggable terminal block included) for power input, RS485, RS232, DI and DO
- Enable RS485 with dtoverlay=uart0 and RS232 with dtoverlay=uart4 in /boot/firmware/config.txt
- RS485 supports Modbus RTU
- Enclosures: Argon Industria HMI 10CS, HMI 8CS, HMI 7C, HMI 5C and Argon Industria Basic Industrial Enclosure, all for Raspberry Pi 5
- Optional LetsTrust TPM module, supported directly by the Linux kernel TPM subsystem
- In the box: 1x Industrial IO HAT+, 1x 20-pin pluggable terminal block, 3x M2.5*21mm PCB stand, 1x sticker for pinout
- Also sold in Argon40 Industria HMI complete kits with display, Industrial IO HAT+ and 16GB Raspberry Pi 5 (5", 7", 8", 10")
- No earth connection required

## Use cases
- Greenhouse environment monitoring (temperature, humidity, soil moisture and nutrients, luminescence)
- Factory monitoring system
- Production line monitoring system
- Defect detection dashboard

## Known limitations
- Supports Raspberry Pi 5 only
- Digital inputs and outputs are limited to 50V; outputs max 500mA
- Digital outputs are dry contact: the load needs its own supply; a flyback diode is recommended for inductive loads to reduce EMI
- All six inputs share one common (DIC); all four outputs share one common (DOC)
- RS485 max 1 Mbps; RS232 max 250 kbps
- UART0 and UART4 must be enabled with dtoverlay lines in config.txt
- RS485 works with A-B only, but connecting GND is recommended for better noise immunity
- The 4A fuse might break on surge or overcurrent; if the device does not power up, check and replace the fuse
- The HAT+ 5A recognition needs Pi 5 bootloader version 2025-06-29 or greater
- With the TPM module fitted, GPIO7–GPIO11, GPIO24 and GPIO25 are used by the TPM
- Operating temperature -20 to 60 ℃; humidity 10 – 80 % non-condensing
- Raspberry Pi and enclosure not included

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 Industrial I/O HAT+"
- Co-developed with Argon40 for the Argon Industria HMI enclosures for Raspberry Pi 5
- Target audience: industrial engineers, training providers (SHRDC), system integrators, industrial AI system integrators
- Cytron tagline: "Simplifying Digital Making"

## Price band
RM138.60 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-industry-hat-plus-for-raspberry-pi-5

## Datasheet
https://docs.google.com/document/d/1G8XOqDg5tSYu-hFeNG1x2qfTjAIdBlXN-yGC49WR2nQ/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1G8XOqDg5tSYu-hFeNG1x2qfTjAIdBlXN-yGC49WR2nQ/edit
