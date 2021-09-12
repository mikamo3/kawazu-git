# Maintainer: mikamo3 <kamo3proj@gmail.com>
pkgname=kawazu-git
pkgver=r106.07bbcef
pkgrel=1
pkgdesc="A dotfiles manager"
arch=(any)
url="https://github.com/mikamo3/kawazu"
license=('MIT')
groups=()
depends=('git')
makedepends=()
provides=()
conflicts=()
replaces=()
source=("$pkgname"::'git+https://github.com/mikamo3/kawazu.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/${pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$srcdir/${pkgname}"
  mkdir -p "$pkgdir/usr/lib/kawazu"
  mkdir -p $pkgdir/usr/lib/kawazu/{bin,lib}
  mkdir -p "$pkgdir/usr/share/licenses/kawazu-git"
  install -D "./LICENSE" "$pkgdir/usr/share/licenses/kawazu-git"
  install -D "./kawazu.sh" "$pkgdir/usr/lib/kawazu/kawazu.sh"
  install -D "./kawazu.fish" "$pkgdir/usr/lib/kawazu/kawazu.fish"
  install -D "./profile/kawazu_vers.sh" "$pkgdir/etc/profile.d/kawazu_vers.sh"
  install ./bin/* "$pkgdir/usr/lib/kawazu/bin"
  install ./lib/* "$pkgdir/usr/lib/kawazu/lib"
}
