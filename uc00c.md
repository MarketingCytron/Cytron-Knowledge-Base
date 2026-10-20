# UC00C (CH340) USB to UART Converter — Verified Reference

| Field | Value |
|---|---|
| Product code | UC00C [PP][UM] |
| Family | USB and serial converters |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-19 |
| Reviewed | 2026-10-19 — master-table review (Medium batch 2): live my.cytron.io product page read (description, features, packing list, resources). VCC current, LED colours, OS testing, size and packing are now Cytron-stated; the physical pin order is only in a page image (not read), so it stays Medium |
| Primary source | "UC00C Cytron USB to UART Converter User's Manual", V1.0, July 2016 (Cytron Technologies Sdn Bhd) — no separate Cytron datasheet exists; the user manual is the top Cytron source and is tagged [UM] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.

## What it is
A small USB-powered USB-to-UART converter board that gives a computer a virtual COM port and connects it directly to a microcontroller's TTL UART at 3.3 V or 5 V logic [UM]. The user manual describes it as "low cost, easy to use", "USB powered, no external source is required", with "5V from USB port available for user", "Configurable for 3.3V/5V UART interface", a "USB Micro-B socket" and a "Selectable Switch 5V and 3.3V" [UM]. The product page names the USB-serial chip as CH340 [PP]; the user manual only says "USB to UART chip" and never names it [UM].

It is a converter/programmer, not a level shifter for RS232: it replaces the old "PC serial port (DB9) + RS232 level shifter" path with "PC USB → UC00C → TTL UART" [UM].

## Specifications
The user manual has no numeric spec table; the rows below collect every stated feature and figure [UM]. Items the manual does not state are listed at the end.

| Item | Value | Src |
|---|---|---|
| USB-to-UART chip | "USB to UART chip" (not named) | [UM] |
| USB-to-UART chip | CH340 (product title "UC00C (CH340) USB to UART Converter") | [PP] |
| Driver package names on product page | "CH341SER V3.5 Mar2019.zip" (Windows), "CH341SER_MAC.ZIP" (Mac V1.5 Mar2019), "CH341SER_LINUX.ZIP" (Linux V1.5 Mar2019) | [PP] |
| USB connector | USB Micro-B socket ("Utilize USB Micro-B socket") | [UM] |
| Power source | USB powered; "no external source is required to use this converter" | [UM] |
| UART logic level | 3.3 V or 5 V TTL, selected by the VCC selectable switch at "F" ("Selectable Switch 5V and 3.3V") | [UM] |
| Power output to target | VCC pin: 3.3 V or 5 V, follows the Vsel slide switch; "5V from USB port is available for user" | [UM] |
| Interface header | 6-way header socket: DTR, RX, TX, VCC, CTS, GND ("Header socket, for Arduino board") | [UM] |
| LEDs | Power LED (green), RX LED, TX LED | [UM] |
| Bootloader compatibility | "Compatible with Bootloader for Arduino board such as BBFuino, Boarduino, Arduino Mini Pro, etc." | [UM] |
| Driver | "Plug and Play, driver is needed for 1st time user only" | [UM] |
| Operating systems | "UC00C are compatible for Windows 7,8 and 10. It appears as Virtual COM port on computer." | [UM] |
| Dimension | 3.9 cm x 2 cm | [UM] |
| Packing list | 1 x UC00C. Optional accessories: USB Micro B cable (sold separately); driver and manual downloaded from the Cytron website | [UM] |
| Warranty | 1 year ("Product warranty is valid for 1 year") | [UM] |
| Warranty | 12 months | [PP] |
| Price | RM15.75 | [PP] |
| Baud rate range, output current on VCC/5V, supply current, operating temperature, header pitch, weight, DTR polarity | Not stated | [UM] |

Chip-vendor reference (not a Cytron spec, for context only): the WCH CH340 datasheet (V1D) states 50 bps to 2 Mbps, USB 2.0 full-speed device, and TXD/RXD/RTS#/CTS#/DTR#/DSR#/DCD#/RI# modem signals [VEN]. Do not state these as UC00C specs — Cytron has not confirmed which CH340 variant is fitted or which rates the board supports (see Needs verification).
### Product page facts (my.cytron.io, read 19 Oct 2026)
- **Voltage switch and current:** slide switch selects 3.3 V or 5 V on VCC and the signal lines. At **5 V** the board sources as much as the USB port provides; at **3.3 V** the maximum current is **500 mA** [PP].
- **LEDs:** red = TX line, orange = RX line [PP].
- **OS:** "tested to work well on Windows 7, 8, 8.1 and 10"; "should auto install on most operating systems without the need for additional drivers" [PP].
- **Features list:** CH340 USB to UART chip; USB powered; selectable 3.3 V / 5 V UART; 6-pin interface DTR, RXD, TXD, VCC, CTS, GND; 6-way header socket for bootloading Arduino-compatible boards (BBFuino, Arduino Pro Mini 328, Arduino Fio); **dimension 39.8 × 21.2 × 5.6 mm** [PP].
- **Packing list:** 1x UC00C (CH340) USB to UART Converter [PP].
- **Resources:** UC00C User Manual (Google Doc); CH34X drivers (Windows V3.5, Mac V1.5, Linux V1.5, Mar 2019), older macOS drivers (third-party links), WCH factory driver, CH341 Mac troubleshooting PDF [PP].
- Pinout image and pin-description image are on the page (`UC00C-Pinout-Image.png`, `UC00C-Pinout-Description.png`) — not read here (image only).

## Interfaces, terminals and pin mapping
### Board layout (user manual section 4.0) [UM]
| Label | Function | Src |
|---|---|---|
| A | MicroB USB socket — USB connection to PC desktop or laptop | [UM] |
| B | Power LED (green) — on once the USB connection to the computer is ready | [UM] |
| C | RX LED — indicates receive activity; works only when connected to a PC over USB | [UM] |
| D | Header socket, for Arduino board — "reserved for loading program to Arduino Mini Pro, BBFuino, Fio and others" | [UM] |
| E | TX LED — indicates transmit activity; works only when connected to a PC over USB | [UM] |
| F | VCC selectable switch — chooses 3.3 V or 5 V for the UART interface pins and the VCC output | [UM] |

### 6-way header socket (user manual section 5.1, in the manual's table order) [UM]
| Label | Definition | Function | Src |
|---|---|---|---|
| DTR | UC00C Data Terminal Ready pin | "In Arduino compatible board, this pin is use for auto-reset." | [UM] |
| RX | UC00C UART Receive pin | Receiver pin of UC00C; connect to the device's transmitter (TX) pin | [UM] |
| TX | UC00C UART Transmit pin | Transmitter pin of UC00C; connect to the device's receiver (RX) pin | [UM] |
| VCC | 3.3 V or 5 V power output from UC00C | Power output to the microcontroller; 3.3 V or 5 V. "If 5V is selected at Vsel slide switch, this pin will supply 5V to target device." | [UM] |
| CTS | UC00C Clear To Send pin | "Hardware Hand-shacking pin." | [UM] |
| GND | Ground or negative | Ground of power and signal; connect to the device's GND | [UM] |

The physical left-to-right order on the socket is shown only in the manual's board figure, which did not extract as text; the table order DTR, RX, TX, VCC, CTS, GND is the only order stated in words [UM]. See Needs verification.

### Voltage selection [UM]
- The switch at "F" sets the TTL level of the UART interface pins and the VCC output: 5V → "all the interface pins which include TX, RX, DTR, CTS, RTS, DSR will be in 5V TTL logic"; 3V3 → all interface pins in 3.3 V TTL logic [UM].
- "Vsel" and "5V" come directly from the computer's USB port [UM] (see Power).

## Rules and gotchas (for code, wiring and tutorials)
- **Cross the data lines.** UC00C RX → target TX; UC00C TX → target RX; GND to GND [UM].
- **Set the switch before plugging into a 3.3 V board.** The switch sets both the signal logic level and the VCC output [UM]. The manual gives no factory default position for UC00C — check the switch; do not tell readers it "defaults to 5V" (that statement exists only in the UC00A manuals).
- **Do not power an application circuit from VCC/5V.** Manual caution: "'Vsel' and '5V' on UC00C is supply directly from USB of computer; it is advised not to use this power source to power application circuit or device. Wrong connection such as wrong polarity, wrong voltage, shorted might permanently damage computer." [UM]
- **DTR is the Arduino auto-reset line** on the 6-way socket [UM]. The manual does not describe the DTR polarity or the capacitor; the auto-reset capacitor sits on the Arduino-style target board, not on UC00C (not stated — do not claim otherwise).
- **CTS is the only hardware handshake pin on the socket.** RTS/DSR are mentioned in the switch description but are not listed on the 6-way socket [UM] — do not promise RTS or DSR access on UC00C.
- **Driver first.** A CH340-family driver must be installed once before the virtual COM port appears [UM][PP]. Use the links on the product page [PP], not the 2016 links inside the manual (those point to an old third-party host, v3.4 Windows / v1.3 Mac).
- **Windows support statement is 7/8/10** [UM]; nothing is stated for Windows 11 or current macOS versions — see Needs verification.
- TX/RX LEDs light only when the board is connected to a PC over USB [UM].

## Power and electrical limits
- Supply: USB bus power only; no external supply input [UM].
- VCC output: 3.3 V or 5 V, selected by the switch [UM]. Current limit: not stated [UM]. The manual says "low current 5V supply from USB port" without a figure [UM].
- "5V" is "supply directly from USB of computer" [UM] — any short or wrong polarity "might permanently damage computer" [UM].
- Absolute maximum ratings, supply current, I/O tolerance: not stated [UM].

## Software support
- Appears as a Virtual COM port [UM]. Works with any serial terminal or Arduino IDE serial upload (bootloader upload stated for BBFuino, Boarduino, Arduino Mini Pro [UM]).
- Drivers linked on the product page [PP] (record only — not downloaded):
  - Windows: CH341SER V3.5 Mar2019 — https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view
  - Mac: CH341SER_MAC V1.5 Mar2019 — https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view
  - Linux: CH341SER_LINUX V1.5 Mar2019 — https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view
  - Mac troubleshooting PDF: https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf (not read — fetch blocked in this session)
- Drivers linked inside the 2016 user manual [UM] (older, third-party host): Windows "CH34x_Install_Windows_v3_4.zip"; Mac "CH34x_Install_MAC_10_9_AND_ABOVE_V1_3.zip" for OS X 10.9–10.11; a GitHub "CH34x_Install_V1.3.zip" for OS X Sierra 10.12; "Linux normally pre-installed with the proper driver" [UM].
- No Cytron library, firmware or GitHub repository is stated [UM].

## Compatibility and accessories
- Bootloader/programming targets stated: Arduino Mini Pro (Pro Mini), BBFuino, Boarduino, Fio "and others" [UM]. Any 3.3 V or 5 V TTL-UART device in general ("development between computer and microcontroller, 3.3V or 5V logic") [UM].
- Which Cytron boards it programs: the manual names only BBFuino among Cytron boards [UM]. No current Cytron board (Maker UNO, Maker Nano, etc.) is named in the manual — do not claim them without a source.
- Cable: USB Micro-B cable, optional accessory, not included [UM].
- Not supported / not stated: RS232 levels (needs a separate level shifter — the manual's own introduction explains this) [UM]; RTS/DSR/DCD/RI pins (not on the socket) [UM]; external power input (none) [UM].

## Common mistakes / troubleshooting
- No COM port appears → driver not installed; install the CH340-family driver from the product page links once, then re-plug [UM][PP].
- Board powers (green LED) but no data → RX/TX not crossed, or GND not shared [UM].
- 3.3 V target damaged or misbehaving → switch left at 5V; the switch sets both signal level and VCC [UM].
- Arduino upload fails to auto-reset → DTR not connected to the target's reset pad; the 6-way socket is meant to plug straight onto Pro Mini/BBFuino bootloader headers [UM].
- Computer USB port shuts down → VCC/5V shorted or used to power a load; the manual advises against powering application circuits from it [UM].
- Mac driver problems → product page links a Mac troubleshooting PDF and a Mac driver V1.5 [PP]; the 2016 manual's Mac driver is v1.3 for OS X 10.9–10.12 only [UM].
- Manual text refers to "UC00A" and "USB mini cable" in the LED descriptions → copy-paste error in the UC00C manual; UC00C uses a Micro-B socket [UM] (see Conflicts).

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| USB-to-UART chip | [UM] "USB to UART chip" (unnamed) | [PP] product title "UC00C (CH340)"; driver zips named CH341SER | [UM] is silent, so [PP] CH340 stands; exact variant (CH340G/C/…) unconfirmed |
| USB connector (within the manual) | [UM] features and layout: "USB Micro-B socket", "MicroB USB socket" | [UM] LED paragraphs: "connected to PC or laptop through USB mini cable", and call the board "UC00A" | Micro-B wins — the layout table is specific; the LED text is copied from the UC00A manual |
| Interface pins on the voltage switch | [UM] switch text: "TX, RX, DTR, CTS, RTS, DSR" | [UM] 6-way socket table: DTR, RX, TX, VCC, CTS, GND only | The socket table wins; RTS/DSR are not broken out on UC00C as documented |
| Warranty | [UM] 1 year | [PP] 12 months | Same value, no conflict |
| Driver versions | [UM] (2016) Windows v3.4, Mac v1.3 | [PP] (2019) Windows V3.5, Mac V1.5, Linux V1.5 | [PP] is newer; use product page links. No spec conflict |

## Needs verification
- Exact CH340 variant fitted (CH340G with external 12 MHz crystal vs CH340C), and whether it has changed across production batches — no Cytron source states it; [VEN] only.
- Supported baud rate range on UC00C — not stated [UM]; CH340 vendor figure 50 bps–2 Mbps [VEN] not confirmed by Cytron.
- Default position of the voltage switch as shipped — not stated [UM].
- Physical pin order of the 6-way socket (left-to-right on the board) — the manual's figure did not extract; only the table order is known [UM]. Whether the socket is keyed/colour-marked (GRN/BLK) like UC00A — not stated.
- Whether DTR is active-low / its polarity — not stated [UM].
- Windows 11, macOS 11+ and Linux kernel-driver support — not stated [UM]; the Mac troubleshooting PDF on the product page was not readable in this session.
- Header socket type (female socket vs male pins) and pitch — "header socket" only [UM].
- Which current Cytron boards it programs — only BBFuino named [UM]; confirm with design team [DT] before naming others.
- Physical pin order: read the product page images `UC00C-Pinout-Image.png` / `UC00C-Pinout-Description.png` when the browser can render images.

## Sources
- [UM] UC00C Cytron USB to UART Converter User's Manual, V1.0, July 2016 — https://docs.google.com/document/d/1adRsDAq_2xHbCvTTBw_mdcA3iCzYsW2S5WuDaZOizjc/view (Google Doc; figures did not extract as text)
- [PP] Product page https://my.cytron.io/p-uc00c-ch340-usb-to-uart-converter (read by coordinator 2026-10-16: RM15.75, in stock 240, warranty 12 months)
- [PP] Windows driver "CH341SER V3.5 Mar2019.zip" — https://drive.google.com/file/d/1kk0b2HTYLKBXxS4TNNlC_neef6iE94sV/view (metadata only; not downloaded)
- [PP] Mac driver "CH341SER_MAC.ZIP" (V1.5 Mar2019) — https://drive.google.com/file/d/1iZ4fO-eAttw0ztlWVN_VTPB9cVSOu3CX/view (metadata only)
- [PP] Linux driver "CH341SER_LINUX.ZIP" (V1.5 Mar2019) — https://drive.google.com/file/d/1YQcex-0j6PN2I8J1Fa5ecxfsCLarANj2/view (metadata only)
- [PP] Mac troubleshooting PDF — https://cdn.cytron.io/makeruno/Troubleshooting_CH431_Driver_For_Mac.pdf (not read; fetch blocked)
- [VEN] WCH "The DataSheet of CH340 (the first)", V1D — https://cdn.sparkfun.com/datasheets/Dev/Arduino/Other/CH340DS1.PDF (mirror; context only)
