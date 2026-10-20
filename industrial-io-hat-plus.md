# Industrial IO HAT+ — Verified Reference

| | |
|---|---|
| Family | Raspberry Pi accessories (industrial) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read. Sale status, price, packing list and the public datasheet link are now Cytron-stated; pinout and dimensions are images only |
| Primary source | *Industrial IO HAT+ — IR4.0 Industrial I/O HAT+, Datasheet*, **Rev 1.0, Sep 2025** (Google Doc last modified 2025-10-29), Cytron Technologies Sdn Bhd |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

No separate user manual exists: the reseller page links this same Google Doc as "User guide and datasheet" [3P]. No [UM] or [DT] source was used.

## What it is
An industrial I/O HAT+ for the **Raspberry Pi 5** [DS]. It adds 1x RS485, 1x RS232, 6x isolated digital inputs (up to 50V) and 4x isolated digital outputs (up to 50V), takes a 10–30 VDC surge-protected supply and powers the Raspberry Pi 5 through the 40-pin header (max 5 A at 5V) [DS]. It also has 2 programmable LEDs, a programmable active buzzer, status LEDs, a 5V display power connector and header pins for an optional LetsTrust TPM module [DS].
The datasheet subtitle is "IR4.0 Industrial I/O HAT+" [DS]. It was co-developed with Argon40 to fit the Argon Industria HMI enclosures for Raspberry Pi 5: Argon40 designed the enclosure and screen, Cytron designed the HAT electronics . It is a HAT, not a computer: it needs a Raspberry Pi 5 (not included) [DS].

## Specifications
Datasheet section 1 (Features) and section 2 (Specifications), every row:

| Item | Value | Src |
|---|---|---|
| Raspberry Pi | Support Raspberry Pi 5 | [DS] |
| HMI enclosure | Argon Industria HMI 10CS Enclosure for Raspberry Pi 5; Argon Industria HMI 8CS Enclosure for Raspberry Pi 5; Argon Industria HMI 7C Enclosure for Raspberry Pi 5; Argon Industria HMI 5C Enclosure for Raspberry Pi 5; Argon Industria Basic Industrial Enclosure for Raspberry Pi 5 | [DS] |
| Interfaces | 1x RS485; 1x RS232; 6x isolated digital input (up to 50V); 4x isolated digital output (up to 50V) | [DS] |
| Power supply | DC 10-30V surge protected | [DS] |
| Additional features | Support LetsTrust TPM Module (Optional); 2x programmable LED; Status LED for RS485, RS232, DIN & DOUT; 1x programmable active buzzer | [DS] |
| Power input voltage (surge protected up to 60V 20ms) | min 10, max 30 VDC | [DS] |
| Maximum current for Raspberry Pi (5V) | max 5 A | [DS] |
| Isolated digital input, low level (VIL) | max ±0.8 V | [DS] |
| Isolated digital input, high level (VIH) | min ±3, max ±50 V | [DS] |
| Isolated digital input, isolation voltage | 3750 Vrms | [DS] |
| Isolated digital output, voltage | max 50 V | [DS] |
| Isolated digital output, current | max 500 mA | [DS] |
| Isolated digital output, isolation voltage | 1500 Vrms | [DS] |
| RS485 maximum baud rate | 1 Mbps | [DS] |
| RS232 maximum baud rate | 250 kbps | [DS] |
| Operating temperature | -20 to 60 ℃ | [DS] |
| Relative humidity (non-condensing) | 10 to 80 % | [DS] |
| Fuse | 4A replaceable fuse for the system | [DS] |
| RS485 termination | Onboard 120 ohm termination resistor | [DS] |
| RS485 direction control | Automatic | [DS] |
| Digital output type | Dry contact, driven by solid state relays, DC or AC load up to 50V 500mA, built-in surge protection | [DS] |
| Dimensions | Not readable (datasheet section 6 is an image) — see *Needs verification* | — |

Note: the datasheet spec table is slightly mangled in the text export (merged cells), but each value above maps to one row of the original table without ambiguity.
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Page notes:** designed to be used with the Argon40 Industria Case; supports a TPM module (LetsTrust TPM for Raspberry Pi is linked) [PP].
- **Packing list:** 1x Industrial IO HAT+, 1x 20-pin pluggable terminal block, 3x M2.5 × 21 mm PCB stand, 1x pinout sticker [PP].
- **Resources:** datasheet (public Google Doc), 3D CAD [PP]. Feature, pinout and dimension images are on the page (`hat-ind-ag-pinout.png`, `hat-ind-ag-dimension.png`) — not read.
- Page image paths use the code **HAT-IND-AG** [PP].

## Interfaces, terminals and pin mapping
Board layout (datasheet section 3) [DS]:
1. Active buzzer — user-programmable active piezo buzzer, **GPIO23, active high**.
2. Status LEDs — 485 (RS-485 activity), 232 (RS232 activity), DI 0-5 (on when input triggered), DO 0-3 (on when output activated), LED0 (user, **GPIO17**), LED1 (user, **GPIO18**).
3. Display power connector — 5V power supply connector for the display.
4. TPM module pin headers — plug in the LetsTrust TPM module.
5. 4A fuse — 4-Amp replaceable fuse for the system.
7. Raspberry Pi headers — connect to the Raspberry Pi 40-pin GPIO header.

Pin mapping (datasheet 5.1; "GPx" = Broadcom GPIO number, not header pin number) [DS]:

| Function | Signal | Raspberry Pi peripheral | GPIO |
|---|---|---|---|
| Digital input | DI0 / DI1 / DI2 / DI3 / DI4 / DI5 | GPIO | GPIO4 / GPIO5 / GPIO6 / GPIO16 / GPIO22 / GPIO27 |
| Digital output | DO0 / DO1 / DO2 / DO3 | GPIO | GPIO19 / GPIO20 / GPIO21 / GPIO26 |
| RS485 | TX / RX | UART0 | GPIO14 / GPIO15 |
| RS232 | TX / RX | UART4 | GPIO12 / GPIO13 |
| LetsTrust TPM | RSTn / IRQn / CS0n / CS1n | GPIO | GPIO24 / GPIO25 / GPIO8 / GPIO7 |
| LetsTrust TPM | MISO / MOSI / SCK | SPI | GPIO9 / GPIO10 / GPIO11 |
| User LED | LED0 / LED1 | GPIO | GPIO17 / GPIO18 |
| Active buzzer | — | GPIO | GPIO23 |

IO terminal: power input, RS485 (A, B, GND), RS232, 6 DI with a **common pin DIC**, 4 DO with a **common pin DOC** [DS]. The exact terminal pin order is only shown as an image in the datasheet and was not readable — see *Needs verification*. A pinout sticker is included in the box .

## Rules and gotchas (for code, wiring and tutorials)
- **Raspberry Pi 5 only.** The datasheet lists only "Support Raspberry Pi 5" [DS]. Do not write that it works on Pi 4 or CM boards.
- **UARTs are off by default.** Add `dtoverlay=uart0` (RS485) and/or `dtoverlay=uart4` (RS232) to `/boot/firmware/config.txt` [DS]. Use exactly this method and path; the datasheet gives no other.
- RS485 = UART0 on GPIO14/15; RS232 = UART4 on GPIO12/13 [DS]. Do not swap them.
- **RS485 has automatic direction control** [DS]: no DE/RE GPIO toggling in code.
- **RS485 has an onboard 120 ohm termination resistor; no external resistor needed** [DS]. The datasheet does not describe a way to disable it.
- RS485 works with A-B only, but Cytron recommends also connecting GND for better noise immunity [DS].
- RS485 max 1 Mbps; RS232 max 250 kbps [DS]. The datasheet does not say the RS485 port is isolated — do not call it "isolated RS485".
- **Six DIs share one common (DIC)**; inputs are bidirectional and take PNP or NPN sensors up to 50V [DS]. VIL max ±0.8 V, VIH ±3 to ±50 V [DS].
- **Four DOs share one common (DOC)** and are **dry contact** solid-state-relay outputs: they switch an external load supply, DC or AC, up to 50V 500mA [DS]. 50 V is the maximum, so never wire mains voltage to them.
- For inductive loads (e.g. a relay coil) a flyback diode in parallel with the load is recommended to reduce EMI; the outputs still have built-in surge protection [DS].
- Buzzer GPIO23 is an **active** buzzer, active high [DS]: drive it on/off; do not write PWM melody code for it.
- User LEDs: LED0 = GPIO17, LED1 = GPIO18 [DS].
- With the TPM module fitted, SPI0 (GPIO9/10/11) plus GPIO7, GPIO8, GPIO24, GPIO25 are used by the TPM [DS]. Do not reuse them in a tutorial that also uses the TPM.
- The pin map assigns every GPIO from GPIO4 to GPIO27; GPIO2/GPIO3 are not listed [DS]. GPIO0/GPIO1 (ID_SD/ID_SC) are reserved for the HAT ID EEPROM by the Raspberry Pi HAT spec [VEN].
- **HAT+ EEPROM:** lets Raspberry Pi OS recognise the HAT+ and tells the Pi 5 the HAT+ can supply 5A; this is only supported from **bootloader version 2025-06-29 or greater** . Tutorials should update the Pi 5 bootloader. (The HAT+ EEPROM format has a `current_supply` field, in milliamps [VEN].)
- No earth connection is required [DS].

## Power and electrical limits
- Power input: 10–30 VDC on the IO terminal, surge protected up to 60V 20ms [DS].
- Output to the Raspberry Pi (5V): max 5 A [DS]. Internal docs describe this as 5V@5A continuous through the Pi 5 40-pin header .
- Power input is fuse-protected by a **4A replaceable fuse**; the fuse might break on surge or overcurrent. If the device does not power up, check and replace the fuse [DS].
- 5V display power connector for the display [DS]; internal docs say it is for powering the Raspberry Pi Touch Display V1 or V2 . Its current rating is not stated.
- DI: up to ±50 V, isolation 3750 Vrms [DS]. DO: max 50 V, max 500 mA, isolation 1500 Vrms [DS].
- Operating temperature -20 to 60 ℃; humidity 10–80 % non-condensing [DS].
- HAT power consumption: not stated.

## Software support
- OS: Raspberry Pi OS on the Raspberry Pi 5; UART overlays `dtoverlay=uart0` and `dtoverlay=uart4` in `/boot/firmware/config.txt` [DS].
- All DI/DO/LED/buzzer lines are plain Raspberry Pi GPIOs (see pin map) [DS].
- No Cytron library, example code or GitHub repo was found in the sources.

## Compatibility and accessories
- Host: Raspberry Pi 5 [DS].
- Enclosures (datasheet names): Argon Industria HMI 10CS, HMI 8CS, HMI 7C, HMI 5C, and Argon Industria Basic Industrial Enclosure, all for Raspberry Pi 5 [DS].
- Optional: LetsTrust TPM module (not included) [DS].
  - CK-AG-HMI-5C — HMI Enclosure with Official RPi 5" Touch Screen Display 2
  - CK-AG-HMI-7C — HMI Enclosure with Official RPi 7" Touch Screen Display 2
  - DS-AG-HMI-8CS — HMI Enclosure with 8" HDMI Display
  - DS-AG-HMI-10CSN — HMI Enclosure with 10" HDMI Display
  - CK-AG-HMI-5C-CP / CK-AG-HMI-7C-CP / CK-AG-HMI-8CS-CP / CK-AG-HMI-10CSN-CP — complete kits (5"/7"/8"/10")

## Common mistakes / troubleshooting
- Device does not power up → check the 4A fuse and replace it if needed [DS]; check input is 10–30 VDC [DS].
- No data on RS485/RS232 → overlay not added (`dtoverlay=uart0` / `dtoverlay=uart4`) or wrong UART used (RS485 = UART0, RS232 = UART4) [DS].
- Unstable RS485 → connect GND as well as A-B [DS]; do not add a second termination at the HAT, one 120 ohm is onboard [DS].
- Baud rate too high → RS232 is limited to 250 kbps, RS485 to 1 Mbps [DS].
- Load does not switch on a DO → outputs are dry contact; the load needs its own supply wired through DOC [DS].
- EMI when switching a relay coil → add a flyback diode across the load [DS].
- Writing GPIO numbers as header pin numbers → the datasheet "GPx" values are BCM GPIO numbers [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Basic enclosure name | "Argon Industria Basic Industrial Enclosure for Raspberry Pi 5" [DS] | "Industria Base" / "Argon Industria Base Industrial Enclosure" [3P] | Datasheet name used in text; the reseller name may be Argon40's retail name — verify |
| Continuous vs max | "Maximum" 5 A [DS] | "5V@5A (continuously)"  | Text says max 5 A [DS]; continuous rating is internal only |

## Needs verification
- **IO terminal pin order** (20-pin): shown only as an image in datasheet 5.2 and in "HAT-IND-AG Pinout.png"; not readable as text. Do not write a terminal pin order until checked.
- **Board dimensions and mounting holes**: datasheet section 6 is an image; OCR of the internal PCBA dimension drawing is mangled (shows figures like 86.50, 58.00, 4 x M2.5) — do not state dimensions.
- Block diagram (datasheet section 4) is an image only.
- Logic polarity of DI reading (triggered = GPIO high or low?) and DO drive (GPIO high = output on?) — not stated, except buzzer active high.
- Whether PNP and NPN sensors can be mixed at the same time (all six DIs share one DIC).
- Whether the RS485 port is isolated (not stated).
- Whether the onboard 120 ohm RS485 termination can be disabled.
- Display power connector type and current rating.
- Linux device names for UART0/UART4 on Pi 5 (e.g. /dev/ttyAMA0, /dev/ttyAMA4) — not in any source read.
- TPM device-tree overlay name and setup steps — not in sources.
- HAT+ EEPROM contents (vendor/product strings, `current_supply` value, any auto-loaded overlay) — not in sources.
- Whether the Pi 5 may also be powered from its own USB-C while the HAT supplies 5V — not stated.
- DI max input frequency, DI input current, total DOC common current — not stated.
- Read the product page pinout and dimension images (`hat-ind-ag-pinout.png`, `hat-ind-ag-dimension.png`).

## Sources
- [DS] Industrial IO HAT+ Datasheet, Rev 1.0, Sep 2025 (Google Doc, modified 2025-10-29): https://docs.google.com/document/d/1G8XOqDg5tSYu-hFeNG1x2qfTjAIdBlXN-yGC49WR2nQ/edit
- [PP] Cytron product page (not read, blocked): https://my.cytron.io/p-industry-hat-plus-for-raspberry-pi-5
- [PP] Cytron assembly tutorial (not read, blocked): https://my.cytron.io/tutorial/argon40-industria-basic-enclosure-with-rpi5-and-cytron-io-hat-plus-assembly-guide
- [VEN] Raspberry Pi HAT+ EEPROM tools and settings template: https://github.com/raspberrypi/utils/tree/master/eeptools
- [VEN] Raspberry Pi HAT (legacy) README, ID_SC/ID_SD rule: https://github.com/raspberrypi/hats/blob/master/README.md
- [3P] The Pi Hut, Industrial IO HAT+ for Pi 5 and Argon Industria Cases: https://thepihut.com/products/industrial-io-hat-for-pi-5-and-argon-industria-cases
