# Dell Latitude E-Series Skylake Hackintosh
Repo chứa tất cả các bản efi hoàn chỉnh cho CPU Skylake trên macOS.

Tôi tạo và test EFI trên Dell Latitude E5570, nhưng tôi cần xác nhận xem EFI này có đang hoạt động trên các tất cả các dòng máy Dell Skylake E-Series khác hay không.

**Cấu hình laptop của tôi:**

| Phần cứng  | Dell Latitude E5570 | Chú thích |
| ------------- | ------------- | --------|
| CPU | Intel Core i3-6100U (Skylake) 2.30 GHz | |
| iGPU | Intel HD Graphics 520  | |
| dGPU | AMD R7 M370 2GB  |Tôi không có dGPU này |
| Memory | 2 x 8GB Samsung DDR4 |  |
| Storage | NVME Hynix 250GB |  |
| Ethernet | Intel Ethernet I219-LM |  |
| Wireless | Dell Wireless DW1820A | BCM94350 |
| Bluetooth | Dell Wireless DW1820A | BCM94350_C2 |
| Card Reader | Realtek RTS525A |  |
| macOS Installed | macOS Monterey 12.4 | |

# Danh sách EFI:
Bootloader: OpenCore 0.8.1 - Cập nhật 29/6/2022

| Tên máy | Tên CPU | Máy có hỗ trợ không ? | Chú thích |
| ---- | ------ | ------ | ----- |
| E5470 |  ? | Need testing. | -/- |
| E5570 |  i3-6100U | **Yes** | 1 |
| E7270 |  i5-6200U | **Yes** | -/- |
| E7470 |  ? | Need testing. | -/- |

1: Tắt dGPU của bạn (Nếu bạn có) bằng [SSDT](https://dortania.github.io/Getting-Started-With-ACPI/Laptops/laptop-disable.html)

**Lưu ý: Danh sách này chưa được hoàn chỉnh. Nếu bạn có kiểu máy tương thích và nó hoạt động khi dùng EFI của tôi, vui lòng xác nhận.**

- Hai hình ảnh dưới đây liệt kê những SSDT và bản vá lỗi mà tôi đã sử dụng.
![ACPI-SSDT](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/ACPI/ACPI-SSDTs.png)
![ACPI-Patches](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/ACPI/ACPI-Patches.png)

# Điều gì đang hoạt động?
Mọi thứ đều hoạt động ...

# Điều gì không hoạt động hoặc lỗi?
Hmmm ... Tôi không thể tìm thấy bất kỳ lỗi nào và mọi thứ không hoạt động.

# Một số phần khác:
> **⚠️ CẢNH BÁO: BẠN PHẢI ĐỌC KỸ PHẦN NÀY!**

- **Số seri:** : [Đọc ở đây](https://dortania.github.io/OpenCore-Install-Guide/config.plist/skylake.html#platforminfo)

- **Màn hình cảm ứng:** Tôi đã thêm VoodooI2C để dùng màn hình cảm ứng. Tuy nhiên, nó đã bị vô hiệu hóa. Nếu bạn có loại máy này, bạn có thể kích hoạt `VoodooI2C.kext` và các kexts liên quan đến nó trong config.plist . Bạn có thể tham khảo [hình ảnh này](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Touchscreen-user-picture.md)

- **Card wifi:** Bạn check tại đây : [Broadcom Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/Wireless-Broadcom-VI.md), [Atheros Wireless User](), [Intel Wireless User](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Tutorials/Wireless-Intel-VI.md)

- **USB:** Bạn cần map USB của mình theo cách thủ công để sử dụng tốt hơn. [USB Mapping Guide của Dortania](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html)

*Lưu ý: Nếu bạn muốn cài đặt macOS 11.2.3 hoặc phiên bản thấp hơn, hãy để nguyên `XHCIPortLimit` trong kích hoạt cấu hình.*
![XHCIPort](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/XHCIPortLimit.png)
![XHCIPortPT](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Kernel/XHCIPortLimit-ProperTree.png)

- **Tối ưu hóa Quản Lí Hiệu Năng:** CPUFriend sẽ giúp bạn. [Xem tại đây](https://dortania.github.io/OpenCore-Post-Install/universal/pm.html#using-cpu-friend)

# Làm cách nào để cài đặt macOS?
**Bạn có 2 tùy chọn:**

Tùy chọn 1: [Cài đặt online.](Https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) Có thể mất nhiều thời gian để cài đặt. Sử dụng phương pháp này khi bạn có USB dưới 8GB hoặc bạn chỉ thư giãn trong thời gian rảnh rỗi, lmao 🐸.

Tùy chọn 2: [Cài đặt offline.]() Phương pháp này yêu cầu bạn có USB lớn hơn 8GB (Khuyến nghị tối thiểu 16GB).

- Tất cả những gì bạn cần là tải xuống EFI và sao chép nó vào Phân vùng EFI trong USB của bạn.

# Một số hình minh họa
![SCS1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image.jpeg)
![SCS2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/Image%202.png)

# Rất cảm ơn:
- [Dortania](https://github.com/dortania) vì [OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) và bootloader
- [Acidanthera](https://github.com/acidanthera), [SkyrilHD](https://github.com/SkyrilHD) và các lập trình viên khác vì đã cung cấp cho tôi rất nhiều kext.
- [NLTD2010](https://github.com/NLTD2010) vì bản dịch tv ngu ngốc này.
- [Tôi](https://github.com/quynkk1) vì đã tạo ra cái EFI này lmao =) .
