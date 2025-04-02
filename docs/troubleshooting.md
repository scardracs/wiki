# :material-auto-fix: Troubleshooting

## Solutions for Common Issues

### Lower Game Performance After September Steam Client Update
The September 2024 Steam client update introduced a new feature allowing users to configure the Maximum Game Resolution (Settings / Display) which now defaults to the native resolution of your display.  With this change the Steam client is ignoring the 720P or 800P game resolution normally configured by SteamFork.  To work around the issue, simply configure your game properties back to either 720P or 800P.  Unfortunately, this must be done on a per game basis.

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

### Decky Loader Issues After Steam Client Update

If Decky Loader breaks after a Steam Client update, you can fix it using one of the following methods:

#### Option 1: Disable and Upgrade via Quick Access Menu
1. Select the option in the Steam error message to disable Decky Loader until the next reboot.
2. Once logged in, open the Quick Access Menu and select Decky.
3. Go to Decky's settings and click **Upgrade**.
4. The upgrade will complete, but the service may get stuck restarting.
5. Reboot the device to finalize the process.

#### Option 2: Upgrade Using the Decky Installer Utility
1. Switch to **Desktop Mode**.
2. Download the Decky installer utility from [https://decky.xyz/download](https://decky.xyz/download).
3. Execute the utility and upgrade Decky.

#### Option 3: Reinstall Decky Using SteamFork Helper
1. Switch to **Desktop Mode**.
2. Use the **SteamFork Helper** application to reinstall Decky.
   - **Note**: This will remove any installed plugins.

### Internal Display Scaling Issue After a Steam Client Update

If the internal display scaling is incorrect after an update, follow these steps to enable and configure UI scaling for the internal display:

1. In **Steam Game Mode**, go to **System Settings** and enable **Developer Mode**.
2. A new section named **Developer** will appear on the left-hand side. Open it and enable **Show display scaling settings for Internal Display**.
3. The new display scaling options will now be available under **Display**.
4. Select your preferred scaling option.
5. Return to **System Settings** and disable **Developer Mode**. The display scaling options will remain available.

