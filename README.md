# Dell Latitude E-Series Skylake Hackintosh
This repo contains all the fixes for Skylake CPU Model on macOS.

I have made and tested this EFI on Dell Latitude E5570, but I need a confirmation if this EFI is working on other Dell Skylake E-Series Models.

**My laptop specification:**

| Model  | Dell Latitude E5570 | Note |
| ------------- | ------------- | --------|
| CPU | Intel Core i3-6100U (Skylake) 2.30 GHz | |
| GPU 1 | Intel HD Graphics 520  | |
| GPU 2 | AMD R7 M370 2GB  | |
| Memory | 2 x 8GB Samsung DDR4 |  |
| Storage | NVME Hynix 250GB |  |
| LAN | Intel Ethernet I219-LM |  |
| Wireless | Dell Wireless DW1820A | BCM94350 |
| Bluetooth | Dell Wireless DW1820A | BCM94350_C2 |
| Card Reader | Realtek RTS525A |  |
| OS | macOS Monterey 12.0.1 | |

# EFI Compatibily List:

| Model | CPU Name | Is that supported ? | Note |
| ---- | ------ | ------ | ----- |
| E5470 |  i5-6300U | Need testing. | -/- |
| E5570 |  i3-6100U | **Yes** | 1 |
| E7270 |  i5-6300U | Need testing. | -/- |
| E7470 |  i5-6300U | Need testing. | -/- |

1: Disable your dGPU (If you have) with a [SSDT](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/laptop-disable.html)

**Note: This list is not completed. If you have compatible model and it worked with my EFI, please make a confirmation.**

# What's working?
Everything is work...

# What's not working or BUGs?
Hmmm... I can't find any BUGs and things aren't working.

# Note (You might read this carefully for having better Hackintosh laptop.)
**Serial Number:** 

**Touchscreen:** I added VoodooI2C to take advantage of the touchscreen display. However, it is disabled. If you have this model, you may enable `VoodooI2C.kext` and its-related kexts in config. You may refer this [image]()

**Intel Chipset Wireless User:** I also added `AirportItlwm.kext` but it only supported macOS Big Sur and disabled. If you have later/previous version of macOS, go to this [link](), select your `AirportItlwm.kext` depend on your OS, replace your `AirportItlwm.kext` in OC/Kext and enable 3 kexts:`AirportItlwm.kext`, `IntelBluetoothFirmware.kext` and `IntelBluetoothInjector.kext` in config.

*Note: If you use macOS Monterey 12.x, you MUST ENABLE `BlueToolFixup.kext` and leave `IntelBluetoothInjector.kext` DISABLE.*
Example [Image]() here if you want.

**Broadcom Chipset Wireless User:** I have created this post for user who have Broadcom Wireless Chipset Adapter. [See here]() for more detail.

**USB:** You need to manually map your USB for better usage. [Dortania's USB Mapping Guide](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html)

**Optimizing Power Management:** CPUFriend will help you. [See here](https://dortania.github.io/OpenCore-Post-Install/universal/pm.html#using-cpu-friend)

# How do I install macOS?
**I will update this soon because of a lack of time***

# Screenshot
