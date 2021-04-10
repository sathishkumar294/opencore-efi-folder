# opencore-efi-folder
EFI Folder for installation using OpenCore v0.6.7

## Working components

[✔] Intel graphics

[✔] Audio

[✔] Ethernet

[✔] Boot without USB


Ref: https://dortania.github.io/OpenCore-Install-Guide/

## If the boot device does not show up in the boot drive list, boot into it manually using the UEFI Shell

1. List the drives
```sh
> map
```

2. Find the drive that contains the apple EFI partition and switch to it (trial and error - switch to each device using `fs1:` command - replace `fs1` with your drive, then ls to see if your EFI folder is there)

```sh
> fs3:
```

3. Start the `bootx64.efi`

```sh
EFI\BOOT\BOOTX64.EFI
```

4. Now the open core bootloader with appear (wait ~15 secs) and you have acess to the boot options.

5. Reset NVRAM to make the drive appear in the MSI bootloader UEFI device list


## Improve font rendering on 1080p

Run this command in terminal. I was able to see instant improvement in font rendered in Safari, VS Code etc. Reboot is suggested.

```sh
defaults write -g CGFontRenderingFontSmoothingDisabled -bool NO
```
Ref: https://www.cleverfiles.com/help/mac-fonts-text-blurry.html
