pkgname=qterminal
pkgver=1.3.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
<<<<<<< HEAD
arch=('x86_64')
url="https://github.com/lxqt/$pkgname"
license=('GPL2')
depends=('qt5-base' 'qtermwidget' 'qt5-x11extras')
makedepends=('cmake' 'qt5-tools' 'lxqt-build-tools')
source=("${pkgname}-${pkgver}::https://github.com/lxqt/$pkgname/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('SKIP')
=======
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qt5-base" "qtermwidget" "qt5-x11extras")
makedepends=("cmake" "qt5-tools" "lxqt-build-tools")
source=("https://github.com/lxde/$pkgname/releases/download/$pkgver/$pkgname-$pkgver.tar.xz")
sha256sums=('7e45e84c36136fc2bb843c936335d848d343bb5e3357b6610fc8bd5743a170c5')
>>>>>>> c198561 (qterminal 1.3.0)

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
