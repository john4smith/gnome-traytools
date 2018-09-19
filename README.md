# gnome-traytools
Python3 TrayTools Indicator for the Gnome Desktop
![Alt text](/screenshot.png?raw=true "Screenshot")
__
### install for Arch Linux
- **Use the PKGBUILD:** https://wiki.archlinux.org/index.php/Makepkg
```
mkdir -p /tmp/build-$$/; cd /tmp/build-$$/
curl -o PKGBUILD https://raw.githubusercontent.com/john4smith/gnome-traytools/master/PKGBUILD
makepkg -d && sudo pacman -U gnome-traytools-*.pkg.tar.xz
```
___
### install for Ubuntu 18.04
- Install the Release deb-File
- Or build a deb-File with the [HowTo](/debian/HowTo.md)
