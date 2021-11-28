# Acer Nitro 5 AN515-54-51NJ Hackintosh

## System Details

| Model            | Acer Nitro 5 AN515-54-51NJ                                 |
| :--------------- | :--------------------------------------------------------- |
| CPU              | Intel® Core(TM) i5-9300H @ 2.40GHz QuadCore Coffee Lake-H  |
| iGPU             | Intel® UHD Graphics 630 (1536 MB)                          |
| dGPU             | NVIDIA GeForce® GTX 1650 (4GB)                             |
| RAM              | Micron 8ATF1G64HZ-3G2J1 Dual DDR4 SDRAM 2x8GB 3200 MHz     |
| SSD              | Asgard AN256NVMe-M.2/80                                    |
| Ethernet         | Realtek RTL8168/8111 PCI-E Gigabit Ethernet Adapter        |
| WiFi / BT        | Intel® AX200NGW 160 MHz                                    |
| Audio            | Realtek ALC255 [lid=31]                                    |
| TouchPad         | Synaptic 7DB5                                              |
| Display          | BOEhydis NV156FHM-N48 15.6" LCD (FHD)                      |
| BIOS Version     | V1.33                                                      |
| OpenCore Version | 0.7.5                                                      |

## What's not working:

- HDMI (won't work because HDMI port is hardwired into GeForce® GTX 1650).
- NVIDIA GeForce® GTX 1650
- NVMe Micron_2200_MTFD (476 GB). Eject or Disable this drive on the BIOS. Use external m.2 case if u need to use this SSD.
- AirDrop and Handoff don't work with Intel® AX200


## BIOS Setup:

1. Open BIOS
2. Security -- > Set Supervisor Password -- > Insert ur passwd
3. Boot -- > Boot Mode -> `UEFI`
4. Boot -- > Secure Boot -- > `Enabled` -> `Disabled`
5. Main -- > Control+S -- > `Replace RST Premium with Optane` -> `AHCI`
6. Main -- > Fast Boot -> `Disabled`
7. Advanced: VTD+VTX = Enabled
6. Exit -> Exit Saving Changes


## Installation Steps

1. Download macOS Big Sur image by click on the magnet link: [Link](https://rutracker.org/forum/viewtopic.php?t=5928524)
2. Burn a macOS image to a USB drive with R-Drive Image (inside ISO)
3. Write CLOVER and Big Sur Partition.
4. After writing, remove `EFI/clover` and insert `EFI/OC` from this repo
4. Generate a new SMBIOS with [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
5. Update to the `config.plist` in the USB drive's `EFI/OC` folder with new SMBIOS
6. Boot with USB drive
7. Follow the installer instructions

macOS Big Sur 11.6.1 (20G224) Perfect worked with this release