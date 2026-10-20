# Product fact sheets

## Product name
CM4 Maker Board: Maker's Carrier Board for Raspberry Pi CM4/CM5

## Aliases
MAKER-CM4, V-MAKER-CM4, CM4 Maker Board, Cytron CM4 Maker Board

## What it is
A carrier board for the Raspberry Pi Compute Module 4 (CM4 Lite or eMMC) with Raspberry Pi 4-style ports, M.2 NVMe, camera and display connectors, an RTC and maker parts (Grove ports, buttons, buzzer, GPIO LEDs). The datasheet covers CM4; the product page title also names CM5.

## Specs and functions
- Power input: USB-C 5V or DC power jack 7V - 18V (only one is needed)
- HDMI: 1x full size, up to 4K resolution (HDMI 0 of CM4)
- USB: 4x USB 2.0 Host
- Ethernet: 1Gbps Gigabit Ethernet
- M.2 Key-M connector for PCIe modules: NVMe SSD 2230 & 2242 (bootable)
- microSD card slot for Raspberry Pi CM4 Lite
- CSI camera port: 15-pin 2-lane MIPI CSI, CAM 1 of CM4, compatible with Raspberry Pi Camera Module
- DSI display port: 15-pin 2-lane MIPI DSI, DSI 1 of CM4
- PCF85063A RTC with CR2032 coin cell holder
- 10 GPIO LEDs (GPIO 2, 3, 5, 6, 12, 13, 14, 15, 23, 24), turn on when the IO state is high
- Passive piezo buzzer on GPIO 19 with buzzer mute switch
- Analog audio out (line level): Left GPIO 19, Right GPIO 18
- User programmable buttons: GPIO 17, 22, 27
- 2 power buttons in series (GLOBAL_EN & GPIO 4), both pressed together to turn the CM4 ON/OFF; external power button header in parallel (not soldered by default)
- Boot switch: RUN or BOOT (BOOT loads the OS image to the CM4 eMMC via USB-C)
- Status LEDs: M.2, ACT, PWR, 5V
- Dimensions: 110 mm × 110 mm; 4 mounting holes Ø 3.2 mm at 104 mm × 104 mm
- Bundle "CM4NW216" = Raspberry Pi CM4 2GB RAM, 16GB eMMC, no wireless, plus USB-C power adapter, USB-C cable and HDMI cable (product page)
- DSI and CSI cannot be used while the RTC is in use (product page)

## Interfaces and compatibility
- Compute Module: Raspberry Pi CM4 (Lite or with eMMC) per datasheet Rev 1.2; product page title says "for Raspberry Pi CM4/CM5"
- 40-pin GPIO breakout, pinout exactly the same as Raspberry Pi 4
- Grove ports: 2x GPIO (GPIO 5, 6 and GPIO 23, 24), 1x PWM (GPIO 12, 13), 1x UART (GPIO 14, 15), 1x I2C (GPIO 2, 3); each GND, 3V3, pin, pin
- Maker Port: I2C on GPIO 2, 3 (shared with the Grove I2C port), compatible with QWIIC / Stemma QT / Grove (with conversion cable)
- Storage: microSD (CM4 Lite), CM4 eMMC, M.2 NVMe 2230 / 2242
- Official Raspberry Pi Camera Module and 7-Inch Display (need the matching dt-blob.bin)
- Setup script and pre-configured bootloader for Raspberry Pi OS (CytronTechnologies/MAKER-CM4_Script)

## Use cases
- Maker's carrier board for Raspberry Pi CM4
- Connecting Grove, QWIIC and Stemma QT modules to a Compute Module
- Booting a CM4 from NVMe SSD, eMMC or microSD
- Cytron tutorial: [Getting Started with CM4 Maker Board](https://my.cytron.io/tutorial/getting-started-with-cm4-maker-board)
- Cytron tutorial: [Node-RED on CM4 Maker Board: Displaying Thermocouple Sensor Data](https://my.cytron.io/tutorial/node-red-on-cm4-maker-board-displaying-thermocouple-sensor-data)
- Cytron tutorial: [Log Thermocouple Sensor Data to Google Sheets using CM4 Maker Board](https://my.cytron.io/tutorial/log-thermocouple-sensor-data-to-google-sheets-using-cm4-maker-board)

## Known limitations
- M.2 SATA SSD is not supported
- microSD slot is not accessible by Raspberry Pi CM4 with eMMC
- USB host on CM4 is disabled by default; the setup script (Raspberry Pi OS only) enables it
- Power buttons cannot wake the CM4 after shutdown unless Cytron's pre-configured bootloader is flashed
- Piezo buzzer shares GPIO 19 with the analog audio out; use the mute switch when using audio
- The audio remap line must be commented out to use hardware PWM for the buzzer
- Maker Port shares GPIO 2, 3 with the Grove I2C port
- dt-blob.bin method is only for the official Raspberry Pi Camera Module and 7-Inch Display
- Make sure the CM4 orientation is correct in the socket
- ESD may disturb normal function; power cycle to recover
- No fan header, USB 3.0 or PoE listed in the datasheet
- CM5 support: the product page states "The CM4 Maker Board is compatible with the newly launched Raspberry Pi CM5"; the datasheet (CM4 only) gives no CM5 setup steps
- Operating temperature and supply current rating: [NOT STATED]

## Positioning (kept apart from specs)
- Datasheet title: "CM4 Maker Board — Maker's Carrier Board for Raspberry Pi CM4"
- Product page title: "CM4 Maker Board: Maker's Carrier Board for Raspberry Pi CM4/CM5"
- Product page bundles: "CM4 Maker board ONLY" and "CM4 Maker Board + CM4NW216 + Accessories"
- Back in stock on my.cytron.io (availability 59, read 2026-10-19)

## Price band
RM224.00–RM651.60 across options (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-cm4-maker-board-and-kits

## Datasheet
https://docs.google.com/document/d/1XmZSR81IN70pndZ2odBmlZgAufiIBawVdKZ71C7101Y/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1XmZSR81IN70pndZ2odBmlZgAufiIBawVdKZ71C7101Y/edit
