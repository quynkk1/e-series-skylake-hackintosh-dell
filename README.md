# Dell Latitude E-Series Skylake Hackintosh
This repository contains all the fixes for Skylake CPU Model on macOS.

I have made and tested this EFI on Dell Latitude E5570, but I need a confirmation if this EFI is working on other Dell Skylake E-Series Models.

**My laptop specification:**

| Model  | Dell Latitude E5570 | Note |
| ------------- | ------------- | --------|
| CPU | Intel Core i3-6100U 2.30 GHz | Skylake CPU Generation |
| GPU 1 | Intel HD Graphics 520 | |
| GPU 2 | AMD R7 M370 2GB | Only available in i5/i7 Model |
| Memory | 2 x 8GB Samsung DDR4 |  |
| Storage (nVME) | SK hynix BC501 HFM256GDJTNG-8310A 250GB |  |
| Storage (SATA) | Samsung SSD 750 EVO 120GB |  |
| Ethernet | Intel Ethernet I219-LM |  |
| Audio Chipset | Realtek ALC293 |  |
| Wireless | Intel Wireless AC 7260 | Original from manufacturer. |
| Wireless | Dell Wireless DW1820A | BCM94350 |
| Bluetooth | Dell Wireless DW1820A | BCM94350_C2 |
| Card Reader | Realtek RTS525A |  |

⚠️: If you about to install macOS Ventura (13.x), iGPU `Intel HD Graphics` will not get best performance.

# EFI Compatibily List:
Bootloader: OpenCore 0.8.4

| Model | CPU Name | Is that supported ? |
| ---- | ------ | ------ |
| E5470 |  ? | Need testing. | 
| E5570 |  i3-6100U | **Yes** | 
| E7270 |  i5-6200U | **Yes** |
| E7470 |  ? | Need testing. |

1: Disable your dGPU (If you have) with a [SSDT](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/laptop-disable.html)

# Tweaking:
> **⚠️ WARNING: YOU MUST READ CAREFULLY THIS SECTION!**

- **1. Serial Number:** [How to generate your S.N?](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/SN-Gen.md)

- **2. Booting and diagnose errors:** [BIOS Setting](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/BIOS.md) - [Diagnose Problems.]()

- **3. Mapping USB:** [See here.](https://github.com/USBToolBox/tool#usage)

- **4. Place OpenCore into hard drive and edit miscellaneous information in config.plist:** [See here.]()

- **5. Network:** You can check here if you want: [Broadcom](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/Wireless-Broadcom.md), [Intel](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/Wireless-Intel.md)

- **6. Optimizing Power Management:** [See here.](https://dortania.github.io/OpenCore-Post-Install/universal/pm.html#using-cpu-friend)

- **7. Turn off CFG Lock (MSR 0xE2) for better Power Management (⚠️: Advanced User):** [See here.](https://github.com/dreamwhite/bios-extraction-guide/tree/master/Dell)


# How do I install macOS?

**You have 2 options:**

Option 1: [Online install.](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) It may take a long time to install. Use this method when you have USB lower than 8GB or you just chill in your free time, lmao 🐸.

Option 2: Offline install. This method requires you have USB larger than 8GB (Recommend 16GB at least).

# Screenshot
![SCS1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image.jpeg)
![SCS2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image%202.png)

# Special thanks to
- [Dortania](https://github.com/dortania) for [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) and bootloader
- [Acidanthera](https://github.com/acidanthera), [SkyrilHD](https://github.com/SkyrilHD) and other developers for many kext I used.
