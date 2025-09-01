# $Id$
# Maintainer: Chupligin Sergey (NeoChapay) <neochapay@gmail.com>

_yearver=2025b
_gitver=2
pkgname=tzdata-timed
pkgver=$_yearver+git$_gitver
pkgrel=1
pkgdesc="Data files for the time daemon, timed"
arch=('x86_64' 'aarch64')
url="https://github.com/sailfishos/tzdata-timed"
license=('Public Domain')
depends=('tzdata')
source=("${url}/archive/refs/tags/$pkgver.tar.gz"
	"0001-Fixes-build.patch")
sha256sums=('db4d206dba09d8a55c15c700b168665823fbba2c2c88686ba213586f43126a8d'
	'dc756a749924c9e2cdf6b7131da3f054ab41e6a2de1c03f18f50ab6c8e4314a9')

prepare() {
  cd $pkgname-$_yearver-git$_gitver
  patch -Np1 -i "${srcdir}/0001-Fixes-build.patch"
}

build() {
  cd $pkgname-$_yearver-git$_gitver
  make
}

package() {
  cd $pkgname-$_yearver-git$_gitver
  make -j 1 PREFIX="$pkgdir/usr" install
}
