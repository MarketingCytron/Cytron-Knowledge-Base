# Product fact sheets

## Product name
Maker Pi Pico Mini: Simplifying Projects with Raspberry Pi Pico

## Aliases
MAKER-PI-PICO-MINI, MAKER-PI-PICO-MINI-NB, Maker Pi Pico Mini, Cytron Maker Pi Pico Mini

## What it is
A small carrier board for the Raspberry Pi Pico / Pico W with status LEDs, a button, a passive buzzer, an RGB LED, three JST-SH Maker Ports and a USB-rechargeable single-cell LiPo / Li-Ion battery input. MAKER-PI-PICO-MINI comes with a Pico / Pico W pre-mounted; MAKER-PI-PICO-MINI-NB has a Pi Pico socket instead.

## Specs and functions
- Power input voltage, USB: 4.5–5.5 VDC (Datasheet, Absolute Maximum Ratings)
- Power input voltage, LiPo battery: 3.3–4.2 VDC
- Digital input voltage: low -0.3 to 0.8 V; high 2.0 to 3.6 V
- Digital output voltage: low 0 to 0.5 V; high 2.6 to 3.3 V
- Analog input voltage: 0 to 3.3 V
- Operating temperature: -20 to 85 ℃
- Dimensions: 53.85 mm × 23.12 mm
- Status LEDs for GP0 - GP5 (6 LEDs), turn on when the IO state is high
- GPIO LED Enable Jumper: cut the trace to disable the GPIO LEDs
- Programmable button on GP20 (hardware pull-up and debounce capacitor per schematic)
- Reset button (RUN)
- Programmable passive piezo buzzer on GP18
- User programmable WS2812B RGB LED on GP28
- LiPo battery connector for single cell LiPo / Li-Ion, rechargeable via USB; charging LED
- Battery charger MCP73831T-2ACI/OT and protection IC CT2105 (schematic)
- 3.3V power LED
- GPIO breakout for all Pico pins (headers not pre-soldered on the pre-mounted version)
- Pi Pico socket on MAKER-PI-PICO-MINI-NB only
- Variants: MAKER-PI-PICO-MINI (Pico), MAKER-PI-PICO-MINI-W (Pico W), MAKER-PI-PICO-MINI-NB (no Pico); Pico variants preloaded with CircuitPython (product page)

## Interfaces and compatibility
- Host: Raspberry Pi Pico / Pico W
- 3x Maker Ports, JST-SH 4-ways, pin order GND, 3V3, GPIO, GPIO: GP0/GP1 (I2C0 SDA0/SCL0, UART0 TX0/RX0), GP4/GP5 (I2C0 SDA0/SCL0, UART1 TX1/RX1), GP26/GP27 (I2C1 SDA1/SCL1, A0/A1)
- Maker Ports compatible with Qwiic, STEMMA QT and Grove (via conversion cable)
- Board uses GP0–GP5 (status LEDs), GP18 (buzzer), GP20 (button), GP28 (RGB LED)
- Battery: single cell LiPo / Li-Ion

## Use cases
- Projects with Raspberry Pi Pico / Pico W
- Battery-powered Pico / Pico W projects with USB recharging
- Connecting Qwiic, STEMMA QT and Grove (via conversion cable) modules to a Pico

## Known limitations
- No audio jack, no microSD socket, no ESP-01 socket, no buzzer mute switch, no on/off switch
- Maker Ports are JST-SH; Grove modules need a conversion cable
- Maker Ports GP0/GP1 and GP4/GP5 both use I2C0
- Only GP26 and GP27 offer analog input on a Maker Port; GP28 (A2) drives the RGB LED
- Status LEDs on GP0–GP5 light whenever the pin is HIGH; cut the jumper to disable them
- GPIO breakout headers are not pre-soldered on the version with Pico / Pico W pre-mounted
- If the board cannot be turned on with the battery connected, charge the battery to activate the battery protection circuit
- Pico 2 / Pico 2 W compatibility: [NOT STATED]
- Charge current and 3V3 current budget for Maker Ports: [NOT STATED]

## Positioning (kept apart from specs)
- Product page title: "Maker Pi Pico Mini: Simplifying Projects with Raspberry Pi Pico"
- Datasheet tagline: "Simplifying Projects with Raspberry Pi Pico / Pico W"

## Price band
RM35.60–RM47.60 across 3 variants (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-maker-pi-pico-mini-simplifying-projects-with-raspberry-pi-pico

## Datasheet
https://docs.google.com/document/d/14Yzc7C-3NXtMi0Cuqn2ZFWilJjBVvCIbsKoMZJ8b24Q/edit

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/14Yzc7C-3NXtMi0Cuqn2ZFWilJjBVvCIbsKoMZJ8b24Q/edit
