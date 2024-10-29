# Maintainer: banhammer
pkgname=warp-terminal
pkgdesc="Warp: The intelligent terminal."
pkgver=0.2024.10.23.14.49.stable.00
_pkgver=0.2024.10.23.14.49.stable_00
pkgrel=1
arch=('x86_64')
source=("https://releases.warp.dev/stable/v${_pkgver}/warp-terminal_${pkgver}_amd64.deb" warp-terminal-bin.desktop warp-terminal.png)
md5sums=('SKIP'
         'a57b804ac5eea9b4e6d5a42b072b8740'
         '31a8d1707a3015c8ff04e5855deb369d')


prepare() {
    mv warp-terminal_${pkgver}_amd64.deb ${pkgname}_${pkgver}.deb
    ar -x ${pkgname}_${pkgver}.deb
    mkdir ${pkgname}-${pkgver}
    tar -xf data.tar.xz --directory="${pkgname}-${pkgver}"
    rm "${srcdir}/${pkgname}-${pkgver}""/usr/share/applications/dev.warp.Warp.desktop"
}


package() {
  cd "$pkgname-$pkgver"
  install -Dm644 ../warp-terminal-bin.desktop ${pkgdir}/usr/share/applications/warp-terminal-bin.desktop
  install -Dm644 ../warp-terminal.png "${pkgdir}"/usr/share/pixmaps/warp-terminal.png
  cp -r ./ ${pkgdir}/
}
