pkgname=qterminal
pkgver=0.6.0
pkgrel=1
pkgdesc="Lightweight Qt-based terminal emulator"
arch=("x86_64")
url="https://github.com/qterminal/qterminal"
license=("GPL2")
depends=("qtermwidget")
makedepends=("git" "cmake" "qt5-tools")
source=("git+https://github.com/qterminal/$pkgname.git" "no_lxqt.patch" "mainwindow.patch" "termwidget.patch")
sha256sums=("SKIP" "b8bdb10a5c5c6386ea350fe822dfd0e7d114fd568379bb7d62aaaf086c433df4" "98e93f6afa2b2ac0df688cd07e4bd04cf5d8389fa2427379b29d2b23e6957f1d" "c7d68b28f4dafcc31762b7571fbc4a004205b1d5d2634c18fad687e0fef5aefe")


prepare() {
  patch -p1 -i no_lxqt.patch 
  patch -p1 -i mainwindow.patch
  patch -p1 -i termwidget.patch
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
