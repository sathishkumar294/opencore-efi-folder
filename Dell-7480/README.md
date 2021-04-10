# EFI Folder for Dell Latitude 7480

## System Specifications:
Dell Latitude 7480
CPU: i7-7600U, Dual core Intel i7 @2.9GHz
GPU: Intel HD Graphics 620
RAM: 2x8GB 2133MHz DDR4
Screen: ELAN Touchscreen, 2560x1440 @60Hz
Storage: PC300 NVMe SK hynix 512GB
Wifi: Intel 

## In MAC Os, Big Sur
![System Specifications](assets/System-Configuration.png?raw=true "System Configuration")


## Working
Audio ✓

Touchscreen ✓

Trackpad ✓

Keyboard ✓

Wifi ✓

Bluetooth ✓

Battery status ✓

HDMI output ✓

Apple Services ✓

Two finger guestures ✓

Camera ✓

Built-in microphone ✓

## Not working

Multi-finger gestures 

Sleep and wake

## To Check

Thunderbolt port (not tested)

SD Card reader (not tested)

Headphone Jack (not tested)

## Reference
Used the EFI folder provided by Jack Lo at https://osxlatitude.com/forums/topic/14721-dell-latitude-7480-skylake-opencore-064-upgrading-catalina-to-big-sur/?do=findComment&comment=106097

(Renamed config-hd620-intel.plist to config.plist)

## Reset NVRAM on first boot
This step is mandatory and it will fix most issues related to mic etc. Press Space on the opencore screen to show other options.

## Enable HiDPI 1920x1080 resolution
I have a ELAN touch screen with 2560x1440 resolution. MacOS by default does not support HiDPI mode on 1920x1080 resolution. The HiDPI is supported at ~1200x900 resolution which is too large, but crisp. Hence I used this tool to enable HiDPI mode for 1920x1080 resolution: [One Key HiDPI](https://github.com/xzhih/one-key-hidpi)

## Download San Francisco Fonts from Apple
By default, the San Francisco fonts are not available for other applications to use. You need to install them separately from Apple website, so that other applications (like VS Code) can use them.
[Apple Fonts](https://developer.apple.com/fonts/)

## Make MacOS the default startup disk
To automatically choose MacOS instead of windows from booting up.

## To clone MacOS to another partition
1. Create an empty partition in Windows and format it to NTFS or FAT32
2. Open Disk Utility and format the new partition to APFS.
3. Use [Carbon Copy Cloner](https://bombich.com) to clone from the source volume to target volume.
4. Add entry for MacOS in grub using this [guide](https://github.com/SayantanRC/URLs/blob/master/grub_to_opencore.md). Thanks [@SayantanRC](https://github.com/SayantanRC) 
    1. Boot into GRUB and create a new boot entry in `/etc/grub.d/40_custom`
    ```sh
    menuentry 'MacOS' $menuentry_id_option 'macOS-efi' {
        insmod chain
        insmod part_gpt
        insmod fat
        set root=(hd0,gpt1)
        chainloader /efi/Mac/oc/for_grub/OpenCore.efi
        set root=(hd0,gpt1)/efi/Mac
    }
    ```
    2. Copy the EFI folder from the source EFI folder (MacOS) to a new folder named 'Mac' in ubuntu's efi(/boot/efi) folder. To mount the efi folder of ubuntu in RW mode,
    ```sh
    sudo mount -o rw,remount /boot/efi
    ```
5. Reboot into Grub and select the new entry to boot.
6. It is advisable to clear the NVRAM once and set the new disk as the default start-up disk in the MacOS System Preferences.