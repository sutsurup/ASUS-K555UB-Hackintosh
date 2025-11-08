# ASUS K555UB XO092T | Intel® Core™ i5 (6th Gen)

[![macOS](https://img.shields.io/badge/macOS-10.15.7-orange)](https://www.apple.com/macos/catalina/)
[![OpenCore](https://img.shields.io/badge/Clover-5.1-9cf)](https://github.com/CloverHackyColor/CloverBootloader)
[![release](https://img.shields.io/badge/download-last%20version-blue.svg)](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/releases)

<img align="right" src="Images/logo.png" alt="ASUS" width="200">

[Türkçe](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/blob/master/README.md) | English

**macOS Version: 10.15.7**

**Clover Version: v5.1 r5129**

**Other supported K555UB models:** XO066T/XO093T/XO096T/XO097T/XO198T/XO266T/XO099D/XO227D

# Details

    Date:         June 5, 2020
    Status:       Stable
    Support:      BIOS (Version 304)
    Build:        Adapted by sutsurup for ASUS K555UB device using Clover Bootloader

![Alt text](Images/Hackintosh.png)

## Hardware

| ║▌║ **ASUS** ║▌║ | Detail                                                 |
| ------------------- | ------------------------------------------- |
| Model Name      | K555UB XO092T      |
| Motherboard           | X555UB     |
| CPU              | Intel(R) Core(TM) i5-6200U CPU @ 2.30GHz (max. 2.80GHz) Skylake-U              |
| RAM           | 4 GB 1600 MHz DDR3 + Samsung 8 GB 1600MHz DDR3    |
| Internal Graphics Card | Intel(R) HD Graphics 520 (1 GB)                     |
| Wi-Fi             | Realtek RTL8723BE Wireless LAN 802.11n PCI-E |
| Camera          | ASUS USB2.0 VGA UVC WebCam           |
| Audio       | Realtek ALC256 (Apple ALC Layout: 28)                        |
| Touchpad       | ELAN1000                        |
| BIOS Version      | X555UB.304 (Version 304)                   |

# Replaced hardware

    HGST Travelstar 2.5-Inch 1TB 5400RPM | https://amzn.to/2LFlFMe
    Realtek RTL8723BE Wireless LAN 802.11n PCI-E
    
    
    Reason: SSD Upgrade (for speed)
    Reason: Apple does not support the RTL8723BE wireless card

| Product    | Information |
| ------------- | ------- |
| Samsung SSD 860 EVO 500GB   | https://amzn.to/2z9ef17   |
| James Donkey JD120 120GB   | https://bit.ly/2ZisP0W   |
| Dell DW1510 Wireless Card Chip: BCM4322   | https://bit.ly/2yXeyMi   |

> II. The SSD was installed after removing the DVD-RW drive from the device. Required part: You can install an HDD or SSD inside a DVD to HDD caddy (similar to https://amzn.to/2Tdf1B5) and then insert it into the DVD-RW port.

> The Dell DW1510 is natively supported in macOS versions like High Sierra and Mojave. If you buy this card, you can use it with the Plug-and-Play method. However, support for this card ended when Catalina was released. To get the card working in Catalina, you need to extract the IO80211Family.kext and IO80211FamilyV2.kext files from the /System/Library/Extensions folder in a High Sierra or Mojave system and install them in the same directory in Catalina. I have extracted these files from a Mojave system and am sharing them under V1.1 in the Releases section. I have explained how to install these files in the post-installation section.

# Unsupported hardware

    1. External Graphics Card (NVIDIA GeForce 940M PCI-e) [Not supported by Apple]
    2. 'FN + media control' function keys [Patched - working]
    3. ELAN1000 Touchpad [Patched - working]
    4. Realtek RTL8723BE Wireless (Wi-Fi card) [Not supported by Apple] -Solution is further down-

## Compatibility
The EFI folder I shared is supported up to **macOS Catalina 10.15.7**.
If you are going to install macOS Mojave 10.14.6, move all files from EFI > Clover > Kexts > 10.15 on the USB drive's EFI partition to the parent directory 10.14. For macOS High Sierra 10.13.6, move them to the 10.13 folder.

## Back up your data
**Before proceeding with the installation instructions;** If you have an operating system such as Windows, Linux, or similar installed on your system, **do not forget to back up your important data** just in case. The disk structure may be corrupted when deleting the wrong disk or **formatting the disk to APFS**. I recommend that you store your backups in an online storage area like [Yandex.Disk](https://disk.yandex.com.tr) or on an external disk (if you have one).

## Pre-installation requirements
* Download the version of [Etcher](https://www.balena.io/etcher/) suitable for your operating system.
* Download the RAW installation file required for macOS installation, packaged by KaoS, from the [OSXINFO site](https://osxinfo.net/konu/macos-catalina-amd-intel-kurulum-imaji.10455). | The link is at the bottom of the topic.
* Download the latest EFI.zip file I shared: [ASUS-K555UB-Hackintosh/releases/1.2](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/releases)

# macOS Installation Instructions


1. Enter the BIOS screen and change the following values (the ESC key helps to enter the BIOS menu):

	- Display memory: 64MB
	- Disable Intel® Virtualization Technology.
	- Disable Secure Boot.
	- Recommended: Select the USB drive as the first boot option in the Boot menu (Top option).

2. To start the macOS installation, write the MAC installation file (RAW) to your USB drive using the Etcher program.
3. Right-click on the downloaded EFI.zip file and extract it to a folder. Delete the BOOT and CLOVER folders inside the EFI folder on the USB drive's EFI partition, and upload the ones from the EFI folder you downloaded.
4. Insert the USB drive, start the device, and press the ESC key as soon as you press the power button. Continue by selecting the USB drive and choose the macOS installer.
5. The touchpad will work, or you can use a USB Mouse.
6. If you are going to install the macOS system alongside Windows, you need to create an Apple HFS disk [as done in this guide](https://www.youtube.com/watch?v=nvXew__fuQE). You will proceed by selecting this disk during the installation phase.
7. If you will only use macOS on the device, go to the "Disk Utility" section when the installation screen appears, press the button above the "View" text in the upper left corner and say show all disks. This way, your HDD/SSD hardware will appear at the bottom. Like "Samsung SSD". Click on it and then click on the "Erase" button on the right side. You will select "APFS" as the format, "GUID Partition Map" as the Scheme, and say erase again. When the process is complete, close this window and continue with the installation normally, select the APFS disk you just created. The device will restart after the installation is finished. After the last operation, you will no longer select the "macOS installer". When it restarts, select the USB drive again as you did in step 4, but this time select the new APFS disk you created. You will select the new APFS disk every time the computer restarts. When the rest of the installation is finished, the system will be ready to use.

Since you have just installed the system, it configures itself during the first few startups. Therefore, it may start up slowly.
Be patient.
```
$ You can reach me for support at the email address I shared or by opening an issue.
``` 

# Post-installation guides/tools you can use
* Recommended: If you are going to log in to iCloud or want to use iMessage, FaceTime, follow this guide exactly: [Enabling iMessage on Hackintosh Devices](https://osxinfo.net/konu/hackintosh-cihazlarda-imessage-etkinlestirmek.84)
* [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/)
* Hackintool ([Forum thread](https://www.insanelymac.com/forum/topic/335018-hackintool-v286/) | [Direct download link](http://headsoft.com.au/download/mac/Hackintool.zip))
* Kext Updater ([Download](https://bitbucket.org/profdrluigi/kextupdater/downloads/) | [Forum](https://www.hackintosh-forum.de/forum/thread/32621-kext-updater-neue-version-3-x/) {German})

### How to get the Dell DW1510 wireless card to work in Catalina?
I mentioned earlier that the Dell DW1510 wireless card is not supported in Catalina. Download the [Mojave-IO80211Family.zip](https://github.com/sutsurup/ASUS-K555UB-Hackintosh/releases/tag/1.1) file I shared with V1.1 in the Releases section.

1. Download the Kext Utility application from the [cVad's MAC](http://cvad-mac.narod.ru/index/0-4) site (Press the blue arrow).
2. We need to disable SIP to install the kexts on the system, open Terminal, and type the codes I will specify in order:
	- sudo -s (It will then ask for a Password, enter the MAC's password)
	- spctl --master-disable
	- mount -uw /
	- killall Finder
3. Move the downloaded Kext Utility application to the Applications folder and run it.
4. After running it, wait until you see the "Enjoy" text.
5. Drag and drop the IO80211Family.kext and IO80211FamilyV2.kext files from Mojave-IO80211Family.zip onto the application and grant permission.
6. Wait again until the "Enjoy" text appears, the installation is complete.
7. Restart the device and enjoy Wi-Fi. :)

# How do I use Wi-Fi?
Since the Realtek RTL8723BE Wireless card that comes with the K555UB system is **not supported** by Apple, you need to replace this card. So what can we do about this?

1. The motherboard supports Half Mini PCI-e cards. For this reason, you should **definitely** go for Half Mini PCI-e cards, not Mini PCI-e.
2. If you want macOS functions like Bluetooth and AirDrop to work, prefer cards that support +Bluetooth.
3. You can buy a Wireless USB Adapter. I am currently using the [ASUS Wireless N150 USB Nano Adapter](https://www.asus.com/tr/Networking/USBN10_NANO).

 I ordered Broadcom DW1510 and Atheros AR5BHB92 cards from AliExpress. **We'll do a test when it arrives.** :)
 Also: I recommend these two cards, especially the AzureWave AW-CB160H, and also the AW-CE123H.
 Edit 05/10/2020: The DW1510 wireless card has arrived, with a tax of 18 Lira. :) It has been included in the hardware.

## How to introduce Wireless USB Adapters to the system?

The Wireless USB Adapters that the installation file I will share runs are listed here:
[chris1111/Wireless-USB-Adapter-Clover](https://github.com/chris1111/Wireless-USB-Adapter-Clover)

1. You can download the latest version from here: [Wireless-USB-Adapter-Clover/Releases](https://github.com/chris1111/Wireless-USB-Adapter-Clover/releases), or by clicking this link directly. [Wireless-USB-Adapter-Clover/V14.zip](https://github.com/chris1111/Wireless-USB-Adapter-Clover/files/4301774/Wireless.USB.Adapter.Clover-V14.zip)  
2. After downloading the installation file, complete the installation. 
3. Restart the device.
```
$ The original ASUS software file for the ASUS Wireless N150 USB Nano Adapter is below:  
```  
1. [USB-N10 NANO // Drivers & Tools](https://www.asus.com/tr/Networking/USBN10_NANO/HelpDesk_Download/) 
2. Alternatively, you can also install the PKG file I shared in the "Wi-Fi Fix" folder in the repo.

> The main reason I shared the last mentioned PKG file is that the signal indicator works compared to the other chris1111 and original ASUS installation files. In the others, there is a symbolic (fixed) Wi-Fi icon in the status bar, you can only see the signal strength when you enter the list, but the Wireless signal strength icon in the status bar that comes with the installation file in the "Wi-Fi Fix" folder is animated, it shows the signal strength clearly.

## Contact
Website: https://sutsurup.tr //
Mail: [veysel@sutsurup.tr](mailto:veysel@sutsurup.tr)

## Other links
- [ASUS Official Website // K555UB](https://www.asus.com/tr/Laptops/K555UB)
- [High Sierra 10.13](https://osxinfo.net/konu/basarili-kurulum-asus-k555ub-xo092t-mojave-10-14.6632)
- [Mojave 10.14](https://osxinfo.net/konu/basarili-kurulum-asus-k555ub-xo092t-mojave-10-14.6632)
- [Catalina 10.15.3](https://osxinfo.net/konu/asus-k555ub-xo092t-catalina-10-15-3.13141)
- [Clover Bootloader](https://github.com/CloverHackyColor/CloverBootloader/releases)

## Support.
If you find the project useful, you can donate to help me find resources.
```
₿ 1Q8CEMHTuecxPUJpEdpRiG6Bg2GVtzw4bN
``` 
<a href='https://github.com/sutsurup/sutsurup/blob/main/Donate.md'><img alt='Donate' src='https://github.com/sutsurup/MSI-Hackintosh-Build/blob/main/Images/donate.png?raw=true' height='360px' width='375px'/></a>
```
You can access alternative options by clicking the QR code
``` 

### Thanks:
**LeeBinder** (README.md examples), **RehabMan** (ACPI hotpatch), and many others who support **Hackintosh** systems...

Good luck!
