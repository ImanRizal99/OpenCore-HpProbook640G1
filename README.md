# OpenCore EFI - HP Probook 640 G1
This repo contains OpenCore EFI files for HP Probook 640 G1. Supports Catalina and BigSur.

![macOS Big Sur Dark](/images/bigsurdark.png)

## Table of Content
* [System Specs](#SystemSpecs)
* [Whats Working / Not Working](#working/notworking)
* [BIOS Settings](#setup)
* [BIOS Settings](#setup)

## Laptop Specs
| Specifications  |  |
| ------------- | ------------- |
| Laptop Model  | HP Probook 640 G3  |
| Processor  | Intel(R) Core(TM) i5-4310M @ 2.70GHz (Haswell)  |
| Memory | 8GB DDR 3L PC3L-12800 (1600 MHz)  |
| Hard Disk  | Samsung 1TB M.2 NVME SSD, Toshiba 128GB SATA HDD  |
| Integrated Graphics  | Intel HD Graphics 4600  |
| Discrette Graphics  | AMD Radeon HD 8750M, with 1GB dedicated DDR5 video memory |
| Display  | 14-inch diagonal LED-backlit FHD anti-glare UWVA slim (1920 x 1080)  |
| Chipset  | Intel 8 Series/C220 Chipset Family  |
| Sound Card  | Content Cell  |
| Wireless Card  | Intel Dual Band Wireless-AC 7260 Series  |
| Ethernet | Intel Gigabit Ethernet i217-V  |
| Trackpad  | Content Cell  |
| SD Card Reader  | Content Cell  |
| Video Port  | Displayport, VGA  |
| Sound Port  | Combo 3.5mm headphone jack / microphone  |

## Disclaimer
* I am not responsible for any damage caused to your components, data loss, or anything else that may happen throughout this process.

* Due to the limitation of the HP Bios, it does not support booting directly from the M.2 SSD. 
If you intend to use M.2 drive for macOS, you HAVE to have at least one more SATA disk for EFI booting. This drive is where we will store the EFI later. 
USB drive can also be used for booting, although its not recommended.

* Discrette Graphics will be disabled, since it is not supported under macOS Big Sur.

## Whats working / not working 
Working
* Hardware Acceleration (Intel HD Graphics 4300)
* Wifi
* Bluetooth
* Ethernet
* Display Brightness
* DisplayPort
* Audio (Built-in / DisplayPort)
* WebCam
* Keyboard / Trackpad
* USB Ports

Not Working
* Airdrop , Handoff
* iMessage , Facetime

Not Tested
* SD Card Reader

## Bugs
* Wifi is very slow, due to itlwm.kext [Read more](https://openintelwireless.github.io/itlwm/FAQ.html#usage) 
* You tell me

## Prerequisites
* Read here
https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html#prerequisites

* It's strongly recommended to use Ethernet for initial installation.

## BIOS Settings

## Kexts Included / Credits
* [Lilu.kext](https://github.com/acidanthera/Lilu) - Arbitrary kext that is required other kexts to work like AppleALC.kext.
* [RTCMemoryFixup.kext](https://github.com/acidanthera/RTCMemoryFixup) - Emulate some offsets in CMOS (RTC) memory. Avoid some conflicts between AppleRTC and firmware/BIOS of the Laptop.
* [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) - Advanced Apple SMC emulator in the kernel. Requires Lilu for full functioning.
* [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen) - Lilu plugin providing patches to select GPUs on macOS.
* [Wireless](https://openintelwireless.github.io)
   * [Airportilwm.kext](https://github.com/win1010525/Airportitlwm-kext) - Enables Wifi on Intel Chip. Uses Apple's IO80211Family. It provides certain Airport features. It's not as stable as itlwm.kext.
   * [IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) - Enables native Bluetooth support on Intel Chip.
   * [IntelBluetoothInjector.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)

* Audio
   * [AppleALC.kext](https://github.com/acidanthera/AppleALC) - Enables audio on a hackintosh.

* Ethernet
   * [IntelMausi.kext](https://github.com/acidanthera/IntelMausi) – Enables ethernet for motherboards using an Intel Ethernet Chipset.

* USB / WebCam
   * USBMapHP640G1.kext

* Keyboard / Mouse
   * [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2) - VoodooPS2Trackpad uses VoodooInput's Magic Trackpad II emulation in order to use macOS native driver instead of handling all gestures itself. This enables the use of any from one to four finger gestures defined by Apple


## FAQ
