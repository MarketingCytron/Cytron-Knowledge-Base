# Cytron Product Knowledge Base

Verified, source-tagged product facts for **Cytron-brand products** — Arduino, ESP32, Pico, Raspberry Pi and micro:bit boards, shields, kits and bundles, robot controllers, sensors, USB-serial converters, motor drivers, power and storage, the IRIV industrial series, and Cytron workshops and services.

It is written to be used as ground truth by AI assistants that write tutorials, articles and product content, and by the people who review that content.

## How it is organised

| Path | What it holds |
|---|---|
| [`INDEX.md`](INDEX.md) | Start here. Rules for using the facts, the product list with confidence levels, and cross-product notes |
| `<product>.md` | Detailed reference per product: specifications, pin and terminal maps, rules and gotchas, conflicts between sources, and what still needs verification |
| [`fact-sheets/`](fact-sheets/) | One short fact sheet per product in a fixed 13-heading format (product name, aliases, specs, interfaces, use cases, limitations, positioning, links) |
| [`fact-sheets/ALL-fact-sheets.md`](fact-sheets/ALL-fact-sheets.md) | Every fact sheet in one file |
| [`_TEMPLATE.md`](_TEMPLATE.md) | Template for adding a product |

## Source rules

- The **datasheet is the main source**. User manuals rank second, then the Cytron product page, Cytron GitHub, chip-vendor documentation, and finally third-party sites. For kits, accessories, consumables and services that have no datasheet, a Cytron guide book, Getting Started document, Cytron tutorial or the product page is the source, and the fact sheet says so.
- Every fact carries a source tag: `[DS]` datasheet, `[UM]` user manual, `[DT]` Cytron design team, `[PP]` product page, `[GH]` GitHub, `[WIKI]` staff wiki, `[VEN]` chip vendor, `[3P]` third party.
- Where sources disagree, both values are recorded under *Conflicts between sources* and the higher-ranked source wins.
- A fact that only a third party states is never presented as a specification — it is listed under *Needs verification*.
- If a source does not state something, the fact sheet says **[NOT STATED]**.

## Products covered (110)

Maker ESP32 · Robo ESP32 · Maker Feather AIoT S3 · Maker UNO · Maker UNO Plus · Maker Uno RP2040 · Maker Nano · Maker Nano RP2040 · Cytron UNO · Cytron UNO Special Edition · Robo Uno Shield · PS2 Shield · ESP8266 WiFi Shield · LiPo Power Shield · 8 Channels RC Servo Controller Shield · Screw Terminal Shield · Maker UNO Edu Kit · Maker UNO Learning Box · Maker Uno X Learning Guide (book) · PikaBot · Robo Pico · EDU PICO V2 · Maker Pi RP2040 · Maker Pi Pico · Maker Pi Pico Mini · MOTION 2350 Pro · Maker Nano RP2040 Getting Started Bundles · DIY Fire Detection (Pico) · MOTION:BIT · MOTION:BIT Pro · SUMO:BIT · REKA:BIT · ZOOM:BIT · Grove WiFi 8266 · REKA:BIT RBT Project Kit · Auto Plant Watering Kit · BEETLE:BIT · STRIKER:BIT · SUMO:BIT Robot Kit · Robot Battle (500g) · SOCCER:BIT · DIY RC Boat · Maker Mini Sumo Controller · URC10 · IR Sumo Start · Ikedo Mini Sumo Robot V2 · Ikedo Mini Sumo Robot Pro Bundle · 1KG RC Sumo Robot Bundles · PCB Plate for Sumo Robot · SC08A Servo Controller · UC00C · UC00A · Maker Line · Maker Object · Maker Reflect · Maker Reflect S · Maker Soil Moisture Sensor · MCP9700 Temperature Sensor · LSA08 Line Sensor · RE08A Rotary Encoder Kit · STEM Robot Building Base · Reconfigurable Line Following Track · Robo Bracket for Micro Servo · Maker Drive · MDD3A · SHIELD-2AMOTOR · SHIELD-3AMOTOR · FD04A · MD10C · MD10-POT · SHIELD-MD10 · MDD10A · SHIELD-MDD10 · HAT-MDD10 · MD13S · MD20A · MDD20A · MD25HV · MD30C · MDDS10 · MDDS30 · MDDS60 · Enhanced SmartDrive40 (MDS40B) · SmartDrive160 (MDS160A) · MDDRC5 · MDDRC10 · iMD16 · IRIV PiControl CM4 · IRIV PiControl CM5 · IRIV IO Controller · IRIV IOC MQTT Gateway · IRIV SmartHub CM5 · IRIV EdgeAI CM5 · IRIV EdgeAI Safety Box Kit · Maker pHAT · Maker Hat Base · CM4 Maker Board · Industrial IO HAT+ · 27W PD USB-C PSU · 17.5W USB-C PSU · 18650 Li-Ion 2200 mAh · Cooling Fan for RPi · MakerDisk NVMe 2242 · MakerDisk NVMe 2280 · MakerDisk NVMe 2280 (JetPack) · MakerDisk SATA 120GB · AI Agent Workshop for RPI 5 · Jetson Orin Nano AI Fundamentals Workshop · Cytron Raspbot Workshop · Flash JetPack Service

## Notes

- Always check prices, stock and availability on the live product page at [my.cytron.io](https://my.cytron.io) before publishing them.
- This is the public edition. Internal working notes are kept privately by the Cytron marketing team.
- Maintained by Cytron Technologies marketing. Last updated 19 Oct 2026.
