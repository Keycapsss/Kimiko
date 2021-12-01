# Kimiko

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/firstcontributions/first-contributions)
[![Discord](https://img.shields.io/discord/548530462419582996?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/frjFXZB "Redirect to Keycapsss Discord")
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

- Aggressive staggered pinky rows
- Support for one rotary encoder per side (two possible positions)
- Per key RGB led with SK6812 Mini-E led (with legs, easy to solder)
- Support for MX switches (Hotswap sockets)

**[Build-Guide](buildguide_en.md)**

**[Keymap-Guide](Keymap.md)**

**Hardware available at [keycapsss.com](https://keycapsss.com)**

![Kimiko keyboard with RGB LED](https://keycapsss.com/media/image/g0/9e/1f/kimiko-split-keyboard-1vUUb4KAeC3ojx_1280x1280.jpg)

## Parts

Part name | Quantity | Remarks | Photo |
| ------- | -------- | ------- | ----- |
| Kimiko PCB | 1 set ||
| Kimiko case | 1 set | 2 solid panels, 2 with holes for switches (plates) |
| [Pro Micro](https://keycapsss.com/keyboard-parts/parts/79/arduino-pro-micro-atmega32u4-controller) or [Puchi-C](https://keycapsss.com/keyboard-parts/parts/141/puchi-c-pro-micro-replacement-with-usb-c-and-atmega32u4) | 2 pcs (a mix is possible) | Recommend to  use [Mill-Max Single Row Socket Headers](https://keycapsss.com/keyboard-parts/parts/100/single-row-socket-headers-pins-mill-max-series-315), to make it hot-swappable. ||
| Key switch (MX) | 58-60 pcs |  ||
| [Kailh switch socket](https://keycapsss.com/keyboard-parts/parts/49/kailh-hot-swap-pcb-sockets-10-pcs) | 58-60 pcs |  ||
| Diodes 1N4148W (SMD) | 60 pcs |||
| TRRS jack | 2 pcs ||
| Tactile switch | 2 pcs | Reset switch ||
| TRRS cable | 1 cable | Must be a 4-pole cable ||
| Key caps | 58-60 pcs | 1.5U caps, can also be 1U ||
| Micro USB or USB-C cable | 1 pcs | Dependent what you use on the master half. ||

## Optionally

Part name | Quantity | Remarks | Photo |
| ------- | -------- | ------- | ----- |
| [OLED module](https://keycapsss.com/keyboard-parts/parts/80/ssd1306-oled-lcd-display-0.91-inch-128x32-i2c-white) | 2 pcs | It is possible to use only one display ||
| SK6812 Mini-E | 60 pcs |RGB LEDs for keycap backlight **(underglow LEDs must be soldered, because they are connected in series)** ||
| [Rotary encoder](https://keycapsss.com/keyboard-parts/parts/59/rotary-encoder-with-switch) |0-2 pcs| One per side are supported. |
| [Mill-Max Single Row Socket Headers](https://keycapsss.com/keyboard-parts/parts/100/single-row-socket-headers-pins-mill-max-series-315), or [Spring-loaded pin headers](https://keycapsss.com/keyboard-parts/parts/91/spring-loaded-pin-headers-12-pin-2pcs-conthrough), | 4 x 12 row headers | To make pro micro Hot-swappable. Highly recommended to get the header pins too (You can use diode legs if you don't get the header pins)|

## Case files

Drawings (SVG, DXF) for the case are located in the [plates folder](plates/).

## Firmware

Clone/download the QMK firmware and execute the following in the [qmk_firmware](https://github.com/qmk/qmk_firmware) directory to write the default Lily58L keymap

    make keycapsss/kimiko:default:avrdude (for pro micro) 

When **`Detecting USB port, reset your controller now...`** is displayed, press the reset button on the keyboard to start writing.
Each half of the keyboard must be programmed separately using this approach.

If you're using DFU bootloader (in case of the Puchi-C or Elite-C), replace the 'avrdude' with 'dfu'
