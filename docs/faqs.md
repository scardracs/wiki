# :material-frequently-asked-questions: Frequently Asked Questions

## About SteamFork

### How often does SteamFork release?
SteamFork has adopted a weekly release cadance, however unless there are enough significant changes to justify releasing we may not release every week.  Significant changes include critical bug fixes, security improvements, major features, or a collection of general distribution improvements.

### Does SteamFork offer any formal support?

No. SteamFork is something that we develop for fun, it is provided as-is.  We do provide a bug tracker, however as a community supported project there is no commitment of formal support.

### Do you support X device?  Will you add support for X device?

You can find the list of currently supported devices here: [Devices](../devices)

If the device you are interested in isn't in that list then no one has contributed the work to add support for it yet.  Why? To add support for a device we (1) need to be interested in adding support for it 😊 and (2) need to have direct access to the device.

That said, anyone who is interested can submit updates to SteamFork to add support for a device they care about! If you are interested in adding support for a new device please start here: [Contribute](../contribute)

### Can I install SteamFork alongside Windows or other operating system?

No. Installing SteamFork on a device will remove all partitions and erase all data, so make sure to backup your data first. However, you can install another operating system, including Windows, after SteamFork is set up on the same drive.

## Using SteamFork

### How do I log in over SSH or Samba?

* Log into desktop mode and enable it with command: `sudo systemctl start sshd`.
* To enable it on every boot (not recommended): `sudo steamos-readonly disable && sudo systemctl enable sshd`.

### How do I update packages in between releases?

SteamFork is immutable so any changes may be lost, however it may be useful to update packages to work around a bug.  To install packages locally temporarily:

* Log into desktop mode and make the filesystem writeable: `sudo steamos-readonly disable`
* Install or update the package: Ex. `sudo pacman -Sy steamfork-customizations-jupiter`

### Enabling Modern Sleep on 7000 Series AMD based devices.

7000 series and newer AMD APU's no longer support S3 sleep, and unfortunately many handheld manufacturers don't configure their firmware to take advantage of modern standby by default.  Fortunately, modern standby can be configured manually in firmware, or by using a helper.

> :warning: **Warning**
>
> The Smokeless UMAF tool has been known to brick devices even by reading values in the BIOS. There is a good chance that setting something incorrectly in the BIOS with this tool will brick your device and void your warranty. This article is posted for informational purposes only.  SteamFork takes no responsibility for any harm caused by following these steps. By following this guide you acknowledge that you are solely responsible for the outcome.

#### Modern Standby Enablement Methods
* Enter your firmware settings to see if you have the options listed in the steps in the next section.  If so, skip the rest of this section.
* If the options are not available, follow the next few steps to create boot media.
  * Format a USB stick with FAT32.
  * Download [Smokeless UMAF](https://github.com/DavidS95/Smokeless_UMAF/raw/main/UMAF_BETA.zip).
  * Extract `UMAF_Beta.zip` and copy the contents into the root of the usb stick.
  * Boot your device and select the USB stick from the boot menu.
  * Navigate to the `Front Page` tab and select `Device Manager`.

#### Enabling Modern Standby
1. Select `AMD PBS` then `Power Saving Configurations`.
2. Under `S3/Modern Standby Support` change the entry to `Modern Standby` (or `Modern Standby Enable` on some devices).
3. Under `Modern Standby Type` select `Modern Standby + S0i2 + S0i3`.
4. Save changes and exit, allowing the device to reboot.

> Note: The first restart after this change may take longer than usual.  Thanks to ChimeraOS for the [initial writeup](https://github.com/ChimeraOS/chimeraos/wiki/Community-Guides#enabling-modern-sleep-on-7000-series-amd-hardware) of this section.

> Note: On newer Ayaneo devices, modern standby is enabled by the BIOS update released on 2024 11 04.

### Updating BIOS (Ayaneo)
1. Grab the firmware files from Ayaneo support: https://ayaneo.com/support/download
2. Download shellx64: https://github.com/pbatard/UEFI-Shell/releases/download/24H1/shellx64.efi
3. Format a USB drive as FAT 32 and create the folders /EFI/Boot/ on the root of the USB drive.
4. Place shellx64.efi into the Boot folder and rename it to BootX64.efi
5. Extract the Ayaneo firmware files to the USB drive. Make sure the .bin file that contains the update is on the root of the USB drive, as well as the file called "AfuEfix64.efi" You may need to find a password in a readme file to get to the actual BIOS file.
6. Create a new plain text file on the root of the USB drive and name it "startup.nsh"
7. Place the following into startup.nsh, replacing <BIOS> with the full name of the .bin file containing the BIOS update:
```
fs1:
AFUEFIx64 <BIOS> /p /b /n /k /L /REBOOT
```
8. Ensure you have more than 50% battery and your device is plugged in.
9. Plug the USB drive into your device, and hold LC and Volume+ until the Ayaneo logo appears.
10. Select the USB drive from the boot menu using the Ayaneo buttons to select and volume button to confirm. Do not press anything or remove the drive until the BIOS update completes and the device reboots. Interrupting the update in any way can brick your device.
