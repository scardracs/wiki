# :material-code-block-tags: Adding Quirks

## Hardware Quirks

Adding hardware quirks are simple, and many examples can be found in `https://github.com/SteamFork/distribution/tree/main/PKGBUILD/steamfork-device-support/src/etc/lib/steamfork_hwsupport/him_devicequirks`.  A quirk generation script is provided with SteamFork that can be used to generate a simple quirk for a new device.

### Creating a Quirk
To create a quirk using `steamfork-quirk-generator`, open a konsole session in live installer or desktop mode if installed and execute it.  The tool will provide instructions on usage.

### Example
To generate a simple quirk to support the OLED panel of the Ayaneo Air family of devices the following would be passed to the tool.
```
/usr/bin/steamfork-quirk-generator --gamescope_rotation left --desktop_rotation left --gamescope_resolution 1280x720 --gamescope_displaysize 1280x720
```

### Additional Quirks

Your device may need additional quirks to function correctly or for optimization.

## Submit Your Quirk

Please follow the instuctons for [Building](build.md) and [Contributing](index.md) to submit your quirks to the distribution for inclusion.  Please do not change major functionality of the distribution as upstream compatibility is a primary goal of SteamFork, submissions that do not follow our standards will need to be revised.

> Note: If you would like to generate a kernel panel rotation patch, please ping a developer in the SteamFork discord for assistance, as the package build tools are intended to run on devices running SteamFork and upload to the official repo by default.
