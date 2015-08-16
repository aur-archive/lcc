# Original Maintainer: lspci <agm2819[[aaaa]][[tttt]]gmail[[dd]][[oo]][[tt]][[cc]][[oo]][[mm]]>
# Contributor: Brendan Long <korin43@gmail.com>
# Current Maintainer: Leopold Bloom <blinxwang at gmail dot com>

pkgname=lcc
pkgver=1.3
pkgrel=4
pkgdesc="C to LC3 compiler from McGraw Hill"
arch=('i686' 'x86_64')
url="http://highered.mcgraw-hill.com/sites/0072467509/student_view0/c_to_lc-3_compiler.html"
license=('LGPL')
depends=('unzip' 'lc3tools')
makedepends=()
replaces=()
conflicts=()
source=("http://highered.mheducation.com/sites/dl/free/0072467509/104652/lcc.zip")
md5sums=('e66851a28023e28e5d55d3fe24e26161')

build()
{
	msg "Building lcc..."
	cd $srcdir/lcc-$pkgver
	chmod +x configure
	./configure --installdir /usr/lib/lc3tools
	make
	msg "Done."
}

package()
{	
	install -m644 -d $srcdir/lcc-$pkgver/include ${pkgdir}/usr/lib/lc3tools/include
	install -m644 -d $srcdir/lcc-$pkgver/lc3lib ${pkgdir}/usr/lib/lc3tools/lc3lib
	install -m755 -D $srcdir/lcc-$pkgver/lc3pp/lc3pp ${pkgdir}/usr/lib/lc3tools/lc3pp
	install -m755 -D $srcdir/lcc-$pkgver/cpp/cpp ${pkgdir}/usr/lib/lc3tools/cpp
	install -m755 -D $srcdir/lcc-$pkgver/etc/lcc ${pkgdir}/usr/lib/lc3tools/lcc
	install -m755 -D $srcdir/lcc-$pkgver/etc/lcc ${pkgdir}/usr/bin/lcc
	install -m755 -D $srcdir/lcc-$pkgver/src/rcc ${pkgdir}/usr/lib/lc3tools/rcc
	ln -s /usr/bin/lc3as ${pkgdir}/usr/lib/lc3tools
}
