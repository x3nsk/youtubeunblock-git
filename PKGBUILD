# Maintainer: none
pkgname=youtubeunblock-git
provides=('youtubeunblock')
pkgver=r30.10006d4
pkgrel=1
pkgdesc="Bypasses Googlevideo detection systems that relies on SNI"
arch=(x86_64)
url=https://github.com/Waujito/youtubeUnblock/
license=(GPL2)
depends=(linux-headers)
makedepends=(gcc make autoconf automake pkgconf)
source=("git+https://github.com/Waujito/youtubeUnblock.git")
#source=("git+https://github.com/Waujito/youtubeUnblock.git#branch=10-tspu-updated")
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/youtubeUnblock"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}


prepare(){
	cd "$srcdir/youtubeUnblock"
	sed -i 's/$(PREFIX)/\/usr/g' ./youtubeUnblock.service
}

build() {
	cd "$srcdir/youtubeUnblock"
	make
}

package() {
	cd "$srcdir/youtubeUnblock"
	make PREFIX="$pkgdir/usr" install
}
