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

The whole operating system takes less than 8G (not counting boot and swap partition). With swap and boot it is 8.5G + your ram size.

The installation process takes about 10~30 minutes depending on the hardware and internet connection.

## For a full installation, do the following in order

### To install Arch Linux, run this command and reboot:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/archinstall)"
```

### To setup a user, login as root and run:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/genuser)"
```

### To install my configuration, reboot again and login as $USER created above, run:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/bootstrap)"
```

### To setup a flickerless boot screen, run:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/ausbxuse/bootstrap/master/flickerless)"
```

## What's next
After you run the scripts successfully, you will need to manually setup GRUB theme and SDDM theme, brave settings, spectacle screenshot location, dynamic wallpapers, and fcitx for other input methods and its theme and shortcut.
