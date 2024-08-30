# ASUS-G14-GA401IV-4900HS-Hackintosh
EFI and settings to build a 2020 ASUS GA401IV Ryzen 9 4900HS Hackintosh

Hackintosh running on Mac OS Ventura.\
What is working:\
-Everything eccept for iMessage and FaceTime\
-Trackpad occasionally freezes for about 15 seconds but will begin to work again\
-USB-C ports that are attached to the dGPU aren't working correctly\
-Still implementing more refined CPUTSCSync replacement for AMD\

Instructions:
Prepare BIOS:
Currently working BIOS version is 220. To secure working, downgrade your BIOS to 220 and make sure Windows Update doesn't update.
-Turn off Secure Boot and Fast Boot
Use UMAF (https://github.com/DavidS95/Smokeless_UMAF/) to change the following settings:
-Device Manager > AMD CBS > NBIO Common Options > GFX Configuration and adjust the IGPU Configuration to UMA_SPECIFIED. Then, set the UMA Frame buffer Size to 2GB.
- Device Manager > PCI Subsystem Settings > Enable 4G Decoding
Download EFI files. Add Mac OS Installer files.

