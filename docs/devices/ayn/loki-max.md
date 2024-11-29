title: AYN Loki Max

<style>
  code {white-space: nowrap;}
  kbd {white-space: nowrap;}
  no-wrap {white-space: nowrap;}
</style>

# AYN Loki Max

![](../../_inc/images/devices/ayn-loki.png){ .off-glb }

## Features

| Feature | Notes |
| -- | -- |
| <no-wrap>:material-harddisk: Storage</no-wrap> | SteamFork can be run from an SD Card, USB Drive or installed directly to the internal NVME. <br> When installed directly to the NVME; an SD Card can be used for game storage. |
| <no-wrap>:material-wifi: Wifi</no-wrap> | Can be turned on in Steam OS under `Main Menu` > `Network Settings`. |
| <no-wrap>:simple-bluetooth: Bluetooth</no-wrap> | Supports bluetooth audio and controllers. |
| <no-wrap>:material-fan: Fan</no-wrap> | Managed automatically. |
| <no-wrap>:material-lightning-bolt-circle: TDP Limit</no-wrap> | Can be set globally, per system or per game. Requires the [SimpleDeckyTDP](https://github.com/SteamFork/SimpleDeckyTDP) plugin.|
| <no-wrap>:material-vibrate: Rumble</no-wrap> | Enables the device rumble motor in emulators that support it. |
| <no-wrap>:material-lightbulb-on: RGB</no-wrap> |Disabled on startup. Requires the [HueSync](https://github.com/honjow/HueSync) plugin for additional RGB control.|

### Function Buttons

| Button | Function |
| -- | -- |
| ++"Home"++ | <kbd>:material-microsoft-xbox: Guide</kbd> <no-wrap>(`Steam Menu`)</no-wrap> |
| ++"LCC (Turbo)"++ | <no-wrap><kbd>:material-microsoft-xbox: Guide</kbd> + <kbd>:material-gamepad-circle-down: A</kbd></no-wrap> <no-wrap>(`Quick Access Menu`)</no-wrap> |
| ++"M1"++ | ++"R3"++ |
| ++"M2"++ | ++"L3"++ |

## Notes

### Installation

Download the latest `AMD64` version of SteamFork from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/SteamFork/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/SteamFork/distribution/releases/latest)

### Booting from an external drive (USB or SD Card)

In order to launch SteamFork from an external drive you will need to first change the boot order in the BIOS.

During boot you can enter the bios by either (1) holding the <no-wrap>++"Home"+"LCC (Turbo)"++</no-wrap> buttons that sit bellow the dpad and right analog stick OR (2) connecting an external keyboard and pressing the ++del++ key.

In the bios; navigate to the `Boot` menu and then change the boot order to prioritize the SD card or USB Drive under `Boot Order Priorities`. Then go `Save & Exit` and select the `Save Changes and Exit` option.  This change will persist through all reboots.  If you want to boot into Windows simply remove the SD Card or USB drive.
