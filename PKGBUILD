# Maintainer: George Boyle <george@thebuds.net>

pkgname=networktablet-system
pkgver=1.5
pkgrel=3
pkgdesc="Linux driver for Android GfxTablet input"
arch=(x86_64 armv7h armv8)
url="http://rfc2822.github.io/GfxTablet/"
license=('GPL3')
conflicts=('networktablet')
source=(
    "https://github.com/rfc2822/GfxTablet/archive/android-app-1.4-linux-driver-$pkgver.tar.gz"
    'networktablet.service'
)
sha512sums=(
    '3f56c4982c95d0be4588424af9c8046e59a4bd7f310738fdc6099a4f93e1b58bf82d8730139167f74d86001e31fd6def20752405c15683ceeb04f7efa3f7c801'
    'a8042d24d9c5b084495a0ebdd94c2115e9ccdce596ccb0c3f03686fbecf7ccff070e1242fef7ea264ffd43f01ef170b97dc0e97aa452cfc2bc5e4a200b62edc9'
)

build() {
  cd GfxTablet-android-app-1.4-linux-driver-$pkgver/driver-uinput/
  make
}

package() {
  install -Dm 644 networktablet.service "$pkgdir/usr/lib/systemd/system/networktablet.service"
  cd GfxTablet-android-app-1.4-linux-driver-$pkgver
  install -D driver-uinput/networktablet "$pkgdir/usr/bin/networktablet"
  install -Dm 644 LICENSE.md "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
