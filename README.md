# Hackintosh
### B660M AORUS PRO DDR4 / Intel i5 12400F / AMD Radeon RX 6650 XT
<img width="1888" alt="Screenshot 2024-03-21 at 12 00 33 1" src="https://github.com/brunorcoelho/Hackintosh-B660M-Aorus-Pro-DDR4-i5-12400F-RX-6650XT/assets/71451870/8174b1e0-ddbe-4495-9ef2-e8f0a5683e1b">

This repository contains my EFI used to successfully boot OpenCore 0.9.9 and install macOS Sonoma 14.4.

## Specifications


| Hardware    | Model                                      |
| ----------- | ------------------------------------------ |
| CPU         | Intel Core i5 12400F                       |
| GPU         | Powercolor Hellhound AMD Radeon RX 6650 XT |
| Motherboard | Gigabyte B660M Aorus Pro DDR4              |
| RAM         | HyperX Fury 2x8GB DDR4 3200MHZ             |
| Storage     | KINGSTON SNV2S1000G 1TB NVME M2            |
| Storage     | XPG GAMMIX S41 256GB NVME M2               |

## Working features

- CPU power management
- Audio
- GPU acceleration
- USB
- Secure boot
- DRM
- Sleep
- iServices

## Non-working features

- WiFi (no card installed)
- Bluetooth (no card installed)
- AirPlay
- SideCar



## SSDTs

| SSDT            | What for?                                         |
| --------------- | ------------------------------------------------- |
| [SSDT-PLUG-ALT] | [Fixing Power Management on Alder Lake CPUs]      |
| [SSDT-BRG0]     | [Spoofing unsupported RX 6650XT as an RX 6600 XT] |
| [SSDT-AWAC]     | [Fixing System Clocks]                            |
| [SSDT-USBX]     | [Fixing Embedded Controller]                      |
| [SSDT-EC]       | [Fixing Embedded Controller]                      |

## Kexts
| Kext                  | What for?                                                                                    |
| --------------------- | -------------------------------------------------------------------------------------------- |
| Lilu                  | A kext to patch many processes.                                                              |
| AppleALC              | Used for AppleHDA patching, allowing support for the majority of on-board sound controllers. |
| VirtualSMC            | Emulates the SMC chip found on real macs.                                                    |
| SMCProcessor          | Used for monitoring Intel CPU temperature.                                                   |
| SMCRadeonGPU          | Exports GPU sensor values to VirtualSMC for monitoring tools that utilise the SMC.           |
| WhateverGreen         | Used for graphics patching, DRM fixes, board ID checks, framebuffer fixes, etc               |
| RadeonSensor          | Main GPU sensor component.                                                                   |
| CPUFriend             | Dynamic power management data injection.                                                     |
| CPUFriendDataProvider | Optimize power management configuration.                                                     |
| NVMeFix               | Fixes NVME power management and initialization on non-Apple NVMe devices.                    |
| RestrictEvents        | Showing proper CPU name (also enables E-cores but i5-12400f has none).                       |
| USBToolBox            | Make USB mapping easier.                                                                     |
| UTBMap                | USB map.                                                                                     |










































[Fixing Embedded Controller]: https://dortania.github.io/Getting-Started-With-ACPI/Universal/ec-fix.html
[Fixing Power Management on Alder Lake CPUs]: https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/Source/SSDT-PLUG-ALT.dsl
[Fixing System Clocks]: https://dortania.github.io/Getting-Started-With-ACPI/Universal/awac.html
[Spoofing unsupported RX 6650XT as an RX 6600 XT]: https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/AcpiSamples/Source/SSDT-BRG0.dsl
[SSDT-AWAC]: /EFI/OC/ACPI/SSDT-AWAC.aml
[SSDT-BRG0]: /EFI/OC/ACPI/SSDT-BRG0.aml
[SSDT-EC]: /EFI/OC/ACPI/SSDT-EC.aml
[SSDT-PLUG-ALT]: /EFI/OC/ACPI/SSDT-PLUG-ALT.aml
[SSDT-USBX]: /EFI/OC/ACPI/SSDT-USBX.aml
