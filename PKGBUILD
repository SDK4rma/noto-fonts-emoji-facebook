# Maintainer: timescam <timescam at duck dot com>

pkgname=noto-fonts-emoji-facebook
_pkgname=noto-fonts-emoji
pkgver=15.4
pkgrel=2
pkgdesc="Google Noto emoji fonts replaced with Facebook branded emoji, modified form a Magisk module"
arch=(any)
url="https://github.com/matmicha/noto-fonts-emoji-facebook"
provides=(emoji-font)
conflicts=(noto-fonts-emoji)
source=("$_pkgname::git+https://github.com/matmicha/noto-fonts-emoji-facebook.git")
md5sums=("SKIP")

package() {
  mkdir -p "$pkgdir"/usr/share/fonts/noto
  install -m644 "$srcdir/$_pkgname/NotoColorEmoji.ttf" "$pkgdir"/usr/share/fonts/noto

# Install fontconfig files
  mkdir -p "$pkgdir"/etc/fonts/conf.{avail,d}
  install -m644 "$srcdir"/$_pkgname/66-noto-color-emoji.conf -t "$pkgdir"/etc/fonts/conf.avail/
  ln -rs "$pkgdir"/etc/fonts/conf.avail/* "$pkgdir"/etc/fonts/conf.d
}
