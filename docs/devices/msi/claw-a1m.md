title: MSI Claw A1M

<style>
  .nowrap {white-space: nowrap;}
</style>

# MSI Claw A1M

![](../../_inc/images/devices/msi-claw.png){ .off-glb }

!!! warning
    Support for this device is still a work in progress. Expect bugs or incomplete/missing features as support is being added.
    Refer to the [Known Issues](#known-issues) section for more information.

## Features

| Feature | Notes |
| -- | -- |
| <span class="nowrap">:material-harddisk: Storage</span> | SteamFork can be run from an SD Card, USB Drive or installed directly to the internal NVME. <br> When installed directly to the NVME; an SD Card can be used for game storage. |
| :material-wifi: Wifi | Can be turned on in Steam OS under Main Menu > Network. |
| <span class="nowrap">:simple-bluetooth: Bluetooth</span> | Supports bluetooth audio and controllers. |
| :material-fan: Fan | Controlled by system firmware. |
| <span class="nowrap">:material-lightning-bolt-circle: TDP Limit</span> | Can be set globally, per system or per game. Requires the [SimpleDeckyTDP](https://github.com/SteamFork/SimpleDeckyTDP) plugin. |
| <span class="nowrap">:material-vibrate: Rumble</span> | Enables the device rumble motor in emulators that support it. |

### Function Buttons

| Button | Function |
| -- | -- |
| ++"MSI Center"++ | <span class="nowrap">:material-microsoft-xbox: ++"Guide"++</span> (Steam Menu) |
| <span class="nowrap">++"Quick Settings"++</span> | <span class="nowrap">:material-microsoft-xbox: ++"Guide"++</span> + <span class="nowrap">:material-gamepad-circle-down: ++"A"++</span> (Quick Access Menu) |
| ++"M1"++ | <span class="nowrap">:material-gamepad-circle-down: ++"A"++</span> |
| ++"M2"++ | <span class="nowrap">:material-gamepad-circle-right: ++"B"++</span> |

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
* RGB currently cannot be controlled.
* Mangohud does not display CPU or GPU power draw and does not correctly display GPU usage.

### Booting from an external USB drive (USB or SD Card)

In order to boot SteamFork, Secure Boot will need to be disabled.

Power on the device and hold <span class="nowrap">++"RB"+"RT"++</span> until the BIOS appears.
Using the <span class="nowrap">:material-gamepad-round: ++"D-pad"++</span> and <span class="nowrap">:material-gamepad-circle-down: ++"A"++</span> or the touchscreen,
navigate to `Security`, select <span class="nowrap">`Secure Boot`</span>, <span class="nowrap">`Secure Boot Support`</span> and select `Disabled`.
Afterwards, navigate to <span class="nowrap">`Save & Exit`</span> and select <span class="nowrap">`Save Changes and Reset`</span>.

Once Secure Boot is disabled, power on the device and hold <span class="nowrap">++"LB"+"RB"++</span> until the Boot Menu appears.
Using the <span class="nowrap">:material-gamepad-round: ++"D-pad"++</span> and <span class="nowrap">:material-gamepad-circle-down: ++"A"++</span> or the touchscreen, select the storage device with SteamFork to boot the distribution.
