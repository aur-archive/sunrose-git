# Maintainer: Tom Vincent <http://tlvince.com/contact/>
pkgname=sunrose-git
_pkgname=sunrose
pkgver=20130126
pkgrel=1
pkgdesc="A generic themes switcher"
arch=(any)
url="https://github.com/tlvince/sunrose"
license=("MIT")
makedepends=("git")
install="$_pkgname.install"

_gitroot=https://github.com/tlvince/sunrose.git
_gitname=$_pkgname

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [[ -d "$_gitname" ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="$pkgdir" PREFIX="/usr" install
}

# vim:set ts=2 sw=2 et:
