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
