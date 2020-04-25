pkgname=qterminal
pkgver=0.15.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qt5-base" "qtermwidget")
makedepends=("cmake" "qt5-tools" "lxqt-build-tools")
source=("https://github.com/lxde/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('e018ece0bd38124a2879a6fbb76dd6b9d70ae2b231845650ad363eeca756fe31')

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
sha256sums=('557f74a946d009bb6e598c5d0c6de9356cda325f674876a457874c7525affd64')
