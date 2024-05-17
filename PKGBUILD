pkgname=qterminal
pkgver=2.0.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qt6-base" "qtermwidget-qt6" "qt6-translations" "libcanberra")
makedepends=("cmake" "qt6-tools" "lxqt2-build-tools" "qt6-5compat")
source=("https://github.com/lxde/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('28f00a5c8c31d9108a54b7dcbf87d46f14e460492d2c56e3ecf5b5c3bba4059f')

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
