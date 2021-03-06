# Dell Latitude E-Series Skylake Hackintosh
This repo contains all the fixes for Skylake CPU Model on macOS.

I have made and tested this EFI on Dell Latitude E5570, but I need a confirmation if this EFI is working on other Dell Skylake E-Series Models.

**My laptop specification:**

| Model  | Dell Latitude E5570 | Note |
| ------------- | ------------- | --------|
| CPU | Intel Core i3-6100U (Skylake) 2.30 GHz | |
| iGPU | Intel HD Graphics 520  | |
| dGPU | AMD R7 M370 2GB  |I don't have this GPU |
| Memory | 2 x 8GB Samsung DDR4 |  |
| Storage | NVME Hynix 250GB |  |
| Ethernet | Intel Ethernet I219-LM |  |
| Wireless | Dell Wireless DW1820A | BCM94350 |
| Bluetooth | Dell Wireless DW1820A | BCM94350_C2 |
| Card Reader | Realtek RTS525A |  |
| macOS Installed | macOS Monterey 12.4 | |

# EFI Compatibily List:
Bootloader: OpenCore 0.8.1 - Updated 29/6/2022

| Model | CPU Name | Is that supported ? | Note |
| ---- | ------ | ------ | ----- |
| E5470 |  ? | Need testing. | -/- |
| E5570 |  i3-6100U | **Yes** | 1 |
| E7270 |  i5-6200U | **Yes** | -/- |
| E7470 |  ? | Need testing. | -/- |

1: Disable your dGPU (If you have) with a [SSDT](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/laptop-disable.html)

**Note: This list is not completed. If you have compatible model and it worked with my EFI, please make a confirmation.**

- Two picture below are listing what SSDTs and patches I have used.
![ACPI-SSDTs](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/ACPI/ACPI-SSDTs.png)
![ACPI-Patches](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/ACPI/ACPI-Patches.png)

# What's working?
Everything is work...

# What's not working or BUGs?
Hmmm... I can't find any BUGs and things aren't working.

# Other things:
> **⚠️ WARNING: YOU MUST READ CAREFULLY THIS SECTION!**

- **Serial Number:**

- **Touchscreen:** [Use VoodooI2C with patched SSDT, see here]()

- **Wireless Adapter Configuration:** You can check here if you want: [Broadcom Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Wireless-Broadcom-User.md), [Atheros Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Wireless-Broadcom-User.md), [Intel Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Wireless-Broadcom-User.md)

- **USB:** You need to manually map your USB for better usage. [Dortania's USB Mapping Guide](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html)

*Note: If you want to install macOS 11.2.3 or lower version, leave quirk `XHCIPortLimit` in config enable.* 
![XHCIPort](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/XHCIPortLimit.png)
![XHCIPortPT](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/XHCIPortLimit-ProperTree.png)

- **Optimizing Power Management:** CPUFriend will help you. [See here](https://dortania.github.io/OpenCore-Post-Install/universal/pm.html#using-cpu-friend)

# How do I install macOS?
**You have 2 options:**

Option 1: [Online install.](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) It may take a long time to install. Use this method when you have USB lower than 8GB or you just chill in your free time, lmao 🐸.

Option 2: [Offline install.]() This method requires you have USB larger than 8GB (Recommend 16GB at least).

- All you need is download EFI and copy it into your EFI Partition in your USB.

# Screenshot
![SCS1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image.jpeg)
![SCS2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image%202.png)

# Special thanks to
- [Dortania](https://github.com/dortania) for [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) and bootloader
- [Acidanthera](https://github.com/acidanthera), [SkyrilHD](https://github.com/SkyrilHD) and other developers for many kext I used.
