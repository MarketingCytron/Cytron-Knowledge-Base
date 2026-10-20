# Advanced Auto-Calibrating Line Sensor (LSA08) — Verified Reference

| | |
|---|---|
| Product code | `LSA08` [PP]; manual title "Advance Line Following Sensor Bar LSA08" [UM] |
| Family | Sensors |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-20 |
| Reviewed | 2026-10-20 — final review round (not-started products): live my.cytron.io product page read. The my.cytron.io page itself says "Refresh rate up to 200Hz" (manual: 100 Hz) — the conflict is now between two Cytron sources |
| Primary source | **No Cytron datasheet exists for this product.** Highest source is the Cytron user manual: "Advance Line Following Sensor Bar LSA08 — User's Manual **V1.1, June 2012**" [UM] (PDF in Cytron's own GitHub repo, identical title/version to the Drive PDF linked from the product page; the Drive link itself was not readable here). Secondary Cytron document: "Advance Line Following Sensor Bar LSA08 — C Library Manual **V1.1, Jan 2013**" [UM-LIB] (public Google Doc) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [UM] = User's Manual V1.1 June 2012 (46 pages, read in full from `LSA08_User_Manual.pdf` in https://github.com/CytronTechnologies/Cytron_LSA08). [UM-LIB] = LSA08 C Library Manual V1.1 Jan 2013 (Google Doc, read in full). [PP] = my.cytron.io product page facts supplied by the coordinator (read 2026-10-16). [PP: Tindie] = Cytron Technologies' own Tindie listing (cross-check only). [GH] = Cytron_LSA08 repository.

## What it is
An 8-sensor line-following sensor bar ("Advance Line Following Sensor Bar") with 8 sensor pairs spaced 16 mm apart, an on-board 2x8 LCD, SEL and MODE buttons, and auto-calibration [UM]. It outputs the line position three ways: serial UART (Port A), an analog voltage (Port A) and 8 parallel digital lines, one per sensor (Port B) [UM]. It runs from 7.5–20 V (12 V typical, "typically 9 to 12V"), draws about 26 mA typical, has power-polarity protection, and is stated to work on reflective or glossy surfaces and on red, green, blue, white, black and grey surfaces [UM]. It also has a junction-pulse output (JPULSE) and an internal junction counter for cross-junction counting [UM].

## Specifications
Manual section 3.2 "Electrical Specifications" and "Absolute Maximum Rating" [UM]; every row is reproduced.

| Item | Value | Src |
|---|---|---|
| Current consumption (12 V) | Min 25.3 mA, Typ 25.5 mA, Max 130 mA | [UM] |
| Input signal, VIH | Min 2 V, Max 5 V | [UM] |
| Input signal, VIL | Min 0 V, Max 0.8 V | [UM] |
| Output signal | 5 V (Max column) | [UM] |
| Operating voltage (absolute maximum rating) | Min 7.5 V, Typ 12 V, Max 20 V | [UM] |
| Maximum current (I/O signal pins) | 20 mA | [UM] |
| Sensing distance (from board) | Min 1 cm, Typ 3 cm, Max 5 cm | [UM] |
| Minimum line width | 15 mm | [UM] |
| Refresh rate | 100 Hz (Min column) | [UM] |
| Typical current (intro text) | "typically around 26mA" | [UM] |
| Number of sensors | 8 sensor pairs (S0–S7), spaced at 16 mm | [UM] |
| Line position range | 0 (sensor 0) to 70 (sensor 7); 35 = between S3 and S4; linear | [UM] |
| Outputs | UART (TX/RX/UEN), analog (AN), junction pulse (JPULSE), 8 parallel digital (O0–O7) | [UM] |
| Analog output | 0 V – 4.5 V = position 0 – 70; 5 V = no line | [UM] |
| Display | 2x8 LCD, line position + bar chart; backlight level 0–10 | [UM] |
| Overall PCB size | 135 mm x 45.7 mm (dimension drawing) | [UM] |
| Mounting-hole spacing | 127.3 mm x 38 mm (dimension drawing) | [UM] |
| Sensor pitch | 16 mm (dimension drawing and text) | [UM] |
| Power polarity protection | Yes ("prevents damage by applying reversed voltage") | [UM] |
| Calibration storage | Non-volatile memory; one-time unless line/background changes | [UM] |
| Packing list | 1 x LSA08 PCB, 1 x LSA08 cable connector | [UM] |
| Price | RM204.75 | [PP] |
| Warranty | 12 months [PP]; manual (2012) says 6 months [UM] — see Conflicts | [PP][UM] |
### Product page facts (my.cytron.io, read 20 Oct 2026)
- **Features list:** 8 sensor pairs, 16 mm spacing; 12 V input power; Mode and Select buttons; 3 output modes (digital, UART, analog); LCD showing 8 analog values with bar chart and line position; auto-calibration; junction pulse (JPULSE); **power polarity protection**; typically 26 mA; works on glossy or reflective surfaces; **"Refresh rate up to 200Hz"** [PP].
- **Description:** green LED emitters so it works on red, green, blue, white, black, grey surfaces [PP].
- **Resources:** user's manual (Drive), LSA08 library manual, tutorials — serial mode with PID, digital mode, serial mode with digital output, analog mode [PP].

## Interfaces, terminals and pin mapping
Two 10-pin ports; pin 1 is the square solder pad; pin labels are printed on the back of the PCB [UM]. The board can be powered from VIN/GND of either Port A or Port B, and both ports may be used at the same time [UM].

**Port A — UART and analog** [UM 6.4.1]

| Pin | Symbol | Description |
|---|---|---|
| 1 | TX | UART TX (transmit). Floating / high-impedance when not sending (UEN not pulled low and no command response pending) |
| 2 | RX | UART RX (receive). Weakly pulled up |
| 3 | UEN | UART Output Enable, **active low**: pull low to stream data out of TX |
| 4 | AN | Analog output, line position as a voltage |
| 5 | JPULSE | Junction pulse output (0 V / 5 V in the manual figure) |
| 6–8 | – | Not used |
| 9 | VIN | VIN (12 V) |
| 10 | GND | GND |

**Port B — digital parallel** [UM 6.4.2]

| Pin | Symbol | Description |
|---|---|---|
| 1–8 | O0–O7 | Digital output 0–7 (sensor 0–7): 5 V / "1" = line detected, 0 V / "0" = no line |
| 9 | VIN | Vin (12 V) |
| 10 | GND | GND |

**UART framing** [UM 6.5.1]: 1 start bit, 8 data bits, no parity, 1 stop bit; baud per setting table.

| Baud setting | bps |
|---|---|
| 0 | 9600 (default) |
| 1 | 19200 |
| 2 | 38400 |
| 3 | 57600 |
| 4 | 115200 |
| 5 | 230400 |

**UART output modes (UARTMODE / command D)** — data streams from TX only while UEN is low [UM 6.2.8, 6.4.1.1]:

| Mode | Output |
|---|---|
| 0 | No UART data output (default) |
| 1 | One byte of digital sensor values; LSB = sensor 0, MSB = sensor 7; bit 1 = line detected |
| 2 | One byte line position 0–70 relative to sensor 0; **255 = no line** |
| 3 | 9-byte raw packet: header 0x00 followed by 8 raw sensor bytes S0–S7 (debug) |

**UART command packet** (4 bytes): ADDRESS, COMMAND, DATA, CHECKSUM, where CHECKSUM = lower byte of (ADDRESS + COMMAND + DATA). The bytes must arrive continuously; LSA08 waits at most 20 ms for the next byte, then discards the incomplete packet. Setting commands with correct address/checksum are answered with the ASCII pair "OK"; data commands return the data instead; a wrong address, command, checksum or baud gives no response [UM 6.5].

| Cmd (ASCII) | Hex | Description | Data (decimal) |
|---|---|---|---|
| C | 0x43 | Calibration (start now) | 0 |
| L | 0x4C | Line mode: 0 = Light-On, 1 = Dark-On | 0–1 |
| T | 0x54 | Line threshold | 0–7 |
| J | 0x4A | Junction width | 3–8 |
| A | 0x41 | UART address | 0–255 |
| B | 0x42 | LCD backlight | 0–10 |
| S | 0x53 | LCD contrast | 0–255 |
| R | 0x52 | UART baud rate setting | 0–5 |
| D | 0x44 | UART data output mode | 0–3 |
| X (table) / 'P' (description) | 0x50 | Junction information: 0 = clear counter, 1 = send counter value | 0–1 |
| P (table) / 'O' (description) | 0x4F | Line/sensor information: 1 = return sensor digital byte (MSB = S7), 2 = return line position 0–70 | 1–2 |

Worked examples from the manual [UM]: `0x01 0x43 0x00 0x44` = calibrate (address 1); `0x02 0x43 0x00 0x45` = calibrate (address 2); `0xF0 0x44 0x03 0x37` = set UART mode 3; `0x01 0x44 0x02 0x47` = set UART mode 2; `0x01 0x53 0x50 0xA4` = contrast 80; `0x01 0x4F 0x02 0x52` = request line position.

**Analog output** [UM 6.4.1.2]: Position = (AN voltage / 4.5 V) x 70; a line centred between S3 and S4 reads about 2.25 V (position 35); 5 V means no line. Only VIN, GND and AN are needed; add JPULSE for junction counting.

**LCD / buttons** [UM 6.2]: MODE steps through the menu; SEL enters a menu and adjusts its value (press-and-hold SEL for fast increment of contrast and address); press MODE to return to the selector; press-and-hold MODE exits. Menu items: LCD CON, CALB, LINEMODE, THRES (0–7), J WIDTH (3–8), UART ADD (0–255), BAUDRATE, UARTMODE (0–3), LCD B/L (0–10, 0 = off), EXIT. Normal screen shows line position 0–70 and a bar chart; "****" = no line. Hidden debug mode: press-and-hold SEL for a few seconds shows each sensor's 10-bit raw value (SEL switches sensor); exit only by power cycling.

**Default settings** [UM 6.3]: Line Mode = Light On; Thres = 4; J_width = 5; UART Add = 1; Baudrate = 0 (9600); UART Mode = 0; LCD BL = 2.

**Calibration** [UM 6.1]: press MODE twice to reach CALB, press SEL to start, then swing the sensor bar across the bright and dark surfaces so every sensor pair sees both; the brightest and darkest values are saved to non-volatile memory. Same method for Dark-On and Light-On. With multi-colour backgrounds, calibrate on the colour pair with the least brightness difference (example: white line, calibrate on the green background). Calibration can also be started by UART command C — the robot must then be rotated over the line and background.

## Rules and gotchas (for code, wiring and tutorials)
- **Supply is 7.5–20 V (12 V typical), NOT 5 V or 3.3 V** [UM]. Typical wiring uses a 9–12 V supply [UM]. Do not connect VIN to a 5 V rail.
- **Outputs are 5 V logic** (Output Signal 5 V; Port B outputs 5 V = "1"; JPULSE 0/5 V; AN up to 5 V) [UM]. For a 3.3 V controller (e.g. Raspberry Pi, Pico, ESP32) TX, AN, JPULSE and O0–O7 need level shifting or a divider — derived from [UM] levels; the manual itself shows only 5 V PIC controllers. Inputs accept VIH 2–5 V [UM], so RX/UEN can be driven from 3.3 V logic (derived).
- **I/O pins are limited to 20 mA** [UM].
- **UART data is sent only while UEN is pulled low** and TX floats otherwise [UM]. A tutorial that reads nothing from TX has usually forgotten UEN.
- **Default UART mode is 0 = no output** [UM]. Set UARTMODE (menu or command D) before expecting streamed data.
- **No-line value differs by interface**: UART mode 2 / command O returns 255; analog gives 5 V; LCD shows "****" [UM]. The C library returns 127 for no line and -35..35 for position [UM-LIB].
- **Position is 0–70 (centre 35) in the manual and firmware**; the C library remaps it to -35..35 centred on 0 [UM][UM-LIB]. Say which convention a tutorial uses.
- **Checksum is the low byte of the sum**, and the four bytes must be sent back-to-back (20 ms inter-byte limit) [UM].
- **Each LSA08 on a shared UART needs a unique address** (set via UART ADD); only the matching unit replies [UM]. Multiple units on analog need one ADC channel each plus JPULSE wiring if junction counting is wanted [UM].
- **Threshold is "number of LCD bars"** (0–7) needed to count a sensor as on-line; junction width is the number of sensors (3–8) that must see the line to count a junction [UM].
- **Line mode names**: Dark-On = dark line on bright background (black on white); Light-On = bright line on dark background. Factory default is Light-On [UM] — black-line-on-white users must change it.
- **Minimum line width 15 mm; sensing distance 1–5 cm (3 cm typical)** [UM].
- **Polling by command is slower than streaming**; for fast robots use UEN streaming of the position [UM].
- Refresh rate: state **100 Hz** [UM]; Tindie's "up to 200Hz" is a lower-authority source (see Conflicts).
- Do not say "Arduino library": the only Cytron library is a PIC C library (LSA08.h) with user-supplied UART/ADC functions [UM-LIB][GH].

## Power and electrical limits
- Operating voltage 7.5 V min / 12 V typ / 20 V max (absolute maximum rating) [UM]; "typically user can connect a 9 to 12V supply" [UM].
- Current consumption at 12 V: 25.3 / 25.5 / 130 mA (min/typ/max); backlight level raises current [UM].
- Max current per I/O signal pin: 20 mA [UM].
- VIH 2–5 V, VIL 0–0.8 V; output signal 5 V [UM].
- Power polarity protection on the supply [UM].
- Operating temperature: **not stated** [UM].

## Software support
- Cytron C library "LSA08.h" (PIC, author "IH", Cytron R&D) with manual "LSA08 C Library Manual V1.1 Jan 2013" [UM-LIB][GH]. The user defines `LSA08_USE_UART` or `LSA08_USE_ANALOG`, `LSA08_ADD` (address), `LSA08_UARTMODE` (0–3), `LSA08_UE` pin, and must supply `UART_INIT/UART_SEND/UART_REC/UART_DUMP` (UART) or `ADC_INIT/GET_ADC` (analog); example code targets PIC16F887/PIC16F877 at 20 MHz, 57600 baud [UM-LIB].
- Library functions: `LSA08_Init`, `LSA08_GetPosition` (UART mode 2 or analog; -35..35, 127 = no line), `LSA08_GetSensor` (UART mode 1), `LSA08_GetJunction`, `LSA08_ClearJunction`, `LSA08_Calibrate`, `LSA08_UARTMode(0-3)`, `LSA08_JunctionWidth(1-8)`, `LSA08_Threshold(0-7)`, `LSA08_LineMode(DARK_ON/LIGHT_ON)`, `LSA08_Contrast(0-255)`, `LSA08_BL(0-10)`; each returns 1 = success, 0 = fail [UM-LIB]. `ANALOG_MIDVAL` (typically 115, 8-bit ADC value at 2.25 V) sets the analog centre [UM-LIB].
- GitHub repo https://github.com/CytronTechnologies/Cytron_LSA08 holds: `LSA08 Library`, `IFC_DI08_linefollow`, `IFClinefollow`, `MC40A_Analog_PID`, `MC40A_UART_PID`, `SK40C_MD10C_PID/SK40CMD10C_linefollow.X`, `LSA08_User_Manual.pdf` [GH]. No library.properties / Arduino package found [GH].
- Demo video linked from Tindie: https://www.youtube.com/embed/qiH-9bH5wMg [PP: Tindie].

## Compatibility and accessories
- Manual example setups: SK40C + 2 x MD10C (UART, analog or Port B), MC40A (UART or analog; "designed for LSS05 but LSA08 can be used instead"), IFC system (IFC-MB00, IFC-PC00, IFC-AI08 analog with 5 V reference jumper, IFC-DI08 digital with 12 V jumper, IFC-BH02/BL02, IFC-CP04), MC40SE (UEN/JPULSE to RB6, 12 V jumper), all on the DC Geared Mobile Robot Base Set HD-BSC-SPG-G with SPG30-20K motors [UM].
- Works with "any" controller via digital parallel, UART or analog [UM 5.5]; multiple LSA08 per controller via addressed UART or separate analog channels [UM 5.6].
- Accessory in the box: LSA08 cable connector [UM].

## Common mistakes / troubleshooting
- **Nothing on TX** → UEN not pulled low, or UART mode left at default 0; set mode 1/2/3 and hold UEN low [UM].
- **No "OK" after a command** → wrong address, command, checksum or baud, or bytes sent with gaps > 20 ms; check UART ADD on the LCD [UM].
- **Position reads 255 / 5 V / "****"** → no line detected; recalibrate, check line mode (Dark-On vs Light-On) and threshold [UM].
- **LCD blank** → wrong contrast; press MODE once, SEL once, then hold SEL to adjust [UM].
- **Board stuck showing raw values** → hidden debug mode; power-cycle to exit [UM].
- **Erratic data at high baud** → "higher baudrate is more prone to error if the wiring is not good" [UM].
- **Junctions not counted** → junction width (3–8) set higher than the number of sensors the cross actually covers [UM].
- **Damaged inputs on a 3.3 V board** → outputs are 5 V logic [UM]; add level shifting.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Refresh rate | [UM] table: 100 Hz | [PP] my.cytron.io (read 2026-10-20) and Tindie: "Refresh rate up to 200Hz" | [UM] wins: state 100 Hz; ask [DT] whether newer firmware reaches 200 Hz |
| Warranty | [UM] (2012) "valid for 6 months"; index says "6 months or 1 year" | [PP] 12 months (2026) | Commercial term: use the current product page's 12 months and cite [PP]; the manual figure is historical |
| Junction width range | [UM] menu and command J: 3–8 | [UM-LIB] `LSA08_JunctionWidth(1-8)` | [UM] wins: 3–8 |
| Junction/sensor command letters | [UM] command table: X = 0x50 junction, P = 0x4F line/sensor | [UM] description section: 'P' = 0x50 junction, 'O' = 0x4F line/sensor (same hex values) | Use the hex values (0x50, 0x4F); the ASCII letters are inconsistent inside the manual |
| UART mode count | [UM] "4 available formats ... 0 to 3" | [UM] "There are 3 data modes available" (mode 0 = no data) | Four settings (0–3), three carry data |
| UART mode 3 heading | [UM] section header says "UART Mode 2 sends continuous bytes of sensors' raw value" | [UM] table: mode 3 = raw packet | Typo; raw packet is mode 3 |
| Position convention | [UM] 0–70, centre 35, 255 = no line | [UM-LIB] -35..35, centre 0, 127 = no line | Both correct in their context; say which one you use |
| Typical current | [UM] table typ 25.5 mA | [UM] text "typically around 26mA" | Not a contradiction (rounding) |

## Needs verification
- The my.cytron.io Drive PDF (https://drive.google.com/file/d/0BzFWfMiqqjyqXzFaMTNHMy1pWUE/view) could not be opened here; the GitHub copy with the same title/V1.1/June 2012 was used. Confirm they are the same revision.
- Dimension drawing: "3" (mm) near a corner mounting hole is unlabelled — hole diameter or edge offset. Mounting-hole diameter not stated in text.
- Port A/B connector type (2x5 box header is implied by the drawing; not stated in text) and the cable connector's length/pinout.
- Operating temperature range; JPULSE pulse width/polarity timing (figure only shows 0 V→5 V pulse).
- Whether current firmware still has the hidden debug mode and the 20 ms packet timeout.
- Weight, and whether the SK40C/MC40A/IFC sample code is still downloadable from Cytron.

## Sources
- [UM] Advance Line Following Sensor Bar LSA08 — User's Manual V1.1, June 2012 — local file `LSA08_User_Manual.pdf` fetched from https://raw.githubusercontent.com/CytronTechnologies/Cytron_LSA08/master/LSA08_User_Manual.pdf (same document as the product-page link https://drive.google.com/file/d/0BzFWfMiqqjyqXzFaMTNHMy1pWUE/view — not opened; mirror: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-108/pdf/cytron-advanced-auto-calibrating-line-sensor-array-manual.pdf)
- [UM-LIB] LSA08 C Library Manual V1.1, Jan 2013 — https://docs.google.com/document/d/16Oy4tDjDCd2lyAl9kVa1tXlG_qfF2iXjrFWCvjgRw5k/view
- [GH] https://github.com/CytronTechnologies/Cytron_LSA08 (LSA08.h read via raw.githubusercontent.com)
- [PP] Product page https://my.cytron.io/p-advanced-auto-calibrating-line-sensor (read by coordinator 2026-10-16: RM204.75, in stock 53, warranty 12 months)
- [PP: Tindie] https://www.tindie.com/products/cytron/advanced-auto-calibrating-line-sensor/ (cross-check only)
