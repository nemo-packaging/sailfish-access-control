# $Id$
# Maintainer: TheKit <nekit1000 at gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=sailfish-access-control-git
_pkgname=sailfish-access-control
pkgver=0.0.3.r0.g3926546
pkgrel=1
pkgdesc="Sailfish Access Control library"
arch=('x86_64' 'aarch64')
url="https://git.sailfishos.org/mer-core/sailfish-access-control"
license=('GPL')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://git.sailfishos.org/mer-core/sailfish-access-control.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${_pkgname%-git}"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/${_pkgname%-git}/glib"
	make
}

package() {
	cd "$srcdir/${_pkgname%-git}/glib"
	make ROOT="$pkgdir/" install-libsailfishaccesscontrol
	make ROOT="$pkgdir/" install-libsailfishaccesscontrol-dev
}
