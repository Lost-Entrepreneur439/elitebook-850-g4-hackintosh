macOS Ventura EFI for the HP EliteBook 850 G4 using OpenCore. I will try to keep this EFI up to date with the latest OpenCore and kexts

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7dad5442-8a8c-4095-8285-c09e3f7c2a09" />

# WARNING! SMBIOS DETAILS ARE NOT INCLUDED IN THE CONFIG.PLIST.
You will have to use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate a **MacBookPro14,1** SMBIOS for your system, and add them to the config.plist.
Make sure you're on BIOS the latest BIOS before continuing. Older versions may cause issues

## Other macOS versions?
No. Ventura is the latest supported by MacBookPro14,1, so it's all I'll ever support. If you want a different version, feel free to fork this repo to modify it for whatever version you want. Do note newer versions will likely require OCLP.

## System specs
Do note if your hardware differs, while unlikely, you may have issues.
- CPU: Intel Core i5-7300U
- GPU: Intel HD Graphics 620
- Chipset: Integrated into CPU
- Touchpad: Synaptics SMBUS 
- Audio: Conexant CX8200
- Wi-Fi: Intel Wireless-AC 8265
- Ethernet: Intel I219-LM
- Disk: Toshiba XG5 256GB

## Issues:
- The fingerprint sensor does not work. The drivers are very closed source and macOS doesn't let you use a fingerprint sensor without a real T1/T2.

If you notice any other problems, please open an issue (or pull request if you have a fix)

### BIOS settings
If you do not set these BIOS settings, macOS will **not** boot.
- Advanced -> Boot Options -> Disable "Fast Boot"
- Advanced -> Secure Boot Configuration -> Configure Legacy Support and Secure Boot -> Legacy Support Disable and Secure Boot Disable
- Advanced -> System Options -> Enable "Hyperthreading"
- Advanced -> System Options -> Enable "Virtualization Technology (VTx)"
- Advanced -> System Options -> Disable "Virtualization Technology for Directed I/O (VTd)"
- Advanced -> Built-In Device Options -> Video memory size -> Set to 64MB or higher
