# Maintainer: john smith <hidden at mail dot com>
pkgname="gnome-traytools"
pkgver=0.1
pkgrel=1
pkgdesc="Gnome Tray Tools by John Smith."
arch=('any')
url="https://github.com/john4smith/gnome-traytools"
license=('GPL3')
depends=('gnome-shell' 'libappindicator-gtk3' 'python-gobject' 'dconf')
optdepends=('gnome-shell-extension-appindicator-git: gnome indicator support'
            'gnome-shell-extension-topicons-plus: gnome indicator support')
source=("${pkgname}-${pkgver}.zip::${url}/archive/master.zip")
sha256sums=('SKIP')

package() {
 cd "${srcdir}"/${pkgname}-*/
 install -dm755 "${pkgdir}"/usr/share/applications
 install -dm755 "${pkgdir}"/usr/share/glib-2.0/schemas
 install -dm755 "${pkgdir}"/usr/share/${pkgname}
 install -m644 ${pkgname}.desktop "${pkgdir}"/usr/share/applications
 install -m644 apps.${pkgname}.gschema.xml "${pkgdir}"/usr/share/glib-2.0/schemas
 install -m755 ${pkgname} "${pkgdir}"/usr/share/${pkgname}
 install -m644 LICENSE "${pkgdir}"/usr/share/${pkgname}
}
