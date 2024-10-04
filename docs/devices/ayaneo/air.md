title: AYANEO Air / Air Pro

# AYANEO Air / Air Pro

![](../../_inc/images/devices/ayaneo-air.png){ .off-glb }

## Features

| Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | Notes |
| -- | -- |
| :material-harddisk: Storage | SteamFork can be run from an SD Card, USB Drive or installed directly to the internal NVME. 
| :material-wifi: Wifi | Can be turned on in Steam OS under Main Menu > Network Settings. |
| :simple-bluetooth: Bluetooth | Supports bluetooth audio and controllers. |
| :material-fan: Fan | Managed automatically. |
| :material-lightning-bolt-circle: TDP Limit | Can be set globally, per system or per game. Requires the [SimpleDeckyTDP](https://github.com/SteamFork/SimpleDeckyTDP) plugin.|
| :material-vibrate: Rumble | Enables the device rumble motor in emulators that support it. |
| :material-lightbulb-on: RGB | Disabled on startup. Requires the [HueSync](https://github.com/honjow/HueSync) plugin for additional RGB control.|

## Notes

### Installation

Download the latest `AMD64` version of SteamFork from the button below and follow the instructions listed on the [Install](../../../play/install/) page.

[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=111111&color=5998FF&label=Latest&style=flat#only-light)](https://github.com/SteamFork/distribution/releases/latest)
[![Latest Version](https://img.shields.io/github/release/SteamFork/distribution.svg?labelColor=dddddd&color=5998FF&label=Latest&style=flat#only-dark)](https://github.com/SteamFork/distribution/releases/latest)

### Booting from an external drive (USB or SD Card)

To boot SteamFork from an external drive, hold ++"LC"+"Volume Up"++ and press the ++"Power"++ button, continue holding ++"LC"+"Volume Up"++ until the Ayaneo logo appears.  Select the storage device with SteamFork from the boot menu using the Ayaneo button, and then press volume up to boot the distribution.

### Fixing Audio Polarity
Early Ayaneo Air and Air Pro models were shipped with speaker polarity reversed.  Correcting this condition is simple, it requires creating a custom quirk.  Custom quirks persist across updates.

```
### Set a variable to define your custom quirk, Ayaneo Air and Air Pro devices use `AYANEO-AIR`.
export CUSTDIR="/home/.steamos/offload/customdevicequirks/AYANEO-AIR/boot.d"

### Create the directory and change into it.
sudo mkdir -p ${CUSTDIR}
cd ${CUSTDIR}

### Create the quirk
cat <<EOF | sudo tee audio-phase-fix.sh
#!/bin/sh
master=alsa_output.pci-0000_04_00.6.analog-stereo
pactl load-module module-ladspa-sink sink_name=ladspa_out sink_master=$master plugin=inv_1429 label=inv channel_map=front-right
pactl load-module module-remap-sink sink_name=remap_FR master=ladspa_out channels=1 master_channel_map=front-right channel_map=front-right
pactl load-module module-remap-sink sink_name=remap_FL master=$master channels=1 master_channel_map=front-left channel_map=front-left
pactl load-module module-combine-sink sink_name='"AYANEO AIR Fixed Phase Audio"' sink_properties=device.description='"AYANEO_AIR_Fixed_Phase_Audio"' slaves=remap_FL,remap_FR channels=2
EOF

chmod 0755 ${CUSTDIR}
### Reboot the device to activate, or execute ${CUSTDIR}/audio-phase-fix.sh
```

### Known Issues

* The display does not always turn on when powering the device on or switching to desktop mode.  Putting it to sleep and waking it up again will resolve it.
