# IRIV PiControl CM5 — Verified Reference

| | |
|---|---|
| Product code | `IRIV-PICL5` (document code in the CM5 user manual header) [UM]. The shared datasheet header code is `IRIV-PICONTROL`, which covers both CM4 and CM5 [DS], so do not use it for CM5 alone. Per-variant codes are not in DS/UM (a reseller lists `IRIV-PICL5-W832`; see *Needs verification*) |
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — CM5 User Manual (Google Doc "IRIV PiControl CM5 User Manual"; cover "IRIV PiControl CM5 — IR4.0 CM5 Industrial Controller — User Manual", Rev 1.5, Jan 2026; page header "User Manual - IRIV-PICL5"; 17 pages) read in full via Google Drive, with every page of its PDF export viewed as an image: front/side panel labels, internal board render, block diagram, terminal wiring diagrams, analog-input schematic and dimension drawings. This settles the CM5 DI0–DI3 = GPIO13/17/22/27 and DO0–DO3 = GPIO23/24/25/26 (same as CM4), the Terminal 1 / Terminal 2 position order, the USB topology behind `/dev/ttyACM0`/`ttyACM1`, eth1 and the mini PCIe, separate WLAN and BT disable jumpers, and a 4-way "ADC Current Mode" DIP switch. Raised Medium → Medium-high; still open: DS vs UM RAM/eMMC options and 4G/SIM hardware (UM figures show "mPCIe PWR / STAT" LEDs and no SIM socket), whether the dwc2 line is right on CM5, DIP-to-channel mapping, the undocumented internal SCL/SDA/3V3/GND header. Earlier: 2026-10-19 master-table review of the live product page (CM4/CM5 spec table, CM5 packing list, resources, FAQ, interface image) made GPU, Wi-Fi/BT, dimensions and sold variants Cytron-stated |
| Primary source | *IRIV PiControl — IR4.0 CM4 / CM5 Industrial Controller, Datasheet*, **Rev 1.2, Nov 2025** [DS] (Cytron Technologies Sdn Bhd; Google Doc last modified 2025-11-12). Covers CM4 and CM5 together; its layout pictures are of the CM4. Secondary: *IRIV PiControl CM5 — IR4.0 CM5 Industrial Controller, User Manual*, **Rev 1.5, Jan 2026** [UM] (newer than the DS; CM5-only; 17 pages, read in full including figures 2026-10-21) — the CM5 source for wiring, GPIO and terminal order |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
An industrial controller built around the Raspberry Pi Compute Module 5 (CM5), in a fanless, DIN-rail-mountable metal enclosure [DS]. It has the same isolated industrial I/O as the CM4 version: 4 DI, 4 DO, 4 AI, isolated RS485 and RS232. It also has two Ethernet ports, an M.2 NVMe socket, a mini PCIe socket (USB 2.0 + SPI only), an RTC, a crypto-authentication chip, an OLED status display, a buzzer, a user button and two user LEDs, and runs from 10–30 VDC [DS]. The UM subtitle is "IR4.0 CM5 Industrial Controller" [UM].
- **The DS does not separate CM4 and CM5 except** in the Features table (compute module, CPU, RAM, storage) and the power-consumption row. Its layout pictures are of the CM4 version ("IRIV PiControl CM5 comes with the CM5 marking"), and its layout text says "CM4" [DS]. Everything else in the DS is shared, and the UM repeats it for CM5 [UM].

## Specifications
| Item | Value | Src |
|---|---|---|
| Compute module | Raspberry Pi CM5 | [DS] |
| CPU | Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) SoC @ 2.4GHz | [DS] |
| RAM | 2GB/4GB/8GB/16GB LPDDR4-4267 (UM: 4GB/8GB/16GB, see *Conflicts*) | [DS] |
| Storage | 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD (UM: 32GB/64GB, see *Conflicts*) | [DS] |
| Variants (UM only) | IRIV PiControl CM5 Wireless 4GB/32GB; Wireless 8GB/32GB; Wireless 8GB/64GB; Wireless 16GB/64GB | [UM] |
| Wireless (optional) | 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE | [DS] |
| HDMI | 1x Full-size HDMI 2.0 (up to 4K@60Hz); Type-A connector | [DS] |
| USB | 2x USB 2.0 port (host, 480Mbps; max current for both ports 1000mA); 1x USB-C (for boot and debug) | [DS] |
| Ethernet | 1x RJ45 Gigabit Ethernet (10/100/1000M) = eth0; 1x RJ45 Ethernet (10/100M) via USB ethernet controller = eth1 | [DS] |
| Digital inputs | 4x Isolated digital input (up to 50V) | [DS] |
| Digital outputs | 4x Isolated digital output (up to 50V) | [DS] |
| Analog inputs | 4x Isolated analog input (0-5V / 0-10V / 0-20mA, Common GND) | [DS] |
| Serial | 1x Isolated RS232; 1x Isolated RS485 | [DS] |
| M.2 | 1x M.2 Key-M socket for NVMe SSD | [DS] |
| Mini PCIe | 1x mini PCIe socket for 4G/LoRa modules (Only USB2.0 & SPI signals are connected to this port. PCIe signal is not available.) | [DS] |
| Power supply | DC 10-30V surge-protected | [DS] |
| Additional features | PCF85063A Real Time Clock; ATECC608B Crypto Authentication; SSD1306 0.96" OLED Display; 1x Reset button & 1x Programmable button; 1x Active buzzer & 2x Programmable LED | [DS] |
| Enclosure | Metal enclosure, fanless design, DIN rail mountable | [DS] |
| Dimension | 141.2mm x 83.5mm x 39.5mm (metal enclosure only, excl. antenna, DIN socket & connectors) | [DS] |
| Power input voltage — Terminal 1 | 10 (min) – 30 (max) VDC; Surge Protected up to 60V 20ms | [DS] |
| Power input voltage — USB-C (3 Amp) | 4.9 (min) – 5.2 (max) VDC | [DS] |
| Power consumption — IRIV PiControl CM5 | max 10.5 W (running `stress-ng --cpu 4 --cpu-method fft`; USB load not included) | [DS] |
| Isolated DI — Low Level (VIL) | -50 (min) – 0.8 (max) V | [DS] |
| Isolated DI — High Level (VIH) | 3 (min) – 50 (max) V | [DS] |
| Isolated DI — turn-on minimum | DC 3.0V 0.2mA; max input DC 50V | [DS] |
| Isolated DI — Isolation Voltage | 3750 Vrms | [DS] |
| Isolated AI — Voltage Mode | 0 – 10 V | [DS] |
| Isolated AI — Current Mode | 0 – 20 mA | [DS] |
| Isolated AI — Input Impedance | 25 kΩ (voltage mode); 250 Ω (current mode) | [DS] |
| Isolated AI — Isolation Voltage | 3000 Vrms | [DS] |
| Isolated DO — Voltage / Current | max 50 V / max 500 mA | [DS] |
| Isolated DO — Isolation Voltage | 1500 Vrms | [DS] |
| Isolated RS485 | Maximum Baud Rate 500 kbps; Isolation Voltage 5000 Vrms | [DS] |
| Isolated RS232 | Maximum Baud Rate 120 kbps; Isolation Voltage 3000 Vrms | [DS] |
| Operating Temperature | -20 – 60 ℃ | [DS] |
| Power-input fuse | 4 Amp replaceable fuse | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Variants sold:** CM5 Wireless 16GB/64GB and CM5 Wireless 8GB/64GB (plus CM4 Wireless 8GB/32GB, 4GB/32GB, 2GB/16GB) [PP]. The spec table lists CM5 RAM 16/8/4/2 GB and eMMC 64/32/16/8 GB, but only the two Wireless 64GB variants are offered [PP].
- **CM5 column:** BCM2712 quad-core Cortex-A76 @ 2.4 GHz; GPU 800 MHz VideoCore VII, OpenGL ES 3.1 [PP].
- **Shared:** Wi-Fi 2.4/5 GHz 802.11 b/g/n/ac, Bluetooth 5.0, BLE; 1x HDMI 2.0 (4K60); 2x USB 2.0; 1x USB-C (boot and debug); RJ45 Gigabit + RJ45 10/100; 4 isolated DI (≤50 V); 4 isolated DO (≤50 V); 4 isolated AI (0–5 V / 0–10 V / 0–20 mA, common GND); isolated RS232 and RS485; M.2 Key-M NVMe socket (optional); mini PCIe socket (USB 2.0 and SPI only — no PCIe); DC 10–30 V surge-protected; PCF85063A RTC; ATECC608B; SSD1306 0.96" OLED; reset + programmable button; 2 programmable LEDs; active buzzer; metal fanless DIN-rail enclosure; **141.2 × 83.5 × 39.5 mm** (enclosure only) [PP].
- "Optional" features are add-ons by enquiry [PP].
- **Packing (CM5 variants):** 1x IRIV PiControl with the CM5 module (no NVMe SSD, no mini PCIe card), 1x dual-band antenna (for CM4 and CM5), 1x transparent flat-head screwdriver 85 × 3 mm, 1x transparent Phillips screwdriver 85 × 3 mm, 4x silicone bumpers 8 × 3 mm [PP].
- **Terminals (interface image):** Terminal 1 = Vin, isolated RS485, RS232, digital outputs; Terminal 2 = isolated digital inputs and analog inputs; analog input mode switch; boot/debug switch; M.2 SSD activity LED [PP: img]. Pin order is still per the UM figures.
- **Resources:** CM4 UM and CM5 UM (Google Docs), 3D CAD, Node-RED hands-on tutorial, Quick Start Guide with built-in dashboard (pre-loaded on stock shipped from 1 Jan 2024), Bookworm and Bullseye OS images, brochure [PP].
- **FAQ:** Cytron supplies hardware only; partner system integrators can help; ships overseas; CodeSys and Ignition (paid) also usable [PP].

## Interfaces, terminals and pin mapping
**Terminals (pluggable)** [DS]: **Terminal 1** = power supply input, isolated RS485, isolated RS232 and isolated digital outputs. **Terminal 2** = isolated digital inputs and isolated analog inputs. Signal names in the DS text: RS485 **A-B** + **GND**, analog **AGND**. Position order below is from the UM front-panel figure and the section 5 wiring diagrams, viewed from the front, positions 1–8 left to right; each terminal is a 2-row × 8 pluggable block [UM] (figure).

**Terminal 1** (silkscreen above / below the block):
| Row | 1 | 2 | 3 | 4 | 5–6 | 7–8 |
|---|---|---|---|---|---|---|
| Upper | VIN (10-30V) | RS485 A | RS485 B | 485G | DO0 (pair) | DO2 (pair) |
| Lower | GND | RS232 TX | RS232 RX | 232G | DO1 (pair) | DO3 (pair) |

**Terminal 2**:
| Row | 1–2 | 3–4 | 5 | 6 | 7 | 8 |
|---|---|---|---|---|---|---|
| Upper | DI0 (+, −) | DI2 (+, −) | AN0 | AGND | AN2 | AGND |
| Lower | DI1 (+, −) | DI3 (+, −) | AN1 | AGND | AN3 | AGND |

- Power: supply + to VIN, − to GND ("DC 10V-30V" diagram); no earth connection required [UM].
- RS485 uses its own ground "485-GND", RS232 its own "232-GND" (separate isolated grounds per the labels) [UM] (figure).
- Each DO is a two-terminal dry contact: the wiring diagram puts the load and an external AC/DC source in series across the pair; labels DO0 (GPIO23), DO1 (GPIO24), DO2 (GPIO25), DO3 (GPIO26) [UM] (figure).
- Each DI has its own + and − terminal: the diagram shows an external source and a switch in series (wet contact); labels DI0 (GPIO13), DI1 (GPIO17), DI2 (GPIO22), DI3 (GPIO27) [UM] (figure).
- Analog: the diagram shows AI0/AI1 wired as 0-10V sources and AI2/AI3 as 0-20mA sources at the same time, all returned to AGND [UM] (figure).

**GPIO / device mapping (DS/UM text and UM figures)**
| Function | Resource | Notes | Src |
|---|---|---|---|
| User button | GPIO4 | User programmable; can be programmed as a safe shutdown button | [DS] |
| LED0 / LED1 | GPIO20 / GPIO21 | User-programmable | [DS] |
| Active buzzer | GPIO19 | Active piezo; beeps when output is high | [DS] |
| Mini PCIe power on/off | GPIO6 | | [DS] |
| Reset button | CM5 GLOBAL_EN (block diagram) | Hard reset; also wakes the CM5 after shutting down | [UM] |
| RS485 | /dev/ttyACM0 | Automatic direction control | [DS] |
| RS232 | /dev/ttyACM1 | | [DS] |
| Digital inputs DI0–DI3 | **GPIO13, GPIO17, GPIO22, GPIO27** (UM block diagram and DI wiring figure) | Active high, "accessible directly from the Raspberry Pi GPIOs"; each through its own isolator | [UM] (figure), [DS] |
| Digital outputs DO0–DO3 | **GPIO23, GPIO24, GPIO25, GPIO26** (UM block diagram and DO wiring figure) | Active high, "controlled directly from the Raspberry Pi GPIO" | [UM] (figure), [DS] |
| Mini PCIe SPI | CM5 SPI (block diagram; bus/CS not named) | Mini PCIe gets USB from the onboard hub and SPI direct from the CM5 | [UM] (figure) |
| USB-C (Debug) | CM5 UART via USB-UART chip | Shows the CM5 console | [UM] |
| Gigabit Ethernet | CM5 native Ethernet → eth0 | | [UM] |
| 10/100M Ethernet | USB ethernet controller → eth1 | | [DS] |
| M.2 Key-M | PCIe Gen 2 x1 | NVMe 2230 & 2242, bootable; CM5 PCIe can be enabled as Gen 3 (not certified) | [DS] |

**DI and DO GPIO numbers** are not in the DS or UM text, but the CM5 UM block diagram and its DI/DO wiring figures give DI0–3 = GPIO13/17/22/27 and DO0–3 = GPIO23/24/25/26 [UM] (figure) — the same as the CM4 KB.

**USB topology (UM block diagram)** [UM] (figure):
- CM5 USB → a USB switch → **USB hub & Ethernet controller**, which feeds the 2x USB 2.0 ports, the 10/100M Ethernet (eth1), the mini PCIe socket (USB) and a **USB-to-dual-UART** chip: UART → isolated RS485 driver (`/dev/ttyACM0`) and UART → isolated RS232 driver (`/dev/ttyACM1`). So RS485/RS232 are USB serial devices, not CM5 UARTs.
- USB-C → a second USB switch → either a USB-to-UART chip on the CM5 UART (Debug) or the CM5 USB path (Boot). The Boot/Debug switch drives both USB switches. Inference, not stated: in Boot mode the hub and everything on it are probably cut off from the CM5.
- GPIO6 → power switch → mini PCIe; the mini PCIe has its own **mPCIe PWR** and **mPCIe Status** LEDs.

**I2C devices** [DS]
| Device | Address | Bus |
|---|---|---|
| PCF85063A RTC | 0x51 | I2C0 (`dtparam=i2c_vc=on`, `dtoverlay=i2c-rtc,pcf85063a,i2c_csi_dsi`) |
| ADS1115 ADC | 0x48 | I2C1 (example code `busnum = 1`) |
| ATECC608B | 0x60 | I2C1 ("other devices") |
| SSD1306 OLED | 0x3C | I2C1 ("other devices") |

**Indicator LEDs**: PWR (CM5 power), ACT (CM5 activity), LED0, LED1, M.2 (NVMe SSD activity) [UM]. The UM front-panel figure also shows two LEDs at the right end labelled **PWR / STAT — mPCIe**, which the UM table does not list [UM] (figure). The DS lists **4G PWR** and **WWAN** LEDs instead (see *Conflicts*) [DS].

**Internal switches and jumpers** [DS]: RS485 120 Ohm termination resistor enable switch; Analog Input Mode switch (voltage 0-10V or current 0-20mA; the code comment calls it a DIP switch); Boot/Debug mode switch for USB-C; Wireless Disable jumper (solder and short to disable WiFi or BT); CR2032 RTC battery; 4A fuse; M.2 standoff (2230 or 2242); mini PCIe standoff.
- From the UM internal-board render [UM] (figure): the analog mode switch is a **4-way DIP, silkscreen "ADC Current Mode", positions 1–4** ("Turn on to measure current"); the wireless disable is **two solder jumpers, "WLAN" and "BT", under "DISABLE"**; the termination switch is silkscreened "RS485 R-TERM" with an ON side; the Boot/Debug slide switch is silkscreened "BOOT" / ON; the board edge carries "RST" and "USER" buttons; a 4-pin connector silkscreened **SCL, SDA, 3V3, GND** sits near the left edge (not described in the text — see *Needs verification*). No SIM socket is visible on the CM5 board render.
- Analog input front end, per channel (UM "simplified schematic") [UM] (figure): input → R1 15 kΩ 0.1 % → ADC pin, R2 10 kΩ 0.1 % and C1 10 nF 50 V to AGND; the "Current Mode" switch SW1 adds R3 250 Ω 0.1 % from the input to AGND. 15 k + 10 k gives the 25 kΩ input impedance and the ÷2.5 divider used in the code.

## Rules and gotchas (for code, wiring and tutorials)
- **Run the setup script** on Raspberry Pi OS: `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash`, then reboot. Only a Raspberry Pi OS script exists. Units shipped with the CM5 included should already be configured [UM].
- **What the script sets** in `/boot/config.txt` (`/boot/firmware/config.txt` on Bookworm): comments out `otg_mode=1`; adds `dtoverlay=dwc2,dr_mode=host` (UM: "the USB host on CM5 is disabled to save power"); `dtparam=i2c_vc=on` + `dtoverlay=i2c-rtc,pcf85063a,i2c_csi_dsi` (RTC); `dtparam=i2c_arm=on` (I2C1); `dtparam=ant2` (external WiFi/BT antenna) [UM][DS]. The UM text is a copy of the CM4 text with "CM4" changed to "CM5"; see *Needs verification* about the dwc2 line on CM5.
- **RS485/RS232 are `/dev/ttyACM0` / `/dev/ttyACM1`**, not CM5 UART names: they are USB serial devices on a USB-to-dual-UART chip behind the onboard USB hub (UM block diagram). RS485 direction control is automatic [DS][UM].
- **"IRIV PiControl" on its own is ambiguous**: it can mean the CM4 version (`IRIV-PICL`) or the CM5 version (`IRIV-PICL5`). The CM5 UM itself says just "IRIV PiControl" in its body text. Always name CM4 or CM5 in content.
- **Terminal wiring:** use the Terminal 1 / Terminal 2 tables above (UM figures); RS485 and RS232 each have their own isolated ground pin (485G, 232G), and AGND is shared by all four analog channels.
- **RS485 wiring:** A-B alone works, but also connect GND for better noise immunity. The 120Ω termination is switched on/off internally [DS].
- **Digital inputs are wet-contact only:** they need an external source of at least DC 3.0V 0.2mA (max DC 50V). They are isolated from the system and from each other [DS].
- **Digital outputs are SSR dry contacts.** They switch an external DC or AC load at max 50V 500mA and are isolated from the system and from each other [DS]. They do not supply power. For pumps, chillers or contactors (as in the  video scripts), drive a relay or contactor coil within 50V 500mA, never the load directly.
- **Analog inputs:** AGND is isolated from system ground but **common to all four channels** [DS]. 0-10V → `gain=1`, `val / 3200` = V; 0-5V → `gain=2`, `val / 6400` = V; 0-20mA → `gain=2`, `val / 1600` = **mA**, and the shunt resistor must be enabled via the internal DIP switch [DS].
- **DS code quirk:** in the 0-20mA example, `val / 1600` is stored in a variable named `voltage`, but the value is current in mA. Name it `current_mA` in tutorials [DS].
- **USB-C function is set by an internal switch:** Boot = load OS image into eMMC; Debug = CM5 console. The port can also power the unit [UM].
- **M.2:** NVMe only (2230/2242, bootable), Gen 2 x1; M.2 SATA SSD is not supported. CM5 PCIe Gen 3 can be enabled but is **not certified** [DS]. Do not call Gen 3 a supported spec.
- **Mini PCIe:** USB 2.0 + SPI only, no PCIe. PCIe-only cards will not work [DS].
- **Pins used onboard (stated):** GPIO4, 6, 19, 20, 21, plus I2C0/I2C1 and the DI/DO GPIOs [DS].
- **No earth connection is required** for the power input [DS].
- **USB 2.0 ports share 1000mA total** [DS].

## Power and electrical limits
- Terminal 1: 10–30 VDC, surge protected up to 60V for 20ms, behind a 4 Amp replaceable fuse. The fuse may break on a surge or overcurrent [DS].
- USB-C: 4.9–5.2 VDC, rated "(3 Amp)"; it can power the unit [DS].
- Power consumption: max 10.5 W for IRIV PiControl CM5 under `stress-ng --cpu 4 --cpu-method fft`, USB load not included (CM4 version 6.5 W) [DS].
- DI: VIH 3–50 V, VIL -50–0.8 V, 3750 Vrms. DO: 50 V / 500 mA, 1500 Vrms. AI: 0–10 V / 0–20 mA, 25 kΩ / 250 Ω, 3000 Vrms. RS485: 5000 Vrms. RS232: 3000 Vrms [DS].
- Operating temperature -20 to 60 ℃ [DS].

## Software support
- **OS:** Raspberry Pi OS. The setup script exists only for Raspberry Pi OS [DS][UM].
- **Setup script:** `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash` (config.txt edits above). It also installs `/usr/local/bin/iriv_pi_control/background_script.py`, which runs after boot. The script shows the IP address and system status (CPU load & temperature, RAM and storage usage) on the OLED and shuts the Pi down safely when the button is pressed [DS].
- **ADC library:** Adafruit `Adafruit_ADS1x15` (`pip install Adafruit_ADS1x15`), `Adafruit_ADS1x15.ADS1115(address = 0x48, busnum = 1)`, channels 0-3 [DS].
- No CM5-specific driver, overlay or OS image download link is given in DS or UM.

## Compatibility and accessories
- **Compute module:** Raspberry Pi CM5 (DS: 2/4/8/16GB RAM, 16/32/64GB eMMC; UM: 4/8/16GB RAM, 32/64GB eMMC; all four UM variants are "Wireless") [DS][UM]. Wireless is listed as optional [DS].
- **Storage:** M.2 Key-M NVMe SSD 2230 or 2242, bootable; standoff provided [DS].
- **Mini PCIe:** DS: "for 4G/LoRa modules (optional)" with a Micro SIM socket and 4G antenna mounting hole [DS]. UM: mini PCIe with no named use, and no SIM socket or 4G antenna hole listed [UM]. See *Conflicts*. No 4G or LoRa module SKU is named.
- **DIN rail:** DIN bracket can be moved to the bottom. Four mounting options: without DIN rail socket, DIN position 1 (default), position 2, position 3 [DS]. Dimension drawings (mm) [UM] (figure):
  - Without DIN rail socket: 141.2 × 83.5, thickness 39.5; end view 98.9.
  - DIN position 1 (default): side view 107.9 wide, end view 39.5; overall height 252.4 incl. antenna (vertical segments 111.2 / 55.6 / 50.6).
  - DIN position 2: side view 98.9 wide, end view 47.5; overall height 252.4 incl. antenna (vertical segments 111.2 / 55.6 / 50.6).
  - DIN position 3: 169.6 wide incl. antenna, 174.5 high incl. antenna, end view 47.5 (horizontal offsets 27.3 and 21.2).
- **RTC battery:** CR2032 coin cell [DS]. **Antennas:** WiFi antenna (optional), extra antenna mounting holes [DS].

**Differences from IRIV PiControl CM4** (only those the sources state)
| Item | CM4 | CM5 | Src |
|---|---|---|---|
| Compute module / CPU | CM4, BCM2711 Cortex-A72 @ 1.5GHz | CM5, BCM2712 Cortex-A76 @ 2.4GHz | [DS] |
| RAM | 1/2/4/8GB LPDDR4-3200 | 2/4/8/16GB LPDDR4-4267 | [DS] |
| eMMC | 8/16/32GB | 16/32/64GB | [DS] |
| Power consumption (stress-ng) | max 6.5 W | max 10.5 W | [DS] |
| M.2 PCIe | Gen 2 x1 | Gen 2 x1; can be enabled as Gen 3 (not certified) | [DS] |
| Document code | IRIV-PICL | IRIV-PICL5 | [UM] |
| DI / DO GPIOs | DI GPIO13/17/22/27, DO GPIO23/24/25/26 | same (CM5 UM block diagram) | [UM] (figure) |
| I/O, serial, terminals, enclosure, dimensions, power input, temperature | same | same | [DS] |

## Common mistakes / troubleshooting
- **Unit will not power up:** check 10–30 VDC supply and the 4 Amp fuse; replace if needed [DS].
- **RTC, ADC, OLED or crypto not found:** I2C0/I2C1 not enabled; run the setup script and reboot [DS].
- **USB ports missing:** run the setup script (USB host settings) and reboot [UM]. eth1, RS485/RS232 (`/dev/ttyACM*`) and the mini PCIe USB all sit behind the same onboard USB hub (UM block diagram), so if the USB ports are missing these are probably missing too (inference).
- **No `/dev/ttyACM*`, no USB ports or no eth1 while the USB-C Boot/Debug switch is on Boot:** set it to Debug for normal running (inference from the block diagram, not stated).
- **RS485 no comms:** wrong device (must be `/dev/ttyACM0`), termination switch, missing GND [DS].
- **DI not responding:** dry contact with no source, below 3.0V 0.2mA, or + and − swapped on the DI pair [DS][UM].
- **AI reads wrong in current mode:** shunt DIP switch not ON, or wrong gain (use gain=2) [DS].
- **Can't flash eMMC / no console:** internal Boot/Debug switch in the wrong position [UM].
- **SATA M.2 SSD not detected:** not supported; use NVMe [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| CM5 RAM options | [DS] Rev 1.2, Nov 2025: 2GB/4GB/8GB/16GB | [UM] Rev 1.5, Jan 2026 (newer): 4GB/8GB/16GB | [DS] wins per rule; UM is newer and lists sale variants. Ask engineering whether a 2GB variant exists |
| CM5 eMMC options | [DS]: 16GB/32GB/64GB | [UM] (newer): 32GB/64GB | [DS] wins per rule; ask engineering whether 16GB is offered |
| 4G hardware | [DS]: 4G PWR + WWAN LEDs, 4G antenna mounting hole, Micro SIM socket, mini PCIe "for 4G/LoRa modules" (layout pictures are CM4) | [UM] (newer): none of these listed; mini PCIe described without a named use | [DS] wins per rule, but its layout is the CM4 version. CM5 UM figures (2026-10-21): front panel LEDs labelled "PWR / STAT — mPCIe", block diagram "mPCIe PWR" / "mPCIe Status", internal render shows no SIM socket. Treat 4G/SIM as unconfirmed on CM5; ask engineering |
| Wireless disable jumper | [UM] text: "Solder and short the jumper together to disable WiFi or Bluetooth (BT)" (one jumper) | [UM] internal-board figure: two solder jumpers, "WLAN" and "BT", under "DISABLE" | Same document; the figure is specific — two separate jumpers |
| Layout wording | [DS] layout text: "CM4 power", "default Gigabit Ethernet of CM4", "load OS image into the EMMC of CM4" | [UM]: same text with CM5 | Same function; DS text not CM5-specific |

## Needs verification
- Per-variant SKUs: [3P] RobotShop lists manufacturer # `IRIV-PICL5-W832` (Wireless 8GB/32GB), which suggests `IRIV-PICL5-W<RAM><eMMC>`; not confirmed by Cytron.
- Whether `dtoverlay=dwc2,dr_mode=host` / `#otg_mode=1` is needed or correct on CM5. The UM text is a CM4 copy, and on CM5 the USB is normally provided by the RP1 chip [VEN, not checked].
- RAM/eMMC option conflict and 4G/SIM hardware on CM5 (see *Conflicts*; CM5 UM figures show mPCIe PWR/STAT LEDs and no SIM socket).
- Which "ADC Current Mode" DIP position (1–4) maps to which analog channel (1 → AI0 is likely but not stated). Mixing modes per channel is shown in the UM figure and schematic.
- Purpose of the internal 4-pin SCL / SDA / 3V3 / GND connector on the CM5 board render (which I2C bus, whether it is for user use) — not described.
- What drives the "mPCIe STAT" LED (module signal not named), and the SPI bus / chip-select used for the mini PCIe.
- Whether the hub-attached devices (USB ports, eth1, RS485/RS232, mini PCIe USB) are disconnected while the Boot/Debug switch is on Boot (inferred from the block diagram).
- Whether the legacy `Adafruit_ADS1x15` library is still recommended. On Bookworm, a system-wide pip install is blocked [VEN].
- Official public download URL for the DS and UM (none given in either document).
- Per-variant SKUs for the two CM5 variants (page shows names, not codes); [3P] RobotShop uses `IRIV-PICL5-W832`.
- Whether the CM5 Lite / smaller RAM-eMMC options in the spec table can be ordered (only two CM5 variants are on the page).

## Sources
- [DS] IRIV PiControl Datasheet, "IR4.0 CM4 / CM5 Industrial Controller", Rev 1.2, Nov 2025 (Cytron-owned Google Doc; modified 2025-11-12) — (Cytron document — link not public)
- [UM] IRIV PiControl CM5 User Manual, "IR4.0 CM5 Industrial Controller", IRIV-PICL5, Rev 1.5, Jan 2026 (Cytron-owned Google Doc; modified 2026-09-30; 17 pages; read in full including all figures via a PDF export on 2026-10-21) — (Cytron document — link not public)
- [PP] not read (fetch error); URL not confirmed
- [3P] https://uk.robotshop.com/products/cytron-iriv-picontrol-cm5-wireless-8gb-ram-32gb-emmc · https://robotshop.com/products/cytron-iriv-picontrol-cm5-wireless-16gb-ram-64gb-emmc
- Setup script short link given in DS/UM: https://tinyurl.com/setup-iriv-picontrol
