# BIOS Configuration Tutorial

### You should config your BIOS like this: 

First, you should click Load Default BIOS, then change: 

**General:**
- Advanced Boot Options: Untick Enable Legacy Options ROMs (Just use UEFI Boot Mode, disable Legacy OS)

**System Configuration:**
- Integrated NIC: Enable (Not Enable w/PXE)
    - Enable UEFI Network Stack: Untick
- Parallel Port: Disable
- Serial Port: Disable
- SATA Operation: AHCI

⚠️: If you are using RAID Mode, consider installing AHCI Driver or re-installing Windows

- SMART Reporting: Tick Enable SMART Reporting

**Secure Boot:**
- Secure Boot Enable: Disable

**POST Behavior:**

- Fastboot: Thorough

**Virtualization Support:**

- Virtualization: Tick Enable Intel Virtualization Technology
- VT for Direct I/O: Untick Enable VT for Direct I/O
