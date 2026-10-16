# CM4 Maker Board — Verified Reference

| | |
|---|---|
| Product code | `MAKER-CM4` [DS Figure/Table captions]; product page variant path `V-MAKER-CM4` [PP] |
| Family | RP2040 / RP2350 boards and Raspberry Pi boards |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | "CM4 Maker Board — Maker's Carrier Board for Raspberry Pi CM4" Datasheet, Rev 1.2, October 2023 (public Google Doc linked from the product page; Drive last modified 2023-10-20) |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
- A carrier board for the **Raspberry Pi Compute Module 4 (CM4)** with Raspberry Pi 4-style ports plus maker parts [DS title, Table 1].
- Onboard [DS Table 1]: CM4 socket, 40-pin GPIO breakout ("pinout is exactly the same as Raspberry Pi 4"), GPIO LEDs, microSD slot (CM4 Lite only), M.2 Key-M (NVMe 2230/2242), full-size HDMI, 4x USB 2.0 host, Gigabit Ethernet, USB-C (5V in + eMMC programming), DC jack 7V–18V, CSI camera and DSI display ports, 5 Grove ports, 1 Maker Port, analog audio out, piezo buzzer with mute switch, PCF85063A RTC with CR2032 holder, 3 user buttons, power buttons + external power button header, boot switch, status LEDs.
- **CM5:** the datasheet covers CM4 only. The product page title now reads "CM4 Maker Board: Maker's Carrier Board for Raspberry Pi CM4/CM5" [PP] — no Cytron document read describes CM5 use (see *Conflicts* and *Needs verification*).
- Not listed in the datasheet: fan header, PoE, USB 3.0, M.2 SATA (explicitly not supported), second HDMI, antenna connector.

## Specifications
The datasheet has no ratings table; rows below are every numeric/functional spec stated in [DS].

| Item | Value | Src |
|---|---|---|
| Supported module | Raspberry Pi CM4 (Lite or with eMMC) | [DS] |
| Power input — USB-C | 5V | [DS] |
| Power input — DC power jack | 7V - 18V | [DS]; silkscreen "DC7V-18V" [DS Figure 1] |
| HDMI | 1x full size, up to 4K, HDMI 0 of CM4 | [DS] |
| USB | 4x USB 2.0 Host | [DS] |
| Ethernet | 1Gbps Gigabit Ethernet | [DS] |
| M.2 | Key-M, PCIe; NVMe SSD 2230 & 2242 (bootable); M.2 SATA not supported | [DS] |
| microSD | For CM4 Lite only; not accessible with eMMC CM4 | [DS] |
| Camera | 15-pin 2-lane MIPI CSI, CAM 1 of CM4, compatible with Raspberry Pi Camera Module | [DS] |
| Display | 15-pin 2-lane MIPI DSI, DSI 1 of CM4 | [DS] |
| RTC | PCF85063A, CR2032 coin cell holder | [DS] |
| Grove ports | 5 (2x GPIO, 1x PWM, 1x UART, 1x I2C) | [DS] |
| Maker Port | 1x I2C (Qwiic / STEMMA QT / Grove via conversion cable) | [DS] |
| GPIO LEDs | 10: GPIO 2, 3, 5, 6, 12, 13, 14, 15, 23, 24 | [DS Figure 1 silkscreen "GPIO STATUS"] |
| Board size | 110 mm × 110 mm | [DS Figure 2] |
| Mounting holes | 4, Ø 3.2 mm, 104 mm × 104 mm spacing | [DS Figure 2] |

Not stated: operating temperature, power-supply current rating, 5V/3V3 current available to GPIO/Grove, board height.

## Interfaces, terminals and pin mapping
| Function | Pins / connection | Notes | Src |
|---|---|---|---|
| Grove GPIO port 1 | GPIO 5, 6 | Grove order GND, 3V3, 5, 6 | [DS]; order [DS Figure 1] |
| Grove GPIO port 2 | GPIO 23, 24 | GND, 3V3, 23, 24 | [DS] |
| Grove PWM port | GPIO 12, 13 | GND, 3V3, 12, 13 | [DS] |
| Grove UART port | GPIO 14, 15 | GND, 3V3, 14, 15 | [DS] |
| Grove I2C port | GPIO 2, 3 | GND, 3V3, 2, 3 | [DS] |
| Maker Port (Qwiic / STEMMA QT compatible; connector part not stated) | GPIO 2, 3 | "The pins are shared with the Grove I2C port (GPIO 2, 3)." Silkscreen 3, 2, 3V3, GND | [DS] |
| Analog Audio Out | Left = GPIO 19, Right = GPIO 18 | "Analog line level output. Connect to external speaker or earphone." Silkscreen "AUDIO L#19 R#18" | [DS] |
| Piezo buzzer | GPIO 19 | Passive; "shared with Analog Audio Out"; silkscreen "BUZZER #19" | [DS] |
| Buzzer mute switch | — | "Turn off the piezo buzzer when not in use (or when using the analog audio out)." | [DS] |
| User buttons | GPIO 17, 22, 27 | "User Programmable Buttons" | [DS] |
| Power buttons (2) | GLOBAL_EN and GPIO 4 | Connected in series; both pressed together to turn the CM4 ON/OFF | [DS] |
| External power button header | Parallel to onboard power buttons | Pin header not soldered by default | [DS] |
| Boot switch | RUN / BOOT | BOOT loads the OS image to the CM4 eMMC via USB-C | [DS] |
| USB-C | 5V input | Also used to program the eMMC | [DS] |
| GPIO breakout | 40-pin | "exactly the same as Raspberry Pi 4" | [DS] |
| Status LEDs | M.2, ACT, PWR, 5V | M.2 = M.2 activity; ACT = CM4 activity (like Pi 4 ACT); PWR = on when CM4 is running; 5V = always on while supply connected | [DS] |
| GPIO LEDs | GPIO 2, 3, 5, 6, 12, 13, 14, 15, 23, 24 | "Turn on when the IO state is high." | [DS]; pins [DS Figure 1] |
| RTC | PCF85063A | Enabled by `dtoverlay=i2c-rtc,pcf85063a,i2c_csi_dsi` (on the CSI/DSI I2C bus) | [DS] |

## Rules and gotchas (for code, wiring and tutorials)
- **Run Cytron's setup script first** (Raspberry Pi OS only): `curl -L tinyurl.com/setup-maker-cm4 | sudo bash`, then reboot [DS]. It edits /boot/config.txt to [DS]:
  - comment out `otg_mode=1` (disable USB OTG);
  - `dtoverlay=dwc2,dr_mode=host` — "By default, USB host on CM4 is disabled to save power." **Without this the 4 USB ports do not work** (derived);
  - `dtparam=i2c_vc=on` and `dtoverlay=i2c-rtc,pcf85063a,i2c_csi_dsi` (I2C for RTC, CSI, DSI);
  - `dtoverlay=audremap,pins_18_19` (audio to GPIO 18/19);
  - `dtoverlay=gpio-shutdown,gpio_pin=4` (safe shutdown when the power buttons are pressed).
- **Flash Cytron's pre-configured CM4 bootloader** or the power buttons cannot wake the CM4 after shutdown [DS]. Changes: `WAKE_ON_GPIO=0`, `POWER_OFF_ON_HALT=1`; full config also sets `BOOT_UART=0`, `BOOT_ORDER=0xf25641`, `ENABLE_SELF_UPDATE=1` [DS]. Procedure (Windows): install rpiboot, extract the "recovery" folder, Boot Switch to BOOT, USB-C to PC, run `rpiboot.exe -d ./`, then Boot Switch to RUN and power cycle [DS].
- **Buzzer and left audio share GPIO 19** [DS]: slide the mute switch when using audio out (derived from [DS] description).
- **Buzzer with hardware PWM:** comment out `dtoverlay=audremap,pins_18_19` [DS: "this line needs to be commented out if you wish to use the hardware PWM function for piezo buzzer"].
- **Grove I2C and Maker Port are the same bus** (GPIO 2, 3) [DS]; modules on both need different I2C addresses (derived).
- **GPIO LEDs sit on the Grove-port pins** [DS Figure 1], so they flicker with I2C/UART/PWM traffic (expected, derived).
- **Official camera / 7-inch display need a dt-blob.bin** [DS]: camera only → `dt-blob-cam1.bin`; display only → `dt-blob-disp1-only.bin`; both → `dt-blob-disp1-cam1.bin`, each downloaded to /boot/dt-blob.bin, then reboot. "Only for the official Raspberry Pi Camera Module & 7-Inch Display." [DS]
- **CM4 orientation:** "Make sure the orientation is correct" when plugging into the CM4 socket [DS].
- **microSD does nothing on an eMMC CM4** [DS]: use CM4 Lite for SD boot, or flash the eMMC via USB-C in BOOT mode.
- **Power from one source only:** "The CM4 Maker Board only needs to be powered from either the USB-C port (5V) or DC Power Jack (7V - 18V)." [DS]
- Grove ports supply 3V3 [DS Figure 1 silkscreen]; Raspberry Pi GPIO are 3.3 V logic (derived).

## Power and electrical limits
- USB-C 5V or DC jack 7V - 18V; only one is needed [DS].
- 5V status LED should be on whenever a supply is connected; PWR LED shows the CM4 is running [DS].
- ESD: "The normal function of the product may be disturbed by electrostatic discharge (ESD). If so, simply reset the product to resume normal operation by power cycling the board." [DS]
- Not stated: supply current needed (with NVMe/USB loads), DC jack size/polarity, reverse-polarity protection, current limits on 5V/3V3 pins.

## Software support
- Setup script for Raspberry Pi OS only [DS; GH README]. Repo: CytronTechnologies/MAKER-CM4_Script with pre-configured bootloader images in `bootloader_config` [GH].
- Bootloader flashing from Windows with Raspberry Pi rpiboot [DS; GH].
- Boot order set by Cytron's bootloader: comment in [DS] reads "Try SD first (1), followed by, USB PCIe, NVMe PCIe, USB SoC XHCI then network" (`BOOT_ORDER=0xf25641`).
- Other OSes: no Cytron script ("Only script for Raspberry Pi OS is available") [DS].

## Compatibility and accessories
- **Compute Module:** Raspberry Pi CM4, Lite (microSD) or eMMC (USB-C flashing) [DS]. CM5: claimed by [PP] title only.
- **Storage:** microSD (CM4 Lite), CM4 eMMC, M.2 NVMe 2230/2242 bootable; M.2 SATA not supported [DS].
- **Camera / display:** Raspberry Pi Camera Module on CSI (CAM 1); DSI display on DSI 1; official 7-inch display named [DS].
- **Modules:** Grove modules (5 ports), Qwiic / STEMMA QT on the Maker Port, Grove via conversion cable [DS].
- **HATs / GPIO:** 40-pin header with Raspberry Pi 4 pinout [DS].
- **RTC battery:** CR2032 [DS].
- **Bundles on product page** [PP]: "CM4 Maker board ONLY" and "CM4 Maker Board + CM4NW216 + Accessories".

## Common mistakes / troubleshooting
- **USB ports dead:** USB host is disabled by default on CM4 — add `dtoverlay=dwc2,dr_mode=host` (setup script) [DS].
- **Power buttons can't restart the CM4 after shutdown:** flash Cytron's bootloader config [DS].
- **Power button does nothing:** both buttons must be pressed together (series) [DS]; check `gpio-shutdown` on GPIO 4 [DS].
- **Buzzer buzzes with audio:** GPIO 19 shared; use the mute switch [DS].
- **Buzzer PWM not working:** comment out the audremap line [DS].
- **Camera/display not detected:** install the matching dt-blob.bin and reboot [DS].
- **SD card ignored:** an eMMC CM4 cannot access the microSD slot [DS].
- **NVMe not detected:** only NVMe (PCIe) 2230/2242 is supported, not M.2 SATA [DS].
- **Board misbehaves after a static zap:** power cycle [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Supported Compute Module | [DS] Rev 1.2 (Oct 2023): "Maker's Carrier Board for Raspberry Pi CM4"; all setup steps are CM4-specific | [PP] title (read 2026-10-16): "for Raspberry Pi CM4/CM5" | [DS] wins in text: CM4. CM5 support unconfirmed — needs [DT] and an updated datasheet |
| Audio channel order | [DS] text and silkscreen: Left = GPIO 19, Right = GPIO 18 | [3P] Tom's Hardware: "GPIO 18 and 19" (no order) | Not contradictory; use [DS] |

## Needs verification
- **CM5 support** — what works on CM5 (USB host overlay, bootloader procedure, audio remap, dt-blob method, RTC overlay, PCIe/NVMe, HDMI) — needs [DT]; no Cytron document read covers CM5.
- Whether the setup script paths (/boot/config.txt, /boot/dt-blob.bin) still apply on current Raspberry Pi OS releases — the datasheet (Oct 2023) does not say.
- Whether CM4 wireless variants need an external antenna (none listed on the carrier).
- Active level of user buttons (GPIO 17, 22, 27) and whether they have hardware pull-ups — schematic not available.
- DC jack barrel size/polarity, supply current rating, operating temperature.
- What "CM4NW216" in the bundle name denotes (not defined in any source read).
- [3P] Tom's Hardware: board height 17.3 mm; HDMI "4K60"; the CM4 "can be inserted upside down"; price $56 — not used as specs.

## Sources
- [DS] CM4 Maker Board Datasheet, Rev 1.2, October 2023 (public Google Doc; read as text and exported to PDF for Figures 1 and 2): https://docs.google.com/document/d/1XmZSR81IN70pndZ2odBmlZgAufiIBawVdKZ71C7101Y/edit
- [PP] https://my.cytron.io/p-cm4-maker-board-and-kits (read by coordinator 2026-10-16)
- [PP] Pinout image (not reachable from this session): https://static.cytron.io/image/catalog/products/V-MAKER-CM4/CM4%20Maker%20Board%20Pinout.png
- [GH] https://raw.githubusercontent.com/CytronTechnologies/MAKER-CM4_Script/main/README.md
- CAD (not read): https://drive.google.com/drive/folders/1cI4fqBKrXHo-Z5plleaJ9RTZGAdneMa0
- [3P, cross-check only] https://www.tomshardware.com/reviews/cytron-cm4-maker-board
