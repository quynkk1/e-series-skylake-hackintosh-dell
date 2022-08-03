# Intel Wireless Tutorial

If you are using Intel Wireless Chipset, follow instrucment below:

**Step 1: Enable Wi-fi Extension**

Open `config.plist` and heading to `Kernel` section, you might look up for `AirPortItlwm.kext`. Tick `Enable` for this kernel extension.

> `AirPortItlwm.kext` in this EFI I used macOS Monterey (12.x) version. You may download and replace with compatible version, depend on what version of macOS you want to use.

> [Itlwm](https://github.com/OpenIntelWireless/itlwm/releases) : you can find your compatible version of your macOS here.

![Kernel-Itlwm](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-Itlwm.png)

**Step 2: Enable Bluetooth Extension**

- For macOS Big Sur (11.x) and lower (Apply for Catalina 10.15.x/Mojave 10.14.x):

Still in `Kernel` section, you might look up for `IntelBluetoothFirmware.kext` and `IntelBluetoothInjector.kext`. Tick `Enable` for that kernel extension.

![Kernel-Itlwm-BLT-11](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BLT-Itlwm-BS.png)

- For macOS Monterey (12.x):

Still in `Kernel` section, you might look up for `BlueToolFixup.kext` and `IntelBluetoothInjector.kext`. Tick `Enable` for that kernel extension.

![Kernel-Itlwm-BLT-12](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BLT-Itlwm-12.png)

**Last step: Save your `config.plist` and restart your computer.**

# Source I have used:

[Itlwm](https://github.com/OpenIntelWireless/itlwm)

[IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
