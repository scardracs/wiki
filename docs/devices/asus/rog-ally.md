title: ASUS ROG Ally / Ally X

# ASUS ROG Ally / Ally X

![](../../_inc/images/devices/asus-rog-ally.png){ .off-glb }

!!!info
    Some community members have been working with ASUS to solve the issue around Ally 1 and X having sometimes a faulty resume where the LED device of gamepad is missing. The fix has been found and is solved permanently in firmware. The Firmware is going through QA, and the estimated release date is October 16, 2024. To update your device you will require Windows (such as dual boot, or on a USB drive). There is an effort underway to reverse engineer the update protocol for use with fwupd.

## Features

| Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Notes |
| -- | -- |
| :material-harddisk: Storage | SteamFork can be run from an SD Card, USB Drive or installed directly to the internal NVME. <br> When installed directly to the NVME; an SD Card can be used for game storage. |
| :material-wifi: Wifi | Can be turned on in Steam OS under Main Menu > Network. |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers .|
| :material-fan: Fan | Managed by system firmware. |
| :material-lightning-bolt-circle: TDP Limit | Can be set globally, per system or per game. Requires the [SimpleDeckyTDP](https://github.com/SteamFork/SimpleDeckyTDP) plugin.|
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |

## Notes

### Installation

Download the latest `AMD64` version of SteamFork from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/SteamFork/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/SteamFork/distribution/releases/latest)

### Booting from an external drive (USB or SD Card)

To boot SteamFork from an external drive, hold :material-power: ++"Power"++ until the device powers on.
Release :material-power: ++"Power"++ and repeatedly tap :material-minus: ++"Volume Down"++ until the `Bios Utility` appears.

Using the :material-gamepad-round: ++"D-pad"++ and :material-gamepad-circle-down: ++"A"++ or the touchscreen, select `Boot Menu` and select the storage device with SteamFork to boot the distribution.
