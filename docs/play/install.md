# :material-progress-check: Installing SteamFork

!!! info "SteamFork is compatible with Intel and AMD based systems.  NVidia GPUs are not supported."

SteamFork is installed by downloading an image, flashing it to an SD Card or USB Drive and then booting your device to run the SteamFork Live image.  The installer will completely replace any existing operating system on the drive.

## Step 1: Download

* Choose the version of SteamFork you want to install:

| Branch       | Upstream Version | Download Link                                                                                                           | Checksum                                                                                                           |
|--------------|---------|-------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
| **Stable**   | 3.6     | [![Stable](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=5998FF&label=Stable&style=flat#only-light)](https://www.steamfork.org/images/installer/steamfork-rel-latest-x86_64.iso)[![Stable](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=5998FF&label=Stable&style=flat#only-dark)](https://www.steamfork.org/images/installer/steamfork-rel-latest-x86_64.iso) | [SHA256](https://www.steamfork.org/images/installer/steamfork-rel-latest-x86_64.iso.sha256)                       |
| **Testing**  | 3.7     | [![Testing](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=FF9900&label=Testing&style=flat#only-light)](https://www.steamfork.org/images/installer/steamfork-testing-latest-x86_64.iso)[![Testing](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=FF9900&label=Testing&style=flat#only-dark)](https://www.steamfork.org/images/installer/steamfork-testing-latest-x86_64.iso) | [SHA256](https://www.steamfork.org/images/installer/steamfork-testing-latest-x86_64.iso.sha256)                   |

* Download the version that best suits your needs:
  * **Stable**: Recommended for most users.
  * **Testing**: Includes experimental features but may not be as stable.

## Step 2: Flash

* Write the downloaded image to an SD Card or USB drive using your preferred imaging tool.
    * Common imaging tools include [Rufus](https://rufus.ie/), [Raspberry Pi Imager](https://www.raspberrypi.com/software/), and [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/).  If you're skilled with the command line, `dd` can also be used.

## Step 3: Boot your device

* Insert your SD Card or USB Drive into your device while its off and then turn it on
* Note: Some devices may require you to set the boot order so your SD Card is loaded first.  Please see documentation for your specific device to see if this applies to you.
* SteamFork will boot its live image and you'll be able to run the SteamFork installer from that to install directly to the drive of your choice.

## Step 4: Run the SteamFork installer

* From the live mode desktop, open the "Install SteamFork" application and then follow the prompts to install to your device.
* Installing SteamFork will erase all data and partitions on selected drive. Make sure to backup your data before proceeding.
* When complete, close the installer, and shut down the device unless you are proceeding to step 5.  Remove the installation media, and then power the device on to boot into SteamOS.

Screenshots of this process:

<table>
  <tr>
    <td><img src="../../_inc/images/install/ksnip_20240603-041039.png"/></td>
    <td><img src="../../_inc/images/install/ksnip_20240603-041127.png"/></td>
  </tr>
  <tr>
    <td><img src="../../_inc/images/install/ksnip_20240603-041200.png"/></td>
    <td><img src="../../_inc/images/install/ksnip_20240603-041232.png"/></td>
  </tr>
  <tr>
    <td><img src="../../_inc/images/install/ksnip_20240603-041323.png"/></td>
    <td><img src="../../_inc/images/install/ksnip_20240603-043344.png"/></td>
  </tr>
</table>

## Step 5: Set up dual boot (optional)

### Shrink Home for Windows

* Open KDE partition manager and select the sf_home partition.
* Right click and select Resize/Move.
* Shrink the partition to the desired size using the slider.
* Select OK.
* Select Apply, followed by Apply Pending Operations.
* Press OK to complete the operation.
* Close KDE Partition Manager.
* Shut down the device.

### Install Windows

* Boot the Windows installation media.
* Select the Custom install option.
* Select the unallocated space created in step 1.
* Install and configure Windows.

### Configure SteamFork as default

* Enter firmware settings, and set SteamFork as the default boot option.

### Boot SteamFork or Windows

* Use your device's firmware boot menu to boot SteamFork or Windows.
