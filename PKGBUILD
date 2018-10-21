# Maintainer: Florian Dejonckheere <florian at floriandejonckheere dot be>
# Contributor: Ronald van Haren <ronald.archlinux.org>
# Contributor: JJDaNiMoTh <jjdanimoth@gmail.com>
# Contributor: nesl247 <nesl247@gmail.com>

_upstream="compizconfig-python"
_pkgver=0.8.14
_micro=""

pkgname=compizconfig-python
pkgver="${_pkgver}${_micro}"
pkgrel=2
pkgdesc="Compizconfig bindings for python"
arch=('i686' 'x86_64')
url="https://gitlab.com/compiz/${_upstream}/"
license=('GPL')
depends=("compiz-core>=v${pkgver}" 'libcompizconfig' 'glib2' 'python' 'libxrandr' 'libsm' 'libxdamage')
makedepends=('cython' 'intltool' 'pkgconfig')
options=('!libtool')
conflicts=('compizconfig-python-git')
source=("${url}-/archive/v${pkgver}/${_upstream}-v${pkgver}.tar.bz2")

build()
{
	cd "${srcdir}/${_upstream}-v${pkgver}"

	NOCONFIGURE=1 ./autogen.sh
	CYTHON=cython2 PYTHON=python ./configure --prefix=/usr
	make
}

package()
{
	cd "${srcdir}/${_upstream}-v${pkgver}"

	make DESTDIR="${pkgdir}" install
}

sha256sums=('49a084a09836cdc4e82e12572411478d34918de07c3d797dfcc2b5c73aa1b654')
