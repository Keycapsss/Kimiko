# Kimiko Build Guide

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/firstcontributions/first-contributions)
[![Discord](https://img.shields.io/discord/548530462419582996?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/frjFXZB "Redirect to Keycapsss Discord")
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

## Required tools

![Required tools for soldering](img/required-tools-1.jpg)

* Soldering iron with adjustable temperature
* Solder (i use Sn99.3Cu0.7 0.5mm/0.02inch)
* Tweezers for the small SMD parts
* Tip cleaner (wet sponge or brass wool)
* Side cutters/flush cutters
* Fine pliers

Most parts I solder at 320-340°C. The SMD LEDs are temperature sensitive, so lower the temperature to 300-320°C.

### How to solder tips

![How to THT soldering](img/soldering-hints-1.png)
*[adafruit](https://github.com/adafruit/Reference-Cards)  CC-BY-SA 4.0*

![How to THT soldering](img/soldering-hints-3.jpg)
*Source: [adafruit](https://learn.adafruit.com/adafruit-guide-excellent-soldering/common-problems)*

![How to SMD soldering](img/soldering-hints-2.png)
*[Timo Schindler](https://github.com/marove2000/referenceCards)  CC-BY-SA 4.0*

## BOM

![Kimiko Parts](img/kimiko-parts-1.jpg)

### Required parts

Part name | Quantity | Remarks | Photo |
| ------- | -------- | ------- | ----- |
| Kimiko PCB | 2 pcs | PCB is reversible |
| Kimiko case | 1 set | 2 solid panels, 2 plates, and screws/spacer |
| [Pro Micro](https://keycapsss.com/keyboard-parts/parts/79/arduino-pro-micro-atmega32u4-controller) or [Puchi-C](https://keycapsss.com/keyboard-parts/parts/141/Puchi-C-pro-micro-replacement-with-usb-c-and-atmega32u4) | 2 pcs (a mix is possible) | I highly recommend, use [Mill-Max Single Row Socket Headers](https://keycapsss.com/keyboard-parts/parts/100/single-row-socket-headers-pins-mill-max-series-315), or [Spring-loaded pin headers](https://keycapsss.com/keyboard-parts/parts/91/spring-loaded-pin-headers-12-pin-2pcs-conthrough), to make it Hot-swappable. ||
| Key switch (MX) | 58-60 pcs | 60 if you do not install the rotary encoder. 3-Pin and 5-Pin switches are supported.  ||
| [Kailh MX switch socket](https://keycapsss.com/keyboard-parts/parts/49/kailh-hot-swap-pcb-sockets-10-pcs) | 58-60 pcs |  ||
| Diodes 1N4148W (SMD SOD-123/SOD-123FL) | 60 pcs |||
| TRRS jack | 2 pcs ||
| Tactile switch | 2 pcs | Reset switch ||
| TRRS cable | 1 cable | Must be a 4-pole cable ||
| Key caps | 58-60 pcs | Keycap for the thumb switch can be a 1.5U, or a 1U keycap. ||
| Micro USB or USB-C cable | 1 pcs | Dependent what you use on the master half (Pro Micro = Micro USB / Puchi-C = USB-C). ||

### Optionally parts

Part name | Quantity | Remarks | Photo |
| ------- | -------- | ------- | ----- |
| [Rotary encoder](https://keycapsss.com/keyboard-parts/parts/59/rotary-encoder-with-switch) |0-2 pcs| One per side are supported. |
| [OLED 0.91 module](https://keycapsss.com/keyboard-parts/parts/80/ssd1306-oLED-lcd-display-0.91-inch-128x32-i2c-white) | 0-2 pcs | It is possible to use only one display. ||
| [SK6812 Mini-E LEDs](https://keycapsss.com/keyboard-parts/parts/114/sk6812-mini-e-rgb-smd-LED) | 60 pcs |RGB LEDs for the keycap backlight. **Also the LEDs under the encoder must be soldered, because they are wired in series.** ||
| [Mill-Max Single Row Socket Headers](https://keycapsss.com/keyboard-parts/parts/100/single-row-socket-headers-pins-mill-max-series-315), or [Spring-loaded pin headers](https://keycapsss.com/keyboard-parts/parts/91/spring-loaded-pin-headers-12-pin-2pcs-conthrough), | 4 x 12 row headers | To make pro micro Hot-swappable. Highly recommended to get the header pins too (You can use diode legs if you don't get the header pins)|

## Introduction

**Note: please be careful, as the case will be scratched if it hits or rubs a hard thing after assembly.**

This PCB is reversible. We will mount parts **on each side.**

Mark the surface with masking tape to make it easy to keep track of the back and front of each board.

The pictures in this guide show the PCB for the left side.

## Attach the diodes

The diodes are mounted on the **back side** of the board.

Pay attention to orientation, diodes are polarized. If the orientation is incorrect, the key will not respond.

Solder the diode as shown in the following figure.

![SMD Diode orientation](img/smd-diode-direction-1.png)

Apply preliminary solder (melt a small amount on the substrate/"tin the pad") on one pad of the PCB diode.

![SMD diode orientation](img/smd-diode-solder-1.jpg)
*PCB back side (left half)*

Then use tweezers to slide the diode into position, whilst you heat the pre-soldered pad.
Remove the soldering iron and allow to cool, whilst still holding the diode.

Then solder the remaining side.  
When all diodes have been soldered, check for missing spots.

![Soldering diodes](img/smd-diode-solder-2.jpg)
*PCB back side (left half)*

You can use a multimeter in "diode mode", on the front side of the board to ensure that the solder connections are good and that the orientation of the diodes is correct.

![Soldering diodes](img/smd-diode-solder-3.jpg)
*All diodes soldered on back side (left half)*

## Solder the LEDs for keycap back (optionally)

Solder the SK6812 Mini-E LEDs (with legs), on the **back side** of the board.  
**Pay attention to orientation of the LEDs** (the angled leg of the led should be soldered to the pad of the PCB with the slanted white mark)**.**

We solder LEDs using the same approach as for the diodes.
Begin by pre-soldering one side of the LED pad.

![SK6812 Mini-E soldering](img/sk6812-mini-e-led-1.jpg)

Place the component, and hold it in place with tweezers.  

![SK6812 Mini-E soldering](img/sk6812-mini-e-led-2.jpg)

Then solder the other pads.

![SK6812 Mini-E soldering](img/sk6812-mini-e-led-3.jpg)

**It is necessary to solder all LEDs, even if you use the rotary encoder.**

For the LEDs it's important to keep the heating as short as possible. Try to not touch the plastic of the LED itself with the iron but only the the metal legs. Use flux if you are having difficulty.
The LEDs are connected in series. If a LED is broken or has bad solder connections, the following LEDs will either not light up at all or will light up in a different color than the default (red).
Doublecheck the last LED that lights up properly and the first that doesn't.  
On the LEDs with legs it's easily possible to get a loose connection.

## Soldering the TRRS jack and reset switch

The TRRS jack and the reset switch are mounted on the **front side** (opposite side of diodes).
Attach the parts and fix them temporarily with masking tape. Turn over the board and solder the pins, making sure that the TRRS jack and reset switch are in firm contact with the board.

![TRRS jack and reset button](img/trrs-jack-reset-button-1.jpg)
*PCB front side (left half)*

**Be careful** Double check your part orientation before you commit to soldering. A mistake here can mean painful desoldering experiences.

## Attach the OLED socket

On the **front side** of the board, apply enough solder to bridge the four jumper terminals in the Pro Micro section.

![Oled jumper pads](img/oled-jumper-pins-1.jpg)
*PCB front side (left half)*

Attach the connector for the OLED on front side (opposite side of diodes). Be careful to avoid adding a lot of solder, as it is easy for solder to flow into the connector. Make sure it is straight and at a right-angle to the PCB.

## Install Pro Micro (with sockets)

### Check Pro Micro by flashing

**Before installing the Pro Micro, no matter which (can also happen on the Puchi-C), check whether they are working by plugging them in and [flashing the default keymap](#flash-keymap-on-pro-micropuchi-c).**

Open [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases/latest) and connect your Pro Micro/Puchi-C to the computer.  
If your Pro Micro/Puchi-C is complete new (without a firmware on it), a message *"***Atmel DFU device connected: ..."* should appear.  

If the message does not appear, press the reset button on the Puchi-C, or short RST & GND pins on the Pro Micro to bring it into the DFU mode. (For first timers you can short using a wire and touching an end each to RST & GND pins while the pro micro is plugged in)
If the message appears, the device should be working correctly.

![QMK toolbox](img/puchi-c-working-test-1.jpg)

### Install onto PCB

You have 3 options:

* Use the pin headers enclosed in the bag of Pro Micro
* Use Mill-Max sockets and Mill-Max headers
* Use Mill-Max sockets with diode legs

For other ways to mount your Pro Micros, look at [the crkbd build guide.](https://nicedoc.io/foostan/crkbd/blob/master/corne-classic/doc/buildguide_en.md#using-pin-sockets)

### Using Pin header enclosed

The pin header enclosed in the bag of Pro Micro can be used. But I highly recommend using the Mill-Max socket headers, or Spring-loaded pin headers. With the Mill-Max header it's easier to replace the Pro Micro, if it's broken. (Especially the Pro Micros- the USB port will break at some point!)

![Standard header/ Mill-Max socket header](img/mill-max-12-single-row-socket-1.jpg)
*Standard headers vs Mill-Max sockets. Note the standard header pins will NOT fit into the Mill-Max sockets. You have to get Mill-Max headers or use diode legs*

1. Note the **outlined sets of holes in PCB,** and insert the Standard header into the outlined holes on the **front side**. Please be careful, as the **connections are different for the right and left boards.** See the image in step 1 of [Mill-Max section](#use-mill-max-sockets-and-mill-max-headers) for a reference.
2. Solder the Standard header from the **back side** and pay attention to not creating solder bridges between the different sets of holes.
3. Place the Pro Micro/Puchi-C on top of the headers on the **Front side**. **(USB socket facing down)**.
![Mill-Max sockets](img/mill-max-12-single-row-socket-6.jpg)
4. Solder the Pro-Micro in place

Go to [Install the OLED on the socket](#install-the-oled-sd1306-on-the-socket)

### Use Mill-Max sockets and Mill-Max headers

1. Note the **outlined sets of holes in PCB,** and insert the Mill-Max sockets into the outlined holes on the **front side**. Please be careful, as the **connections are different for the right and left boards.**
![Pro Micro_PCB](img/pro-micro-solder-location-1.jpg)
*PCB front side (left half)*
2. Solder the Mill-Max sockets from the **back side** and pay attention to not creating solder bridges between the different sets of holes.
3. Insert the Mill-Max pins with pliers into the sockets.
![Mill-Max sockets](img/mill-max-12-single-row-socket-5.jpg)
*Example image with Mill-Max sockets*
4. Place the Pro Micro/Puchi-C on top of the headers on the **Front side**. **(USB socket facing down)**.
![Punchi-C Placement](img/mill-max-12-single-row-socket-6.jpg)
*Puchi-C Placement*
5. Solder the pins.

Go to [Install the OLED on the socket](#install-the-oled-sd1306-on-the-socket)

### Use Mill-Max sockets with diode legs

1. Note the **outlined sets of holes in PCB,** and insert the Mill-Max sockets into the outlined holes on the **front side**. Please be careful, as the **connections are different for the right and left boards.**
![Pro Micro_PCB](img/pro-micro-solder-location-1.jpg)
*PCB front side (left half)*
2. Solder the Mill-Max sockets from the **back side** and pay attention to not creating solder bridges between the different sets of holes.
3. Optional but highly recommended: Cover the sockets with heat resistant tape (scotch tape or electrical tape). This will prevent the solder seeping into the sockets which will make it practically impossible to remove the pro-microsocket
![Pro Micro with tape](img/pro-micro-tape-diode-legs-1.jpg)
*Example with tape*
4. Insert the diodes legs with pliers or tweezers into the sockets. You should hear/feel 2 'clicks' Once when it puches through the tape and the second when it engages into place on the Max-Mill socket. Do not use your hands as the diode legs can be sharp
![Mill-Max sockets](img/mill-max-12-single-row-socket-2.jpg)
*Example image with diode legs*
5. Place the Pro Micro/Puchi-C **(USB socket facing down)**.
![Diode legs 1](img/mill-max-12-single-row-socket-3.jpg)
*Pro Micro placement with diode legs*
6. Solder the pins. Shorten the pins with side cutters/flush cutters
![Diode legs 2](img/mill-max-12-single-row-socket-4.jpg)
*Time to snip*
7. You should be able to slowly wedge off the pro micro from the Max-Mill sockets using tweezers and a bit of levering from the top and bottom of the pro micro. Take off the tape.
![Pro Micro Removed](img/pro-micro-wedgin-1.jpg)
*Pro Micro levered off the pins. Now time to remove tape*

## Install the OLED (SD1306) on the socket

Remove the black plastic spacer that's part of the header installed in the OLED. Then you'll be able to shorten it's legs with your pliers and put them into the socket, resulting into a way more low profile OLED. You can wiggle it off with pliers carefully.

![Oled SD1306 shorten pins](img/oled-shorten-pins-sd1306-1.jpg) ![Oled SD1306 shorten pins](img/oled-shorten-pins-sd1306-2.jpg)

## You have reached a checkpoint

Plug your keyboard (**do not plug-in or remove the TRRS cable, while a Pro Micro is connected via USB**), look what happens, solve problems, be happy if there are none (if you followed all the steps your pro micros should have [firmware](#flash-keymap-on-pro-micro) at this point).  

By now you can also checked whether all switches will be able to work. In order to do so, open the [QMK Test Site](https://config.qmk.fm/#/test), short the pads on which the kailh sockets will be installed (next step) with tweezers.

See [Troubleshooting](#troubleshooting) if anything is not working

![Tweezers test switch](img/kailh-socket-pad-test-1.jpg)

## Solder the sockets

The sockets are mounted on the **back side**, the same side as the diodes.

Much like the approach used for the diodes above, begin by pre-soldering one side of the socket pad.

![Solder Kailh Hotswap sockets](img/solder-kailh-mx-sockets-1.jpg)

Place the component, and hold it in place with tweezers. (The sockets can also be held in place by hand, but please take extra care not to burn yourself.)

![Solder Kailh Hotswap sockets](img/solder-kailh-mx-sockets-2.jpg)

> The sockets take **way** more solder than the other components like the LEDs and the diodes. But don't exaggerate...

## Case assembly

![case parts overview](img/case-all-parts-1.jpg)

### Attach the spacer

Attach two **10mm spacers** to the holes near TRRS jack with the **5mm screws**.
It's easy to insert a screw from the back of the board and attach the spacer from the top.

![Spacer for oled guard plate](img/case-spacer-guard-plate-1.jpg)

Attach the **7mm spacer** to the top plate. If your kit comes with washers attached those to the spacers (They will hold the top plate slightly off the PCB)

![Top plate 7mm spacer](img/case-top-plate-spacer-1.jpg)

![Top plate washer](img/case-top-plate-washer-1.jpg)
*Spacer washer for acrylic case (not necessary for FR4 plate case).*

### Prepare the rotary encoder

Remove the alignment legs on the rotary encoder with diagonal pliers.

![Rotary encoder cut legs](img/rotary-encoder-cut-legs-1.jpg)

If your rotary encoder has a metal surface at the bottom, cover it with some isolation tape, to prevent shorts on the LED pads.

![Rotary encoder isolation tape](img/rotary-encoder-isolation-tape-1.jpg)

You can place one encoder per side, or leave it empty and place a switch at this position.

![Rotary encoder position](img/rotary-encoder-position-1.jpg)

**Do not solder the rotary encoder at this point.** If it sits loose on the mid pcb, the clearance helps that the encoder fits in the top plate hole.

![Rotary encoder positions](img/rotary-encoder-position-2.jpg)

### Attach the key switch

Attach four key switches to the top plate. The hole for the switch led is facing down.

![Top plate with 4 switches](img/case-top-plate-spacer-switches.jpg)

It's important that the switch pins are not bend.

![Switch pin align](img/switch-pins-align-1.jpg)

Insert the switch into the board for alignment, and line up the components.

![Top plate](img/case-top-plate-align-2.jpg)
![Top plate align](img/case-top-plate-align-1.jpg)

After confirming that there are no bends in the switch pins, you can attach it firmly by starting from the middle row and working outward.
Be careful: some switches require some power for installation.
Always be careful to put the switches in nice and straight, otherwise you'll bend the pins and scratch the PCB.
After mounting the plate, push the switches again to make sure that installation is complete.

![Top plate complete with switches](img/case-top-plate-complete-1.jpg)

Confirm that the rotary encoder sits straight on the PCB.  
Solder the 5 points.

![Solder the rotary encoder](img/rotary-encoder-solder-1.jpg)

Soldering the rotary encoder is as simple as any other component. Put the encoder from the front into the holes on the PCB, just below the screen, and solder it from the back.

**Tip** Depending on your case you should first try and bend the rotary encoder legs a bit before soldering it in. The legs can prevent your case from closing completly, as it will rest on the protruding legs. Bending the pins so that they are flush with the encoder helps here. (you can also just clip them off)

> **For your information.** The top **two** legs serve as a simple connection that is closed by the rotary encoders tactile press. It's connected to the pins a switch would be connected to, if there were on in the place of the rotary encoder. Therefore, in your firmware the rotary encoder will behave as a normal keyswitch in the matrix.

The lower three pins do the actual rotary-encoding part

### Pro Micro protective acrylic installation

Peel off the protective plastic layer covering the acrylic.  
Antistatic spray helps to counteract that the cover is a dust magnet. I use [Velind Antistatik Spray](https://amzn.to/2ZMTz93)**affiliate link*

![Guard plate protective film](img/guard-plate-2.jpg)

Attach the acrylic plate to the board with 5mm screws.

![Guard plate](img/guard-plate-3.jpg)
![Guard plate](img/guard-plate-1.jpg)

### Assemble the bottom plate

To complete the case, attach the bottom plate with 5 screws and stick the 4 rubber feeds to the corners.

![Bottom plate](img/case-bottom-plate-1.jpg)

Your Kimiko keyboard is now complete.

![Proud](https://media.giphy.com/media/PudZiAbQDUEik/giphy.gif)

## Flash keymap on Pro Micro/Puchi-C

The board requires a [keymap](https://github.com/qmk/qmk_firmware/tree/master/keyboards/keycapsss/kimiko) in order to function. This section assumes that you're familiar with keymaps and the use of the QMK tool. If not, please refer to [the QMK "Getting Started" guide](https://docs.qmk.fm/#/getting_started_build_tools) (Windows: MSYS2; Mac, Linux: avrdude)

The [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases) can be used to write non-customized keymaps via a GUI, avoiding the need to configure a local QMK environment. (For custom keymaps/rotary encoder behavior, it's recommended to build the full environment described above).

Clone/download the QMK firmware and execute the following in the [qmk_firmware](https://github.com/qmk/qmk_firmware) directory to write the default Lily58L keymap

```bash
make keycapsss/kimiko:default:avrdude
```

When **`Detecting USB port, reset your controller now...`** is displayed, press the reset button on the keyboard to start writing.
Each half of the keyboard must be programmed separately using this approach.

If you're using DFU bootloader (in case of the Puchi-C/Elite-C), replace the `avrdude` with `dfu`.

### Congratulations 🥳

If everything works: You have built your Kimiko. Have fun!
[If something doesn't work](#troubleshooting)

## Customize the default keymap

**[Keymap-Guide](Keymap.md)**

## Troubleshooting

### Q. One or more rows/columns of key switches do not respond

A. The Pro Micro board may not be soldered and attached firmly. Check again, and re-solder and reinstall if necessary.

### Q. A single key switch doesn't respond

A. There may be a problem with the key switch's insertion, socket or diode soldering.

In the case of bad key switch insertion:
After removing the key switch, make sure that the pins aren't bent, and then push it in again and install it.

In the case of badly attached socket:
Re-solder the problem socket, or reflow and add solder if the joint is weak.
  
In the case of badly attached diode:
Check the [direction of the diode](#attach-the-diodes) in question. If it is wrong, remove it and re-solder it. Additionally, if there isn't enough solder, please re-solder.

### Q. Both half‘s are working as single, but if i connect them via TRRS cable one side is not working.

A. Check the TRRS jack solder points for bridges or cold solder points.

The TRRS cable should have 4 poles.

Use a multimeter to check the cable. Each pole should only have connection to the opposite pole.

### Q. One side does not respond.

A. Check if all LED‘s have the correct orientation.

### Q. A symbol different from the symbol input by "@" or "[" etc. is input (on Windows, etc.)

A. Please set OS Keyboard Layout as a US keyboard in the OS keyboard settings.

**If you have any problems, please feel free to send a message on Discord (<https://discord.gg/frjFXZB>) or Twitter: [@keycapsss](https://twitter.com/keycapsss)**
