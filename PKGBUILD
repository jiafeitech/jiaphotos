pkgname=jiaphotos
pkgver=r5432.be0da0e
pkgrel=1
pkgdesc='A fast and easy to use image viewer for KDE'
arch=('i686' 'x86_64')
url='http://kde.org/applications/graphics/gwenview/'
license=('GPL')
depends=(baloo cfitsio kactivities kimageannotator kitemmodels kparts libkdcraw perl phonon-qt5 purpose)
makedepends=('extra-cmake-modules' 'git' 'kdoctools')
conflicts=('kdegraphics-gwenview' 'gwenview')
provides=('gwenview')
source=("git+https://invent.kde.org/graphics/gwenview.git#branch=release/22.12")
sha256sums=('SKIP')

prepare() {
  mkdir -p build
}

build() { 
  cd build
  cmake ../gwenview \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_BUILD_TYPE=Release \
    -DLIB_INSTALL_DIR=lib \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
