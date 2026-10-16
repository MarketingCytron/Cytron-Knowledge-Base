# MOTION 2350 Pro — Verified Reference

| | |
|---|---|
| Product code | Not stated in any source read. The datasheet uses the name "MOTION 2350 Pro"; reseller mirror filenames use `MOTION-2350-PRO` |
| Family | RP2040 / RP2350 boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Datasheet "MOTION 2350 Pro – An Advanced Robotics Controller for Beginners", **Rev 2.0, September 2025**, Cytron Technologies Sdn Bhd (public mirror on Farnell) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Notes: [DS] = Rev 2.0 (Sep 2025) unless marked [DS-R1] (Rev 1.0, July 2024, for comparison only). No user manual was found. [PP] = www.cytron.io/p-motion-2350-pro (my.cytron.io returned an error). [VEN] here also covers firmware/core board definitions (CircuitPython, MicroPython, arduino-pico). The datasheet was read as extracted text. Its figures (pinout, dimensions) were not readable, so the GPIO map comes from Cytron's GitHub pinout image [GH].

## What it is
- A robot controller board built on the Raspberry Pi **RP2350** [PP, DS title]. Its datasheet tagline is "An Advanced Robotics Controller for Beginners" [DS].
- On board: a 4-channel brushed DC motor driver, 8 RC servo ports, a GPIO breakout, 3 Maker Ports, a USB host port (Type-A), WS2812B RGB LEDs, a piezo buzzer with mute switch, user buttons, motor test buttons, and status LEDs for GPIOs and motors [DS, GH pinout, PP].
- [PP]: "combines the Raspberry Pi Pico 2, the benefits of the Maker series… compatible with the existing Raspberry Pi Pico ecosystem."
- CircuitPython comes preloaded with a demo program [PP].

## Specifications
Datasheet Table 2 is titled "MOTION 2350 Pro **Absolute Maximum Ratings**" (under section "3. SPECIFICATIONS"). Every row is below [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (USB or VIN) | Min 3.6 V, Max 16 V | [DS] |
| Digital input voltage, low level | -0.3 to 0.8 V | [DS] |
| Digital input voltage, high level | 2.0 to 5.5 V | [DS] |
| Digital output voltage, low level | 0 to 0.5 V | [DS] |
| Digital output voltage, high level | 2.6 to 3.3 V | [DS] |
| Analog input voltage | 0 to 3.3 V | [DS] |
| Vmotor, only USB connected | VUSB - 0.4 V to VUSB | [DS] |
| Vmotor, only VIN connected | VIN | [DS] |
| Vmotor, USB and VIN, VIN < VUSB | VUSB - 0.4 V to VUSB | [DS] |
| Vmotor, USB and VIN, VIN > VUSB and VIN - VUSB < 0.6 V | VIN - 0.4 V | [DS] |
| Vmotor, USB and VIN, VIN - VUSB > 0.6 V | VIN | [DS] |
| 5V output voltage (servo ports), VIN > 5.8 V | 5 V | [DS] |
| 5V output voltage (servo ports), VIN < 5.5 V | VIN | [DS] |
| USB host output voltage | max 5 V | [DS] |
| USB host output current | max 100 mA | [DS] |
| Max DC motor current each channel, continuous | 5 A | [DS] |
| Max DC motor current each channel, peak (< 5 seconds) | 10 A | [DS] |
| Motor driver overtemperature shutdown threshold | 150 ℃ | [DS] |
| Motor driver overtemperature thermal hysteresis (recovery) | 60 ℃ | [DS] |
| DC motor driver PWM frequency | max 20 kHz | [DS] |
| Total +3V3 output current (GPIO breakout & Maker Ports) | max 200 mA | [DS] |
| Total +5V output current (servo ports), VIN < 5.8 V | max 3 A | [DS] |
| Total +5V output current (servo ports), VIN > 5.8 V | max 2.5 A | [DS] |
| Operating temperature | -20 to 85 ℃ | [DS] |

Table footnotes [DS]: "It's not recommended to connect both USB and VIN at the same time", adding that doing so is perfectly safe. "The absolute maximum VIN is 18V but the recommended maximum voltage is 16V."

## Interfaces, terminals and pin mapping
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| Servo ports (8) | GP0–GP7 | 5V from the 5V Supply section. The header is marked GND / 5V / SIG | [DS] pins; [GH] header order |
| DC motor 1 (M1A / M1B) | GP8 / GP9 | | [GH pinout]; [VEN] CircuitPython, MicroPython, arduino-pico agree |
| DC motor 2 (M2A / M2B) | GP10 / GP11 | | [GH]; [VEN] |
| DC motor 3 (M3A / M3B) | GP12 / GP13 | | [GH]; [VEN] |
| DC motor 4 (M4A / M4B) | GP14 / GP15 | | [GH]; [VEN] |
| User buttons (2) | GP20, GP21 | Demo enables the internal pull-up and reads a press as LOW | [GH pinout + demo]; [PP] names GP20/GP21 |
| Piezo buzzer | GP22 | Buzzer mute switch | [DS] |
| RGB LEDs | GP23 | WS2812B, NeoPixel compatible. Count = **2** | [DS] pin/type; count [GH demo], [VEN] arduino-pico `NUM_NEOPIXEL 2` |
| USB host (Type-A) | D+ = GP24, D- = GP25 | | [DS] |
| Measure VIN jumper | GP29 (ADC3) | Solder the jumper to enable it. The GP29 GPIO LED then stays on | [DS] |
| Maker Ports (3), JST-SH 4-way | GP16/GP17, GP26/GP27, GP28/GP29 | Qwiic, STEMMA QT, Grove (via conversion cable). [DS] lists the six pins; [GH] pinout shows the pairing | [DS]; [GH] |
| GPIO breakout (8), colour-coded GVS | GP16, GP17, GP18, GP19, GP26, GP27, GP28, GP29 | Each has a 3.3V pin. **Same GPIOs as the Maker Ports, except GP18/GP19** | [DS] |
| Debug header | SWDIO, GND, SWCLK | | [GH pinout] |
| BOOT and RST buttons | Hardware | Shown on the board in the pinout image | [GH pinout] |
| On/Off switch, Ext. On/Off header | Hardware | The onboard switch must be Off to use the external switch | [DS] |
| Motor test buttons, motor status LEDs | Hardware | The test button runs the motor at full speed. The LEDs turn on while the motor runs | [DS] |
| GPIO/Servo status LEDs | Hardware | On when the IO is high | [DS] |

Breakout pin functions [DS]:
- GP16: PWM0-A, SPI0 SDI, I2C0 SDA, UART0 TX
- GP17: PWM0-B, SPI0 CSn, I2C0 SCL, UART0 RX
- GP18: PWM1-A, SPI0 SCK, I2C1 SDA, UART0 CTS
- GP19: PWM1-B, SPI0 SDO, I2C1 SCL, UART0 RTS
- GP26: PWM5-A, SPI1 SCK, I2C1 SDA, UART1 CTS, ADC0
- GP27: PWM5-B, SPI1 SDO, I2C1 SCL, UART1 RTS, ADC1
- GP28: PWM6-A, SPI1 SDI, I2C0 SDA, UART0 TX, ADC2
- GP29: PWM6-B, SPI1 CSn, I2C0 SCL, UART0 RX, ADC3

Motor PWM slices [GH pinout]: M1 = PWM4 (GP8/GP9), M2 = PWM5 (GP10/GP11), M3 = PWM6 (GP12/GP13), M4 = PWM7 (GP14/GP15).

## Rules and gotchas (for code, wiring and tutorials)
- **Board-reserved pins:** GP0–GP7 (servos), GP8–GP15 (motors), GP20/GP21 (buttons), GP22 (buzzer), GP23 (RGB), GP24/GP25 (USB host) [DS, GH]. GP29 is also reserved once the VIN jumper is soldered [DS]. Free user I/O is GP16–GP19 and GP26–GP29 only [DS].
- **Maker Ports and the GPIO breakout share pins** (GP16/17, GP26/27, GP28/29) [DS]. Don't wire two devices to the same GPIO.
- **Motor current (Rev 2.0): 5 A continuous, 10 A peak (< 5 s) per channel** [DS]. Older material says 3 A (see *Conflicts*). Use the Rev 2.0 figure only for Rev 2.0 boards.
- **Motor driver protection (Rev 2.0):** "integrated with overcurrent and overtemperature features" [DS]. It shuts off above about 150 ℃ (typical) and resumes once the chip cools to about 100 ℃ (typical). "Shutdown may occur even if current is below the rated value." A heatsink or better airflow helps [DS]. **Rev 1.0 has no overcurrent protection** [DS-R1].
- **Motor direction:** "Swapping the connection (MA & MB) will reverse the direction" [DS]. The datasheet has no truth table (brake vs coast is not stated).
- **Servo 5V rail:** above VIN 5.8 V a buck converter gives 5 V. Below 5.5 V the rail follows VIN. A Schmitt trigger switches between the two to protect the servos [DS]. So the **servo voltage equals VIN at low battery voltages**.
- **Test buttons run the motors at full speed with no code** [DS]. Lift the robot first.
- **Status LEDs follow the GPIO state** [DS]. With the VIN jumper soldered, the GP29 LED is always on [DS].
- **Arduino `LED_BUILTIN`:** the arduino-pico variant sets `PIN_LED` = GP2, which is a servo signal pin [VEN]. Arduino-pico also puts `Serial1` on GP0/GP1 and `SPI` on GP4–GP7 (servo pins), with `Wire` on GP16/GP17 and `Wire1` on GP26/GP27 [VEN].
- **CircuitPython defaults:** `board.I2C()` / `board.STEMMA_I2C()` use GP16 (SDA) and GP17 (SCL). Default SPI is SCK GP18, MOSI GP19, MISO GP16 — **MISO overlaps the I2C SDA pin** [VEN].
- **Unlike a bare Pico 2, GP23–GP25 are board functions** (RGB, USB host) [DS]. Pico 2 example code that blinks GP25 won't work here. MicroPython's `LED` name maps to GP23, the NeoPixel pin [VEN].
- Spec values are **absolute maximum ratings** [DS], not operating targets.

## Power and electrical limits
- Power comes from **USB-C** or the **VIN terminal, 3.6–16 V DC** [DS]. VIN "Can be powered up with external LiPo or 4x AA batteries" [DS]. There is no onboard battery charger in any source read.
- **Overvoltage protection (Rev 2.0):** "When the power input is higher than 18V, the board will automatically enter a shutdown state". It resumes once the voltage is back in the safe range. The absolute maximum is 18 V and the recommended maximum is 16 V [DS].
- Vmotor follows the source (see *Specifications*). On USB only it is VUSB - 0.4 V [DS]. "Motor voltage at full speed is equal to power source voltage" [DS].
- Total current limits: +3V3 is 200 mA (GPIO breakout + Maker Ports). +5V servo is 3 A (VIN < 5.8 V) or 2.5 A (VIN > 5.8 V). The USB host port gives 5 V, 100 mA [DS].
- **VIN measurement:** solder the "Measure VIN" PCB bridge and read GP29 (ADC3). VIN is "VIN input terminal or VUSB input voltage (whichever is higher)" [DS]. The formula is printed as **"VIN = VADC / 6.1"** [DS text, GH pinout] — see *Needs verification*.
- Operating temperature: -20 to 85 ℃ [DS].

## Software support
- **CircuitPython:** preloaded with a demo [PP]. Firmware: circuitpython.org board `cytron_motion_2350_pro` [GH README]. The board definition names the pins `board.M1A`…`board.M4B` (GP8–GP15), `NEOPIXEL` (GP23), `VOLTAGE_MONITOR` / `A3` (GP29), `A0`–`A2` (GP26–GP28), `SDA`/`SCL` (GP16/GP17). NeoPixel, Motor and SimpleIO libraries are frozen in [VEN]. Each USB product string is "MOTION 2350 Pro", VID 0x2E8A, PID 0x1096 [VEN].
- **Demo code** ([GH] `demo_code/code.py`): plays a melody and runs the blue LEDs at power-up. GP20 and GP21 play melodies and light the LEDs. It uses `neopixel.NeoPixel(board.GP23, 2)` and `simpleio.tone(board.GP22, …)` [GH].
- **MicroPython:** official board `CYTRON_MOTION_2350_PRO` on micropython.org, including a RISC-V variant. Pin names: `M1A`…`M4B`, `BTN1` (GP20), `BTN2` (GP21), `NEOPIXEL`/`LED` (GP23), `ADC0`–`ADC3` [VEN]. [PP] lists MicroPython.
- **C/C++:** listed by [PP] ("C/C++").
- **Arduino:** [PP] says "Arduino IDE (coming soon)". The Earle Philhower `arduino-pico` core now includes the board **"Cytron Motion 2350 Pro"** (variant `cytron_motion_2350_pro`) [VEN]. See *Conflicts*.
- The Cytron GitHub repo also carries `flash_nuke_rp2350.uf2` (flash erase) [GH].
- Cytron getting-started tutorial (CircuitPython): https://www.cytron.io/tutorial/getting-started-with-motion-2350-pro-cp (linked from circuitpython.org; not read).

## Compatibility and accessories
- **Maker Ports:** Qwiic / STEMMA QT, and Grove via a conversion cable [DS].
- **USB host:** for a USB joystick/gamepad [PP].
- **4 brushed DC motors** ([PP] mentions mecanum-wheel robots) and **8 RC servos** [DS, PP].
- Pico ecosystem: [PP] says Pico software, firmware and libraries "should work seamlessly."
- **Rev 1 vs Rev 2 (both Cytron datasheets):** to identify a Rev 2.0 board, look for the "REV 2.0" silkscreen just below the "MOTION 2350 PRO" logo. The bottom side has fewer IC chips and the product-name label sits slightly higher [DS]. Spec changes from Rev 1.0 [DS-R1] to Rev 2.0 [DS]:
  - Motor current: 3 A continuous / 5 A peak → 5 A / 10 A.
  - Digital input high max: 3.6 V → 5.5 V.
  - +5V servo total with VIN > 5.8 V: 2 A → 2.5 A.
  - Motor driver: "do not have overcurrent protection" → overcurrent + overtemperature protection (150 ℃ shutdown).
  - New in Rev 2.0: input overvoltage shutdown above 18 V.
  - Rev 1.0's "RP2350 GPIO Pull-Down Issue (Errata E9)" note (use an external pull-down < 8 kΩ) is not in Rev 2.0.
  - The +3V3 row says "Grove Ports" in Rev 1.0 and "Maker Ports" in Rev 2.0.
- The older MOTION 2040 was not compared: no Cytron source read states its differences.

## Common mistakes / troubleshooting
- **Quoting 3 A per channel for a Rev 2.0 board:** the product page, GitHub pinout and resellers still say 3 A (Rev 1 figures). The Rev 2.0 datasheet says 5 A continuous, 10 A peak [DS].
- **Demo code comment** says "Neopixel RGB LEDs on pin GP18" but the code uses GP23 [GH]. GP23 is correct [DS].
- **Motor stops under heavy load (Rev 2.0):** thermal shutdown, which can trip below the rated current. Add a heatsink or airflow, and let it cool [DS].
- **Board shuts down on a high-voltage pack:** input above 18 V trips overvoltage protection (Rev 2.0) [DS]. Stay at or below 16 V.
- **Servos act up on low battery:** below VIN 5.5 V the 5 V rail follows VIN [DS].
- **GP29 LED always on:** expected once the VIN jumper is soldered [DS].
- **External switch does nothing:** the onboard switch must be Off [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Motor current per channel | [DS] Rev 2.0 (Sep 2025): 5 A continuous, 10 A peak (< 5 s) | [PP] www.cytron.io and [GH] pinout image: "3A Max each channel" / "3A Continuous, 5A Peak"; [DS-R1] Rev 1.0: 3 A / 5 A; [3P] Adafruit, circuitpython.org: 3 A | [DS] Rev 2.0 wins for the current board. 3 A / 5 A is the Rev 1.0 rating, so the product page and pinout image are out of date |
| Motor overcurrent protection | [DS] Rev 2.0: has overcurrent + overtemperature protection | [DS-R1] Rev 1.0: "do not have overcurrent protection" | Revision difference. Rev 2.0 has it, Rev 1.0 does not |
| USB host output current | [DS] Rev 2.0: 100 mA | [DS-R1] Rev 1.0 mirrors disagree: electrokit copy 100 mA, Akizuki copy 500 mA (both "Rev 1.0, July 2024") | 100 mA for Rev 2.0. The Rev 1.0 value is unclear |
| Arduino support | [PP]: "Arduino IDE (coming soon)" | [VEN] arduino-pico core includes "Cytron Motion 2350 Pro" | Board support exists in arduino-pico; [PP] wording is out of date. Ask [DT] whether Cytron officially supports it |
| USB host pin names | [DS]: D+ = GP24, D- = GP25 (arduino-pico agrees: DP 24, DM 25) | [VEN] MicroPython pins.csv: `USBA_DN` = GPIO24, `USBA_UP` = GPIO25 | [DS] wins |
| Motor driver recovery temperature | [DS] Table 2: thermal hysteresis 60 ℃ (150 - 60 = 90 ℃) | [DS] text: resumes "below a safe temperature (typically 100°C)" | Inside the same datasheet. Quote both as written; see *Needs verification* |
| RGB LED count | [DS] gives no count | [GH] demo and [VEN] arduino-pico: 2 | 2, sourced from [GH] |

## Needs verification
- **VIN formula:** printed as "VIN = VADC / 6.1" [DS, GH]. At a 16 V input, that would put more than 3.3 V on the ADC, so the working formula is probably VIN = VADC × 6.1. Confirm with [DT] before publishing code.
- **Flash size:** not in any Cytron source. CircuitPython declares W25Q16JV, and arduino-pico 2 MB [VEN]. Confirm with [DT].
- **RP2350 package and stepping:** CircuitPython and arduino-pico say RP2350A [VEN]. The datasheet doesn't say. Also unconfirmed: whether Rev 2.0 dropped the Errata E9 note because of a newer chip stepping.
- **5.5 V digital input on ADC pins:** RP2350 ADC-capable pins (GP26–GP29) are generally not 5 V tolerant [VEN, from memory, not re-read]. The datasheet's 5.5 V high-level row doesn't separate them. Confirm before telling users 5 V signals are fine on Maker Ports.
- Motor driver IC part number, and the brake/coast truth table (not in [DS]).
- Rev 1.0 USB host current (100 vs 500 mA, see *Conflicts*).
- Dimensions and mounting holes (datasheet figure not readable).
- Product code / SKU, package contents, price (Adafruit lists USD 31.25 [3P] only).
- Whether my.cytron.io carries the same 3 A text (page not readable).
- Arduino IDE official status ("coming soon" on [PP]).

## Sources
- [DS] MOTION 2350 Pro Datasheet, Rev 2.0, September 2025, Cytron Technologies Sdn Bhd (public mirror): https://www.farnell.com/datasheets/4726021.pdf
- [DS-R1] MOTION 2350 Pro Datasheet, Rev 1.0, July 2024 (public mirrors): https://www.electrokit.com/upload/quick/5f/62/6a8c_MOTION-2350-PRO-Datasheet.pdf · https://akizukidenshi.com/goodsaffix/MOTION-2350-PRO%20Datasheet.pdf
- [PP] https://www.cytron.io/p-motion-2350-pro (read). https://my.cytron.io/p-motion-2350-pro (not readable)
- [GH] https://github.com/CytronTechnologies/CYTRON-MOTION-2350-PRO — README, `demo_code/code.py`, `images/Pinout_Diagram_MOTION-2350-Pro.png` (via raw.githubusercontent.com)
- [VEN] CircuitPython board: https://raw.githubusercontent.com/adafruit/circuitpython/main/ports/raspberrypi/boards/cytron_motion_2350_pro/pins.c (and `mpconfigboard.mk`); circuitpython.org page source: https://raw.githubusercontent.com/adafruit/circuitpython-org/main/_board/cytron_motion_2350_pro.md
- [VEN] MicroPython board: https://raw.githubusercontent.com/micropython/micropython/master/ports/rp2/boards/CYTRON_MOTION_2350_PRO/pins.csv
- [VEN] arduino-pico: https://raw.githubusercontent.com/earlephilhower/arduino-pico/master/variants/cytron_motion_2350_pro/pins_arduino.h · https://raw.githubusercontent.com/earlephilhower/arduino-pico/master/boards.txt
- [3P] https://www.adafruit.com/product/6080 · https://www.cnx-software.com/2024/08/09/cytron-motion-2350-pro-a-raspberry-pi-rp2350-board-for-robotics-and-motor-control/
