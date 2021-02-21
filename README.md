# OpenCore EFI - HP Probook 640 G1
This repo contains OpenCore EFI files for HP Probook 640 G1, in order to run macOS Big Sur. 

![macOS Big Sur Dark](/images/bigsurdark.png)

## Table of Content
* [System Specs](#SystemSpecs)
* [Whats Working / Not Working](#working/notworking)
* [BIOS Settings](#setup)

## System Specs
| Specifications  | Second Header |
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

## Whats working / not working 
Wifi
Bluetooth
Display Brightness
DisplayPort
Audio
WebCam

## Disclaimer
* Due to the limitation of the HP Bios, it does not support booting directly from the M.2 SSD. 
If you intend to use M.2 drive for macOS, you HAVE to have at least one more SATA disk for EFI booting. This drive is where we will store the EFI later. 
USB drive can also be used for booting, although its not recommended.

* Discrette Graphics will be disabled, since it is not supported under macOS Big Sur.

## Prerequisites
* Read here
https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html#prerequisites

* It's recommended to use Ethernet for initial installation.

## Prepare Install Media

## BIOS Settings

## Kexts Included
Airportilwm.kext
AppleALC.kext
IntelBluetoothFirmware.kext
IntelBluetoothInjector.kext
IntelMausi.kext
Lilu.kext
RTCMemoryFixup.kext
USBMapHP640G1.kext
VirtualSMC.kext
VoodooPS2Controller.kext
WhateverGreen.kext

## FAQ

## Credits
