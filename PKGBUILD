# Maintainer: callmetango
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=sonic-frameworks-core-addons
pkgver=6.26.0
pkgrel=2
pkgdesc='Addons to QtCore'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-frameworks-core-addons'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(glibc
         libgcc
         libstdc++
         qt6-base
         systemd-libs
         util-linux-libs)
makedepends=(doxygen
             pyside6
             python-build
             python-setuptools
             qt6-declarative
             qt6-tools
             sonic-frameworks-cmake-modules)
optdepends=('pyside6: Python bindings'
            'qt6-declarative: QML bindings')
provides=(kcoreaddons)
conflicts=(kcoreaddons)
groups=(sonicde-frameworks)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('a2480ffeea641f0d46c56037f9bbefc37d1d7c6955cab12abf26e01a82d5cd69')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
