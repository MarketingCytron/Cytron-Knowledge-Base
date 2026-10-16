# Cytron Product Knowledge Base

Verified product facts for **Cytron-brand products**, written for AI agents (tutorial, article and script writers) and for the people who check their output. Every fact is tagged with its source; anything a source doesn't state is marked as not stated rather than guessed.

**Start here:** read this index, then load only the product files a task needs.

**Scope: Cytron-brand products only.** Third-party boards and modules that Cytron resells are not covered here.

This is the public edition. Internal working notes (internal document links, pricing sources, unreleased products and the open-issues log) are kept privately by the Cytron marketing team.

## Rules for any agent using this KB

1. **Only state a spec that is in a product file.** If it isn't there, say it's unconfirmed — never fill the gap from memory or a reseller page.
3. **Read the *Conflicts* and *Needs verification* sections** before writing about a product. Anything listed under *Needs verification* must not appear as fact in published content.
4. **Pin rules are hard rules.** Code and wiring must follow each file's "Pin rules and gotchas".
6. **Dated facts** (price, stock, store list) must be re-checked on the live page before going public.

## How the KB is arranged (two layers)

| Layer | Folder | Format | Use it for |
|---|---|---|---|
| **1. Product fact sheets** | `fact-sheets/` | Cytron Content Hub "Product fact sheets" form: 13 fixed headings, source-only facts, `[NOT STATED]` where the source is silent | Pasting into the Content Hub; marketing, scripts and articles; the first thing any agent reads |
| **2. Detailed references** | this folder (`<product>.md`) | Source-tagged reference with pin maps, conflicts and *Needs verification* | Writing code, wiring and tutorials; checking where a fact came from |

`fact-sheets/ALL-fact-sheets.md` holds every sheet in one file, ready to paste. A fact sheet must never say more than its detailed reference. When a reference changes, update the matching fact sheet in the same edit.

Fact sheet rules (from the Content Hub form): use only what the source states; keep numbers, units and names exactly; `[NOT STATED]` for anything missing; keep every heading in order; keep every stated limitation; marketing language only under *Positioning*; when product page and datasheet disagree give both with their source; price only if a source states one; each alias belongs to one product only.

## Products

### Maker ESP32 family (ESP32 ecosystem)

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| Maker ESP32 | [`maker-esp32.md`](maker-esp32.md) | `MAKER-ESP32` | ESP32 (WROOM-32E-N8) | Active, launched Sep 2026 | **High** |
| Robo ESP32 | [`robo-esp32.md`](robo-esp32.md) | `ROBO-ESP32` | None onboard — hosts a 30-pin NodeMCU ESP32 / Maker ESP32 | Active (Datasheet Rev 1.1, Feb 2026) | **Medium** |
| Maker Feather AIoT S3 | [`maker-feather-aiot-s3.md`](maker-feather-aiot-s3.md) | `MAKER-FEATHER-AIOT-S3` (+`-H`) | ESP32-S3 (WROOM-1-N8R8) | Active | **Medium-high** |

### Raspberry Pi Pico boards and kits (Robo series, EDU PICO)

| Product | File | Code | Chip | Primary source | Confidence |
|---|---|---|---|---|---|
| Robo Pico | [`robo-pico.md`](robo-pico.md) | `ROBO-PICO` | None onboard — hosts a Raspberry Pi Pico / Pico W | Datasheet Rev 1.0, Apr 2023 | **Medium** |
| EDU PICO V2 | [`edu-pico-v2.md`](edu-pico-v2.md) | `EDU-PICO2` (`EDU-PICO2-NB` = no Pico) | Raspberry Pi Pico 2 W | Datasheet Rev 1.1, Jun 2026 | **Medium** |
| Maker Mini Sumo Controller | [`maker-mini-sumo.md`](maker-mini-sumo.md) | `MAKER-MSUMO` | ATmega328P | Active (Datasheet Rev 1.0, Nov 2019) | **Medium-high** |

### Cytron sumo robot controllers

| Product | File | Code | Chip | Status | Confidence |
|---|---|---|---|---|---|
| URC10 | [`urc10.md`](urc10.md) | `URC10` | Not stated by Cytron | Datasheet Rev 1.0, Mar 2019 + User's Manual V1.2, Apr 2019 | **Medium** |
| IR Sumo Start | [`ir-sumo-start.md`](ir-sumo-start.md) | `IR-SUMO-START` | — (IR start module) | Datasheet Rev 1.0, Apr 2025 | **Medium-high** |

### Cytron motor drivers

| Product | File | Code | Rating (per datasheet) | Primary source | Confidence |
|---|---|---|---|---|---|
| Maker Drive | [`maker-drive.md`](maker-drive.md) | `MAKER-DRIVE` | 2 ch, 2.5–9.5 V, 1 A cont / 1.5 A peak (<5 s) | Datasheet Rev 1.0, Feb 2019 | **Medium-high** |
| MDD3A | [`mdd3a.md`](mdd3a.md) | `MDD3A` | 2 ch, 4–16 V, 3 A cont / 5 A peak (<5 s) | Datasheet Rev 1.0, Mar 2019 | **Medium** |
| MD10C | [`md10c.md`](md10c.md) | `MD10C` (Rev 3.0) | 1 ch, 5–30 V, 13 A cont / 30 A peak (≤10 s) | User's Manual Rev3.0 V1.0, Aug 2018 (no datasheet) | **Medium** |
| MDD10A | [`mdd10a.md`](mdd10a.md) | `MDD10A` (Rev 2.0) | 2 ch, 5–30 V, 10 A cont / 30 A peak (≤10 s) per ch | User's Manual V2.0, Jun 2017 (no datasheet) | **Medium-high** |
| MDDS10 SmartDriveDuo-10 | [`mdds10.md`](mdds10.md) | `MDDS10` | 2 ch, 10 A cont / 30 A peak (≤1 s) | User's Manual V1.0, Jun 2015 (no datasheet) | **Medium** |
| MDDRC5 | [`mddrc5.md`](mddrc5.md) | `MDDRC5` | 2 ch R/C, 7–30 V, 5 A cont / 20 A peak (<1 s) per ch | Datasheet Rev 1.0, Mar 2026 | **Medium-high** |
| iMD16 | [`imd16.md`](imd16.md) | `IMD16` | 1 ch, 16 A cont / 30 A peak (<10 s), no current limit | Datasheet Rev 1.0, Apr 2026 | **Medium-high** |

- **No reverse-polarity protection** on MD10C, MDD10A, MDDS10 (Maker Drive and MDD3A do have it). **No over-current protection is stated on any of them** — never claim it.
- **Switching power supplies:** MDD10A, MDDS10 and iMD16 documents warn about regenerated current / back-EMF — use a battery, or a battery of the same voltage in parallel (MDDS10, MDD10A), or bulk capacitors / TVS (iMD16).
- **Brake vs coast differs by board.** Both inputs LOW = brake on Maker Drive, MDD3A and Robo Pico; both HIGH = coast on Maker Drive but brake on MDD3A. PWM LOW = brake on MD10C, MDD10A, iMD16. Check each file.
- **Control mode:** Maker Drive and MDD3A are two-PWM (CytronMotorDriver `PWM_PWM`), not PWM+DIR.
- **MDDRC5:** peak is 20 A for <1 s (product page says <5 s); its 5 V RC-header pin is for the receiver only (500 mA) — never power a servo from it; USB-C does not power the motors.

### Raspberry Pi accessories (industrial)

| Product | File | Code | For | Primary source | Confidence |
|---|---|---|---|---|---|
| Industrial IO HAT+ | [`industrial-io-hat-plus.md`](industrial-io-hat-plus.md) | `HAT-IND-AG` | Raspberry Pi 5 only | Datasheet Rev 1.0, Sep 2025 | **Medium-high** |

### IRIV industrial series

| Product | File | Code | Processor | Primary source | Confidence |
|---|---|---|---|---|---|
| IRIV PiControl CM4 | [`iriv-picontrol-cm4.md`](iriv-picontrol-cm4.md) | `IRIV-PICL` | Raspberry Pi CM4 (BCM2711) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.3, Nov 2025 | **Medium-high** |
| IRIV PiControl CM5 | [`iriv-picontrol-cm5.md`](iriv-picontrol-cm5.md) | `IRIV-PICL5` | Raspberry Pi CM5 (BCM2712) | **Datasheet Rev 1.2, Nov 2025** (CM4/CM5) + User Manual Rev 1.5, Jan 2026 | **Medium** |
| IRIV IO Controller | [`iriv-io-controller.md`](iriv-io-controller.md) | `IRIV-IOC` | Raspberry Pi RP2350A (microcontroller, no Linux) | Datasheet Rev 1.0, Jul 2024 | **Medium** |
| IRIV IOC MQTT Gateway | [`iriv-ioc-mqtt-gateway.md`](iriv-ioc-mqtt-gateway.md) | `IRIV-IOC-MQTT` | Same hardware as IO Controller + factory MQTT firmware | Datasheet Rev 1.0, Jun 2026 | **Medium** |
| IRIV SmartHub CM5 | [`iriv-smarthub-cm5.md`](iriv-smarthub-cm5.md) | `IRIV-SH5` | Raspberry Pi CM5 (BCM2712) | User Manual Rev 1.3, Dec 2025 | **Medium-high** |
| IRIV EdgeAI CM5 | [`iriv-edgeai-cm5.md`](iriv-edgeai-cm5.md) | `IRIV-EDGEAI-CM5` | Raspberry Pi CM5 (BCM2712) + AI HAT+ | Datasheet Rev 1.0, Jul 2025 | **Medium-high** |
| IRIV EdgeAI Safety Box Kit | [`iriv-edgeai-safety-box-kit.md`](iriv-edgeai-safety-box-kit.md) | `KIT-IRIV-EAI-PPE` | IRIV EdgeAI CM5 (8GB/32GB) + Hailo-8 26 TOPS | No kit datasheet. Controller: EdgeAI CM5 Datasheet Rev 1.0 | **Medium-low** |

**Source rule for IRIV (16 Oct 2026): the datasheet is the main source.** User manuals rank second ([UM]); where a newer manual disagrees, the datasheet still wins in the text and the conflict is listed for engineering.

IRIV notes for every agent:
- **IO Controller is not a Raspberry Pi computer.** No Raspberry Pi OS or Node-RED on the device.
- **IOC MQTT Gateway firmware must not be overwritten** — no CircuitPython/UF2 steps; setup is via USB-C web page at 10.0.0.1. Plain MQTT on port 1883, no TLS on the device.
- **PiControl CM4, PiControl CM5 and EdgeAI CM5 RS485 is a USB serial device (`/dev/ttyACM*`)**, not a GPIO UART.
- **mini PCIe sockets on PiControl CM4, PiControl CM5, SmartHub CM5 and EdgeAI CM5 carry USB 2.0 only** (no PCIe). M.2 = NVMe only, no SATA.
- **Bare "IRIV PiControl" is ambiguous** between CM4 (`IRIV-PICL`) and CM5 (`IRIV-PICL5`); the shared datasheet code `IRIV-PICONTROL` covers both.
- **Safety Box Kit is not a certified safety system**, detects helmets and vests only, needs RTSP IP cameras (not included), and its "up to 6 cameras" holds only for 640x360 sub-streams at 15–25 FPS. No accuracy figure exists — "96% compliant" in marketing is an example dashboard reading.
- **Bare "IRIV SmartHub" is ambiguous** with the SmartHub dashboard feature of EdgeAI. Always use the full name.
## Quick cross-product facts (ESP32 family)

| | Maker ESP32 | Robo ESP32 | Maker Feather AIoT S3 |
|---|---|---|---|
| USB | USB-C, CH9102F | none (uses host board) | USB-C, native USB (no bridge) |
| Arduino board | ESP32 Dev Module | ESP32 Dev Module (host) | Cytron Maker Feather AIoT S3 |
| Flash / PSRAM | 8 MB / — | — | 8 MB / 8 MB octal |
| Onboard LED pin | 14 LEDs (incl. GPIO2) | NeoPixel ×2 on GPIO15 | GPIO2 + RGB on GPIO46 |
| Buzzer | GPIO26 | GPIO23 | GPIO12 |
| User button | GPIO4 | GPIO34, 35 | GPIO3 |
| I2C port | Maker Port 21/22 | Grove 2 + Maker Port 21/22 | Maker Port 42/41 |
| Analog safe with Wi-Fi | ADC1: 32–39 | Grove 4–7 (33, 32, 39, 36) | GPIO4–10 (A0–A5, A7) |

## How to add or update a product

1. Check it is a Cytron-brand product. Then copy `_TEMPLATE.md` to `<product-slug>.md`.
2. Start from the Cytron datasheet. Tag every fact with its source. Put conflicts and unconfirmed items in their sections — don't drop them.
3. Fill `fact-sheets/<product-slug>.md` in the Content Hub template from that reference (only what it states), and add it to `fact-sheets/ALL-fact-sheets.md`. Check the aliases don't clash with another product.
4. Add the row to *Products* above with an honest confidence level.
5. Commit to this repository with a message like `kb: add <product>`.
6. When the design team confirms something, mark it [DT] with the date and remove it from *Needs verification*.

