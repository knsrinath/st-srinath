# Maintainer: knsrinath <knsrinath2005@gmail.com>
pkgname=st-srinath
pkgver=0.8.4
pkgrel=1
pkgdesc="A heavily-patched and customized build of st the Suckless simple terminal from Srinath."
arch=(x86_64)
url="https://github.com/knsrinath/st-srinath.git"
license=('MIT')
groups=()
depends=(ttf-jetbrains-mono)
makedepends=(git make)
checkdepends=()
optdepends=()
provides=(st)
conflicts=(st)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  printf "0.8.4" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd st-srinath
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd st-srinath  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README.md"
}
