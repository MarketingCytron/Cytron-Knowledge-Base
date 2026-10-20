# Product fact sheets

## Product name
Maker Pi RP2040

## Aliases
MAKER-PI-RP2040, Cytron Maker Pi RP2040, Maker Pi RP2040: Simplifying Robotics with Raspberry Pi RP2040

## What it is
A robot controller board with the Raspberry Pi RP2040 microcontroller soldered on the board. It has a 2-channel DC motor driver, 4 servo ports and 7 Grove ports.

## Specs and functions
- Product code: MAKER-PI-RP2040
- Datasheet: Rev 1.2, January 2022; its spec table is titled "Absolute Maximum Ratings"
- MCU (product page): Raspberry Pi RP2040, dual-core Arm Cortex-M0+, 264KB internal RAM, 2MB of Flash memory, "the exact same specifications with Raspberry Pi Pico"
- Power input voltage (USB, LiPo or VIN): 3.6 – 6 V
- Power sources: Micro USB, single-cell LiPo / Li-Ion connector, VIN terminal (any power source within 3.6 - 6V); product page: "Automatic power selection: USB 5V, LiPo (1-cell) or Vin (3.6-6V)"
- Battery: rechargeable via USB, protected from overcharge and over-discharge; product page: built-in 1-cell LiPo/Li-Ion charger
- On/Off switch, power LED, reset button (resets the RP2040), boot button (hold while resetting to enter bootloader mode), debug port
- DC motor driver: 2 channels, 1 A continuous and 1.5 A peak (< 5 seconds) per channel, PWM frequency max 20 kHz
- Product page: controls 2x brushed DC motors or 1x bipolar/unipolar stepper motor
- Motor pins: M1A = GP8, M1B = GP9, M2A = GP10, M2B = GP11
- Motor truth table: A Low, B Low → Brake; A High, B Low → Forward; A Low, B High → Backward; A High, B High → Hi-Z (Open), Coast
- Motor test buttons (motor runs at full speed: MxA forward, MxB backward) and motor status LEDs
- Servo ports: 4 x RC servo, signal on GP12, GP13, GP14, GP15; V+ equals the power source voltage
- Vmotor & Vservo: USB only → VUSB - 0.4 V; LiPo only or VIN only → VLiPo or VIN; USB + LiPo → VUSB - 0.4 V; USB + VIN: VIN < VUSB → VUSB - 0.4 V, VIN > VUSB and VIN - VUSB < 0.6 → VIN - 0.4 V, VIN - VUSB > 0.6 → VIN
- RGB LEDs: WS2812B on GP18 (product page: 2x RGB LED (Neopixel))
- Programmable buttons: GP20 and GP21
- Piezo buzzer: GP22, with buzzer mute switch
- Grove ports: 7; total +3V3 output current 300 mA max
- Grove 1: GP0, GP1 (PWM0, SPI0, I2C0, UART0)
- Grove 2: GP2, GP3 (PWM1, SPI0, I2C1)
- Grove 3: GP4, GP5 (PWM2, SPI0, I2C0, UART1)
- Grove 4: GP16, GP17 (PWM0, SPI0, I2C0, UART0)
- Grove 5: GP6, GP26 (GP26 = ADC0)
- Grove 6: GP26, GP27 (ADC0, ADC1; I2C1)
- Grove 7: GP7, GP28 (GP28 = ADC2)
- GPIO status LEDs: 13, for the Grove-port GPIOs (GP0–7, GP16, GP17, GP26–28), on when the GPIO is high
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃
- USB VID & PID (CircuitPython & Arduino Core): VID 0x2E8A, PID 0x1000
- Product page: dimensions 88mm(L) x 64mm(W) x 13mm(H); 4x 4.8mm mounting hole (LEGO® pin compatible); 6x M3 screw hole
- Packing: board, 4 Grove-to-female cables, mini screwdriver, 4 rubber feet (product page)
- Size 88 × 64 × 13 mm; 4 × 4.8 mm LEGO-pin holes and 6 × M3 holes (product page)

## Interfaces and compatibility
- Micro USB (upload programs and power), LiPo battery connector, VIN terminal, 2 DC motor terminals, 4 servo ports, 7 Grove ports, debug port
- CircuitPython: preloaded with a demo program; board-specific firmware at circuitpython.org/board/cytron_maker_pi_rp2040 with adafruit_motor, neopixel and simpleio built in; the Raspberry Pi Pico CircuitPython firmware also works if those libraries are added manually
- Bootloader: hold BOOT and press RST to get the RPI-RP2 drive, then copy the .uf2 file
- MicroPython and C/C++ for Pico/RP2040
- Arduino: datasheet lists the USB VID/PID for the Arduino Core; product page points to Arduino's official news
- Product page: "Software, firmware, libraries and resources that are developed for Pico should work seamlessly"
- Wi-Fi: product page suggests adding a Grove WiFi 8266 module via a Grove port
- Compatible accessory (product page): USB Micro B cable

## Use cases
- Robotics with the Raspberry Pi RP2040
- DIY robot / motion control projects
- Driving 2 brushed DC motors or 1 bipolar/unipolar stepper motor
- Driving up to 4 RC servo motors
- Connecting Grove modules (digital, analog, I2C, SPI, UART)

## Known limitations
- Spec values are absolute maximum ratings
- Power input range is 3.6 – 6 V; motor and servo voltage equals the power input voltage (VUSB - 0.4 V on USB only)
- Motor current: 1 A continuous, 1.5 A peak for under 5 seconds per channel; PWM max 20 kHz
- Pins used by the board: GP8–GP11 (motors), GP12–GP15 (servos), GP18 (RGB), GP20, GP21 (buttons), GP22 (buzzer)
- GP26 is on both Grove 5 and Grove 6
- Grove 5 and Grove 7 cannot carry I2C
- Grove +3V3 total: 300 mA max
- A High / B High is coast, not brake; Low / Low is brake. With adafruit_motor, throttle = 0 drives both pins high (coast on this board) and throttle = None drives both low (brake) — the opposite of the comments in Cytron's demo code
- Motor test buttons run the motor at full speed without any code
- Connecting LiPo and VIN at the same time is not recommended, "Although it's perfectly safe to do so"
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Battery charge current is not stated
- No onboard Wi-Fi

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Robotics with Raspberry Pi® RP2040"
- Product page: "Cytron Maker Pi RP2040 is basically the Raspberry Pi Pico + Maker series' goodness"
- Cytron internal: "very well received among the users", launched in Jun 2021

## Price band
RM50.40 (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-maker-pi-rp2040-simplifying-robotics-with-raspberry-pi-rp2040

## Datasheet
https://docs.google.com/document/d/1DJASwxgbattM37V4AIlJVR4pxukq0up25LppA8-z_AY/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1DJASwxgbattM37V4AIlJVR4pxukq0up25LppA8-z_AY/edit
