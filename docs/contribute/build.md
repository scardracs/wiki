# :octicons-stack-16: Building SteamFork

## Minimal SteamFork
Install SteamFork using the [release image](https://www.steamfork.org/images/installer/) onto a PC or in a virtual machine.  Building the OS requires ~20GB of free space.  To install a minimal SteamFork instance using the minimal image, build and boot the image and then install using the `steamfork-installer` tool.

Ex. `steamfork-installer --drive /dev/sda --username builder --password SteamFork --root_password SteamFork`

## Building Images

Log in as your user and perform the following steps to configure the OS for building:

1. Clone the SteamFork distribution repository: `git clone https://github.com/SteamFork/distribution.git`
2. Build `rel` (stable) or `minimal` (no UI) SteamFork install media: `cd distribution && make image rel`

Optional:

1. Enable SSH for remote access: `sudo steamos-readonly disable && sudo systemctl enable sshd`

