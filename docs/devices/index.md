# :material-television: Device Support

## Tested devices

SteamFork has been tested (i.e. booted at least once) on the list of devices below.  Devices with a sponsor are actively tested and used with SteamFork frequently.  Devices without a sponsor are not actively maintained and may have unknown issues.

| Manufacturer | Device | Sponsor<sup>1</sup> | Known Issues |
| -- | -- | -- | -- |
| Atari | VCS | [Fewtarius](https://github.com/fewtarius) | None |
| AYANEO | 1S | Unsponsored | Unknown |
| AYANEO | 2 | Unsponsored | Unknown |
| AYANEO | 2021 / Pro / Retro Power | Unsponsored | Unknown |
| AYANEO | 2S | [Fewtarius](https://github.com/fewtarius) | Must enable sleep in firmware<sup>2</sup>. |
| AYANEO | Air / Air Pro | [Fewtarius](https://github.com/fewtarius) |EDID bug sometimes prevents display from working on boot (sleep/resume to correct), and breaks GPU performance mode.|
| AYANEO | Air Plus | [Fewtarius](https://github.com/fewtarius) |None |
| AYANEO | Flip DS | Unsponsored | Unknown |
| AYANEO | Flip KB | [Fewtarius](https://github.com/fewtarius) | Must enable sleep in firmware<sup>2</sup>. Touch input does not work yet.|
| AYANEO | Founder Edition | Unsponsored | Unknown |
| AYANEO | Geek | Unsponsored | Unknown |
| AYANEO | Next, Next Pro | Unsponsored | Unknown |
| Ayn | Loki Max | [Fewtarius](https://github.com/fewtarius) | None |
| Ayn | Loki Zero | Unsponsored | Unknown |
| GPD | Win 4 (6800U) | [anthonycaccese](https://github.com/anthonycaccese) | None |
| GPD | Win Mini (8840U) | Unsponsored | None |

!!! info
    - <sup>1</sup> Sponsored devices are fully supported by its maintainer.  Support for unsponsored devices may vary. 
    - <sup>2</sup> New AMD 7000 series devices do not support S3 sleep due to an incorrect firmware setting.  This setting is locked down and must be enabled using a third party helper.  Follow the process from @ChimeraOS to enable sleep [here](https://github.com/ChimeraOS/chimeraos/wiki/Community-Guides#enabling-modern-sleep-on-7000-series-amd-hardware).

## Sponsoring a device

Sponsoring a device is a commitment to maintaining support for your device by validating, testing, and bugfixing any issues that may arise.  Adding support for a device's basic features is straight forward, however, it can become far more technical to add support for features such as fan control.  If you are interested in sponsoring your device, follow the process below.

1. Create a GitHub account if you do not already have one.
2. Boot the SteamFork live image.
3. Create a device quirk using the quirk generator included.  Minimum requirements are gamescope resolution, and rotation if needed.
```
$ sudo -s
# steamfork_quirk_generator --help
```
4. Create a pull request to the [SteamFork Device Support](https://github.com/SteamFork/distribution/tree/main/PKGBUILD/steamfork-device-support) package with your new addition.
5. Open and take ownership of any issues specific to your device on the [SteamFork Bug Tracker](https://github.com/SteamFork/bugtracker).
6. When ready to begin sunsetting support for your device, generate and PR new quirk with the `--supported false` property.

