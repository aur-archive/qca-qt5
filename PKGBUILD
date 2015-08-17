# Maintainer: Antonio Rojas <arojas@archlinux.org>
# Contributor: Christian Bühler <christian.buehler@ipoplan.de>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Pierre Schmitz <pierre@archlinux.de>

pkgname=qca-qt5
pkgver=2.1.0.3
pkgrel=1
pkgdesc="Qt Cryptographic Architecture"
arch=('i686' 'x86_64')
url="http://delta.affinix.com/qca/"
license=('LGPL')
depends=('nss' 'qt5-base')
makedepends=('cmake' 'doxygen')
source=("http://download.kde.org/stable/$pkgname/$pkgver/src/$pkgname-$pkgver.tar.xz")
md5sums=('e29cc1d8f0292eb28e20b216f52d60fc')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DBUILD_TESTS=OFF \
    -DQCA_SUFFIX=qt5 \
    -DQCA_INSTALL_IN_QT_PREFIX=ON
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
