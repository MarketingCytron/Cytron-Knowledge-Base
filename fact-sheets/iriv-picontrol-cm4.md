# Product fact sheets

## Product name
IRIV PiControl CM4

## Aliases
IRIV PiControl CM4, IRIV-PICL, PiControl CM4, IRIV PiControl IR4.0 CM4 Industrial Controller

## What it is
An industrial controller built around the Raspberry Pi Compute Module 4 in a fanless, DIN-rail-mountable metal enclosure. It adds isolated digital inputs, digital outputs, analog inputs, RS485 and RS232, two Ethernet ports and M.2 NVMe / mini PCIe expansion, powered from 10–30 VDC. The datasheet also lists an optional 4G module setup (Micro SIM socket, 4G antenna mounting hole, 4G status LEDs).

## Specs and functions
- Primary source: IRIV PiControl Datasheet Rev 1.2, Nov 2025 (covers CM4 and CM5; CM4 values only here); secondary: User Manual Rev 1.3, Nov 2025
- Document code: IRIV-PICL (User Manual Rev 1.3, Nov 2025; not stated in the datasheet)
- Compute module: Raspberry Pi CM4
- CPU: Broadcom BCM2711 quad-core 64-bit Cortex-A72 (ARM v8) SoC @ 1.5GHz
- RAM: 1GB/2GB/4GB/8GB LPDDR4-3200
- Storage: 8GB/16GB/32GB eMMC, expandable via M.2 NVMe SSD
- Wireless (optional): 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- Power input: Terminal 1 10–30 VDC, surge protected up to 60V 20ms; or USB-C (3 Amp) 4.9–5.2 VDC
- Power-input fuse: 4 Amp, replaceable
- Power consumption: max 6.5 W (stress-ng --cpu 4 --cpu-method fft; USB load not included)
- 4x isolated digital input: VIL -50 to 0.8 V, VIH 3 to 50 V, turn-on minimum DC 3.0V 0.2mA, isolation 3750 Vrms, active high, wet contact only; DI0/DI1/DI2/DI3 = GPIO13/GPIO17/GPIO22/GPIO27
- 4x isolated digital output: solid state relay dry contact, DC or AC load, max 50 V 500 mA, isolation 1500 Vrms, active high; DO0/DO1/DO2/DO3 = GPIO23/GPIO24/GPIO25/GPIO26
- 4x isolated analog input: 0-5V / 0-10V / 0-20mA, common AGND; voltage mode 0–10 V, current mode 0–20 mA; input impedance 25 kΩ (voltage) / 250 Ω (current); isolation 3000 Vrms; ADS1115 ADC at I2C 0x48 (bus 1)
- Isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, /dev/ttyACM0, switchable 120Ω termination
- Isolated RS232: max 120 kbps, isolation 3000 Vrms, /dev/ttyACM1
- PCF85063A RTC (I2C 0x51, I2C0) with CR2032 coin-cell holder
- ATECC608B crypto authentication (I2C 0x60)
- SSD1306 0.96" OLED display (I2C 0x3C)
- User button on GPIO4 (can be programmed as safe-shutdown button); reset button (hard reset, also wakes the CM4 after shutdown)
- Active buzzer on GPIO19 (beeps when high); LED0 on GPIO20, LED1 on GPIO21
- Status LEDs: PWR, ACT, M.2 (NVMe activity), 4G PWR (4G module power), WWAN (4G WWAN activity) — the 4G PWR and WWAN LEDs are in the datasheet but not the user manual, whose drawing shows mPCIe PWR / STAT instead (to be confirmed by engineering)
- Optional 4G hardware (datasheet): Micro SIM socket for the 4G module, 4G antenna mounting hole — not shown in the user manual (to be confirmed by engineering)
- Operating temperature: -20 to 60 ℃
- Enclosure: metal, fanless, DIN rail mountable; 141.2mm x 83.5mm x 39.5mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- DIN bracket can be moved; four mounting options (no DIN socket, DIN positions 1 (default), 2 and 3)
- Sold on my.cytron.io as CM4 Wireless 8GB/32GB, 4GB/32GB and 2GB/16GB (page shared with CM5)
- Warranty 12 months (product page)
- Packing: controller with CM4, dual-band antenna, flat and Phillips screwdrivers, 4 silicone bumpers; no NVMe SSD or mini PCIe card (product page)

## Interfaces and compatibility
- 1x full-size HDMI 2.0 (up to 4K@60Hz)
- 2x USB 2.0 host (480Mbps), 1000mA max for both ports together
- 1x USB-C: Boot mode (load OS image into eMMC) or Debug mode (CM4 UART console via USB-UART chip), set by an internal switch; can also power the unit
- 1x RJ45 Gigabit Ethernet (10/100/1000M) = eth0; 1x RJ45 10/100M Ethernet via USB Ethernet controller = eth1
- 1x M.2 Key-M socket: PCIe Gen 2 x1, NVMe SSD 2230 & 2242, bootable
- 1x mini PCIe socket for 4G/LoRa modules (optional): USB 2.0 and SPI only, no PCIe signal; power switched by GPIO6
- Terminal 1: VIN (10-30V), GND, RS485 A / B / 485G, RS232 TX / RX / 232G, DO0–DO3
- Terminal 2: DI0–DI3 (+/−), AN0–AN3 (AI0–AI3), AGND
- OS: Raspberry Pi OS; setup script `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash` (Raspberry Pi OS only), then reboot
- Setup script enables USB host (dtoverlay=dwc2,dr_mode=host), I2C0 + RTC, I2C1, external antenna (dtparam=ant2), and installs the OLED/status/shutdown background script
- ADC library: Adafruit_ADS1x15 (pip install Adafruit_ADS1x15)
- Raspberry Pi GPIO libraries and serial libraries (pySerial) work with the GPIO numbers and /dev/ttyACM0 / ttyACM1 (staff wiki)
- Node-RED: Cytron 13-part tutorial series "IRIV PiControl Hands-On Using Node-RED in Industry 4.0" (staff wiki)
- eMMC flashing with rpiboot (github.com/raspberrypi/usbboot) in USB-C Boot mode (staff wiki)

## Use cases
- Edge computing
- IoT gateways
- Industrial automation
- Robotics
- Data logging
- Energy management systems
- Machine monitoring
- Energy monitoring
- PLC / data integration (PLC / Modbus data into an app, dashboard or report)
- Remote monitoring / IIoT
- System integrator pathway
- Training (workshops, kits, Industry 4.0 capability building)
- Custom IRIV solution
- Cytron tutorial: [Ai-Gestured Controlled with IRIV PiControl](https://my.cytron.io/tutorial/gesture-controlled-with-iriv-picontrol)
- Cytron tutorial: [AI Plant Disease Detection with IRIV PiControl](https://my.cytron.io/tutorial/ai-plant-disease-detection-with-iriv-picontrol)

## Known limitations
- Digital inputs accept wet contacts only (need an external source, min DC 3.0V 0.2mA, max DC 50V); a plain dry switch will not register
- Digital outputs are dry contacts, max 50V 500mA; they switch an external source and do not supply voltage
- AGND is isolated from system ground but common to all four analog input channels
- 0-20mA measurement needs the internal shunt DIP switch ON (enclosure must be opened)
- RS485 termination, analog mode and USB-C Boot/Debug selection are internal switches
- M.2 SATA SSDs are not supported (NVMe only, 2230/2242)
- Mini PCIe has no PCIe signal: only USB 2.0 and SPI
- USB host is disabled by default on CM4: USB 2.0 ports, eth1 and the RS485/RS232 chip need the setup script (or manual config) before they work
- Setup script is only available for Raspberry Pi OS
- RS485/RS232 appear as /dev/ttyACM0 and /dev/ttyACM1, not as CM4 GPIO UARTs
- USB 2.0 ports share 1000mA total
- Wireless is optional (depends on CM4 variant); WiFi or BT can be disabled only by solder-shorting a jumper
- GPIO4, 6, 13, 17, 19, 20, 21, 22, 23, 24, 25, 26, 27 are used by onboard functions
- Operating temperature -20 to 60 ℃
- The manual's 0-20mA code example stores a current in mA in a variable named `voltage`
- On Raspberry Pi OS Bookworm, a system-wide pip install is blocked; use a virtual environment

## Positioning (kept apart from specs)
- Manual tagline: "Simplifying Digital Making"
- Described as an "IR4.0 CM4 Industrial Controller" (user manual) / "IR4.0 CM4 / CM5 Industrial Controller" (datasheet) / Industry 4.0 controller
- Sibling product IRIV PiControl CM5 (IRIV-PICL5) exists; keep CM4 and CM5 specs apart

## Price band
RM1,489.00–RM2,899.00 across CM4/CM5 variants (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-iriv-picontrol-cm4-industrial-controller

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

