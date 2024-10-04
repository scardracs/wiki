# Antec Core HS

![](../../_inc/images/devices/ayaneo-slide.png){ .off-glb }

!!! warning
    Support for this device is still a work in progress. Expect bugs or incomplete/missing features as support is being added.
    Refer to the [Known Issues](#known-issues) section for more information.

!!!info
    New AMD 7000 series devices do not support S3 sleep and must be configured for Modern Standby + s0i3.
    Follow the [process on the Wiki](https://wiki.steamfork.org/troubleshooting/#enabling-modern-sleep-on-7000-series-amd-based-devices) to configure your device.

## Features

| Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Notes |
| -- | -- |
| :material-harddisk: Storage | SteamFork can be run from a USB Drive or installed directly to the internal NVME. 
| :material-wifi: Wifi | Can be turned on in Steam OS under Main Menu > Network Settings. |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers. |
| :material-fan: Fan | Controlled by system firmware. |
| :material-lightning-bolt-circle: TDP Limit | Can be set globally, per system or per game. Requires the [SimpleDeckyTDP](https://github.com/SteamFork/SimpleDeckyTDP) plugin.|
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |
| :material-lightbulb-on: RGB | Disabled on startup. Requires the [HueSync](https://github.com/honjow/HueSync) plugin for additional RGB control.|

## Notes

### Installation

Download the latest `AMD64` version of SteamFork from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/SteamFork/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/SteamFork/distribution/releases/latest)

### Known Issues

* An unknown issue exists that causes the device to reboot unexpectedly.  There is no notification or panic log.
* When Modern Standby is enabled, the power button does not send events to the OS.  Sleep works with Modern Standby + Si02 when selected from the Steam interface.

### Booting from an external drive (USB or SD Card)

To boot SteamFork from an external drive, hold ++"LC"+"Volume Up"++ and press the ++"Power"++ button, continue holding ++"LC"+"Volume Up"++ until the Ayaneo logo appears.  Select the storage device with SteamFork from the boot menu using the Ayaneo button, and then press volume up to boot the distribution.
