# Build guide: solar garden light to MeshCore repeater

A step-by-step walkthrough of the build shown in the video. For the parts list and links, see the [README](README.md).

**Skill level:** basic soldering.
**Time:** <!-- TODO: how long it took --> about an afternoon.

> **Before you start**
> - The battery is a lithium cell. Don't short its wires together, and unplug it before you solder anything.
> - Solder in a ventilated space or use a fume extractor.
> - Your light may differ from ours. Check each wire with a multimeter before you connect it to the radio; don't rely on wire colors.

## Contents

1. [Open the light](#1-open-the-light)
2. [Unpack the MeshNode](#2-unpack-the-meshnode)
3. [Rewire the battery and switch](#3-rewire-the-battery-and-switch)
4. [Connect the solar panel](#4-connect-the-solar-panel)
5. [Connect the MeshNode and fit everything in](#5-connect-the-meshnode-and-fit-everything-in)
6. [Flash MeshCore](#6-flash-meshcore)
7. [Attach the antenna](#7-attach-the-antenna)
8. [Close the enclosure](#8-close-the-enclosure)
9. [Print the mount and hang it](#9-print-the-mount-and-hang-it)
10. [Check that it works](#10-check-that-it-works)

---

## 1. Open the light

<img src="images/01-solar-light.jpg" width="300" alt="The solar light: the panel on its swivel, the lamp head cut open, and the ground stake">
<img src="images/02-enclosure-open.jpg" width="300" alt="The solar light opened up, showing the charge board and wires inside">

1. Switch the light off.
2. Remove the screws from the back of the housing and lift it apart.
3. Unplug or remove the battery.
4. Identify what's inside: the solar panel leads, the battery bay and its connector, the small charge board, the power switch, and the LED board.

Only the top section of the light is used for the repeater. The LED part is not needed.
<!-- TODO: say what you did with the LED board and lens: removed, unplugged, or left in place. -->

<img src="images/03-solar-panel.jpg" width="300" alt="The solar panel section of the light">

## 2. Unpack the MeshNode

<img src="images/04-meshnode-box.jpg" width="300" alt="The Mesh Node T096 kit in its case">
<img src="images/05-meshnode-board.jpg" width="300" alt="The Heltec T096 MeshNode board held in hand">
<img src="images/kit-contents.jpg" width="300" alt="The kit laid out: the board in its case, with the cables and small parts">

The Heltec T096 MeshNode kit includes the board with its screen and a few accessories.

- **It has two radios:** LoRa for the mesh, and Bluetooth for setting it up from a phone.
- **The kit includes a GPS antenna.** A fixed repeater doesn't need it, so leave it out.
- **Never power the board without a LoRa antenna attached.** Transmitting with no antenna can damage the radio.

## 3. Rewire the battery and switch

<img src="images/06-housing-halves.jpg" width="300" alt="Both halves of the housing on the bench: the battery bay with the charge board, and the lid with wires coming through">
<img src="images/07-battery-wires.jpg" width="300" alt="Battery connector wires coming through the housing">
<img src="images/battery-bay.jpg" width="300" alt="Inside the battery compartment: the spring contacts and the wires soldered to them">
<img src="images/second-build-wiring.jpg" width="300" alt="Both halves of our second build wired up before assembly (this one used red and blue wire)">

1. Desolder the light's existing battery wires.
2. Solder short wires from the battery connector to the power switch, so the switch turns the whole repeater on and off.
3. Slide heat shrink onto each wire **before** soldering, then shrink it over the finished joint.

<img src="images/08-joining-wires.jpg" width="300" alt="Joining two wires in a helping-hands clamp, with heat shrink already on the wire">

<!-- TODO: add the exact connections, for example:
     battery connector + (which color) -> switch terminal ...
     switch other terminal -> ...
     battery connector - (which color) -> ...
     A simple wiring diagram or a labelled photo here would help more than anything else in this guide. -->

On ours, the battery connector wires are yellow and white. Yours may differ, so confirm which is positive with a multimeter.

## 4. Connect the solar panel

<img src="images/09-soldering-charge-board.jpg" width="300" alt="Soldering a wire to the light's small charge board under the fume extractor hood">
<img src="images/charge-board-wired.jpg" width="300" alt="The charge board with its wires soldered on">

Solder the solar panel leads so the panel charges the battery.

<!-- TODO: say where the panel connects in your build. The light has its own small charge board and the Heltec board has charging built in. State which one you used, whether the light's charge board stayed in the circuit, and which pads the wires go to. -->

Tip: we kept the light's existing leads and joined the new connector wires to them, which is easier than soldering directly to the small pads.

## 5. Connect the MeshNode and fit everything in

<img src="images/10-fitting-board.jpg" width="300" alt="Pressing the MeshNode and battery into the housing">
<img src="images/11-assembled-interior.jpg" width="300" alt="The MeshNode, battery and charge board fitted inside the housing">
<img src="images/running-on-battery.jpg" width="300" alt="The MeshNode powered from the light's battery, screen on">

1. Plug the battery connector into the MeshNode's battery socket. **Check polarity first**: the connector on your wires must match the + and − markings on the board.
2. Seat the battery in its bay.
3. Lay the MeshNode beside it, with the USB-C port reachable so you can flash it.
4. Tuck the wires so nothing is pinched when the housing closes. A dab of hot glue keeps the boards from moving.

<!-- TODO: confirm how the board is held in place (hot glue, tape, printed bracket). -->

## 6. Flash MeshCore

<img src="images/13-flashing.jpg" width="300" alt="The MeshCore web flasher showing 'Flashing' on a laptop">

1. Connect the MeshNode to your computer with a USB-C cable.
2. Open the MeshCore web flasher: <https://meshcore.io/flasher> <!-- TODO: confirm this is the address you used -->
3. Choose **Heltec Mesh Node T096** as the device.
4. Choose **Repeater** as the firmware type.
5. Put the board into update mode: **double-click the bottom button**, the one to the left of the screen under the USB port. The screen changes to a DFU page.

   <img src="images/12-button.jpg" width="300" alt="Pressing the bottom button on the MeshNode">

6. Click **Flash** and select the board when the browser asks.
7. Wait for **Flashing complete!** Don't unplug the board while it's working.

<img src="images/14-flashing-complete.jpg" width="300" alt="The flasher showing 'Flashing complete!'">

The board restarts and its screen shows that it's running.

<img src="images/15-screen-on.jpg" width="300" alt="The MeshNode screen lit up inside the enclosure after flashing">

<!-- TODO: add the repeater settings you chose after flashing: name, radio region or frequency preset, and anything else you set from the "Configure via USB" button or the phone app. Readers need the same radio settings as the other repeaters in their area. -->

## 7. Attach the antenna

<img src="images/16-antenna-cable.jpg" width="300" alt="The antenna cable plugged into the MeshNode inside the housing">
<img src="images/17-antenna.jpg" width="300" alt="The antenna cable running out to the antenna connector">
<img src="images/coax-through-housing.jpg" width="300" alt="The antenna cable passing through the hole in the housing, beside the battery">
<img src="images/antenna-connector.jpg" width="300" alt="The antenna pigtail and its threaded connector, with the housing hole it fits">

1. Connect the antenna pigtail cable to the LoRa antenna socket on the MeshNode.
2. Feed the connector through the existing hole in the housing. On our light the antenna connector fits the hole that was already there.
3. Tighten the nut, then screw on the omnidirectional antenna.

<!-- TODO: say which hole you used and whether you added any sealant or a gasket around it. -->

## 8. Close the enclosure

<img src="images/18-screws.jpg" width="300" alt="Screwing the housing closed">
<img src="images/closed-with-mount-parts.jpg" width="300" alt="The closed housing with the mount parts beside it">

1. Check that the original gasket is seated all the way around.
2. Make sure no wire crosses the sealing edge.
3. Switch the repeater on.
4. Refit the back and tighten the screws evenly.

## 9. Print the mount and hang it

<img src="images/19-mount.jpg" width="300" alt="Fitting the mount hardware to the closed housing">
<img src="images/20-finished.jpg" width="300" alt="The finished repeater with antenna attached">

1. Print the mount from [The People's Repeater on Printables](https://www.printables.com/model/1768397-the-peoples-repeater-affordable-solar-mesh-repeate).
   <!-- TODO: material and print settings you used. For outdoor use, PETG or ASA holds up better in sun than PLA. -->
2. Attach the housing to the mount.
3. Hang it as high as you can, with the solar panel facing the sun and the antenna vertical and clear of metal.

## 10. Check that it works

1. From another MeshCore device, or the MeshCore phone app, look for your repeater by name.
2. Tell the repeater to send an advertisement and confirm the other device sees it.
3. Leave it outside for a few days and check that the battery holds through the night.

<!-- TODO: add your own results once it has been outside: range, battery behaviour, anything you would change. -->

---

## Troubleshooting

| Problem | Things to check |
|---|---|
| The board doesn't appear in the flasher | Use a USB-C cable that carries data, not a charge-only one. Use a browser that supports Web Serial, such as Chrome. Double-click the bottom button again to re-enter update mode. |
| The screen stays dark on battery | Is the switch on? Is the battery charged? Is the battery connector polarity correct? |
| The battery doesn't charge | Check the solar panel joints, and measure the panel's voltage in direct sun. |
| Other nodes can't hear it | Confirm the antenna is on the LoRa socket and the radio settings match your local mesh. |

Found a mistake or a better way? Open an issue on this repository.
