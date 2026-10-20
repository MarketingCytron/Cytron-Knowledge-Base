# Product fact sheets

## Product name
EDU PICO V2 – EDU Project & Innovation Kit for Pico 2 W

## Aliases
EDU PICO V2, EDU PICO 2, EDU-PICO2, EDU-PICO2-NB, EDUPICO2, EDU PICO 2: Project & Innovation Kit for Pico 2W, EDU Project & Innovation Kit for Pico 2 W

## What it is
A project and innovation board for the Raspberry Pi Pico 2 W with built-in sensors, display, audio, motor driver, servo ports and a USB relay. The Pico 2 W plugs into a socket on the board and is included in the kit, except in the EDU-PICO2-NB variant.

## Specs and functions
- Board name in datasheet: EDU-PICO2; variant EDU-PICO2-NB ships without the Raspberry Pi Pico 2 W
- Datasheet: Rev 1.1, June 2026; its spec table is titled "Absolute Maximum Ratings"
- Pi Pico socket: 2×20 female pin headers for the Pico 2 / Pico 2 W (inner rows); outer rows break out the GPIO pins
- Pico chip: RP2350 (EDU PICO hub)
- Power input voltage (USB, LiPo or VIN): 3.6 – 6 V
- Vin terminal: 3.6 V – 6 V, fits wires up to 18 AWG
- Battery: JST-PH 2-pin, single-cell LiPo or Li-ion; built-in charger, rechargeable via the USB port of the Raspberry Pi Pico 2 / Pico 2 W; protected from over-charge and over-discharge
- Charging LED, Power LED, On/Off switch (also powers the Pico), Reset button
- Digital input: low -0.3 – 0.8 V, high 2.0 – 5.5 V, with the datasheet footnote "Only Pico 2 / Pico 2 W boards with RP2340-A4 stepping support 5 V-tolerant digital GPIO pins."
- Digital output: low 0 – 0.5 V, high 2.6 – 3.3 V; analog input 0 – 3.3 V
- Push buttons: Button A = GP0, Button B = GP1; pulled HIGH, LOW when pressed
- RGB LEDs: 5× addressable SK6812-based, WS2812B compatible, on GP14
- I2C bus: SDA = GP4, SCL = GP5
- Temperature & humidity sensor: AHT20, I2C 0x38
- Colour & light sensor: OPT4048, I2C 0x44
- OLED display: 0.96 inch 128x64 white, SSD1315, I2C 0x3C
- Gesture & proximity sensor: PAJ7620, I2C 0x73
- PDM microphone: MP34DT01, DOUT = GP2, CLK = GP3
- Potentiometer: GP28 (ADC2)
- Stereo audio jack: Right = GP20, Left = GP21; non-amplified, for earphone or amplified speaker
- Audio/Buzzer switch: selects left-channel audio out or the piezo buzzer
- Piezo buzzer: datasheet says GP8; Cytron's EDU PICO 2 code (GitHub) uses GP21
- Servo ports: 4× RC servo, signal GP6, GP7, GP8, GP9; V+ equals power source voltage
- DC motor driver: 2 channels, locked-antiphase (dual-PWM); M1A = GP10, M1B = GP11, M2A = GP12, M2B = GP13; terminals fit wires up to 18 AWG
- Motor current per channel: 1 A continuous, 1.5 A peak (< 5 seconds); PWM frequency max 20 kHz
- Motor truth table: A Low, B Low → Brake; A High, B Low → Forward; A Low, B High → Backward; A High, B High → Hi-Z (Open), Coast
- Motor test buttons (run the motor at full speed) and red motor status LEDs
- Vmotor & Vservo: USB only → VUSB - 0.4 V; LiPo only or VIN only → VLiPo or VIN; USB + LiPo → VUSB - 0.4 V; USB + VIN: VIN < VUSB → VUSB - 0.4 V, VIN > VUSB and VIN - VUSB < 0.6 → VIN - 0.4 V, VIN - VUSB > 0.6 → VIN
- USB relay: 5 V USB output switched by a relay on GP22; max 5 V, 500 mA; overcurrent protection above 500 mA; D+ = GP26, D- = GP27
- Micro SD card socket (SPI): GP16 = SDO, GP17 = CSn, GP18 = SCK, GP19 = SDI (datasheet labels)
- Log Data to Pico's Flash switch: GP15; Enable = pulled LOW, Disable = pulled HIGH; can be repurposed
- Grove ports: 9, 4-pin, 2.0 mm pitch, already connected to the adjacent Grove modules; total +3V3 output current 300 mA max
- Grove 1: GP0, GP1 – Buttons
- Grove 2: GP14 only – RGB LEDs
- Grove 3, 4, 5: GP4, GP5 – AHT20, PAJ7620, OPT4048, SSD1315
- Grove 6: GP2, GP3 – PDM Microphone
- Grove 7: GP28 only – Potentiometer
- Grove 8: GP20, GP21 – Audio & Buzzer
- Grove 9: GP26, GP27 – USB-A Port
- Status LEDs for the Grove-port GPIOs, on when the GPIO is high
- Protoboard with Grove port
- Operating temperature: -20 – 85 ℃
- In the box: EDU PICO V2 Board ×1; Step-by-step Guidebook (English) ×1; Raspberry Pi Pico 2 W ×1 (not in EDU-PICO2-NB); USB Micro B Cable ×1; Grove 4 Pin Buckled 20cm Cable ×8; Micro Servo with Servo Horns ×1; DC2-6V Miniature Motor with 20cm Wire ×1; Mini Phillips Head Screwdriver ×1; DIY 4 Blades 56mm Motor Propeller (Blue) ×1; USB LED Light Stick (Blue) ×1; Cable Tie 100mm ×5; Self adhesive Round Velcro 10mm (Hook and loop pairs) ×27
- 12 GPIO status LEDs (product page)
- Packing (with Pico 2 W): board, English guidebook, Pico 2 W, USB cable, micro servo, 8 Grove cables, 2–6 V motor, screwdriver, 56 mm propeller, Velcro, 2 cable ties, USB LED stick; the other option omits the Pico 2 W (product page)

## Interfaces and compatibility
- Hosts: Raspberry Pi Pico 2 W (included except EDU-PICO2-NB); socket text also names Pico 2
- 9 Grove ports, 4 servo ports, 2 DC motor terminals, USB-A relay port, Micro SD socket, stereo audio jack, LiPo connector, VIN terminal
- CircuitPython: official course language; Thonny IDE with "CircuitPython (generic)" interpreter; Thonny firmware install with target volume RP2350 and variant "Cytron EDU PICO 2" for Pico 2 W
- GitHub repo Cytron-EDU-PICO2: firmware UF2, CircuitPython demo code, guidebook code
- Course: 8 chapters, 7 projects, over 10 activities; guidebook in English (Malay and Chinese "Coming soon")
- MicroPython, Arduino, MicroBlocks: [NOT STATED] for V2
- Changes from EDU PICO (V1) per the two datasheets: Pico W → Pico 2 W; APDS9960 (0x39) replaced by PAJ7620 (0x73) and OPT4048 (0x44); USB relay gains D+ GP26 / D- GP27; Grove 9 now connected to the USB-A port; digital input high max 3.6 V → 5.5 V (with stepping footnote); box adds cable ties and velcro
- Same in V1 and V2 datasheets: buttons GP0/GP1, RGB GP14, I2C GP4/GP5, AHT20 0x38, SSD1315 0x3C, microphone GP2/GP3, potentiometer GP28, audio GP20/GP21, servos GP6–GP9, motors GP10–GP13, SD GP16–GP19, log switch GP15, relay GP22, 3.6 – 6 V input, motor and relay ratings

## Use cases
- Introduction to CircuitPython
- Water Drinking Reminder
- Gesture Reaction Game
- Colour Detection Game
- Automated Waste Bin
- Noise Pollution Monitoring
- Smart Classroom
- Climate Control Greenhouse
- Flappy Bird Game
- Wireless Communication System
- DIY SpaceShip Game
- Gesture Snake game
- Color Based Water pH System
- Smart Microphone Alert System
- Data logging to the Pico's flash with CircuitPython

## Known limitations
- Spec values are absolute maximum ratings
- Power input 3.6 – 6 V only
- 5 V-tolerant digital inputs only on Pico 2 / Pico 2 W boards with the stepping named in the datasheet footnote ("RP2340-A4")
- Motor current: 1 A continuous, 1.5 A peak for under 5 seconds per channel; PWM max 20 kHz
- A High / B High is coast, not brake; Low / Low is brake
- Motor direction depends on wiring; swap MxA and MxB to reverse
- Motor test buttons run the motor at full speed
- Motor and servo voltage on USB only is VUSB - 0.4 V; servo V+ equals power source voltage
- USB relay: 5 V, 500 mA max; overcurrent protection above 500 mA
- Grove +3V3 total: 300 mA max
- Grove 2 and Grove 7 carry one GPIO each
- GP26/GP27 are shared by Grove 9 and the USB-A port D+ / D-
- GP8 is a servo signal pin
- The buzzer and the left audio channel share one output, selected by the Audio/Buzzer switch
- Audio jack output is not amplified
- Protoboard: only the pins near the Grove port pins are connected
- USB and VIN can be connected at the same time; "electrically safe" but "not recommended for normal operation"
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Charging LED flickering often, or on with no battery, means the board is not getting enough power from the USB port
- AHT20: measure every 2 seconds for accuracy
- Log-data switch with Cytron's boot.py makes the filesystem read-only to the computer; needed when powered via USB only
- Datasheet is internally inconsistent on the buzzer pin (GP8) and motor truth-table pins (GP8/GP9); the motor terminals are GP10–GP13
- Battery charge current: [NOT STATED]
- Dimensions: [NOT STATED] in text (drawing only)

## Positioning (kept apart from specs)
- "Explore CircuitPython, the fastest-growing programming language with EDU PICO V2" (EDU PICO hub)
- "EDU PICO V2 came with new and improved RP2350 that can handle more complex code and component" (EDU PICO hub)
- "Educational kit for learning Python"; "An all-in-one platform to learn electronics and Python programming through hands-on-projects" (product-page images)
- "13 Built-in Functions with 9 Detachable Modules"; "Breakable Modules – Total of 9 functional grove modules"; "No soldering & wiring required" (product-page images)
- "Beginner friendly"; "Perfect for students & educators" (product-page images)

## Price band
RM259.00–RM299.00, without / with Raspberry Pi Pico 2 W (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-edu-pico-2-project-innovation-kit-for-pico-2-w

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

