# Hướng dẫn cho người dùng có Card Wifi Broadcom
Đối với người dùng đang sử dụng Card Wifi Broadcom, để biết tên chipset của card `Bạn nên dùng AIDA64.`

## Các chipset wifi được hỗ trợ: 

- Big Sur (11.x) và Monterey (12.x) trở lên: BCM943602, BCM94360, BCM94352, BCM94350

- Catalina (10.15) trở lên: BCM943224, BCM94331

- Mojave (10.14) trở lên: BCM94322

Nếu card WiFi của bạn không có trong danh sách thì làm theo hướng dẫn bên dưới ⬇️.

## Hướng dẫn :

**Step 1: Tìm đường dẫn PCI của card WiFi qua Hackintool và thêm nó vào config.plist phần > `DeviceProperties`**

> Zí Zụ : Ví dụ đường dẫn Pci của DW1820A (Tôi đã thay card) là `PciRoot(0x0)/Pci(0x1C,0x0)/Pci(0x0,0x0)` và kiểm tra bạn đã thêm đường dẫn như bên dưới chưa.

Mở Hackintool, chọn tab `PCIe`, tìm card wifi của bạn, nhấp chuột phải vào nó và bấm vào `Copy Device Path`

![hackintool-1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/DeviceProperties/Hackintool-PCIe.png)

Mở config.plist trong EFI, nhấp vào phần `DeviceProperties`, thêm PCI bằng cách nhấp vào nút` + 'và dán đường dẫn PCI vào.

![image1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/DeviceProperties/DeviceProperties-WLAN-BCM-1.png)

**Bước 2: Thêm properties**

![image2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/DeviceProperties/DeviceProperties-WLAN-BCM-2.png)

Bạn có thể tham khảo thông tin bên dưới ⬇️

|Key |Value |Type |
| --- | --- | --- |
|AAPL,slot-name|WLAN|String|
|device_type|Airport Extreme|String|
|name|AirPort|String|
|pci-aspm-default|0|Number|
|compatible|pci14e4,43a0|String|
|model|Place with your wireless card name|String|

⚠️ **WARNING** : Giá trị tương thích bạn nên thay thế và kiểm tra cho đến khi bạn nhận được kết nối Wi-fi hoạt động

Một số compatible bạn có thể thử: `pci14e4,4353` ; `pci14e4:4331` ; `pci14e4,43ba` ; `pci14e4,43a0`

Trong trường hợp của tôi (DW1820A), Tôi đã dùng `pci14e4,43a0` và nó hoạt động rất tốt.

**Step 3: Bật Kext WiFi**

Heading into `Kernel` section, enable all mention kext I have choosen below.

![Kernel-Wifi-BCM](https://raw.githubusercontent.com/quynkk1/e-series-skylake-hackintosh-dell/main/Image/Kernel/Kernel-BCM-Wifi.png)

**Step 4: Bật Kext Bluetooth**

Trong mục `Kernel` , bật các kext tôi đã ghi bên dưới.

Nếu bạn dùng macOS Big Sur (11.x) và các bản thấp hơn, bật 3 kext: `BrcmBluetoothInjector.kext` ; `BrcmFirmwareData.kext` ; `BrcmPatchRAM3.kext`

![Kernel-Blt-BCM-BS](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/Kernel-BCM-BLT.png?raw=true)

Nếu bạn dùng macOS Monterey (12.x), bật 3 kext: `BlueToolFixup.kext` ; `BrcmFirmwareData.kext` ; `BrcmPatchRAM3.kext` chắc chắn `BrcmBluetoothInjector.kext` đang tắt.

![Kernel-Blt-BCM-BS](https://raw.githubusercontent.com/quynkk1/e-series-skylake-hackintosh-dell/main/Image/Kernel/Kernel-BCM-BLT-M.png)

**Bước cuối, save file config và restart máy**

## Các hướng dẫn tôi đã dùng:

[OSXLatitude Guide Broadcom BCM4350 cards under High Sierra/Mojave/Catalina/Big Sur/Monterey](https://osxlatitude.com/forums/topic/11322-broadcom-bcm4350-cards-under-high-sierramojavecatalinabig-surmonterey/)

[OpenCore Wireless Guide](https://dortania.github.io/Wireless-Buyers-Guide/)
                            
