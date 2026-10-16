# IRIV IO Controller — Verified Reference

| | |
|---|---|
| Product code | `IRIV-IOC` (datasheet page header "Datasheet - IRIV-IOC") [DS] |
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | *IRIV IO Controller — IR4.0 Industrial I/O Controller, Datasheet*, **Rev 1.0, July 2024**, Cytron Technologies Sdn Bhd |

**Authority rule:** Datasheet/manual [DS] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
An industrial I/O controller built on the **Raspberry Pi RP2350A microcontroller** (not a Raspberry Pi computer or Compute Module). It is a standalone controller, not a Linux device. It has 11 isolated digital inputs, 4 isolated digital outputs, 2 analog inputs, isolated RS485, W5500 Ethernet, an RTC and a passive buzzer, in a fanless metal DIN-rail enclosure, powered from 10–30 VDC [DS]. The datasheet subtitle is "IR4.0 Industrial I/O Controller" [DS]. The [WIKI] calls it RP2350-based: this is correct, because the RP2350A is a variant of the RP2350 family [DS][VEN].
Applications as framed by the staff wiki: "lightweight automation, industrial I/O expansion, MODBUS RTU/TCP gateways, data acquisition, sensor monitoring, and edge control systems" [WIKI]. A Cytron video frames it as a pulse counter for flow meters, energy meters and rotary encoders, with Modbus-register totals polled by a PLC, SCADA or dashboard .

## Specifications
| Item | Value | Src |
|---|---|---|
| Microcontroller | Raspberry Pi RP2350A, Dual Cortex-M33 @ 150MHz | [DS] |
| RAM | 520KB on chip SRAM | [DS] |
| Storage | 2MB flash memory | [DS] |
| USB | 1x USB-C (for programming and configuration; can also power the unit) | [DS] |
| Ethernet | 1x RJ45 via Wiznet W5500 (embedded 10BaseT/100BaseTX PHY) | [DS] |
| RS485 | 1x isolated RS485 | [DS] |
| Digital inputs | 11x isolated digital input (up to 50V) | [DS] |
| Digital outputs | 4x isolated digital output (up to 50V) | [DS] |
| Analog inputs | 2x 12-bit analog input (0 - 10.56V / 0 - 42.58mA), non-isolated | [DS] |
| Power input, Terminal 1 | 10 – 30 VDC (surge protected up to 60V 20ms) | [DS] |
| Power input, USB-C | 4.9 – 5.2 VDC | [DS] |
| Power consumption | max 0.7 W | [DS] |
| DI low level (VIL) | max ±0.8 V | [DS] |
| DI high level (VIH) | ±3 to ±50 V | [DS] |
| DI max pulse frequency (50% duty cycle) | 5000 Hz | [DS] |
| DI isolation voltage | 3750 Vrms | [DS] |
| AI resolution | 12 bit | [DS] |
| AI voltage mode | 0 – 10.56 V | [DS] |
| AI current mode | 0 – 42.58 mA | [DS] |
| AI input impedance, voltage mode | 32K Ω | [DS] |
| AI input impedance, current mode | 248 Ω | [DS] |
| DO voltage | max 50 V (DC or AC load) | [DS] |
| DO current | max 500 mA | [DS] |
| DO isolation voltage | 1500 Vrms | [DS] |
| RS485 max baud rate | 500 kbps | [DS] |
| RS485 isolation voltage | 5000 Vrms | [DS] |
| Operating temperature | -20 to 70 ℃ | [DS] |
| Relative humidity (non-condensing) | 10 – 80 % | [DS] |
| RTC | PCF85063A, I2C address 0x51, CR2032 backup cell (cell fitted by user: "Insert a CR2032 coin cell") | [DS] |
| Buttons | 1x reset, 1x boot, 1x programmable (user) | [DS] |
| LEDs | 1x programmable LED (USR); status LEDs PWR, 485, DOUT 0-3, DIN 0-10 | [DS] |
| Buzzer | 1x passive buzzer (variable-frequency tone or melody) | [DS] |
| Enclosure | Metal enclosure, fanless design, DIN rail mountable | [DS] |
| Dimension | (L)140mm x (W)60mm x (H)36mm (metal enclosure only, excluding DIN socket & connectors) | [DS] |
| Drawing extras | DIN bracket adds 8mm; pluggable terminals stick out 15.5mm | [DS §6 drawing] |

## Interfaces, terminals and pin mapping
**RP2350A pin mapping** (DS §5.1; the DS writes both "GP0" and "GPIO0")
| Function | Signal | Peripheral | RP2350A pin |
|---|---|---|---|
| Digital Input | DI0 – DI10 | GPIO | GP0 – GP10 (DIn = GPn) |
| Analog Input | AN0 / AN1 | ADC | GP26 / GP27 |
| Digital Output | DO0 / DO1 / DO2 / DO3 | GPIO | GP12 / GP13 / GP14 / GP15 |
| RS485 | TX / RX | UART1 | GP24 / GP25 |
| Ethernet (W5500) | INT / RESET / CSn | GPIO | GP18 / GP23 / GP21 |
| Ethernet (W5500) | MOSI / MISO / SCK | SPI0 | GP19 / GP20 / GP22 |
| Real Time Clock (PCF85063) | SDA / SCL | I2C0 | GP16 / GP17 |
| User Programmable Button | — | GPIO (active low) | GP28 |
| User Programmable LED | — | GPIO | GP29 |
| Passive Buzzer | — | GPIO/PWM | GP11 |

**Terminal 1** (left pluggable block, 2 rows of 8; read from the DS §5.2 terminal drawings) [DS]
| Left row (top → bottom) | Right row (top → bottom) |
|---|---|
| V- (power negative) | V+ (10-30V) |
| DGND (dry-contact ground) | A (RS485) |
| S/S0..4 (common for DIN Group 1) | B (RS485) |
| DI0 | G (RS485 ground) |
| DI1 | AGND |
| DI2 | AGND |
| DI3 | AN0 |
| DI4 | AN1 |

**Terminal 2** (right pluggable block) [DS]
| Left row (top → bottom) | Right row |
|---|---|
| DGND, S/S5..10, DI5, DI6, DI7, DI8, DI9, DI10 | DO0 (2 contacts), DO1 (2), DO2 (2), DO3 (2) |

**Bottom-panel DIP switches** [DS]
| Switch | Function |
|---|---|
| RS485 R-Term | ON connects the 120 Ω termination resistor. Only needed on the first and last device of the RS485 chain |
| AN-IN MODE | Sets voltage or current mode. The DS drawing shows **one switch per channel** (AN0 and AN1) |

**Front panel** [DS]: USB-C (marked PROG), RESET and BOOT (pinhole buttons, press with a paperclip), USER button, status LEDs, RJ45 (ETH).

## Rules and gotchas (for code, wiring and tutorials)
- **It is a microcontroller, not a Linux computer.** No OS, no Raspberry Pi OS, no Node-RED on the device. DS §5.2.5 says the outputs are "controlled directly from the Raspberry Pi GPIO". This means the RP2350A GPIO12–15, not a Raspberry Pi computer [DS].
- **Digital inputs are active high and split into two groups.** Group 1 = DI0–DI4 with common S/S0..4, on **Terminal 1**. Group 2 = DI5–DI10 with common S/S5..10, on **Terminal 2**. Each group can be wired sink or source on its own, so PNP and NPN sensors can be used at the same time [DS].
- **DI wiring from the DS drawings:** dry contact goes between **DGND** and DIx (uses the built-in isolated supply, no external power). PNP sensors: external supply **−** to S/S, sensor output to DIx. NPN sensors: external supply **+** to S/S, sensor output to DIx [DS §5.2.4].
- **DGND is the dry-contact ground**, shared by both DIN groups. It is not the power-supply return; power goes to V+ / V- [DS].
- **Digital outputs** are dry-contact solid-state relay outputs, active high. They are isolated from the system and from each other, and handle DC or AC loads up to 50V 500mA. Each DO has its own two-contact pair [DS].
- For **inductive loads** (e.g. relay coils), fit a flyback diode in parallel with the load to cut EMI. The outputs have built-in surge protection, so running without the diode is still safe [DS].
- **Analog inputs are NOT isolated.** AGND is shared with system GND [DS].
- **Analog scaling (voltage mode):** MCU pin voltage = AN × 5/16, so 10.56 V full scale reads as 3.3 V at the ADC [DS schematic]. The divider is 22K + 10K to GND (= 32 kΩ). In current mode, the DIP switch adds a 250 Ω shunt to GND, which gives 248 Ω effective input impedance. 42.58 mA × 248 Ω ≈ 10.56 V [DS schematic].
- In CircuitPython, `analogio.AnalogIn.value` is scaled to 16-bit (0–65535) regardless of the 12-bit ADC, so convert from that range [VEN].
- **RS485** has automatic direction control, so code does not toggle a DE/RE pin. It is on **UART1, TX GP24 / RX GP25**. A and B are usually enough, but the DS recommends also wiring G (GND) for noise immunity [DS].
- **Ethernet:** W5500 on **SPI0** (MOSI GP19, MISO GP20, SCK GP22, CSn GP21), INT GP18, RESET GP23. SPI runs up to 80MHz, SPI mode 0 or 3 [DS].
- **I2C0** (SDA GP16 / SCL GP17) carries the PCF85063A RTC at **0x51** [DS].
- **User button GP28 is active low**, so a press reads LOW. **USR LED = GP29. Buzzer = GP11** and is passive: drive it with PWM at a frequency, because a DC level gives no tone [DS].
- **Bootloader:** hold BOOT while resetting the RP2350A (press RESET) [DS]. The board then appears as a USB drive for drag-and-drop UF2 upload [WIKI][VEN].
- No earth connection is required [DS].

## Power and electrical limits
- Terminal 1: 10–30 VDC, surge protected up to 60V for 20ms. Protected by a **500mA PTC**, which may open on a surge or overcurrent. If the unit will not power up, let the PTC cool down; if it still fails, contact Cytron support [DS].
- USB-C: 4.9–5.2 VDC. USB-C alone can power the unit [DS].
- Power consumption max 0.7 W [DS].
- DI: up to ±50 V high level, ±0.8 V max low level, 5000 Hz max pulse rate at 50% duty [DS].
- DO: max 50 V, 500 mA per channel, AC or DC [DS].
- Isolation: DI 3750 Vrms, DO 1500 Vrms, RS485 5000 Vrms. Analog inputs are not isolated [DS].
- Environment: -20 to 70 ℃, 10–80 %RH non-condensing [DS].

## Software support
- The DS names no software. All entries below come from lower-authority sources.
- **CircuitPython:** official board build "IRIV IO Controller (RP2350)" on circuitpython.org (latest stable 10.3.1 at time of check), installed as a UF2 file [VEN: https://circuitpython.org/board/cytron_iriv_io_controller/].
- Cytron tutorial "Getting Started with IRIV IO Controller with CircuitPython" by Hussien Jawhar Sathik, published 11 Nov 2024. It covers buttons/LEDs/buzzer, DI/DO, analog, RTC, RS485/MODBUS RTU, Ethernet, IoT (Blynk, ThingSpeak, MQTT) and an agricultural automation example, and links 14 sub-tutorials [WIKI].
- MicroPython and the Raspberry Pi C/C++ SDK: the [WIKI] lists both as "compatible with RP2350A". It names no board-specific build or examples (see *Needs verification*).
- Communication: the W5500 has a hardwired TCP/IP stack (TCP, UDP, ICMP, IPv4, ARP, IGMP, PPPoE), 8 simultaneous sockets, 32 KB Tx/Rx buffer, power-down mode and Wake on LAN over UDP. The DS states support for OT (MODBUS TCP) and IT (MQTT/HTTP) communication [DS]. MODBUS RTU runs over the RS485 port [WIKI].
- Default firmware: the [WIKI] says the unit ships preprogrammed as a "MODBUS RTU IO Expander with counter function". This is not in the DS (see *Needs verification*).
- 3D CAD files: Google Drive folder https://drive.google.com/drive/folders/1QK7IpfoBMk6oEOzWjXBTad1ygx5aiyUH [WIKI].

## Compatibility and accessories
- No Compute Module, Raspberry Pi board or HAT. The MCU (RP2350A) is on the board [DS].
- DIN rail mountable through the DIN bracket on the enclosure [DS]. The [WIKI] says "standard 35mm DIN rail", which the DS does not state.
- RTC backup: CR2032 coin cell, inserted by the user [DS]. The cell is not listed as included.
- Terminals are pluggable [DS].
- The RS485 bus is for MODBUS RTU or other RS485 devices. Fit termination only at the bus ends [DS].

## Common mistakes / troubleshooting
- **Unit won't power up** after a surge or overcurrent: the 500mA PTC has opened. Remove power, let it cool and retry; if it still fails, contact support [DS].
- **RS485 errors on long or multi-drop buses:** turn R-Term ON only on the first and last devices. Wire G as well as A/B for noise immunity [DS].
- **Analog reads wrong:** check the AN-IN MODE switch for that channel (voltage vs current). Remember the 5/16 divider. AGND is system GND, so it is not isolated [DS].
- **Sensor doesn't trigger a DI:** check the group's S/S polarity. PNP needs S/S to supply −; NPN needs S/S to supply +. Dry contacts go to DGND, not to S/S [DS].
- **EMI when switching relays:** add a flyback diode across the coil [DS].
- **Can't upload:** hold BOOT, press RESET (both are pinhole buttons, use a paperclip), then copy the UF2 to the drive that appears [DS][WIKI].
- **Treating it as a Pi:** do not write Raspberry Pi OS / Linux / Node-RED-on-device steps for this product [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Terminal for DIN Group 1 (DI0–DI4, S/S0..4) | [DS] Terminal 1 (block diagram + terminal drawings) | [WIKI] hardware-layout: Terminal 2 | [DS] wins: Terminal 1 |
| Terminal 1 pin list | [DS] V-, DGND, S/S0..4, DI0–DI4, V+, A, B, G, AGND ×2, AN0, AN1 | [WIKI] V+, DGND ("ground for power supply"), "S/S RS485 Sink/Source", A, B, AGND, AN0, AN1 | [DS] wins. No RS485 S/S pin exists. Power return is V-; DGND is the dry-contact ground |
| Analog mode switch | [DS] drawings show separate AN0 and AN1 switches | [WIKI] "both channels share the same mode … cannot measure voltage on one and current on the other" | [DS] wins: per-channel switch. Confirm on hardware ([DT]) |
| User button access | [DS] only BOOT and RESET are pinhole buttons | [WIKI] user button is "pinhole, requires paperclip" | [DS] wins |
| Analog current range | [DS] spec table 0–42.58 mA; layout table "(0-40mA)" | [DS] wiring drawing and PCB silk "0-20mA" | Inside the DS. The spec table is the measurement range; 0-20mA is the drawn sensor example. Spec = 0–42.58 mA |
| Analog voltage range | [DS] spec 0–10.56 V | [DS] layout table / drawing "0-10V" | Spec = 0–10.56 V full scale; 0-10V is the nominal sensor range |
| Isolation/impedance/resolution columns | [DS] single values (3750 Vrms, 12 bit, 32K Ω, 248 Ω) | [WIKI] io-reference puts them in the "Minimum" column | [DS]: treat as single stated values |
| Analog isolation | [DS] non-isolated, AGND = system GND | [3P] CNX Software: "2 isolated 12-bit analog inputs" | [DS] wins: non-isolated |
| Ethernet IT protocols | [DS] MQTT/HTTP | [WIKI] "HTTP/HTTPS" | Use [DS] wording. HTTPS is not stated by the DS |
| MCU cores | [DS] Dual Cortex-M33 @ 150MHz | [3P] CNX also lists dual Hazard3 RISC-V cores | [DS] wording for specs. RISC-V cores are a chip fact [VEN], not stated by Cytron |
| Product page URL | [WIKI] https://my.cytron.io/c-industrial-with-raspberry-pi/p-iriv-io-controller | [VEN] circuitpython.org: https://www.cytron.io/p-iriv-ioc; [3P] CNX: https://www.cytron.io/p-iriv-io-controller | Unresolved: none could be opened. KB uses the [WIKI] URL |

No conflict with Drive: the only Drive item is a video subtitle file (see Sources), and it does not contradict the DS.

## Needs verification
- **Product page not read**: my.cytron.io / cytron.io return errors to automated fetches. Product status, price, package contents and the canonical URL are unconfirmed.
- Default firmware "MODBUS RTU IO Expander with counter function" [WIKI only]: confirm with [DT] or [PP], and get the register map.
- Price: CNX Software reports US$64.90 on Cytron's store (Sept 2024) [3P only].
- Whether the AN0/AN1 switches set modes independently (the DS drawings say yes; the wiki says no). Also the switch position for "current" (the schematic says ON connects the 250 Ω shunt).
- Whether isolated DI/DO/RS485 work when the unit is powered from USB-C only. The DS does not say.
- CircuitPython `board` pin names for DI/DO/AN/RS485, and the example code on GitHub: https://github.com/CytronTechnologies/Cytron-IRIV-IO-Controller (cited by CNX; could not be opened). CNX says it has CircuitPython samples for analog input, Ethernet, Modbus, pulse counter and RTC.
- MicroPython / C SDK / Arduino support specific to this board [WIKI says "compatible"; no board build confirmed].
- DIN rail width (35 mm) [WIKI only]. Warranty 12 months [WIKI only]. CR2032 included or not.
- Official Cytron datasheet download URL (the wiki says "available from the product page"; CNX says it is shared through Google Docs).

## Sources
- [PP] Product page (not read; URL as given by the wiki): https://my.cytron.io/c-industrial-with-raspberry-pi/p-iriv-io-controller
- [WIKI] Tutorial: https://my.cytron.io/tutorial/getting-started-with-iriv-io-controller-with-circuit-python
- [VEN] CircuitPython board page: https://circuitpython.org/board/cytron_iriv_io_controller/
- [VEN] Raspberry Pi microcontroller docs: https://www.raspberrypi.com/documentation/microcontrollers/; Wiznet W5500: https://www.wiznet.io/product-item/w5500/
- [3P] CNX Software, 13 Sep 2024: https://www.cnx-software.com/2024/09/13/raspberry-pi-rp2350-industrial-io-controller/
- [3P] Resellers: https://www.robotshop.com/products/cytron-iriv-io-controller-ir40-industrial-i-o-controller, https://thepihut.com/products/iriv-io-controller-ir4-0-industrial-i-o-controller
