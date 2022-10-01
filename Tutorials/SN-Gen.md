# Serial Number Generate Guidance:

For making your Hackintosh working well when using Apple Services, I recommend you should generate your Serial Number before install macOS.

## Things you should need:

1. Command Line (such as Terminal, Command Prompt, ...)
2. [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) from Cropnewt
3. [Xplist Editor](https://github.com/ic005k/Xplist/releases/tag/1.2.47)
4. Your knowledge about editing *.plist* file

## How do I do it ?

1. Open your `config.plist` via  and go to `PlatformInfo > Generic`

![1](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/PlatformInfo/New/SN-Gen-1.png)

2. Open GenSMBIOS you have downloaded `GenSMBIOS.bat (For Windows) and GenSMBIOS.command (For macOS)` 

![2](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/PlatformInfo/New/SN-Gen-2.png)

3. Press `1. Install/Update MacSerial` first and then `3. Generate SMBIOS`

![3](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/PlatformInfo/New/SN-Gen-3.png)

4. Type correctly (I recommend you should paste this!): MacBookPro13,1

![4](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/PlatformInfo/New/SN-Gen-4.png)

5. After typed step 4, you got 5 infomation about `Type`, `Serial`, `Board Serial`, `SmUUID`, `Apple ROM (You can ignore this)`.

- The `Type` part gets copied to Generic -> `SystemProductName`.

- The `Serial` part gets copied to Generic -> `SystemSerialNumber`.

- The `Board Serial` part gets copied to Generic -> `MLB`.

- The `SmUUID` part gets copied to Generic -> `SystemUUID`.

![5](https://github.com/quynkk1/e-series-skylake-hackintosh-dell/blob/main/Image/PlatformInfo/New/SN-Gen-5.png)

6. After inserting all part in Step 5, save your config.
