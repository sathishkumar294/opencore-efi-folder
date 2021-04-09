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