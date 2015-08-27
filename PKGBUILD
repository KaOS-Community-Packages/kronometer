pkgname=kronometer
pkgver=2.0.1
pkgrel=1
pkgdesc="A simple chronometer application."
arch=('x86_64')
url="http://aelog.org/kronometer"
license=('GPL2')
depends=('kconfig' 'kxmlgui' 'kwidgetsaddons')
makedepends=('extra-cmake-modules' 'kdoctools' 'python3')
install=$pkgname.install
source=(http://download.kde.org/stable/$pkgname/$pkgver/src/$pkgname-$pkgver.tar.xz)
sha256sums=('6e407a295819b61e6ef2e3bdc47d59671cd66d1928c4e5667518bf2e0bcf2651')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
