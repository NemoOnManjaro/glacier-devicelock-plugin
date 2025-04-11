# $Id$
# Maintainer: Chupligin Sergey (NeoChapay) <neochapay@gmail.com>

pkgname=glacier-devicelock-plugin
pkgver=0.3.2
pkgrel=1
pkgdesc="Glacier devicelock plugin"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/glacier-devicelock-plugin"
license=('LGPL-2.1')
depends=('nemo-qml-plugin-devicelock')
makedepends=('cmake' 'glib2' 'qt6-tools' 'clang')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('feb9d92b3f20a5822e7a5f29bc230faf6369f6ca0b8ce4f1addd8f0a8a97c2db')

build() {
    cmake \
        -B "${pkgname}-${pkgver}/build" \
        -S "${pkgname}-${pkgver}" \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make -C "${pkgname}-${pkgver}/build" all
}

package() {
    make -C "${srcdir}/${pkgname}-${pkgver}/build" DESTDIR="$pkgdir" install
}
