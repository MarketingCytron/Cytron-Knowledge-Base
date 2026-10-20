# Product fact sheets

## Product name
Maker Uno RP2040

## Aliases
MAKER-UNO-RP2040, Cytron Maker Uno RP2040, MakerUnoRP2040, Uno RP2040

## What it is
A development board in the Arduino UNO form factor built around the Raspberry Pi RP2040 (dual-core ARM Cortex-M0+). It uses 3.3 V logic and has onboard Grove ports, servo ports, LEDs, a buzzer and a LiPo charger.

## Specs and functions
- Product code: MAKER-UNO-RP2040
- Datasheet: Rev 1.0, February 2024; its spec table is titled "Absolute Maximum Ratings"
- MCU: Raspberry Pi RP2040, dual-core ARM Cortex-M0+, up to 133 MHz, 264 KB SRAM
- Flash: 2 MB (Winbond W25Q16JVUXIQ per schematic; not stated in the datasheet)
- USB Type-C: for both powering and programming the board from a PC
- Power input voltage (USB or LiPo/Li-Ion): 3.6 – 6 V
- Nominal sources: LiPo / Li-Ion 3.7V (single cell only) or USB-C 5V
- Battery: 2-pin JST-PH connector for a single-cell LiPo / Li-Ion battery, rechargeable via USB, protected from overcharge and over-discharge; charging LED on while charging, off when full
- On/Off slide switch; power LEDs for 3.3V and 5V
- Total +3V3 output current: 500 mA max; total +5V output current: 600 mA max
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.62 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃
- USB VID & PID (CircuitPython & Arduino Core): VID 0x2E8A, PID 0x1071
- Reset button; Boot button (hold while resetting to enter bootloader mode)
- User programmable button: GP2
- Piezo buzzer: GP8, with buzzer mute switch on the bottom layer
- RGB LEDs: 2x WS2812B on GP25
- GPIO status LEDs: 16 (GP0–GP13, GP20, GP21), on when the GPIO is high; can be disabled by cutting a solder jumper (closed by default)
- Servo ports: 4 x RC servo, signal on GP14, GP15, GP16, GP17
- Vservo: USB only → VUSB - 0.4 V; LiPo/Li-Ion only → VBAT; USB and LiPo/Li-Ion → VUSB - 0.4 V
- Grove ports: 6 (4-pin, 2.0 mm pitch), 3.3V power pin
- Grove 1: GP0, GP1 (PWM0, SPI0, I2C0, UART0)
- Grove 2: GP4, GP5 (PWM2, SPI0, I2C0, UART1)
- Grove 3: GP6, GP26 (GP26 = ADC0)
- Grove 4: GP7, GP27 (GP27 = ADC1)
- Grove 5: GP28, GP29 (ADC2, ADC3; I2C0; UART0)
- Grove 6: GP20, GP21 (I2C0 SDA0/SCL0; UART1)
- Maker Port: JST-SH 4-pin, GP20 / GP21, shared with Grove 6
- SPI header (2x3 male): MISO GP12, SCK GP10, MOSI GP11, 5V, RESET, GND
- Analog inputs: A0–A3 = GP26–GP29 (ADC0–ADC3)
- Peripherals: 2x I2C, 2x SPI, 2x UART, 16 PWM (8 slices x 2 outputs)
- Onboard ICs (schematic): MCP73831T-2ACI/OT charger, MT3608 5 V boost, AP1117E33L 3.3 V regulator, 12 MHz crystal
- Packing list: 1x Maker Uno RP2040, 1x Silicone Rubber Feet (pack of 4), 4x Grove to female header cable
- 2 MB flash, 2 × WS2812 RGB LEDs, 16 status LEDs (product page)
- Variants: Edu Bundle with Bahasa Malaysia teacher's guide (softcopy) and component set, or board only with 4 Grove-to-female cables and rubber feet (product page)

## Interfaces and compatibility
- Arduino UNO form factor; use 3.3 V-compatible UNO shields only
- Digital header order (from USB end): GP21 (SCL), GP20 (SDA), NC, GND, GP10, GP12, GP11, GP13, GP9, GP8 | GP7, GP6, GP5, GP4, GP3, GP2, GP0, GP1
- Power header order: NC, IOREF, RESET, 3.3V, 5V, GND, GND, "~5V out"
- Analog header: A0 GP26, A1 GP27, A2 GP28, A3 GP29, SDA GP20, SCL GP21
- Maker Port: compatible with QWIIC / Stemma QT / Grove (with conversion cable)
- Arduino IDE 2: Earle F. Philhower "Raspberry Pi Pico/RP2040" core, Boards Manager URL https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json, board "Cytron Maker Uno RP2040"
- CircuitPython: board id cytron_maker_uno_rp2040 (circuitpython.org); Thonny variant "Cytron Technologies • Maker Uno RP2040"
- MicroPython: no custom Cytron firmware yet; Cytron points to the Pico (rp2-pico) MicroPython firmware
- Cytron example code (Arduino, CircuitPython, MicroPython) in the CytronTechnologies/Cytron-MAKER-UNO-RP2040 GitHub repo
- Accessories used in Cytron examples: TS90A micro servo, Maker Soil Sensor, ultrasonic ranging module, SSD1306 0.96" I2C OLED

## Use cases
- Programming with Arduino IDE, CircuitPython or MicroPython in the Uno form factor
- Plug-and-play Grove and Maker Port sensors and modules
- Driving up to 4 servo motors from the onboard servo ports
- Portable projects powered by a single-cell LiPo / Li-Ion battery
- Offline Dino Game Cheat with Maker Uno RP2040
- DHT11 sensor data logging
- Playing a game using a joystick
- Cytron tutorial: [DHT11 Sensor Data Logging using Maker Uno RP2040](https://my.cytron.io/tutorial/data-logging-maker-uno-rp2040)
- Cytron tutorial: [Getting Started with Maker Uno RP2040](https://my.cytron.io/tutorial/getting-started-guide-with-maker-uno-rp2040)
- Cytron tutorial: [Play Game using Joystick on Maker Uno RP2040](https://my.cytron.io/tutorial/joystick-maker-uno-rp2040)
- Cytron tutorial: [Offline Dino Game Cheat with Maker Uno RP2040](https://my.cytron.io/tutorial/offline-dino-game-cheat-with-maker-uno-rp2040)
- Cytron tutorial: [Maker UNO RP2040 Project Collection 2024](https://my.cytron.io/tutorial/maker-uno-rp2040-project-collection-2024)

## Known limitations
- 3.3 V logic: digital input high max 3.6 V, analog input 0 – 3.3 V; not for 5 V shields or 5 V signals
- Spec values are absolute maximum ratings
- Power inputs are only USB Type-C and the LiPo/Li-Ion connector (3.6 – 6 V); no DC jack or VIN input
- The UNO VIN position is labelled "~5V out"; the AREF position is NC
- Code pin numbers are GP numbers; the D10–D13 positions carry GP10, GP12, GP11, GP13 and the D1/D0 positions carry GP0/GP1
- Only 4 analog inputs (GP26–GP29)
- Servo voltage equals the power-source voltage (VUSB - 0.4 V on USB, VBAT on battery only); servo current limit not stated
- Total +3V3 output 500 mA max; total +5V output 600 mA max
- Shared PWM channels cannot run PWM at the same time: GP0/GP16 (Servo 3), GP1/GP17 (Servo 4), GP4/GP20, GP5/GP21, GP10/GP26, GP11/GP27, GP12/GP28, GP13/GP29, GP9/GP25
- Grove 6, the Maker Port and header SDA/SCL all use GP20/GP21
- Grove 3 and Grove 4 cannot carry I2C (two SDA or two SCL pins each)
- Mute the buzzer if GP8 is used for other purposes
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Battery charge current not stated
- Switch the board on before entering bootloader mode; the COM port may need reselecting after each upload
- The datasheet does not state the flash size or the RGB LED count

## Positioning (kept apart from specs)
- Brings the Raspberry Pi RP2040 into the familiar Uno form factor while keeping its user-friendly nature
- Large flash makes CircuitPython and MicroPython possible on an Uno-style board
- Maker series features: onboard LEDs for troubleshooting, programmable buzzer and button, Grove and Maker ports for plug-and-play connections
- Follows the move from 5V to 3.3V microcontrollers

## Price band
RM62.58 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-maker-uno-rp2040

## Datasheet
https://docs.google.com/document/d/16RTRPaV0Xaqg3xKwM89iMkXrDB8T_pBjCKYHOadv_Z4/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/16RTRPaV0Xaqg3xKwM89iMkXrDB8T_pBjCKYHOadv_Z4/edit
