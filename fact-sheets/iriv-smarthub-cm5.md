# Product fact sheets

## Product name
IRIV SmartHub CM5

## Aliases
IRIV-SH5, IRIV SmartHub CM5, SmartHub CM5

## What it is
An industrial controller in a fanless metal enclosure, built around the Raspberry Pi Compute Module 5. It adds HDMI, USB, Gigabit Ethernet, an M.2 NVMe socket and a USB-2.0-only mini PCIe socket, and runs from DC 10-30V.

## Specs and functions
- Product code: IRIV-SH5
- Datasheet subtitle: IR4.0 CM5 Industrial Controller
- CPU: Broadcom BCM2712, Quad-Core Cortex-A76 64-bit SoC @ 2.4GHz (Raspberry Pi Compute Module 5)
- RAM: 2GB/4GB/8GB/16GB
- Storage: 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD
- Wireless: 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE; one external antenna for WiFi and Bluetooth
- Power input: DC barrel jack 10-30 VDC (surge protected up to 60V 20ms), adapter rated more than 2A recommended; USB-C 4.9-5.2 VDC, 5V 5A adapter recommended
- Power input fuse: 4A, replaceable
- USB 3.0 total output current: max 2 A for both ports
- USB 2.0 total output current: max 1 A for both ports
- Operating temperature: -20 to 60 ℃
- RTC: CR2032 coin cell holder keeps the CM5 built-in RTC running when powered off
- User button: GPIO4, can be programmed as a safe shutdown button
- Power button: single press to turn on; double-press or long-press to turn off
- User LEDs: LED0 = GPIO20, LED1 = GPIO21
- Status LEDs: PWR (same as red LED on Pi 5), ACT (same as green LED on Pi 5), M.2 (NVMe SSD activity); panel also shows mPCIe PWR and mPCIe STAT
- Active piezo buzzer: GPIO19, beeps when output is high
- Mini PCIe power on/off: GPIO6; mini PCIe reset: pull GPIO5 low
- Boot/Run switch (inside enclosure): selects USB-C for OS flashing into eMMC (Boot) or normal use (Run)
- Wireless disable jumper (back of board, labels BT and WLAN): solder-short to disable WiFi or Bluetooth
- Enclosure: metal, fanless design
- Dimensions: 147mm x 94mm x 35.7mm (metal enclosure only, excluding antenna) per datasheet Features table; the datasheet dimension drawing shows 147.00 x 98.00 x 35.00
- Mounting: 4x M4 VESA mount 75x75mm; flange slots (M4 and M8) per datasheet drawing

## Interfaces and compatibility
- 2x full size HDMI 2.0 (HDMI0, HDMI1), Type-A, up to 4K@60Hz
- 2x USB 3.0 host, 5 Gbps, direct from CM5
- 2x USB 2.0 host, 480Mbps, through an onboard USB hub
- 1x USB-C (for boot and power)
- 1x RJ45 Gigabit Ethernet (10/100/1000M), eth0 in Raspberry Pi OS
- 1x M.2 Key-M socket: Gen 2 1-lane PCIe, NVMe SSD 2230 & 2242, bootable
- 1x mini PCIe socket: USB 2.0 only, no PCIe signal
- Compute module: Raspberry Pi CM5
- OS: Raspberry Pi OS; Cytron tutorial also lists Ubuntu as a Raspberry Pi Imager choice
- OS flashing: Boot switch + USB-C to a PC; Cytron tutorial uses rpiboot (if required) and Raspberry Pi Imager
- Optional 4G/LTE module in the mini PCIe socket (not included; regional compatibility varies) per Cytron tutorial
- Remote access per Cytron tutorials: SSH (iriv-smarthub.local or IP), VNC via raspi-config, SCP/SFTP/USB drive file transfer, UVC USB webcam

## Use cases
- IR4.0 industrial controller
- Edge computing
- Industrial automation and centralized control
- Remote monitoring
- Thin clients
- Digital systems
- Smart infrastructure
- Headless, field and rack-mounted deployments
- Moving scripts and software updates; retrieving logs
- Air-gapped or offline file transfer by USB drive
- Basic machine vision with a UVC USB webcam
- Inspection stations
- Offline video monitoring

## Known limitations
- Mini PCIe socket is USB 2.0 only; PCIe signal is not available, so PCIe-only cards will not work
- M.2 socket supports NVMe 2230 and 2242 only; M.2 SATA SSD is not supported
- USB-C input range is 4.9-5.2 VDC only
- DC input is 10-30 VDC
- USB current is shared: 2 A total across both USB 3.0 ports, 1 A total across both USB 2.0 ports
- The 6 W power figure excludes USB load and applies to the stated stress-ng CPU test only
- Operating temperature is -20 to 60 ℃
- Dimensions exclude the antenna; datasheet Features table and drawing disagree on width/height (94 vs 98 mm, 35.7 vs 35 mm)
- No field I/O (RS485, CAN, digital or analog I/O) and no 40-pin GPIO header are listed
- GPIO4, 5, 6, 19, 20, 21 are used by onboard functions
- Boot/Run switch and wireless disable jumper are inside the enclosure; disabling WiFi/BT needs soldering
- 4G/LTE module and CR2032 battery are not included (Cytron tutorial); a SIM card is needed only when an LTE module is installed
- DIN-rail mounting is not stated
- Datasheet text calls the PWR/ACT LEDs "CM4" LEDs; this is a typo, the module is CM5

## Positioning (kept apart from specs)
- Centralized point for data processing, device connectivity and intelligent control at the edge
- Alternative to traditional PCs for edge computing: compact, fanless metal enclosure with no moving parts, lower maintenance, lower power, simpler infrastructure
- Raspberry Pi CM5 compute with industrial power handling, cooling and a finished enclosure
- Datasheet tagline: "Simplifying Smart Technology"

## Price band
[NOT STATED]

## Product page
https://my.cytron.io/p-iriv-smarthub-cm5

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

