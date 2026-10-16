# IRIV SmartHub CM5 — Verified Reference

| | |
|---|---|
| Product code | `IRIV-SH5` [DS]. Per-variant SKU codes not stated in the [DS] — see *Needs verification* |
| Family | IRIV industrial series |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |

**Authority rule:** Datasheet/manual [DS] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub & staff wiki [GH]/[WIKI] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
An industrial controller in a fanless metal enclosure, built around the Raspberry Pi Compute Module 5 (Broadcom BCM2712, quad-core Cortex-A76 64-bit @ 2.4GHz) [DS]. The [DS] subtitle is "IR4.0 CM5 Industrial Controller". It takes DC 10–30V surge-protected power and adds 2× HDMI, 2× USB 3.0, 2× USB 2.0, Gigabit Ethernet, an M.2 Key-M NVMe socket, a USB-2.0-only mini PCIe socket, an RTC battery holder, a user button, 2 user LEDs and an active buzzer [DS]. It has no field I/O terminals (no RS485, CAN, digital or analog I/O) in the [DS]; it is a compute/gateway box, not an I/O controller.


Positioning (product page via , not specs): "compact, high-performance computing hub for Industrial Revolution 4.0"; a centralized point for data processing, device connectivity and intelligent control at the edge; an alternative to traditional PCs for edge computing (compact, fanless metal enclosure with no moving parts, lower maintenance, lower power, simpler infrastructure); Raspberry Pi CM5 compute with industrial power handling, cooling and a finished enclosure. [DS] page-header tagline: "Simplifying Smart Technology".

## Specifications
From the [DS] *Features* table (p.3) and *Specifications* table (p.4).

| Item | Value | Src |
|---|---|---|
| CPU | Broadcom BCM2712, Quad-Core Cortex-A76 64-bit SoC @ 2.4GHz | [DS] |
| Compute module | Raspberry Pi Compute Module 5 (CM5) | [DS] |
| RAM | 2GB/4GB/8GB/16GB | [DS] |
| Storage | 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD | [DS] |
| Wireless | 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE | [DS] |
| HDMI | 2x full size HDMI 2.0 (up to 4K@60Hz); full-size Type-A, labelled HDMI0 and HDMI1 | [DS], labels [DS-fig] |
| USB 3.0 | 2x USB 3.0 host, 5 Gbps | [DS] |
| USB 2.0 | 2x USB 2.0 host, 480Mbps | [DS] |
| USB-C | 1x USB-C (for boot and power) | [DS] |
| Ethernet | 1x RJ45 Gigabit Ethernet (10/100/1000M) | [DS] |
| M.2 | 1x M.2 Key-M socket for NVMe SSD (Gen 2 1-lane PCIe; 2230 & 2242; bootable) | [DS] |
| Mini PCIe | 1x mini PCIe socket (Only USB2.0 is connected to this port. PCIe signal is not available) | [DS] |
| Power supply | DC 10-30V surge protected | [DS] |
| Power input voltage, DC barrel jack | Min 10, Max 30 VDC (Surge Protected up to 60V 20ms) | [DS] |
| Power input voltage, USB-C | Min 4.9, Max 5.2 VDC | [DS] |
| Power consumption | Max 6 W, when running stress test command "stress-ng --cpu 4 --cpu-method fft". *USB load not included* | [DS] |
| Power consumption (product page) | "< 12W" ("operates on low power") — a separate statement, not the same test as the 6 W figure |  (quoting [PP]) |
| USB 3.0 port total output current | Max 2 A (2000mA for both ports) | [DS] |
| USB 2.0 port total output current | Max 1 A (1000mA for both ports) | [DS] |
| Operating temperature | -20 to 60 ℃ | [DS] |
| RTC | Coin Cell Battery Holder CR2032 for RTC (RTC is built into the CM5) | [DS] |
| User controls | 1x programmable button, 1x power button | [DS] |
| User LEDs | 2x programmable LED | [DS] |
| Buzzer | 1x active buzzer | [DS] |
| Fuse | 4A replaceable fuse on the power input | [DS] |
| Enclosure | Metal enclosure, fanless design | [DS] |
| Dimension (Features table) | 147mm x 94mm x 35.7mm (metal enclosure only, excluding antenna) | [DS] |
| Dimension (drawing, p.10) | 147.00 x 98.00 x 35.00 (mm) — disagrees with the Features table, see *Conflicts* | [DS-fig] |
| Mounting (drawing, p.10) | 4xM4 VESA Mount 75x75mm on the base; mounting flanges with slots dimensioned 66.00 / 30.00 (labelled M4) and 48.00 (labelled M8) | [DS-fig] |
| Variants (product page, 2026-09-08) | Wireless 2GB RAM 16GB eMMC, Wireless 4GB RAM 32GB eMMC, Wireless 16GB RAM 64GB eMMC |  (quoting [PP]) |

## Interfaces, terminals and pin mapping
The [DS] gives no 40-pin header and no field terminals. Its only GPIO mapping is the onboard functions below.

**Onboard GPIO mapping (CM5 GPIO numbers)**

| Function | GPIO | Behaviour as stated | Src |
|---|---|---|---|
| User button (USER) | GPIO4 | User programmable; can be programmed to be a safe shutdown button | [DS] |
| Mini PCIe reset | GPIO5 | "The Mini PCIe module can be reset by pulling GPIO5 low" | [DS] |
| Mini PCIe power | GPIO6 | "Power to the Mini PCIe socket can be turned on/off via GPIO6" (polarity not stated) | [DS] |
| Active buzzer | GPIO19 | Beeps when output is high | [DS] |
| LED0 | GPIO20 | User programmable LED 0 | [DS] |
| LED1 | GPIO21 | User programmable LED 1 | [DS] |

**External ports** (p.5 drawing: LEFT and RIGHT panels)

| No. | Port | Panel | Notes | Src |
|---|---|---|---|---|
| 1 | Gigabit Ethernet (GIGABIT) | Left | Default CM5 Ethernet; `eth0` in Raspberry Pi OS | [DS] |
| 2 | 2x USB 2.0 | Left | 480Mbps; max 1000mA for both ports; via onboard USB hub | [DS], hub [DS-fig] |
| 3 | 2x HDMI (HDMI0, HDMI1) | Left | Full-size Type-A, up to 4K | [DS] |
| 4 | DC barrel jack (POWER IN DC10-30V) | Left | DC10-30V, recommended current rating more than 2A | [DS] |
| 5 | USB-C (POWER/BOOT) | Left | Boot: load OS image into CM5 eMMC. Power: recommended USB-C adapter 5V 5A | [DS] |
| 6 | 2x USB 3.0 | Right | 5 Gbps; max 2000mA for both ports; direct from CM5 | [DS], direct [DS-fig] |
| 7 | User button (USER) | Right | GPIO4 | [DS] |
| 8 | Power button (PWR) | Right | Single press to turn on; double-press or long-press to turn off | [DS] |
| 9 | LEDs | Right | LED0, LED1, PWR, ACT, M.2 (table); panel also shows mPCIe PWR and mPCIe STAT | [DS], [DS-fig] |
| 10 | WiFi antenna (ANT) | Right | Antenna for CM5 WiFi and Bluetooth | [DS] |
| 11 | Extra antenna mounting hole | Right | Extra mounting holes for the antennas | [DS] |

**Status LEDs**

| LED | Meaning | Src |
|---|---|---|
| LED0 / LED1 | User LEDs, GPIO20 / GPIO21 | [DS] |
| PWR | Power; "Same as the red LED on Pi 5" ([DS] text says "CM4 power", an evident typo) | [DS] |
| ACT | Activity; "Same as the green LED on Pi 5" ([DS] text says "CM4 activity") | [DS] |
| M.2 | NVMe SSD activity | [DS] |
| mPCIe PWR, mPCIe STAT | Mini PCIe power and status; shown on panel, PCB and block diagram, not described in text | [DS-fig] |

**Internal board** (p.7–8; open the enclosure)

| No. | Item | Notes | Src |
|---|---|---|---|
| 1 | M.2 Key-M socket | Gen 2 1-lane PCIe; NVMe 2230 & 2242, bootable; M.2 SATA SSD not supported | [DS] |
| 2 | M.2 module standoff | Positions for 2230 or 2242 | [DS] |
| 3 | Mini PCIe socket | USB 2.0 only, no PCIe; power via GPIO6; reset via GPIO5 low | [DS] |
| 4 | Mini PCIe module standoff | | [DS] |
| 5 | Active buzzer | GPIO19 (silkscreen "BUZZER (GP19)") | [DS] |
| 6 | 4A fuse | Replaceable, power input | [DS] |
| 7 | Boot/Run mode switch | Selects USB-C for boot (OS install on CM5) or run. Silkscreen BOOT / RUN; drawing callout and block diagram say "Boot/Debug" | [DS], [DS-fig] |
| 8 | RTC battery | CR2032 keeps the CM5 RTC running when powered off | [DS] |
| 9 | Wireless disable jumper (back side) | Solder-short to disable WiFi or BT. Silkscreen "DISABLE": BT, WLAN | [DS], labels [DS-fig] |
| 10 | CM5 socket (back side) | Mount CM5 following the silkscreen orientation | [DS] |

**Block diagram signal paths** (p.9) [DS-fig]: 2x USB 3.0 direct to CM5. CM5 USB 2.0 → USB switch (set by the Boot/Debug switch, other side to USB-C) → USB hub → 2x USB 2.0 ports and the mini PCIe USB. DC jack and USB-C both feed one power block. Two HDMI from CM5. CM5 PCIe → M.2. CM5 GPIO5 → mini PCIe reset; GPIO6 → mini PCIe power switch. Gigabit Ethernet = eth0.

## Rules and gotchas (for code, wiring and tutorials)
- The mini PCIe socket carries **USB 2.0 only — no PCIe**. PCIe-only mini PCIe cards will not work there [DS].
- The M.2 socket is **NVMe (PCIe Gen 2 x1) only**, sizes **2230 and 2242**. M.2 SATA SSDs are not supported; do not write "2280" [DS].
- GPIO4, 5, 6, 19, 20, 21 are used onboard (button, mini PCIe reset/power, buzzer, LED0, LED1). Code must use these numbers; don't reuse them for other functions [DS].
- Buzzer is **active**: drive GPIO19 high to beep. No PWM tone needed or stated [DS].
- Reset the mini PCIe module by pulling GPIO5 **low** [DS]. GPIO6 on/off polarity is not stated in the [DS]; the [WIKI] claims HIGH = on (unverified).
- USB-C has two roles chosen by the internal Boot/Run switch. Boot = OS flashing into eMMC; Run = normal use. The switch is inside the enclosure [DS].
- USB-C input range is narrow: **4.9–5.2 VDC**; recommended adapter **5V 5A** [DS]. DC jack: **10–30 VDC**, adapter rating **more than 2A** recommended [DS].
- USB current budgets are **shared**: 2 A total across both USB 3.0 ports, 1 A total across both USB 2.0 ports [DS].
- The 6 W power figure **excludes USB load** and is for one specific CPU stress test. Do not quote it as total system draw [DS].
- Operating temperature is **-20 to 60 ℃** [DS]. Do not write -40 to 85 ℃ (that range is not stated for this product).
- WiFi/BT are disabled by **soldering** a jumper on the back of the board, not by a switch or DIP [DS].
- Wireless is from the CM5 module; the one external antenna serves both WiFi and Bluetooth [DS].
- There is no 40-pin GPIO header, RS485, CAN, digital I/O or analog I/O listed in the [DS]. Do not describe the SmartHub with field I/O; that belongs to other IRIV products.
- Supported CM5: the [DS] RAM/eMMC options all include eMMC; CM5 Lite (no eMMC) support is not stated.

## Power and electrical limits
| Parameter | Min | Max | Unit | Src |
|---|---|---|---|---|
| DC barrel jack input | 10 | 30 | VDC | [DS] |
| DC surge protection | — | 60V for 20ms | — | [DS] |
| USB-C input | 4.9 | 5.2 | VDC | [DS] |
| Power consumption (stress-ng --cpu 4 --cpu-method fft, USB load excluded) | — | 6 | W | [DS] |
| USB 3.0 total output current (both ports) | — | 2 | A | [DS] |
| USB 2.0 total output current (both ports) | — | 1 | A | [DS] |
| Operating temperature | -20 | 60 | ℃ | [DS] |

- Power input fuse: 4A, replaceable [DS].
- Recommended adapters: DC jack rated more than 2A; USB-C 5V 5A [DS]. Getting-started tutorial examples: 12V 2A or 24V 1.5A DC-jack adapters, 45W or 27W USB-C PD supplies .
- Using DC jack and USB-C at the same time is not addressed in the [DS] — see *Needs verification*.

## Software support
- OS: Raspberry Pi OS (the [DS] names `eth0` "in Raspberry Pi OS"). The [DS] gives no image, driver, overlay or example-code download.
- OS flashing: set the internal switch to Boot, connect USB-C to a PC, load the OS image into the CM5 eMMC [DS]. Cytron's tutorial uses `rpiboot` (if required) plus Raspberry Pi Imager, and lists Raspberry Pi OS or Ubuntu as choices .
- Pre-installed OS: the tutorial series says units used for the initial setup "can have" Raspberry Pi OS pre-installed ; the [WIKI] says it ships pre-installed. Not in the [DS].
- GPIO control examples on the [WIKI] use `pinctrl set <gpio> op dh|dl` (Raspberry Pi OS). Pin numbers match the [DS]; command syntax is [VEN]-level, not from the [DS].
- Node-RED, libraries, overlays and Cytron example code: not stated in any source read.

## Compatibility and accessories
- Compute module: Raspberry Pi CM5; RAM 2/4/8/16GB, eMMC 16/32/64GB [DS]. Sold as "Wireless" variants .
- Storage expansion: M.2 NVMe 2230/2242, bootable [DS].
- Mini PCIe: USB-2.0 modules. Cytron's tutorial names an optional 4G/LTE module (not included; regional compatibility varies; the module in that guide suits Malaysia; SIM card needed only with LTE) . LoRa modules are mentioned only by the [WIKI].
- Mounting: 4x M4 VESA 75x75mm and flange slots [DS-fig]. DIN-rail mounting is **not** stated in any source.
- Enclosure: the product ships in its own metal fanless enclosure [DS]; no separate enclosure or kit is stated.

## Common mistakes / troubleshooting
- Using an M.2 SATA SSD or a 2280 NVMe — not supported; use NVMe 2230/2242 [DS].
- Expecting a PCIe card to work in the mini PCIe slot — USB 2.0 only [DS].
- Mini PCIe module not detected: power-cycle it with GPIO6 and reset it with GPIO5 low; reseat the module [DS] (procedure from [WIKI]).
- Cannot flash the OS: the Boot/Run switch must be on Boot, and the USB-C cable must carry data; set it back to Run after flashing [DS] / [WIKI].
- No power: check the supply is within 10–30V (DC) or 4.9–5.2V (USB-C) and check the 4A fuse [DS].
- WiFi/BT not working: check the wireless-disable jumper has not been shorted, and that the antenna is fitted [DS] / [WIKI].
- RTC loses time after power-off: fit a CR2032 [DS].
- Overloading USB: 2 A total for USB 3.0 pair, 1 A total for USB 2.0 pair [DS].
- Older content may call the PWR/ACT LEDs "CM4" LEDs (copied from the [DS] typo); the module is CM5.

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Enclosure dimensions | [DS] Features table: 147mm x 94mm x 35.7mm | [DS-fig] drawing p.10: 147.00 x 98.00 x 35.00; [WIKI] copies the drawing (147 x 98 x 35mm) | Internal [DS] inconsistency. Quote the Features table (147 x 94 x 35.7 mm, excl. antenna) and flag; 98 vs 94 may be including the mounting flanges (unconfirmed). Ask design team |
| Mounting holes | [DS-fig]: 4xM4 VESA Mount 75x75mm; flange slots 66.00/30.00 (M4), 48.00 (M8) | [WIKI]: "VESA mount: 66mm x 30mm pattern with M4 holes" and "M4 (30mm spacing)" | [DS-fig] wins: VESA is 75x75mm; 66/30/48 are flange slot dimensions |
| PWR / ACT LED name | [DS] text: "CM4 power", "CM4 activity" | [WIKI]: "CM5 power", "CM5 activity" | Product uses CM5 ([DS] everywhere else); [DS] wording is a typo. Use "power / activity LED (same as Pi 5 red/green LED)" |
| Wireless disable labels | [DS-fig] silkscreen: BT, WLAN | [WIKI]: "labeled WL for WiFi, BT" | [DS-fig] wins: WLAN |
| Boot switch name | [DS] tables: "Boot/Run Mode Switch"; silkscreen BOOT/RUN | [DS-fig] callout and block diagram: "Boot/Debug" | Same switch. Use "Boot/Run switch" |
| Manual revision | [DS] file here: Rev 1.3, Dec 2025 | : built from Rev 1.4, Feb 2026 (adds variant list) | Rev 1.4 is newer but not available here; Rev 1.3 facts used. Re-verify against Rev 1.4 |
| Power consumption | [DS]: max 6 W under stress-ng CPU test, USB load excluded |  quoting [PP]: "< 12W" | Different statements; record both with source. Don't merge |
| WiFi standards | [DS]: 802.11 b/g/n/ac, 2.4/5.0GHz | : 802.11b/g/n on 2.4GHz, 802.11a/n/ac on 5.0GHz | Compatible detail; [DS] wording is the spec |
| M.2 use | [DS]: "for PCIe module", NVMe SSD |  quoting [PP]: "NVMe SSD or other compatible M.2 module" | [DS] wins; only NVMe is stated as supported |
| Pre-installed OS | [DS]: not stated | [WIKI]: "ships with Raspberry Pi OS pre-installed";  tutorial: units "can have" it | Not a spec; *Needs verification* |
| Power-on behaviour | [DS]: single press of power button turns on | [WIKI]: DC power auto-starts; USB-C needs a button press | [DS] wins; [WIKI] claim unverified |
| USB-C PD | [DS]: USB-C 4.9–5.2V, 5V 5A adapter recommended | [WIKI]: "5V 5A (PD capable)" | PD requirement not in [DS]; tutorial examples are PD supplies  |

## Needs verification
- Per-variant product codes / SKUs (only `IRIV-SH5` is stated) — Cytron product team.
- Manual Rev 1.4 (Feb 2026) contents vs Rev 1.3 — get the file and re-check this page.
- Enclosure width/height: 94 vs 98 mm, 35.7 vs 35 mm — design team.
- Whether the 8GB/32GB variant is sold; current price per variant (only [3P] price seen: RobotShop USD 207.25 for 4GB/32GB) — product page.
- GPIO6 polarity for mini PCIe power (wiki: HIGH = on); user button active level (wiki: LOW when pressed).
- Whether DC power auto-starts the unit; soft vs forced shutdown on double vs long press.
- Whether DC jack and USB-C may be connected at the same time.
- Whether units ship with an OS pre-installed and which version; whether the antenna and RTC battery are in the box.
- Back of PCB drawing shows an unlabelled card holder near the wireless jumper (appears to be a SIM holder) — not described in the [DS].
- CM5 Lite (no eMMC) and non-wireless CM5 support.
- Whether the Boot switch position disconnects the USB 2.0 ports / mini PCIe from the CM5 (block diagram routes them through the same USB switch).
- Node-RED, Cytron libraries or example code for this product — none found.

## Sources
- [PP] Product page (not read this pass): https://my.cytron.io/p-iriv-smarthub-cm5 (also linked as https://my.cytron.io/c-industrial-with-raspberry-pi/p-iriv-smarthub-cm5)
- [VEN] Raspberry Pi Compute Module documentation: https://www.raspberrypi.com/documentation/computers/compute-module.html ; usbboot / rpiboot: https://github.com/raspberrypi/usbboot
- [3P] RobotShop listing (price cross-check only): https://robotshop.com/products/cytron-iriv-smarthub-cm5-wireless-4gb-ram-32gb-emmc
