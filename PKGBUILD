# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kemoticons
pkgver=4.99.0
pkgrel=1
pkgdesc='KEmoticons'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kemoticons'
license=('LGPL')
depends=('karchive' 'kservice')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('7860bb4b9d89f205fe9ad258b79534b5')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
