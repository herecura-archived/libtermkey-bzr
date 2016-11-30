# Maintainer: Florian Walch <florian+aur@fwalch.com>

pkgname=libtermkey-bzr
pkgver=364
pkgrel=1
pkgdesc='Library for easy processing of keyboard entry from terminal-based programs.'
arch=('i686' 'x86_64')
url='http://www.leonerd.org.uk/code/libtermkey'
license=('MIT')
depends=('unibilium')
makedepends=('bzr')
conflicts=('libtermkey')
provides=("libtermkey=${pkgver}")
source=("${pkgname}::bzr+http://bazaar.leonerd.org.uk/c/libtermkey/")
sha256sums=('SKIP')

pkgver() {
  cd "${pkgname}"
  bzr revno
}

build() {
  cd "${pkgname}"
  make PREFIX=/usr termkey.h libtermkey.la
}

package() {
  cd "${pkgname}"
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set sw=2 sts=2 et:
