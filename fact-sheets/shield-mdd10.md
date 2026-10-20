# Product fact sheets

## Product name
10Amp 7V-30V DC Motor Driver Shield for Arduino (2 Channels)

## Aliases
SHIELD-MDD10, Cytron SHIELD-MDD10, Shield MDD10, 10A Dual Channel DC Motor Driver Shield for Arduino

## What it is
An Arduino-shield-format driver for two brushed DC motors, 10 A continuous per channel from a 7–30 V battery. Each motor is controlled by a PWM input and a DIR input on jumper-selected Arduino pins.

## Specs and functions
- Power input voltage: 7 V to 30 V (VB+ / VB-)
- Motor current per channel: 10 A continuous; 30 A peak
- Peak current is limited by the overcurrent protection circuit; actual limit depends on board temperature; 30 A value is at room temperature (25 - 30 degree Celsius); no peak duration stated
- 2 channels, PWM + DIR control per channel
- Logic input (PWM & DIR): low level 0 V to 0.8 V; high level 1.5 V to 5.5 V
- PWM frequency: standard DC to 20 kHz; extended 20 kHz to 40 kHz (continuous motor current reduced in the extended range); output frequency is same as input frequency
- Truth table: PWM low = brake (both outputs low); PWM high + DIR low = forward; PWM high + DIR high = backward (actual direction depends on motor connection)
- Built-in 5 V buck regulator powers the Arduino by default; DC +5V output 500 mA max
- Overcurrent protection with active current limiting (OC LED on when limiting)
- Temperature protection: higher board temperature gives a lower current-limit threshold
- Undervoltage shutdown (ERR LED on)
- Test buttons MA (forward) and MB (backward), run the motor at full speed
- LEDs: Power, motor status MA/MB, Error, OC
- Arduino reset button
- Dimensions: [NOT STATED]
- Operating temperature: [NOT STATED]
- Can drive one bipolar/unipolar stepper motor (product page)
- 5 V buck output 500 mA max to power the Arduino (product page)
- Packing: 1 × shield (product page)

## Interfaces and compatibility
- Arduino shield form factor: male header (bottom) to the Arduino, female header (top) for stacking other shields
- PWM/DIR Input Pin Selector to choose the Arduino pins for PWM and DIR; selectable pins: [NOT STATED]
- 5V Output solder jumper: cut the track to stop the shield powering the Arduino 5V pin
- Power Input Terminal VB+ / VB-; Motor Output Terminals MA / MB per motor
- Arduino library: Cytron Motor Drivers Library, PWM_DIR_DUAL example (CytronMD with PWM_DIR)
- Logic high threshold 1.5 V to 5.5 V
- 3D CAD file linked from the product page

## Use cases
- Driving two brushed DC motors from an Arduino
- Driving a motor that stalls or is oversized, with current limiting protecting the driver ("when the motor stalls or an oversized motor is hooked up")

## Known limitations
- No reverse polarity protection: "Connecting in reverse polarity will damage the motor driver instantaneously."
- 5 V output to the Arduino is 500 mA max
- Continuous current is reduced when PWM runs at 20–40 kHz
- Current-limit threshold falls as the board heats up
- Output shuts down if the power input drops below the lower limit (threshold [NOT STATED])
- Locked-antiphase operation: [NOT STATED]

## Positioning (kept apart from specs)
- [NOT STATED]

## Price band
RM120.12 (Cytron product page, read 2026-10-19)

## Product page
https://my.cytron.io/p-10amp-7v-30v-dc-motor-driver-shield-for-arduino-2-channels

## Datasheet
https://docs.google.com/document/d/1QHlQbs6f5fY_BMBs3hJRg1QLFe4yqy4nyH3mBavZ2-0

## Source type
Datasheet

## Source link
https://docs.google.com/document/d/1QHlQbs6f5fY_BMBs3hJRg1QLFe4yqy4nyH3mBavZ2-0
