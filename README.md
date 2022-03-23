# Bootstrapping script for my Arch Linux desktop configuration using a custom offline ISO

## What's in my setup
- **Desktop Environment**                 : KDE Plasma 
- **Desktop Theme**                       : White Sur
- **Display Manager**                     : SDDM
- **Shell**                               : zsh
- **Text Editor/IDE**                     : neovim
- **Terminal Emulator**                   : alacritty
- **File Manager**                        : Ranger/Dolphin
- **Music Player**                        : Elisa

The whole operating system takes less than 9G (excluding boot and swap partition), but will need more than 11G + ram size * 1.5 to complete the installation.

The installation process takes about 5 minutes depending on the hardware and internet connection.

## Requirements
- A device that supports booting with UEFI 
- A bootable USB drive containing the custom ISO that this script supports

### To build the custom ISO:
On an Arch Linux machine:
1. install archiso package from pacman
2. generate a list of packages needed by running
```
mkdir /tmp/blankdb
mkdir official-repo
cd official-repo
sudo pacman -Syw --cache-dir . --dbpath /tmp/blankdb base base-devel linux linux-firmware systemd mkinitcpio lvm2 neovim git grub efibootmgr intel-ucode os-prober networkmanager zsh plasma xorg-server xorg-xinit sddm-kcm alacritty rsync exa bat tmux unzip xclip xsel pass ncdu dolphin unclutter noto-fonts-emoji sxiv zathura-pdf-mupdf adobe-source-han-sans-otc-fonts adobe-source-han-serif-otc-fonts bluez-utils fd neofetch htop ripgrep plocate fzf ksysguard okular mpv lsof man-db zbar spectacle tumbler trash-cli elisa zip pulseaudio-bluetooth bc android-tools python-pip ueberzug capitaine-cursors sdcv kcm-fcitx fcitx-sunpinyin gimp kdeconnect syncthing make cmake gcc gettext extra-cmake-modules qt5-tools qt5-x11extras kcrash kglobalaccel kde-dev-utils kio knotifications kinit kwin alsa-lib gtk3 libxss nss ttf-font glibc libinput cairo systemd-libs libx11 libxi libxrandr libxtst pugixml glib2
repo-add ./custom-official.db.tar.gz ./*.zst
```
3. copy the default ISO profile(releng) to the project directory
5. move official-repo to airootfs/root
4. clone ausbxuse/dots ausbxuse/bootstrap to airootfs/root
5. in another directory, clone the AUR packages and makepkg
6. copy *.zst to a new directory called aur-packages
7. move the aur-packages to airootfs/root
8. 
```
sudo mkarchiso -v -w ~/.local/share/ISOs/work -o ~/.local/share/ISOs/out ~/.local/src/public-repos/<your project dir>
```
9. use dd to flash the image on to your USB flash drive

## For a full installation, do the following in order

1. Enter BIOS, disable secure boot, and enable USB boot
2. Boot into the live environment with the bootable USB containing the custom image. (hold down F12 on boot to choose USB boot option)

### To install Arch Linux and my custom desktop environment setup, run this command and reboot:
```
cat ~/bootstrap/archinstall | bash
```

## What's next
After you run the scripts successfully, you will need to manually setup kvantum, brave settings, dynamic wallpapers, and fcitx for other input methods and its theme and shortcut.

# TODOs:
- [ ] grub detect windows and silent grub
- [ ] output errors log
- [ ] alacritty meslo font
- [ ] zsh history
- [ ] grub-silent
- [ ] tap to click
- [ ] bluetooth(pairing and both system)
- [ ] kernel parameters to quiet down, allow os-prober
- [ ] nvim language servers
- [ ] norg tsinstall
