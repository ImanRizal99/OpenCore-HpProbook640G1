# OpenCore EFI - HP Probook 640 G1
![opencore](https://img.shields.io/badge/OpenCore-0.6.6-brightgreen)

This repo contains OpenCore EFI files for HP Probook 640 G1. Supports macOS Catalina (Read important notes first) and BigSur.

![macOS Big Sur Dark](/images/bigsurdark.png)

## Laptop Specs
| Model  | HP Probook 640 G1 |
| ------------- | ------------- |
| Processor  | Intel(R) Core(TM) i5-4310M @ 2.70GHz (Haswell)  |
| Memory | 8GB DDR 3L PC3L-12800 (1600 MHz)  |
| Hard Disk  | Samsung 1TB M.2 NVME SSD, Toshiba 128GB SATA HDD  |
| Integrated Graphics  | Intel HD Graphics 4600  |
| Discrette Graphics  | AMD Radeon HD 8750M, with 1GB dedicated DDR5 video memory |
| Display  | 14-inch diagonal LED-backlit FHD anti-glare UWVA slim (1920 x 1080)  |
| Chipset  | Intel 8 Series/C220 Chipset Family  |
| Sound Card  |   |
| Wireless Card  | Intel Dual Band Wireless-AC 7260 Series  |
| Ethernet | Intel Gigabit Ethernet i217-V  |
| Trackpad  |   |
| SD Card Reader  |   |
| Video Port  | Displayport, VGA  |
| Sound Port  | Combo 3.5mm headphone jack / microphone  |

## Disclaimer
* I am not responsible for any damage caused to your components, data loss, or anything else that may happen throughout this process.
* No selling of EFI folder (config) that's readily available for free.
* Discrette Graphics will be disabled, since it is not supported under macOS Big Sur.

## Important Notes
* Due to the limitation and quirkness of the HP bios installed on this laptop, if you only have one M.2 SSD installed, you will need to install additional SATA HDD for booting. Look at FAQ for more information.
* Airportitlwm.kext requires specific macOS version to function. Include in this repo is for BigSur. For Catalina use, download the kext [here](https://github.com/OpenIntelWireless/itlwm/releases) specific for Catalina and put it in the kext folder replacing the other one.


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
* iCloud

Not Working
* Airdrop , Handoff
* iMessage , Facetime
* Discrette Graphics (not supported under macOS)

Not Tested
* SD Card Reader
* Sleep
* Battery reader (my battery not working)

## Bugs
* Wifi is stable but very slow, due to [Airportitlwm.kext/itlwm.kext](https://openintelwireless.github.io/itlwm/FAQ.html#usage) 
* [You tell me](https://github.com/ImanRizal99/OpenCore-HpProbook640G1/issues)

## Prerequisites
* Read here
https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html#prerequisites

* It's strongly recommended to use Ethernet for initial installation.

* Update your BIOS first to the latest version.

## BIOS Settings
* Boot Options
  * UEFI Hybrid (With CSM)
  * Fast Boot : disabled 
  * USB device boot : enabled
  * Upgrade Bay Hard Drive boot : enabled
* Device Configurations
  * Video memory size : 512mb
  * Data Execution Prevention : enabled
  * Sata Device Mode : AHCI
  * Hybrid Graphics Enhanced Display Feature : enabled
* Built-In Device Options
  * LAN/WLAN Switching : disabled
  * Wake Unit from sleep when lid is opened : disabled
  * M.2 SSD : enabled (only if you intent to use M.2 SSD)
* Port Options
  * Serial Port : disabled
  * Parallel Port : disabled
  * Flash Media Port : disabled
  * USB Port : enabled
  * Smart Port : disabled
  * eSata Port : enabled


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
* Why this laptop won't boot from M.2 SSD?
  * Due to the limitation of the HP Bios on this laptop, it does not support booting directly from the M.2 SSD (i don't know why). 
If you intend to use M.2 drive for macOS, you HAVE to have at least one SATA disk for EFI booting. This drive is where we will store the EFI later and boot into. 
USB drive can also be used for booting, although its not recommended.
 
* I'm using a different type of NVMe m.2 ssd, and as soon as I installed macOS on it, it kernel panic.
   * In that case, please download NVme.kext and put it inside the EFI/OC/Kext folder, then do a clean snapshot or manually update the config.plist

* Can i sell this EFI?
   * NO

