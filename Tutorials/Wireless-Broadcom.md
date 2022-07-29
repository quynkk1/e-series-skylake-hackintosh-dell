# Broadcom Wireless User Tutorial
For users who are using Broadcom Wireless Chipset, you should discover name first. `You should use AIDA64.`

## List of supported wireless chipset: 

- Big Sur (11.x) and Monterey (12.x) and older: BCM943602, BCM94360, BCM94352, BCM94350

- Catalina (10.15) and older: BCM943224, BCM94331

- Mojave (10.14) and older: BCM94322

If your wireless card name isn't same as list above, you might consider replacing.

If your wireless card name sames as list above, follow instrucment below:

## Instrucment:

**Step 1: Finding your PCI wireless card via Hackintool and add it into config.plist > `DeviceProperties`**

> Example: My PCI Name of DW1820A (I have replaced) is `PciRoot(0x0)/Pci(0x1C,0x0)/Pci(0x0,0x0)` and make sure you added it as image below.

Open Hackintool, choose tab `PCIe`, heading into your wireless card, right-click into them and click `Copy Device Path`

![hackintool-1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/DeviceProperties/Hackintool-PCIe.png)

Open config.plist in my EFI, click `DeviceProperties` section, adding PCI by click `+` button and paste your wireless PCI.

![image1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/DeviceProperties/DeviceProperties-WLAN-BCM-1.png)

**Step 2: Adding properties**

![image2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/DeviceProperties/DeviceProperties-WLAN-BCM-2.png)

You might refer information below. The complete properties injection will be:

|Key |Value |Type |
| --- | --- | --- |
|AAPL,slot-name|WLAN|String|
|device_type|Airport Extreme|String|
|name|AirPort|String|
|pci-aspm-default|0|Number|
|compatible|pci14e4,43a0|String|
|model|Place with your wireless card name|String|

⚠️ **WARNING** : Compatible value you should replace and test until you get working Wi-fi connection

Some compatible you can try: `pci14e4,4353` ; `pci14e4:4331` ; `pci14e4,43ba` ; `pci14e4,43a0`

In my case (DW1820A), I have used `pci14e4,43a0` and it worked well.

**Step 3: Enable kernel extension for Wi-Fi**

Heading into `Kernel` section, enable all mention kext I have choosen below.

![Kernel-Wifi-BCM](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BCM-Wifi.png)

**Step 4: Enable kernel extension for bluetooth**

Still in `Kernel` section, enable all mention kext I have choosen below.

If you are using macOS Big Sur (11.x) and below, enable 3 kexts: `BrcmBluetoothInjector.kext` ; `BrcmFirmwareData.kext` ; `BrcmPatchRAM3.kext`

![Kernel-Blt-BCM-BS](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BCM-BLT.png)

If you are using macOS Monterey (12.x), enable 3 kexts: `BlueToolFixup.kext` ; `BrcmFirmwareData.kext` ; `BrcmPatchRAM3.kext` and MAKE SURE `BrcmBluetoothInjector.kext` IS DISABLED/NOT APPEARED.

![Kernel-Blt-BCM-BS](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BCM-BLT-M.png)

**Last step: Save your edited config.plist and restart your computer**

## Source I have used:

[OSXLatitude Guide Broadcom BCM4350 cards under High Sierra/Mojave/Catalina/Big Sur/Monterey](https://osxlatitude.com/forums/topic/11322-broadcom-bcm4350-cards-under-high-sierramojavecatalinabig-surmonterey/)

[OpenCore Wireless Guide](https://dortania.github.io/Wireless-Buyers-Guide/)
