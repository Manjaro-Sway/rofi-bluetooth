# Maintainer: Olegs Jeremejevs <olegs@jeremejevs.com>

_pkgname=rofi-bluetooth
pkgname="${_pkgname}"
pkgver=r20.893db1f
_commit="893db1f2b549e7bc0e9c62e7670314349a29cdf2"
pkgrel=2
pkgdesc='A script that generates a rofi menu that uses bluetoothctl to connect to bluetooth devices and display status info'
arch=('any')
url='https://github.com/ClydeDroid/rofi-bluetooth'
license=('GPL-3.0')
depends=('rofi' 'bluez-utils')
makedepends=('git')
source=("${_pkgname}::git+https://github.com/ClydeDroid/rofi-bluetooth.git#commit=${_commit}")
md5sums=('SKIP')

prepare() {
  cd "${_pkgname}"
  sed -i 's/rofi_command=.*/rofi_command="rofi -dmenu -p"/' rofi-bluetooth
}

pkgver() {
  cd "${_pkgname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "${_pkgname}"
  install -D -m 755 -t "${pkgdir}/usr/bin/" rofi-bluetooth
  install -D -m 644 -t "${pkgdir}/usr/share/licenses/${_pkgname}/" LICENSE
}
