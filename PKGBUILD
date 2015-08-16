# Maintainer: Evan Teitelman <teitelmanevan@gmail.com>
# Contributor: nofxx <x@nofxx.com>

pkgname=irpas
pkgver=0.10
pkgrel=3
pkgdesc="Internetwork Routing Protocol Attack Suite."
arch=('i686' 'x86_64')
url="http://phenoelit-us.org/irpas"
license=('Custom')
depends=('libpcap')
provides=(irpas)
conflicts=(irpas)
install=
source=(http://www.phenoelit.org/irpas/${pkgname}_${pkgver}.tar.gz)
md5sums=('314670e9d239694cdd4e1f529b63959b')

build() {
	cd $srcdir
	make || return 1
}	

package() {
	cd $srcdir
	# Copying executables to /usr/bin...
	install -d $pkgdir/usr/bin
	for binary in dhcpx itrace tctrace ass file2cable dfkaa cdp hsrp icmp_redirect\
		igrp irdp irdpresponder netenum netmask protos timestamp; do
		install -Dm755 $binary $pkgdir/usr/bin/$binary || return 1
	done
}
