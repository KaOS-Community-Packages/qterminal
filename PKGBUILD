pkgname=qterminal
pkgver=2.1.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qt6-base" "qtermwidget-qt6" "qt6-translations" "libcanberra")
makedepends=("cmake" "qt6-tools" "lxqt2-build-tools" "qt6-5compat")
source=("https://github.com/lxde/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('a65e788645bc694ede5d89de4118ee88443e0d6cbc388b0ce50d5c5d07b1213c')

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

