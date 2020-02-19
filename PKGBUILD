# Maintainer: timescam <rex.ky.ng at gmail dot com>

pkgname=noto-fonts-emoji-apple
pkgver=13.2
pkgrel=1
pkgdesc="Google Noto emoji fonts replaced with apple branded emoji, modified form a magisk module"
arch=(any)
url="https://forum.xda-developers.com/apps/magisk/magisk-ios-13-2-emoji-t3993487"
provides=(emoji-font)
conflicts=(noto-fonts-emoji)
source=(
        66-noto-color-emoji.conf)
md5sums=('10b08759ef07dd07e0d98af410a8acec'
         '18955ae5df80d561bea65564f2d3d30e')

package() {
  cd noto-emoji-*
  mkdir -p "$pkgdir"/usr/share/fonts/noto
  install -m644 NotoColorEmoji.ttf "$pkgdir"/usr/share/fonts/noto

# Install fontconfig files
  mkdir -p "$pkgdir"/etc/fonts/conf.{avail,d}
  install -m644 "$srcdir"/66-noto-color-emoji.conf -t "$pkgdir"/etc/fonts/conf.avail/
  ln -rs "$pkgdir"/etc/fonts/conf.avail/* "$pkgdir"/etc/fonts/conf.d
}