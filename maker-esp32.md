# Maker ESP32 — Verified Reference

| | |
|---|---|
| Product code | `MAKER-ESP32` (tuck box `BOX-MAKER-ESP32`) |
| Family | Maker ESP32 family (ESP32 ecosystem) — flagship |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-16 |
| Primary source | Maker ESP32 Datasheet **Rev 1.1** (Sept 2026): (Cytron document — link not public) |

Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.


## What it is
An ESP32 development board on the ESP32-WROOM-32E-N8 module, in the NodeMCU ESP32 30-pin layout, with learning aids built in: 14 GPIO LEDs, RX/TX LEDs, a user button, a passive buzzer with mute switch, USB-C and an I2C Maker Port [DS][PP]. It is the drop-in upgrade for the NodeMCU ESP32 that Cytron sold before it: same pins, so existing NodeMCU ESP32 code and wiring keep working [PP]. Target audience: tertiary students and makers .

## Board facts
| Item | Value | Src |
|---|---|---|
| Module | ESP32-WROOM-32E-N8: 8 MB flash, no PSRAM | [DS] |
| CPU / RAM | Dual-core Xtensa LX6 up to 240 MHz, 520 KB SRAM | [PP] |
| Radio | Wi-Fi 802.11 b/g/n 2.4 GHz, Bluetooth 4.2 + BLE | [PP] |
| Module approval | ESP32-WROOM-32E type-approved by SIRIM under Cytron Technologies | [PP launch page] |
| USB | USB-C: 5 V power, upload and serial | [DS] |
| USB-UART | WCH **CH9102F**. Windows driver if needed: WCH CH343SER | [DT 2026-09-28] |
| Upload | Automatic — no need to hold BOOT | [PP launch page] |
| Power in | USB-C 5 V, or VIN pin 4.6–5.5 V | [DS] |
| 3V3 rail | LDO, **700 mA max**, shared by module, LEDs, buzzer, Maker Port and USB-UART | [DS Rev 1.1] |
| Logic levels | VIH 2.5–3.6 V, VIL -0.3–0.8 V, VOH 2.6–3.3 V, VOL 0–0.4 V; analog in 0–3.3 V | [DS] |
| GPIO current | Source 40 mA, sink 28 mA (absolute max); internal pull-up / pull-down 45 kΩ | [DS] |
| Operating temp | **-10 to 70 °C** | [DS Rev 1.1] |
| Size | 58 × 28.4 mm (PCB 51.7 mm) | [DS] |
| Buttons | BOOT, EN (reset), USER (GPIO4) | [DS] |
| Indicator LEDs | 3V3 power LED, RX/TX LEDs, 14 GPIO LEDs | [DS] |
| In the box | Board + Getting Started card with QR code to the tutorial | [PP launch page] |

## Onboard peripherals and pins
| Function | GPIO / pin | Notes | Src |
|---|---|---|---|
| GPIO LEDs (14, active HIGH) | 2, 12, 13, 16, 17, 18, 19, 21, 22, 23, 25, 27, 32, 33 | LED lights whenever the pin is HIGH | [DS] |
| LED bar order (official examples) | 32, 33, 25, 27, 12, 13, 23, 22, 21, 19, 18, 17, 16, 2 | Use this order for "fill" / chase effects | [GH] |
| User button | GPIO4 | | [DS] |
| Piezo buzzer (passive) | GPIO26 | Mute switch: **Up = ON, Down = muted** | [DS][DT] |
| Maker Port (JST-SH 4-pin) | GND, 3V3, SDA = GPIO21, SCL = GPIO22 | Qwiic / STEMMA QT direct; Grove via conversion cable | [DS] |
| USB serial | GPIO1 (TX), GPIO3 (RX) | | [VEN] |
| BOOT button | GPIO0 | **GPIO0 is not on the header** | [DS] |

**Header** [DS]
- Top row: 23, 22, TX(1), RX(3), 21, 19, 18, 5, 17, 16, 4, 2, 15, GND, 3V3
- Bottom row: EN, VP(36), VN(39), 34, 35, 32, 33, 25, 26, 27, 14, 12, 13, GND, VIN

## Pin rules and gotchas (for code and tutorials)
- **Input-only:** 34, 35, 36, 39 — no internal pull resistors [VEN].
- **Never use:** 6–11 (internal flash; not broken out) [VEN].
- **Strapping pins:** 0, 2, 5, 12, 15. GPIO12 must not be pulled HIGH at boot [VEN].
- **GPIO1/3** carry USB serial — avoid them [VEN].
- **ADC2 does not work while Wi-Fi is on** (pins 2, 4, 12–15, 25–27). Any Wi-Fi project with an analog sensor uses ADC1: 32, 33, 34, 35, 36, 39 [VEN].
- **GPIO26 = buzzer.** Never use it for SPI CS or data (e.g. dot-matrix CS moved 26 → 17) — or tell the reader to mute (switch Down) [DS].
- **GPIO4 = user button.** Avoid it for external devices unless you want the button [DS].
- **LED pins:** harmless, but expect I2C on 21/22 to flicker those LEDs [DS].
- **Free pins with no onboard load:** 14 (fully free); 5 and 15 (strapping — fine as outputs / SPI CS, don't hold at a fixed level during boot); input-only 34–39 [DS][VEN].
- 5 V sensors must not drive GPIO directly. Relays, motors and solenoids need a driver [DS].

## Power and electrical limits
- One power source at a time. USB-C + VIN together is protected (safe) but not recommended; external VIN must stay within 4.6–5.5 V [DT].
- On USB power the **VIN pin outputs 5 V** (from USB, not from the LDO), so it can power 5 V modules [DT].
- 3V3 budget is 700 mA **including** onboard loads — check before adding displays, servos on 3V3 or many modules [DS].

## Software support
- **Arduino IDE:** "esp32 by Espressif Systems" package; board **ESP32 Dev Module** [GH].
- Official examples use the **ESP32 Arduino core 3.x** API (`ledcAttach()`). Core 2.x `ledcSetup()` / `ledcAttachPin()` will not compile on 3.x [GH][VEN].
- Official examples: `Out_of_the_box_Demo_Code`, `LEDs_Fade`, `LEDs_Fill_Button`, `Buzzer_Melody` [GH].
- **ESP-IDF** supported [PP launch page]. No manual driver install normally needed [PP launch page].

## Compatibility and accessories
- NodeMCU ESP32 form factor: fits **Robo ESP32** and the **Expansion Board for ESP32** (`BB-NMCU-BASE`) [PP].
- On Robo ESP32 these pins clash (derived from both datasheets — see `robo-esp32.md`): GPIO4 (Maker button = Robo servo D4), GPIO26 (Maker buzzer = Robo Grove 3), GPIO23 (Robo buzzer = a Maker LED). Maker LEDs on 12/13/27/18/19 flicker with motor PWM / servo pulses (harmless).
- Bundles: Maker ESP32 + Expansion Board; "NodeMCU ESP32 Only" still sold as a bundle option [PP].

## Common mistakes in older tutorials / migration notes
- **NodeMCU ESP32 → Maker ESP32 revamp checklist** (NodeMCU ESP32 is not a Cytron-brand product, so it has no file of its own here):
  1. Board name, photos and product link → Maker ESP32 (`MAKER-ESP32`). Cable: micro-USB → USB-C. Driver step: drop CP210x.
  2. Arduino board stays `ESP32 Dev Module`. Pin numbers and header positions are the same, so wiring diagrams stay valid.
  3. GPIO26 used for anything (SPI CS, servo, sensor)? It is now the buzzer — move it (e.g. 26 → 17) or tell the reader to mute (switch Down).
  4. GPIO4 used for an external device? It is now the user button — move it, or use the button on purpose.
  5. Pins 2, 12, 13, 16–19, 21–23, 25, 27, 32, 33 now each drive an LED — harmless; mention the flicker on I2C 21/22.
  6. A wired external button, buzzer or LED can often be replaced by the onboard button (GPIO4), buzzer (GPIO26) or LEDs.
  7. Remove "hold BOOT to upload" steps — upload is automatic.
  8. Check power claims against the 700 mA 3V3 budget.
  9. Move core 2.x `ledcSetup` / `ledcAttachPin` to core 3.x `ledcAttach`.
- **NodeMCU-32S is a different board** (ESP32-S module, CH340, 38 pins, discontinued). Tutorials written for it need a full wiring re-check, not a board-name swap.
- Remove "hold BOOT to upload", "install CP210x", "Micro USB cable", "4 MB flash" from revamped tutorials.
- Any sketch with pins 4 or 26 wired to external parts must be re-pinned.

## Positioning (for marketing and scripts)
- Datasheet tagline: "Simplifying Digital Making." Launch headline: "The ESP32 you know. Easier to learn, better to build with." [DS][PP]
- Three pillars: **Start Faster** (USB-C, one-click upload), **Understand Better** (14 GPIO LEDs + RX/TX), **Build Further** (8 MB flash, Wi-Fi/BT, Maker Port) [PP].
- Comparison vs NodeMCU ESP32: 8 MB vs 4 MB flash, USB-C vs Micro USB, 14 GPIO LEDs vs 1, plus RX/TX LEDs, buzzer, user button, Maker Port [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| 3V3 max current | Rev 1.0: 1.35 A | Rev 1.1: 700 mA | Rev 1.1 wins: **700 mA** |
| GPIO output current | Product page: 40 mA max per pin | Datasheet: 40 mA source / 28 mA sink | Datasheet wins (state both) |
| GPIO4 | Old AI Coding Pack text: strapping pin | Espressif: not a strapping pin | Fixed in pack 2026-09-28 |
| LED list | Old pack `source-audit.md`: 20 pins | Datasheet: 14 pins | Datasheet wins |

## Needs verification
- None for board-level facts (all open items closed by the design team on 2026-09-28).
- RRP and store list change over time — re-check the live product page before quoting in public content.

## Sources
- [DS] Maker ESP32 Datasheet Rev 1.1 (Sept 2026) — (Cytron document — link not public)
- [DT] Cytron design team confirmations, 2026-09-28 (CH9102F, VIN 5 V out, mute switch, dual power) — recorded in `claude/maker-esp32-reference.md`
- [PP] https://my.cytron.io/p-maker-esp32 · launch page https://my.cytron.io/maker-esp32
- [GH] https://github.com/CytronTechnologies/Cytron-Maker-ESP32
- [VEN] https://docs.espressif.com/projects/esp-idf/en/stable/esp32/api-reference/peripherals/gpio.html
