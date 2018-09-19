# Make a Debian/Ubuntu Package
#### Download the Source Package from GitHub, extract it and then run this in your Terminal
```
pkgname="gnome-traytools"
pkgdir="/tmp/gnome-traytools-$$"
cd ${pkgname}-*/
mkdir -p "${pkgdir}"/DEBIAN
install -dm755 "${pkgdir}"/usr/share/applications
install -dm755 "${pkgdir}"/usr/share/glib-2.0/schemas
install -dm755 "${pkgdir}"/usr/share/${pkgname}
install -m644 ${pkgname}.desktop "${pkgdir}"/usr/share/applications
install -m644 apps.${pkgname}.gschema.xml "${pkgdir}"/usr/share/glib-2.0/schemas
install -m755 ${pkgname} "${pkgdir}"/usr/share/${pkgname}
install -m644 LICENSE "${pkgdir}"/usr/share/${pkgname}
install -m644 debian/control "${pkgdir}"/DEBIAN
pkgsize=$(du -s "${pkgdir}"/usr | cut -f1)
pkgver=$(grep ^Version: "${pkgdir}"/DEBIAN/control | cut -d" " -f2)
sed -i "s/^Installed-Size:.*/Installed-Size: ${pkgsize}/" "${pkgdir}"/DEBIAN/control
bash -c "cd \"${pkgdir}\"; find usr/ -type f -exec md5sum '{}' \; > DEBIAN/md5sums"
dpkg-deb --build "${pkgdir}" ../${pkgname}-${pkgver}_all.deb
```
