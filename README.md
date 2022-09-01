# Dell Latitude E-Series Skylake Hackintosh
This repository contains all the fixes for Skylake CPU Model on macOS.

For Vietnamese User: [You can read the translation from here 🇻🇳](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/README-VN.md)

I have made and tested this EFI on Dell Latitude E5570, but I need a confirmation if this EFI is working on other Dell Skylake E-Series Models.

**My laptop specification:**

| Model  | Dell Latitude E5570 | Note |
| ------------- | ------------- | --------|
| CPU | Intel Core i3-6100U (Skylake) 2.30 GHz | |
| iGPU | Intel HD Graphics 520 | |
| dGPU | AMD R7 M370 2GB | Only available in i5/i7 Model |
| Memory | 2 x 8GB Samsung DDR4 |  |
| Storage (nVME) | SK hynix BC501 HFM256GDJTNG-8310A 250GB |  |
| Storage (SATA) | Samsung SSD 750 EVO 120GB |  |
| Ethernet | Intel Ethernet I219-LM |  |
| Audio Chipset | Realtek ALC293 |  |
| Wireless (Old) | Intel Wireless AC 7260 |  |
| Wireless | Dell Wireless DW1820A | BCM94350 |
| Bluetooth | Dell Wireless DW1820A | BCM94350_C2 |
| Card Reader | Realtek RTS525A |  |
| macOS Installed | macOS Monterey 12.5 | [macOS Ventura (13.x)](https://www.apple.com/macos/macos-ventura-preview/features/) will support soon. |

⚠️: If you about to install macOS Ventura (13.x), iGPU will not get best performance. Take your own risk.

# EFI Compatibily List:
Bootloader: OpenCore 0.8.3

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

- **Serial Number:** [You need to manually generate your S.N. Read this guide: How to generate your S.N]()

- **Wireless Adapter Configuration:** You can check here if you want: [Broadcom Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/Wireless-Broadcom.md), [Intel Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/Wireless-Intel.md)

- **USB:** Enable XHCIPortLimit when you are using macOS 11.2.3 or lower. [Dortania's USB Mapping Guide](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html)

- **Optimizing Power Management:** CPUFriend will help you. [See here](https://dortania.github.io/OpenCore-Post-Install/universal/pm.html#using-cpu-friend)

# How do I install macOS?

- You should change your BIOS: [BIOS Setting Guide](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/BIOS.md)

**You have 2 options:**

Option 1: [Online install.](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) It may take a long time to install. Use this method when you have USB lower than 8GB or you just chill in your free time, lmao 🐸.

Option 2: [Offline install.]() This method requires you have USB larger than 8GB (Recommend 16GB at least).

- All you need is download this EFI from Release tab and copy it into your EFI Partition in your USB.

# Screenshot
![SCS1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image.jpeg)
![SCS2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image%202.png)

# Special thanks to
- [Dortania](https://github.com/dortania) for [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) and bootloader
- [Acidanthera](https://github.com/acidanthera), [SkyrilHD](https://github.com/SkyrilHD) and other developers for many kext I used.
- [NLTD2010](https://github.com/NLTD2010) for VietNamese Readme translate and for my IGPU patched.
