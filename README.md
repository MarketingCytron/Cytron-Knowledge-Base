# Cytron Product Knowledge Base

Verified, source-tagged product facts for **Cytron-brand products** — Arduino, ESP32 and Pico boards, robot controllers, motor drivers and the IRIV industrial series.

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

- The **datasheet is the main source**. User manuals rank second, then the Cytron product page, Cytron GitHub, chip-vendor documentation, and finally third-party sites.
- Every fact carries a source tag: `[DS]` datasheet, `[UM]` user manual, `[DT]` Cytron design team, `[PP]` product page, `[GH]` GitHub, `[WIKI]` staff wiki, `[VEN]` chip vendor, `[3P]` third party.
- Where sources disagree, both values are recorded under *Conflicts between sources* and the higher-ranked source wins.
- A fact that only a third party states is never presented as a specification — it is listed under *Needs verification*.
- If a source does not state something, the fact sheet says **[NOT STATED]**.

## Products covered (33)

Maker ESP32 · Robo ESP32 · Maker Feather AIoT S3 · Maker UNO · Maker Uno RP2040 · Robo Pico · EDU PICO V2 · Maker Mini Sumo Controller · URC10 · IR Sumo Start · Maker Drive · MDD3A · MD10C · MD13S · MD20A · MDD10A · MDD20A · MD25HV · MDDS10 · MDDS30 · MDDS60 · Enhanced SmartDrive40 (MDS40B) · MDDRC5 · MDDRC10 · iMD16 · Industrial IO HAT+ · IRIV PiControl CM4 · IRIV PiControl CM5 · IRIV IO Controller · IRIV IOC MQTT Gateway · IRIV SmartHub CM5 · IRIV EdgeAI CM5 · IRIV EdgeAI Safety Box Kit

## Notes

- Always check prices, stock and availability on the live product page at [my.cytron.io](https://my.cytron.io) before publishing them.
- This is the public edition. Internal working notes are kept privately by the Cytron marketing team.
- Maintained by Cytron Technologies marketing. Last updated 16 Oct 2026.
