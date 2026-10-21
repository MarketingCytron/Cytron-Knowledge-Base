# MakerDisk 32GB Preloaded Offline MakeCode & Raspberry Pi OS — Verified Reference

| Field | Value |
|---|---|
| Product code | `MMR-USD-32-MC` [PP] |
| Family | Storage (MakerDisk) |
| Status | Check the live product page on my.cytron.io |
| Last verified | 2026-10-21 |
| Reviewed | 2026-10-21 — new product added: full Cytron OEM product page, its four description images (MakeCode app window, extension import steps) and the card photo; the linked "User Instruction - microbit MakeCode offline server v2.pdf" (Google Drive) read in full; metadata of the linked installer files and extension folder |
| Primary source | Cytron product page https://my.cytron.io/cytron-oem/p-makerdisk-class-10-a1-microsd-card-preloaded-offline-makecode-with-raspberry-pi-os (read 2026-10-21) [PP]; "User Instruction - microbit MakeCode offline server" v2 (TomatoCube, last updated April 2023) [UM] |

**Authority rule:** Datasheet [DS] > user manual [UM] > Cytron design team [DT] > Cytron product page [PP] / internal docs > Cytron GitHub [GH] > vendor docs [VEN] > third-party [3P]. Where sources disagree, the higher one wins and the conflict is listed under *Conflicts*. A [3P]-only fact is never stated as a spec — it goes to *Needs verification*.
Tag notes: [PP] = Cytron product page text read 2026-10-21; [PP: img] = images on that page; [UM] = the linked user instruction for the offline MakeCode application (14 slides; the application is "created & maintained by TomatoCube" per its splash screen and the slides). The MakerDisk card itself has no datasheet. The page's slug says "class-10-a1"; the title does not.

## What it is
- A 32GB Cytron-brand MakerDisk microSD card with **Raspberry Pi OS** and an **offline micro:bit MakeCode editor** preinstalled, so a Raspberry Pi can program micro:bit boards without internet [PP].
- After boot, a "microbit" icon on the desktop opens the editor; the user chooses the offline editor inside the app or the browser-based editor (which needs internet) [PP].
- 18 MakeCode extensions are supplied as .hex files in the Download folder; they are imported into the editor by hand [PP].
- Sibling: `makerdisk-microsd-rpi-os.md` (plain Raspberry Pi OS cards).

## Specifications
| Item | Value | Src |
|---|---|---|
| Capacity | 32GB ("1GB = 1,000,000,000 bytes") | [PP] |
| Preloaded software | Raspberry Pi OS (version/bit-width not stated) + offline MakeCode editor + 18 extension .hex files | [PP] |
| Target board | Raspberry Pi 4 Model B "with the latest bootloader firmware" | [PP] |
| Speed class (Features) | "Class 10, A1, U3, V30 microSD card" | [PP] |
| "SD Card Performance Test" | Write 21.8 MB/s; Read 1.1 GB/s (see *Conflicts* — copied from the VisionFive 2 card's `dd` test) | [PP] |
| Card face (product photo) | MakerDisk 32GB, micro SD HC, UHS-I, Class 10, A1; "OS READY" and "PRELOADED with MakeCode Offline" badges | [PP: img] |
| MakeCode app (screenshot) | Window "microbit MakeCode" showing a Cytron logo, build string dated April 2023, IP address and Port 1234; buttons "Open Makecode Editor within this Program" and "Open Makecode Editor with an external browser"; "Program created & maintained by TomatoCube" | [PP: img] |
| Local web server | Starts in the background; reachable from other LAN machines at http://<host IP>:1234 | [UM] |
| Warranty | 12 months | [PP] |

### Extensions included (.hex) [PP]
microbit-BH1750, microbit-cutebot, microbit-Environment-and-Science-IoT, microbit-Grove, microbit-koi, microbit-maqueen, microbit-pxt-DHT11_DHT22, microbit-pxt-edubit, microbit-pxt-kitronik-servo-lite, microbit-pxt-motionbit, microbit-pxt-nezha, microbit-pxt-rekabit-rbt-project-kit, microbit-pxt-rekabit, microbit-pxt-zoombit, microbit-reromicro, microbit-RingbitCar, microbit-smarthome-kit, microbit-tinkercademy-tinker-kit.

### Product page facts (my.cytron.io, read 21 Oct 2026)
- Code `MMR-USD-32-MC`, RM54.00, availability 10, warranty 12 months, 1 rating [PP].
- Packing list: 1 × 32GB MakerDisk microSD with Raspberry Pi OS, pre-loaded with MakeCode offline editor [PP].
- Accessories offered: USB2.0 Cytron microSD Card Reader/Writer Adapter, Maker-Friendly Zipper Case [PP].
- Resources ("In case you need to flash the OS again"): User Instruction (PDF); micro:bit MakeCode (Raspberry Pi) = `Cytron_April23_microbit_Raspberry_armhf.deb` (≈239 MB); micro:bit MakeCode (Windows) = `Cytron_April23_microbit_Windows.exe` (≈239 MB); Extensions (Drive folder "Extension") [PP][Drive metadata].

## Interfaces, terminals and pin mapping
- microSD card for the Raspberry Pi slot [PP]. The micro:bit is connected to the Pi by USB; the [UM] says code upload from the built-in app is by mass-storage (drag-and-drop) transfer, and one-click WebUSB upload needs an external Chrome/Chromium browser.

## Rules and gotchas (for code, wiring and tutorials)
- **Do not format the card** if it will boot a Raspberry Pi [PP].
- **Board stated: Raspberry Pi 4 Model B with the latest bootloader** [PP]. Pi 5 / Pi 400 / Pi 3 are not mentioned — do not promise them.
- **Extensions are not pre-loaded into the editor:** unzip the folder in Downloads, then Extensions → Import File → choose the .hex [PP][UM].
- **Offline vs browser editor:** the in-app editor works offline; the "external browser" option and WebUSB flashing need a Chrome-based browser [UM]; the browser-based MakeCode in the page's sense requires internet [PP].
- **Re-installing:** Cytron's Drive has only the **armhf** (32-bit) .deb for Raspberry Pi; the [UM] says the 64-bit OS needs `microbit_1.0.0_arm64.deb`, which is not linked [UM][PP]. Install with `sudo dpkg -i <file>.deb`, run with `microbit` [UM].
- Do not quote "Read 1.1 GB/s" as card performance (see *Conflicts*).

## Power and electrical limits
- Not stated. Powered from the Raspberry Pi's microSD slot.

## Software support
- Raspberry Pi OS (release not stated) [PP]; MakeCode offline application build dated April 2023 (installer names "Cytron_April23") [PP][PP: img].
- The [UM] (last updated April 2023) lists builds for Raspbian 32-bit (Bullseye 32-bit and Buster, armhf), 64-bit (Bullseye 64-bit, arm64) and Windows; adding a menu shortcut via Main Menu Editor; hosting the editor on port 1234 for LAN browsers; generating extension .hex files from GitHub via Import URL → "Download as file" [UM].

## Compatibility and accessories
- Raspberry Pi 4 Model B (latest bootloader) [PP]; any micro:bit board ("MakeCode offline editor can be used to program any micro:bit boards") [PP].
- Cytron micro:bit boards whose extensions are on the card: EDU:BIT (`edu-bit.md`), REKA:BIT (`reka-bit.md`), REKA:BIT RBT Project Kit (`rekabit-rbt-project-kit.md`), MOTION:BIT (`motion-bit.md`), ZOOM:BIT (`zoom-bit.md`) [PP].
- Accessories: `cytron-microsd-card-reader.md` [PP].

## Common mistakes / troubleshooting
- **Extension blocks missing:** import the .hex from the Downloads folder first [PP].
- **Can't flash with one click:** use an external Chrome/Chromium for WebUSB, or drag the .hex to the MICROBIT drive [UM].
- **Card re-flashed with plain Raspberry Pi OS:** the MakeCode app must be re-installed from the linked .deb [PP].

## Conflicts between sources
| Fact | Source A says | Source B says | Resolution |
|---|---|---|---|
| "Read Speed: 1.1 GB/s" | This page's performance test [PP] | The identical figures come from the VisionFive 2 card page's `dd` screenshot, where 1.1 GB is the 1 GiB test-file size and the read was of a file just written (cached in RAM) [PP: img on `makerdisk-microsd-visionfive2.md`] | Not a card speed; omit. A microSD on a Pi 4 cannot read at 1.1 GB/s |
| 32GB speed class | This page: A1, U3, V30 [PP] | Raspberry Pi OS MakerDisk page: 32GB A1 is U1, V10 [PP] | Unresolved; quote only "Class 10, A1" (printed on the card) |
| Bit-width of the preloaded OS | Not stated [PP] | Only the armhf (32-bit) MakeCode installer is linked [PP] | Inferred that the image may be 32-bit; not confirmed |

## Needs verification
- Raspberry Pi OS release and 32/64-bit of the preloaded image.
- Whether the card boots Raspberry Pi 5 / Pi 400 / Pi 3.
- Real Raspberry Pi Diagnostics figures for this card.
- Whether this card is covered by the Raspberry Pi approval certificates (not claimed on this page).

## Sources
- [PP] https://my.cytron.io/cytron-oem/p-makerdisk-class-10-a1-microsd-card-preloaded-offline-makecode-with-raspberry-pi-os — read 2026-10-21
- [PP: img] `MMR-USD-32-MC-1.jpg` (app window), `MMR-USD-32-MC-4 .png` (extension import steps), `MMR-USD-32-MC-800x800.png` (card photo)
- [UM] "User Instruction - microbit MakeCode offline server v2.pdf" — (Cytron document — link not public) (read 2026-10-21)
- Drive metadata: (Cytron document — link not public) (armhf .deb), (Cytron document — link not public) (Windows .exe), (Cytron document — link not public) (Extension folder)
- KB cross-references: `makerdisk-microsd-rpi-os.md`, `makerdisk-microsd-visionfive2.md`, `cytron-microsd-card-reader.md`, `edu-bit.md`, `reka-bit.md`, `rekabit-rbt-project-kit.md`, `motion-bit.md`, `zoom-bit.md`
