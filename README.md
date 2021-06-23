# hackintosh-skylake-z170
Hackintosh builds for Skylake

If you have the exact same build as mine, you may just copy the EFI and modify **PlatformInfo** ([how to modify](https://dortania.github.io/OpenCore-Install-Guide/config.plist/skylake.html#platforminfo)), then everything should be working.

Otherwise, please follow the official OpenCore Guide.


## Specs

| Type        | Item                       |
| ----------- | -------------------------- |
| CPU         | Intel SkyLake i7-6700      |
| Motherboard | MSI Z170 Krait Gaming      |
| Memory      | Kingston DDR4 2400 16G x 2 |
| VGA         | ~~MSI Nvidia GTX 550 Ti~~   |
|             | No support since 10.14 Mojave, changed to **Asus RX 570 4 GB** |
| Storage     | ~~NVMe M.2 Intel 600p 256G~~ Possible cause random kernel panic   |
|             | Changed to **ADATA SX8200Pro 512G**


## Guides

- [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/)
- [Getting Started with ACPI](https://dortania.github.io/Getting-Started-With-ACPI/)
- [GPU Buyers Guide](https://dortania.github.io/GPU-Buyers-Guide/)


## Requirements

- [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg/releases)


## Tools

- [SSDTTime](https://github.com/corpnewt/SSDTTime)
- [ProperTree](https://github.com/corpnewt/ProperTree)
- [MountEFI](https://github.com/corpnewt/MountEFI)
- [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
- [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)

## Drivers & Fixes

- [HfsPlus.efi](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
- [OpenRuntime.efi](https://github.com/acidanthera/OpenCorePkg/releases)
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases)
- [Lilu](https://github.com/vit9696/Lilu/releases)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases)
- [AppleALC](https://github.com/vit9696/AppleALC/releases)
- [IntelMausi](https://github.com/acidanthera/IntelMausi/releases)
- [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/)
- [NVMeFix](https://github.com/acidanthera/NVMeFix/releases)

