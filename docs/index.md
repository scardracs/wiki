<div class="preview-container">
  <img class="off-glb" src="_inc/images/preview.png"/>
</div>

# Welcome to the SteamFork Wiki

SteamFork is a personal project to create an immutable Linux distribution that is as SteamOS like as possible without sacrificing device compatibility.

## Features
* Full SteamOS UI/UX, including desktop mode.
* Minimal changes to SteamOS to preserve upstream compatibility.
* Power management optimizations ported from [JustEnoughLinuxOS](https://github.com/JustEnoughLinuxOS).
* Improved fan curves on supported devices.
* RGB disabled by default on Ayaneo and Ayn devices.
* Supports booting from removable media such as usb drives and micro sd cards.

## Screenshots
<table>
  <tr>
    <td><img src="https://raw.githubusercontent.com/SteamFork/.github/main/profile/.images/20240525-max-1.jpg"/></td>
    <td><img src="https://raw.githubusercontent.com/SteamFork/.github/main/profile/.images/20240525-max-2.jpg"/></td>
  </tr>
</table>

## Licenses
SteamFork is a Linux distribution that is made up of many open-source components, and each component is provided under its respective license.  Unless otherwise noted, the content of this project itself is made available under the terms of the MIT license.  See [LICENSE](LICENSE) for details.

## Device Support

Please see the [devices](../devices) section.

## Downloads
Downloads are hosted at [SteamFork.org](https://www.steamfork.org/steamfork-images/steamfork-installer/) and updates are available OTA.  A download link to the latest installation ISO can be
 found below.

| Branch | URL | Checksum |
| -- | -- | -- |
| Stable | [LATEST](https://www.steamfork.org/steamfork-images/steamfork-installer/steamfork-rel-latest-x86_64.iso) | [CHECKSUM](https://www.steamfork.org/steamfork-images/steamfork-installer/steamfork-rel-latest-x86_64.iso.sha256) |

### Installation
To install SteamFork, flash the bootable image to a USB device and then follow the procedure for your device to boot from removable media.  From the live mode desktop, open the "Install SteamFork" application and then follow the prompts to install to your device.  When complete, close the installer, and shut down the device.  Remove the installation media, and then power the device on to boot into SteamOS.

* SteamFork only supports systems with AMD APU/GPUs.
* Installation to removable media such as microsd and usb drive is not currently supported.

## Power Management / TDP Control
To enable management of the device TDP, switch to desktop mode and then install Decky Loader and Simple Decky TDP.

| Source | Installation URL |
| -- | -- |
| [Decky Loader](https://github.com/SteamDeckHomebrew/decky-loader) | ```curl -L https://github.com/SteamDeckHomebrew/decky-installer/releases/latest/download/install_release.sh \| sh``` |
| [Simple Decky TDP](https://github.com/SteamFork/SimpleDeckyTDP) | ```curl -L https://github.com/SteamFork/SimpleDeckyTDP/raw/main/install.sh \| sh``` |

## Credits

Like any Linux distribution, this project is not the work of one person.  It is the work of many persons all over the world who have developed the open source bits without which this project could not exist.  Special thanks to Valve for providing SteamOS, HoloISO which this project is based upon, ShadowBlip, JELOS, ChimeraOS, and developers and contributors all across the open source community.

## Support
This distribution is made available for myself and others who may want to use it, however it is provided as-is.  Bug fix and feature PRs are always welcome.

## Sources
This project utilizes sources from SteamOS (release repositories), the unofficial Valve source repo, and AUR.

* Valve package repository: `buildroot/pacman-build-*.conf`
* evlaV Repository: https://gitlab.com/evlaV
* Arch AUR repository: https://aur.archlinux.org
* HoloISO (which this project was based): https://github.com/HoloISO