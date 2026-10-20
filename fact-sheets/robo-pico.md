# Product fact sheets

## Product name
Robo Pico

## Aliases
ROBO-PICO, RoboPico, Robo Pico Board

## What it is
A robot controller carrier board for the Raspberry Pi Pico / Pico W. The Pico plugs into a socket on the board; there is no microcontroller on the Robo Pico itself.

## Specs and functions
- Product code: ROBO-PICO
- Datasheet: Rev 1.0, April 2023; its spec table is titled "Absolute Maximum Ratings"
- Pi Pico Socket: socket for Raspberry Pi Pico and Pico W
- Power input voltage (USB, LiPo or VIN): 3.6 – 6 V
- Battery: single-cell LiPo / Li-ion, rechargeable via the USB port on the Raspberry Pi Pico / Pico W, protected from over-charge and over-discharge
- VIN terminal: any power source within 3.6 – 6 V
- On/Off switch: turns all power on/off, including the Raspberry Pi Pico; power LED; reset button (resets the Pico)
- DC motor driver: 2 channels, 1 A continuous and 1.5 A peak (< 5 seconds) per channel, PWM frequency max 20 kHz
- Motor pins: M1A = GP8, M1B = GP9, M2A = GP10, M2B = GP11
- Motor truth table: A Low, B Low → Brake; A High, B Low → Forward; A Low, B High → Backward; A High, B High → Hi-Z (Open), Coast
- Motor test buttons (run the motor at full speed: MxA forward, MxB backward) and motor status LEDs
- Servo ports: 4 x RC servo, signal on GP12, GP13, GP14, GP15; V+ equals the power source voltage
- Vmotor & Vservo: USB only → VUSB - 0.4 V; LiPo only or VIN only → VLiPo or VIN; USB + LiPo → VUSB - 0.4 V; USB + VIN: VIN < VUSB → VUSB - 0.4 V, VIN > VUSB and VIN - VUSB < 0.6 V → VIN - 0.4 V, VIN - VUSB > 0.6 V → VIN
- NeoPixel RGB LEDs: on GP18 (2 LEDs in Cytron's example code)
- Programmable buttons: GP20 and GP21
- Piezo buzzer: GP22, with buzzer mute switch
- VBAT sense: solder the jumper on the back to read VBAT on GP28 (ADC2); VADC2 = VBAT / 2 (VBAT = VIN or VUSB or VLiPo, whichever is higher)
- Grove ports: 7; total +3V3 output current 300 mA max
- Grove 1: GP0, GP1 (PWM0, SPI0, I2C0, UART0)
- Grove 2: GP2, GP3 (PWM1, SPI0, I2C1); shared with the Maker Port
- Grove 3: GP4, GP5 (PWM2, SPI0, I2C0, UART1)
- Grove 4: GP16, GP17 (PWM0, SPI0, I2C0, UART0)
- Grove 5: GP6, GP26 (GP26 = ADC0)
- Grove 6: GP26, GP27 (ADC0, ADC1; I2C1)
- Grove 7: GP7, GP28 (GP28 = ADC2)
- Status LEDs for the Grove-port GPIOs (13 pins in Cytron's demo code), on when the GPIO is high
- GPIO breakout: female pin headers for the Pico / Pico W GPIO pins
- Digital input: low -0.3 – 0.8 V, high 2.0 – 3.6 V; digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Operating temperature: -20 – 85 ℃
- Works with Raspberry Pi Pico 2, Pico and Pico W (product page)
- Packing (board only): Robo Pico, 4 Grove-to-female cables, screwdriver, 4 rubber feet; bundles add a Pico 2 SH / Pico H / Pico 2 WH and USB cable (product page)
- Power: USB 5 V, 1-cell LiPo or Vin 3.6–6 V, auto-selected; LiPo charger with over-charge/over-discharge protection (product page)
- RGB LEDs: 2 × WS2812 (Neopixel) (product page pinout image)
- Size: 88 × 72 mm; 4 × Ø4.8 mm + 4 × Ø3 mm holes (product page dimension image)

## Interfaces and compatibility
- Hosts: Raspberry Pi Pico and Raspberry Pi Pico W
- Maker Port: compatible with QWIIC / STEMMA QT / Grove (with conversion cable); pins shared with Grove 2 (GP2, GP3)
- 7 Grove ports, 4 servo ports, 2 DC motor terminals, LiPo battery connector, VIN terminal
- CircuitPython: Pico / Pico W firmware from circuitpython.org; official examples Blink, Button, Buzzer, DC_Motor, Servo_Motor, Analog_Read, NTP_Clock, IoT_Blynk (libraries: neopixel, simpleio, adafruit_motor, adafruit_ntp, adafruit_requests)
- MicroPython: rp2-pico / rp2-pico-w firmware; official examples Blink, Button, Buzzer, DC_Motor, Servo_Motor, Analog_Read, NTP_Clock
- Arduino: arduino-pico core (Earle Philhower) via Boards Manager; official examples Blink, Button, Buzzer, DC_Motor (CytronMotorDriver, PWM_PWM on 8/9 and 10/11), Servo_Motor (Servo.h on 12–15), Analog_Read (pin 27)
- Cytron tutorial: Getting Started Guide with Robo Pico using CircuitPython

## Use cases
- Robotics with Raspberry Pi Pico / Pico W
- Build BocoBot Car with Robo Pico
- Build an RC robot car using Pi Pico W and Robo Pico
- Analog sensor reading (Maker Line / Maker Soil on Grove 6)
- SSD1315 OLED text display over I2C
- NTP clock
- IoT examples: simple HTTP server, ThingSpeak, Blynk

## Known limitations
- No microcontroller on the board; a Raspberry Pi Pico or Pico W is needed
- Datasheet names Pico and Pico W only
- Spec values are absolute maximum ratings
- Pins used by the board: GP8–GP11 (motors), GP12–GP15 (servos), GP18 (NeoPixel), GP20, GP21 (buttons), GP22 (buzzer); GP28 also, when the VBAT sense jumper is soldered
- GP26 is on both Grove 5 and Grove 6
- Grove 2 and the Maker Port share GP2 and GP3
- Grove 7's GP28 doubles as VBAT sense when the jumper is soldered
- Grove 5 (two SDA pins) and Grove 7 (one SCL pin) cannot carry I2C
- Motor current: 1 A continuous, 1.5 A peak for under 5 seconds per channel; PWM max 20 kHz
- A High / B High is coast, not brake; Low / Low is brake. With adafruit_motor, throttle = 0 drives both pins high (coast on this board) and throttle = None drives both low (brake) — the opposite of the comments in Cytron's demo code
- Cytron's MicroPython DC_Motor example labels A-low / B-high as "Forwards", which the datasheet truth table calls Backward
- Motor test buttons run the motor at full speed without any code
- Grove +3V3 total: 300 mA max
- Connecting LiPo and VIN at the same time is not recommended, "Although it's perfectly safe to do so"
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Battery charge current is not stated
- Motor and servo voltage on USB only is VUSB - 0.4 V

## Positioning (kept apart from specs)
- Datasheet tagline: "Simplifying Robotics with Raspberry Pi Pico / Pico W"
- Part of Cytron's Robo series

## Price band
RM59.60–RM109.97 across 4 options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-robo-pico-simplifying-robotics-with-raspberry-pi-pico

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

