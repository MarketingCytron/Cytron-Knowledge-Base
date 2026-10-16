# Maker Uno RP2040 — Verified Reference

| | |
|---|---|
| Product code | `MAKER-UNO-RP2040` (the datasheet's figure and table captions use this code) |
| Family | Arduino-compatible boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Maker Uno RP2040 Datasheet, Rev 1.0, February 2024, Cytron Technologies Sdn Bhd. It is a public Google Doc, linked from circuitpython.org and from reseller pages, and mirrored as a PDF at electrokit.com and robu.in. |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes:
- No user manual [UM] was found. The datasheet's own section 6 serves as the getting-started guide.
- [GH] is Cytron's GitHub repo `Cytron-MAKER-UNO-RP2040`, including its pinout-diagram image, which was viewed directly. The datasheet's pinout (section 3) and dimension drawing (section 5) are images that could not be read from the Doc.

## What it is
- A development board in the Arduino UNO form factor, built around the Raspberry Pi RP2040, a "dual-core ARM Cortex-M0+" microcontroller [DS].
- Onboard [DS]:
  - power: USB Type-C, a JST-PH LiPo/Li-Ion connector with a charger, on/off switch, charging LED and power LEDs
  - buttons: reset, boot, and one user button
  - ports: Grove ports, 1 Maker Port, 4 servo ports, an SPI header and the female UNO-style pin header
  - indicators and sound: WS2812B RGB LEDs, GPIO status LEDs, a piezo buzzer with mute switch, and a solder jumper that disables the IO LEDs
- It is a **3.3 V-logic** board [DS logic levels; INT: "Operating Voltage 3.3V" vs Maker Uno 5V].
- It has no motor driver. Motors connect only through the 4 servo ports [DS, by omission].
  - it "brings the power of the Raspberry Pi® RP2040 chip into the familiar Uno form factor" while maintaining Uno's "user-friendly nature"
  - "thanks to its large flash memory", CircuitPython and MicroPython are possible
  - Maker-series features (onboard LEDs for troubleshooting, buzzer, buttons, Grove/Maker ports for plug-and-play)
  - it "follows the transitioning trend from 5V to 3.3V"

## Specifications
The datasheet's Table 4 is titled "MAKER-UNO-RP2040 **Absolute Maximum Ratings**". Every row of it is below [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB or LiPo/Li-Ion) | Min 3.6 V, Max 6 V | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 3.6 V | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.62 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Total +3V3 output current | max 500 mA | [DS] |
| Total +5V output current | max 600 mA | [DS] |
| Vservo, only USB connected | VUSB - 0.4 V | [DS] |
| Vservo, only LiPo/Li-Ion connected | VBAT ("*VBAT is the voltage of the LiPo/Li-Ion battery") | [DS] |
| Vservo, USB and LiPo/Li-Ion connected | VUSB - 0.4 V | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |
| USB VID & PID (CircuitPython & Arduino Core) | VID 0x2E8A, PID 0x1071 | [DS] |

Other specifications (not in Table 4):

| Item | Value | Src |
|---|---|---|
| MCU | Raspberry Pi RP2040, dual-core ARM Cortex-M0+ | [DS] |
| Flash | **2 MB.** The datasheet does not state it. The schematic shows Winbond W25Q16JVUXIQ QSPI flash , which is a 16 Mbit (2 MB) part [VEN]. See *Conflicts*. |  + [VEN] |
| USB connector | USB Type-C, used for both power and programming | [DS] |
| Battery | Single-cell LiPo / Li-Ion on a 2-pin JST-PH. Rechargeable via USB; protected from over-charge and over-discharge | [DS] |
| Nominal sources | "LIPO / LI-ON 3.7V" (single cell only) or "USB-C 5V" | [GH] pinout;  |
| Grove ports | 6 (4-pin, 2.0 mm pitch) | [DS] table lists Grove 1–6 |
| Servo ports | 4 | [DS] |
| RGB LEDs | WS2812B on GP25. **2 LEDs**: [GH] features image "2X RGB LED",  schematic shows two WS2812B. The datasheet says "RGB LEDs" in the heading and "LED" in the text | [DS] pin; count [GH]/ |
| GPIO status LEDs | 16: L0–L13 and L20, L21, for GP0–GP13, GP20, GP21. They light when the GPIO is high | [DS] function; [GH] pinout/features image;  |

## Interfaces, terminals and pin mapping
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| User button | GP2 | "Internally connected to GP2" | [DS] |
| Piezo buzzer | GP8 | Mute slide switch on the bottom layer; mute it if GP8 is used for other purposes | [DS] |
| RGB LEDs (WS2812B) | GP25 | 2 LEDs, chained (see Specifications) | [DS] |
| Servo 1–4 | GP14, GP15, GP16, GP17 | "Signal (S) is internally connected to GP14, GP15, GP16 and GP17 respectively". Servo + = power-source voltage | [DS] |
| Grove 1 | GP0, GP1 | GP0: PWM0-A, SDI0, SDA0, TX0. GP1: PWM0-B, CSn0, SCL0, RX0 | [DS] |
| Grove 2 | GP4, GP5 | GP4: PWM2-A, SDI0, SDA0, TX1. GP5: PWM2-B, CSn0, SCL0, RX1 | [DS] |
| Grove 3 | GP6, GP26 | GP6: PWM3-A, SCK0, SDA1. GP26: PWM5-A, SCK1, SDA1, ADC0 | [DS] |
| Grove 4 | GP7, GP27 | GP7: PWM3-B, SDO0, SCL1. GP27: PWM5-B, SDO1, SCL1, ADC1 | [DS] |
| Grove 5 | GP28, GP29 | GP28: PWM6-A, SDI1, SDA0, TX0, ADC2. GP29: PWM6-B, CSn1, SCL0, RX0, ADC3 | [DS] |
| Grove 6 | GP20, GP21 | GP20: PWM2-A, SDI0, SDA0, TX1. GP21: PWM2-B, CSn0, SCL0, RX1 | [DS] |
| Maker Port (JST-SH 4-pin) | GP20, GP21 | QWIIC / Stemma QT / Grove (with conversion cable). "The pins are shared with the Grove 6 port (GPIO 20, 21)" | [DS] |
| Grove / Maker Port power pin | 3.3V | Every Grove port and the Maker Port show a 3.3V pin | [GH] pinout |
| SPI header (2x3 male) | MISO GP12, 5V, SCK GP10, MOSI GP11, RESET, GND | GP10–GP13 are SPI1 (SCK1/SDO1/SDI1/CSn1) | [DS] function; pins [GH] |
| Analog header | A0 GP26, A1 GP27, A2 GP28, A3 GP29, SDA GP20, SCL GP21 | ADC0–ADC3 are GP26–GP29 | [DS] ADC; [GH] |

**Header order** [GH pinout and silkscreen], top = USB end:
- **Digital header:** GP21 (SCL), GP20 (SDA), NC, GND, GP10, GP12, GP11, GP13, GP9, GP8 | GP7, GP6, GP5, GP4, GP3, GP2, GP0, GP1.
- **Power header:** NC, IOREF, RESET, 3.3V, 5V, GND, GND, "~5V out".
- On the pinout, the "Dn" labels mean GPn: D10 = GP10, and so on.

**Board-position gotcha (derived):** the standard UNO R3 digital order from the same end is SCL, SDA, AREF, GND, D13, D12, D11, D10, D9, D8 | D7 … D2, D1, D0. On this board, the positions where an UNO shield expects D13/D12/D11/D10 carry **GP10/GP12/GP11/GP13**. The positions for D1/D0 carry **GP0/GP1**. The AREF position is NC, and the VIN position is labelled "~5V out". The SPI roles still land where a shield expects them (SCK, MISO, MOSI, CS), and so does UART (TX at D1, RX at D0). But the code pin number is the GP number, not the printed UNO label. This comparison is derived; see *Needs verification*.

**PWM sharing** [DS section 2]: each GPIO has a fixed PWM slice and channel, and "if the GPIO pins share the same PWM channel, simultaneous PWM usage is not possible".
- Datasheet Table 3 lists: GP0 + GP16 (Servo 3) on PWM0-A; GP1 + GP17 (Servo 4) on PWM0-B; GP4 + GP20 on PWM2-A; GP5 + GP21 on PWM2-B (Table 3 misprints this pair as PWM2-A).
- The pinout [GH] shows more pairs that Table 3 omits: GP10 + GP26 (PWM5A), GP11 + GP27 (PWM5B), GP12 + GP28 (PWM6A), GP13 + GP29 (PWM6B), and GP9 + GP25 (PWM4B; GP25 is the RGB LED). Servo 1 and 2 (GP14, GP15) are on PWM7A/7B.

## Rules and gotchas (for code, wiring and tutorials)
- **3.3 V logic only.**
  - Digital input high is max 3.6 V, and analog input is 0–3.3 V [DS].
  - Never feed 5 V signals from a 5 V shield or sensor into a GPIO.
- **Pin numbers in code = GP numbers.**
  - Arduino: `pinMode(1, OUTPUT)` drives GP1 / LED1 [DS example].
  - CircuitPython: `board.GP1` [DS example].
  - The printed UNO positions do not match GP numbers on the D10–D13 and D0/D1 positions (see the header order above).
- **Onboard pins:** GP2 (button), GP8 (buzzer), GP14–GP17 (servos) and GP25 (RGB) [DS]. To use GP8 for anything else, switch the buzzer to mute [DS].
- **Grove 6, the Maker Port and the header SDA/SCL pins are all GP20/GP21** [DS; GH]. Only one device per pin, unless they share an I2C bus.
- **Grove 1 shares a PWM channel with Servo 3/4.** GP0/GP1 share PWM0-A/B with GP16/GP17. Do not use PWM on Grove 1 while driving Servo 3 or 4 [DS Table 3].
- **Grove 2 and Grove 6 share PWM2-A/B** (GP4/GP20, GP5/GP21) [DS].
- **I2C-capable ports.**
  - Grove 1, 2, 5 and 6 carry an SDA/SCL pair: I2C0 on Grove 1, 2, 5 and 6 [DS].
  - Grove 3 (GP6 SDA1 + GP26 SDA1) and Grove 4 (GP7 SCL1 + GP27 SCL1) each have **two SDA or two SCL pins**, so they cannot carry I2C [DS table, derived].
- **Analog input** exists only on GP26–GP29 (A0–A3; Grove 3, 4, 5) [DS]. There are 4 analog inputs, not 6 as on a classic UNO .
- **The GPIO status LEDs light when the pin is high** [DS]. To turn them off, cut the "Digital IO LEDs Disable" solder jumper on the bottom; it is closed by default [DS].
- **Bootloader mode:**
  - Hold BOOT, press and release RESET, then release BOOT [DS].
  - The RPI-RP2 drive appears [DS].
  - "Make sure you switch on the board first before start flashing your code" [DS]. The on/off switch matters even on USB.
- **Arduino first upload:**
  - Put the board in bootloader mode.
  - The port first appears as "UF2_Board", then comes back as the normal COM port.
  - "You might need to recheck and reselect the COM port for the next sketch/code upload" [DS].
- The datasheet's Arduino blink comment mentions LED_BUILTIN, but the code uses pin 1 [DS]. Write explicit GP numbers in tutorials (see *Needs verification* for LED_BUILTIN).
- The datasheet's Boards Manager note shows an ESP32 URL only as an example of comma-separated URLs [DS]. It is not needed for this board.

## Power and electrical limits
- **Power inputs:**
  - Only two are listed: USB Type-C and the LiPo/Li-Ion JST-PH connector, each 3.6–6 V [DS].
  - There is no DC barrel jack or VIN input [DS, by omission].
- **Battery:**
  - Single cell only [GH pinout]. It is charged from USB [DS].
  - The charging LED is on while the battery charges and off when it is full [DS].
  - "If the board cannot be turned on when the battery is connected, please charge the battery to activate the battery protection circuit." [DS]
  - Charge current is not stated.
- **Output current limits** [DS]:
  - Total +3V3 output: 500 mA max. This covers the Grove/Maker ports and the 3.3V header pin [GH] for which pins are 3.3 V.
  - Total +5V output: 600 mA max.
- **Servo voltage** [DS]:
  - It equals the power-source voltage, not a regulated 5 V.
  - USB only gives VUSB - 0.4 V; LiPo only gives VBAT; both connected gives VUSB - 0.4 V.
  - On a single LiPo cell, the servos get the battery voltage.
  - Servo current limit: [not stated].
- **"~5V out" on the UNO VIN position** [GH] is labelled as an output. Do not feed power into it. Its source is unconfirmed (see *Needs verification*).
- **On/off switch:** the slide switch turns power on and off [DS].
- **Operating temperature:** -20 to 85 ℃ [DS].

## Software support
- **Arduino IDE** (the datasheet is written for IDE 2) [DS]:
  - Additional Boards Manager URL: `https://github.com/earlephilhower/arduino-pico/releases/download/global/package_rp2040_index.json`.
  - Install "Raspberry Pi Pico/RP2040 by Earle F. Philhower".
  - Select Tools > Board > Raspberry Pi Pico/RP2040 > **Cytron Maker Uno RP2040**.
- **CircuitPython:**
  - Firmware is on circuitpython.org/board/cytron_maker_uno_rp2040/ (board id `cytron_maker_uno_rp2040`) [DS link].
  - Install by dragging the .uf2 onto RPI-RP2, or in Thonny via "Install CircuitPython…" with the variant "Cytron Technologies • Maker Uno RP2040" [DS].
  - The interpreter shows as "CircuitPython (generic)" [DS].
- **MicroPython:**
  - The datasheet names it but gives no steps [DS].
  - Cytron: "For MicroPython, we have not created a custom firmware yet. For now, you can use Pico MicroPython Firmware" (rp2-pico) [GH].
- **Cytron examples:** Arduino, CircuitPython and MicroPython examples are in the CytronTechnologies/Cytron-MAKER-UNO-RP2040 repo. They cover the onboard parts, an OLED, and digital and analog sensors [GH].

## Compatibility and accessories
- **UNO form factor:**
  - IOREF is broken out on the header [GH]; its voltage is not stated.
- **Maker Port:** QWIIC / Stemma QT / Grove (with conversion cable) [DS].
- **Grove modules:** the 6 Grove ports supply 3.3V on their power pin [GH]. The 4 included Grove-to-female cables let generic modules plug into Grove ports .
- **Servos:** 4 RC servos, signal pins GP14–GP17 [DS]. The Cytron repo pairs the board with the TS90A micro servo [GH].
- **Other Cytron parts used in repo examples** [GH]: Maker Soil Sensor, the 3V–5.5V ultrasonic ranging module, and an SSD1306 0.96" I2C OLED.
- **Cytron project tutorials linked from the repo** [GH]: "Offline Dino Game Cheat with Maker Uno RP2040", "DHT11 Sensor Data Logging using Maker Uno RP2040", "Play Game using Joystick on Maker Uno RP2040".

## Common mistakes / troubleshooting
- **The board won't power on from the battery:** charge it over USB to reset the protection circuit [DS].
- **No RPI-RP2 drive:**
  - Switch the board ON first.
  - Hold BOOT while pressing RESET, and release RESET first [DS].
- **Arduino upload fails the second time:** reselect the COM port; it can change after upload [DS].
- **The buzzer clicks or sounds when GP8 is used as I/O:** slide the mute switch [DS].
- **PWM on a pin stops when a servo runs:** the two share a PWM channel. Check the pairs above [DS; GH].
- **A 5 V UNO shield or sensor misbehaves or damages the GPIO:** the board is 3.3 V logic [DS].
- **Shield SPI or UART code uses D10–D13 / D0–D1 numbers:** use the GP number wired to that position instead (see *Interfaces*).
- **The status LEDs are distracting or draw power:** cut the IO-LED solder jumper [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| GP5/GP21 PWM channel | [DS] Table 3: PWM2-A | [DS] Table 1 Grove table and [GH] pinout: PWM2-B | PWM2-B. Table 3 is a typo, and GPIO5 is PWM2 B per RP2040 [VEN]. |
| Shared PWM pairs | [DS] Table 3 lists 4 pairs (GP0/16, GP1/17, GP4/20, GP5/21) | [GH] pinout also shows GP10/26, GP11/27, GP12/28, GP13/29, GP9/25 | Both are correct. Table 3 is incomplete; use the full list. |
| Grove 3 pins | [DS]: GP6, GP26 | [3P] ThePiHut copy: "GP6/GP25" | DS wins: GP6, GP26. |
| SPI on GP10–GP13 | [GH] pinout: SCK1/SDO1/SDI1/CSn1 (SPI1); [3P] Zephyr uses SPI1 | [3P] arduino-pico variant names them PIN_SPI0_* | Hardware is SPI1 per the pinout. Arduino behaviour is unverified (see below). |

## Needs verification
- **IOREF voltage:** the scrambled schematic text suggests IOREF is tied to +3V3 . Confirm with [DT].
- **"~5V out" source** (UNO VIN position): the 5 V boost rail or the servo/VM rail? Confirm with [DT].
- **UNO position mapping:** the D10–D13 / D0–D1 comparison above is derived from the pinout plus the standard UNO R3 header order. Confirm with [DT] or the schematic.
- **Arduino LED_BUILTIN:** the arduino-pico variant defines PIN_LED = 3 (GP3), and Zephyr aliases led0 = GP3 [3P]. The DS example blinks GP1 (LED1). Do not use LED_BUILTIN in tutorials until confirmed.
- **Arduino `SPI` on GP10–GP13:** the arduino-pico variant labels these pins as SPI0 and leaves SPI1 "Not pinned out" [3P], but in hardware they are SPI1 [GH]. Test `SPI` versus `SPI1` before writing SPI tutorials.
- **Default buses in other upstream configs** [3P, Cytron-authored]:
  - Arduino: Wire = GP20/GP21, Wire1 = GP26/GP27, Serial1 = GP0/GP1.
  - CircuitPython: board.I2C = GP20/GP21, board.SPI = GP10/11/12, board.UART = GP0/GP1.
  - CircuitPython names: BUTTON = GP2, BUZZER = GP8, NEOPIXEL/RGB = GP25, SERVO1–4 = GP14–17, LED0–LED13/LED20/LED21, D0–D13, D20, D21, A0–A3.
- **CircuitPython firmware libraries:** the upstream board config freezes the NeoPixel and SimpleIO libraries into the firmware [3P].
- **Other platforms:** Zephyr lists a board target `maker_uno_rp2040` [3P]. micropython.org (checked 2026-10-16) has no Maker Uno RP2040 build [3P].
- **Charge current** and LiPo charge voltage (MCP73831 variant) are not stated.
- **Servo current limit** is not stated.
- **Exact current product-page wording:** the product page could not be read.

## Sources
- [DS] Maker Uno RP2040 Datasheet, Rev 1.0, February 2024 (public Google Doc): https://docs.google.com/document/d/16RTRPaV0Xaqg3xKwM89iMkXrDB8T_pBjCKYHOadv_Z4/edit
- [DS mirror] https://www.electrokit.com/upload/Maker-Uno-RP2040-Datasheet.pdf (Rev 1.0, February 2024; same content)
- [DS mirror] https://aws.robu.in/wp-content/uploads/2024/04/Maker-Uno-RP2040-Datasheet.pdf (Rev 1.0, February 2024)
- [PP] Product page (not read; fetch error): https://my.cytron.io/p-maker-uno-rp2040
- [PP] Cytron tutorial "Getting Started Guide with Maker Uno RP2040": https://www.cytron.io/tutorial/getting-started-guide-with-maker-uno-rp2040
- [GH] https://github.com/CytronTechnologies/Cytron-MAKER-UNO-RP2040 (README; Images/MAKER-UNO-RP2040-pinout-diagram.png; Images/MAKER-UNO-RP2040-features-labeled.png)
- [3P] CircuitPython board: https://circuitpython.org/board/cytron_maker_uno_rp2040/ and https://raw.githubusercontent.com/adafruit/circuitpython/main/ports/raspberrypi/boards/cytron_maker_uno_rp2040/pins.c
- [3P] arduino-pico variant: https://raw.githubusercontent.com/earlephilhower/arduino-pico/master/variants/cytron_maker_uno_rp2040/pins_arduino.h
- [3P] Zephyr: https://docs.zephyrproject.org/latest/boards/cytron/maker_uno_rp2040/doc/index.html
- [3P] MicroPython downloads (no Maker Uno RP2040 build listed): https://micropython.org/download/?mcu=rp2040
- [3P] Resellers: https://thepihut.com/collections/cytron/products/maker-uno-rp2040, https://www.robotshop.com/products/cytron-maker-uno-rp2040
