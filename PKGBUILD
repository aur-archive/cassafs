# Maintainer: Michael Ivko <ivko.mv@gmail.com>
pkgname=cassafs
pkgver=0.0.17
pkgrel=3
pkgdesc="Cassandra FUSE filesystem"
url="http://dwerryhouse.com/software/cassafs/"
license=('GPL')
arch=('any')
depends=('python2-fuse' 'python2-pycassa' 'python2-zc-zookeeper-static')
makedepends=('python2-setuptools')
source=(http://dwerryhouse.com/software/cassafs/source/$pkgname-$pkgver.tar.gz)
md5sums=('4c38a54153a0d4789bec86cef048d51b')

prepare() {
    sed -i 's:^#!/usr/bin/env python$:&2:' $pkgname-$pkgver/scripts/mkcassafs
    sed -i 's:^#!/usr/bin/python$:&2:' $pkgname-$pkgver/scripts/cassafs
}

build() {
    cd $pkgname-$pkgver/
    python2 setup.py build
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  python2 setup.py install --root="$pkgdir/" --optimize=1
}

# vim:set ts=2 sw=2 et:
