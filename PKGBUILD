pkgname=qterminal
pkgver=0.6.0.89.gee32e84
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qtermwidget")
makedepends=("git" "cmake" "qt5-tools")
source=("git+https://github.com/qterminal/$pkgname.git")
sha256sums=("SKIP")


pkgver() {
	cd "$srcdir/$pkgname"
	git describe --always | sed "s/-/./g"
}

build() {
	mkdir -p build
	cd build
	cmake "$srcdir/$pkgname" \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_INSTALL_LIBDIR=lib \
		-DUSE_SYSTEM_QXT=OFF \
		-DUSE_QT5=true
	make
}

package() {
	cd build
	make DESTDIR="$pkgdir" install
}
