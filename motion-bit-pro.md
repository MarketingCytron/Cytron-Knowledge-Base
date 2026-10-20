# MOTION:BIT Pro — Verified Reference

| | |
|---|---|
| Product code | `MOTION-BIT-PRO` (Cytron datasheet PDF file title "MOTION-BIT-PRO Datasheet.pdf" [DS]). Switch Science lists "CYTRON-MOTION-BIT-PRO" [3P]. my.cytron.io page: p-motion-bit-pro-12v-robotics-expansion-board-for-micro-bit [PP] |
| Family | micro:bit accessories |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 1): live my.cytron.io product page read plus Cytron images including the MOTION:BIT vs MOTION:BIT Pro comparison table. Power source (external Vin only — no micro USB, no battery), current ratings, servo power selection, counts and package are now Cytron-stated |
| Primary source | MOTION:BIT Pro — "Simplifying Motion Control with micro:bit" — Datasheet **Rev 1.0, April 2024** (public PDF on Google Drive): https://drive.google.com/file/d/17kkl6oBU0n-gQtyQ84ylxg2KX3E9Ma0_/view |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

Tag notes: MOTION:BIT Pro **is a separate product with its own Cytron datasheet**. The datasheet PDF was read in full via Drive and cross-checked against the RobotShop mirror (same title, Rev 1.0, April 2024). The link is **public** (linked from The Pi Hut and Switch Science product pages; mirrored on cdn.robotshop.com). No separate user manual found. The Cytron product page URL was not found and www.cytron.io pages could not be fetched. Much of the Pro datasheet text is reused from the MOTION:BIT datasheet — see *Conflicts*. [GH] = CytronTechnologies/pxt-motionbit, which the Pro datasheet names as its MakeCode extension; the [GH] code itself is written for MOTION:BIT. No [DT] confirmation exists yet.

## What it is
A higher-voltage version of MOTION:BIT: a robotics / motion-control expansion board for the BBC micro:bit, powered from an external **7–12 V** input, with motor terminals rated **3 A continuous / 5 A peak (< 5 s)**, 8 RC servo ports with a jumper to choose servo power (internal 5 V buck converter or VIN), a **3 A** 5 V output, a colour-coded GVS breakout of 11 micro:bit I/O with status LEDs, JST-SH Maker Ports, WS2812B RGB LEDs on P8 and motor test buttons [DS]. It is programmed with the same **MOTION:BIT** MakeCode extension [DS]. Unlike MOTION:BIT, the datasheet lists **no 18650 battery holder** [DS].

## Specifications
Datasheet Table 2 is titled **"MOTION:BIT Pro Absolute Maximum Ratings"** — absolute limits, not recommended operating points [DS].

| Item | Value | Src |
|---|---|---|
| Power input voltage (absolute max) | Min 6 V, Max 16 V | [DS Table 2] |
| Power input terminal (board function) | "Terminal for external 7V - 12V power input. Can be used for external LiPo or 4x AA batteries." | [DS Table 1] |
| Analog input voltage | Min 0 V, Max 3.3 V | [DS] |
| Total +3V3 output current (GPIO Breakout & Grove Ports) | Max 200 mA | [DS] |
| Total +5V output current | Max 3 A | [DS] |
| Maximum DC motor current, continuous | Max 3 A (per channel or total not stated) | [DS] |
| Maximum DC motor current, peak (< 5 seconds) | Max 5 A | [DS] |
| Motor control | "Add MOTION:BIT Extension in MakeCode Editor to control the DC Motors and Servo Motors"; the extension exposes M1–M4 | [DS] / [GH] |
| Servo ports | "Connectors for 8x RC servo motors" | [DS] |
| Servo Power Selection | Header pin jumper selects power for servo pins **VCC1 and VCC2**: 5V (internal buck converter) or directly from VIN (7V - 12V). "If selecting VIN make sure your servo voltage rating is compatible with voltage input VIN, else it might damage your servo." | [DS] |
| RGB LEDs | User-programmable WS2812B, connected to P8 | [DS] |
| External RGB LED | For external WS2812B, daisy-chained (Dout of RGB LED 1) | [DS] |
| GPIO breakout | Colour-coded GVS, 3.3 V power per GPIO: P0, P1, P2, Button A, Button B, P9, P12, P13, P14, P15, P16 | [DS] |
| GPIO status LEDs | On when the IO state is high | [DS] |
| Maker Ports | JST-SH 4-way; Qwiic, STEMMA QT, Grove (via conversion cable); "These pins are available on Maker Ports: P0-P9, P1-P2, P2-P12" (printed as-is) | [DS] |
| Maker Port (I2C) | JST-SH 4-way; "for I2C modules only" | [DS] |
| I2C breakout | "Breakout of micro:bit I2C pins" | [DS] |
| 5V Supply | 5V output for external sensors/modules | [DS] |
| Micro USB | **None on the Pro** — the product-page feature list and Cytron comparison table give external Vin as the only power source [PP][PP: img]. The datasheet row "for charging the battery or power up the Motion:Bit" is copied from MOTION:BIT (see Conflicts) | [PP][DS] |
| Power / Charge LED | Power: on when powered. Charge: on while charging, off when full (see Conflicts) | [DS] |
| On/Off switch + Ext. On/Off switch header | External switch works only with onboard switch Off | [DS] |
| Motor test buttons | Motor runs at full speed | [DS] |
| Motor status LEDs | On when the motor is running | [DS] |
| Motor terminals | Motor voltage at full speed = power source voltage; swapping MA & MB reverses direction | [DS] |
| Battery holder | **None listed** in Table 1 | [DS] |
| Motor driver IC | **Not stated** | [DS] |
| Buzzer / speaker | **Not stated** | [DS] |
| Dimensions | Figure 2 drawing only, no values in the text | [DS] |
| Protections (reverse polarity, over-current, thermal) | **Not stated** | [DS] |
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Features list:** 11 GPIO status LEDs; 11 GPIO breakout; 3 Maker Ports (JST-SH 4-way) + 1 I2C Maker Port; I2C breakout; vertical micro:bit socket; 4 motor terminals; 8 motor test buttons; 8 motor status LEDs; 8 servo ports; 2 servo power selectors; 2 RGB LEDs + external RGB LED; **12 V power input terminal block**; 6x 5V supply; on/off switch + external on/off switch; power/charge LED. **No micro USB and no 18650 holder** are listed [PP].
- **Comparison image (Cytron, Pro column):** power source **external Vin only**; Vin 7–12 V; 4 DC channels; max DC motor current **3 A continuous, 5 A peak**; USB Li-ion charging: no; Li-ion protection circuit: no; slide switch with MOSFET shock-proof circuit; external on/off: yes; 6x 5V pins, **total 5 V output 3 A**; 8 servo channels, **servo power selectable 5 V or Vin**, total servo current 3 A; 2 RGB LEDs + external RGB expansion; 11 GPIO status LEDs; 3 Maker Ports (JST-SH 1 mm) + 11 GVS headers; I2C: 1 Maker Port + 1 4-pin header; official MakeCode extension MOTION:BIT; same form factor as MOTION:BIT [PP: img].
- Image: "4-channel DC motor driver that controls up to 4x 7V–12V DC motors"; "8x servo motor ports — selectable power between the 5V and VIN … 12V high torque servo motors" [PP: img].
- **Packing:** 1x MOTION:BIT Pro, 1x tiny Phillips screwdriver, 3x Grove to JST-SH (Qwiic) cable, 4x silicone bumper, 4x building-block pin with friction ridges [PP].
- Resources: Getting Started with MOTION:BIT Pro (tutorial), datasheet (Drive PDF), pxt-motionbit extension, 3D CAD [PP].

## Interfaces, terminals and pin mapping
| micro:bit pin | Used for | Src |
|---|---|---|
| P19 (SCL) / P20 (SDA) | micro:bit I2C pins: I2C breakout and Maker Port (I2C). The shared extension drives motors/servos through a PCA9685 at 0x40 over I2C — **assumed** to apply to Pro (code written for MOTION:BIT) | [DS] + [VEN] + [GH] |
| P8 | Onboard WS2812B RGB LEDs + external chain | [DS] |
| P0, P1, P2, P9, P12, P13, P14, P15, P16, Button A (P5), Button B (P11) | GVS breakout with status LEDs, 3.3 V per pin | [DS] / pin numbers [VEN] |
| P0/P9, P1/P2, P2/P12 | Maker Ports, as printed — exact pairing unclear | [DS] |
| Servo power pins VCC1, VCC2 | Selected by jumper: 5V buck or VIN | [DS] |
| Motor terminal MA / MB | Swapping reverses direction (Figure 3: Connection Diagram for Brushed DC Motor) | [DS] |

Extension channel names (from [GH]): motors M1–M4; servos S1–S8 (block "all" also available).

## Rules and gotchas (for code, wiring and tutorials)
- Use the **same MakeCode extension as MOTION:BIT** — search "motionbit" in MakeCode Extensions [DS][GH]. There is no separate "Pro" extension.
- **Servo power jumper:** VIN (7–12 V) goes straight to servos on that rail — most hobby servos are not rated for 12 V. Use the 5V setting unless the servo is rated for VIN [DS].
- Motor full-speed voltage **equals the supply voltage** — choose motors rated for 7–12 V input used [DS].
- Insert the micro:bit with **LEDs facing out** [DS].
- The Pro has **no micro USB and no battery** — power it from the 7–12 V terminal block; program via the micro:bit's own USB [PP][PP: img].
- External On/Off switch needs the onboard switch **Off** [DS].
- Motor test buttons run the motor at **full speed** [DS].
- **P8** is used by the RGB LEDs [DS].
- Don't describe the Pro as battery-powered from an onboard 18650 — no battery holder is listed [DS].
- Quote 7–12 V as the input range in content; 6–16 V is the absolute-maximum rating, not an operating range [DS].

## Power and electrical limits
- External input terminal **7–12 V** (LiPo or 4x AA suggested); absolute maximum **6–16 V** [DS].
- DC motor **3 A continuous, 5 A peak (< 5 s)** [DS]; per channel vs total not stated.
- **+5V output 3 A total** (internal buck converter) [DS]; **+3V3 200 mA total** for GPIO breakout and Grove/Maker ports [DS].
- Servo rail: 5V (buck) or VIN by jumper [DS].
- Analog inputs 0–3.3 V [DS].
- Reverse-polarity, over-current and thermal protection: **not stated**.

## Software support
- **MakeCode:** "Add MOTION:BIT Extension in MakeCode Editor to control the DC Motors and Servo Motors" [DS]; datasheet links https://makecode.microbit.org/pkg/CytronTechnologies/pxt-motionbit [DS].
- Extension `pxt-motionbit` v1.2.0, block category "MOTION:BIT" (DC Motors, Servos, RGB LED, External RGB LED) [GH]. Install: MakeCode → Extensions → search "motionbit" or https://github.com/cytrontechnologies/pxt-motionbit [GH].
- **Python:** not stated by Cytron; resellers mention MakeCode JavaScript/Python text modes [3P] — Needs verification.

## Compatibility and accessories
- micro:bit version support is **not stated in the Pro datasheet**; the shared extension README says MOTION:BIT works with V1 & V2 [GH]; The Pi Hut says Pro works with V1 and V2 [3P].
- Maker Ports: Qwiic, STEMMA QT, Grove (via conversion cable) [DS].
- External WS2812B RGB LEDs [DS].
- Smaller sibling: **MOTION:BIT** (3.6–6 V, 18650 holder, 1 A / 1.5 A) — see `motion-bit.md`.

## Common mistakes / troubleshooting
- **Servo burnt / hot** → servo jumper on VIN with a 5–6 V servo; move jumper to 5V [DS].
- **Nothing powers up from USB** → the Pro is described by resellers as external-VIN only [3P]; use the 7–12 V terminal (see Conflicts).
- **Motors don't move but micro:bit runs** → board switch Off; turn it on [GH behaviour].
- **Motor runs the wrong way** → swap MA & MB [DS].
- **External switch does nothing** → onboard switch must be Off [DS].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| Input voltage | [DS Table 1] 7V - 12V (power input terminal) | [DS Table 2] 6 – 16 V absolute maximum | Not a contradiction: use 7–12 V as operating range, 6–16 V as abs max |
| Servo V+ | [DS] Servos Port row: "V+ voltage is equal to power source voltage" | [DS] Servo Power Selection: jumper selects 5V buck or VIN | Jumper row is Pro-specific; the Servos Port row appears copied from MOTION:BIT. Text uses the jumper. Confirm with [DT] |
| Battery / micro USB charging | [DS] Micro USB "for charging the battery or power up the Motion:Bit"; Charge LED | [DS] no battery holder in Table 1; [3P] Switch Science: "External VIN only", no USB Li-ion charging or battery protection circuit; [3P] The Pi Hut on-board list has no micro USB | Unresolved — don't claim USB power/charging for Pro. Ask [DT] |
| Motor channel count | [DS] not stated | [3P] 4 channels (The Pi Hut, Switch Science); [GH] extension M1–M4 | Content may say the extension controls M1–M4; physical count Needs verification |
| Datasheet link label | [DS] Drive PDF is the Pro datasheet | [3P] Switch Science labels the same link "MOTION:BIT" datasheet | Document title is "MOTION:BIT Pro" — use it for Pro |

## Needs verification
- micro:bit V1 & V2 support for Pro ([3P] only).
- Whether Pro uses the same PCA9685 at I2C 0x40 (assumed from the shared extension).
- Maker Ports pin pairing ("P0-P9, P1-P2, P2-P12" lists P2 twice).
- Whether 3 A / 5 A is per channel or total (comparison image does not say); dimensions in mm (same form factor as MOTION:BIT, 95.2 × 57.2 mm, implied but not stated for Pro); motor driver IC; protections.
- Datasheet micro USB row ("for charging the battery or power up") — conflicts with the product page; ask Cytron to correct the datasheet.

## Cytron tutorials
Add-on: Cytron tutorials that use this product, most-read first. Use them for wiring examples and project ideas; they never override [DS] or [UM] specs, and tutorial code is not copied here [PP: tutorial].
- [Getting Started with MOTION:BIT Pro](https://my.cytron.io/tutorial/getting-started-with-motion-bit-pro) — Tutorial, Beginner, 2024 (series, 8 parts) [PP: tutorial]

## Sources
- [DS] MOTION:BIT Pro Datasheet Rev 1.0, April 2024 — https://drive.google.com/file/d/17kkl6oBU0n-gQtyQ84ylxg2KX3E9Ma0_/view (public). PDF mirror, same revision: https://cdn.robotshop.com/media/C/Cyt/RB-Cyt-437/pdf/cytron-motionbit-pro-12v-robotics-expansion-board-for-microbit-datasheet.pdf
- [PP] Product page: not found; Cytron tutorial linked by The Pi Hut (**not read**): https://www.cytron.io/tutorial/getting-started-with-motion-bit-pro
- [GH] https://github.com/CytronTechnologies/pxt-motionbit (README.md, pxt.json, motor.ts, rgb.ts) · https://makecode.microbit.org/pkg/CytronTechnologies/pxt-motionbit
- [VEN] https://tech.microbit.org/hardware/edgeconnector/
- [3P] (cross-check only) https://thepihut.com/products/motion-bit-pro-for-micro-bit · https://www.switch-science.com/collections/cytron/products/9790 · https://www.switch-science.com/products/9789 (comparison table) · https://ca.robotshop.com/products/cytron-motionbit-pro-12v-robotics-expansion-board-microbit
- [PP: tutorial] Cytron tutorials on my.cytron.io/tutorial (catalogue of 24 Sep 2026 and tutorial database of 17 Oct 2026), listed only where the tutorial uses this product.
