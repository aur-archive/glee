# Maintainer : SpepS <dreamspepser at yahoo dot it>
# Contributor: Philipp Brüschweiler <blei42 at gmail dot com >

pkgname=glee
pkgver=5.4
pkgrel=3
pkgdesc="Free cross-platform extension loading library for OpenGL."
arch=('i686' 'x86_64')
url="http://elf-stone.com/glee.php"
license=('BSD')
depends=('libgl')
source=("http://elf-stone.com/downloads/GLee/GLee-5.4.0-src.tar.gz")
md5sums=('0bd03db136dbc075488b6c6e83f326ae')

build() {
  cd "$srcdir"

  [ "$CARCH" = 'x86_64' ] && export CXXFLAGS="$CXXFLAGS -fPIC"

  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir"

  # lib and headers
  install -Dm755 libGLee.so "$pkgdir/usr/lib/libGLee.so"
  install -Dm644 GLee.h "$pkgdir/usr/include/GLee.h"

  # license
  install -Dm644 readme.txt "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  sed -i '9,32!d' "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et: