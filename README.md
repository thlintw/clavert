# Clavert

Clavert: Clever, clavier, vertical, avert carpal tunnels.
It's a (pair of?) ZMK powered wireless ergonomic split keyboard, using Redox layout.

## Suggested Materials

Below are some of the more important materials for the build. Misc materials not listed.

- MX compatible switches * 70
- Kailh hotswap sockets * 70
- 1N4148 diodes * 70
- EVQWGD001 encoder * 1
- 6mm x 6mm x 4mm 4 pin push button switch * 2
- 11.5 mm x 5.5mm micro slide switch * 2
- 18650 battery * 2
- nice!nano v2 * 2
- M3*8 heat set inserts * 16
- M3*6 flat head hex screw * 16

This board only uses 1u keycaps because
1. It's really hard to find keycap sets that come with enough 1.5u or 1.25u keys.
2. Thanks to the rise of popularity of ortholinear keyboards it's relatively easy to find good ortho sets and they usually comes with many extra/novelty caps.
3. Your milage may vary but I personally don't think >1u modifiers are necessary.

## Printing the case

Download the STL files from `stl` directory.

The case consists of two halves and a battery holder. They should be printed with the 'inside' facing build plate and with supports. Currently there's no cutout for physical reset buttons and power switches because ZMK supports sending reset/bootloader signal with key press. The left side face half comes with two versions, with or without encoder. Only left side because as of writing of this readme ZMK only supports encoders on the central side. The halves and battery holders are assembled with heat set inserts and screws.

**DO NOT** mirror face half and print them because you will mirror the switch pin holes and hotswap socket holes too. The back halves are fine.

#### Print setting suggestions

There are a lot of steep overhangs in the lower layers due to the print orientation. If your slicer supports it, it's better to print outer walls first to prevent warping which might result in small details in lower layers getting knocked off.  ("External pemimeters first" for Slic3r and forks and "Wall Ordering -> Outside to Inside" for Cura)

## Wiring

I don't know how to design a PCB so this is a hand wired build. It's basically a Redox layout with an encoder.

[schematic pic]

## Customizing

You might want to make your own keymap instead of using mine(which I guess only make sense to me). You can fork this repository and edit the .keymap file. ZMK utilize Github actions to compile firmwares so upon commit Github will automatically create firmware files with your keymap. You can find it in the actions tab to your repo -> `https://github.com/$your_username/$your_repo_name/actions`

To flash nice!nanos you need only to double click reset(or quickly bridge GND and RESET twice) and it will show up as a flash drive. You can then drop the `.uf2` files that you grabbed from Github to it and it's done.

Please refer to official ZMK documentations for more info.
https://zmk.dev/docs/user-setup
https://zmk.dev/docs/customization

## Credits

- Obviously, the layout and schematics are from [Redox keyboard](https://github.com/mattdibi/redox-keyboard)
- The design is inspired by and derived from [Redox Manuform by Fosk_LL](https://www.thingiverse.com/thing:3503380)
- The 18650 battery holder is modefied from [this design by YXC](https://www.thingiverse.com/thing:2847497)