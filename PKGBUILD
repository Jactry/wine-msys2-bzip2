# Maintainer: Alexey Pavlov <alexpux@gmail.com>

pkgname=('bzip2' 'libbz2' 'libbz2-devel')
pkgver=1.0.6
pkgrel=2
pkgdesc="A high-quality data compression program"
groups=('base' 'compression')
arch=('i686' 'x86_64')
license=('custom')
url="http://sources.redhat.com/bzip2"
makedepends=('gcc' 'make' 'patch')
source=(http://www.bzip.org/$pkgver/bzip2-$pkgver.tar.gz
        bzip2-1.0.6-msys-dll.patch
        bzip2-1.0.6-msys2.patch)
sha1sums=('3f89f861209ce81a6bab1fd1998c0ef311712002'
          '6fb96968691f7e2d0679b26b5e8d71e8886502fd'
          'ad4c11f0abcc229498ae6ef5209556fdf91f0c56')

prepare() {
  cd "$srcdir/$pkgname-$pkgver"

  patch -p1 -i ${srcdir}/bzip2-1.0.6-msys-dll.patch
  patch -p1 -i ${srcdir}/bzip2-1.0.6-msys2.patch
}

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr --enable-shared
  make all
  make PREFIX="${srcdir}/dest" install
}

check() {
  cd "$srcdir/$pkgname-$pkgver"
  make test
}

package_bzip2() {
  depends=('libbz2')

  mkdir -p ${pkgdir}/usr/bin

  cp -f ${srcdir}/dest/bin/b* ${pkgdir}/usr/bin/
  cp -rf ${srcdir}/dest/share ${pkgdir}/usr/

}

package_libbz2() {
  groups=('libraries')
  depends=('gcc-libs')

  mkdir -p ${pkgdir}/usr/bin

  cp -f ${srcdir}/dest/bin/*.dll ${pkgdir}/usr/bin/
}

package_libbz2-devel() {
  pkgdesc="Libbz2 headers and libraries"
  groups=('development')
  options=('staticlibs')
  depends=("libbz2=${pkgver}")

  mkdir -p ${pkgdir}/usr/{include,lib}

  cp -rf ${srcdir}/dest/include ${pkgdir}/usr/
  cp -rf ${srcdir}/dest/lib ${pkgdir}/usr/
}
# Maintainer: Alexey Pavlov <alexpux@gmail.com>

pkgname=('bzip2' 'libbz2' 'libbz2-devel')
pkgver=1.0.6
pkgrel=2
pkgdesc="A high-quality data compression program"
groups=('base' 'compression')
arch=('i686' 'x86_64')
license=('custom')
url="http://sources.redhat.com/bzip2"
makedepends=('gcc' 'make' 'patch')
source=(http://www.bzip.org/$pkgver/bzip2-$pkgver.tar.gz
        bzip2-1.0.6-msys-dll.patch
        bzip2-1.0.6-msys2.patch)
sha1sums=('3f89f861209ce81a6bab1fd1998c0ef311712002'
          '6fb96968691f7e2d0679b26b5e8d71e8886502fd'
          'ad4c11f0abcc229498ae6ef5209556fdf91f0c56')

prepare() {
  cd "$srcdir/$pkgname-$pkgver"

  patch -p1 -i ${srcdir}/bzip2-1.0.6-msys-dll.patch
  patch -p1 -i ${srcdir}/bzip2-1.0.6-msys2.patch
}

build() {
  cd "$srcdir/$pkgname-$pkgver"

  ./configure --prefix=/usr --enable-shared
  make all
  make PREFIX="${srcdir}/dest" install
}

check() {
  cd "$srcdir/$pkgname-$pkgver"
  make test
}

package_bzip2() {
  depends=('libbz2')

  mkdir -p ${pkgdir}/usr/bin

  cp -f ${srcdir}/dest/bin/b* ${pkgdir}/usr/bin/
  cp -rf ${srcdir}/dest/share ${pkgdir}/usr/

}

package_libbz2() {
  groups=('libraries')
  depends=('gcc-libs')

  mkdir -p ${pkgdir}/usr/bin

  cp -f ${srcdir}/dest/bin/*.dll ${pkgdir}/usr/bin/
}

package_libbz2-devel() {
  pkgdesc="Libbz2 headers and libraries"
  groups=('development')
  options=('staticlibs')
  depends=("libbz2=${pkgver}")

  mkdir -p ${pkgdir}/usr/{include,lib}

  cp -rf ${srcdir}/dest/include ${pkgdir}/usr/
  cp -rf ${srcdir}/dest/lib ${pkgdir}/usr/
}
