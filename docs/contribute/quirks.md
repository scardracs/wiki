# :material-code-block-tags: Adding Quirks

## Panel Rotation

If you have a new device that supports Mainline Linux, adding and submitting a rotation patch is very simple. Adding a rotation patch to the kernel will provide the hints needed for Wayland/Weston to also correctly rotate the panel.

To begin, download the kernel sources.  Extract the kernel and rename it to linux-{version}.orig, and then copy that folder to linux-{version} or extract it again so there are two copies.  This will be necessary to create the [patch](modify.md#creating-a-patch-for-a-package-using-git).

### Panel Definition and Default Orientation

Next, edit `linux-{version}/./drivers/gpu/drm/drm_panel_orientation_quirks.c` and add a struct describing your panel and its orientation if one does not already exist.  For example:

```
static const struct drm_dmi_panel_orientation_data lcd1080x1920_leftside_up = {
  .width = 1080,
  .height = 1920,
  .orientation = DRM_MODE_PANEL_ORIENTATION_LEFT_UP,
};
```

In the example above, the panel is 1080p, and rotated to the left in order to be corrected.

### DMI Matching

Now that the rotation correction has been defined, the kernel needs a method to match and apply it.  For this we use DMI data.  You can retrieve the DMI data by using `cat`, or `dmidecode`.  For our example, we'll use `cat`.

```
airplus:~ # cat /sys/class/dmi/id/sys_vendor
AYANEO
airplus:~ # cat /sys/class/dmi/id/product_name
AIR Plus
```

Using this data, we will create a match rule to match our panel struct in drm_panel_orientation_quirks.c.

```
{
  .matches = {
    DMI_EXACT_MATCH(DMI_SYS_VENDOR, "AYANEO"),
    DMI_EXACT_MATCH(DMI_PRODUCT_NAME, "AIR Plus"),
  },
  .driver_data = (void *)&lcd1080x1920_leftside_up,
}
```

Save, and build your patch following the instructions [here](modify.md). Place your patch in `packages/kernel/linux/patches/AMD64` or the appropriate device directory, and run a test build.

!!! note "DMI_EXACT_MATCH or DMI_MATCH can be used.  DMI_EXACT_MATCH is as implied, an exact match.  DMI_MATCH will match that any device where its DMI data includes "AIR Plus""

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
