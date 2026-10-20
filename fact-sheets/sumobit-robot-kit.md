# Product fact sheets

## Product name
SUMO:BIT Robot Kits - 1kg Sumo Robot for micro:bit

## Aliases
V-KIT-SUMOBIT, SUMO:BIT Robot Kit, SUMO:BIT Robot Kits, SUMOBIT Robot Kit, SUMO:BIT 1kg Sumo Robot Kit, 1kg Sumo Robot for micro:bit

## What it is
A 1 kg-class sumo robot kit for the BBC micro:bit built around the SUMO:BIT board with two MD13S motor drivers, five Maker Object opponent sensors, two Maker Reflect edge sensors, two 12 V DC motors, a 3S LiPo battery and a 3D-printed body with a steel blade. It runs autonomously from MakeCode or under remote control.

## Specs and functions
- Product code: V-KIT-SUMOBIT
- Competition class: 1 kg sumo robot
- Purchase options: Complete Kit (with body) / Basic Kit (without body) / 3D Printed Body only, each with or without micro:bit
- Controller: SUMO:BIT board with 2x MD13S attached (board specs: see the SUMO:BIT fact sheet)
- Drive motors: 2x 12 V 580 rpm DC motor with wires (Assembly guide and Checking guide); product page says "12V brushed DC motor" without rpm
- Motor torque: [NOT STATED]
- Wheels: 2x aluminium rim + silicone tyre wheel set, each rim fixed with two screws on the motor shaft flat
- Battery: LiPo 11.1 V 1300 mAh (3-cell); product page packing list 1x, Assembly guide item list 2x
- Charger: not included; "2-3 cell LiPo balance charger" offered as an accessory; guide says use a LiPo balance charger or USB LiPo charger
- 3-cell LiPo full charge up to 12.6 V; do not let the battery drop below 11 V
- Opponent sensors: 5x Maker Object
- Edge sensors: 2x Maker Reflect; "For best result, use with the latest (11 Dec 2024 onwards) Maker Reflect"
- Robot weight without extra weight: "around ±860g"
- Robot dimensions: [NOT STATED]
- Body: 1x 3D-printed main body, 1x right motor bracket, 1x left motor bracket, 2x copper base, 1x 6" stainless steel blade, 1x PCB plate (training), back cover (new step 13); free STL files on the Cytron-SUMOBIT GitHub
- Extra weight: not included; maximum 4 pieces in a row beside the battery compartment, covered to prevent short circuits
- Complete Kit packing list (with micro:bit, product page): 1x SUMO:BIT with 2x MD13S attached, small flat screwdriver, Phillips screwdriver, Dean T male connector 18 AWG 15 cm, 5x Maker Object, 2x Maker Reflect, 7x GVS F-F extension cable 10 cm, 2x 12 V brushed DC motor with wires, 2x wheel set, M2 Allen key, 1x LiPo 11.1 V 1300 mAh, 3S LiPo charger cable extension 10 cm, 2x copper base for mini sumo robot, 4x M3 nylon lock nut, 4x M3 bolt 20 mm, 10x M3x6 self-tapping screw, 1x PCB Plate for Blade (training), 1x 6" stainless steel blade, 1x 3D-printed chassis with motor brackets, 1x micro:bit Junior Kit, 1x BBC micro:bit V2, USB Micro B cable, sticker set
- Assembly guide item list: 1x SUMO:BIT board, 1x micro:bit Junior Kit, 5x Maker Object, 2x Maker Reflect, 2x 12 V 580 rpm DC motor with wires, 2x aluminium silicone wheel set, 2x LiPo battery 11.1 V 1300 mAh, 1x 3D-printed main body, 1x right motor bracket, 1x left motor bracket, 2x copper base, 1x steel blade, 1x PCB plate, 7x 10 cm GVS female-to-female cables, 1x Dean T male connector with cable, 1x 10 cm 3S LiPo charger cable extension, 1x small flat screwdriver, 1x Phillips screwdriver, 10x M3 tapping screws (6 mm), 4x M3 bolt and nut (20 mm)
- Basic Kit and Body-only contents: [NOT STATED]
- Dohyo used in the guides: 1 m diameter
- A typical sumo round lasts around 10 seconds or less; more than 1 minute continuous running may overheat the motors
- Guides: Assembly (V1) 2 Dec 2024, Checking 2 Dec 2024, Maintenance 2 Dec 2024, Autonomous 9 Dec 2024, RC (Remote Control) 10 Dec 2024 (Google Slides)
- Warranty: [NOT STATED]
- Four options: Complete or Basic kit, each with or without micro:bit; Basic kits have no 3D-printed chassis (product page)
- One 11.1 V 1300 mAh LiPo per kit (product page)
- Motor: 12 V 580 rpm 3.5 kgf·cm geared motor (product page packing-list link)

## Interfaces and compatibility
- Wiring: EDGE-L = left Maker Reflect, EDGE-R = right Maker Reflect, OPP-L = left Maker Object, OPP-FL = front-left, OPP-FC = front-centre, OPP-FR = front-right, OPP-R = right Maker Object, all on 10 cm GVS F-F cables; motors on the LEFT MOTOR / RIGHT MOTOR terminals; battery on the battery terminal through the Dean T cable
- Maker Reflect cable pins OUT, VCC, GND; Maker Object cable pins GND, VCC, OUT (as the guide lists them)
- Assembly: 13 steps (edge sensors, copper bases, motors and brackets, opponent sensors, optional weights, motor and battery connection, motor direction check with the alignment button, sensor connections, board mounting, rims and tyres, micro:bit, PCB plate or blade, optional robot holder, back cover)
- micro:bit inserted with buttons and LED matrix facing up; only required for autonomous mode
- Programming: Microsoft MakeCode with the "sumobit" extension (https://github.com/CytronTechnologies/pxt-sumobit); flash by USB from a computer or wirelessly from an iPad/iPhone/Android app (press the micro:bit reset button three times for Bluetooth mode)
- Autonomous sample programs: edge sensor and battery readout, navigation, move around the dohyo, detect obstacle, basic sumo robot with 5 s countdown, community DIP-strategy programs started by button or by IR Sumo Start
- RC mode 1 — wireless USB joystick: remove the micro:bit, plug the receiver into the USB-A port, RGB LEDs stay yellow when ready; only the Cytron USB Joystick model is supported; half speed by default, hold R2 for full speed
- RC mode 2 — hobby RC receiver on the SERVO/RC port: port 1 = speed (forward/reverse), port 2 = steering; turn on the transmitter first; RGB LEDs stay orange when ready; example mappings FlySky FS-iA6B CH2/CH4, Hot RC F-06A CH2/CH1, Dumborc X6F CH2/CH1 to RC port 1/2
- RC mode 3 — a second micro:bit as joystick (Joystick:bit V2 used in the guide): code on both ends, semi-auto possible; press B on the joystick to set the edge threshold before a run
- Firmware update: .uf2 from the SUMO:BIT GitHub page, hold the boot button while connecting USB-C, copy to the RPI-RP2 drive
- Accessories offered: USB Joystick, 2-3 cell LiPo balance charger
- Support: Telegram SUMO:BIT Support Group (https://t.me/sumobit_support)

## Use cases
- Start your sumo journey: build and compete with a 1 kg sumo robot
- Autonomous sumo robot programmed in MakeCode (edge detection, opponent detection, attack and search)
- Remote-controlled sumo robot via wireless USB joystick, hobby RC transmitter, or a second micro:bit as joystick
- DIP-switch strategy selection for competitions, started by button or IR Sumo Start
- Practice with the PCB plate; tournaments with the steel blade
- Cytron tutorial: [Joystick Pairing with SUMO:BIT and Motion 2350 Pro](https://my.cytron.io/tutorial/joystick-pairing-with-sumobit-and-motion-2350-pro)

## Known limitations
- Charger not included; extra weights, robot holder tape, Joystick:bit and a second micro:bit are not included
- "Without micro:bit" options omit the micro:bit; the micro:bit is removed for USB-joystick and RC-receiver modes
- USB joystick mode only supports the Cytron USB Joystick model
- Do not discharge the 3S LiPo below 11 V; full charge is 12.6 V
- Motors are high-current and heat quickly; rest the robot if the motor bracket feels warm; more than 1 minute continuous running is too long
- Run only on a dohyo (or a clean flat surface for RC testing); avoid tiles, uneven or dusty floors and carpet
- Check battery polarity at the board before connecting
- The blade is sharp; use the PCB plate for practice
- Screws loosen after impacts and need regular tightening
- Best edge-sensor results need Maker Reflect units from 11 Dec 2024 onwards
- Robot dimensions, motor torque and the Basic Kit / Body-only contents are not stated
- Product page lists 1 battery while the Assembly guide lists 2

## Positioning (kept apart from specs)
- "Start your sumo journey with the SUMO:BIT Robot Kit!"
- "Whether you're a beginner or looking to sharpen your skills, this kit has everything you need to start your journey."
- "SUMO:BIT board, MD13S Motor Driver, Essential accessories, Free STL file for robot body"

## Price band
RM80.00–RM1,047.70 across options (Cytron product page, read 2026-10-20)

## Product page
https://my.cytron.io/p-sumobit-robot-kits-1kg-sumo-robot-for-microbit

## Datasheet
https://docs.google.com/presentation/d/15mmPIKEZlVMuslrhgAz_jTQuCI3Ud2Z0r1F7EQjnnpk/edit

## Source type
Datasheet

## Source link
https://docs.google.com/presentation/d/15mmPIKEZlVMuslrhgAz_jTQuCI3Ud2Z0r1F7EQjnnpk/edit
