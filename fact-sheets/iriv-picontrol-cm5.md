# Product fact sheets

## Product name
IRIV PiControl CM5

## Aliases
IRIV-PICL5, IRIV PiControl CM5, PiControl CM5, IRIV PiControl IR4.0 CM5 Industrial Controller, IR4.0 CM5 Industrial Controller

## What it is
An industrial controller built around the Raspberry Pi Compute Module 5 in a fanless, DIN-rail-mountable metal enclosure. It adds isolated digital inputs, digital outputs, analog inputs, RS485 and RS232, two Ethernet ports and M.2 NVMe / mini PCIe expansion, and runs from 10–30 VDC.

## Specs and functions
- Document code: IRIV-PICL5 (User Manual Rev 1.5, Jan 2026); datasheet: IRIV PiControl Datasheet Rev 1.2, Nov 2025 (covers CM4 and CM5)
- Compute module: Raspberry Pi CM5
- CPU: Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) SoC @ 2.4GHz
- RAM: 2GB/4GB/8GB/16GB LPDDR4-4267 (Datasheet Rev 1.2); 4GB/8GB/16GB (User Manual Rev 1.5)
- Storage: 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD (Datasheet Rev 1.2); 32GB/64GB eMMC (User Manual Rev 1.5)
- Variants listed in the User Manual: IRIV PiControl CM5 Wireless 4GB/32GB, Wireless 8GB/32GB, Wireless 8GB/64GB, Wireless 16GB/64GB
- Wireless (optional): 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- Power input: Terminal 1 10–30 VDC, surge protected up to 60V 20ms; or USB-C (3 Amp) 4.9–5.2 VDC
- Power-input fuse: 4 Amp, replaceable
- Power consumption: max 10.5 W (stress-ng --cpu 4 --cpu-method fft; USB load not included)
- 4x isolated digital input: VIL -50 to 0.8 V, VIH 3 to 50 V, turn-on minimum DC 3.0V 0.2mA, isolation 3750 Vrms, active high, wet contact only
- 4x isolated digital output: solid state relay dry contact, DC or AC load, max 50 V 500 mA, isolation 1500 Vrms, active high
- 4x isolated analog input: 0-5V / 0-10V / 0-20mA, common AGND; voltage mode 0–10 V, current mode 0–20 mA; input impedance 25 kΩ (voltage) / 250 Ω (current); isolation 3000 Vrms; ADS1115 ADC at I2C 0x48 (bus 1)
- Isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, /dev/ttyACM0, switchable 120Ω termination
- Isolated RS232: max 120 kbps, isolation 3000 Vrms, /dev/ttyACM1
- PCF85063A RTC (I2C 0x51, I2C0) with CR2032 coin-cell holder
- ATECC608B crypto authentication (I2C 0x60)
- SSD1306 0.96" OLED display (I2C 0x3C)
- User button on GPIO4 (can be programmed as safe-shutdown button); reset button (hard reset, also wakes the CM5 after shutting down)
- Active buzzer on GPIO19 (beeps when high); LED0 on GPIO20, LED1 on GPIO21
- Status LEDs: PWR, ACT, M.2 (NVMe SSD activity); mini PCIe PWR and STAT LEDs on the front panel (User Manual figure)
- Operating temperature: -20 to 60 ℃
- Enclosure: metal, fanless, DIN rail mountable; 141.2mm x 83.5mm x 39.5mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- DIN bracket can be moved; four mounting options (without DIN rail socket, DIN positions 1 (default), 2 and 3)
- DI0–DI3 on GPIO13, 17, 22, 27; DO0–DO3 on GPIO23, 24, 25, 26 (User Manual block diagram; same as the CM4 version)
- Sold on my.cytron.io as CM5 Wireless 16GB/64GB and 8GB/64GB (product page shared with CM4)
- GPU: 800 MHz VideoCore VII, OpenGL ES 3.1 (product page)
- Wireless: 2.4/5 GHz Wi-Fi 802.11ac, Bluetooth 5.0, BLE (product page)
- Dimension: 141.2 × 83.5 × 39.5 mm, enclosure only (product page)
- Packing: controller with CM5, dual-band antenna, flat and Phillips screwdrivers, 4 silicone bumpers; no NVMe SSD or mini PCIe card (product page)

## Interfaces and compatibility
- 1x full-size HDMI 2.0 (up to 4K@60Hz), Type-A
- 2x USB 2.0 host (480Mbps), 1000mA max for both ports together
- 1x USB-C: Boot mode (load OS image into eMMC) or Debug mode (CM5 UART console via USB-UART chip), set by an internal switch; can also power the unit
- 1x RJ45 Gigabit Ethernet (10/100/1000M) = eth0; 1x RJ45 10/100M Ethernet via USB ethernet controller = eth1
- 1x M.2 Key-M socket: PCIe Gen 2 x1, NVMe SSD 2230 & 2242, bootable; CM5 PCIe can be enabled as Gen 3 (not certified)
- 1x mini PCIe socket: USB 2.0 and SPI only, no PCIe; power switched by GPIO6. Datasheet says "for 4G/LoRa modules (optional)"; User Manual names no use
- Terminal 1 (2 × 8, User Manual figure): upper row VIN (10-30V), RS485 A, RS485 B, 485G, DO0 pair, DO2 pair; lower row GND, RS232 TX, RS232 RX, 232G, DO1 pair, DO3 pair
- Terminal 2 (2 × 8, User Manual figure): upper row DI0 +/−, DI2 +/−, AN0, AGND, AN2, AGND; lower row DI1 +/−, DI3 +/−, AN1, AGND, AN3, AGND
- RS485 (/dev/ttyACM0) and RS232 (/dev/ttyACM1) come from a USB-to-dual-UART chip on the onboard USB hub, which also serves the two USB 2.0 ports, the 10/100M Ethernet (eth1) and the mini PCIe USB (User Manual block diagram)
- OS: Raspberry Pi OS; setup script `curl -L tinyurl.com/setup-iriv-picontrol | sudo bash` (Raspberry Pi OS only), then reboot
- Setup script edits config.txt (USB host, I2C0 + RTC, I2C1, external antenna dtparam=ant2) and installs the OLED/status/safe-shutdown background script
- ADC library: Adafruit_ADS1x15 (pip install Adafruit_ADS1x15), ADS1115(address = 0x48, busnum = 1)
- Same I/O, terminals, enclosure, dimensions, power input and operating temperature as IRIV PiControl CM4; differs in compute module, CPU, RAM, eMMC, power consumption (10.5 W vs 6.5 W) and optional PCIe Gen 3 (not certified)

## Use cases
- Machine monitoring
- Energy monitoring
- PLC / data integration (PLC / Modbus data into an app, dashboard or report)
- Remote monitoring / IIoT
- System integrator pathway
- Training (workshops, kits, Industry 4.0 capability building)
- Custom IRIV solution

## Known limitations
- Digital inputs accept wet contacts only (need an external source, min DC 3.0V 0.2mA, max DC 50V)
- Digital outputs are dry contacts, max 50V 500mA; they switch an external source and do not supply voltage
- AGND is isolated from system ground but common to all four analog input channels
- 0-20mA measurement needs the internal shunt DIP switch ON (4-way "ADC Current Mode" DIP; channel mapping not stated)
- RS485 termination, analog mode and USB-C Boot/Debug selection are internal switches
- M.2 SATA SSDs are not supported (NVMe only, 2230/2242); PCIe Gen 3 on CM5 is not certified
- Mini PCIe has no PCIe signal: only USB 2.0 and SPI
- Setup script is only available for Raspberry Pi OS
- RS485/RS232 appear as /dev/ttyACM0 and /dev/ttyACM1
- USB 2.0 ports share 1000mA total
- WiFi or BT can be disabled only by solder-shorting a jumper (separate WLAN and BT jumpers in the User Manual figure)
- GPIO4, 6, 19, 20, 21 are used by onboard functions, and GPIO13, 17, 22, 27 (DI) and 23, 24, 25, 26 (DO) by the isolated I/O
- Operating temperature -20 to 60 ℃
- The datasheet's 0-20mA code example stores a current in mA in a variable named `voltage`
- Datasheet layout pictures and layout text are of the CM4 version

## Positioning (kept apart from specs)
- Described as an "IR4.0 CM5 Industrial Controller"
- Sibling product IRIV PiControl CM4 (IRIV-PICL); keep CM4 and CM5 specs apart. "IRIV PiControl" alone is ambiguous between the two

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

