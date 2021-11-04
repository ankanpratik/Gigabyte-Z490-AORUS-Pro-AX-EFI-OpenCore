# [☀️] OpenCore EFI for Z490 AORUS Pro


![FC5Ntu8VkAMP8Rk](https://user-images.githubusercontent.com/9656361/140409328-7013ee8b-adf0-476d-8db7-5b46ff1ccae1.jpeg)



## [🔥] Update

**11.2021: I've updated the files to support Monterey!!**

Since the last update, I've removed the Fenvi module and am using completely onboard WiFi + Bluetooth thanks to OpenIntelWireless. In my opinion, this gives much better reception and coverage. AirDrop, Continuity, HandOff and AirPlay works now without any problems. On the next patch I'll update it to 0.7.5 as well.

Also I've been using the BSXiMacSilver theme for the bootloader and I quite like it. You could always change to the default ones included on the folder.
You would also need to run the CreateVault Utility to fully support SecureBoot and make it more robust.

## [🚨] Warning

**Please change your SMBIOS details on the config.plist to your own before using, otherwise your system won't boot.**

(OLD VERSION):
This is taken from AORUS Elite EFI and has been modified to work with the motherboard for the time being. Will update soon with proper configurations. Presently everything seems to work including Sleep, WiFi, Bluetooth (Fenvi TV919 + disabled the onboard WiFi + Bluetooth module). I'm relatively new to Hackintosh so please take it as a grain of salt and use it just to load up your system. Won't suggest to use it as your main system for stability.


## [☘️] Installation

Create a bootable USB
Copy the EFI Folder to your removable storage
Open Config.plist and add your SMBIOS details etc. and save it
Boot into the drive and install
Post-install, copy the EFI into your hard disk.
Before reboot, run the CreateVault command from the Utility section.
Done.
