pkgname=qterminal
pkgver=1.2.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=('x86_64')
url="https://github.com/lxqt/$pkgname"
license=('GPL2')
depends=('qt5-base' 'qtermwidget' 'qt5-x11extras')
makedepends=('cmake' 'qt5-tools' 'lxqt-build-tools')
source=("${pkgname}-${pkgver}::https://github.com/lxqt/$pkgname/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('SKIP')

build() {
	mkdir -p build
	cd build

	cmake "$srcdir/$pkgname-$pkgver" \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_INSTALL_LIBDIR=lib
	make
}

package() {
	cd build
	make DESTDIR="$pkgdir" install
}
