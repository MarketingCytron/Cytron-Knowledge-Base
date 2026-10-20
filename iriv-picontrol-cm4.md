# IRIV PiControl CM4 — Verified Reference

| | |
|---|---|
| Product code | `IRIV-PICL` (document code in the user manual header) [UM]; the datasheet does not state a code. Per-variant SKUs (RAM / eMMC / wireless) not confirmed — see *Needs verification* |
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (High priority — status not confirmed): live my.cytron.io product page read (CM4 column of the spec table, CM4 packing lists, resources). Sale status, variants sold, warranty and the public user-manual link are now Cytron-stated |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
An industrial controller built around the Raspberry Pi Compute Module 4 (CM4), in a fanless, DIN-rail-mountable metal enclosure [DS][UM]. It adds isolated industrial I/O (4 DI, 4 DO, 4 AI), isolated RS485 and RS232, two Ethernet ports, an M.2 NVMe socket, a mini PCIe socket, an RTC, a crypto-authentication chip, an OLED status display, a buzzer, a user button and two user LEDs, powered from 10–30 VDC [DS][UM]. The datasheet also lists optional 4G hardware: a Micro SIM socket, a 4G antenna mounting hole and 4G PWR / WWAN LEDs, with the mini PCIe socket "for 4G/LoRa modules (optional)" [DS] (not in the manual — see *Conflicts*). Subtitles: datasheet "IR4.0 CM4 / CM5 Industrial Controller" [DS]; manual "IR4.0 CM4 Industrial Controller" [UM].
- Applications named by the wiki: edge computing, IoT gateways, industrial automation, robotics, data logging, energy management systems [WIKI].
- Positioning (not specs): manual footer tagline "Simplifying Digital Making" [UM]; "IR4.0" / Industry 4.0 controller [DS][UM][WIKI].

## Specifications
| Item | Value | Src |
|---|---|---|
| Compute module | Raspberry Pi CM4 | [DS][UM] |
| CPU | Broadcom BCM2711 quad-core 64-bit Cortex-A72 (ARM v8) SoC @ 1.5GHz | [DS][UM] |
| RAM | 1GB/2GB/4GB/8GB LPDDR4-3200 | [DS][UM] |
| Storage | 8GB/16GB/32GB eMMC, expandable via M.2 NVMe SSD | [DS][UM] |
| Wireless (optional) | 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE | [DS][UM] |
| HDMI | 1x Full-size HDMI 2.0 (up to 4K@60Hz); Type-A connector | [DS][UM] |
| USB | 2x USB 2.0 host (480Mbps), max current for both ports together 1000mA; 1x USB-C (boot and debug) | [DS][UM] |
| Ethernet | 1x RJ45 Gigabit (10/100/1000M) = eth0; 1x RJ45 10/100M (via USB Ethernet controller) = eth1 | [DS][UM] |
| Digital inputs | 4x isolated (up to 50V), wet contact only, active high | [DS][UM] |
| Digital outputs | 4x isolated (up to 50V), solid-state-relay dry contact, AC or DC load, active high | [DS][UM] |
| Analog inputs | 4x isolated (0-5V / 0-10V / 0-20mA, Common GND), ADS1115 ADC at I2C 0x48 | [DS][UM] |
| Serial | 1x isolated RS232, 1x isolated RS485 | [DS][UM] |
| Expansion | 1x M.2 Key-M socket for NVMe SSD; 1x mini PCIe socket (only USB2.0 & SPI connected; no PCIe) | [DS][UM] |
| Mini PCIe intended use | "for 4G/LoRa modules (optional)" (DS Features table) / "for 4G or LoRa module (optional)" (DS internal layout) | [DS] |
| 4G hardware (optional) | 1x Micro SIM socket ("Insert SIM card for the 4G module (optional)"); 4G antenna mounting hole; 4G PWR LED (4G module power) and WWAN LED (4G WWAN activity) | [DS] — not in [UM]; see *Conflicts* |
| Power supply | DC 10-30V surge-protected (Terminal 1); or USB-C | [DS][UM] |
| Additional features | PCF85063A RTC; ATECC608B crypto authentication; SSD1306 0.96" OLED; 1x reset button & 1x programmable button; 1x active buzzer & 2x programmable LED | [DS][UM] |
| Enclosure | Metal enclosure, fanless design, DIN rail mountable | [DS][UM] |
| Dimension | 141.2mm x 83.5mm x 39.5mm (metal enclosure only, excl. antenna, DIN socket & connectors) | [DS][UM] |
| Power input voltage — Terminal 1 | 10 (min) – 30 (max) VDC; surge protected up to 60V 20ms | [DS][UM] |
| Power input voltage — USB-C (3 Amp) | 4.9 (min) – 5.2 (max) VDC | [DS][UM] |
| Power consumption | max 6.5 W (IRIV PiControl CM4, running `stress-ng --cpu 4 --cpu-method fft`; USB load not included) | [DS][UM] |
| Isolated DI — Low level (VIL) | -50 (min) – 0.8 (max) V | [DS][UM] |
| Isolated DI — High level (VIH) | 3 (min) – 50 (max) V | [DS][UM] |
| Isolated DI — turn-on minimum | DC 3.0V 0.2mA | [DS][UM] |
| Isolated DI — isolation voltage | 3750 Vrms | [DS][UM] |
| Isolated AI — voltage mode | 0 – 10 V | [DS][UM] |
| Isolated AI — current mode | 0 – 20 mA | [DS][UM] |
| Isolated AI — input impedance | 25 kΩ (voltage mode); 250 Ω (current mode) | [DS][UM] |
| Isolated AI — isolation voltage | 3000 Vrms | [DS][UM] |
| Isolated DO — voltage / current | max 50 V / max 500 mA | [DS][UM] |
| Isolated DO — isolation voltage | 1500 Vrms | [DS][UM] |
| Isolated RS485 | max baud rate 500 kbps; isolation 5000 Vrms; automatic direction control; /dev/ttyACM0 | [DS][UM] |
| Isolated RS232 | max baud rate 120 kbps; isolation 3000 Vrms; /dev/ttyACM1 | [DS][UM] |
| Operating temperature | -20 – 60 ℃ | [DS][UM] |
| Power-input fuse | 4 Amp replaceable fuse | [DS][UM] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **CM4 column (spec table):** Broadcom BCM2711 quad-core Cortex-A72 @ 1.5 GHz; GPU 700 MHz VideoCore VI, OpenGL ES 3.0; RAM 8/4/2/1 GB; eMMC 32/16/8 GB, expandable via M.2 NVMe SSD [PP].
- **Shared spec rows:** 2.4/5 GHz Wi-Fi 802.11 b/g/n/ac, Bluetooth 5.0, BLE; 1x HDMI 2.0; 2x USB 2.0; USB-C for boot and debug; RJ45 Gigabit + RJ45 10/100; 4 isolated DI (≤50 V); 4 isolated DO (≤50 V); 4 isolated AI (0–5 V / 0–10 V / 0–20 mA, common GND); isolated RS232 and RS485; M.2 Key-M NVMe (optional); mini PCIe (USB 2.0 and SPI only, no PCIe); DC 10–30 V surge-protected; PCF85063A RTC; ATECC608B; SSD1306 0.96" OLED; reset + programmable button; 2 programmable LEDs; active buzzer; metal fanless DIN-rail enclosure; 141.2 × 83.5 × 39.5 mm (enclosure only) [PP]. "Optional" items are add-ons by enquiry [PP].
- **Variants sold (CM4):** Wireless 8GB/32GB, 4GB/32GB, 2GB/16GB [PP]. No non-wireless or Lite variant is offered.
- **Packing (each CM4 variant):** 1x IRIV PiControl with the CM4 module (no NVMe SSD, no mini PCIe card), 1x dual-band antenna for CM4, 1x transparent flat-head screwdriver 85 × 3 mm, 1x transparent Phillips screwdriver 85 × 3 mm, 4x silicone bumpers 8 × 3 mm [PP].
- **Resources:** IRIV PiControl CM4 User Manual (public Google Doc), CM5 User Manual, 3D CAD, Node-RED hands-on tutorial, Quick Start Guide with built-in dashboard, Bookworm and Bullseye OS images, brochure [PP]. The page links the user manual, not a datasheet.
- The page lists no SIM socket, 4G antenna hole or 4G LEDs; the mini PCIe row says only USB 2.0 and SPI are connected [PP].

## Interfaces, terminals and pin mapping
**Terminal 1 (pluggable, 2 rows x 8)** — front-panel labels from UM Fig. 3.1 [UM] (the datasheet confirms "Pluggable terminal 1" [DS]; its figures are images and were not readable in the text export)
| Row | Positions (left → right) |
|---|---|
| Top | VIN (10-30V), A (RS485), B (RS485), 485G, DO0 (2 terminals), DO2 (2 terminals) |
| Bottom | GND, TX (RS232), RX (RS232), 232G, DO1 (2 terminals), DO3 (2 terminals) |

**Terminal 2 (pluggable, 2 rows x 8)** [UM]
| Row | Positions (left → right) |
|---|---|
| Top | DI0 (+, −), DI2 (+, −), AN0, AGND, AN2, AGND |
| Bottom | DI1 (+, −), DI3 (+, −), AN1, AGND, AN3, AGND |
The panel prints **AN0–AN3**; the manual text and block diagram call them **AI0–AI3** [UM]. The datasheet code comments call them "Analog Input Channel (0-3)" [DS].

**GPIO / device mapping** (DS §3, §5 tables and text; UM block diagram §4 and figures for the DI/DO GPIOs, GLOBAL_EN and the dual-UART chip — the DS block diagram is an image not readable in the text export)
| Function | CM4 resource | Notes | Src |
|---|---|---|---|
| DI0 / DI1 / DI2 / DI3 | GPIO13 / GPIO17 / GPIO22 / GPIO27 | Active high, through isolator ("accessible directly from the Raspberry Pi GPIOs" [DS]) | GPIO numbers [UM]; active high [DS][UM] |
| DO0 / DO1 / DO2 / DO3 | GPIO23 / GPIO24 / GPIO25 / GPIO26 | Active high, through isolator to SSR ("controlled directly from the Raspberry Pi GPIO" [DS]) | GPIO numbers [UM]; active high [DS][UM] |
| User button | GPIO4 | Can be programmed as safe-shutdown button | [DS][UM] |
| LED0 / LED1 | GPIO20 / GPIO21 | User-programmable | [DS][UM] |
| Active buzzer | GPIO19 | Beeps when output is high | [DS][UM] |
| Mini PCIe power on/off | GPIO6 | Via power switch; only USB 2.0 and SPI available at the socket | [DS][UM] |
| Reset button | GLOBAL_EN | Hard reset; also wakes CM4 after shutdown | Function [DS][UM]; GLOBAL_EN [UM] |
| RS485 | /dev/ttyACM0 | Via onboard USB-to-dual-UART chip on the USB hub, not CM4 GPIO UART | Device [DS][UM]; chip [UM] |
| RS232 | /dev/ttyACM1 | Same USB-to-dual-UART chip | Device [DS][UM]; chip [UM] |
| USB-C (Debug) | CM4 UART via USB-UART chip | Shows CM4 console | [DS][UM] |
| Gigabit Ethernet | CM4 native Ethernet → eth0 | | [DS][UM] |
| 10/100M Ethernet | USB Ethernet controller (behind the USB hub [UM]) → eth1 | | [DS][UM] |
| M.2 Key-M | CM4 PCIe, Gen 2 x1 | NVMe 2230 & 2242, bootable; M.2 SATA not supported | [DS][UM] |

**I2C devices** [DS][UM]
| Device | Address | Bus |
|---|---|---|
| PCF85063A RTC | 0x51 | I2C0 (`i2c_vc`, CSI/DSI) |
| ADS1115 ADC | 0x48 | I2C1 (isolator per UM block diagram [UM]); Python examples use `busnum = 1` |
| ATECC608B | 0x60 | I2C1 |
| SSD1306 OLED | 0x3C | I2C1 |

**Indicator LEDs** [DS]: PWR (CM4 power, same as red LED on Pi 4), ACT (CM4 activity, same as green LED on Pi 4), LED0, LED1, M.2 (NVMe activity) [DS][UM]; **4G PWR** (power indicator for the 4G module) and **WWAN** (4G WWAN activity) [DS]. The manual's layout table lists only the first five; its front-panel drawing and block diagram show **mPCIe PWR** and **mPCIe STAT/Status** LEDs instead [UM] — see *Conflicts*.

**Other front-panel items** [DS]: WiFi antenna (optional); 4G antenna mounting hole; extra antenna mounting hole; Micro SIM socket for the optional 4G module. The manual lists the WiFi antenna and extra antenna holes but not the 4G antenna hole or the SIM socket [UM].

**Internal switches and jumpers** [DS][UM]: RS485 120Ω termination enable switch; Analog Input Mode switch (DIP) — voltage (0-10V) or current (0-20mA); Boot/Debug mode switch for USB-C; Wireless Disable jumper (solder-short to disable WiFi or BT); CR2032 RTC battery holder; 4A fuse; M.2 module standoff (2230 or 2242); mini PCIe module standoff.

## Rules and gotchas (for code, wiring and tutorials)
- **Run the setup script first** on a fresh Raspberry Pi OS: `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash`, then reboot. Only a Raspberry Pi OS script exists. Units shipped with CM4 included should already be configured [DS][UM].
- **USB host is off by default on CM4.** The script sets `dtoverlay=dwc2,dr_mode=host` and comments out `otg_mode=1` [DS][UM]. Per the block diagram, the USB 2.0 ports, eth1, RS485/RS232 (dual-UART chip) and mini PCIe USB all sit behind the USB hub, so none of them work until USB host is on (derived from UM §4 block diagram + DS/UM §6).
- **I2C:** RTC needs `dtparam=i2c_vc=on` + `dtoverlay=i2c-rtc,pcf85063a,i2c_csi_dsi`; ADC/OLED/crypto need `dtparam=i2c_arm=on` [DS][UM]. Config file is `/boot/config.txt`, or `/boot/firmware/config.txt` on Bookworm [DS][UM].
- **External antenna:** `dtparam=ant2` switches WiFi/BT to the external antenna [DS][UM].
- **RS485/RS232 are `/dev/ttyACM0` / `/dev/ttyACM1`**, not `/dev/ttyAMA0`/`ttyS0`/`serial0` [DS][UM]. RS485 direction control is automatic (no DE/RE GPIO in code) [DS][UM].
- **RS485 wiring:** A-B alone works; also connect 485-GND for better noise immunity [DS][UM]. 120Ω termination is switched on the internal board [DS][UM]. Enable it only at the two ends of the bus [WIKI].
- **Digital inputs are wet-contact only** (need an external voltage, min DC 3.0V 0.2mA, max DC 50V). A plain dry switch with no source will not register [DS][UM]. Each DI is isolated from the system and from the other channels [DS][UM] and has its own + and − terminal [UM].
- **Digital outputs are SSR dry contacts.** They switch an external AC/DC source and load in series, max 50V 500mA. They do not supply voltage [DS][UM]. Isolated from system and from each other [DS][UM]. Two terminals per channel per the UM terminal drawing [UM].
- **Analog inputs:** AGND is isolated from system ground but **common to all four channels** [DS][UM]. 0-10V → gain=1, `val/3200` V; 0-5V → gain=2, `val/6400` V; 0-20mA → gain=2, `val/1600` = **mA**, shunt DIP must be ON [DS][UM]. Divider scale 2.5 and shunt 250Ω [DS][UM]; divider values 15kΩ/10kΩ from the UM simplified schematic [UM].
- **Code quirk (DS and UM):** in the 0-20mA example the result `val / 1600` is assigned to a variable named `voltage`, but the value is **current in mA**. Name it `current_mA` in tutorials [DS][UM].
- **Mixed AI modes:** the UM wiring figure shows AI0/AI1 on 0-10V and AI2/AI3 on 0-20mA at the same time, and the UM schematic shows a "Current Mode" switch per input [UM]. Do **not** write that all four channels must share one mode (see *Conflicts*). Neither DS nor UM text labels which DIP position maps to which channel.
- **Pins already used onboard:** GPIO4, 6, 19, 20, 21 [DS][UM]; GPIO13, 17, 22, 27 (DI) and 23, 24, 25, 26 (DO) [UM]. Do not reassign them in code that also uses the I/O.
- **USB-C mode is set by a physical internal switch** (Boot = flash eMMC; Debug = CM4 console). Flashing eMMC needs Boot position [DS][UM].
- **M.2:** NVMe only (2230/2242), Gen 2 x1; M.2 SATA SSDs are not supported [DS][UM]. **Mini PCIe:** USB 2.0 + SPI only, no PCIe — PCIe cards will not work [DS][UM]. The datasheet names 4G or LoRa modules as the intended (optional) use [DS].
- **No earth connection is required** for the power input [DS][UM].

## Power and electrical limits
- Terminal 1: 10–30 VDC, surge protected up to 60V for 20ms, 4A replaceable fuse. If the unit will not power up, check/replace the 4A fuse [DS][UM].
- USB-C can also power the unit: 4.9–5.2 VDC, rated "(3 Amp)" [DS][UM].
- Power consumption max 6.5 W under `stress-ng --cpu 4 --cpu-method fft`, USB load not included [DS][UM].
- USB 2.0 ports: 1000mA max for both ports combined [DS][UM].
- DO: max 50V, 500mA per channel, isolation 1500 Vrms. DI: VIH 3–50V, VIL -50–0.8V, 3750 Vrms. AI: 0–10V / 0–20mA, 3000 Vrms. RS485 5000 Vrms; RS232 3000 Vrms [DS][UM].
- Operating temperature -20 to 60 ℃ [DS][UM].

## Software support
- **OS:** Raspberry Pi OS (setup script supports Raspberry Pi OS only) [DS][UM]. Images: https://www.raspberrypi.com/software/operating-systems/ [WIKI][VEN].
- **Setup script:** `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash` — edits config.txt (USB host, I2C0+RTC, I2C1, ant2) and installs `/usr/local/bin/iriv_pi_control/background_script.py`, which runs after boot, shows IP address and system status (CPU load & temperature, RAM, storage) on the OLED, and monitors the button to shut down the Pi safely [DS][UM].
- **ADC library:** Adafruit `Adafruit_ADS1x15` (`pip install Adafruit_ADS1x15`), `ADS1115(address = 0x48, busnum = 1)` [DS][UM]. On Bookworm a system-wide `pip install` is blocked by the externally-managed-environment rule — use a virtual environment [VEN].
- **Serial:** standard serial libraries on `/dev/ttyACM0` (RS485) and `/dev/ttyACM1` (RS232); wiki examples use pySerial [WIKI].
- **GPIO:** standard Raspberry Pi GPIO libraries with the GPIO numbers above [WIKI].
- **Node-RED:** Cytron tutorial series "IRIV PiControl Hands-On Using Node-RED in Industry 4.0" (13 parts) — https://my.cytron.io/tutorial/iriv-picontrol-hands-on-using-nodered-in-industry-4 [WIKI]. Wiki says the dashboard is at `iriv.local:1880/ui` [WIKI].
- **eMMC flashing:** USB-C in Boot mode; host tool `rpiboot` from https://github.com/raspberrypi/usbboot [WIKI][VEN].
- Other Cytron tutorial: RS485 sensor via Modbus RTU — https://www.cytron.io/tutorial/p-rs485-sensor-with-iriv-power-meter (link from [3P] article; not opened).

## Compatibility and accessories
- **Compute module:** Raspberry Pi CM4 with 1/2/4/8GB RAM and 8/16/32GB eMMC; wireless optional [DS][UM]. Datasheet and manual say the configuration "should be pre-configured if your unit is shipped with CM4 included", implying units can ship with the CM4 fitted [DS][UM].
- **Storage:** M.2 Key-M NVMe SSD, 2230 or 2242, bootable; standoff provided for both lengths [DS][UM].
- **Mini PCIe:** USB 2.0 + SPI modules only; power switchable by GPIO6 [DS][UM]. Intended for 4G/LoRa modules (optional) [DS]; no module SKU confirmed.
- **4G (optional):** Micro SIM socket and 4G antenna mounting hole for the optional 4G module [DS]. Not in [UM]; see *Conflicts*.
- **DIN rail:** DIN bracket can be moved to the bottom of the unit; 4 mounting options in §7 (without DIN rail socket; positions 1 (default), 2, 3) [DS][UM]. Dimensions below are from the UM drawings [UM] (DS §7 drawings are images, not readable in the text export):
  - Without DIN rail socket: 141.2 x 83.5 x 39.5 mm enclosure (drawing also shows 98.9 mm on the side view).
  - Position 1 (default): drawing shows 107.9 mm depth, 39.5 mm width, 252.4 mm overall height incl. antenna (111.2 antenna, 55.6 / 50.6 clip offsets).
  - Position 2: 98.9 mm depth, 47.5 mm width, 252.4 mm overall height.
  - Position 3: 169.6 mm wide (antenna horizontal), 174.5 mm high, 47.5 mm deep (27.3 / 21.2 clip offsets).
- **RTC battery:** CR2032 coin cell (keeps RTC running when powered off) [DS][UM].
- **Antennas:** WiFi/BT antenna (optional) plus extra antenna mounting holes [DS][UM]; 4G antenna mounting hole [DS].
- **Sibling product:** IRIV PiControl CM5 (`IRIV-PICL5` , BCM2712, CM5) shares the I/O design; datasheet Rev 1.2 covers both [DS]. CM5 specs (e.g. 10.5 W max consumption, LPDDR4-4267, Gen 3 PCIe option) do not apply to this file.

## Common mistakes / troubleshooting
- **No power from Terminal 1:** check voltage (10–30 VDC), polarity, and the 4A fuse; replace if blown [DS][UM][WIKI].
- **eth1, USB ports, RS485 or RS232 missing:** setup script not run / USB host not enabled (`dtoverlay=dwc2,dr_mode=host`, `#otg_mode=1`); reboot [DS][UM][WIKI].
- **OLED blank / no IP shown:** run the setup script; check `dtparam=i2c_arm=on`; check the background script exists at `/usr/local/bin/iriv_pi_control/background_script.py`; `i2cdetect -y 1` should show 0x3C [DS][UM][WIKI].
- **RS485 no comms:** A/B swapped, wrong termination, baud mismatch, wrong device path (must be `/dev/ttyACM0`), missing GND [DS][UM][WIKI].
- **Can't flash eMMC / no console:** Boot/Debug switch in the wrong position (internal) [DS][UM][WIKI].
- **DI not responding:** dry contact used without a source, or voltage below 3V [DS][UM].
- **AI reads ~0 in current mode:** shunt DIP not ON, or wrong gain (use gain=2) [DS][UM].
- **Using the wrong serial port names** (`/dev/ttyAMA0`, `/dev/serial0`) for RS485/RS232 — they are USB ACM devices [DS][UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Analog input mode | [WIKI] terminal-2 / internal-layout / troubleshooting: all four channels share one mode; cannot mix voltage and current | [UM] §5.2.2 figure shows AI0/AI1 0-10V and AI2/AI3 0-20mA together; UM schematic shows a current-mode switch per input. [DS] text says only "Configure the analog inputs to measure voltage (0-10V) or current (0-20mA)" | [UM] outranks [WIKI]: do not state "cannot mix". Per-channel DIP mapping → *Needs verification* |
| USB-C power current | [DS][UM]: "USB-C (3 Amp)", 4.9–5.2 VDC | [WIKI] getting-started: 5V, min 1.5A, max 3A | [DS] wins: state 3 A rating; 1.5 A minimum is unverified |
| Safe-shutdown button behaviour | [DS][UM] §6: script "shuts down the Pi safely when the button is pressed" | [WIKI]: press cycles OLED pages; hold 5 s to shut down, buzzer sounds | [DS] wording kept; 5 s hold / page cycling → *Needs verification* |
| Front-panel LEDs | [DS] Datasheet Rev 1.2, Nov 2025 (Google Doc last modified 2025-11-12): layout table lists PWR, ACT, LED0, LED1, M.2, **4G PWR** (4G module power) and **WWAN** (4G WWAN activity) | [UM] User Manual Rev 1.3, Nov 2025: layout table lists PWR, ACT, LED0, LED1, M.2 only; front-panel drawing and block diagram show **mPCIe PWR** and **mPCIe STAT** instead | [DS] wins in main text. Both dated Nov 2025; the UM has the higher revision number (1.3 vs 1.2) but they are separate document series, so which is newer is unclear. The two extra LEDs may be the same pair under different names — engineering should confirm the CM4 panel labels |
| Micro SIM socket | [DS] Rev 1.2, Nov 2025: item 16 "Micro SIM Socket — Insert SIM card for the 4G module (optional)" | [UM] Rev 1.3, Nov 2025: no SIM socket in layout table or drawing | [DS] wins in main text (stated as optional 4G hardware). UM may be newer (higher rev, same month) — engineering should confirm whether current CM4 units have the SIM socket |
| 4G antenna mounting hole | [DS] Rev 1.2, Nov 2025: item 9 "4G Antenna Mounting Hole" | [UM] Rev 1.3, Nov 2025: WiFi antenna and extra antenna mounting holes only | [DS] wins in main text. Engineering should confirm (UM may be newer) |
| Mini PCIe purpose | [DS] Rev 1.2, Nov 2025: "mini PCIe socket for 4G/LoRa modules" / "for 4G or LoRa module (optional)"; only USB 2.0 & SPI connected. [3P] CNX agrees | [UM] Rev 1.3, Nov 2025: "Only USB 2.0 and SPI are available" — no use named | Not a contradiction: [DS] adds the intended use; stated in main text. No 4G/LoRa module SKU confirmed |
| AI input impedance column | [DS][UM]: "input impedance is 25kΩ for voltage mode and 250Ω for current mode" (single values) | [WIKI] terminal-2 puts them under "Maximum" | [DS]: single nominal values |

## Needs verification
- Per-variant SKUs. A reseller URL suggests `IRIV-PICL-W216` (wireless, 2GB, 16GB) [3P]. Which RAM/eMMC/wireless combinations are sold: [3P] lists wireless 2GB/16GB and 4GB/32GB. Whether a "no CM4" unit is sold.
- Optional MeanWell 24W DIN-rail PSU accessory — [3P] only.
- Which DIP position maps to which AI channel; whether modes can be set per channel (UM figure implies yes; DS text does not say).
- User button polarity (wiki: active LOW) and mini PCIe power polarity (wiki: HIGH = on) — [WIKI] only.
- USB-C debug console baud (wiki: 115200) — [WIKI] only.
- Whether the 4A fuse also protects USB-C input (wiki: USB-C bypasses fuse) — [WIKI] only.
- Node-RED pre-installed on shipped units, AP-mode default, `iriv.local` hostname — from the Node-RED tutorial via [WIKI]; not in DS or UM.
- Wireless Disable jumper: one jumper for both WiFi and BT, or separate — DS and UM wording ambiguous.
- Micro SIM socket, 4G antenna hole and 4G PWR / WWAN LEDs on current CM4 hardware ([DS] Rev 1.2 lists them; [UM] Rev 1.3 does not). Whether a 4G or LoRa module is sold or fitted, and which one.
- DI/DO GPIO numbers, GLOBAL_EN reset, dual-UART chip, terminal pinouts and §7 dimensions are from [UM] only — the DS figures/block diagram could not be read from the Google Doc text export; check them against the DS drawings.
- CM4 Lite (no eMMC) support — not stated.
- Whether Adafruit's legacy `Adafruit_ADS1x15` package is still the recommended library (DS and UM recommend it).
- Per-variant SKU codes — the page shows variant names only (Wireless 8GB/32GB, 4GB/32GB, 2GB/16GB).

## Sources
- [PP] not read — https://my.cytron.io/p-iriv-picontrol-cm4-industrial-controller
- [WIKI] Node-RED tutorial — https://my.cytron.io/tutorial/iriv-picontrol-hands-on-using-nodered-in-industry-4
- [VEN] https://github.com/raspberrypi/usbboot · https://www.raspberrypi.com/software/operating-systems/
- [3P] https://www.cnx-software.com/2023/12/21/cytron-iriv-picontrol-industry-4-0-controller-raspberry-pi-cm4/ · https://www.robotshop.com/products/iriv-picontrol-ir40-cm4-industrial-controller-wireless-2gb-ram-16gb-emmc · https://trace-tec.vn/IRIV-PICL-W216-pe56589.html
