+++
title = "First Steps with a Keyboard on ZMK"
tags = ["guide", "zmk"]
+++

This article provides a guide to help you take your first steps in mastering a keyboard on ZMK. After reading the article, the user will learn how to: manage the keyboard's power, connect the keyboard to multiple devices, and update the firmware.

## Connecting the Keyboard

Step 1. First, turn it on by switching the physical toggle to the "On" position.

![image](/images/zmk-keyboards/buttons.png)

Step 2. Next, the halves need to be connected to each other. To do this, simultaneously press the "Reset" button on the bottom of both halves.

Step 3. Once the keyboard is turned on and the halves are connected, you can proceed to connect it. First, make sure that the current connection profile is cleared by pressing `&BT_CLR` (in the default layout, the profile control keys are located on layer 3; you can switch to it by holding down the layer 1 and 2 switch keys). This will reset the devices bound to the profile.

![image](/images/zmk-keyboards/sel_clr.png)

Step 4. Next, to connect to a device via Bluetooth, you need to press the profile selection key, for example, `&BT_SEL 0`.

Step 5. After pressing, the keyboard will enter pairing mode and appear in the list of available devices for connection. Select it, and voila, everything works!

![image](/images/zmk-keyboards/connect.png)

> **P.S.** If the keyboard is not working correctly, for example, key presses from one half do not reach the device, you should repeat the procedure of connecting the halves by simultaneously pressing the `Reset` key on both.

## Connecting to Multiple Devices

For wireless connection, the keyboard can remember up to 5 devices. Each connected device is bound to the selected "profile" after connection.

To connect to the second device, press the `&BT_SEL 1` key, the keyboard will become available for pairing, connect to it from the device.

To reconnect to the first device, press `&BT_SEL 0`, the device will automatically see the keyboard and connect to it. Similarly, you can connect devices to profiles 3, 4, 5.

![image](/images/zmk-keyboards/sel.png)

## Battery Status

The current charge of the main (left by default) half is displayed in the OS, in the list of connected Bluetooth devices. It is not possible to see the charge status of the secondary (right by default) half; under normal conditions, this half discharges slower than the main one.

![image](/images/zmk-keyboards/power_level.png)

## Turning Off the Keyboard

You can turn off the keyboard with the [switch on the back of the keyboard](#connecting-the-keyboard) by switching it to the Off position, and you can also configure the shutdown directly on the keyboard key by assigning `&SOFT_OFF` to it. When this key is pressed, both halves of the keyboard will be switched to the off state. To wake it up, you need to press the `Reset` button on the bottom of the keyboard.

## Entering Sleep State

After 10 minutes of inactivity, the keyboard enters sleep mode to save power. To wake it up from sleep, simply press any key, and the keyboard will wake up in a couple of seconds.

## Wired Connection

When the keyboard is connected to a device with a wire, the keyboard automatically starts transmitting data via the wire. After disconnecting the wire, the keyboard will return to Bluetooth data transmission mode.

In situations where the keyboard is being charged from one device, but it is necessary to transmit data to another, you can press the `&OUT_BLE` key. This will forcibly switch the keyboard to Bluetooth transmission mode, and data will be sent to the device bound to the current profile.

![image](/images/zmk-keyboards/cables.jpg)

## Keyboard Firmware

Updating the keyboard firmware is done as follows:
1) Connect half of the keyboard with a wire;
2) Double-click the `Reset` key on the bottom of the keyboard (the pause between clicks should be minimal);
3) Similar to flashing keyboards on QMK, a new removable disk is detected in the PC, and the firmware file must be placed in it.

**Important!** The firmware of the halves have differences, and the left half must be flashed with a file whose name ends in `left.uf2`, and the right half with a file ending in `right.uf2`.

> You can switch the keyboard to firmware mode not only by double-clicking `Reset`, but also by pressing the `&bootloader` key. Pressing `&bootloader` switches only the half on which it was pressed to firmware mode.

More information in the ZMK documentation: https://zmk.dev/docs

![image](/images/zmk-keyboards/velvet.jpg)
