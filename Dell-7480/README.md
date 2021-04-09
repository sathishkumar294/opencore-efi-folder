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

## Not working
Multi-finger gestures 

Thunderbolt port

Built-in microphone

## Reference
Used the EFI folder provided by Jack Lo at https://osxlatitude.com/forums/topic/14721-dell-latitude-7480-skylake-opencore-064-upgrading-catalina-to-big-sur/?do=findComment&comment=106097

(Renamed config-hd620-intel.plist to config.plist)

## Enable HiDPI 1920x1080 resolution
I have a ELAN touch screen with 2560x1440 resolution. MacOS by default does not support HiDPI mode on 1920x1080 resolution. The HiDPI is supported at ~1200x900 resolution which is too large, but crisp. Hence I used this tool to enable HiDPI mode for 1920x1080 resolution: [One Key HiDPI](https://github.com/xzhih/one-key-hidpi)