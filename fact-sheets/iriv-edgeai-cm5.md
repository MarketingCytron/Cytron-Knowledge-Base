# Product fact sheets

## Product name
IRIV EdgeAI CM5

## Aliases
IRIV-EDGEAI-CM5, IRIV EdgeAI CM5, IRIV Edge AI CM5, EdgeAI CM5

## What it is
An industrial controller built around the Raspberry Pi Compute Module 5 in a fanless, DIN-rail-mountable metal enclosure. It has a PCIe port for the Raspberry Pi AI HAT+, two MIPI CSI camera ports, NVMe and mPCIe expansion, dual Gigabit Ethernet, and a terminal with isolated RS485, isolated digital inputs/outputs and LED lighting drivers.

## Specs and functions
- Product code: IRIV-EDGEAI-CM5 (datasheet header)
- Compute module: Raspberry Pi CM5
- CPU: Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) SoC @ 2.4GHz
- RAM: 2GB/4GB/8GB/16GB LPDDR4-4267 (datasheet)
- Storage: 16GB/32GB/64GB eMMC, expandable via M.2 NVMe SSD (datasheet)
- Configurations listed on the product page (via internal KB): 16GB RAM + 64GB eMMC + 26 TOPS; 8GB RAM + 32GB eMMC + 26 TOPS; 8GB RAM + 32GB eMMC + 13 TOPS
- AI acceleration: Raspberry Pi AI HAT+ on a dedicated PCIe port (similar to the PCIe port on Raspberry Pi 5)
- Wireless: 2.4GHz / 5.0GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- 1x full-size HDMI 2.0 (up to 4K@60Hz)
- 2x USB 3.0 host ports (sharing one USB 3.0 hub); 1x USB-C for boot and debug
- 2x 22-way MIPI ports for CSI camera (datasheet); product page describes "dual 4-lane MIPI CSI"
- 2x RJ45 Gigabit Ethernet (10/100/1000M): eth0 = CM5 native, eth1 = USB 3.0-to-Gigabit Ethernet controller
- 2x isolated bidirectional digital inputs: VIL 0–0.8 V, VIH 3–50 V, isolation 3750 Vrms, PNP or NPN sensors, common S/S pin
- 2x isolated bidirectional digital outputs: dry contact (solid state relay), DC or AC load up to 50 V 500 mA, isolation 1500 Vrms
- 2x LED lighting drivers: wet contact, output voltage = Vin, up to 2 A per channel, PWM capable, independent 2 A fuse per channel
- 1x isolated RS485: max 500 kbps, isolation 5000 Vrms, automatic direction control, onboard 120 Ω termination, mapped to /dev/ttyACM0
- 1x M.2 Key-M socket: PCIe Gen 2 1-lane, NVMe SSD 2230 & 2242, bootable
- 1x mPCIe socket for 4G/LoRa modules (USB 2.0 only), Micro SIM socket
- Power input: terminal 10–30 VDC (surge protected up to 60 V 20 ms); USB-C 4.9–5.2 VDC (PD supply, up to 5V 5A)
- Power consumption: max 11 W running "stress-ng --cpu 4 --cpu-method fft", USB load not included
- ATECC608B secure authentication (I2C1, 0x60)
- SSD1315 0.96" OLED display (I2C1, 0x3C)
- 1x power button (single press on, double-press soft shutdown, long-press force shutdown); 1x programmable button on GPIO4
- 1x active buzzer on GPIO19 (active high); 2x programmable LEDs: LED0 GPIO20, LED1 GPIO21
- Status LEDs: PWR, ACT, M.2, 4G PWR, WWAN, LED0, LED1
- GPIO map: DI0 GPIO22, DI1 GPIO27, DO0 GPIO23, DO1 GPIO24, L0 GPIO12, L1 GPIO13, mPCIe reset GPIO5 (active low), mPCIe power GPIO6, USB-C debug UART0
- CR2032 holder keeps the CM5 RTC running when powered off
- 4 A replaceable system fuse (LED drivers excluded)
- Internal Boot/Run switch: Boot = load OS into eMMC via USB-C; Run = USB-C is the CM5 UART0 console
- Solder jumpers to disable WiFi (WL) or Bluetooth (BT)
- Operating temperature: -20 to 60 ℃
- Enclosure: metal, fanless, DIN rail mountable (bracket can move to the bottom)
- Dimension: 139mm x 88mm x 38mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- Configurations: 16GB/64GB + 26 TOPS, 8GB/32GB + 26 TOPS, 8GB/32GB + 13 TOPS AI HAT+; options EdgeAI Only, Basic Kit (PSU, camera, dome light, stand), Complete Kit (+HDMI cable, keyboard/mouse) (product page)
- Operating temperature −20 to 60 °C; power max 11 W (product page)

## Interfaces and compatibility
- Terminal (pluggable): VIN, GND, RS485 A/B/G, S/S, DI0, DI1, DO0, DO1, L0 +/−, L1 +/−
- Raspberry Pi AI HAT+ (PCIe port plus 40-pin header with only 5V, 3V3, GND, ID_SC, ID_SD connected)
- CSI cameras on MIPI0 / MIPI1
- NVMe M.2 SSD 2230/2242 (M.2 SATA not supported)
- 4G or LoRa mini-PCIe modules that use USB 2.0; Micro SIM for the 4G module; reserved 4G antenna mounting hole
- HDMI display, USB 3.0 devices, two Ethernet networks
- RS485 devices via /dev/ttyACM0; PNP or NPN sensors on the digital inputs
- DIN rail
- Raspberry Pi OS (staff wiki)
- Used as the controller in the IRIV EdgeAI Safety Box Kit (KIT-IRIV-EAI-PPE), a separate product

## Use cases
- Edge AI and vision applications
- Defect detection / quality control
- Sorting lines
- Machine-learning inference at the edge, without offloading to the cloud
- IIoT edge gateway connecting sensors, legacy machinery and cloud platforms
- Compact industrial server for Docker/containerized applications, OPC UA servers and local databases
- Industrial automation and digital control
- Smart surveillance
- Agriculture, energy and infrastructure monitoring
- Factory floor, mobile robotics and network-edge deployments
- Cytron tutorial: [Getting Started with IRIV EdgeAI CM5](https://my.cytron.io/tutorial/getting-started-with-iriv-edgeai-cm5)
- Cytron tutorial: [Empowering Edge AI: Highlights from the AI Horizon Exhibition at SPICE Arena Penang](https://my.cytron.io/tutorial/AIHorizon25)
- Cytron tutorial: [IRIV EdgeAI CM5: Enhancing CCTV Cameras](https://my.cytron.io/tutorial/enhance-rtsp-camera-with-iriv-edge-ai)
- Cytron tutorial: [Automate Shutdown and Power‑On with IRIV Real‑Time Clock](https://my.cytron.io/tutorial/automate-shutdown-and-poweron-with-iriv-realtime-clock)
- Cytron tutorial: [Custom Object Detection on IRIV Edge AI](https://my.cytron.io/tutorial/custom-object-detection-on-iriv-edge-ai)

## Known limitations
- mPCIe socket has only USB 2.0 connected; no PCIe signal
- M.2 SATA SSD is not supported
- LED driver outputs (L0, L1) are not powered when running from USB-C (getting-started tutorial)
- LED driver output voltage equals Vin; it is not set separately
- Digital outputs are dry contacts: the load needs its own supply, max 50 V 500 mA
- The two digital inputs share one S/S common
- Inductive loads on the digital outputs: a flyback diode is recommended to reduce EMI
- RS485 max baud rate is 500 kbps; it appears as /dev/ttyACM0, not a GPIO UART
- The 4 A system fuse does not cover the LED drivers; the fuse can blow on surge or overcurrent
- The 11 W maximum excludes USB load
- Boot/Run switch and wireless-disable jumpers are inside the enclosure
- Only 5V, 3V3, GND, ID_SC and ID_SD of the AI HAT+ 40-pin header are connected
- 4G antenna position is a reserved mounting hole only
- Dimensions exclude antenna, DIN socket and connectors
- Operating temperature is -20 to 60 ℃

## Positioning (kept apart from specs)
- Datasheet subtitle: "IR4.0 CM5 Edge AI Controller"
- Product-page name: "IRIV EdgeAI CM5 - IR4.0 Industrial AI Controller"
- Product-page framing: "IR4.0 Industrial-Grade, Low Power, High Performance AI Hub with CM5."
- For manufacturers, machine builders, developers and system integrators deploying Industry 4.0 systems
- Combines Raspberry Pi CM5 compute, AI acceleration, industrial I/O, modular connectivity, fanless metal enclosure and DIN-rail mounting
- Local edge processing to avoid depending on the cloud for AI inference and to reduce latency and bandwidth in IIoT deployments

## Price band
RM2,487.00–RM5,152.50 across configurations and kits (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-iriv-edge-ai-cm5

## Datasheet
[NOT STATED]

## Source type
Datasheet

## Source link
[NOT STATED]

