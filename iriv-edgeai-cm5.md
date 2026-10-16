# IRIV EdgeAI CM5 — Verified Reference

| | |
|---|---|
| Product code | `IRIV-EDGEAI-CM5` (datasheet page header). Per-variant SKUs: not stated in any source read |
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | *IRIV EdgeAI CM5 — IR4.0 CM5 Edge AI Controller, Datasheet* **Rev 1.0, July 2025**, Cytron Technologies Sdn Bhd (15 pages) |

**Authority rule:** Datasheet/manual [DS] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is



## Specifications
| Item | Value | Src |
|---|---|---|
| Compute module | Raspberry Pi CM5 | [DS] |
| CPU | Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) SoC @ 2.4GHz | [DS] |
| RAM | 2GB / 4GB / 8GB / 16GB LPDDR4-4267 | [DS] |
| Storage | 16GB / 32GB / 64GB eMMC, expandable via M.2 NVMe SSD | [DS] |
| AI accelerator | PCIe port + header for Raspberry Pi AI HAT+ ("The AI Accelerator from Raspberry Pi"). DS board photo shows an AI HAT+ marked "26 TOPS" / "HAILO" | [DS] |
| Wireless | 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE | [DS] |
| HDMI | 1x full-size HDMI 2.0 (Type-A), up to 4K@60Hz | [DS] |
| USB | 2x USB 3.0 host (both share one USB 3.0 hub); 1x USB-C (boot and debug) | [DS] |
| Camera | 2x 22-way MIPI ports for CSI camera (MIPI0, MIPI1) | [DS] |
| Ethernet | 2x RJ45 Gigabit (10/100/1000M): eth0 = CM5 native; eth1 = USB 3.0-to-Gigabit Ethernet controller | [DS] |
| Digital input | 2x isolated bidirectional (PNP or NPN), up to 50V | [DS] |
| Digital output | 2x isolated bidirectional, dry contact (solid state relay), up to 50V | [DS] |
| LED lighting driver | 2x, output voltage follows Vin, PWM capable | [DS] |
| RS485 | 1x isolated | [DS] |
| M.2 | 1x Key-M, PCIe Gen 2* 1-lane, NVMe 2230 & 2242, bootable. M.2 SATA not supported (the "*" is not explained in the DS) | [DS] |
| AI HAT+ port | 1x PCIe port, "similar to the PCIe port on Raspberry Pi 5" | [DS] |
| mPCIe | 1x mini PCIe socket for 4G/LoRa modules. Only USB 2.0 connected; no PCIe signal | [DS] |
| SIM | Micro SIM socket (for the 4G module) | [DS] |
| Power supply | DC 10–30V, surge-protected | [DS] |
| Security | ATECC608B secure authentication, I2C 0x60 | [DS] |
| Display | SSD1315 0.96" OLED, I2C 0x3C | [DS] |
| Buttons | 1x power button, 1x programmable button (GPIO4) | [DS] |
| Buzzer / LEDs | 1x active buzzer (GPIO19), 2x programmable LED (GPIO20, GPIO21) | [DS] |
| RTC | CM5 RTC; CR2032 coin-cell holder keeps it running when powered off | [DS] |
| Enclosure | Metal, fanless, DIN rail mountable | [DS] |
| Dimension | 139mm x 88mm x 38mm (metal enclosure only, excl. antenna, DIN socket & connectors) | [DS] |
| Drawing extras | 250.70 overall height with antenna; 111.46 width with DIN bracket; DIN bracket 8.00 (drawing gives no unit; mm assumed from DS text) | [DS] |
| Power input voltage (Vin), terminal | Min 10, max 30 VDC (surge protected up to 60V 20ms) | [DS] |
| Power input voltage, USB-C | Min 4.9, max 5.2 VDC | [DS] |
| Power consumption | Max 11 W (running `stress-ng --cpu 4 --cpu-method fft`; USB load not included) | [DS] |
| Isolated DI low level (VIL) | 0 – 0.8 V | [DS] |
| Isolated DI high level (VIH) | 3 – 50 V | [DS] |
| Isolated DI isolation voltage | 3750 Vrms | [DS] |
| Isolated DO (dry contact) voltage | Max 50 V (DC or AC load) | [DS] |
| Isolated DO current | Max 500 mA | [DS] |
| Isolated DO isolation voltage | 1500 Vrms | [DS] |
| LED driver (wet contact) output voltage | Vin | [DS] |
| LED driver current | Max 2 A (per channel) | [DS] |
| LED driver PWM | Yes | [DS] |
| RS485 max baud rate | 500 kbps | [DS] |
| RS485 isolation voltage | 5000 Vrms | [DS] |
| RS485 onboard termination | 120 Ω | [DS] |
| Operating temperature | -20 to 60 ℃ | [DS] |
| Storage temp, humidity, IP rating, weight, certifications | Not stated | — |

## Interfaces, terminals and pin mapping
**DS 5.1 Pin & Interface Mapping** [DS]
| Function | Channel | Raspberry Pi CM5 |
|---|---|---|
| RS485 | — | `/dev/ttyACM0` |
| Digital Input | DI0 | GPIO22 |
| Digital Input | DI1 | GPIO27 |
| Digital Output | DO0 | GPIO23 |
| Digital Output | DO1 | GPIO24 |
| LED Lighting Driver | L0 | GPIO12 |
| LED Lighting Driver | L1 | GPIO13 |
| User Button | — | GPIO4 |
| User LED | LED0 | GPIO20 |
| User LED | LED1 | GPIO21 |
| Active Buzzer | — | GPIO19 (active high) |
| mPCIe | Reset (Active Low) | GPIO5 |
| mPCIe | Power | GPIO6 |
| USB-C Debug | — | UART0 |
| SSD1315 0.96" OLED | — | I2C1 (Add: 0x3C) |
| ATECC608 Secure Authentication | — | I2C1 (Add: 0x60) |

**Pluggable terminal** (16 positions, two rows of 8, as printed on the front panel) [DS]
| Row | Positions, left to right |
|---|---|
| Top | VIN · RS485 A · RS485 B · RS485 G · DO0 (2 contacts) · L0 + / − |
| Bottom | GND · S/S · DI0 · DI1 (S/S + DI0 + DI1 = "DIN" group) · DO1 (2 contacts) · L1 + / − |

**Front-panel status LEDs** [DS]: PWR (CM5 power, = red LED on Pi 5), ACT (CM5 activity, = green LED on Pi 5), M.2 (NVMe activity), 4G PWR (4G module power), WWAN (4G WWAN activity), LED0 (GPIO20), LED1 (GPIO21).

**Internal bus routing (DS block diagram)** [DS]
- RS485: isolated RS485 driver → UART → USB-to-UART → USB 3.0 hub → CM5. That is why it is `/dev/ttyACM0`, not a CM5 GPIO UART.
- USB 3.0 hub (on CM5 USB3-1) feeds the 2 USB-A ports, the RS485 USB-UART and the mPCIe socket (USB).
- eth1: Gigabit Ethernet controller on CM5 USB3-0. eth0: CM5 native.
- M.2 and AI HAT+ share the CM5 PCIe lane through a PCIe switch.
- USB-C: USB mux set by the Boot/Debug switch → either CM5 USB (Boot) or a USB-to-UART on CM5 UART0 (Run).
- AI HAT+ header: only 5V, 3V3, GND, ID_SC, ID_SD are connected (HAT+ EEPROM auto-identification).
- MIPI0 uses I2C0; MIPI1 uses the ID_SD/ID_SC lines (as drawn).
- LED drivers: VIN switched by a MOSFET per channel (GPIO12/13). DI/DO pass through isolators.

## Rules and gotchas (for code, wiring and tutorials)
- **RS485 is `/dev/ttyACM0`** (USB CDC through the hub), automatic direction control — no DE/RE GPIO to toggle, no `raspi-config` serial setting needed for it [DS]. Max 500 kbps [DS].
- RS485 works with only A-B connected; Cytron recommends also wiring G (GND) for noise immunity [DS]. A 120 Ω terminator is onboard — do not tell readers to add one externally [DS]. The DS does not say whether it can be switched off.
- **Isolation:** RS485 is isolated from the system and other interfaces (5000 Vrms) [DS]. DO0/DO1 are isolated from the system and from each other (1500 Vrms) [DS]. DI0/DI1 are isolated from the system (3750 Vrms) but **share one S/S common** [DS]. The LED driver outputs are not described as isolated: they output Vin (wet contact) [DS].
- **DI wiring:** PNP sensors — S/S to supply −, sensor outputs to DI0/DI1. NPN sensors — S/S to supply +, sensor outputs to DI0/DI1 [DS diagrams]. Low ≤ 0.8 V, high 3–50 V [DS].
- **DO = dry contact (SSR)**, DC or AC load up to 50 V 500 mA; the load needs its own supply [DS]. For inductive loads (relays) Cytron recommends a flyback diode across the load to cut EMI; outputs have built-in surge protection [DS]. Do not describe DO as a voltage output.
- **LED drivers = wet contact**: output voltage equals Vin, up to 2 A per channel, PWM capable (GPIO12/GPIO13) [DS]. A 24 V supply puts 24 V on L0/L1 — the LED load must be rated for Vin.
- **LED drivers are not powered when the unit runs from USB-C** — use the VIN terminal [WIKI]; consistent with the DS block diagram (VIN → MOSFET).
- **mPCIe carries USB 2.0 only** — PCIe-only mini-PCIe cards will not work [DS]. Module power is switched by GPIO6; reset is GPIO5, active low [DS].
- **M.2 is NVMe only** (2230/2242, PCIe Gen 2 x1); M.2 SATA SSDs are not supported [DS].
- **Boot/Run switch is internal** (enclosure must be opened): Boot = flash eMMC over USB-C; Run = USB-C is the UART0 console [DS].
- **Wireless disable** = solder jumpers WL (WiFi) / BT (Bluetooth) on the board; there is no switch [DS].
- I2C1 holds the OLED (0x3C) and ATECC608B (0x60) [DS].
- Reserved GPIOs — don't reuse in example code: 4, 5, 6, 12, 13, 19, 20, 21, 22, 23, 24, 27 [DS]. There is no user 40-pin GPIO header on the enclosure; the internal header is only for the AI HAT+ [DS].
- USB-C is not a host port and there is no microSD slot in the DS layout [DS].
- Power button: single press = on, double-press = soft shutdown, long-press = force shutdown [DS].
- No earth connection is required [DS].

## Power and electrical limits
- Terminal Vin: 10–30 VDC, surge protected up to 60 V for 20 ms [DS].
- USB-C: 4.9–5.2 VDC [DS]; "can be used to power up … with a PD capable power supply, which can support up to 5V 5A" [DS]. The getting-started tutorial specifies a 5V 5A supply for USB-C .
- Max 11 W under `stress-ng --cpu 4 --cpu-method fft`, USB load excluded [DS]. Whether AI HAT+, NVMe or mPCIe load is included is not stated.
- System fuse: 4 A, replaceable; does not cover the LED drivers [DS]. If the unit does not power up, check/replace the 4 A fuse [DS].
- LED drivers: each channel has an independent 2 A fuse [DS].
- DO: 50 V / 500 mA per channel. DI: up to 50 V [DS].
- Operating temperature -20 to 60 ℃ [DS].

## Software support
- The DS names no OS image, driver or library. It is a CM5 device: OS is flashed to eMMC over USB-C in Boot mode [DS].
- Raspberry Pi OS is listed as supported; flashing with `rpiboot` / Raspberry Pi Imager [WIKI][VEN].
- Getting-started tutorial: https://my.cytron.io/tutorial/getting-started-with-iriv-edgeai-cm5 [WIKI] (covers power-up; the wiki says it also references AI processor and AI computer-vision topics).
- Wiki GPIO examples use `pinctrl` (e.g. `pinctrl set 20 op dh`), `i2cdetect -y 1`, pyserial on `/dev/ttyACM0` [WIKI].
- AI HAT+ software: not documented by Cytron in any source read; the wiki defers to Raspberry Pi AI HAT+ docs [WIKI].
- Cytron download pages, Node-RED flows, OLED/ATECC libraries, 3D model: not published (wiki lists them as placeholders) [WIKI].

## Compatibility and accessories
- Compute module: Raspberry Pi CM5 with eMMC (DS options 16/32/64 GB eMMC, 2–16 GB RAM) [DS]. CM5 Lite (no eMMC) is not mentioned [DS]; boot from NVMe is supported [DS].
- NVMe M.2 2230/2242 SSD; 4G or LoRa mini-PCIe module (USB type) with Micro SIM; 4G antenna position is reserved (hole only) [DS].
- CSI cameras on 22-way MIPI ports [DS].
- DIN rail bracket, repositionable to the bottom of the unit [DS].
- CR2032 coin cell for the RTC (not stated as included) [DS].

## Common mistakes / troubleshooting
- Won't power on → check supply (10–30 V terminal / 5 V USB-C) and the 4 A system fuse [DS].
- L0/L1 dead → running from USB-C (no Vin) [WIKI], or blown 2 A LED fuse [DS].
- Writing RS485 code for `/dev/serial0`, `/dev/ttyAMA*` or a DE/RE pin → wrong; use `/dev/ttyACM0` [DS].
- Adding an external 120 Ω terminator → already onboard [DS].
- Expecting a PCIe card (e.g. Wi-Fi/NVMe adapter) to work in mPCIe → USB 2.0 only [DS].
- M.2 SATA SSD not detected → not supported; use NVMe 2230/2242 [DS].
- Cannot flash → Boot/Run switch must be on Boot; set back to Run after flashing [DS]. Wiki adds: use a data-capable USB-C cable [WIKI].
- No WiFi/BT → check the WL/BT solder jumpers have not been bridged [DS].
- Time lost after power-off → CR2032 missing/flat [DS].
- Camera check: the wiki uses `libcamera-hello --list-cameras`; current Raspberry Pi OS names it `rpicam-hello` [WIKI][VEN].
- Digital output treated as a voltage source → it is a dry contact; supply the load separately [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| OLED controller | DS features, layout, mapping: SSD1315 | DS block diagram label: SSD1306 | SSD1315 (stated three times in text) |
| Secure chip | DS features/layout: ATECC608B | DS mapping table & block diagram: ATECC608 | ATECC608B |
| USB-C power | DS spec table: 4.9–5.2 VDC; DS layout: PD supply "up to 5V 5A" | WIKI/tutorial: "5V 5A" as the requirement | Not contradictory; quote DS range + "5V 5A PD" |
| Power-off | DS: double-press = soft shutdown, long-press = force | Tutorial (INT) / WIKI: hold power button 5 s; also hold User Button 5 s to power off | DS wins for the button; the 5 s and User Button behaviour are unverified |
| Power-on from VIN | DS: single press turns on | WIKI: VIN "auto-starts / boots automatically" | DS wins; auto-boot unverified |
| LED/mPCIe polarity | DS: buzzer active high, mPCIe reset active low; LED0/1 and mPCIe power polarity not stated | WIKI: LED HIGH = on; GPIO6 HIGH = power on | Unverified — not stated as fact |
| LED driver fuse | DS: independent 2 A fuse; only the 4 A system fuse is called "replaceable" | WIKI: 2 A fuse "replaceable" | DS wording; replaceability unverified |
| Third-party listing | DS: BCM2712 Cortex-A76 2.4GHz, 10–30 V, 139×88×38 mm | [3P] Cirkit Designer: Cortex-A53 1.5GHz, 2.5 TOPS, 4GB, 5V 2A, 55×40×10 mm | DS wins; the Cirkit page is wrong — never cite it |
| "IRIV EdgeAI v2" | Drive `product-facts.md`: "IRIV EdgeAI v2 (PPE + zone detection appliance)"; PPE funnel sheet: appliance for 4–6 IP-camera streams | No source says EdgeAI v2 = EdgeAI CM5 | Treat EdgeAI v2 as the PPE/zone appliance (matches the Safety Box Kit), **not** an alias of this controller |
| Product page URL | INT: my.cytron.io/p-iriv-edge-ai-cm5 | WIKI: my.cytron.io/c-industrial-with-raspberry-pi/p-iriv-edge-ai-cm5 | Same slug; give the short form |

## Needs verification
- Product page not read (my.cytron.io fetch failed 2026-10-16). Price, live variant list, per-variant SKUs and in-box contents (antenna, CR2032, terminal plug) unconfirmed.
- Which AI HAT+ accelerator chip each configuration uses (13 vs 26 TOPS). Hailo-8 for 26 TOPS is stated only for the Safety Box Kit ; Hailo-8L for 13 TOPS is [VEN] only.
- Logic sense of DI (does an active input read 1 or 0?), DO (does GPIO high close the contact?), LED0/LED1 and mPCIe power (GPIO6) polarity.
- Power-off by holding the User Button 5 s, and auto-boot on VIN — likely depends on Cytron's preinstalled image; not in DS.
- Whether the 11 W figure includes AI HAT+ / NVMe load; total Vin current budget with LED drivers.
- PCIe "Gen 2*" footnote meaning (can Gen 3 be enabled?).
- Whether the onboard 120 Ω RS485 terminator can be disabled.
- A newer datasheet revision than Rev 1.0 (July 2025).
- Preinstalled OS image and any Cytron software (OLED status app, Node-RED, AI demos).

## Sources
- [PP] https://my.cytron.io/p-iriv-edge-ai-cm5 (also https://my.cytron.io/c-industrial-with-raspberry-pi/p-iriv-edge-ai-cm5) — not read; facts via 
- [VEN] https://www.raspberrypi.com/documentation/computers/compute-module.html · https://github.com/raspberrypi/usbboot
- [3P, rejected] https://docs.cirkitdesigner.com/component/ab31ab26-a746-4ba8-85ce-e0a748435f64/iriv-edgeai-cm5
