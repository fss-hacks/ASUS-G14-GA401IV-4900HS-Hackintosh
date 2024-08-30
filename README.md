# ASUS-G14-GA401IV-4900HS-Hackintosh
EFI and settings to build a 2020 ASUS GA401IV Ryzen 9 4900HS Hackintosh

Hackintosh running on Mac OS Ventura.\
OpenCore 1.0.1\
What is working:\
-Everything eccept for iMessage and FaceTime (work in progress)\
-Trackpad occasionally freezes for about 15 seconds but will begin to work again\
-USB-C ports that are attached to the dGPU may not work correctly\
-Still implementing more refined CPUTSCSync replacement for AMD

Instructions:\
Prepare BIOS:\
Currently working BIOS version is 220. To secure working, downgrade your BIOS to 220 and make sure Windows Update doesn't update.\
-Turn off Secure Boot and Fast Boot\
-Use UMAF (https://github.com/DavidS95/Smokeless_UMAF/) to change the following settings:\
-Device Manager > AMD CBS > NBIO Common Options > GFX Configuration and adjust the IGPU Configuration to UMA_SPECIFIED. Then, set the UMA Frame buffer Size to 2GB.\
- Device Manager > PCI Subsystem Settings > Enable 4G Decoding
- Partition drive and make a partition for Mac OS, you can format it NTFS for now. Use software like Minitool Partition Wizard (https://www.partitionwizard.com/) to resize existing Windows partition without losing data.\
-Download EFI files. Add Mac OS Installer files. Add random SMBIOS serial/ID info. Make USB installer flash drive.\
-Boot into BIOS by pressing F2 repeatedly, then F8 to select the flash drive. Installer will boot in verbose mode (-v). Format your drive with Disk Utility then install Mac OS Ventura. The machine will restart several times, pay quick attention to this so you can select OpenCore when the restart happens.

Finishing:
Once your install is done and you have gone thru setup, you have the choice to either:\
-use MountEFI (https://github.com/corpnewt/MountEFI) to mount your install drive EFI folder and copy your USB EFI to it\
-use EasyUEFI (https://www.easyuefi.com/index-us.html) to dual boot Windows and Mac OS by copying your USB EFI to the existing Windows EFI folder (replacing BOOT and copying OC folder) and creating an EFI record for OpenCore moved to the top of the Boot Manager list.\
You can do this with an already existing Windows installation without losing data.\
If you need to update OpenCore, kexts, and ACPIs, use OCAT (https://github.com/ic005k/OCAuxiliaryTools) to help you.\

Big thanks to:\
Plut02 (https://github.com/PIut02/ROG-Zephyrus-G14-GA401-Hackintosh?tab=readme-ov-file)
b00t0x (https://github.com/b00t0x/ROG-Zephyrus-G14-GA402-Hackintosh)
DavidS95 (https://github.com/DavidS95/Smokeless_UMAF)
ChefKissInc (https://github.com/ChefKissInc/NootedRed)
clear_crystal______ (Reddit)

Big 🖕 to:\
Dortania for writing HORRIBLE, unreadable guides that miss important pieces of the process\
People who constantly ask for EFIs without doing any work or development\
All the posters on Reddit and AMD-OSX who claim that "you can't hackintosh this machine cuz GPU etc"




