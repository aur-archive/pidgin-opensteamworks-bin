# Maintainer: kaptoxic <kaptoxic _at_ yahoo _dot_ com >
# Contributor: sumt <sumt at sci dot fi>
# Contributor: onny <onny@project-insanity.org>

pkgname=pidgin-opensteamworks-bin
pkgver=1.5
pkgrel=1
pkgdesc="A plugin to connect to Steam Friends/IM for purple (compiled binaries)"
url="https://code.google.com/p/pidgin-opensteamworks"
arch=('i686' 'x86_64')
license=('GPL3')
depends=('libpurple' 'json-glib')
makedepends=('unzip')
[ "$CARCH" == x86_64 ] && _carch="64"
source=("http://pidgin-opensteamworks.googlecode.com/svn/trunk/steam-mobile/releases/libsteam$_carch-$pkgver.so"
        "https://pidgin-opensteamworks.googlecode.com/files/icons.zip")
sha1sums=('74f4b8e1a1a047878006e8343d60505cc80de02e'
          '1388429ce0e64008e0a1a29b62641bf23c6776e2')
[ "$CARCH" == i686 ] && sha1sums[0]='3024a515a53fe87961ed84fd68d85852b727578c'

package() {
  # installing purple plugin
  install -Dm755 libsteam*-$pkgver.so "$pkgdir/usr/lib/purple-2/libsteam.so"
  # installing icons
  mkdir -p "$pkgdir/usr/share/pixmaps/pidgin/protocols"
  unzip "icons.zip" -d "$pkgdir/usr/share/pixmaps/pidgin/protocols/"
}
