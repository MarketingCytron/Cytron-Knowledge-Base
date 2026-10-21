# Milesight CT Series LoRaWAN Smart Current Transformer (CT101 / CT103 / CT303 / CT310) — Verified Reference

| | |
|---|---|
| Product code | Cytron parent code `V-LR-CT10X`. Variants: `LR-CT101` (MPN `CT101-915M`), `LR-CT103` (MPN `CT103-915M`), `LR-CT303` (MPN `CT303-915M`), `LR-CT310` (MPN `CT310-915M`) [PP]. Milesight families: CT10x (CT101, CT103, CT105) and CT3xx (CT303, CT305, CT310) [DS] |
| Family | LoRaWAN and IoT (Milesight) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: Cytron product page (all 4 variants: code, MPN, price), CT10x datasheet and CT3xx datasheet read in full, CT10x user guide (V2.0, 19 Mar 2026) and CT3xx user guide (V2.0, 19 Mar 2026) read for hardware, LED, ToolBox, installation and uplink sections |
| Primary source | Milesight *CT10x Datasheet* and *CT3xx Datasheet* (resource.milesight.com, read 2026-10-21; no version printed) [DS] |

**Authority rule (distributed product):** Manufacturer datasheet [DS] > manufacturer user guide [UM] > Cytron product page [PP] > other manufacturer pages, FAQs and release notes [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: [DS] = Milesight CT10x datasheet PDF (CT101/CT103/CT105) and CT3xx datasheet PDF (CT303/CT305/CT310). [UM] = Milesight CT10x User Guide V2.0 and CT3xx User Guide V2.0 (both 19 Mar 2026). [PP] = Cytron product page. [VEN] = milesight.com CT10x product page (download links only). Cytron sells only CT101, CT103, CT303 and CT310; CT105 and CT305 are in the datasheets but not on the Cytron page.

## What it is
- **CT101 / CT103** (CT10x): one clamp, 100 A / 250 A rated, clamp and transceiver in one body; the clamp can be detached and moved away from the transceiver on an extension cable [DS][UM].
- **CT303 / CT310** (CT3xx): one small transceiver with **three clamps** for three phases or three loads, 300 A / 1000 A rated per CT [DS][PP].
A USB-C NTC cable-temperature sensor is included for wire-temperature alarms [UM][PP]. Indoor use only, IP30 [DS][UM].

## Specifications
| Item | Value | Src |
|---|---|---|
| Detection parameter | RMS current | [DS] |
| Sampling frequency | 3.3 kHz | [DS] |
| Working frequency | 50 ~ 60 Hz | [DS] |
| Rated primary current | CT101 100 A rms; CT103 250 A rms; CT303 300 A rms per CT; CT310 1000 A rms per CT (CT105 500 A, CT305 500 A not sold by Cytron) | [DS] |
| Rated secondary current | CT101 100 mA rms; CT103 125 mA rms; CT3xx 150 mA rms | [DS] |
| Minimum reporting current (self-powered) | CT101 1.5 A (1 min interval) / 1.4 A (10 min); CT103 3 A / 2.8 A; CT303 3 A / 2.5 A; CT310 10 A / 8.5 A. Lower currents need USB power | [DS][UM] |
| Accuracy | CT10x: ±1 % (> 5 A rms), ±3 % (≤ 5 A rms). CT3xx: ±1 % | [DS] |
| Resolution | 1 mA | [DS] |
| Cable temperature sensor | 1 × NTC (USB-C), -20 °C ~ 100 °C, ±1 % | [DS] |
| Protocol | LoRaWAN®, OTAA/ABP, Class A (fixed) | [DS][UM] |
| Frequency plans (Milesight) | CN470 / IN865 / RU864 / EU868 / US915 / AU915 / KR920 / AS923-1&2&3&4 | [DS] |
| Frequency plan (Cytron) | "Support Malaysia AS923-2, Singapore AS923-1"; MPN suffix `-915M` | [PP] |
| Tx power | CT10x: 16 dBm (868) / 22 dBm (915) / 19 dBm (470). CT3xx: 16 dBm (868) / 20 dBm (915) / 19 dBm (470) | [DS] |
| Sensitivity | -137 dBm | [DS] |
| Antenna connector | 1 × 50 Ω SMA (centre pin: SMA female) | [DS] |
| Button / LED | 1 × reboot button (RST); 1 × status/alarm LED | [DS] |
| Port | 1 × USB Type-C for power supply, configuration, console or cable temperature sensor | [DS] |
| Configuration | USB Type-C (Milesight ToolBox) or LoRaWAN downlink | [DS][UM] |
| Advanced features | Threshold alarm, over-range alarm, FUOTA | [DS] |
| Power supply | 1. Induced current from the measured conductor; 2. 5 V via USB Type-C | [DS] |
| Insulation voltage | CT10x 2.5 kVac rms (1 mA / 1 min); CT3xx 3 kVac rms (1 mA / 1 min) | [DS] |
| Material | Blue, PBT+PC (UL94 V0) | [DS] |
| Cable length | 1 m (CT10x extension cable; CT3xx clamp cable) | [DS] |
| Operating temperature | Transceiver -20 °C ~ 70 °C; CT3xx clamp -40 °C ~ 55 °C | [DS] |
| Storage temperature | Transceiver -25 °C ~ 80 °C; CT3xx clamp -40 °C ~ 55 °C | [DS] |
| Humidity | ≤ 95 % non-condensing | [DS] |
| Ingress protection | IP30 | [DS] |
| Dimensions | CT101/CT103: 86.5 × 31 × 37.4 mm, wire hole Ø16 mm, 85.65 g. CT303: transceiver 38 × 34.5 × 16 mm (13.05 g), clamp 56.5 × 36.5 × 68.5 mm, wire hole Ø24.2 mm, 250 g per clamp. CT310: clamp 97.1 × 119 × 59.5 mm, wire hole Ø51 mm, 855.55 g per clamp | [DS] |
| Installation | Transceiver: cable-tie mounting; CT clamp: suspended on the conductor | [DS] |
| Approvals | CE, FCC, UL508 | [DS] |
| Reporting interval | 1 ~ 1440 min, default 10 min | [UM] |
### Product page facts (my.cytron.io, read 21 Oct 2026)
- Title "CT Series LoRaWAN Smart Current Transformer"; brand Milesight; parent code `V-LR-CT10X`; price range RM361.60 – RM1,420.65; cashback RM10.85 – RM42.62; default view "Out Of Stock / NOTIFY ME!" [PP].
- Variants: CT101 `LR-CT101` / `CT101-915M` RM361.60; CT103 `LR-CT103` / `CT103-915M` RM413.30; CT303 `LR-CT303` / `CT303-915M` RM585.50 (warranty 12 months shown); CT310 `LR-CT310` / `CT310-915M` RM1,420.65. Each variant shows "Availability: Enquiry / INQUIRE NOW" [PP].
- Capacity wording: CT101 100 A, CT103 250 A, CT303 300 A per CT, CT310 1000 A per CT [PP].
- Spec block matches [DS] except Tx power (see *Conflicts*). Frequency plan: "Support Malaysia AS923-2, Singapore AS923-1" [PP].
- **Packing list:** CT101/103 — 1 × smart current transformer, 1 × LoRaWAN antenna, 1 × cable temperature sensor, 1 × transceiver cover, 1 × extension cable. CT303/CT310 — 1 × smart current transformer, 1 × LoRaWAN antenna, 1 × cable temperature sensor [PP].
- Optional antennas: high-gain, mini stubby and magnetic [PP].
- **Resources:** CT10x and CT3xx datasheets, CT10x and CT3xx user guides (resource.milesight.com), payload decoder (github.com/Milesight-IoT/SensorDecoders), Milesight firmware & SDK download centre [PP].
- "You May Also Need": Split-core Current Transformers for CTH01, UG65 gateway [PP].

## Interfaces, terminals and pin mapping
There are no screw terminals. Connections [DS][UM]:
| Part | Function | Src |
|---|---|---|
| Split-core clamp | Clips around ONE phase conductor; closes with a "click" | [UM] |
| CT-to-transceiver socket (CT101/CT103) | Probe wiring socket; can be unplugged and replaced by the 1 m extension cable so the clamp sits apart from the transceiver | [UM] |
| CT connectors (CT3xx) | Three CT cables plug into the transceiver "without any specific order matching requirement", but at least the phase A CT must be on the phase A wire | [UM] |
| USB Type-C | 5 V power, ToolBox configuration/console, or the USB-C NTC cable temperature sensor | [DS][UM] |
| SMA (female centre pin) | LoRaWAN antenna; hand-tighten, orient vertically | [DS][UM] |
| RST button | Quick press = reboot (green LED blinks once) | [UM] |
| Cable-tie holes | Fix the transceiver | [UM] |

**LED** [UM]: green blink every 2 s = normal; green blink every 13 s = low-voltage mode (not enough induced current; stops reporting); red fast blink = current over threshold or over range, or temperature over threshold.

## Rules and gotchas (for code, wiring and tutorials)
- **Installation by a qualified person only**, following local electrical safety regulations [UM]. Installing the clamp does not need the circuit de-energized (non-invasive clamp) [DS].
- **Clamp one phase wire only. Never put phase and neutral through the same CT** — the fields cancel [UM].
- **CT3xx: the phase A CT must be on the phase A wire**, otherwise the device has no power (it is powered from phase A only) [DS][UM].
- **Below the minimum reporting current the device does not report** (low-voltage mode, green blink every 13 s). For light loads, power it from USB-C 5 V [DS][UM]. If current is above the minimum but it still enters low-voltage mode, the conductor is faulty or unpowered [UM].
- **Energy (kWh) is calculated, not measured:** Energy = kAh × voltage × power factor, with voltage (0–600 V) and PF (0–1) typed into ToolBox; both default to 1 if left unset [UM]. There is no voltage sensing.
- **The over-range alarm is always on** (5 min interval, 3 reports, fixed) [UM].
- **Payload** (application port 85 default): CT10x current = channel 04 type 98, UINT16/100 A; total current 03 97 UINT32/100 Ah; temperature 09 67 INT16/10 °C; energy 10 99 UINT32/100 kWh. CT3xx per-phase: totals 03/05/07 type 97 (Ah), currents 04/06/08 type 99 **UINT16/10 A**, energy 10/11/12 type 99 (kWh). Use the official decoder from github.com/Milesight-IoT/SensorDecoders [UM].
- **Frequency plan must match the gateway.** For AS923, choose the sub-plan (Malaysia: AS923-2 per Cytron) in ToolBox [UM][PP].
- **CT secondary:** the clamps plug into the transceiver (CT101/CT103 via a wiring socket or the extension cable; CT3xx via three CT connectors). Neither Milesight document says whether a clamp may be unplugged while it is around a live conductor. Plug and unplug only with the clamp off the conductor (general CT practice, inferred — see *Needs verification*).

## Power and electrical limits
- Self-powered by induced current from the measured conductor, or 5 V on USB-C [DS].
- Rated primary current: 100 A (CT101), 250 A (CT103), 300 A per CT (CT303), 1000 A per CT (CT310) [DS]. Do not exceed the rated capacity [UM].
- Insulation: 2.5 kVac rms (CT10x), 3 kVac rms (CT3xx), 1 mA / 1 min [DS]. These are insulation test values; no voltage category (CAT rating) is stated.
- Working frequency 50–60 Hz [DS].
- Environment: transceiver -20 ~ 70 °C; CT3xx clamp -40 ~ 55 °C; ≤ 95 % RH; IP30, indoor only [DS][UM].

## Software support
- **Milesight ToolBox** over USB-C: LoRaWAN settings (frequency/channels, OTAA/ABP, LoRaWAN V1.0.2/V1.0.3, ADR, confirmed mode, RX2, SF, Tx power), reporting interval, cumulative data type (kAh or kWh), thresholds, firmware upgrade, JSON config template backup, reset [UM].
- Downlink commands for general and threshold settings [UM].
- Works with standard LoRaWAN gateways and network servers and the Milesight Development Platform (OTAA required there) [DS][UM].
- Payload decoders: https://github.com/Milesight-IoT/SensorDecoders [UM][PP].

## Compatibility and accessories
- Needs a LoRaWAN gateway on the same plan, e.g. `milesight-ug65.md`, `milesight-ug56.md` or `milesight-ug67.md`. With a Milesight gateway on US915/AU915/CN470 defaults, set channel index 8-15 [UM].
- In the box: antenna, USB-C NTC cable-temperature sensor; CT101/103 also get a transceiver cover and 1 m extension cable [PP][UM]. The user guide also lists a warranty card and quick guide [UM].
- Antenna options: mini stubby (50 mm), stubby (108 mm), magnetic; only one type is standard [DS].
- For a hub that takes several separate CT clamps and RS485, see `milesight-cth01.md` with `milesight-cth01-ct-clamps.md`.

## Common mistakes / troubleshooting
- **No data from a lightly loaded circuit:** below the minimum reporting current → low-voltage mode. Power via USB-C [DS][UM].
- **CT3xx dead:** no CT on phase A [UM].
- **Reading near zero:** phase and neutral both inside the clamp [UM].
- **Clamp not closed:** close until it clicks [UM].
- **No join:** frequency plan / AS923 sub-band differs from the gateway; antenna not fitted [UM].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Tx power at 915 MHz (CT303/CT310) | [PP] "22 dBm (915 MHz)" for the whole page | [DS] CT3xx: 20 dBm (915 MHz); CT10x: 22 dBm | [DS] wins: 22 dBm CT101/CT103, 20 dBm CT303/CT310 |
| Frequency plans | [PP] "Support Malaysia AS923-2, Singapore AS923-1" | [DS] lists all plans (CN470 … AS923-1&2&3&4) for the model family | Not a contradiction: Cytron sells the `-915M` hardware and names the plans for MY/SG. Exact plan list of the 915M hardware is in *Needs verification* |
| Minimum reporting current | [PP] not stated | [DS] V2.0 values (e.g. CT101 1.5 A at 1 min) | [DS] |

## Needs verification
- Exact list of plans supported by the `-915M` hardware variant (inferred to cover the 915 MHz family including AS923; Milesight's datasheet lists plans for the model family only).
- Whether the CT303 / CT310 box contains three clamps (the datasheet gives "per CT clamp" figures and three-phase detection; Cytron's packing list says "1 x Smart Current Transformer").
- Whether the CT101/CT103 clamp may be disconnected from the transceiver while on a live conductor (no "do not open the secondary" statement found in either document).
- Measurement category / maximum conductor voltage (only insulation test voltages are stated).
- Warranty for CT101/CT103/CT310 (Cytron shows 12 months only on CT303).

## Sources
- [DS] CT10x Datasheet: https://resource.milesight.com/milesight/iot/document/ct10x-datasheet-en.pdf (read 2026-10-21).
- [DS] CT3xx Datasheet: https://resource.milesight.com/milesight/iot/document/ct3xx-datasheet-en.pdf (read 2026-10-21).
- [UM] CT10x User Guide V2.0 (19 Mar 2026): https://resource.milesight.com/milesight/iot/document/ct10x-user-guide-en.pdf
- [UM] CT3xx User Guide V2.0 (19 Mar 2026): https://resource.milesight.com/milesight/iot/document/ct3xx-user-guide-en.pdf
- [VEN] Milesight CT10x product page: https://www.milesight.com/iot/product/lorawan-sensor/ct10x
- [PP] Cytron product page: https://my.cytron.io/Milesight/p-ct10x-smart-current-transformer (read 2026-10-21).
- [VEN] Payload decoders: https://github.com/Milesight-IoT/SensorDecoders
