# Milesight WS101 LoRaWAN Smart Button — Verified Reference

| | |
|---|---|
| Product code | `WS101` (Milesight model). Cytron code `LR-WS101`; no MPN shown [PP][DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (description, features, specifications, packing list, resources), Milesight WS101 datasheet PDF (3 pages, read in full) and WS101 User Guide V1.2 (Nov 30, 2022; packing list, LED table, quick start, button modes, LoRaWAN and general settings, D2D, installation, battery, payload read) |
| Primary source | Milesight *WS101 Datasheet* (PDF, no version or date printed), https://resource.milesight.com/milesight/iot/document/ws101-datasheet-en.pdf [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is

## Specifications
| Item | Value | Src |
|---|---|---|
| Technology | LoRaWAN, Milesight D2D; internal antenna | [DS] |
| Frequency plans (model) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1, -2, -3, -4 | [DS] |
| Tx power | 16 dBm (868 MHz) / 22 dBm (915 MHz) / 19 dBm (470 MHz) | [DS] |
| Sensitivity | -137 dBm @ 300 bps | [DS] |
| Mode | OTAA / ABP Class A; LoRaWAN V1.0.2 / V1.0.3 / V1.1; application port default 85 | [DS][UM] |
| Range | 15 km line of sight | [DS] |
| Button | 1 × external press button, Ø20 mm; modes: short press (≤ 3 s), long press (> 3 s), double press (within 3 s; can be disabled) | [DS][UM] |
| Other | 1 × internal reset button; 1 × status/alarm LED; 1 × buzzer | [DS] |
| Configuration | Mobile app via NFC (card emulation supported) or downlink | [DS] |
| Advanced | Milesight D2D controller | [DS] |
| Power supply | 1 × 1650 mAh ER14335 Li-SOCl₂ | [DS] |
| Battery life (1080 min report interval, 10 presses/day, 25 °C, lab) | ~9.5 years (SF7, EU868); ~7.7 years (SF10, EU868); ~9.3 years (SF7, US915); ~7.1 years (SF10, US915) | [DS] |
| Reporting interval | Battery level every 1080 min by default (1–1080); button uplinks on each press; low-battery uplink once at 1 % | [UM] |
| Operating temperature | -20 °C to +60 °C | [DS] |
| Humidity | ≤ 90 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Housing / colour | Anti-flaming polycarbonate; white body, button white (Scene) or red (SOS) | [DS] |
| Weight | 38.8 g with battery | [DS] |
| Dimensions | 50 × 50 × 18 mm | [DS] |
| Installation | Flat surfaces with screws or 3M tape; lanyard | [DS] |
| Regulatory | CE, FCC, LoRaWAN Certified; RoHS | [DS] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "WS101 LoRaWAN Smart Button"; brand Milesight; Code `LR-WS101`; warranty 12 months; RM206.65; Availability: Enquiry [PP].
- **Frequency plan:** "Support Malaysia AS923-2, Singapore AS923-1" [PP]. No MPN or button-colour option shown.
- Spec list matches [DS] (Tx 16/22/19 dBm, -137 dBm, Class A, external + internal reset button, LED, buzzer, NFC, 1 × 1650 mAh ER14335, -20 to +60 °C, ≤ 90 % RH, IP30, 50 × 50 × 18 mm, Ø20 mm button, white with white/red button option, screws/3M tape/lanyard) [PP].
- Battery wording: "over 5 years (1080 min interval + 10 presses per day)" — conservative versus [DS] [PP].
- Range wording: 15 km rural / 2 km urban; Milesight IoT Cloud compatible [PP].
- **Packing list:** "1 x WS101 LoRaWAN Smart Button" [PP]. The [UM] lists device, 2 wall mounting kits, quick guide, warranty card. No lanyard is listed by either.
- **Resources:** WS101 datasheet, WS101 user guide, payload decoder (GitHub `Milesight-IoT/SensorDecoders`), firmware & SDK download [PP].

## Interfaces, terminals and pin mapping
No wired interfaces [DS].
| Event / action | LED | Src |
|---|---|---|
| Power on (pull the battery insulating sheet) | Green for 3 s | [UM] |
| Join request / joined | Red blinks once / green blinks twice | [UM] |
| Hold internal reset > 3 s | Reboot (slow blink) | [UM] |
| Hold > 10 s | Factory reset (quick blink) | [UM] |
The buzzer sounds together with the LED on presses once the device has joined the network; LED and buzzer can each be disabled (the reset LED cannot) [UM].

## Rules and gotchas (for code, wiring and tutorials)
- **Not a certified emergency system.** Milesight: convenient call/control only, not the sole emergency response tool [DS][UM].
- **LoRaWAN:** a default AppKey is set at the factory (see the user guide; not copied); OTAA is required for Milesight IoT Cloud / Development Platform; set the same plan as the gateway (Cytron: AS923-2 Malaysia); for US915/AU915 with Milesight gateway defaults use channel index 8-15 [UM][PP]. Pair with `milesight-ug65.md` / `milesight-ug56.md`.
- **Button payload:** `ff 2e` + `01` short / `02` long / `03` double press; battery `01 75` (%) [UM].
- **Downlinks (port 85):** reboot `ff10ff`; report interval `ff03` (s); LED `ff2f` 00/01; double-press mode `ff74` 00/01; buzzer `ff3e` 00/01 [UM].
- **D2D:** set RX2 data rate/frequency, a D2D key matching the agent, and a 2-byte command per press mode; enable "LoRa Uplink" if the gateway should also receive the press [UM]. Agents include Milesight switches/controllers such as `milesight-ws50x.md`, `milesight-ws558-ln.md` (inferred from the D2D controller role).
- **Double press** is a separate mode; disabling it also hides its D2D settings [UM].

## Power and electrical limits
- 1 × ER14335 Li-SOCl₂ 1650 mAh only — **not alkaline**; observe polarity; open the back cover with a screwdriver; remove the cell for long storage [UM].
- ~7.1–9.5 years at 1080-min interval and 10 presses/day (lab) [DS].
- -20 to +60 °C, ≤ 90 % RH, IP30 — indoor [DS].

## Software support
- Milesight IoT Cloud and Milesight Development Platform [DS].
- Decoders: GitHub `Milesight-IoT/SensorDecoders` [UM][PP].

## Compatibility and accessories
- LoRaWAN gateway on the same plan: `milesight-ug65.md`, `milesight-ug56.md`, `milesight-ug67.md` [PP].
- Lanyard mounting uses the hole near the edge; a lanyard is not listed in either packing list [UM][PP].
- Related: `milesight-ws301.md` (door contact), `milesight-ws202.md` (PIR).

## Common mistakes / troubleshooting
- **No LED at first:** remove the battery insulating sheet [UM].
- **No buzzer on press:** the buzzer only works once joined; check it is enabled [UM].
- **Long press read as short:** long press must exceed 3 s [UM].
- **Join fails (red blink):** plan, channels and keys must match the network server [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Battery life | [DS] ~7.1–9.5 years (1080 min + 10 presses/day) | [PP] "over 5 years" | [DS] wins; [PP] is conservative, not contradictory |
| Packing list | [UM] device, 2 wall mounting kits, quick guide, warranty card | [PP] device only | [UM] for contents; confirm with Cytron |
| Button colour | [DS] white Scene Button or red SOS Button versions | [PP] "White (Button: White/Red Optional)", no option to choose | Unresolved which colour Cytron ships |

## Needs verification
- Which button colour (white Scene / red SOS) and frequency build Cytron ships (no MPN shown).
- Datasheet version/date (none printed).
- Content of Milesight's "Disclaimer and Important Information" PDF (not opened).

## Sources
- [DS] Milesight WS101 Datasheet: https://resource.milesight.com/milesight/iot/document/ws101-datasheet-en.pdf (read 2026-10-21).
- [UM] Milesight WS101 User Guide V1.2 (Nov 30, 2022): https://resource.milesight.com/milesight/iot/document/ws101-user-guide-en.pdf (read 2026-10-21).
- [VEN] Milesight WS101 page: https://www.milesight.com/iot/product/lorawan-sensor/ws101; disclaimer PDF: https://resource.milesight.com/milesight/iot/document/ws101-disclaimer-and-important-information-en.pdf (not opened).
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ws101-lorawan-smart-button (read 2026-10-21).
