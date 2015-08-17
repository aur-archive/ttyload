# Maintainer: Kyle Keen <keenerd@gmail.com>
# Contributor: Denis Saintilma <1068des@gmail.com>
# Contributor: Steven Susbauer <stupendoussteve@hotmail.com>

pkgname=ttyload
pkgver=0.5.3
pkgrel=1
pkgdesc="A color-coded console load graph."
arch=('i686' 'x86_64')
url="http://www.daveltd.com/src/util/ttyload/"
license=('custom')
depends=('glibc')
source=(http://www.daveltd.com/src/util/ttyload/$pkgname-$pkgver.tar.bz2)
#source=(http://ftp.de.netbsd.org/pub/FreeBSD/ports/distfiles/$pkgname-$pkgver.tar.bz2)
md5sums=('e078fe59d94725ee41155e4d8de49087')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  # bug added in 0.5.3
  sed -i '10i #include <time.h>' ttyload.h
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  install -D -m755 "$pkgname" "$pkgdir/usr/bin/$pkgname"
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

