# Maintainer: speps <speps at aur dot archlinux dot org>

pkgname=nomacs
pkgver=1.2.0
pkgrel=1
pkgdesc="A Qt image viewer"
arch=(i686 x86_64)
url="http://www.nomacs.org/"
license=('GPL3')
depends=('qt4' 'exiv2' 'libraw' 'opencv')
makedepends=('cmake')
install="$pkgname.install"
source=("http://downloads.sourceforge.net/project/$pkgname/$pkgname-$pkgver/$pkgname-$pkgver-source.tar.bz2")
md5sums=('0fdef67b960276375024f270dfaa4b93')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  [ -d bld ] || mkdir bld && cd bld
  cmake .. -DCMAKE_INSTALL_PREFIX=/usr \
           -DQT_QMAKE_EXECUTABLE=/usr/bin/qmake-qt4
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver/bld"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
