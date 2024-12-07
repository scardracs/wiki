<div class="preview-container">
  <img class="off-glb" src="_inc/images/preview.png"/>
</div>

# Welcome to the SteamFork Wiki

SteamFork is a SteamOS-based operating system with improved hardware compatibility.  It is designed to provide the same experience as SteamOS on a SteamDeck.

## Features
* Works on a variety of devices from ASUS, Antec, Atari, Ayaneo, Ayn, and GPD along with MiniPCs and other computers with compatible hardware.
* Provides a full SteamOS UI/UX experience, including SteamOS's desktop mode.
* Minimal changes are made to SteamOS to preserve compatibility with Steam Deck plugins, software, and documentation.
* Offers improved fan curves are available on supported devices from Ayaneo and Ayn.
* Disables RGB off by default on supported devices, RGB will flash on low battery when available.
* Includes power management optimizations ported from [JustEnoughLinuxOS](https://github.com/JustEnoughLinuxOS).
* Supports booting from removable media such as usb drives and micro sd cards (64GB minimum) and dual boot with Windows.
* SteamFork is an atomic distribution with simple rollback and recovery options.
* Compatible Epic Games Store, GoG, and Amazon Prime Gaming via Heroic, available for installation in discover.
* SteamOS is our upstream, making SteamFork the only active Linux gaming solution truly derived from SteamOS.

## Screenshots
<table>
  <tr>
    <td><img src="https://raw.githubusercontent.com/SteamFork/.github/main/profile/.images/20240609-max-1.jpg"/></td>
    <td><img src="https://raw.githubusercontent.com/SteamFork/.github/main/profile/.images/20240609-max-2.jpg"/></td>
  </tr>
</table>

## Licenses
SteamFork is a Linux distribution that is made up of many open-source components, and each component is provided under its respective license.  Unless otherwise noted, the content of this project itself is made available under the terms of the MIT license.  See [LICENSE](LICENSE) for details.

## Community
We use Discord for project related discussion.  Everyone is welcome to join our community by clicking the invitation link below.

* [SteamFork Discord](https://discord.gg/AQ5rtQstCf)

## Device Support

Please see the [devices](../devices) section.

## Installation

Please see the [install](../play/install) section.

## Power Management / TDP Control

To enable management of device TDP, switch to desktop mode and use the SteamFork Helper applet to install Decky Loader and any desired plugins including our fork of SimpleDeckyTDP.  A list of recommended software and plugins can be found in the [software](../play/verified-software) section.

## Credits

Like any Linux distribution, this project is not the work of one person.  It is the work of many persons all over the world who have developed the open source bits without which this project could not exist.  Special thanks to Valve for providing SteamOS, HoloISO which this project is based upon, ShadowBlip, JELOS, ChimeraOS, and developers and contributors all across the open source community.

## Support
This distribution is made available for myself and others who may want to use it, however it is provided as-is.  Bug fix and feature PRs are always welcome.

## Sources
In addition to sources developed by SteamFork, this project utilizes sources from SteamOS (release repositories), the unofficial Valve source repo, and AUR.

* SteamFork repository: https://github.com/steamfork
* Valve package repository: `buildroot/pacman-build-*.conf`
* evlaV Repository: https://gitlab.com/evlaV
* Arch AUR repository: https://aur.archlinux.org
* HoloISO (which this project was originally based): https://github.com/HoloISO
