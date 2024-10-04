# MSI Claw A1M

![](../../_inc/images/devices/msi-claw.png){ .off-glb }

!!! warning
    Support for this device is still a work in progress. Expect bugs or incomplete/missing features as support is being added.

## Features

| Feature | Notes |
| -- | -- |
| :material-harddisk: Storage | SteamFork can be run from an SD Card, USB Drive or installed directly to the internal NVME. <br> When installed directly to the NVME; an SD Card can be used for game storage. |
| :material-wifi: Wifi | Can be turned on in Steam OS under Main Menu > Network. |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers. |
| :material-fan: Fan | Controlled by system firmware. |
| :material-lightning-bolt-circle: TDP Limit | Can be set globally, per system or per game. Requires the [SimpleDeckyTDP](https://github.com/SteamFork/SimpleDeckyTDP) plugin. |
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |

### Function Buttons

| Button | Function |
| -- | -- |
| ++"MSI Center"++ | :material-microsoft-xbox: ++"Guide"++ |
| ++"Quick Settings"++ | :material-microsoft-xbox: ++"Guide"++ + :material-gamepad-circle-down: ++"A"++ (Quick Access Menu) |

## Notes

### Installation

Download the latest `AMD64` version of SteamFork from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/SteamFork/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/SteamFork/distribution/releases/latest)

### Known Issues

* Sleep currently does not work properly.  Attempting to sleep will break some controls until the device is powered off with external power removed.
* WiFi performance can be erratic at times.
* Sound occasionally becomes glitchy or stops working altogether until the device is rebooted.
* Sound currently does not work over HDMI.
* Game support is currently hit-or-miss.  DirectX 12 may be especially problematic.
* Built-in controls currently cannot be recalibrated.
* Paddle buttons currently cannot be remapped.

### Booting from an external USB drive (USB or SD Card)

In order to boot SteamFork, Secure Boot will need to be disabled.

Power on the device and hold ++"RB"+"RT"++ until the BIOS appears.
Using the :material-gamepad-round: ++"D-pad"++ and :material-gamepad-circle-down: ++"A"++ or the touchscreen, navigate to `Security`, select `Secure Boot`, `Secure Boot Support` and select `Disabled`.
Afterwards, navigate `Save & Exit` and select `Save Changes and Reset`.

Once Secure Boot is disabled, power on the device and hold ++"LB"+"RB"++ until the Boot Menu appears.
Using the :material-gamepad-round: ++"D-pad"++ and :material-gamepad-circle-down: ++"A"++ or the touchscreen, select the storage device with SteamFork to boot the distribution.
