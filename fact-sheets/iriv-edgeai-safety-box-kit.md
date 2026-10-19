# Product fact sheets

## Product name
IRIV EdgeAI Safety Box Kit

## Aliases
KIT-IRIV-EAI-PPE, IRIV EdgeAI Safety Box Kit, IRIV EdgeAI Safety Box, IRIV EdgeAI - Safety Box: PPE and Zone Monitoring, EdgeAI Safety Box, Safety Box Kit, IRIV SafeVision, IRIV SafeOps, IRIV EdgeAI Safety Vision, IRIV EdgeAI v2

## What it is
A packaged on-premise AI vision appliance: an IRIV EdgeAI CM5 controller with a Hailo-8 26 TOPS accelerator and 128GB NVMe SSD in an IP67 ABS enclosure with its own 24V power supply and fan. It connects to existing RTSP IP cameras to detect missing safety helmets / hi-vis vests and entry into restricted zones, logs events and triggers alarm outputs and digital alerts.

## Specs and functions
- Product code: KIT-IRIV-EAI-PPE
- Availability: by enquiry (product page, 2026-10-19)
- Warranty: 12 months
- Controller: 1x IRIV EdgeAI CM5 Wireless, 8GB RAM, 32GB eMMC, 26 TOPS AI
- Processor: Raspberry Pi Compute Module 5, Broadcom BCM2712 quad-core 64-bit Cortex-A76 (ARM v8) @ 2.4GHz
- RAM: 8GB (controller datasheet type: LPDDR4-4267)
- Storage: 32GB eMMC + pre-installed 128GB NVMe 2242 B+M-Key MakerDisk SSD
- AI accelerator: Hailo-8 NPU, 26 TOPS, on the Raspberry Pi AI HAT+ PCIe port
- Camera stream capacity: up to 6 RTSP IP camera sub-streams, 640x360 @ 15–25 FPS, H.264/H.265
- PPE detection: safety helmet and hi-vis / safety vest, enabled per camera; only non-compliant PPE raises an alert
- Restricted zones: polygon or circle zones drawn on the live view; multiple zones per camera; detects people, vehicles and animals entering; zone entry tracked until clear
- Alerts: isolated digital outputs DO0/DO1 (stack lights, buzzers/sirens, door interlocks, relays), Telegram, Email, MQTT
- Event records: timestamp, camera, detection type, snapshot; optional event clips; filter by date range, camera, zone, detection type
- Web interface: five tabs — Live View, Analytics, Events, Reports, Settings (cameras, models, alerts, users, system)
- Live View: detections drawn on each camera tile; layouts Auto, Grid, Focus, Single; Smart Live switch stops idle tiles after about 30 seconds and resumes on motion or a detection; cameras can be started and stopped
- Analytics: compliance rates, PPE vs zone events, most active zone, top violation type, helmet-vs-vest split
- Reports: audit-ready CSV/PDF reports; Reports tab generates a PDF safety report for a period; Workplace Safety Audit report on demand or by email every month
- Software: pre-loaded web UI and pre-trained PPE and safety-zone models; on-board database; inference runs locally on the Hailo NPU, video is not uploaded to the cloud
- Digital outputs: 2x isolated dry contact (solid state relay), max 50 V DC or AC, max 500 mA, 1500 Vrms isolation (controller datasheet); product page says "up to 50V DC"
- Digital inputs: 2x isolated (up to 50V)
- Wireless: 2.4/5.0 GHz IEEE 802.11 b/g/n/ac WiFi, Bluetooth 5.0, BLE
- Display: 1x full-size HDMI 2.0 (up to 4K@60Hz); SSD1315 0.96" OLED status display
- Kit power supply: industrial switching power supply 24V 36W, wide DC and AC input voltage
- Controller power input: DC 10–30V, surge-protected
- Cooling: 24V DC exhaust fan with 2x intake/exhaust dust filters
- Enclosure: IP67 ABS industrial enclosure, 250 × 350 × 160mm
- Controller dimensions: 139mm × 88mm × 38mm (metal enclosure only, excl. antenna, DIN socket & connectors)
- Controller operating temperature: -20 to 60 ℃; kit operating temperature [NOT STATED]
- First run: connect the box to the local network (wired LAN recommended), read its IP address on the front OLED, open it in a web browser, sign in with the factory account from the Quick Start Guide; the box forces a new password (at least 8 characters) on first sign-in
- Setup wizard: Secure account → Add camera → Ready; camera discovery, shared-credential pairing or manual RTSP URL; re-run from Settings → Setup wizard
- Runs without internet: inference is on the device and video does not leave the site
- Typical setup is stated as under 10 minutes per camera
- In the box: 1x IRIV EdgeAI CM5 Wireless 8GB RAM / 32GB eMMC / 26 TOPS AI; 1x NVMe 2242 B+M-Key MakerDisk SSD 128GB; 2x Gigabit Ethernet cables 0.5m; 1x industrial switching power supply 24V 36W; 1x UK plug power cord with 13A fuse, C13 (D-shape); 1x IEC fuse chassis male power plug with switch; 2x female-to-female RJ45 extension ports; 1x 24V DC fan; 2x intake/exhaust filters; 1x DIN-rail power-distribution terminal block 6P

## Interfaces and compatibility
- Cameras: IP cameras with RTSP streaming support (required); ONVIF for automatic discovery; manual add by RTSP URL
- Camera streams: H.264/H.265, 640x360 sub-stream
- Network: 2x RJ45 Gigabit Ethernet (10/100/1000M) on the controller; 2x female-to-female RJ45 extension ports on the enclosure for external network access
- Outputs: DO0 (GPIO23) and DO1 (GPIO24), dry contact; DO1 can be driven by zone presence
- Integrations: MQTT, Telegram, Email
- Controller ports: 2x USB 3.0, 1x USB-C (boot and debug), 2x MIPI CSI, 1x HDMI 2.0, 1x isolated RS485, 2x isolated DI
- Expansion: 1x M.2 Key-M (holds the 128GB NVMe SSD), 1x PCIe (Raspberry Pi AI HAT+), 1x mPCIe (USB 2.0 only)
- Mains: UK plug, 13A fuse, C13 cord into an IEC fused, switched inlet
- Not included: IP cameras, sirens / stack lights

## Use cases
- Manufacturing plants
- Warehouses
- Construction sites
- Production floors: PPE and restricted-zone monitoring
- Loading bays: forklift/loading-bay monitoring
- Forklift lanes: restricted-zone monitoring
- Oil & Gas: PPE and hazardous-zone monitoring
- Palm oil mills: machinery-area zone monitoring
- Utilities: restricted-area monitoring
- Water treatment: restricted-area monitoring
- EHS / safety operations for EHS officers and safety managers
- PPE compliance monitoring (helmet and vest detection)
- Restricted-zone monitoring (configurable zone-entry detection)
- Audit preparation: logs, snapshots, CSV/PDF reporting, analytics

## Known limitations
- Requires IP cameras with RTSP streaming support; ONVIF is for discovery only
- Up to 6 RTSP feeds, stated at 640x360 sub-streams, 15–25 FPS, H.264/H.265
- PPE detection is limited to safety helmets and safety vests
- Not a certified safety system; supports but does not replace certified safety controls, procedures or trained supervision
- Lighting and camera angle affect suitability
- IP cameras are not included in the packing list
- Digital outputs are dry contacts (max 50 V, 500 mA); the alarm device needs its own supply
- mPCIe expansion uses USB 2.0, not PCIe
- Kit operating temperature, detection distance and accuracy: [NOT STATED]

## Positioning (kept apart from specs)
- Product page name: "IRIV EdgeAI - Safety Box: PPE and Zone Monitoring"; landing-page headline: "AI Vision for Workplace Safety."
- Retrofit layer that turns existing CCTV into an AI safety-monitoring system without replacing cameras; framed around Detection, Response and Record
- Local/on-premise processing positioned as a privacy and latency advantage; video stays on-site
- Target users: EHS officers, safety managers, plant managers and site supervisors; runs alongside existing safety supervision
- Aligned with Malaysia's OSHMP30 framework

## Price band
RM7,999.00 (Cytron product page, availability "Enquiry", read 2026-10-19)

## Product page
https://my.cytron.io/p-iriv-edgeai-safety-box-kit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/p-iriv-edgeai-safety-box-kit
