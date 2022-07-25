# $Id$
# Maintainer: Chupligin Sergey (NeoChapay) <neochapay@gmail.com>

pkgname=glacier-devicelock-plugin
pkgver=0.2.1
pkgrel=1
pkgdesc="Glacier devicelock plugin"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/glacier-devicelock-plugin"
license=('LGPL-2.1')
depends=('nemo-qml-plugin-devicelock')
makedepends=('cmake' 'glib2')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('038e4a5392f7fc6dd252c8eefdd66615bd3d90bd91d4c9462465c08339672e60')

build() {
    cd $pkgname-$pkgver
    cmake \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make all
}

package() {
    cd $pkgname-$pkgver
    make DESTDIR="$pkgdir" install
}
