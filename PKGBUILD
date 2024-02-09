pkgname=qterminal
pkgver=1.4.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qt5-base" "qtermwidget" "qt5-x11extras")
makedepends=("cmake" "qt5-tools" "lxqt-build-tools")
source=("https://github.com/lxde/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('8313326ac3ef728924271cd60a8f79e17e5e755a6bfa4e4419a4b7a53528659f')

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
