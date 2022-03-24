# [☀️] OpenCore EFI for Z490 AORUS Pro
</br>

![FC5Ntu8VkAMP8Rk](https://user-images.githubusercontent.com/9656361/140409328-7013ee8b-adf0-476d-8db7-5b46ff1ccae1.jpeg)
</br>
</br>
</br>

## Build Info

<details>
<summary><strong>Hardware Components</strong></summary>

| Component           | Details                                                 |
| :-------------------|-------------------------------------------------------- |
| Mainboard           | Gigabyte Z490 AORUS Pro AX |
| BIOS		            | F21. F5 or newer is required to disable `CFG Lock`. Otherwise use Kernel Quirk `AppleXcpmCfgLock`|
| CPU                 | Intel® Core i7 10700K (Comet Lake)|
| RAM                 | 32 GB DDR4 3000Mhz G.Skill TridentZ RGB |
| iGPU		            | Intel® UHD 630. Configured for computing tasks only |
| GPU                 | ASUS RX580 8GB |
| Audio               | Realtek® ALC1220-VB (Layout-id: 1D000000) |
| Ethernet            | Using onboard Intel® I225-V 2.5GbE |
| WiFi + Bluetooth    | Using onboard through Airportitlm + IntelBluetooth Kexts |

</details>
<details>
<summary><strong>BIOS Settings</strong></summary>

* **Tweaker [TAB]**
	* Extreme Memory Profile (XMP): Enabled (if supported by RAM)
	* Advanced CPU Settings
		* VT-d: Enabled (disabled in config.plist anyway, so only relevant to Windows)
		* Intel Speed Shit: Enabled
* **Settings [TAB]**
	* Platform Power
		* Platform Power Management: Disabled
		* ErP: Enabled (so USB Power turns off, after PC is shut down)
	* IO Ports
		* Internal Graphics: enabled (if CPU has integrated graphics). **NOTE**: The config.plist uses dGPU for Display(s) and iGPU for computational tasks only by default. If you want to use the iGPU to drive a display you need a different Framebuffer Patch (see "EFI Install Instructions" for details).
		* OnBoard LAN Controller: Enabled
		* Audio Controller: Enabled (if On-Board Sound Card is used)
		* Above 4G Decoding: Enabled
		* Re-Size BAR Support: Disabled
		* IOAPIC 24-119 Entries: Enabled
		* Super IO Configuration
			* Serial Port: Disabled
		* USB Configuration
			* Legacy USB Support: Disabled
			* XHCI Hand-off: Enabled
		* Network Stack Configuration
			* Network Stack: Disabled
* **Boot [TAB]**
	* CFGLock: Disabled (Option only available on newer BIOS versions)
	* Windows 10 Features: Windows 10 
	* CSM: Disabled (to get rid of legacy code from `DSDT`)
</details>

## [🔥] Update

**25.03.2022: Updated to OC 0.7.9**

**02.2022: Updated to OC 0.7.8**

**11.2021: I've updated the files to support Monterey!!**

Since the last update, I've removed the Fenvi module and am using completely onboard WiFi + Bluetooth thanks to OpenIntelWireless. In my opinion, this gives much better reception and coverage. AirDrop, Continuity, HandOff and AirPlay works now without any problems. On the next patch I'll update it to 0.7.5 as well.

Also I've been using the BSXiMacSilver theme for the bootloader and I quite like it. You could always change to the default ones included on the folder.
You would also need to run the CreateVault Utility to fully support SecureBoot and make it more robust.
</br>
</br>

## [🚨] Warning

**Please change your SMBIOS details on the config.plist to your own before using, otherwise your system won't boot.**

(OLD VERSION):
This is taken from AORUS Elite EFI and has been modified to work with the motherboard for the time being. Will update soon with proper configurations. Presently everything seems to work including Sleep, WiFi, Bluetooth (Fenvi TV919 + disabled the onboard WiFi + Bluetooth module). I'm relatively new to Hackintosh so please take it as a grain of salt and use it just to load up your system. Won't suggest to use it as your main system for stability.
</br>
</br>

## [☘️] Installation

• Create a bootable USB</br>
• Copy the EFI Folder to your removable storage</br>
• Open Config.plist and add your SMBIOS details etc. and save it</br>
• Boot into the drive and install</br>
• Post-install, copy the EFI into your hard disk.</br>
• Before reboot, run the CreateVault command from the Utility section.</br>
• Done.
