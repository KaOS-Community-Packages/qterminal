pkgname=qterminal
pkgver=1.2.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qt5-base" "qtermwidget" "qt5-x11extras")
makedepends=("cmake" "qt5-tools" "lxqt-build-tools")
source=("https://github.com/lxde/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('d9410a74899d50b0648510c738483244a1502d308276ce4b7b74b85ef716a45f')

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
