# Maintainer: Nick Smallbone <nick.smallbone@gmail.com>
pkgname=emacs-adoc-mode-git
pkgver=20121020
pkgrel=1
pkgdesc="AsciiDoc mode for Emacs, with plenty of syntax highlighting"
arch=('any')
url="https://github.com/sensorflo/adoc-mode/wiki"
license=('GPL')
depends=('emacs' 'emacs-markup-faces-git')
conflicts=('emacs-adoc-mode-svn')
replaces=('emacs-adoc-mode-svn')
makedepends=('git')
install=emacs-adoc-mode-git.install

_gitroot=git://github.com/sensorflo/adoc-mode.git
_gitname=adoc-mode

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
  cd "$srcdir/$_gitname"
  install -Dm644 adoc-mode.el "$pkgdir/usr/share/emacs/site-lisp/adoc-mode.el"
}
