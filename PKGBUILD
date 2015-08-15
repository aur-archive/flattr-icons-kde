# Maintainer: Ender Fletcher <e2fletcher@gmail.com>

pkgname=flattr-icons-kde
pkgver=0.r272.c62bb1a
pkgrel=2
pkgdesc="Flattr is an icon theme for Linux desktops, the set is inspired by the latest flat design trend."
arch=('i686' 'x86_64')
url="https://github.com/MishkaRogachev/flattr-icons-kde"
license=('CC BY-NC-SA 4.0')
depends=('librsvg')
makedepends=('git')
conflicts=('flattr-icons','flattr-icon-theme','flattr-icon-theme-git', 'flattr-icons-kde-kaosx-git')
provides=('flattr-icon-theme')
source=("$pkgname"::'git+https://github.com/MishkaRogachev/flattr-icons-kde.git')
# Because the sources are not static, skip Git checksum:
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  # Use the tag of the last commit
  printf "0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$srcdir/$pkgname"
  install -d -m 755 "$pkgdir"/usr/share/icons/Flattr
  rm -rf {.git,.gitignore,CONTRIBUTORS,COPYING,CREDITS,LICENSE.txt,README.md}
  cp -r . "$pkgdir"/usr/share/icons/Flattr/
}
