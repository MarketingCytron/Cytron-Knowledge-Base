# Product fact sheets

## Product name
DIY RC Boat Using micro:bit

## Aliases
DIY RC Boat Using micro:bit, PR-DIY-BOAT-MBIT, DIY RC Boat, micro:bit RC Boat, RC Boat micro:bit, DIY Boat micro:bit

## What it is
A do-it-yourself remote-controlled boat project for the BBC micro:bit: one micro:bit on the boat plugged into a MOTION:BIT drives two DC motors with propellers and a 9 g servo rudder fin, and a second micro:bit is the radio remote. The product page is the build guide and the hull is 3D-printed from Cytron's STL files or made from foam or plastic.

## Specs and functions
- Product code: PR-DIY-BOAT-MBIT
- Project kit; the product page is itself the build guide (6 build steps: gather components, assemble hull, ...)
- Controller board: MOTION:BIT (see the MOTION:BIT fact sheet; not re-documented here)
- Components listed: BBC micro:bit x2; MOTION:BIT; 2x DC motors with propellers; 9g servo (fin); 3.7V LiPo battery pack; boat hull 3D-printed (STL provided) or foam/plastic; waterproof enclosure optional
- Propulsion: 2x DC motors with propellers
- Steering: 9 g servo moving a fin; fin positions used by Cytron's remote code: 130 degrees, 50 degrees, 90 degrees (centre)
- Power: 18650 cell in the MOTION:BIT holder, supplied with the MOTION:BIT bundle (page text calls it a "3.7V LiPo battery pack")
- Software: MakeCode blocks with the MOTIONBIT extension; Code #1 on the boat micro:bit, Code #2 on the remote micro:bit
- Remote controls: Shake = start the motors; Button A = fin to 130 degrees; Button B = fin to 50 degrees; Buttons A+B = fin back to 90 degrees; touch the micro:bit logo = stop the motors
- Hull: 3D-printed (STL files provided; Cytron printed it on an Artillery Hornet) or foam/plastic
- Packing list (product page image): 2 × 56 mm 4-blade propellers; 1 × SG90 micro servo; 2 × 3 V miniature brushed DC motors with leads; 1 × MOTION:BIT bundle with micro:bit Junior Kit and 18650; 1 × micro:bit V2 Go Bundle. No hull
- Warranty: [NOT STATED]
- Dimensions: [NOT STATED]
- Weight: [NOT STATED]

## Interfaces and compatibility
- Boat: micro:bit on MOTION:BIT; 2 DC motors on MOTION:BIT motor terminals; 9 g servo on a MOTION:BIT servo port
- Motors on MOTION:BIT M1 and M2; servo on a right-side servo header, port number not readable (product page image)
- Remote: second micro:bit over micro:bit radio; radio group: [NOT STATED]
- Battery: 18650 in the MOTION:BIT holder
- MakeCode blocks; MOTIONBIT extension https://github.com/CytronTechnologies/pxt-motionbit
- Linked resources: Getting Started with MOTION:BIT & Projects Guide tutorial; MOTION:BIT datasheet; pxt-motionbit; MOTION:BIT 3D CAD
- Tutorial with video: Build an RC Boat Using micro:bit (https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit)
- micro:bit: remote is the micro:bit V2 Go Bundle (touch logo needs V2); boat micro:bit comes in the micro:bit Junior Kit

## Use cases
- Build a remote-control boat with a micro:bit
- Control the boat's motors and rudder fin from a second micro:bit using shake, buttons and the touch logo
- 3D-print a boat hull from the provided STL files

## Known limitations
- No datasheet, booklet or packing list; the product page and tutorial are the only guides
- The hull is not included
- MOTION:BIT motor channels, servo port and the radio group are not stated in text (shown only in code-block images)
- The hull must be 3D-printed from the STL files or made from foam or plastic
- Waterproof enclosure is optional and not described; the micro:bit, MOTION:BIT and LiPo are not waterproof
- MOTION:BIT limits apply: 3.6–6 V input, 1 A continuous / 1.5 A peak per motor channel
- The remote's touch-logo stop command needs a micro:bit with a touch logo
- Motor current, run time and warranty are not stated

## Positioning (kept apart from specs)
- Remote-control boat built with a micro:bit, with a video tutorial available

## Price band
RM297.55 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-diy-boat-mbit

## Datasheet
[NOT STATED]

## Source type
Website

## Source link
https://my.cytron.io/tutorial/build-an-rc-boat-using-micro-bit
