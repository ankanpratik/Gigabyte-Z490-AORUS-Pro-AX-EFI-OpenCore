# [☀️] OpenCore EFI for Z490 AORUS Pro
</br>

![FC5Ntu8VkAMP8Rk](https://user-images.githubusercontent.com/9656361/140409328-7013ee8b-adf0-476d-8db7-5b46ff1ccae1.jpeg)
</br>
</br>

Hello everyone,</br>
I'm sharing my EFI for Gigabyte AORUS Pro AX here. I've completely created this from scratch through the great guide from Dortiana / OpenCore. It's a solid stable build and I have been daily driving this system for my main work. Always open to feedbacks and to improve it further!</br>
Cheers.</br>
✌️</br>
</br>

## [🛠] Build Info
</br>

**Hardware Components**

| Component           | Details                                                 |
| :-------------------|-------------------------------------------------------- |
| Mainboard           | Gigabyte Z490 AORUS Pro AX |
| BIOS		      | F21. F5 or newer is required to disable `CFG Lock`. Otherwise use Kernel Quirk `AppleXcpmCfgLock`|
| CPU                 | Intel® Core i7 10700K (Comet Lake)|
| RAM                 | 32 GB DDR4 3000Mhz G.Skill TridentZ RGB |
| iGPU		      | Intel® UHD 630. Configured for computing tasks only |
| GPU                 | ASUS RX580 8GB |
| Audio               | Realtek® ALC1220-VB (Layout-id: 1D000000) |
| Ethernet            | Using onboard Intel® I225-V 2.5GbE |
| WiFi + Bluetooth    | Using onboard through Airportitlm + IntelBluetooth Kexts |

</br>
</br>

**BIOS Settings**

* **Tweaker [TAB]**
	* Extreme Memory Profile (XMP): Enabled (if supported by RAM)
	* Advanced CPU Settings
		* VT-d: Enabled (disabled in config.plist anyway, so only relevant to Windows)
		* Intel Speed Shift: Enabled
* **Settings [TAB]**
	* Platform Power
		* Platform Power Management: Disabled
		* ErP: Enabled (so USB Power turns off, after PC is shut down)
	* IO Ports
		* Internal Graphics: enabled (if CPU has integrated graphics). **NOTE**: The config.plist uses dGPU for Display(s) and iGPU for computational tasks only by default. If you want to use the iGPU to drive a display you need a different Framebuffer Patch.
		* OnBoard LAN Controller: Enabled
		* Audio Controller: Enabled (if On-Board Sound Card is used)
		* Above 4G Decoding: Disabled
		* Re-Size BAR Support: Disabled
		* IOAPIC 24-119 Entries: Enabled
		* USB Configuration
			* Legacy USB Support: Disabled
			* XHCI Hand-off: Enabled
			
* **Boot [TAB]**
	* CFGLock: Disabled (Option only available on newer BIOS versions)
	* Windows 10 Features: Other OS 
	* CSM: Disabled (to get rid of legacy code from `DSDT`)
</details>
</br>
</br>

## [🔥] Update
I've stopped using the Fenvi module and am using completely onboard WiFi + Bluetooth thanks to OpenIntelWireless. In my opinion, this gives much better reception and coverage. Continuity, HandOff and Sidecar to iPad (using USB) works without any problems. If you need AirDrop, Airplay or Universal Control, disable the Kexts AirportItlwm.kext, IntelBTPatcher.kext, IntelBluetoothFirmware.kext and BlueToolFixup.kext. Since this system is in a different room, I'm unable to test LAN, but the onboard WiFi works solid!
</br>
Also I've been using the BSXiMacSilver theme for the bootloader and I quite like it. You could always change to the default ones included on the folder.
</br>
</br>

## [💚] What Works
- [x] **MacOS Ventura 13.1**
- [x] In-built Wi-fi and Bluetooth
- [x] Audio: Realtek ALC1220-VB (AppleALC.kext, layout-id=7,FakeID.kext, FakePCIID_Intel_HDMI_Audio.kext)
- [x] USB - All ports including front USB ports (NZXT S340 Elite)
- [x] Using iMacPro1,1: Amazon Prime Video and Netflix in Safari, AppleTV
- [x] Shutdown
- [x] Restart
- [x] Facetime + iMessages
- [x] Handoff, Sidecar through USB, Continuity
- [x] Upgrading to newer MacOS versions. I had upgraded from Catalina to Big Sur to recently Ventura, without any issues!
- [x] Sleep (use this fantastic guide by SchmockLord (https://github.com/SchmockLord/Hackintosh-Intel-i9-10900k-Gigabyte-Z490-Vision-D)
</br>

## [💔] What Doesn't Work
- [ ] (Outside my control) Airdrop / Universal Control using Itwlm. You'll need a native compatible PCIe card, like Fenvi TV919 for it to work. If you have that, remove AirportItlwm.kext, IntelBTPatcher.kext, IntelBluetoothFirmware.kext and BlueToolFixup.kext.
</br>

## [🚨] Warning
**Please change your SMBIOS details on the config.plist to your own before using, otherwise your system won't boot.**
</br>
</br>

## [☘️] Installation
• Create a bootable USB</br>
• Copy the EFI Folder to your removable storage</br>
• Open Config.plist and add your SMBIOS details etc. and save it</br>
• Boot into the drive and install</br>
• Post-install, copy the EFI into your hard disk.</br>
• Done.

## [🙏] Credits
• https://github.com/SchmockLord
• https://github.com/5T33Z0
• https://github.com/acidanthera
• https://github.com/dortania
