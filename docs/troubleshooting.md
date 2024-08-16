# :material-auto-fix: Troubleshooting

## Solutions for Common Issues

### Unknown Trust

SteamFork is SteamOS (Arch) based which uses the `pacman` package manager, and the repository and the packages contained within it are signed.  Although the distribution is immutable, the platform does allow users to temporarily disable the read only rootfs to update packages between releases if desired.  If you receive an unknown trust error while using pacman, issue the following commands to rebuild the trust database.

```
sudo steamos-readonly disable
sudo pacman-key --init
sudo pacman-key --populate
```

### Update download errors

Mirror lists are managed in the background automatically, however if you receive an error downloading updates you may need to refresh your mirror list manually.  To update your mirror lists, execute the following command in desktop mode.

```
sudo steamfork-get-mirror refresh
```

### Manually Updating

Updates are available over the air using the Software Updates item in system settings, however there may be scenarios where you would prefer to update manually.  Three manual update options are available.

#### Using steamos-update

While in desktop mode, open `Konsole` and use the SteamOS update tool directly.

```
sudo steamos-update check
sudo steamos-update
```

#### Installing an Image Manually

Again in desktop mode, open `Konsole`.  Choose a mirror to download from and pull the update image with curl. The latest image can be found in the [/images](https://www.steamfork.org/images/) directory on any of the SteamFork mirrors.


```
curl -LO https://www.steamfork.org/images/steamfork_rel_20240812.0916.img.zst
curl -LO https://www.steamfork.org/images/steamfork_rel_20240812.0916.sha256

sha256sum steamfork_rel_20240812.0916.img.zst

# Verify the sum matches the sum contained within the .sha256.

sudo steamfork-deploy install steamfork_rel_20240812.0916.img.zst
sudo steamfork-deploy switch rootfs/steamfork_rel_20240812.0916
```

If there are no errors, reboot.

#### Using the Installation Image

Download the latest installation image from the [images/installer](https://www.steamfork.org/images/installer/) directory of any SteamFork mirror on your PC, and flash it to a USB stick.  Boot the USB stick and use the `Upgrade SteamFork` launcher on the desktop to perform the upgrade.

### Recovering From a Bad Update

The update tooling is expected to be reliable and has recovery mechanisms built in, however there may be a time where your system fails to update correctly.  When this occurs the simplest recovery is to boot the installation image and execute commands to recover using the `Konsole` application.  If you have not yet rebooted the system, you can switch to desktop mode and ensure your system is configured not to boot the failed update.

#### Using steamfork-deploy switch

If your system is bootable, or if you have not yet rebooted, switch to desktop mode and open `Konsole`.  Use `steamfork-deploy` to ensure the system boots the desired rootfs volume when restarted.

```
sudo steamfork-deploy switch
```

Select the last known good root filesystem.  If you're unsure, use the `steamfork-info` command to display the version of the OS you're currently using.

#### Using Installation Media

If your system does not boot, boot from live installation media and open `Konsole`.  Mount the roofs volume, use the `btrfs` command to remove the broken root volume and then upgrade using the `Upgrade SteamFork` desktop icon to update.

```
# Use blkid to find the sf_root partition. For example NVMe users may find it on /dev/nvme0n1p2.  Update the mount command below with your partition.
sudo blkid
sudo mount /dev/nvme0n1p2 /mnt
# Update the command below for the version of SteamFork to remove.  Use ls /mnt/rootfs/ to list available volumes.
sudo btrfs subvolume delete /mnt/rootfs/steamfork_rel_20240812.0916
sudo umount /mnt
```

### Enabling Modern Sleep on 7000 Series AMD based devices.

7000 series and newer AMD APU's no longer support S3 sleep, and unfortunately many handheld manufacturers don't configure their firmware to take advantage of modern standby by default.  Fortunately, modern standby can be configured manually in firmware, or by using a helper.

> :warning: **Warning**
>
> The Smokeless UMAF tool has been known to brick devices even by reading values in the BIOS. There is a good chance that setting something incorrectly in the BIOS with this tool will brick your device and void your warranty. This article is posted for informational purposes only.  SteamFork takes no responsibility for any harm caused by following these steps. By following this guide you acknowledge that you are solely responsible for the outcome.

#### Enable Modern Standby
1. First enter your firmware to see if you have the options listed in the steps below.  If so, skip creating the Smokeless UMAF USB stick.
The first step is to create a UEFI compatible EFI bootloader on a USB drive.

2. If the options are not available, follow the next few steps to create boot media.
  * Format a USB stick with FAT32.
  * Download [Smokeless UMAF](https://github.com/DavidS95/Smokeless_UMAF/raw/main/UMAF_BETA.zip).
  * Extract `UMAF_Beta.zip` and copy the contents into the root of the usb stick.
  * Boot your device and select the USB stick from the boot menu.
  * Navigate to the `Front Page` tab and select `Device Manager`.

3. Select `AMD PBS` then `Power Saving Configurations`.
6. Under `S3/Modern Standby Support` change the entry to `Modern Standby` (or `Modern Standby Enable` on some devices).
7. Under `Modern Standby Type` select `Modern Standby + S0i2 + S0i3`.
8. Save changes and exit, allowing the device to reboot.

> Note: The first restart after this change may take longer than usual.  Thanks to ChimeraOS for the [initial writeup](https://github.com/ChimeraOS/chimeraos/wiki/Community-Guides#enabling-modern-sleep-on-7000-series-amd-hardware) of this section.

