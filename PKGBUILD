# Maintainer: timescam <rex.ky.ng at gmail dot com>

pkgname=noto-fonts-emoji-apple
pkgver=0
pkgrel=2
pkgdesc="Google Noto emoji fonts replaced with apple branded emoji, modified form a magisk module"
arch=(any)
url="https://gitlab.com/timescam/noto-fonts-emoji-apple"
provides=(emoji-font)
conflicts=(noto-fonts-emoji)
source=("$_pkgname::git+https://gitlab.com/timescam/noto-fonts-emoji-apple.git")
md5sums=("SKIP")

pkgver() {
    cd "$srcdir/$_pkgname"
	git describe --long --tags | sed 's/^v//;s/\([^-]*-g\)/r\1/;s/-/./g'
}

package() {
  cd noto-emoji-*
  mkdir -p "$pkgdir"/usr/share/fonts/noto
  install -m644 NotoColorEmoji.ttf "$pkgdir"/usr/share/fonts/noto

# Install fontconfig files
  mkdir -p "$pkgdir"/etc/fonts/conf.{avail,d}
  install -m644 "$srcdir"/66-noto-color-emoji.conf -t "$pkgdir"/etc/fonts/conf.avail/
  ln -rs "$pkgdir"/etc/fonts/conf.avail/* "$pkgdir"/etc/fonts/conf.d
}