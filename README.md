
# OpenCore Hackintosh EFI For MSI GF63 Thin 9SCXR 

The EFI is nearly perfect for the MSI GF 63 Thin 9SCXR Tested On  **Sonoma** , although it's not perfect in some aspects, but major things are Fixed and working absolutely fine. Before using this EFI, follow the complete guide.
## Screenshot
![Screenshot 2023-12-01 at 2 50 32 PM](https://github.com/rahulhingve/Hackintosh-Msi-GF63-Thin-9SCXR-Sonoma/assets/62886652/b8c63940-25a5-463f-8a3e-4fff7a271c4a)

![Screenshot 2023-12-01 at 2 57 39 PM](https://github.com/rahulhingve/Hackintosh-Msi-GF63-Thin-9SCXR-Sonoma/assets/62886652/9f1e7460-a8b0-483b-a267-2cc28a7ab4c0)



## Video




https://github.com/rahulhingve/Hackintosh-Msi-GF63-Thin-9SCXR-Sonoma/assets/62886652/393ffa3b-b626-476e-81a7-dd4f943c2873










# Warning !

**After Booting to macOS Dont Sign Into Apple Account Change The Serial Number  First. IF You Dont Know How to Then follow the following Guide**

**Use Both Guide And Video**

Use THIS In SMBIOS Tools =>    MacBookPro16,1


- Tool Link
https://github.com/corpnewt/GenSMBIOS

-  Guide
https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#platforminfo

- Video With TimeStamp
https://youtu.be/jvb-BIMV1Mw?si=a8llG4d1W8aXJb0d&t=2046
<hr>

## Specs













| Name             | Details                                                                |
| ----------------- | ------------------------------------------------------------------ |
|Model|GF63-Thin-9SCXR|
| CPU | Intel Core i7-9750H   |
| CPU Family |  Coffee Lake  |
| WiFi Chipset |Intel Wireless-AC 9560 160MHz  |
| Audio Codec |  ALC 235  |
| SSD |  KINGSTON OM8PCP3512F-AI1 (500gb) |




## Full Specs

[Click here](https://www.msi.com/Laptop/GF63-Thin-9SCXR/Specification)


## Description

Everything was easily fixed, but there was one main problem where the **display backlight** would turn on after **3-5 minutes** of being turned on. This issue really messed up my mind, and after some time, I did some research on GitHub. I found a solution and it was successful. The problem was that in Sonoma, the display port was recognizing as an HDMI port. I followed a guide, replaced or added some kext files, and it got fixed.
**Tested On Sonoma**

   System Version:	macOS **Sonoma** 14.1.1 (23B81)
  Kernel Version:	Darwin 23.1.0

Used **AirportItlwm** For Wifi fix And Working Fine

Used **IntelBluetoothFirmware** For Fixing Bluetooth

Used https://github.com/XuanTung95/hackintosh_msi_gf63_9sc for Fixing **black screen on startup**
- [@XuanTung95](https://github.com/XuanTung95) Thanks

##More On Fixing Black Screen Or Backlight 3-5 Minutes Delay 
https://dortania.github.io/OpenCore-Post-Install/gpu-patching/intel-patching/connector.html

framebuffer-patch-enable = 01000000 Enables WhateverGreen's patching mechanism framebuffer-conX-enable = 01000000 Enables WhateverGreen's patching on conX framebuffer-conX-type = 00080000 Sets the port to HDMI(<00 08 00 00>)
![Screenshot 2023-12-01 at 3 49 43 PM](https://github.com/rahulhingve/Hackintosh-Msi-GF63-Thin-9SCXR-Sonoma/assets/62886652/a783eb94-7155-49a0-ba90-a8fd1044c366)




Update WhateverGreen, Lilu, VirtualSMC, AppleALC, Bluetooth, Airportltlwm
Fix DisplayPort for HDMI port 1: https://lzhoang2601.github.io/post-install/gpu/intel-igpu#hdmi-sound
Add WhateverGreen's patch to boot-args :-  -wegnoegpu igfxfw=2 igfxagdc=0  igfxonln=1 -igfxbls -igfxblt -igfxcdc -igfxdbeo
![Screenshot 2023-12-01 at 3 51 29 PM](https://github.com/rahulhingve/Hackintosh-Msi-GF63-Thin-9SCXR-Sonoma/assets/62886652/fa29786e-e9ee-4116-8ceb-4fc9ddbf6c6e)


**All Thing Working Perfectly ✌😁**


### Guide Links
https://dortania.github.io/OpenCore-Install-Guide/

https://www.youtube.com/watch?v=jvb-BIMV1Mw  

https://www.youtube.com/watch?v=GGy3V3YT6tI

and some googgling skills.

##  Whats Working 
Fixed HDMI Output in latest commit
https://github.com/rahulhingve/Hackintosh-Msi-GF63-Thin-9SCXR-Sonoma/commit/f9c162c0d4270de7fa4d68cec6e4ef230b4adb9d

WiFi      ✅

Bluetooth ✅

Sound    ✅

Keyboard ✅

TrackPad  & trackpad buttons ✅

Function Key ✅

- [@dushan12k](https://github.com/dushan12k) thanks for Brightness key ✅

##  Not Working
nvdia 1650 Max-Q so Disabled
How to Check Gpu if On or off  in MSI
If Led Of power Key is White then Turned Of
If Red Then Gpu is Powered On

## Bugs
- AirDrop  (showing the iphone but tapping on share nothing happens )
- Closing And Opening  laptop lid  Cause Nvdia Gpu Get Power On (You can check power key led turned red ) And it is the main Problem for battery drain so If you also facing this just Restart Again

## BIOS Setting 
### Disable 
- Fast Boot
- Secure Boot
- VT-d
### Enable
- Boot Mode UEFI
- SATA Mode: AHCI
- Hyper-Threading


For more about BIOS Follow This Guide For Detailed Info

https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#intel-bios-settings










## Thanks 
- [Dortania Guide](https://dortania.github.io/OpenCore-Install-Guide/)
