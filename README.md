# Bootstrapping script for my desktop configuration

## What's in the system
- **Desktop Environment**                 : KDE Plasma 
- **Desktop Theme**                       : White Sur
- **Display Manager**                     : SDDM
- **Shell**                               : zsh
- **Text Editor/IDE**                     : neovim
- **Terminal Emulator**                   : alacritty
- **File Manager**                        : Ranger/Dolphin
- **Music Player**                        : Elisa

The whole operating system takes less than 8G (excluding boot and swap partition). With swap and boot it is 8.5G + your ram size.

The installation process takes about 10~30 minutes depending on the hardware and internet connection.

## For a full installation, do the following in order

1. Enter BIOS, disable secure boot, and enable USB boot
2. Boot into the live environment with a bootable USB containing Arch Linux. (hold down F12 on boot to choose USB boot option)
3. Connect to the internet with iwctl

### To install Arch Linux, run this command and reboot:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/archinstall)"
```

### To setup a user, login as root and run:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/genuser)"
```

### To install my configuration, reboot again and login as $USER created above, cd to homd directory, and run:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/bootstrap)"
```

### To beautify the desktop environment a little more, run:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/postinstall)"
```

## What's next
After you run the scripts successfully, you will need to manually setup GRUB theme and SDDM theme, kvantum, brave settings, spectacle screenshot location, dynamic wallpapers, and fcitx for other input methods and its theme and shortcut.
