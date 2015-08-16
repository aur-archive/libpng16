# Maintainer: Christian Hesse <mail@eworm.de>

pkgname=libpng16
pkgver=1.6.8
pkgrel=1
pkgdesc="A collection of routines used to create PNG format graphics files (1.6 branch)"
arch=('i686' 'x86_64')
url="http://www.libpng.org/pub/png/libpng.html"
license=('custom')
depends=('zlib')
conflicts=('libpng<1.7')
options=('!libtool')
source=("http://downloads.sourceforge.net/sourceforge/libpng/libpng-${pkgver}.tar.xz"
	"http://downloads.sourceforge.net/sourceforge/libpng/libpng-${pkgver}.tar.xz.asc")

build() {
	cd libpng-${pkgver}

	./configure --prefix=/usr
	make
}

package() {
	cd libpng-${pkgver}

	make DESTDIR="${pkgdir}" install

	rm -rf "${pkgdir}/usr/share"
	rm -rf "${pkgdir}/usr/bin/libpng-config"
	rm -rf "${pkgdir}/usr/lib/"{libpng.so,libpng.a}
	rm -rf "${pkgdir}/usr/lib/pkgconfig/libpng.pc"
	rm -rf "${pkgdir}/usr/include/"{pngconf.h,pnglibconf.h,png.h}
}

sha256sums=('24f73d8b5e1d74a9482c81b65c3f93f96c7da7ed0417b8a948a75d2d99133081'
            'SKIP')
