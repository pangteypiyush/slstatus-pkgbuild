# Maintainer: Piyush Pangtey <gokuvsvegita at gmail dot com>

pkgname=slstatus
pkgver=r552.b14e039
pkgrel=1
pkgdesc="slstatus by suckless"
arch=('x86_64')
url="https://tools.suckless.org/slstatus"
license=('ISC')
makedepeds=('base-devel')
source=(
    "git://git.suckless.org/slstatus"
    "config.h"
)
sha256sums=(
    'SKIP'
    'SKIP'
)

pkgver() {
  cd "${pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
    cp config.h "$pkgname"
}

build() {
    make -C "$pkgname"
}

package() {
    make -C "$pkgname" PREFIX="usr/" DESTDIR="$pkgdir/" install
    install -Dm644 "$pkgname/LICENSE" "$pkgdir/usr/share/doc/$pkgname/LICENSE"
    install -Dm644 "$pkgname/README" "$pkgdir/usr/share/doc/$pkgname/README"
}
