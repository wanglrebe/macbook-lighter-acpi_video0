# Maintainer: wanglrebe <wangxinyi2002@gmail.com>
# Inspired by lighter, many thanks to Janhouse's perl script https://github.com/Janhouse/lighter
pkgname=macbook-lighter-acpi_video0
pkgver=0.0.2.2.gae0c4d2
pkgrel=1
pkgdesc="Macbook screen/keyboard backlight CLI and auto-adjust on ambient light"
arch=(any)
url="https://github.com/wanglrebe/macbook-lighter-acpi_video0"
license=('GPL')
depends=('bc')
makedepends=('git')
provides=()
conflicts=()
source=('git+https://github.com/wanglrebe/macbook-lighter-acpi_video0.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  git describe --tags | sed 's|-|.|g'
}

package() {
  cd "$srcdir/$pkgname"
  [ ! -f $pkgdir/etc/macbook-lighter.conf ] && install -Dm644 macbook-lighter.conf $pkgdir/etc/macbook-lighter.conf
  install -Dm644 "macbook-lighter.service" "$pkgdir/usr/lib/systemd/system/macbook-lighter.service"
  install -Dm755 "src/macbook-lighter-ambient.sh" "$pkgdir/usr/bin/macbook-lighter-ambient"
  install -Dm755 "src/macbook-lighter-screen.sh" "$pkgdir/usr/bin/macbook-lighter-screen"
  install -Dm755 "src/macbook-lighter-kbd.sh" "$pkgdir/usr/bin/macbook-lighter-kbd"
}
