# Hướng dẫn cho WiFi Intel

Nếu bạn dùng card WiFi Intel, làm theo hướng dẫn bên dưới:

**Bước 1: Bật Kext WiFi**

Mở `config.plist` và vào phần `Kernel` , Bạn hãy tìm kext `AirPortItlwm.kext`. Tick vào nút `Enable` cho kext này.

> `AirPortItlwm.kext` trong EFI này, tôi đã sử dụng phiên bản dành cho macOS Monterey (12.x). Bạn có thể tải xuống và thay thế bằng phiên bản tương thích, tùy thuộc vào phiên bản macOS bạn muốn sử dụng.

> [Itlwm](https://github.com/OpenIntelWireless/itlwm/releases) : bạn có thể tìm thấy kext dành cho phiên bản macOS tương thích của mình tại đây.

![Kernel-Itlwm](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-Itlwm.png)

**Bước 2: Bật Kext Bluetooth**

- Đối với macOS Big Sur (11.x) trở xuống (Áp dụng cho Catalina 10.15.x / Mojave 10.14.x):

Trong phần `Kernel` , Bạn hãy tìm `IntelBluetoothFirmware.kext` và `IntelBluetoothInjector.kext`. Tick `Enable` cho các kext đó.

![Kernel-Itlwm-BLT-11](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BLT-Itlwm-BS.png)

- Đối với macOS Monterey (12.x):

Trong phần `Kernel`, Bạn hãy tìm `BlueToolFixup.kext` và `IntelBluetoothInjector.kext`. Tick `Enable` cho các kext đó.

![Kernel-Itlwm-BLT-12](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BLT-Itlwm-12.png)

**Bước cuối: Lưu lại file `config.plist` và restart máy bạn.**

# Nguồn tôi đã dùng:

[Itlwm](https://github.com/OpenIntelWireless/itlwm)

[IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
