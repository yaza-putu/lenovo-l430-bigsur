# lenovo-thinkpad-l430 
## Upgrade from Catalina 10.15.7 to Bigsur 11.6.5
![lenovo thinkpad l430](https://res.cloudinary.com/dk0053zbe/image/upload/v1643354951/bigsur_rf2s10.png)

## spesifikasi :
- Bootloader Opencore 0.6.3
- processor core i3 3120M (Ivy Bridge)
- vga intel hd 4000
- audio alc269 layout-id 29
- Ethernet RTL8168E-VL
- Intel(R) Centrino(R) Advanced-N 6205
- Intel 7 Series Chipset
- Touchpad ELAN

## Working :
- iGpu intel HD 4000
- USB port
- Sound Alc269
- Touchpad
- etc
- Sleep (Not perfect)
- shotdown
- Restart
- Must be set SMBIOS MacBookPro11,1 to be install BIGSUR and SET to MacBookPro10.2 with boot args no_compat_check to fixing Power management Issue in ivy bridge bigsur (SSDT-PM.aml generated from catalina)
- Brightness, Fn + p (brightness up) and Fn + k (brightness down)
- Display Port
- WLAN Intel(R) Centrino(R) Advanced-N 6205
## Not Working :
- VGA port

## Patch SSDT:
- PNLF (Fix Brightness)
- PM (CPU power management)
- EC (Fixes the embedded controller)
- XOSI (Makes all _OSI calls specific to Windows work for macOS (Darwin) Identifier. This may help enabling some features like XHCI and others.)
- IMEI (Needed to add a missing IMEI device on Ivy Bridge)
- HPET (Fixing IRQ Conflicts) https://dortania.github.io/Getting-Started-With-ACPI/Universal/irq.html
- SBUS-MCHC fix SMBUS

## Kext Version Control
- AppleALC              : V1.6.1 (RELEASE)
- Lilu                  : V1.5.3 (RELEASE)
- RealtekRTL8111        : V2.4.2 (RELEASE)
- VirtualSMC            : V1.2.4 (RELEASE)
- VoodooPS2Controller   : V2.2.3 (RELEASE)
- WhateverGreen         : V1.5.0 (RELEASE)
- YogaSMC               : V1.5.1 (RELEASE)
- USBMap                : Generated (CUSTOM)
- AirportItlwm.kext     : V2.1.0 (STABLE)

## Change Log
- 17 Maret 2022 , change SMBIOS MacBookPro11.1 to MacBookPro10.2 to fix power management (old SSDT PM generated from catalina) issue CORE REQ always high for Ivy Brige processor in BIGSUR

## Issue
- sleep not perfect
